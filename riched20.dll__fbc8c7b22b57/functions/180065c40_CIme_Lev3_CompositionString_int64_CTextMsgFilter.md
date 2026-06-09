# CIme_Lev3::CompositionString(__int64,CTextMsgFilter &)

- ea: `0x180065c40`
- end: `0x1800665c9`
- name: `?CompositionString@CIme_Lev3@@UEAAJ_JAEAVCTextMsgFilter@@@Z`
- size: `2441`
- prototype: `int(CIme_Lev3 *__hidden this, __int64, struct CTextMsgFilter *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180065b60`

## callees

- `0x1800475e8`
- `0x18004d518`
- `0x180065848`
- `0x180065990`
- `0x180065c40`
- `0x180066898`
- `0x180067548`
- `0x180067920`
- `0x18009366c`
- `0x18009370c`
- `0x180093c00`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CIme_Lev3::CompositionString(CIme_Lev3 *this, __int64 a2, struct CTextMsgFilter *a3)
{
  _QWORD *v3; // r15
  struct CTextMsgFilter *v4; // rsi
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r13d
  int v12; // r14d
  int v13; // r9d
  unsigned int ImmContext; // r12d
  int CompositionStringInfo; // eax
  int v16; // ecx
  unsigned __int64 v17; // rcx
  int v18; // edx
  char v19; // r12
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // ecx
  __int64 v24; // rcx
  _DWORD *v25; // r12
  __int64 v26; // rcx
  char *v27; // rbx
  __int64 v28; // rcx
  char *v29; // r12
  int v30; // eax
  int v31; // r12d
  __int64 v32; // rcx
  int v33; // r13d
  CIme_Lev3 *v34; // rcx
  int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40[2]; // [rsp+70h] [rbp-90h] BYREF
  struct ITextFont *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int16 *v47; // [rsp+A0h] [rbp-60h]
  struct CTextMsgFilter *v48; // [rsp+A8h] [rbp-58h]
  unsigned __int8 v49[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v50[256]; // [rsp+1B0h] [rbp+B0h] BYREF

  v48 = a3;
  v3 = (_QWORD *)((char *)a3 + 120);
  v4 = a3;
  v45 = 0;
  *((_WORD *)this + 6) = 0;
  if ( *((_WORD *)this + 40) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 320LL))(*v3);
    *((_WORD *)this + 40) = 0;
  }
  if ( !a2 || (a2 & 0x800) != 0 )
  {
    v40[0] = 0;
    if ( a2 )
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, v40);
    v7 = *((_DWORD *)this + 11);
    if ( v7 )
    {
      v8 = *v3;
      v9 = *((unsigned int *)this + 10);
      v38 = 0;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 192LL))(
        v8,
        v9,
        (unsigned int)(v9 + v7),
        &v38);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      *((_DWORD *)this + 11) = 0;
    }
    v10 = *((_QWORD *)this + 4);
    v43 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 56LL))(v10, &v43);
    if ( v43 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 16) + 152LL))(*((_QWORD *)v4 + 16));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
      *((_QWORD *)v4 + 15),
      4284967302LL,
      0);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0xFFFFFFFFLL);
    CIme::CheckInsertResultString(a2, v4, 0);
    if ( a2 )
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)v4 + 15) + 152LL))(*((_QWORD *)v4 + 15), v40);
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)v4 + 16) + 112LL))(*((_QWORD *)v4 + 16), &v45);
    *((_DWORD *)this + 10) = v45;
    if ( *((_DWORD *)v4 + 6) == 949 )
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
        *((_QWORD *)v4 + 15),
        4284967301LL,
        0);
  }
  if ( (a2 & 0x18) == 0 )
    return 0;
  v11 = *((_DWORD *)this + 11);
  LODWORD(v41) = 0;
  v39 = 0;
  v12 = 0;
  LODWORD(v43) = 0;
  v40[0] = 0;
  v38 = 0;
  v46 = 0;
  v42 = 0;
  *((_DWORD *)this + 11) = 0;
  ImmContext = LocalGetImmContext(v4);
  if ( ImmContext )
  {
    CompositionStringInfo = CIme::GetCompositionStringInfo(
                              ImmContext,
                              8u,
                              v50,
                              v13,
                              v49,
                              256,
                              v40,
                              &v39,
                              *((_DWORD *)v4 + 6),
                              (*((unsigned __int16 *)v4 + 16) >> 1) & 1,
                              (*((unsigned __int16 *)v4 + 16) >> 6) & 1);
    v16 = 255;
    if ( CompositionStringInfo < 255 )
      v16 = CompositionStringInfo;
    *((_DWORD *)this + 11) = v16;
    v17 = v16;
    if ( v17 >= 256 )
      _report_rangecheckfailure();
    v50[v17] = 0;
    LocalReleaseImmContext(v4, ImmContext);
    v12 = v40[0];
    LODWORD(v41) = v39;
    LODWORD(v43) = v40[0];
  }
  v18 = *((_DWORD *)this + 11);
  v19 = 0;
  v47 = 0;
  if ( v18 )
  {
    v20 = *((_QWORD *)v4 + 15);
    v39 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v20 + 328LL))(
            v20,
            (unsigned int)(v18 - v11),
            &v39)
      && v39 > 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 15) + 344LL))(*((_QWORD *)v4 + 15));
      v21 = *((_DWORD *)this + 11);
      if ( v21 <= v39 )
        v22 = 0;
      else
        v22 = v21 - v39;
      *((_DWORD *)this + 11) = v22;
      if ( (unsigned __int64)(2LL * v22) >= 0x200 )
        _report_rangecheckfailure();
      v50[v22] = 0;
      if ( !v22 && *((_DWORD *)v4 + 6) == 949 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 240LL))(*((_QWORD *)v4 + 15), 0);
    }
    v47 = CW32System::SysAllocString(v50);
    if ( !v47 )
      return 2147942414LL;
    if ( (a2 & 0x800) != 0 )
    {
      *((_WORD *)this + 6) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v4 + 15) + 176LL))(
        *((_QWORD *)v4 + 15),
        4284967301LL,
        0);
      if ( (*((_BYTE *)v4 + 32) & 4) == 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
      v24 = *((_QWORD *)v4 + 16);
      *(_QWORD *)v40 = 0;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 144LL))(v24, v40);
      (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)v40 + 56LL))(*(_QWORD *)v40, (char *)this + 32);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
      CIme::CheckKeyboardFontMatching(*((_DWORD *)this + 10), v4, *((struct ITextFont **)this + 4));
    }
  }
  if ( v11 || *((_DWORD *)this + 11) )
  {
    if ( (*((_BYTE *)v4 + 32) & 4) == 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 15) + 280LL))(*((_QWORD *)v4 + 15), 0);
    if ( v11
      || *((_DWORD *)v4 + 6) != 949
      || (*((_BYTE *)v4 + 32) & 0x10) == 0
      || *((_WORD *)this + 8)
      || (*((_WORD *)v4 + 16) & 0x1000) != 0 )
    {
      v27 = (char *)this + 40;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)*v3 + 192LL))(
        *v3,
        *((unsigned int *)this + 10),
        (unsigned int)(*((_DWORD *)this + 10) + v11),
        &v38);
      if ( v11 )
      {
        if ( v12 )
        {
          (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, &v42);
          v19 = 1;
        }
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
      }
    }
    else
    {
      v26 = *v3;
      v40[0] = 0;
      v27 = (char *)this + 40;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v26 + 192LL))(
        v26,
        *((unsigned int *)this + 10),
        (unsigned int)(*((_DWORD *)this + 10) + 1),
        &v38);
      if ( !(*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 72LL))(v38, v40) )
      {
        if ( v40[0] == 13 || v40[0] == 10 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 224LL))(v38, *(unsigned int *)v27);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v3 + 176LL))(*v3, 4284967302LL, 0);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, 0);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v3 + 176LL))(*v3, 4284967301LL, 0);
        }
      }
    }
    *((_WORD *)this + 8) = 0;
    if ( v12 && !v19 )
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 144LL))(*v3, &v42);
    v28 = *((_QWORD *)this + 4);
    v44 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, &v44) && v44 )
    {
      if ( (*((_BYTE *)v4 + 32) & 8) != 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 16) + 152LL))(*((_QWORD *)v4 + 16));
        v29 = (char *)this + 40;
