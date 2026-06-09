# CVisual::SetOffset(float,float,float)

- ea: `0x1800ea650`
- end: `0x1800eab54`
- name: `?SetOffset@CVisual@@QEAAXMMM@Z`
- size: `1284`
- prototype: `void __fastcall(CVisual *__hidden this, float, float, float)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800c4170`
- `0x180192cd0`

## callees

- `0x18004a0bc`
- `0x180050270`
- `0x1800ea650`
- `0x1800ebba0`
- `0x1800ec868`
- `0x180200488`
- `0x180204120`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ea830`
- `CoreMessaging!CoreUICallSend` at `0x1800eaaaf`
- `CoreMessaging!CoreUICallSend` at `0x1800eaaaf`

## pseudocode

```c
void __fastcall CVisual::SetOffset(CVisual *this, float a2, float a3, float a4)
{
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  _QWORD *v7; // rsi
  __int64 v8; // rdi
  char *v9; // rbp
  __int64 v10; // rax
  __int64 v11; // r12
  _BYTE *v12; // rsi
  CVisual *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // r15
  __int64 v16; // rdi
  _QWORD *v17; // rbp
  __int64 v18; // rax
  int v19; // ebx
  const char *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  _QWORD ***v24; // rbx
  _QWORD **v25; // rbx
  _QWORD *i; // rdi
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  _QWORD ***v30; // rax
  _QWORD **v31; // rax
  __int64 v32; // rax
  _QWORD *j; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // edx
  int v37; // eax
  int v38; // r9d
  _DWORD v39[4]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v40[2]; // [rsp+50h] [rbp-68h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+0h]

  if ( *((float *)this + 27) == a2 && *((float *)this + 28) == a3 && *((float *)this + 29) == a4 )
    return;
  *((float *)this + 27) = a2;
  *((float *)this + 28) = a3;
  *((float *)this + 29) = a4;
  v5 = (_QWORD *)((char *)this + 32);
  if ( (*v5 & 3) != 0 )
  {
    if ( (*v5 & 3LL) == 1 )
    {
      v6 = (_QWORD *)(*v5 & 0xFFFFFFFFFFFFFFFCuLL);
      goto LABEL_8;
    }
    if ( (*v5 & 3LL) == 2 )
    {
      v6 = 0;
      goto LABEL_8;
    }
    if ( (*v5 & 3LL) != 3 )
      ModuleFailFastForHRESULT(-2147418113, retaddr);
  }
  v6 = v5;
LABEL_8:
  v7 = (_QWORD *)((char *)this + 88);
  v8 = detail::pointer_buffer_impl<CResource *,0>::last();
  v9 = (char *)this + 88;
  while ( v6 != (_QWORD *)v8 )
  {
    v9 = (char *)this + 88;
    if ( *v6 != *((_QWORD *)this + 11) )
      (*(void (__fastcall **)(_QWORD, _QWORD, CVisual *))(*(_QWORD *)*v6 + 80LL))(*v6, 0, this);
    ++v6;
  }
  v10 = (*(__int64 (__fastcall **)(CVisual *))(*(_QWORD *)this + 160LL))(this);
  *((_BYTE *)this + 96) |= 0x15u;
  v11 = v10;
  if ( v10 )
    ++*(_DWORD *)(v10 + 28);
  else
    v7 = v9;
  v12 = (_BYTE *)*v7;
  v13 = this;
  while ( (*((_BYTE *)v13 + 102) & 0x20) != 0 && v12 && (v12[96] & 0x91) != 0x91 )
  {
    v12[96] |= 0x91u;
    if ( (*((_QWORD *)v12 + 4) & 3) != 0 )
    {
      if ( (*((_QWORD *)v12 + 4) & 3LL) == 1 )
      {
        v14 = (_QWORD *)(*((_QWORD *)v12 + 4) & 0xFFFFFFFFFFFFFFFCuLL);
        goto LABEL_20;
      }
      if ( (*((_QWORD *)v12 + 4) & 3LL) == 2 )
      {
        v14 = 0;
        goto LABEL_20;
      }
      if ( (*((_QWORD *)v12 + 4) & 3LL) != 3 )
        ModuleFailFastForHRESULT(-2147418113, retaddr);
    }
    v14 = v12 + 32;
LABEL_20:
    v15 = v12 + 88;
    v16 = detail::pointer_buffer_impl<CResource *,0>::last();
    v17 = v12 + 88;
    while ( v14 != (_QWORD *)v16 )
    {
      v17 = v12 + 88;
      if ( *v14 != *((_QWORD *)v12 + 11) )
        (*(void (__fastcall **)(_QWORD, _QWORD, _BYTE *))(*(_QWORD *)*v14 + 80LL))(*v14, 0, v12);
      ++v14;
    }
    v18 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 160LL))(v12);
    if ( v18 )
    {
      if ( v11 == v18 )
      {
        v15 = v17;
        goto LABEL_25;
      }
      ++*(_DWORD *)(v18 + 24);
      v11 = v18;
      v13 = (CVisual *)v12;
      v12 = (_BYTE *)*v15;
    }
    else
    {
LABEL_25:
      v13 = (CVisual *)v12;
      v12 = (_BYTE *)*v15;
    }
  }
  v19 = *((_DWORD *)g_pComposition + 1426);
  if ( GetCurrentThreadId() != v19 && !*((_BYTE *)g_pComposition + 6466) )
    wil::details::in1diag3::_FailFast_Unexpected(
      (wil::details::in1diag3 *)retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\treedata.cpp",
      v20);
  *((_QWORD *)this + 68) = 0;
  v21 = *((_QWORD *)this + 28);
  if ( *(int *)v21 < 0 )
  {
    v22 = *(unsigned int *)(v21 + 4);
    v23 = 0;
    if ( (_DWORD)v22 )
    {
      while ( *(_BYTE *)(v23 + v21 + 8) != 1 )
      {
        v23 = (unsigned int)(v23 + 1);
        if ( (unsigned int)v23 >= (unsigned int)v22 )
          goto LABEL_55;
      }
LABEL_34:
      v24 = (_QWORD ***)(v21 + ((v22 + 15) & 0xFFFFFFFFFFFFFFF8uLL) + 8 * v23);
    }
    else
    {
LABEL_55:
      if ( (unsigned int)v23 < (unsigned int)v22 )
        goto LABEL_34;
      v24 = 0;
    }
    v25 = *v24;
    if ( v25 )
    {
      for ( i = *v25; i != v25; i = (_QWORD *)*i )
        CTreeData::InvalidateWorldTransform((CTreeData *)(i - 43));
    }
  }
  *((_BYTE *)this + 457) = 1;
  v27 = *((_QWORD *)this + 28);
  if ( *(int *)v27 < 0 )
  {
    v28 = *(unsigned int *)(v27 + 4);
    v29 = 0;
    if ( (_DWORD)v28 )
    {
      while ( *(_BYTE *)(v29 + v27 + 8) != 1 )
      {
        v29 = (unsigned int)(v29 + 1);
        if ( (unsigned int)v29 >= (unsigned int)v28 )
          goto LABEL_58;
      }
LABEL_40:
      v30 = (_QWORD ***)(v27 + ((v28 + 15) & 0xFFFFFFFFFFFFFFF8uLL) + 8 * v29);
    }
    else
    {
LABEL_58:
      if ( (unsigned int)v29 < (unsigned int)v28 )
        goto LABEL_40;
      v30 = 0;
    }
    v31 = *v30;
    if ( v31 )
    {
      for ( j = *v31; j != v31; j = (_QWORD *)*j )
        *((_BYTE *)j - 207) = 1;
    }
  }
  v32 = *((_QWORD *)this + 7);
  if ( v32 )
  {
    if ( *(_DWORD *)(v32 + 124) )
    {
      if ( *((_DWORD *)this + 18) )
      {
        if ( (*((_DWORD *)this + 19) & 0x10000000) != 0 )
        {
          v34 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 3) + 6384LL) + 72LL))(
                  *(_QWORD *)(*((_QWORD *)this + 3) + 6384LL),
                  9);
          if ( v34 )
          {
            v35 = *((_QWORD *)this + 7);
            if ( v35 )
              v36 = *(_DWORD *)(v35 + 124);
            else
              v36 = 0;
            v40[0] = v36;
            v40[1] = *((unsigned int *)this + 18);
            *(float *)v39 = a2;
            *(float *)&v39[1] = a3;
            *(float *)&v39[2] = a4;
            v37 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, __int64, __int16, void *, int, _DWORD *))CoreUICallSend)(
                    v34,
                    v40,
                    2,
                    9,
                    3,
                    &unk_1802D2725,
                    28,
                    v39);
            v38 = 0;
            if ( v37 != -2018375675 )
              v38 = v37;
            if ( v38 < 0 )
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v38, 0x155u, 0);
          }
        }
      }
    }
  }
  if ( *((_QWORD *)this + 6) )
    CResource::InvalidateConsumingAnimationsInternal(this, 28);
}

