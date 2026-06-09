# NegoExtsDeleteKernelContext

- ea: `0x1400221e0`
- end: `0x14002226c`
- name: `NegoExtsDeleteKernelContext`
- size: `140`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007008`
- `0x14000dd78`
- `0x14000e344`
- `0x1400221e0`

## string_xrefs

- `0x1400221f9`: `NegoExtsDeleteKernelContext called\n`
- `0x14002224d`: `NegoExtsDeleteKernelContext returned %#x\n`

## pseudocode

```c
__int64 __fastcall NegoExtsDeleteKernelContext(_QWORD *P, _QWORD *a2)
{
  unsigned int v4; // ebx

  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsDeleteKernelContext called\n");
  if ( *P == 0x4F47454E5458544BLL )
  {
    *a2 = P[1];
    NegoExtsFreeContext(P);
    v4 = 0;
  }
  else
  {
    v4 = -1073741816;
  }
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsDeleteKernelContext returned %#x\n", v4);
  return v4;
}

```

## disassembly

```asm
0x1400221e0  mov     [rsp+arg_0], rbx
0x1400221e5  push    rdi
0x1400221e6  sub     rsp, 30h
0x1400221ea  mov     rdi, rdx
0x1400221ed  mov     rbx, rcx
0x1400221f0  cmp     cs:KsecInfoLevel, 0
0x1400221f7  jz      short loc_14002220B
0x1400221f9  lea     rdx, aNegoextsdelete; "NegoExtsDeleteKernelContext called\n"
0x140022200  mov     ecx, 4
0x140022205  call    KsecDebugOut
0x14002220a  nop
0x14002220b  mov     rax, 4F47454E5458544Bh
0x140022215  cmp     [rbx], rax
0x140022218  jz      short loc_140022225
0x14002221a  mov     ebx, 0C0000008h
0x14002221f  mov     [rsp+38h+var_18], ebx
0x140022223  jmp     short loc_140022241
0x140022225  mov     rax, [rbx+8]
0x140022229  mov     [rdi], rax
0x14002222c  mov     rcx, rbx; P
0x14002222f  call    NegoExtsFreeContext
0x140022234  xor     ebx, ebx
0x140022236  jmp     short loc_140022241
0x140022238  mov     ebx, 0C0000008h
0x14002223d  mov     [rsp+38h+var_18], ebx
0x140022241  cmp     cs:KsecInfoLevel, 0
0x140022248  jz      short loc_14002225E
0x14002224a  mov     r8d, ebx
0x14002224d  lea     rdx, aNegoextsdelete_0; "NegoExtsDeleteKernelContext returned %#"...
0x140022254  mov     ecx, 4
0x140022259  call    KsecDebugOut
0x14002225e  mov     eax, ebx
0x140022260  mov     rbx, [rsp+38h+arg_0]
0x140022265  add     rsp, 30h
0x140022269  pop     rdi
0x14002226a  retn
0x140023e37  push    rbp
0x140023e39  sub     rsp, 20h
0x140023e3d  mov     rbp, rdx
0x140023e40  call    NegoExtsExceptionFilter
0x140023e45  nop
0x140023e46  add     rsp, 20h
0x140023e4a  pop     rbp
0x140023e4b  retn
```
