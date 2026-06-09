# NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18002336c`
- end: `0x18002344e`
- name: `?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z`
- size: `226`
- prototype: `__int64 __fastcall(NgcUtils *this, const WCHAR *, struct _SECURITY_ATTRIBUTES *, const WCHAR *, const unsigned __int16 *dwType, BYTE *lpData, unsigned __int8 *cbData)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015410`
- `0x180018eec`
- `0x18001b0b4`

## callees

- `0x1800136b0`
- `0x1800153f0`
- `0x18001737c`
- `0x18002336c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023409`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023409`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233cd`

## string_xrefs

- `0x180023418`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NgcUtils::SetRegistryValue(
        NgcUtils *this,
        const WCHAR *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        const WCHAR *a4,
        const unsigned __int16 *dwType,
        BYTE *lpData,
        unsigned __int8 *cbData)
{
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x2001Fu, a3, phkResult, 0);
  if ( Key )
  {
    v12 = 108;
  }
  else
  {
    Key = RegSetValueExW(hKey, a4, 0, (DWORD)dwType, lpData, (DWORD)cbData);
    if ( !Key )
    {
      v13 = 0;
      goto LABEL_7;
    }
    v12 = 116;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)Key,
          dwOptions);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v13;
}

```

## disassembly

```asm
0x18002336c  mov     rax, rsp
0x18002336f  mov     [rax+10h], rbx
0x180023373  mov     [rax+18h], rsi
0x180023377  mov     [rax+8], rcx
0x18002337b  push    rdi
0x18002337c  sub     rsp, 50h
0x180023380  mov     rsi, r9
0x180023383  mov     rbx, r8
0x180023386  mov     rdi, rdx
0x180023389  mov     qword ptr [rax+8], 0
0x180023391  lea     rcx, [rax+8]
0x180023395  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18002339a  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800233a3  mov     [rsp+58h+phkResult], rax; phkResult
0x1800233a8  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800233ad  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800233b5  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800233bd  xor     r9d, r9d; lpClass
0x1800233c0  xor     r8d, r8d; Reserved
0x1800233c3  mov     rdx, rdi; lpSubKey
0x1800233c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800233cd  call    cs:__imp_RegCreateKeyExW
0x1800233d3  test    eax, eax
0x1800233d5  jz      short loc_1800233DE
0x1800233d7  mov     edx, 6Ch ; 'l'
0x1800233dc  jmp     short loc_180023418
0x1800233de  mov     eax, [rsp+58h+cbData]
0x1800233e5  mov     [rsp+58h+samDesired], eax; cbData
0x1800233e9  mov     rax, [rsp+58h+lpData]
0x1800233f1  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x1800233f6  mov     r9d, dword ptr [rsp+58h+dwType]; dwType
0x1800233fe  xor     r8d, r8d; Reserved
0x180023401  mov     rdx, rsi; lpValueName
0x180023404  mov     rcx, [rsp+58h+hKey]; hKey
0x180023409  call    cs:__imp_RegSetValueExW
0x18002340f  test    eax, eax
0x180023411  jz      short loc_180023430
0x180023413  mov     edx, 74h ; 't'; void *
0x180023418  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002341f  mov     r9d, eax; char *
0x180023422  mov     rcx, [rsp+58h]; this
0x180023427  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002342c  mov     ebx, eax
0x18002342e  jmp     short loc_180023432
0x180023430  xor     ebx, ebx
0x180023432  lea     rcx, [rsp+58h+hKey]
0x180023437  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002343c  mov     eax, ebx
0x18002343e  mov     rbx, [rsp+58h+arg_8]
0x180023443  mov     rsi, [rsp+58h+arg_10]
0x180023448  add     rsp, 50h
0x18002344c  pop     rdi
0x18002344d  retn
```
