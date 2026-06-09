# CloudPCHelpers::IsPhysicalDeviceAccessConfigured(void)

- ea: `0x1800449ec`
- end: `0x180044b23`
- name: `?IsPhysicalDeviceAccessConfigured@CloudPCHelpers@@YA_NXZ`
- size: `311`
- prototype: `bool __fastcall(CloudPCHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800689c8`

## callees

- `0x1800449ec`
- `0x180044b2c`
- `0x18004fb80`
- `0x180069c88`
- `0x18006f2b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180044a90`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180044a90`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044a4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044ad9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044a4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044ad9`

## string_xrefs

- `0x180044ace`: `Software\Microsoft\Windows\BootToCloud\PhysicalDeviceAccess`
- `0x180044ac7`: `PhysicalDeviceAccessConfigured`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CloudPCHelpers::IsPhysicalDeviceAccessConfigured(CloudPCHelpers *this, __int64 a2)
{
  char v2; // bl
  CloudPCHelpers *v3; // rcx
  LSTATUS v4; // eax
  bool v5; // sf
  unsigned int ValueW; // eax
  unsigned int v7; // r8d
  bool v8; // bl
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  HKEY phkResult[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  int pvData; // [rsp+70h] [rbp+18h] BYREF
  int v14; // [rsp+78h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+28h] BYREF
  DWORD v16; // [rsp+88h] [rbp+30h] BYREF

  pvData = 0;
  pcbData = 4;
  v2 = 1;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::GetImpl'::`2'::impl,
    a2);
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\PolicyManager\\current\\Device\\CloudDesktop",
         L"BootToCloudMode",
         0x10u,
         0,
         &pvData,
         &pcbData)
    || pvData != 1 )
  {
    v2 = 0;
  }
  if ( !v2 || !CloudPCHelpers::IsPhysicalDeviceAccessPolicyEnabled(v3) )
    return 0;
  v14 = 0;
  v16 = 4;
  phkResult[0] = 0;
  v4 = RegOpenCurrentUser(0x20019u, phkResult);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( v5 )
  {
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
    return 0;
  }
  ValueW = RegGetValueW(
             phkResult[0],
             L"Software\\Microsoft\\Windows\\BootToCloud\\PhysicalDeviceAccess",
             L"PhysicalDeviceAccessConfigured",
             0x10u,
             0,
             &v14,
             &v16);
  if ( ValueW != 2 )
  {
    if ( !ValueW )
    {
      v8 = v14 != 0;
      goto LABEL_16;
    }
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x82, v7, (const char *)ValueW, pdwType);
    goto LABEL_13;
  }
  v8 = 0;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  return v8;
}

```

## disassembly

```asm
0x1800449ec  push    rbp
0x1800449ee  push    rbx
0x1800449ef  mov     rbp, rsp
0x1800449f2  sub     rsp, 58h
0x1800449f6  mov     [rbp+arg_0], 0
0x1800449fd  mov     [rbp+arg_10], 4
0x180044a04  mov     ebx, 1
0x180044a09  mov     dl, bl
0x180044a0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly> `wil::Feature<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::GetImpl(void)'::`2'::impl
0x180044a12  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044a17  lea     rax, [rbp+arg_10]
0x180044a1b  mov     [rsp+58h+pcbData], rax; pcbData
0x180044a20  lea     rax, [rbp+arg_0]
0x180044a24  mov     [rsp+58h+pvData], rax; pvData
0x180044a29  mov     [rsp+58h+pdwType], 0; pdwType
0x180044a32  lea     r9d, [rbx+0Fh]; dwFlags
0x180044a36  lea     r8, Value; "BootToCloudMode"
0x180044a3d  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\PolicyManager\\cur"...
0x180044a44  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180044a4b  call    cs:__imp_RegGetValueW
0x180044a51  test    eax, eax
0x180044a53  jnz     short loc_180044A5A
0x180044a55  cmp     [rbp+arg_0], ebx
0x180044a58  jz      short loc_180044A5C
0x180044a5a  xor     bl, bl
0x180044a5c  test    bl, bl
0x180044a5e  jz      loc_180044B06
0x180044a64  call    ?IsPhysicalDeviceAccessPolicyEnabled@CloudPCHelpers@@YA_NXZ; CloudPCHelpers::IsPhysicalDeviceAccessPolicyEnabled(void)
0x180044a69  test    al, al
0x180044a6b  jz      loc_180044B06
0x180044a71  mov     [rbp+arg_8], 0
0x180044a78  mov     [rbp+arg_18], 4
0x180044a7f  mov     [rbp+phkResult], 0
0x180044a87  lea     rdx, [rbp+phkResult]; phkResult
0x180044a8b  mov     ecx, 20019h; samDesired
0x180044a90  call    cs:__imp_RegOpenCurrentUser
0x180044a96  test    eax, eax
0x180044a98  jle     short loc_180044AA4
0x180044a9a  movzx   eax, ax
0x180044a9d  or      eax, 80070000h
0x180044aa2  test    eax, eax
0x180044aa4  js      short loc_180044AFD
0x180044aa6  lea     rax, [rbp+arg_18]
0x180044aaa  mov     [rsp+58h+pcbData], rax; pcbData
0x180044aaf  lea     rax, [rbp+arg_8]
0x180044ab3  mov     [rsp+58h+pvData], rax; pvData
0x180044ab8  mov     [rsp+58h+pdwType], 0; unsigned int
0x180044ac1  mov     r9d, 10h; dwFlags
0x180044ac7  lea     r8, aPhysicaldevice; "PhysicalDeviceAccessConfigured"
0x180044ace  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\BootToClo"...
0x180044ad5  mov     rcx, [rbp+phkResult]; hkey
0x180044ad9  call    cs:__imp_RegGetValueW
0x180044adf  cmp     eax, 2
0x180044ae2  jnz     short loc_180044AE8
0x180044ae4  xor     bl, bl
0x180044ae6  jmp     short loc_180044B16
0x180044ae8  test    eax, eax
0x180044aea  jz      short loc_180044B0F
0x180044aec  mov     rcx, [rbp+10h]; this
0x180044af0  mov     r9d, eax; char *
0x180044af3  mov     edx, 82h; void *
0x180044af8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180044afd  lea     rcx, [rbp+phkResult]
0x180044b01  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044b06  xor     al, al
0x180044b08  add     rsp, 58h
0x180044b0c  pop     rbx
0x180044b0d  pop     rbp
0x180044b0e  retn
0x180044b0f  cmp     [rbp+arg_8], 0
0x180044b13  setnz   bl
0x180044b16  lea     rcx, [rbp+phkResult]
0x180044b1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044b1f  mov     al, bl
0x180044b21  jmp     short loc_180044B08
```
