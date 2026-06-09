# GameControllerRawInputProvider::UpdateFocusPids(void)

- ea: `0x18000e8bc`
- end: `0x18000eab2`
- name: `?UpdateFocusPids@GameControllerRawInputProvider@@AEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(GameControllerRawInputProvider *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000e3f4`
- `0x18000e730`
- `0x180114554`
- `0x180114d40`
- `0x180114d60`
- `0x18011521c`

## callees

- `0x18000e8bc`
- `0x18008daac`
- `0x1800af9b8`
- `0x1801144a8`
- `0x1801152d0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e90b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e90b`
- `ntdll!RtlPublishWnfStateData` at `0x18000e9da`
- `ntdll!RtlPublishWnfStateData` at `0x18000ea47`
- `ntdll!RtlPublishWnfStateData` at `0x18000e9da`
- `ntdll!RtlPublishWnfStateData` at `0x18000ea47`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000e98b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000e98b`

## pseudocode

```c
int __fastcall GameControllerRawInputProvider::UpdateFocusPids(GameControllerRawInputProvider *this)
{
  char IsEnabled; // al
  unsigned int *v3; // rsi
  DWORD CurrentProcessId; // edx
  __int64 v5; // rcx
  char *v6; // rcx
  const char *v7; // r9
  unsigned int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  unsigned int v14; // [rsp+80h] [rbp+28h] BYREF
  DWORD InBuffer; // [rsp+88h] [rbp+30h] BYREF
  unsigned int v16; // [rsp+90h] [rbp+38h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+40h] BYREF

  InBuffer = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix>::GetImpl'::`2'::impl);
  v3 = (unsigned int *)((char *)this + 160);
  CurrentProcessId = *((_DWORD *)this + 40);
  if ( IsEnabled )
  {
    if ( !CurrentProcessId )
    {
      CurrentProcessId = *((_DWORD *)this + 42);
      if ( !CurrentProcessId )
      {
        CurrentProcessId = *((_DWORD *)this + 41);
        if ( !CurrentProcessId )
        {
          if ( *((_BYTE *)this + 176) )
          {
            CurrentProcessId = GetCurrentProcessId();
            goto LABEL_11;
          }
          goto LABEL_10;
        }
      }
    }
  }
  else if ( !CurrentProcessId )
  {
    CurrentProcessId = *((_DWORD *)this + 42);
    if ( !CurrentProcessId )
    {
      CurrentProcessId = *((_DWORD *)this + 41);
      if ( !CurrentProcessId )
LABEL_10:
        CurrentProcessId = *((_DWORD *)this + 39);
    }
  }
LABEL_11:
  InBuffer = CurrentProcessId;
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  v6 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
    && !DeviceIoControl(v6, 0x40001C28u, &InBuffer, 4u, 0, 0, 0, 0) )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x395,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrol"
                           "lerrawinputprovider.cpp",
             v7);
  }
  v9 = *v3;
  if ( !*v3 )
    v9 = *((_DWORD *)this + 39);
  v16 = v9;
  v10 = RtlPublishWnfStateData(WNF_SHEL_FOCUS_CHANGE, 0, &v16, 4);
  if ( v10 < 0 )
  {
    v11 = 945;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v11,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontrol"
                           "lerrawinputprovider.cpp",
             (const char *)(unsigned int)v10,
             0);
  }
  v12 = *((_DWORD *)this + 42);
  if ( !v12 )
    v12 = *((_DWORD *)this + 41);
  if ( *v3 )
    v12 = 0;
  v14 = v12;
  v17 = *((_DWORD *)this + 43);
  if ( v12 != v17 )
  {
    v10 = RtlPublishWnfStateData(WNF_SHEL_GAMECONTROLLER_FOCUS_INFO, 0, &v14, 4);
    if ( v10 < 0 )
    {
      v11 = 973;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v11,
               (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\gamecontroller\\lib\\gamecontr"
                             "ollerrawinputprovider.cpp",
               (const char *)(unsigned int)v10,
               0);
    }
    *((_DWORD *)this + 43) = v14;
  }
  ISMTracing::GameControllerRawInputProvider_UpdateFocusPids<unsigned long &,unsigned long &,unsigned long &,unsigned long const &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &>(
    (unsigned int *)this + 39,
    (unsigned int *)this + 40,
    (unsigned int *)this + 41,
    &v17,
    &InBuffer,
    &v16,
    &v14,
    (unsigned int *)this + 42,
    (bool *)this + 176);
  return 0;
}

