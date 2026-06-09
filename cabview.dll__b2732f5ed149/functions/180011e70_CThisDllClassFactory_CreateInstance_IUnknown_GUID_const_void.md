# CThisDllClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180011e70`
- end: `0x180011eb9`
- name: `?CreateInstance@CThisDllClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `int(CThisDllClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b074`
- `0x18000d478`
- `0x180011e70`

## pseudocode

```c
__int64 __fastcall CThisDllClassFactory::CreateInstance(
        CThisDllClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v5 = *(_QWORD *)&CLSID_CabFolder.Data1 - *(_QWORD *)((char *)this + 12);
  if ( *(_QWORD *)&CLSID_CabFolder.Data1 == *(_QWORD *)((char *)this + 12) )
    v5 = *(_QWORD *)CLSID_CabFolder.Data4 - *(_QWORD *)((char *)this + 20);
  if ( v5 )
    return CabViewDataObject_CreateInstance(a3, a4);
  else
    return CabFolder_CreateInstance(a3, a4);
}

```

## disassembly

```asm
0x180011e70  test    r9, r9
0x180011e73  jnz     short loc_180011E7B
0x180011e75  mov     eax, 80070057h
0x180011e7a  retn
0x180011e7b  mov     qword ptr [r9], 0
0x180011e82  test    rdx, rdx
0x180011e85  jz      short loc_180011E8D
0x180011e87  mov     eax, 80040110h
0x180011e8c  retn
0x180011e8d  mov     rax, qword ptr cs:CLSID_CabFolder.Data1
0x180011e94  sub     rax, [rcx+0Ch]
0x180011e98  jnz     short loc_180011EA5
0x180011e9a  mov     rax, qword ptr cs:CLSID_CabFolder.Data4
0x180011ea1  sub     rax, [rcx+14h]
0x180011ea5  mov     rdx, r9; void **
0x180011ea8  mov     rcx, r8; struct _GUID *
0x180011eab  test    rax, rax
0x180011eae  jz      ?CabFolder_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CabFolder_CreateInstance(_GUID const &,void * *)
0x180011eb4  jmp     ?CabViewDataObject_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CabViewDataObject_CreateInstance(_GUID const &,void * *)
```
