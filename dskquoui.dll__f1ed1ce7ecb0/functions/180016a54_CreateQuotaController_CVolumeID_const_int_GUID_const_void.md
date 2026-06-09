# CreateQuotaController(CVolumeID const &,int,_GUID const &,void * *)

- ea: `0x180016a54`
- end: `0x180016b08`
- name: `?CreateQuotaController@@YAJAEBVCVolumeID@@HAEBU_GUID@@PEAPEAX@Z`
- size: `180`
- prototype: `__int64 __fastcall(const struct CVolumeID *, int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016410`
- `0x180018a68`

## callees

- `0x180016a54`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016a99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016a99`

## pseudocode

```c
__int64 __fastcall CreateQuotaController(const struct CVolumeID *a1, __int64 a2, const struct _GUID *a3, void **a4)
{
  HRESULT v6; // ebx
  LPVOID v8; // [rsp+50h] [rbp+18h] BYREF

  *a4 = 0;
  v8 = 0;
  v6 = CoCreateInstance(&CLSID_DiskQuotaControl, 0, 1u, &GUID_7988b572_ec89_11cf_9c00_00aa00a14f56, &v8);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v8 + 40LL))(v8, **((_QWORD **)a1 + 1), 1);
    if ( v6 >= 0 )
      v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))v8)(v8, &GUID_7988b572_ec89_11cf_9c00_00aa00a14f56, a4);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016a54  mov     r11, rsp
0x180016a57  mov     [r11+8], rbx
0x180016a5b  mov     [r11+10h], rsi
0x180016a5f  mov     [r11+18h], r8
0x180016a63  push    rdi
0x180016a64  sub     rsp, 30h
0x180016a68  xor     edx, edx; pUnkOuter
0x180016a6a  mov     qword ptr [r9], 0
0x180016a71  mov     rdi, r9
0x180016a74  mov     qword ptr [r11+18h], 0
0x180016a7c  mov     rsi, rcx
0x180016a7f  lea     rax, [r11+18h]
0x180016a83  lea     r9, _GUID_7988b572_ec89_11cf_9c00_00aa00a14f56; riid
0x180016a8a  mov     [r11-18h], rax
0x180016a8e  lea     r8d, [rdx+1]; dwClsContext
0x180016a92  lea     rcx, CLSID_DiskQuotaControl; rclsid
0x180016a99  call    cs:__imp_CoCreateInstance
0x180016a9f  mov     ebx, eax
0x180016aa1  test    eax, eax
0x180016aa3  js      short loc_180016AF6
0x180016aa5  mov     rcx, [rsp+38h+arg_10]
0x180016aaa  mov     r8d, 1
0x180016ab0  mov     rdx, [rsi+8]
0x180016ab4  mov     rax, [rcx]
0x180016ab7  mov     rdx, [rdx]
0x180016aba  mov     rax, [rax+28h]
0x180016abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ac3  mov     ebx, eax
0x180016ac5  test    eax, eax
0x180016ac7  js      short loc_180016AE5
0x180016ac9  mov     rcx, [rsp+38h+arg_10]
0x180016ace  lea     rdx, _GUID_7988b572_ec89_11cf_9c00_00aa00a14f56
0x180016ad5  mov     r8, rdi
0x180016ad8  mov     rax, [rcx]
0x180016adb  mov     rax, [rax]
0x180016ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae3  mov     ebx, eax
0x180016ae5  mov     rcx, [rsp+38h+arg_10]
0x180016aea  mov     rax, [rcx]
0x180016aed  mov     rax, [rax+10h]
0x180016af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af6  mov     rsi, [rsp+38h+arg_8]
0x180016afb  mov     eax, ebx
0x180016afd  mov     rbx, [rsp+38h+arg_0]
0x180016b02  add     rsp, 30h
0x180016b06  pop     rdi
0x180016b07  retn
```
