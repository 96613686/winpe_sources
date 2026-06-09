# MDICreateDecompressionGlobal

- ea: `0x1800084e8`
- end: `0x1800088b8`
- name: `MDICreateDecompressionGlobal`
- size: `976`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000847c`

## callees

- `0x1800084e8`
- `0x180008e38`
- `0x1800092c0`
- `0x180015bc8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MDICreateDecompressionGlobal(__int64 a1)
{
  unsigned int v1; // edx
  _DWORD *v2; // r14
  int v4; // edi
  int v5; // ecx
  bool v6; // cf
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rax
  int v11; // eax
  __int64 *v12; // r15
  __int64 v13; // r13
  void (__fastcall *v14)(__int64); // rbp
  __int64 (__fastcall *v15)(__int64); // r12
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // r10
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // edx
  int v22; // r14d
  int v23; // eax
  int v24; // ecx
  int *v25; // rax
  int *v26; // rax
  __int64 v27; // [rsp+30h] [rbp-88h]
  __int64 v28; // [rsp+60h] [rbp-58h]
  __int64 v29; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+10h]
  __int64 v31; // [rsp+D0h] [rbp+18h]
  __int64 v32; // [rsp+D8h] [rbp+20h]

  v1 = *(unsigned __int16 *)(a1 + 266);
  v2 = (_DWORD *)(a1 + 236);
  v29 = 0;
  v30 = 0;
  *(_DWORD *)(a1 + 236) = 0x8000;
  v4 = 7;
  if ( (v1 & 0xF) == 0 )
  {
    *(_DWORD *)(a1 + 240) = 0x8000;
    goto LABEL_9;
  }
  if ( (v1 & 0xF) != 1 )
  {
    switch ( v1 & 0xF )
    {
      case 2u:
        HIDWORD(v29) = *(_DWORD *)(a1 + 64);
        LODWORD(v29) = (v1 >> 8) & 0x1F;
        v6 = (unsigned int)QDICreateDecompression((_DWORD)v2, (unsigned int)&v29, 0, 0, a1 + 240, 0) != 0;
        break;
      case 3u:
        LODWORD(v30) = 1 << (BYTE1(v1) & 0x1F);
        if ( a1 == -240 )
        {
          v5 = 2;
        }
        else
        {
          *(_DWORD *)(a1 + 240) = 38916;
          v5 = 0;
        }
        v6 = v5 != 0;
        break;
      case 0xFu:
        return 1;
      default:
        v7 = 6;
        goto LABEL_33;
    }
    v7 = v6 ? 7 : 0;
    if ( !v7 )
      goto LABEL_9;
LABEL_33:
    v26 = *(int **)a1;
    *v26 = v7;
    v26[1] = 0;
LABEL_38:
    v26[2] = 1;
    *(_WORD *)(a1 + 266) = 15;
    return 0;
  }
  *(_DWORD *)(a1 + 240) = 32780;
