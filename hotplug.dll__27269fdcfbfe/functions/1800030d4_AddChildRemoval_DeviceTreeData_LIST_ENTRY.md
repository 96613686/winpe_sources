# AddChildRemoval(_DeviceTreeData *,_LIST_ENTRY *)

- ea: `0x1800030d4`
- end: `0x180003125`
- name: `?AddChildRemoval@@YAXPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@@Z`
- size: `81`
- prototype: `void __fastcall(struct _DeviceTreeData *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d4`
- `0x180004664`

## callees

- `0x1800030d4`
- `0x180006124`

## pseudocode

```c
void __fastcall AddChildRemoval(struct _DeviceTreeData *a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rbx
  __int64 v5; // rbp

  Flink = a2->Flink;
  if ( a2->Flink != a2 )
  {
    v5 = *((_QWORD *)a1 + 6);
    do
    {
      Flink[5].Flink = *(struct _LIST_ENTRY **)(v5 + 80);
      *(_QWORD *)(v5 + 80) = Flink;
      InvalidateTreeItemRect(*((HWND *)a1 + 1), (struct _TREEITEM *)Flink[5].Blink);
      AddChildRemoval(a1, Flink + 1);
      Flink = Flink->Flink;
    }
    while ( Flink != a2 );
  }
}

```

## disassembly

```asm
0x1800030d4  push    rbx
0x1800030d6  push    rbp
0x1800030d7  push    rsi
0x1800030d8  push    rdi
0x1800030d9  sub     rsp, 28h
0x1800030dd  mov     rbx, [rdx]
0x1800030e0  mov     rdi, rdx
0x1800030e3  mov     rsi, rcx
0x1800030e6  cmp     rbx, rdx
0x1800030e9  jz      short loc_18000311C
0x1800030eb  mov     rbp, [rcx+30h]
0x1800030ef  mov     rax, [rbp+50h]
0x1800030f3  mov     [rbx+50h], rax
0x1800030f7  mov     [rbp+50h], rbx
0x1800030fb  mov     rdx, [rbx+58h]; struct _TREEITEM *
0x1800030ff  mov     rcx, [rsi+8]; hWnd
0x180003103  call    ?InvalidateTreeItemRect@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; InvalidateTreeItemRect(HWND__ *,_TREEITEM *)
0x180003108  lea     rdx, [rbx+10h]; struct _LIST_ENTRY *
0x18000310c  mov     rcx, rsi; struct _DeviceTreeData *
0x18000310f  call    ?AddChildRemoval@@YAXPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@@Z; AddChildRemoval(_DeviceTreeData *,_LIST_ENTRY *)
0x180003114  mov     rbx, [rbx]
0x180003117  cmp     rbx, rdi
0x18000311a  jnz     short loc_1800030EF
0x18000311c  add     rsp, 28h
0x180003120  pop     rdi
0x180003121  pop     rsi
0x180003122  pop     rbp
0x180003123  pop     rbx
0x180003124  retn
```
