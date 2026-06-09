# _SafeArrayDestroy(tagSAFEARRAY *,int)

- ea: `0x180020860`
- end: `0x180020eab`
- name: `?_SafeArrayDestroy@@YAJPEAUtagSAFEARRAY@@H@Z`
- size: `1611`
- prototype: `__int64 __fastcall(struct tagSAFEARRAY *, int)`
- caller_count: `19`
- callee_count: `12`
- tags: ``

## callers

- `0x1800078c0`
- `0x18001b890`
- `0x18001c260`
- `0x18001c7f0`
- `0x18001cfb0`
- `0x18001e030`
- `0x18001f470`
- `0x18001f6e0`
- `0x18001fdd0`
- `0x18001ffc0`
- `0x1800302d4`
- `0x18003b7dc`
- `0x180074290`
- `0x180075200`
- `0x1800758b0`
- `0x180096cc4`
- `0x180096eb4`
- `0x1800972dc`
- `0x18009b1d0`

## callees

- `0x1800039b8`
- `0x180020860`
- `0x1800214f0`
- `0x18002197c`
- `0x180021a54`
- `0x180021d20`
- `0x180021dc0`
- `0x180022068`
- `0x1800220c4`
- `0x18004e530`
- `0x18009b1d0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020971`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020986`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209df`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020d4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020d69`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020971`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020986`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209df`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020d4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020d69`

## pseudocode

```c
__int64 __fastcall _SafeArrayDestroy(unsigned __int64 cElements_high, int a2)
{
  struct tagSAFEARRAY *v2; // rbx
  USHORT v3; // r8
  struct tagSAFEARRAY **v4; // rdi
  USHORT v5; // si
  ULONG *v6; // r9
  unsigned int v7; // ebp
  SAFEARRAYBOUND *v8; // r11
  USHORT i; // r10
  ULONG cElements; // r15d
  int v11; // r15d
  unsigned int v12; // ebp
  USHORT fFeatures; // dx
  PVOID pvData; // rdi
  __int64 v15; // rcx
  _QWORD *v16; // rax
  USHORT v17; // ax
  _QWORD *Value; // rax
  USHORT v20; // r10
  ULONG *v21; // r11
  unsigned int v22; // ebp
  SAFEARRAYBOUND *v23; // rdi
  USHORT kk; // r9
  ULONG v25; // ecx
  unsigned int v26; // ecx
  int v27; // esi
  ULONG v28; // ecx
  OLECHAR **v29; // rdi
  __int64 v30; // rdx
  unsigned int v31; // r15d
  unsigned int v32; // esi
  OLECHAR *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // r15d
  unsigned int v37; // esi
  struct tagSAFEARRAY *v38; // rcx
  SAFEARRAYBOUND v39; // r12
  unsigned int v40; // esi
  __int64 v41; // r13
  SAFEARRAYBOUND v42; // r12
  unsigned int v43; // esi
  __int64 v44; // r13
  unsigned int jj; // esi
  VARIANTARG *v46; // rcx
  unsigned int m; // esi
  VARIANTARG *v48; // rcx
  unsigned int n; // esi
  unsigned int j; // esi
  SAFEARRAYBOUND v51; // rcx
  unsigned int ii; // esi
  unsigned int k; // esi
  unsigned int v54; // ecx

  v2 = (struct tagSAFEARRAY *)cElements_high;
  if ( !cElements_high )
    return 0;
  if ( !*(_DWORD *)(cElements_high + 8) )
  {
    v3 = *(_WORD *)(cElements_high + 2);
    if ( (v3 & 0x2000) == 0 )
    {
      v4 = *(struct tagSAFEARRAY ***)(cElements_high + 16);
      if ( !v4 )
        goto LABEL_24;
      v5 = *(_WORD *)cElements_high;
      v6 = (ULONG *)(cElements_high + 4);
      v7 = 0;
      if ( *(_WORD *)cElements_high )
      {
        v7 = *v6;
        v8 = (SAFEARRAYBOUND *)(cElements_high + 24);
        for ( i = 0; i < v5; ++i )
        {
          cElements = v8->cElements;
          cElements_high = HIWORD(v8->cElements);
          if ( HIWORD(v7) )
          {
            if ( HIWORD(v8->cElements) )
              goto LABEL_14;
            cElements_high = v7;
            LOWORD(v7) = v8->cElements;
          }
          else
          {
            if ( !HIWORD(v8->cElements) )
            {
              v7 = (unsigned __int16)cElements * (unsigned __int16)v7;
              goto LABEL_11;
            }
            cElements_high = cElements;
          }
          v11 = (unsigned __int16)v7;
          v12 = (unsigned __int16)v7 * WORD1(cElements_high);
          if ( HIWORD(v12)
            || (cElements_high = v11 * (unsigned int)(unsigned __int16)cElements_high,
                v7 = cElements_high + ((unsigned __int16)v12 << 16),
                v7 < (unsigned int)cElements_high) )
          {
LABEL_14:
            v7 = -1;
            break;
          }
LABEL_11:
          ++v8;
        }
      }
      if ( a2 )
      {
        cElements_high = *v6;
        if ( (_DWORD)cElements_high )
        {
          v35 = v7 % (unsigned int)cElements_high;
          v36 = v7 / (unsigned int)cElements_high;
          if ( (v3 & 0x100) != 0 )
          {
            v37 = 0;
            if ( v7 / (unsigned int)cElements_high )
            {
              do
              {
                v38 = *v4++;
                SysFreeString(&v38->cDims);
                ++v37;
              }
              while ( v37 < v36 );
            }
          }
          else if ( (v3 & 0x200) != 0 )
          {
            for ( j = 0; j < v36; ++j )
            {
              cElements_high = (unsigned __int64)*v4;
              if ( *v4 )
                (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)cElements_high + 16LL))(
                  cElements_high,
                  v35);
              ++v4;
            }
          }
          else if ( (v3 & 0x400) != 0 )
          {
            for ( k = 0; k < v36; ++k )
            {
              cElements_high = (unsigned __int64)*v4;
              if ( *v4 )
                (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)cElements_high + 16LL))(
                  cElements_high,
                  v35);
              ++v4;
            }
          }
          else if ( (v3 & 0x800) != 0 )
          {
            for ( m = 0; m < v36; ++m )
            {
              v48 = (VARIANTARG *)v4;
              v4 += 3;
              VariantClear(v48);
            }
          }
          else if ( (v3 & 0x20) != 0 )
          {
            v42 = v2[-1].rgsabound[0];
            if ( v42 )
            {
              v43 = 0;
              if ( v36 )
              {
                v44 = *v6;
                do
                {
                  (*(void (__fastcall **)(SAFEARRAYBOUND, struct tagSAFEARRAY **))(**(_QWORD **)&v42 + 32LL))(v42, v4);
                  v4 = (struct tagSAFEARRAY **)((char *)v4 + v44);
                  ++v43;
                }
                while ( v43 < v36 );
              }
            }
          }
        }
        if ( (v2->fFeatures & 2) != 0 )
          memset_0(v2->pvData, 0, v7);
      }
      fFeatures = v2->fFeatures;
      LOBYTE(cElements_high) = (fFeatures & 7) != 0;
      if ( ((unsigned __int8)cElements_high & ((fFeatures & 0x1000) == 0)) != 0 )
      {
LABEL_24:
        if ( (v2->fFeatures & 0x20) != 0 )
        {
          cElements_high = (unsigned __int64)v2[-1].rgsabound[0];
          if ( cElements_high )
          {
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)cElements_high + 16LL))(cElements_high);
            v2[-1].rgsabound[0] = 0;
          }
        }
        v17 = v2->fFeatures;
        if ( (v17 & 7) != 0 && (v17 & 0x1000) == 0
          || (unsigned int)RefCountMap<tagSAFEARRAY *>::Decrement(cElements_high, v2) )
        {
          return 0;
        }
        if ( !TlsGetValue(g_itlsAppData) )
        {
          if ( (int)InitAppData() < 0 )
            return 0;
          TlsGetValue(g_itlsAppData);
        }
        Value = TlsGetValue(g_itlsAppData);
        (*(void (__fastcall **)(_QWORD, PVOID *))(*(_QWORD *)*Value + 40LL))(*Value, &v2[-1].pvData);
        return 0;
      }
      if ( (fFeatures & 0x2000) != 0 )
      {
        v2->fFeatures = fFeatures & 0xDFFF;
        goto LABEL_23;
      }
      pvData = v2->pvData;
      if ( (unsigned int)RefCountMap<void *>::Get(cElements_high, pvData) )
        memset_0(pvData, 0, v7);
      if ( (unsigned int)RefCountMap<void *>::Decrement(v15, pvData) )
        goto LABEL_23;
      if ( !TlsGetValue(g_itlsAppData) )
      {
        if ( (int)InitAppData() < 0 )
          goto LABEL_23;
        TlsGetValue(g_itlsAppData);
      }
      v16 = TlsGetValue(g_itlsAppData);
      (*(void (__fastcall **)(_QWORD, PVOID))(*(_QWORD *)*v16 + 40LL))(*v16, pvData);
