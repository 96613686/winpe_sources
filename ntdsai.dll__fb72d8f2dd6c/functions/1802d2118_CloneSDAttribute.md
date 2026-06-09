# CloneSDAttribute

- ea: `0x1802d2118`
- end: `0x1802d24af`
- name: `CloneSDAttribute`
- size: `919`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1802d24b8`
- `0x1802d4c68`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x1801737f0`
- `0x1802d1f90`
- `0x1802d2118`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1802d227e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1802d227e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1802d237c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1802d237c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1802d2392`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1802d2392`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1802d2336`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1802d2336`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1802d2351`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1802d2351`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1802d2366`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1802d2366`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1802d23bf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1802d241a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1802d23bf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1802d241a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d239c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d23c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d23d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d2443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d239c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d23c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d23d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d2443`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802d2221`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802d2221`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802d21d7`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802d21d7`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802d21a8`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802d21a8`
- `ntdll!RtlCreateAcl` at `0x1802d22b5`
- `ntdll!RtlCreateAcl` at `0x1802d22b5`

## pseudocode

```c
__int64 __fastcall CloneSDAttribute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  void *v8; // rbx
  NTSTATUS OwnerSecurityDescriptor; // eax
  NTSTATUS GroupSecurityDescriptor; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  ULONG v12; // ebx
  struct _ACL *v13; // r14
  NTSTATUS Acl; // eax
  PACL v15; // rcx
  unsigned int v16; // edi
  PACL i; // rbx
  BOOL v18; // ebx
  DWORD LastError; // eax
  DWORD v20; // eax
  void *v21; // rbx
  int v22; // r8d
  int v23; // r9d
  DWORD v24; // eax
  DWORD *v25; // rax
  DWORD v26; // ecx
  __int64 result; // rax
  DWORD dwDaclSize; // [rsp+60h] [rbp-39h] BYREF
  PACL Dacl; // [rsp+68h] [rbp-31h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+70h] [rbp-29h] BYREF
  DWORD dwOwnerSize; // [rsp+74h] [rbp-25h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+78h] [rbp-21h] BYREF
  int v33; // [rsp+7Ch] [rbp-1Dh] BYREF
  PSID Owner; // [rsp+80h] [rbp-19h] BYREF
  PSID Group; // [rsp+88h] [rbp-11h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v37; // [rsp+B0h] [rbp+17h]
  unsigned __int8 OwnerDefaulted; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned __int8 DaclPresent; // [rsp+110h] [rbp+77h] BYREF
  DWORD dwBufferLength; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = a2 + 16;
  Owner = 0;
  v37 = 0;
  Group = 0;
  Dacl = 0;
  DaclPresent = 0;
  OwnerDefaulted = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  dwBufferLength = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  if ( *(_DWORD *)(a2 + 8) != 1 || !**(_DWORD **)v4 )
    DraExcept(8409, 0, 19202952, 1);
  v8 = *(void **)(*(_QWORD *)v4 + 8LL);
  OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v8, &Owner, &OwnerDefaulted);
  if ( OwnerSecurityDescriptor < 0 )
    DraExcept(3221225703LL, OwnerSecurityDescriptor, 19202961, 1);
  GroupSecurityDescriptor = RtlGetGroupSecurityDescriptor(v8, &Group, &OwnerDefaulted);
  if ( GroupSecurityDescriptor < 0 )
    DraExcept(3221225703LL, GroupSecurityDescriptor, 19202968, 1);
  if ( *(_QWORD *)(a3 + 1640) )
  {
    v33 = 0;
    dwDaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v8, &DaclPresent, &Dacl, &OwnerDefaulted);
    if ( DaclSecurityDescriptor < 0 )
      DraExcept(3221225703LL, DaclSecurityDescriptor, 19202992, 1);
    MakeAbsoluteSD(
      v8,
      0,
      &dwAbsoluteSecurityDescriptorSize,
      0,
      &dwDaclSize,
      0,
      &dwDaclSize,
      0,
      &dwOwnerSize,
      0,
      &dwPrimaryGroupSize);
    v12 = dwDaclSize;
    v13 = (struct _ACL *)THAlloc_(a1, 1, dwDaclSize, 1, 0, 19203003);
    Acl = RtlCreateAcl(v13, v12, Dacl->AclRevision);
    if ( Acl < 0 )
      DraExcept(3221225703LL, Acl, 19203009, 1);
    v15 = Dacl;
    v16 = 0;
    for ( i = Dacl + 1; v16 < v15->AceCount; i = (PACL)((char *)i + i->AclSize) )
    {
      if ( (i->Sbz1 & 0x10) == 0 )
      {
        CloneAce(a1, v15, i, a3, &v33, v13);
        v15 = Dacl;
      }
      ++v16;
    }
    v18 = 1;
  }
  else
  {
    v13 = 0;
    v18 = 0;
  }
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorOwner(pSecurityDescriptor, Owner, 0)
    || !SetSecurityDescriptorGroup(pSecurityDescriptor, Group, 0)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, v18, v13, 0)
    || !SetSecurityDescriptorSacl(pSecurityDescriptor, 0, 0, 0) )
  {
    LastError = GetLastError();
    DraExcept(8430, LastError, 19203034, 1);
  }
  if ( !MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength) && GetLastError() != 122 )
  {
    v20 = GetLastError();
    DraExcept(8430, v20, 19203039, 1);
  }
  v21 = (void *)THAlloc_(a1, 1, dwBufferLength, 1, 0, 19203042);
  if ( !MakeSelfRelativeSD(pSecurityDescriptor, v21, &dwBufferLength) )
  {
    if ( v21 )
      THFreeAux(a1, (_DWORD)v21, v22, v23, 19203044);
    v21 = 0;
    dwBufferLength = 0;
    v24 = GetLastError();
    DraExcept(8430, v24, 19203047, 1);
  }
  v25 = (DWORD *)THAlloc_(a1, 1, 16, 1, 0, 19203050);
  v26 = dwBufferLength;
  *(_QWORD *)(a4 + 8) = v25;
  *(_DWORD *)a4 = 1;
  *v25 = v26;
  result = *(_QWORD *)(a4 + 8);
  *(_QWORD *)(result + 8) = v21;
  return result;
}

