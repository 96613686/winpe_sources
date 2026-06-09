# NpInternalRead

- ea: `0x14000c800`
- end: `0x14000ca25`
- name: `NpInternalRead`
- size: `549`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000efb0`

## callees

- `0x14000c800`
- `0x14000deb8`
- `0x14000e1b0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c896`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c896`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c9fe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c9fe`
- `ntoskrnl!KeBugCheckEx` at `0x14000c8ef`
- `ntoskrnl!KeBugCheckEx` at `0x14000c8ef`

## pseudocode

```c
__int64 __fastcall NpInternalRead(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rcx
  char v5; // r15
  __int64 v7; // rdi
  int v9; // r13d
  unsigned __int64 v10; // rbx
  __int64 v11; // rsi
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // r14
  int v14; // r9d
  int v15; // ecx
  bool v16; // zf
  unsigned int v17; // ebx
  unsigned __int64 v18; // rdi
  size_t Size; // [rsp+28h] [rbp-70h]
  int v20; // [rsp+50h] [rbp-48h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+8h]

  v4 = *(_QWORD *)(a2 + 184);
  v5 = a3;
  v7 = *(_QWORD *)(v4 + 48);
  if ( (*(_QWORD *)(v7 + 32) & 1) == 0 )
    return 3221225648LL;
  if ( **(_WORD **)(v7 + 24) != 514 )
    return 3221225485LL;
  v9 = *(_DWORD *)(v4 + 8);
  v10 = *(_QWORD *)(v7 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
  v11 = (*(_QWORD *)(v7 + 32) >> 1) & 1LL;
  v12 = v10 + 64;
  v21 = *(_QWORD *)(a2 + 24);
  v13 = (-(__int64)(((*(_QWORD *)(v7 + 32) >> 1) & 1) != 0) & 0xFFFFFFFFFFFFFFA0uLL) + 168;
  ExAcquirePushLockExclusiveEx(v10 + 64, 0, a3, a4);
  if ( (*(_QWORD *)(v7 + 32) & 1) == 0 || *(_BYTE *)(v10 + 8) == 1 )
  {
    v17 = -1073741648;
  }
  else if ( *(_BYTE *)(v10 + 8) == 2 )
  {
    v17 = -1073741645;
  }
  else
  {
    if ( (unsigned int)*(unsigned __int8 *)(v10 + 8) - 3 >= 2 )
      KeBugCheckEx(0x25u, 0xD070Bu, *(unsigned __int8 *)(v10 + 8), 0, 0);
    v15 = (unsigned __int16)*(_DWORD *)(*(_QWORD *)(v10 + 40) + 256LL);
    if ( (_DWORD)v11 )
      v16 = v15 == 1;
    else
      v16 = v15 == 0;
    if ( v16 )
    {
      v17 = -1073741811;
    }
    else if ( v5 != 1 || (*(_BYTE *)(v11 + v10 + 9) & 1) != 0 )
    {
      v18 = v13 + v10;
      if ( *(_DWORD *)(v13 + v10 + 16) == 1 )
      {
        LOBYTE(v14) = v5;
        LODWORD(Size) = v9;
        *(_OWORD *)(a2 + 48) = *(_OWORD *)NpReadDataQueue(
                                            (int)&v20,
                                            (int)v13 + (int)v10,
                                            0,
                                            v14,
                                            v21,
                                            Size,
                                            0,
                                            *(_BYTE *)(v11 + v10 + 9) & 1,
                                            v10,
                                            a4);
        v17 = *(_DWORD *)(a2 + 48);
        *(_QWORD *)(a2 + 88) = (unsigned int)(*(_DWORD *)(v18 + 20) - *(_DWORD *)(v18 + 36));
      }
      else if ( *(_BYTE *)(v10 + 8) == 4 )
      {
        v17 = -1073741493;
      }
      else if ( (*(_BYTE *)(v11 + v10 + 9) & 2) != 0 )
      {
        v17 = -1073741607;
      }
      else
      {
        LODWORD(Size) = v9;
        v17 = NpAddDataQueueEntry(v11, v10, (int)v13 + (int)v10, 0, 1, Size, a2, 0, 0);
      }
    }
    else
    {
      v17 = -1073741644;
    }
  }
  ExReleasePushLockExclusiveEx(v12, 0);
  return v17;
}

```

## disassembly

```asm
0x14000c800  mov     [rsp+arg_8], rbx
0x14000c805  mov     [rsp+arg_18], r9
0x14000c80a  mov     [rsp+arg_0], rcx
0x14000c80f  push    rbp
0x14000c810  push    rsi
0x14000c811  push    rdi
0x14000c812  push    r12
0x14000c814  push    r13
0x14000c816  push    r14
0x14000c818  push    r15
0x14000c81a  sub     rsp, 60h
0x14000c81e  mov     rcx, [rdx+0B8h]
0x14000c825  mov     r15b, r8b
0x14000c828  mov     rbp, rdx
0x14000c82b  mov     rdi, [rcx+30h]
0x14000c82f  mov     rax, [rdi+20h]
0x14000c833  test    al, 1
0x14000c835  jnz     short loc_14000C841
0x14000c837  mov     eax, 0C00000B0h
0x14000c83c  jmp     loc_14000CA0C
0x14000c841  mov     rax, [rdi+18h]
0x14000c845  mov     edx, 202h
0x14000c84a  cmp     [rax], dx
0x14000c84d  jz      short loc_14000C859
0x14000c84f  mov     eax, 0C000000Dh
0x14000c854  jmp     loc_14000CA0C
0x14000c859  mov     rsi, [rdi+20h]
0x14000c85d  mov     rbx, [rdi+20h]
0x14000c861  mov     r13d, [rcx+8]
0x14000c865  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000c869  shr     rsi, 1
0x14000c86c  and     esi, 1
0x14000c86f  mov     eax, esi
0x14000c871  neg     eax
0x14000c873  lea     r12, [rbx+40h]
0x14000c877  mov     rax, [rbp+18h]
0x14000c87b  mov     rcx, r12
0x14000c87e  sbb     r14, r14
0x14000c881  mov     [rsp+98h+arg_0], rax
0x14000c889  and     r14, 0FFFFFFFFFFFFFFA0h
0x14000c88d  xor     edx, edx
0x14000c88f  add     r14, 0A8h
0x14000c896  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c89d  nop     dword ptr [rax+rax+00h]
0x14000c8a2  mov     rax, [rdi+20h]
0x14000c8a6  mov     r8d, 1
0x14000c8ac  test    r8b, al
0x14000c8af  jz      loc_14000C9F4
0x14000c8b5  movzx   edx, byte ptr [rbx+8]
0x14000c8b9  mov     ecx, edx
0x14000c8bb  sub     ecx, r8d
0x14000c8be  jz      loc_14000C9F4
0x14000c8c4  sub     ecx, r8d
0x14000c8c7  jz      loc_14000C9ED
0x14000c8cd  sub     ecx, r8d
0x14000c8d0  jz      short loc_14000C8FC
0x14000c8d2  cmp     ecx, r8d
0x14000c8d5  jz      short loc_14000C8FC
0x14000c8d7  xor     r9d, r9d; BugCheckParameter3
0x14000c8da  mov     [rsp+98h+BugCheckParameter4], 0; BugCheckParameter4
0x14000c8e3  mov     r8d, edx; BugCheckParameter2
0x14000c8e6  mov     edx, 0D070Bh; BugCheckParameter1
0x14000c8eb  lea     ecx, [r9+25h]; BugCheckCode
0x14000c8ef  call    cs:__imp_KeBugCheckEx
0x14000c8fc  mov     rax, [rbx+28h]
0x14000c900  mov     ecx, [rax+100h]
0x14000c906  movzx   ecx, cx
0x14000c909  test    esi, esi
0x14000c90b  jz      short loc_14000C91C
0x14000c90d  cmp     ecx, r8d
0x14000c910  jnz     short loc_14000C920
0x14000c912  mov     ebx, 0C000000Dh
0x14000c917  jmp     loc_14000C9F9
0x14000c91c  test    ecx, ecx
0x14000c91e  jmp     short loc_14000C910
0x14000c920  movzx   ecx, byte ptr [rsi+rbx+9]
0x14000c925  mov     eax, ecx
0x14000c927  and     eax, r8d
0x14000c92a  cmp     r15b, r8b
0x14000c92d  jnz     short loc_14000C93D
0x14000c92f  test    eax, eax
0x14000c931  jnz     short loc_14000C93D
0x14000c933  mov     ebx, 0C00000B4h
0x14000c938  jmp     loc_14000C9F9
0x14000c93d  lea     rdi, [r14+rbx]
0x14000c941  cmp     [rdi+10h], r8d
0x14000c945  jz      short loc_14000C996
0x14000c947  cmp     dl, 4
0x14000c94a  jnz     short loc_14000C956
0x14000c94c  mov     ebx, 0C000014Bh
0x14000c951  jmp     loc_14000C9F9
0x14000c956  test    cl, 2
0x14000c959  jnz     short loc_14000C98F
0x14000c95b  mov     dword ptr [rsp+98h+var_58], 0; int
0x14000c963  xor     r9d, r9d; int
0x14000c966  mov     [rsp+98h+Src], 0; Src
0x14000c96f  mov     rdx, rbx; int
0x14000c972  mov     qword ptr [rsp+98h+var_68], rbp; __int64
0x14000c977  mov     ecx, esi; int
0x14000c979  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14000c97e  mov     dword ptr [rsp+98h+BugCheckParameter4], r8d; int
0x14000c983  mov     r8, rdi; int
0x14000c986  call    NpAddDataQueueEntry
0x14000c98b  mov     ebx, eax
0x14000c98d  jmp     short loc_14000C9F9
0x14000c98f  mov     ebx, 0C00000D9h
0x14000c994  jmp     short loc_14000C9F9
0x14000c996  mov     rcx, [rsp+98h+arg_18]
0x14000c99e  mov     r9b, r15b; int
0x14000c9a1  mov     [rsp+98h+var_50], rcx; __int64
0x14000c9a6  xor     r8d, r8d; int
0x14000c9a9  mov     [rsp+98h+var_58], rbx; __int64
0x14000c9ae  lea     rcx, [rsp+98h+var_48]; int
0x14000c9b3  mov     dword ptr [rsp+98h+Src], eax; int
0x14000c9b7  mov     rdx, rdi; int
0x14000c9ba  mov     rax, [rsp+98h+arg_0]
0x14000c9c2  mov     [rsp+98h+var_68], 0; char
0x14000c9c7  mov     dword ptr [rsp+98h+Size], r13d; Size
0x14000c9cc  mov     [rsp+98h+BugCheckParameter4], rax; __int64
0x14000c9d1  call    NpReadDataQueue
0x14000c9d6  movups  xmm0, xmmword ptr [rax]
0x14000c9d9  movdqu  xmmword ptr [rbp+30h], xmm0
0x14000c9de  mov     eax, [rdi+14h]
0x14000c9e1  sub     eax, [rdi+24h]
0x14000c9e4  mov     ebx, [rbp+30h]
0x14000c9e7  mov     [rbp+58h], rax
0x14000c9eb  jmp     short loc_14000C9F9
0x14000c9ed  mov     ebx, 0C00000B3h
0x14000c9f2  jmp     short loc_14000C9F9
0x14000c9f4  mov     ebx, 0C00000B0h
0x14000c9f9  xor     edx, edx
0x14000c9fb  mov     rcx, r12
0x14000c9fe  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ca05  nop     dword ptr [rax+rax+00h]
0x14000ca0a  mov     eax, ebx
0x14000ca0c  mov     rbx, [rsp+98h+arg_8]
0x14000ca14  add     rsp, 60h
0x14000ca18  pop     r15
0x14000ca1a  pop     r14
0x14000ca1c  pop     r13
0x14000ca1e  pop     r12
0x14000ca20  pop     rdi
0x14000ca21  pop     rsi
0x14000ca22  pop     rbp
0x14000ca23  retn
```
