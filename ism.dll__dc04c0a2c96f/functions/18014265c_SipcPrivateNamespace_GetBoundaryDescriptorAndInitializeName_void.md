# SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)

- ea: `0x18014265c`
- end: `0x18014278d`
- name: `?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18014202c`
- `0x180142ffc`

## callees

- `0x1800f0990`
- `0x18014265c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801426f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801426f6`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18014274c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18014274c`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18014273c`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18014275e`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18014273c`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x18014275e`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18014271b`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18014271b`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1801426e7`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1801426e7`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(SipcPrivateNamespace *this, void **a2)
{
  char *v3; // rcx
  unsigned __int64 v5; // r9
  _WORD *v6; // r8
  unsigned int v7; // edx
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE BoundaryDescriptor; // [rsp+20h] [rbp-20h] BYREF
  int RequiredSid; // [rsp+28h] [rbp-18h] BYREF
  __int64 v13; // [rsp+2Ch] [rbp-14h]

  *a2 = 0;
  v3 = (char *)this + 8;
  v5 = 0;
  v6 = (_WORD *)((char *)this + 18);
  *(_QWORD *)v3 = SipcPrivateNamespace::NamespacePrefix;
  *((_DWORD *)v3 + 2) = 95;
  do
  {
    v7 = *((unsigned __int8 *)this + v5++ + 84);
    *v6 = a0123456789abcd[(unsigned __int64)v7 >> 4];
    v6 += 2;
    *(v6 - 1) = a0123456789abcd[v7 & 0xF];
  }
  while ( v5 < 0x10 );
  *v6 = 0;
  BoundaryDescriptor = CreateBoundaryDescriptorW((LPCWSTR)v3, 0);
  if ( BoundaryDescriptor
    && (RequiredSid = 257, v13 = 0x1000000, AddSIDToBoundaryDescriptor(&BoundaryDescriptor, &RequiredSid))
    && (IsWellKnownSid((char *)this + 100, WinNullSid)
     || AddSIDToBoundaryDescriptor(&BoundaryDescriptor, (char *)this + 100)) )
  {
    *a2 = BoundaryDescriptor;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = -2147418113;
    if ( LastError < 0 )
      v9 = LastError;
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return v9;
  }
}

```

## disassembly

```asm
0x18014265c  mov     [rsp-8+arg_10], rbx
0x180142661  mov     [rsp-8+arg_18], rdi
0x180142666  push    rbp
0x180142667  mov     rbp, rsp
0x18014266a  sub     rsp, 40h
0x18014266e  mov     rax, cs:__security_cookie
0x180142675  xor     rax, rsp
0x180142678  mov     [rbp+var_8], rax
0x18014267c  mov     qword ptr [rdx], 0
0x180142683  lea     r10, a0123456789abcd; "0123456789ABCDEF"
0x18014268a  movsd   xmm0, cs:?NamespacePrefix@SipcPrivateNamespace@@0QBGB; ushort const near * const SipcPrivateNamespace::NamespacePrefix
0x180142692  mov     rbx, rcx
0x180142695  add     rcx, 8; Name
0x180142699  mov     rdi, rdx
0x18014269c  xor     r9d, r9d
0x18014269f  lea     r8, [rbx+12h]
0x1801426a3  movsd   qword ptr [rcx], xmm0
0x1801426a7  mov     eax, cs:dword_1801FB398
0x1801426ad  mov     [rcx+8], eax
0x1801426b0  movzx   edx, byte ptr [rbx+r9+54h]
0x1801426b6  inc     r9
0x1801426b9  mov     eax, edx
0x1801426bb  and     edx, 0Fh
0x1801426be  shr     rax, 4
0x1801426c2  movzx   eax, word ptr [r10+rax*2]
0x1801426c7  mov     [r8], ax
0x1801426cb  lea     r8, [r8+4]
0x1801426cf  movzx   eax, word ptr [r10+rdx*2]
0x1801426d4  mov     [r8-2], ax
0x1801426d9  cmp     r9, 10h
0x1801426dd  jb      short loc_1801426B0
0x1801426df  xor     eax, eax
0x1801426e1  xor     edx, edx; Flags
0x1801426e3  mov     [r8], ax
0x1801426e7  call    cs:__imp_CreateBoundaryDescriptorW
0x1801426ed  mov     [rbp+BoundaryDescriptor], rax
0x1801426f1  test    rax, rax
0x1801426f4  jnz     short loc_180142725
0x1801426f6  call    cs:__imp_GetLastError
0x1801426fc  test    eax, eax
0x1801426fe  jle     short loc_180142708
0x180142700  movzx   eax, ax
0x180142703  or      eax, 80070000h
0x180142708  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x18014270c  test    eax, eax
0x18014270e  mov     ebx, 8000FFFFh
0x180142713  cmovs   ebx, eax
0x180142716  test    rcx, rcx
0x180142719  jz      short loc_180142721
0x18014271b  call    cs:__imp_DeleteBoundaryDescriptor
0x180142721  mov     eax, ebx
0x180142723  jmp     short loc_180142771
0x180142725  lea     rdx, [rbp+RequiredSid]; RequiredSid
0x180142729  mov     [rbp+RequiredSid], 101h
0x180142730  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180142734  mov     [rbp+var_14], 1000000h
0x18014273c  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180142742  test    eax, eax
0x180142744  jz      short loc_1801426F6
0x180142746  xor     edx, edx; WellKnownSidType
0x180142748  lea     rcx, [rbx+64h]; pSid
0x18014274c  call    cs:__imp_IsWellKnownSid
0x180142752  test    eax, eax
0x180142754  jnz     short loc_180142768
0x180142756  lea     rdx, [rbx+64h]; RequiredSid
0x18014275a  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x18014275e  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180142764  test    eax, eax
0x180142766  jz      short loc_1801426F6
0x180142768  mov     rax, [rbp+BoundaryDescriptor]
0x18014276c  mov     [rdi], rax
0x18014276f  xor     eax, eax
0x180142771  mov     rcx, [rbp+var_8]
0x180142775  xor     rcx, rsp; StackCookie
0x180142778  call    __security_check_cookie
0x18014277d  mov     rbx, [rsp+40h+arg_10]
0x180142782  mov     rdi, [rsp+40h+arg_18]
0x180142787  add     rsp, 40h
0x18014278b  pop     rbp
0x18014278c  retn
```
