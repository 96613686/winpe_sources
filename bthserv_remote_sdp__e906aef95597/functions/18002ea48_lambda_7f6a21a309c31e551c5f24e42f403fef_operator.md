# _lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()

- ea: `0x18002ea48`
- end: `0x18002ef48`
- name: `_lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()`
- size: `1280`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18002dcf0`

## callees

- `0x180001b94`
- `0x180002a94`
- `0x180003740`
- `0x180009c50`
- `0x180011b9c`
- `0x1800120b8`
- `0x18002ea48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ea7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002eb42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ebaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ea7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002eb42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ebaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eab7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eab7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ebee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002eb0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002eb0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eaa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eaa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebe0`

## string_xrefs

- `0x18002ed33`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002ede0`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002ee8d`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002ef33`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()(__int64 *a1)
{
  __int64 v1; // rdi
  HANDLE EventW; // rax
  char *v4; // rbp
  HANDLE v5; // r14
  DWORD LastError; // ebx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD **v10; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v12; // r14
  char v13; // di
  HANDLE v14; // rax
  char *v15; // rbp
  HANDLE v16; // r15
  DWORD v17; // ebx
  __int64 v18; // rbp
  HANDLE v19; // rax
  char *v20; // r14
  HANDLE v21; // r15
  DWORD v22; // ebx
  __int64 v23; // rbx
  _OWORD *v24; // rax
  const struct std::nothrow_t *v25; // rdx
  void *v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 result; // rax
  signed int v31; // eax
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // ecx
  unsigned int v35; // eax
  signed int v36; // eax
  int v37; // edx
  int v38; // r8d
  unsigned int v39; // ecx
  bool v40; // di
  unsigned int v41; // eax
  signed int v42; // eax
  int v43; // edx
  int v44; // r8d
  unsigned int v45; // ecx
  bool v46; // di
  unsigned int v47; // eax
  signed int v48; // eax
  int v49; // edx
  int v50; // r8d
  unsigned int v51; // ecx
  unsigned int v52; // eax
  int v53; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = *a1;
  *(_OWORD *)(v1 + 88) = 0;
  *(_OWORD *)(v1 + 104) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = *(char **)(v1 + 120);
  v5 = EventW;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  v7 = *a1;
  *(_QWORD *)(v1 + 120) = v5;
  v8 = *(_QWORD *)(v7 + 120);
  if ( !v8 )
  {
    v36 = GetLastError();
    v39 = v36;
    if ( v36 > 0 )
      v39 = (unsigned __int16)v36 | 0x80070000;
    *(_DWORD *)a1[1] = v39;
    v40 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v40 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v37) = v40;
      LOBYTE(v38) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, v38, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v41 = wil::verify_hresult<long>(*(unsigned int *)a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v41,
      v53);
  }
  *(_QWORD *)(v7 + 112) = v8;
  v9 = v7 + 72;
  v10 = (_QWORD **)a1[3];
  *(_BYTE *)(v7 + 16) = *(_BYTE *)a1[2];
  *(_QWORD *)(v7 + 17) = **v10;
  *(_OWORD *)(v7 + 25) = *(_OWORD *)*(_QWORD *)a1[4];
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_OnIgnoreTimer,
                      (PVOID)v7,
                      0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    v9,
    ThreadpoolTimer);
  v12 = *a1;
  if ( !*(_QWORD *)(*a1 + 72) )
  {
    v42 = GetLastError();
    v45 = v42;
    if ( v42 > 0 )
      v45 = (unsigned __int16)v42 | 0x80070000;
    *(_DWORD *)a1[1] = v45;
    v46 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v46 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v43) = v46;
      LOBYTE(v44) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, v44, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v47 = wil::verify_hresult<long>(*(unsigned int *)a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v47,
      v53);
  }
  v13 = 1;
  v14 = CreateEventW(0, 1, 0, 0);
  v15 = *(char **)(v12 + 2048);
  v16 = v14;
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v17 = GetLastError();
    CloseHandle(v15);
    SetLastError(v17);
  }
  v18 = *a1;
  *(_QWORD *)(v12 + 2048) = v16;
  if ( !*(_QWORD *)(v18 + 2048) )
  {
    v48 = GetLastError();
    v51 = v48;
    if ( v48 > 0 )
      v51 = (unsigned __int16)v48 | 0x80070000;
    *(_DWORD *)a1[1] = v51;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v13 = 0;
    if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v49) = v13;
      LOBYTE(v50) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, v50, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v52 = wil::verify_hresult<long>(*(unsigned int *)a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v52,
      v53);
  }
  v19 = CreateEventW(0, 1, 0, 0);
  v20 = *(char **)(v18 + 2056);
  v21 = v19;
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v22 = GetLastError();
    CloseHandle(v20);
    SetLastError(v22);
  }
  v23 = *a1;
  *(_QWORD *)(v18 + 2056) = v21;
  if ( !*(_QWORD *)(v23 + 2056) )
  {
    v31 = GetLastError();
    v34 = v31;
    if ( v31 > 0 )
      v34 = (unsigned __int16)v31 | 0x80070000;
    *(_DWORD *)a1[1] = v34;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v13 = 0;
    if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v32) = v13;
      LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v35 = wil::verify_hresult<long>(*(unsigned int *)a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v35,
      v53);
  }
  v24 = operator new[](0x2Du);
  *v24 = 0;
  v24[1] = 0;
  *((_QWORD *)v24 + 4) = 0;
  *((_DWORD *)v24 + 10) = 0;
  *((_BYTE *)v24 + 44) = 0;
  v26 = *(void **)(v23 + 128);
  *(_QWORD *)(v23 + 128) = v24;
  if ( v26 )
    operator delete(v26, v25);
  v27 = *a1;
  v28 = 0;
  v29 = *(_QWORD *)(*a1 + 128);
  do
  {
    *(_BYTE *)(v28 + v29 + 24) = *(_BYTE *)(v27 + 16);
    ++v28;
  }
  while ( v28 < 2 );
  *(_DWORD *)(v29 + 26) = 16779836;
  *(_DWORD *)(v29 + 33) = 4;
  *(_WORD *)(v29 + 30) = 767;
  *(_BYTE *)(v29 + 32) = 12;
  result = *(_QWORD *)(v27 + 17);
  *(_QWORD *)(v29 + 37) = result;
  return result;
}

