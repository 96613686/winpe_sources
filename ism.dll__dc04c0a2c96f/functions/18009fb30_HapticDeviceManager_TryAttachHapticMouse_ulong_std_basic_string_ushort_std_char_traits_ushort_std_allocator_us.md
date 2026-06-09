# HapticDeviceManager::TryAttachHapticMouse(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009fb30`
- end: `0x18009fcfc`
- name: `?TryAttachHapticMouse@HapticDeviceManager@@QEAAJKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180112684`

## callees

- `0x180012ee0`
- `0x18008dcac`
- `0x18008ead4`
- `0x18009fb30`
- `0x18009fd10`
- `0x18009fd34`
- `0x18009fd54`
- `0x18009fd78`
- `0x18009feb8`
- `0x18009ff30`
- `0x1800a00c0`
- `0x1800da6a8`
- `0x1800e4190`
- `0x1800f0acc`
- `0x18013dad4`
- `0x180193bf8`
- `0x18019c020`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fb78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fb78`
- `HID!HidD_GetPreparsedData` at `0x18009fb9f`
- `HID!HidD_GetPreparsedData` at `0x18009fb9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HapticDeviceManager::TryAttachHapticMouse(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  const WCHAR *v4; // rax
  char *FileW; // rax
  void (__fastcall ***v9)(_QWORD); // rbx
  struct InputSystemServerConnection *BamoServerConnection; // rax
  void (__fastcall ***v11)(_QWORD); // rax
  void (__fastcall ***v12)(_QWORD); // rsi
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-58h]
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  char *v19; // [rsp+48h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-28h] BYREF
  void (__fastcall ***v21)(_QWORD); // [rsp+58h] [rbp-20h] BYREF
  char v22[24]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  PHIDP_PREPARSED_DATA PreparsedData; // [rsp+B8h] [rbp+40h] BYREF

  v4 = (const WCHAR *)a4;
  if ( *(_QWORD *)(a4 + 24) > 7u )
    v4 = *(const WCHAR **)a4;
  FileW = (char *)CreateFileW(v4, 0x40000000u, 3u, 0, 3u, 0, 0);
  v19 = FileW;
  PreparsedData = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
    && HidD_GetPreparsedData(FileW, &PreparsedData)
    && CompliantHapticInterface::HasManualTriggerHaptic(PreparsedData) )
  {
    wil::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>(
      &v20,
      *(_QWORD *)(a1 + 72));
    v9 = (void (__fastcall ***)(_QWORD))operator new(0x278u);
    v21 = v9;
    BamoServerConnection = ISMStatics::GetBamoServerConnection();
    v11 = (void (__fastcall ***)(_QWORD))MouseHapticDevice::MouseHapticDevice(v9, BamoServerConnection, a2, a3);
    v12 = v11;
    v21 = v11;
    if ( v11 )
      (**v11)(v11);
    v13 = MouseHapticDevice::Initialize(v12, &v19, &PreparsedData);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v15 = Microsoft::Bamo::ListPrincipalSimpleCommon<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,ISMBamos_AutoBamos::BamoConnection,Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Stub,wil::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>,BamoSimpleHapticsControllerPrincipal *>::Add(
              v20,
              v12);
      if ( v15 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\api\\server\\hapticd"
                        "evicemanager.cpp",
          (const char *)(unsigned int)v15,
          dwCreationDisposition);
      v18 = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_HapticMouseAttachedTipTest_attributes,tip2::test_data_basic>>::start(
        &v18,
        v22);
      if ( v18 )
        tip2::details::shared_data<0,0,1>::complete_without_lock(v18 + 8);
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const unsigned __int16 **)a3;
      InputTraceLogging::Haptics::HapticDeviceAdded(IMDT_MOUSE, a3);
      wil::com_ptr_t<tip2::details::merged_data<_tip_HapticPenAttachedTipTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HapticPenAttachedTipTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v18);
      v14 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\api\\server\\hapticdevicemanager.cpp",
        (const char *)(unsigned int)v13,
        dwCreationDisposition);
    }
    wil::com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>::~com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>(&v21);
    wil::com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>::~com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>(&v20);
    wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(&PreparsedData);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    return v14;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(&PreparsedData);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18009fb30  push    rbp
