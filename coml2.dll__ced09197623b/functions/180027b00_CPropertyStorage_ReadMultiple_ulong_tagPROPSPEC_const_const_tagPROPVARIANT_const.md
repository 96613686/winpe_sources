# CPropertyStorage::ReadMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT * const)

- ea: `0x180027b00`
- end: `0x180027eae`
- name: `?ReadMultiple@CPropertyStorage@@UEAAJKQEBUtagPROPSPEC@@QEAUtagPROPVARIANT@@@Z`
- size: `942`
- prototype: `__int64 __fastcall(CPropertyStorage *__hidden this, unsigned int, const struct tagPROPSPEC *const, struct tagPROPVARIANT *const)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180027b00`
- `0x180027eb4`
- `0x180027ee0`
- `0x180027f14`
- `0x180027f8c`
- `0x180027fc8`
- `0x180028d3c`
- `0x18003f834`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!FreePropVariantArrayWorker` at `0x180027e85`
- `api-ms-win-core-com-private-l1-1-0!FreePropVariantArrayWorker` at `0x180027e85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ea3`

## pseudocode

```c
__int64 __fastcall CPropertyStorage::ReadMultiple(
        struct CPropertySetStream **this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        struct tagPROPVARIANT *const a4)
{
  unsigned int v4; // r15d
  unsigned int *v5; // r14
  CPropertyStorage *v10; // rcx
  int v11; // ebx
  const struct tagPROPSPEC *v12; // r8
  CPropertyStorage *v13; // rcx
  __int64 v14; // r9
  unsigned int *v15; // r9
  int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // r12d
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r15
  LPVOID **v24; // rsi
  LPVOID *v25; // rcx
  unsigned int v26; // ecx
  LPVOID *v27; // rdx
  int vt; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  LPVOID *v33; // r15
  int v34; // eax
  unsigned int v35; // eax
  __int64 v36; // rsi
  __int64 v37; // rcx
  LARGE_INTEGER hVal; // rcx
  struct tagPROPVARIANT *v39; // [rsp+28h] [rbp-80h]
  unsigned int v40; // [rsp+40h] [rbp-68h]
  void *v41; // [rsp+48h] [rbp-60h] BYREF
  __int64 v42; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v43; // [rsp+B8h] [rbp+10h] BYREF

