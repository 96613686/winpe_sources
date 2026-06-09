# GcContext::Release(void)

- ea: `0x18000beb0`
- end: `0x18000befe`
- name: `?Release@GcContext@@QEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(GcContext *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008ad0`
- `0x180009e28`
- `0x18000ba90`
- `0x18000bc50`
- `0x18003b8e0`

## callees

- `0x18000beb0`
- `0x1800585c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000bee8`
- `KERNEL32!DeleteCriticalSection` at `0x18000bee8`

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
0x18000beb0  mov     [rsp+arg_0], rbx
0x18000beb5  push    rdi
0x18000beb6  sub     rsp, 20h
0x18000beba  mov     rdi, rcx
0x18000bebd  mov     ebx, 0FFFFFFFFh
0x18000bec2  lock xadd [rcx], ebx
0x18000bec6  sub     ebx, 1
0x18000bec9  jnz     short loc_18000BED0
0x18000becb  test    rcx, rcx
0x18000bece  jnz     short loc_18000BEDE
0x18000bed0  mov     eax, ebx
0x18000bed2  mov     rbx, [rsp+28h+arg_0]
0x18000bed7  add     rsp, 20h
0x18000bedb  pop     rdi
0x18000bedc  retn
0x18000bede  add     rcx, 38h ; '8'; lpCriticalSection
0x18000bee2  cmp     byte ptr [rcx+29h], 0
0x18000bee6  jz      short loc_18000BEF4
0x18000bee8  call    cs:__imp_DeleteCriticalSection
0x18000beef  nop     dword ptr [rax+rax+00h]
0x18000bef4  mov     rcx, rdi; Block
0x18000bef7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000befc  jmp     short loc_18000BED0
```
