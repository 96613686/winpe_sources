# CFontAgent::_CheckDeletePermision(ushort const *)

- ea: `0x180008404`
- end: `0x1800085a3`
- name: `?_CheckDeletePermision@CFontAgent@@IEAAHPEBG@Z`
- size: `415`
- prototype: `int(CFontAgent *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800085ac`

## callees

- `0x180008404`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000856f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000856f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000842c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000842c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000843e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000843e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008583`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180008480`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800084ca`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180008480`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800084ca`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000845a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000845a`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008503`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008503`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180008555`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180008555`

## pseudocode

```c
__int64 __fastcall CFontAgent::_CheckDeletePermision(CFontAgent *this, const unsigned __int16 *a2)
{
  unsigned int v2; // edi
  HANDLE CurrentProcess; // rax
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-29h] BYREF
  DWORD AccessMask; // [rsp+44h] [rbp-25h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-21h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-1Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp-19h] BYREF
  void *DuplicateTokenHandle; // [rsp+58h] [rbp-11h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-9h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-1h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+Fh] BYREF

  v2 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
  {
    DuplicateTokenHandle = 0;
    if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      nLengthNeeded = 0;
      GetFileSecurityW(a2, 7u, 0, 0, &nLengthNeeded);
      if ( nLengthNeeded )
      {
        v5 = nLengthNeeded;
        ProcessHeap = GetProcessHeap();
        v7 = HeapAlloc(ProcessHeap, 8u, v5);
        if ( v7 )
        {
          if ( GetFileSecurityW(a2, 7u, v7, nLengthNeeded, &nLengthNeeded) )
          {
            GenericMapping.GenericRead = 1179785;
            GenericMapping.GenericWrite = 1179926;
            GenericMapping.GenericExecute = 1179808;
            GenericMapping.GenericAll = 2032127;
            AccessMask = 0x10000;
            MapGenericMask(&AccessMask, &GenericMapping);
            GrantedAccess = 0;
            AccessStatus = 0;
            memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
            PrivilegeSetLength = 20;
            if ( AccessCheck(
                   v7,
                   DuplicateTokenHandle,
                   AccessMask,
                   &GenericMapping,
                   &PrivilegeSet,
                   &PrivilegeSetLength,
                   &GrantedAccess,
                   &AccessStatus) )
            {
              v2 = AccessStatus;
            }
            v8 = GetProcessHeap();
            HeapFree(v8, 0, v7);
          }
        }
      }
      CloseHandle(DuplicateTokenHandle);
    }
    CloseHandle(TokenHandle);
  }
  return v2;
}

```

## disassembly

```asm
0x180008404  push    rbp
0x180008406  push    rbx
0x180008407  push    rsi
0x180008408  push    rdi
0x180008409  lea     rbp, [rsp-3Fh]
0x18000840e  sub     rsp, 0A8h
0x180008415  mov     rax, cs:__security_cookie
0x18000841c  xor     rax, rsp
0x18000841f  mov     [rbp+57h+var_30], rax
0x180008423  xor     edi, edi
0x180008425  mov     rsi, rdx
0x180008428  mov     [rbp+57h+TokenHandle], rdi
0x18000842c  call    cs:__imp_GetCurrentProcess
0x180008432  lea     ebx, [rdi+2]
0x180008435  mov     rcx, rax; ProcessHandle
0x180008438  mov     edx, ebx; DesiredAccess
0x18000843a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000843e  call    cs:__imp_OpenProcessToken
0x180008444  test    eax, eax
0x180008446  jz      loc_180008589
0x18000844c  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180008450  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180008454  mov     edx, ebx; ImpersonationLevel
0x180008456  mov     [rbp+57h+DuplicateTokenHandle], rdi
0x18000845a  call    cs:__imp_DuplicateToken
0x180008460  test    eax, eax
0x180008462  jz      loc_18000857F
0x180008468  lea     rax, [rbp+57h+nLengthNeeded]
0x18000846c  mov     [rbp+57h+nLengthNeeded], edi
0x18000846f  xor     r9d, r9d; nLength
0x180008472  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180008477  xor     r8d, r8d; pSecurityDescriptor
0x18000847a  lea     edx, [rdi+7]; RequestedInformation
0x18000847d  mov     rcx, rsi; lpFileName
0x180008480  call    cs:__imp_GetFileSecurityW
0x180008486  mov     eax, [rbp+57h+nLengthNeeded]
0x180008489  test    eax, eax
0x18000848b  jz      loc_180008575
0x180008491  mov     ebx, eax
0x180008493  call    cs:__imp_GetProcessHeap
0x180008499  mov     r8d, ebx; dwBytes
0x18000849c  lea     edx, [rdi+8]; dwFlags
0x18000849f  mov     rcx, rax; hHeap
0x1800084a2  call    cs:__imp_HeapAlloc
0x1800084a8  mov     rbx, rax
0x1800084ab  test    rax, rax
0x1800084ae  jz      loc_180008575
0x1800084b4  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1800084b8  lea     rax, [rbp+57h+nLengthNeeded]
0x1800084bc  mov     r8, rbx; pSecurityDescriptor
0x1800084bf  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800084c4  lea     edx, [rdi+7]; RequestedInformation
0x1800084c7  mov     rcx, rsi; lpFileName
0x1800084ca  call    cs:__imp_GetFileSecurityW
0x1800084d0  test    eax, eax
0x1800084d2  jz      loc_180008575
0x1800084d8  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1800084dc  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1800084e3  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800084e7  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1800084ee  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1800084f5  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1800084fc  mov     [rbp+57h+AccessMask], 10000h
0x180008503  call    cs:__imp_MapGenericMask
0x180008509  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18000850d  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180008511  mov     rdx, [rbp+57h+DuplicateTokenHandle]; ClientToken
0x180008515  xor     eax, eax
0x180008517  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18000851a  xorps   xmm0, xmm0
0x18000851d  mov     [rbp+57h+var_74], eax
0x180008520  mov     rcx, rbx; pSecurityDescriptor
0x180008523  mov     [rbp+57h+var_78], eax
0x180008526  lea     rax, [rbp+57h+var_78]
0x18000852a  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18000852f  lea     rax, [rbp+57h+var_74]
0x180008533  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180008538  lea     rax, [rbp+57h+var_70]
0x18000853c  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180008541  lea     rax, [rbp+57h+PrivilegeSet]
0x180008545  mov     [rsp+0C0h+lpnLengthNeeded], rax; PrivilegeSet
0x18000854a  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18000854e  mov     [rbp+57h+var_70], 14h
0x180008555  call    cs:__imp_AccessCheck
0x18000855b  test    eax, eax
0x18000855d  cmovnz  edi, [rbp+57h+var_78]
0x180008561  call    cs:__imp_GetProcessHeap
0x180008567  mov     r8, rbx; lpMem
0x18000856a  xor     edx, edx; dwFlags
0x18000856c  mov     rcx, rax; hHeap
0x18000856f  call    cs:__imp_HeapFree
0x180008575  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x180008579  call    cs:__imp_CloseHandle
0x18000857f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180008583  call    cs:__imp_CloseHandle
0x180008589  mov     eax, edi
0x18000858b  mov     rcx, [rbp+57h+var_30]
0x18000858f  xor     rcx, rsp; StackCookie
0x180008592  call    __security_check_cookie
0x180008597  add     rsp, 0A8h
0x18000859e  pop     rdi
0x18000859f  pop     rsi
0x1800085a0  pop     rbx
0x1800085a1  pop     rbp
0x1800085a2  retn
```
