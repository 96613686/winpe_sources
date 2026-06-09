# CAdvancedSettingsReader::RetrieveCurrentProfile(NET_FW_PROFILE_TYPE2_ *)

- ea: `0x1800132e0`
- end: `0x180013361`
- name: `?RetrieveCurrentProfile@CAdvancedSettingsReader@@SAJPEAW4NET_FW_PROFILE_TYPE2_@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(enum NET_FW_PROFILE_TYPE2_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000abc8`

## callees

- `0x1800132e0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013316`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013316`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsReader::RetrieveCurrentProfile(enum NET_FW_PROFILE_TYPE2_ *a1)
{
  enum NET_FW_PROFILE_TYPE2_ v3; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  *a1 = NET_FW_PROFILE2_ALL;
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_1fda955b_61ff_11da_978c_0008744faab7,
         0,
         1u,
         &GUID_1fda955c_61ff_11da_978c_0008744faab7,
         &ppv) >= 0 )
  {
    v3 = 0;
    if ( !(*(unsigned int (__fastcall **)(LPVOID, enum NET_FW_PROFILE_TYPE2_ *))(*(_QWORD *)ppv + 40LL))(ppv, &v3) )
      *a1 = v3;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return 0;
}

```

## disassembly

```asm
0x1800132e0  push    rbx
0x1800132e2  sub     rsp, 30h
0x1800132e6  xor     edx, edx; pUnkOuter
0x1800132e8  mov     dword ptr [rcx], 7FFFFFFFh
0x1800132ee  mov     rbx, rcx
0x1800132f1  mov     [rsp+38h+arg_8], 0
0x1800132fa  lea     rax, [rsp+38h+arg_8]
0x1800132ff  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x180013306  mov     [rsp+38h+ppv], rax; ppv
0x18001330b  lea     r8d, [rdx+1]; dwClsContext
0x18001330f  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x180013316  call    cs:__imp_CoCreateInstance
0x18001331c  test    eax, eax
0x18001331e  js      short loc_180013359
0x180013320  mov     rcx, [rsp+38h+arg_8]
0x180013325  lea     rdx, [rsp+38h+arg_0]
0x18001332a  mov     [rsp+38h+arg_0], 0
0x180013332  mov     rax, [rcx]
0x180013335  mov     rax, [rax+28h]
0x180013339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001333e  test    eax, eax
0x180013340  jnz     short loc_180013348
0x180013342  mov     eax, [rsp+38h+arg_0]
0x180013346  mov     [rbx], eax
0x180013348  mov     rcx, [rsp+38h+arg_8]
0x18001334d  mov     rax, [rcx]
0x180013350  mov     rax, [rax+10h]
0x180013354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013359  xor     eax, eax
0x18001335b  add     rsp, 30h
0x18001335f  pop     rbx
0x180013360  retn
```
