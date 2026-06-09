# SetDeviceManagementConfigInfo

- ea: `0x180013610`
- end: `0x18001378a`
- name: `SetDeviceManagementConfigInfo`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006138`
- `0x18000b0f4`
- `0x180013610`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180013625`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180013625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001375c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001375c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800136db`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800136db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013688`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013688`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013770`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013738`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013738`

## string_xrefs

- `0x18001366b`: `onecoreuap\admin\enterprisemgmt\enrollactivities\mdmregistration\dllmain.cpp`
- `0x1800136f1`: `onecoreuap\admin\enterprisemgmt\enrollactivities\mdmregistration\dllmain.cpp`
- `0x180013724`: `ConfigInfo`

## pseudocode

```c
__int64 __fastcall SetDeviceManagementConfigInfo(__int64 a1, _WORD *a2)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  HLOCAL v8; // rbx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  LSTATUS v12; // eax
  int dwOptions; // [rsp+20h] [rbp-40h]
  int dwOptionsa; // [rsp+20h] [rbp-40h]
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v18; // [rsp+90h] [rbp+30h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  v18 = a1;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  hMem = 0;
  v4 = L"OSData\\Software\\Microsoft\\DeviceManageabilityCSP\\Provider\\";
  if ( !IsStateSeparationEnabled )
    v4 = L"Software\\Microsoft\\DeviceManageabilityCSP\\Provider\\";
  v16 = v4;
  v5 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short const *>(
         &hMem,
         &v16,
         &v18);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = hMem;
    dwDisposition = 0;
    hKey = 0;
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem, 0, 0, 0, 0x102u, 0, &hKey, &dwDisposition);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      v12 = RegSetKeyValueW(hKey, 0, L"ConfigInfo", 1u, a2, 2 * v11 + 2);
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x411,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\mdmregistration\\dllmain.cpp",
        (const char *)(unsigned int)v9,
        dwOptionsa);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v8 )
      LocalFree(v8);
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\mdmregistration\\dllmain.cpp",
      (const char *)(unsigned int)v5,
      dwOptions);
    if ( hMem )
      LocalFree(hMem);
    return v6;
  }
}

```

## disassembly

```asm
0x180013610  mov     [rsp-28h+arg_0], rcx
0x180013615  push    rbp
0x180013616  push    rbx
0x180013617  push    rsi
0x180013618  push    rdi
0x180013619  push    r14
0x18001361b  mov     rbp, rsp
0x18001361e  sub     rsp, 60h
0x180013622  mov     rsi, rdx
0x180013625  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001362c  nop     dword ptr [rax+rax+00h]
0x180013631  xor     r14d, r14d
0x180013634  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\DeviceManageabilit"...
0x18001363b  test    al, al
0x18001363d  mov     [rbp+hMem], r14
0x180013641  lea     rcx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\DeviceMana"...
0x180013648  cmovz   rcx, rdx
0x18001364c  lea     r8, [rbp+arg_0]
0x180013650  mov     [rbp+var_8], rcx
0x180013654  lea     rdx, [rbp+var_8]
0x180013658  lea     rcx, [rbp+hMem]
0x18001365c  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const * const &)
0x180013661  mov     ebx, eax
0x180013663  test    eax, eax
0x180013665  jns     short loc_18001369B
0x180013667  mov     rcx, [rbp+28h]; this
0x18001366b  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180013672  mov     r9d, eax; char *
0x180013675  mov     edx, 40Eh; void *
0x18001367a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001367f  mov     rcx, [rbp+hMem]; hMem
0x180013683  test    rcx, rcx
0x180013686  jz      short loc_180013694
0x180013688  call    cs:__imp_LocalFree
0x18001368f  nop     dword ptr [rax+rax+00h]
0x180013694  mov     eax, ebx
0x180013696  jmp     loc_18001377E
0x18001369b  mov     rbx, [rbp+hMem]
0x18001369f  lea     rax, [rbp+dwDisposition]
0x1800136a3  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800136a8  xor     r9d, r9d; lpClass
0x1800136ab  lea     rax, [rbp+hKey]
0x1800136af  mov     [rbp+dwDisposition], r14d
0x1800136b3  mov     [rsp+60h+phkResult], rax; phkResult
0x1800136b8  xor     r8d, r8d; Reserved
0x1800136bb  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800136c0  mov     rdx, rbx; lpSubKey
0x1800136c3  mov     [rsp+60h+samDesired], 102h; samDesired
0x1800136cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800136d2  mov     [rsp+60h+dwOptions], r14d; int
0x1800136d7  mov     [rbp+hKey], r14
0x1800136db  call    cs:__imp_RegCreateKeyExW
0x1800136e2  nop     dword ptr [rax+rax+00h]
0x1800136e7  mov     edi, eax
0x1800136e9  test    eax, eax
0x1800136eb  jns     short loc_180013707
0x1800136ed  mov     rcx, [rbp+28h]; this
0x1800136f1  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800136f8  mov     r9d, eax; char *
0x1800136fb  mov     edx, 411h; void *
0x180013700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013705  jmp     short loc_180013753
0x180013707  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001370b  inc     rax
0x18001370e  cmp     [rsi+rax*2], r14w
0x180013713  jnz     short loc_18001370B
0x180013715  mov     rcx, [rbp+hKey]; hKey
0x180013719  lea     eax, ds:2[rax*2]
0x180013720  mov     [rsp+60h+samDesired], eax; cbData
0x180013724  lea     r8, ValueName; "ConfigInfo"
0x18001372b  mov     r9d, 1; dwType
0x180013731  mov     qword ptr [rsp+60h+dwOptions], rsi; lpData
0x180013736  xor     edx, edx; lpSubKey
0x180013738  call    cs:__imp_RegSetKeyValueW
0x18001373f  nop     dword ptr [rax+rax+00h]
0x180013744  mov     edi, eax
0x180013746  test    eax, eax
0x180013748  jle     short loc_180013753
0x18001374a  movzx   edi, ax
0x18001374d  or      edi, 80070000h
0x180013753  mov     rcx, [rbp+hKey]; hKey
0x180013757  test    rcx, rcx
0x18001375a  jz      short loc_180013768
0x18001375c  call    cs:__imp_RegCloseKey
0x180013763  nop     dword ptr [rax+rax+00h]
0x180013768  test    rbx, rbx
0x18001376b  jz      short loc_18001377C
0x18001376d  mov     rcx, rbx; hMem
0x180013770  call    cs:__imp_LocalFree
0x180013777  nop     dword ptr [rax+rax+00h]
0x18001377c  mov     eax, edi
0x18001377e  add     rsp, 60h
0x180013782  pop     r14
0x180013784  pop     rdi
0x180013785  pop     rsi
0x180013786  pop     rbx
0x180013787  pop     rbp
0x180013788  retn
```