```

## disassembly

```asm
0x1800ea650  push    r14
0x1800ea652  sub     rsp, 0B0h
0x1800ea659  movss   xmm0, dword ptr [rcx+6Ch]
0x1800ea65e  mov     r14, rcx
0x1800ea661  movaps  [rsp+0B8h+var_38], xmm6
0x1800ea669  movaps  xmm6, xmm3
0x1800ea66c  movaps  [rsp+0B8h+var_48], xmm7
0x1800ea671  movaps  xmm7, xmm2
0x1800ea674  movaps  [rsp+0B8h+var_58], xmm8
0x1800ea67a  movaps  xmm8, xmm1
0x1800ea67e  ucomiss xmm0, xmm8
0x1800ea682  jp      short loc_1800EA6BB
0x1800ea684  jnz     short loc_1800EA6BB
0x1800ea686  movss   xmm0, dword ptr [rcx+70h]
0x1800ea68b  ucomiss xmm0, xmm7
0x1800ea68e  jp      short loc_1800EA6BB
0x1800ea690  jnz     short loc_1800EA6BB
0x1800ea692  movss   xmm0, dword ptr [rcx+74h]
0x1800ea697  ucomiss xmm0, xmm6
0x1800ea69a  jp      short loc_1800EA6BB
0x1800ea69c  jnz     short loc_1800EA6BB
0x1800ea69e  movaps  xmm6, [rsp+0B8h+var_38]
0x1800ea6a6  movaps  xmm7, [rsp+0B8h+var_48]
0x1800ea6ab  movaps  xmm8, [rsp+0B8h+var_58]
0x1800ea6b1  add     rsp, 0B0h
0x1800ea6b8  pop     r14
0x1800ea6ba  retn
0x1800ea6bb  movss   dword ptr [rcx+6Ch], xmm8
0x1800ea6c1  movss   dword ptr [rcx+70h], xmm7
0x1800ea6c6  movss   dword ptr [rcx+74h], xmm6
0x1800ea6cb  add     rcx, 20h ; ' '
0x1800ea6cf  mov     [rsp+0B8h+arg_8], rbx
0x1800ea6d7  mov     rbx, [rcx]
0x1800ea6da  mov     rax, rbx
0x1800ea6dd  and     eax, 3
0x1800ea6e0  jz      loc_1800EA979
0x1800ea6e6  sub     rax, 1
0x1800ea6ea  jz      loc_1800EA970
0x1800ea6f0  sub     rax, 1
0x1800ea6f4  jnz     loc_1800EA957
0x1800ea6fa  xor     ebx, ebx
0x1800ea6fc  mov     [rsp+0B8h+arg_10], rbp
0x1800ea704  mov     [rsp+0B8h+var_10], rsi
0x1800ea70c  mov     [rsp+0B8h+var_18], rdi
0x1800ea714  mov     [rsp+0B8h+var_20], r12
0x1800ea71c  call    ?last@?$pointer_buffer_impl@PEAVCResource@@$0A@@detail@@QEBAPEAPEAVCResource@@XZ; detail::pointer_buffer_impl<CResource *,0>::last(void)
0x1800ea721  lea     rsi, [r14+58h]
0x1800ea725  mov     rdi, rax
0x1800ea728  mov     rbp, rsi
0x1800ea72b  cmp     rbx, rdi
0x1800ea72e  jnz     loc_1800EAAF7
0x1800ea734  mov     rax, [r14]
0x1800ea737  mov     rcx, r14
0x1800ea73a  mov     rax, [rax+0A0h]
0x1800ea741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea746  or      byte ptr [r14+60h], 15h
0x1800ea74b  mov     r12, rax
0x1800ea74e  test    rax, rax
0x1800ea751  jz      loc_1800EAB1E
0x1800ea757  inc     dword ptr [rax+1Ch]
0x1800ea75a  mov     rsi, [rsi]
0x1800ea75d  mov     rax, r14
0x1800ea760  mov     [rsp+0B8h+var_28], r15
0x1800ea768  nop     dword ptr [rax+rax+00000000h]
0x1800ea770  test    byte ptr [rax+66h], 20h
0x1800ea774  jz      loc_1800EA823
0x1800ea77a  test    rsi, rsi
0x1800ea77d  jz      loc_1800EA823
0x1800ea783  movzx   ecx, byte ptr [rsi+60h]
0x1800ea787  mov     eax, ecx
0x1800ea789  and     eax, 91h
0x1800ea78e  cmp     al, 91h
0x1800ea790  jz      loc_1800EA823
0x1800ea796  or      cl, 91h
0x1800ea799  mov     [rsi+60h], cl
0x1800ea79c  lea     rcx, [rsi+20h]
0x1800ea7a0  mov     rbx, [rcx]
0x1800ea7a3  mov     rax, rbx
0x1800ea7a6  and     eax, 3
0x1800ea7a9  jz      short loc_1800EA81E
0x1800ea7ab  sub     rax, 1
0x1800ea7af  jz      short loc_1800EA818
0x1800ea7b1  sub     rax, 1
0x1800ea7b5  jnz     short loc_1800EA7FF
0x1800ea7b7  xor     ebx, ebx
0x1800ea7b9  call    ?last@?$pointer_buffer_impl@PEAVCResource@@$0A@@detail@@QEBAPEAPEAVCResource@@XZ; detail::pointer_buffer_impl<CResource *,0>::last(void)
0x1800ea7be  lea     r15, [rsi+58h]
0x1800ea7c2  mov     rdi, rax
0x1800ea7c5  mov     rbp, r15
0x1800ea7c8  cmp     rbx, rdi
0x1800ea7cb  jnz     loc_1800EA9B7
0x1800ea7d1  mov     rax, [rsi]
0x1800ea7d4  mov     rcx, rsi
0x1800ea7d7  mov     rax, [rax+0A0h]
0x1800ea7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea7e3  test    rax, rax
0x1800ea7e6  jz      short loc_1800EA7F4
0x1800ea7e8  cmp     r12, rax
0x1800ea7eb  jnz     loc_1800EA92D
0x1800ea7f1  mov     r15, rbp
0x1800ea7f4  mov     rax, rsi
0x1800ea7f7  mov     rsi, [r15]
0x1800ea7fa  jmp     loc_1800EA770
0x1800ea7ff  cmp     rax, 1
0x1800ea803  jz      short loc_1800EA81E
0x1800ea805  mov     rdx, [rsp+0B8h]; void *
0x1800ea80d  mov     ecx, 8000FFFFh; int
0x1800ea812  call    ModuleFailFastForHRESULT
0x1800ea818  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ea81c  jmp     short loc_1800EA7B9
0x1800ea81e  mov     rbx, rcx
0x1800ea821  jmp     short loc_1800EA7B9
0x1800ea823  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800ea82a  mov     ebx, [rax+1648h]
0x1800ea830  call    cs:__imp_GetCurrentThreadId
0x1800ea836  cmp     eax, ebx
0x1800ea838  jnz     loc_1800EAB26
0x1800ea83e  mov     qword ptr [r14+220h], 0
0x1800ea849  mov     rdx, [r14+0E0h]
0x1800ea850  cmp     dword ptr [rdx], 0
0x1800ea853  jge     short loc_1800EA892
0x1800ea855  mov     r8d, [rdx+4]
0x1800ea859  xor     ecx, ecx
0x1800ea85b  test    r8d, r8d
0x1800ea85e  jz      loc_1800EA98C
0x1800ea864  cmp     byte ptr [rcx+rdx+8], 1
0x1800ea869  jnz     loc_1800EA981
0x1800ea86f  lea     rax, [r8+0Fh]
0x1800ea873  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800ea877  add     rax, rdx
0x1800ea87a  lea     rbx, [rax+rcx*8]
0x1800ea87e  mov     rbx, [rbx]
0x1800ea881  test    rbx, rbx
0x1800ea884  jz      short loc_1800EA892
0x1800ea886  mov     rdi, [rbx]
0x1800ea889  cmp     rdi, rbx
0x1800ea88c  jnz     loc_1800EA9E0
0x1800ea892  mov     byte ptr [r14+1C9h], 1
0x1800ea89a  mov     rdx, [r14+0E0h]
0x1800ea8a1  cmp     dword ptr [rdx], 0
0x1800ea8a4  jge     short loc_1800EA8D7
0x1800ea8a6  mov     r8d, [rdx+4]
0x1800ea8aa  xor     ecx, ecx
0x1800ea8ac  test    r8d, r8d
0x1800ea8af  jz      loc_1800EA9A7
0x1800ea8b5  cmp     byte ptr [rcx+rdx+8], 1
0x1800ea8ba  jnz     loc_1800EA99C
0x1800ea8c0  lea     rax, [r8+0Fh]
0x1800ea8c4  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800ea8c8  add     rax, rdx
0x1800ea8cb  lea     rax, [rax+rcx*8]
0x1800ea8cf  mov     rax, [rax]
0x1800ea8d2  test    rax, rax
0x1800ea8d5  jnz     short loc_1800EA93E
0x1800ea8d7  mov     rax, [r14+38h]
0x1800ea8db  test    rax, rax
0x1800ea8de  jnz     loc_1800EA9FA
0x1800ea8e4  cmp     qword ptr [r14+30h], 0
0x1800ea8e9  jz      short loc_1800EA8F8
0x1800ea8eb  mov     edx, 1Ch
0x1800ea8f0  mov     rcx, r14
0x1800ea8f3  call    ?InvalidateConsumingAnimationsInternal@CResource@@AEAAXUDCOMPOSITION_PROPERTY_ID@@@Z; CResource::InvalidateConsumingAnimationsInternal(DCOMPOSITION_PROPERTY_ID)
0x1800ea8f8  mov     r15, [rsp+0B8h+var_28]
0x1800ea900  mov     rdi, [rsp+0B8h+var_18]
0x1800ea908  mov     rsi, [rsp+0B8h+var_10]
0x1800ea910  mov     rbp, [rsp+0B8h+arg_10]
0x1800ea918  mov     r12, [rsp+0B8h+var_20]
0x1800ea920  mov     rbx, [rsp+0B8h+arg_8]
0x1800ea928  jmp     loc_1800EA69E
0x1800ea92d  inc     dword ptr [rax+18h]
0x1800ea930  mov     r12, rax
0x1800ea933  mov     rax, rsi
0x1800ea936  mov     rsi, [r15]
0x1800ea939  jmp     loc_1800EA770
0x1800ea93e  mov     rcx, [rax]
0x1800ea941  cmp     rcx, rax
0x1800ea944  jz      short loc_1800EA8D7
0x1800ea946  mov     byte ptr [rcx-0CFh], 1
0x1800ea94d  mov     rcx, [rcx]
0x1800ea950  cmp     rcx, rax
0x1800ea953  jz      short loc_1800EA8D7
0x1800ea955  jmp     short loc_1800EA946
0x1800ea957  cmp     rax, 1
0x1800ea95b  jz      short loc_1800EA979
0x1800ea95d  mov     rdx, [rsp+0B8h]; void *
0x1800ea965  mov     ecx, 8000FFFFh; int
0x1800ea96a  call    ModuleFailFastForHRESULT
0x1800ea970  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ea974  jmp     loc_1800EA6FC
0x1800ea979  mov     rbx, rcx
0x1800ea97c  jmp     loc_1800EA6FC
0x1800ea981  inc     ecx
0x1800ea983  cmp     ecx, r8d
0x1800ea986  jb      loc_1800EA864
0x1800ea98c  cmp     ecx, r8d
0x1800ea98f  jb      loc_1800EA86F
0x1800ea995  xor     ebx, ebx
0x1800ea997  jmp     loc_1800EA87E
0x1800ea99c  inc     ecx
0x1800ea99e  cmp     ecx, r8d
0x1800ea9a1  jb      loc_1800EA8B5
0x1800ea9a7  cmp     ecx, r8d
0x1800ea9aa  jb      loc_1800EA8C0
0x1800ea9b0  xor     eax, eax
0x1800ea9b2  jmp     loc_1800EA8CF
0x1800ea9b7  mov     rcx, [rbx]
0x1800ea9ba  lea     rbp, [rsi+58h]
0x1800ea9be  cmp     rcx, [rbp+0]
0x1800ea9c2  jz      short loc_1800EA9D5
0x1800ea9c4  mov     rax, [rcx]
0x1800ea9c7  mov     r8, rsi
0x1800ea9ca  xor     edx, edx
0x1800ea9cc  mov     rax, [rax+50h]
0x1800ea9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea9d5  add     rbx, 8
0x1800ea9d9  jmp     loc_1800EA7C8
0x1800ea9e0  lea     rcx, [rdi-158h]; this
0x1800ea9e7  call    ?InvalidateWorldTransform@CTreeData@@IEAAXXZ; CTreeData::InvalidateWorldTransform(void)
0x1800ea9ec  mov     rdi, [rdi]
0x1800ea9ef  cmp     rdi, rbx
0x1800ea9f2  jz      loc_1800EA892
0x1800ea9f8  jmp     short loc_1800EA9E0
0x1800ea9fa  cmp     dword ptr [rax+7Ch], 0
0x1800ea9fe  jz      loc_1800EA8E4
0x1800eaa04  cmp     dword ptr [r14+48h], 0
0x1800eaa09  jz      loc_1800EA8E4
0x1800eaa0f  test    dword ptr [r14+4Ch], 10000000h
0x1800eaa17  jz      loc_1800EA8E4
0x1800eaa1d  mov     rax, [r14+18h]
0x1800eaa21  mov     ebx, 9
0x1800eaa26  mov     edx, ebx
0x1800eaa28  mov     rcx, [rax+18F0h]
0x1800eaa2f  mov     rax, [rcx]
0x1800eaa32  mov     rax, [rax+48h]
0x1800eaa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eaa3b  mov     r10, rax
0x1800eaa3e  test    rax, rax
0x1800eaa41  jz      loc_1800EA8E4
0x1800eaa47  mov     rcx, [r14+38h]
0x1800eaa4b  test    rcx, rcx
0x1800eaa4e  jnz     loc_1800EAAEF
0x1800eaa54  xor     edx, edx
0x1800eaa56  mov     eax, edx
0x1800eaa58  mov     r9d, ebx
0x1800eaa5b  mov     [rsp+0B8h+var_68], rax
0x1800eaa60  lea     rdx, [rsp+0B8h+var_68]
0x1800eaa65  mov     eax, [r14+48h]
0x1800eaa69  mov     r8d, 2
0x1800eaa6f  mov     [rsp+0B8h+var_60], rax
0x1800eaa74  mov     rcx, r10
0x1800eaa77  lea     rax, [rsp+0B8h+var_78]
0x1800eaa7c  movss   [rsp+0B8h+var_78], xmm8
0x1800eaa83  mov     [rsp+0B8h+var_80], rax
0x1800eaa88  lea     rax, unk_1802D2725
0x1800eaa8f  mov     [rsp+0B8h+var_88], 1Ch
0x1800eaa97  mov     [rsp+0B8h+var_90], rax
0x1800eaa9c  mov     word ptr [rsp+0B8h+var_98], 3
0x1800eaaa3  movss   [rsp+0B8h+var_74], xmm7
0x1800eaaa9  movss   [rsp+0B8h+var_70], xmm6
0x1800eaaaf  call    cs:__imp_CoreUICallSend
0x1800eaab5  xor     r9d, r9d
0x1800eaab8  cmp     eax, 87B20805h
0x1800eaabd  cmovnz  r9d, eax; int
0x1800eaac1  test    r9d, r9d
0x1800eaac4  jns     loc_1800EA8E4
0x1800eaaca  mov     [rsp+0B8h+var_90], 0; void *
0x1800eaad3  xor     r8d, r8d; unsigned int
0x1800eaad6  xor     edx, edx; int *
0x1800eaad8  mov     [rsp+0B8h+var_98], 155h; unsigned int
0x1800eaae0  mov     ecx, 14h; unsigned int
0x1800eaae5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800eaaea  jmp     loc_1800EA8E4
0x1800eaaef  mov     edx, [rcx+7Ch]
0x1800eaaf2  jmp     loc_1800EAA56
0x1800eaaf7  mov     rcx, [rbx]
0x1800eaafa  lea     rbp, [r14+58h]
0x1800eaafe  cmp     rcx, [rbp+0]
0x1800eab02  jz      short loc_1800EAB15
0x1800eab04  mov     rax, [rcx]
0x1800eab07  mov     r8, r14
0x1800eab0a  xor     edx, edx
0x1800eab0c  mov     rax, [rax+50h]
0x1800eab10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eab15  add     rbx, 8
0x1800eab19  jmp     loc_1800EA72B
0x1800eab1e  mov     rsi, rbp
0x1800eab21  jmp     loc_1800EA75A
0x1800eab26  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800eab2d  cmp     byte ptr [rax+1942h], 0
0x1800eab34  jnz     loc_1800EA83E
0x1800eab3a  mov     rcx, [rsp+0B8h]; this
0x1800eab42  lea     r8, aOnecoreuapWind_203; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800eab49  mov     edx, 0E8h; void *
0x1800eab4e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
