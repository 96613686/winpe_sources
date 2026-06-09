# CMediaWrapperFilter::CreateInstance(IUnknown *,long *)

- ea: `0x180016500`
- end: `0x180016535`
- name: `?CreateInstance@CMediaWrapperFilter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `53`
- prototype: `static struct CUnknown *(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001020`
- `0x1800152f0`
- `0x180016500`

## pseudocode

```c
struct CUnknown *__fastcall CMediaWrapperFilter::CreateInstance(struct IUnknown *a1, int *a2)
{
  struct CUnknown *result; // rax
  struct IUnknown *v4; // rdx

  result = (struct CUnknown *)operator new(0x1C8u);
  if ( result )
    return CMediaWrapperFilter::CMediaWrapperFilter(result, v4, a2, &CLSID_DMOWrapperFilter);
  return result;
}

```

## disassembly

```asm
0x180016500  push    rbx
0x180016502  sub     rsp, 20h
0x180016506  mov     ecx, 1C8h; Size
0x18001650b  mov     rbx, rdx
0x18001650e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016513  test    rax, rax
0x180016516  jz      short loc_18001652F
0x180016518  lea     r9, CLSID_DMOWrapperFilter; struct _GUID *
0x18001651f  mov     r8, rbx; int *
0x180016522  mov     rcx, rax; this
0x180016525  add     rsp, 20h
0x180016529  pop     rbx
0x18001652a  jmp     ??0CMediaWrapperFilter@@QEAA@PEAUIUnknown@@PEAJPEBU_GUID@@@Z; CMediaWrapperFilter::CMediaWrapperFilter(IUnknown *,long *,_GUID const *)
0x18001652f  add     rsp, 20h
0x180016533  pop     rbx
0x180016534  retn
```
