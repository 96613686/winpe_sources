# CacheDirMonitorEntry::FileChanged(ushort *)

- ea: `0x180008d60`
- end: `0x180008f09`
- name: `?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z`
- size: `425`
- prototype: `void(CacheDirMonitorEntry *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008c10`

## callees

- `0x180008d60`
- `0x18000a340`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `msvcrt!wcschr` at `0x180008dbb`
- `msvcrt!wcschr` at `0x180008dbb`
- `msvcrt!_wcsupr` at `0x180008e71`
- `msvcrt!_wcsupr` at `0x180008e71`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008ec4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008ec4`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008df9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008e1e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008df9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008e1e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e10`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e68`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e7c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e10`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e68`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008e7c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008de0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008de0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008dad`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008dad`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e59`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008e59`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008e47`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008e47`

## pseudocode

```c
void __fastcall CacheDirMonitorEntry::FileChanged(const unsigned __int16 **this, unsigned __int16 *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rcx
  unsigned __int16 *v6; // rdi
  wchar_t *Str; // rax
  char *v8; // rcx
  _QWORD v9[3]; // [rsp+20h] [rbp-288h] BYREF
  int v10; // [rsp+38h] [rbp-270h]
  _BYTE v11[64]; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v12[264]; // [rsp+80h] [rbp-228h] BYREF

  memset_0(v12, 0, 0x208u);
  STRU::STRU((STRU *)v11, v12, 0x104u);
  v4 = wcschr(a2, 0x7Eu);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > a2 )
    {
      do
      {
        if ( *v5 == 92 )
          break;
        --v5;
      }
      while ( v5 > a2 );
    }
    *v5 = 0;
  }
  if ( (int)STRU::Copy((STRU *)v11, this[2]) >= 0 )
  {
    if ( !*a2
      || (STRU::QueryCCH((STRU *)v11) && (v6 = STRU::QueryStr((STRU *)v11), v6[STRU::QueryCCH((STRU *)v11) - 1] == 92)
       || (int)STRU::Append((STRU *)v11, L"\\", 1u) >= 0)
      && (int)STRU::Append((STRU *)v11, a2) >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v11);
      _wcsupr(Str);
      v9[1] = STRU::QueryStr((STRU *)v11);
      v9[0] = &FileChangeProvider::`vftable';
      v8 = (char *)(this + 14);
      v10 = 0;
      if ( !this )
        v8 = 0;
      v9[2] = v8;
      W3_SERVER::GlobalNotify((__int64)g_pW3Server, 0x80u, (__int64)v9);
    }
  }
  STRU::~STRU((STRU *)v11);
}

```

## disassembly

```asm
0x180008d60  mov     [rsp+arg_18], rbx
0x180008d65  push    rsi
0x180008d66  sub     rsp, 2A0h
0x180008d6d  mov     rax, cs:__security_cookie
0x180008d74  xor     rax, rsp
0x180008d77  mov     [rsp+2A8h+var_18], rax
0x180008d7f  mov     rbx, rdx
0x180008d82  mov     rsi, rcx
0x180008d85  xor     edx, edx; Val
0x180008d87  lea     rcx, [rsp+2A8h+var_228]; void *
0x180008d8f  mov     r8d, 208h; Size
0x180008d95  call    memset_0
0x180008d9a  mov     r8d, 104h
0x180008da0  lea     rdx, [rsp+2A8h+var_228]
0x180008da8  lea     rcx, [rsp+2A8h+var_268]
0x180008dad  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008db3  mov     edx, 7Eh ; '~'; Ch
0x180008db8  mov     rcx, rbx; Str
0x180008dbb  call    cs:__imp_wcschr
0x180008dc1  mov     rcx, rax
0x180008dc4  test    rax, rax
0x180008dc7  jz      short loc_180008DD7
0x180008dc9  cmp     rax, rbx
0x180008dcc  ja      loc_180008EF0
0x180008dd2  xor     eax, eax
0x180008dd4  mov     [rcx], ax
0x180008dd7  mov     rdx, [rsi+10h]
0x180008ddb  lea     rcx, [rsp+2A8h+var_268]
0x180008de0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008de6  test    eax, eax
0x180008de8  js      loc_180008EBF
0x180008dee  cmp     word ptr [rbx], 0
0x180008df2  jz      short loc_180008E63
0x180008df4  lea     rcx, [rsp+2A8h+var_268]
0x180008df9  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008dff  test    eax, eax
0x180008e01  jz      short loc_180008E35
0x180008e03  lea     rcx, [rsp+2A8h+var_268]
0x180008e08  mov     [rsp+2A8h+arg_10], rdi
0x180008e10  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008e16  lea     rcx, [rsp+2A8h+var_268]
0x180008e1b  mov     rdi, rax
0x180008e1e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008e24  dec     eax
0x180008e26  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180008e2b  mov     rdi, [rsp+2A8h+arg_10]
0x180008e33  jz      short loc_180008E51
0x180008e35  mov     r8d, 1
0x180008e3b  lea     rdx, asc_180039114; "\\"
0x180008e42  lea     rcx, [rsp+2A8h+var_268]
0x180008e47  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180008e4d  test    eax, eax
0x180008e4f  js      short loc_180008EBF
0x180008e51  mov     rdx, rbx
0x180008e54  lea     rcx, [rsp+2A8h+var_268]
0x180008e59  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008e5f  test    eax, eax
0x180008e61  js      short loc_180008EBF
0x180008e63  lea     rcx, [rsp+2A8h+var_268]
0x180008e68  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008e6e  mov     rcx, rax; String
0x180008e71  call    cs:__imp__wcsupr
0x180008e77  lea     rcx, [rsp+2A8h+var_268]
0x180008e7c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008e82  mov     [rsp+2A8h+var_280], rax
0x180008e87  lea     rcx, ??_7FileChangeProvider@@6B@; const FileChangeProvider::`vftable'
0x180008e8e  mov     [rsp+2A8h+var_288], rcx
0x180008e93  mov     edx, 80h
0x180008e98  xor     eax, eax
0x180008e9a  lea     rcx, [rsi+70h]
0x180008e9e  test    rsi, rsi
0x180008ea1  mov     [rsp+2A8h+var_270], eax
0x180008ea5  lea     r8, [rsp+2A8h+var_288]
0x180008eaa  cmovz   rcx, rax
0x180008eae  mov     [rsp+2A8h+var_278], rcx
0x180008eb3  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180008eba  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x180008ebf  lea     rcx, [rsp+2A8h+var_268]
0x180008ec4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008eca  mov     rcx, [rsp+2A8h+var_18]
0x180008ed2  xor     rcx, rsp; StackCookie
0x180008ed5  call    __security_check_cookie
0x180008eda  mov     rbx, [rsp+2A8h+arg_18]
0x180008ee2  add     rsp, 2A0h
0x180008ee9  pop     rsi
0x180008eea  retn
0x180008ef0  cmp     word ptr [rcx], 5Ch ; '\'
0x180008ef4  jz      loc_180008DD2
0x180008efa  sub     rcx, 2
0x180008efe  cmp     rcx, rbx
0x180008f01  jbe     loc_180008DD2
0x180008f07  jmp     short loc_180008EF0
```
