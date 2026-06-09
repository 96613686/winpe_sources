# CUSTOM_LOG_FIELDS::`vector deleting destructor'(uint)

- ea: `0x180003194`
- end: `0x1800031e9`
- name: `??_ECUSTOM_LOG_FIELDS@@QEAAPEAXI@Z`
- size: `85`
- prototype: `void *__fastcall(CUSTOM_LOG_FIELDS *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001cd0`
- `0x180003154`

## callees

- `0x1800025f0`
- `0x180003120`
- `0x180003194`

## pseudocode

```c
char *__fastcall CUSTOM_LOG_FIELDS::`vector deleting destructor'(CUSTOM_LOG_FIELDS *this)
{
  char *v1; // rsi
  __int64 v2; // rbx
  CUSTOM_LOG_FIELDS *i; // rdi

  v1 = (char *)this - 8;
  v2 = *((_QWORD *)this - 1);
  for ( i = (CUSTOM_LOG_FIELDS *)((char *)this + 176 * v2); v2; --v2 )
  {
    i = (CUSTOM_LOG_FIELDS *)((char *)i - 176);
    CUSTOM_LOG_FIELDS::~CUSTOM_LOG_FIELDS(i);
  }
  operator delete(v1);
  return v1;
}

```

## disassembly

```asm
0x180003194  mov     [rsp+arg_0], rbx
0x180003199  mov     [rsp+arg_8], rsi
0x18000319e  push    rdi
0x18000319f  sub     rsp, 20h
0x1800031a3  lea     rsi, [rcx-8]
0x1800031a7  mov     rbx, [rsi]
0x1800031aa  imul    rdi, rbx, 0B0h
0x1800031b1  add     rdi, rcx
0x1800031b4  test    rbx, rbx
0x1800031b7  jz      short loc_1800031CE
0x1800031b9  sub     rdi, 0B0h
0x1800031c0  mov     rcx, rdi; this
0x1800031c3  call    ??1CUSTOM_LOG_FIELDS@@QEAA@XZ; CUSTOM_LOG_FIELDS::~CUSTOM_LOG_FIELDS(void)
0x1800031c8  sub     rbx, 1
0x1800031cc  jnz     short loc_1800031B9
0x1800031ce  mov     rcx, rsi; Block
0x1800031d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800031d6  mov     rbx, [rsp+28h+arg_0]
0x1800031db  mov     rax, rsi
0x1800031de  mov     rsi, [rsp+28h+arg_8]
0x1800031e3  add     rsp, 20h
0x1800031e7  pop     rdi
0x1800031e8  retn
```
