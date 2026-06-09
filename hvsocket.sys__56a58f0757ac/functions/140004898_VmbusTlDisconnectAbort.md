# VmbusTlDisconnectAbort

- ea: `0x140004898`
- end: `0x1400048ec`
- name: `VmbusTlDisconnectAbort`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001fa0`
- `0x140002b00`
- `0x140003fe0`
- `0x1400042d0`
- `0x14000440c`
- `0x1400045c0`
- `0x140004690`
- `0x1400049a0`
- `0x14000aa50`
- `0x14000b740`

## callees

- `0x140004898`
- `0x1400049a0`

## pseudocode

```c
__int64 __fastcall VmbusTlDisconnectAbort(__int64 a1)
{
  __int64 result; // rax

  if ( !*(_BYTE *)(a1 + 532) && (*(_DWORD *)(a1 + 528) & 0x100) == 0 )
  {
    *(_BYTE *)(a1 + 532) = 1;
    *(_DWORD *)(a1 + 520) = 255;
    *(_DWORD *)(a1 + 524) = 255;
    VmbusTlTransitionDisconnectState(a1, 18);
    return VmbusTlTransitionDisconnectState(a1, 3);
  }
  return result;
}

```

## disassembly

```asm
0x140004898  push    rbx
0x14000489a  sub     rsp, 20h
0x14000489e  cmp     byte ptr [rcx+214h], 0
0x1400048a5  mov     rbx, rcx
0x1400048a8  jnz     short loc_1400048E5
0x1400048aa  test    dword ptr [rcx+210h], 100h
0x1400048b4  jnz     short loc_1400048E5
0x1400048b6  mov     eax, 0FFh
0x1400048bb  mov     byte ptr [rcx+214h], 1
0x1400048c2  mov     edx, 12h
0x1400048c7  mov     [rcx+208h], eax
0x1400048cd  mov     [rcx+20Ch], eax
0x1400048d3  call    VmbusTlTransitionDisconnectState
0x1400048d8  mov     edx, 3
0x1400048dd  mov     rcx, rbx
0x1400048e0  call    VmbusTlTransitionDisconnectState
0x1400048e5  add     rsp, 20h
0x1400048e9  pop     rbx
0x1400048ea  retn
```