```

## disassembly

```asm
0x18002ea48  mov     [rsp+arg_0], rbx
0x18002ea4d  mov     [rsp+arg_8], rbp
0x18002ea52  mov     [rsp+arg_10], rsi
0x18002ea57  push    rdi
0x18002ea58  push    r14
0x18002ea5a  push    r15
0x18002ea5c  sub     rsp, 50h
0x18002ea60  mov     rdi, [rcx]
0x18002ea63  xorps   xmm0, xmm0
0x18002ea66  mov     rsi, rcx
0x18002ea69  xor     r9d, r9d; lpName
0x18002ea6c  xor     r8d, r8d; bInitialState
0x18002ea6f  xor     edx, edx; bManualReset
0x18002ea71  xor     ecx, ecx; lpEventAttributes
0x18002ea73  movups  xmmword ptr [rdi+58h], xmm0
0x18002ea77  movups  xmmword ptr [rdi+68h], xmm0
0x18002ea7b  call    cs:__imp_CreateEventW
0x18002ea82  nop     dword ptr [rax+rax+00h]
0x18002ea87  mov     rbp, [rdi+78h]
0x18002ea8b  mov     r14, rax
0x18002ea8e  lea     rdx, [rbp-1]
0x18002ea92  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002ea96  ja      short loc_18002EAC3
0x18002ea98  call    cs:__imp_GetLastError
0x18002ea9f  nop     dword ptr [rax+rax+00h]
0x18002eaa4  mov     rcx, rbp; hObject
0x18002eaa7  mov     ebx, eax
0x18002eaa9  call    cs:__imp_CloseHandle
0x18002eab0  nop     dword ptr [rax+rax+00h]
0x18002eab5  mov     ecx, ebx; dwErrCode
0x18002eab7  call    cs:__imp_SetLastError
0x18002eabe  nop     dword ptr [rax+rax+00h]
0x18002eac3  mov     rdx, [rsi]; pv
0x18002eac6  mov     [rdi+78h], r14
0x18002eaca  mov     rax, [rdx+78h]
0x18002eace  test    rax, rax
0x18002ead1  jz      loc_18002ED48
0x18002ead7  mov     [rdx+70h], rax
0x18002eadb  lea     rbx, [rdx+48h]
0x18002eadf  mov     rax, [rsi+10h]
0x18002eae3  xor     r8d, r8d; pcbe
0x18002eae6  mov     cl, [rax]
0x18002eae8  mov     rax, [rsi+18h]
0x18002eaec  mov     [rdx+10h], cl
0x18002eaef  mov     rcx, [rax]
0x18002eaf2  mov     rax, [rcx]
0x18002eaf5  mov     [rdx+11h], rax
0x18002eaf9  mov     rax, [rsi+20h]
0x18002eafd  mov     rcx, [rax]
0x18002eb00  movups  xmm0, xmmword ptr [rcx]
0x18002eb03  lea     rcx, ?s_OnIgnoreTimer@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002eb0a  movdqu  xmmword ptr [rdx+19h], xmm0
0x18002eb0f  call    cs:__imp_CreateThreadpoolTimer
0x18002eb16  nop     dword ptr [rax+rax+00h]
0x18002eb1b  mov     rdx, rax
0x18002eb1e  mov     rcx, rbx
0x18002eb21  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002eb26  mov     r14, [rsi]
0x18002eb29  cmp     qword ptr [r14+48h], 0
0x18002eb2e  jz      loc_18002EDF5
0x18002eb34  xor     r9d, r9d; lpName
0x18002eb37  xor     r8d, r8d; bInitialState
0x18002eb3a  xor     ecx, ecx; lpEventAttributes
0x18002eb3c  lea     edi, [r9+1]
0x18002eb40  mov     edx, edi; bManualReset
0x18002eb42  call    cs:__imp_CreateEventW
0x18002eb49  nop     dword ptr [rax+rax+00h]
0x18002eb4e  mov     rbp, [r14+800h]
0x18002eb55  mov     r15, rax
0x18002eb58  lea     rdx, [rbp-1]
0x18002eb5c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002eb60  ja      short loc_18002EB8D
0x18002eb62  call    cs:__imp_GetLastError
0x18002eb69  nop     dword ptr [rax+rax+00h]
0x18002eb6e  mov     rcx, rbp; hObject
0x18002eb71  mov     ebx, eax
0x18002eb73  call    cs:__imp_CloseHandle
0x18002eb7a  nop     dword ptr [rax+rax+00h]
0x18002eb7f  mov     ecx, ebx; dwErrCode
0x18002eb81  call    cs:__imp_SetLastError
0x18002eb88  nop     dword ptr [rax+rax+00h]
0x18002eb8d  mov     rbp, [rsi]
0x18002eb90  mov     [r14+800h], r15
0x18002eb97  cmp     qword ptr [rbp+800h], 0
0x18002eb9f  jz      loc_18002EEA2
0x18002eba5  xor     r9d, r9d; lpName
0x18002eba8  xor     r8d, r8d; bInitialState
0x18002ebab  mov     edx, edi; bManualReset
0x18002ebad  xor     ecx, ecx; lpEventAttributes
0x18002ebaf  call    cs:__imp_CreateEventW
0x18002ebb6  nop     dword ptr [rax+rax+00h]
0x18002ebbb  mov     r14, [rbp+808h]
0x18002ebc2  mov     r15, rax
0x18002ebc5  lea     rdx, [r14-1]
0x18002ebc9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002ebcd  ja      short loc_18002EBFA
0x18002ebcf  call    cs:__imp_GetLastError
0x18002ebd6  nop     dword ptr [rax+rax+00h]
0x18002ebdb  mov     rcx, r14; hObject
0x18002ebde  mov     ebx, eax
0x18002ebe0  call    cs:__imp_CloseHandle
0x18002ebe7  nop     dword ptr [rax+rax+00h]
0x18002ebec  mov     ecx, ebx; dwErrCode
0x18002ebee  call    cs:__imp_SetLastError
0x18002ebf5  nop     dword ptr [rax+rax+00h]
0x18002ebfa  mov     rbx, [rsi]
0x18002ebfd  mov     [rbp+808h], r15
0x18002ec04  cmp     qword ptr [rbx+808h], 0
0x18002ec0c  jz      loc_18002ECA2
0x18002ec12  mov     ecx, 2Dh ; '-'; unsigned __int64
0x18002ec17  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ec1c  xor     ecx, ecx
0x18002ec1e  xorps   xmm0, xmm0
0x18002ec21  movups  xmmword ptr [rax], xmm0
0x18002ec24  movups  xmmword ptr [rax+10h], xmm0
0x18002ec28  mov     [rax+20h], rcx
0x18002ec2c  mov     [rax+28h], ecx
0x18002ec2f  mov     [rax+2Ch], cl
0x18002ec32  mov     rcx, [rbx+80h]; void *
0x18002ec39  mov     [rbx+80h], rax
0x18002ec40  test    rcx, rcx
0x18002ec43  jz      short loc_18002EC4A
0x18002ec45  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ec4a  mov     r8, [rsi]
0x18002ec4d  xor     edx, edx
0x18002ec4f  mov     rcx, [r8+80h]
0x18002ec56  mov     al, [r8+10h]
0x18002ec5a  mov     [rdx+rcx+18h], al
0x18002ec5e  add     rdx, rdi
0x18002ec61  cmp     rdx, 2
0x18002ec65  jl      short loc_18002EC56
0x18002ec67  mov     dword ptr [rcx+1Ah], 1000A3Ch
0x18002ec6e  lea     r11, [rsp+68h+var_18]
0x18002ec73  mov     rbx, [r11+20h]
0x18002ec77  mov     rbp, [r11+28h]
0x18002ec7b  mov     rsi, [r11+30h]
0x18002ec7f  mov     dword ptr [rcx+21h], 4
0x18002ec86  mov     word ptr [rcx+1Eh], 2FFh
0x18002ec8c  mov     byte ptr [rcx+20h], 0Ch
0x18002ec90  mov     rax, [r8+11h]
0x18002ec94  mov     [rcx+25h], rax
0x18002ec98  mov     rsp, r11
0x18002ec9b  pop     r15
0x18002ec9d  pop     r14
0x18002ec9f  pop     rdi
0x18002eca0  retn
0x18002eca2  call    cs:__imp_GetLastError
0x18002eca9  nop     dword ptr [rax+rax+00h]
0x18002ecae  mov     ecx, eax
0x18002ecb0  test    eax, eax
0x18002ecb2  jle     short loc_18002ECBD
0x18002ecb4  movzx   ecx, ax
0x18002ecb7  or      ecx, 80070000h
0x18002ecbd  mov     rax, [rsi+8]
0x18002ecc1  mov     [rax], ecx
0x18002ecc3  mov     r10, cs:WPP_GLOBAL_Control
0x18002ecca  lea     rax, WPP_GLOBAL_Control
0x18002ecd1  cmp     r10, rax
0x18002ecd4  jz      short loc_18002ECDD
0x18002ecd6  cmp     byte ptr [r10+19h], 2
0x18002ecdb  jnb     short loc_18002ECE0
0x18002ecdd  xor     dil, dil
0x18002ece0  lea     rax, WPP_RECORDER_INITIALIZED
0x18002ece7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002ecee  setnz   r8b
0x18002ecf2  test    dil, dil
0x18002ecf5  jnz     short loc_18002ECFC
0x18002ecf7  test    r8b, r8b
0x18002ecfa  jz      short loc_18002ED23
0x18002ecfc  mov     r9, [r10+28h]
0x18002ed00  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ed07  mov     [rsp+68h+var_20], ecx
0x18002ed0b  mov     dl, dil
0x18002ed0e  mov     rcx, [r10+10h]
0x18002ed12  mov     [rsp+68h+var_30], rax
0x18002ed17  mov     [rsp+68h+var_38], 10h
0x18002ed1e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002ed23  mov     rcx, [rsi+8]
0x18002ed27  mov     ecx, [rcx]
0x18002ed29  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ed2e  mov     rcx, [rsp+68h]; this
0x18002ed33  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ed3a  mov     r9d, eax; char *
0x18002ed3d  mov     edx, 6Bh ; 'k'; void *
0x18002ed42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed48  call    cs:__imp_GetLastError
0x18002ed4f  nop     dword ptr [rax+rax+00h]
0x18002ed54  mov     ecx, eax
0x18002ed56  test    eax, eax
0x18002ed58  jle     short loc_18002ED63
0x18002ed5a  movzx   ecx, ax
0x18002ed5d  or      ecx, 80070000h
0x18002ed63  mov     rax, [rsi+8]
0x18002ed67  mov     [rax], ecx
0x18002ed69  mov     r10, cs:WPP_GLOBAL_Control
0x18002ed70  lea     rax, WPP_GLOBAL_Control
0x18002ed77  cmp     r10, rax
0x18002ed7a  jz      short loc_18002ED8A
0x18002ed7c  cmp     byte ptr [r10+19h], 2
0x18002ed81  jb      short loc_18002ED8A
0x18002ed83  mov     edi, 1
0x18002ed88  jmp     short loc_18002ED8D
0x18002ed8a  xor     dil, dil
0x18002ed8d  lea     rax, WPP_RECORDER_INITIALIZED
0x18002ed94  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002ed9b  setnz   r8b
0x18002ed9f  test    dil, dil
0x18002eda2  jnz     short loc_18002EDA9
0x18002eda4  test    r8b, r8b
0x18002eda7  jz      short loc_18002EDD0
0x18002eda9  mov     r9, [r10+28h]
0x18002edad  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002edb4  mov     [rsp+68h+var_20], ecx
0x18002edb8  mov     dl, dil
0x18002edbb  mov     rcx, [r10+10h]
0x18002edbf  mov     [rsp+68h+var_30], rax
0x18002edc4  mov     [rsp+68h+var_38], 0Dh
0x18002edcb  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002edd0  mov     rcx, [rsi+8]
0x18002edd4  mov     ecx, [rcx]
0x18002edd6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002eddb  mov     rcx, [rsp+68h]; this
0x18002ede0  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ede7  mov     r9d, eax; char *
0x18002edea  mov     edx, 49h ; 'I'; void *
0x18002edef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002edf5  call    cs:__imp_GetLastError
0x18002edfc  nop     dword ptr [rax+rax+00h]
0x18002ee01  mov     ecx, eax
0x18002ee03  test    eax, eax
0x18002ee05  jle     short loc_18002EE10
0x18002ee07  movzx   ecx, ax
0x18002ee0a  or      ecx, 80070000h
0x18002ee10  mov     rax, [rsi+8]
0x18002ee14  mov     [rax], ecx
0x18002ee16  mov     r10, cs:WPP_GLOBAL_Control
0x18002ee1d  lea     rax, WPP_GLOBAL_Control
0x18002ee24  cmp     r10, rax
0x18002ee27  jz      short loc_18002EE37
0x18002ee29  cmp     byte ptr [r10+19h], 2
0x18002ee2e  jb      short loc_18002EE37
0x18002ee30  mov     edi, 1
0x18002ee35  jmp     short loc_18002EE3A
0x18002ee37  xor     dil, dil
0x18002ee3a  lea     rax, WPP_RECORDER_INITIALIZED
0x18002ee41  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002ee48  setnz   r8b
0x18002ee4c  test    dil, dil
0x18002ee4f  jnz     short loc_18002EE56
0x18002ee51  test    r8b, r8b
0x18002ee54  jz      short loc_18002EE7D
0x18002ee56  mov     r9, [r10+28h]
0x18002ee5a  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ee61  mov     [rsp+68h+var_20], ecx
0x18002ee65  mov     dl, dil
0x18002ee68  mov     rcx, [r10+10h]
0x18002ee6c  mov     [rsp+68h+var_30], rax
0x18002ee71  mov     [rsp+68h+var_38], 0Eh
0x18002ee78  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002ee7d  mov     rcx, [rsi+8]
0x18002ee81  mov     ecx, [rcx]
0x18002ee83  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ee88  mov     rcx, [rsp+68h]; this
0x18002ee8d  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ee94  mov     r9d, eax; char *
0x18002ee97  mov     edx, 5Bh ; '['; void *
0x18002ee9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eea2  call    cs:__imp_GetLastError
0x18002eea9  nop     dword ptr [rax+rax+00h]
0x18002eeae  mov     ecx, eax
0x18002eeb0  test    eax, eax
0x18002eeb2  jle     short loc_18002EEBD
0x18002eeb4  movzx   ecx, ax
0x18002eeb7  or      ecx, 80070000h
0x18002eebd  mov     rax, [rsi+8]
0x18002eec1  mov     [rax], ecx
0x18002eec3  mov     r10, cs:WPP_GLOBAL_Control
0x18002eeca  lea     rax, WPP_GLOBAL_Control
0x18002eed1  cmp     r10, rax
0x18002eed4  jz      short loc_18002EEDD
0x18002eed6  cmp     byte ptr [r10+19h], 2
0x18002eedb  jnb     short loc_18002EEE0
0x18002eedd  xor     dil, dil
0x18002eee0  lea     rax, WPP_RECORDER_INITIALIZED
0x18002eee7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002eeee  setnz   r8b
0x18002eef2  test    dil, dil
0x18002eef5  jnz     short loc_18002EEFC
0x18002eef7  test    r8b, r8b
0x18002eefa  jz      short loc_18002EF23
0x18002eefc  mov     r9, [r10+28h]
0x18002ef00  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ef07  mov     [rsp+68h+var_20], ecx
0x18002ef0b  mov     dl, dil
0x18002ef0e  mov     rcx, [r10+10h]
0x18002ef12  mov     [rsp+68h+var_30], rax
0x18002ef17  mov     [rsp+68h+var_38], 0Fh
0x18002ef1e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002ef23  mov     rcx, [rsi+8]
0x18002ef27  mov     ecx, [rcx]
  ... truncated ...
```
