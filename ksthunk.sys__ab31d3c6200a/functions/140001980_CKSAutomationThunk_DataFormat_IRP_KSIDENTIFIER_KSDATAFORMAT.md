# CKSAutomationThunk::DataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x140001980`
- end: `0x140001986`
- name: `?DataFormat@CKSAutomationThunk@@MEAAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CKSAutomationThunk *__hidden this, struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::DataFormat(
        CKSAutomationThunk *this,
        struct _IRP *a2,
        struct KSIDENTIFIER *a3,
        union KSDATAFORMAT *a4)
{
  return 3221226021LL;
}

```

## disassembly

```asm
0x140001980  mov     eax, 0C0000225h
0x140001985  retn
```
