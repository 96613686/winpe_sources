# NpInternalWrite

- ea: `0x14000b54c`
- end: `0x14000b75f`
- name: `NpInternalWrite`
- size: `531`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000efb0`

## callees

- `0x14000b54c`
- `0x14000d314`
- `0x14000deb8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b5d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b5d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b731`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b731`

## pseudocode

```c
__int64 __fastcall NpInternalWrite(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbp
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  __int64 v10; // rbp
  __int64 v11; // r14
  unsigned int v12; // ebx
  int v13; // ecx
  char v15; // al
  __int64 v16; // rcx
  unsigned __int64 v17; // r15
  int v18; // r8d
  size_t Size; // [rsp+28h] [rbp-70h]
  __int64 v21; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+10h]
  __int64 v23; // [rsp+B8h] [rbp+20h]

  v21 = a1;
  *(_DWORD *)(a2 + 16) &= ~0x40u;
  v5 = *(_QWORD *)(a2 + 184);
  LODWORD(v21) = 0;
  v7 = *(_QWORD *)(v5 + 48);
  if ( (*(_QWORD *)(v7 + 32) & 1) != 0 && **(_WORD **)(v7 + 24) == 514 )
  {
    v8 = *(_QWORD *)(v7 + 32);
    v9 = v8 & 0xFFFFFFFFFFFFFFFCuLL;
    v10 = *(unsigned int *)(v5 + 16);
    v23 = *(_QWORD *)(a2 + 24);
    v11 = (v8 >> 1) & 1;
    v22 = *(_QWORD *)(a2 + 152);
    ExAcquirePushLockExclusiveEx(v9 + 64, 0, a3, a4);
    if ( (*(_QWORD *)(v7 + 32) & 1) == 0 )
      goto LABEL_4;
    v13 = (unsigned __int16)*(_DWORD *)(*(_QWORD *)(v9 + 40) + 256LL);
    if ( (_DWORD)v11 ? v13 == 0 : v13 == 1 )
      goto LABEL_4;
    *(_QWORD *)(a2 + 56) = v10;
    v15 = *(_BYTE *)(v9 + 8);
    if ( v15 == 3 )
    {
      v16 = (_DWORD)v11 != 0 ? 168LL : 72LL;
      v17 = v16 + v9;
      v18 = *(_DWORD *)(*(_QWORD *)(v9 + 40) + 260LL);
      if ( !v18
        && (*(_BYTE *)((unsigned int)v11 + v9 + 9) & 2) != 0
        && (*(_DWORD *)(v17 + 16) || *(_DWORD *)(v17 + 20) < (unsigned int)v10) )
      {
        *(_QWORD *)(a2 + 56) = 0;
        v12 = 0;
      }
      else
      {
        v12 = NpWriteDataQueue(
                v16 + v9,
                *(_BYTE *)(((unsigned int)v11 ^ 1LL) + v9 + 9) & 1,
                v23,
                v10,
                0,
                v18,
                (unsigned int *)&v21,
                v9,
                v11,
                v22,
                a3);
        if ( v12 == -1073741802 )
        {
          if ( (*(_BYTE *)((unsigned int)v11 + v9 + 9) & 2) != 0 )
          {
            v12 = 0;
            *(_QWORD *)(a2 + 56) = (unsigned int)(v10 - v21);
          }
          else
          {
            LODWORD(Size) = v10;
            v12 = NpAddDataQueueEntry(v11, v9, v17, 1, 1, Size, a2, 0, (int)v10 - (int)v21);
          }
        }
      }
      goto LABEL_23;
    }
    if ( v15 == 1 )
    {
LABEL_4:
      v12 = -1073741648;
    }
    else
    {
      v12 = -1073741647;
      if ( v15 == 2 )
        v12 = -1073741645;
    }
LABEL_23:
    ExReleasePushLockExclusiveEx(v9 + 64, 0);
    return v12;
  }
  return 3221225648LL;
}

```

## disassembly

