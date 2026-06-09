# HeapDumper::~HeapDumper(void)

- ea: `0x1801e5c2c`
- end: `0x1801e5cb4`
- name: `??1HeapDumper@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(HeapDumper *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801e5e40`
- `0x180218a30`
- `0x18034d0e2`
- `0x1803562ac`

## callees

- `0x1801e5c2c`
- `0x18035e010`

## import_xrefs

- `msvcrt!free` at `0x1801e5c69`
- `msvcrt!free` at `0x1801e5c69`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801e5c80`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801e5c80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HeapDumper::~HeapDumper(void **this)
{
  _QWORD *v2; // rdi
  void *v3; // rcx

  v2 = this + 5;
  if ( this[1] )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v2 + 40LL))(*v2, *(unsigned int *)this);
    free(this[1]);
    this[1] = 0;
  }
  v3 = this[3];
  if ( v3 )
  {
    CoTaskMemFree(v3);
    this[3] = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
}

```

## disassembly

```asm
0x1801e5c2c  mov     rax, rsp
0x1801e5c2f  mov     [rax+8], rcx
0x1801e5c33  push    rdi
0x1801e5c34  sub     rsp, 30h
0x1801e5c38  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1801e5c40  mov     [rax+10h], rbx
0x1801e5c44  mov     rbx, rcx
0x1801e5c47  mov     r8, [rcx+8]
0x1801e5c4b  lea     rdi, [rcx+28h]
0x1801e5c4f  test    r8, r8
0x1801e5c52  jz      short loc_1801E5C77
0x1801e5c54  mov     rcx, [rdi]
0x1801e5c57  mov     rax, [rcx]
0x1801e5c5a  mov     edx, [rbx]
0x1801e5c5c  mov     rax, [rax+28h]
0x1801e5c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e5c65  mov     rcx, [rbx+8]; Block
0x1801e5c69  call    cs:__imp_free
0x1801e5c6f  mov     qword ptr [rbx+8], 0
0x1801e5c77  mov     rcx, [rbx+18h]; pv
0x1801e5c7b  test    rcx, rcx
0x1801e5c7e  jz      short loc_1801E5C8E
0x1801e5c80  call    cs:__imp_CoTaskMemFree
0x1801e5c86  mov     qword ptr [rbx+18h], 0
0x1801e5c8e  mov     rcx, [rdi]
0x1801e5c91  test    rcx, rcx
0x1801e5c94  jz      short loc_1801E5CA9
0x1801e5c96  mov     rax, [rcx]
0x1801e5c99  mov     rax, [rax+10h]
0x1801e5c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e5ca2  mov     qword ptr [rdi], 0
0x1801e5ca9  mov     rbx, [rsp+38h+arg_8]
0x1801e5cae  add     rsp, 30h
0x1801e5cb2  pop     rdi
0x1801e5cb3  retn
```
