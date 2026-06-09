# CMediaWrapperFilter::CreateInstanceOldGuid(IUnknown *,long *)

- ea: `0x180016540`
- end: `0x180016575`
- name: `?CreateInstanceOldGuid@CMediaWrapperFilter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `53`
- prototype: `static struct CUnknown *(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001020`
- `0x1800152f0`
- `0x180016540`

## pseudocode

```c
struct CUnknown *__fastcall CMediaWrapperFilter::CreateInstanceOldGuid(struct IUnknown *a1, int *a2)
{
  struct CUnknown *result; // rax
  struct IUnknown *v4; // rdx

  result = (struct CUnknown *)operator new(0x1C8u);
  if ( result )
    return CMediaWrapperFilter::CMediaWrapperFilter(result, v4, a2, &CLSID_WINME_DMOWrapperFilter);
  return result;
}

```

## disassembly

```asm
0x180016540  push    rbx
0x180016542  sub     rsp, 20h
0x180016546  mov     ecx, 1C8h; Size
0x18001654b  mov     rbx, rdx
0x18001654e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016553  test    rax, rax
0x180016556  jz      short loc_18001656F
0x180016558  lea     r9, CLSID_WINME_DMOWrapperFilter; struct _GUID *
0x18001655f  mov     r8, rbx; int *
0x180016562  mov     rcx, rax; this
0x180016565  add     rsp, 20h
0x180016569  pop     rbx
0x18001656a  jmp     ??0CMediaWrapperFilter@@QEAA@PEAUIUnknown@@PEAJPEBU_GUID@@@Z; CMediaWrapperFilter::CMediaWrapperFilter(IUnknown *,long *,_GUID const *)
0x18001656f  add     rsp, 20h
0x180016573  pop     rbx
0x180016574  retn
```
