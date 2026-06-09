# CreateMmpcDiscoveryMessage(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18002d8dc`
- end: `0x18002dc1c`
- name: `?CreateMmpcDiscoveryMessage@@YAJPEBG00000PEAPEAG@Z`
- size: `832`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001f594`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000b0d4`
- `0x18000b0f4`
- `0x1800194e0`
- `0x180019814`
- `0x18001e98c`
- `0x18002d8dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002da72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002da72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002da5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dace`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002da5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dace`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002daa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002daa1`

## string_xrefs

- `0x18002dab8`: `onecoreuap\admin\enterprisemgmt\enrollactivities\lib\mmpjsonparser.cpp`
- `0x18002dbb8`: `onecoreuap\admin\enterprisemgmt\enrollactivities\lib\mmpjsonparser.cpp`
- `0x18002dbe5`: `onecoreuap\admin\enterprisemgmt\enrollactivities\lib\mmpjsonparser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateMmpcDiscoveryMessage(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7)
{
  __int64 v10; // rbx
  __int64 v11; // r10
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdi
  unsigned int v18; // r8d
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  SIZE_T v23; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v25; // rbx
  __int64 v26; // rcx
  const char *v27; // r9
  unsigned int LastError; // edi
  HANDLE v29; // rax
  unsigned int v31; // r8d
  int v32; // eax
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v35; // [rsp+64h] [rbp-9Ch]
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v37; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v38; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v39; // [rsp+80h] [rbp-80h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v37 = a1;
  v38 = a6;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  v15 = -1;
  do
    ++v15;
  while ( a5[v15] );
  v16 = -1;
  do
    ++v16;
  while ( a6[v16] );
  v17 = v11 + v12 + v13 + v14 + v15 + v16;
  v18 = *(_DWORD *)Feature_MMPC_Single_Discovery_Template__descriptor;
  if ( (*(_DWORD *)Feature_MMPC_Single_Discovery_Template__descriptor & 4) == 0 )
  {
    v36 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template>::GetCachedFeatureEnabledState(
                       v15,
                       &v36);
    v18 = v36;
  }
  v34 = 0;
  v35 = 3;
  wil::details::ReportUsageToService(&qword_180070DE0, 44240013, (v18 >> 10) & 1, (v18 >> 11) & 1, &v34, 1);
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  v20 = -1;
  do
    ++v20;
  while ( a3[v20] );
  v21 = -1;
  do
    ++v21;
  while ( a4[v21] );
  do
    ++v10;
  while ( a5[v10] );
  v36 = 0;
  v22 = v19 + v20 + 44 + v17 + v10 + v21;
  v23 = 2 * v22;
  if ( is_mul_ok(v22, 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v25 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v23);
    v39 = v25;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) )
    {
      v31 = *(_DWORD *)Feature_MMPC_Single_Discovery_Template__descriptor;
      if ( (*(_DWORD *)Feature_MMPC_Single_Discovery_Template__descriptor & 4) == 0 )
      {
        v36 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template>::GetCachedFeatureEnabledState(
                           v26,
                           &v36);
        v31 = v36;
      }
      v34 = 0;
      v35 = 3;
      wil::details::ReportUsageToService(&qword_180070DE0, 44240013, (v31 >> 10) & 1, (v31 >> 11) & 1, &v34, 1);
      v32 = StringCbPrintfW(v25, v23, v38, v37);
      LastError = v32;
      if ( v32 >= 0 )
      {
        *a7 = v25;
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\mmpjsonparser.cpp",
        (const char *)(unsigned int)v32,
        (int)a2);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x43,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\mmpjsonparser.cpp",
                    v27);
    }
    if ( v25 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v25);
    }
    return LastError;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\mmpjsonparser.cpp",
      (const char *)0x80070216LL,
      v33);
    return 2147942934LL;
  }
}

```

## disassembly