LABEL_23:
      v2->pvData = 0;
      goto LABEL_24;
    }
    v20 = *(_WORD *)cElements_high;
    v21 = (ULONG *)(cElements_high + 4);
    v22 = 0;
    if ( !*(_WORD *)cElements_high )
    {
LABEL_40:
      if ( a2 )
      {
        v28 = *v21;
        if ( *v21 )
        {
          v29 = (OLECHAR **)v2->pvData;
          if ( v29 )
          {
            v30 = v22 % v28;
            v31 = v22 / v28;
            if ( (v3 & 0x100) != 0 )
            {
              v32 = 0;
              if ( v22 / v28 )
              {
                do
                {
                  v33 = *v29++;
                  if ( v33 )
                    SysReleaseString(v33);
                  ++v32;
                }
                while ( v32 < v31 );
              }
            }
            else if ( (v3 & 0x200) != 0 )
            {
              for ( n = 0; n < v31; ++n )
              {
                if ( *v29 )
                  (*(void (__fastcall **)(OLECHAR *, __int64))(*(_QWORD *)*v29 + 16LL))(*v29, v30);
                ++v29;
              }
            }
            else if ( (v3 & 0x400) != 0 )
            {
              for ( ii = 0; ii < v31; ++ii )
              {
                if ( *v29 )
                  (*(void (__fastcall **)(OLECHAR *, __int64))(*(_QWORD *)*v29 + 16LL))(*v29, v30);
                ++v29;
              }
            }
            else if ( (v3 & 0x800) != 0 )
            {
              for ( jj = 0; jj < v31; ++jj )
              {
                v46 = (VARIANTARG *)v29;
                v29 += 3;
                VariantClear(v46);
              }
            }
            else if ( (v3 & 0x20) != 0 )
            {
              v39 = v2[-1].rgsabound[0];
              if ( v39 )
              {
                v40 = 0;
                if ( v31 )
                {
                  v41 = *v21;
                  do
                  {
                    (*(void (__fastcall **)(SAFEARRAYBOUND, OLECHAR **))(**(_QWORD **)&v39 + 32LL))(v39, v29);
                    v29 = (OLECHAR **)((char *)v29 + v41);
                    ++v40;
                  }
                  while ( v40 < v31 );
                }
              }
            }
          }
        }
      }
      if ( (v2->fFeatures & 0x20) != 0 )
      {
        v51 = v2[-1].rgsabound[0];
        if ( v51 )
        {
          (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v51 + 16LL))(v51);
          v2[-1].rgsabound[0] = 0;
        }
      }
      if ( (v2->fFeatures & 0x1002) == 2 )
      {
        memset_0(v2->pvData, 0, v22);
      }
      else
      {
        if ( (unsigned int)RefCountMap<tagSAFEARRAY *>::Get(4098, v2) )
          memset_0(v2->pvData, 0, v22);
        if ( !(unsigned int)RefCountMap<tagSAFEARRAY *>::Decrement(v34, v2) )
          _SafeArrayFreeData(&v2[-1].pvData);
      }
      return 0;
    }
    v22 = *v21;
    v23 = (SAFEARRAYBOUND *)(cElements_high + 24);
    for ( kk = 0; ; ++kk )
    {
      if ( kk >= v20 )
        goto LABEL_40;
      v25 = HIWORD(v23->cElements);
      if ( HIWORD(v22) )
      {
        if ( (_WORD)v25 )
          goto LABEL_39;
        v26 = v22;
        LOWORD(v22) = v23->cElements;
      }
      else
      {
        if ( !(_WORD)v25 )
        {
          v22 = (unsigned __int16)v23->cElements * (unsigned __int16)v22;
          goto LABEL_36;
        }
        v26 = v23->cElements;
      }
      v27 = (unsigned __int16)v22 * HIWORD(v26);
      if ( HIWORD(v27)
        || (v54 = (unsigned __int16)v22 * (unsigned __int16)v26, v22 = v54 + ((unsigned __int16)v27 << 16), v22 < v54) )
      {
LABEL_39:
        v22 = -1;
        goto LABEL_40;
      }
LABEL_36:
      ++v23;
    }
  }
  return 2147614733LL;
}

