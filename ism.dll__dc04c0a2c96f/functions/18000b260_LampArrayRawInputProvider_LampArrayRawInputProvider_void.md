# LampArrayRawInputProvider::LampArrayRawInputProvider(void)

- ea: `0x18000b260`
- end: `0x18000b427`
- name: `??0LampArrayRawInputProvider@@AEAA@XZ`
- size: `455`
- prototype: `LampArrayRawInputProvider *__fastcall(LampArrayRawInputProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084670`

## callees

- `0x18000b260`
- `0x18000cd64`
- `0x18009e19c`
- `0x1800ae370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b3ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b415`

## pseudocode

```c
LampArrayRawInputProvider *__fastcall LampArrayRawInputProvider::LampArrayRawInputProvider(
        LampArrayRawInputProvider *this)
{
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF

  *((_QWORD *)this + 3) = &RefCountedObject::`vftable';
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &LampArrayRawInputProvider::`vftable'{for `IRawInputProvider'};
  *((_QWORD *)this + 1) = &LampArrayRawInputProvider::`vftable'{for `IRawInputSessionNotify'};
  *((_QWORD *)this + 2) = &LampArrayRawInputProvider::`vftable'{for `IInputFocusListener'};
  *((_QWORD *)this + 3) = &LampArrayRawInputProvider::`vftable'{for `RefCountedObject'};
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 13) = (char *)this + 96;
  *((_QWORD *)this + 12) = (char *)this + 96;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 16) = (char *)this + 120;
  *((_QWORD *)this + 15) = (char *)this + 120;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_BYTE *)this + 184) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 60) = 0;
  *((_QWORD *)this + 29) = (char *)this + 224;
  *((_QWORD *)this + 28) = (char *)this + 224;
  *((_QWORD *)this + 31) = 0;
  *((_DWORD *)this + 68) = 0;
  *((_QWORD *)this + 33) = (char *)this + 256;
  *((_QWORD *)this + 32) = (char *)this + 256;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 36) = (char *)this + 280;
  *((_QWORD *)this + 35) = (char *)this + 280;
  QpcTimeConverter::QpcTimeConverter((LampArrayRawInputProvider *)((char *)this + 304));
  *((_BYTE *)this + 320) = 0;
  *((_QWORD *)this + 41) = -1;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Alloc_sentinel_and_proxy();
  hObject = CreateEventW(0, 0, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)this + 328,
    &hObject);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = CreateEventW(0, 0, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)this + 336,
    &hObject);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return this;
}

