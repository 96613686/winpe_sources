# SetAllowEmbeddedMode(int)

- ea: `0x1800184a4`
- end: `0x180018587`
- name: `?SetAllowEmbeddedMode@@YAJH@Z`
- size: `227`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180008018`

## callees

- `0x18001053c`
- `0x180010558`
- `0x18001839c`
- `0x1800184a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018557`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018557`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018504`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018504`

## string_xrefs

- `0x1800184cc`: `System\CurrentControlSet\Services\EmbeddedMode\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetAllowEmbeddedMode()
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  int SMBIOSUniqueIdHash; // eax
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  lpData = 0;
  cbData = 0;
  hKey = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\EmbeddedMode\\Parameters",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
    SMBIOSUniqueIdHash = GetSMBIOSUniqueIdHash(&lpData, &cbData);
    if ( SMBIOSUniqueIdHash >= 0 )
    {
      SMBIOSUniqueIdHash = RegSetValueExW(hKey, L"Flags", 0, 3u, lpData, cbData);
      if ( SMBIOSUniqueIdHash > 0 )
        SMBIOSUniqueIdHash = (unsigned __int16)SMBIOSUniqueIdHash | 0x80070000;
    }
    v1 = SMBIOSUniqueIdHash;
  }
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800184a4  mov     rax, rsp
0x1800184a7  mov     [rax+8], ecx
0x1800184aa  push    rbx
0x1800184ab  sub     rsp, 50h
0x1800184af  mov     qword ptr [rax-18h], 0
0x1800184b7  xor     r9d, r9d; lpClass
0x1800184ba  mov     qword ptr [rax+10h], 0
0x1800184c2  xor     r8d, r8d; Reserved
0x1800184c5  mov     dword ptr [rax+8], 0
0x1800184cc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Em"...
0x1800184d3  mov     qword ptr [rax+18h], 0
0x1800184db  lea     rax, [rax+18h]
0x1800184df  mov     [rsp+58h+phkResult], rax; phkResult
0x1800184e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184eb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800184f4  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800184fc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180018504  call    cs:__imp_RegCreateKeyExW
0x18001850a  mov     ebx, eax
0x18001850c  test    eax, eax
0x18001850e  jle     short loc_180018519
0x180018510  movzx   ebx, ax
0x180018513  or      ebx, 80070000h
0x180018519  test    ebx, ebx
0x18001851b  js      short loc_18001856B
0x18001851d  lea     rdx, [rsp+58h+cbData]
0x180018522  lea     rcx, [rsp+58h+lpData]
0x180018527  call    GetSMBIOSUniqueIdHash
0x18001852c  test    eax, eax
0x18001852e  js      short loc_180018569
0x180018530  mov     eax, [rsp+58h+cbData]
0x180018534  lea     rdx, ValueName; "Flags"
0x18001853b  mov     rcx, [rsp+58h+hKey]; hKey
0x180018540  mov     r9d, 3; dwType
0x180018546  mov     [rsp+58h+samDesired], eax; cbData
0x18001854a  xor     r8d, r8d; Reserved
0x18001854d  mov     rax, [rsp+58h+lpData]
0x180018552  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180018557  call    cs:__imp_RegSetValueExW
0x18001855d  test    eax, eax
0x18001855f  jle     short loc_180018569
0x180018561  movzx   eax, ax
0x180018564  or      eax, 80070000h
0x180018569  mov     ebx, eax
0x18001856b  lea     rcx, [rsp+58h+lpData]
0x180018570  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180018575  lea     rcx, [rsp+58h+hKey]
0x18001857a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001857f  mov     eax, ebx
0x180018581  add     rsp, 50h
0x180018585  pop     rbx
0x180018586  retn
```
