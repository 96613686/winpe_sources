# ProvResults::GetRootKey(ulong)

- ea: `0x18003cedc`
- end: `0x18003cf81`
- name: `?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `165`
- prototype: `PHKEY __fastcall(PHKEY phkResult, REGSAM samDesired)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003cd14`
- `0x18003d0dc`
- `0x18003d1b8`

## callees

- `0x1800092dc`
- `0x18002f9bc`
- `0x18003cedc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cf4f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cf4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
PHKEY __fastcall ProvResults::GetRootKey(PHKEY phkResult, REGSAM samDesired)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *phkResult = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v5 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
  if ( !IsStateSeparationEnabled )
    v5 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, samDesired, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x264,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)Key,
      dwOptions);
  return phkResult;
}

```

## disassembly

```asm
0x18003cedc  mov     rax, rsp
0x18003cedf  mov     [rax+10h], rbx
0x18003cee3  mov     [rax+8], rcx
0x18003cee7  push    rdi
0x18003cee8  sub     rsp, 60h
0x18003ceec  mov     ebx, edx
0x18003ceee  mov     rdi, rcx
0x18003cef1  mov     dword ptr [rax-18h], 0
0x18003cef8  mov     dword ptr [rax-18h], 1
0x18003ceff  mov     qword ptr [rcx], 0
0x18003cf06  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18003cf0b  lea     rcx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Provisioning\\Resu"...
0x18003cf12  lea     rdx, aOsdataSoftware_7; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18003cf19  test    al, al
0x18003cf1b  cmovz   rdx, rcx; lpSubKey
0x18003cf1f  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18003cf28  mov     [rsp+68h+phkResult], rdi; phkResult
0x18003cf2d  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003cf36  mov     [rsp+68h+samDesired], ebx; samDesired
0x18003cf3a  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18003cf42  xor     r9d, r9d; lpClass
0x18003cf45  xor     r8d, r8d; Reserved
0x18003cf48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cf4f  call    cs:__imp_RegCreateKeyExW
0x18003cf55  test    eax, eax
0x18003cf57  jnz     short loc_18003CF67
0x18003cf59  mov     rax, rdi
0x18003cf5c  mov     rbx, [rsp+68h+arg_8]
0x18003cf61  add     rsp, 60h
0x18003cf65  pop     rdi
0x18003cf66  retn
0x18003cf67  mov     rcx, [rsp+68h]; this
0x18003cf6c  mov     r9d, eax; char *
0x18003cf6f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003cf76  mov     edx, 264h; void *
0x18003cf7b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
