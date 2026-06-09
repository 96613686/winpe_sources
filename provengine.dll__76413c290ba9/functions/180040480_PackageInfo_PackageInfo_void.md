# PackageInfo::PackageInfo(void)

- ea: `0x180040480`
- end: `0x18004050e`
- name: `??0PackageInfo@@QEAA@XZ`
- size: `142`
- prototype: `PackageInfo *__fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014cf8`
- `0x18001c9e0`

## callees

- `0x1800092dc`
- `0x18002f9bc`
- `0x180040480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800404e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800404e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PackageInfo *__fastcall PackageInfo::PackageInfo(PHKEY phkResult)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *phkResult = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\PackageInfo";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\PackageInfo";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0xBu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)Key,
      dwOptions);
  return (PackageInfo *)phkResult;
}

```

## disassembly

```asm
0x180040480  mov     [rsp+arg_0], rcx
0x180040485  push    rbx
0x180040486  sub     rsp, 50h
0x18004048a  mov     rbx, rcx
0x18004048d  mov     qword ptr [rcx], 0
0x180040494  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180040499  lea     rcx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x1800404a0  lea     rdx, aOsdataSoftware_11; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800404a7  test    al, al
0x1800404a9  cmovz   rdx, rcx; lpSubKey
0x1800404ad  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800404b6  mov     [rsp+58h+phkResult], rbx; phkResult
0x1800404bb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800404c4  mov     [rsp+58h+samDesired], 0Bh; samDesired
0x1800404cc  mov     [rsp+58h+dwOptions], 0; unsigned int
0x1800404d4  xor     r9d, r9d; lpClass
0x1800404d7  xor     r8d, r8d; Reserved
0x1800404da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800404e1  call    cs:__imp_RegCreateKeyExW
0x1800404e7  mov     rcx, [rsp+58h]; this
0x1800404ec  test    eax, eax
0x1800404ee  jnz     short loc_1800404F9
0x1800404f0  mov     rax, rbx
0x1800404f3  add     rsp, 50h
0x1800404f7  pop     rbx
0x1800404f8  retn
0x1800404f9  mov     r9d, eax; char *
0x1800404fc  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180040503  mov     edx, 13h; void *
0x180040508  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
