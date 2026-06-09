# PTPProcessor::CheckForHapticTouchpadArrival(DeviceInfo const *)

- ea: `0x18009f680`
- end: `0x18009f7c3`
- name: `?CheckForHapticTouchpadArrival@PTPProcessor@@AEAAXPEBUDeviceInfo@@@Z`
- size: `323`
- prototype: `void __fastcall(PTPProcessor *__hidden this, const struct DeviceInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1801bd0a0`

## callees

- `0x180012ee0`
- `0x18009326c`
- `0x18009329c`
- `0x18009f680`
- `0x18009fd10`
- `0x18009fd34`
- `0x1800f0acc`
- `0x18010f9ec`
- `0x180190ff4`
- `0x1801915a0`
- `0x18019c020`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009f6c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009f6c4`
- `HID!HidD_GetPreparsedData` at `0x18009f6eb`
- `HID!HidD_GetPreparsedData` at `0x18009f6eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PTPProcessor::CheckForHapticTouchpadArrival(PTPProcessor *this, const WCHAR *a2)
{
  char *FileW; // rax
  struct InputSystemServerConnection *BamoServerConnection; // rsi
  __int64 v5; // rax
  PTPProcessor *v6; // rbx
  HapticDeviceManager *v7; // rax
  PTPProcessor *v8; // [rsp+70h] [rbp+28h] BYREF
  PHIDP_PREPARSED_DATA PreparsedData; // [rsp+78h] [rbp+30h] BYREF
  char *v10; // [rsp+80h] [rbp+38h] BYREF
  HapticDeviceManager *v11; // [rsp+88h] [rbp+40h]

  v8 = this;
  if ( !*((_BYTE *)a2 + 12) )
  {
    FileW = (char *)CreateFileW(a2 + 38, 0x40000000u, 3u, 0, 3u, 0, 0);
    v10 = FileW;
    PreparsedData = 0;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && HidD_GetPreparsedData(FileW, &PreparsedData)
      && CompliantHapticInterface::HasManualTriggerHaptic(PreparsedData) )
    {
      BamoServerConnection = ISMStatics::GetBamoServerConnection();
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)BamoServerConnection + 31) + 8LL) + 168LL))(*((_QWORD *)BamoServerConnection + 31) + 8LL);
      wil::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>(
        &v8,
        v5);
      v6 = v8;
      if ( !v8 )
      {
        v11 = (HapticDeviceManager *)operator new(0xA0u);
        v7 = HapticDeviceManager::HapticDeviceManager(v11, BamoServerConnection);
        wil::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>::operator=(&v8, v7);
        v6 = v8;
        (*(void (__fastcall **)(__int64, PTPProcessor *))(*(_QWORD *)(*((_QWORD *)BamoServerConnection + 31) + 8LL)
                                                        + 176LL))(
          *((_QWORD *)BamoServerConnection + 31) + 8LL,
          v8);
      }
      HapticDeviceManager::AttachHapticTouchpad(v6, a2, &v10, &PreparsedData);
      wil::com_ptr_t<MPCManager,wil::err_exception_policy>::~com_ptr_t<MPCManager,wil::err_exception_policy>(&v8);
    }
    wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(&PreparsedData);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  }
}

