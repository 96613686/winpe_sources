# TBFreeBuffer

- ea: `0x18001f058`
- end: `0x18001f085`
- name: `TBFreeBuffer`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049e8`
- `0x18001f008`
- `0x1800237b0`
- `0x180023a78`

## callees

- `0x18001f058`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18001f06b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001f06b`

## pseudocode

```c
void __fastcall TBFreeBuffer(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001f058  push    rbx
0x18001f05a  sub     rsp, 20h
0x18001f05e  mov     rbx, rcx
0x18001f061  mov     rcx, [rcx]; P
0x18001f064  test    rcx, rcx
0x18001f067  jz      short loc_18001F07E
0x18001f069  xor     edx, edx; Tag
0x18001f06b  call    cs:__imp_ExFreePoolWithTag
0x18001f072  nop     dword ptr [rax+rax+00h]
0x18001f077  mov     qword ptr [rbx], 0
0x18001f07e  add     rsp, 20h
0x18001f082  pop     rbx
0x18001f083  retn
```
