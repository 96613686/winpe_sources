# ProvResults::GetRootKey(ulong)

- ea: `0x18002d090`
- end: `0x18002d12e`
- name: `?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `158`
- prototype: `PHKEY __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016d64`

## callees

- `0x18001434c`
- `0x18001b3a8`
- `0x18002d090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d101`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d101`

## pseudocode

```c
PHKEY __fastcall ProvResults::GetRootKey(PHKEY phkResult)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *phkResult = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x10009u, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)Key,
      dwOptions);
  return phkResult;
}

```

## disassembly

```asm
0x18002d090  mov     [rsp+arg_0], rcx
0x18002d095  push    rbx
0x18002d096  sub     rsp, 60h
0x18002d09a  mov     rbx, rcx
0x18002d09d  mov     [rsp+68h+var_18], 0
0x18002d0a5  mov     [rsp+68h+var_18], 1
0x18002d0ad  mov     qword ptr [rcx], 0
0x18002d0b4  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18002d0b9  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Provisioning\\Resu"...
0x18002d0c0  lea     rdx, aOsdataSoftware_4; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18002d0c7  test    al, al
0x18002d0c9  cmovz   rdx, rcx; lpSubKey
0x18002d0cd  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18002d0d6  mov     [rsp+68h+phkResult], rbx; phkResult
0x18002d0db  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002d0e4  mov     [rsp+68h+samDesired], 10009h; samDesired
0x18002d0ec  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18002d0f4  xor     r9d, r9d; lpClass
0x18002d0f7  xor     r8d, r8d; Reserved
0x18002d0fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d101  call    cs:__imp_RegCreateKeyExW
0x18002d107  test    eax, eax
0x18002d109  jnz     short loc_18002D114
0x18002d10b  mov     rax, rbx
0x18002d10e  add     rsp, 60h
0x18002d112  pop     rbx
0x18002d113  retn
0x18002d114  mov     rcx, [rsp+68h]; this
0x18002d119  mov     r9d, eax; char *
0x18002d11c  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18002d123  mov     edx, 264h; void *
0x18002d128  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