```

## disassembly

```asm
0x18000e8bc  push    rbp
0x18000e8be  push    rbx
0x18000e8bf  push    rsi
0x18000e8c0  push    rdi
0x18000e8c1  mov     rbp, rsp
0x18000e8c4  sub     rsp, 58h
0x18000e8c8  mov     rbx, rcx
0x18000e8cb  mov     [rbp+InBuffer], 0
0x18000e8d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix> `wil::Feature<__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix>::GetImpl(void)'::`2'::impl
0x18000e8d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Input_DesktopNavigationGamepad_ListenerFix>::__private_IsEnabled(void)
0x18000e8de  lea     rsi, [rbx+0A0h]
0x18000e8e5  mov     edx, [rsi]
0x18000e8e7  test    al, al
0x18000e8e9  jz      short loc_18000E915
0x18000e8eb  test    edx, edx
0x18000e8ed  jnz     short loc_18000E933
0x18000e8ef  mov     edx, [rbx+0A8h]
0x18000e8f5  test    edx, edx
0x18000e8f7  jnz     short loc_18000E933
0x18000e8f9  mov     edx, [rbx+0A4h]
0x18000e8ff  test    edx, edx
0x18000e901  jnz     short loc_18000E933
0x18000e903  cmp     [rbx+0B0h], dl
0x18000e909  jz      short loc_18000E92D
0x18000e90b  call    cs:__imp_GetCurrentProcessId
0x18000e911  mov     edx, eax
0x18000e913  jmp     short loc_18000E933
0x18000e915  test    edx, edx
0x18000e917  jnz     short loc_18000E933
0x18000e919  mov     edx, [rbx+0A8h]
0x18000e91f  test    edx, edx
0x18000e921  jnz     short loc_18000E933
0x18000e923  mov     edx, [rbx+0A4h]
0x18000e929  test    edx, edx
0x18000e92b  jnz     short loc_18000E933
0x18000e92d  mov     edx, [rbx+9Ch]
0x18000e933  mov     [rbp+InBuffer], edx
0x18000e936  mov     rcx, [rbx+40h]
0x18000e93a  test    rcx, rcx
0x18000e93d  jz      short loc_18000E94B
0x18000e93f  mov     rax, [rcx]
0x18000e942  mov     rax, [rax+40h]
0x18000e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94b  mov     rcx, [rbx+50h]; hDevice
0x18000e94f  lea     rax, [rcx-1]
0x18000e953  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e957  ja      short loc_18000E9AF
0x18000e959  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18000e962  mov     [rsp+58h+lpBytesReturned], 0; lpBytesReturned
0x18000e96b  mov     [rsp+58h+nOutBufferSize], 0; nOutBufferSize
0x18000e973  mov     [rsp+58h+lpOutBuffer], 0; lpOutBuffer
0x18000e97c  mov     r9d, 4; nInBufferSize
0x18000e982  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000e986  mov     edx, 40001C28h; dwIoControlCode
0x18000e98b  call    cs:__imp_DeviceIoControl
0x18000e991  test    eax, eax
0x18000e993  jnz     short loc_18000E9AF
0x18000e995  mov     rcx, [rbp+20h]; this
0x18000e999  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e9a0  mov     edx, 395h; void *
0x18000e9a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e9aa  jmp     loc_18000EAA9
0x18000e9af  mov     eax, [rsi]
0x18000e9b1  test    eax, eax
0x18000e9b3  jnz     short loc_18000E9BB
0x18000e9b5  mov     eax, [rbx+9Ch]
0x18000e9bb  mov     [rbp+arg_10], eax
0x18000e9be  mov     [rsp+58h+lpOutBuffer], 0; int
0x18000e9c7  mov     r9d, 4
0x18000e9cd  lea     r8, [rbp+arg_10]
0x18000e9d1  xor     edx, edx
0x18000e9d3  mov     rcx, cs:WNF_SHEL_FOCUS_CHANGE
0x18000e9da  call    cs:__imp_RtlPublishWnfStateData
0x18000e9e0  test    eax, eax
0x18000e9e2  jns     short loc_18000EA01
0x18000e9e4  mov     edx, 3B1h; void *
0x18000e9e9  lea     r8, aOnecoreuapWind_226; "onecoreuap\\windows\\moderncore\\inputv"...
0x18000e9f0  mov     r9d, eax; char *
0x18000e9f3  mov     rcx, [rbp+20h]; this
0x18000e9f7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000e9fc  jmp     loc_18000EAA9
0x18000ea01  lea     rdi, [rbx+0A8h]
0x18000ea08  mov     ecx, [rdi]
0x18000ea0a  test    ecx, ecx
0x18000ea0c  jnz     short loc_18000EA14
0x18000ea0e  mov     ecx, [rbx+0A4h]
0x18000ea14  xor     eax, eax
0x18000ea16  cmp     [rsi], eax
0x18000ea18  cmovnz  ecx, eax
0x18000ea1b  mov     [rbp+arg_0], ecx
0x18000ea1e  mov     eax, [rbx+0ACh]
0x18000ea24  mov     [rbp+arg_18], eax
0x18000ea27  cmp     ecx, eax
0x18000ea29  jz      short loc_18000EA61
0x18000ea2b  mov     [rsp+58h+lpOutBuffer], 0
0x18000ea34  mov     r9d, 4
0x18000ea3a  lea     r8, [rbp+arg_0]
0x18000ea3e  xor     edx, edx
0x18000ea40  mov     rcx, cs:WNF_SHEL_GAMECONTROLLER_FOCUS_INFO
0x18000ea47  call    cs:__imp_RtlPublishWnfStateData
0x18000ea4d  test    eax, eax
0x18000ea4f  jns     short loc_18000EA58
0x18000ea51  mov     edx, 3CDh
0x18000ea56  jmp     short loc_18000E9E9
0x18000ea58  mov     eax, [rbp+arg_0]
0x18000ea5b  mov     [rbx+0ACh], eax
0x18000ea61  lea     rax, [rbx+0B0h]
0x18000ea68  lea     r8, [rbx+0A4h]; unsigned int *
0x18000ea6f  lea     rcx, [rbx+9Ch]; unsigned int *
0x18000ea76  mov     [rsp+58h+var_18], rax; bool *
0x18000ea7b  mov     [rsp+58h+lpOverlapped], rdi; unsigned int *
0x18000ea80  lea     rax, [rbp+arg_0]
0x18000ea84  mov     [rsp+58h+lpBytesReturned], rax; unsigned int *
0x18000ea89  lea     rax, [rbp+arg_10]
0x18000ea8d  mov     qword ptr [rsp+58h+nOutBufferSize], rax; unsigned int *
0x18000ea92  lea     rax, [rbp+InBuffer]
0x18000ea96  mov     [rsp+58h+lpOutBuffer], rax; unsigned int *
0x18000ea9b  lea     r9, [rbp+arg_18]; unsigned int *
0x18000ea9f  mov     rdx, rsi; unsigned int *
0x18000eaa2  call    ??$GameControllerRawInputProvider_UpdateFocusPids@AEAKAEAKAEAKAEBKAEAKAEAKAEAKAEAKAEA_N@ISMTracing@@SAXAEAK00AEBK0000AEA_N@Z; ISMTracing::GameControllerRawInputProvider_UpdateFocusPids<ulong &,ulong &,ulong &,ulong const &,ulong &,ulong &,ulong &,ulong &,bool &>(ulong &,ulong &,ulong &,ulong const &,ulong &,ulong &,ulong &,ulong &,bool &)
0x18000eaa7  xor     eax, eax
0x18000eaa9  add     rsp, 58h
0x18000eaad  pop     rdi
0x18000eaae  pop     rsi
0x18000eaaf  pop     rbx
0x18000eab0  pop     rbp
0x18000eab1  retn
```