```

## disassembly

```asm
0x1802d2118  mov     [rsp-8+arg_0], rbx
0x1802d211d  push    rbp
0x1802d211e  push    rsi
0x1802d211f  push    rdi
0x1802d2120  push    r12
0x1802d2122  push    r13
0x1802d2124  push    r14
0x1802d2126  push    r15
0x1802d2128  lea     rbp, [rsp-27h]
0x1802d212d  sub     rsp, 0C0h
0x1802d2134  xor     r13d, r13d
0x1802d2137  lea     rbx, [rdx+10h]
0x1802d213b  xor     eax, eax
0x1802d213d  mov     [rbp+57h+Owner], r13
0x1802d2141  xorps   xmm0, xmm0
0x1802d2144  mov     [rbp+57h+var_40], rax
0x1802d2148  mov     r12, r9
0x1802d214b  mov     [rbp+57h+Group], r13
0x1802d214f  mov     r15, r8
0x1802d2152  mov     [rbp+57h+Dacl], r13
0x1802d2156  lea     edi, [rax+1]
0x1802d2159  mov     [rbp+57h+DaclPresent], r13b
0x1802d215d  mov     rsi, rcx
0x1802d2160  mov     [rbp+57h+OwnerDefaulted], r13b
0x1802d2164  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1802d2168  mov     [rbp+57h+dwBufferLength], r13d
0x1802d216c  movups  [rbp+57h+var_50], xmm0
0x1802d2170  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x1802d2174  cmp     [rdx+8], edi
0x1802d2177  jnz     short loc_1802D2181
0x1802d2179  mov     rax, [rbx]
0x1802d217c  cmp     [rax], r13d
0x1802d217f  jnz     short loc_1802D2196
0x1802d2181  mov     r9d, edi
0x1802d2184  xor     edx, edx
0x1802d2186  mov     ecx, 20D9h
0x1802d218b  mov     r8d, 1250388h
0x1802d2191  call    DraExcept
0x1802d2196  mov     rax, [rbx]
0x1802d2199  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x1802d219d  lea     rdx, [rbp+57h+Owner]; Owner
0x1802d21a1  mov     rbx, [rax+8]
0x1802d21a5  mov     rcx, rbx; SecurityDescriptor
0x1802d21a8  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1802d21ae  mov     r14d, 0C00000E7h
0x1802d21b4  test    eax, eax
0x1802d21b6  jns     short loc_1802D21CC
0x1802d21b8  movsxd  rdx, eax
0x1802d21bb  mov     r9d, edi
0x1802d21be  mov     r8d, 1250391h
0x1802d21c4  mov     ecx, r14d
0x1802d21c7  call    DraExcept
0x1802d21cc  lea     r8, [rbp+57h+OwnerDefaulted]; GroupDefaulted
0x1802d21d0  mov     rcx, rbx; SecurityDescriptor
0x1802d21d3  lea     rdx, [rbp+57h+Group]; Group
0x1802d21d7  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1802d21dd  test    eax, eax
0x1802d21df  jns     short loc_1802D21F5
0x1802d21e1  movsxd  rdx, eax
0x1802d21e4  mov     r9d, edi
0x1802d21e7  mov     r8d, 1250398h
0x1802d21ed  mov     ecx, r14d
0x1802d21f0  call    DraExcept
0x1802d21f5  cmp     [r15+668h], r13
0x1802d21fc  jz      loc_1802D232A
0x1802d2202  lea     r9, [rbp+57h+OwnerDefaulted]; DaclDefaulted
0x1802d2206  mov     [rbp+57h+var_74], r13d
0x1802d220a  lea     r8, [rbp+57h+Dacl]; Dacl
0x1802d220e  mov     [rbp+57h+dwDaclSize], r13d
0x1802d2212  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1802d2216  mov     [rbp+57h+dwOwnerSize], r13d
0x1802d221a  mov     rcx, rbx; SecurityDescriptor
0x1802d221d  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x1802d2221  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1802d2227  test    eax, eax
0x1802d2229  jns     short loc_1802D223F
0x1802d222b  movsxd  rdx, eax
0x1802d222e  mov     r9d, edi
0x1802d2231  mov     r8d, 12503B0h
0x1802d2237  mov     ecx, r14d
0x1802d223a  call    DraExcept
0x1802d223f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1802d2243  xor     r9d, r9d; pDacl
0x1802d2246  mov     [rsp+0F0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1802d224b  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1802d224f  mov     [rsp+0F0h+pPrimaryGroup], r13; pPrimaryGroup
0x1802d2254  lea     rax, [rbp+57h+dwOwnerSize]
0x1802d2258  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1802d225d  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1802d225f  mov     [rsp+0F0h+pOwner], r13; pOwner
0x1802d2264  lea     rax, [rbp+57h+dwDaclSize]
0x1802d2268  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x1802d226d  mov     rcx, rbx; pSelfRelativeSecurityDescriptor
0x1802d2270  lea     rax, [rbp+57h+dwDaclSize]
0x1802d2274  mov     [rsp+0F0h+pSacl], r13; pSacl
0x1802d2279  mov     [rsp+0F0h+lpdwDaclSize], rax; lpdwDaclSize
0x1802d227e  call    cs:__imp_MakeAbsoluteSD
0x1802d2284  mov     ebx, [rbp+57h+dwDaclSize]
0x1802d2287  mov     r9d, edi
0x1802d228a  mov     r8d, ebx
0x1802d228d  mov     dword ptr [rsp+0F0h+pSacl], 12503BBh
0x1802d2295  mov     rdx, rdi
0x1802d2298  mov     dword ptr [rsp+0F0h+lpdwDaclSize], r13d
0x1802d229d  mov     rcx, rsi
0x1802d22a0  call    THAlloc_
0x1802d22a5  mov     r8, [rbp+57h+Dacl]
0x1802d22a9  mov     edx, ebx; AclSize
0x1802d22ab  mov     rcx, rax; Acl
0x1802d22ae  mov     r14, rax
0x1802d22b1  movzx   r8d, byte ptr [r8]; AclRevision
0x1802d22b5  call    cs:__imp_RtlCreateAcl
0x1802d22bb  test    eax, eax
0x1802d22bd  jns     short loc_1802D22D5
0x1802d22bf  movsxd  rdx, eax
0x1802d22c2  mov     r9d, edi
0x1802d22c5  mov     ecx, 0C00000E7h
0x1802d22ca  mov     r8d, 12503C1h
0x1802d22d0  call    DraExcept
0x1802d22d5  mov     rcx, [rbp+57h+Dacl]
0x1802d22d9  mov     edi, r13d
0x1802d22dc  lea     rbx, [rcx+8]
0x1802d22e0  cmp     r13w, [rcx+4]
0x1802d22e5  jnb     short loc_1802D2321
0x1802d22e7  test    byte ptr [rbx+1], 10h
0x1802d22eb  jnz     short loc_1802D2310
0x1802d22ed  lea     rax, [rbp+57h+var_74]
0x1802d22f1  mov     [rsp+0F0h+pSacl], r14
0x1802d22f6  mov     rdx, rcx
0x1802d22f9  mov     [rsp+0F0h+lpdwDaclSize], rax
0x1802d22fe  mov     rcx, rsi
0x1802d2301  mov     r9, r15
0x1802d2304  mov     r8, rbx
0x1802d2307  call    CloneAce
0x1802d230c  mov     rcx, [rbp+57h+Dacl]
0x1802d2310  movzx   eax, word ptr [rbx+2]
0x1802d2314  inc     edi
0x1802d2316  add     rbx, rax
0x1802d2319  movzx   eax, word ptr [rcx+4]
0x1802d231d  cmp     edi, eax
0x1802d231f  jb      short loc_1802D22E7
0x1802d2321  mov     edi, 1
0x1802d2326  mov     ebx, edi
0x1802d2328  jmp     short loc_1802D2330
0x1802d232a  mov     r14, r13
0x1802d232d  mov     ebx, r13d
0x1802d2330  mov     edx, edi; dwRevision
0x1802d2332  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1802d2336  call    cs:__imp_InitializeSecurityDescriptor
0x1802d233c  mov     r15d, 20EEh
0x1802d2342  test    eax, eax
0x1802d2344  jz      short loc_1802D239C
0x1802d2346  mov     rdx, [rbp+57h+Owner]; pOwner
0x1802d234a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1802d234e  xor     r8d, r8d; bOwnerDefaulted
0x1802d2351  call    cs:__imp_SetSecurityDescriptorOwner
0x1802d2357  test    eax, eax
0x1802d2359  jz      short loc_1802D239C
0x1802d235b  mov     rdx, [rbp+57h+Group]; pGroup
0x1802d235f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1802d2363  xor     r8d, r8d; bGroupDefaulted
0x1802d2366  call    cs:__imp_SetSecurityDescriptorGroup
0x1802d236c  test    eax, eax
0x1802d236e  jz      short loc_1802D239C
0x1802d2370  xor     r9d, r9d; bDaclDefaulted
0x1802d2373  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1802d2377  mov     r8, r14; pDacl
0x1802d237a  mov     edx, ebx; bDaclPresent
0x1802d237c  call    cs:__imp_SetSecurityDescriptorDacl
0x1802d2382  test    eax, eax
0x1802d2384  jz      short loc_1802D239C
0x1802d2386  xor     r9d, r9d; bSaclDefaulted
0x1802d2389  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1802d238d  xor     r8d, r8d; pSacl
0x1802d2390  xor     edx, edx; bSaclPresent
0x1802d2392  call    cs:__imp_SetSecurityDescriptorSacl
0x1802d2398  test    eax, eax
0x1802d239a  jnz     short loc_1802D23B5
0x1802d239c  call    cs:__imp_GetLastError
0x1802d23a2  mov     edx, eax
0x1802d23a4  mov     r9d, edi
0x1802d23a7  mov     r8d, 12503DAh
0x1802d23ad  mov     ecx, r15d
0x1802d23b0  call    DraExcept
0x1802d23b5  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1802d23b9  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1802d23bb  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1802d23bf  call    cs:__imp_MakeSelfRelativeSD
0x1802d23c5  test    eax, eax
0x1802d23c7  jnz     short loc_1802D23ED
0x1802d23c9  call    cs:__imp_GetLastError
0x1802d23cf  cmp     eax, 7Ah ; 'z'
0x1802d23d2  jz      short loc_1802D23ED
0x1802d23d4  call    cs:__imp_GetLastError
0x1802d23da  mov     edx, eax
0x1802d23dc  mov     r9d, edi
0x1802d23df  mov     r8d, 12503DFh
0x1802d23e5  mov     ecx, r15d
0x1802d23e8  call    DraExcept
0x1802d23ed  mov     r8d, [rbp+57h+dwBufferLength]
0x1802d23f1  mov     r9d, edi
0x1802d23f4  mov     dword ptr [rsp+0F0h+pSacl], 12503E2h
0x1802d23fc  mov     rdx, rdi
0x1802d23ff  mov     rcx, rsi
0x1802d2402  mov     dword ptr [rsp+0F0h+lpdwDaclSize], r13d
0x1802d2407  call    THAlloc_
0x1802d240c  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1802d2410  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1802d2413  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1802d2417  mov     rbx, rax
0x1802d241a  call    cs:__imp_MakeSelfRelativeSD
0x1802d2420  test    eax, eax
0x1802d2422  jnz     short loc_1802D245C
0x1802d2424  test    rbx, rbx
0x1802d2427  jz      short loc_1802D243C
0x1802d2429  mov     rdx, rbx
0x1802d242c  mov     dword ptr [rsp+0F0h+lpdwDaclSize], 12503E4h
0x1802d2434  mov     rcx, rsi
0x1802d2437  call    THFreeAux
0x1802d243c  mov     rbx, r13
0x1802d243f  mov     [rbp+57h+dwBufferLength], r13d
0x1802d2443  call    cs:__imp_GetLastError
0x1802d2449  mov     edx, eax
0x1802d244b  mov     r9d, edi
0x1802d244e  mov     r8d, 12503E7h
0x1802d2454  mov     ecx, r15d
0x1802d2457  call    DraExcept
0x1802d245c  mov     dword ptr [rsp+0F0h+pSacl], 12503EAh
0x1802d2464  mov     r9d, edi
0x1802d2467  mov     r8d, 10h
0x1802d246d  mov     dword ptr [rsp+0F0h+lpdwDaclSize], r13d
0x1802d2472  mov     rdx, rdi
0x1802d2475  mov     rcx, rsi
0x1802d2478  call    THAlloc_
0x1802d247d  mov     ecx, [rbp+57h+dwBufferLength]
0x1802d2480  mov     [r12+8], rax
0x1802d2485  mov     [r12], edi
0x1802d2489  mov     [rax], ecx
0x1802d248b  mov     rax, [r12+8]
0x1802d2490  mov     [rax+8], rbx
0x1802d2494  mov     rbx, [rsp+0F0h+arg_0]
0x1802d249c  add     rsp, 0C0h
0x1802d24a3  pop     r15
0x1802d24a5  pop     r14
0x1802d24a7  pop     r13
0x1802d24a9  pop     r12
0x1802d24ab  pop     rdi
0x1802d24ac  pop     rsi
0x1802d24ad  pop     rbp
0x1802d24ae  retn
```
