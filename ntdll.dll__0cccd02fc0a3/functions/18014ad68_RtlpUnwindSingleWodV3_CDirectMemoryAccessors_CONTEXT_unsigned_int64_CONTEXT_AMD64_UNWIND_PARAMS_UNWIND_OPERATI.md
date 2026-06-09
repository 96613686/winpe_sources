# RtlpUnwindSingleWodV3<CDirectMemoryAccessors,_CONTEXT *>(unsigned __int64,_CONTEXT *,_AMD64_UNWIND_PARAMS *,UNWIND_OPERATION_V3 const *,unsigned __int64,uchar *)

- ea: `0x18014ad68`
- end: `0x18014b47f`
- name: `??$RtlpUnwindSingleWodV3@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJ_KPEAU_CONTEXT@@PEAU_AMD64_UNWIND_PARAMS@@PEBTUNWIND_OPERATION_V3@@0PEAE@Z`
- size: `1815`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18014a108`
- `0x18014a718`

## callees

- `0x180053990`
- `0x1801497c4`
- `0x180149834`
- `0x18014ad68`
- `0x18014bfb0`

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
0x18014ad68  mov     [rsp+arg_10], r8
0x18014ad6d  mov     [rsp+arg_8], rdx
0x18014ad72  mov     [rsp+arg_0], rcx
0x18014ad77  push    rbx
0x18014ad78  push    rsi
0x18014ad79  push    rdi
0x18014ad7a  push    r12
0x18014ad7c  push    r13
0x18014ad7e  push    r14
0x18014ad80  push    r15
0x18014ad82  sub     rsp, 30h
0x18014ad86  mov     rsi, r9
0x18014ad89  mov     rbx, r8
0x18014ad8c  mov     rdi, rdx
0x18014ad8f  mov     rax, [rsp+68h+arg_28]
0x18014ad97  mov     byte ptr [rax], 0
0x18014ad9a  mov     cl, [r9]; unsigned __int8
0x18014ad9d  call    ?RtlpDecodeWodOpcode@@YAEE@Z; RtlpDecodeWodOpcode(uchar)
0x18014ada2  movzx   ecx, al
0x18014ada5  cmp     ecx, 6
0x18014ada8  ja      loc_18014B0A2
0x18014adae  jz      loc_18014AFFD
0x18014adb4  test    al, al
0x18014adb6  jz      loc_18014AFD7
0x18014adbc  sub     ecx, 1
0x18014adbf  jz      loc_18014AFCF
0x18014adc5  sub     ecx, 1
0x18014adc8  jz      loc_18014AFC6
0x18014adce  sub     ecx, 1
0x18014add1  jz      loc_18014AED1
0x18014add7  sub     ecx, 1
0x18014adda  jz      short loc_18014AE2D
0x18014addc  cmp     ecx, 1
0x18014addf  jnz     loc_18014B474
0x18014ade5  movzx   r14d, byte ptr [rsi]
0x18014ade9  shr     r14d, 3
0x18014aded  mov     dword ptr [rsp+68h+arg_28], r14d
0x18014adf5  mov     esi, [rsi+1]
0x18014adf8  mov     rax, [rsp+68h+arg_20]
0x18014ae00  lea     rsi, [rsi+rax]
0x18014ae04  mov     [rsp+68h+arg_0], rsi
0x18014ae09  jmp     loc_18014B022
0x18014ae0e  mov     rbx, [rsp+68h+arg_10]
0x18014ae16  mov     rdi, [rsp+68h+arg_8]
0x18014ae1b  mov     r14d, dword ptr [rsp+68h+arg_28]
0x18014ae23  mov     rsi, [rsp+68h+arg_0]
0x18014ae28  jmp     loc_18014B065
0x18014ae2d  movzx   esi, byte ptr [rsi]
0x18014ae30  shr     esi, 3
0x18014ae33  mov     dword ptr [rsp+68h+arg_28], esi
0x18014ae3a  lea     r15, [rdi+98h]
0x18014ae41  mov     [rsp+68h+arg_0], r15
0x18014ae46  mov     r14, [r15]
0x18014ae49  mov     [rsp+68h+arg_18], r14
0x18014ae51  mov     rax, [rbx]
0x18014ae54  test    rax, rax
0x18014ae57  jz      short loc_18014AE76
0x18014ae59  cmp     r14, [rax]
0x18014ae5c  jb      loc_18014B2E9
0x18014ae62  mov     rax, [rbx+8]
0x18014ae66  mov     rcx, [rax]
0x18014ae69  sub     rcx, 8
0x18014ae6d  cmp     r14, rcx
0x18014ae70  ja      loc_18014B2E9
0x18014ae76  xor     eax, eax
0x18014ae78  jmp     short loc_18014AE9B
0x18014ae7a  mov     rbx, [rsp+68h+arg_10]
0x18014ae82  mov     rdi, [rsp+68h+arg_8]
0x18014ae87  mov     esi, dword ptr [rsp+68h+arg_28]
0x18014ae8e  mov     r15, [rsp+68h+arg_0]
0x18014ae93  mov     r14, [rsp+68h+arg_18]
0x18014ae9b  test    eax, eax
0x18014ae9d  js      loc_18014B463
0x18014aea3  mov     r8, [r14]
0x18014aea6  mov     edx, esi
0x18014aea8  mov     rcx, rdi
0x18014aeab  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014aeb0  mov     rcx, [rbx+10h]
0x18014aeb4  test    rcx, rcx
0x18014aeb7  jz      short loc_18014AEC8
0x18014aeb9  cmp     esi, 10h
0x18014aebc  jnb     short loc_18014AEC8
0x18014aebe  mov     eax, esi
0x18014aec0  mov     [rcx+rax*8+80h], r14
0x18014aec8  add     qword ptr [r15], 8
0x18014aecc  jmp     loc_18014B461
0x18014aed1  mov     al, [rsi+1]
0x18014aed4  cmp     al, 3
0x18014aed6  ja      loc_18014B461
0x18014aedc  lea     r9, [rdi+98h]
0x18014aee3  mov     [rsp+68h+arg_0], r9
0x18014aee8  mov     rcx, [r9]
0x18014aeeb  and     al, 1
0x18014aeed  lea     rdx, [rcx+8]
0x18014aef1  cmovz   rdx, rcx
0x18014aef5  mov     [rsp+68h+arg_18], rdx
0x18014aefd  movzx   r8d, al
0x18014af01  lea     r8, [r8+3]
0x18014af05  lea     r8, [rcx+r8*8]
0x18014af09  mov     [rsp+68h+var_48], r8
0x18014af0e  mov     rax, [rbx]
0x18014af11  test    rax, rax
0x18014af14  jz      short loc_18014AF33
0x18014af16  cmp     rdx, [rax]
0x18014af19  jb      loc_18014B2E9
0x18014af1f  mov     rax, [rbx+8]
0x18014af23  mov     rcx, [rax]
0x18014af26  sub     rcx, 8
0x18014af2a  cmp     rdx, rcx
0x18014af2d  ja      loc_18014B2E9
0x18014af33  xor     eax, eax
0x18014af35  jmp     short loc_18014AF56
0x18014af37  mov     rbx, [rsp+68h+arg_10]
0x18014af3f  mov     rdi, [rsp+68h+arg_8]
0x18014af44  mov     rdx, [rsp+68h+arg_18]
0x18014af4c  mov     r8, [rsp+68h+var_48]
0x18014af51  mov     r9, [rsp+68h+arg_0]
0x18014af56  test    eax, eax
0x18014af58  js      loc_18014B463
0x18014af5e  mov     rax, [rbx]
0x18014af61  test    rax, rax
0x18014af64  jz      short loc_18014AF83
0x18014af66  cmp     r8, [rax]
0x18014af69  jb      loc_18014B2E9
0x18014af6f  mov     rax, [rbx+8]
0x18014af73  mov     rcx, [rax]
0x18014af76  sub     rcx, 8
0x18014af7a  cmp     r8, rcx
0x18014af7d  ja      loc_18014B2E9
0x18014af83  xor     eax, eax
0x18014af85  jmp     short loc_18014AF9E
0x18014af87  mov     rdi, [rsp+68h+arg_8]
0x18014af8c  mov     rdx, [rsp+68h+arg_18]
0x18014af94  mov     r8, [rsp+68h+var_48]
0x18014af99  mov     r9, [rsp+68h+arg_0]
0x18014af9e  test    eax, eax
0x18014afa0  js      loc_18014B463
0x18014afa6  mov     rax, [rdx]
0x18014afa9  mov     [rdi+0F8h], rax
0x18014afb0  mov     rax, [r8]
0x18014afb3  mov     [r9], rax
0x18014afb6  mov     rax, [rsp+68h+arg_28]
0x18014afbe  mov     byte ptr [rax], 1
0x18014afc1  jmp     loc_18014B461
0x18014afc6  movzx   eax, word ptr [rsi+1]
0x18014afca  jmp     loc_18014B31A
0x18014afcf  mov     eax, [rsi+1]
0x18014afd2  jmp     loc_18014B31E
0x18014afd7  movzx   ebx, byte ptr [rsi+1]
0x18014afdb  mov     edx, ebx
0x18014afdd  and     edx, 0Fh
0x18014afe0  mov     rcx, rdi
0x18014afe3  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x18014afe8  mov     ecx, ebx
0x18014afea  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18014afee  sub     rax, rcx
0x18014aff1  mov     [rdi+98h], rax
0x18014aff8  jmp     loc_18014B461
0x18014affd  movzx   r14d, byte ptr [rsi]
0x18014b001  shr     r14d, 3
0x18014b005  mov     dword ptr [rsp+68h+arg_28], r14d
0x18014b00d  movzx   ecx, word ptr [rsi+1]
0x18014b011  mov     rax, [rsp+68h+arg_20]
0x18014b019  lea     rsi, [rax+rcx*8]
0x18014b01d  mov     [rsp+68h+arg_0], rsi
0x18014b022  mov     rax, [rbx]
0x18014b025  test    rax, rax
0x18014b028  jz      short loc_18014B047
0x18014b02a  cmp     rsi, [rax]
0x18014b02d  jb      loc_18014B2E9
0x18014b033  mov     rax, [rbx+8]
0x18014b037  mov     rcx, [rax]
0x18014b03a  sub     rcx, 8
0x18014b03e  cmp     rsi, rcx
0x18014b041  ja      loc_18014B2E9
0x18014b047  xor     eax, eax
0x18014b049  jmp     short loc_18014B065
0x18014b04b  mov     rbx, [rsp+68h+arg_10]
0x18014b053  mov     rdi, [rsp+68h+arg_8]
0x18014b058  mov     r14d, dword ptr [rsp+68h+arg_28]
0x18014b060  mov     rsi, [rsp+68h+arg_0]
0x18014b065  test    eax, eax
0x18014b067  js      loc_18014B463
0x18014b06d  mov     r8, [rsi]
0x18014b070  mov     edx, r14d
0x18014b073  mov     rcx, rdi
0x18014b076  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014b07b  mov     rcx, [rbx+10h]
0x18014b07f  test    rcx, rcx
0x18014b082  jz      loc_18014B461
0x18014b088  cmp     r14d, 10h
0x18014b08c  jnb     loc_18014B461
0x18014b092  mov     eax, r14d
0x18014b095  mov     [rcx+rax*8+80h], rsi
0x18014b09d  jmp     loc_18014B461
0x18014b0a2  sub     ecx, 7
0x18014b0a5  jz      loc_18014B32A
0x18014b0ab  sub     ecx, 1
0x18014b0ae  jz      loc_18014B312
0x18014b0b4  sub     ecx, 1
0x18014b0b7  jz      loc_18014B29F
0x18014b0bd  sub     ecx, 1
0x18014b0c0  jz      loc_18014B21E
0x18014b0c6  cmp     ecx, 16h
0x18014b0c9  jnz     loc_18014B474
0x18014b0cf  movzx   edx, word ptr [rsi]
0x18014b0d2  mov     word ptr [rsp+68h+arg_28], dx
0x18014b0da  lea     rsi, [rdi+98h]
0x18014b0e1  mov     [rsp+68h+arg_0], rsi
0x18014b0e6  mov     r14, [rsi]
0x18014b0e9  mov     [rsp+68h+arg_18], r14
0x18014b0f1  mov     rax, [rbx]
0x18014b0f4  test    rax, rax
0x18014b0f7  jz      short loc_18014B116
0x18014b0f9  cmp     r14, [rax]
0x18014b0fc  jb      loc_18014B2E9
0x18014b102  mov     rax, [rbx+8]
0x18014b106  mov     rcx, [rax]
0x18014b109  sub     rcx, 8
0x18014b10d  cmp     r14, rcx
0x18014b110  ja      loc_18014B2E9
0x18014b116  xor     eax, eax
0x18014b118  jmp     short loc_18014B13C
0x18014b11a  mov     rbx, [rsp+68h+arg_10]
0x18014b122  mov     rdi, [rsp+68h+arg_8]
0x18014b127  mov     rsi, [rsp+68h+arg_0]
0x18014b12c  mov     r14, [rsp+68h+arg_18]
0x18014b134  movzx   edx, word ptr [rsp+68h+arg_28]
0x18014b13c  test    eax, eax
0x18014b13e  js      loc_18014B463
0x18014b144  movzx   r15d, dx
0x18014b148  mov     dword ptr [rsp+68h+arg_28], r15d
0x18014b150  mov     r12d, r15d
0x18014b153  shr     r12d, 0Bh
0x18014b157  mov     r8, [r14]
0x18014b15a  mov     edx, r12d
0x18014b15d  mov     rcx, rdi
0x18014b160  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014b165  lea     r13, [rbx+10h]
0x18014b169  mov     [rsp+68h+arg_18], r13
0x18014b171  mov     rcx, [r13+0]
0x18014b175  test    rcx, rcx
0x18014b178  jz      short loc_18014B188
0x18014b17a  cmp     r12d, 10h
0x18014b17e  jnb     short loc_18014B188
0x18014b180  mov     [rcx+r12*8+80h], r14
0x18014b188  add     qword ptr [rsi], 8
0x18014b18c  mov     r14, [rsi]
0x18014b18f  mov     [rsp+68h+var_48], r14
0x18014b194  mov     rax, [rbx]
0x18014b197  test    rax, rax
0x18014b19a  jz      short loc_18014B1B9
0x18014b19c  cmp     r14, [rax]
0x18014b19f  jb      loc_18014B2E9
0x18014b1a5  mov     rax, [rbx+8]
0x18014b1a9  mov     rcx, [rax]
0x18014b1ac  sub     rcx, 8
0x18014b1b0  cmp     r14, rcx
0x18014b1b3  ja      loc_18014B2E9
0x18014b1b9  xor     eax, eax
0x18014b1bb  jmp     short loc_18014B1DC
0x18014b1bd  mov     rdi, [rsp+68h+arg_8]
0x18014b1c2  mov     r13, [rsp+68h+arg_18]
0x18014b1ca  mov     rsi, [rsp+68h+arg_0]
0x18014b1cf  mov     r14, [rsp+68h+var_48]
0x18014b1d4  mov     r15d, dword ptr [rsp+68h+arg_28]
0x18014b1dc  test    eax, eax
0x18014b1de  js      loc_18014B463
0x18014b1e4  shr     r15d, 6
0x18014b1e8  and     r15d, 1Fh
0x18014b1ec  mov     r8, [r14]
0x18014b1ef  mov     edx, r15d
0x18014b1f2  mov     rcx, rdi
0x18014b1f5  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT *>(_CONTEXT *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x18014b1fa  mov     rcx, [r13+0]
0x18014b1fe  test    rcx, rcx
0x18014b201  jz      loc_18014B45D
0x18014b207  cmp     r15d, 10h
0x18014b20b  jnb     loc_18014B45D
0x18014b211  mov     [rcx+r15*8+80h], r14
0x18014b219  jmp     loc_18014B45D
0x18014b21e  movzx   r9d, byte ptr [rsi]
0x18014b222  shr     r9d, 4
0x18014b226  mov     dword ptr [rsp+68h+arg_28], r9d
0x18014b22e  movzx   r8d, word ptr [rsi+1]
0x18014b233  add     r8, r8
0x18014b236  mov     rax, [rsp+68h+arg_20]
0x18014b23e  lea     r8, [rax+r8*8]
0x18014b242  mov     [rsp+68h+arg_0], r8
0x18014b247  jmp     short loc_18014B2C4
0x18014b249  xor     eax, eax
0x18014b24b  jmp     short loc_18014B267
0x18014b24d  mov     rbx, [rsp+68h+arg_10]
0x18014b255  mov     rdi, [rsp+68h+arg_8]
0x18014b25a  mov     r9d, dword ptr [rsp+68h+arg_28]
0x18014b262  mov     r8, [rsp+68h+arg_0]
0x18014b267  test    eax, eax
0x18014b269  js      loc_18014B463
0x18014b26f  mov     rdx, [r8+8]
0x18014b273  mov     r10d, r9d
  ... truncated ...
```
