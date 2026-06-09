# SameAsProcessSid(void *)

- ea: `0x180017a6c`
- end: `0x180017c1d`
- name: `?SameAsProcessSid@@YAHPEAX@Z`
- size: `433`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180017728`

## callees

- `0x1800087f8`
- `0x18000da78`
- `0x180017a6c`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x180017aea`
- `msvcrt!free` at `0x180017b65`
- `msvcrt!free` at `0x180017be5`
- `msvcrt!free` at `0x180017c0c`
- `msvcrt!free` at `0x180017aea`
- `msvcrt!free` at `0x180017b65`
- `msvcrt!free` at `0x180017be5`
- `msvcrt!free` at `0x180017c0c`
- `ADVAPI32!EqualSid` at `0x180017bf7`
- `ADVAPI32!EqualSid` at `0x180017bf7`
- `ADVAPI32!GetTokenInformation` at `0x180017b16`
- `ADVAPI32!GetTokenInformation` at `0x180017b96`
- `ADVAPI32!GetTokenInformation` at `0x180017b16`
- `ADVAPI32!GetTokenInformation` at `0x180017b96`
- `ADVAPI32!OpenProcessToken` at `0x180017a9c`
- `ADVAPI32!OpenProcessToken` at `0x180017a9c`
- `KERNEL32!GetCurrentProcess` at `0x180017a8a`
- `KERNEL32!GetCurrentProcess` at `0x180017a8a`
- `KERNEL32!GetLastError` at `0x180017aa6`
- `KERNEL32!GetLastError` at `0x180017b1c`
- `KERNEL32!GetLastError` at `0x180017ba0`
- `KERNEL32!GetLastError` at `0x180017aa6`
- `KERNEL32!GetLastError` at `0x180017b1c`
- `KERNEL32!GetLastError` at `0x180017ba0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SameAsProcessSid(PSID pSid1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v5; // eax
  PSID *v6; // rbx
  DWORD v7; // eax
  unsigned int v8; // edi
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  PSID *v11; // [rsp+68h] [rbp+38h]

  v11 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids, LastError);
LABEL_5:
    CHandle::~CHandle((CHandle *)&TokenHandle);
    free(0);
    return 0;
  }
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v5 = GetLastError();
  if ( v5 != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids, v5);
    goto LABEL_5;
  }
  v6 = (PSID *)MmAllocate(TokenInformationLength);
  v11 = v6;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids, v7);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    free(v6);
    return 0;
  }
  v8 = EqualSid(pSid1, *v6);
  CHandle::~CHandle((CHandle *)&TokenHandle);
  free(v6);
  return v8;
}

```

## disassembly