```

## disassembly

```asm
0x180020860  push    rbx
0x180020862  push    rbp
0x180020863  push    rsi
0x180020864  push    rdi
0x180020865  push    r12
0x180020867  push    r13
0x180020869  push    r14
0x18002086b  push    r15
0x18002086d  sub     rsp, 28h
0x180020871  mov     rbx, rcx
0x180020874  test    rcx, rcx
0x180020877  jz      loc_1800209F8
0x18002087d  cmp     dword ptr [rcx+8], 0
0x180020881  ja      loc_180020C58
0x180020887  movzx   r8d, word ptr [rcx+2]
0x18002088c  mov     r12d, 2000h
0x180020892  xor     r14d, r14d
0x180020895  test    r12w, r8w
0x180020899  jnz     loc_180020A0B
0x18002089f  mov     rdi, [rcx+10h]
0x1800208a3  test    rdi, rdi
0x1800208a6  jz      loc_1800209A2
0x1800208ac  movzx   esi, word ptr [rcx]
0x1800208af  lea     r9, [rcx+4]
0x1800208b3  mov     ebp, r14d
0x1800208b6  test    si, si
0x1800208b9  jz      short loc_18002091F
0x1800208bb  mov     ebp, [r9]
0x1800208be  lea     r11, [rcx+18h]
0x1800208c2  movzx   r10d, r14w
0x1800208c6  cmp     r10w, si
0x1800208ca  jnb     short loc_18002091F
0x1800208cc  mov     r15d, [r11]
0x1800208cf  mov     eax, ebp
0x1800208d1  mov     ecx, r15d
0x1800208d4  shr     eax, 10h
0x1800208d7  shr     ecx, 10h
0x1800208da  test    ax, ax
0x1800208dd  jnz     loc_180020E65
0x1800208e3  test    cx, cx
0x1800208e6  jnz     short loc_1800208FC
0x1800208e8  movzx   ebp, bp
0x1800208eb  movzx   eax, r15w
0x1800208ef  imul    ebp, eax
0x1800208f2  add     r11, 8
0x1800208f6  inc     r10w
0x1800208fa  jmp     short loc_1800208C6
0x1800208fc  mov     ecx, r15d
0x1800208ff  movzx   r15d, bp
0x180020903  mov     ebp, ecx
0x180020905  shr     ebp, 10h
0x180020908  imul    ebp, r15d
0x18002090c  mov     eax, ebp
0x18002090e  shr     eax, 10h
0x180020911  test    ax, ax
0x180020914  jz      loc_180020DBC
0x18002091a  mov     ebp, 0FFFFFFFFh
0x18002091f  test    edx, edx
0x180020921  jnz     loc_180020B18
0x180020927  movzx   edx, word ptr [rbx+2]
0x18002092b  mov     eax, 0Ch
0x180020930  test    dl, 7
0x180020933  setnz   cl
0x180020936  bt      dx, ax
0x18002093a  setnb   al
0x18002093d  test    al, cl
0x18002093f  jnz     short loc_1800209A2
0x180020941  test    r12w, dx
0x180020945  jnz     loc_180020E78
0x18002094b  mov     rdi, [rbx+10h]
0x18002094f  mov     rdx, rdi
0x180020952  call    ?Get@?$RefCountMap@PEAX@@QEAAHPEAX@Z; RefCountMap<void *>::Get(void *)
0x180020957  test    eax, eax
0x180020959  jnz     loc_180020E89
0x18002095f  mov     rdx, rdi
0x180020962  call    ?Decrement@?$RefCountMap@PEAX@@QEAAHPEAX@Z; RefCountMap<void *>::Decrement(void *)
0x180020967  test    eax, eax
0x180020969  jnz     short loc_18002099E
0x18002096b  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180020971  call    cs:__imp_TlsGetValue
0x180020977  test    rax, rax
0x18002097a  jz      loc_180020D56
0x180020980  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180020986  call    cs:__imp_TlsGetValue
0x18002098c  mov     rdx, rdi
0x18002098f  mov     rcx, [rax]
0x180020992  mov     rax, [rcx]
0x180020995  mov     rax, [rax+28h]
0x180020999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002099e  mov     [rbx+10h], r14
0x1800209a2  test    byte ptr [rbx+2], 20h
0x1800209a6  jnz     loc_180020C88
0x1800209ac  movzx   eax, word ptr [rbx+2]
0x1800209b0  test    al, 7
0x1800209b2  jnz     loc_180020E9B
0x1800209b8  mov     rdx, rbx
0x1800209bb  call    ?Decrement@?$RefCountMap@PEAUtagSAFEARRAY@@@@QEAAHPEAUtagSAFEARRAY@@@Z; RefCountMap<tagSAFEARRAY *>::Decrement(tagSAFEARRAY *)
0x1800209c0  test    eax, eax
0x1800209c2  jnz     short loc_1800209F8
0x1800209c4  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x1800209ca  call    cs:__imp_TlsGetValue
0x1800209d0  test    rax, rax
0x1800209d3  jz      loc_180020D38
0x1800209d9  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x1800209df  call    cs:__imp_TlsGetValue
0x1800209e5  lea     rdx, [rbx-10h]
0x1800209e9  mov     rcx, [rax]
0x1800209ec  mov     rax, [rcx]
0x1800209ef  mov     rax, [rax+28h]
0x1800209f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209f8  xor     eax, eax
0x1800209fa  add     rsp, 28h
0x1800209fe  pop     r15
0x180020a00  pop     r14
0x180020a02  pop     r13
0x180020a04  pop     r12
0x180020a06  pop     rdi
0x180020a07  pop     rsi
0x180020a08  pop     rbp
0x180020a09  pop     rbx
0x180020a0a  retn
0x180020a0b  movzx   r10d, word ptr [rcx]
0x180020a0f  lea     r11, [rcx+4]
0x180020a13  mov     ebp, r14d
0x180020a16  test    r10w, r10w
0x180020a1a  jz      short loc_180020A7A
0x180020a1c  mov     ebp, [r11]
0x180020a1f  lea     rdi, [rcx+18h]
0x180020a23  movzx   r9d, r14w
0x180020a27  cmp     r9w, r10w
0x180020a2b  jnb     short loc_180020A7A
0x180020a2d  mov     esi, [rdi]
0x180020a2f  mov     eax, ebp
0x180020a31  mov     ecx, esi
0x180020a33  shr     eax, 10h
0x180020a36  shr     ecx, 10h
0x180020a39  test    ax, ax
0x180020a3c  jnz     loc_180020E53
0x180020a42  test    cx, cx
0x180020a45  jnz     short loc_180020A5A
0x180020a47  movzx   ecx, si
0x180020a4a  movzx   ebp, bp
0x180020a4d  imul    ebp, ecx
0x180020a50  add     rdi, 8
0x180020a54  inc     r9w
0x180020a58  jmp     short loc_180020A27
0x180020a5a  mov     ecx, esi
0x180020a5c  mov     esi, ecx
0x180020a5e  movzx   ebp, bp
0x180020a61  shr     esi, 10h
0x180020a64  imul    esi, ebp
0x180020a67  mov     eax, esi
0x180020a69  shr     eax, 10h
0x180020a6c  test    ax, ax
0x180020a6f  jz      loc_180020E38
0x180020a75  mov     ebp, 0FFFFFFFFh
0x180020a7a  test    edx, edx
0x180020a7c  jz      short loc_180020AC3
0x180020a7e  mov     ecx, [r11]
0x180020a81  test    ecx, ecx
0x180020a83  jz      short loc_180020AC3
0x180020a85  mov     rdi, [rbx+10h]
0x180020a89  test    rdi, rdi
0x180020a8c  jz      short loc_180020AC3
0x180020a8e  xor     edx, edx
0x180020a90  mov     eax, ebp
0x180020a92  div     ecx
0x180020a94  bt      r8w, 8
0x180020a9a  mov     r15d, eax
0x180020a9d  jnb     loc_180020B70
0x180020aa3  mov     esi, r14d
0x180020aa6  test    eax, eax
0x180020aa8  jz      short loc_180020AC3
0x180020aaa  nop     word ptr [rax+rax+00h]
0x180020ab0  mov     rcx, [rdi]; bstrString
0x180020ab3  lea     rdi, [rdi+8]
0x180020ab7  test    rcx, rcx
0x180020aba  jnz     short loc_180020B11
0x180020abc  inc     esi
0x180020abe  cmp     esi, r15d
0x180020ac1  jb      short loc_180020AB0
0x180020ac3  test    byte ptr [rbx+2], 20h
0x180020ac7  jnz     loc_180020D87
0x180020acd  movzx   eax, word ptr [rbx+2]
0x180020ad1  mov     ecx, 1002h
0x180020ad6  and     ax, cx
0x180020ad9  cmp     ax, 2
0x180020add  jz      loc_180020DA9
0x180020ae3  mov     rdx, rbx
0x180020ae6  call    ?Get@?$RefCountMap@PEAUtagSAFEARRAY@@@@QEAAHPEAUtagSAFEARRAY@@@Z; RefCountMap<tagSAFEARRAY *>::Get(tagSAFEARRAY *)
0x180020aeb  test    eax, eax
0x180020aed  jnz     loc_180020D74
0x180020af3  mov     rdx, rbx
0x180020af6  call    ?Decrement@?$RefCountMap@PEAUtagSAFEARRAY@@@@QEAAHPEAUtagSAFEARRAY@@@Z; RefCountMap<tagSAFEARRAY *>::Decrement(tagSAFEARRAY *)
0x180020afb  test    eax, eax
0x180020afd  jnz     loc_1800209F8
0x180020b03  lea     rcx, [rbx-10h]; void *
0x180020b07  call    ?_SafeArrayFreeData@@YAXPEAX@Z; _SafeArrayFreeData(void *)
0x180020b0c  jmp     loc_1800209F8
0x180020b11  call    SysReleaseString
0x180020b16  jmp     short loc_180020ABC
0x180020b18  mov     ecx, [r9]
0x180020b1b  test    ecx, ecx
0x180020b1d  jz      short loc_180020B53
0x180020b1f  xor     edx, edx
0x180020b21  mov     eax, ebp
0x180020b23  div     ecx
0x180020b25  bt      r8w, 8
0x180020b2b  mov     r15d, eax
0x180020b2e  jnb     loc_180020BE2
0x180020b34  mov     esi, r14d
0x180020b37  test    eax, eax
0x180020b39  jz      short loc_180020B53
0x180020b3b  nop     dword ptr [rax+rax+00h]
0x180020b40  mov     rcx, [rdi]; bstrString
0x180020b43  lea     rdi, [rdi+8]
0x180020b47  call    SysFreeString
0x180020b4c  inc     esi
0x180020b4e  cmp     esi, r15d
0x180020b51  jb      short loc_180020B40
0x180020b53  test    byte ptr [rbx+2], 2
0x180020b57  jz      loc_180020927
0x180020b5d  mov     rcx, [rbx+10h]; void *
0x180020b61  xor     edx, edx; Val
0x180020b63  mov     r8d, ebp; Size
0x180020b66  call    memset_0
0x180020b6b  jmp     loc_180020927
0x180020b70  bt      r8w, 9
0x180020b76  jb      loc_180020CD8
0x180020b7c  bt      r8w, 0Ah
0x180020b82  jb      loc_180020DD8
0x180020b88  bt      r8w, 0Bh
0x180020b8e  jb      loc_180020C62
0x180020b94  test    r8b, 20h
0x180020b98  jz      loc_180020AC3
0x180020b9e  mov     r12, [rbx-8]
0x180020ba2  test    r12, r12
0x180020ba5  jz      loc_180020AC3
0x180020bab  mov     esi, r14d
0x180020bae  test    r15d, r15d
0x180020bb1  jz      loc_180020AC3
0x180020bb7  mov     r13, rcx
0x180020bba  nop     word ptr [rax+rax+00h]
0x180020bc0  mov     rax, [r12]
0x180020bc4  mov     rdx, rdi
0x180020bc7  mov     rcx, r12
0x180020bca  mov     rax, [rax+20h]
0x180020bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd3  add     rdi, r13
0x180020bd6  inc     esi
0x180020bd8  cmp     esi, r15d
0x180020bdb  jb      short loc_180020BC0
0x180020bdd  jmp     loc_180020AC3
0x180020be2  bt      r8w, 9
0x180020be8  jb      loc_180020D08
0x180020bee  bt      r8w, 0Ah
0x180020bf4  jb      loc_180020E08
0x180020bfa  bt      r8w, 0Bh
0x180020c00  jb      loc_180020CAA
0x180020c06  test    r8b, 20h
0x180020c0a  jz      loc_180020B53
0x180020c10  mov     r12, [rbx-8]
0x180020c14  test    r12, r12
0x180020c17  jz      short loc_180020C4D
0x180020c19  mov     esi, r14d
0x180020c1c  test    r15d, r15d
0x180020c1f  jz      short loc_180020C4D
0x180020c21  mov     r13, rcx
0x180020c24  nop     dword ptr [rax+00h]
0x180020c28  nop     dword ptr [rax+rax+00000000h]
0x180020c30  mov     rax, [r12]
0x180020c34  mov     rdx, rdi
0x180020c37  mov     rcx, r12
0x180020c3a  mov     rax, [rax+20h]
0x180020c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c43  add     rdi, r13
0x180020c46  inc     esi
0x180020c48  cmp     esi, r15d
0x180020c4b  jb      short loc_180020C30
0x180020c4d  mov     r12d, 2000h
0x180020c53  jmp     loc_180020B53
0x180020c58  mov     eax, 8002000Dh
0x180020c5d  jmp     loc_1800209FA
0x180020c62  mov     esi, r14d
0x180020c65  test    r15d, r15d
0x180020c68  jz      loc_180020AC3
0x180020c6e  xchg    ax, ax
0x180020c70  mov     rcx, rdi; pvarg
0x180020c73  add     rdi, 18h
0x180020c77  call    VariantClear
0x180020c7c  inc     esi
0x180020c7e  cmp     esi, r15d
0x180020c81  jb      short loc_180020C70
0x180020c83  jmp     loc_180020AC3
0x180020c88  mov     rcx, [rbx-8]
0x180020c8c  test    rcx, rcx
0x180020c8f  jz      loc_1800209AC
0x180020c95  mov     rax, [rcx]
0x180020c98  mov     rax, [rax+10h]
0x180020c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
