# CsqRemoveIrp

- ea: `0x1400050c0`
- end: `0x1400050e9`
- name: `CsqRemoveIrp`
- size: `41`
- prototype: `IO_CSQ_REMOVE_IRP`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400050c0`

## pseudocode

```c
void __fastcall CsqRemoveIrp(PIO_CSQ Csq, PIRP Irp)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&Irp->Tail.Overlay.ListEntry;
  Flink = p_ListEntry->ListEntry.Flink;
  if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)p_ListEntry->ListEntry.Flink->Blink != p_ListEntry
    || (Blink = p_ListEntry->ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
}

```

## disassembly

```asm
0x1400050c0  add     rdx, 0A8h
0x1400050c7  mov     rcx, [rdx]
0x1400050ca  cmp     [rcx+8], rdx
0x1400050ce  jnz     short loc_1400050E2
0x1400050d0  mov     rax, [rdx+8]
0x1400050d4  cmp     [rax], rdx
0x1400050d7  jnz     short loc_1400050E2
0x1400050d9  mov     [rax], rcx
0x1400050dc  mov     [rcx+8], rax
0x1400050e0  retn
0x1400050e2  mov     ecx, 3
0x1400050e7  int     29h; Win8: RtlFailFast(ecx)
```
