# FTP_SITE::QuerySessionState(ushort const *,ushort * *,ushort * *,_SYSTEMTIME *,ushort * *,_SYSTEMTIME *,ushort * *,unsigned __int64 *,unsigned __int64 *,long *)

- ea: `0x18000a440`
- end: `0x18000a628`
- name: `?QuerySessionState@FTP_SITE@@QEAAJPEBGPEAPEAG1PEAU_SYSTEMTIME@@121PEA_K3PEAJ@Z`
- size: `488`
- prototype: `__int64 __fastcall(FTP_SITE *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, unsigned __int64 *, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016b00`

## callees

- `0x18000a440`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a522`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a522`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a511`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a511`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a575`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a575`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a4d9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a4d9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a584`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a593`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a584`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a593`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SITE::QuerySessionState(
        FTP_SITE *this,
        char *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct _SYSTEMTIME *a5,
        unsigned __int16 **a6,
        struct _SYSTEMTIME *a7,
        unsigned __int16 **a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        int *a11)
{
  CReaderWriterLock3 *v15; // rbp
  char *v16; // rsi
  char *i; // rbx
  __int64 v18; // rax
  char *v19; // r8
  int v20; // ecx
  int v21; // edx
  unsigned int v22; // ebx
  _BYTE v24[56]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v25[56]; // [rsp+C8h] [rbp-A0h] BYREF
  _OWORD v26[2]; // [rsp+100h] [rbp-68h] BYREF
  __int64 v27; // [rsp+120h] [rbp-48h]

  STRU::STRU(v25);
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  STRU::STRU((STRU *)v24, (unsigned __int16 *)v26, 0x14u);
  v15 = (FTP_SITE *)((char *)this + 200);
  CReaderWriterLock3::ReadLock((FTP_SITE *)((char *)this + 200));
  v16 = (char *)this + 240;
  for ( i = (char *)*((_QWORD *)this + 30); ; i = *(char **)i )
  {
    if ( i == v16 )
    {
      v22 = -2147024809;
      goto LABEL_9;
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)i - 14) + 64LL))((_QWORD *)i - 14);
    v19 = &a2[-v18];
    do
    {
      v20 = *(unsigned __int16 *)&v19[v18];
      v21 = *(unsigned __int16 *)v18 - v20;
      if ( v21 )
        break;
      v18 += 2;
    }
    while ( v20 );
    if ( !v21 )
      break;
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 **, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, struct _SYSTEMTIME *, unsigned __int16 **, unsigned __int64 *, unsigned __int64 *, int *))(*((_QWORD *)i - 14) + 56LL))(
          (_QWORD *)i - 14,
          a3,
          a4,
          a5,
          a6,
          a7,
          a8,
          a9,
          a10,
          a11);
LABEL_9:
  CReaderWriterLock3::ReadUnlock(v15);
  STRU::~STRU(v24);
  STRU::~STRU(v25);
  return v22;
}

