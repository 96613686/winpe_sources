# CuipGetMarkOfTheWeb(ushort const *)

- ea: `0x140018c68`
- end: `0x140018ce1`
- name: `?CuipGetMarkOfTheWeb@@YAKPEBG@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f200`

## callees

- `0x140018b88`
- `0x140018c68`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140018ca0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140018ca0`

## pseudocode

```c
__int64 __fastcall CuipGetMarkOfTheWeb(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v4; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  v4 = 999;
  ppv = 0;
  CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppv);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, int *, __int64))(*(_QWORD *)ppv + 40LL))(ppv, a1, &v4, 2);
  v2 = v4;
  wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(&ppv);
  return v2;
}

```

## disassembly

```asm
0x140018c68  push    rbx
0x140018c6a  sub     rsp, 30h
0x140018c6e  mov     rbx, rcx
0x140018c71  mov     [rsp+38h+arg_8], 3E7h
0x140018c79  mov     [rsp+38h+arg_10], 0
0x140018c82  lea     rax, [rsp+38h+arg_10]
0x140018c87  mov     [rsp+38h+ppv], rax; ppv
0x140018c8c  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x140018c93  xor     edx, edx; pUnkOuter
0x140018c95  lea     r8d, [rdx+1]; dwClsContext
0x140018c99  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x140018ca0  call    cs:__imp_CoCreateInstance
0x140018ca6  nop
0x140018ca7  mov     rcx, [rsp+38h+arg_10]
0x140018cac  test    rcx, rcx
0x140018caf  jz      short loc_140018CCB
0x140018cb1  mov     rax, [rcx]
0x140018cb4  mov     r9d, 2
0x140018cba  lea     r8, [rsp+38h+arg_8]
0x140018cbf  mov     rdx, rbx
0x140018cc2  mov     rax, [rax+28h]
0x140018cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ccb  mov     ebx, [rsp+38h+arg_8]
0x140018ccf  lea     rcx, [rsp+38h+arg_10]
0x140018cd4  call    ??1?$com_ptr_t@UIInternetSecurityManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(void)
0x140018cd9  mov     eax, ebx
0x140018cdb  add     rsp, 30h
0x140018cdf  pop     rbx
0x140018ce0  retn
```
