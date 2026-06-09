# CW32System::OleCreateFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)

- ea: `0x18008fbd0`
- end: `0x18008fc5e`
- name: `?OleCreateFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct IDataObject *, const struct _GUID *, unsigned int, struct tagFORMATETC *, struct IOleClientSite *, struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006c4c0`

## callees

- `0x180041adc`
- `0x18008fbd0`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008fbf3`: `OleCreateFromData`

## pseudocode

```c
__int64 __fastcall CW32System::OleCreateFromData(
        struct IDataObject *a1,
        const struct _GUID *a2,
        __int64 a3,
        struct tagFORMATETC *a4,
        struct IOleClientSite *a5,
        struct IStorage *a6,
        void **a7)
{
  FARPROC *Ole32Procs; // rax
  __int64 (__fastcall **v10)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **); // rbx

  Ole32Procs = (FARPROC *)CThreadData::GetOle32Procs();
  v10 = (__int64 (__fastcall **)(struct IDataObject *, GUID *, __int64, struct tagFORMATETC *, _QWORD, struct IStorage *, void **))Ole32Procs;
  if ( !*Ole32Procs )
    SetProcAddr(Ole32Procs, 1, "OleCreateFromData");
  if ( *v10 )
    return (*v10)(a1, &IID_IOleObject, 1, a4, 0, a6, a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18008fbd0  mov     [rsp+arg_0], rbx
0x18008fbd5  mov     [rsp+arg_8], rsi
0x18008fbda  push    rdi
0x18008fbdb  sub     rsp, 40h
0x18008fbdf  mov     rdi, r9
0x18008fbe2  mov     rsi, rcx
0x18008fbe5  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008fbea  mov     rbx, rax
0x18008fbed  cmp     qword ptr [rax], 0
0x18008fbf1  jnz     short loc_18008FC07
0x18008fbf3  lea     r8, aOlecreatefromd; "OleCreateFromData"
0x18008fbfa  mov     edx, 1
0x18008fbff  mov     rcx, rax
0x18008fc02  call    SetProcAddr
0x18008fc07  mov     rax, [rbx]
0x18008fc0a  test    rax, rax
0x18008fc0d  jz      short loc_18008FC49
0x18008fc0f  mov     rcx, [rsp+48h+arg_30]
0x18008fc17  lea     rdx, IID_IOleObject
0x18008fc1e  mov     [rsp+48h+var_18], rcx
0x18008fc23  mov     r9, rdi
0x18008fc26  mov     rcx, [rsp+48h+arg_28]
0x18008fc2b  mov     r8d, 1
0x18008fc31  mov     [rsp+48h+var_20], rcx
0x18008fc36  mov     rcx, rsi
0x18008fc39  mov     [rsp+48h+var_28], 0
0x18008fc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fc47  jmp     short loc_18008FC4E
0x18008fc49  mov     eax, 80004005h
0x18008fc4e  mov     rbx, [rsp+48h+arg_0]
0x18008fc53  mov     rsi, [rsp+48h+arg_8]
0x18008fc58  add     rsp, 40h
0x18008fc5c  pop     rdi
0x18008fc5d  retn
```