LABEL_9:
  v8 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(unsigned int *)(a1 + 240));
  *(_QWORD *)(a1 + 112) = v8;
  if ( !v8 )
  {
LABEL_37:
    v26 = *(int **)a1;
    **(_QWORD **)a1 = 5;
    goto LABEL_38;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))((unsigned int)*v2);
  *(_QWORD *)(a1 + 120) = v9;
  if ( !v9 )
  {
    (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 112));
    goto LABEL_37;
  }
  if ( (*(_WORD *)(a1 + 266) & 0xF) == 1 )
  {
    v23 = MDICreateDecompression((_DWORD)v2, *(_QWORD *)(a1 + 16), *(_QWORD *)(a1 + 8), (int)a1 + 240, a1 + 96);
LABEL_25:
    if ( !v23 )
      return 1;
    v24 = 7;
    if ( v23 == 1 )
      v24 = 5;
    v4 = v24;
    goto LABEL_29;
  }
  if ( (*(_WORD *)(a1 + 266) & 0xF) == 2 )
  {
    v23 = QDICreateDecompression(
            (_DWORD)v2,
            (unsigned int)&v29,
            *(_QWORD *)(a1 + 16),
            *(_QWORD *)(a1 + 8),
            a1 + 240,
            a1 + 96);
    goto LABEL_25;
  }
  if ( (*(_WORD *)(a1 + 266) & 0xF) != 3 )
    return 1;
  if ( a1 == -240 )
    goto LABEL_29;
  v11 = *v2 + 6148;
  if ( *v2 >= 0xFFFFE7FC )
    goto LABEL_29;
  v12 = (__int64 *)(a1 + 96);
  v13 = *(_QWORD *)(a1 + 56);
  v14 = *(void (__fastcall **)(__int64))(a1 + 8);
  v15 = *(__int64 (__fastcall **)(__int64))(a1 + 16);
  v28 = *(_QWORD *)(a1 + 48);
  v32 = *(_QWORD *)(a1 + 40);
  v31 = *(_QWORD *)(a1 + 32);
  v29 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 240) = v11;
  if ( a1 == -96 )
    return 1;
  *v12 = 0;
  v16 = v15(80);
  if ( v16 )
  {
    v17 = v15(12072);
    *(_QWORD *)(v16 + 72) = v17;
    if ( v17 )
    {
      v18 = v29;
      v19 = v31;
      v20 = v32;
      v27 = v32;
      *(_QWORD *)(v16 + 32) = v31;
      *(_QWORD *)(v16 + 40) = v20;
      *(_QWORD *)(v16 + 48) = v28;
      v21 = v30;
      *(_QWORD *)(v16 + 24) = v18;
      *(_QWORD *)(v16 + 8) = v15;
      *(_QWORD *)(v16 + 16) = v14;
      *(_QWORD *)(v16 + 56) = v13;
      *(_DWORD *)(v16 + 64) = *v2;
      *(_DWORD *)(v16 + 68) = HIDWORD(v30);
      *(_DWORD *)v16 = 1128875084;
      v22 = LZX_DecodeInit(v17, v21, (_DWORD)v15, (_DWORD)v14, v18, v19, v27, v28, v13);
      if ( !v22 )
      {
        *v12 = v16;
        return 1;
      }
      v14(*(_QWORD *)(v16 + 72));
      v14(v16);
      if ( v22 != 1 )
        goto LABEL_29;
    }
    else
    {
      v14(v16);
    }
  }
  v4 = 5;
LABEL_29:
  (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 112));
  (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 120));
  v25 = *(int **)a1;
  *v25 = v4;
  v25[1] = 0;
  v25[2] = 1;
  *(_WORD *)(a1 + 266) = 15;
  return 0;
}

