# NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18001ce64`
- end: `0x18001cf45`
- name: `?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z`
- size: `225`
- prototype: `__int64 __fastcall(NgcUtils *this, const WCHAR *, const unsigned __int16 *, const WCHAR *, const unsigned __int16 *dwType, BYTE *lpData, unsigned __int8 *cbData)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010de8`
- `0x180014490`

## callees

- `0x180008c74`
- `0x18000cc58`
- `0x18000ef9c`
- `0x18001ce64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cf05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cf05`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cec9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cec9`

## string_xrefs

- `0x18001cf14`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcUtils::SetRegistryValue(
        NgcUtils *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        const unsigned __int16 *dwType,
        BYTE *lpData,
        unsigned __int8 *cbData)
{
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v9 )
  {
    v10 = 108;
  }
  else
  {
    v9 = RegSetValueExW(hKey, a4, 0, (DWORD)dwType, lpData, (DWORD)cbData);
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_7;
    }
    v10 = 116;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)v9,
          dwOptions);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v11;
}

```

## disassembly

```asm
0x18001ce64  mov     rax, rsp
0x18001ce67  mov     [rax+8], rbx
0x18001ce6b  mov     [rax+18h], r8
0x18001ce6f  push    rdi
0x18001ce70  sub     rsp, 50h
0x18001ce74  mov     rdi, r9
0x18001ce77  mov     rbx, rdx
0x18001ce7a  mov     qword ptr [rax+18h], 0
0x18001ce82  xor     edx, edx
0x18001ce84  lea     rcx, [rax+18h]
0x18001ce88  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ce8d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001ce96  lea     rax, [rsp+58h+hKey]
0x18001ce9b  mov     [rsp+58h+phkResult], rax; phkResult
0x18001cea0  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001cea9  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18001ceb1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001ceb9  xor     r9d, r9d; lpClass
0x18001cebc  xor     r8d, r8d; Reserved
0x18001cebf  mov     rdx, rbx; lpSubKey
0x18001cec2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cec9  call    cs:__imp_RegCreateKeyExW
0x18001cecf  test    eax, eax
0x18001ced1  jz      short loc_18001CEDA
0x18001ced3  mov     edx, 6Ch ; 'l'
0x18001ced8  jmp     short loc_18001CF14
0x18001ceda  mov     eax, [rsp+58h+cbData]
0x18001cee1  mov     [rsp+58h+samDesired], eax; cbData
0x18001cee5  mov     rax, [rsp+58h+lpData]
0x18001ceed  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x18001cef2  mov     r9d, dword ptr [rsp+58h+dwType]; dwType
0x18001cefa  xor     r8d, r8d; Reserved
0x18001cefd  mov     rdx, rdi; lpValueName
0x18001cf00  mov     rcx, [rsp+58h+hKey]; hKey
0x18001cf05  call    cs:__imp_RegSetValueExW
0x18001cf0b  test    eax, eax
0x18001cf0d  jz      short loc_18001CF2C
0x18001cf0f  mov     edx, 74h ; 't'; void *
0x18001cf14  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cf1b  mov     r9d, eax; char *
0x18001cf1e  mov     rcx, [rsp+58h]; this
0x18001cf23  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001cf28  mov     ebx, eax
0x18001cf2a  jmp     short loc_18001CF2E
0x18001cf2c  xor     ebx, ebx
0x18001cf2e  lea     rcx, [rsp+58h+hKey]
0x18001cf33  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001cf38  mov     eax, ebx
0x18001cf3a  mov     rbx, [rsp+58h+arg_0]
0x18001cf3f  add     rsp, 50h
0x18001cf43  pop     rdi
0x18001cf44  retn
```
