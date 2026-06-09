# RRasConfigStore::GetLastUpdateTimestampForRoutingDomains(_FILETIME *)

- ea: `0x180048bf8`
- end: `0x180048d7c`
- name: `?GetLastUpdateTimestampForRoutingDomains@RRasConfigStore@@QEAAKPEAU_FILETIME@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004162c`

## callees

- `0x180048bf8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048d50`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048ce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048ce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048c68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048c68`

## string_xrefs

- `0x180048c5a`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180048d0f`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180048c8d`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x180048d16`: `RRasConfigStore::GetLastUpdateTimestampForRoutingDomains`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetLastUpdateTimestampForRoutingDomains(
        RRasConfigStore *this,
        struct _FILETIME *a2)
{
  LSTATUS v3; // eax
  unsigned int InfoKeyW; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v9; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v10[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  hKey = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &hKey);
  InfoKeyW = v3;
  if ( v3 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_8;
    LODWORD(phkResult) = v3;
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      &v9,
      L"%s: RegOpenKeyEx (%s) failed: %d.",
      L"RRasConfigStore::GetLastUpdateTimestampForRoutingDomains",
      L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
      phkResult);
    goto LABEL_7;
  }
  InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, a2);
  if ( InfoKeyW && (_QWORD)xmmword_180078C50 )
  {
    LODWORD(phkResulta) = InfoKeyW;
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      &v9,
      L"%s: RegQueryInfoKey (%s) failed: %d.",
      L"RRasConfigStore::GetLastUpdateTimestampForRoutingDomains",
      L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
      phkResulta);
LABEL_7:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v9);
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return InfoKeyW;
}

```

## disassembly

```asm
0x180048bf8  mov     [rsp-8+arg_0], rbx
0x180048bfd  mov     [rsp-8+arg_10], rdi
0x180048c02  push    rbp
0x180048c03  lea     rbp, [rsp-780h]
0x180048c0b  sub     rsp, 880h
0x180048c12  mov     rax, cs:__security_cookie
0x180048c19  xor     rax, rsp
0x180048c1c  mov     [rbp+780h+var_10], rax
0x180048c23  mov     rdi, rdx
0x180048c26  mov     [rsp+880h+hKey], 0
0x180048c2f  xor     eax, eax
0x180048c31  lea     rcx, [rsp+880h+var_80C]; void *
0x180048c36  xor     edx, edx; Val
0x180048c38  mov     [rsp+880h+var_810], eax
0x180048c3c  mov     r8d, 7FCh; Size
0x180048c42  call    memset_0
0x180048c47  lea     rax, [rsp+880h+hKey]
0x180048c4c  mov     r9d, 0F003Fh; samDesired
0x180048c52  xor     r8d, r8d; ulOptions
0x180048c55  mov     [rsp+880h+phkResult], rax; phkResult
0x180048c5a  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x180048c61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048c68  call    cs:__imp_RegOpenKeyExW
0x180048c6e  mov     ebx, eax
0x180048c70  test    eax, eax
0x180048c72  jz      short loc_180048C96
0x180048c74  cmp     qword ptr cs:xmmword_180078C50, 0
0x180048c7c  jz      loc_180048D46
0x180048c82  xor     ecx, ecx
0x180048c84  mov     dword ptr [rsp+880h+phkResult], eax
0x180048c88  mov     word ptr [rsp+880h+var_810], cx
0x180048c8d  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x180048c94  jmp     short loc_180048D0F
0x180048c96  mov     rcx, [rsp+880h+hKey]; hKey
0x180048c9b  xor     r9d, r9d; lpReserved
0x180048c9e  mov     [rsp+880h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180048ca3  xor     r8d, r8d; lpcchClass
0x180048ca6  mov     [rsp+880h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180048caf  xor     edx, edx; lpClass
0x180048cb1  mov     [rsp+880h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180048cba  mov     [rsp+880h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180048cc3  mov     [rsp+880h+lpcValues], 0; lpcValues
0x180048ccc  mov     [rsp+880h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180048cd5  mov     [rsp+880h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180048cde  mov     [rsp+880h+phkResult], 0; lpcSubKeys
0x180048ce7  call    cs:__imp_RegQueryInfoKeyW
0x180048ced  mov     ebx, eax
0x180048cef  test    eax, eax
0x180048cf1  jz      short loc_180048D46
0x180048cf3  cmp     qword ptr cs:xmmword_180078C50, 0
0x180048cfb  jz      short loc_180048D46
0x180048cfd  xor     eax, eax
0x180048cff  mov     dword ptr [rsp+880h+phkResult], ebx
0x180048d03  mov     word ptr [rsp+880h+var_810], ax
0x180048d08  lea     rdx, aSRegqueryinfok; "%s: RegQueryInfoKey (%s) failed: %d."
0x180048d0f  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x180048d16  lea     r8, aRrasconfigstor_4; "RRasConfigStore::GetLastUpdateTimestamp"...
0x180048d1d  lea     rcx, [rsp+880h+var_810]
0x180048d22  call    FormatRRASErrorString
0x180048d27  mov     rdx, qword ptr cs:xmmword_180078C50
0x180048d2e  lea     r8, [rsp+880h+var_810]
0x180048d33  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048d3a  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180048d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d46  mov     rcx, [rsp+880h+hKey]; hKey
0x180048d4b  test    rcx, rcx
0x180048d4e  jz      short loc_180048D56
0x180048d50  call    cs:__imp_RegCloseKey
0x180048d56  mov     eax, ebx
0x180048d58  mov     rcx, [rbp+780h+var_10]
0x180048d5f  xor     rcx, rsp; StackCookie
0x180048d62  call    __security_check_cookie
0x180048d67  lea     r11, [rsp+880h+var_s0]
0x180048d6f  mov     rbx, [r11+10h]
0x180048d73  mov     rdi, [r11+20h]
0x180048d77  mov     rsp, r11
0x180048d7a  pop     rbp
0x180048d7b  retn
```
