# InitializeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)

- ea: `0x1800234b0`
- end: `0x180023579`
- name: `?InitializeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct _SERVICE_THREAD_SECURITY_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023aa8`

## callees

- `0x180016090`
- `0x18002345c`
- `0x1800234b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800234ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800234ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800234e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800234e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002353e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002353e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023534`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023534`

## pseudocode

```c
__int64 __fastcall InitializeServiceThreadSecurityInfo(struct _SERVICE_THREAD_SECURITY_INFO **a1)
{
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  struct _SERVICE_THREAD_SECURITY_INFO *pSid; // rax
  struct _SERVICE_THREAD_SECURITY_INFO *v4; // rdi
  struct _SERVICE_THREAD_SECURITY_INFO *v6; // [rsp+60h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF

  LastError = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  qword_180031828 = 0;
  ProcessHeap = GetProcessHeap();
  pSid = (struct _SERVICE_THREAD_SECURITY_INFO *)HeapAlloc(ProcessHeap, 8u, 8u);
  v6 = pSid;
  v4 = pSid;
  if ( !pSid )
    return 2148532230LL;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, (PSID *)pSid) )
  {
    qword_180031828 = v4;
  }
  else
  {
    LastError = GetLastError();
    FreeServiceThreadSecurityInfo(&v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800234b0  mov     [rsp+arg_0], rbx
0x1800234b5  push    rdi
0x1800234b6  sub     rsp, 80h
0x1800234bd  mov     rax, cs:__security_cookie
0x1800234c4  xor     rax, rsp
0x1800234c7  mov     [rsp+88h+var_18], rax
0x1800234cc  xor     ebx, ebx
0x1800234ce  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x1800234d5  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], ebx
0x1800234d9  mov     cs:qword_180031828, rbx
0x1800234e0  call    cs:__imp_GetProcessHeap
0x1800234e6  lea     edx, [rbx+8]; dwFlags
0x1800234e9  mov     rcx, rax; hHeap
0x1800234ec  mov     r8d, edx; dwBytes
0x1800234ef  call    cs:__imp_HeapAlloc
0x1800234f5  mov     [rsp+88h+var_28], rax
0x1800234fa  mov     rdi, rax
0x1800234fd  test    rax, rax
0x180023500  jnz     short loc_180023509
0x180023502  mov     eax, 80100006h
0x180023507  jmp     short loc_18002355B
0x180023509  mov     [rsp+88h+pSid], rdi; pSid
0x18002350e  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180023513  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x180023517  xor     r9d, r9d; nSubAuthority1
0x18002351a  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x18002351e  mov     dl, 1; nSubAuthorityCount
0x180023520  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x180023524  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x180023528  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x18002352c  lea     r8d, [r9+0Bh]; nSubAuthority0
0x180023530  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x180023534  call    cs:__imp_AllocateAndInitializeSid
0x18002353a  test    eax, eax
0x18002353c  jnz     short loc_180023552
0x18002353e  call    cs:__imp_GetLastError
0x180023544  lea     rcx, [rsp+88h+var_28]; struct _SERVICE_THREAD_SECURITY_INFO **
0x180023549  mov     ebx, eax
0x18002354b  call    ?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x180023550  jmp     short loc_180023559
0x180023552  mov     cs:qword_180031828, rdi
0x180023559  mov     eax, ebx
0x18002355b  mov     rcx, [rsp+88h+var_18]
0x180023560  xor     rcx, rsp; StackCookie
0x180023563  call    __security_check_cookie
0x180023568  mov     rbx, [rsp+88h+arg_0]
0x180023570  add     rsp, 80h
0x180023577  pop     rdi
0x180023578  retn
```
