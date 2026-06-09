# sub_18009EAEC

- ea: `0x18009eaec`
- end: `0x18009ec63`
- name: `sub_18009EAEC`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009ea30`

## callees

- `0x18009eaec`
- `0x1801411f8`
- `0x180189008`
- `0x1801899dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009eb36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009eb36`

## pseudocode

```c
__int64 __fastcall sub_18009EAEC(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  int v4; // edi
  int v6; // ebx
  __int16 v7; // ax
  bool v8; // cc
  __int64 v9; // rcx
  int v10; // r8d
  __int64 v11; // rcx
  __int128 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h]
  unsigned int v15; // [rsp+84h] [rbp+34h]

  v15 = HIDWORD(a3);
  v13 = 0;
  v4 = a2;
  if ( (xmmword_1801FAD20 & 2) != 0 )
    sub_1801899DC(a1, a2, a3, a1, a2, a3);
  if ( *(_DWORD *)(a1 + 48) && *(_DWORD *)(a1 + 48) != GetCurrentThreadId() )
  {
    v6 = -2147417842;
    goto LABEL_27;
  }
  if ( v4 <= 6 )
  {
    if ( v4 == 6 )
      goto LABEL_11;
    if ( (unsigned int)v4 > 2 )
    {
      if ( v4 == 3 || (unsigned int)(v4 - 4) <= 1 )
      {
LABEL_11:
        LOWORD(v13) = 11;
        if ( a3 )
          v7 = -1;
        else
          v7 = 0;
        WORD4(v13) = v7;
        goto LABEL_26;
      }
LABEL_15:
      v6 = -2147024809;
      goto LABEL_27;
    }
    goto LABEL_13;
  }
  switch ( v4 )
  {
    case 7:
      goto LABEL_11;
    case 8:
LABEL_13:
      v8 = a3 <= 0xFFFFFFFF;
LABEL_14:
      if ( !v8 )
        goto LABEL_15;
      DWORD2(v13) = a3;
      LOWORD(v13) = 19;
      goto LABEL_26;
    case 9:
      *((_QWORD *)&v13 + 1) = __PAIR64__(v15, a3);
      LOWORD(v13) = 21;
      goto LABEL_26;
  }
  if ( v4 != 10 )
  {
    if ( v4 != 11 )
      goto LABEL_15;
    v8 = a3 - 2 <= 0x7E;
    goto LABEL_14;
  }
LABEL_26:
  v9 = *(_QWORD *)(a1 + 40);
  v14 = 0;
  v6 = sub_1801411F8(v9, (unsigned int)v4, &v13);