LABEL_68:
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v38 + 64LL))(v38, v47);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        else
          v27 = v29;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 128LL))(v38, &v46);
        v25 = (_DWORD *)((char *)v4 + 24);
        v30 = v46 - *(_DWORD *)v27;
        *((_DWORD *)this + 11) = v30;
        if ( *((_DWORD *)v4 + 6) == 949 )
        {
          v43 = 0;
          if ( v12 )
            (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 152LL))(*v3, &v42);
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, char *))(*(_QWORD *)v38 + 432LL))(
                 v38,
                 10,
                 &v43,
                 (char *)&v43 + 4) )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 448LL))(v38, 0);
          }
          (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)*v3 + 240LL))(*v3, *((_DWORD *)this + 11) != 0);
        }
        else if ( v30 && v30 <= (int)v41 && v30 > 0 )
        {
          v31 = 0;
          do
          {
            v32 = *((_QWORD *)this + 4);
            v41 = 0;
            if ( (*(unsigned int (__fastcall **)(__int64, struct ITextFont **))(*(_QWORD *)v32 + 56LL))(v32, &v41)
              || !v41 )
            {
              break;
            }
            ((void (__fastcall *)(struct ITextFont *, __int64))v41->lpVtbl->Reset)(v41, 4284967297LL);
            v33 = v31 + 1;
            v34 = (CIme_Lev3 *)v49[v31];
            if ( v31 + 1 < *((_DWORD *)this + 11) )
            {
              do
              {
                if ( (_BYTE)v34 != v49[v33] )
                  break;
                ++v33;
              }
              while ( v33 < *((_DWORD *)this + 11) );
              v4 = v48;
            }
            CIme_Lev3::SetCompositionStyle(v34, v4, v49[v31], v41);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v38 + 224LL))(
              v38,
              (unsigned int)(v31 + *(_DWORD *)v27),
              (unsigned int)(*(_DWORD *)v27 + v33));
            (*(void (__fastcall **)(__int64, struct ITextFont *))(*(_QWORD *)v38 + 152LL))(v38, v41);
            ((void (__fastcall *)(struct ITextFont *))v41->lpVtbl->Release)(v41);
            v31 = v33;
          }
          while ( v33 < *((_DWORD *)this + 11) );
          v12 = v43;
          v25 = (_DWORD *)((char *)v4 + 24);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        goto LABEL_90;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 152LL))(v38);
    }
    v29 = v27;
    goto LABEL_68;
  }
  v25 = (_DWORD *)((char *)v4 + 24);
  if ( *((_DWORD *)v4 + 6) != 949 )
    goto LABEL_91;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 15) + 352LL))(*((_QWORD *)v4 + 15), 0xFFFFFFFFLL);