```asm
0x18002d8dc  push    rbp
0x18002d8de  push    rbx
0x18002d8df  push    rsi
0x18002d8e0  push    rdi
0x18002d8e1  push    r12
0x18002d8e3  push    r13
0x18002d8e5  push    r14
0x18002d8e7  push    r15
0x18002d8e9  lea     rbp, [rsp-0C8h]
0x18002d8f1  sub     rsp, 1C8h
0x18002d8f8  mov     rax, cs:__security_cookie
0x18002d8ff  xor     rax, rsp
0x18002d902  mov     [rbp+100h+var_50], rax
0x18002d909  mov     r15, r9
0x18002d90c  mov     r14, r8
0x18002d90f  mov     rsi, rdx
0x18002d912  mov     [rsp+200h+var_190], rcx
0x18002d917  mov     r12, [rbp+100h+arg_20]
0x18002d91e  mov     r11, [rbp+100h+arg_28]
0x18002d925  mov     [rsp+200h+var_188], r11
0x18002d92a  mov     r13, [rbp+100h+arg_30]
0x18002d931  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d935  mov     r10, rbx
0x18002d938  xor     edi, edi
0x18002d93a  inc     r10
0x18002d93d  cmp     [rcx+r10*2], di
0x18002d942  jnz     short loc_18002D93A
0x18002d944  mov     r9, rbx
0x18002d947  inc     r9
0x18002d94a  cmp     [rdx+r9*2], di
0x18002d94f  jnz     short loc_18002D947
0x18002d951  mov     r8, rbx
0x18002d954  inc     r8
0x18002d957  cmp     [r14+r8*2], di
0x18002d95c  jnz     short loc_18002D954
0x18002d95e  mov     rdx, rbx
0x18002d961  inc     rdx
0x18002d964  cmp     [r15+rdx*2], di
0x18002d969  jnz     short loc_18002D961
0x18002d96b  mov     rcx, rbx
0x18002d96e  inc     rcx
0x18002d971  cmp     [r12+rcx*2], di
0x18002d976  jnz     short loc_18002D96E
0x18002d978  mov     rax, rbx
0x18002d97b  inc     rax
0x18002d97e  cmp     [r11+rax*2], di
0x18002d983  jnz     short loc_18002D97B
0x18002d985  lea     rdi, [rcx+rax]
0x18002d989  add     rdi, rdx
0x18002d98c  add     rdi, r8
0x18002d98f  add     rdi, r9
0x18002d992  add     rdi, r10
0x18002d995  mov     rax, cs:Feature_MMPC_Single_Discovery_Template__descriptor
0x18002d99c  mov     r8d, [rax]
0x18002d99f  test    r8b, 4
0x18002d9a3  jnz     short loc_18002D9BA
0x18002d9a5  lea     rdx, [rsp+200h+var_198]
0x18002d9aa  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template>::GetCachedFeatureEnabledState(void)
0x18002d9af  mov     rcx, [rax]
0x18002d9b2  mov     [rsp+200h+var_198], rcx
0x18002d9b7  mov     r8d, ecx
0x18002d9ba  xor     ecx, ecx
0x18002d9bc  mov     [rsp+200h+var_1A0], ecx
0x18002d9c0  mov     [rsp+200h+var_19C], 3
0x18002d9c7  mov     r9d, r8d
0x18002d9ca  shr     r9d, 0Bh
0x18002d9ce  and     r9d, 1
0x18002d9d2  shr     r8d, 0Ah
0x18002d9d6  and     r8d, 1
0x18002d9da  mov     dword ptr [rsp+200h+var_1D8], 1
0x18002d9e2  lea     rax, [rsp+200h+var_1A0]
0x18002d9e7  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x18002d9ec  mov     edx, 2A30C8Dh
0x18002d9f1  lea     rcx, qword_180070DE0
0x18002d9f8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002d9fd  mov     r8, rbx
0x18002da00  xor     r9d, r9d
0x18002da03  inc     r8
0x18002da06  cmp     [rsi+r8*2], r9w
0x18002da0b  jnz     short loc_18002DA03
0x18002da0d  mov     rdx, rbx
0x18002da10  inc     rdx
0x18002da13  cmp     [r14+rdx*2], r9w
0x18002da18  jnz     short loc_18002DA10
0x18002da1a  mov     rcx, rbx
0x18002da1d  inc     rcx
0x18002da20  cmp     [r15+rcx*2], r9w
0x18002da25  jnz     short loc_18002DA1D
0x18002da27  inc     rbx
0x18002da2a  cmp     [r12+rbx*2], r9w
0x18002da2f  jnz     short loc_18002DA27
0x18002da31  mov     [rsp+200h+var_198], r9
0x18002da36  lea     rax, [rdi+rbx]
0x18002da3a  add     rcx, rax
0x18002da3d  add     rdx, 2Ch ; ','
0x18002da41  add     rcx, rdx
0x18002da44  add     rcx, r8
0x18002da47  mov     eax, 2
0x18002da4c  mul     rcx
0x18002da4f  mov     rdi, rax
0x18002da52  test    rdx, rdx
0x18002da55  jnz     loc_18002DBD6
0x18002da5b  call    cs:__imp_GetProcessHeap
0x18002da62  nop     dword ptr [rax+rax+00h]
0x18002da67  mov     rcx, rax; hHeap
0x18002da6a  mov     r8, rdi; dwBytes
0x18002da6d  mov     edx, 8; dwFlags
0x18002da72  call    cs:__imp_HeapAlloc
0x18002da79  nop     dword ptr [rax+rax+00h]
0x18002da7e  mov     rbx, rax
0x18002da81  mov     [rbp+100h+var_180], rax
0x18002da85  xor     edx, edx; Val
0x18002da87  mov     r8d, 118h; Size
0x18002da8d  lea     rcx, [rbp+100h+VersionInformation.dwMajorVersion]; void *
0x18002da91  call    memset_0
0x18002da96  mov     [rbp+100h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002da9d  lea     rcx, [rbp+100h+VersionInformation]; lpVersionInformation
0x18002daa1  call    cs:__imp_GetVersionExW
0x18002daa8  nop     dword ptr [rax+rax+00h]
0x18002daad  test    eax, eax
0x18002daaf  jnz     short loc_18002DAF5
0x18002dab1  mov     rcx, [rbp+108h]; this
0x18002dab8  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002dabf  lea     edx, [rax+43h]; void *
0x18002dac2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dac7  mov     edi, eax
0x18002dac9  test    rbx, rbx
0x18002dacc  jz      short loc_18002DAEE
0x18002dace  call    cs:__imp_GetProcessHeap
0x18002dad5  nop     dword ptr [rax+rax+00h]
0x18002dada  mov     rcx, rax; hHeap
0x18002dadd  mov     r8, rbx; lpMem
0x18002dae0  xor     edx, edx; dwFlags
0x18002dae2  call    cs:__imp_HeapFree
0x18002dae9  nop     dword ptr [rax+rax+00h]
0x18002daee  mov     eax, edi
0x18002daf0  jmp     loc_18002DBF8
0x18002daf5  mov     rax, cs:Feature_MMPC_Single_Discovery_Template__descriptor
0x18002dafc  mov     r8d, [rax]
0x18002daff  test    r8b, 4
0x18002db03  jnz     short loc_18002DB1A
0x18002db05  lea     rdx, [rsp+200h+var_198]
0x18002db0a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Single_Discovery_Template>::GetCachedFeatureEnabledState(void)
0x18002db0f  mov     rcx, [rax]
0x18002db12  mov     [rsp+200h+var_198], rcx
0x18002db17  mov     r8d, ecx
0x18002db1a  mov     [rsp+200h+var_1A0], 0
0x18002db22  mov     [rsp+200h+var_19C], 3
0x18002db29  mov     r9d, r8d
0x18002db2c  shr     r9d, 0Bh
0x18002db30  and     r9d, 1
0x18002db34  shr     r8d, 0Ah
0x18002db38  and     r8d, 1
0x18002db3c  mov     dword ptr [rsp+200h+var_1D8], 1
0x18002db44  lea     rax, [rsp+200h+var_1A0]
0x18002db49  mov     qword ptr [rsp+200h+var_1E0], rax
0x18002db4e  mov     edx, 2A30C8Dh
0x18002db53  lea     rcx, qword_180070DE0
0x18002db5a  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002db5f  mov     ecx, [rbp+100h+VersionInformation.dwBuildNumber]
0x18002db62  shr     ecx, 10h
0x18002db65  movzx   eax, word ptr [rbp+100h+VersionInformation.dwBuildNumber]
0x18002db69  mov     [rsp+200h+var_1A8], ecx
0x18002db6d  mov     [rsp+200h+var_1B0], eax
0x18002db71  mov     eax, [rbp+100h+VersionInformation.dwMinorVersion]
0x18002db74  mov     [rsp+200h+var_1B8], eax
0x18002db78  mov     eax, [rbp+100h+VersionInformation.dwMajorVersion]
0x18002db7b  mov     [rsp+200h+var_1C0], eax
0x18002db7f  mov     [rsp+200h+var_1C8], r12
0x18002db84  mov     [rsp+200h+var_1D0], r15
0x18002db89  mov     [rsp+200h+var_1D8], r14
0x18002db8e  mov     qword ptr [rsp+200h+var_1E0], rsi; int
0x18002db93  mov     r9, [rsp+200h+var_190]
0x18002db98  mov     r8, [rsp+200h+var_188]; unsigned __int16 *
0x18002db9d  mov     rdx, rdi; unsigned __int64
0x18002dba0  mov     rcx, rbx; unsigned __int16 *
0x18002dba3  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dba8  mov     edi, eax
0x18002dbaa  test    eax, eax
0x18002dbac  jns     short loc_18002DBCE
0x18002dbae  mov     rcx, [rbp+108h]; this
0x18002dbb5  mov     r9d, eax; char *
0x18002dbb8  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002dbbf  mov     edx, 52h ; 'R'; void *
0x18002dbc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbc9  jmp     loc_18002DAC9
0x18002dbce  mov     [r13+0], rbx
0x18002dbd2  xor     eax, eax
0x18002dbd4  jmp     short loc_18002DBF8
0x18002dbd6  mov     rcx, [rbp+108h]; this
0x18002dbdd  mov     ebx, 80070216h
0x18002dbe2  mov     r9d, ebx; char *
0x18002dbe5  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002dbec  mov     edx, 3Dh ; '='; void *
0x18002dbf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbf6  mov     eax, ebx
0x18002dbf8  mov     rcx, [rbp+100h+var_50]
0x18002dbff  xor     rcx, rsp; StackCookie
0x18002dc02  call    __security_check_cookie
0x18002dc07  add     rsp, 1C8h
0x18002dc0e  pop     r15
0x18002dc10  pop     r14
0x18002dc12  pop     r13
0x18002dc14  pop     r12
0x18002dc16  pop     rdi
0x18002dc17  pop     rsi
0x18002dc18  pop     rbx
0x18002dc19  pop     rbp
0x18002dc1a  retn
```
