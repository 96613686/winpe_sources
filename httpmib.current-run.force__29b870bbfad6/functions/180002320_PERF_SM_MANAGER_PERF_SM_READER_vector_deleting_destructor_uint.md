# PERF_SM_MANAGER::PERF_SM_READER::`vector deleting destructor'(uint)

- ea: `0x180002320`
- end: `0x18000238d`
- name: `??_EPERF_SM_READER@PERF_SM_MANAGER@@UEAAPEAXI@Z`
- size: `109`
- prototype: `void *__fastcall(PERF_SM_MANAGER::PERF_SM_READER *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001928`
- `0x180002290`
- `0x180002320`

## pseudocode

```c
PERF_SM_MANAGER::PERF_SM_READER *__fastcall PERF_SM_MANAGER::PERF_SM_READER::`vector deleting destructor'(
        PERF_SM_MANAGER::PERF_SM_READER *this,
        char a2)
{
  char *v4; // r14
  __int64 v5; // rdi
  PERF_SM_MANAGER::PERF_SM_READER *i; // rbx

  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    v5 = *((_QWORD *)this - 1);
    for ( i = (PERF_SM_MANAGER::PERF_SM_READER *)((char *)this + 72 * v5); v5; --v5 )
    {
      i = (PERF_SM_MANAGER::PERF_SM_READER *)((char *)i - 72);
      PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(i);
    }
    if ( (a2 & 1) != 0 )
      operator delete(v4);
    return (PERF_SM_MANAGER::PERF_SM_READER *)v4;
  }
  else
  {
    PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(this);
    if ( (a2 & 1) != 0 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x180002320  push    rbx
0x180002322  push    rsi
0x180002323  push    rdi
0x180002324  push    r14
0x180002326  sub     rsp, 28h
0x18000232a  mov     esi, edx
0x18000232c  mov     rbx, rcx
0x18000232f  test    dl, 2
0x180002332  jz      short loc_18000236D
0x180002334  lea     r14, [rcx-8]
0x180002338  mov     rdi, [r14]
0x18000233b  lea     rax, [rdi+rdi*8]
0x18000233f  lea     rbx, [rcx+rax*8]
0x180002343  test    rdi, rdi
0x180002346  jz      short loc_18000235A
0x180002348  sub     rbx, 48h ; 'H'
0x18000234c  mov     rcx, rbx; this
0x18000234f  call    ??1PERF_SM_READER@PERF_SM_MANAGER@@UEAA@XZ; PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(void)
0x180002354  sub     rdi, 1
0x180002358  jnz     short loc_180002348
0x18000235a  test    sil, 1
0x18000235e  jz      short loc_180002368
0x180002360  mov     rcx, r14; Block
0x180002363  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002368  mov     rax, r14
0x18000236b  jmp     short loc_180002383
0x18000236d  call    ??1PERF_SM_READER@PERF_SM_MANAGER@@UEAA@XZ; PERF_SM_MANAGER::PERF_SM_READER::~PERF_SM_READER(void)
0x180002372  test    sil, 1
0x180002376  jz      short loc_180002380
0x180002378  mov     rcx, rbx; Block
0x18000237b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002380  mov     rax, rbx
0x180002383  add     rsp, 28h
0x180002387  pop     r14
0x180002389  pop     rdi
0x18000238a  pop     rsi
0x18000238b  pop     rbx
0x18000238c  retn
```
