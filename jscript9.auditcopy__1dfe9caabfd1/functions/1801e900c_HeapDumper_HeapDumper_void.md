# HeapDumper::~HeapDumper(void)

- ea: `0x1801e900c`
- end: `0x1801e90a1`
- name: `??1HeapDumper@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(void **this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801e9230`
- `0x18021c350`
- `0x1803534cb`
- `0x18035c66f`

## callees

- `0x1801e900c`
- `0x180364010`

## import_xrefs

- `msvcrt!free` at `0x1801e9049`
- `msvcrt!free` at `0x1801e9049`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801e9066`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801e9066`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HeapDumper::~HeapDumper(void **this)
{
  void **v2; // rdi
  void *v3; // rcx

  v2 = this + 5;
  if ( this[1] )
  {
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 40LL))(*v2, *(unsigned int *)this);
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
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
}

```

## disassembly

```asm
0x1801e900c  mov     rax, rsp
0x1801e900f  mov     [rax+8], rcx
0x1801e9013  push    rdi
0x1801e9014  sub     rsp, 30h
0x1801e9018  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1801e9020  mov     [rax+10h], rbx
0x1801e9024  mov     rbx, rcx
0x1801e9027  mov     r8, [rcx+8]
0x1801e902b  lea     rdi, [rcx+28h]
0x1801e902f  test    r8, r8
0x1801e9032  jz      short loc_1801E905D
0x1801e9034  mov     rcx, [rdi]
0x1801e9037  mov     rax, [rcx]
0x1801e903a  mov     edx, [rbx]
0x1801e903c  mov     rax, [rax+28h]
0x1801e9040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9045  mov     rcx, [rbx+8]; Block
0x1801e9049  call    cs:__imp_free
0x1801e9050  nop     dword ptr [rax+rax+00h]
0x1801e9055  mov     qword ptr [rbx+8], 0
0x1801e905d  mov     rcx, [rbx+18h]; pv
0x1801e9061  test    rcx, rcx
0x1801e9064  jz      short loc_1801E907A
0x1801e9066  call    cs:__imp_CoTaskMemFree
0x1801e906d  nop     dword ptr [rax+rax+00h]
0x1801e9072  mov     qword ptr [rbx+18h], 0
0x1801e907a  mov     rcx, [rdi]
0x1801e907d  test    rcx, rcx
0x1801e9080  jz      short loc_1801E9095
0x1801e9082  mov     rax, [rcx]
0x1801e9085  mov     rax, [rax+10h]
0x1801e9089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e908e  mov     qword ptr [rdi], 0
0x1801e9095  mov     rbx, [rsp+38h+arg_8]
0x1801e909a  add     rsp, 30h
0x1801e909e  pop     rdi
0x1801e909f  retn
```