```

## disassembly

```asm
0x18000b260  push    rbx
0x18000b262  push    rbp
0x18000b263  push    rsi
0x18000b264  push    rdi
0x18000b265  sub     rsp, 28h
0x18000b269  mov     rdi, rcx
0x18000b26c  lea     rax, ??_7RefCountedObject@@6B@; const RefCountedObject::`vftable'
0x18000b273  mov     [rcx+18h], rax
0x18000b277  mov     dword ptr [rcx+20h], 1
0x18000b27e  lea     rax, ??_7LampArrayRawInputProvider@@6BIRawInputProvider@@@; const LampArrayRawInputProvider::`vftable'{for `IRawInputProvider'}
0x18000b285  mov     [rcx], rax
0x18000b288  lea     rax, ??_7LampArrayRawInputProvider@@6BIRawInputSessionNotify@@@; const LampArrayRawInputProvider::`vftable'{for `IRawInputSessionNotify'}
0x18000b28f  mov     [rcx+8], rax
0x18000b293  lea     rax, ??_7LampArrayRawInputProvider@@6BIInputFocusListener@@@; const LampArrayRawInputProvider::`vftable'{for `IInputFocusListener'}
0x18000b29a  mov     [rcx+10h], rax
0x18000b29e  lea     rax, ??_7LampArrayRawInputProvider@@6BRefCountedObject@@@; const LampArrayRawInputProvider::`vftable'{for `RefCountedObject'}
0x18000b2a5  mov     [rcx+18h], rax
0x18000b2a9  xor     ebp, ebp
0x18000b2ab  mov     [rcx+28h], rbp
0x18000b2af  mov     [rcx+30h], rbp
0x18000b2b3  mov     [rcx+38h], rbp
0x18000b2b7  mov     [rcx+40h], ebp
0x18000b2ba  lea     rax, [rcx+48h]
0x18000b2be  mov     [rax+10h], ebp
0x18000b2c1  mov     [rax+8], rax
0x18000b2c5  mov     [rax], rax
0x18000b2c8  lea     rax, [rcx+60h]
0x18000b2cc  mov     [rax+10h], ebp
0x18000b2cf  mov     [rax+8], rax
0x18000b2d3  mov     [rax], rax
0x18000b2d6  lea     rax, [rcx+78h]
0x18000b2da  mov     [rax+10h], ebp
0x18000b2dd  mov     [rax+8], rax
0x18000b2e1  mov     [rax], rax
0x18000b2e4  xor     eax, eax
0x18000b2e6  mov     [rcx+90h], rax
0x18000b2ed  mov     [rcx+98h], rax
0x18000b2f4  mov     [rcx+0A0h], rax
0x18000b2fb  mov     [rcx+0A8h], rbp
0x18000b302  mov     [rcx+0B0h], rbp
0x18000b309  mov     [rcx+0B8h], bpl
0x18000b310  mov     [rcx+0C0h], rbp
0x18000b317  mov     [rcx+0C8h], rbp
0x18000b31e  mov     [rcx+0D0h], rbp
0x18000b325  mov     [rcx+0D8h], rbp
0x18000b32c  lea     rax, [rcx+0E0h]
0x18000b333  mov     [rax+10h], ebp
0x18000b336  mov     [rax+8], rax
0x18000b33a  mov     [rax], rax
0x18000b33d  xor     eax, eax
0x18000b33f  mov     [rcx+0F8h], rax
0x18000b346  lea     rax, [rcx+100h]
0x18000b34d  mov     [rax+10h], ebp
0x18000b350  mov     [rax+8], rax
0x18000b354  mov     [rax], rax
0x18000b357  lea     rax, [rcx+118h]
0x18000b35e  mov     [rax+10h], ebp
0x18000b361  mov     [rax+8], rax
0x18000b365  mov     [rax], rax
0x18000b368  add     rcx, 130h; this
0x18000b36f  call    ??0QpcTimeConverter@@QEAA@XZ; QpcTimeConverter::QpcTimeConverter(void)
0x18000b374  mov     [rdi+140h], bpl
0x18000b37b  lea     rbx, [rdi+148h]
0x18000b382  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000b389  lea     rsi, [rdi+150h]
0x18000b390  mov     [rsi], rbp
0x18000b393  mov     [rdi+158h], rbp
0x18000b39a  lea     rcx, [rdi+170h]
0x18000b3a1  mov     [rcx], rbp
0x18000b3a4  mov     [rcx+8], rbp
0x18000b3a8  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000b3ad  xor     r9d, r9d; lpName
0x18000b3b0  xor     r8d, r8d; bInitialState
0x18000b3b3  xor     edx, edx; bManualReset
0x18000b3b5  xor     ecx, ecx; lpEventAttributes
0x18000b3b7  call    cs:__imp_CreateEventW
0x18000b3bd  mov     [rsp+48h+hObject], rax
0x18000b3c2  lea     rdx, [rsp+48h+hObject]
0x18000b3c7  mov     rcx, rbx
0x18000b3ca  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000b3cf  mov     rcx, [rsp+48h+hObject]; hObject
0x18000b3d4  lea     rax, [rcx-1]
0x18000b3d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b3dc  ja      short loc_18000B3E4
0x18000b3de  call    cs:__imp_CloseHandle
0x18000b3e4  xor     r9d, r9d; lpName
0x18000b3e7  xor     r8d, r8d; bInitialState
0x18000b3ea  xor     edx, edx; bManualReset
0x18000b3ec  xor     ecx, ecx; lpEventAttributes
0x18000b3ee  call    cs:__imp_CreateEventW
0x18000b3f4  mov     [rsp+48h+hObject], rax
0x18000b3f9  lea     rdx, [rsp+48h+hObject]
0x18000b3fe  mov     rcx, rsi
0x18000b401  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000b406  mov     rcx, [rsp+48h+hObject]; hObject
0x18000b40b  lea     rax, [rcx-1]
0x18000b40f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b413  ja      short loc_18000B41B
0x18000b415  call    cs:__imp_CloseHandle
0x18000b41b  mov     rax, rdi
0x18000b41e  add     rsp, 28h
0x18000b422  pop     rdi
0x18000b423  pop     rsi
0x18000b424  pop     rbp
0x18000b425  pop     rbx
0x18000b426  retn
```
