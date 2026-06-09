# Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(_BLUETOOTH_DEVICE_INFO const *)

- ea: `0x180025ecc`
- end: `0x18002664a`
- name: `?BthpFindAndStampPnpInfoFromServiceSearch@BthServ@Services@Bluetooth@Microsoft@@YAJPEBU_BLUETOOTH_DEVICE_INFO@@@Z`
- size: `1918`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, const struct _BLUETOOTH_DEVICE_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025648`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180007f94`
- `0x180007fb4`
- `0x180012004`
- `0x18002424c`
- `0x1800246b4`
- `0x180025ecc`
- `0x180029e10`
- `0x180029e30`
- `0x180029e4c`
- `0x1800370c4`
- `0x180037be8`
- `0x1800381b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180026129`
- `ntdll!RtlNtStatusToDosError` at `0x180026231`
- `ntdll!RtlNtStatusToDosError` at `0x180026129`
- `ntdll!RtlNtStatusToDosError` at `0x180026231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002662d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002662d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002655e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002655e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025ff0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800260aa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800261c2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026308`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026390`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026409`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026542`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025ff0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800260aa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800261c2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026308`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026390`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026409`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026542`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(
        Microsoft::Bluetooth::Services::BthServ *this,
        const struct _BLUETOOTH_DEVICE_INFO *a2)
{
  void *v3; // rcx
  char v4; // dl
  int LastError; // ebx
  const char *v6; // r9
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  signed int v9; // eax
  signed int v10; // edi
  HANDLE v11; // rcx
  bool v12; // cc
  int *v14; // rsi
  NTSTATUS AttributeInTree; // eax
  signed int v16; // eax
  const char *v17; // r9
  signed int v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  signed int v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  signed int v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  signed int v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  signed int v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  signed int v33; // eax
  int v34; // edx
  unsigned int v35; // r8d
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  int lpOutBuffera; // [rsp+20h] [rbp-E0h]
  const char *nOutBufferSize; // [rsp+28h] [rbp-D8h]
  HANDLE hDevice; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  void **v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+70h] [rbp-90h] BYREF
  _DWORD InBuffer[5]; // [rsp+78h] [rbp-88h] BYREF
  char v45; // [rsp+8Ch] [rbp-74h]
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  HANDLE *p_hDevice; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  char v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v51; // [rsp+BCh] [rbp-44h]
  __int16 v52; // [rsp+CCh] [rbp-34h]
  int v53; // [rsp+1ACh] [rbp+ACh]
  __int64 v54; // [rsp+1B0h] [rbp+B0h] BYREF
  int v55; // [rsp+1BCh] [rbp+BCh]
  __int16 v56; // [rsp+1C0h] [rbp+C0h]
  __int16 v57; // [rsp+1C2h] [rbp+C2h]
  __int16 v58; // [rsp+1C6h] [rbp+C6h]
  int v59; // [rsp+8E0h] [rbp+7E0h] BYREF
  __int16 v60; // [rsp+8E4h] [rbp+7E4h]
  char v61; // [rsp+8E6h] [rbp+7E6h] BYREF
  _BYTE OutBuffer[4]; // [rsp+8F0h] [rbp+7F0h] BYREF
  int v63; // [rsp+8F4h] [rbp+7F4h]
  char v64; // [rsp+8F8h] [rbp+7F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A08h] [rbp+908h]

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v4 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  hDevice = 0;
  p_hDevice = &hDevice;
  v48 = 0;
  v49 = 1;
  LastError = BthDevnodeOpenInterfaceHandle(v3, 0, &v48);
  wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hDevice);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
      (const char *)(unsigned int)LastError,
      lpOutBuffer);
LABEL_70:
    if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hDevice);
    return (unsigned int)LastError;
  }
  memset(&InBuffer[2], 0, 12);
  *(_QWORD *)InBuffer = *((_QWORD *)this + 1);
  v45 = 10;
  if ( !DeviceIoControl(hDevice, 0x410200u, InBuffer, 0x15u, InBuffer, 0x15u, 0, 0) )
  {
    v7 = 230;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
                  v6);
    if ( !*(_QWORD *)&InBuffer[3] )
      goto LABEL_70;
    v40 = *(_QWORD *)&InBuffer[3];
LABEL_69:
    DeviceIoControl(hDevice, 0x410204u, &v40, 8u, 0, 0, 0, 0);
    goto LABEL_70;
  }
  memset_0(&v50, 0, 0x100u);
  v50 = *(_QWORD *)&InBuffer[3];
  v51 = 4608;
  v52 = 304;
  v53 = 33882625;
  memset_0(OutBuffer, 0, 0xD1u);
  if ( !DeviceIoControl(hDevice, 0x410210u, &v50, 0x100u, OutBuffer, 0xD1u, 0, 0) )
  {
    v7 = 251;
    goto LABEL_11;
  }
  v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
  v42 = 0;
  v40 = 0;
  v46 = 0;
  v43 = 0;
  SdpGetNextElement((unsigned int)&v64, v63, 0, (unsigned int)&v46, (__int64)&v43);
  if ( !v46 || !v43 )
  {
    LastError = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x105,
                  (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
                  (const char *)0x490,
                  (unsigned int)"Pnp attribute not found",
                  nOutBufferSize);
    if ( v42 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
      {
        v18 = GetLastError();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
        __debugbreak();
      }
      v42 = 0;
    }
    if ( !*(_QWORD *)&InBuffer[3] )
      goto LABEL_70;
    v40 = *(_QWORD *)&InBuffer[3];
    goto LABEL_69;
  }
  v8 = SdpTreeFromStream(v46, (unsigned int)v43, &v42);
  v9 = RtlNtStatusToDosError(v8);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    memset_0(&v54, 0, 0x72Au);
    v59 = 33686017;
    v60 = 517;
    v14 = &v59;
    do
    {
      AttributeInTree = SdpFindAttributeInTree(v42, *(unsigned __int16 *)v14, &v40);
      v16 = RtlNtStatusToDosError(AttributeInTree);
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
          (const char *)(unsigned int)v10,
          lpOutBuffera);
        v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
        if ( !v42 )
          goto LABEL_23;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
        {
          v24 = GetLastError();
          if ( v24 > 0 )
            v24 = (unsigned __int16)v24 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
          __debugbreak();
        }
        goto LABEL_22;
      }
      if ( *(_WORD *)(v40 + 16) != 1 || *(_WORD *)(v40 + 18) != 272 || *(_DWORD *)(v40 + 24) != 2 )
      {
        v10 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
          (const char *)0x80070057LL,
          lpOutBuffera);
        v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
        if ( !v42 )
          goto LABEL_23;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
        {
          v21 = GetLastError();
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
          __debugbreak();
        }
        goto LABEL_22;
      }
      switch ( *(_WORD *)v14 )
      {
        case 0x201:
          v56 = *(_WORD *)(v40 + 32);
          break;
        case 0x202:
          v57 = *(_WORD *)(v40 + 32);
          break;
        case 0x205:
          v58 = *(_WORD *)(v40 + 32);
          break;
      }
      v14 = (int *)((char *)v14 + 2);
    }
    while ( v14 != (int *)&v61 );
    v54 = *((_QWORD *)this + 1);
    v55 = 20;
    if ( !DeviceIoControl(hDevice, 0x411030u, &v54, 0x72Au, 0, 0, 0, 0) )
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x145,
              (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
              v17);
      v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
      if ( v42 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
        {
          v30 = GetLastError();
          if ( v30 > 0 )
            v30 = (unsigned __int16)v30 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
          __debugbreak();
        }
        v42 = 0;
      }
      if ( *(_QWORD *)&InBuffer[3] )
      {
        v40 = *(_QWORD *)&InBuffer[3];
        DeviceIoControl(hDevice, 0x410204u, &v40, 8u, 0, 0, 0, 0);
      }
      v11 = hDevice;
      v12 = (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_26;
    }
    v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
    if ( v42 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
      {
        v33 = GetLastError();
        if ( v33 > 0 )
          v33 = (unsigned __int16)v33 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v33, v34, v35);
        JUMPOUT(0x180026649LL);
      }
      v42 = 0;
    }
    if ( *(_QWORD *)&InBuffer[3] )
    {
      v40 = *(_QWORD *)&InBuffer[3];
      DeviceIoControl(hDevice, 0x410204u, &v40, 8u, 0, 0, 0, 0);
    }
    if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hDevice);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
      (const char *)(unsigned int)v10,
      lpOutBuffera);
    v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
    if ( v42 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v41) )
      {
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
        __debugbreak();
      }
LABEL_22:
      v42 = 0;
    }
LABEL_23:
    if ( *(_QWORD *)&InBuffer[3] )
    {
      v40 = *(_QWORD *)&InBuffer[3];
      DeviceIoControl(hDevice, 0x410204u, &v40, 8u, 0, 0, 0, 0);
    }
    v11 = hDevice;
    v12 = (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_26:
    if ( v12 )
      CloseHandle(v11);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180025ecc  mov     [rsp-8+arg_8], rbx
0x180025ed1  mov     [rsp-8+arg_10], rsi
0x180025ed6  push    rbp
0x180025ed7  push    rdi
0x180025ed8  push    r12
0x180025eda  push    r14
0x180025edc  push    r15
0x180025ede  lea     rbp, [rsp-8E0h]
0x180025ee6  sub     rsp, 9E0h
0x180025eed  mov     rax, cs:__security_cookie
0x180025ef4  xor     rax, rsp
0x180025ef7  mov     [rbp+900h+var_30], rax
0x180025efe  mov     r14, rcx
0x180025f01  lea     rax, WPP_GLOBAL_Control
0x180025f08  xor     r15d, r15d
0x180025f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f12  cmp     rcx, rax
0x180025f15  jz      short loc_180025F1F
0x180025f17  cmp     byte ptr [rcx+19h], 5
0x180025f1b  mov     dl, 1
0x180025f1d  jnb     short loc_180025F22
0x180025f1f  mov     dl, r15b
0x180025f22  lea     rax, WPP_RECORDER_INITIALIZED
0x180025f29  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025f30  setnz   r8b
0x180025f34  test    dl, dl
0x180025f36  jnz     short loc_180025F3D
0x180025f38  test    r8b, r8b
0x180025f3b  jz      short loc_180025F5D
0x180025f3d  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180025f44  mov     [rsp+0A00h+lpOverlapped], rax
0x180025f49  mov     word ptr [rsp+0A00h+lpBytesReturned], 0Fh
0x180025f50  mov     r9, [rcx+28h]
0x180025f54  mov     rcx, [rcx+10h]
0x180025f58  call    WPP_RECORDER_AND_TRACE_SF_s
0x180025f5d  mov     [rsp+0A00h+hDevice], r15
0x180025f62  lea     rax, [rsp+0A00h+hDevice]
0x180025f67  mov     [rbp+900h+var_968], rax
0x180025f6b  mov     [rbp+900h+var_960], r15
0x180025f6f  mov     [rbp+900h+var_958], 1
0x180025f73  lea     r8, [rbp+900h+var_960]
0x180025f77  xor     edx, edx
0x180025f79  call    BthDevnodeOpenInterfaceHandle
0x180025f7e  mov     ebx, eax
0x180025f80  lea     rcx, [rbp+900h+var_968]
0x180025f84  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180025f89  test    ebx, ebx
0x180025f8b  jns     short loc_180025FAD
0x180025f8d  mov     rcx, [rbp+908h]; this
0x180025f94  mov     r9d, ebx; char *
0x180025f97  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180025f9e  mov     edx, 0C7h; void *
0x180025fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025fa8  jmp     loc_18002654F
0x180025fad  mov     [rbp+900h+var_980], r15
0x180025fb1  mov     [rbp+900h+var_978], r15d
0x180025fb5  mov     rax, [r14+8]
0x180025fb9  mov     [rsp+0A00h+InBuffer], rax
0x180025fbe  mov     [rbp+900h+var_974], 0Ah
0x180025fc2  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x180025fc7  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x180025fcc  mov     r9d, 15h; nInBufferSize
0x180025fd2  mov     dword ptr [rsp+0A00h+nOutBufferSize], r9d; nOutBufferSize
0x180025fd7  lea     rax, [rsp+0A00h+InBuffer]
0x180025fdc  mov     [rsp+0A00h+lpOutBuffer], rax; lpOutBuffer
0x180025fe1  lea     r8, [rsp+0A00h+InBuffer]; lpInBuffer
0x180025fe6  mov     edx, 410200h; dwIoControlCode
0x180025feb  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x180025ff0  call    cs:__imp_DeviceIoControl
0x180025ff7  nop     dword ptr [rax+rax+00h]
0x180025ffc  test    eax, eax
0x180025ffe  jnz     short loc_180026031
0x180026000  mov     edx, 0E6h; void *
0x180026005  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18002600c  mov     rcx, [rbp+908h]; this
0x180026013  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026018  mov     ebx, eax
0x18002601a  mov     rcx, [rbp+900h+var_980+4]
0x18002601e  test    rcx, rcx
0x180026021  jz      loc_18002654F
0x180026027  mov     [rsp+0A00h+var_9A8], rcx
0x18002602c  jmp     loc_180026519
0x180026031  mov     edi, 100h
0x180026036  mov     r8d, edi; Size
0x180026039  xor     edx, edx; Val
0x18002603b  lea     rcx, [rbp+900h+var_950]; void *
0x18002603f  call    memset_0
0x180026044  mov     rax, [rbp+900h+var_980+4]
0x180026048  mov     [rbp+900h+var_950], rax
0x18002604c  mov     eax, 1200h
0x180026051  mov     [rbp+900h+var_944], ax
0x180026055  lea     eax, [rdi+30h]
0x180026058  mov     [rbp+900h+var_934], ax
0x18002605c  mov     [rbp+900h+var_854], 2050201h
0x180026066  mov     esi, 205h
0x18002606b  lea     ebx, [rdi-2Fh]
0x18002606e  mov     r8d, ebx; Size
0x180026071  xor     edx, edx; Val
0x180026073  lea     rcx, [rbp+900h+OutBuffer]; void *
0x18002607a  call    memset_0
0x18002607f  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x180026084  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x180026089  mov     dword ptr [rsp+0A00h+nOutBufferSize], ebx; char *
0x18002608d  lea     rax, [rbp+900h+OutBuffer]
0x180026094  mov     [rsp+0A00h+lpOutBuffer], rax; lpOutBuffer
0x180026099  mov     r9d, edi; nInBufferSize
0x18002609c  lea     r8, [rbp+900h+var_950]; lpInBuffer
0x1800260a0  mov     edx, 410210h; dwIoControlCode
0x1800260a5  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x1800260aa  call    cs:__imp_DeviceIoControl
0x1800260b1  nop     dword ptr [rax+rax+00h]
0x1800260b6  test    eax, eax
0x1800260b8  jnz     short loc_1800260C2
0x1800260ba  lea     edx, [rdi-5]
0x1800260bd  jmp     loc_180026005
0x1800260c2  lea     r12, ??_7?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable'
0x1800260c9  mov     [rsp+0A00h+var_9A0], r12
0x1800260ce  mov     [rsp+0A00h+var_998], r15
0x1800260d3  mov     [rsp+0A00h+var_9A8], r15
0x1800260d8  mov     [rbp+900h+var_970], r15
0x1800260dc  mov     [rsp+0A00h+var_990], r15d
0x1800260e1  lea     rax, [rsp+0A00h+var_990]
0x1800260e6  mov     [rsp+0A00h+lpOutBuffer], rax; int
0x1800260eb  lea     r9, [rbp+900h+var_970]
0x1800260ef  xor     r8d, r8d
0x1800260f2  mov     edx, [rbp+900h+var_10C]
0x1800260f8  lea     rcx, [rbp+900h+var_108]
0x1800260ff  call    SdpGetNextElement
0x180026104  mov     rcx, [rbp+900h+var_970]
0x180026108  test    rcx, rcx
0x18002610b  jz      loc_1800264C1
0x180026111  mov     edx, [rsp+0A00h+var_990]
0x180026115  test    edx, edx
0x180026117  jz      loc_1800264C1
0x18002611d  lea     r8, [rsp+0A00h+var_998]
0x180026122  call    SdpTreeFromStream
0x180026127  mov     ecx, eax; Status
0x180026129  call    cs:__imp_RtlNtStatusToDosError
0x180026130  nop     dword ptr [rax+rax+00h]
0x180026135  mov     edi, eax
0x180026137  mov     ebx, 80070000h
0x18002613c  test    eax, eax
0x18002613e  jle     short loc_180026145
0x180026140  movzx   edi, ax
0x180026143  or      edi, ebx
0x180026145  test    edi, edi
0x180026147  jns     loc_1800261F1
0x18002614d  mov     rcx, [rbp+908h]; this
0x180026154  mov     r9d, edi; char *
0x180026157  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18002615e  mov     edx, 10Eh; void *
0x180026163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026168  mov     [rsp+0A00h+var_9A0], r12
0x18002616d  cmp     [rsp+0A00h+var_998], r15
0x180026172  jz      short loc_18002618B
0x180026174  lea     rcx, [rsp+0A00h+var_9A0]
0x180026179  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x18002617e  test    al, al
0x180026180  jz      loc_1800265F3
0x180026186  mov     [rsp+0A00h+var_998], r15
0x18002618b  mov     rax, [rbp+900h+var_980+4]
0x18002618f  test    rax, rax
0x180026192  jz      short loc_1800261CF
0x180026194  mov     [rsp+0A00h+var_9A8], rax
0x180026199  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x18002619e  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x1800261a3  mov     dword ptr [rsp+0A00h+nOutBufferSize], r15d; nOutBufferSize
0x1800261a8  mov     [rsp+0A00h+lpOutBuffer], r15; lpOutBuffer
0x1800261ad  mov     r9d, 8; nInBufferSize
0x1800261b3  lea     r8, [rsp+0A00h+var_9A8]; lpInBuffer
0x1800261b8  mov     edx, 410204h; dwIoControlCode
0x1800261bd  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x1800261c2  call    cs:__imp_DeviceIoControl
0x1800261c9  nop     dword ptr [rax+rax+00h]
0x1800261ce  nop
0x1800261cf  mov     rcx, [rsp+0A00h+hDevice]; hObject
0x1800261d4  lea     rdx, [rcx-1]
0x1800261d8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800261dc  ja      short loc_1800261EA
0x1800261de  call    cs:__imp_CloseHandle
0x1800261e5  nop     dword ptr [rax+rax+00h]
0x1800261ea  mov     eax, edi
0x1800261ec  jmp     loc_18002656C
0x1800261f1  xor     edx, edx; Val
0x1800261f3  mov     r8d, 72Ah; Size
0x1800261f9  lea     rcx, [rbp+900h+var_850]; void *
0x180026200  call    memset_0
0x180026205  mov     [rbp+900h+var_120], 2020201h
0x18002620f  mov     [rbp+900h+var_11C], si
0x180026216  lea     rsi, [rbp+900h+var_120]
0x18002621d  lea     r8, [rsp+0A00h+var_9A8]
0x180026222  movzx   edx, word ptr [rsi]
0x180026225  mov     rcx, [rsp+0A00h+var_998]
0x18002622a  call    SdpFindAttributeInTree
0x18002622f  mov     ecx, eax; Status
0x180026231  call    cs:__imp_RtlNtStatusToDosError
0x180026238  nop     dword ptr [rax+rax+00h]
0x18002623d  mov     edi, eax
0x18002623f  test    eax, eax
0x180026241  jle     short loc_180026248
0x180026243  movzx   edi, ax
0x180026246  or      edi, ebx
0x180026248  test    edi, edi
0x18002624a  js      loc_18002647F
0x180026250  mov     rdx, [rsp+0A00h+var_9A8]
0x180026255  cmp     word ptr [rdx+10h], 1
0x18002625a  jnz     loc_180026438
0x180026260  mov     eax, 110h
0x180026265  cmp     [rdx+12h], ax
0x180026269  jnz     loc_180026438
0x18002626f  cmp     dword ptr [rdx+18h], 2
0x180026273  jnz     loc_180026438
0x180026279  movzx   ecx, word ptr [rsi]
0x18002627c  mov     eax, 201h
0x180026281  sub     ecx, eax
0x180026283  jz      short loc_1800262A9
0x180026285  sub     ecx, 1
0x180026288  jz      short loc_18002629C
0x18002628a  cmp     ecx, 3
0x18002628d  jnz     short loc_1800262B4
0x18002628f  movzx   eax, word ptr [rdx+20h]
0x180026293  mov     [rbp+900h+var_83A], ax
0x18002629a  jmp     short loc_1800262B4
0x18002629c  movzx   eax, word ptr [rdx+20h]
0x1800262a0  mov     [rbp+900h+var_83E], ax
0x1800262a7  jmp     short loc_1800262B4
0x1800262a9  movzx   eax, word ptr [rdx+20h]
0x1800262ad  mov     [rbp+900h+var_840], ax
0x1800262b4  add     rsi, 2
0x1800262b8  lea     rax, [rbp+900h+var_11A]
0x1800262bf  cmp     rsi, rax
0x1800262c2  jnz     loc_18002621D
0x1800262c8  mov     rax, [r14+8]
0x1800262cc  mov     [rbp+900h+var_850], rax
0x1800262d3  mov     [rbp+900h+var_844], 14h
0x1800262dd  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x1800262e2  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x1800262e7  mov     dword ptr [rsp+0A00h+nOutBufferSize], r15d; nOutBufferSize
0x1800262ec  mov     [rsp+0A00h+lpOutBuffer], r15; lpOutBuffer
0x1800262f1  mov     r9d, 72Ah; nInBufferSize
0x1800262f7  lea     r8, [rbp+900h+var_850]; lpInBuffer
0x1800262fe  mov     edx, 411030h; dwIoControlCode
0x180026303  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x180026308  call    cs:__imp_DeviceIoControl
0x18002630f  nop     dword ptr [rax+rax+00h]
0x180026314  test    eax, eax
0x180026316  jnz     loc_1800263AF
0x18002631c  mov     rcx, [rbp+908h]; this
0x180026323  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18002632a  mov     edx, 145h; void *
0x18002632f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026334  mov     edi, eax
0x180026336  mov     [rsp+0A00h+var_9A0], r12
0x18002633b  cmp     [rsp+0A00h+var_998], r15
0x180026340  jz      short loc_180026359
0x180026342  lea     rcx, [rsp+0A00h+var_9A0]
0x180026347  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x18002634c  test    al, al
0x18002634e  jz      loc_180026610
0x180026354  mov     [rsp+0A00h+var_998], r15
0x180026359  mov     rax, [rbp+900h+var_980+4]
0x18002635d  test    rax, rax
0x180026360  jz      short loc_18002639D
0x180026362  mov     [rsp+0A00h+var_9A8], rax
0x180026367  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x18002636c  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x180026371  mov     dword ptr [rsp+0A00h+nOutBufferSize], r15d; nOutBufferSize
0x180026376  mov     [rsp+0A00h+lpOutBuffer], r15; lpOutBuffer
0x18002637b  mov     r9d, 8; nInBufferSize
0x180026381  lea     r8, [rsp+0A00h+var_9A8]; lpInBuffer
0x180026386  mov     edx, 410204h; dwIoControlCode
0x18002638b  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x180026390  call    cs:__imp_DeviceIoControl
0x180026397  nop     dword ptr [rax+rax+00h]
0x18002639c  nop
0x18002639d  mov     rcx, [rsp+0A00h+hDevice]
0x1800263a2  lea     rax, [rcx-1]
0x1800263a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800263aa  jmp     loc_1800261DC
0x1800263af  mov     [rsp+0A00h+var_9A0], r12
0x1800263b4  cmp     [rsp+0A00h+var_998], r15
0x1800263b9  jz      short loc_1800263D2
0x1800263bb  lea     rcx, [rsp+0A00h+var_9A0]
0x1800263c0  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x1800263c5  test    al, al
0x1800263c7  jz      loc_18002662D
0x1800263cd  mov     [rsp+0A00h+var_998], r15
0x1800263d2  mov     rax, [rbp+900h+var_980+4]
0x1800263d6  test    rax, rax
0x1800263d9  jz      short loc_180026416
0x1800263db  mov     [rsp+0A00h+var_9A8], rax
0x1800263e0  mov     [rsp+0A00h+lpOverlapped], r15; lpOverlapped
0x1800263e5  mov     [rsp+0A00h+lpBytesReturned], r15; lpBytesReturned
0x1800263ea  mov     dword ptr [rsp+0A00h+nOutBufferSize], r15d; nOutBufferSize
0x1800263ef  mov     [rsp+0A00h+lpOutBuffer], r15; lpOutBuffer
0x1800263f4  mov     r9d, 8; nInBufferSize
0x1800263fa  lea     r8, [rsp+0A00h+var_9A8]; lpInBuffer
0x1800263ff  mov     edx, 410204h; dwIoControlCode
0x180026404  mov     rcx, [rsp+0A00h+hDevice]; hDevice
0x180026409  call    cs:__imp_DeviceIoControl
  ... truncated ...
```
