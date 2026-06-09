# SetHandleIntegrityLevel(void *,void *)

- ea: `0x1800812d0`
- end: `0x18008143f`
- name: `?SetHandleIntegrityLevel@@YAJPEAX0@Z`
- size: `367`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID pLabelSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081180`

## callees

- `0x1800812d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081329`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008142a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008142a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008131b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008137a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008141c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008131b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008137a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008141c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008136e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008140a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008136e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008140a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180081400`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180081400`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800813e9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800813e9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800813d0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800813d0`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18008135d`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x18008135d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180081340`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180081340`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800812ff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800812ff`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800812e6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800812e6`

## pseudocode

```c
__int64 __fastcall SetHandleIntegrityLevel(HANDLE Handle, PSID pLabelSid)
{
  struct _ACL *v4; // rbp
  DWORD LengthSid; // eax
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  struct _ACL *v8; // rax
  struct _ACL *v9; // rdi
  signed int LastError; // ebx
  bool v11; // sf
  HANDLE v12; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]

  v4 = 0;
  if ( !IsValidSid(pLabelSid) )
  {
    LOWORD(LastError) = 87;
    goto LABEL_15;
  }
  LengthSid = GetLengthSid(pLabelSid);
  if ( LengthSid + 12 < LengthSid || (v6 = LengthSid + 20, LengthSid + 20 < LengthSid + 12) )
  {
    LOWORD(LastError) = 534;
LABEL_15:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  ProcessHeap = GetProcessHeap();
  v8 = (struct _ACL *)HeapAlloc(ProcessHeap, 0, v6);
  v9 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    goto LABEL_11;
  }
  if ( !InitializeAcl(v8, v6, 4u) || !AddMandatoryAce(v9, 4u, 3u, 1u, pLabelSid) )
  {
    LastError = GetLastError();
    v11 = LastError < 0;
    if ( !LastError )
      goto LABEL_17;
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v9);
LABEL_11:
    if ( LastError <= 0 )
      goto LABEL_16;
    goto LABEL_15;
  }
  LastError = 0;
  v4 = v9;
LABEL_16:
  v11 = LastError < 0;
