# InitializeCNG

- ea: `0x18000b45c`
- end: `0x18000b57e`
- name: `InitializeCNG`
- size: `290`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009aa4`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180009c20`
- `0x18000b45c`
- `0x18000b584`
- `0x18000de78`
- `0x180016744`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18000b469`
- `ntdll!RtlInitializeCriticalSection` at `0x18000b4dc`
- `ntdll!RtlInitializeCriticalSection` at `0x18000b469`
- `ntdll!RtlInitializeCriticalSection` at `0x18000b4dc`

## string_xrefs

- `0x18000b49a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`
- `0x18000b514`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`
- `0x18000b556`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`

## pseudocode

```c
__int64 InitializeCNG()
{
  int v0; // edx
  unsigned int v1; // ebx
  __int64 *v2; // rax
  NTSTATUS v3; // eax
  char v4; // r9
  unsigned int v5; // eax

  v1 = RtlInitializeCriticalSection(&g_ResLock);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v0,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx",
        (unsigned int)"Status",
        v1,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx",
        196);
    goto LABEL_12;
  }
  v2 = off_180025160;
  dword_180025D78 |= 4u;
  off_180025160[1] = (__int64)off_180025160;
  *v2 = (__int64)v2;
  v3 = RtlInitializeCriticalSection(&CriticalSection);
  v1 = v3;
  if ( v3 >= 0 )
    dword_180025FFC = 1;
  if ( v3 )
  {
    v4 = -49;
LABEL_11:
    DebugTraceError(
      v3,
      (int)"Status",
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx",
      v4);
LABEL_12:
    UninitializeCNG();
    return v1;
  }
  dword_180025D78 |= 1u;
  v3 = InitializeLoader();
  v1 = v3;
  if ( v3 )
  {
    v4 = -40;
    goto LABEL_11;
  }
  dword_180025D78 |= 2u;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetImpl'::`2'::impl) )
  {
    v5 = InitializeKeyIsoPerfCounters();
    if ( v5 )
      DebugTraceError(
        v5,
        (int)"Status",
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx",
        229);
    else
      dword_180025D78 |= 8u;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b45c  push    rbx
0x18000b45e  sub     rsp, 40h
0x18000b462  lea     rcx, g_ResLock; CriticalSection
0x18000b469  call    cs:__imp_RtlInitializeCriticalSection
0x18000b46f  mov     ebx, eax
0x18000b471  test    eax, eax
0x18000b473  jz      short loc_18000B4C0
0x18000b475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b47c  lea     rax, WPP_GLOBAL_Control
0x18000b483  cmp     rcx, rax
0x18000b486  jz      loc_18000B529
0x18000b48c  test    byte ptr [rcx+1Ch], 1
0x18000b490  jz      loc_18000B529
0x18000b496  mov     rcx, [rcx+10h]
0x18000b49a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b4a1  mov     [rsp+48h+var_18], 0C4h
0x18000b4a9  lea     r9, aStatus; "Status"
0x18000b4b0  mov     [rsp+48h+var_20], r8
0x18000b4b5  mov     [rsp+48h+var_28], ebx
0x18000b4b9  call    WPP_SF_sDsd
0x18000b4be  jmp     short loc_18000B529
0x18000b4c0  mov     rax, cs:off_180025160
0x18000b4c7  lea     rcx, CriticalSection; CriticalSection
0x18000b4ce  or      cs:dword_180025D78, 4
0x18000b4d5  mov     [rax+8], rax
0x18000b4d9  mov     [rax], rax
0x18000b4dc  call    cs:__imp_RtlInitializeCriticalSection
0x18000b4e2  mov     ebx, eax
0x18000b4e4  test    eax, eax
0x18000b4e6  js      short loc_18000B4F2
0x18000b4e8  mov     cs:dword_180025FFC, 1
0x18000b4f2  jz      short loc_18000B4FC
0x18000b4f4  mov     r9d, 0CFh
0x18000b4fa  jmp     short loc_18000B514
0x18000b4fc  or      cs:dword_180025D78, 1
0x18000b503  call    InitializeLoader
0x18000b508  mov     ebx, eax
0x18000b50a  test    eax, eax
0x18000b50c  jz      short loc_18000B530
0x18000b50e  mov     r9d, 0D8h
0x18000b514  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b51b  mov     ecx, eax
0x18000b51d  lea     rdx, aStatus; "Status"
0x18000b524  call    DebugTraceError
0x18000b529  call    UninitializeCNG
0x18000b52e  jmp     short loc_18000B576
0x18000b530  or      cs:dword_180025D78, 2
0x18000b537  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT> `wil::Feature<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetImpl(void)'::`2'::impl
0x18000b53e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::__private_IsEnabled(void)
0x18000b543  test    al, al
0x18000b545  jz      short loc_18000B574
0x18000b547  call    InitializeKeyIsoPerfCounters
0x18000b54c  test    eax, eax
0x18000b54e  jz      short loc_18000B56D
0x18000b550  mov     r9d, 0E5h
0x18000b556  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b55d  lea     rdx, aStatus; "Status"
0x18000b564  mov     ecx, eax
0x18000b566  call    DebugTraceError
0x18000b56b  jmp     short loc_18000B574
0x18000b56d  or      cs:dword_180025D78, 8
0x18000b574  xor     ebx, ebx
0x18000b576  mov     eax, ebx
0x18000b578  add     rsp, 40h
0x18000b57c  pop     rbx
0x18000b57d  retn
```