LABEL_90:
  if ( *v25 == 949 )
    goto LABEL_102;
LABEL_91:
  if ( v12 > 0 )
  {
    v35 = *((_DWORD *)this + 11);
    if ( v12 < v35 )
      v35 = v12;
    v12 = v35 + *((_DWORD *)this + 10);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 16) + 224LL))(
      *((_QWORD *)v4 + 16),
      (unsigned int)v12,
      (unsigned int)v12);
    goto LABEL_100;
  }
  if ( v12 )
  {
LABEL_101:
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 152LL))(*v3, &v42);
    goto LABEL_102;
  }
  v36 = *v3;
  v37 = *((unsigned int *)this + 10);
  v44 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 192LL))(
          v36,
          v37,
          (unsigned int)(v37 + 1),
          &v38) )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, char *))(*(_QWORD *)v38 + 432LL))(
           v38,
           32,
           &v44,
           (char *)&v44 + 4) )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 448LL))(v38, 32);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_100:
    if ( v12 )
      goto LABEL_101;
  }
LABEL_102:
  if ( v47 )
    CW32System::SysFreeString(v47);
  if ( *v25 == 950 || *v25 == 936 )
    (*(void (__fastcall **)(CIme_Lev3 *, __int64, __int64, struct CTextMsgFilter *, int))(*(_QWORD *)this + 32LL))(
      this,
      5,
      1,
      v4,
      1);
  return 0;
}