```

## disassembly

```asm
0x18000a440  mov     [rsp+arg_8], rbx
0x18000a445  push    rbp
0x18000a446  push    rsi
0x18000a447  push    rdi
0x18000a448  push    r12
0x18000a44a  push    r13
0x18000a44c  push    r14
0x18000a44e  push    r15
0x18000a450  sub     rsp, 130h
0x18000a457  mov     rax, cs:__security_cookie
0x18000a45e  xor     rax, rsp
0x18000a461  mov     [rsp+168h+var_40], rax
0x18000a469  mov     r12, r9
0x18000a46c  mov     r15, r8
0x18000a46f  mov     r14, rdx
0x18000a472  mov     rbx, rcx
0x18000a475  mov     r13, [rsp+168h+arg_20]
0x18000a47d  mov     rax, [rsp+168h+arg_28]
0x18000a485  mov     [rsp+168h+var_E0], rax
0x18000a48d  mov     rax, [rsp+168h+arg_30]
0x18000a495  mov     [rsp+168h+var_E8], rax
0x18000a49d  mov     rax, [rsp+168h+arg_38]
0x18000a4a5  mov     [rsp+168h+var_F0], rax
0x18000a4aa  mov     rax, [rsp+168h+arg_40]
0x18000a4b2  mov     [rsp+168h+var_F8], rax
0x18000a4b7  mov     rax, [rsp+168h+arg_48]
0x18000a4bf  mov     [rsp+168h+var_100], rax
0x18000a4c4  mov     rax, [rsp+168h+arg_50]
0x18000a4cc  mov     [rsp+168h+var_108], rax
0x18000a4d1  lea     rcx, [rsp+168h+var_A0]
0x18000a4d9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a4df  nop
0x18000a4e0  xorps   xmm0, xmm0
0x18000a4e3  xor     eax, eax
0x18000a4e5  movups  [rsp+168h+var_68], xmm0
0x18000a4ed  movups  [rsp+168h+var_58], xmm0
0x18000a4f5  mov     [rsp+168h+var_48], rax
0x18000a4fd  lea     r8d, [rax+14h]
0x18000a501  lea     rdx, [rsp+168h+var_68]
0x18000a509  lea     rcx, [rsp+168h+var_D8]
0x18000a511  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a517  nop
0x18000a518  lea     rbp, [rbx+0C8h]
0x18000a51f  mov     rcx, rbp
0x18000a522  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000a528  lea     rsi, [rbx+0F0h]
0x18000a52f  mov     rbx, [rsi]
0x18000a532  jmp     short loc_18000A568
0x18000a534  lea     rdi, [rbx-70h]
0x18000a538  mov     rax, [rdi]
0x18000a53b  mov     rcx, rdi
0x18000a53e  mov     rax, [rax+40h]
0x18000a542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a547  mov     r8, r14
0x18000a54a  sub     r8, rax
0x18000a54d  movzx   edx, word ptr [rax]
0x18000a550  movzx   ecx, word ptr [rax+r8]
0x18000a555  sub     edx, ecx
0x18000a557  jnz     short loc_18000A561
0x18000a559  add     rax, 2
0x18000a55d  test    ecx, ecx
0x18000a55f  jnz     short loc_18000A54D
0x18000a561  test    edx, edx
0x18000a563  jz      short loc_18000A5C6
0x18000a565  mov     rbx, [rbx]
0x18000a568  cmp     rbx, rsi
0x18000a56b  jnz     short loc_18000A534
0x18000a56d  mov     ebx, 80070057h
0x18000a572  mov     rcx, rbp
0x18000a575  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a57b  nop
0x18000a57c  lea     rcx, [rsp+168h+var_D8]
0x18000a584  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a58a  nop
0x18000a58b  lea     rcx, [rsp+168h+var_A0]
0x18000a593  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a599  mov     eax, ebx
0x18000a59b  mov     rcx, [rsp+168h+var_40]
0x18000a5a3  xor     rcx, rsp; StackCookie
0x18000a5a6  call    __security_check_cookie
0x18000a5ab  mov     rbx, [rsp+168h+arg_8]
0x18000a5b3  add     rsp, 130h
0x18000a5ba  pop     r15
0x18000a5bc  pop     r14
0x18000a5be  pop     r13
0x18000a5c0  pop     r12
0x18000a5c2  pop     rdi
0x18000a5c3  pop     rsi
0x18000a5c4  pop     rbp
0x18000a5c5  retn
0x18000a5c6  mov     rax, [rdi]
0x18000a5c9  mov     rcx, [rsp+168h+var_108]
0x18000a5ce  mov     [rsp+168h+var_120], rcx
0x18000a5d3  mov     rcx, [rsp+168h+var_100]
0x18000a5d8  mov     [rsp+168h+var_128], rcx
0x18000a5dd  mov     rcx, [rsp+168h+var_F8]
0x18000a5e2  mov     [rsp+168h+var_130], rcx
0x18000a5e7  mov     rcx, [rsp+168h+var_F0]
0x18000a5ec  mov     [rsp+168h+var_138], rcx
0x18000a5f1  mov     rcx, [rsp+168h+var_E8]
0x18000a5f9  mov     [rsp+168h+var_140], rcx
0x18000a5fe  mov     rcx, [rsp+168h+var_E0]
0x18000a606  mov     [rsp+168h+var_148], rcx
0x18000a60b  mov     r9, r13
0x18000a60e  mov     r8, r12
0x18000a611  mov     rdx, r15
0x18000a614  mov     rcx, rdi
0x18000a617  mov     rax, [rax+38h]
0x18000a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a620  mov     ebx, eax
0x18000a622  jmp     loc_18000A572
```
