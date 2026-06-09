# StringA_To_StringW(tagVARIANTCONVERT *,tagMIMEVARIANT *,tagMIMEVARIANT *)

- ea: `0x1800102c0`
- end: `0x1800106f1`
- name: `?StringA_To_StringW@@YAJPEAUtagVARIANTCONVERT@@PEAUtagMIMEVARIANT@@1@Z`
- size: `1073`
- prototype: `__int64 __fastcall(struct tagVARIANTCONVERT *, struct tagMIMEVARIANT *, struct tagMIMEVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800102c0`
- `0x180010700`
- `0x180033b58`
- `0x1800577ec`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x1800104d4`
- `KERNEL32!IsValidCodePage` at `0x1800104d4`
- `KERNEL32!MultiByteToWideChar` at `0x1800104b6`
- `KERNEL32!MultiByteToWideChar` at `0x180010582`
- `KERNEL32!MultiByteToWideChar` at `0x18001066b`
- `KERNEL32!MultiByteToWideChar` at `0x1800104b6`
- `KERNEL32!MultiByteToWideChar` at `0x180010582`
- `KERNEL32!MultiByteToWideChar` at `0x18001066b`
- `ole32!CoCreateInstance` at `0x180010466`
- `ole32!CoCreateInstance` at `0x180010466`

## pseudocode

```c
__int64 __fastcall StringA_To_StringW(
        struct tagVARIANTCONVERT *a1,
        struct tagMIMEVARIANT *a2,
        struct tagMIMEVARIANT *a3)
{
  LPCCH *v3; // rbx
  __int64 v7; // rax
  __int64 v8; // r15
  bool v9; // zf
  __int64 v10; // r12
  unsigned int v11; // edi
  __int128 v12; // xmm1
  int *v13; // r13
  UINT v14; // r12d
  LPCCH v15; // rax
  HRESULT v16; // eax
  LPVOID v17; // rcx
  void *v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  int v23; // [rsp+40h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-31h] BYREF
  UINT CodePage; // [rsp+50h] [rbp-29h]
  int v26; // [rsp+54h] [rbp-25h] BYREF
  int v27; // [rsp+58h] [rbp-21h]
  __int128 v28; // [rsp+60h] [rbp-19h] BYREF
  __int128 v29; // [rsp+70h] [rbp-9h]
  LPCCH v30; // [rsp+80h] [rbp+7h]
  __int128 v31; // [rsp+88h] [rbp+Fh] BYREF

  v3 = (LPCCH *)((char *)a2 + 8);
  if ( a2 == (struct tagMIMEVARIANT *)-8LL || !*v3 || (*v3)[*((_QWORD *)a2 + 2)] )
    return 2147942487LL;
  if ( *(_DWORD *)a3 == 2 )
  {
    *((_QWORD *)a3 + 1) = 0;
    *((_QWORD *)a3 + 2) = 0;
  }
  v7 = *((_QWORD *)a1 + 1);
  v8 = 0;
  v28 = 2u;
  v9 = (*(_BYTE *)(v7 + 16) & 1) == 0;
  v29 = 0u;
  if ( !v9 )
  {
    if ( (*((_BYTE *)a1 + 28) & 1) != 0 )
    {
      if ( (*((_DWORD *)a1 + 8) & 0x800) == 0 )
      {
        if ( CMimeInternational::HrEncodeProperty(0, a1, a2, (struct tagMIMEVARIANT *)&v28) >= 0 )
        {
          v10 = *((_QWORD *)&v28 + 1);
          v8 = *((_QWORD *)&v28 + 1);
          goto LABEL_12;
        }
LABEL_41:
        v10 = *((_QWORD *)&v28 + 1);
LABEL_12:
        if ( v10 )
          goto LABEL_13;
      }
    }
    else if ( *((_DWORD *)a1 + 6) == 9 )
    {
      if ( (int)CMimeInternational::HrDecodeProperty(0, a1, a2, (struct tagMIMEVARIANT *)&v28) >= 0 )
      {
        v10 = *((_QWORD *)&v28 + 1);
        v8 = *((_QWORD *)&v28 + 1);
        goto LABEL_12;
      }
      goto LABEL_41;
    }
  }
  v13 = (int *)(v3 + 1);
  v11 = -2147467259;
  v14 = *(_DWORD *)(*((_QWORD *)a1 + 2) + 136LL);
  v15 = *v3;
  CodePage = v14;
  v30 = v15;
  if ( v15 )
  {
    v26 = *v13;
    v27 = 0;
    ppv = 0;
    v16 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a, &ppv);
    v23 = v16;
    if ( v16 >= 0 )
    {
      v23 = 1;
      v31 = 0;
      v16 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, LPCCH, int *, __int128 *, int *))(*(_QWORD *)ppv + 176LL))(
              ppv,
              2,
              0,
              v30,
              &v26,
              &v31,
              &v23);
      v23 = v16;
      if ( v16 >= 0 )
      {
        if ( SHIDWORD(v31) <= 85 )
        {
          v16 = -2147467259;
          v23 = -2147467259;
        }
        else
        {
          v27 = DWORD1(v31);
        }
      }
    }
    v17 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
      v16 = v23;
    }
    if ( v16 >= 0 && v27 == 65001 )
    {
      v14 = 65001;
      CodePage = 65001;
    }
  }
  v18 = (void *)MultiByteToWideChar(v14, 0, *v3, *v13, 0, 0);
  ppv = v18;
  if ( !(_DWORD)v18 )
  {
    if ( *(void **)v13 == v18 )
    {
      ppv = 0;
    }
    else
    {
      if ( IsValidCodePage(v14) )
        goto LABEL_28;
      v20 = MultiByteToWideChar(0, 0, *v3, *v13, 0, 0);
      ppv = (LPVOID)v20;
      if ( !v20 )
        goto LABEL_28;
      CodePage = 0;
    }
  }
  *((_QWORD *)&v28 + 1) = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(
                            g_pMalloc,
                            2LL * (_QWORD)ppv + 2);
  v10 = *((_QWORD *)&v28 + 1);
  if ( !*((_QWORD *)&v28 + 1) )
  {
    v11 = -2147024882;
    goto LABEL_28;
  }
  v19 = MultiByteToWideChar(CodePage, 0, *v3, *v13, *((LPWSTR *)&v28 + 1), (_DWORD)ppv + 1);
  *(_QWORD *)&v29 = v19;
  if ( !v19 && *(_QWORD *)v13 )
    goto LABEL_28;
  *(_WORD *)(v10 + 2LL * v19) = 0;
  BYTE4(v28) = 0;
  v8 = v10;
