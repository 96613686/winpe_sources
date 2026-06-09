# CGhostMgr::CleanupGhostThreads(int)

- ea: `0x180007b74`
- end: `0x180007c23`
- name: `?CleanupGhostThreads@CGhostMgr@@AEAAXH@Z`
- size: `175`
- prototype: `void __fastcall(CGhostMgr *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007ac8`

## callees

- `0x180001190`
- `0x180001962`
- `0x180005d04`
- `0x180005d34`
- `0x180007b74`
- `0x180008b38`
- `0x180009f60`
- `0x180009f70`
- `0x18000c010`

## pseudocode

```c
void __fastcall CGhostMgr::CleanupGhostThreads(CGhostMgr *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  CDynamicCountedObjectArray *v3; // rsi
  unsigned int i; // ebx
  CGhostThread *v5; // rax
  _BYTE v6[512]; // [rsp+30h] [rbp-218h] BYREF

  memset_0(v6, 0, sizeof(v6));
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (CGhostMgr *)((char *)this + 56);
  for ( i = CDynamicArray::GetCount((CGhostMgr *)((char *)this + 56));
        i;
        (*(void (__fastcall **)(CDynamicCountedObjectArray *, _QWORD))(*(_QWORD *)v3 + 16LL))(v3, i) )
  {
    v5 = CDynamicCountedObjectArray::Get(v3, --i);
    CGhostThread::ShutdownGhostThread(v5, 0);
  }
  CLock::Release(v2);
}

```

## disassembly

```asm
0x180007b74  mov     [rsp+arg_8], rbx
0x180007b79  mov     [rsp+arg_10], rsi
0x180007b7e  push    rdi
0x180007b7f  sub     rsp, 240h
0x180007b86  mov     rax, cs:__security_cookie
0x180007b8d  xor     rax, rsp
0x180007b90  mov     [rsp+248h+var_18], rax
0x180007b98  mov     rbx, rcx
0x180007b9b  xor     edx, edx; Val
0x180007b9d  lea     rcx, [rsp+248h+var_218]; void *
0x180007ba2  mov     r8d, 200h; Size
0x180007ba8  call    memset_0
0x180007bad  lea     rdi, [rbx+10h]
0x180007bb1  mov     rcx, rdi; lpCriticalSection
0x180007bb4  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180007bb9  lea     rsi, [rbx+38h]
0x180007bbd  mov     rcx, rsi; this
0x180007bc0  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180007bc5  mov     ebx, eax
0x180007bc7  test    eax, eax
0x180007bc9  jz      short loc_180007BF6
0x180007bcb  dec     ebx
0x180007bcd  mov     rcx, rsi; this
0x180007bd0  mov     edx, ebx; unsigned int
0x180007bd2  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x180007bd7  xor     edx, edx; void **
0x180007bd9  mov     rcx, rax; this
0x180007bdc  call    ?ShutdownGhostThread@CGhostThread@@QEAAHPEAPEAX@Z; CGhostThread::ShutdownGhostThread(void * *)
0x180007be1  mov     rax, [rsi]
0x180007be4  mov     edx, ebx
0x180007be6  mov     rcx, rsi
0x180007be9  mov     rax, [rax+10h]
0x180007bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf2  test    ebx, ebx
0x180007bf4  jnz     short loc_180007BCB
0x180007bf6  mov     rcx, rdi; lpCriticalSection
0x180007bf9  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180007bfe  mov     rcx, [rsp+248h+var_18]
0x180007c06  xor     rcx, rsp; StackCookie
0x180007c09  call    __security_check_cookie
0x180007c0e  lea     r11, [rsp+248h+var_8]
0x180007c16  mov     rbx, [r11+18h]
0x180007c1a  mov     rsi, [r11+20h]
0x180007c1e  mov     rsp, r11
0x180007c21  pop     rdi
0x180007c22  retn
```
