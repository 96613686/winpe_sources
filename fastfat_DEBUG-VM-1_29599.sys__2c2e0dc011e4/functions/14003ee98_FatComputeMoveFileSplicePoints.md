# FatComputeMoveFileSplicePoints

- ea: `0x14003ee98`
- end: `0x14003f0fc`
- name: `FatComputeMoveFileSplicePoints`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400412a8`

## callees

- `0x140005c80`
- `0x14003eb84`
- `0x14003ee98`
- `0x14003f50c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003efd9`
- `ntoskrnl!ExRaiseStatus` at `0x14003efd9`

## pseudocode

```c
_DWORD *__fastcall FatComputeMoveFileSplicePoints(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        _DWORD *a9,
        __int64 a10)
{
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v13; // rdx
  char v14; // al
  __int64 v15; // r14
  _BYTE *v16; // r15
  unsigned int v17; // ebx
  _QWORD *v18; // r13
  char v19; // r8
  char v20; // al
  __int64 v21; // r14
  int v22; // ebx
  int v23; // edx
  char NextMcbEntry; // al
  unsigned int v25; // esi
  int v26; // edx
  unsigned int v27; // r12d
  __int64 v28; // r8
  __int64 v29; // r15
  unsigned int v30; // r13d
  _DWORD *result; // rax
  __int64 v32; // rdx
  bool v33; // zf
  _BYTE v34[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v35; // [rsp+38h] [rbp-28h] BYREF
  _BYTE *v36; // [rsp+40h] [rbp-20h]
  _QWORD *v37; // [rsp+48h] [rbp-18h]
  __int64 v38; // [rsp+50h] [rbp-10h]
  unsigned int v39; // [rsp+A8h] [rbp+48h] BYREF
  int v40; // [rsp+B0h] [rbp+50h] BYREF
  int v41; // [rsp+B8h] [rbp+58h]

  v41 = a4;
  v10 = *(_QWORD *)(a2 + 184);
  v11 = a2 + 288;
  v38 = a2 + 288;
  v13 = a2 + 288;
  v35 = 0;
  v39 = 0;
  v40 = 0;
  if ( (_DWORD)a3 )
  {
    v20 = FatLookupMcbEntry(v10, v13, (unsigned int)(a3 - 1), &v35, &v40, &v39);
    v21 = v35;
    v18 = (_QWORD *)(v10 + 352);
    v22 = v40;
    v16 = (_BYTE *)(v10 + 378);
    v19 = v20;
    v23 = ((v35 - *(_QWORD *)(v10 + 352)) >> *(_BYTE *)(v10 + 378)) + 2;
    v37 = (_QWORD *)(v10 + 352);
    v36 = (_BYTE *)(v10 + 378);
    *a6 = v23;
    if ( v20 && v22 == 1 )
    {
      NextMcbEntry = FatGetNextMcbEntry(v10, v11, ++v39, v34, &v35, &v40);
      v15 = v35;
      v19 = NextMcbEntry;
      v17 = v40;
      goto LABEL_8;
    }
    v15 = v21 + 1;
    v17 = v22 - 1;
    v35 = v15;
    v40 = v17;
  }
  else
  {
    *a6 = 0;
    v14 = FatGetNextMcbEntry(v10, v13, a3, v34, &v35, &v40);
    v15 = v35;
    v16 = (_BYTE *)(v10 + 378);
    v17 = v40;
    v18 = (_QWORD *)(v10 + 352);
    v19 = v14;
  }
  v37 = v18;
  v36 = v16;
LABEL_8:
  if ( !v19 )
  {
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  v25 = 0;
  v26 = v41;
  v27 = a5;
  v28 = v39;
  *a7 = v41;
  *a8 = (v27 >> *v16) + v26 - 1;
  if ( v27 )
  {
    v29 = v38;
    v30 = 0;
    do
    {
      if ( v30 )
      {
        FatGetNextMcbEntry(v10, v29, v28, v34, &v35, &v40);
        v15 = v35;
        v17 = v40;
      }
      v25 = v27;
      if ( v17 < v27 )
        v25 = v17;
      FatAddMcbEntry(v10, a10, v30, v15, v25);
      v30 += v25;
      v28 = ++v39;
      v27 -= v25;
    }
    while ( v27 );
    v16 = v36;
    v18 = v37;
  }
  if ( v25 < v17 )
  {
    result = a9;
    v32 = v15 + v25 - *(_QWORD *)(v10 + 352);
LABEL_22:
    *result = (v32 >> *v16) + 2;
    return result;
  }
  v33 = (unsigned __int8)FatGetNextMcbEntry(v10, v38, v28, v34, &v35, &v40) == 0;
  result = a9;
  if ( !v33 )
  {
    v32 = v35 - *v18;
    goto LABEL_22;
  }
  *a9 = 0xFFFFFFF;
  return result;
}

```

## disassembly

```asm
0x14003ee98  mov     r11, rsp
0x14003ee9b  mov     [r11+8], rbx
0x14003ee9f  mov     [r11+20h], r9d
0x14003eea3  push    rbp
0x14003eea4  push    rsi
0x14003eea5  push    rdi
0x14003eea6  push    r12
0x14003eea8  push    r13
0x14003eeaa  push    r14
0x14003eeac  push    r15
0x14003eeae  mov     rbp, rsp
0x14003eeb1  sub     rsp, 60h
0x14003eeb5  mov     rdi, [rdx+0B8h]
0x14003eebc  lea     rsi, [rdx+120h]
0x14003eec3  mov     r12, rcx
0x14003eec6  mov     [rbp+var_10], rsi
0x14003eeca  xor     ecx, ecx
0x14003eecc  mov     rdx, rsi
0x14003eecf  mov     [rbp+var_28], rcx
0x14003eed3  mov     [rbp+arg_8], ecx
0x14003eed6  mov     [rbp+arg_10], ecx
0x14003eed9  test    r8d, r8d
0x14003eedc  jnz     short loc_14003EF1D
0x14003eede  mov     rax, [rbp+arg_28]
0x14003eee2  lea     r9, [rbp+var_30]
0x14003eee6  mov     [rax], ecx
0x14003eee8  lea     rax, [rbp+arg_10]
0x14003eeec  mov     [r11-70h], rax
0x14003eef0  mov     rcx, rdi
0x14003eef3  lea     rax, [rbp+var_28]
0x14003eef7  mov     [r11-78h], rax
0x14003eefb  call    FatGetNextMcbEntry
0x14003ef00  mov     r14, [rbp+var_28]
0x14003ef04  lea     r15, [rdi+17Ah]
0x14003ef0b  mov     ebx, [rbp+arg_10]
0x14003ef0e  lea     r13, [rdi+160h]
0x14003ef15  mov     r8b, al
0x14003ef18  jmp     loc_14003EFC2
0x14003ef1d  lea     rax, [rbp+arg_8]
0x14003ef21  dec     r8d
0x14003ef24  mov     [rsp+60h+var_38], rax
0x14003ef29  lea     r9, [rbp+var_28]
0x14003ef2d  lea     rax, [rbp+arg_10]
0x14003ef31  mov     rcx, rdi
0x14003ef34  mov     [rsp+60h+var_40], rax
0x14003ef39  call    FatLookupMcbEntry
0x14003ef3e  mov     r14, [rbp+var_28]
0x14003ef42  lea     r13, [rdi+160h]
0x14003ef49  mov     ebx, [rbp+arg_10]
0x14003ef4c  lea     r15, [rdi+17Ah]
0x14003ef53  mov     cl, [r15]
0x14003ef56  mov     r8b, al
0x14003ef59  mov     rax, [rbp+arg_28]
0x14003ef5d  mov     rdx, r14
0x14003ef60  sub     rdx, [r13+0]
0x14003ef64  sar     rdx, cl
0x14003ef67  add     edx, 2
0x14003ef6a  mov     [rbp+var_18], r13
0x14003ef6e  mov     [rbp+var_20], r15
0x14003ef72  mov     [rax], edx
0x14003ef74  test    r8b, r8b
0x14003ef77  jz      short loc_14003EFB6
0x14003ef79  cmp     ebx, 1
0x14003ef7c  jnz     short loc_14003EFB6
0x14003ef7e  mov     r8d, [rbp+arg_8]
0x14003ef82  lea     rax, [rbp+arg_10]
0x14003ef86  mov     [rsp+60h+var_38], rax
0x14003ef8b  lea     r9, [rbp+var_30]
0x14003ef8f  lea     rax, [rbp+var_28]
0x14003ef93  inc     r8d
0x14003ef96  mov     rdx, rsi
0x14003ef99  mov     [rsp+60h+var_40], rax
0x14003ef9e  mov     rcx, rdi
0x14003efa1  mov     [rbp+arg_8], r8d
0x14003efa5  call    FatGetNextMcbEntry
0x14003efaa  mov     r14, [rbp+var_28]
0x14003efae  mov     r8b, al
0x14003efb1  mov     ebx, [rbp+arg_10]
0x14003efb4  jmp     short loc_14003EFCA
0x14003efb6  inc     r14
0x14003efb9  dec     ebx
0x14003efbb  mov     [rbp+var_28], r14
0x14003efbf  mov     [rbp+arg_10], ebx
0x14003efc2  mov     [rbp+var_18], r13
0x14003efc6  mov     [rbp+var_20], r15
0x14003efca  test    r8b, r8b
0x14003efcd  jnz     short loc_14003EFE6
0x14003efcf  mov     ecx, 0C0000102h; Status
0x14003efd4  mov     [r12+48h], ecx
0x14003efd9  call    cs:__imp_ExRaiseStatus
0x14003efe6  mov     rax, [rbp+arg_30]
0x14003efea  xor     esi, esi
0x14003efec  mov     edx, [rbp+arg_18]
0x14003efef  mov     r12d, [rbp+arg_20]
0x14003eff3  mov     r8d, [rbp+arg_8]
0x14003eff7  mov     [rax], edx
0x14003eff9  mov     eax, r12d
0x14003effc  mov     cl, [r15]
0x14003efff  shr     eax, cl
0x14003f001  lea     ecx, [rdx-1]
0x14003f004  add     ecx, eax
0x14003f006  mov     rax, [rbp+arg_38]
0x14003f00a  mov     [rax], ecx
0x14003f00c  test    r12d, r12d
0x14003f00f  jz      short loc_14003F082
0x14003f011  mov     r15, [rbp+var_10]
0x14003f015  mov     r13d, esi
0x14003f018  test    r13d, r13d
0x14003f01b  jz      short loc_14003F045
0x14003f01d  lea     rax, [rbp+arg_10]
0x14003f021  mov     rdx, r15
0x14003f024  mov     [rsp+60h+var_38], rax
0x14003f029  lea     r9, [rbp+var_30]
0x14003f02d  lea     rax, [rbp+var_28]
0x14003f031  mov     rcx, rdi
0x14003f034  mov     [rsp+60h+var_40], rax
0x14003f039  call    FatGetNextMcbEntry
0x14003f03e  mov     r14, [rbp+var_28]
0x14003f042  mov     ebx, [rbp+arg_10]
0x14003f045  mov     rdx, [rbp+arg_48]
0x14003f04c  cmp     ebx, r12d
0x14003f04f  mov     esi, r12d
0x14003f052  mov     r9, r14
0x14003f055  cmovb   esi, ebx
0x14003f058  mov     r8d, r13d
0x14003f05b  mov     rcx, rdi
0x14003f05e  mov     dword ptr [rsp+60h+var_40], esi
0x14003f062  call    FatAddMcbEntry
0x14003f067  mov     r8d, [rbp+arg_8]
0x14003f06b  add     r13d, esi
0x14003f06e  inc     r8d
0x14003f071  mov     [rbp+arg_8], r8d
0x14003f075  sub     r12d, esi
0x14003f078  jnz     short loc_14003F018
0x14003f07a  mov     r15, [rbp+var_20]
0x14003f07e  mov     r13, [rbp+var_18]
0x14003f082  cmp     esi, ebx
0x14003f084  jnb     short loc_14003F09B
0x14003f086  mov     rax, [rbp+arg_40]
0x14003f08d  mov     edx, esi
0x14003f08f  sub     rdx, [rdi+160h]
0x14003f096  add     rdx, r14
0x14003f099  jmp     short loc_14003F0D0
0x14003f09b  mov     rdx, [rbp+var_10]
0x14003f09f  lea     rax, [rbp+arg_10]
0x14003f0a3  mov     [rsp+60h+var_38], rax
0x14003f0a8  lea     r9, [rbp+var_30]
0x14003f0ac  lea     rax, [rbp+var_28]
0x14003f0b0  mov     rcx, rdi
0x14003f0b3  mov     [rsp+60h+var_40], rax
0x14003f0b8  call    FatGetNextMcbEntry
0x14003f0bd  test    al, al
0x14003f0bf  mov     rax, [rbp+arg_40]
0x14003f0c6  jz      short loc_14003F0DD
0x14003f0c8  mov     rdx, [rbp+var_28]
0x14003f0cc  sub     rdx, [r13+0]
0x14003f0d0  mov     cl, [r15]
0x14003f0d3  sar     rdx, cl
0x14003f0d6  add     edx, 2
0x14003f0d9  mov     [rax], edx
0x14003f0db  jmp     short loc_14003F0E3
0x14003f0dd  mov     dword ptr [rax], 0FFFFFFFh
0x14003f0e3  mov     rbx, [rsp+60h+arg_0]
0x14003f0eb  add     rsp, 60h
0x14003f0ef  pop     r15
0x14003f0f1  pop     r14
0x14003f0f3  pop     r13
0x14003f0f5  pop     r12
0x14003f0f7  pop     rdi
0x14003f0f8  pop     rsi
0x14003f0f9  pop     rbp
0x14003f0fa  retn
```
