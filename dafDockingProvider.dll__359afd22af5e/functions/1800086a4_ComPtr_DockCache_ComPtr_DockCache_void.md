# ComPtr<DockCache>::~ComPtr<DockCache>(void)

- ea: `0x1800086a4`
- end: `0x1800086e8`
- name: `??1?$ComPtr@VDockCache@@@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d09b`
- `0x18001dca7`

## callees

- `0x1800014d0`
- `0x1800086a4`
- `0x18001134c`

## pseudocode

```c
void __fastcall ComPtr<DockCache>::~ComPtr<DockCache>(volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(v1 + 24, 0xFFFFFFFF) == 1 )
    {
      DockCache::~DockCache((DockCache *)v1);
      operator delete((void *)v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1800086a4  mov     [rsp+arg_8], rbx
0x1800086a9  push    rdi
0x1800086aa  sub     rsp, 20h
0x1800086ae  mov     rbx, [rcx]
0x1800086b1  mov     rdi, rcx
0x1800086b4  test    rbx, rbx
0x1800086b7  jz      short loc_1800086DD
0x1800086b9  or      eax, 0FFFFFFFFh
0x1800086bc  lock xadd [rbx+60h], eax
0x1800086c1  cmp     eax, 1
0x1800086c4  jnz     short loc_1800086D6
0x1800086c6  mov     rcx, rbx; this
0x1800086c9  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x1800086ce  mov     rcx, rbx; Block
0x1800086d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800086d6  mov     qword ptr [rdi], 0
0x1800086dd  mov     rbx, [rsp+28h+arg_8]
0x1800086e2  add     rsp, 20h
0x1800086e6  pop     rdi
0x1800086e7  retn
```
