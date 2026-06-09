# _dynamic_atexit_destructor_for___AtlModule__

- ea: `0x180087470`
- end: `0x180087515`
- name: `_dynamic_atexit_destructor_for___AtlModule__`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019a00`
- `0x180026304`
- `0x180087470`
- `0x180088010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800874f2`
- `KERNEL32!DeleteCriticalSection` at `0x1800874f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall dynamic_atexit_destructor_for___AtlModule__(__int64 a1, struct _LIST_ENTRY *Flink)
{
  struct _LIST_ENTRY *Blink; // rbx
  PLIST_ENTRY OrderedPointer; // rax

  Blink = ATL::_AtlComModule.InsertOrderList.Blink;
  OrderedPointer = ATL::_AtlComModule.OrderedPointer;
  while ( Blink < OrderedPointer )
  {
    Flink = Blink->Flink;
    if ( Blink->Flink )
    {
      ((void (__fastcall *)(_QWORD))Flink[4].Flink)(0);
      OrderedPointer = ATL::_AtlComModule.OrderedPointer;
    }
    Blink = (struct _LIST_ENTRY *)((char *)Blink + 8);
  }
  if ( LODWORD(Table.TableRoot) )
  {
    if ( Table.InsertOrderList.Flink )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&Table);
      Table.InsertOrderList.Flink = 0;
    }
    if ( Table.FreeRoutine )
      (*(void (__fastcall **)(PRTL_GENERIC_FREE_ROUTINE))(*(_QWORD *)Table.FreeRoutine + 16LL))(Table.FreeRoutine);
    DeleteCriticalSection((LPCRITICAL_SECTION)&Table.InsertOrderList.Blink);
    LODWORD(Table.TableRoot) = 0;
  }
  UdfFileSystemSupport::UpdateDirectoryRecordDataLength(&Table, Flink);
}

```

## disassembly

```asm
0x180087470  push    rbx
0x180087472  sub     rsp, 20h
0x180087476  mov     rbx, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.InsertOrderList.Blink; ATL::CAtlComModule ATL::_AtlComModule ...
0x18008747d  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x180087484  jmp     short loc_1800874A4
0x180087486  mov     rdx, [rbx]
0x180087489  test    rdx, rdx
0x18008748c  jz      short loc_1800874A0
0x18008748e  xor     ecx, ecx
0x180087490  mov     rax, [rdx+40h]
0x180087494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087499  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x1800874a0  add     rbx, 8
0x1800874a4  cmp     rbx, rax
0x1800874a7  jb      short loc_180087486
0x1800874a9  cmp     dword ptr cs:Table.TableRoot, 0
0x1800874b0  jz      short loc_180087502
0x1800874b2  cmp     cs:Table.InsertOrderList.Flink, 0
0x1800874ba  jz      short loc_1800874D3
0x1800874bc  lea     rcx, Table; struct ATL::_ATL_MODULE70 *
0x1800874c3  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800874c8  mov     cs:Table.InsertOrderList.Flink, 0
0x1800874d3  mov     rcx, cs:Table.FreeRoutine
0x1800874da  test    rcx, rcx
0x1800874dd  jz      short loc_1800874EB
0x1800874df  mov     rax, [rcx]
0x1800874e2  mov     rax, [rax+10h]
0x1800874e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800874eb  lea     rcx, Table.InsertOrderList.Blink; lpCriticalSection
0x1800874f2  call    cs:__imp_DeleteCriticalSection
0x1800874f8  mov     dword ptr cs:Table.TableRoot, 0
0x180087502  lea     rcx, Table; Table
0x180087509  call    ?UpdateDirectoryRecordDataLength@UdfFileSystemSupport@@UEAAXAEAVImapiDirectoryInfo@@@Z; UdfFileSystemSupport::UpdateDirectoryRecordDataLength(ImapiDirectoryInfo &)
0x18008750e  nop
0x18008750f  add     rsp, 20h
0x180087513  pop     rbx
0x180087514  retn
```
