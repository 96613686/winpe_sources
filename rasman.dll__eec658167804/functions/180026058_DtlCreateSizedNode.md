# DtlCreateSizedNode

- ea: `0x180026058`
- end: `0x1800260b2`
- name: `DtlCreateSizedNode`
- size: `90`
- prototype: `_QWORD *__fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800246b8`
- `0x1800260b8`
- `0x18002615c`

## callees

- `0x180026058`
- `0x1800263ce`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026074`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180026074`

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
0x180026058  mov     [rsp+arg_0], rbx
0x18002605d  push    rdi
0x18002605e  sub     rsp, 20h
0x180026062  movsxd  rdi, ecx
0x180026065  xor     ebx, ebx
0x180026067  lea     eax, [rdi+20h]
0x18002606a  cmp     eax, 20h ; ' '
0x18002606d  jb      short loc_1800260A4
0x18002606f  mov     edx, eax; dwBytes
0x180026071  lea     ecx, [rbx+40h]; uFlags
0x180026074  call    cs:__imp_GlobalAlloc
0x18002607a  mov     rbx, rax
0x18002607d  test    rax, rax
0x180026080  jz      short loc_1800260A4
0x180026082  lea     r8, [rdi+20h]; Size
0x180026086  xor     edx, edx; Val
0x180026088  mov     rcx, rax; void *
0x18002608b  call    memset_0
0x180026090  test    edi, edi
0x180026092  jz      short loc_18002609C
0x180026094  lea     rcx, [rbx+20h]
0x180026098  mov     [rbx+10h], rcx
0x18002609c  mov     qword ptr [rbx+18h], 0
0x1800260a4  mov     rax, rbx
0x1800260a7  mov     rbx, [rsp+28h+arg_0]
0x1800260ac  add     rsp, 20h
0x1800260b0  pop     rdi
0x1800260b1  retn
```
