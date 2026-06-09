# LuafvEnumerateFileTable

- ea: `0x14001fdd0`
- end: `0x1400200f3`
- name: `LuafvEnumerateFileTable`
- size: `803`
- prototype: `void __fastcall(__int64, char, void (__fastcall *)(__int64, __int64), void (__fastcall *)(__int64, __int64), __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140015e28`
- `0x140016080`
- `0x140016114`
- `0x140016670`
- `0x14001e720`
- `0x14001ef70`

## callees

- `0x140005c90`
- `0x14001fda8`
- `0x14001fdd0`
- `0x1400200fc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe35`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe74`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fea6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fee5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ffc3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020031`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020074`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400200cf`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe35`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe74`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fea6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fee5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ffc3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020031`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020074`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400200cf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe12`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe55`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe83`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fec6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ff86`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002000e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020051`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020092`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe12`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe55`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe83`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fec6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ff86`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002000e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020051`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020092`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ffb4`
- `FLTMGR!FltReleasePushLockEx` at `0x1400200c0`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ffb4`
- `FLTMGR!FltReleasePushLockEx` at `0x1400200c0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001fe46`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001feb7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020042`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001fe46`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001feb7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020042`

## pseudocode

```c
void __fastcall LuafvEnumerateFileTable(
        __int64 a1,
        char a2,
        void (__fastcall *a3)(__int64, __int64),
        void (__fastcall *a4)(__int64, __int64),
        __int64 a5)
{
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 i; // rax
  __int64 v15; // rbx
  bool v16; // zf
  __int64 v17; // rbx
  __int64 v18; // rax

  if ( !a2 )
  {
    v9 = *(_QWORD *)(a1 + 32);
    if ( v9 )
    {
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(v9 + 8) == KeGetCurrentThread() )
      {
        ++*(_DWORD *)(v9 + 16);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v9, 0);
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)(v9 + 8) = KeGetCurrentThread();
        *(_DWORD *)(v9 + 16) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
    }
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a1 + 8) == KeGetCurrentThread() )
    {
      ++*(_DWORD *)(a1 + 16);
    }
    else
    {
      ExReleaseFastMutex(&FastMutex);
      FltAcquirePushLockExclusiveEx(a1, 0);
      ExAcquireFastMutex(&FastMutex);
      *(_QWORD *)(a1 + 8) = KeGetCurrentThread();
      *(_DWORD *)(a1 + 16) = 1;
    }
    ExReleaseFastMutex(&FastMutex);
  }
  v10 = a1;
LABEL_12:
  if ( a3 )
    a3(v10, a5);
  v11 = *(_QWORD *)(v10 + 40);
  if ( v11 )
  {
    v13 = *(_QWORD *)(v10 + 40);
    *(_QWORD *)(v11 + 8) = 0;
    for ( i = LuafvEnumerateTableWithoutSplaying(v13, v11 + 8); ; i = LuafvEnumerateTable(v11, 0) )
    {
      v12 = i;
      if ( !i || (*(_BYTE *)(i + 24) & 7) != 1 )
        break;
    }
  }
  else
  {
    v12 = 0;
  }
  while ( 1 )
  {
    if ( v12 )
    {
      v10 = v12 - 48;
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(v10 + 8) == KeGetCurrentThread() )
      {
        ++*(_DWORD *)(v10 + 16);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v10, 0);
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)(v10 + 8) = KeGetCurrentThread();
        *(_DWORD *)(v10 + 16) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
      goto LABEL_12;
    }
    v15 = *(_QWORD *)(v10 + 32);
    if ( a4 )
    {
      a4(v10, a5);
      goto LABEL_30;
    }
    if ( v10 == a1 && a2 )
      return;
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v10 + 8) != KeGetCurrentThread() )
      goto LABEL_28;
    v16 = (*(_DWORD *)(v10 + 16))-- == 1;
    if ( v16 )
    {
      *(_QWORD *)(v10 + 8) = 0;
LABEL_28:
      FltReleasePushLockEx(v10, 0);
    }
    ExReleaseFastMutex(&FastMutex);
