# GetKernelObjectOwnerSID(void *)

- ea: `0x18007321c`
- end: `0x18007336b`
- name: `?GetKernelObjectOwnerSID@@YAPEAXPEAX@Z`
- size: `335`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004060`

## callees

- `0x18007321c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180073342`
- `KERNEL32!LocalFree` at `0x180073353`
- `KERNEL32!LocalFree` at `0x180073342`
- `KERNEL32!LocalFree` at `0x180073353`
- `KERNEL32!LocalAlloc` at `0x18007328b`
- `KERNEL32!LocalAlloc` at `0x1800732ff`
- `KERNEL32!LocalAlloc` at `0x18007328b`
- `KERNEL32!LocalAlloc` at `0x1800732ff`
- `KERNEL32!GetLastError` at `0x180073270`
- `KERNEL32!GetLastError` at `0x180073270`
- `ADVAPI32!CopySid` at `0x18007332f`
- `ADVAPI32!CopySid` at `0x18007332f`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1800732da`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1800732da`
- `ADVAPI32!GetKernelObjectSecurity` at `0x18007325e`
- `ADVAPI32!GetKernelObjectSecurity` at `0x1800732bd`
- `ADVAPI32!GetKernelObjectSecurity` at `0x18007325e`
- `ADVAPI32!GetKernelObjectSecurity` at `0x1800732bd`
- `ADVAPI32!GetLengthSid` at `0x1800732ef`
- `ADVAPI32!GetLengthSid` at `0x18007331b`
- `ADVAPI32!GetLengthSid` at `0x1800732ef`
- `ADVAPI32!GetLengthSid` at `0x18007331b`

## pseudocode

```c
HLOCAL __fastcall GetKernelObjectOwnerSID(void *a1)
{
  HANDLE v1; // rbx
  HLOCAL v2; // rdi
  HLOCAL v3; // rsi
  DWORD LengthSid; // eax
  PSID v5; // rbx
  DWORD v6; // eax
  DWORD uBytes; // [rsp+50h] [rbp+8h] BYREF
  int uBytes_4; // [rsp+54h] [rbp+Ch]
  WINBOOL bOwnerDefaulted; // [rsp+58h] [rbp+10h] BYREF
  PSID pOwner; // [rsp+60h] [rbp+18h] BYREF

  uBytes_4 = HIDWORD(a1);
  v1 = CResourceManager::m_hData;
  v2 = 0;
  uBytes = 0;
  pOwner = 0;
  bOwnerDefaulted = 1;
  if ( !GetKernelObjectSecurity(CResourceManager::m_hData, 1u, 0, 0, &uBytes) && (v3 = 0, GetLastError() != 122)
    || (v3 = LocalAlloc(0, uBytes)) == 0
    || !GetKernelObjectSecurity(v1, 1u, v3, uBytes, &uBytes)
    || !GetSecurityDescriptorOwner(v3, &pOwner, &bOwnerDefaulted)
    || (LengthSid = GetLengthSid(pOwner), (v2 = LocalAlloc(0, LengthSid)) == 0)
    || (v5 = pOwner, v6 = GetLengthSid(pOwner), !CopySid(v6, v2, v5)) )
  {
    LocalFree(v2);
    v2 = 0;
  }
  LocalFree(v3);
  return v2;
}

