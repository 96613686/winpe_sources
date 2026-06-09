# utl::make_unique<Kerb3961::MutableBinary [0],0>(unsigned __int64)

- ea: `0x140007490`
- end: `0x14000750f`
- name: `??$make_unique@$$BY0A@UMutableBinary@Kerb3961@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@UMutableBinary@Kerb3961@@U?$default_delete@$$BY0A@UMutableBinary@Kerb3961@@@utl@@@0@_K@Z`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007600`
- `0x1400078f8`

## callees

- `0x140007490`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400074d3`
- `ntoskrnl!ExAllocatePool2` at `0x1400074d3`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<Kerb3961::MutableBinary [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  size_t v3; // rsi
  __int64 v4; // rcx
  void *Pool2; // rax
  void *v6; // rbx
  _QWORD *result; // rax

  v3 = 16 * a2;
  if ( !is_mul_ok(a2, 0x10u) )
    v3 = -1;
  v4 = 64;
  if ( KerbPoolType == PagedPool )
    v4 = 256;
  Pool2 = (void *)ExAllocatePool2(v4, v3, 1130525259);
  v6 = Pool2;
  if ( Pool2 )
    memset(Pool2, 0, v3);
  else
    v6 = 0;
  result = a1;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x140007490  mov     [rsp+arg_0], rbx
0x140007495  mov     [rsp+arg_8], rsi
0x14000749a  push    rdi
0x14000749b  sub     rsp, 20h
0x14000749f  mov     rdi, rcx
0x1400074a2  mov     eax, 10h
0x1400074a7  mul     rdx
0x1400074aa  mov     r8d, 4362724Bh
0x1400074b0  mov     rsi, rax
0x1400074b3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400074ba  cmovb   rsi, rax
0x1400074be  cmp     cs:?KerbPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE KerbPoolType
0x1400074c5  mov     rdx, rsi
0x1400074c8  lea     ecx, [rax+41h]
0x1400074cb  mov     eax, 100h
0x1400074d0  cmovz   ecx, eax
0x1400074d3  call    cs:__imp_ExAllocatePool2
0x1400074da  nop     dword ptr [rax+rax+00h]
0x1400074df  mov     rbx, rax
0x1400074e2  test    rax, rax
0x1400074e5  jz      short loc_1400074F6
0x1400074e7  mov     r8, rsi; Size
0x1400074ea  xor     edx, edx; Val
0x1400074ec  mov     rcx, rax; void *
0x1400074ef  call    memset
0x1400074f4  jmp     short loc_1400074F8
0x1400074f6  xor     ebx, ebx
0x1400074f8  mov     rsi, [rsp+28h+arg_8]
0x1400074fd  mov     rax, rdi
0x140007500  mov     [rdi], rbx
0x140007503  mov     rbx, [rsp+28h+arg_0]
0x140007508  add     rsp, 20h
0x14000750c  pop     rdi
0x14000750d  retn
```
