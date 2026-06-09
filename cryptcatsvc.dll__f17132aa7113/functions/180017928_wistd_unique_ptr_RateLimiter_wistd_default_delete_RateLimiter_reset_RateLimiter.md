# wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)

- ea: `0x180017928`
- end: `0x180017954`
- name: `?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ad54`
- `0x180017328`
- `0x180017614`
- `0x180021d30`

## callees

- `0x18000c210`
- `0x180017274`
- `0x180017928`

## pseudocode

```c
void __fastcall wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(
        RateLimiter **a1,
        RateLimiter *a2)
{
  RateLimiter *v2; // rbx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    RateLimiter::~RateLimiter(v2);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180017928  push    rbx
0x18001792a  sub     rsp, 20h
0x18001792e  mov     rbx, [rcx]
0x180017931  mov     [rcx], rdx
0x180017934  test    rbx, rbx
0x180017937  jz      short loc_18001794E
0x180017939  mov     rcx, rbx; this
0x18001793c  call    ??1RateLimiter@@QEAA@XZ; RateLimiter::~RateLimiter(void)
0x180017941  mov     edx, 10h; unsigned __int64
0x180017946  mov     rcx, rbx; void *
0x180017949  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001794e  add     rsp, 20h
0x180017952  pop     rbx
0x180017953  retn
```