LABEL_30:
    if ( v10 == a1 )
      break;
    v10 = v15;
    v17 = *(_QWORD *)(v15 + 40);
    do
    {
      v18 = LuafvEnumerateTableWithoutSplaying(v17, v17 + 8);
      v12 = v18;
    }
    while ( v18 && (*(_BYTE *)(v18 + 24) & 7) == 1 );
  }
  if ( !a2 && v15 )
  {
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v15 + 8) != KeGetCurrentThread() )
      goto LABEL_44;
    v16 = (*(_DWORD *)(v15 + 16))-- == 1;
    if ( v16 )
    {
      *(_QWORD *)(v15 + 8) = 0;
LABEL_44:
      FltReleasePushLockEx(v15, 0);
    }
    ExReleaseFastMutex(&FastMutex);
  }
}

```

## disassembly

```asm
0x14001fdd0  mov     [rsp+arg_0], rbx
0x14001fdd5  mov     [rsp+arg_10], rbp
0x14001fdda  push    rsi
0x14001fddb  push    rdi
0x14001fddc  push    r12
0x14001fdde  push    r14
0x14001fde0  push    r15
0x14001fde2  sub     rsp, 20h
0x14001fde6  lea     rbp, FastMutex
0x14001fded  mov     r12, r9
0x14001fdf0  mov     r15, r8
0x14001fdf3  mov     r14b, dl
0x14001fdf6  mov     rsi, rcx
0x14001fdf9  mov     edi, 1
0x14001fdfe  test    dl, dl
0x14001fe00  jnz     loc_14001FEF1
0x14001fe06  mov     rbx, [rcx+20h]
0x14001fe0a  test    rbx, rbx
0x14001fe0d  jz      short loc_14001FE80
0x14001fe0f  mov     rcx, rbp; FastMutex
0x14001fe12  call    cs:__imp_ExAcquireFastMutex
0x14001fe19  nop     dword ptr [rax+rax+00h]
0x14001fe1e  mov     rax, gs:188h
0x14001fe27  cmp     [rbx+8], rax
0x14001fe2b  jnz     short loc_14001FE32
0x14001fe2d  add     [rbx+10h], edi
0x14001fe30  jmp     short loc_14001FE71
0x14001fe32  mov     rcx, rbp; FastMutex
0x14001fe35  call    cs:__imp_ExReleaseFastMutex
0x14001fe3c  nop     dword ptr [rax+rax+00h]
0x14001fe41  xor     edx, edx
0x14001fe43  mov     rcx, rbx
0x14001fe46  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001fe4d  nop     dword ptr [rax+rax+00h]
0x14001fe52  mov     rcx, rbp; FastMutex
0x14001fe55  call    cs:__imp_ExAcquireFastMutex
0x14001fe5c  nop     dword ptr [rax+rax+00h]
0x14001fe61  mov     rax, gs:188h
0x14001fe6a  mov     [rbx+8], rax
0x14001fe6e  mov     [rbx+10h], edi
0x14001fe71  mov     rcx, rbp; FastMutex
0x14001fe74  call    cs:__imp_ExReleaseFastMutex
0x14001fe7b  nop     dword ptr [rax+rax+00h]
0x14001fe80  mov     rcx, rbp; FastMutex
0x14001fe83  call    cs:__imp_ExAcquireFastMutex
0x14001fe8a  nop     dword ptr [rax+rax+00h]
0x14001fe8f  mov     rax, gs:188h
0x14001fe98  cmp     [rsi+8], rax
0x14001fe9c  jnz     short loc_14001FEA3
0x14001fe9e  add     [rsi+10h], edi
0x14001fea1  jmp     short loc_14001FEE2
0x14001fea3  mov     rcx, rbp; FastMutex
0x14001fea6  call    cs:__imp_ExReleaseFastMutex
0x14001fead  nop     dword ptr [rax+rax+00h]
0x14001feb2  xor     edx, edx
0x14001feb4  mov     rcx, rsi
0x14001feb7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001febe  nop     dword ptr [rax+rax+00h]
0x14001fec3  mov     rcx, rbp; FastMutex
0x14001fec6  call    cs:__imp_ExAcquireFastMutex
0x14001fecd  nop     dword ptr [rax+rax+00h]
0x14001fed2  mov     rax, gs:188h
0x14001fedb  mov     [rsi+8], rax
0x14001fedf  mov     [rsi+10h], edi
0x14001fee2  mov     rcx, rbp; FastMutex
0x14001fee5  call    cs:__imp_ExReleaseFastMutex
0x14001feec  nop     dword ptr [rax+rax+00h]
0x14001fef1  mov     rdi, rsi
0x14001fef4  test    r15, r15
0x14001fef7  jz      short loc_14001FF09
0x14001fef9  mov     rdx, [rsp+48h+arg_20]
0x14001fefe  mov     rcx, rdi
0x14001ff01  mov     rax, r15
0x14001ff04  call    _guard_dispatch_icall
0x14001ff09  mov     rbx, [rdi+28h]
0x14001ff0d  test    rbx, rbx
0x14001ff10  jnz     short loc_14001FF16
0x14001ff12  xor     edx, edx
0x14001ff14  jmp     short loc_14001FF51
0x14001ff16  lea     rdx, [rbx+8]
0x14001ff1a  mov     rcx, rbx
0x14001ff1d  mov     qword ptr [rdx], 0
0x14001ff24  call    LuafvEnumerateTableWithoutSplaying
0x14001ff29  jmp     short loc_14001FF40
0x14001ff2b  mov     cl, [rdx+18h]
0x14001ff2e  and     cl, 7
0x14001ff31  cmp     cl, 1
0x14001ff34  jnz     short loc_14001FF51
0x14001ff36  xor     edx, edx
0x14001ff38  mov     rcx, rbx
0x14001ff3b  call    LuafvEnumerateTable
0x14001ff40  mov     rdx, rax
0x14001ff43  test    rax, rax
0x14001ff46  jnz     short loc_14001FF2B
0x14001ff48  jmp     short loc_14001FF51
0x14001ff4a  lea     rbp, FastMutex
0x14001ff51  test    rdx, rdx
0x14001ff54  jnz     loc_140020007
0x14001ff5a  mov     rbx, [rdi+20h]
0x14001ff5e  test    r12, r12
0x14001ff61  jz      short loc_14001FF75
0x14001ff63  mov     rdx, [rsp+48h+arg_20]
0x14001ff68  mov     rcx, rdi
0x14001ff6b  mov     rax, r12
0x14001ff6e  call    _guard_dispatch_icall
0x14001ff73  jmp     short loc_14001FFCF
0x14001ff75  cmp     rdi, rsi
0x14001ff78  jnz     short loc_14001FF83
0x14001ff7a  test    r14b, r14b
0x14001ff7d  jnz     loc_1400200DB
0x14001ff83  mov     rcx, rbp; FastMutex
0x14001ff86  call    cs:__imp_ExAcquireFastMutex
0x14001ff8d  nop     dword ptr [rax+rax+00h]
0x14001ff92  mov     rax, gs:188h
0x14001ff9b  cmp     [rdi+8], rax
0x14001ff9f  jnz     short loc_14001FFAF
0x14001ffa1  sub     dword ptr [rdi+10h], 1
0x14001ffa5  jnz     short loc_14001FFC0
0x14001ffa7  mov     qword ptr [rdi+8], 0
0x14001ffaf  xor     edx, edx
0x14001ffb1  mov     rcx, rdi
0x14001ffb4  call    cs:__imp_FltReleasePushLockEx
0x14001ffbb  nop     dword ptr [rax+rax+00h]
0x14001ffc0  mov     rcx, rbp; FastMutex
0x14001ffc3  call    cs:__imp_ExReleaseFastMutex
0x14001ffca  nop     dword ptr [rax+rax+00h]
0x14001ffcf  cmp     rdi, rsi
0x14001ffd2  jz      loc_140020085
0x14001ffd8  mov     rdi, rbx
0x14001ffdb  mov     rbx, [rbx+28h]
0x14001ffdf  jmp     short loc_14001FFEE
0x14001ffe1  mov     al, [rdx+18h]
0x14001ffe4  and     al, 7
0x14001ffe6  cmp     al, 1
0x14001ffe8  jnz     loc_14001FF4A
0x14001ffee  lea     rdx, [rbx+8]
0x14001fff2  mov     rcx, rbx
0x14001fff5  call    LuafvEnumerateTableWithoutSplaying
0x14001fffa  mov     rdx, rax
0x14001fffd  test    rax, rax
0x140020000  jnz     short loc_14001FFE1
0x140020002  jmp     loc_14001FF4A
0x140020007  mov     rcx, rbp; FastMutex
0x14002000a  lea     rdi, [rdx-30h]
0x14002000e  call    cs:__imp_ExAcquireFastMutex
0x140020015  nop     dword ptr [rax+rax+00h]
0x14002001a  mov     rax, gs:188h
0x140020023  cmp     [rdi+8], rax
0x140020027  jnz     short loc_14002002E
0x140020029  inc     dword ptr [rdi+10h]
0x14002002c  jmp     short loc_140020071
0x14002002e  mov     rcx, rbp; FastMutex
0x140020031  call    cs:__imp_ExReleaseFastMutex
0x140020038  nop     dword ptr [rax+rax+00h]
0x14002003d  xor     edx, edx
0x14002003f  mov     rcx, rdi
0x140020042  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140020049  nop     dword ptr [rax+rax+00h]
0x14002004e  mov     rcx, rbp; FastMutex
0x140020051  call    cs:__imp_ExAcquireFastMutex
0x140020058  nop     dword ptr [rax+rax+00h]
0x14002005d  mov     rax, gs:188h
0x140020066  mov     [rdi+8], rax
0x14002006a  mov     dword ptr [rdi+10h], 1
0x140020071  mov     rcx, rbp; FastMutex
0x140020074  call    cs:__imp_ExReleaseFastMutex
0x14002007b  nop     dword ptr [rax+rax+00h]
0x140020080  jmp     loc_14001FEF4
0x140020085  test    r14b, r14b
0x140020088  jnz     short loc_1400200DB
0x14002008a  test    rbx, rbx
0x14002008d  jz      short loc_1400200DB
0x14002008f  mov     rcx, rbp; FastMutex
0x140020092  call    cs:__imp_ExAcquireFastMutex
0x140020099  nop     dword ptr [rax+rax+00h]
0x14002009e  mov     rax, gs:188h
0x1400200a7  cmp     [rbx+8], rax
0x1400200ab  jnz     short loc_1400200BB
0x1400200ad  sub     dword ptr [rbx+10h], 1
0x1400200b1  jnz     short loc_1400200CC
0x1400200b3  mov     qword ptr [rbx+8], 0
0x1400200bb  xor     edx, edx
0x1400200bd  mov     rcx, rbx
0x1400200c0  call    cs:__imp_FltReleasePushLockEx
0x1400200c7  nop     dword ptr [rax+rax+00h]
0x1400200cc  mov     rcx, rbp; FastMutex
0x1400200cf  call    cs:__imp_ExReleaseFastMutex
0x1400200d6  nop     dword ptr [rax+rax+00h]
0x1400200db  mov     rbx, [rsp+48h+arg_0]
0x1400200e0  mov     rbp, [rsp+48h+arg_10]
0x1400200e5  add     rsp, 20h
0x1400200e9  pop     r15
0x1400200eb  pop     r14
0x1400200ed  pop     r12
0x1400200ef  pop     rdi
0x1400200f0  pop     rsi
0x1400200f1  retn
```
