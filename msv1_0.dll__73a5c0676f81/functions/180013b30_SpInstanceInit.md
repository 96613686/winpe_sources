# SpInstanceInit

- ea: `0x180013b30`
- end: `0x180013d23`
- name: `SpInstanceInit`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013b30`
- `0x18002ee7c`
- `0x18002f014`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180013c64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180013c64`
- `ntdll!RtlInitializeResource` at `0x180013c9c`
- `ntdll!RtlInitializeResource` at `0x180013c9c`
- `ntdll!RtlGetNtProductType` at `0x180013bcc`
- `ntdll!RtlGetNtProductType` at `0x180013bcc`
- `ntdll!RtlDeleteResource` at `0x180013cde`
- `ntdll!RtlDeleteResource` at `0x180013cde`

## pseudocode

```c
__int64 __fastcall SpInstanceInit(__int64 a1, __int64 a2)
{
  int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 i; // rbx
  DWORD dwNumberOfProcessors; // eax
  _SYSTEM_INFO SystemInfo; // [rsp+28h] [rbp-50h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+88h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
  ProductType = 0;
  v3 = 0;
  if ( NtLmState != 1 )
    NtLmState = 2;
  UserFunctions = a2;
  v4 = 0;
  v5 = 0;
  do
  {
    *(&NtLmUserContextList + v5 + 1) = (struct _LIST_ENTRY near *)&(&NtLmUserContextList)[v5];
    (&NtLmUserContextList)[v5] = (struct _LIST_ENTRY near *)&(&NtLmUserContextList)[v5];
    ++v4;
    v5 += 2;
  }
  while ( v4 != 256 );
  NtLmUserContextLockCount = 1;
  NtLmProcessAppContainerCached = 0;
  NtLmProcessAppContainerSid = 0;
  RtlGetNtProductType(&ProductType);
  if ( (unsigned int)(ProductType - 2) <= 1 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( (SystemInfo.dwNumberOfProcessors & 1) != 0 )
      dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors + 1;
    if ( dwNumberOfProcessors > 4 )
      dwNumberOfProcessors = 4;
    if ( dwNumberOfProcessors )
      NtLmUserContextLockCount = dwNumberOfProcessors;
  }
  for ( i = 0; (unsigned int)i < NtLmUserContextLockCount; i = (unsigned int)(i + 1) )
  {
    RtlInitializeResource((PRTL_RESOURCE)&(&NtLmUserContextLock)[12 * i]);
    ++v3;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180013b30  mov     [rsp+arg_0], rbx
0x180013b35  mov     [rsp+arg_10], rsi
0x180013b3a  push    rdi
0x180013b3b  push    r14
0x180013b3d  push    r15
0x180013b3f  sub     rsp, 60h
0x180013b43  mov     rbx, rdx
0x180013b46  lea     r15, WPP_GLOBAL_Control
0x180013b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b54  cmp     rcx, r15
0x180013b57  jnz     loc_180013C26
0x180013b5d  xor     esi, esi
0x180013b5f  mov     [rsp+78h+ProductType], esi
0x180013b66  xor     edi, edi
0x180013b68  mov     [rsp+78h+var_58], edi
0x180013b6c  cmp     cs:NtLmState, 1
0x180013b73  jz      short loc_180013B7F
0x180013b75  mov     cs:NtLmState, 2
0x180013b7f  mov     cs:UserFunctions, rbx
0x180013b86  xor     edx, edx
0x180013b88  xor     ecx, ecx
0x180013b8a  lea     r8, ?NtLmUserContextList@@3PAU_LIST_ENTRY@@A; _LIST_ENTRY near * NtLmUserContextList
0x180013b91  lea     rax, [rcx+r8]
0x180013b95  mov     [rcx+r8+8], rax
0x180013b9a  mov     [rax], rax
0x180013b9d  inc     rdx
0x180013ba0  lea     rcx, [rcx+10h]
0x180013ba4  cmp     rdx, 100h
0x180013bab  jnz     short loc_180013B91
0x180013bad  mov     cs:?NtLmUserContextLockCount@@3KA, 1; ulong NtLmUserContextLockCount
0x180013bb7  mov     cs:?NtLmProcessAppContainerCached@@3HA, esi; int NtLmProcessAppContainerCached
0x180013bbd  mov     cs:?NtLmProcessAppContainerSid@@3PEAXEA, rsi; void * NtLmProcessAppContainerSid
0x180013bc4  lea     rcx, [rsp+78h+ProductType]; ProductType
0x180013bcc  call    cs:__imp_RtlGetNtProductType
0x180013bd2  mov     eax, [rsp+78h+ProductType]
0x180013bd9  add     eax, 0FFFFFFFEh
0x180013bdc  cmp     eax, 1
0x180013bdf  jbe     short loc_180013C4D
0x180013be1  xor     ebx, ebx
0x180013be3  lea     r14, ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * NtLmUserContextLock
0x180013bea  cmp     ebx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x180013bf0  jb      loc_180013C91
0x180013bf6  test    esi, esi
0x180013bf8  js      loc_180013CCD
0x180013bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c05  cmp     rcx, r15
0x180013c08  jnz     loc_180013CF9
0x180013c0e  mov     eax, esi
0x180013c10  lea     r11, [rsp+78h+var_18]
0x180013c15  mov     rbx, [r11+20h]
0x180013c19  mov     rsi, [r11+30h]
0x180013c1d  mov     rsp, r11
0x180013c20  pop     r15
0x180013c22  pop     r14
0x180013c24  pop     rdi
0x180013c25  retn
0x180013c26  test    dword ptr [rcx+1Ch], 100h
0x180013c2d  jz      loc_180013B5D
0x180013c33  mov     edx, 12h
0x180013c38  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180013c3f  mov     rcx, [rcx+10h]
0x180013c43  call    WPP_SF_
0x180013c48  jmp     loc_180013B5D
0x180013c4d  xorps   xmm0, xmm0
0x180013c50  movups  xmmword ptr [rsp+78h+SystemInfo], xmm0
0x180013c55  movups  xmmword ptr [rsp+78h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180013c5a  movups  xmmword ptr [rsp+78h+SystemInfo.dwNumberOfProcessors], xmm0
0x180013c5f  lea     rcx, [rsp+78h+SystemInfo]; lpSystemInfo
0x180013c64  call    cs:__imp_GetSystemInfo
0x180013c6a  mov     eax, [rsp+78h+SystemInfo.dwNumberOfProcessors]
0x180013c6e  test    al, 1
0x180013c70  jz      short loc_180013C74
0x180013c72  inc     eax
0x180013c74  mov     ecx, 4
0x180013c79  cmp     eax, ecx
0x180013c7b  cmova   eax, ecx
0x180013c7e  test    eax, eax
0x180013c80  jz      loc_180013BE1
0x180013c86  mov     cs:?NtLmUserContextLockCount@@3KA, eax; ulong NtLmUserContextLockCount
0x180013c8c  jmp     loc_180013BE1
0x180013c91  lea     rcx, [rbx+rbx*2]
0x180013c95  shl     rcx, 5
0x180013c99  add     rcx, r14; Resource
0x180013c9c  call    cs:__imp_RtlInitializeResource
0x180013ca2  inc     edi
0x180013ca4  mov     [rsp+78h+var_58], edi
0x180013ca8  jmp     short loc_180013CC6
0x180013caa  mov     esi, 0C000009Ah
0x180013caf  lea     r15, WPP_GLOBAL_Control
0x180013cb6  lea     r14, ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * NtLmUserContextLock
0x180013cbd  mov     edi, [rsp+78h+var_58]
0x180013cc1  jmp     loc_180013BF6
0x180013cc6  inc     ebx
0x180013cc8  jmp     loc_180013BEA
0x180013ccd  xor     ebx, ebx
0x180013ccf  test    edi, edi
0x180013cd1  jz      short loc_180013CEA
0x180013cd3  lea     rcx, [rbx+rbx*2]
0x180013cd7  shl     rcx, 5
0x180013cdb  add     rcx, r14; Resource
0x180013cde  call    cs:__imp_RtlDeleteResource
0x180013ce4  inc     ebx
0x180013ce6  cmp     ebx, edi
0x180013ce8  jb      short loc_180013CD3
0x180013cea  mov     cs:?NtLmUserContextLockCount@@3KA, 0; ulong NtLmUserContextLockCount
0x180013cf4  jmp     loc_180013BFE
0x180013cf9  test    dword ptr [rcx+1Ch], 100h
0x180013d00  jz      loc_180013C0E
0x180013d06  mov     edx, 13h
0x180013d0b  mov     r9d, esi
0x180013d0e  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180013d15  mov     rcx, [rcx+10h]
0x180013d19  call    WPP_SF_d
0x180013d1e  jmp     loc_180013C0E
```
