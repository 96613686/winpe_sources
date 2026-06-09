# Recycler::AbortConcurrent(bool)

- ea: `0x180258618`
- end: `0x18025871e`
- name: `?AbortConcurrent@Recycler@@AEAA_N_N@Z`
- size: `262`
- prototype: `bool __fastcall(Recycler *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180258a90`

## callees

- `0x1800936a0`
- `0x180258618`
- `0x1802587b8`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258693`
- `KERNEL32!SetThreadPriority` at `0x180258693`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1802586b2`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1802586b2`

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
  ArenaAllocator *v8; // rbp
  char *v9; // rsi
  char *i; // rdx
  char *v11; // rbx
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
    v8 = (ArenaAllocator *)*((_QWORD *)this + 2020);
    v9 = (char *)this + 12928;
    for ( i = (char *)*((_QWORD *)this + 1616); i != v9; i = v11 )
    {
      v11 = *(char **)i;
      ArenaAllocatorBase<InPlaceFreeListPolicy>::Free(v8, i, 16);
    }
    *(_QWORD *)v9 = v9;
    Recycler::CleanupPendingUnroot(this);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180258618  mov     r11, rsp
0x18025861b  mov     [r11+18h], rbx
0x18025861f  mov     [r11+20h], rbp
0x180258623  mov     [rsp+arg_8], dl
0x180258627  mov     [r11+8], rcx
0x18025862b  push    rsi
0x18025862c  push    rdi
0x18025862d  push    r14
0x18025862f  sub     rsp, 40h
0x180258633  mov     rax, [rcx+3290h]
0x18025863a  mov     rdi, rcx
0x18025863d  mov     rcx, [rcx+3298h]; hThread
0x180258644  mov     ebp, 1
0x180258649  mov     [r11-28h], rax
0x18025864d  mov     rax, rcx
0x180258650  neg     rax
0x180258653  mov     [r11-20h], rcx
0x180258657  mov     eax, [rdi]
0x180258659  sbb     esi, esi
0x18025865b  xor     r14d, r14d
0x18025865e  neg     esi
0x180258660  add     esi, ebp
0x180258662  bt      eax, 0Dh
0x180258666  jnb     loc_180258704
0x18025866c  mov     edx, 6001h
0x180258671  and     eax, edx
0x180258673  cmp     eax, edx
0x180258675  jnz     short loc_180258687
0x180258677  mov     rbx, [rdi+168h]
0x18025867e  mov     [rdi+168h], r14
0x180258685  jmp     short loc_18025868C
0x180258687  xor     ebx, ebx
0x180258689  xor     bpl, bpl
0x18025868c  test    rcx, rcx
0x18025868f  jz      short loc_18025869F
0x180258691  xor     edx, edx; nPriority
0x180258693  call    cs:__imp_SetThreadPriority
0x18025869a  nop     dword ptr [rax+rax+00h]
0x18025869f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1802586a3  mov     [rsp+58h+bAlertable], r14d; bAlertable
0x1802586a8  xor     r8d, r8d; bWaitAll
0x1802586ab  lea     rdx, [rsp+58h+Handles]; lpHandles
0x1802586b0  mov     ecx, esi; nCount
0x1802586b2  call    cs:__imp_WaitForMultipleObjectsEx
0x1802586b9  nop     dword ptr [rax+rax+00h]
0x1802586be  mov     r14d, eax
0x1802586c1  test    bpl, bpl
0x1802586c4  jz      short loc_1802586CD
0x1802586c6  mov     [rdi+168h], rbx
0x1802586cd  mov     rbp, [rdi+3F20h]
0x1802586d4  lea     rsi, [rdi+3280h]
0x1802586db  mov     rdx, [rsi]
0x1802586de  cmp     rdx, rsi
0x1802586e1  jz      short loc_1802586F9
0x1802586e3  mov     rbx, [rdx]
0x1802586e6  mov     r8d, 10h
0x1802586ec  mov     rcx, rbp
0x1802586ef  call    ?Free@?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAAXPEAX_K@Z; ArenaAllocatorBase<InPlaceFreeListPolicy>::Free(void *,unsigned __int64)
0x1802586f4  mov     rdx, rbx
0x1802586f7  jmp     short loc_1802586DE
0x1802586f9  mov     rcx, rdi; this
0x1802586fc  mov     [rsi], rsi
0x1802586ff  call    ?CleanupPendingUnroot@Recycler@@AEAAXXZ; Recycler::CleanupPendingUnroot(void)
0x180258704  mov     rbx, [rsp+58h+arg_10]
0x180258709  test    r14d, r14d
0x18025870c  mov     rbp, [rsp+58h+arg_18]
0x180258711  setz    al
0x180258714  add     rsp, 40h
0x180258718  pop     r14
0x18025871a  pop     rdi
0x18025871b  pop     rsi
0x18025871c  retn
```
