# DsRolepCopyFileAttributes

- ea: `0x18000c350`
- end: `0x18000c5f8`
- name: `DsRolepCopyFileAttributes`
- size: `680`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000de20`

## callees

- `0x18000c350`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c51e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c54d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c51e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c54d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000c587`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000c587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5c9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000c56e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000c56e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000c4eb`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000c4eb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c449`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c449`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000c3ce`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000c430`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000c3ce`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000c430`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000c488`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000c488`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c4cc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c4cc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c4a5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c4a5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000c40d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000c40d`
- `ntdll!RtlAllocateHeap` at `0x18000c3e7`
- `ntdll!RtlAllocateHeap` at `0x18000c3e7`
- `ntdll!RtlFreeHeap` at `0x18000c5ab`
- `ntdll!RtlFreeHeap` at `0x18000c5ab`

## pseudocode

```c
__int64 __fastcall DsRolepCopyFileAttributes(LPCWSTR lpFileName, LPCWSTR a2)
{
  SECURITY_INFORMATION v3; // ebx
  PVOID Heap; // rdi
  __int64 FileW; // r14
  __int64 v8; // rsi
  SECURITY_DESCRIPTOR_CONTROL v9; // dx
  DWORD LastError; // ebx
  WORD pControl[2]; // [rsp+40h] [rbp-39h] BYREF
  DWORD nLengthNeeded; // [rsp+44h] [rbp-35h] BYREF
  WINBOOL bDaclPresent; // [rsp+48h] [rbp-31h] BYREF
  WINBOOL bSaclPresent; // [rsp+4Ch] [rbp-2Dh] BYREF
  DWORD dwRevision; // [rsp+50h] [rbp-29h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+54h] [rbp-25h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+58h] [rbp-21h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-19h] BYREF
  PACL pSacl; // [rsp+68h] [rbp-11h] BYREF
  _OWORD FileInformation[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v21; // [rsp+90h] [rbp+17h]

  v21 = 0;
  nLengthNeeded = 0;
  bDaclPresent = 0;
  v3 = 15;
  bDaclDefaulted = 0;
  pDacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pSacl = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  pControl[0] = 0;
  dwRevision = 0;
  GetFileSecurityW(lpFileName, 0xFu, 0, 0, &nLengthNeeded);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, nLengthNeeded);
  if ( !Heap )
    return 8;
  FileW = -1;
  v8 = -1;
  if ( !InitializeSecurityDescriptor(Heap, 1u)
    || !GetFileSecurityW(lpFileName, 0xFu, Heap, nLengthNeeded, &nLengthNeeded)
    || !GetSecurityDescriptorControl(Heap, pControl, &dwRevision) )
  {
    goto LABEL_20;
  }
  v9 = (pControl[0] >> 2) & 0x100 | 0x200;
  if ( (pControl[0] & 0x800) == 0 )
    v9 = (pControl[0] >> 2) & 0x100;
  if ( !SetSecurityDescriptorControl(Heap, v9, v9)
    || !GetSecurityDescriptorDacl(Heap, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    goto LABEL_20;
  }
  if ( !bDaclPresent )
    v3 = 11;
  if ( !GetSecurityDescriptorSacl(Heap, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_20;
  if ( !bSaclPresent )
    v3 &= ~8u;
  if ( !SetFileSecurityW(a2, v3, Heap)
    || (FileW = (__int64)CreateFileW(lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0), FileW == -1)
    || (v8 = (__int64)CreateFileW(a2, 0x100u, 2u, 0, 3u, 0x2000080u, 0), v8 == -1)
    || !GetFileInformationByHandleEx((HANDLE)FileW, FileBasicInfo, FileInformation, 0x28u)
    || (LastError = 0, !SetFileInformationByHandle((HANDLE)v8, FileBasicInfo, FileInformation, 0x28u)) )
  {
LABEL_20:
    LastError = GetLastError();
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return LastError;
}

```

## disassembly

