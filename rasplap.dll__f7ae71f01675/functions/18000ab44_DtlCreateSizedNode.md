# DtlCreateSizedNode

- ea: `0x18000ab44`
- end: `0x18000ab9e`
- name: `DtlCreateSizedNode`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008854`
- `0x180009148`
- `0x1800091ec`

## callees

- `0x18000ab44`
- `0x18000b0ce`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18000ab60`
- `KERNEL32!GlobalAlloc` at `0x18000ab60`

## pseudocode

```c
_QWORD *__fastcall DtlCreateSizedNode(unsigned int a1)
{
  __int64 v1; // rdi
  _QWORD *v2; // rbx
  _QWORD *v3; // rax

  v1 = (int)a1;
  v2 = 0;
  if ( a1 < 0xFFFFFFE0 )
  {
    v3 = GlobalAlloc(0x40u, a1 + 32);
    v2 = v3;
    if ( v3 )
    {
      memset_0(v3, 0, v1 + 32);
      if ( (_DWORD)v1 )
        v2[2] = v2 + 4;
      v2[3] = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000ab44  mov     [rsp+arg_0], rbx
0x18000ab49  push    rdi
0x18000ab4a  sub     rsp, 20h
0x18000ab4e  movsxd  rdi, ecx
0x18000ab51  xor     ebx, ebx
0x18000ab53  lea     eax, [rdi+20h]
0x18000ab56  cmp     eax, 20h ; ' '
0x18000ab59  jb      short loc_18000AB90
0x18000ab5b  mov     edx, eax; dwBytes
0x18000ab5d  lea     ecx, [rbx+40h]; uFlags
0x18000ab60  call    cs:__imp_GlobalAlloc
0x18000ab66  mov     rbx, rax
0x18000ab69  test    rax, rax
0x18000ab6c  jz      short loc_18000AB90
0x18000ab6e  lea     r8, [rdi+20h]; Size
0x18000ab72  xor     edx, edx; Val
0x18000ab74  mov     rcx, rax; void *
0x18000ab77  call    memset_0
0x18000ab7c  test    edi, edi
0x18000ab7e  jz      short loc_18000AB88
0x18000ab80  lea     rcx, [rbx+20h]
0x18000ab84  mov     [rbx+10h], rcx
0x18000ab88  mov     qword ptr [rbx+18h], 0
0x18000ab90  mov     rax, rbx
0x18000ab93  mov     rbx, [rsp+28h+arg_0]
0x18000ab98  add     rsp, 20h
0x18000ab9c  pop     rdi
0x18000ab9d  retn
```
