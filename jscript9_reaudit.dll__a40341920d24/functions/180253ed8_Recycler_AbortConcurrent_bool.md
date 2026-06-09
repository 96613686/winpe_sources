# Recycler::AbortConcurrent(bool)

- ea: `0x180253ed8`
- end: `0x180253fd1`
- name: `?AbortConcurrent@Recycler@@AEAA_N_N@Z`
- size: `249`
- prototype: `bool __fastcall(Recycler *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180254344`

## callees

- `0x180082350`
- `0x180253ed8`
- `0x18025406c`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180253f53`
- `KERNEL32!SetThreadPriority` at `0x180253f53`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180253f6c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180253f6c`

## pseudocode

```c
bool __fastcall Recycler::AbortConcurrent(Recycler *this)
{
  void *v1; // rax
  void *v3; // rcx
  char v4; // bp
  DWORD v5; // r14d
  DWORD v6; // esi
  __int64 v7; // rbx
  __int64 v8; // rbp
  _QWORD *v9; // rsi
  _QWORD *i; // rdx
  _QWORD *v11; // rbx
  HANDLE Handles[5]; // [rsp+30h] [rbp-28h] BYREF

  v1 = (void *)*((_QWORD *)this + 1618);
  v3 = (void *)*((_QWORD *)this + 1619);
  v4 = 1;
  Handles[0] = v1;
  Handles[1] = v3;
  v5 = 0;
  v6 = (v3 != 0) + 1;
  if ( (*(_DWORD *)this & 0x2000) != 0 )
  {
    if ( (*(_DWORD *)this & 0x6001) == 0x6001 )
    {
      v7 = *((_QWORD *)this + 45);
      *((_QWORD *)this + 45) = 0;
    }
    else
    {
      v7 = 0;
      v4 = 0;
    }
    if ( v3 )
      SetThreadPriority(v3, 0);
    v5 = WaitForMultipleObjectsEx(v6, Handles, 0, 0xFFFFFFFF, 0);
    if ( v4 )
      *((_QWORD *)this + 45) = v7;
    v8 = *((_QWORD *)this + 2020);
    v9 = (_QWORD *)((char *)this + 12928);
    for ( i = (_QWORD *)*((_QWORD *)this + 1616); i != v9; i = v11 )
    {
      v11 = (_QWORD *)*i;
      ArenaAllocatorBase<InPlaceFreeListPolicy>::Free(v8, i, 16);
    }
    *v9 = v9;
    Recycler::CleanupPendingUnroot(this);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180253ed8  mov     r11, rsp
0x180253edb  mov     [r11+18h], rbx
0x180253edf  mov     [r11+20h], rbp
0x180253ee3  mov     [rsp+arg_8], dl
0x180253ee7  mov     [r11+8], rcx
0x180253eeb  push    rsi
0x180253eec  push    rdi
0x180253eed  push    r14
0x180253eef  sub     rsp, 40h
0x180253ef3  mov     rax, [rcx+3290h]
0x180253efa  mov     rdi, rcx
0x180253efd  mov     rcx, [rcx+3298h]; hThread
0x180253f04  mov     ebp, 1
0x180253f09  mov     [r11-28h], rax
0x180253f0d  mov     rax, rcx
0x180253f10  neg     rax
0x180253f13  mov     [r11-20h], rcx
0x180253f17  mov     eax, [rdi]
0x180253f19  sbb     esi, esi
0x180253f1b  xor     r14d, r14d
0x180253f1e  neg     esi
0x180253f20  add     esi, ebp
0x180253f22  bt      eax, 0Dh
0x180253f26  jnb     loc_180253FB8
0x180253f2c  mov     edx, 6001h
0x180253f31  and     eax, edx
0x180253f33  cmp     eax, edx
0x180253f35  jnz     short loc_180253F47
0x180253f37  mov     rbx, [rdi+168h]
0x180253f3e  mov     [rdi+168h], r14
0x180253f45  jmp     short loc_180253F4C
0x180253f47  xor     ebx, ebx
0x180253f49  xor     bpl, bpl
0x180253f4c  test    rcx, rcx
0x180253f4f  jz      short loc_180253F59
0x180253f51  xor     edx, edx; nPriority
0x180253f53  call    cs:__imp_SetThreadPriority
0x180253f59  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180253f5d  mov     [rsp+58h+bAlertable], r14d; bAlertable
0x180253f62  xor     r8d, r8d; bWaitAll
0x180253f65  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180253f6a  mov     ecx, esi; nCount
0x180253f6c  call    cs:__imp_WaitForMultipleObjectsEx
0x180253f72  mov     r14d, eax
0x180253f75  test    bpl, bpl
0x180253f78  jz      short loc_180253F81
0x180253f7a  mov     [rdi+168h], rbx
0x180253f81  mov     rbp, [rdi+3F20h]
0x180253f88  lea     rsi, [rdi+3280h]
0x180253f8f  mov     rdx, [rsi]
0x180253f92  cmp     rdx, rsi
0x180253f95  jz      short loc_180253FAD
0x180253f97  mov     rbx, [rdx]
0x180253f9a  mov     r8d, 10h
0x180253fa0  mov     rcx, rbp
0x180253fa3  call    ?Free@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAAXPEAX_K@Z; ArenaAllocatorBase<InPlaceFreeListPolicy>::Free(void *,unsigned __int64)
0x180253fa8  mov     rdx, rbx
0x180253fab  jmp     short loc_180253F92
0x180253fad  mov     rcx, rdi; this
0x180253fb0  mov     [rsi], rsi
0x180253fb3  call    ?CleanupPendingUnroot@Recycler@@AEAAXXZ; Recycler::CleanupPendingUnroot(void)
0x180253fb8  mov     rbx, [rsp+58h+arg_10]
0x180253fbd  test    r14d, r14d
0x180253fc0  mov     rbp, [rsp+58h+arg_18]
0x180253fc5  setz    al
0x180253fc8  add     rsp, 40h
0x180253fcc  pop     r14
0x180253fce  pop     rdi
0x180253fcf  pop     rsi
0x180253fd0  retn
```
