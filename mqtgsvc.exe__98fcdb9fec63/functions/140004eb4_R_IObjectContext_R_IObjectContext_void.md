# R<IObjectContext>::~R<IObjectContext>(void)

- ea: `0x140004eb4`
- end: `0x140004ed2`
- name: `??1?$R@UIObjectContext@@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x140003be8`
- `0x140003c5c`
- `0x1400076a8`
- `0x14000799c`
- `0x140007e04`
- `0x1400082d4`
- `0x1400083b0`
- `0x140008464`
- `0x140008b60`
- `0x140008f50`
- `0x140009238`
- `0x14000a6dc`
- `0x14000ac9c`
- `0x14000b23c`
- `0x14000bdc0`
- `0x14000cca0`
- `0x14000cf50`
- `0x14000d110`
- `0x14000d4a8`
- `0x14000d648`
- `0x14000e620`
- `0x14000e768`
- `0x140015d64`
- `0x14001e1c2`
- `0x14001ed4d`
- `0x14001eded`

## callees

- `0x140004eb4`
- `0x140020010`

## pseudocode

```c
__int64 __fastcall R<IObjectContext>::~R<IObjectContext>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140004eb4  sub     rsp, 28h
0x140004eb8  mov     rcx, [rcx]
0x140004ebb  test    rcx, rcx
0x140004ebe  jz      short loc_140004ECD
0x140004ec0  mov     rax, [rcx]
0x140004ec3  mov     rax, [rax+10h]
0x140004ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ecc  nop
0x140004ecd  add     rsp, 28h
0x140004ed1  retn
```
