# RxpBuildTargetFcbTableNameForRename

- ea: `0x14006a2b0`
- end: `0x14006a4b7`
- name: `RxpBuildTargetFcbTableNameForRename`
- size: `519`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140069a20`
- `0x14006f9e0`

## callees

- `0x14000e290`
- `0x140011610`
- `0x140019924`
- `0x14001f150`
- `0x140025d80`
- `0x14006a2b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006a3ef`
- `ntoskrnl!ExAllocatePool2` at `0x14006a3ef`

## pseudocode

```c
__int64 __fastcall RxpBuildTargetFcbTableNameForRename(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  unsigned int v4; // ebx
  __int64 v5; // r13
  int v7; // ebp
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int v11; // edi
  unsigned __int16 v12; // ax
  __int64 v13; // r12
  unsigned int v14; // ecx
  void *Pool2; // rax
  __int128 v17; // [rsp+40h] [rbp-48h] BYREF
  __int16 v18; // [rsp+90h] [rbp+8h] BYREF
  __int16 v19; // [rsp+98h] [rbp+10h] BYREF

  v4 = 0;
  v5 = *(_QWORD *)(a1 + 56);
  v7 = a1;
  v9 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 24LL);
  if ( v9 )
  {
    *(_OWORD *)a3 = *(_OWORD *)(*(_QWORD *)(v9 + 24) + 336LL);
    *a4 = 0;
  }
  else
  {
    v10 = *(_QWORD *)(a2 + 24);
    v17 = 0;
    v11 = *(_DWORD *)(v10 + 16);
    if ( v11 <= 0xFFFE )
    {
      RxLastComponentUnicodeString(v5 + 336, 92, &v17);
      if ( *(_WORD *)(v10 + 20) == 58 )
      {
        v19 = 0;
        v18 = 0;
        RxFindSeparatorN((unsigned int)&v17, 0, 1, 58, (__int64)&v19, (__int64)&v18);
        v12 = 0;
        if ( v18 )
          v12 = v17 - v19;
      }
      else
      {
        v12 = v17;
      }
      v13 = v12;
      v14 = v11 + *(unsigned __int16 *)(v5 + 336) - v12;
      if ( v14 >= v11 )
      {
        if ( v14 <= 0xFFFE )
        {
          *(_WORD *)(a3 + 2) = v14;
          *(_WORD *)a3 = v14;
          Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)v14, 1934456914);
          *(_QWORD *)(a3 + 8) = Pool2;
          if ( Pool2 )
          {
            memmove(Pool2, *(const void **)(v5 + 344), *(unsigned __int16 *)(v5 + 336) - v13);
            memmove(
              (void *)(*(_QWORD *)(a3 + 8) + *(unsigned __int16 *)(v5 + 336) - v13),
              (const void *)(v10 + 20),
              *(unsigned int *)(v10 + 16));
            RxRemoveDollarDataSuffix(a3, 0);
            *a4 = 1;
          }
          else
          {
            v4 = -1073741670;
          }
        }
        else
        {
          v4 = -1073741562;
        }
      }
      else
      {
        v4 = -1073741811;
      }
    }
    else
    {
      v4 = -1073741562;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqZZ(WPP_GLOBAL_Control->AttachedDevice, v5 + 336, a3, v7, v5, v5 + 336, a3);
  }
  return v4;
}

