# _guard_dispatch_icall

- ea: `0x140006b80`
- end: `0x140006b86`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `50`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000110c`
- `0x14000113c`
- `0x140001608`
- `0x140001930`
- `0x140002480`
- `0x1400024dc`
- `0x140002520`
- `0x140002574`
- `0x1400025d0`
- `0x140002958`
- `0x140002e0c`
- `0x1400035b8`
- `0x140003f00`
- `0x140004620`
- `0x140005164`
- `0x1400051c0`
- `0x140005504`
- `0x140005720`
- `0x14000592c`
- `0x140005f90`
- `0x140008010`
- `0x14000d010`
- `0x14000d0c8`
- `0x14000d15c`
- `0x14000d2b0`
- `0x14000e290`
- `0x14000f410`
- `0x140010130`
- `0x1400102b0`
- `0x1400108d4`
- `0x140010e50`
- `0x1400112e8`
- `0x140011430`
- `0x140011560`
- `0x14001169c`
- `0x140012854`
- `0x140012aa8`
- `0x140012dc8`
- `0x1400130a4`
- `0x140013344`
- `0x140014884`
- `0x1400152f4`
- `0x140015660`
- `0x140015bb0`
- `0x140015cf0`
- `0x140016310`
- `0x140016534`
- `0x140017740`
- `0x140017a00`
- `0x140018230`

## callees

- `0x140006bb0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140006b80  jmp     cs:__guard_dispatch_icall_fptr
```
