# RDPEVNTLIST_CreateNewList

- ea: `0x140004120`
- end: `0x14000415f`
- name: `RDPEVNTLIST_CreateNewList`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001af10`

## callees

- `0x140003188`
- `0x140004120`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000413e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000413e`

## pseudocode

```c
KSPIN_LOCK *RDPEVNTLIST_CreateNewList()
{
  KSPIN_LOCK *v0; // rax
  KSPIN_LOCK *v1; // rbx

  v0 = (KSPIN_LOCK *)operator new(0x18u, 0x40u);
  v1 = v0;
  if ( v0 )
  {
    KeInitializeSpinLock(v0);
    v1[2] = (KSPIN_LOCK)(v1 + 1);
    v1[1] = (KSPIN_LOCK)(v1 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140004120  push    rbx
0x140004122  sub     rsp, 20h
0x140004126  mov     edx, 40h ; '@'; unsigned __int64
0x14000412b  lea     ecx, [rdx-28h]; unsigned __int64
0x14000412e  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140004133  mov     rbx, rax
0x140004136  test    rax, rax
0x140004139  jz      short loc_140004155
0x14000413b  mov     rcx, rax; SpinLock
0x14000413e  call    cs:__imp_KeInitializeSpinLock
0x140004145  nop     dword ptr [rax+rax+00h]
0x14000414a  lea     rcx, [rbx+8]
0x14000414e  mov     [rcx+8], rcx
0x140004152  mov     [rcx], rcx
0x140004155  mov     rax, rbx
0x140004158  add     rsp, 20h
0x14000415c  pop     rbx
0x14000415d  retn
```
