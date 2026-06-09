# CModule::UnregisterServer(void)

- ea: `0x180003fd0`
- end: `0x180004084`
- name: `?UnregisterServer@CModule@@QEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a630`

## callees

- `0x180003fd0`
- `0x18000408c`
- `0x18000412c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004067`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004033`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004067`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000407d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003ffe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003ffe`

## string_xrefs

- `0x180004005`: `CLSID\{58fb76b9-ac85-4e55-ac04-427593b1d060}`
- `0x180004039`: `CLSID`

## pseudocode

```c
void __fastcall CModule::UnregisterServer(CModule *this)
{
  char *v1; // rbx
  HKEY v2; // rdx
  int v3; // r9d
  HKEY v4; // rdx
  int v5; // r9d
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF
  char *v7; // [rsp+38h] [rbp+10h]

  hKey = (HKEY)this;
  v1 = (char *)&off_180011028 + SHIDWORD((*off_180011028)[1]);
  v7 = v1;
  RtlAcquireSRWLockExclusive(&v1[*(int *)(*(_QWORD *)v1 + 4LL)]);
  CRegKey::CRegKey(&hKey, v2, L"CLSID\\{58fb76b9-ac85-4e55-ac04-427593b1d060}", v3);
  CRegKey::DeleteKey(&hKey, L"InprocServer32");
  if ( hKey )
    RegCloseKey(hKey);
  CRegKey::CRegKey(&hKey, v4, L"CLSID", v5);
  CRegKey::DeleteKey(&hKey, L"{58fb76b9-ac85-4e55-ac04-427593b1d060}");
  if ( hKey )
    RegCloseKey(hKey);
  RtlReleaseSRWLockExclusive(&v1[*(int *)(*(_QWORD *)v1 + 4LL)]);
}

```

## disassembly

```asm
0x180003fd0  mov     [rsp+hKey], rcx
0x180003fd5  push    rbx
0x180003fd6  sub     rsp, 20h
0x180003fda  mov     rax, cs:off_180011028
0x180003fe1  movsxd  rbx, dword ptr [rax+0Ch]
0x180003fe5  lea     rax, off_180011028
0x180003fec  add     rbx, rax
0x180003fef  mov     [rsp+28h+arg_8], rbx
0x180003ff4  mov     rax, [rbx]
0x180003ff7  movsxd  rcx, dword ptr [rax+4]
0x180003ffb  add     rcx, rbx
0x180003ffe  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004004  nop
0x180004005  lea     r8, aClsid58fb76b9A; "CLSID\\{58fb76b9-ac85-4e55-ac04-427593b"...
0x18000400c  lea     rcx, [rsp+28h+hKey]; phkResult
0x180004011  call    ??0CRegKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegKey::CRegKey(HKEY__ *,ushort const *,ulong)
0x180004016  nop
0x180004017  lea     rdx, aInprocserver32; "InprocServer32"
0x18000401e  lea     rcx, [rsp+28h+hKey]; this
0x180004023  call    ?DeleteKey@CRegKey@@QEBAXPEBG@Z; CRegKey::DeleteKey(ushort const *)
0x180004028  nop
0x180004029  mov     rcx, [rsp+28h+hKey]; hKey
0x18000402e  test    rcx, rcx
0x180004031  jz      short loc_180004039
0x180004033  call    cs:__imp_RegCloseKey
0x180004039  lea     r8, aClsid; "CLSID"
0x180004040  lea     rcx, [rsp+28h+hKey]; phkResult
0x180004045  call    ??0CRegKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegKey::CRegKey(HKEY__ *,ushort const *,ulong)
0x18000404a  nop
0x18000404b  lea     rdx, aClsid58fb76b9A+0Ch; unsigned __int16 *
0x180004052  lea     rcx, [rsp+28h+hKey]; this
0x180004057  call    ?DeleteKey@CRegKey@@QEBAXPEBG@Z; CRegKey::DeleteKey(ushort const *)
0x18000405c  nop
0x18000405d  mov     rcx, [rsp+28h+hKey]; hKey
0x180004062  test    rcx, rcx
0x180004065  jz      short loc_18000406E
0x180004067  call    cs:__imp_RegCloseKey
0x18000406d  nop
0x18000406e  mov     rax, [rbx]
0x180004071  movsxd  rcx, dword ptr [rax+4]
0x180004075  add     rcx, rbx
0x180004078  add     rsp, 20h
0x18000407c  pop     rbx
0x18000407d  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
