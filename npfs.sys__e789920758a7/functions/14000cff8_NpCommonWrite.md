# NpCommonWrite

- ea: `0x14000cff8`
- end: `0x14000d30c`
- name: `NpCommonWrite`
- size: `788`
- prototype: `char __fastcall(__int64, void *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ce40`
- `0x14000cf10`

## callees

- `0x14000cff8`
- `0x14000d314`
- `0x14000d630`
- `0x14000deb8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d083`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d083`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d0a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d26e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d0a2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d26e`
- `ntoskrnl!ExGetPreviousMode` at `0x14000d2eb`
- `ntoskrnl!ExGetPreviousMode` at `0x14000d2eb`

## pseudocode

```c
char __fastcall NpCommonWrite(__int64 a1, void *a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  __int64 v7; // rbx
  __int64 v9; // rbp
  unsigned __int64 v10; // rdi
  __int64 v11; // r15
  __int64 v12; // r12
  int v13; // r14d
  char v15; // cl
  char v16; // dl
  _DWORD *v17; // rsi
  __int64 v18; // r14
  unsigned int v19; // ecx
  int v20; // r12d
  KPROCESSOR_MODE PreviousMode; // al
  int v22; // eax
  int v23; // r9d
  unsigned int v24; // edx
  int v25; // eax
  size_t Size; // [rsp+28h] [rbp-70h]
  unsigned int v27; // [rsp+A0h] [rbp+8h] BYREF
  void *Src; // [rsp+A8h] [rbp+10h]
  __int64 v29; // [rsp+B8h] [rbp+20h]

  v29 = a4;
  Src = a2;
  v7 = a5;
  v9 = (unsigned int)a3;
  v27 = 0;
  *(_QWORD *)(a5 + 8) = 0;
  if ( (*(_QWORD *)(a1 + 32) & 1) == 0 )
  {
    *(_DWORD *)v7 = -1073741648;
    return 1;
  }
  if ( **(_WORD **)(a1 + 24) != 514 )
  {
    *(_DWORD *)v7 = -1073741811;
    return 1;
  }
  v10 = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
  v11 = (*(_QWORD *)(a1 + 32) >> 1) & 1LL;
  v12 = *(_QWORD *)(v10 + 40);
  a5 = v12;
  v13 = *(_DWORD *)(v12 + 256);
  ExAcquirePushLockExclusiveEx(v10 + 64, 0, a3, a4);
  if ( (*(_QWORD *)(a1 + 32) & 1) == 0 )
  {
LABEL_4:
    *(_DWORD *)v7 = -1073741648;
LABEL_5:
    ExReleasePushLockExclusiveEx(v10 + 64, 0);
    return 1;
  }
  v15 = *(_BYTE *)(v10 + 8);
  if ( v15 != 3 )
  {
    if ( v15 != 1 )
    {
      v25 = -1073741647;
      if ( v15 == 2 )
        v25 = -1073741645;
      *(_DWORD *)v7 = v25;
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  if ( (_DWORD)v11 )
  {
    if ( !(_WORD)v13 )
    {
LABEL_10:
      *(_DWORD *)v7 = -1073741811;
      goto LABEL_5;
    }
    v16 = *(_BYTE *)(v10 + 9);
    v17 = (_DWORD *)(v10 + 168);
  }
  else
  {
    if ( (unsigned __int16)v13 == 1 )
      goto LABEL_10;
    v16 = *(_BYTE *)(v10 + 10);
    v17 = (_DWORD *)(v10 + 72);
  }
  v18 = a6;
  *(_DWORD *)v7 = 0;
  *(_QWORD *)(v7 + 8) = v9;
  if ( v17[4] )
  {
    if ( v17[7] - v17[8] >= (unsigned int)v9 )
      goto LABEL_14;
  }
  else
  {
    v19 = v17[5];
    if ( v19 >= (unsigned int)v9 || v17[7] >= (unsigned int)v9 - v19 )
      goto LABEL_14;
  }
  if ( !*(_DWORD *)(v12 + 260) && (*(_BYTE *)(v11 + v10 + 9) & 2) != 0 )
  {
    *(_QWORD *)(v7 + 8) = 0;
    goto LABEL_38;
  }
  if ( v18 )
  {
LABEL_14:
    v20 = v16 & 1;
    if ( v18 )
      PreviousMode = *(_BYTE *)(v18 + 64);
    else
      PreviousMode = ExGetPreviousMode();
    v22 = NpWriteDataQueue(
            (__int64)v17,
            v20,
            (__int64)Src,
            v9,
            PreviousMode,
            *(_DWORD *)(a5 + 260),
            &v27,
            v10,
            v11,
            v29,
            a7);
    *(_DWORD *)v7 = v22;
    v23 = v22;
    if ( v22 != -1073741802 )
      goto LABEL_17;
    v24 = v27;
    if ( (*(_BYTE *)(v11 + v10 + 9) & 2) == 0 && v18 || v17[7] - v17[8] >= v27 )
    {
      LODWORD(Size) = v9;
      v23 = NpAddDataQueueEntry((unsigned int)v11, v10, (__int64)v17, 1, 0, Size, v18, Src, (unsigned int)v9 - v27);
      *(_DWORD *)v7 = v23;
      goto LABEL_17;
    }
    *(_DWORD *)v7 = 0;
    *(_QWORD *)(v7 + 8) = (unsigned int)v9 - v24;
LABEL_38:
    v23 = 0;
LABEL_17:
    if ( (_DWORD)v9 )
    {
      NpEventsWriteCompleted(v10, v11, (_DWORD)v17, v23, *(_QWORD *)(v7 + 8));
      *(_QWORD *)(v10 + 448) = MEMORY[0xFFFFF78000000014];
    }
    goto LABEL_5;
  }
  ExReleasePushLockExclusiveEx(v10 + 64, 0);
  return 0;
}

```

