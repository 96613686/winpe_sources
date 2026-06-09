# CallStackContext::CallStackContext(ulong,ulong)

- ea: `0x180001c60`
- end: `0x180001cd2`
- name: `??0CallStackContext@@QEAA@KK@Z`
- size: `114`
- prototype: `CallStackContext *__fastcall(CallStackContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004338`
- `0x1800049b0`

## callees

- `0x180001c60`
- `0x180001ce0`
- `0x180001cf0`
- `0x18000389c`

## pseudocode

```c
CallStackContext *__fastcall CallStackContext::CallStackContext(CallStackContext *this, int a2, unsigned int a3)
{
  int v3; // r14d
  __int64 v5; // rbx
  CallStackInfo *v8; // rdi
  CallStackContext *result; // rax

  v3 = 124;
  v5 = 124;
  v8 = this;
  do
  {
    CallStackInfo::CallStackInfo(v8);
    v8 = (CallStackInfo *)((char *)v8 + 16);
    --v5;
  }
  while ( v5 );
  if ( a3 < 0x7C )
    v3 = a3;
  *((_DWORD *)this + 498) = v3;
  memset_0(this, 0, 0x7C0u);
  CallStackContext::ClearState((GUID *)this);
  result = this;
  *((_DWORD *)this + 496) = a2;
  return result;
}

```

## disassembly

```asm
0x180001c60  push    rbx
0x180001c62  push    rbp
0x180001c63  push    rsi
0x180001c64  push    rdi
0x180001c65  push    r14
0x180001c67  push    r15
0x180001c69  sub     rsp, 28h
0x180001c6d  mov     r14d, 7Ch ; '|'
0x180001c73  mov     ebp, r8d
0x180001c76  mov     ebx, r14d
0x180001c79  mov     r15d, edx
0x180001c7c  mov     rsi, rcx
0x180001c7f  mov     rdi, rcx
0x180001c82  mov     rcx, rdi; this
0x180001c85  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x180001c8a  add     rdi, 10h
0x180001c8e  sub     rbx, 1
0x180001c92  jnz     short loc_180001C82
0x180001c94  cmp     ebp, r14d
0x180001c97  jnb     short loc_180001C9C
0x180001c99  mov     r14, rbp
0x180001c9c  xor     edx, edx; Val
0x180001c9e  mov     [rsi+7C8h], r14d
0x180001ca5  mov     r8d, 7C0h; Size
0x180001cab  mov     rcx, rsi; void *
0x180001cae  call    memset_0
0x180001cb3  mov     rcx, rsi; this
0x180001cb6  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180001cbb  mov     rax, rsi
0x180001cbe  mov     [rsi+7C0h], r15d
0x180001cc5  add     rsp, 28h
0x180001cc9  pop     r15
0x180001ccb  pop     r14
0x180001ccd  pop     rdi
0x180001cce  pop     rsi
0x180001ccf  pop     rbp
0x180001cd0  pop     rbx
0x180001cd1  retn
```
