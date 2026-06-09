# MsoCreateLogonIdAcl(ulong)

- ea: `0x180122ea8`
- end: `0x180122f4c`
- name: `?MsoCreateLogonIdAcl@@YAPEAU_ACL@@K@Z`
- size: `164`
- prototype: `struct _ACL *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1801228e0`

## callees

- `0x1800264b4`
- `0x180122b28`
- `0x180122d2c`
- `0x180122ea8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180122ec1`
- `KERNEL32!GetCurrentProcess` at `0x180122ec1`
- `KERNEL32!CloseHandle` at `0x180122f15`
- `KERNEL32!CloseHandle` at `0x180122f15`
- `ADVAPI32!OpenProcessToken` at `0x180122ed4`
- `ADVAPI32!OpenProcessToken` at `0x180122ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _ACL *__fastcall MsoCreateLogonIdAcl(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  struct _ACL *result; // rax
  HANDLE CurrentProcess; // rax
  void **v7; // rdx
  __int64 v8; // rcx
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF
  void *v10; // [rsp+50h] [rbp+18h] BYREF

  v4 = (int)a1;
  result = (struct _ACL *)vpLogonIdSID;
  if ( vpLogonIdSID )
  {
LABEL_11:
    LODWORD(TokenHandle) = v4;
    v10 = result;
    return MsoCreateAcl(a1, a2, (DWORD *)&TokenHandle, a4, &v10);
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) && TokenHandle )
  {
    if ( FGetLogonSID(TokenHandle, v7) )
      goto LABEL_8;
    v8 = 1422169;
  }
  else
  {
    v8 = 1422168;
  }
  MsoShipAssertTagProc(v8);
LABEL_8:
  a1 = (unsigned int *)TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(a1);
  }
  result = (struct _ACL *)vpLogonIdSID;
  if ( vpLogonIdSID )
    goto LABEL_11;
  return result;
}

```

## disassembly

```asm
0x180122ea8  push    rbx
0x180122eaa  sub     rsp, 30h
0x180122eae  mov     ebx, ecx
0x180122eb0  mov     rax, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x180122eb7  test    rax, rax
0x180122eba  jnz     short loc_180122F28
0x180122ebc  mov     [rsp+38h+TokenHandle], rax
0x180122ec1  call    cs:__imp_GetCurrentProcess
0x180122ec7  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180122ecc  mov     edx, 8; DesiredAccess
0x180122ed1  mov     rcx, rax; ProcessHandle
0x180122ed4  call    cs:__imp_OpenProcessToken
0x180122eda  test    eax, eax
0x180122edc  jz      short loc_180122EF8
0x180122ede  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180122ee3  test    rcx, rcx
0x180122ee6  jz      short loc_180122EF8
0x180122ee8  call    ?FGetLogonSID@@YA_NPEAXPEAPEAX@Z; FGetLogonSID(void *,void * *)
0x180122eed  test    al, al
0x180122eef  jnz     short loc_180122F02
0x180122ef1  mov     ecx, 15B359h
0x180122ef6  jmp     short loc_180122EFD
0x180122ef8  mov     ecx, 15B358h
0x180122efd  call    MsoShipAssertTagProc
0x180122f02  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180122f07  test    rcx, rcx
0x180122f0a  jz      short loc_180122F1C
0x180122f0c  mov     [rsp+38h+TokenHandle], 0
0x180122f15  call    cs:__imp_CloseHandle
0x180122f1b  nop
0x180122f1c  mov     rax, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x180122f23  test    rax, rax
0x180122f26  jz      short loc_180122F46
0x180122f28  mov     dword ptr [rsp+38h+TokenHandle], ebx
0x180122f2c  mov     [rsp+38h+arg_10], rax
0x180122f31  lea     rax, [rsp+38h+arg_10]
0x180122f36  mov     [rsp+38h+var_18], rax; void **
0x180122f3b  lea     r8, [rsp+38h+TokenHandle]; unsigned int *
0x180122f40  call    ?MsoCreateAcl@@YAPEAU_ACL@@QEBKH0HQEAPEAX@Z; MsoCreateAcl(ulong const * const,int,ulong const * const,int,void * * const)
0x180122f45  nop
0x180122f46  add     rsp, 30h
0x180122f4a  pop     rbx
0x180122f4b  retn
```
