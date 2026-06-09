# LuafvDereferenceTableNodeEx

- ea: `0x14001d8e0`
- end: `0x14001db35`
- name: `LuafvDereferenceTableNodeEx`
- size: `597`
- prototype: `void __fastcall(__int64, char, char)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140001730`
- `0x140014474`
- `0x140015b34`
- `0x140016114`
- `0x1400163b0`
- `0x140017e10`
- `0x14001a378`
- `0x14001b794`
- `0x14001d4d4`
- `0x14001d8e0`
- `0x14001dbd0`
- `0x14001de78`
- `0x14001ef70`
- `0x140022b00`
- `0x140022d98`
- `0x140028d54`
- `0x140029a20`

## callees

- `0x140001200`
- `0x14001d8e0`
- `0x14001db3c`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001d925`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d970`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da45`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001daf4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d925`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d970`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da45`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001daf4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d8ff`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d949`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da0e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dac1`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d8ff`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d949`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da0e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dac1`
- `FLTMGR!FltReleasePushLockEx` at `0x14001da32`
- `FLTMGR!FltReleasePushLockEx` at `0x14001daa9`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dae1`
- `FLTMGR!FltReleasePushLockEx` at `0x14001da32`
- `FLTMGR!FltReleasePushLockEx` at `0x14001daa9`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dae1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d936`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d9b8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d936`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d9b8`

## pseudocode

```c
void __fastcall LuafvDereferenceTableNodeEx(__int64 a1, char a2, char a3)
{
  signed __int32 v5; // eax
  _QWORD *v6; // r8
  __int64 v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // rcx
  bool v10; // zf

  if ( !a2 )
  {
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
  v5 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 20));
  if ( !v5 )
  {
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a1 + 8) == KeGetCurrentThread() )
    {
      v10 = (*(_DWORD *)(a1 + 16))-- == 1;
      if ( !v10 )
      {
LABEL_15:
        ExReleaseFastMutex(&FastMutex);
        v9 = *(_QWORD *)(a1 + 32);
        if ( v9 )
        {
          LuafvDereferenceTableNodeEx(v9, 0, 0);
          FreeTableNode(a1);
        }
        return;
      }
      *(_QWORD *)(a1 + 8) = 0;
    }
    FltReleasePushLockEx(a1, 0);
    goto LABEL_15;
  }
  if ( v5 == 1 && (*(_BYTE *)(a1 + 30) & 6) == 0 && (*(_QWORD *)(a1 + 168) & 0xFFFFFFFFFFFFFFF8uLL) != 0 )
  {
    FltAcquirePushLockExclusiveEx(&qword_14000EC58, 0);
    if ( (*(_QWORD *)(a1 + 168) & 0xFFFFFFFFFFFFFFF8uLL) != 0 )
    {
      RemoveMruListNode(a1);
      v6 = (_QWORD *)(*(_QWORD *)(a1 + 168) & 0xFFFFFFFFFFFFFFF8uLL);
      if ( *v6 )
      {
        v7 = v6[5];
        v8 = v6 + 5;
        if ( *(_QWORD **)(v7 + 8) != v8 )
          __fastfail(3u);
        *(_QWORD *)(a1 + 208) = v7;
        *(_QWORD *)(a1 + 216) = v8;
        *(_QWORD *)(v7 + 8) = a1 + 208;
        *v8 = a1 + 208;
      }
    }
    *(_QWORD *)(a1 + 224) = MEMORY[0xFFFFF78000000014];
    FltReleasePushLockEx(&qword_14000EC58, 0);
  }
  if ( !a3 )
  {
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a1 + 8) == KeGetCurrentThread() )
    {
      v10 = (*(_DWORD *)(a1 + 16))-- == 1;
      if ( !v10 )
        goto LABEL_22;
      *(_QWORD *)(a1 + 8) = 0;
    }
    FltReleasePushLockEx(a1, 0);
LABEL_22:
    ExReleaseFastMutex(&FastMutex);
  }
}

```

## disassembly

