# OleCreateStaticFromDataHelper(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x1800083f8`
- end: `0x180008488`
- name: `?OleCreateStaticFromDataHelper@@YAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022ca4`

## callees

- `0x1800083f8`
- `0x180008c80`
- `0x180008d2c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008432`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008432`

## string_xrefs

- `0x18000842b`: `OleCreateStaticFromData`

## pseudocode

```c
__int64 __fastcall OleCreateStaticFromDataHelper(
        struct IDataObject *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct tagFORMATETC *a4,
        struct IOleClientSite *a5,
        struct IStorage *a6,
        void **a7)
{
  FARPROC ProcAddress; // rax

  if ( AutoLibrary::valid((AutoLibrary *)&g_ole32Helper)
    && (AutoLibrary::load((AutoLibrary *)&g_ole32Helper),
        (ProcAddress = GetProcAddress(hModule, "OleCreateStaticFromData")) != 0) )
  {
    return ((__int64 (__fastcall *)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **))ProcAddress)(
             a1,
             &IID_IOleObject,
             2,
             a4,
             a5,
             a6,
             a7);
  }
  else
  {
    return 2147942527LL;
  }
}

```

## disassembly

```asm
0x1800083f8  mov     [rsp+arg_0], rbx
0x1800083fd  push    rdi
0x1800083fe  sub     rsp, 40h
0x180008402  mov     rdi, rcx
0x180008405  mov     rbx, r9
0x180008408  lea     rcx, ?g_ole32Helper@@3UAutoLibrary@@A; this
0x18000840f  call    ?valid@AutoLibrary@@QEAA_NXZ; AutoLibrary::valid(void)
0x180008414  test    al, al
0x180008416  jz      short loc_180008478
0x180008418  lea     rcx, ?g_ole32Helper@@3UAutoLibrary@@A; this
0x18000841f  call    ?load@AutoLibrary@@AEAAXXZ; AutoLibrary::load(void)
0x180008424  mov     rcx, cs:hModule; hModule
0x18000842b  lea     rdx, aOlecreatestati; "OleCreateStaticFromData"
0x180008432  call    cs:__imp_GetProcAddress
0x180008438  test    rax, rax
0x18000843b  jz      short loc_180008478
0x18000843d  mov     rcx, [rsp+48h+arg_30]
0x180008445  lea     rdx, IID_IOleObject
0x18000844c  mov     [rsp+48h+var_18], rcx
0x180008451  mov     r9, rbx
0x180008454  mov     rcx, [rsp+48h+arg_28]
0x180008459  mov     r8d, 2
0x18000845f  mov     [rsp+48h+var_20], rcx
0x180008464  mov     rcx, [rsp+48h+arg_20]
0x180008469  mov     [rsp+48h+var_28], rcx
0x18000846e  mov     rcx, rdi
0x180008471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008476  jmp     short loc_18000847D
0x180008478  mov     eax, 8007007Fh
0x18000847d  mov     rbx, [rsp+48h+arg_0]
0x180008482  add     rsp, 40h
0x180008486  pop     rdi
0x180008487  retn
```