```asm
0x18000c350  mov     [rsp-8+arg_10], rbx
0x18000c355  push    rbp
0x18000c356  push    rsi
0x18000c357  push    rdi
0x18000c358  push    r12
0x18000c35a  push    r13
0x18000c35c  push    r14
0x18000c35e  push    r15
0x18000c360  lea     rbp, [rsp-27h]
0x18000c365  sub     rsp, 0A0h
0x18000c36c  mov     rax, cs:__security_cookie
0x18000c373  xor     rax, rsp
0x18000c376  mov     [rbp+57h+var_38], rax
0x18000c37a  xor     r13d, r13d
0x18000c37d  xor     eax, eax
0x18000c37f  xorps   xmm0, xmm0
0x18000c382  mov     [rbp+57h+var_40], rax
0x18000c386  mov     r12, rdx
0x18000c389  mov     [rbp+57h+nLengthNeeded], r13d
0x18000c38d  lea     rax, [rbp+57h+nLengthNeeded]
0x18000c391  mov     [rbp+57h+bDaclPresent], r13d
0x18000c395  lea     ebx, [r13+0Fh]
0x18000c399  mov     [rbp+57h+bDaclDefaulted], r13d
0x18000c39d  mov     edx, ebx; RequestedInformation
0x18000c39f  mov     [rbp+57h+pDacl], r13
0x18000c3a3  xor     r9d, r9d; nLength
0x18000c3a6  mov     [rbp+57h+bSaclPresent], r13d
0x18000c3aa  xor     r8d, r8d; pSecurityDescriptor
0x18000c3ad  mov     [rbp+57h+bSaclDefaulted], r13d
0x18000c3b1  mov     r15, rcx
0x18000c3b4  mov     [rbp+57h+pSacl], r13
0x18000c3b8  movups  [rbp+57h+FileInformation], xmm0
0x18000c3bc  mov     [rbp+57h+pControl], r13w
0x18000c3c1  movups  [rbp+57h+var_50], xmm0
0x18000c3c5  mov     [rbp+57h+dwRevision], r13d
0x18000c3c9  mov     [rsp+0D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000c3ce  call    cs:__imp_GetFileSecurityW
0x18000c3d4  mov     rcx, gs:60h
0x18000c3dd  xor     edx, edx; Flags
0x18000c3df  mov     r8d, [rbp+57h+nLengthNeeded]; Size
0x18000c3e3  mov     rcx, [rcx+30h]; HeapHandle
0x18000c3e7  call    cs:__imp_RtlAllocateHeap
0x18000c3ed  mov     rdi, rax
0x18000c3f0  test    rax, rax
0x18000c3f3  jnz     short loc_18000C3FD
0x18000c3f5  lea     eax, [rbx-7]
0x18000c3f8  jmp     loc_18000C5D1
0x18000c3fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c401  mov     rcx, rdi; pSecurityDescriptor
0x18000c404  mov     r14, rax
0x18000c407  mov     rsi, rax
0x18000c40a  lea     edx, [rax+2]; dwRevision
0x18000c40d  call    cs:__imp_InitializeSecurityDescriptor
0x18000c413  test    eax, eax
0x18000c415  jz      loc_18000C591
0x18000c41b  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x18000c41f  lea     rax, [rbp+57h+nLengthNeeded]
0x18000c423  mov     r8, rdi; pSecurityDescriptor
0x18000c426  mov     [rsp+0D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000c42b  mov     edx, ebx; RequestedInformation
0x18000c42d  mov     rcx, r15; lpFileName
0x18000c430  call    cs:__imp_GetFileSecurityW
0x18000c436  test    eax, eax
0x18000c438  jz      loc_18000C591
0x18000c43e  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18000c442  mov     rcx, rdi; pSecurityDescriptor
0x18000c445  lea     rdx, [rbp+57h+pControl]; pControl
0x18000c449  call    cs:__imp_GetSecurityDescriptorControl
0x18000c44f  test    eax, eax
0x18000c451  jz      loc_18000C591
0x18000c457  movzx   eax, [rbp+57h+pControl]
0x18000c45b  mov     edx, 100h
0x18000c460  movzx   ecx, ax
0x18000c463  shr     cx, 2
0x18000c467  and     cx, dx
0x18000c46a  mov     edx, 800h
0x18000c46f  and     ax, dx
0x18000c472  movzx   edx, cx
0x18000c475  or      dx, 200h
0x18000c47a  test    ax, ax
0x18000c47d  cmovz   dx, cx; ControlBitsOfInterest
0x18000c481  mov     rcx, rdi; pSecurityDescriptor
0x18000c484  movzx   r8d, dx; ControlBitsToSet
0x18000c488  call    cs:__imp_SetSecurityDescriptorControl
0x18000c48e  test    eax, eax
0x18000c490  jz      loc_18000C591
0x18000c496  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18000c49a  mov     rcx, rdi; pSecurityDescriptor
0x18000c49d  lea     r8, [rbp+57h+pDacl]; pDacl
0x18000c4a1  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18000c4a5  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c4ab  test    eax, eax
0x18000c4ad  jz      loc_18000C591
0x18000c4b3  cmp     [rbp+57h+bDaclPresent], r13d
0x18000c4b7  lea     eax, [rsi+0Ch]
0x18000c4ba  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18000c4be  mov     rcx, rdi; pSecurityDescriptor
0x18000c4c1  lea     r8, [rbp+57h+pSacl]; pSacl
0x18000c4c5  cmovz   ebx, eax
0x18000c4c8  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18000c4cc  call    cs:__imp_GetSecurityDescriptorSacl
0x18000c4d2  test    eax, eax
0x18000c4d4  jz      loc_18000C591
0x18000c4da  cmp     [rbp+57h+bSaclPresent], r13d
0x18000c4de  jnz     short loc_18000C4E3
0x18000c4e0  and     ebx, 0FFFFFFF7h
0x18000c4e3  mov     r8, rdi; pSecurityDescriptor
0x18000c4e6  mov     edx, ebx; SecurityInformation
0x18000c4e8  mov     rcx, r12; lpFileName
0x18000c4eb  call    cs:__imp_SetFileSecurityW
0x18000c4f1  test    eax, eax
0x18000c4f3  jz      loc_18000C591
0x18000c4f9  xor     r9d, r9d; lpSecurityAttributes
0x18000c4fc  mov     [rsp+0D0h+hTemplateFile], r13; hTemplateFile
0x18000c501  mov     ebx, 2000080h
0x18000c506  mov     edx, 80h; dwDesiredAccess
0x18000c50b  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18000c50f  mov     rcx, r15; lpFileName
0x18000c512  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], 3; dwCreationDisposition
0x18000c51a  lea     r8d, [r9+1]; dwShareMode
0x18000c51e  call    cs:__imp_CreateFileW
0x18000c524  mov     r14, rax
0x18000c527  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c52b  jz      short loc_18000C591
0x18000c52d  xor     r9d, r9d; lpSecurityAttributes
0x18000c530  mov     [rsp+0D0h+hTemplateFile], r13; hTemplateFile
0x18000c535  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18000c539  mov     edx, 100h; dwDesiredAccess
0x18000c53e  mov     rcx, r12; lpFileName
0x18000c541  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], 3; dwCreationDisposition
0x18000c549  lea     r8d, [r9+2]; dwShareMode
0x18000c54d  call    cs:__imp_CreateFileW
0x18000c553  mov     rsi, rax
0x18000c556  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c55a  jz      short loc_18000C591
0x18000c55c  mov     r15d, 28h ; '('
0x18000c562  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18000c566  mov     r9d, r15d; dwBufferSize
0x18000c569  xor     edx, edx; FileInformationClass
0x18000c56b  mov     rcx, r14; hFile
0x18000c56e  call    cs:__imp_GetFileInformationByHandleEx
0x18000c574  test    eax, eax
0x18000c576  jz      short loc_18000C591
0x18000c578  mov     r9d, r15d; dwBufferSize
0x18000c57b  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18000c57f  xor     edx, edx; FileInformationClass
0x18000c581  mov     rcx, rsi; hFile
0x18000c584  mov     ebx, r13d
0x18000c587  call    cs:__imp_SetFileInformationByHandle
0x18000c58d  test    eax, eax
0x18000c58f  jnz     short loc_18000C599
0x18000c591  call    cs:__imp_GetLastError
0x18000c597  mov     ebx, eax
0x18000c599  mov     rcx, gs:60h
0x18000c5a2  mov     r8, rdi; P
0x18000c5a5  xor     edx, edx; Flags
0x18000c5a7  mov     rcx, [rcx+30h]; HeapHandle
0x18000c5ab  call    cs:__imp_RtlFreeHeap
0x18000c5b1  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000c5b5  jz      short loc_18000C5C0
0x18000c5b7  mov     rcx, r14; hObject
0x18000c5ba  call    cs:__imp_CloseHandle
0x18000c5c0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c5c4  jz      short loc_18000C5CF
0x18000c5c6  mov     rcx, rsi; hObject
0x18000c5c9  call    cs:__imp_CloseHandle
0x18000c5cf  mov     eax, ebx
0x18000c5d1  mov     rcx, [rbp+57h+var_38]
0x18000c5d5  xor     rcx, rsp; StackCookie
0x18000c5d8  call    __security_check_cookie
0x18000c5dd  mov     rbx, [rsp+0D0h+arg_10]
0x18000c5e5  add     rsp, 0A0h
0x18000c5ec  pop     r15
0x18000c5ee  pop     r14
0x18000c5f0  pop     r13
0x18000c5f2  pop     r12
0x18000c5f4  pop     rdi
0x18000c5f5  pop     rsi
0x18000c5f6  pop     rbp
0x18000c5f7  retn
```