```

## disassembly

```asm
0x18007321c  mov     rax, rsp
0x18007321f  mov     [rax+8], rcx
0x180073223  push    rbx
0x180073224  push    rsi
0x180073225  push    rdi
0x180073226  sub     rsp, 30h
0x18007322a  mov     rbx, cs:?m_hData@CResourceManager@@0PEAXEA; void * CResourceManager::m_hData
0x180073231  xor     edi, edi
0x180073233  mov     dword ptr [rax+8], 0
0x18007323a  xor     r9d, r9d; nLength
0x18007323d  mov     qword ptr [rax+18h], 0
0x180073245  xor     r8d, r8d; pSecurityDescriptor
0x180073248  mov     dword ptr [rax+10h], 1
0x18007324f  lea     rax, [rax+8]
0x180073253  lea     edx, [rdi+1]; RequestedInformation
0x180073256  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18007325b  mov     rcx, rbx; Handle
0x18007325e  call    cs:__imp_GetKernelObjectSecurity
0x180073265  nop     dword ptr [rax+rax+00h]
0x18007326a  test    eax, eax
0x18007326c  jnz     short loc_180073285
0x18007326e  xor     esi, esi
0x180073270  call    cs:__imp_GetLastError
0x180073277  nop     dword ptr [rax+rax+00h]
0x18007327c  cmp     eax, 7Ah ; 'z'
0x18007327f  jnz     loc_18007333F
0x180073285  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180073289  xor     ecx, ecx; uFlags
0x18007328b  call    cs:__imp_LocalAlloc
0x180073292  nop     dword ptr [rax+rax+00h]
0x180073297  mov     rsi, rax
0x18007329a  test    rax, rax
0x18007329d  jz      loc_18007333F
0x1800732a3  mov     r9d, dword ptr [rsp+48h+uBytes]; nLength
0x1800732a8  lea     rax, [rsp+48h+uBytes]
0x1800732ad  mov     r8, rsi; pSecurityDescriptor
0x1800732b0  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800732b5  mov     edx, 1; RequestedInformation
0x1800732ba  mov     rcx, rbx; Handle
0x1800732bd  call    cs:__imp_GetKernelObjectSecurity
0x1800732c4  nop     dword ptr [rax+rax+00h]
0x1800732c9  test    eax, eax
0x1800732cb  jz      short loc_18007333F
0x1800732cd  lea     r8, [rsp+48h+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800732d2  mov     rcx, rsi; pSecurityDescriptor
0x1800732d5  lea     rdx, [rsp+48h+pOwner]; pOwner
0x1800732da  call    cs:__imp_GetSecurityDescriptorOwner
0x1800732e1  nop     dword ptr [rax+rax+00h]
0x1800732e6  test    eax, eax
0x1800732e8  jz      short loc_18007333F
0x1800732ea  mov     rcx, [rsp+48h+pOwner]; pSid
0x1800732ef  call    cs:__imp_GetLengthSid
0x1800732f6  nop     dword ptr [rax+rax+00h]
0x1800732fb  mov     edx, eax; uBytes
0x1800732fd  xor     ecx, ecx; uFlags
0x1800732ff  call    cs:__imp_LocalAlloc
0x180073306  nop     dword ptr [rax+rax+00h]
0x18007330b  mov     rdi, rax
0x18007330e  test    rax, rax
0x180073311  jz      short loc_18007333F
0x180073313  mov     rbx, [rsp+48h+pOwner]
0x180073318  mov     rcx, rbx; pSid
0x18007331b  call    cs:__imp_GetLengthSid
0x180073322  nop     dword ptr [rax+rax+00h]
0x180073327  mov     r8, rbx; pSourceSid
0x18007332a  mov     rdx, rdi; pDestinationSid
0x18007332d  mov     ecx, eax; nDestinationSidLength
0x18007332f  call    cs:__imp_CopySid
0x180073336  nop     dword ptr [rax+rax+00h]
0x18007333b  test    eax, eax
0x18007333d  jnz     short loc_180073350
0x18007333f  mov     rcx, rdi; hMem
0x180073342  call    cs:__imp_LocalFree
0x180073349  nop     dword ptr [rax+rax+00h]
0x18007334e  xor     edi, edi
0x180073350  mov     rcx, rsi; hMem
0x180073353  call    cs:__imp_LocalFree
0x18007335a  nop     dword ptr [rax+rax+00h]
0x18007335f  mov     rax, rdi
0x180073362  add     rsp, 30h
0x180073366  pop     rdi
0x180073367  pop     rsi
0x180073368  pop     rbx
0x180073369  retn
```