```asm
0x14001d8e0  push    rbx
0x14001d8e2  push    rbp
0x14001d8e3  push    rsi
0x14001d8e4  push    rdi
0x14001d8e5  sub     rsp, 28h
0x14001d8e9  movzx   ebp, r8b
0x14001d8ed  mov     rbx, rcx
0x14001d8f0  test    dl, dl
0x14001d8f2  jnz     loc_14001D97C
0x14001d8f8  lea     rcx, FastMutex; FastMutex
0x14001d8ff  call    cs:__imp_ExAcquireFastMutex
0x14001d906  nop     dword ptr [rax+rax+00h]
0x14001d90b  mov     rax, gs:188h
0x14001d914  cmp     [rbx+8], rax
0x14001d918  jz      loc_14001DB2D
0x14001d91e  lea     rcx, FastMutex; FastMutex
0x14001d925  call    cs:__imp_ExReleaseFastMutex
0x14001d92c  nop     dword ptr [rax+rax+00h]
0x14001d931  xor     edx, edx
0x14001d933  mov     rcx, rbx
0x14001d936  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d93d  nop     dword ptr [rax+rax+00h]
0x14001d942  lea     rcx, FastMutex; FastMutex
0x14001d949  call    cs:__imp_ExAcquireFastMutex
0x14001d950  nop     dword ptr [rax+rax+00h]
0x14001d955  mov     rax, gs:188h
0x14001d95e  mov     [rbx+8], rax
0x14001d962  mov     dword ptr [rbx+10h], 1
0x14001d969  lea     rcx, FastMutex; FastMutex
0x14001d970  call    cs:__imp_ExReleaseFastMutex
0x14001d977  nop     dword ptr [rax+rax+00h]
0x14001d97c  mov     eax, 0FFFFFFFFh
0x14001d981  lock xadd [rbx+14h], eax
0x14001d986  sub     eax, 1
0x14001d989  jz      short loc_14001DA07
0x14001d98b  cmp     eax, 1
0x14001d98e  jnz     loc_14001DAB5
0x14001d994  test    byte ptr [rbx+1Eh], 6
0x14001d998  jnz     loc_14001DAB5
0x14001d99e  test    qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFF8h
0x14001d9a9  jz      loc_14001DAB5
0x14001d9af  xor     edx, edx
0x14001d9b1  lea     rcx, qword_14000EC58
0x14001d9b8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d9bf  nop     dword ptr [rax+rax+00h]
0x14001d9c4  test    qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFF8h
0x14001d9cf  jz      loc_14001DA8F
0x14001d9d5  mov     rcx, rbx
0x14001d9d8  call    RemoveMruListNode
0x14001d9dd  mov     r8, [rbx+0A8h]
0x14001d9e4  and     r8, 0FFFFFFFFFFFFFFF8h
0x14001d9e8  cmp     qword ptr [r8], 0
0x14001d9ec  jz      loc_14001DA8F
0x14001d9f2  mov     rcx, [r8+28h]
0x14001d9f6  add     r8, 28h ; '('
0x14001d9fa  cmp     [rcx+8], r8
0x14001d9fe  jz      short loc_14001DA7A
0x14001da00  mov     ecx, 3
0x14001da05  int     29h; Win8: RtlFailFast(ecx)
0x14001da07  lea     rcx, FastMutex; FastMutex
0x14001da0e  call    cs:__imp_ExAcquireFastMutex
0x14001da15  nop     dword ptr [rax+rax+00h]
0x14001da1a  mov     rax, gs:188h
0x14001da23  cmp     [rbx+8], rax
0x14001da27  jz      loc_14001DB18
0x14001da2d  xor     edx, edx
0x14001da2f  mov     rcx, rbx
0x14001da32  call    cs:__imp_FltReleasePushLockEx
0x14001da39  nop     dword ptr [rax+rax+00h]
0x14001da3e  lea     rcx, FastMutex; FastMutex
0x14001da45  call    cs:__imp_ExReleaseFastMutex
0x14001da4c  nop     dword ptr [rax+rax+00h]
0x14001da51  mov     rcx, [rbx+20h]
0x14001da55  test    rcx, rcx
0x14001da58  jz      loc_14001DB00
0x14001da5e  xor     r8d, r8d
0x14001da61  xor     edx, edx
0x14001da63  call    LuafvDereferenceTableNodeEx
0x14001da68  mov     rcx, rbx
0x14001da6b  call    FreeTableNode
0x14001da70  add     rsp, 28h
0x14001da74  pop     rdi
0x14001da75  pop     rsi
0x14001da76  pop     rbp
0x14001da77  pop     rbx
0x14001da78  retn
0x14001da7a  lea     rax, [rbx+0D0h]
0x14001da81  mov     [rax], rcx
0x14001da84  mov     [rax+8], r8
0x14001da88  mov     [rcx+8], rax
0x14001da8c  mov     [r8], rax
0x14001da8f  mov     rax, ds:0FFFFF78000000014h
0x14001da99  lea     rcx, qword_14000EC58
0x14001daa0  xor     edx, edx
0x14001daa2  mov     [rbx+0E0h], rax
0x14001daa9  call    cs:__imp_FltReleasePushLockEx
0x14001dab0  nop     dword ptr [rax+rax+00h]
0x14001dab5  test    bpl, bpl
0x14001dab8  jnz     short loc_14001DB00
0x14001daba  lea     rcx, FastMutex; FastMutex
0x14001dac1  call    cs:__imp_ExAcquireFastMutex
0x14001dac8  nop     dword ptr [rax+rax+00h]
0x14001dacd  mov     rax, gs:188h
0x14001dad6  cmp     [rbx+8], rax
0x14001dada  jz      short loc_14001DB0A
0x14001dadc  xor     edx, edx
0x14001dade  mov     rcx, rbx
0x14001dae1  call    cs:__imp_FltReleasePushLockEx
0x14001dae8  nop     dword ptr [rax+rax+00h]
0x14001daed  lea     rcx, FastMutex; FastMutex
0x14001daf4  call    cs:__imp_ExReleaseFastMutex
0x14001dafb  nop     dword ptr [rax+rax+00h]
0x14001db00  add     rsp, 28h
0x14001db04  pop     rdi
0x14001db05  pop     rsi
0x14001db06  pop     rbp
0x14001db07  pop     rbx
0x14001db08  retn
0x14001db0a  sub     dword ptr [rbx+10h], 1
0x14001db0e  jnz     short loc_14001DAED
0x14001db10  xor     eax, eax
0x14001db12  mov     [rbx+8], rax
0x14001db16  jmp     short loc_14001DADC
0x14001db18  sub     dword ptr [rbx+10h], 1
0x14001db1c  jnz     loc_14001DA3E
0x14001db22  xor     eax, eax
0x14001db24  mov     [rbx+8], rax
0x14001db28  jmp     loc_14001DA2D
0x14001db2d  inc     dword ptr [rbx+10h]
0x14001db30  jmp     loc_14001D969
```