```asm
0x180017a6c  push    rbp
0x180017a6e  push    rbx
0x180017a6f  push    rdi
0x180017a70  mov     rbp, rsp
0x180017a73  sub     rsp, 30h
0x180017a77  mov     rdi, rcx
0x180017a7a  mov     [rbp+arg_18], 0
0x180017a82  mov     [rbp+TokenHandle], 0
0x180017a8a  call    cs:__imp_GetCurrentProcess
0x180017a90  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180017a94  mov     edx, 8; DesiredAccess
0x180017a99  mov     rcx, rax; ProcessHandle
0x180017a9c  call    cs:__imp_OpenProcessToken
0x180017aa2  test    eax, eax
0x180017aa4  jnz     short loc_180017AF8
0x180017aa6  call    cs:__imp_GetLastError
0x180017aac  lea     rdx, WPP_GLOBAL_Control
0x180017ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017aba  cmp     rcx, rdx
0x180017abd  jz      short loc_180017ADE
0x180017abf  test    byte ptr [rcx+1Ch], 1
0x180017ac3  jz      short loc_180017ADE
0x180017ac5  mov     edx, 0Ah
0x180017aca  mov     r9d, eax
0x180017acd  lea     r8, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids
0x180017ad4  mov     rcx, [rcx+10h]
0x180017ad8  call    WPP_SF_d
0x180017add  nop
0x180017ade  lea     rcx, [rbp+TokenHandle]; this
0x180017ae2  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180017ae7  nop
0x180017ae8  xor     ecx, ecx; Block
0x180017aea  call    cs:__imp_free
0x180017af0  nop
0x180017af1  xor     eax, eax
0x180017af3  jmp     loc_180017C15
0x180017af8  mov     [rbp+TokenInformationLength], 0
0x180017aff  lea     rax, [rbp+TokenInformationLength]
0x180017b03  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180017b08  xor     r9d, r9d; TokenInformationLength
0x180017b0b  xor     r8d, r8d; TokenInformation
0x180017b0e  lea     edx, [r9+1]; TokenInformationClass
0x180017b12  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180017b16  call    cs:__imp_GetTokenInformation
0x180017b1c  call    cs:__imp_GetLastError
0x180017b22  cmp     eax, 7Ah ; 'z'
0x180017b25  jz      short loc_180017B6E
0x180017b27  lea     rdx, WPP_GLOBAL_Control
0x180017b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b35  cmp     rcx, rdx
0x180017b38  jz      short loc_180017B59
0x180017b3a  test    byte ptr [rcx+1Ch], 1
0x180017b3e  jz      short loc_180017B59
0x180017b40  mov     edx, 0Bh
0x180017b45  mov     r9d, eax
0x180017b48  lea     r8, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids
0x180017b4f  mov     rcx, [rcx+10h]
0x180017b53  call    WPP_SF_d
0x180017b58  nop
0x180017b59  lea     rcx, [rbp+TokenHandle]; this
0x180017b5d  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180017b62  nop
0x180017b63  xor     ecx, ecx; Block
0x180017b65  call    cs:__imp_free
0x180017b6b  nop
0x180017b6c  jmp     short loc_180017AF1
0x180017b6e  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180017b71  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180017b76  mov     rbx, rax
0x180017b79  mov     [rbp+arg_18], rax
0x180017b7d  lea     rax, [rbp+TokenInformationLength]
0x180017b81  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180017b86  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180017b8a  mov     r8, rbx; TokenInformation
0x180017b8d  mov     edx, 1; TokenInformationClass
0x180017b92  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180017b96  call    cs:__imp_GetTokenInformation
0x180017b9c  test    eax, eax
0x180017b9e  jnz     short loc_180017BF1
0x180017ba0  call    cs:__imp_GetLastError
0x180017ba6  lea     rdx, WPP_GLOBAL_Control
0x180017bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bb4  cmp     rcx, rdx
0x180017bb7  jz      short loc_180017BD8
0x180017bb9  test    byte ptr [rcx+1Ch], 1
0x180017bbd  jz      short loc_180017BD8
0x180017bbf  mov     edx, 0Ch
0x180017bc4  mov     r9d, eax
0x180017bc7  lea     r8, WPP_20ca15b2a10238a941d519cfc1532a9f_Traceguids
0x180017bce  mov     rcx, [rcx+10h]
0x180017bd2  call    WPP_SF_d
0x180017bd7  nop
0x180017bd8  lea     rcx, [rbp+TokenHandle]; this
0x180017bdc  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180017be1  nop
0x180017be2  mov     rcx, rbx; Block
0x180017be5  call    cs:__imp_free
0x180017beb  nop
0x180017bec  jmp     loc_180017AF1
0x180017bf1  mov     rdx, [rbx]; pSid2
0x180017bf4  mov     rcx, rdi; pSid1
0x180017bf7  call    cs:__imp_EqualSid
0x180017bfd  mov     edi, eax
0x180017bff  lea     rcx, [rbp+TokenHandle]; this
0x180017c03  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180017c08  nop
0x180017c09  mov     rcx, rbx; Block
0x180017c0c  call    cs:__imp_free
0x180017c12  nop
0x180017c13  mov     eax, edi
0x180017c15  add     rsp, 30h
0x180017c19  pop     rdi
0x180017c1a  pop     rbx
0x180017c1b  pop     rbp
0x180017c1c  retn
```