LABEL_17:
  if ( !v11 )
  {
    v17 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v4, 0)
      || !SetKernelObjectSecurity(Handle, 0x10u, pSecurityDescriptor) )
    {
      v13 = GetLastError();
      LastError = v13;
      if ( v13 > 0 )
        LastError = (unsigned __int16)v13 | 0x80070000;
    }
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v4);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800812d0  push    rbx
0x1800812d2  push    rbp
0x1800812d3  push    rsi
0x1800812d4  push    rdi
0x1800812d5  push    r14
0x1800812d7  push    r15
0x1800812d9  sub     rsp, 68h
0x1800812dd  mov     r14, rcx
0x1800812e0  mov     rsi, rdx
0x1800812e3  mov     rcx, rdx; pSid
0x1800812e6  call    cs:__imp_IsValidSid
0x1800812ec  xor     ebp, ebp
0x1800812ee  mov     r15d, 80070000h
0x1800812f4  test    eax, eax
0x1800812f6  jz      loc_1800813A5
0x1800812fc  mov     rcx, rsi; pSid
0x1800812ff  call    cs:__imp_GetLengthSid
0x180081305  lea     ecx, [rax+0Ch]
0x180081308  cmp     ecx, eax
0x18008130a  jb      loc_18008139E
0x180081310  lea     ebx, [rcx+8]
0x180081313  cmp     ebx, ecx
0x180081315  jb      loc_18008139E
0x18008131b  call    cs:__imp_GetProcessHeap
0x180081321  mov     r8d, ebx; dwBytes
0x180081324  xor     edx, edx; dwFlags
0x180081326  mov     rcx, rax; hHeap
0x180081329  call    cs:__imp_HeapAlloc
0x18008132f  mov     rdi, rax
0x180081332  test    rax, rax
0x180081335  jz      short loc_180081390
0x180081337  lea     r8d, [rbp+4]; dwAclRevision
0x18008133b  mov     edx, ebx; nAclLength
0x18008133d  mov     rcx, rax; pAcl
0x180081340  call    cs:__imp_InitializeAcl
0x180081346  test    eax, eax
0x180081348  jz      short loc_18008136E
0x18008134a  lea     edx, [rbp+4]; dwAceRevision
0x18008134d  mov     [rsp+98h+pLabelSid], rsi; pLabelSid
0x180081352  lea     r9d, [rbp+1]; MandatoryPolicy
0x180081356  mov     rcx, rdi; pAcl
0x180081359  lea     r8d, [rbp+3]; AceFlags
0x18008135d  call    cs:__imp_AddMandatoryAce
0x180081363  test    eax, eax
0x180081365  jz      short loc_18008136E
0x180081367  xor     ebx, ebx
0x180081369  mov     rbp, rdi
0x18008136c  jmp     short loc_1800813B0
0x18008136e  call    cs:__imp_GetLastError
0x180081374  mov     ebx, eax
0x180081376  test    eax, eax
0x180081378  jz      short loc_1800813B2
0x18008137a  call    cs:__imp_GetProcessHeap
0x180081380  mov     r8, rdi; lpMem
0x180081383  xor     edx, edx; dwFlags
0x180081385  mov     rcx, rax; hHeap
0x180081388  call    cs:__imp_HeapFree
0x18008138e  jmp     short loc_180081398
0x180081390  call    cs:__imp_GetLastError
0x180081396  mov     ebx, eax
0x180081398  test    ebx, ebx
0x18008139a  jg      short loc_1800813AA
0x18008139c  jmp     short loc_1800813B0
0x18008139e  mov     ebx, 216h
0x1800813a3  jmp     short loc_1800813AA
0x1800813a5  mov     ebx, 57h ; 'W'
0x1800813aa  movzx   ebx, bx
0x1800813ad  or      ebx, r15d
0x1800813b0  test    ebx, ebx
0x1800813b2  js      short loc_180081430
0x1800813b4  xor     eax, eax
0x1800813b6  lea     rcx, [rsp+98h+pSecurityDescriptor]; pSecurityDescriptor
0x1800813bb  xorps   xmm0, xmm0
0x1800813be  mov     [rsp+98h+var_48], rax
0x1800813c3  movups  [rsp+98h+pSecurityDescriptor], xmm0
0x1800813c8  lea     edx, [rax+1]; dwRevision
0x1800813cb  movups  [rsp+98h+var_58], xmm0
0x1800813d0  call    cs:__imp_InitializeSecurityDescriptor
0x1800813d6  test    eax, eax
0x1800813d8  jz      short loc_18008140A
0x1800813da  xor     r9d, r9d; bSaclDefaulted
0x1800813dd  lea     rcx, [rsp+98h+pSecurityDescriptor]; pSecurityDescriptor
0x1800813e2  mov     r8, rbp; pSacl
0x1800813e5  lea     edx, [r9+1]; bSaclPresent
0x1800813e9  call    cs:__imp_SetSecurityDescriptorSacl
0x1800813ef  test    eax, eax
0x1800813f1  jz      short loc_18008140A
0x1800813f3  lea     r8, [rsp+98h+pSecurityDescriptor]; SecurityDescriptor
0x1800813f8  mov     edx, 10h; SecurityInformation
0x1800813fd  mov     rcx, r14; Handle
0x180081400  call    cs:__imp_SetKernelObjectSecurity
0x180081406  test    eax, eax
0x180081408  jnz     short loc_18008141C
0x18008140a  call    cs:__imp_GetLastError
0x180081410  mov     ebx, eax
0x180081412  test    eax, eax
0x180081414  jle     short loc_18008141C
0x180081416  movzx   ebx, ax
0x180081419  or      ebx, r15d
0x18008141c  call    cs:__imp_GetProcessHeap
0x180081422  mov     r8, rbp; lpMem
0x180081425  xor     edx, edx; dwFlags
0x180081427  mov     rcx, rax; hHeap
0x18008142a  call    cs:__imp_HeapFree
0x180081430  mov     eax, ebx
0x180081432  add     rsp, 68h
0x180081436  pop     r15
0x180081438  pop     r14
0x18008143a  pop     rdi
0x18008143b  pop     rsi
0x18008143c  pop     rbp
0x18008143d  pop     rbx
0x18008143e  retn
```