  v4 = 0;
  v42 = -1;
  v43 = 0;
  v5 = 0;
  v11 = CPropertyStorage::Validate((CPropertyStorage *)this);
  if ( v11 )
    goto LABEL_18;
  if ( !a2 )
    return 1;
  v11 = CPropertyStorage::ValidateRGPROPSPEC(v10, a2, v12);
  if ( v11 )
    goto LABEL_18;
  if ( !v14 )
  {
    v11 = -2147024809;
    goto LABEL_18;
  }
  v11 = CPropertyStorage::Lock(v13);
  if ( v11 < 0 )
    goto LABEL_18;
  if ( (unsigned int)CPropertyStorage::IsReverted((CPropertyStorage *)this) )
  {
    v11 = -2147286782;
    goto LABEL_17;
  }
  if ( ((_BYTE)this[14] & 1) != 0 )
  {
    v11 = -2147287035;
    goto LABEL_17;
  }
  if ( a2 == 1 )
  {
    v5 = (unsigned int *)&v42;
  }
  else
  {
    v21 = a2 + 1;
    if ( (unsigned int)v21 < a2 || (v20 = 4 * v21, v20 > 0xFFFFFFFF) )
    {
      v11 = -2147024362;
      goto LABEL_17;
    }
    v11 = 0;
    v5 = (unsigned int *)CoTaskMemAlloc((unsigned int)v20);
    if ( !v5 )
    {
      v11 = -2147024882;
      goto LABEL_17;
    }
  }
  v16 = PrQueryProperties(this[4], a2, a3, v15, v5, a4, &v43);
  if ( v16 < 0 )
  {
    v11 = DfpNtStatusToHResult(v16);
    goto LABEL_17;
  }
  v17 = v43;
  if ( !v43 )
    goto LABEL_21;
  v40 = 0;
  v18 = 0;
  while ( !v11 )
  {
    if ( v5[v18] == -1 )
      goto LABEL_15;
    v22 = v5[v18];
    v23 = v22;
    v24 = (LPVOID **)(&a4->decVal.Lo32 + 6 * v22);
    if ( (*((_BYTE *)this + 108) & 1) == 0 || (v27 = *v24) == 0 || !*(_WORD *)v27 )
    {
      v25 = *v24;
      if ( a4[v22].vt == 73 )
      {
        CoTaskMemFree(v25[2]);
        v25 = *v24;
      }
      CoTaskMemFree(v25);
      v26 = v43;
      *(_OWORD *)&a4[v23].vt = 0;
      a4[v23].bstrblobVal.pData = 0;
      v17 = v26 - 1;
      v43 = v17;
      goto LABEL_32;
    }
    vt = a4[v22].vt;
    v41 = 0;
    v29 = vt - 66;
    if ( !v29 )
      goto LABEL_46;
    v30 = v29 - 1;
    if ( !v30 )
      goto LABEL_50;
    v31 = v30 - 1;
    if ( !v31 )
      goto LABEL_46;
    v32 = v31 - 1;
    if ( !v32 )
    {
LABEL_50:
      LODWORD(v39) = 0;
      v34 = (*(__int64 (__fastcall **)(struct CPropertySetStream *, LPVOID *, _QWORD, _QWORD, _QWORD, struct tagPROPVARIANT *, void **))(*(_QWORD *)this[2] + 48LL))(
              this[2],
              v27,
              0,
              (_DWORD)this[14] & 0xFFFEEF8F | 0x10,
              0,
              v39,
              &v41);
      v33 = (LPVOID *)v24;
      goto LABEL_48;
    }
    if ( v32 != 4 )
    {
      v11 = -2147023537;
LABEL_54:
      v35 = v18;
      v4 = 0;
      v40 = v18;
      goto LABEL_56;
    }
    v33 = v27 + 2;
    if ( v27 == (LPVOID *)-16LL )
LABEL_46:
      v33 = (LPVOID *)(&a4->decVal.Lo32 + 6 * v22);
    v34 = (*(__int64 (__fastcall **)(struct CPropertySetStream *, LPVOID, _QWORD, _QWORD, _DWORD, void **))(*(_QWORD *)this[2] + 32LL))(
            this[2],
            *v33,
            0,
            (_DWORD)this[14] & 0xFFFEEF8F | 0x10,
            0,
            &v41);
LABEL_48:
    v11 = v34;
    if ( v34 )
    {
      if ( v34 != -2147287038 )
        goto LABEL_54;
    }
    else
    {
      CoTaskMemFree(*v33);
      *v33 = v41;
    }
    v17 = v43;
LABEL_32:
    ++v18;
    v4 = 0;
  }
  v35 = 0;
LABEL_56:
  if ( v35 )
  {
    do
    {
      v36 = v5[v4];
      if ( a4[v5[v4]].vt == 66 || a4[v5[v4]].vt == 67 || a4[v5[v4]].vt == 68 || a4[v5[v4]].vt == 69 )
      {
        hVal = a4[v5[v4]].hVal;
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)hVal.QuadPart + 16LL))(hVal);
      }
      else if ( a4[v5[v4]].vt == 73 )
      {
        v37 = *(_QWORD *)(a4[v5[v4]].hVal.QuadPart + 16);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        CoTaskMemFree(a4[v36].puuid);
      }
      ++v4;
      *(_OWORD *)&a4[v36].vt = 0;
      a4[v36].bstrblobVal.pData = 0;
    }
    while ( v4 < v40 );
  }
  FreePropVariantArrayWorker(a2, a4, 1);
  v17 = v43;
LABEL_21:
  if ( !v11 )
  {
LABEL_15:
    if ( !v17 )
      v11 = 1;
  }
LABEL_17:
  CPropertyStorage::Unlock((CPropertyStorage *)this);
