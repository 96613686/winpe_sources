# TenantRestrictionsHelpers::GetJsonArraySize(Windows::Data::Json::IJsonArray *)

- ea: `0x18000e5e0`
- end: `0x18000e661`
- name: `?GetJsonArraySize@TenantRestrictionsHelpers@@YAIPEAUIJsonArray@Json@Data@Windows@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(TenantRestrictionsHelpers *this, struct Windows::Data::Json::IJsonArray *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e668`
- `0x18000f7cc`

## callees

- `0x18000c41c`
- `0x18000dcdc`
- `0x18000e5e0`
- `0x180012010`

## string_xrefs

- `0x18000e639`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::GetJsonArraySize(
        TenantRestrictionsHelpers *this,
        struct Windows::Data::Json::IJsonArray *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  if ( !this )
    return 0;
  v8 = 0;
  (**(void (__fastcall ***)(TenantRestrictionsHelpers *, GUID *, __int64 *))this)(
    this,
    &GUID_d44662bc_dce3_59a8_9272_4b210f33908b,
    &v8);
  v7 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 56LL))(v8, &v7);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E1,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)(unsigned int)v3,
      v5);
  v4 = v7;
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v8);
  return v4;
}

```

## disassembly

```asm
0x18000e5e0  push    rbx; int
0x18000e5e2  sub     rsp, 20h
0x18000e5e6  test    rcx, rcx
0x18000e5e9  jnz     short loc_18000E5EF
0x18000e5eb  xor     eax, eax
0x18000e5ed  jmp     short loc_18000E65B
0x18000e5ef  mov     [rsp+28h+arg_8], 0
0x18000e5f8  mov     rax, [rcx]
0x18000e5fb  lea     r8, [rsp+28h+arg_8]
0x18000e600  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x18000e607  mov     rax, [rax]
0x18000e60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e60f  mov     [rsp+28h+arg_0], 0
0x18000e617  mov     rcx, [rsp+28h+arg_8]
0x18000e61c  mov     rax, [rcx]
0x18000e61f  lea     rdx, [rsp+28h+arg_0]
0x18000e624  mov     rax, [rax+38h]
0x18000e628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e62d  mov     rcx, [rsp+28h]; this
0x18000e632  test    eax, eax
0x18000e634  jns     short loc_18000E64B
0x18000e636  mov     r9d, eax; char *
0x18000e639  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e640  mov     edx, 1E1h; void *
0x18000e645  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e64b  mov     ebx, [rsp+28h+arg_0]
0x18000e64f  lea     rcx, [rsp+28h+arg_8]
0x18000e654  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000e659  mov     eax, ebx
0x18000e65b  add     rsp, 20h
0x18000e65f  pop     rbx
0x18000e660  retn
```
