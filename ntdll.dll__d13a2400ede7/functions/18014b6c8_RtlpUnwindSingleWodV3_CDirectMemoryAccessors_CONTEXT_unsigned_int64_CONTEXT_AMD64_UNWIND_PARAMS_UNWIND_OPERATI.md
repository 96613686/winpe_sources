# RtlpUnwindSingleWodV3<CDirectMemoryAccessors,_CONTEXT *>(unsigned __int64,_CONTEXT *,_AMD64_UNWIND_PARAMS *,UNWIND_OPERATION_V3 const *,unsigned __int64,uchar *)

- ea: `0x18014b6c8`
- end: `0x18014bddf`
- name: `??$RtlpUnwindSingleWodV3@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJ_KPEAU_CONTEXT@@PEAU_AMD64_UNWIND_PARAMS@@PEBTUNWIND_OPERATION_V3@@0PEAE@Z`
- size: `1815`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18014aa68`
- `0x18014b078`

## callees

- `0x180070370`
- `0x18014a124`
- `0x18014a194`
- `0x18014b6c8`
- `0x18014c910`

## pseudocode

```c
__int64 __fastcall RtlpUnwindSingleWodV3<CDirectMemoryAccessors,_CONTEXT *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        __int64 a5,
        _BYTE *a6)
{
  unsigned __int8 v9; // al
  unsigned int v10; // r14d
  _QWORD *v11; // rsi
  unsigned int v12; // esi
  _QWORD *v13; // r14
  __int64 v14; // rcx
  unsigned __int8 v15; // al
  __int64 v16; // rcx
  unsigned __int8 v17; // al
  _QWORD *v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // ebx
  __int64 v23; // rcx
  unsigned __int16 v24; // dx
  _QWORD *v25; // rsi
  _QWORD *v26; // r14
  unsigned int v27; // r15d
  __int64 v28; // r12
  _QWORD *v29; // r13
  __int64 v30; // rcx
  _QWORD *v31; // r14
  unsigned int v32; // r15d
  unsigned int v33; // r9d
  _QWORD *v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned int v39; // r14d
  _QWORD *v40; // r15
  __int64 v41; // r12
  _QWORD *v42; // r13
  __int64 v43; // rcx
  _QWORD *v44; // r15

  *a6 = 0;
  v9 = RtlpDecodeWodOpcode(*a4);
  if ( v9 > 6u )
  {
    if ( v9 != 7 )
    {
      switch ( v9 )
      {
        case 8u:
          v20 = (*a4 >> 4) + 1;
          goto LABEL_63;
        case 9u:
          v33 = *a4 >> 4;
          v34 = (_QWORD *)(*(unsigned int *)(a4 + 1) + a5);
          break;
        case 0xAu:
          v33 = *a4 >> 4;
          v34 = (_QWORD *)(a5 + 16LL * *(unsigned __int16 *)(a4 + 1));
          break;
        case 0x20u:
          v24 = *(_WORD *)a4;
          v25 = (_QWORD *)(a2 + 152);
          v26 = *(_QWORD **)(a2 + 152);
          if ( *(_QWORD *)a3
            && ((unsigned __int64)v26 < **(_QWORD **)a3 || (unsigned __int64)v26 > **(_QWORD **)(a3 + 8) - 8LL) )
          {
            return 3221225512LL;
          }
          v27 = v24;
          v28 = v24 >> 11;
          RtlpAmd64SetContextGp<_CONTEXT *>(a2, v28, *v26);
          v29 = (_QWORD *)(a3 + 16);
          v30 = *(_QWORD *)(a3 + 16);
          if ( v30 && (unsigned int)v28 < 0x10 )
            *(_QWORD *)(v30 + 8 * v28 + 128) = v26;
          *v25 += 8LL;
          v31 = (_QWORD *)*v25;
          if ( *(_QWORD *)a3 )
          {
            if ( (unsigned __int64)v31 < **(_QWORD **)a3 || (unsigned __int64)v31 > **(_QWORD **)(a3 + 8) - 8LL )
              return 3221225512LL;
          }
          v32 = (v27 >> 6) & 0x1F;
          RtlpAmd64SetContextGp<_CONTEXT *>(a2, v32, *v31);
          if ( *v29 && v32 < 0x10 )
            *(_QWORD *)(*v29 + 8LL * v32 + 128) = v31;
          goto LABEL_77;
        default:
          goto LABEL_79;
      }
      if ( !*(_QWORD *)a3
        || (unsigned __int64)v34 >= **(_QWORD **)a3 && (unsigned __int64)v34 <= **(_QWORD **)(a3 + 8) - 16LL )
      {
        v35 = v34[1];
        v36 = 2 * (v33 + 26LL);
        *(_QWORD *)(a2 + 8 * v36) = *v34;
        *(_QWORD *)(a2 + 8 * v36 + 8) = v35;
        v37 = *(_QWORD *)(a3 + 16);
        if ( v37 )
          *(_QWORD *)(v37 + 8LL * v33) = v34;
        return 0;
      }
      return 3221225512LL;
    }
    v39 = *a4 >> 3;
    v25 = (_QWORD *)(a2 + 152);
    v40 = *(_QWORD **)(a2 + 152);
    if ( *(_QWORD *)a3
      && ((unsigned __int64)v40 < **(_QWORD **)a3 || (unsigned __int64)v40 > **(_QWORD **)(a3 + 8) - 8LL) )
    {
      return 3221225512LL;
    }
    v41 = v39 + 1;
    RtlpAmd64SetContextGp<_CONTEXT *>(a2, v41, *v40);
    v42 = (_QWORD *)(a3 + 16);
    v43 = *(_QWORD *)(a3 + 16);
    if ( v43 && (unsigned int)v41 < 0x10 )
      *(_QWORD *)(v43 + 8 * v41 + 128) = v40;
    *v25 += 8LL;
    v44 = (_QWORD *)*v25;
    if ( *(_QWORD *)a3 )
    {
      if ( (unsigned __int64)v44 < **(_QWORD **)a3 || (unsigned __int64)v44 > **(_QWORD **)(a3 + 8) - 8LL )
        return 3221225512LL;
    }
    RtlpAmd64SetContextGp<_CONTEXT *>(a2, v39, *v44);
    if ( *v42 && v39 < 0x10 )
      *(_QWORD *)(*v42 + 8LL * v39 + 128) = v44;
LABEL_77:
    *v25 += 8LL;
    return 0;
  }
  switch ( v9 )
  {
    case 6u:
      v10 = *a4 >> 3;
      v11 = (_QWORD *)(a5 + 8LL * *(unsigned __int16 *)(a4 + 1));
      goto LABEL_31;
    case 0u:
      v22 = a4[1];
      *(_QWORD *)(a2 + 152) = RtlpAmd64GetContextGp<_CONTEXT *>(a2, a4[1] & 0xF) - (v22 & 0xFFFFFFF0);
      return 0;
    case 1u:
      v21 = *(unsigned int *)(a4 + 1);
LABEL_64:
      *(_QWORD *)(a2 + 152) += v21;
      return 0;
    case 2u:
      v20 = *(unsigned __int16 *)(a4 + 1);
LABEL_63:
      v21 = 8 * v20;
      goto LABEL_64;
  }
  if ( v9 != 3 )
  {
    if ( v9 == 4 )
    {
      v12 = *a4 >> 3;
      v13 = *(_QWORD **)(a2 + 152);
      if ( !*(_QWORD *)a3
        || (unsigned __int64)v13 >= **(_QWORD **)a3 && (unsigned __int64)v13 <= **(_QWORD **)(a3 + 8) - 8LL )
      {
        RtlpAmd64SetContextGp<_CONTEXT *>(a2, v12, *v13);
        v14 = *(_QWORD *)(a3 + 16);
        if ( v14 && v12 < 0x10 )
          *(_QWORD *)(v14 + 8LL * v12 + 128) = v13;
        *(_QWORD *)(a2 + 152) += 8LL;
        return 0;
      }
      return 3221225512LL;
    }
    if ( v9 == 5 )
    {
      v10 = *a4 >> 3;
      v11 = (_QWORD *)(*(unsigned int *)(a4 + 1) + a5);
LABEL_31:
      if ( !*(_QWORD *)a3
        || (unsigned __int64)v11 >= **(_QWORD **)a3 && (unsigned __int64)v11 <= **(_QWORD **)(a3 + 8) - 8LL )
      {
        RtlpAmd64SetContextGp<_CONTEXT *>(a2, v10, *v11);
        v23 = *(_QWORD *)(a3 + 16);
        if ( v23 )
        {
          if ( v10 < 0x10 )
            *(_QWORD *)(v23 + 8LL * v10 + 128) = v11;
        }
        return 0;
      }
      return 3221225512LL;
    }
LABEL_79:
    RtlRaiseStatus(3221225727LL);
  }
  v15 = a4[1];
  if ( v15 <= 3u )
  {
    v16 = *(_QWORD *)(a2 + 152);
    v17 = v15 & 1;
    v18 = (_QWORD *)(v16 + 8);
    if ( !v17 )
      v18 = *(_QWORD **)(a2 + 152);
    v19 = (_QWORD *)(v16 + 8 * (v17 + 3LL));
    if ( *(_QWORD *)a3
      && ((unsigned __int64)v18 < **(_QWORD **)a3 || (unsigned __int64)v18 > **(_QWORD **)(a3 + 8) - 8LL)
      || *(_QWORD *)a3
      && ((unsigned __int64)v19 < **(_QWORD **)a3 || (unsigned __int64)v19 > **(_QWORD **)(a3 + 8) - 8LL) )
    {
      return 3221225512LL;
    }
    *(_QWORD *)(a2 + 248) = *v18;
    *(_QWORD *)(a2 + 152) = *v19;
    *a6 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18014b6c8  mov     [rsp+arg_10], r8
0x18014b6cd  mov     [rsp+arg_8], rdx
0x18014b6d2  mov     [rsp+arg_0], rcx
0x18014b6d7  push    rbx
0x18014b6d8  push    rsi
0x18014b6d9  push    rdi
0x18014b6da  push    r12
0x18014b6dc  push    r13
0x18014b6de  push    r14
0x18014b6e0  push    r15
0x18014b6e2  sub     rsp, 30h
0x18014b6e6  mov     rsi, r9
0x18014b6e9  mov     rbx, r8
0x18014b6ec  mov     rdi, rdx
0x18014b6ef  mov     rax, [rsp+68h+arg_28]
0x18014b6f7  mov     byte ptr [rax], 0
0x18014b6fa  mov     cl, [r9]; unsigned __int8
0x18014b6fd  call    ?RtlpDecodeWodOpcode@@YAEE@Z; RtlpDecodeWodOpcode(uchar)
0x18014b702  movzx   ecx, al
0x18014b705  cmp     ecx, 6
0x18014b708  ja      loc_18014BA02
0x18014b70e  jz      loc_18014B95D
0x18014b714  test    al, al
0x18014b716  jz      loc_18014B937
0x18014b71c  sub     ecx, 1
0x18014b71f  jz      loc_18014B92F
0x18014b725  sub     ecx, 1
0x18014b728  jz      loc_18014B926
0x18014b72e  sub     ecx, 1
0x18014b731  jz      loc_18014B831
0x18014b737  sub     ecx, 1
0x18014b73a  jz      short loc_18014B78D
0x18014b73c  cmp     ecx, 1
0x18014b73f  jnz     loc_18014BDD4
0x18014b745  movzx   r14d, byte ptr [rsi]
0x18014b749  shr     r14d, 3
0x18014b74d  mov     dword ptr [rsp+68h+arg_28], r14d
0x18014b755  mov     esi, [rsi+1]
0x18014b758  mov     rax, [rsp+68h+arg_20]
0x18014b760  lea     rsi, [rsi+rax]
0x18014b764  mov     [rsp+68h+arg_0], rsi
0x18014b769  jmp     loc_18014B982
0x18014b76e  mov     rbx, [rsp+68h+arg_10]
0x18014b776  mov     rdi, [rsp+68h+arg_8]
0x18014b77b  mov     r14d, dword ptr [rsp+68h+arg_28]
0x18014b783  mov     rsi, [rsp+68h+arg_0]
0x18014b788  jmp     loc_18014B9C5
0x18014b78d  movzx   esi, byte ptr [rsi]
0x18014b790  shr     esi, 3
0x18014b793  mov     dword ptr [rsp+68h+arg_28], esi
0x18014b79a  lea     r15, [rdi+98h]
0x18014b7a1  mov     [rsp+68h+arg_0], r15
0x18014b7a6  mov     r14, [r15]
0x18014b7a9  mov     [rsp+68h+arg_18], r14
0x18014b7b1  mov     rax, [rbx]
0x18014b7b4  test    rax, rax
0x18014b7b7  jz      short loc_18014B7D6
0x18014b7b9  cmp     r14, [rax]
0x18014b7bc  jb      loc_18014BC49
0x18014b7c2  mov     rax, [rbx+8]
0x18014b7c6  mov     rcx, [rax]
0x18014b7c9  sub     rcx, 8
0x18014b7cd  cmp     r14, rcx
0x18014b7d0  ja      loc_18014BC49
0x18014b7d6  xor     eax, eax
0x18014b7d8  jmp     short loc_18014B7FB
0x18014b7da  mov     rbx, [rsp+68h+arg_10]
0x18014b7e2  mov     rdi, [rsp+68h+arg_8]
0x18014b7e7  mov     esi, dword ptr [rsp+68h+arg_28]
0x18014b7ee  mov     r15, [rsp+68h+arg_0]
0x18014b7f3  mov     r14, [rsp+68h+arg_18]
0x18014b7fb  test    eax, eax
0x18014b7fd  js      loc_18014BDC3
0x18014b803  mov     r8, [r14]
0x18014b806  mov     edx, esi
0x18014b808  mov     rcx, rdi
0x18014b80b  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014b810  mov     rcx, [rbx+10h]
0x18014b814  test    rcx, rcx
0x18014b817  jz      short loc_18014B828
0x18014b819  cmp     esi, 10h
0x18014b81c  jnb     short loc_18014B828
0x18014b81e  mov     eax, esi
0x18014b820  mov     [rcx+rax*8+80h], r14
0x18014b828  add     qword ptr [r15], 8
0x18014b82c  jmp     loc_18014BDC1
0x18014b831  mov     al, [rsi+1]
0x18014b834  cmp     al, 3
0x18014b836  ja      loc_18014BDC1
0x18014b83c  lea     r9, [rdi+98h]
0x18014b843  mov     [rsp+68h+arg_0], r9
0x18014b848  mov     rcx, [r9]
0x18014b84b  and     al, 1
0x18014b84d  lea     rdx, [rcx+8]
0x18014b851  cmovz   rdx, rcx
0x18014b855  mov     [rsp+68h+arg_18], rdx
0x18014b85d  movzx   r8d, al
0x18014b861  lea     r8, [r8+3]
0x18014b865  lea     r8, [rcx+r8*8]
0x18014b869  mov     [rsp+68h+var_48], r8
0x18014b86e  mov     rax, [rbx]
0x18014b871  test    rax, rax
0x18014b874  jz      short loc_18014B893
0x18014b876  cmp     rdx, [rax]
0x18014b879  jb      loc_18014BC49
0x18014b87f  mov     rax, [rbx+8]
0x18014b883  mov     rcx, [rax]
0x18014b886  sub     rcx, 8
0x18014b88a  cmp     rdx, rcx
0x18014b88d  ja      loc_18014BC49
0x18014b893  xor     eax, eax
0x18014b895  jmp     short loc_18014B8B6
0x18014b897  mov     rbx, [rsp+68h+arg_10]
0x18014b89f  mov     rdi, [rsp+68h+arg_8]
0x18014b8a4  mov     rdx, [rsp+68h+arg_18]
0x18014b8ac  mov     r8, [rsp+68h+var_48]
0x18014b8b1  mov     r9, [rsp+68h+arg_0]
0x18014b8b6  test    eax, eax
0x18014b8b8  js      loc_18014BDC3
0x18014b8be  mov     rax, [rbx]
0x18014b8c1  test    rax, rax
0x18014b8c4  jz      short loc_18014B8E3
0x18014b8c6  cmp     r8, [rax]
0x18014b8c9  jb      loc_18014BC49
0x18014b8cf  mov     rax, [rbx+8]
0x18014b8d3  mov     rcx, [rax]
0x18014b8d6  sub     rcx, 8
0x18014b8da  cmp     r8, rcx
0x18014b8dd  ja      loc_18014BC49
0x18014b8e3  xor     eax, eax
0x18014b8e5  jmp     short loc_18014B8FE
0x18014b8e7  mov     rdi, [rsp+68h+arg_8]
0x18014b8ec  mov     rdx, [rsp+68h+arg_18]
0x18014b8f4  mov     r8, [rsp+68h+var_48]
0x18014b8f9  mov     r9, [rsp+68h+arg_0]
0x18014b8fe  test    eax, eax
0x18014b900  js      loc_18014BDC3
0x18014b906  mov     rax, [rdx]
0x18014b909  mov     [rdi+0F8h], rax
0x18014b910  mov     rax, [r8]
0x18014b913  mov     [r9], rax
0x18014b916  mov     rax, [rsp+68h+arg_28]
0x18014b91e  mov     byte ptr [rax], 1
0x18014b921  jmp     loc_18014BDC1
0x18014b926  movzx   eax, word ptr [rsi+1]
0x18014b92a  jmp     loc_18014BC7A
0x18014b92f  mov     eax, [rsi+1]
0x18014b932  jmp     loc_18014BC7E
0x18014b937  movzx   ebx, byte ptr [rsi+1]
0x18014b93b  mov     edx, ebx
0x18014b93d  and     edx, 0Fh
0x18014b940  mov     rcx, rdi
0x18014b943  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x18014b948  mov     ecx, ebx
0x18014b94a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18014b94e  sub     rax, rcx
0x18014b951  mov     [rdi+98h], rax
0x18014b958  jmp     loc_18014BDC1
0x18014b95d  movzx   r14d, byte ptr [rsi]
0x18014b961  shr     r14d, 3
0x18014b965  mov     dword ptr [rsp+68h+arg_28], r14d
0x18014b96d  movzx   ecx, word ptr [rsi+1]
0x18014b971  mov     rax, [rsp+68h+arg_20]
0x18014b979  lea     rsi, [rax+rcx*8]
0x18014b97d  mov     [rsp+68h+arg_0], rsi
0x18014b982  mov     rax, [rbx]
0x18014b985  test    rax, rax
0x18014b988  jz      short loc_18014B9A7
0x18014b98a  cmp     rsi, [rax]
0x18014b98d  jb      loc_18014BC49
0x18014b993  mov     rax, [rbx+8]
0x18014b997  mov     rcx, [rax]
0x18014b99a  sub     rcx, 8
0x18014b99e  cmp     rsi, rcx
0x18014b9a1  ja      loc_18014BC49
0x18014b9a7  xor     eax, eax
0x18014b9a9  jmp     short loc_18014B9C5
0x18014b9ab  mov     rbx, [rsp+68h+arg_10]
0x18014b9b3  mov     rdi, [rsp+68h+arg_8]
0x18014b9b8  mov     r14d, dword ptr [rsp+68h+arg_28]
0x18014b9c0  mov     rsi, [rsp+68h+arg_0]
0x18014b9c5  test    eax, eax
0x18014b9c7  js      loc_18014BDC3
0x18014b9cd  mov     r8, [rsi]
0x18014b9d0  mov     edx, r14d
0x18014b9d3  mov     rcx, rdi
0x18014b9d6  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014b9db  mov     rcx, [rbx+10h]
0x18014b9df  test    rcx, rcx
0x18014b9e2  jz      loc_18014BDC1
0x18014b9e8  cmp     r14d, 10h
0x18014b9ec  jnb     loc_18014BDC1
0x18014b9f2  mov     eax, r14d
0x18014b9f5  mov     [rcx+rax*8+80h], rsi
0x18014b9fd  jmp     loc_18014BDC1
0x18014ba02  sub     ecx, 7
0x18014ba05  jz      loc_18014BC8A
0x18014ba0b  sub     ecx, 1
0x18014ba0e  jz      loc_18014BC72
0x18014ba14  sub     ecx, 1
0x18014ba17  jz      loc_18014BBFF
0x18014ba1d  sub     ecx, 1
0x18014ba20  jz      loc_18014BB7E
0x18014ba26  cmp     ecx, 16h
0x18014ba29  jnz     loc_18014BDD4
0x18014ba2f  movzx   edx, word ptr [rsi]
0x18014ba32  mov     word ptr [rsp+68h+arg_28], dx
0x18014ba3a  lea     rsi, [rdi+98h]
0x18014ba41  mov     [rsp+68h+arg_0], rsi
0x18014ba46  mov     r14, [rsi]
0x18014ba49  mov     [rsp+68h+arg_18], r14
0x18014ba51  mov     rax, [rbx]
0x18014ba54  test    rax, rax
0x18014ba57  jz      short loc_18014BA76
0x18014ba59  cmp     r14, [rax]
0x18014ba5c  jb      loc_18014BC49
0x18014ba62  mov     rax, [rbx+8]
0x18014ba66  mov     rcx, [rax]
0x18014ba69  sub     rcx, 8
0x18014ba6d  cmp     r14, rcx
0x18014ba70  ja      loc_18014BC49
0x18014ba76  xor     eax, eax
0x18014ba78  jmp     short loc_18014BA9C
0x18014ba7a  mov     rbx, [rsp+68h+arg_10]
0x18014ba82  mov     rdi, [rsp+68h+arg_8]
0x18014ba87  mov     rsi, [rsp+68h+arg_0]
0x18014ba8c  mov     r14, [rsp+68h+arg_18]
0x18014ba94  movzx   edx, word ptr [rsp+68h+arg_28]
0x18014ba9c  test    eax, eax
0x18014ba9e  js      loc_18014BDC3
0x18014baa4  movzx   r15d, dx
0x18014baa8  mov     dword ptr [rsp+68h+arg_28], r15d
0x18014bab0  mov     r12d, r15d
0x18014bab3  shr     r12d, 0Bh
0x18014bab7  mov     r8, [r14]
0x18014baba  mov     edx, r12d
0x18014babd  mov     rcx, rdi
0x18014bac0  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014bac5  lea     r13, [rbx+10h]
0x18014bac9  mov     [rsp+68h+arg_18], r13
0x18014bad1  mov     rcx, [r13+0]
0x18014bad5  test    rcx, rcx
0x18014bad8  jz      short loc_18014BAE8
0x18014bada  cmp     r12d, 10h
0x18014bade  jnb     short loc_18014BAE8
0x18014bae0  mov     [rcx+r12*8+80h], r14
0x18014bae8  add     qword ptr [rsi], 8
0x18014baec  mov     r14, [rsi]
0x18014baef  mov     [rsp+68h+var_48], r14
0x18014baf4  mov     rax, [rbx]
0x18014baf7  test    rax, rax
0x18014bafa  jz      short loc_18014BB19
0x18014bafc  cmp     r14, [rax]
0x18014baff  jb      loc_18014BC49
0x18014bb05  mov     rax, [rbx+8]
0x18014bb09  mov     rcx, [rax]
0x18014bb0c  sub     rcx, 8
0x18014bb10  cmp     r14, rcx
0x18014bb13  ja      loc_18014BC49
0x18014bb19  xor     eax, eax
0x18014bb1b  jmp     short loc_18014BB3C
0x18014bb1d  mov     rdi, [rsp+68h+arg_8]
0x18014bb22  mov     r13, [rsp+68h+arg_18]
0x18014bb2a  mov     rsi, [rsp+68h+arg_0]
0x18014bb2f  mov     r14, [rsp+68h+var_48]
0x18014bb34  mov     r15d, dword ptr [rsp+68h+arg_28]
0x18014bb3c  test    eax, eax
0x18014bb3e  js      loc_18014BDC3
0x18014bb44  shr     r15d, 6
0x18014bb48  and     r15d, 1Fh
0x18014bb4c  mov     r8, [r14]
0x18014bb4f  mov     edx, r15d
0x18014bb52  mov     rcx, rdi
0x18014bb55  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014bb5a  mov     rcx, [r13+0]
0x18014bb5e  test    rcx, rcx
0x18014bb61  jz      loc_18014BDBD
0x18014bb67  cmp     r15d, 10h
0x18014bb6b  jnb     loc_18014BDBD
0x18014bb71  mov     [rcx+r15*8+80h], r14
0x18014bb79  jmp     loc_18014BDBD
0x18014bb7e  movzx   r9d, byte ptr [rsi]
0x18014bb82  shr     r9d, 4
0x18014bb86  mov     dword ptr [rsp+68h+arg_28], r9d
0x18014bb8e  movzx   r8d, word ptr [rsi+1]
0x18014bb93  add     r8, r8
0x18014bb96  mov     rax, [rsp+68h+arg_20]
0x18014bb9e  lea     r8, [rax+r8*8]
0x18014bba2  mov     [rsp+68h+arg_0], r8
0x18014bba7  jmp     short loc_18014BC24
0x18014bba9  xor     eax, eax
0x18014bbab  jmp     short loc_18014BBC7
0x18014bbad  mov     rbx, [rsp+68h+arg_10]
0x18014bbb5  mov     rdi, [rsp+68h+arg_8]
0x18014bbba  mov     r9d, dword ptr [rsp+68h+arg_28]
0x18014bbc2  mov     r8, [rsp+68h+arg_0]
0x18014bbc7  test    eax, eax
0x18014bbc9  js      loc_18014BDC3
0x18014bbcf  mov     rdx, [r8+8]
0x18014bbd3  mov     r10d, r9d
  ... truncated ...
```
