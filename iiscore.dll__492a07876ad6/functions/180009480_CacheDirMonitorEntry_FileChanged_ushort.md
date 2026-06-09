# CacheDirMonitorEntry::FileChanged(ushort *)

- ea: `0x180009480`
- end: `0x180009679`
- name: `?FileChanged@CacheDirMonitorEntry@@AEAAXPEAG@Z`
- size: `505`
- prototype: `void __fastcall(const unsigned __int16 **this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009310`

## callees

- `0x180009480`
- `0x18000ac10`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `msvcrt!wcschr` at `0x1800094e1`
- `msvcrt!wcschr` at `0x1800094e1`
- `msvcrt!_wcsupr` at `0x1800095cf`
- `msvcrt!_wcsupr` at `0x1800095cf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000962e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000962e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000952f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009560`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000952f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009560`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000954c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095c0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000954c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095c0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095e0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000950c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000950c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800094cd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800094cd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800095ab`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800095ab`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000958f`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000958f`

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
      W3_SERVER::GlobalNotify(g_pW3Server, 128, v9);
    }
  }
  STRU::~STRU((STRU *)v11);
}

```

## disassembly

```asm
0x180009480  mov     [rsp+arg_18], rbx
0x180009485  push    rsi
0x180009486  sub     rsp, 2A0h
0x18000948d  mov     rax, cs:__security_cookie
0x180009494  xor     rax, rsp
0x180009497  mov     [rsp+2A8h+var_18], rax
0x18000949f  mov     rbx, rdx
0x1800094a2  mov     rsi, rcx
0x1800094a5  xor     edx, edx; Val
0x1800094a7  lea     rcx, [rsp+2A8h+var_228]; void *
0x1800094af  mov     r8d, 208h; Size
0x1800094b5  call    memset_0
0x1800094ba  mov     r8d, 104h
0x1800094c0  lea     rdx, [rsp+2A8h+var_228]
0x1800094c8  lea     rcx, [rsp+2A8h+var_268]
0x1800094cd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800094d4  nop     dword ptr [rax+rax+00h]
0x1800094d9  mov     edx, 7Eh ; '~'; Ch
0x1800094de  mov     rcx, rbx; Str
0x1800094e1  call    cs:__imp_wcschr
0x1800094e8  nop     dword ptr [rax+rax+00h]
0x1800094ed  mov     rcx, rax
0x1800094f0  test    rax, rax
0x1800094f3  jz      short loc_180009503
0x1800094f5  cmp     rax, rbx
0x1800094f8  ja      loc_180009660
0x1800094fe  xor     eax, eax
0x180009500  mov     [rcx], ax
0x180009503  mov     rdx, [rsi+10h]
0x180009507  lea     rcx, [rsp+2A8h+var_268]
0x18000950c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009513  nop     dword ptr [rax+rax+00h]
0x180009518  test    eax, eax
0x18000951a  js      loc_180009629
0x180009520  cmp     word ptr [rbx], 0
0x180009524  jz      loc_1800095BB
0x18000952a  lea     rcx, [rsp+2A8h+var_268]
0x18000952f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180009536  nop     dword ptr [rax+rax+00h]
0x18000953b  test    eax, eax
0x18000953d  jz      short loc_18000957D
0x18000953f  lea     rcx, [rsp+2A8h+var_268]
0x180009544  mov     [rsp+2A8h+arg_10], rdi
0x18000954c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009553  nop     dword ptr [rax+rax+00h]
0x180009558  lea     rcx, [rsp+2A8h+var_268]
0x18000955d  mov     rdi, rax
0x180009560  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180009567  nop     dword ptr [rax+rax+00h]
0x18000956c  dec     eax
0x18000956e  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180009573  mov     rdi, [rsp+2A8h+arg_10]
0x18000957b  jz      short loc_1800095A3
0x18000957d  mov     r8d, 1
0x180009583  lea     rdx, asc_18003C114; "\\"
0x18000958a  lea     rcx, [rsp+2A8h+var_268]
0x18000958f  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180009596  nop     dword ptr [rax+rax+00h]
0x18000959b  test    eax, eax
0x18000959d  js      loc_180009629
0x1800095a3  mov     rdx, rbx
0x1800095a6  lea     rcx, [rsp+2A8h+var_268]
0x1800095ab  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800095b2  nop     dword ptr [rax+rax+00h]
0x1800095b7  test    eax, eax
0x1800095b9  js      short loc_180009629
0x1800095bb  lea     rcx, [rsp+2A8h+var_268]
0x1800095c0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095c7  nop     dword ptr [rax+rax+00h]
0x1800095cc  mov     rcx, rax; String
0x1800095cf  call    cs:__imp__wcsupr
0x1800095d6  nop     dword ptr [rax+rax+00h]
0x1800095db  lea     rcx, [rsp+2A8h+var_268]
0x1800095e0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095e7  nop     dword ptr [rax+rax+00h]
0x1800095ec  mov     [rsp+2A8h+var_280], rax
0x1800095f1  lea     rcx, ??_7FileChangeProvider@@6B@; const FileChangeProvider::`vftable'
0x1800095f8  mov     [rsp+2A8h+var_288], rcx
0x1800095fd  mov     edx, 80h
0x180009602  xor     eax, eax
0x180009604  lea     rcx, [rsi+70h]
0x180009608  test    rsi, rsi
0x18000960b  mov     [rsp+2A8h+var_270], eax
0x18000960f  lea     r8, [rsp+2A8h+var_288]
0x180009614  cmovz   rcx, rax
0x180009618  mov     [rsp+2A8h+var_278], rcx
0x18000961d  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180009624  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x180009629  lea     rcx, [rsp+2A8h+var_268]
0x18000962e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009635  nop     dword ptr [rax+rax+00h]
0x18000963a  mov     rcx, [rsp+2A8h+var_18]
0x180009642  xor     rcx, rsp; StackCookie
0x180009645  call    __security_check_cookie
0x18000964a  mov     rbx, [rsp+2A8h+arg_18]
0x180009652  add     rsp, 2A0h
0x180009659  pop     rsi
0x18000965a  retn
0x180009660  cmp     word ptr [rcx], 5Ch ; '\'
0x180009664  jz      loc_1800094FE
0x18000966a  sub     rcx, 2
0x18000966e  cmp     rcx, rbx
0x180009671  jbe     loc_1800094FE
0x180009677  jmp     short loc_180009660
```