```asm
0x14000b54c  mov     rax, rsp
0x14000b54f  mov     [rax+18h], rbx
0x14000b553  mov     [rax+8], rcx
0x14000b557  push    rbp
0x14000b558  push    rsi
0x14000b559  push    rdi
0x14000b55a  push    r12
0x14000b55c  push    r13
0x14000b55e  push    r14
0x14000b560  push    r15
0x14000b562  sub     rsp, 60h
0x14000b566  and     dword ptr [rdx+10h], 0FFFFFFBFh
0x14000b56a  mov     r13, r8
0x14000b56d  mov     rbp, [rdx+0B8h]
0x14000b574  mov     rdi, rdx
0x14000b577  mov     dword ptr [rax+8], 0
0x14000b57e  mov     rbx, [rbp+30h]
0x14000b582  mov     rax, [rbx+20h]
0x14000b586  test    al, 1
0x14000b588  jz      loc_14000B741
0x14000b58e  mov     rax, [rbx+18h]
0x14000b592  mov     ecx, 202h
0x14000b597  cmp     [rax], cx
0x14000b59a  jnz     loc_14000B741
0x14000b5a0  mov     rsi, [rbx+20h]
0x14000b5a4  mov     r14, [rbx+20h]
0x14000b5a8  and     rsi, 0FFFFFFFFFFFFFFFCh
0x14000b5ac  mov     rax, [rdx+18h]
0x14000b5b0  mov     ebp, [rbp+10h]
0x14000b5b3  mov     [rsp+98h+arg_18], rax
0x14000b5bb  mov     rax, [rdx+98h]
0x14000b5c2  lea     rcx, [rsi+40h]
0x14000b5c6  shr     r14, 1
0x14000b5c9  xor     edx, edx
0x14000b5cb  and     r14d, 1
0x14000b5cf  mov     [rsp+98h+arg_8], rax
0x14000b5d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b5de  nop     dword ptr [rax+rax+00h]
0x14000b5e3  mov     rax, [rbx+20h]
0x14000b5e7  test    al, 1
0x14000b5e9  jnz     short loc_14000B5F5
0x14000b5eb  mov     ebx, 0C00000B0h
0x14000b5f0  jmp     loc_14000B72B
0x14000b5f5  mov     rax, [rsi+28h]
0x14000b5f9  xor     r9d, r9d
0x14000b5fc  mov     ecx, [rax+100h]
0x14000b602  movzx   ecx, cx
0x14000b605  test    r14d, r14d
0x14000b608  jz      short loc_14000B63E
0x14000b60a  test    ecx, ecx
0x14000b60c  jz      short loc_14000B5EB
0x14000b60e  mov     eax, r14d
0x14000b611  mov     [rdi+38h], rbp
0x14000b615  neg     eax
0x14000b617  mov     al, [rsi+8]
0x14000b61a  sbb     rcx, rcx
0x14000b61d  and     ecx, 60h
0x14000b620  add     rcx, 48h ; 'H'
0x14000b624  cmp     al, 3
0x14000b626  jz      short loc_14000B643
0x14000b628  cmp     al, 1
0x14000b62a  jz      short loc_14000B5EB
0x14000b62c  mov     ebx, 0C00000B1h
0x14000b631  cmp     al, 2
0x14000b633  lea     ecx, [rbx+2]
0x14000b636  cmovz   ebx, ecx
0x14000b639  jmp     loc_14000B72B
0x14000b63e  cmp     ecx, 1
0x14000b641  jmp     short loc_14000B60C
0x14000b643  mov     rax, [rsi+28h]
0x14000b647  lea     r15, [rcx+rsi]
0x14000b64b  mov     r8d, [rax+104h]
0x14000b652  test    r8d, r8d
0x14000b655  jnz     short loc_14000B677
0x14000b657  test    byte ptr [r14+rsi+9], 2
0x14000b65d  jz      short loc_14000B677
0x14000b65f  cmp     [r15+10h], r9d
0x14000b663  jnz     short loc_14000B66B
0x14000b665  cmp     [r15+14h], ebp
0x14000b669  jnb     short loc_14000B677
0x14000b66b  mov     [rdi+38h], r9
0x14000b66f  mov     ebx, r9d
0x14000b672  jmp     loc_14000B72B
0x14000b677  mov     [rsp+98h+var_48], r13
0x14000b67c  mov     rax, r14
0x14000b67f  xor     rax, 1
0x14000b683  mov     rcx, r15
0x14000b686  movzx   edx, byte ptr [rax+rsi+9]
0x14000b68b  mov     rax, [rsp+98h+arg_8]
0x14000b693  and     edx, 1
0x14000b696  mov     [rsp+98h+var_50], rax
0x14000b69b  lea     rax, [rsp+98h+arg_0]
0x14000b6a3  mov     [rsp+98h+var_58], r14d
0x14000b6a8  mov     [rsp+98h+Src], rsi
0x14000b6ad  mov     [rsp+98h+var_68], rax
0x14000b6b2  mov     dword ptr [rsp+98h+Size], r8d
0x14000b6b7  mov     r8, [rsp+98h+arg_18]
0x14000b6bf  mov     byte ptr [rsp+98h+var_78], r9b
0x14000b6c4  mov     r9d, ebp
0x14000b6c7  call    NpWriteDataQueue
0x14000b6cc  mov     ebx, eax
0x14000b6ce  cmp     eax, 0C0000016h
0x14000b6d3  jnz     short loc_14000B72B
0x14000b6d5  test    byte ptr [r14+rsi+9], 2
0x14000b6db  jz      short loc_14000B6EE
0x14000b6dd  sub     ebp, dword ptr [rsp+98h+arg_0]
0x14000b6e4  mov     eax, ebp
0x14000b6e6  xor     ebx, ebx
0x14000b6e8  mov     [rdi+38h], rax
0x14000b6ec  jmp     short loc_14000B72B
0x14000b6ee  mov     eax, ebp
0x14000b6f0  mov     r9d, 1; int
0x14000b6f6  sub     eax, dword ptr [rsp+98h+arg_0]
0x14000b6fd  mov     r8, r15; int
0x14000b700  mov     [rsp+98h+var_58], eax; int
0x14000b704  mov     rdx, rsi; int
0x14000b707  mov     [rsp+98h+Src], 0; Src
0x14000b710  mov     ecx, r14d; int
0x14000b713  mov     [rsp+98h+var_68], rdi; __int64
0x14000b718  mov     dword ptr [rsp+98h+Size], ebp; Size
0x14000b71c  mov     [rsp+98h+var_78], 1; int
0x14000b724  call    NpAddDataQueueEntry
0x14000b729  mov     ebx, eax
0x14000b72b  xor     edx, edx
0x14000b72d  lea     rcx, [rsi+40h]
0x14000b731  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b738  nop     dword ptr [rax+rax+00h]
0x14000b73d  mov     eax, ebx
0x14000b73f  jmp     short loc_14000B746
0x14000b741  mov     eax, 0C00000B0h
0x14000b746  mov     rbx, [rsp+98h+arg_10]
0x14000b74e  add     rsp, 60h
0x14000b752  pop     r15
0x14000b754  pop     r14
0x14000b756  pop     r13
0x14000b758  pop     r12
0x14000b75a  pop     rdi
0x14000b75b  pop     rsi
0x14000b75c  pop     rbp
0x14000b75d  retn
```
