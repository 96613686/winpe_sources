# DtlCreateSizedNode

- ea: `0x18002700c`
- end: `0x18002706d`
- name: `DtlCreateSizedNode`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180025480`
- `0x180027074`
- `0x180027118`

## callees

- `0x18002700c`
- `0x18002739e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180027028`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180027028`

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
0x18002700c  mov     [rsp+arg_0], rbx
0x180027011  push    rdi
0x180027012  sub     rsp, 20h
0x180027016  movsxd  rdi, ecx
0x180027019  xor     ebx, ebx
0x18002701b  lea     eax, [rdi+20h]
0x18002701e  cmp     eax, 20h ; ' '
0x180027021  jb      short loc_18002705E
0x180027023  mov     edx, eax; dwBytes
0x180027025  lea     ecx, [rbx+40h]; uFlags
0x180027028  call    cs:__imp_GlobalAlloc
0x18002702f  nop     dword ptr [rax+rax+00h]
0x180027034  mov     rbx, rax
0x180027037  test    rax, rax
0x18002703a  jz      short loc_18002705E
0x18002703c  lea     r8, [rdi+20h]; Size
0x180027040  xor     edx, edx; Val
0x180027042  mov     rcx, rax; void *
0x180027045  call    memset_0
0x18002704a  test    edi, edi
0x18002704c  jz      short loc_180027056
0x18002704e  lea     rcx, [rbx+20h]
0x180027052  mov     [rbx+10h], rcx
0x180027056  mov     qword ptr [rbx+18h], 0
0x18002705e  mov     rax, rbx
0x180027061  mov     rbx, [rsp+28h+arg_0]
0x180027066  add     rsp, 20h
0x18002706a  pop     rdi
0x18002706b  retn
```
