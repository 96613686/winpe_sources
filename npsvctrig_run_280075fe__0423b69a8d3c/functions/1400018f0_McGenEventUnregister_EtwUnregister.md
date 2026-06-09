# McGenEventUnregister_EtwUnregister

- ea: `0x1400018f0`
- end: `0x14000191f`
- name: `McGenEventUnregister_EtwUnregister`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008250`
- `0x14000b080`

## callees

- `0x1400018f0`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x140001905`
- `ntoskrnl!EtwUnregister` at `0x140001905`

## pseudocode

```c
NTSTATUS __fastcall McGenEventUnregister_EtwUnregister(REGHANDLE *a1)
{
  REGHANDLE v2; // rcx
  NTSTATUS result; // eax

  v2 = *a1;
  if ( !v2 )
    return 0;
  result = EtwUnregister(v2);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400018f0  push    rbx
0x1400018f2  sub     rsp, 20h
0x1400018f6  mov     rbx, rcx
0x1400018f9  mov     rcx, [rcx]; RegHandle
0x1400018fc  test    rcx, rcx
0x1400018ff  jnz     short loc_140001905
0x140001901  xor     eax, eax
0x140001903  jmp     short loc_140001918
0x140001905  call    cs:__imp_EtwUnregister
0x14000190c  nop     dword ptr [rax+rax+00h]
0x140001911  mov     qword ptr [rbx], 0
0x140001918  add     rsp, 20h
0x14000191c  pop     rbx
0x14000191d  retn
```