0x18009fb32  push    rbx
0x18009fb33  push    rsi
0x18009fb34  push    rdi
0x18009fb35  mov     rbp, rsp
0x18009fb38  sub     rsp, 78h
0x18009fb3c  mov     rax, r9
0x18009fb3f  mov     rdi, r8
0x18009fb42  mov     esi, edx
0x18009fb44  mov     rbx, rcx
0x18009fb47  cmp     qword ptr [r9+18h], 7
0x18009fb4c  jbe     short loc_18009FB51
0x18009fb4e  mov     rax, [r9]
0x18009fb51  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18009fb5a  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18009fb62  mov     r8d, 3; dwShareMode
0x18009fb68  mov     [rsp+78h+dwCreationDisposition], r8d; int
0x18009fb6d  xor     r9d, r9d; lpSecurityAttributes
0x18009fb70  mov     edx, 40000000h; dwDesiredAccess
0x18009fb75  mov     rcx, rax; lpFileName
0x18009fb78  call    cs:__imp_CreateFileW
0x18009fb7e  mov     [rbp+var_30], rax
0x18009fb82  mov     [rbp+PreparsedData], 0
0x18009fb8a  lea     rcx, [rax-1]
0x18009fb8e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18009fb92  ja      loc_18009FCDB
0x18009fb98  lea     rdx, [rbp+PreparsedData]; PreparsedData
0x18009fb9c  mov     rcx, rax; HidDeviceObject
0x18009fb9f  call    cs:__imp_HidD_GetPreparsedData
0x18009fba5  test    al, al
0x18009fba7  jz      loc_18009FCDB
0x18009fbad  mov     rcx, [rbp+PreparsedData]; struct _HIDP_PREPARSED_DATA *
0x18009fbb1  call    ?HasManualTriggerHaptic@CompliantHapticInterface@@SA_NPEAU_HIDP_PREPARSED_DATA@@@Z; CompliantHapticInterface::HasManualTriggerHaptic(_HIDP_PREPARSED_DATA *)
0x18009fbb6  test    al, al
0x18009fbb8  jz      loc_18009FCDB
0x18009fbbe  mov     rdx, [rbx+48h]
0x18009fbc2  lea     rcx, [rbp+var_28]
0x18009fbc6  call    ??0?$com_ptr_t@VBamoSimpleHapticsControllerPrincipal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVBamoSimpleHapticsControllerPrincipal@@@Z; wil::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>(BamoSimpleHapticsControllerPrincipal *)
0x18009fbcb  nop
0x18009fbcc  mov     ecx, 278h; Size
0x18009fbd1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009fbd6  mov     rbx, rax
0x18009fbd9  mov     [rbp+var_20], rax
0x18009fbdd  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18009fbe2  mov     r9, rdi
0x18009fbe5  mov     r8d, esi
0x18009fbe8  mov     rdx, rax
0x18009fbeb  mov     rcx, rbx
0x18009fbee  call    ??0MouseHapticDevice@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MouseHapticDevice::MouseHapticDevice(ISMBamos_AutoBamos::BamoConnection *,ulong,std::wstring const &)
0x18009fbf3  mov     rsi, rax
0x18009fbf6  mov     [rbp+var_20], rax
0x18009fbfa  test    rax, rax
0x18009fbfd  jz      short loc_18009FC0E
0x18009fbff  mov     rcx, [rax]
0x18009fc02  mov     rax, [rcx]
0x18009fc05  mov     rcx, rsi
0x18009fc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fc0d  nop
0x18009fc0e  lea     r8, [rbp+PreparsedData]
0x18009fc12  lea     rdx, [rbp+var_30]
0x18009fc16  mov     rcx, rsi
0x18009fc19  call    ?Initialize@MouseHapticDevice@@QEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; MouseHapticDevice::Initialize(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>> &&)
0x18009fc1e  mov     ebx, eax
0x18009fc20  test    eax, eax
0x18009fc22  jns     short loc_18009FC3E
0x18009fc24  mov     rcx, [rbp+20h]; this
0x18009fc28  mov     r9d, eax; char *
0x18009fc2b  lea     r8, aOnecoreuapWind_26; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009fc32  mov     edx, 0FEh; void *
0x18009fc37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fc3c  jmp     short loc_18009FCB0
0x18009fc3e  mov     rdx, rsi
0x18009fc41  mov     rcx, [rbp+var_28]
0x18009fc45  call    ?Add@?$ListPrincipalSimpleCommon@VBamoList_SimpleHapticsControllerPrincipal_Principal@ISMBamos_AutoBamos@Lib@Bamo@Microsoft@@VBamoConnection@2@VBamoList_SimpleHapticsControllerPrincipal_Stub@2345@V?$com_ptr_t@VBamoSimpleHapticsControllerPrincipal@@Uerr_returncode_policy@wil@@@wil@@PEAVBamoSimpleHapticsControllerPrincipal@@@Bamo@Microsoft@@QEAAJPEAVBamoSimpleHapticsControllerPrincipal@@@Z; Microsoft::Bamo::ListPrincipalSimpleCommon<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,ISMBamos_AutoBamos::BamoConnection,Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Stub,wil::com_ptr_t<BamoSimpleHapticsControllerPrincipal,wil::err_returncode_policy>,BamoSimpleHapticsControllerPrincipal *>::Add(BamoSimpleHapticsControllerPrincipal *)
0x18009fc4a  mov     rcx, [rbp+20h]; this
0x18009fc4e  test    eax, eax
0x18009fc50  jns     short loc_18009FC67
0x18009fc52  mov     r9d, eax; char *
0x18009fc55  lea     r8, aOnecoreuapWind_26; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009fc5c  mov     edx, 101h; void *
0x18009fc61  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009fc67  mov     [rbp+var_38], 0
0x18009fc6f  lea     rdx, [rbp+var_18]
0x18009fc73  lea     rcx, [rbp+var_38]
0x18009fc77  call    ?start@?$tip_test@V?$merged_data@U_tip_HapticMouseAttachedTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HapticMouseAttachedTipTest_attributes,tip2::test_data_basic>>::start(void)
0x18009fc7c  mov     rcx, [rbp+var_38]
0x18009fc80  test    rcx, rcx
0x18009fc83  jz      short loc_18009FC8E
0x18009fc85  add     rcx, 8
0x18009fc89  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::complete_without_lock(void)
0x18009fc8e  cmp     qword ptr [rdi+18h], 7
0x18009fc93  jbe     short loc_18009FC98
0x18009fc95  mov     rdi, [rdi]
0x18009fc98  mov     rdx, rdi; unsigned __int16 *
0x18009fc9b  mov     ecx, 2; enum tagINPUT_MESSAGE_DEVICE_TYPE
0x18009fca0  call    ?HapticDeviceAdded@Haptics@InputTraceLogging@@SAXW4tagINPUT_MESSAGE_DEVICE_TYPE@@PEBG@Z; InputTraceLogging::Haptics::HapticDeviceAdded(tagINPUT_MESSAGE_DEVICE_TYPE,ushort const *)
0x18009fca5  lea     rcx, [rbp+var_38]
0x18009fca9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_HapticPenAttachedTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HapticPenAttachedTipTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HapticPenAttachedTipTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x18009fcae  xor     ebx, ebx
0x18009fcb0  lea     rcx, [rbp+var_20]
0x18009fcb4  call    ??1?$com_ptr_t@VBamoList_SimpleHapticsControllerPrincipal_Principal@ISMBamos_AutoBamos@Lib@Bamo@Microsoft@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>::~com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>(void)
0x18009fcb9  nop
0x18009fcba  lea     rcx, [rbp+var_28]
0x18009fcbe  call    ??1?$com_ptr_t@VBamoList_SimpleHapticsControllerPrincipal_Principal@ISMBamos_AutoBamos@Lib@Bamo@Microsoft@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>::~com_ptr_t<Microsoft::Bamo::Lib::ISMBamos_AutoBamos::BamoList_SimpleHapticsControllerPrincipal_Principal,wil::err_returncode_policy>(void)
0x18009fcc3  nop
0x18009fcc4  lea     rcx, [rbp+PreparsedData]
0x18009fcc8  call    ??1?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(void)
0x18009fccd  nop
0x18009fcce  lea     rcx, [rbp+var_30]
0x18009fcd2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009fcd7  mov     eax, ebx
0x18009fcd9  jmp     short loc_18009FCF3
0x18009fcdb  lea     rcx, [rbp+PreparsedData]
0x18009fcdf  call    ??1?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(void)
0x18009fce4  nop
0x18009fce5  lea     rcx, [rbp+var_30]
0x18009fce9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009fcee  mov     eax, 80004002h
0x18009fcf3  add     rsp, 78h
0x18009fcf7  pop     rdi
0x18009fcf8  pop     rsi
0x18009fcf9  pop     rbx
0x18009fcfa  pop     rbp
0x18009fcfb  retn
```
