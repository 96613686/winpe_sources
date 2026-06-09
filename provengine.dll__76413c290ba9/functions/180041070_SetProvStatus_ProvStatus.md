# SetProvStatus(ProvStatus)

- ea: `0x180041070`
- end: `0x180041163`
- name: `?SetProvStatus@@YAXW4ProvStatus@@@Z`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018068`

## callees

- `0x1800092dc`
- `0x18002f9bc`
- `0x180040fd4`
- `0x180041070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041115`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004112e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004112e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800410e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800410e4`

## string_xrefs

- `0x18004109e`: `OSData\SOFTWARE\Microsoft\Provisioning\Agent`
- `0x180041097`: `SOFTWARE\Microsoft\Provisioning\Agent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int SetProvStatus()
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v1; // rdx
  unsigned int v2; // eax
  unsigned int result; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = GetProvStatus() | 1;
  hKey = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v1 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Agent";
  if ( !IsStateSeparationEnabled )
    v1 = L"SOFTWARE\\Microsoft\\Provisioning\\Agent";
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1C,
      (int)"onecoreuap\\admin\\prov\\lib\\provstatus.cpp",
      (const char *)v2,
      dwOptions);
  result = RegSetValueExW(hKey, L"Status", 0, 4u, (const BYTE *)&Data, 4u);
  if ( result )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1F,
      (int)"onecoreuap\\admin\\prov\\lib\\provstatus.cpp",
      (const char *)result,
      dwOptionsa);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180041070  mov     [rsp+Data], ecx
0x180041074  sub     rsp, 58h
0x180041078  mov     [rsp+58h+Data], 1
0x180041080  call    ?GetProvStatus@@YA?AW4ProvStatus@@XZ; GetProvStatus(void)
0x180041085  or      [rsp+58h+Data], eax
0x180041089  mov     [rsp+58h+hKey], 0
0x180041092  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180041097  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\Agen"...
0x18004109e  lea     rdx, aOsdataSoftware_4; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800410a5  test    al, al
0x1800410a7  cmovz   rdx, rcx; lpSubKey
0x1800410ab  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800410b4  lea     rax, [rsp+58h+hKey]
0x1800410b9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800410be  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800410c7  mov     [rsp+58h+samDesired], 2; samDesired
0x1800410cf  mov     [rsp+58h+dwOptions], 0; unsigned int
0x1800410d7  xor     r9d, r9d; lpClass
0x1800410da  xor     r8d, r8d; Reserved
0x1800410dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800410e4  call    cs:__imp_RegCreateKeyExW
0x1800410ea  mov     rcx, [rsp+58h]; this
0x1800410ef  test    eax, eax
0x1800410f1  jnz     short loc_18004114E
0x1800410f3  lea     r9d, [rax+4]; dwType
0x1800410f7  mov     [rsp+58h+samDesired], r9d; cbData
0x1800410fc  lea     rax, [rsp+58h+Data]
0x180041101  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x180041106  xor     r8d, r8d; Reserved
0x180041109  lea     rdx, aStatus; "Status"
0x180041110  mov     rcx, [rsp+58h+hKey]; hKey
0x180041115  call    cs:__imp_RegSetValueExW
0x18004111b  mov     rcx, [rsp+58h]; this
0x180041120  test    eax, eax
0x180041122  jnz     short loc_180041139
0x180041124  mov     rcx, [rsp+58h+hKey]; hKey
0x180041129  test    rcx, rcx
0x18004112c  jz      short loc_180041134
0x18004112e  call    cs:__imp_RegCloseKey
0x180041134  add     rsp, 58h
0x180041138  retn
0x180041139  mov     r9d, eax; char *
0x18004113c  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\lib\\provstatu"...
0x180041143  mov     edx, 1Fh; void *
0x180041148  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004114e  mov     r9d, eax; char *
0x180041151  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\lib\\provstatu"...
0x180041158  mov     edx, 1Ch; void *
0x18004115d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
