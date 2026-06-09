# GetDeviceManagementConfigInfo

- ea: `0x18000d940`
- end: `0x18000da4d`
- name: `GetDeviceManagementConfigInfo`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006138`
- `0x18000b0f4`
- `0x18000d940`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000d95a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000d95a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000da10`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000da10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da2e`

## string_xrefs

- `0x18000d9a7`: `onecoreuap\admin\enterprisemgmt\enrollactivities\mdmregistration\dllmain.cpp`
- `0x18000d9eb`: `ConfigInfo`

## pseudocode

```c
__int64 __fastcall GetDeviceManagementConfigInfo(__int64 a1, DWORD *a2, void *a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  HLOCAL v10; // rbx
  LSTATUS ValueW; // eax
  unsigned int v12; // edi
  int pdwType; // [rsp+20h] [rbp-38h]
  const wchar_t *v14; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v16 = a1;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  hMem = 0;
  v6 = L"OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider\\";
  if ( !IsStateSeparationEnabled )
    v6 = L"Software\\Microsoft\\DeviceManageabilityCSP\\Provider\\";
  v14 = v6;
  v7 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const *>(
         &hMem,
         &v14,
         &v16);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = hMem;
    if ( hMem )
    {
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem, L"ConfigInfo", 0x10002u, 0, a3, a2);
      v12 = ValueW;
      if ( ValueW > 0 )
        v12 = (unsigned __int16)ValueW | 0x80070000;
      LocalFree(v10);
      return v12;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\mdmregistration\\dllmain.cpp",
      (const char *)(unsigned int)v7,
      pdwType);
    if ( hMem )
      LocalFree(hMem);
    return v8;
  }
}

```

## disassembly

```asm
0x18000d940  mov     [rsp+arg_8], rbx
0x18000d945  mov     [rsp+arg_10], rsi
0x18000d94a  mov     [rsp+arg_0], rcx
0x18000d94f  push    rdi
0x18000d950  sub     rsp, 50h
0x18000d954  mov     rdi, r8
0x18000d957  mov     rsi, rdx
0x18000d95a  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000d961  nop     dword ptr [rax+rax+00h]
0x18000d966  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\DeviceManageabilit"...
0x18000d96d  mov     [rsp+58h+hMem], 0
0x18000d976  test    al, al
0x18000d978  lea     rcx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\DeviceMana"...
0x18000d97f  lea     r8, [rsp+58h+arg_0]
0x18000d984  cmovz   rcx, rdx
0x18000d988  lea     rdx, [rsp+58h+var_18]
0x18000d98d  mov     [rsp+58h+var_18], rcx
0x18000d992  lea     rcx, [rsp+58h+hMem]
0x18000d997  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const * const &)
0x18000d99c  mov     ebx, eax
0x18000d99e  test    eax, eax
0x18000d9a0  jns     short loc_18000D9D5
0x18000d9a2  mov     rcx, [rsp+58h]; this
0x18000d9a7  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18000d9ae  mov     r9d, eax; char *
0x18000d9b1  mov     edx, 3EEh; void *
0x18000d9b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9bb  mov     rcx, [rsp+58h+hMem]; hMem
0x18000d9c0  test    rcx, rcx
0x18000d9c3  jz      short loc_18000D9D1
0x18000d9c5  call    cs:__imp_LocalFree
0x18000d9cc  nop     dword ptr [rax+rax+00h]
0x18000d9d1  mov     eax, ebx
0x18000d9d3  jmp     short loc_18000DA3C
0x18000d9d5  mov     rbx, [rsp+58h+hMem]
0x18000d9da  test    rbx, rbx
0x18000d9dd  jnz     short loc_18000D9E6
0x18000d9df  mov     eax, 8007000Eh
0x18000d9e4  jmp     short loc_18000DA3C
0x18000d9e6  mov     [rsp+58h+pcbData], rsi; pcbData
0x18000d9eb  lea     r8, ValueName; "ConfigInfo"
0x18000d9f2  mov     [rsp+58h+pvData], rdi; pvData
0x18000d9f7  mov     r9d, 10002h; dwFlags
0x18000d9fd  mov     rdx, rbx; lpSubKey
0x18000da00  mov     [rsp+58h+pdwType], 0; pdwType
0x18000da09  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000da10  call    cs:__imp_RegGetValueW
0x18000da17  nop     dword ptr [rax+rax+00h]
0x18000da1c  mov     edi, eax
0x18000da1e  test    eax, eax
0x18000da20  jle     short loc_18000DA2B
0x18000da22  movzx   edi, ax
0x18000da25  or      edi, 80070000h
0x18000da2b  mov     rcx, rbx; hMem
0x18000da2e  call    cs:__imp_LocalFree
0x18000da35  nop     dword ptr [rax+rax+00h]
0x18000da3a  mov     eax, edi
0x18000da3c  mov     rbx, [rsp+58h+arg_8]
0x18000da41  mov     rsi, [rsp+58h+arg_10]
0x18000da46  add     rsp, 50h
0x18000da4a  pop     rdi
0x18000da4b  retn
```