LABEL_18:
  if ( a2 != 1 && v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180027b00  mov     rax, rsp
0x180027b03  push    rbx
0x180027b04  push    rbp
0x180027b05  push    rsi
0x180027b06  push    rdi
0x180027b07  push    r12
0x180027b09  push    r13
0x180027b0b  push    r14
0x180027b0d  push    r15
0x180027b0f  sub     rsp, 68h
0x180027b13  xor     r15d, r15d
0x180027b16  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFFh
0x180027b1e  mov     [rax+10h], r15d
0x180027b22  mov     r14d, r15d
0x180027b25  mov     rdi, r9
0x180027b28  mov     rsi, r8
0x180027b2b  mov     ebp, edx
0x180027b2d  mov     r13, rcx
0x180027b30  mov     r12d, 0FFFFFFFFh
0x180027b36  call    ?Validate@CPropertyStorage@@AEAAJXZ; CPropertyStorage::Validate(void)
0x180027b3b  mov     ebx, eax
0x180027b3d  test    eax, eax
0x180027b3f  jnz     loc_180027C04
0x180027b45  test    ebp, ebp
0x180027b47  jz      loc_180027CC4
0x180027b4d  mov     edx, ebp; unsigned int
0x180027b4f  call    ?ValidateRGPROPSPEC@CPropertyStorage@@AEAAJKQEBUtagPROPSPEC@@@Z; CPropertyStorage::ValidateRGPROPSPEC(ulong,tagPROPSPEC const * const)
0x180027b54  mov     ebx, eax
0x180027b56  test    eax, eax
0x180027b58  jnz     loc_180027C04
0x180027b5e  test    r9, r9
0x180027b61  jz      loc_180027CCE
0x180027b67  call    ?Lock@CPropertyStorage@@AEAAJXZ; CPropertyStorage::Lock(void)
0x180027b6c  mov     ebx, eax
0x180027b6e  test    eax, eax
0x180027b70  js      loc_180027C04
0x180027b76  mov     rcx, r13; this
0x180027b79  call    ?IsReverted@CPropertyStorage@@AEAAHXZ; CPropertyStorage::IsReverted(void)
0x180027b7e  test    eax, eax
0x180027b80  jnz     loc_180027CD8
0x180027b86  test    byte ptr [r13+70h], 1
0x180027b8b  jnz     loc_180027C20
0x180027b91  cmp     ebp, 1
0x180027b94  jnz     loc_180027C53
0x180027b9a  lea     r14, [rsp+0A8h+var_58]
0x180027b9f  mov     rcx, [r13+20h]; this
0x180027ba3  lea     rax, [rsp+0A8h+arg_8]
0x180027bab  mov     [rsp+0A8h+var_78], rax; unsigned int *
0x180027bb0  mov     r8, rsi; struct tagPROPSPEC *
0x180027bb3  mov     [rsp+0A8h+var_80], rdi; struct tagPROPVARIANT *
0x180027bb8  mov     edx, ebp; unsigned int
0x180027bba  mov     [rsp+0A8h+var_88], r14; unsigned int *
0x180027bbf  call    ?PrQueryProperties@@YAJPEAVCPropertySetStream@@KPEBUtagPROPSPEC@@PEAK2PEAUtagPROPVARIANT@@2@Z; PrQueryProperties(CPropertySetStream *,ulong,tagPROPSPEC const *,ulong *,ulong *,tagPROPVARIANT *,ulong *)
0x180027bc4  test    eax, eax
0x180027bc6  js      short loc_180027C34
0x180027bc8  mov     ecx, [rsp+0A8h+arg_8]
0x180027bcf  mov     [rsp+0A8h+arg_8], ecx
0x180027bd6  test    ecx, ecx
0x180027bd8  jz      short loc_180027C27
0x180027bda  mov     [rsp+0A8h+var_68], r15d
0x180027bdf  mov     r12d, r15d
0x180027be2  test    ebx, ebx
0x180027be4  jnz     loc_180027DFC
0x180027bea  mov     eax, r12d
0x180027bed  mov     edx, 0FFFFFFFFh
0x180027bf2  cmp     [r14+rax*4], edx
0x180027bf6  jnz     short loc_180027C5C
0x180027bf8  test    ecx, ecx
0x180027bfa  jz      short loc_180027C2D
0x180027bfc  mov     rcx, r13; this
0x180027bff  call    ?Unlock@CPropertyStorage@@AEAAJXZ; CPropertyStorage::Unlock(void)
0x180027c04  cmp     ebp, 1
0x180027c07  jnz     loc_180027E97
0x180027c0d  mov     eax, ebx
0x180027c0f  add     rsp, 68h
0x180027c13  pop     r15
0x180027c15  pop     r14
0x180027c17  pop     r13
0x180027c19  pop     r12
0x180027c1b  pop     rdi
0x180027c1c  pop     rsi
0x180027c1d  pop     rbp
0x180027c1e  pop     rbx
0x180027c1f  retn
0x180027c20  mov     ebx, 80030005h
0x180027c25  jmp     short loc_180027BFC
0x180027c27  test    ebx, ebx
0x180027c29  jz      short loc_180027BF8
0x180027c2b  jmp     short loc_180027BFC
0x180027c2d  mov     ebx, 1
0x180027c32  jmp     short loc_180027BFC
0x180027c34  mov     ecx, eax; int
0x180027c36  call    ?DfpNtStatusToHResult@@YAJJ@Z; DfpNtStatusToHResult(long)
0x180027c3b  mov     ebx, eax
0x180027c3d  jmp     short loc_180027BFC
0x180027c3f  shl     rax, 2
0x180027c43  cmp     rax, r12
0x180027c46  jbe     loc_180027CE2
0x180027c4c  mov     ebx, 80070216h
0x180027c51  jmp     short loc_180027BFC
0x180027c53  lea     eax, [rbp+1]
0x180027c56  cmp     eax, ebp
0x180027c58  jb      short loc_180027C4C
0x180027c5a  jmp     short loc_180027C3F
0x180027c5c  test    byte ptr [r13+6Ch], 1
0x180027c61  lea     rsi, [rdi+8]
0x180027c65  mov     eax, [r14+rax*4]
0x180027c69  lea     r15, [rax+rax*2]
0x180027c6d  lea     rsi, [rsi+r15*8]
0x180027c71  jnz     loc_180027D03
0x180027c77  cmp     word ptr [rdi+r15*8], 49h ; 'I'
0x180027c7d  mov     rcx, [rsi]
0x180027c80  jnz     short loc_180027C8F
0x180027c82  mov     rcx, [rcx+10h]; pv
0x180027c86  call    cs:__imp_CoTaskMemFree
0x180027c8c  mov     rcx, [rsi]; pv
0x180027c8f  call    cs:__imp_CoTaskMemFree
0x180027c95  mov     ecx, [rsp+0A8h+arg_8]
0x180027c9c  xor     eax, eax
0x180027c9e  xorps   xmm0, xmm0
0x180027ca1  movups  xmmword ptr [rdi+r15*8], xmm0
0x180027ca6  mov     [rdi+r15*8+10h], rax
0x180027cab  mov     eax, 0FFFFFFFFh
0x180027cb0  add     ecx, eax
0x180027cb2  mov     [rsp+0A8h+arg_8], ecx
0x180027cb9  inc     r12d
0x180027cbc  xor     r15d, r15d
0x180027cbf  jmp     loc_180027BE2
0x180027cc4  mov     ebx, 1
0x180027cc9  jmp     loc_180027C0D
0x180027cce  mov     ebx, 80070057h
0x180027cd3  jmp     loc_180027C04
0x180027cd8  mov     ebx, 80030102h
0x180027cdd  jmp     loc_180027BFC
0x180027ce2  mov     ecx, eax; cb
0x180027ce4  mov     ebx, r15d
0x180027ce7  call    cs:__imp_CoTaskMemAlloc
0x180027ced  mov     r14, rax
0x180027cf0  test    rax, rax
0x180027cf3  jnz     loc_180027B9F
0x180027cf9  mov     ebx, 8007000Eh
0x180027cfe  jmp     loc_180027BFC
0x180027d03  mov     rdx, [rsi]
0x180027d06  xor     r10d, r10d
0x180027d09  test    rdx, rdx
0x180027d0c  jz      loc_180027C77
0x180027d12  cmp     [rdx], r10w
0x180027d16  jz      loc_180027C77
0x180027d1c  movzx   ecx, word ptr [rdi+r15*8]
0x180027d21  mov     [rsp+0A8h+var_60], r10
0x180027d26  sub     ecx, 42h ; 'B'
0x180027d29  jz      short loc_180027D4C
0x180027d2b  sub     ecx, 1
0x180027d2e  jz      short loc_180027D9C
0x180027d30  sub     ecx, 1
0x180027d33  jz      short loc_180027D4C
0x180027d35  sub     ecx, 1
0x180027d38  jz      short loc_180027D9C
0x180027d3a  cmp     ecx, 4
0x180027d3d  jnz     loc_180027DEB
0x180027d43  lea     r15, [rdx+10h]
0x180027d47  test    r15, r15
0x180027d4a  jnz     short loc_180027D4F
0x180027d4c  mov     r15, rsi
0x180027d4f  mov     rcx, [r13+10h]
0x180027d53  lea     rdx, [rsp+0A8h+var_60]
0x180027d58  mov     r9d, [r13+70h]
0x180027d5c  xor     r8d, r8d
0x180027d5f  mov     [rsp+0A8h+var_80], rdx
0x180027d64  and     r9d, 0FFFEEF9Fh
0x180027d6b  mov     rdx, [r15]
0x180027d6e  or      r9d, 10h
0x180027d72  mov     rax, [rcx]
0x180027d75  mov     dword ptr [rsp+0A8h+var_88], r10d
0x180027d7a  mov     rax, [rax+20h]
0x180027d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d83  mov     ebx, eax
0x180027d85  test    eax, eax
0x180027d87  jnz     short loc_180027DD7
0x180027d89  mov     rcx, [r15]; pv
0x180027d8c  call    cs:__imp_CoTaskMemFree
0x180027d92  mov     rax, [rsp+0A8h+var_60]
0x180027d97  mov     [r15], rax
0x180027d9a  jmp     short loc_180027DDF
0x180027d9c  mov     rcx, [r13+10h]
0x180027da0  lea     r8, [rsp+0A8h+var_60]
0x180027da5  mov     r9d, [r13+70h]
0x180027da9  mov     [rsp+0A8h+var_78], r8
0x180027dae  and     r9d, 0FFFEEF9Fh
0x180027db5  mov     dword ptr [rsp+0A8h+var_80], r10d
0x180027dba  or      r9d, 10h
0x180027dbe  mov     rax, [rcx]
0x180027dc1  xor     r8d, r8d
0x180027dc4  mov     [rsp+0A8h+var_88], r10
0x180027dc9  mov     rax, [rax+30h]
0x180027dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd2  mov     r15, rsi
0x180027dd5  jmp     short loc_180027D83
0x180027dd7  cmp     ebx, 80030002h
0x180027ddd  jnz     short loc_180027DF0
0x180027ddf  mov     ecx, [rsp+0A8h+arg_8]
0x180027de6  jmp     loc_180027CB9
0x180027deb  mov     ebx, 8007054Fh
0x180027df0  mov     eax, r12d
0x180027df3  xor     r15d, r15d
0x180027df6  mov     [rsp+0A8h+var_68], eax
0x180027dfa  jmp     short loc_180027E00
0x180027dfc  mov     eax, [rsp+0A8h+var_68]
0x180027e00  test    eax, eax
0x180027e02  jz      short loc_180027E7A
0x180027e04  mov     r12d, [rsp+0A8h+var_68]
0x180027e09  mov     eax, r15d
0x180027e0c  mov     ecx, [r14+rax*4]
0x180027e10  lea     rsi, [rcx+rcx*2]
0x180027e14  movzx   ecx, word ptr [rdi+rsi*8]
0x180027e18  sub     ecx, 42h ; 'B'
0x180027e1b  jz      short loc_180027E53
0x180027e1d  sub     ecx, 1
0x180027e20  jz      short loc_180027E53
0x180027e22  sub     ecx, 1
0x180027e25  jz      short loc_180027E53
0x180027e27  sub     ecx, 1
0x180027e2a  jz      short loc_180027E53
0x180027e2c  cmp     ecx, 4
0x180027e2f  jnz     short loc_180027E64
0x180027e31  mov     rax, [rdi+rsi*8+8]
0x180027e36  mov     rcx, [rax+10h]
0x180027e3a  mov     rax, [rcx]
0x180027e3d  mov     rax, [rax+10h]
0x180027e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e46  mov     rcx, [rdi+rsi*8+8]; pv
0x180027e4b  call    cs:__imp_CoTaskMemFree
0x180027e51  jmp     short loc_180027E64
0x180027e53  mov     rcx, [rdi+rsi*8+8]
0x180027e58  mov     rax, [rcx]
0x180027e5b  mov     rax, [rax+10h]
0x180027e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e64  xor     eax, eax
0x180027e66  xorps   xmm0, xmm0
0x180027e69  inc     r15d
0x180027e6c  movups  xmmword ptr [rdi+rsi*8], xmm0
0x180027e70  mov     [rdi+rsi*8+10h], rax
0x180027e75  cmp     r15d, r12d
0x180027e78  jb      short loc_180027E09
0x180027e7a  mov     r8d, 1
0x180027e80  mov     rdx, rdi
0x180027e83  mov     ecx, ebp
0x180027e85  call    cs:__imp_FreePropVariantArrayWorker
0x180027e8b  mov     ecx, [rsp+0A8h+arg_8]
0x180027e92  jmp     loc_180027C27
0x180027e97  test    r14, r14
0x180027e9a  jz      loc_180027C0D
0x180027ea0  mov     rcx, r14; pv
0x180027ea3  call    cs:__imp_CoTaskMemFree
0x180027ea9  jmp     loc_180027C0D
```