```

## disassembly

```asm
0x180065c40  mov     [rsp-8+arg_8], rbx
0x180065c45  push    rbp
0x180065c46  push    rsi
0x180065c47  push    rdi
0x180065c48  push    r12
0x180065c4a  push    r13
0x180065c4c  push    r14
0x180065c4e  push    r15
0x180065c50  lea     rbp, [rsp-2C0h]
0x180065c58  sub     rsp, 3C0h
0x180065c5f  mov     rax, cs:__security_cookie
0x180065c66  xor     rax, rsp
0x180065c69  mov     [rbp+2F0h+var_40], rax
0x180065c70  xor     r12d, r12d
0x180065c73  mov     [rbp+2F0h+var_348], r8
0x180065c77  lea     r15, [r8+78h]
0x180065c7b  mov     rsi, r8
0x180065c7e  mov     rbx, rdx
0x180065c81  mov     rdi, rcx
0x180065c84  mov     [rbp+2F0h+var_358], r12d
0x180065c88  mov     [rcx+0Ch], r12w
0x180065c8d  cmp     [rcx+50h], r12w
0x180065c92  jz      short loc_180065CAB
0x180065c94  mov     rcx, [r15]
0x180065c97  mov     rax, [rcx]
0x180065c9a  mov     rax, [rax+140h]
0x180065ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ca6  mov     [rdi+50h], r12w
0x180065cab  test    rbx, rbx
0x180065cae  jz      short loc_180065CBB
0x180065cb0  bt      rbx, 0Bh
0x180065cb5  jnb     loc_180065E13
0x180065cbb  mov     [rsp+3F0h+var_380], r12d
0x180065cc0  test    rbx, rbx
0x180065cc3  jz      short loc_180065CDC
0x180065cc5  mov     rcx, [r15]
0x180065cc8  lea     rdx, [rsp+3F0h+var_380]
0x180065ccd  mov     rax, [rcx]
0x180065cd0  mov     rax, [rax+90h]
0x180065cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cdc  mov     r8d, [rdi+2Ch]
0x180065ce0  test    r8d, r8d
0x180065ce3  jz      short loc_180065D2F
0x180065ce5  mov     rcx, [r15]
0x180065ce8  lea     r9, [rsp+3F0h+var_390]
0x180065ced  mov     edx, [rdi+28h]
0x180065cf0  add     r8d, edx
0x180065cf3  mov     [rsp+3F0h+var_390], r12
0x180065cf8  mov     rax, [rcx]
0x180065cfb  mov     rax, [rax+0C0h]
0x180065d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d07  mov     rcx, [rsp+3F0h+var_390]
0x180065d0c  xor     edx, edx
0x180065d0e  mov     rax, [rcx]
0x180065d11  mov     rax, [rax+40h]
0x180065d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d1a  mov     rcx, [rsp+3F0h+var_390]
0x180065d1f  mov     rax, [rcx]
0x180065d22  mov     rax, [rax+10h]
0x180065d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d2b  mov     [rdi+2Ch], r12d
0x180065d2f  mov     rcx, [rdi+20h]
0x180065d33  lea     rdx, [rbp+2F0h+var_368]
0x180065d37  mov     [rbp+2F0h+var_368], r12
0x180065d3b  mov     rax, [rcx]
0x180065d3e  mov     rax, [rax+38h]
0x180065d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d47  mov     rdx, [rbp+2F0h+var_368]
0x180065d4b  test    rdx, rdx
0x180065d4e  jz      short loc_180065D76
0x180065d50  mov     rcx, [rsi+80h]
0x180065d57  mov     rax, [rcx]
0x180065d5a  mov     rax, [rax+98h]
0x180065d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d66  mov     rcx, [rbp+2F0h+var_368]
0x180065d6a  mov     rax, [rcx]
0x180065d6d  mov     rax, [rax+10h]
0x180065d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d76  mov     rcx, [rsi+78h]
0x180065d7a  xor     r8d, r8d
0x180065d7d  mov     edx, 0FF676986h
0x180065d82  mov     rax, [rcx]
0x180065d85  mov     rax, [rax+0B0h]
0x180065d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d91  mov     rcx, [rsi+78h]
0x180065d95  or      edx, 0FFFFFFFFh
0x180065d98  mov     rax, [rcx]
0x180065d9b  mov     rax, [rax+118h]
0x180065da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065da7  xor     r8d, r8d; __int16 *
0x180065daa  mov     rdx, rsi; struct CTextMsgFilter *
0x180065dad  mov     rcx, rbx; __int64
0x180065db0  call    ?CheckInsertResultString@CIme@@KAJ_JAEAVCTextMsgFilter@@PEAF@Z; CIme::CheckInsertResultString(__int64,CTextMsgFilter &,short *)
0x180065db5  test    rbx, rbx
0x180065db8  jz      short loc_180065DD2
0x180065dba  mov     rcx, [rsi+78h]
0x180065dbe  lea     rdx, [rsp+3F0h+var_380]
0x180065dc3  mov     rax, [rcx]
0x180065dc6  mov     rax, [rax+98h]
0x180065dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065dd2  mov     rcx, [rsi+80h]
0x180065dd9  lea     rdx, [rbp+2F0h+var_358]
0x180065ddd  mov     rax, [rcx]
0x180065de0  mov     rax, [rax+70h]
0x180065de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065de9  mov     eax, [rbp+2F0h+var_358]
0x180065dec  mov     [rdi+28h], eax
0x180065def  cmp     dword ptr [rsi+18h], 3B5h
0x180065df6  jnz     short loc_180065E13
0x180065df8  mov     rcx, [rsi+78h]
0x180065dfc  xor     r8d, r8d
0x180065dff  mov     edx, 0FF676985h
0x180065e04  mov     rax, [rcx]
0x180065e07  mov     rax, [rax+0B0h]
0x180065e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e13  test    bl, 18h
0x180065e16  jz      loc_18006659C
0x180065e1c  mov     r13d, [rdi+2Ch]
0x180065e20  mov     eax, r12d
0x180065e23  mov     rcx, rsi; struct CTextMsgFilter *
0x180065e26  mov     dword ptr [rsp+3F0h+var_378], eax
0x180065e2a  mov     [rsp+3F0h+var_388], eax
0x180065e2e  mov     r14d, r12d
0x180065e31  mov     dword ptr [rbp+2F0h+var_368], r12d
0x180065e35  mov     [rsp+3F0h+var_380], r12d
0x180065e3a  mov     [rsp+3F0h+var_390], r12
0x180065e3f  mov     [rbp+2F0h+var_354], r12d
0x180065e43  mov     [rbp+2F0h+var_370], r12d
0x180065e47  mov     [rdi+2Ch], r12d
0x180065e4b  call    ?LocalGetImmContext@@YAKAEAVCTextMsgFilter@@@Z; LocalGetImmContext(CTextMsgFilter &)
0x180065e50  mov     r12d, eax
0x180065e53  mov     eax, 1
0x180065e58  test    r12d, r12d
0x180065e5b  jz      loc_180065EFF
0x180065e61  movzx   edx, word ptr [rsi+20h]
0x180065e65  lea     r8, [rbp+2F0h+var_240]; unsigned __int16 *
0x180065e6c  mov     ecx, edx
0x180065e6e  shr     edx, 1
0x180065e70  and     edx, eax
0x180065e72  shr     ecx, 6
0x180065e75  and     ecx, eax
0x180065e77  mov     eax, [rsi+18h]
0x180065e7a  mov     [rsp+3F0h+var_3A0], ecx; int
0x180065e7e  mov     ecx, r12d; unsigned int
0x180065e81  mov     [rsp+3F0h+var_3A8], edx; int
0x180065e85  mov     edx, 8; unsigned int
0x180065e8a  mov     [rsp+3F0h+var_3B0], eax; unsigned int
0x180065e8e  lea     rax, [rsp+3F0h+var_388]
0x180065e93  mov     [rsp+3F0h+var_3B8], rax; int *
0x180065e98  lea     rax, [rsp+3F0h+var_380]
0x180065e9d  mov     [rsp+3F0h+var_3C0], rax; int *
0x180065ea2  lea     rax, [rbp+2F0h+var_340]
0x180065ea6  mov     [rsp+3F0h+var_3C8], 100h; int
0x180065eae  mov     [rsp+3F0h+var_3D0], rax; unsigned __int8 *
0x180065eb3  call    ?GetCompositionStringInfo@CIme@@KAHKKPEAGHPEAEHPEAJ2IHH@Z; CIme::GetCompositionStringInfo(ulong,ulong,ushort *,int,uchar *,int,long *,long *,uint,int,int)
0x180065eb8  mov     ecx, 0FFh
0x180065ebd  cmp     eax, ecx
0x180065ebf  cmovl   ecx, eax
0x180065ec2  movsxd  rax, ecx
0x180065ec5  mov     [rdi+2Ch], ecx
0x180065ec8  lea     rcx, [rax+rax]
0x180065ecc  cmp     rcx, 200h
0x180065ed3  jnb     loc_180065F5E
0x180065ed9  xor     eax, eax
0x180065edb  mov     edx, r12d; unsigned int
0x180065ede  mov     [rbp+rcx+2F0h+var_240], ax
0x180065ee6  mov     rcx, rsi; struct CTextMsgFilter *
0x180065ee9  call    ?LocalReleaseImmContext@@YAXAEAVCTextMsgFilter@@K@Z; LocalReleaseImmContext(CTextMsgFilter &,ulong)
0x180065eee  mov     eax, [rsp+3F0h+var_388]
0x180065ef2  mov     r14d, [rsp+3F0h+var_380]
0x180065ef7  mov     dword ptr [rsp+3F0h+var_378], eax
0x180065efb  mov     dword ptr [rbp+2F0h+var_368], r14d
0x180065eff  mov     edx, [rdi+2Ch]
0x180065f02  xor     r12d, r12d
0x180065f05  mov     [rbp+2F0h+var_350], r12
0x180065f09  test    edx, edx
0x180065f0b  jz      loc_180066077
0x180065f11  mov     rcx, [rsi+78h]
0x180065f15  lea     r8, [rsp+3F0h+var_388]
0x180065f1a  mov     [rsp+3F0h+var_388], r12d
0x180065f1f  sub     edx, r13d
0x180065f22  mov     rax, [rcx]
0x180065f25  mov     rax, [rax+148h]
0x180065f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f31  test    eax, eax
0x180065f33  jnz     short loc_180065FA5
0x180065f35  cmp     [rsp+3F0h+var_388], r12d
0x180065f3a  jle     short loc_180065FA5
0x180065f3c  mov     rcx, [rsi+78h]
0x180065f40  mov     rax, [rcx]
0x180065f43  mov     rax, [rax+158h]
0x180065f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f4f  mov     ecx, [rdi+2Ch]
0x180065f52  cmp     ecx, [rsp+3F0h+var_388]
0x180065f56  jle     short loc_180065F64
0x180065f58  sub     ecx, [rsp+3F0h+var_388]
0x180065f5c  jmp     short loc_180065F67
0x180065f5e  call    __report_rangecheckfailure
0x180065f64  mov     ecx, r12d
0x180065f67  movsxd  rax, ecx
0x180065f6a  mov     [rdi+2Ch], ecx
0x180065f6d  lea     rdx, [rax+rax]
0x180065f71  cmp     rdx, 200h
0x180065f78  jnb     short loc_180065FC4
0x180065f7a  mov     [rbp+rdx+2F0h+var_240], r12w
0x180065f83  test    ecx, ecx
0x180065f85  jnz     short loc_180065FA5
0x180065f87  cmp     dword ptr [rsi+18h], 3B5h
0x180065f8e  jnz     short loc_180065FA5
0x180065f90  mov     rcx, [rsi+78h]
0x180065f94  xor     edx, edx
0x180065f96  mov     rax, [rcx]
0x180065f99  mov     rax, [rax+0F0h]
0x180065fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fa5  lea     rcx, [rbp+2F0h+var_240]; unsigned __int16 *
0x180065fac  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x180065fb1  mov     [rbp+2F0h+var_350], rax
0x180065fb5  test    rax, rax
0x180065fb8  jnz     short loc_180065FCA
0x180065fba  mov     eax, 8007000Eh
0x180065fbf  jmp     loc_18006659E
0x180065fc4  call    __report_rangecheckfailure
0x180065fca  bt      rbx, 0Bh
0x180065fcf  jnb     loc_180066077
0x180065fd5  mov     word ptr [rdi+0Ch], 1
0x180065fdb  xor     r8d, r8d
0x180065fde  mov     rcx, [rsi+78h]
0x180065fe2  mov     edx, 0FF676985h
0x180065fe7  mov     rax, [rcx]
0x180065fea  mov     rax, [rax+0B0h]
0x180065ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ff6  test    byte ptr [rsi+20h], 4
0x180065ffa  jnz     short loc_180066011
0x180065ffc  mov     rcx, [rsi+78h]
0x180066000  xor     edx, edx
0x180066002  mov     rax, [rcx]
0x180066005  mov     rax, [rax+118h]
0x18006600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066011  lea     rbx, [rdi+20h]
0x180066015  mov     rcx, [rbx]
0x180066018  mov     rax, [rcx]
0x18006601b  mov     rax, [rax+10h]
0x18006601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066024  mov     rcx, [rsi+80h]
0x18006602b  lea     rdx, [rsp+3F0h+var_380]
0x180066030  mov     qword ptr [rsp+3F0h+var_380], r12
0x180066035  mov     rax, [rcx]
0x180066038  mov     rax, [rax+90h]
0x18006603f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066044  mov     rcx, qword ptr [rsp+3F0h+var_380]
0x180066049  mov     rdx, rbx
0x18006604c  mov     rax, [rcx]
0x18006604f  mov     rax, [rax+38h]
0x180066053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066058  mov     rcx, qword ptr [rsp+3F0h+var_380]
0x18006605d  mov     rax, [rcx]
0x180066060  mov     rax, [rax+10h]
0x180066064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066069  mov     r8, [rbx]; struct ITextFont *
0x18006606c  mov     rdx, rsi; struct CTextMsgFilter *
0x18006606f  mov     ecx, [rdi+28h]; int
0x180066072  call    ?CheckKeyboardFontMatching@CIme@@SAXJAEAVCTextMsgFilter@@PEAUITextFont@@@Z; CIme::CheckKeyboardFontMatching(long,CTextMsgFilter &,ITextFont *)
0x180066077  xor     ebx, ebx
0x180066079  test    r13d, r13d
0x18006607c  jnz     short loc_1800660B0
0x18006607e  cmp     [rdi+2Ch], ebx
0x180066081  jnz     short loc_1800660B0
0x180066083  lea     r12, [rsi+18h]
0x180066087  cmp     dword ptr [r12], 3B5h
0x18006608f  jnz     loc_18006648E
0x180066095  mov     rcx, [rsi+78h]
0x180066099  or      edx, 0FFFFFFFFh
0x18006609c  mov     rax, [rcx]
0x18006609f  mov     rax, [rax+160h]
0x1800660a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660ab  jmp     loc_180066480
0x1800660b0  test    byte ptr [rsi+20h], 4
0x1800660b4  jnz     short loc_1800660CB
0x1800660b6  mov     rcx, [rsi+78h]
0x1800660ba  xor     edx, edx
0x1800660bc  mov     rax, [rcx]
0x1800660bf  mov     rax, [rax+118h]
0x1800660c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660cb  test    r13d, r13d
0x1800660ce  jnz     loc_1800661BD
0x1800660d4  cmp     dword ptr [rsi+18h], 3B5h
0x1800660db  jnz     loc_1800661BD
0x1800660e1  test    byte ptr [rsi+20h], 10h
0x1800660e5  jz      loc_1800661BD
0x1800660eb  cmp     [rdi+10h], bx
0x1800660ef  jnz     loc_1800661BD
0x1800660f5  mov     eax, 1000h
0x1800660fa  test    [rsi+20h], ax
0x1800660fe  jnz     loc_1800661BD
0x180066104  mov     rcx, [r15]
0x180066107  lea     r9, [rsp+3F0h+var_390]
0x18006610c  mov     [rsp+3F0h+var_380], ebx
0x180066110  lea     rbx, [rdi+28h]
0x180066114  mov     edx, [rbx]
0x180066116  mov     rax, [rcx]
  ... truncated ...
```
