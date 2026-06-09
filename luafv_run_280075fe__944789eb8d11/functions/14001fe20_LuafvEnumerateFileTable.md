# LuafvEnumerateFileTable

- ea: `0x14001fe20`
- end: `0x140020143`
- name: `LuafvEnumerateFileTable`
- size: `803`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140015e28`
- `0x140016080`
- `0x140016114`
- `0x140016670`
- `0x14001e770`
- `0x14001efc0`

## callees

- `0x140006010`
- `0x14001fdf8`
- `0x14001fe20`
- `0x14002014c`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe85`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fec4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fef6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ff35`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020013`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020081`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400200c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002011f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fe85`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fec4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001fef6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ff35`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020013`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020081`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400200c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002011f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe62`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fea5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fed3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ff16`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ffd6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002005e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400200a1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400200e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fe62`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fea5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001fed3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ff16`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ffd6`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002005e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400200a1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400200e2`
- `FLTMGR!FltReleasePushLockEx` at `0x140020004`
- `FLTMGR!FltReleasePushLockEx` at `0x140020110`
- `FLTMGR!FltReleasePushLockEx` at `0x140020004`
- `FLTMGR!FltReleasePushLockEx` at `0x140020110`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001fe96`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ff07`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020092`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001fe96`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ff07`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020092`

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
    for ( i = LuafvEnumerateTableWithoutSplaying(v13); ; i = LuafvEnumerateTable(v11, 0) )
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
      v18 = LuafvEnumerateTableWithoutSplaying(v17);
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
0x14001fe20  mov     [rsp+arg_0], rbx
0x14001fe25  mov     [rsp+arg_10], rbp
0x14001fe2a  push    rsi
0x14001fe2b  push    rdi
0x14001fe2c  push    r12
0x14001fe2e  push    r14
0x14001fe30  push    r15
0x14001fe32  sub     rsp, 20h
0x14001fe36  lea     rbp, FastMutex
0x14001fe3d  mov     r12, r9
0x14001fe40  mov     r15, r8
0x14001fe43  mov     r14b, dl
0x14001fe46  mov     rsi, rcx
0x14001fe49  mov     edi, 1
0x14001fe4e  test    dl, dl
0x14001fe50  jnz     loc_14001FF41
0x14001fe56  mov     rbx, [rcx+20h]
0x14001fe5a  test    rbx, rbx
0x14001fe5d  jz      short loc_14001FED0
0x14001fe5f  mov     rcx, rbp; FastMutex
0x14001fe62  call    cs:__imp_ExAcquireFastMutex
0x14001fe69  nop     dword ptr [rax+rax+00h]
0x14001fe6e  mov     rax, gs:188h
0x14001fe77  cmp     [rbx+8], rax
0x14001fe7b  jnz     short loc_14001FE82
0x14001fe7d  add     [rbx+10h], edi
0x14001fe80  jmp     short loc_14001FEC1
0x14001fe82  mov     rcx, rbp; FastMutex
0x14001fe85  call    cs:__imp_ExReleaseFastMutex
0x14001fe8c  nop     dword ptr [rax+rax+00h]
0x14001fe91  xor     edx, edx
0x14001fe93  mov     rcx, rbx
0x14001fe96  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001fe9d  nop     dword ptr [rax+rax+00h]
0x14001fea2  mov     rcx, rbp; FastMutex
0x14001fea5  call    cs:__imp_ExAcquireFastMutex
0x14001feac  nop     dword ptr [rax+rax+00h]
0x14001feb1  mov     rax, gs:188h
0x14001feba  mov     [rbx+8], rax
0x14001febe  mov     [rbx+10h], edi
0x14001fec1  mov     rcx, rbp; FastMutex
0x14001fec4  call    cs:__imp_ExReleaseFastMutex
0x14001fecb  nop     dword ptr [rax+rax+00h]
0x14001fed0  mov     rcx, rbp; FastMutex
0x14001fed3  call    cs:__imp_ExAcquireFastMutex
0x14001feda  nop     dword ptr [rax+rax+00h]
0x14001fedf  mov     rax, gs:188h
0x14001fee8  cmp     [rsi+8], rax
0x14001feec  jnz     short loc_14001FEF3
0x14001feee  add     [rsi+10h], edi
0x14001fef1  jmp     short loc_14001FF32
0x14001fef3  mov     rcx, rbp; FastMutex
0x14001fef6  call    cs:__imp_ExReleaseFastMutex
0x14001fefd  nop     dword ptr [rax+rax+00h]
0x14001ff02  xor     edx, edx
0x14001ff04  mov     rcx, rsi
0x14001ff07  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001ff0e  nop     dword ptr [rax+rax+00h]
0x14001ff13  mov     rcx, rbp; FastMutex
0x14001ff16  call    cs:__imp_ExAcquireFastMutex
0x14001ff1d  nop     dword ptr [rax+rax+00h]
0x14001ff22  mov     rax, gs:188h
0x14001ff2b  mov     [rsi+8], rax
0x14001ff2f  mov     [rsi+10h], edi
0x14001ff32  mov     rcx, rbp; FastMutex
0x14001ff35  call    cs:__imp_ExReleaseFastMutex
0x14001ff3c  nop     dword ptr [rax+rax+00h]
0x14001ff41  mov     rdi, rsi
0x14001ff44  test    r15, r15
0x14001ff47  jz      short loc_14001FF59
0x14001ff49  mov     rdx, [rsp+48h+arg_20]
0x14001ff4e  mov     rcx, rdi
0x14001ff51  mov     rax, r15
0x14001ff54  call    _guard_dispatch_icall
0x14001ff59  mov     rbx, [rdi+28h]
0x14001ff5d  test    rbx, rbx
0x14001ff60  jnz     short loc_14001FF66
0x14001ff62  xor     edx, edx
0x14001ff64  jmp     short loc_14001FFA1
0x14001ff66  lea     rdx, [rbx+8]
0x14001ff6a  mov     rcx, rbx
0x14001ff6d  mov     qword ptr [rdx], 0
0x14001ff74  call    LuafvEnumerateTableWithoutSplaying
0x14001ff79  jmp     short loc_14001FF90
0x14001ff7b  mov     cl, [rdx+18h]
0x14001ff7e  and     cl, 7
0x14001ff81  cmp     cl, 1
0x14001ff84  jnz     short loc_14001FFA1
0x14001ff86  xor     edx, edx
0x14001ff88  mov     rcx, rbx
0x14001ff8b  call    LuafvEnumerateTable
0x14001ff90  mov     rdx, rax
0x14001ff93  test    rax, rax
0x14001ff96  jnz     short loc_14001FF7B
0x14001ff98  jmp     short loc_14001FFA1
0x14001ff9a  lea     rbp, FastMutex
0x14001ffa1  test    rdx, rdx
0x14001ffa4  jnz     loc_140020057
0x14001ffaa  mov     rbx, [rdi+20h]
0x14001ffae  test    r12, r12
0x14001ffb1  jz      short loc_14001FFC5
0x14001ffb3  mov     rdx, [rsp+48h+arg_20]
0x14001ffb8  mov     rcx, rdi
0x14001ffbb  mov     rax, r12
0x14001ffbe  call    _guard_dispatch_icall
0x14001ffc3  jmp     short loc_14002001F
0x14001ffc5  cmp     rdi, rsi
0x14001ffc8  jnz     short loc_14001FFD3
0x14001ffca  test    r14b, r14b
0x14001ffcd  jnz     loc_14002012B
0x14001ffd3  mov     rcx, rbp; FastMutex
0x14001ffd6  call    cs:__imp_ExAcquireFastMutex
0x14001ffdd  nop     dword ptr [rax+rax+00h]
0x14001ffe2  mov     rax, gs:188h
0x14001ffeb  cmp     [rdi+8], rax
0x14001ffef  jnz     short loc_14001FFFF
0x14001fff1  sub     dword ptr [rdi+10h], 1
0x14001fff5  jnz     short loc_140020010
0x14001fff7  mov     qword ptr [rdi+8], 0
0x14001ffff  xor     edx, edx
0x140020001  mov     rcx, rdi
0x140020004  call    cs:__imp_FltReleasePushLockEx
0x14002000b  nop     dword ptr [rax+rax+00h]
0x140020010  mov     rcx, rbp; FastMutex
0x140020013  call    cs:__imp_ExReleaseFastMutex
0x14002001a  nop     dword ptr [rax+rax+00h]
0x14002001f  cmp     rdi, rsi
0x140020022  jz      loc_1400200D5
0x140020028  mov     rdi, rbx
0x14002002b  mov     rbx, [rbx+28h]
0x14002002f  jmp     short loc_14002003E
0x140020031  mov     al, [rdx+18h]
0x140020034  and     al, 7
0x140020036  cmp     al, 1
0x140020038  jnz     loc_14001FF9A
0x14002003e  lea     rdx, [rbx+8]
0x140020042  mov     rcx, rbx
0x140020045  call    LuafvEnumerateTableWithoutSplaying
0x14002004a  mov     rdx, rax
0x14002004d  test    rax, rax
0x140020050  jnz     short loc_140020031
0x140020052  jmp     loc_14001FF9A
0x140020057  mov     rcx, rbp; FastMutex
0x14002005a  lea     rdi, [rdx-30h]
0x14002005e  call    cs:__imp_ExAcquireFastMutex
0x140020065  nop     dword ptr [rax+rax+00h]
0x14002006a  mov     rax, gs:188h
0x140020073  cmp     [rdi+8], rax
0x140020077  jnz     short loc_14002007E
0x140020079  inc     dword ptr [rdi+10h]
0x14002007c  jmp     short loc_1400200C1
0x14002007e  mov     rcx, rbp; FastMutex
0x140020081  call    cs:__imp_ExReleaseFastMutex
0x140020088  nop     dword ptr [rax+rax+00h]
0x14002008d  xor     edx, edx
0x14002008f  mov     rcx, rdi
0x140020092  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140020099  nop     dword ptr [rax+rax+00h]
0x14002009e  mov     rcx, rbp; FastMutex
0x1400200a1  call    cs:__imp_ExAcquireFastMutex
0x1400200a8  nop     dword ptr [rax+rax+00h]
0x1400200ad  mov     rax, gs:188h
0x1400200b6  mov     [rdi+8], rax
0x1400200ba  mov     dword ptr [rdi+10h], 1
0x1400200c1  mov     rcx, rbp; FastMutex
0x1400200c4  call    cs:__imp_ExReleaseFastMutex
0x1400200cb  nop     dword ptr [rax+rax+00h]
0x1400200d0  jmp     loc_14001FF44
0x1400200d5  test    r14b, r14b
0x1400200d8  jnz     short loc_14002012B
0x1400200da  test    rbx, rbx
0x1400200dd  jz      short loc_14002012B
0x1400200df  mov     rcx, rbp; FastMutex
0x1400200e2  call    cs:__imp_ExAcquireFastMutex
0x1400200e9  nop     dword ptr [rax+rax+00h]
0x1400200ee  mov     rax, gs:188h
0x1400200f7  cmp     [rbx+8], rax
0x1400200fb  jnz     short loc_14002010B
0x1400200fd  sub     dword ptr [rbx+10h], 1
0x140020101  jnz     short loc_14002011C
0x140020103  mov     qword ptr [rbx+8], 0
0x14002010b  xor     edx, edx
0x14002010d  mov     rcx, rbx
0x140020110  call    cs:__imp_FltReleasePushLockEx
0x140020117  nop     dword ptr [rax+rax+00h]
0x14002011c  mov     rcx, rbp; FastMutex
0x14002011f  call    cs:__imp_ExReleaseFastMutex
0x140020126  nop     dword ptr [rax+rax+00h]
0x14002012b  mov     rbx, [rsp+48h+arg_0]
0x140020130  mov     rbp, [rsp+48h+arg_10]
0x140020135  add     rsp, 20h
0x140020139  pop     r15
0x14002013b  pop     r14
0x14002013d  pop     r12
0x14002013f  pop     rdi
0x140020140  pop     rsi
0x140020141  retn
```