LABEL_27:
  v10 = v6 >> 31;
  if ( (xmmword_1801FAD00[(v6 >> 31) + 2] & 2) != 0 )
  {
    v11 = (unsigned __int16)(v10 + 2) << 9;
    LOWORD(v11) = (((_WORD)v10 + 2) << 9) | 1;
    sub_180189008(v11, 148, qword_1801DA730, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009eaec  mov     rax, rsp
0x18009eaef  mov     [rax+8], rbx
0x18009eaf3  mov     [rax+10h], rsi
0x18009eaf7  mov     [rax+18h], r8
0x18009eafb  push    rbp
0x18009eafc  push    rdi
0x18009eafd  push    r14
0x18009eaff  mov     rbp, rsp
0x18009eb02  sub     rsp, 50h
0x18009eb06  xorps   xmm0, xmm0
0x18009eb09  mov     rbx, r8
0x18009eb0c  movups  [rbp+var_20], xmm0
0x18009eb10  mov     edi, edx
0x18009eb12  mov     rsi, rcx
0x18009eb15  xor     r14d, r14d
0x18009eb18  test    byte ptr cs:xmmword_1801FAD20, 2
0x18009eb1f  jz      short loc_18009EB30
0x18009eb21  mov     [rax-40h], rbx
0x18009eb25  mov     r9, rcx
0x18009eb28  mov     [rax-48h], edx
0x18009eb2b  call    sub_1801899DC
0x18009eb30  cmp     [rsi+30h], r14d
0x18009eb34  jz      short loc_18009EB51
0x18009eb36  call    cs:GetCurrentThreadId
0x18009eb3d  nop     dword ptr [rax+rax+00h]
0x18009eb42  cmp     [rsi+30h], eax
0x18009eb45  jz      short loc_18009EB51
0x18009eb47  mov     ebx, 8001010Eh
0x18009eb4c  jmp     loc_18009EC05
0x18009eb51  cmp     edi, 6
0x18009eb54  jg      short loc_18009EB9B
0x18009eb56  jz      short loc_18009EB77
0x18009eb58  mov     ecx, edi
0x18009eb5a  test    edi, edi
0x18009eb5c  jz      short loc_18009EB8A
0x18009eb5e  sub     ecx, 1
0x18009eb61  jz      short loc_18009EB8A
0x18009eb63  sub     ecx, 1
0x18009eb66  jz      short loc_18009EB8A
0x18009eb68  sub     ecx, 1
0x18009eb6b  jz      short loc_18009EB77
0x18009eb6d  sub     ecx, 1
0x18009eb70  jz      short loc_18009EB77
0x18009eb72  cmp     ecx, 1
0x18009eb75  jnz     short loc_18009EB94
0x18009eb77  mov     eax, 0Bh
0x18009eb7c  mov     word ptr [rbp+var_20], ax
0x18009eb80  test    rbx, rbx
0x18009eb83  jz      short loc_18009EBE2
0x18009eb85  or      eax, 0FFFFFFFFh
0x18009eb88  jmp     short loc_18009EBE4
0x18009eb8a  mov     eax, 0FFFFFFFFh
0x18009eb8f  cmp     rbx, rax
0x18009eb92  jbe     short loc_18009EBD4
0x18009eb94  mov     ebx, 80070057h
0x18009eb99  jmp     short loc_18009EC05
0x18009eb9b  mov     ecx, edi
0x18009eb9d  sub     ecx, 7
0x18009eba0  jz      short loc_18009EB77
0x18009eba2  sub     ecx, 1
0x18009eba5  jz      short loc_18009EB8A
0x18009eba7  sub     ecx, 1
0x18009ebaa  jz      short loc_18009EBC0
0x18009ebac  sub     ecx, 1
0x18009ebaf  jz      short loc_18009EBE8
0x18009ebb1  cmp     ecx, 1
0x18009ebb4  jnz     short loc_18009EB94
0x18009ebb6  lea     rax, [rbx-2]
0x18009ebba  cmp     rax, 7Eh ; '~'
0x18009ebbe  jmp     short loc_18009EB92
0x18009ebc0  mov     eax, 15h
0x18009ebc5  mov     dword ptr [rbp+var_20+8], ebx
0x18009ebc8  mov     word ptr [rbp+var_20], ax
0x18009ebcc  mov     eax, [rbp+arg_14]
0x18009ebcf  mov     dword ptr [rbp+var_20+0Ch], eax
0x18009ebd2  jmp     short loc_18009EBE8
0x18009ebd4  mov     eax, 13h
0x18009ebd9  mov     dword ptr [rbp+var_20+8], ebx
0x18009ebdc  mov     word ptr [rbp+var_20], ax
0x18009ebe0  jmp     short loc_18009EBE8
0x18009ebe2  xor     eax, eax
0x18009ebe4  mov     word ptr [rbp+var_20+8], ax
0x18009ebe8  movups  xmm0, [rbp+var_20]
0x18009ebec  mov     rcx, [rsi+28h]
0x18009ebf0  lea     r8, [rbp+var_20]
0x18009ebf4  mov     edx, edi
0x18009ebf6  mov     [rbp+var_10], r14
0x18009ebfa  movaps  [rbp+var_20], xmm0
0x18009ebfe  call    sub_1801411F8
0x18009ec03  mov     ebx, eax
0x18009ec05  mov     r8d, ebx
0x18009ec08  lea     rax, xmmword_1801FAD00
0x18009ec0f  sar     r8d, 1Fh
0x18009ec13  lea     ecx, ds:4[r8*2]
0x18009ec1b  movsxd  rdx, ecx
0x18009ec1e  test    byte ptr [rax+rdx*8], 2
0x18009ec22  jz      short loc_18009EC4D
0x18009ec24  add     r8w, 2
0x18009ec29  mov     eax, 200h
0x18009ec2e  movzx   ecx, r8w
0x18009ec32  mov     edx, 94h
0x18009ec37  imul    ecx, eax
0x18009ec3a  lea     r8, qword_1801DA730
0x18009ec41  mov     r9d, ebx
0x18009ec44  or      cx, 1
0x18009ec48  call    sub_180189008
0x18009ec4d  mov     rsi, [rsp+50h+arg_8]
0x18009ec52  mov     eax, ebx
0x18009ec54  mov     rbx, [rsp+50h+arg_0]
0x18009ec59  add     rsp, 50h
0x18009ec5d  pop     r14
0x18009ec5f  pop     rdi
0x18009ec60  pop     rbp
0x18009ec61  retn
```