```

## disassembly

```asm
0x18009f680  mov     rax, rsp
0x18009f683  mov     [rax+8], rcx
0x18009f687  push    rbp
0x18009f688  push    rbx
0x18009f689  push    rsi
0x18009f68a  push    rdi
0x18009f68b  mov     rbp, rsp
0x18009f68e  sub     rsp, 48h
0x18009f692  mov     rdi, rdx
0x18009f695  cmp     byte ptr [rdx+0Ch], 0
0x18009f699  jnz     loc_18009F7BA
0x18009f69f  lea     rcx, [rdx+4Ch]; lpFileName
0x18009f6a3  mov     qword ptr [rax-38h], 0
0x18009f6ab  mov     dword ptr [rax-40h], 0
0x18009f6b2  mov     r8d, 3; dwShareMode
0x18009f6b8  mov     [rax-48h], r8d
0x18009f6bc  xor     r9d, r9d; lpSecurityAttributes
0x18009f6bf  mov     edx, 40000000h; dwDesiredAccess
0x18009f6c4  call    cs:__imp_CreateFileW
0x18009f6ca  mov     [rbp+arg_10], rax
0x18009f6ce  mov     [rbp+PreparsedData], 0
0x18009f6d6  lea     rcx, [rax-1]
0x18009f6da  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18009f6de  ja      loc_18009F7A7
0x18009f6e4  lea     rdx, [rbp+PreparsedData]; PreparsedData
0x18009f6e8  mov     rcx, rax; HidDeviceObject
0x18009f6eb  call    cs:__imp_HidD_GetPreparsedData
0x18009f6f1  test    al, al
0x18009f6f3  jz      loc_18009F7A7
0x18009f6f9  mov     rcx, [rbp+PreparsedData]; struct _HIDP_PREPARSED_DATA *
0x18009f6fd  call    ?HasManualTriggerHaptic@CompliantHapticInterface@@SA_NPEAU_HIDP_PREPARSED_DATA@@@Z; CompliantHapticInterface::HasManualTriggerHaptic(_HIDP_PREPARSED_DATA *)
0x18009f702  test    al, al
0x18009f704  jz      loc_18009F7A7
0x18009f70a  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18009f70f  mov     rsi, rax
0x18009f712  mov     rcx, [rax+0F8h]
0x18009f719  add     rcx, 8
0x18009f71d  mov     rdx, [rcx]
0x18009f720  mov     rax, [rdx+0A8h]
0x18009f727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f72c  mov     rdx, rax
0x18009f72f  lea     rcx, [rbp+arg_0]
0x18009f733  call    ??0?$com_ptr_t@VHapticDeviceManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVHapticDeviceManager@@@Z; wil::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>(HapticDeviceManager *)
0x18009f738  nop
0x18009f739  mov     rbx, [rbp+arg_0]
0x18009f73d  test    rbx, rbx
0x18009f740  jnz     short loc_18009F789
0x18009f742  mov     ecx, 0A0h; Size
0x18009f747  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f74c  mov     [rbp+arg_18], rax
0x18009f750  mov     rdx, rsi; struct ISMBamos_AutoBamos::BamoConnection *
0x18009f753  mov     rcx, rax; this
0x18009f756  call    ??0HapticDeviceManager@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@@Z; HapticDeviceManager::HapticDeviceManager(ISMBamos_AutoBamos::BamoConnection *)
0x18009f75b  nop
0x18009f75c  mov     rdx, rax
0x18009f75f  lea     rcx, [rbp+arg_0]
0x18009f763  call    ??4?$com_ptr_t@VHapticDeviceManager@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAVHapticDeviceManager@@@Z; wil::com_ptr_t<HapticDeviceManager,wil::err_returncode_policy>::operator=(HapticDeviceManager *)
0x18009f768  mov     rcx, [rsi+0F8h]
0x18009f76f  add     rcx, 8
0x18009f773  mov     rax, [rcx]
0x18009f776  mov     rbx, [rbp+arg_0]
0x18009f77a  mov     rdx, rbx
0x18009f77d  mov     rax, [rax+0B0h]
0x18009f784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f789  lea     r9, [rbp+PreparsedData]
0x18009f78d  lea     r8, [rbp+arg_10]
0x18009f791  mov     rdx, rdi
0x18009f794  mov     rcx, rbx
0x18009f797  call    ?AttachHapticTouchpad@HapticDeviceManager@@QEAAJPEBULegacyDeviceInfo@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@4@@Z; HapticDeviceManager::AttachHapticTouchpad(LegacyDeviceInfo const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>> &&)
0x18009f79c  nop
0x18009f79d  lea     rcx, [rbp+arg_0]
0x18009f7a1  call    ??1?$com_ptr_t@VMPCManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<MPCManager,wil::err_exception_policy>::~com_ptr_t<MPCManager,wil::err_exception_policy>(void)
0x18009f7a6  nop
0x18009f7a7  lea     rcx, [rbp+PreparsedData]
0x18009f7ab  call    ??1?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(void)
0x18009f7b0  nop
0x18009f7b1  lea     rcx, [rbp+arg_10]
0x18009f7b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009f7ba  add     rsp, 48h
0x18009f7be  pop     rdi
0x18009f7bf  pop     rsi
0x18009f7c0  pop     rbx
0x18009f7c1  pop     rbp
0x18009f7c2  retn
```