```

## disassembly

```asm
0x14006a2b0  push    rbx
0x14006a2b2  push    rbp
0x14006a2b3  push    r13
0x14006a2b5  push    r15
0x14006a2b7  sub     rsp, 68h
0x14006a2bb  mov     rax, [rdx+0B8h]
0x14006a2c2  xor     ebx, ebx
0x14006a2c4  mov     r13, [rcx+38h]
0x14006a2c8  mov     r15, r8
0x14006a2cb  mov     [rsp+88h+var_38], r14
0x14006a2d0  mov     rbp, rcx
0x14006a2d3  mov     r14, r9
0x14006a2d6  mov     rax, [rax+18h]
0x14006a2da  test    rax, rax
0x14006a2dd  jz      short loc_14006A2F6
0x14006a2df  mov     rax, [rax+18h]
0x14006a2e3  movups  xmm0, xmmword ptr [rax+150h]
0x14006a2ea  movups  xmmword ptr [r8], xmm0
0x14006a2ee  mov     [r9], bl
0x14006a2f1  jmp     loc_14006A461
0x14006a2f6  mov     [rsp+88h+arg_10], rsi
0x14006a2fe  xorps   xmm0, xmm0
0x14006a301  mov     rsi, [rdx+18h]
0x14006a305  mov     [rsp+88h+var_28], rdi
0x14006a30a  movups  [rsp+88h+var_48], xmm0
0x14006a30f  mov     edi, [rsi+10h]
0x14006a312  cmp     edi, 0FFFEh
0x14006a318  jbe     short loc_14006A324
0x14006a31a  mov     ebx, 0C0000106h
0x14006a31f  jmp     loc_14006A454
0x14006a324  lea     rcx, [r13+150h]
0x14006a32b  mov     [rsp+88h+var_30], r12
0x14006a330  mov     edx, 5Ch ; '\'
0x14006a335  lea     r8, [rsp+88h+var_48]
0x14006a33a  call    RxLastComponentUnicodeString
0x14006a33f  mov     r9d, 3Ah ; ':'
0x14006a345  cmp     r9w, [rsi+14h]
0x14006a34a  jnz     short loc_14006A3A5
0x14006a34c  xor     eax, eax
0x14006a34e  lea     rcx, [rsp+88h+var_48]
0x14006a353  mov     [rsp+88h+arg_8], ax
0x14006a35b  xor     edx, edx
0x14006a35d  mov     [rsp+88h+arg_0], ax
0x14006a365  mov     r8d, 1
0x14006a36b  lea     rax, [rsp+88h+arg_0]
0x14006a373  mov     [rsp+88h+var_60], rax
0x14006a378  lea     rax, [rsp+88h+arg_8]
0x14006a380  mov     [rsp+88h+var_68], rax
0x14006a385  call    RxFindSeparatorN
0x14006a38a  xor     eax, eax
0x14006a38c  cmp     ax, [rsp+88h+arg_0]
0x14006a394  jz      short loc_14006A3AA
0x14006a396  movzx   eax, word ptr [rsp+88h+var_48]
0x14006a39b  sub     ax, [rsp+88h+arg_8]
0x14006a3a3  jmp     short loc_14006A3AA
0x14006a3a5  movzx   eax, word ptr [rsp+88h+var_48]
0x14006a3aa  movzx   ecx, word ptr [r13+150h]
0x14006a3b2  movzx   r12d, ax
0x14006a3b6  sub     ecx, r12d
0x14006a3b9  add     ecx, edi
0x14006a3bb  cmp     ecx, edi
0x14006a3bd  jnb     short loc_14006A3C9
0x14006a3bf  mov     ebx, 0C000000Dh
0x14006a3c4  jmp     loc_14006A44F
0x14006a3c9  cmp     ecx, 0FFFEh
0x14006a3cf  jbe     short loc_14006A3D8
0x14006a3d1  mov     ebx, 0C0000106h
0x14006a3d6  jmp     short loc_14006A44F
0x14006a3d8  movzx   edx, cx
0x14006a3db  mov     r8d, 734D7852h
0x14006a3e1  mov     ecx, 102h
0x14006a3e6  mov     [r15+2], dx
0x14006a3eb  mov     [r15], dx
0x14006a3ef  call    cs:__imp_ExAllocatePool2
0x14006a3f6  nop     dword ptr [rax+rax+00h]
0x14006a3fb  mov     [r15+8], rax
0x14006a3ff  test    rax, rax
0x14006a402  jnz     short loc_14006A40B
0x14006a404  mov     ebx, 0C000009Ah
0x14006a409  jmp     short loc_14006A44F
0x14006a40b  movzx   r8d, word ptr [r13+150h]
0x14006a413  mov     rcx, rax; void *
0x14006a416  mov     rdx, [r13+158h]; Src
0x14006a41d  sub     r8, r12; Size
0x14006a420  call    memmove
0x14006a425  movzx   ecx, word ptr [r13+150h]
0x14006a42d  lea     rdx, [rsi+14h]; Src
0x14006a431  mov     r8d, [rsi+10h]; Size
0x14006a435  sub     rcx, r12
0x14006a438  add     rcx, [r15+8]; void *
0x14006a43c  call    memmove
0x14006a441  xor     edx, edx
0x14006a443  mov     rcx, r15
0x14006a446  call    RxRemoveDollarDataSuffix
0x14006a44b  mov     byte ptr [r14], 1
0x14006a44f  mov     r12, [rsp+88h+var_30]
0x14006a454  mov     rsi, [rsp+88h+arg_10]
0x14006a45c  mov     rdi, [rsp+88h+var_28]
0x14006a461  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a468  lea     rax, WPP_GLOBAL_Control
0x14006a46f  mov     r14, [rsp+88h+var_38]
0x14006a474  cmp     rcx, rax
0x14006a477  jz      short loc_14006A4A9
0x14006a479  mov     edx, [rcx+2Ch]
0x14006a47c  test    dl, 20h
0x14006a47f  jz      short loc_14006A4A9
0x14006a481  cmp     byte ptr [rcx+29h], 2
0x14006a485  jb      short loc_14006A4A9
0x14006a487  mov     rcx, [rcx+18h]
0x14006a48b  lea     rdx, [r13+150h]
0x14006a492  mov     [rsp+88h+var_58], r15
0x14006a497  mov     r9, rbp
0x14006a49a  mov     [rsp+88h+var_60], rdx
0x14006a49f  mov     [rsp+88h+var_68], r13
0x14006a4a4  call    WPP_SF_qqZZ
0x14006a4a9  mov     eax, ebx
0x14006a4ab  add     rsp, 68h
0x14006a4af  pop     r15
0x14006a4b1  pop     r13
0x14006a4b3  pop     rbp
0x14006a4b4  pop     rbx
0x14006a4b5  retn
```
