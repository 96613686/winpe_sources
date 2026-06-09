# sbit_GetMetrics(sbit_State *,sfac_ClientRec const *,point *,point *,point *,point *,point *,point *,DWRITE_Rect *,ushort *,uint *,uint *)

- ea: `0x140029fe8`
- end: `0x14002a569`
- name: `?sbit_GetMetrics@@YAHPEAUsbit_State@@PEBUsfac_ClientRec@@PEAUpoint@@22222PEAUDWRITE_Rect@@PEAGPEAI5@Z`
- size: `1409`
- prototype: `__int64 __fastcall(struct sbit_State *, const struct sfac_ClientRec *, struct point *, struct point *, struct point *, struct point *, struct point *, struct point *, struct DWRITE_Rect *, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14002a840`

## callees

- `0x14002973c`
- `0x140029fe8`
- `0x14002a570`
- `0x14002a630`
- `0x14002a6f0`
- `0x14002a7a8`
- `0x140042a00`
- `0x14004b584`
- `0x140050cac`
- `0x140072578`

## pseudocode

```c
__int64 __fastcall sbit_GetMetrics(
        struct sbit_State *a1,
        const struct sfac_ClientRec *a2,
        struct point *a3,
        struct point *a4,
        struct point *a5,
        struct point *a6,
        struct point *a7,
        struct point *a8,
        struct DWRITE_Rect *a9,
        unsigned __int16 *a10,
        unsigned int *a11,
        unsigned int *a12)
{
  __int64 result; // rax
  _WORD *v14; // rax
  __int64 v15; // r8
  _WORD *v16; // rax
  __int64 v17; // r8
  int v18; // ebx
  __int16 *v19; // rax
  __int64 v20; // rcx
  int v21; // r12d
  int v22; // r15d
  int v23; // r14d
  int v24; // esi
  int v25; // edi
  int v26; // ebx
  int v27; // r14d
  int v28; // r9d
  unsigned __int16 v29; // r8
  unsigned int v30; // eax
  unsigned __int16 v31; // cx
  int v32; // r10d
  unsigned __int16 v33; // ax
  int v34; // r11d
  int v35; // r15d
  int v36; // esi
  int v37; // r9d
  int v38; // edi
  __int16 v39; // cx
  __int16 v40; // dx
  __int16 v41; // r8
  int v42; // edx
  unsigned __int16 *v43; // rbx
  unsigned int v44; // edx
  bool v45; // zf
  __int16 v46; // r8
  __int16 v47; // dx
  int v48; // edx
  int v49; // r8d
  int v50; // ecx
  struct point *v51; // rax
  __int16 v52; // r8
  __int16 v53; // dx
  int v54; // r10d
  int v55; // r10d
  int v56; // r12d
  __int16 v57; // r8
  int v58; // eax
  __int16 v59; // dx
  __int16 v60; // r8
  int v61; // r9d
  int v62; // ecx
  int v63; // edx
  unsigned int *v64; // rax
  __int16 v65; // [rsp+22h] [rbp-1Eh] BYREF
  _BYTE v66[4]; // [rsp+24h] [rbp-1Ch] BYREF
  int v67; // [rsp+28h] [rbp-18h]
  int v68; // [rsp+2Ch] [rbp-14h] BYREF
  _DWORD v69[4]; // [rsp+30h] [rbp-10h] BYREF

  result = GetSbitMetrics(a1, a2);
  if ( !(_DWORD)result )
  {
    v14 = (_WORD *)UScaleX(&v65, a1, *((unsigned __int16 *)a1 + 22));
    v15 = *((unsigned __int16 *)a1 + 21);
    *((_WORD *)a1 + 27) = *v14;
    v16 = (_WORD *)UScaleY(&v65, a1, v15);
    v17 = *((unsigned __int16 *)a1 + 35);
    *((_WORD *)a1 + 26) = *v16;
    v18 = *(__int16 *)SScaleY(&v65, a1, v17);
    v19 = (__int16 *)SScaleX(&v65, a1, *((unsigned __int16 *)a1 + 34));
    if ( *((_WORD *)a1 + 26) > 0x7FFFu
      || (v21 = v18, v67 = v18 - *((__int16 *)a1 + 26), v20 = (unsigned int)(v67 + 0x8000), (unsigned int)v20 > 0xFFFF)
      || *((_WORD *)a1 + 27) > 0x7FFFu
      || (v65 = *v19,
          v20 = (unsigned int)v65,
          v69[0] = v65,
          v68 = v20 + *((__int16 *)a1 + 27),
          (unsigned int)(v68 + 0x8000) > 0xFFFF) )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v20, v19);
      JUMPOUT(0x14002A568LL);
    }
    v22 = *(unsigned __int16 *)UScaleX(v66, a1, *((unsigned __int16 *)a1 + 23));
    v23 = *(unsigned __int16 *)UScaleY(v66, a1, *((unsigned __int16 *)a1 + 24));
    v24 = *(__int16 *)SScaleX(v66, a1, *((unsigned __int16 *)a1 + 34));
    v25 = *(__int16 *)SScaleY(v66, a1, *((unsigned __int16 *)a1 + 35));
    v26 = *(__int16 *)SScaleX(v66, a1, *((unsigned __int16 *)a1 + 36));
    v27 = v23 << 6;
    v28 = *(__int16 *)SScaleY(v66, a1, *((unsigned __int16 *)a1 + 37));
    v29 = (((unsigned int)*((unsigned __int16 *)a1 + 22) + 31) >> 3) & 0xFFFC;
    v30 = *((unsigned __int16 *)a1 + 27) + 31;
    *((_WORD *)a1 + 25) = v29;
    v31 = (v30 >> 3) & 0xFFFC;
    v32 = v22 << 6;
    *((_WORD *)a1 + 28) = v31;
    v33 = *((_WORD *)a1 + 26);
    v34 = v24 << 6;
    v35 = v25 << 6;
    v36 = v26 << 6;
    v37 = v28 << 6;
    if ( *((_WORD *)a1 + 21) >= v33 )
      v33 = *((_WORD *)a1 + 21);
    if ( v29 >= v31 )
      v31 = v29;
    v38 = v31 * v33;
    switch ( *((_WORD *)a1 + 17) )
    {
      case 0:
        v39 = v65;
        v40 = v68;
        v41 = v67;
        *(_WORD *)a9 = v21;
        *((_WORD *)a9 + 1) = v39;
        *((_WORD *)a9 + 3) = v40;
        *((_WORD *)a9 + 2) = v41;
        v42 = *((unsigned __int16 *)a1 + 26);
        *((_DWORD *)a3 + 1) = 0;
        *(_DWORD *)a3 = v32;
        *(_DWORD *)a4 = v34;
        *((_DWORD *)a4 + 1) = v35;
        *(_DWORD *)a5 = v34;
        *((_DWORD *)a5 + 1) = v21 << 6;
        *(_DWORD *)a6 = 0;
        v43 = (unsigned __int16 *)((char *)a1 + 58);
        *((_DWORD *)a6 + 1) = v27;
        *(_DWORD *)a7 = v36;
        *((_DWORD *)a7 + 1) = v37;
        *(_DWORD *)a8 = v36;
        *((_DWORD *)a8 + 1) = v37;
        v44 = ((((unsigned int)*((unsigned __int16 *)a1 + 27) + 31) >> 3) & 0xFFFC) * v42;
        v45 = *((_WORD *)a1 + 12) == 3;
        *((_WORD *)a1 + 29) = (((unsigned int)*((unsigned __int16 *)a1 + 27) + 31) >> 3) & 0xFFFC;
        *((_DWORD *)a1 + 4) = v44;
        if ( !v45 )
          v38 = 0;
        goto LABEL_13;
      case 1:
        v59 = v68;
        v60 = -(__int16)v67;
        *((_WORD *)a9 + 1) = -(__int16)v21;
        v61 = -v37;
        *((_WORD *)a9 + 2) = v65;
        *(_WORD *)a9 = v59;
        *((_WORD *)a9 + 3) = v60;
        v62 = v59 << 6;
        v63 = v59 - v69[0];
        *(_DWORD *)a3 = 0;
        *((_DWORD *)a3 + 1) = v32;
        v63 <<= 6;
        *(_DWORD *)a4 = -v35;
        *((_DWORD *)a4 + 1) = v63 + v34;
        *((_DWORD *)a5 + 1) = v62 - v34;
        *(_DWORD *)a5 = 0;
        *(_DWORD *)a7 = v61;
        *(_QWORD *)a6 = (unsigned int)-v27;
        *((_DWORD *)a7 + 1) = v63 + v36;
        v51 = a8;
        *(_DWORD *)a8 = v61 - (v21 << 6);
        break;
      case 2:
        v52 = v67;
        v53 = v68;
        *(_WORD *)a9 = -(__int16)v67;
        *((_WORD *)a9 + 1) = -v53;
        *((_WORD *)a9 + 2) = -(__int16)v21;
        *((_WORD *)a9 + 3) = -v65;
        *(_DWORD *)a3 = -v32;
        v54 = v69[0];
        *((_DWORD *)a3 + 1) = 0;
        v55 = (v54 - v53) << 6;
        v56 = (v21 - v52) << 6;
        *(_DWORD *)a4 = v55 - v34;
        *((_DWORD *)a4 + 1) = v56 - v35;
        *((_DWORD *)a5 + 1) = -64 * v52;
        *(_DWORD *)a5 = -v34;
        *(_DWORD *)a6 = 0;
        *((_DWORD *)a6 + 1) = -v27;
        *(_DWORD *)a7 = v55 - v36;
        *((_DWORD *)a7 + 1) = v56 - v37;
        *(_DWORD *)a8 = -64 * v53;
        *((_DWORD *)a8 + 1) = -v37;
        v69[0] = *((unsigned __int16 *)a1 + 27);
        v69[0] = (*(_DWORD *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<int>(
                               v69,
                               &v68,
                               31) >> 3)
               & 0x1FFFFFFC;
        v57 = *(_WORD *)SafeInt<unsigned short,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator=<unsigned int>(
                          v66,
                          v69);
        v58 = *((unsigned __int16 *)a1 + 26);
LABEL_23:
        v43 = (unsigned __int16 *)((char *)a1 + 58);
        v69[0] = v58;
        *((_WORD *)a1 + 29) = v57;
        v64 = (unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned short>(
                                v69,
                                &v68);
        v44 = *v64;
        *((_DWORD *)a1 + 4) = *v64;
LABEL_13:
        *((_DWORD *)a1 + 5) = v38;
        *a10 = *v43;
        *a11 = v44;
        *a12 = v38;
        return 0;
      case 3:
        v46 = v67;
        v47 = v68;
        *(_WORD *)a9 = -v65;
        *((_WORD *)a9 + 2) = -v47;
        *((_WORD *)a9 + 1) = v46;
        *((_WORD *)a9 + 3) = v21;
        v48 = v46;
        v49 = v69[0] << 6;
        *(_DWORD *)a3 = 0;
        *((_DWORD *)a3 + 1) = -v32;
        v50 = (v48 - v21) << 6;
        *(_DWORD *)a4 = v50 + v35;
        *((_DWORD *)a4 + 1) = -v34;
        *(_DWORD *)a5 = 0;
        *((_DWORD *)a5 + 1) = v34 - v49;
        *(_DWORD *)a6 = v27;
        *((_DWORD *)a6 + 1) = 0;
        *(_DWORD *)a7 = v50 + v37;
        *((_DWORD *)a7 + 1) = -64 * v26;
        v51 = a8;
        *(_DWORD *)a8 = v37 + ((v48 - 2 * v21) << 6);
        break;
      default:
        return 6146;
    }
    *((_DWORD *)v51 + 1) = 0;
    v69[0] = *((unsigned __int16 *)a1 + 26);
    v69[0] = (*(_DWORD *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<int>(
                           v69,
                           &v68,
                           31) >> 3)
           & 0x1FFFFFFC;
    v57 = *(_WORD *)SafeInt<unsigned short,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator=<unsigned int>(
                      v66,
                      v69);
    v58 = *((unsigned __int16 *)a1 + 27);
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x140029fe8  mov     [rsp-38h+arg_0], rbx
0x140029fed  mov     [rsp-38h+arg_18], r9
0x140029ff2  mov     [rsp-38h+arg_10], r8
0x140029ff7  push    rbp
0x140029ff8  push    rsi
0x140029ff9  push    rdi
0x140029ffa  push    r12
0x140029ffc  push    r13
0x140029ffe  push    r14
0x14002a000  push    r15
0x14002a002  mov     rbp, rsp
0x14002a005  sub     rsp, 40h
0x14002a009  mov     r13, rcx
0x14002a00c  call    GetSbitMetrics
0x14002a011  test    eax, eax
0x14002a013  jnz     loc_14002A291
0x14002a019  movzx   r8d, word ptr [r13+2Ch]
0x14002a01e  lea     rcx, [rbp+var_1E]
0x14002a022  mov     rdx, r13
0x14002a025  call    UScaleX
0x14002a02a  movzx   r8d, word ptr [r13+2Ah]
0x14002a02f  lea     rcx, [rbp+var_1E]
0x14002a033  mov     rdx, r13
0x14002a036  movzx   eax, word ptr [rax]
0x14002a039  mov     [r13+36h], ax
0x14002a03e  call    UScaleY
0x14002a043  movzx   r8d, word ptr [r13+46h]
0x14002a048  lea     rcx, [rbp+var_1E]
0x14002a04c  mov     rdx, r13
0x14002a04f  movzx   eax, word ptr [rax]
0x14002a052  mov     [r13+34h], ax
0x14002a057  call    SScaleY
0x14002a05c  movzx   r8d, word ptr [r13+44h]
0x14002a061  lea     rcx, [rbp+var_1E]
0x14002a065  mov     rdx, r13
0x14002a068  movsx   ebx, word ptr [rax]
0x14002a06b  call    SScaleX
0x14002a070  mov     r9d, 7FFFh
0x14002a076  mov     rdx, rax
0x14002a079  cmp     [r13+34h], r9w
0x14002a07e  ja      loc_14002A563
0x14002a084  movsx   ecx, word ptr [r13+34h]
0x14002a089  mov     eax, ebx
0x14002a08b  sub     eax, ecx
0x14002a08d  mov     r8d, 0FFFFh
0x14002a093  mov     r12d, ebx
0x14002a096  mov     [rbp+var_18], eax
0x14002a099  lea     ecx, [rax+8000h]
0x14002a09f  cmp     ecx, r8d
0x14002a0a2  ja      loc_14002A563
0x14002a0a8  cmp     [r13+36h], r9w
0x14002a0ad  ja      loc_14002A563
0x14002a0b3  movsx   eax, word ptr [rdx]
0x14002a0b6  mov     [rbp+var_1E], ax
0x14002a0ba  mov     ecx, eax
0x14002a0bc  mov     [rbp+var_10], eax
0x14002a0bf  movsx   eax, word ptr [r13+36h]
0x14002a0c4  add     eax, ecx
0x14002a0c6  mov     [rbp+var_14], eax
0x14002a0c9  add     eax, 8000h
0x14002a0ce  cmp     eax, r8d
0x14002a0d1  ja      loc_14002A563
0x14002a0d7  movzx   r8d, word ptr [r13+2Eh]
0x14002a0dc  lea     rcx, [rbp+var_1C]
0x14002a0e0  mov     rdx, r13
0x14002a0e3  call    UScaleX
0x14002a0e8  movzx   r8d, word ptr [r13+30h]
0x14002a0ed  lea     rcx, [rbp+var_1C]
0x14002a0f1  mov     rdx, r13
0x14002a0f4  movzx   r15d, word ptr [rax]
0x14002a0f8  call    UScaleY
0x14002a0fd  movzx   r8d, word ptr [r13+44h]
0x14002a102  lea     rcx, [rbp+var_1C]
0x14002a106  mov     rdx, r13
0x14002a109  movzx   r14d, word ptr [rax]
0x14002a10d  call    SScaleX
0x14002a112  movzx   r8d, word ptr [r13+46h]
0x14002a117  lea     rcx, [rbp+var_1C]
0x14002a11b  mov     rdx, r13
0x14002a11e  movsx   esi, word ptr [rax]
0x14002a121  call    SScaleY
0x14002a126  movzx   r8d, word ptr [r13+48h]
0x14002a12b  lea     rcx, [rbp+var_1C]
0x14002a12f  mov     rdx, r13
0x14002a132  movsx   edi, word ptr [rax]
0x14002a135  call    SScaleX
0x14002a13a  movzx   r8d, word ptr [r13+4Ah]
0x14002a13f  lea     rcx, [rbp+var_1C]
0x14002a143  mov     rdx, r13
0x14002a146  movsx   ebx, word ptr [rax]
0x14002a149  call    SScaleY
0x14002a14e  movzx   r8d, word ptr [r13+2Ch]
0x14002a153  mov     ecx, 0FFFCh
0x14002a158  add     r8d, 1Fh
0x14002a15c  shl     r14d, 6
0x14002a160  shr     r8d, 3
0x14002a164  mov     r10d, r15d
0x14002a167  movsx   r9d, word ptr [rax]
0x14002a16b  and     r8w, cx
0x14002a16f  movzx   eax, word ptr [r13+36h]
0x14002a174  mov     r11d, esi
0x14002a177  add     eax, 1Fh
0x14002a17a  mov     [r13+32h], r8w
0x14002a17f  shr     eax, 3
0x14002a182  mov     r15d, edi
0x14002a185  and     cx, ax
0x14002a188  shl     r10d, 6
0x14002a18c  mov     [r13+38h], cx
0x14002a191  mov     esi, ebx
0x14002a193  movzx   eax, word ptr [r13+34h]
0x14002a198  shl     r11d, 6
0x14002a19c  shl     r15d, 6
0x14002a1a0  shl     esi, 6
0x14002a1a3  shl     r9d, 6
0x14002a1a7  cmp     [r13+2Ah], ax
0x14002a1ac  cmovnb  ax, [r13+2Ah]
0x14002a1b2  cmp     r8w, cx
0x14002a1b6  movzx   edi, ax
0x14002a1b9  cmovnb  cx, r8w
0x14002a1be  xor     ebx, ebx
0x14002a1c0  movzx   eax, cx
0x14002a1c3  movzx   ecx, word ptr [r13+22h]
0x14002a1c8  imul    rdi, rax
0x14002a1cc  test    ecx, ecx
0x14002a1ce  jnz     loc_14002A2A9
0x14002a1d4  mov     rax, [rbp+arg_40]
0x14002a1db  movzx   ecx, [rbp+var_1E]
0x14002a1df  mov     edx, [rbp+var_14]
0x14002a1e2  mov     r8d, [rbp+var_18]
0x14002a1e6  mov     [rax], r12w
0x14002a1ea  mov     [rax+2], cx
0x14002a1ee  mov     ecx, 0FFFCh
0x14002a1f3  mov     [rax+6], dx
0x14002a1f7  mov     [rax+4], r8w
0x14002a1fc  mov     rax, [rbp+arg_10]
0x14002a200  movzx   edx, word ptr [r13+34h]
0x14002a205  shl     r12d, 6
0x14002a209  mov     [rax+4], ebx
0x14002a20c  mov     [rax], r10d
0x14002a20f  mov     rax, [rbp+arg_18]
0x14002a213  mov     [rax], r11d
0x14002a216  mov     [rax+4], r15d
0x14002a21a  mov     rax, [rbp+arg_20]
0x14002a21e  mov     [rax], r11d
0x14002a221  mov     [rax+4], r12d
0x14002a225  mov     rax, [rbp+arg_28]
0x14002a229  mov     [rax], ebx
0x14002a22b  lea     rbx, [r13+3Ah]
0x14002a22f  mov     [rax+4], r14d
0x14002a233  mov     rax, [rbp+arg_30]
0x14002a237  mov     [rax], esi
0x14002a239  mov     [rax+4], r9d
0x14002a23d  mov     rax, [rbp+arg_38]
0x14002a241  mov     [rax], esi
0x14002a243  mov     [rax+4], r9d
0x14002a247  movzx   eax, word ptr [r13+36h]
0x14002a24c  add     eax, 1Fh
0x14002a24f  shr     eax, 3
0x14002a252  and     ax, cx
0x14002a255  movzx   eax, ax
0x14002a258  imul    edx, eax
0x14002a25b  cmp     word ptr [r13+18h], 3
0x14002a261  mov     [rbx], ax
0x14002a264  mov     [r13+10h], edx
0x14002a268  jz      short loc_14002A26C
0x14002a26a  xor     edi, edi
0x14002a26c  mov     rax, [rbp+arg_48]
0x14002a273  mov     [r13+14h], edi
0x14002a277  movzx   ecx, word ptr [rbx]
0x14002a27a  mov     [rax], cx
0x14002a27d  mov     rax, [rbp+arg_50]
0x14002a284  mov     [rax], edx
0x14002a286  mov     rax, [rbp+arg_58]
0x14002a28d  mov     [rax], edi
0x14002a28f  xor     eax, eax
0x14002a291  mov     rbx, [rsp+40h+arg_0]
0x14002a299  add     rsp, 40h
0x14002a29d  pop     r15
0x14002a29f  pop     r14
0x14002a2a1  pop     r13
0x14002a2a3  pop     r12
0x14002a2a5  pop     rdi
0x14002a2a6  pop     rsi
0x14002a2a7  pop     rbp
0x14002a2a8  retn
0x14002a2a9  sub     ecx, 1
0x14002a2ac  jz      loc_14002A465
0x14002a2b2  sub     ecx, 1
0x14002a2b5  jz      loc_14002A368
0x14002a2bb  cmp     ecx, 1
0x14002a2be  jz      short loc_14002A2C7
0x14002a2c0  mov     eax, 1802h
0x14002a2c5  jmp     short loc_14002A291
0x14002a2c7  mov     rax, [rbp+arg_40]
0x14002a2ce  neg     r10d
0x14002a2d1  movzx   ecx, [rbp+var_1E]
0x14002a2d5  neg     esi
0x14002a2d7  mov     r8d, [rbp+var_18]
0x14002a2db  neg     cx
0x14002a2de  mov     edx, [rbp+var_14]
0x14002a2e1  mov     [rax], cx
0x14002a2e4  neg     dx
0x14002a2e7  mov     [rax+4], dx
0x14002a2eb  mov     [rax+2], r8w
0x14002a2f0  mov     [rax+6], r12w
0x14002a2f5  mov     rax, [rbp+arg_10]
0x14002a2f9  movsx   edx, r8w
0x14002a2fd  mov     r8d, [rbp+var_10]
0x14002a301  mov     ecx, edx
0x14002a303  sub     ecx, r12d
0x14002a306  shl     r8d, 6
0x14002a30a  mov     [rax], ebx
0x14002a30c  mov     rbx, [rbp+arg_18]
0x14002a310  mov     [rax+4], r10d
0x14002a314  shl     ecx, 6
0x14002a317  lea     eax, [rcx+r15]
0x14002a31b  mov     [rbx], eax
0x14002a31d  mov     eax, r11d
0x14002a320  neg     eax
0x14002a322  sub     r11d, r8d
0x14002a325  mov     [rbx+4], eax
0x14002a328  mov     rax, [rbp+arg_20]
0x14002a32c  mov     dword ptr [rax], 0
0x14002a332  mov     [rax+4], r11d
0x14002a336  mov     rax, [rbp+arg_28]
0x14002a33a  mov     [rax], r14d
0x14002a33d  mov     dword ptr [rax+4], 0
0x14002a344  lea     eax, [rcx+r9]
0x14002a348  mov     rcx, [rbp+arg_30]
0x14002a34c  mov     [rcx], eax
0x14002a34e  lea     eax, [r12+r12]
0x14002a352  sub     edx, eax
0x14002a354  mov     [rcx+4], esi
0x14002a357  mov     rax, [rbp+arg_38]
0x14002a35b  shl     edx, 6
0x14002a35e  add     edx, r9d
0x14002a361  mov     [rax], edx
0x14002a363  jmp     loc_14002A4FA
0x14002a368  mov     rcx, [rbp+arg_40]
0x14002a36f  neg     r10d
0x14002a372  mov     r8d, [rbp+var_18]
0x14002a376  neg     r14d
0x14002a379  mov     edx, [rbp+var_14]
0x14002a37c  movzx   eax, r8w
0x14002a380  neg     ax
0x14002a383  mov     [rcx], ax
0x14002a386  movzx   eax, dx
0x14002a389  neg     ax
0x14002a38c  movsx   edx, dx
0x14002a38f  mov     [rcx+2], ax
0x14002a393  movzx   eax, r12w
0x14002a397  neg     ax
0x14002a39a  mov     [rcx+4], ax
0x14002a39e  movzx   eax, [rbp+var_1E]
0x14002a3a2  neg     ax
0x14002a3a5  mov     [rcx+6], ax
0x14002a3a9  mov     rax, [rbp+arg_10]
0x14002a3ad  movsx   ecx, r8w
0x14002a3b1  mov     r8d, 1Fh
0x14002a3b7  sub     r12d, ecx
0x14002a3ba  neg     ecx
0x14002a3bc  shl     ecx, 6
0x14002a3bf  mov     [rax], r10d
0x14002a3c2  mov     r10d, [rbp+var_10]
0x14002a3c6  mov     [rax+4], ebx
0x14002a3c9  sub     r10d, edx
0x14002a3cc  mov     rbx, [rbp+arg_18]
0x14002a3d0  neg     edx
0x14002a3d2  shl     r10d, 6
0x14002a3d6  mov     eax, r10d
0x14002a3d9  shl     edx, 6
0x14002a3dc  sub     eax, r11d
0x14002a3df  shl     r12d, 6
0x14002a3e3  mov     [rbx], eax
0x14002a3e5  neg     r11d
0x14002a3e8  mov     eax, r12d
0x14002a3eb  sub     r10d, esi
0x14002a3ee  sub     eax, r15d
0x14002a3f1  sub     r12d, r9d
0x14002a3f4  mov     [rbx+4], eax
0x14002a3f7  neg     r9d
0x14002a3fa  mov     rax, [rbp+arg_20]
0x14002a3fe  mov     [rax+4], ecx
0x14002a401  lea     rcx, [rbp+var_10]
0x14002a405  mov     [rax], r11d
0x14002a408  mov     rax, [rbp+arg_28]
0x14002a40c  mov     dword ptr [rax], 0
0x14002a412  mov     [rax+4], r14d
0x14002a416  mov     rax, [rbp+arg_30]
0x14002a41a  mov     [rax], r10d
0x14002a41d  mov     [rax+4], r12d
0x14002a421  mov     rax, [rbp+arg_38]
0x14002a425  mov     [rax], edx
0x14002a427  lea     rdx, [rbp+var_14]
0x14002a42b  mov     [rax+4], r9d
0x14002a42f  movzx   eax, word ptr [r13+36h]
0x14002a434  mov     [rbp+var_10], eax
0x14002a437  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<int>(int)
0x14002a43c  lea     rdx, [rbp+var_10]
0x14002a440  mov     ecx, [rax]
  ... truncated ...
```
