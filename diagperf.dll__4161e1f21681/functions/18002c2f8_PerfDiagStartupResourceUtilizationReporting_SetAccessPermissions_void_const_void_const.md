# PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(void * const,void * const)

- ea: `0x18002c2f8`
- end: `0x18002c3db`
- name: `?SetAccessPermissions@PerfDiagStartupResourceUtilizationReporting@@YAJQEAX0@Z`
- size: `227`
- prototype: `__int64 __fastcall(HANDLE handle, PSID pSid, void *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002f06c`
- `0x1800c49c4`

## callees

- `0x18002c2f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c352`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c3c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c3c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c3ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c3ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c323`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c323`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c30c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c30c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18002c37f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18002c37f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002c348`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002c348`
- `ADVAPI32!SetSecurityInfo` at `0x18002c3ae`
- `ADVAPI32!SetSecurityInfo` at `0x18002c3ae`

## pseudocode

```c
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::SetAccessPermissions(
        HANDLE handle,
        PSID pSid,
        void *const a3)
{
  DWORD v5; // esi
  HANDLE ProcessHeap; // rax
  struct _ACL *v7; // rax
  struct _ACL *pDacl; // rdi
  unsigned int v9; // ebx
  signed int LastError; // eax
  bool v11; // cc
  HANDLE v12; // rax

  v5 = GetLengthSid(pSid) + 16;
  ProcessHeap = GetProcessHeap();
  v7 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v5);
  pDacl = v7;
  if ( v7 )
  {
    if ( InitializeAcl(v7, v5, 2u) && AddAccessAllowedAceEx(pDacl, 2u, 3u, 0x10000000u, pSid) )
    {
      LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
      v9 = LastError;
      v11 = LastError <= 0;
      if ( !LastError )
      {
LABEL_9:
        v12 = GetProcessHeap();
        HeapFree(v12, 0, pDacl);
        return v9;
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v11 = LastError <= 0;
    }
    if ( !v11 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18002c2f8  push    rbx
0x18002c2fa  push    rbp
0x18002c2fb  push    rsi
0x18002c2fc  push    rdi
0x18002c2fd  push    r14
0x18002c2ff  sub     rsp, 40h
0x18002c303  mov     r14, rcx
0x18002c306  mov     rbp, rdx
0x18002c309  mov     rcx, rdx; pSid
0x18002c30c  call    cs:__imp_GetLengthSid
0x18002c312  lea     esi, [rax+10h]
0x18002c315  call    cs:__imp_GetProcessHeap
0x18002c31b  mov     r8d, esi; dwBytes
0x18002c31e  xor     edx, edx; dwFlags
0x18002c320  mov     rcx, rax; hHeap
0x18002c323  call    cs:__imp_HeapAlloc
0x18002c329  mov     rdi, rax
0x18002c32c  test    rax, rax
0x18002c32f  jnz     short loc_18002C33B
0x18002c331  mov     ebx, 8007000Eh
0x18002c336  jmp     loc_18002C3CE
0x18002c33b  mov     ebx, 2
0x18002c340  mov     edx, esi; nAclLength
0x18002c342  mov     r8d, ebx; dwAclRevision
0x18002c345  mov     rcx, rdi; pAcl
0x18002c348  call    cs:__imp_InitializeAcl
0x18002c34e  test    eax, eax
0x18002c350  jnz     short loc_18002C369
0x18002c352  call    cs:__imp_GetLastError
0x18002c358  mov     ebx, eax
0x18002c35a  test    eax, eax
0x18002c35c  jle     short loc_18002C3BA
0x18002c35e  movzx   ebx, ax
0x18002c361  or      ebx, 80070000h
0x18002c367  jmp     short loc_18002C3BA
0x18002c369  mov     r9d, 10000000h; AccessMask
0x18002c36f  mov     [rsp+68h+pSid], rbp; pSid
0x18002c374  mov     r8d, 3; AceFlags
0x18002c37a  mov     edx, ebx; dwAceRevision
0x18002c37c  mov     rcx, rdi; pAcl
0x18002c37f  call    cs:__imp_AddAccessAllowedAceEx
0x18002c385  test    eax, eax
0x18002c387  jz      short loc_18002C352
0x18002c389  xor     r9d, r9d; psidOwner
0x18002c38c  mov     [rsp+68h+pSacl], 0; pSacl
0x18002c395  mov     [rsp+68h+pDacl], rdi; pDacl
0x18002c39a  mov     rcx, r14; handle
0x18002c39d  mov     [rsp+68h+pSid], 0; psidGroup
0x18002c3a6  lea     edx, [r9+1]; ObjectType
0x18002c3aa  lea     r8d, [r9+4]; SecurityInfo
0x18002c3ae  call    cs:__imp_SetSecurityInfo
0x18002c3b4  mov     ebx, eax
0x18002c3b6  test    eax, eax
0x18002c3b8  jnz     short loc_18002C35C
0x18002c3ba  call    cs:__imp_GetProcessHeap
0x18002c3c0  mov     r8, rdi; lpMem
0x18002c3c3  xor     edx, edx; dwFlags
0x18002c3c5  mov     rcx, rax; hHeap
0x18002c3c8  call    cs:__imp_HeapFree
0x18002c3ce  mov     eax, ebx
0x18002c3d0  add     rsp, 40h
0x18002c3d4  pop     r14
0x18002c3d6  pop     rdi
0x18002c3d7  pop     rsi
0x18002c3d8  pop     rbp
0x18002c3d9  pop     rbx
0x18002c3da  retn
```