```

## disassembly

```asm
0x1800084e8  mov     rax, rsp
0x1800084eb  push    rbx
0x1800084ec  push    rbp
0x1800084ed  push    rsi
0x1800084ee  push    rdi
0x1800084ef  push    r12
0x1800084f1  push    r13
0x1800084f3  push    r14
0x1800084f5  push    r15
0x1800084f7  sub     rsp, 78h
0x1800084fb  movzx   edx, word ptr [rcx+10Ah]
0x180008502  lea     r14, [rcx+0ECh]
0x180008509  mov     ebp, 0Fh
0x18000850e  mov     qword ptr [rax+8], 0
0x180008516  mov     rbx, rcx
0x180008519  mov     [rsp+0B8h+arg_8], 0
0x180008525  mov     ecx, edx
0x180008527  mov     r8d, 8000h
0x18000852d  mov     [r14], r8d
0x180008530  lea     edi, [rbp-8]
0x180008533  and     ecx, ebp
0x180008535  jnz     loc_180008602
0x18000853b  mov     [rbx+0F0h], r8d
0x180008542  jmp     short loc_180008594
0x180008544  sub     ecx, 1
0x180008547  jz      loc_1800087DE
0x18000854d  sub     ecx, 1
0x180008550  jnz     loc_1800087B8
0x180008556  lea     eax, [rcx+1]
0x180008559  shr     edx, 8
0x18000855c  and     edx, 1Fh
0x18000855f  mov     cl, dl
0x180008561  shl     eax, cl
0x180008563  mov     dword ptr [rsp+0B8h+arg_8], eax
0x18000856a  lea     rax, [rbx+0F0h]
0x180008571  test    rax, rax
0x180008574  jz      loc_1800087D4
0x18000857a  mov     dword ptr [rax], 9804h
0x180008580  xor     ecx, ecx
0x180008582  xor     eax, eax
0x180008584  sub     eax, ecx
0x180008586  neg     eax
0x180008588  sbb     ecx, ecx
0x18000858a  and     ecx, edi
0x18000858c  test    ecx, ecx
0x18000858e  jnz     loc_1800087C6
0x180008594  mov     rax, [rbx+10h]
0x180008598  lea     rsi, [rbx+0F0h]
0x18000859f  mov     ecx, [rsi]
0x1800085a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a6  mov     [rbx+70h], rax
0x1800085aa  test    rax, rax
0x1800085ad  jz      loc_180008838
0x1800085b3  mov     ecx, [r14]
0x1800085b6  mov     rax, [rbx+10h]
0x1800085ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085bf  mov     [rbx+78h], rax
0x1800085c3  test    rax, rax
0x1800085c6  jz      loc_18000882B
0x1800085cc  movzx   ecx, word ptr [rbx+10Ah]
0x1800085d3  and     ecx, ebp
0x1800085d5  sub     ecx, 1
0x1800085d8  jz      loc_180008748
0x1800085de  sub     ecx, 1
0x1800085e1  jz      loc_18000888D
0x1800085e7  cmp     ecx, 1
0x1800085ea  jz      short loc_18000861A
0x1800085ec  mov     eax, 1
0x1800085f1  add     rsp, 78h
0x1800085f5  pop     r15
0x1800085f7  pop     r14
0x1800085f9  pop     r13
0x1800085fb  pop     r12
0x1800085fd  pop     rdi
0x1800085fe  pop     rsi
0x1800085ff  pop     rbp
0x180008600  pop     rbx
0x180008601  retn
0x180008602  sub     ecx, 1
0x180008605  jnz     loc_180008544
0x18000860b  mov     dword ptr [rbx+0F0h], 800Ch
0x180008615  jmp     loc_180008594
0x18000861a  test    rsi, rsi
0x18000861d  jz      loc_18000877B
0x180008623  mov     eax, [r14]
0x180008626  add     eax, 1804h
0x18000862b  cmp     eax, 1804h
0x180008630  jb      loc_18000877B
0x180008636  mov     rcx, [rbx+30h]
0x18000863a  lea     r15, [rbx+60h]
0x18000863e  mov     r13, [rbx+38h]
0x180008642  mov     rbp, [rbx+8]
0x180008646  mov     r12, [rbx+10h]
0x18000864a  mov     [rsp+0B8h+var_58], rcx
0x18000864f  mov     rcx, [rbx+28h]
0x180008653  mov     [rsp+0B8h+arg_18], rcx
0x18000865b  mov     rcx, [rbx+20h]
0x18000865f  mov     [rsp+0B8h+arg_10], rcx
0x180008667  mov     rcx, [rbx+18h]
0x18000866b  mov     [rsp+0B8h+arg_0], rcx
0x180008673  mov     [rsi], eax
0x180008675  test    r15, r15
0x180008678  jz      loc_1800085EC
0x18000867e  mov     ecx, 50h ; 'P'
0x180008683  mov     qword ptr [r15], 0
0x18000868a  mov     rax, r12
0x18000868d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008692  mov     rsi, rax
0x180008695  test    rax, rax
0x180008698  jz      loc_180008883
0x18000869e  mov     ecx, 2F28h
0x1800086a3  mov     rax, r12
0x1800086a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ab  mov     [rsi+48h], rax
0x1800086af  mov     rcx, rax
0x1800086b2  test    rax, rax
0x1800086b5  jz      loc_180008855
0x1800086bb  mov     rdx, [rsp+0B8h+var_58]
0x1800086c0  mov     r10, [rsp+0B8h+arg_0]
0x1800086c8  mov     r9, [rsp+0B8h+arg_10]
0x1800086d0  mov     r8, [rsp+0B8h+arg_18]
0x1800086d8  mov     [rsp+0B8h+var_78], r13
0x1800086dd  mov     [rsp+0B8h+var_80], rdx
0x1800086e2  mov     [rsp+0B8h+var_88], r8
0x1800086e7  mov     [rsi+20h], r9
0x1800086eb  mov     [rsi+28h], r8
0x1800086ef  mov     r8, r12
0x1800086f2  mov     [rsi+30h], rdx
0x1800086f6  mov     edx, dword ptr [rsp+0B8h+arg_8]
0x1800086fd  mov     [rsp+0B8h+var_90], r9
0x180008702  mov     r9, rbp
0x180008705  mov     [rsi+18h], r10
0x180008709  mov     [rsi+8], r12
0x18000870d  mov     [rsi+10h], rbp
0x180008711  mov     [rsi+38h], r13
0x180008715  mov     eax, [r14]
0x180008718  mov     [rsi+40h], eax
0x18000871b  mov     eax, dword ptr [rsp+0B8h+arg_8+4]
0x180008722  mov     [rsi+44h], eax
0x180008725  mov     dword ptr [rsi], 4349444Ch
0x18000872b  mov     [rsp+0B8h+var_98], r10
0x180008730  call    LZX_DecodeInit
0x180008735  mov     r14d, eax
0x180008738  test    eax, eax
0x18000873a  jnz     loc_180008862
0x180008740  mov     [r15], rsi
0x180008743  jmp     loc_1800085EC
0x180008748  mov     r8, [rbx+8]
0x18000874c  lea     rax, [rbx+60h]
0x180008750  mov     rdx, [rbx+10h]
0x180008754  mov     r9, rsi
0x180008757  mov     rcx, r14
0x18000875a  mov     [rsp+0B8h+var_98], rax
0x18000875f  call    MDICreateDecompression
0x180008764  test    eax, eax
0x180008766  jz      loc_1800085EC
0x18000876c  mov     ecx, edi
0x18000876e  cmp     eax, 1
0x180008771  mov     edi, 5
0x180008776  cmovz   ecx, edi
0x180008779  mov     edi, ecx
0x18000877b  mov     rcx, [rbx+70h]
0x18000877f  mov     rax, [rbx+8]
0x180008783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008788  mov     rcx, [rbx+78h]
0x18000878c  mov     rax, [rbx+8]
0x180008790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008795  mov     rax, [rbx]
0x180008798  mov     [rax], edi
0x18000879a  mov     dword ptr [rax+4], 0
0x1800087a1  mov     dword ptr [rax+8], 1
0x1800087a8  mov     word ptr [rbx+10Ah], 0Fh
0x1800087b1  xor     eax, eax
0x1800087b3  jmp     loc_1800085F1
0x1800087b8  cmp     ecx, 0Ch
0x1800087bb  jz      loc_1800085EC
0x1800087c1  mov     ecx, 6
0x1800087c6  mov     rax, [rbx]
0x1800087c9  mov     [rax], ecx
0x1800087cb  mov     dword ptr [rax+4], 0
0x1800087d2  jmp     short loc_180008842
0x1800087d4  mov     ecx, 2
0x1800087d9  jmp     loc_180008582
0x1800087de  mov     eax, [rbx+40h]
0x1800087e1  xor     r9d, r9d
0x1800087e4  shr     edx, 8
0x1800087e7  xor     r8d, r8d
0x1800087ea  and     edx, 1Fh
0x1800087ed  mov     dword ptr [rsp+0B8h+arg_0+4], eax
0x1800087f4  mov     dword ptr [rsp+0B8h+arg_0], edx
0x1800087fb  lea     rax, [rbx+0F0h]
0x180008802  lea     rdx, [rsp+0B8h+arg_0]
0x18000880a  mov     [rsp+0B8h+var_90], 0
0x180008813  mov     rcx, r14
0x180008816  mov     [rsp+0B8h+var_98], rax
0x18000881b  call    QDICreateDecompression
0x180008820  xor     ecx, ecx
0x180008822  sub     ecx, eax
0x180008824  neg     ecx
0x180008826  jmp     loc_180008588
0x18000882b  mov     rcx, [rbx+70h]
0x18000882f  mov     rax, [rbx+8]
0x180008833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008838  mov     rax, [rbx]
0x18000883b  mov     qword ptr [rax], 5
0x180008842  mov     dword ptr [rax+8], 1
0x180008849  mov     [rbx+10Ah], bp
0x180008850  jmp     loc_1800087B1
0x180008855  mov     rcx, rsi
0x180008858  mov     rax, rbp
0x18000885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008860  jmp     short loc_180008883
0x180008862  mov     rcx, [rsi+48h]
0x180008866  mov     rax, rbp
0x180008869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000886e  mov     rcx, rsi
0x180008871  mov     rax, rbp
0x180008874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008879  cmp     r14d, 1
0x18000887d  jnz     loc_18000877B
0x180008883  mov     edi, 5
0x180008888  jmp     loc_18000877B
0x18000888d  mov     r9, [rbx+8]
0x180008891  lea     rax, [rbx+60h]
0x180008895  mov     r8, [rbx+10h]
0x180008899  lea     rdx, [rsp+0B8h+arg_0]
0x1800088a1  mov     [rsp+0B8h+var_90], rax
0x1800088a6  mov     rcx, r14
0x1800088a9  mov     [rsp+0B8h+var_98], rsi
0x1800088ae  call    QDICreateDecompression
0x1800088b3  jmp     loc_180008764
```
