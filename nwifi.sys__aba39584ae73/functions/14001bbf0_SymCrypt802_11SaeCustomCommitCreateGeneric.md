# SymCrypt802_11SaeCustomCommitCreateGeneric

- ea: `0x14001bbf0`
- end: `0x14001bf09`
- name: `SymCrypt802_11SaeCustomCommitCreateGeneric`
- size: `793`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400937b8`
- `0x1400938cc`

## callees

- `0x140004b1c`
- `0x140004b50`
- `0x140007200`
- `0x140007d24`
- `0x14000bc04`
- `0x14001b3d8`
- `0x14001bbf0`
- `0x14001d0c0`
- `0x14001d0dc`
- `0x14002071c`
- `0x14002c550`
- `0x14005ad6c`
- `0x14005aea8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001be79`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bed0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001be79`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bee1`

## pseudocode

```c
__int64 __fastcall SymCrypt802_11SaeCustomCommitCreateGeneric(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // r10d
  unsigned int v10; // edx
  unsigned __int64 v11; // r12
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rbp
  __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // edx
  _DWORD *v19; // r14
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // r15d
  _DWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rbx
  unsigned int Value; // r15d
  int v30; // r9d
  int v31; // r8d
  __int64 v32; // rbp
  __int64 v33; // rdi
  int v35; // [rsp+30h] [rbp-58h]

  v5 = *a1;
  v7 = 1;
  v8 = *(_DWORD *)(*a1 + 12LL);
  if ( v8 )
  {
    if ( v8 <= 0x100000 )
      v9 = (*(_DWORD *)(*a1 + 12LL) >> 9) + (((*(_DWORD *)(*a1 + 12LL) & 0x1FFu) + 511) >> 9);
    else
      v9 = 0;
  }
  else
  {
    v9 = 1;
  }
  v10 = *(_DWORD *)(v5 + 48) + *(_DWORD *)(v5 + 52);
  v11 = ((unsigned __int64)v9 << 8) + 64;
  if ( v10 <= *(_DWORD *)(v5 + 56) )
    v10 = *(_DWORD *)(v5 + 56);
  if ( v11 <= v10 )
    v11 = v10;
  v12 = SymCryptCallbackAlloc(v11);
  v13 = *(_QWORD *)(v5 + 624);
  v14 = v12;
  v15 = 0;
  v16 = SymCryptCallbackAlloc(*(unsigned int *)(v13 + 16));
  if ( v16 )
  {
    v15 = v16;
    v17 = (*(_DWORD *)(v13 + 4) << 6) - 64;
    *(_QWORD *)(v17 + v16) = 0;
    *(_QWORD *)(v17 + v16 + 8) = 0;
    *(_QWORD *)(v17 + v16 + 16) = 0;
    *(_QWORD *)(v17 + v16 + 24) = 0;
    *(_QWORD *)(v17 + v16 + 32) = 0;
    *(_QWORD *)(v17 + v16 + 40) = 0;
    *(_QWORD *)(v17 + v16 + 48) = 0;
    *(_QWORD *)(v17 + v16 + 56) = 0;
  }
  v18 = *(_DWORD *)(v5 + 24) + *(_DWORD *)(v5 + 64);
  if ( v18 )
  {
    if ( v18 <= 0x100000 )
      v7 = (v18 >> 9) + (((v18 & 0x1FF) + 511) >> 9);
    else
      v7 = 0;
  }
  v19 = 0;
  v20 = SymCryptFdefSizeofIntFromDigits(v7);
  v23 = v20;
  if ( v20 )
  {
    v24 = (_DWORD *)SymCryptCallbackAlloc(v20);
    if ( v24 )
    {
      *v24 = 1732837376;
      v24[1] = v7;
      v24[2] = v23;
      v19 = v24;
    }
  }
  v25 = SymCryptEcpointAllocate(v5, v21, v22);
  v28 = v25;
  if ( v15 && v19 && v25 && v14 )
  {
    SymCryptModAdd(*(_QWORD *)(v5 + 624), a1[2], a1[3], v15, v14, v11);
    Value = SymCryptFdefModElementGetValue(*(_QWORD *)(v5 + 624), v15, a2, a3);
    if ( !Value )
    {
      SymCryptModElementToInt(*(_QWORD *)(v5 + 624), a1[3], (_DWORD)v19, v14, v11);
      Value = SymCryptEcpointScalarMul(v5, (_DWORD)v19, a1[4], v30, v28, v14, v11);
      if ( !Value )
      {
        SymCryptEcpointNegate(v5, v28, -1, v14, v11);
        Value = SymCryptEcpointGetValue(v5, v28, v31, 2, a4, a5, v35, v14, v11);
      }
    }
    goto LABEL_27;
  }
  Value = 32783;
  if ( v19 )
LABEL_27:
    SymCryptIntFree(v19, v26, v27);
  if ( v15 )
  {
    SymCryptWipeAsm(v15, *(unsigned int *)(*(_QWORD *)(v5 + 624) + 16LL));
    v32 = v15 - *(unsigned int *)(v15 - 4);
    if ( v32 )
    {
      if ( *(_QWORD *)(v32 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v32 - 16), (PVOID)(v32 - 16));
      else
        ExFreePoolWithTag((PVOID)(v32 - 16), *(_DWORD *)(v32 - 16 + 8));
    }
  }
  if ( v28 )
    SymCryptEcpointFree(v5, v28);
  if ( v14 )
  {
    SymCryptWipeAsm(v14, v11);
    v33 = v14 - *(unsigned int *)(v14 - 4);
    if ( v33 )
    {
      if ( *(_QWORD *)(v33 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v33 - 16), (PVOID)(v33 - 16));
      else
        ExFreePoolWithTag((PVOID)(v33 - 16), *(_DWORD *)(v33 - 16 + 8));
    }
  }
  return Value;
}