## disassembly

```asm
0x14000cff8  mov     rax, rsp
0x14000cffb  mov     [rax+18h], rbx
0x14000cfff  mov     [rax+20h], r9
0x14000d003  mov     [rax+10h], rdx
0x14000d007  push    rbp
0x14000d008  push    rsi
0x14000d009  push    rdi
0x14000d00a  push    r12
0x14000d00c  push    r13
0x14000d00e  push    r14
0x14000d010  push    r15
0x14000d012  sub     rsp, 60h
0x14000d016  mov     rbx, [rsp+98h+arg_20]
0x14000d01e  mov     rsi, rcx
0x14000d021  mov     ebp, r8d
0x14000d024  mov     dword ptr [rax+8], 0
0x14000d02b  mov     qword ptr [rbx+8], 0
0x14000d033  mov     r10, [rcx+20h]
0x14000d037  test    r10b, 1
0x14000d03b  jz      loc_14000D281
0x14000d041  mov     rax, [rcx+18h]
0x14000d045  mov     ecx, 202h
0x14000d04a  cmp     cx, [rax]
0x14000d04d  jnz     loc_14000D28C
0x14000d053  mov     r15, [rsi+20h]
0x14000d057  xor     edx, edx
0x14000d059  mov     rdi, [rsi+20h]
0x14000d05d  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14000d061  shr     r15, 1
0x14000d064  and     r15d, 1
0x14000d068  mov     r12, [rdi+28h]
0x14000d06c  lea     r13, [rdi+40h]
0x14000d070  mov     rcx, r13
0x14000d073  mov     [rsp+98h+arg_20], r12
0x14000d07b  mov     r14d, [r12+100h]
0x14000d083  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d08a  nop     dword ptr [rax+rax+00h]
0x14000d08f  mov     rax, [rsi+20h]
0x14000d093  test    al, 1
0x14000d095  jnz     short loc_14000D0C9
0x14000d097  mov     dword ptr [rbx], 0C00000B0h
0x14000d09d  xor     edx, edx
0x14000d09f  mov     rcx, r13
0x14000d0a2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d0a9  nop     dword ptr [rax+rax+00h]
0x14000d0ae  mov     al, 1
0x14000d0b0  mov     rbx, [rsp+98h+arg_10]
0x14000d0b8  add     rsp, 60h
0x14000d0bc  pop     r15
0x14000d0be  pop     r14
0x14000d0c0  pop     r13
0x14000d0c2  pop     r12
0x14000d0c4  pop     rdi
0x14000d0c5  pop     rsi
0x14000d0c6  pop     rbp
0x14000d0c7  retn
0x14000d0c9  mov     cl, [rdi+8]
0x14000d0cc  cmp     cl, 3
0x14000d0cf  jnz     loc_14000D297
0x14000d0d5  movzx   eax, r14w
0x14000d0d9  test    r15d, r15d
0x14000d0dc  jz      loc_14000D1D2
0x14000d0e2  test    eax, eax
0x14000d0e4  jnz     short loc_14000D0EE
0x14000d0e6  mov     dword ptr [rbx], 0C000000Dh
0x14000d0ec  jmp     short loc_14000D09D
0x14000d0ee  mov     dl, [rdi+9]
0x14000d0f1  lea     rsi, [rdi+0A8h]
0x14000d0f8  mov     r14, [rsp+98h+arg_28]
0x14000d100  mov     dword ptr [rbx], 0
0x14000d106  mov     [rbx+8], rbp
0x14000d10a  cmp     dword ptr [rsi+10h], 0
0x14000d10e  jnz     loc_14000D247
0x14000d114  mov     ecx, [rsi+14h]
0x14000d117  cmp     ecx, ebp
0x14000d119  jb      loc_14000D2B5
0x14000d11f  movzx   r12d, dl
0x14000d123  and     r12d, 1
0x14000d127  test    r14, r14
0x14000d12a  jz      loc_14000D2EB
0x14000d130  mov     al, [r14+40h]
0x14000d134  mov     rcx, [rsp+98h+arg_30]
0x14000d13c  mov     r9d, ebp
0x14000d13f  mov     r8, [rsp+98h+arg_8]
0x14000d147  mov     edx, r12d
0x14000d14a  mov     [rsp+98h+var_48], rcx
0x14000d14f  mov     rcx, [rsp+98h+arg_18]
0x14000d157  mov     [rsp+98h+var_50], rcx
0x14000d15c  lea     rcx, [rsp+98h+arg_0]
0x14000d164  mov     [rsp+98h+var_58], r15d
0x14000d169  mov     [rsp+98h+Src], rdi
0x14000d16e  mov     [rsp+98h+var_68], rcx
0x14000d173  mov     rcx, [rsp+98h+arg_20]
0x14000d17b  mov     ecx, [rcx+104h]
0x14000d181  mov     dword ptr [rsp+98h+Size], ecx
0x14000d185  mov     rcx, rsi
0x14000d188  mov     byte ptr [rsp+98h+var_78], al
0x14000d18c  call    NpWriteDataQueue
0x14000d191  mov     [rbx], eax
0x14000d193  mov     r9d, eax
0x14000d196  cmp     eax, 0C0000016h
0x14000d19b  jz      short loc_14000D1E7
0x14000d19d  test    ebp, ebp
0x14000d19f  jz      loc_14000D09D
0x14000d1a5  mov     rax, [rbx+8]
0x14000d1a9  mov     r8, rsi
0x14000d1ac  mov     edx, r15d
0x14000d1af  mov     qword ptr [rsp+98h+var_78], rax
0x14000d1b4  mov     rcx, rdi
0x14000d1b7  call    NpEventsWriteCompleted
0x14000d1bc  mov     rax, ds:0FFFFF78000000014h
0x14000d1c6  mov     [rdi+1C0h], rax
0x14000d1cd  jmp     loc_14000D09D
0x14000d1d2  cmp     eax, 1
0x14000d1d5  jz      loc_14000D0E6
0x14000d1db  mov     dl, [rdi+0Ah]
0x14000d1de  lea     rsi, [rdi+48h]
0x14000d1e2  jmp     loc_14000D0F8
0x14000d1e7  test    byte ptr [r15+rdi+9], 2
0x14000d1ed  mov     edx, [rsp+98h+arg_0]
0x14000d1f4  jnz     loc_14000D2FC
0x14000d1fa  test    r14, r14
0x14000d1fd  jz      loc_14000D2FC
0x14000d203  mov     eax, ebp
0x14000d205  mov     r9d, 1; int
0x14000d20b  sub     eax, edx
0x14000d20d  mov     r8, rsi; int
0x14000d210  mov     [rsp+98h+var_58], eax; int
0x14000d214  mov     rdx, rdi; int
0x14000d217  mov     rax, [rsp+98h+arg_8]
0x14000d21f  mov     ecx, r15d; int
0x14000d222  mov     [rsp+98h+Src], rax; Src
0x14000d227  mov     [rsp+98h+var_68], r14; __int64
0x14000d22c  mov     dword ptr [rsp+98h+Size], ebp; Size
0x14000d230  mov     [rsp+98h+var_78], 0; int
0x14000d238  call    NpAddDataQueueEntry
0x14000d23d  mov     r9d, eax
0x14000d240  mov     [rbx], eax
0x14000d242  jmp     loc_14000D19D
0x14000d247  mov     ecx, [rsi+1Ch]
0x14000d24a  sub     ecx, [rsi+20h]
0x14000d24d  cmp     ecx, ebp
0x14000d24f  jnb     loc_14000D11F
0x14000d255  cmp     dword ptr [r12+104h], 0
0x14000d25e  jz      short loc_14000D2C3
0x14000d260  test    r14, r14
0x14000d263  jnz     loc_14000D11F
0x14000d269  xor     edx, edx
0x14000d26b  mov     rcx, r13
0x14000d26e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d275  nop     dword ptr [rax+rax+00h]
0x14000d27a  xor     al, al
0x14000d27c  jmp     loc_14000D0B0
0x14000d281  mov     dword ptr [rbx], 0C00000B0h
0x14000d287  jmp     loc_14000D0AE
0x14000d28c  mov     dword ptr [rbx], 0C000000Dh
0x14000d292  jmp     loc_14000D0AE
0x14000d297  cmp     cl, 1
0x14000d29a  jz      loc_14000D097
0x14000d2a0  mov     eax, 0C00000B1h
0x14000d2a5  cmp     cl, 2
0x14000d2a8  lea     edx, [rax+2]
0x14000d2ab  cmovz   eax, edx
0x14000d2ae  mov     [rbx], eax
0x14000d2b0  jmp     loc_14000D09D
0x14000d2b5  mov     eax, ebp
0x14000d2b7  sub     eax, ecx
0x14000d2b9  cmp     [rsi+1Ch], eax
0x14000d2bc  jb      short loc_14000D255
0x14000d2be  jmp     loc_14000D11F
0x14000d2c3  test    byte ptr [r15+rdi+9], 2
0x14000d2c9  jz      short loc_14000D260
0x14000d2cb  mov     qword ptr [rbx+8], 0
0x14000d2d3  jmp     short loc_14000D2E3
0x14000d2d5  mov     eax, ebp
0x14000d2d7  mov     dword ptr [rbx], 0
0x14000d2dd  sub     eax, edx
0x14000d2df  mov     [rbx+8], rax
0x14000d2e3  xor     r9d, r9d
0x14000d2e6  jmp     loc_14000D19D
0x14000d2eb  call    cs:__imp_ExGetPreviousMode
0x14000d2f2  nop     dword ptr [rax+rax+00h]
0x14000d2f7  jmp     loc_14000D134
0x14000d2fc  mov     ecx, [rsi+1Ch]
0x14000d2ff  sub     ecx, [rsi+20h]
0x14000d302  cmp     ecx, edx
0x14000d304  jnb     loc_14000D203
0x14000d30a  jmp     short loc_14000D2D5
```
