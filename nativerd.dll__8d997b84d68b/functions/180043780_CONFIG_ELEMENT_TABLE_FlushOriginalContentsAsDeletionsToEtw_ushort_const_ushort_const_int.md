# CONFIG_ELEMENT_TABLE::FlushOriginalContentsAsDeletionsToEtw(ushort const *,ushort const *,int)

- ea: `0x180043780`
- end: `0x1800438f6`
- name: `?FlushOriginalContentsAsDeletionsToEtw@CONFIG_ELEMENT_TABLE@@QEAAJPEBG0H@Z`
- size: `374`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT_TABLE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045578`

## callees

- `0x18003618c`
- `0x180043780`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800438ac`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800438ac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800438c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800438c3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180043847`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180043864`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180043847`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180043864`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800437dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800437dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004380c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004380c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180043824`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180043824`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800437e7`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800437e7`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT_TABLE::FlushOriginalContentsAsDeletionsToEtw(
        CONFIG_ELEMENT_TABLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v4; // r12d
  int v5; // r15d
  int v8; // ebx
  const unsigned __int16 *i; // rdi
  unsigned __int16 *Str; // rax
  __int64 *v11; // rdx
  const WCHAR *v12; // rcx
  _BYTE v14[64]; // [rsp+50h] [rbp-108h] BYREF
  unsigned __int16 v15[64]; // [rsp+90h] [rbp-C8h] BYREF

  v4 = (int)a3;
  v5 = (int)a2;
  v8 = 0;
  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v14, v15, 0x40u);
  for ( i = MULTISZ::First((CONFIG_ELEMENT_TABLE *)((char *)this + 40));
        i;
        i = MULTISZ::Next((CONFIG_ELEMENT_TABLE *)((char *)this + 40), i) )
  {
    v8 = STRU::Copy((STRU *)v14, L"/");
    if ( v8 < 0 )
      break;
    v8 = STRU::Append((STRU *)v14, i);
    if ( v8 < 0 )
      break;
    if ( a4 )
    {
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x40) != 0 )
      {
        Str = STRU::QueryStr((STRU *)v14);
        v11 = NATIVERD_EVENT_CONFIGURATION_WRITE_SUCCESS;
LABEL_9:
        v12 = &szDomain;
        if ( *((_QWORD *)this + 12) )
          v12 = (const WCHAR *)*((_QWORD *)this + 12);
        McTemplateU0zzzzqzz_EtwEventWriteTransfer(
          (_DWORD)v12,
          (_DWORD)v11,
          v5,
          v4,
          (__int64)v12,
          (__int64)Str,
          2,
          (__int64)&szDomain,
          (__int64)&szDomain);
      }
    }
    else if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
    {
      Str = STRU::QueryStr((STRU *)v14);
      v11 = NATIVERD_EVENT_CONFIGURATION_WRITE_FAILURE;
      goto LABEL_9;
    }
  }
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043780  mov     [rsp+arg_18], rbx
0x180043785  push    rbp
0x180043786  push    rsi
0x180043787  push    rdi
0x180043788  push    r12
0x18004378a  push    r13
0x18004378c  push    r14
0x18004378e  push    r15
0x180043790  sub     rsp, 120h
0x180043797  mov     rax, cs:__security_cookie
0x18004379e  xor     rax, rsp
0x1800437a1  mov     [rsp+158h+var_48], rax
0x1800437a9  mov     r12, r8
0x1800437ac  mov     r15, rdx
0x1800437af  mov     rsi, rcx
0x1800437b2  xor     edx, edx; Val
0x1800437b4  mov     r8d, 80h; Size
0x1800437ba  lea     rcx, [rsp+158h+var_C8]; void *
0x1800437c2  mov     r14d, r9d
0x1800437c5  xor     ebx, ebx
0x1800437c7  call    memset_0
0x1800437cc  lea     r8d, [rbx+40h]
0x1800437d0  lea     rdx, [rsp+158h+var_C8]
0x1800437d8  lea     rcx, [rsp+158h+var_108]
0x1800437dd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800437e3  lea     rcx, [rsi+28h]
0x1800437e7  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x1800437ed  mov     rdi, rax
0x1800437f0  test    rax, rax
0x1800437f3  jz      loc_1800438BE
0x1800437f9  lea     r13, szDomain
0x180043800  lea     rdx, asc_18005F044; "/"
0x180043807  lea     rcx, [rsp+158h+var_108]
0x18004380c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180043812  mov     ebx, eax
0x180043814  test    eax, eax
0x180043816  js      loc_1800438BE
0x18004381c  mov     rdx, rdi
0x18004381f  lea     rcx, [rsp+158h+var_108]
0x180043824  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18004382a  mov     ebx, eax
0x18004382c  test    eax, eax
0x18004382e  js      loc_1800438BE
0x180043834  test    r14d, r14d
0x180043837  jz      short loc_180043856
0x180043839  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 40h
0x180043840  jz      short loc_1800438A5
0x180043842  lea     rcx, [rsp+158h+var_108]
0x180043847  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004384d  lea     rdx, NATIVERD_EVENT_CONFIGURATION_WRITE_SUCCESS
0x180043854  jmp     short loc_180043871
0x180043856  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x18004385d  jz      short loc_1800438A5
0x18004385f  lea     rcx, [rsp+158h+var_108]
0x180043864  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004386a  lea     rdx, NATIVERD_EVENT_CONFIGURATION_WRITE_FAILURE
0x180043871  cmp     qword ptr [rsi+60h], 0
0x180043876  mov     rcx, r13
0x180043879  mov     [rsp+158h+var_118], r13
0x18004387e  mov     r9, r12
0x180043881  cmovnz  rcx, [rsi+60h]
0x180043886  mov     r8, r15
0x180043889  mov     [rsp+158h+var_120], r13
0x18004388e  mov     [rsp+158h+var_128], 2
0x180043896  mov     [rsp+158h+var_130], rax
0x18004389b  mov     [rsp+158h+var_138], rcx
0x1800438a0  call    McTemplateU0zzzzqzz_EtwEventWriteTransfer
0x1800438a5  mov     rdx, rdi
0x1800438a8  lea     rcx, [rsi+28h]
0x1800438ac  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800438b2  mov     rdi, rax
0x1800438b5  test    rax, rax
0x1800438b8  jnz     loc_180043800
0x1800438be  lea     rcx, [rsp+158h+var_108]
0x1800438c3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800438c9  mov     eax, ebx
0x1800438cb  mov     rcx, [rsp+158h+var_48]
0x1800438d3  xor     rcx, rsp; StackCookie
0x1800438d6  call    __security_check_cookie
0x1800438db  mov     rbx, [rsp+158h+arg_18]
0x1800438e3  add     rsp, 120h
0x1800438ea  pop     r15
0x1800438ec  pop     r14
0x1800438ee  pop     r13
0x1800438f0  pop     r12
0x1800438f2  pop     rdi
0x1800438f3  pop     rsi
0x1800438f4  pop     rbp
0x1800438f5  retn
```