```

## disassembly

```asm
0x14001bbf0  mov     rax, rsp
0x14001bbf3  mov     [rax+8], rbx
0x14001bbf7  mov     [rax+20h], r9
0x14001bbfb  mov     [rax+18h], r8
0x14001bbff  mov     [rax+10h], rdx
0x14001bc03  push    rbp
0x14001bc04  push    rsi
0x14001bc05  push    rdi
0x14001bc06  push    r12
0x14001bc08  push    r13
0x14001bc0a  push    r14
0x14001bc0c  push    r15
0x14001bc0e  sub     rsp, 50h
0x14001bc12  mov     rsi, [rcx]
0x14001bc15  xor     r15d, r15d
0x14001bc18  mov     r13, rcx
0x14001bc1b  mov     ebx, 1
0x14001bc20  mov     ecx, 1FFh
0x14001bc25  mov     eax, [rsi+0Ch]
0x14001bc28  test    eax, eax
0x14001bc2a  jnz     short loc_14001BC31
0x14001bc2c  mov     r10d, ebx
0x14001bc2f  jmp     short loc_14001BC50
0x14001bc31  cmp     eax, 100000h
0x14001bc36  jbe     short loc_14001BC3D
0x14001bc38  mov     r10d, r15d
0x14001bc3b  jmp     short loc_14001BC50
0x14001bc3d  mov     r10d, eax
0x14001bc40  shr     eax, 9
0x14001bc43  and     r10d, ecx
0x14001bc46  add     r10d, ecx
0x14001bc49  shr     r10d, 9
0x14001bc4d  add     r10d, eax
0x14001bc50  mov     r8d, [rsi+38h]
0x14001bc54  mov     edx, [rsi+34h]
0x14001bc57  add     edx, [rsi+30h]
0x14001bc5a  mov     r12d, r10d
0x14001bc5d  shl     r12, 8
0x14001bc61  add     r12, 40h ; '@'
0x14001bc65  cmp     edx, r8d
0x14001bc68  cmovbe  edx, r8d
0x14001bc6c  mov     eax, edx
0x14001bc6e  cmp     r12, rax
0x14001bc71  cmovbe  r12, rax
0x14001bc75  mov     rcx, r12
0x14001bc78  call    SymCryptCallbackAlloc
0x14001bc7d  mov     r14, [rsi+270h]
0x14001bc84  mov     rdi, rax
0x14001bc87  mov     rbp, r15
0x14001bc8a  mov     ecx, [r14+10h]
0x14001bc8e  call    SymCryptCallbackAlloc
0x14001bc93  test    rax, rax
0x14001bc96  jz      short loc_14001BCCC
0x14001bc98  mov     ecx, [r14+4]
0x14001bc9c  mov     rbp, rax
0x14001bc9f  shl     ecx, 6
0x14001bca2  sub     ecx, 40h ; '@'
0x14001bca5  mov     [rcx+rax], r15
0x14001bca9  mov     [rcx+rax+8], r15
0x14001bcae  mov     [rcx+rax+10h], r15
0x14001bcb3  mov     [rcx+rax+18h], r15
0x14001bcb8  mov     [rcx+rax+20h], r15
0x14001bcbd  mov     [rcx+rax+28h], r15
0x14001bcc2  mov     [rcx+rax+30h], r15
0x14001bcc7  mov     [rcx+rax+38h], r15
0x14001bccc  mov     edx, [rsi+40h]
0x14001bccf  add     edx, [rsi+18h]
0x14001bcd2  jz      short loc_14001BCF4
0x14001bcd4  cmp     edx, 100000h
0x14001bcda  jbe     short loc_14001BCE1
0x14001bcdc  mov     ebx, r15d
0x14001bcdf  jmp     short loc_14001BCF4
0x14001bce1  mov     ebx, edx
0x14001bce3  mov     eax, 1FFh
0x14001bce8  and     ebx, eax
0x14001bcea  shr     edx, 9
0x14001bced  add     ebx, eax
0x14001bcef  shr     ebx, 9
0x14001bcf2  add     ebx, edx
0x14001bcf4  mov     ecx, ebx
0x14001bcf6  mov     r14, r15
0x14001bcf9  call    SymCryptFdefSizeofIntFromDigits
0x14001bcfe  mov     r15d, eax
0x14001bd01  test    eax, eax
0x14001bd03  jz      short loc_14001BD22
0x14001bd05  mov     ecx, r15d
0x14001bd08  call    SymCryptCallbackAlloc
0x14001bd0d  test    rax, rax
0x14001bd10  jz      short loc_14001BD22
0x14001bd12  mov     dword ptr [rax], 67490000h
0x14001bd18  mov     [rax+4], ebx
0x14001bd1b  mov     [rax+8], r15d
0x14001bd1f  mov     r14, rax
0x14001bd22  mov     rcx, rsi
0x14001bd25  call    SymCryptEcpointAllocate
0x14001bd2a  mov     rbx, rax
0x14001bd2d  test    rbp, rbp
0x14001bd30  jz      loc_14001BE35
0x14001bd36  test    r14, r14
0x14001bd39  jz      loc_14001BE35
0x14001bd3f  test    rax, rax
0x14001bd42  jz      loc_14001BE35
0x14001bd48  test    rdi, rdi
0x14001bd4b  jz      loc_14001BE35
0x14001bd51  mov     r8, [r13+18h]
0x14001bd55  mov     r9, rbp
0x14001bd58  mov     rdx, [r13+10h]
0x14001bd5c  mov     rcx, [rsi+270h]
0x14001bd63  mov     [rsp+88h+var_60], r12
0x14001bd68  mov     [rsp+88h+var_68], rdi
0x14001bd6d  call    SymCryptModAdd
0x14001bd72  mov     r9, [rsp+88h+arg_10]
0x14001bd7a  mov     rdx, rbp
0x14001bd7d  mov     r8, [rsp+88h+arg_8]
0x14001bd85  mov     rcx, [rsi+270h]
0x14001bd8c  mov     [rsp+88h+var_58], r12
0x14001bd91  mov     [rsp+88h+var_60], rdi
0x14001bd96  call    SymCryptFdefModElementGetValue
0x14001bd9b  mov     r15d, eax
0x14001bd9e  test    eax, eax
0x14001bda0  jnz     loc_14001BE40
0x14001bda6  mov     rdx, [r13+18h]
0x14001bdaa  mov     r9, rdi
0x14001bdad  mov     rcx, [rsi+270h]
0x14001bdb4  mov     r8, r14
0x14001bdb7  mov     [rsp+88h+var_68], r12
0x14001bdbc  call    SymCryptModElementToInt
0x14001bdc1  mov     r8, [r13+20h]
0x14001bdc5  mov     rdx, r14
0x14001bdc8  mov     [rsp+88h+var_58], r12
0x14001bdcd  mov     rcx, rsi
0x14001bdd0  mov     [rsp+88h+var_60], rdi
0x14001bdd5  mov     [rsp+88h+var_68], rbx
0x14001bdda  call    SymCryptEcpointScalarMul
0x14001bddf  mov     r15d, eax
0x14001bde2  test    eax, eax
0x14001bde4  jnz     short loc_14001BE40
0x14001bde6  mov     r9, rdi
0x14001bde9  mov     [rsp+88h+var_68], r12
0x14001bdee  or      r8d, 0FFFFFFFFh
0x14001bdf2  mov     rdx, rbx
0x14001bdf5  mov     rcx, rsi
0x14001bdf8  call    SymCryptEcpointNegate
0x14001bdfd  mov     rax, [rsp+88h+arg_20]
0x14001be05  lea     r9d, [r15+2]
0x14001be09  mov     [rsp+88h+var_48], r12
0x14001be0e  mov     rdx, rbx
0x14001be11  mov     [rsp+88h+var_50], rdi
0x14001be16  mov     rcx, rsi
0x14001be19  mov     [rsp+88h+var_60], rax
0x14001be1e  mov     rax, [rsp+88h+arg_18]
0x14001be26  mov     [rsp+88h+var_68], rax
0x14001be2b  call    SymCryptEcpointGetValue
0x14001be30  mov     r15d, eax
0x14001be33  jmp     short loc_14001BE40
0x14001be35  mov     r15d, 800Fh
0x14001be3b  test    r14, r14
0x14001be3e  jz      short loc_14001BE48
0x14001be40  mov     rcx, r14
0x14001be43  call    SymCryptIntFree
0x14001be48  test    rbp, rbp
0x14001be4b  jz      short loc_14001BE96
0x14001be4d  mov     rax, [rsi+270h]
0x14001be54  mov     rcx, rbp
0x14001be57  mov     edx, [rax+10h]
0x14001be5a  call    SymCryptWipeAsm
0x14001be5f  mov     eax, [rbp-4]
0x14001be62  sub     rbp, rax
0x14001be65  jz      short loc_14001BE96
0x14001be67  lea     rcx, [rbp-10h]; P
0x14001be6b  mov     rax, [rcx]
0x14001be6e  test    rax, rax
0x14001be71  jz      short loc_14001BE87
0x14001be73  mov     rdx, rcx; Entry
0x14001be76  mov     rcx, rax; Lookaside
0x14001be79  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001be80  nop     dword ptr [rax+rax+00h]
0x14001be85  jmp     short loc_14001BE96
0x14001be87  mov     edx, [rcx+8]; Tag
0x14001be8a  call    cs:__imp_ExFreePoolWithTag
0x14001be91  nop     dword ptr [rax+rax+00h]
0x14001be96  test    rbx, rbx
0x14001be99  jz      short loc_14001BEA6
0x14001be9b  mov     rdx, rbx
0x14001be9e  mov     rcx, rsi
0x14001bea1  call    SymCryptEcpointFree
0x14001bea6  test    rdi, rdi
0x14001bea9  jz      short loc_14001BEED
0x14001beab  mov     rdx, r12
0x14001beae  mov     rcx, rdi
0x14001beb1  call    SymCryptWipeAsm
0x14001beb6  mov     eax, [rdi-4]
0x14001beb9  sub     rdi, rax
0x14001bebc  jz      short loc_14001BEED
0x14001bebe  lea     rcx, [rdi-10h]; P
0x14001bec2  mov     rax, [rcx]
0x14001bec5  test    rax, rax
0x14001bec8  jz      short loc_14001BEDE
0x14001beca  mov     rdx, rcx; Entry
0x14001becd  mov     rcx, rax; Lookaside
0x14001bed0  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001bed7  nop     dword ptr [rax+rax+00h]
0x14001bedc  jmp     short loc_14001BEED
0x14001bede  mov     edx, [rcx+8]; Tag
0x14001bee1  call    cs:__imp_ExFreePoolWithTag
0x14001bee8  nop     dword ptr [rax+rax+00h]
0x14001beed  mov     rbx, [rsp+88h+arg_0]
0x14001bef5  mov     eax, r15d
0x14001bef8  add     rsp, 50h
0x14001befc  pop     r15
0x14001befe  pop     r14
0x14001bf00  pop     r13
0x14001bf02  pop     r12
0x14001bf04  pop     rdi
0x14001bf05  pop     rsi
0x14001bf06  pop     rbp
0x14001bf07  retn
```
