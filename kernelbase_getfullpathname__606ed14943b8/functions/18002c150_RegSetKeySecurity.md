# RegSetKeySecurity

- ea: `0x18002c150`
- end: `0x18002c75d`
- name: `RegSetKeySecurity`
- size: `1549`
- prototype: `LSTATUS __stdcall(HKEY hKey, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a4384`
- `0x1801172e4`

## callees

- `0x18002c150`
- `0x18002c770`
- `0x18002d7e0`
- `0x18002e0c4`
- `0x18005e040`
- `0x18005e7e0`
- `0x18005fcf0`
- `0x180060700`
- `0x180060db0`
- `0x1801369c9`
- `0x180136e28`
- `0x180139854`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002c313`
- `ntdll!RtlNtStatusToDosError` at `0x18002c3ae`
- `ntdll!RtlNtStatusToDosError` at `0x18002c6a6`
- `ntdll!RtlNtStatusToDosError` at `0x18002c313`
- `ntdll!RtlNtStatusToDosError` at `0x18002c3ae`
- `ntdll!RtlNtStatusToDosError` at `0x18002c6a6`
- `ntdll!NtClose` at `0x18002c742`
- `ntdll!NtClose` at `0x18002c742`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c5fd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002c5fd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c633`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002c633`
- `ntdll!RtlValidSecurityDescriptor` at `0x18002c293`
- `ntdll!RtlValidSecurityDescriptor` at `0x18002c293`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002c2aa`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002c2aa`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18002c305`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18002c305`
- `ntdll!NtSetSecurityObject` at `0x18002c396`
- `ntdll!NtSetSecurityObject` at `0x18002c396`
- `ntdll!RtlFreeHeap` at `0x18002c3d0`
- `ntdll!RtlFreeHeap` at `0x18002c724`
- `ntdll!RtlFreeHeap` at `0x18002c3d0`
- `ntdll!RtlFreeHeap` at `0x18002c724`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002c377`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18002c377`
- `ntdll!RtlAllocateHeap` at `0x18002c2d8`
- `ntdll!RtlAllocateHeap` at `0x18002c2d8`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetKeySecurity` at `0x18002c59b`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetKeySecurity` at `0x18002c59b`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetKeySecurity` at `0x18002c675`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetKeySecurity` at `0x18002c675`

## pseudocode

```c
LSTATUS __stdcall RegSetKeySecurity(
        HKEY hKey,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  HKEY *v6; // rbx
  HKEY v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r13d
  int v10; // eax
  LSTATUS result; // eax
  ULONG v12; // esi
  HANDLE v13; // r12
  void *v14; // r12
  ULONG v15; // edi
  PVOID Heap; // rax
  NTSTATUS SelfRelativeSD; // eax
  HANDLE v18; // rdi
  int v19; // esi
  __int64 v20; // rdi
  NTSTATUS KeySemantics; // eax
  int v22; // eax
  void **v23; // rcx
  void *v24; // rax
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  HANDLE Handle; // [rsp+40h] [rbp-258h] BYREF
  ULONG BufferLength[4]; // [rsp+48h] [rbp-250h] BYREF
  HANDLE v32; // [rsp+58h] [rbp-240h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-238h] BYREF
  ULONG v34; // [rsp+68h] [rbp-230h]
  HANDLE v35; // [rsp+70h] [rbp-228h] BYREF
  void *v36; // [rsp+78h] [rbp-220h]
  HKEY v37; // [rsp+80h] [rbp-218h] BYREF
  __int64 v38; // [rsp+88h] [rbp-210h] BYREF
  int v39; // [rsp+90h] [rbp-208h] BYREF
  __int64 v40; // [rsp+94h] [rbp-204h]
  int v41; // [rsp+9Ch] [rbp-1FCh]
  PVOID P; // [rsp+A0h] [rbp-1F8h]
  UNICODE_STRING Source; // [rsp+A8h] [rbp-1F0h] BYREF
  _BYTE v44[400]; // [rsp+C0h] [rbp-1D8h] BYREF

  Handle = hKey;
  *(_OWORD *)BufferLength = 0;
  v6 = 0;
  v37 = 0;
  v38 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  v7 = hKey + 0x20000000;
  v8 = 239;
  if ( ((unsigned __int64)v7 > 7 || !_bittest64(&v8, (unsigned __int64)v7))
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT
    || (SecurityInformation & 8) == 0 )
  {
    hKeya = 0;
    v12 = MapPredefinedHandleInternal(hKey, &Handle, &v37, &v38);
    v9 = 0x2000000;
    v13 = Handle;
LABEL_14:
    if ( !v12 )
    {
      v36 = 0;
      if ( ((unsigned __int8)v13 & 1) != 0 || ((unsigned __int8)v13 & 2) == 0 && hKey != HKEY_CLASSES_ROOT )
        goto LABEL_16;
      v40 = 0;
      Source = 0;
      memset_0(v44, 0, 0x18Au);
      v32 = 0;
      v35 = 0;
      P = v44;
      v41 = 394;
      v39 = 0;
      KeySemantics = BaseRegGetKeySemantics(v13, &Source);
      if ( KeySemantics >= 0 )
      {
        if ( (v39 & 2) != 0 )
        {
          v32 = v13;
          v22 = 2;
          v23 = &v35;
        }
        else
        {
          v35 = v13;
          v22 = 1;
          v23 = &v32;
        }
        BaseRegOpenClassKeyFromLocation(&v39, v13, &Source, v9 & 0x1000300 | 0x2000000, v22, 0, v23, 0);
        if ( (v39 & 0x20) != 0 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        if ( v32 )
        {
          v24 = v35;
          if ( v35 )
          {
            v14 = v35;
            if ( v32 != Handle )
              v14 = v32;
            v36 = v14;
            if ( hKey == HKEY_CLASSES_ROOT )
              v24 = v32;
            Handle = v24;
LABEL_17:
            *(_QWORD *)BufferLength = 0;
            if ( !RtlValidSecurityDescriptor(pSecurityDescriptor) )
            {
              v12 = 87;
              goto LABEL_22;
            }
            v15 = RtlLengthSecurityDescriptor(pSecurityDescriptor);
            Heap = *(PVOID *)BufferLength;
            if ( *(_QWORD *)BufferLength )
            {
              if ( BufferLength[2] >= v15 )
                goto LABEL_21;
              v12 = 14;
            }
            else
            {
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
              *(_QWORD *)BufferLength = Heap;
              if ( Heap )
              {
                BufferLength[2] = v15;
LABEL_21:
                BufferLength[3] = v15;
                SelfRelativeSD = RtlMakeSelfRelativeSD(pSecurityDescriptor, Heap, &BufferLength[2]);
                v12 = RtlNtStatusToDosError(SelfRelativeSD);
LABEL_22:
                Heap = *(PVOID *)BufferLength;
                goto LABEL_23;
              }
              v12 = 14;
            }
LABEL_23:
            if ( !v12 )
            {
              v18 = Handle;
              if ( ((unsigned __int8)Handle & 1) != 0 )
              {
                if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
                {
                  v12 = BaseRegSetKeySecurity(
                          (unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL,
                          SecurityInformation,
                          BufferLength);
                  v34 = v12;
                }
              }
              else if ( Heap )
              {
                if ( Handle == (HANDLE)-2147483644LL
                  || Handle == (HANDLE)-2147483568LL
                  || Handle == (HANDLE)-2147483552LL )
                {
                  v19 = -1073741816;
                }
                else
                {
                  if ( RtlValidRelativeSecurityDescriptor(Heap, BufferLength[2], SecurityInformation) )
                    v19 = NtSetSecurityObject(v18, SecurityInformation, *(PSECURITY_DESCRIPTOR *)BufferLength);
                  else
                    v19 = -1073741811;
                  if ( v19 >= 0 && (unsigned __int8)IsTermsrvDeleteKeyPresent() )
                    TermsrvSetKeySecurity(v18, SecurityInformation, *(_QWORD *)BufferLength);
                }
                v12 = RtlNtStatusToDosError(v19);
              }
              else
              {
                v12 = 87;
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)BufferLength);
              if ( v14 )
                NtClose(v14);
            }
            goto LABEL_35;
          }
        }
LABEL_16:
        v14 = 0;
        goto LABEL_17;
      }
      v12 = RtlNtStatusToDosError(KeySemantics);
    }
LABEL_35:
    if ( hKeya )
      RegCloseKey(hKeya);
    hKeya = v37;
    v20 = v38;
    if ( v37 )
      BaseRegCloseKeyInternal(&hKeya);
    if ( v20 )
    {
      RtlAcquireSRWLockExclusive(&PredefinedHandleTableSRWLock);
      if ( (*(_DWORD *)(v20 + 8))-- == 1 )
      {
        v26 = *(_QWORD **)(v20 + 16);
        v27 = v26[1];
        if ( v20 != v27 || *(_QWORD *)v20 != *v26 )
        {
          v6 = (HKEY *)v20;
          v28 = RemoveUnitFromList(v27, v20, *(_QWORD *)(v20 + 16));
          *(_QWORD *)(v29 + 8) = v28;
        }
      }
      RtlReleaseSRWLockExclusive(&PredefinedHandleTableSRWLock);
      if ( v6 )
      {
        RegCloseKey(*v6);
        FreeEnvironmentStringsW((LPWCH)v6);
      }
    }
    return v12;
  }
  if ( (SecurityInformation & 4) != 0 )
  {
    v9 = 50593792;
  }
  else
  {
    v9 = 50331648;
    if ( (SecurityInformation & 1) != 0 )
      v9 = 50855936;
  }
  if ( ((unsigned __int64)(hKey + 0x20000000) > 7 || !_bittest64(&v8, (unsigned __int64)(hKey + 0x20000000)))
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT )
  {
    return 1010;
  }
  v10 = MapPredefinedRegistryHandleToIndex((unsigned int)hKey);
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, HANDLE *))*(&off_1803A41E0 + 4 * v10))(0, v9, &Handle);
  if ( !result )
  {
    v12 = 0;
    v13 = Handle;
    hKeya = (HKEY)Handle;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x18002c150  push    rbx
0x18002c152  push    rsi
0x18002c153  push    rdi
0x18002c154  push    r12
0x18002c156  push    r13
0x18002c158  push    r14
0x18002c15a  push    r15
0x18002c15c  sub     rsp, 260h
0x18002c163  mov     rax, cs:__security_cookie
0x18002c16a  xor     rax, rsp
0x18002c16d  mov     [rsp+298h+var_48], rax
0x18002c175  mov     r14, r8
0x18002c178  mov     r15d, edx
0x18002c17b  mov     rdi, rcx
0x18002c17e  mov     [rsp+298h+Handle], rcx
0x18002c183  xorps   xmm0, xmm0
0x18002c186  movups  xmmword ptr [rsp+298h+BufferLength], xmm0
0x18002c18b  xor     ebx, ebx
0x18002c18d  mov     [rsp+298h+var_218], rbx
0x18002c195  mov     [rsp+298h+var_210], rbx
0x18002c19d  cmp     rcx, 0FFFFFFFF80000004h
0x18002c1a4  jz      loc_18002C573
0x18002c1aa  mov     edx, 80000000h
0x18002c1af  lea     rax, [rcx+rdx]
0x18002c1b3  mov     ecx, 0EFh
0x18002c1b8  cmp     rax, 7
0x18002c1bc  ja      short loc_18002C230
0x18002c1be  bt      rcx, rax
0x18002c1c2  jnb     short loc_18002C230
0x18002c1c4  test    r15b, 8
0x18002c1c8  jz      short loc_18002C242
0x18002c1ca  test    r15b, 4
0x18002c1ce  jz      loc_18002C6D1
0x18002c1d4  mov     r13d, 3040000h
0x18002c1da  lea     rax, [rdi+rdx]
0x18002c1de  cmp     rax, 7
0x18002c1e2  ja      loc_18002C6E9
0x18002c1e8  bt      rcx, rax
0x18002c1ec  jnb     loc_18002C6E9
0x18002c1f2  mov     ecx, edi
0x18002c1f4  call    MapPredefinedRegistryHandleToIndex
0x18002c1f9  movsxd  rcx, eax
0x18002c1fc  shl     rcx, 5
0x18002c200  lea     rax, off_1803A41E0
0x18002c207  mov     rax, [rcx+rax]
0x18002c20b  lea     r8, [rsp+298h+Handle]
0x18002c210  mov     edx, r13d
0x18002c213  xor     ecx, ecx
0x18002c215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c21a  test    eax, eax
0x18002c21c  jnz     loc_18002C422
0x18002c222  mov     esi, ebx
0x18002c224  mov     r12, [rsp+298h+Handle]
0x18002c229  mov     [rsp+298h+hKey], r12
0x18002c22e  jmp     short loc_18002C271
0x18002c230  cmp     rdi, 0FFFFFFFF80000050h
0x18002c237  jz      short loc_18002C1C4
0x18002c239  cmp     rdi, 0FFFFFFFF80000060h
0x18002c240  jz      short loc_18002C1C4
0x18002c242  mov     [rsp+298h+hKey], rbx
0x18002c247  lea     r9, [rsp+298h+var_210]
0x18002c24f  lea     r8, [rsp+298h+var_218]
0x18002c257  lea     rdx, [rsp+298h+Handle]
0x18002c25c  mov     rcx, rdi
0x18002c25f  call    MapPredefinedHandleInternal
0x18002c264  mov     esi, eax
0x18002c266  mov     r13d, 2000000h
0x18002c26c  mov     r12, [rsp+298h+Handle]
0x18002c271  test    esi, esi
0x18002c273  jnz     loc_18002C3E5
0x18002c279  mov     [rsp+298h+var_220], rbx
0x18002c27e  test    r12b, 1
0x18002c282  jz      loc_18002C446
0x18002c288  mov     r12, rbx
0x18002c28b  mov     qword ptr [rsp+298h+BufferLength], rbx
0x18002c290  mov     rcx, r14; SecurityDescriptor
0x18002c293  call    cs:__imp_RtlValidSecurityDescriptor
0x18002c29a  nop     dword ptr [rax+rax+00h]
0x18002c29f  test    al, al
0x18002c2a1  jz      loc_18002C5C4
0x18002c2a7  mov     rcx, r14; SecurityDescriptor
0x18002c2aa  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002c2b1  nop     dword ptr [rax+rax+00h]
0x18002c2b6  mov     edi, eax
0x18002c2b8  mov     rax, qword ptr [rsp+298h+BufferLength]
0x18002c2bd  test    rax, rax
0x18002c2c0  jnz     loc_18002C5E2
0x18002c2c6  mov     r8d, edi; Size
0x18002c2c9  mov     rcx, gs:60h
0x18002c2d2  xor     edx, edx; Flags
0x18002c2d4  mov     rcx, [rcx+30h]; HeapHandle
0x18002c2d8  call    cs:__imp_RtlAllocateHeap
0x18002c2df  nop     dword ptr [rax+rax+00h]
0x18002c2e4  mov     qword ptr [rsp+298h+BufferLength], rax
0x18002c2e9  test    rax, rax
0x18002c2ec  jz      loc_18002C69A
0x18002c2f2  mov     [rsp+298h+BufferLength+8], edi
0x18002c2f6  mov     [rsp+298h+BufferLength+0Ch], edi
0x18002c2fa  lea     r8, [rsp+298h+BufferLength+8]; BufferLength
0x18002c2ff  mov     rdx, rax; SelfRelativeSD
0x18002c302  mov     rcx, r14; AbsoluteSD
0x18002c305  call    cs:__imp_RtlMakeSelfRelativeSD
0x18002c30c  nop     dword ptr [rax+rax+00h]
0x18002c311  mov     ecx, eax; Status
0x18002c313  call    cs:__imp_RtlNtStatusToDosError
0x18002c31a  nop     dword ptr [rax+rax+00h]
0x18002c31f  mov     esi, eax
0x18002c321  mov     rax, qword ptr [rsp+298h+BufferLength]
0x18002c326  test    esi, esi
0x18002c328  jnz     loc_18002C3E5
0x18002c32e  mov     rdi, [rsp+298h+Handle]
0x18002c333  test    dil, 1
0x18002c337  jnz     loc_18002C57D
0x18002c33d  test    rax, rax
0x18002c340  jz      loc_18002C735
0x18002c346  cmp     rdi, 0FFFFFFFF80000004h
0x18002c34d  jz      loc_18002C5D8
0x18002c353  cmp     rdi, 0FFFFFFFF80000050h
0x18002c35a  jz      loc_18002C5D8
0x18002c360  cmp     rdi, 0FFFFFFFF80000060h
0x18002c367  jz      loc_18002C5D8
0x18002c36d  mov     r8d, r15d; RequiredInformation
0x18002c370  mov     edx, [rsp+298h+BufferLength+8]; SecurityDescriptorLength
0x18002c374  mov     rcx, rax; SecurityDescriptorInput
0x18002c377  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18002c37e  nop     dword ptr [rax+rax+00h]
0x18002c383  test    al, al
0x18002c385  jz      loc_18002C5CE
0x18002c38b  mov     r8, qword ptr [rsp+298h+BufferLength]; SecurityDescriptor
0x18002c390  mov     edx, r15d; SecurityInformation
0x18002c393  mov     rcx, rdi; Handle
0x18002c396  call    cs:__imp_NtSetSecurityObject
0x18002c39d  nop     dword ptr [rax+rax+00h]
0x18002c3a2  mov     esi, eax
0x18002c3a4  test    esi, esi
0x18002c3a6  jns     loc_18002C65D
0x18002c3ac  mov     ecx, esi; Status
0x18002c3ae  call    cs:__imp_RtlNtStatusToDosError
0x18002c3b5  nop     dword ptr [rax+rax+00h]
0x18002c3ba  mov     esi, eax
0x18002c3bc  mov     rcx, gs:60h
0x18002c3c5  mov     r8, qword ptr [rsp+298h+BufferLength]; P
0x18002c3ca  xor     edx, edx; Flags
0x18002c3cc  mov     rcx, [rcx+30h]; HeapHandle
0x18002c3d0  call    cs:__imp_RtlFreeHeap
0x18002c3d7  nop     dword ptr [rax+rax+00h]
0x18002c3dc  test    r12, r12
0x18002c3df  jnz     loc_18002C73F
0x18002c3e5  mov     rcx, [rsp+298h+hKey]; hKey
0x18002c3ea  test    rcx, rcx
0x18002c3ed  jnz     loc_18002C753
0x18002c3f3  mov     rax, [rsp+298h+var_218]
0x18002c3fb  mov     [rsp+298h+hKey], rax
0x18002c400  mov     rdi, [rsp+298h+var_210]
0x18002c408  test    rax, rax
0x18002c40b  jz      short loc_18002C417
0x18002c40d  lea     rcx, [rsp+298h+hKey]
0x18002c412  call    BaseRegCloseKeyInternal
0x18002c417  test    rdi, rdi
0x18002c41a  jnz     loc_18002C5F6
0x18002c420  mov     eax, esi
0x18002c422  mov     rcx, [rsp+298h+var_48]
0x18002c42a  xor     rcx, rsp; StackCookie
0x18002c42d  call    __security_check_cookie
0x18002c432  add     rsp, 260h
0x18002c439  pop     r15
0x18002c43b  pop     r14
0x18002c43d  pop     r13
0x18002c43f  pop     r12
0x18002c441  pop     rdi
0x18002c442  pop     rsi
0x18002c443  pop     rbx
0x18002c444  retn
0x18002c446  test    r12b, 2
0x18002c44a  jnz     short loc_18002C459
0x18002c44c  cmp     rdi, 0FFFFFFFF80000000h
0x18002c453  jnz     loc_18002C288
0x18002c459  mov     [rsp+298h+var_204], rbx
0x18002c461  xorps   xmm0, xmm0
0x18002c464  movups  xmmword ptr [rsp+298h+Source.Length], xmm0
0x18002c46c  xor     edx, edx; Val
0x18002c46e  mov     r8d, 18Ah; Size
0x18002c474  lea     rcx, [rsp+298h+var_1D8]; void *
0x18002c47c  call    memset_0
0x18002c481  mov     [rsp+298h+var_240], rbx
0x18002c486  mov     [rsp+298h+var_228], rbx
0x18002c48b  lea     rax, [rsp+298h+var_1D8]
0x18002c493  mov     [rsp+298h+P], rax
0x18002c49b  mov     [rsp+298h+var_1FC], 18Ah
0x18002c4a6  mov     [rsp+298h+var_208], ebx
0x18002c4ad  lea     r8, [rsp+298h+var_208]
0x18002c4b5  lea     rdx, [rsp+298h+Source]; Source
0x18002c4bd  mov     rcx, r12; KeyHandle
0x18002c4c0  call    BaseRegGetKeySemantics
0x18002c4c5  test    eax, eax
0x18002c4c7  js      loc_18002C6A4
0x18002c4cd  test    byte ptr [rsp+298h+var_208], 2
0x18002c4d5  jz      loc_18002C686
0x18002c4db  mov     [rsp+298h+var_240], r12
0x18002c4e0  mov     eax, 2
0x18002c4e5  lea     rcx, [rsp+298h+var_228]
0x18002c4ea  and     r13d, 1000300h
0x18002c4f1  bts     r13d, 19h
0x18002c4f6  mov     [rsp+298h+var_260], rbx
0x18002c4fb  mov     [rsp+298h+var_268], rcx
0x18002c500  mov     [rsp+298h+var_270], ebx
0x18002c504  mov     [rsp+298h+var_278], eax
0x18002c508  mov     r9d, r13d
0x18002c50b  lea     r8, [rsp+298h+Source]
0x18002c513  mov     rdx, r12
0x18002c516  lea     rcx, [rsp+298h+var_208]
0x18002c51e  call    BaseRegOpenClassKeyFromLocation
0x18002c523  test    byte ptr [rsp+298h+var_208], 20h
0x18002c52b  jnz     loc_18002C70D
0x18002c531  mov     rcx, [rsp+298h+var_240]
0x18002c536  test    rcx, rcx
0x18002c539  jz      loc_18002C288
0x18002c53f  mov     rax, [rsp+298h+var_228]
0x18002c544  test    rax, rax
0x18002c547  jz      loc_18002C288
0x18002c54d  mov     r12, rax
0x18002c550  cmp     rcx, [rsp+298h+Handle]
0x18002c555  cmovnz  r12, rcx
0x18002c559  mov     [rsp+298h+var_220], r12
0x18002c55e  cmp     rdi, 0FFFFFFFF80000000h
0x18002c565  cmovz   rax, rcx
0x18002c569  mov     [rsp+298h+Handle], rax
0x18002c56e  jmp     loc_18002C28B
0x18002c573  mov     eax, 6
0x18002c578  jmp     loc_18002C422
0x18002c57d  call    IsBaseRegCloseKeyPresent
0x18002c582  test    al, al
0x18002c584  jz      loc_18002C3BC
0x18002c58a  mov     rcx, [rsp+298h+Handle]
0x18002c58f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002c593  lea     r8, [rsp+298h+BufferLength]
0x18002c598  mov     edx, r15d
0x18002c59b  call    cs:__imp_BaseRegSetKeySecurity
0x18002c5a2  nop     dword ptr [rax+rax+00h]
0x18002c5a7  mov     esi, eax
0x18002c5a9  mov     [rsp+298h+var_230], eax
0x18002c5ad  jmp     loc_18002C3BC
0x18002c5b2  mov     esi, eax
0x18002c5b4  mov     [rsp+298h+var_230], eax
0x18002c5b8  xor     ebx, ebx
0x18002c5ba  mov     r12, [rsp+298h+var_220]
0x18002c5bf  jmp     loc_18002C3BC
0x18002c5c4  mov     esi, 57h ; 'W'
0x18002c5c9  jmp     loc_18002C321
0x18002c5ce  mov     esi, 0C000000Dh
0x18002c5d3  jmp     loc_18002C3A4
0x18002c5d8  mov     esi, 0C0000008h
0x18002c5dd  jmp     loc_18002C3AC
0x18002c5e2  cmp     [rsp+298h+BufferLength+8], edi
0x18002c5e6  jnb     loc_18002C2F6
0x18002c5ec  mov     esi, 0Eh
0x18002c5f1  jmp     loc_18002C326
0x18002c5f6  lea     rcx, PredefinedHandleTableSRWLock
0x18002c5fd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002c604  nop     dword ptr [rax+rax+00h]
0x18002c609  add     dword ptr [rdi+8], 0FFFFFFFFh
0x18002c60d  jnz     short loc_18002C62C
0x18002c60f  mov     rax, [rdi+10h]
0x18002c613  mov     rcx, [rax+8]
0x18002c617  cmp     rdi, rcx
0x18002c61a  jnz     loc_18002C6B9
0x18002c620  mov     rax, [rax]
0x18002c623  cmp     [rdi], rax
0x18002c626  jnz     loc_18002C6B9
0x18002c62c  lea     rcx, PredefinedHandleTableSRWLock
0x18002c633  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002c63a  nop     dword ptr [rax+rax+00h]
0x18002c63f  test    rbx, rbx
0x18002c642  jz      loc_18002C420
0x18002c648  mov     rcx, [rbx]; hKey
0x18002c64b  call    RegCloseKey
0x18002c650  mov     rcx, rbx; penv
0x18002c653  call    FreeEnvironmentStringsW
0x18002c658  jmp     loc_18002C420
0x18002c65d  call    IsTermsrvDeleteKeyPresent
0x18002c662  test    al, al
0x18002c664  jz      loc_18002C3AC
0x18002c66a  mov     r8, qword ptr [rsp+298h+BufferLength]
0x18002c66f  mov     edx, r15d
0x18002c672  mov     rcx, rdi
0x18002c675  call    cs:__imp_TermsrvSetKeySecurity
0x18002c67c  nop     dword ptr [rax+rax+00h]
0x18002c681  jmp     loc_18002C3AC
0x18002c686  mov     [rsp+298h+var_228], r12
0x18002c68b  mov     eax, 1
0x18002c690  lea     rcx, [rsp+298h+var_240]
0x18002c695  jmp     loc_18002C4EA
0x18002c69a  mov     esi, 0Eh
0x18002c69f  jmp     loc_18002C326
0x18002c6a4  mov     ecx, eax; Status
0x18002c6a6  call    cs:__imp_RtlNtStatusToDosError
0x18002c6ad  nop     dword ptr [rax+rax+00h]
0x18002c6b2  mov     esi, eax
0x18002c6b4  jmp     loc_18002C3E5
0x18002c6b9  mov     rbx, rdi
  ... truncated ...
```