LABEL_13:
  v11 = 0;
  if ( (*((_BYTE *)a1 + 28) & 5) == 5 )
  {
    v11 = -2146644430;
    goto LABEL_28;
  }
  if ( *(_DWORD *)a3 == 4 )
  {
    v21 = *((_QWORD *)a3 + 1);
    if ( !v21 )
    {
      v11 = -2147024809;
      goto LABEL_28;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 32LL))(
            v21,
            v10,
            (unsigned int)v29,
            0);
LABEL_55:
    v11 = v22;
LABEL_28:
    if ( v8 )
      ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
    return v11;
  }
  if ( *(_DWORD *)a3 != 2 )
    goto LABEL_28;
  if ( (*((_DWORD *)a1 + 7) & 2) != 0 )
  {
    v22 = HrWriteNameInDataW(a1, (struct tagMIMEVARIANT *)&v28, a3);
    goto LABEL_55;
  }
  if ( v10 != v8 )
    goto LABEL_28;
  v12 = v29;
  *(_OWORD *)a3 = v28;
  *((_OWORD *)a3 + 1) = v12;
  *((_BYTE *)a3 + 4) = 0;
  return v11;
}

```

## disassembly

```asm
0x1800102c0  push    rbp
0x1800102c2  push    rbx
0x1800102c3  push    rsi
0x1800102c4  push    rdi
0x1800102c5  push    r14
0x1800102c7  lea     rbp, [rsp-37h]
0x1800102cc  sub     rsp, 0B0h
0x1800102d3  mov     rax, cs:__security_cookie
0x1800102da  xor     rax, rsp
0x1800102dd  mov     [rbp+57h+var_38], rax
0x1800102e1  lea     rbx, [rdx+8]
0x1800102e5  mov     rsi, r8
0x1800102e8  mov     r14, rcx
0x1800102eb  test    rbx, rbx
0x1800102ee  jz      short loc_180010302
0x1800102f0  mov     rax, [rbx]
0x1800102f3  test    rax, rax
0x1800102f6  jz      short loc_180010302
0x1800102f8  mov     rcx, [rdx+10h]
0x1800102fc  cmp     byte ptr [rax+rcx], 0
0x180010300  jz      short loc_180010321
0x180010302  mov     eax, 80070057h
0x180010307  mov     rcx, [rbp+57h+var_38]
0x18001030b  xor     rcx, rsp; StackCookie
0x18001030e  call    __security_check_cookie
0x180010313  add     rsp, 0B0h
0x18001031a  pop     r14
0x18001031c  pop     rdi
0x18001031d  pop     rsi
0x18001031e  pop     rbx
0x18001031f  pop     rbp
0x180010320  retn
0x180010321  xor     ecx, ecx; this
0x180010323  mov     [rsp+0D0h+var_30], r15
0x18001032b  cmp     dword ptr [r8], 2
0x18001032f  jnz     short loc_180010339
0x180010331  mov     [r8+8], rcx
0x180010335  mov     [r8+10h], rcx
0x180010339  mov     rax, [r14+8]
0x18001033d  mov     r15, rcx
0x180010340  mov     [rsp+0D0h+arg_18], r12
0x180010348  mov     [rsp+0D0h+var_28], r13
0x180010350  mov     qword ptr [rbp+57h+var_70], 2
0x180010358  test    byte ptr [rax+10h], 1
0x18001035c  mov     qword ptr [rbp+57h+var_60], rcx
0x180010360  mov     qword ptr [rbp+57h+var_60+8], rcx
0x180010364  mov     qword ptr [rbp+57h+var_70+8], rcx
0x180010368  jz      loc_180010415
0x18001036e  test    byte ptr [r14+1Ch], 1
0x180010373  jnz     loc_180010507
0x180010379  cmp     dword ptr [r14+18h], 9
0x18001037e  jnz     loc_180010415
0x180010384  mov     r8, rdx; struct tagMIMEVARIANT *
0x180010387  lea     r9, [rbp+57h+var_70]; struct tagMIMEVARIANT *
0x18001038b  mov     rdx, r14; struct tagVARIANTCONVERT *
0x18001038e  call    ?HrDecodeProperty@CMimeInternational@@QEAAJPEAUtagVARIANTCONVERT@@PEAUtagMIMEVARIANT@@1@Z; CMimeInternational::HrDecodeProperty(tagVARIANTCONVERT *,tagMIMEVARIANT *,tagMIMEVARIANT *)
0x180010393  test    eax, eax
0x180010395  js      loc_180010624
0x18001039b  mov     r12, qword ptr [rbp+57h+var_70+8]
0x18001039f  mov     r15, r12
0x1800103a2  test    r12, r12
0x1800103a5  jz      loc_1800105A9
0x1800103ab  mov     ecx, [r14+1Ch]
0x1800103af  xor     edi, edi
0x1800103b1  mov     eax, ecx
0x1800103b3  and     eax, 5
0x1800103b6  cmp     al, 5
0x1800103b8  jz      loc_1800106A6
0x1800103be  mov     eax, [rsi]
0x1800103c0  cmp     eax, 4
0x1800103c3  jz      loc_1800106B0
0x1800103c9  cmp     eax, 2
0x1800103cc  jnz     loc_1800104E3
0x1800103d2  test    al, cl
0x1800103d4  jnz     loc_1800106DB
0x1800103da  cmp     r12, r15
0x1800103dd  jnz     loc_1800104E3
0x1800103e3  movups  xmm0, [rbp+57h+var_70]
0x1800103e7  movups  xmm1, [rbp+57h+var_60]
0x1800103eb  movups  xmmword ptr [rsi], xmm0
0x1800103ee  movups  xmmword ptr [rsi+10h], xmm1
0x1800103f2  mov     [rsi+4], dil
0x1800103f6  mov     r15, [rsp+0D0h+var_30]
0x1800103fe  mov     eax, edi
0x180010400  mov     r13, [rsp+0D0h+var_28]
0x180010408  mov     r12, [rsp+0D0h+arg_18]
0x180010410  jmp     loc_180010307
0x180010415  mov     rax, [r14+10h]
0x180010419  lea     r13, [rbx+8]
0x18001041d  mov     edi, 80004005h
0x180010422  mov     r12d, [rax+88h]
0x180010429  mov     rax, [rbx]
0x18001042c  mov     [rbp+57h+CodePage], r12d
0x180010430  mov     [rbp+57h+var_50], rax
0x180010434  test    rax, rax
0x180010437  jz      short loc_18001049F
0x180010439  mov     eax, [r13+0]
0x18001043d  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x180010444  mov     [rbp+57h+var_7C], eax
0x180010447  xor     edx, edx; pUnkOuter
0x180010449  lea     rax, [rbp+57h+var_88]
0x18001044d  mov     [rbp+57h+var_78], ecx
0x180010450  mov     [rbp+57h+var_88], rcx
0x180010454  mov     r8d, 1; dwClsContext
0x18001045a  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180010461  mov     [rsp+0D0h+ppv], rax; ppv
0x180010466  call    cs:__imp_CoCreateInstance
0x18001046c  mov     [rbp+57h+var_90], eax
0x18001046f  test    eax, eax
0x180010471  jns     loc_1800105B0
0x180010477  mov     rcx, [rbp+57h+var_88]
0x18001047b  test    rcx, rcx
0x18001047e  jz      short loc_180010497
0x180010480  mov     [rbp+57h+var_88], 0
0x180010488  mov     rax, [rcx]
0x18001048b  mov     rax, [rax+10h]
0x18001048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010494  mov     eax, [rbp+57h+var_90]
0x180010497  test    eax, eax
0x180010499  jns     loc_180010637
0x18001049f  mov     r9d, [r13+0]; cbMultiByte
0x1800104a3  xor     eax, eax
0x1800104a5  mov     r8, [rbx]; lpMultiByteStr
0x1800104a8  xor     edx, edx; dwFlags
0x1800104aa  mov     [rsp+0D0h+cchWideChar], eax; cchWideChar
0x1800104ae  mov     ecx, r12d; CodePage
0x1800104b1  mov     [rsp+0D0h+ppv], rax; lpWideCharStr
0x1800104b6  call    cs:__imp_MultiByteToWideChar
0x1800104bc  cdqe
0x1800104be  mov     [rbp+57h+var_88], rax
0x1800104c2  test    rax, rax
0x1800104c5  jnz     short loc_180010538
0x1800104c7  cmp     [r13+0], rax
0x1800104cb  jz      loc_180010689
0x1800104d1  mov     ecx, r12d; CodePage
0x1800104d4  call    cs:__imp_IsValidCodePage
0x1800104da  cmp     eax, 1
0x1800104dd  jnz     loc_180010653
0x1800104e3  test    r15, r15
0x1800104e6  jz      loc_1800103F6
0x1800104ec  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800104f3  mov     rdx, r15
0x1800104f6  mov     rax, [rcx]
0x1800104f9  mov     rax, [rax+28h]
0x1800104fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010502  jmp     loc_1800103F6
0x180010507  test    dword ptr [r14+20h], 800h
0x18001050f  jnz     loc_180010415
0x180010515  mov     r8, rdx; struct tagMIMEVARIANT *
0x180010518  lea     r9, [rbp+57h+var_70]; struct tagMIMEVARIANT *
0x18001051c  mov     rdx, r14; struct tagVARIANTCONVERT *
0x18001051f  call    ?HrEncodeProperty@CMimeInternational@@QEAAJPEAUtagVARIANTCONVERT@@PEAUtagMIMEVARIANT@@1@Z; CMimeInternational::HrEncodeProperty(tagVARIANTCONVERT *,tagMIMEVARIANT *,tagMIMEVARIANT *)
0x180010524  test    eax, eax
0x180010526  js      loc_180010624
0x18001052c  mov     r12, qword ptr [rbp+57h+var_70+8]
0x180010530  mov     r15, r12
0x180010533  jmp     loc_1800103A2
0x180010538  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001053f  mov     rdx, [rbp+57h+var_88]
0x180010543  mov     rax, [rcx]
0x180010546  lea     rdx, ds:2[rdx*2]
0x18001054e  mov     rax, [rax+18h]
0x180010552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010557  mov     qword ptr [rbp+57h+var_70+8], rax
0x18001055b  mov     r12, rax
0x18001055e  test    rax, rax
0x180010561  jz      loc_18001061A
0x180010567  mov     rax, [rbp+57h+var_88]
0x18001056b  xor     edx, edx; dwFlags
0x18001056d  mov     r9d, [r13+0]; cbMultiByte
0x180010571  inc     eax
0x180010573  mov     r8, [rbx]; lpMultiByteStr
0x180010576  mov     ecx, [rbp+57h+CodePage]; CodePage
0x180010579  mov     [rsp+0D0h+cchWideChar], eax; cchWideChar
0x18001057d  mov     [rsp+0D0h+ppv], r12; lpWideCharStr
0x180010582  call    cs:__imp_MultiByteToWideChar
0x180010588  movsxd  rcx, eax
0x18001058b  mov     qword ptr [rbp+57h+var_60], rcx
0x18001058f  test    eax, eax
0x180010591  jz      loc_180010696
0x180010597  xor     eax, eax
0x180010599  mov     [r12+rcx*2], ax
0x18001059e  mov     byte ptr [rbp+57h+var_70+4], al
0x1800105a1  mov     r15, r12
0x1800105a4  jmp     loc_1800103AB
0x1800105a9  xor     ecx, ecx
0x1800105ab  jmp     loc_180010415
0x1800105b0  mov     eax, [rbp+57h+var_7C]
0x1800105b3  lea     r8, [rbp+57h+var_90]
0x1800105b7  mov     rcx, [rbp+57h+var_88]
0x1800105bb  xorps   xmm0, xmm0
0x1800105be  mov     r9, [rbp+57h+var_50]
0x1800105c2  mov     edx, 2
0x1800105c7  mov     [rsp+0D0h+var_A0], r8
0x1800105cc  lea     r8, [rbp+57h+var_48]
0x1800105d0  mov     qword ptr [rsp+0D0h+cchWideChar], r8
0x1800105d5  lea     r8, [rbp+57h+var_7C]
0x1800105d9  mov     [rbp+57h+var_7C], eax
0x1800105dc  mov     [rbp+57h+var_90], 1
0x1800105e3  movups  [rbp+57h+var_48], xmm0
0x1800105e7  mov     rax, [rcx]
0x1800105ea  mov     [rsp+0D0h+ppv], r8
0x1800105ef  xor     r8d, r8d
0x1800105f2  mov     rax, [rax+0B0h]
0x1800105f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fe  mov     [rbp+57h+var_90], eax
0x180010601  test    eax, eax
0x180010603  js      loc_180010477
0x180010609  cmp     dword ptr [rbp+57h+var_48+0Ch], 55h ; 'U'
0x18001060d  jle     short loc_18001062D
0x18001060f  mov     ecx, dword ptr [rbp+57h+var_48+4]
0x180010612  mov     [rbp+57h+var_78], ecx
0x180010615  jmp     loc_180010477
0x18001061a  mov     edi, 8007000Eh
0x18001061f  jmp     loc_1800104E3
0x180010624  mov     r12, qword ptr [rbp+57h+var_70+8]
0x180010628  jmp     loc_1800103A2
0x18001062d  mov     eax, edi
0x18001062f  mov     [rbp+57h+var_90], eax
0x180010632  jmp     loc_180010477
0x180010637  cmp     [rbp+57h+var_78], 0FDE9h
0x18001063e  jnz     loc_18001049F
0x180010644  mov     r12d, 0FDE9h
0x18001064a  mov     [rbp+57h+CodePage], r12d
0x18001064e  jmp     loc_18001049F
0x180010653  mov     r9d, [r13+0]; cbMultiByte
0x180010657  xor     r12d, r12d
0x18001065a  mov     r8, [rbx]; lpMultiByteStr
0x18001065d  xor     edx, edx; dwFlags
0x18001065f  mov     [rsp+0D0h+cchWideChar], r12d; cchWideChar
0x180010664  xor     ecx, ecx; CodePage
0x180010666  mov     [rsp+0D0h+ppv], r12; lpWideCharStr
0x18001066b  call    cs:__imp_MultiByteToWideChar
0x180010671  cdqe
0x180010673  mov     [rbp+57h+var_88], rax
0x180010677  test    rax, rax
0x18001067a  jz      loc_1800104E3
0x180010680  mov     [rbp+57h+CodePage], r12d
0x180010684  jmp     loc_180010538
0x180010689  mov     [rbp+57h+var_88], 0
0x180010691  jmp     loc_180010538
0x180010696  cmp     qword ptr [r13+0], 0
0x18001069b  jnz     loc_1800104E3
0x1800106a1  jmp     loc_180010597
0x1800106a6  mov     edi, 800CCE32h
0x1800106ab  jmp     loc_1800104E3
0x1800106b0  mov     rcx, [rsi+8]
0x1800106b4  test    rcx, rcx
0x1800106b7  jnz     short loc_1800106C3
0x1800106b9  mov     edi, 80070057h
0x1800106be  jmp     loc_1800104E3
0x1800106c3  mov     rax, [rcx]
0x1800106c6  xor     r9d, r9d
0x1800106c9  mov     r8d, dword ptr [rbp+57h+var_60]
0x1800106cd  mov     rdx, r12
0x1800106d0  mov     rax, [rax+20h]
0x1800106d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d9  jmp     short loc_1800106EA
0x1800106db  mov     r8, rsi; struct tagMIMEVARIANT *
0x1800106de  lea     rdx, [rbp+57h+var_70]; struct tagMIMEVARIANT *
0x1800106e2  mov     rcx, r14; struct tagVARIANTCONVERT *
0x1800106e5  call    ?HrWriteNameInDataW@@YAJPEBUtagVARIANTCONVERT@@PEAUtagMIMEVARIANT@@1@Z; HrWriteNameInDataW(tagVARIANTCONVERT const *,tagMIMEVARIANT *,tagMIMEVARIANT *)
0x1800106ea  mov     edi, eax
0x1800106ec  jmp     loc_1800104E3
```
