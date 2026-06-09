# MDMWinsOverGP_HandleRemainingConfigurations(void)

- ea: `0x180010fec`
- end: `0x1800111a1`
- name: `?MDMWinsOverGP_HandleRemainingConfigurations@@YAJXZ`
- size: `437`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006ef30`

## callees

- `0x1800071c0`
- `0x180010fec`
- `0x1800118f8`
- `0x180011938`
- `0x18002e1a0`
- `0x18003b068`
- `0x1800760a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800110df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800110df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011041`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011041`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001112b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001112b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 MDMWinsOverGP_HandleRemainingConfigurations(void)
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  unsigned int v2; // ebx
  __int64 v4; // r8
  int v5; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-19h]
  HKEY hKey; // [rsp+60h] [rbp+27h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp+2Fh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_szMDMWinsOverGpBlockRoot, 0, 1u, &hKey);
  if ( v0 != 2 )
  {
    if ( v0 )
    {
      v1 = 1577;
LABEL_4:
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v1,
             (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
             (const char *)v0,
             phkResult);
LABEL_5:
      if ( hKey )
        RegCloseKey(hKey);
      return v2;
    }
    cSubKeys = 0;
    v0 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v0 )
    {
      v1 = 1594;
      goto LABEL_4;
    }
    if ( cSubKeys )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
          (const EVENT_DESCRIPTOR *)RecordsFoundForReEvaluation,
          v4,
          1u,
          &v9);
      v5 = MdmWinsOverGp_UnblockForGp();
      v2 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x646,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
          (const char *)(unsigned int)v5,
          phkResult);
        goto LABEL_5;
      }
    }
    else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
        (const EVENT_DESCRIPTOR *)NoRecordsForReEvaluation,
        v4,
        1u,
        &v9);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180010fec  mov     [rsp-8+arg_0], rbx
0x180010ff1  push    rbp
0x180010ff2  lea     rbp, [rsp-57h]
0x180010ff7  sub     rsp, 90h
0x180010ffe  mov     rax, cs:__security_cookie
0x180011005  xor     rax, rsp
0x180011008  mov     [rbp+57h+var_10], rax
0x18001100c  mov     [rbp+57h+hKey], 0
0x180011014  xor     edx, edx
0x180011016  lea     rcx, [rbp+57h+hKey]
0x18001101a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001101f  lea     rax, [rbp+57h+hKey]
0x180011023  mov     [rsp+90h+phkResult], rax; unsigned int
0x180011028  mov     ebx, 1
0x18001102d  mov     r9d, ebx; samDesired
0x180011030  xor     r8d, r8d; ulOptions
0x180011033  mov     rdx, cs:?c_szMDMWinsOverGpBlockRoot@@3PEBGEB; lpSubKey
0x18001103a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011041  call    cs:__imp_RegOpenKeyExW
0x180011047  cmp     eax, 2
0x18001104a  jz      loc_180011122
0x180011050  test    eax, eax
0x180011052  jz      short loc_180011084
0x180011054  mov     edx, 629h; void *
0x180011059  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x180011060  mov     r9d, eax; char *
0x180011063  mov     rcx, [rbp+5Fh]; this
0x180011067  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001106c  mov     ebx, eax
0x18001106e  mov     rcx, [rbp+57h+hKey]; hKey
0x180011072  test    rcx, rcx
0x180011075  jz      short loc_18001107D
0x180011077  call    cs:__imp_RegCloseKey
0x18001107d  mov     eax, ebx
0x18001107f  jmp     loc_180011133
0x180011084  mov     [rbp+57h+cSubKeys], 0
0x18001108b  mov     [rsp+90h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180011094  mov     [rsp+90h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18001109d  mov     [rsp+90h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800110a6  mov     [rsp+90h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800110af  mov     [rsp+90h+lpcValues], 0; lpcValues
0x1800110b8  mov     [rsp+90h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800110c1  mov     [rsp+90h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800110ca  lea     rax, [rbp+57h+cSubKeys]
0x1800110ce  mov     [rsp+90h+phkResult], rax; lpcSubKeys
0x1800110d3  xor     r9d, r9d; lpReserved
0x1800110d6  xor     r8d, r8d; lpcchClass
0x1800110d9  xor     edx, edx; lpClass
0x1800110db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800110df  call    cs:__imp_RegQueryInfoKeyW
0x1800110e5  test    eax, eax
0x1800110e7  jz      short loc_1800110F3
0x1800110e9  mov     edx, 63Ah
0x1800110ee  jmp     loc_180011059
0x1800110f3  cmp     [rbp+57h+cSubKeys], 0
0x1800110f7  jnz     short loc_180011150
0x1800110f9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x180011100  jz      short loc_180011122
0x180011102  lea     rax, [rbp+57h+var_20]
0x180011106  mov     [rsp+90h+phkResult], rax
0x18001110b  mov     r9d, ebx
0x18001110e  lea     rdx, NoRecordsForReEvaluation
0x180011115  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18001111c  call    McGenEventWrite_EventWriteTransfer
0x180011121  nop
0x180011122  mov     rcx, [rbp+57h+hKey]; hKey
0x180011126  test    rcx, rcx
0x180011129  jz      short loc_180011131
0x18001112b  call    cs:__imp_RegCloseKey
0x180011131  xor     eax, eax
0x180011133  mov     rcx, [rbp+57h+var_10]
0x180011137  xor     rcx, rsp; StackCookie
0x18001113a  call    __security_check_cookie
0x18001113f  mov     rbx, [rsp+90h+arg_0]
0x180011147  add     rsp, 90h
0x18001114e  pop     rbp
0x18001114f  retn
0x180011150  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x180011157  jz      short loc_180011178
0x180011159  lea     rax, [rbp+57h+var_20]
0x18001115d  mov     [rsp+90h+phkResult], rax; int
0x180011162  mov     r9d, ebx
0x180011165  lea     rdx, RecordsFoundForReEvaluation
0x18001116c  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180011173  call    McGenEventWrite_EventWriteTransfer
0x180011178  call    ?MdmWinsOverGp_UnblockForGp@@YAJH@Z; MdmWinsOverGp_UnblockForGp(int)
0x18001117d  mov     ebx, eax
0x18001117f  test    eax, eax
0x180011181  jns     short loc_180011122
0x180011183  mov     rcx, [rbp+5Fh]; this
0x180011187  mov     r9d, eax; char *
0x18001118a  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x180011191  mov     edx, 646h; void *
0x180011196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001119b  jmp     loc_18001106E
```
