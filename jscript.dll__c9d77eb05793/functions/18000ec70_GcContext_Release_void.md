# GcContext::Release(void)

- ea: `0x18000ec70`
- end: `0x18000ecb7`
- name: `?Release@GcContext@@QEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(GcContext *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b970`
- `0x18000cc8c`
- `0x18000e870`
- `0x18000ea20`
- `0x180034a54`

## callees

- `0x18000ec70`
- `0x180057694`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000eca7`
- `KERNEL32!DeleteCriticalSection` at `0x18000eca7`

## pseudocode

```c
__int64 __fastcall GcContext::Release(GcContext *this)
{
  unsigned __int32 v2; // ebx
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this);
  if ( !v2 && this )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
    if ( BYTE1(v4[1].DebugInfo) )
      DeleteCriticalSection(v4);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ec70  mov     [rsp+arg_0], rbx
0x18000ec75  push    rdi
0x18000ec76  sub     rsp, 20h
0x18000ec7a  mov     rdi, rcx
0x18000ec7d  mov     ebx, 0FFFFFFFFh
0x18000ec82  lock xadd [rcx], ebx
0x18000ec86  sub     ebx, 1
0x18000ec89  jnz     short loc_18000EC90
0x18000ec8b  test    rcx, rcx
0x18000ec8e  jnz     short loc_18000EC9D
0x18000ec90  mov     eax, ebx
0x18000ec92  mov     rbx, [rsp+28h+arg_0]
0x18000ec97  add     rsp, 20h
0x18000ec9b  pop     rdi
0x18000ec9c  retn
0x18000ec9d  add     rcx, 38h ; '8'; lpCriticalSection
0x18000eca1  cmp     byte ptr [rcx+29h], 0
0x18000eca5  jz      short loc_18000ECAD
0x18000eca7  call    cs:__imp_DeleteCriticalSection
0x18000ecad  mov     rcx, rdi; Block
0x18000ecb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ecb5  jmp     short loc_18000EC90
```
