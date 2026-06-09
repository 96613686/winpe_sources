# CMDCOM::ComMDBackupWithPasswdW(ulong,ushort const *,ulong,ulong,ushort const *)

- ea: `0x1800162d0`
- end: `0x180016387`
- name: `?ComMDBackupWithPasswdW@CMDCOM@@UEAAJKPEBGKK0@Z`
- size: `183`
- prototype: `int(CMDCOM *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015e30`
- `0x1800162d0`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180016314`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180016314`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001632a`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001632a`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016306`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016306`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001635c`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001635c`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDBackupWithPasswdW(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  unsigned int v9; // ebx
  char *StrA; // rax
  CMDCOM *v11; // rcx
  _BYTE v13[128]; // [rsp+40h] [rbp-A8h] BYREF

  STRAU::STRAU((STRAU *)v13);
  if ( STRAU::Copy((STRAU *)v13, a6) )
  {
    StrA = STRAU::QueryStrA((STRAU *)v13);
    v9 = CMDCOM::ComMDBackupD(v11, a2, a3, a4, a5, 1, StrA);
  }
  else
  {
    v9 = -2147024882;
  }
  STRAU::~STRAU((STRAU *)v13);
  return v9;
}

```

## disassembly

```asm
0x1800162d0  mov     [rsp+arg_0], rbx
0x1800162d5  push    rbp
0x1800162d6  push    rsi
0x1800162d7  push    rdi
0x1800162d8  sub     rsp, 0D0h
0x1800162df  mov     rax, cs:__security_cookie
0x1800162e6  xor     rax, rsp
0x1800162e9  mov     [rsp+0E8h+var_28], rax
0x1800162f1  mov     rbx, [rsp+0E8h+arg_28]
0x1800162f9  lea     rcx, [rsp+0E8h+var_A8]
0x1800162fe  mov     ebp, r9d
0x180016301  mov     rsi, r8
0x180016304  mov     edi, edx
0x180016306  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18001630c  mov     rdx, rbx
0x18001630f  lea     rcx, [rsp+0E8h+var_A8]
0x180016314  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x18001631a  test    eax, eax
0x18001631c  jnz     short loc_180016325
0x18001631e  mov     ebx, 8007000Eh
0x180016323  jmp     short loc_180016357
0x180016325  lea     rcx, [rsp+0E8h+var_A8]
0x18001632a  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180016330  mov     [rsp+0E8h+var_B8], rax; char *
0x180016335  mov     r9d, ebp; unsigned int
0x180016338  mov     eax, [rsp+0E8h+arg_20]
0x18001633f  mov     r8, rsi; char *
0x180016342  mov     [rsp+0E8h+var_C0], 1; int
0x18001634a  mov     edx, edi; unsigned int
0x18001634c  mov     [rsp+0E8h+var_C8], eax; unsigned int
0x180016350  call    ?ComMDBackupD@CMDCOM@@QEAAJKPEADKKH0@Z; CMDCOM::ComMDBackupD(ulong,char *,ulong,ulong,int,char *)
0x180016355  mov     ebx, eax
0x180016357  lea     rcx, [rsp+0E8h+var_A8]
0x18001635c  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180016362  mov     eax, ebx
0x180016364  mov     rcx, [rsp+0E8h+var_28]
0x18001636c  xor     rcx, rsp; StackCookie
0x18001636f  call    __security_check_cookie
0x180016374  mov     rbx, [rsp+0E8h+arg_0]
0x18001637c  add     rsp, 0D0h
0x180016383  pop     rdi
0x180016384  pop     rsi
0x180016385  pop     rbp
0x180016386  retn
```
