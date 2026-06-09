# CONTENT_TYPE_ALLOWED_ENTRY::Terminate(_LIST_ENTRY *)

- ea: `0x180001910`
- end: `0x180001952`
- name: `?Terminate@CONTENT_TYPE_ALLOWED_ENTRY@@SAXPEAU_LIST_ENTRY@@@Z`
- size: `66`
- prototype: `void __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d0`

## callees

- `0x180001910`
- `0x180001960`

## pseudocode

```c
void __fastcall CONTENT_TYPE_ALLOWED_ENTRY::Terminate(struct _LIST_ENTRY *a1)
{
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v3; // rax

  while ( 1 )
  {
    Flink = a1->Flink;
    if ( a1->Flink == a1 )
      break;
    if ( Flink->Blink != a1 || (v3 = Flink->Flink, Flink->Flink->Blink != Flink) )
      __fastfail(3u);
    a1->Flink = v3;
    v3->Blink = a1;
    CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'((CONTENT_TYPE_ALLOWED_ENTRY *)Flink);
  }
}

```

## disassembly

```asm
0x180001910  push    rbx
0x180001912  sub     rsp, 20h
0x180001916  mov     rbx, rcx
0x180001919  nop     dword ptr [rax+00000000h]
0x180001920  mov     rcx, [rbx]; this
0x180001923  cmp     rcx, rbx
0x180001926  jz      short loc_180001945
0x180001928  cmp     [rcx+8], rbx
0x18000192c  jnz     short loc_18000194B
0x18000192e  mov     rax, [rcx]
0x180001931  cmp     [rax+8], rcx
0x180001935  jnz     short loc_18000194B
0x180001937  mov     [rbx], rax
0x18000193a  mov     [rax+8], rbx
0x18000193e  call    ??_GCONTENT_TYPE_ALLOWED_ENTRY@@QEAAPEAXI@Z; CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(uint)
0x180001943  jmp     short loc_180001920
0x180001945  add     rsp, 20h
0x180001949  pop     rbx
0x18000194a  retn
0x18000194b  mov     ecx, 3
0x180001950  int     29h; Win8: RtlFailFast(ecx)
```
