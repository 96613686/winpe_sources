# DoDerefBundleCBWork

- ea: `0x140005494`
- end: `0x140005505`
- name: `DoDerefBundleCBWork`
- size: `113`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `32`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140001be0`
- `0x140003620`
- `0x140004be0`
- `0x140005930`
- `0x140007560`
- `0x140007710`
- `0x140007bf0`
- `0x140007fb0`
- `0x140008e5c`
- `0x140010e00`
- `0x140011320`
- `0x140011540`
- `0x140024008`
- `0x140025070`
- `0x1400254c8`
- `0x140025c80`
- `0x1400267f4`
- `0x140026970`
- `0x140026c80`
- `0x1400274e0`
- `0x140027a50`
- `0x140027da0`
- `0x140027fe0`
- `0x140028610`
- `0x140028f60`
- `0x14002a0f0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`
- `0x14002e540`
- `0x140030940`
- `0x140031b80`

## callees

- `0x140005494`
- `0x140005568`
- `0x1400057d8`
- `0x140013b68`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400054e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400054e2`

## pseudocode

```c
void __fastcall DoDerefBundleCBWork(_QWORD *Entry)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = Entry[306];
  if ( v2 )
  {
    BwcDereferenceQoSPolicy(v2);
    Entry[306] = 0;
  }
  v3 = Entry[307];
  if ( v3 )
  {
    BwcDereferenceQoSPolicy(v3);
    Entry[307] = 0;
  }
  KeReleaseSpinLock(Entry + 221, *((_BYTE *)Entry + 1776));
  RemoveBundleFromConnectionTable(Entry);
  NdisWanFreeBundleCB(Entry);
}

```

## disassembly

```asm
0x140005494  push    rbx
0x140005496  sub     rsp, 20h
0x14000549a  mov     rbx, rcx
0x14000549d  mov     rcx, [rcx+990h]
0x1400054a4  test    rcx, rcx
0x1400054a7  jz      short loc_1400054B9
0x1400054a9  call    BwcDereferenceQoSPolicy
0x1400054ae  mov     qword ptr [rbx+990h], 0
0x1400054b9  mov     rcx, [rbx+998h]
0x1400054c0  test    rcx, rcx
0x1400054c3  jz      short loc_1400054D5
0x1400054c5  call    BwcDereferenceQoSPolicy
0x1400054ca  mov     qword ptr [rbx+998h], 0
0x1400054d5  mov     dl, [rbx+6F0h]; NewIrql
0x1400054db  lea     rcx, [rbx+6E8h]; SpinLock
0x1400054e2  call    cs:__imp_KeReleaseSpinLock
0x1400054e9  nop     dword ptr [rax+rax+00h]
0x1400054ee  mov     rcx, rbx
0x1400054f1  call    RemoveBundleFromConnectionTable
0x1400054f6  mov     rcx, rbx; Entry
0x1400054f9  call    NdisWanFreeBundleCB
0x1400054fe  add     rsp, 20h
0x140005502  pop     rbx
0x140005503  retn
```
