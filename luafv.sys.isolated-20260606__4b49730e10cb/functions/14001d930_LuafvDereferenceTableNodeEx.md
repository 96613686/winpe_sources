# LuafvDereferenceTableNodeEx

- ea: `0x14001d930`
- end: `0x14001db85`
- name: `LuafvDereferenceTableNodeEx`
- size: `597`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140001730`
- `0x140014474`
- `0x140015b34`
- `0x140016114`
- `0x1400163b0`
- `0x140017e60`
- `0x14001a3c8`
- `0x14001b7e4`
- `0x14001d524`
- `0x14001d930`
- `0x14001dc20`
- `0x14001dec8`
- `0x14001efc0`
- `0x140022b50`
- `0x140022de8`
- `0x140028d54`
- `0x140029a20`

## callees

- `0x140001200`
- `0x14001d930`
- `0x14001db8c`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001d975`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d9c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da95`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001db44`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d975`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d9c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da95`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001db44`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d94f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d999`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da5e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001db11`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d94f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001d999`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da5e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001db11`
- `FLTMGR!FltReleasePushLockEx` at `0x14001da82`
- `FLTMGR!FltReleasePushLockEx` at `0x14001daf9`
- `FLTMGR!FltReleasePushLockEx` at `0x14001db31`
- `FLTMGR!FltReleasePushLockEx` at `0x14001da82`
- `FLTMGR!FltReleasePushLockEx` at `0x14001daf9`
- `FLTMGR!FltReleasePushLockEx` at `0x14001db31`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d986`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001da08`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001d986`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001da08`

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
    FltAcquirePushLockExclusiveEx(&qword_14000F298, 0);
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
    FltReleasePushLockEx(&qword_14000F298, 0);
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
0x14001d930  push    rbx
0x14001d932  push    rbp
0x14001d933  push    rsi
0x14001d934  push    rdi
0x14001d935  sub     rsp, 28h
0x14001d939  movzx   ebp, r8b
0x14001d93d  mov     rbx, rcx
0x14001d940  test    dl, dl
0x14001d942  jnz     loc_14001D9CC
0x14001d948  lea     rcx, FastMutex; FastMutex
0x14001d94f  call    cs:__imp_ExAcquireFastMutex
0x14001d956  nop     dword ptr [rax+rax+00h]
0x14001d95b  mov     rax, gs:188h
0x14001d964  cmp     [rbx+8], rax
0x14001d968  jz      loc_14001DB7D
0x14001d96e  lea     rcx, FastMutex; FastMutex
0x14001d975  call    cs:__imp_ExReleaseFastMutex
0x14001d97c  nop     dword ptr [rax+rax+00h]
0x14001d981  xor     edx, edx
0x14001d983  mov     rcx, rbx
0x14001d986  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001d98d  nop     dword ptr [rax+rax+00h]
0x14001d992  lea     rcx, FastMutex; FastMutex
0x14001d999  call    cs:__imp_ExAcquireFastMutex
0x14001d9a0  nop     dword ptr [rax+rax+00h]
0x14001d9a5  mov     rax, gs:188h
0x14001d9ae  mov     [rbx+8], rax
0x14001d9b2  mov     dword ptr [rbx+10h], 1
0x14001d9b9  lea     rcx, FastMutex; FastMutex
0x14001d9c0  call    cs:__imp_ExReleaseFastMutex
0x14001d9c7  nop     dword ptr [rax+rax+00h]
0x14001d9cc  mov     eax, 0FFFFFFFFh
0x14001d9d1  lock xadd [rbx+14h], eax
0x14001d9d6  sub     eax, 1
0x14001d9d9  jz      short loc_14001DA57
0x14001d9db  cmp     eax, 1
0x14001d9de  jnz     loc_14001DB05
0x14001d9e4  test    byte ptr [rbx+1Eh], 6
0x14001d9e8  jnz     loc_14001DB05
0x14001d9ee  test    qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFF8h
0x14001d9f9  jz      loc_14001DB05
0x14001d9ff  xor     edx, edx
0x14001da01  lea     rcx, qword_14000F298
0x14001da08  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001da0f  nop     dword ptr [rax+rax+00h]
0x14001da14  test    qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFF8h
0x14001da1f  jz      loc_14001DADF
0x14001da25  mov     rcx, rbx
0x14001da28  call    RemoveMruListNode
0x14001da2d  mov     r8, [rbx+0A8h]
0x14001da34  and     r8, 0FFFFFFFFFFFFFFF8h
0x14001da38  cmp     qword ptr [r8], 0
0x14001da3c  jz      loc_14001DADF
0x14001da42  mov     rcx, [r8+28h]
0x14001da46  add     r8, 28h ; '('
0x14001da4a  cmp     [rcx+8], r8
0x14001da4e  jz      short loc_14001DACA
0x14001da50  mov     ecx, 3
0x14001da55  int     29h; Win8: RtlFailFast(ecx)
0x14001da57  lea     rcx, FastMutex; FastMutex
0x14001da5e  call    cs:__imp_ExAcquireFastMutex
0x14001da65  nop     dword ptr [rax+rax+00h]
0x14001da6a  mov     rax, gs:188h
0x14001da73  cmp     [rbx+8], rax
0x14001da77  jz      loc_14001DB68
0x14001da7d  xor     edx, edx
0x14001da7f  mov     rcx, rbx
0x14001da82  call    cs:__imp_FltReleasePushLockEx
0x14001da89  nop     dword ptr [rax+rax+00h]
0x14001da8e  lea     rcx, FastMutex; FastMutex
0x14001da95  call    cs:__imp_ExReleaseFastMutex
0x14001da9c  nop     dword ptr [rax+rax+00h]
0x14001daa1  mov     rcx, [rbx+20h]
0x14001daa5  test    rcx, rcx
0x14001daa8  jz      loc_14001DB50
0x14001daae  xor     r8d, r8d
0x14001dab1  xor     edx, edx
0x14001dab3  call    LuafvDereferenceTableNodeEx
0x14001dab8  mov     rcx, rbx
0x14001dabb  call    FreeTableNode
0x14001dac0  add     rsp, 28h
0x14001dac4  pop     rdi
0x14001dac5  pop     rsi
0x14001dac6  pop     rbp
0x14001dac7  pop     rbx
0x14001dac8  retn
0x14001daca  lea     rax, [rbx+0D0h]
0x14001dad1  mov     [rax], rcx
0x14001dad4  mov     [rax+8], r8
0x14001dad8  mov     [rcx+8], rax
0x14001dadc  mov     [r8], rax
0x14001dadf  mov     rax, ds:0FFFFF78000000014h
0x14001dae9  lea     rcx, qword_14000F298
0x14001daf0  xor     edx, edx
0x14001daf2  mov     [rbx+0E0h], rax
0x14001daf9  call    cs:__imp_FltReleasePushLockEx
0x14001db00  nop     dword ptr [rax+rax+00h]
0x14001db05  test    bpl, bpl
0x14001db08  jnz     short loc_14001DB50
0x14001db0a  lea     rcx, FastMutex; FastMutex
0x14001db11  call    cs:__imp_ExAcquireFastMutex
0x14001db18  nop     dword ptr [rax+rax+00h]
0x14001db1d  mov     rax, gs:188h
0x14001db26  cmp     [rbx+8], rax
0x14001db2a  jz      short loc_14001DB5A
0x14001db2c  xor     edx, edx
0x14001db2e  mov     rcx, rbx
0x14001db31  call    cs:__imp_FltReleasePushLockEx
0x14001db38  nop     dword ptr [rax+rax+00h]
0x14001db3d  lea     rcx, FastMutex; FastMutex
0x14001db44  call    cs:__imp_ExReleaseFastMutex
0x14001db4b  nop     dword ptr [rax+rax+00h]
0x14001db50  add     rsp, 28h
0x14001db54  pop     rdi
0x14001db55  pop     rsi
0x14001db56  pop     rbp
0x14001db57  pop     rbx
0x14001db58  retn
0x14001db5a  sub     dword ptr [rbx+10h], 1
0x14001db5e  jnz     short loc_14001DB3D
0x14001db60  xor     eax, eax
0x14001db62  mov     [rbx+8], rax
0x14001db66  jmp     short loc_14001DB2C
0x14001db68  sub     dword ptr [rbx+10h], 1
0x14001db6c  jnz     loc_14001DA8E
0x14001db72  xor     eax, eax
0x14001db74  mov     [rbx+8], rax
0x14001db78  jmp     loc_14001DA7D
0x14001db7d  inc     dword ptr [rbx+10h]
0x14001db80  jmp     loc_14001D9B9
```
