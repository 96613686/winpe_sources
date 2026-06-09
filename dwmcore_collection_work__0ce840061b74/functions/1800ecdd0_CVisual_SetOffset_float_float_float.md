# CVisual::SetOffset(float,float,float)

- ea: `0x1800ecdd0`
- end: `0x1800ed2d4`
- name: `?SetOffset@CVisual@@QEAAXMMM@Z`
- size: `1284`
- prototype: `void __fastcall(CVisual *__hidden this, float, float, float)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800c69e0`
- `0x180191ca0`

## callees

- `0x18003cc50`
- `0x180042de0`
- `0x1800ecdd0`
- `0x1800ee320`
- `0x1800eefe8`
- `0x180200468`
- `0x180204100`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ecfb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ecfb0`
- `CoreMessaging!CoreUICallSend` at `0x1800ed22f`
- `CoreMessaging!CoreUICallSend` at `0x1800ed22f`

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
  v8 = detail::pointer_buffer_impl<CResource *,0>::last(v5);
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
    v16 = detail::pointer_buffer_impl<CResource *,0>::last(v12 + 32);
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
            v37 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, __int64, __int16, char *, int, _DWORD *))CoreUICallSend)(
                    v34,
                    v40,
                    2,
                    9,
                    3,
                    byte_1802D4ED5,
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
0x1800ecdd0  push    r14
0x1800ecdd2  sub     rsp, 0B0h
0x1800ecdd9  movss   xmm0, dword ptr [rcx+6Ch]
0x1800ecdde  mov     r14, rcx
0x1800ecde1  movaps  [rsp+0B8h+var_38], xmm6
0x1800ecde9  movaps  xmm6, xmm3
0x1800ecdec  movaps  [rsp+0B8h+var_48], xmm7
0x1800ecdf1  movaps  xmm7, xmm2
0x1800ecdf4  movaps  [rsp+0B8h+var_58], xmm8
0x1800ecdfa  movaps  xmm8, xmm1
0x1800ecdfe  ucomiss xmm0, xmm8
0x1800ece02  jp      short loc_1800ECE3B
0x1800ece04  jnz     short loc_1800ECE3B
0x1800ece06  movss   xmm0, dword ptr [rcx+70h]
0x1800ece0b  ucomiss xmm0, xmm7
0x1800ece0e  jp      short loc_1800ECE3B
0x1800ece10  jnz     short loc_1800ECE3B
0x1800ece12  movss   xmm0, dword ptr [rcx+74h]
0x1800ece17  ucomiss xmm0, xmm6
0x1800ece1a  jp      short loc_1800ECE3B
0x1800ece1c  jnz     short loc_1800ECE3B
0x1800ece1e  movaps  xmm6, [rsp+0B8h+var_38]
0x1800ece26  movaps  xmm7, [rsp+0B8h+var_48]
0x1800ece2b  movaps  xmm8, [rsp+0B8h+var_58]
0x1800ece31  add     rsp, 0B0h
0x1800ece38  pop     r14
0x1800ece3a  retn
0x1800ece3b  movss   dword ptr [rcx+6Ch], xmm8
0x1800ece41  movss   dword ptr [rcx+70h], xmm7
0x1800ece46  movss   dword ptr [rcx+74h], xmm6
0x1800ece4b  add     rcx, 20h ; ' '
0x1800ece4f  mov     [rsp+0B8h+arg_8], rbx
0x1800ece57  mov     rbx, [rcx]
0x1800ece5a  mov     rax, rbx
0x1800ece5d  and     eax, 3
0x1800ece60  jz      loc_1800ED0F9
0x1800ece66  sub     rax, 1
0x1800ece6a  jz      loc_1800ED0F0
0x1800ece70  sub     rax, 1
0x1800ece74  jnz     loc_1800ED0D7
0x1800ece7a  xor     ebx, ebx
0x1800ece7c  mov     [rsp+0B8h+arg_10], rbp
0x1800ece84  mov     [rsp+0B8h+var_10], rsi
0x1800ece8c  mov     [rsp+0B8h+var_18], rdi
0x1800ece94  mov     [rsp+0B8h+var_20], r12
0x1800ece9c  call    ?last@?$pointer_buffer_impl@PEAVCResource@@$0A@@detail@@QEBAPEAPEAVCResource@@XZ; detail::pointer_buffer_impl<CResource *,0>::last(void)
0x1800ecea1  lea     rsi, [r14+58h]
0x1800ecea5  mov     rdi, rax
0x1800ecea8  mov     rbp, rsi
0x1800eceab  cmp     rbx, rdi
0x1800eceae  jnz     loc_1800ED277
0x1800eceb4  mov     rax, [r14]
0x1800eceb7  mov     rcx, r14
0x1800eceba  mov     rax, [rax+0A0h]
0x1800ecec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecec6  or      byte ptr [r14+60h], 15h
0x1800ececb  mov     r12, rax
0x1800ecece  test    rax, rax
0x1800eced1  jz      loc_1800ED29E
0x1800eced7  inc     dword ptr [rax+1Ch]
0x1800eceda  mov     rsi, [rsi]
0x1800ecedd  mov     rax, r14
0x1800ecee0  mov     [rsp+0B8h+var_28], r15
0x1800ecee8  nop     dword ptr [rax+rax+00000000h]
0x1800ecef0  test    byte ptr [rax+66h], 20h
0x1800ecef4  jz      loc_1800ECFA3
0x1800ecefa  test    rsi, rsi
0x1800ecefd  jz      loc_1800ECFA3
0x1800ecf03  movzx   ecx, byte ptr [rsi+60h]
0x1800ecf07  mov     eax, ecx
0x1800ecf09  and     eax, 91h
0x1800ecf0e  cmp     al, 91h
0x1800ecf10  jz      loc_1800ECFA3
0x1800ecf16  or      cl, 91h
0x1800ecf19  mov     [rsi+60h], cl
0x1800ecf1c  lea     rcx, [rsi+20h]
0x1800ecf20  mov     rbx, [rcx]
0x1800ecf23  mov     rax, rbx
0x1800ecf26  and     eax, 3
0x1800ecf29  jz      short loc_1800ECF9E
0x1800ecf2b  sub     rax, 1
0x1800ecf2f  jz      short loc_1800ECF98
0x1800ecf31  sub     rax, 1
0x1800ecf35  jnz     short loc_1800ECF7F
0x1800ecf37  xor     ebx, ebx
0x1800ecf39  call    ?last@?$pointer_buffer_impl@PEAVCResource@@$0A@@detail@@QEBAPEAPEAVCResource@@XZ; detail::pointer_buffer_impl<CResource *,0>::last(void)
0x1800ecf3e  lea     r15, [rsi+58h]
0x1800ecf42  mov     rdi, rax
0x1800ecf45  mov     rbp, r15
0x1800ecf48  cmp     rbx, rdi
0x1800ecf4b  jnz     loc_1800ED137
0x1800ecf51  mov     rax, [rsi]
0x1800ecf54  mov     rcx, rsi
0x1800ecf57  mov     rax, [rax+0A0h]
0x1800ecf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf63  test    rax, rax
0x1800ecf66  jz      short loc_1800ECF74
0x1800ecf68  cmp     r12, rax
0x1800ecf6b  jnz     loc_1800ED0AD
0x1800ecf71  mov     r15, rbp
0x1800ecf74  mov     rax, rsi
0x1800ecf77  mov     rsi, [r15]
0x1800ecf7a  jmp     loc_1800ECEF0
0x1800ecf7f  cmp     rax, 1
0x1800ecf83  jz      short loc_1800ECF9E
0x1800ecf85  mov     rdx, [rsp+0B8h]; void *
0x1800ecf8d  mov     ecx, 8000FFFFh; int
0x1800ecf92  call    ModuleFailFastForHRESULT
0x1800ecf98  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ecf9c  jmp     short loc_1800ECF39
0x1800ecf9e  mov     rbx, rcx
0x1800ecfa1  jmp     short loc_1800ECF39
0x1800ecfa3  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800ecfaa  mov     ebx, [rax+1648h]
0x1800ecfb0  call    cs:__imp_GetCurrentThreadId
0x1800ecfb6  cmp     eax, ebx
0x1800ecfb8  jnz     loc_1800ED2A6
0x1800ecfbe  mov     qword ptr [r14+220h], 0
0x1800ecfc9  mov     rdx, [r14+0E0h]
0x1800ecfd0  cmp     dword ptr [rdx], 0
0x1800ecfd3  jge     short loc_1800ED012
0x1800ecfd5  mov     r8d, [rdx+4]
0x1800ecfd9  xor     ecx, ecx
0x1800ecfdb  test    r8d, r8d
0x1800ecfde  jz      loc_1800ED10C
0x1800ecfe4  cmp     byte ptr [rcx+rdx+8], 1
0x1800ecfe9  jnz     loc_1800ED101
0x1800ecfef  lea     rax, [r8+0Fh]
0x1800ecff3  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800ecff7  add     rax, rdx
0x1800ecffa  lea     rbx, [rax+rcx*8]
0x1800ecffe  mov     rbx, [rbx]
0x1800ed001  test    rbx, rbx
0x1800ed004  jz      short loc_1800ED012
0x1800ed006  mov     rdi, [rbx]
0x1800ed009  cmp     rdi, rbx
0x1800ed00c  jnz     loc_1800ED160
0x1800ed012  mov     byte ptr [r14+1C9h], 1
0x1800ed01a  mov     rdx, [r14+0E0h]
0x1800ed021  cmp     dword ptr [rdx], 0
0x1800ed024  jge     short loc_1800ED057
0x1800ed026  mov     r8d, [rdx+4]
0x1800ed02a  xor     ecx, ecx
0x1800ed02c  test    r8d, r8d
0x1800ed02f  jz      loc_1800ED127
0x1800ed035  cmp     byte ptr [rcx+rdx+8], 1
0x1800ed03a  jnz     loc_1800ED11C
0x1800ed040  lea     rax, [r8+0Fh]
0x1800ed044  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800ed048  add     rax, rdx
0x1800ed04b  lea     rax, [rax+rcx*8]
0x1800ed04f  mov     rax, [rax]
0x1800ed052  test    rax, rax
0x1800ed055  jnz     short loc_1800ED0BE
0x1800ed057  mov     rax, [r14+38h]
0x1800ed05b  test    rax, rax
0x1800ed05e  jnz     loc_1800ED17A
0x1800ed064  cmp     qword ptr [r14+30h], 0
0x1800ed069  jz      short loc_1800ED078
0x1800ed06b  mov     edx, 1Ch
0x1800ed070  mov     rcx, r14
0x1800ed073  call    ?InvalidateConsumingAnimationsInternal@CResource@@AEAAXUDCOMPOSITION_PROPERTY_ID@@@Z; CResource::InvalidateConsumingAnimationsInternal(DCOMPOSITION_PROPERTY_ID)
0x1800ed078  mov     r15, [rsp+0B8h+var_28]
0x1800ed080  mov     rdi, [rsp+0B8h+var_18]
0x1800ed088  mov     rsi, [rsp+0B8h+var_10]
0x1800ed090  mov     rbp, [rsp+0B8h+arg_10]
0x1800ed098  mov     r12, [rsp+0B8h+var_20]
0x1800ed0a0  mov     rbx, [rsp+0B8h+arg_8]
0x1800ed0a8  jmp     loc_1800ECE1E
0x1800ed0ad  inc     dword ptr [rax+18h]
0x1800ed0b0  mov     r12, rax
0x1800ed0b3  mov     rax, rsi
0x1800ed0b6  mov     rsi, [r15]
0x1800ed0b9  jmp     loc_1800ECEF0
0x1800ed0be  mov     rcx, [rax]
0x1800ed0c1  cmp     rcx, rax
0x1800ed0c4  jz      short loc_1800ED057
0x1800ed0c6  mov     byte ptr [rcx-0CFh], 1
0x1800ed0cd  mov     rcx, [rcx]
0x1800ed0d0  cmp     rcx, rax
0x1800ed0d3  jz      short loc_1800ED057
0x1800ed0d5  jmp     short loc_1800ED0C6
0x1800ed0d7  cmp     rax, 1
0x1800ed0db  jz      short loc_1800ED0F9
0x1800ed0dd  mov     rdx, [rsp+0B8h]; void *
0x1800ed0e5  mov     ecx, 8000FFFFh; int
0x1800ed0ea  call    ModuleFailFastForHRESULT
0x1800ed0f0  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ed0f4  jmp     loc_1800ECE7C
0x1800ed0f9  mov     rbx, rcx
0x1800ed0fc  jmp     loc_1800ECE7C
0x1800ed101  inc     ecx
0x1800ed103  cmp     ecx, r8d
0x1800ed106  jb      loc_1800ECFE4
0x1800ed10c  cmp     ecx, r8d
0x1800ed10f  jb      loc_1800ECFEF
0x1800ed115  xor     ebx, ebx
0x1800ed117  jmp     loc_1800ECFFE
0x1800ed11c  inc     ecx
0x1800ed11e  cmp     ecx, r8d
0x1800ed121  jb      loc_1800ED035
0x1800ed127  cmp     ecx, r8d
0x1800ed12a  jb      loc_1800ED040
0x1800ed130  xor     eax, eax
0x1800ed132  jmp     loc_1800ED04F
0x1800ed137  mov     rcx, [rbx]
0x1800ed13a  lea     rbp, [rsi+58h]
0x1800ed13e  cmp     rcx, [rbp+0]
0x1800ed142  jz      short loc_1800ED155
0x1800ed144  mov     rax, [rcx]
0x1800ed147  mov     r8, rsi
0x1800ed14a  xor     edx, edx
0x1800ed14c  mov     rax, [rax+50h]
0x1800ed150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed155  add     rbx, 8
0x1800ed159  jmp     loc_1800ECF48
0x1800ed160  lea     rcx, [rdi-158h]; this
0x1800ed167  call    ?InvalidateWorldTransform@CTreeData@@IEAAXXZ; CTreeData::InvalidateWorldTransform(void)
0x1800ed16c  mov     rdi, [rdi]
0x1800ed16f  cmp     rdi, rbx
0x1800ed172  jz      loc_1800ED012
0x1800ed178  jmp     short loc_1800ED160
0x1800ed17a  cmp     dword ptr [rax+7Ch], 0
0x1800ed17e  jz      loc_1800ED064
0x1800ed184  cmp     dword ptr [r14+48h], 0
0x1800ed189  jz      loc_1800ED064
0x1800ed18f  test    dword ptr [r14+4Ch], 10000000h
0x1800ed197  jz      loc_1800ED064
0x1800ed19d  mov     rax, [r14+18h]
0x1800ed1a1  mov     ebx, 9
0x1800ed1a6  mov     edx, ebx
0x1800ed1a8  mov     rcx, [rax+18F0h]
0x1800ed1af  mov     rax, [rcx]
0x1800ed1b2  mov     rax, [rax+48h]
0x1800ed1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed1bb  mov     r10, rax
0x1800ed1be  test    rax, rax
0x1800ed1c1  jz      loc_1800ED064
0x1800ed1c7  mov     rcx, [r14+38h]
0x1800ed1cb  test    rcx, rcx
0x1800ed1ce  jnz     loc_1800ED26F
0x1800ed1d4  xor     edx, edx
0x1800ed1d6  mov     eax, edx
0x1800ed1d8  mov     r9d, ebx
0x1800ed1db  mov     [rsp+0B8h+var_68], rax
0x1800ed1e0  lea     rdx, [rsp+0B8h+var_68]
0x1800ed1e5  mov     eax, [r14+48h]
0x1800ed1e9  mov     r8d, 2
0x1800ed1ef  mov     [rsp+0B8h+var_60], rax
0x1800ed1f4  mov     rcx, r10
0x1800ed1f7  lea     rax, [rsp+0B8h+var_78]
0x1800ed1fc  movss   [rsp+0B8h+var_78], xmm8
0x1800ed203  mov     [rsp+0B8h+var_80], rax
0x1800ed208  lea     rax, byte_1802D4ED5
0x1800ed20f  mov     [rsp+0B8h+var_88], 1Ch
0x1800ed217  mov     [rsp+0B8h+var_90], rax
0x1800ed21c  mov     word ptr [rsp+0B8h+var_98], 3
0x1800ed223  movss   [rsp+0B8h+var_74], xmm7
0x1800ed229  movss   [rsp+0B8h+var_70], xmm6
0x1800ed22f  call    cs:__imp_CoreUICallSend
0x1800ed235  xor     r9d, r9d
0x1800ed238  cmp     eax, 87B20805h
0x1800ed23d  cmovnz  r9d, eax; int
0x1800ed241  test    r9d, r9d
0x1800ed244  jns     loc_1800ED064
0x1800ed24a  mov     [rsp+0B8h+var_90], 0; void *
0x1800ed253  xor     r8d, r8d; unsigned int
0x1800ed256  xor     edx, edx; int *
0x1800ed258  mov     [rsp+0B8h+var_98], 155h; unsigned int
0x1800ed260  mov     ecx, 14h; unsigned int
0x1800ed265  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800ed26a  jmp     loc_1800ED064
0x1800ed26f  mov     edx, [rcx+7Ch]
0x1800ed272  jmp     loc_1800ED1D6
0x1800ed277  mov     rcx, [rbx]
0x1800ed27a  lea     rbp, [r14+58h]
0x1800ed27e  cmp     rcx, [rbp+0]
0x1800ed282  jz      short loc_1800ED295
0x1800ed284  mov     rax, [rcx]
0x1800ed287  mov     r8, r14
0x1800ed28a  xor     edx, edx
0x1800ed28c  mov     rax, [rax+50h]
0x1800ed290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed295  add     rbx, 8
0x1800ed299  jmp     loc_1800ECEAB
0x1800ed29e  mov     rsi, rbp
0x1800ed2a1  jmp     loc_1800ECEDA
0x1800ed2a6  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800ed2ad  cmp     byte ptr [rax+1942h], 0
0x1800ed2b4  jnz     loc_1800ECFBE
0x1800ed2ba  mov     rcx, [rsp+0B8h]; this
0x1800ed2c2  lea     r8, aOnecoreuapWind_203; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800ed2c9  mov     edx, 0E8h; void *
0x1800ed2ce  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
