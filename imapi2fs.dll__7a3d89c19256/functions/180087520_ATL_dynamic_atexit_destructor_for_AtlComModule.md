# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180087520`
- end: `0x1800875a5`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180019a00`
- `0x180087520`
- `0x180088010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18008757f`
- `KERNEL32!DeleteCriticalSection` at `0x18008757f`

## pseudocode

```c
void __fastcall ATL::_dynamic_atexit_destructor_for___AtlComModule__(__int64 a1, void *a2)
{
  struct _LIST_ENTRY *Blink; // rbx
  PLIST_ENTRY OrderedPointer; // rax
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // rcx

  if ( LODWORD(ATL::_AtlComModule.TableRoot) )
  {
    Blink = ATL::_AtlComModule.InsertOrderList.Blink;
    OrderedPointer = ATL::_AtlComModule.OrderedPointer;
    while ( Blink < OrderedPointer )
    {
      Flink = Blink->Flink;
      if ( Blink->Flink )
      {
        v5 = Flink[2].Flink;
        if ( v5 )
          ((void (__fastcall *)(struct _LIST_ENTRY *))v5->Flink[1].Flink)(v5);
        Flink[2].Flink = 0;
        OrderedPointer = ATL::_AtlComModule.OrderedPointer;
      }
      Blink = (struct _LIST_ENTRY *)((char *)Blink + 8);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&ATL::_AtlComModule.WhichOrderedElement);
    LODWORD(ATL::_AtlComModule.TableRoot) = 0;
  }
  UdfFileSystemSupport::UpdateDirectoryRecordDataLength(&ATL::_AtlComModule, a2);
}

```

## disassembly

```asm
0x180087520  mov     [rsp+arg_0], rbx
0x180087525  push    rdi
0x180087526  sub     rsp, 20h
0x18008752a  cmp     dword ptr cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.TableRoot, 0; ATL::CAtlComModule ATL::_AtlComModule ...
0x180087531  jz      short loc_18008758F
0x180087533  mov     rbx, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.InsertOrderList.Blink; ATL::CAtlComModule ATL::_AtlComModule ...
0x18008753a  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x180087541  jmp     short loc_180087573
0x180087543  mov     rdi, [rbx]
0x180087546  test    rdi, rdi
0x180087549  jz      short loc_18008756F
0x18008754b  mov     rcx, [rdi+20h]
0x18008754f  test    rcx, rcx
0x180087552  jz      short loc_180087560
0x180087554  mov     rax, [rcx]
0x180087557  mov     rax, [rax+10h]
0x18008755b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087560  mov     qword ptr [rdi+20h], 0
0x180087568  mov     rax, cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.OrderedPointer; ATL::CAtlComModule ATL::_AtlComModule ...
0x18008756f  add     rbx, 8
0x180087573  cmp     rbx, rax
0x180087576  jb      short loc_180087543
0x180087578  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A.WhichOrderedElement; lpCriticalSection
0x18008757f  call    cs:__imp_DeleteCriticalSection
0x180087585  mov     dword ptr cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A.TableRoot, 0; ATL::CAtlComModule ATL::_AtlComModule ...
0x18008758f  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; Table
0x180087596  mov     rbx, [rsp+28h+arg_0]
0x18008759b  add     rsp, 20h
0x18008759f  pop     rdi
0x1800875a0  jmp     ?UpdateDirectoryRecordDataLength@UdfFileSystemSupport@@UEAAXAEAVImapiDirectoryInfo@@@Z; UdfFileSystemSupport::UpdateDirectoryRecordDataLength(ImapiDirectoryInfo &)
```
