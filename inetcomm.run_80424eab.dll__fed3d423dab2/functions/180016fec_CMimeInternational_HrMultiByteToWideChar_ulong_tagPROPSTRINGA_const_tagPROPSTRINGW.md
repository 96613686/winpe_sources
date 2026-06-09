# CMimeInternational::HrMultiByteToWideChar(ulong,tagPROPSTRINGA const *,tagPROPSTRINGW *)

- ea: `0x180016fec`
- end: `0x18001724d`
- name: `?HrMultiByteToWideChar@CMimeInternational@@QEAAJKPEBUtagPROPSTRINGA@@PEAUtagPROPSTRINGW@@@Z`
- size: `609`
- prototype: `int(CMimeInternational *__hidden this, unsigned int, const struct tagPROPSTRINGA *, struct tagPROPSTRINGW *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010700`
- `0x180010fc0`
- `0x180056318`
- `0x180056f54`

## callees

- `0x180016fec`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x1800170d2`
- `KERNEL32!IsValidCodePage` at `0x1800170d2`
- `KERNEL32!MultiByteToWideChar` at `0x1800170b5`
- `KERNEL32!MultiByteToWideChar` at `0x18001714e`
- `KERNEL32!MultiByteToWideChar` at `0x18001721a`
- `KERNEL32!MultiByteToWideChar` at `0x1800170b5`
- `KERNEL32!MultiByteToWideChar` at `0x18001714e`
- `KERNEL32!MultiByteToWideChar` at `0x18001721a`
- `ole32!CoCreateInstance` at `0x18001705e`
- `ole32!CoCreateInstance` at `0x18001705e`

## pseudocode

```c
__int64 __fastcall CMimeInternational::HrMultiByteToWideChar(
        CMimeInternational *this,
        UINT a2,
        LPCCH *a3,
        struct tagPROPSTRINGW *a4)
{
  int *v4; // rbx
  unsigned int v8; // edi
  int v9; // r13d
  HRESULT v10; // r15d
  LPVOID v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  WCHAR *v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+40h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-38h] BYREF
  int v20; // [rsp+50h] [rbp-30h] BYREF
  LPCCH v21; // [rsp+58h] [rbp-28h]
  __int128 v22; // [rsp+60h] [rbp-20h] BYREF

  v4 = (int *)(a3 + 1);
  v21 = *a3;
  v8 = -2147467259;
  if ( v21 )
  {
    v18 = *v4;
    ppv = 0;
    v9 = 0;
    v10 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a, &ppv);
    if ( v10 >= 0 )
    {
      v20 = 1;
      v22 = 0;
      v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, LPCCH, int *, __int128 *, int *))(*(_QWORD *)ppv + 176LL))(
              ppv,
              2,
              0,
              v21,
              &v18,
              &v22,
              &v20);
      if ( v10 >= 0 )
      {
        if ( SHIDWORD(v22) <= 85 )
          v10 = -2147467259;
        else
          v9 = DWORD1(v22);
      }
    }
    v11 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v10 >= 0 && v9 == 65001 )
      a2 = 65001;
  }
  *(_QWORD *)a4 = 0;
  *((_QWORD *)a4 + 1) = 0;
  v12 = MultiByteToWideChar(a2, 0, *a3, *v4, 0, 0);
  v13 = v12;
  *((_QWORD *)a4 + 1) = v12;
  if ( !v12 )
  {
    if ( *(_QWORD *)v4 )
    {
      if ( IsValidCodePage(a2) )
        return v8;
      v17 = MultiByteToWideChar(0, 0, *a3, *v4, 0, 0);
      v13 = v17;
      *((_QWORD *)a4 + 1) = v17;
      if ( !v17 )
        return v8;
      a2 = 0;
    }
    else
    {
      v13 = 0;
    }
  }
  v15 = (WCHAR *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 2 * v13 + 2);
  *(_QWORD *)a4 = v15;
  if ( v15 )
  {
    v16 = MultiByteToWideChar(a2, 0, *a3, *v4, v15, *((_DWORD *)a4 + 2) + 1);
    *((_QWORD *)a4 + 1) = v16;
    if ( v16 || !*(_QWORD *)v4 )
    {
      v8 = 0;
      *(_WORD *)(*(_QWORD *)a4 + 2LL * v16) = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180016fec  mov     [rsp-38h+arg_0], rbx
0x180016ff1  push    rbp
0x180016ff2  push    rsi
0x180016ff3  push    rdi
0x180016ff4  push    r12
0x180016ff6  push    r13
0x180016ff8  push    r14
0x180016ffa  push    r15
0x180016ffc  mov     rbp, rsp
0x180016fff  sub     rsp, 80h
0x180017006  mov     rax, cs:__security_cookie
0x18001700d  xor     rax, rsp
0x180017010  mov     [rbp+var_10], rax
0x180017014  mov     rax, [r8]
0x180017017  lea     rbx, [r8+8]
0x18001701b  xor     r15d, r15d
0x18001701e  mov     [rbp+var_28], rax
0x180017022  mov     rsi, r9
0x180017025  mov     r12, r8
0x180017028  mov     r14d, edx
0x18001702b  mov     edi, 80004005h
0x180017030  test    rax, rax
0x180017033  jz      short loc_180017098
0x180017035  mov     eax, [rbx]
0x180017037  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x18001703e  mov     [rbp+var_40], eax
0x180017041  lea     r8d, [r15+1]; dwClsContext
0x180017045  lea     rax, [rbp+var_38]
0x180017049  mov     [rbp+var_38], r15
0x18001704d  xor     edx, edx; pUnkOuter
0x18001704f  mov     [rsp+80h+ppv], rax; ppv
0x180017054  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18001705b  mov     r13d, r15d
0x18001705e  call    cs:__imp_CoCreateInstance
0x180017064  mov     r15d, eax
0x180017067  test    eax, eax
0x180017069  jns     loc_180017173
0x18001706f  mov     rcx, [rbp+var_38]
0x180017073  test    rcx, rcx
0x180017076  jz      short loc_18001708C
0x180017078  mov     [rbp+var_38], 0
0x180017080  mov     rax, [rcx]
0x180017083  mov     rax, [rax+10h]
0x180017087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001708c  test    r15d, r15d
0x18001708f  jns     loc_1800171EC
0x180017095  xor     r15d, r15d
0x180017098  mov     [rsi], r15
0x18001709b  xor     edx, edx; dwFlags
0x18001709d  mov     [rsi+8], r15
0x1800170a1  mov     ecx, r14d; CodePage
0x1800170a4  mov     r9d, [rbx]; cbMultiByte
0x1800170a7  mov     r8, [r12]; lpMultiByteStr
0x1800170ab  mov     [rsp+80h+cchWideChar], r15d; cchWideChar
0x1800170b0  mov     [rsp+80h+ppv], r15; lpWideCharStr
0x1800170b5  call    cs:__imp_MultiByteToWideChar
0x1800170bb  movsxd  rdx, eax
0x1800170be  mov     [rsi+8], rdx
0x1800170c2  test    eax, eax
0x1800170c4  jnz     short loc_18001710A
0x1800170c6  cmp     [rbx], r15
0x1800170c9  jz      loc_180017237
0x1800170cf  mov     ecx, r14d; CodePage
0x1800170d2  call    cs:__imp_IsValidCodePage
0x1800170d8  cmp     eax, 1
0x1800170db  jnz     loc_180017205
0x1800170e1  mov     eax, edi
0x1800170e3  mov     rcx, [rbp+var_10]
0x1800170e7  xor     rcx, rsp; StackCookie
0x1800170ea  call    __security_check_cookie
0x1800170ef  mov     rbx, [rsp+80h+arg_0]
0x1800170f7  add     rsp, 80h
0x1800170fe  pop     r15
0x180017100  pop     r14
0x180017102  pop     r13
0x180017104  pop     r12
0x180017106  pop     rdi
0x180017107  pop     rsi
0x180017108  pop     rbp
0x180017109  retn
0x18001710a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180017111  lea     rdx, ds:2[rdx*2]
0x180017119  mov     rax, [rcx]
0x18001711c  mov     rax, [rax+18h]
0x180017120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017125  mov     [rsi], rax
0x180017128  mov     rcx, rax
0x18001712b  test    rax, rax
0x18001712e  jz      loc_1800171DA
0x180017134  mov     eax, [rsi+8]
0x180017137  xor     edx, edx; dwFlags
0x180017139  mov     r9d, [rbx]; cbMultiByte
0x18001713c  inc     eax
0x18001713e  mov     r8, [r12]; lpMultiByteStr
0x180017142  mov     [rsp+80h+cchWideChar], eax; cchWideChar
0x180017146  mov     [rsp+80h+ppv], rcx; lpWideCharStr
0x18001714b  mov     ecx, r14d; CodePage
0x18001714e  call    cs:__imp_MultiByteToWideChar
0x180017154  movsxd  r8, eax
0x180017157  mov     [rsi+8], r8
0x18001715b  test    eax, eax
0x18001715d  jz      loc_18001723F
0x180017163  mov     rdx, [rsi]
0x180017166  mov     edi, r15d
0x180017169  mov     [rdx+r8*2], r15w
0x18001716e  jmp     loc_1800170E1
0x180017173  mov     eax, [rbp+var_40]
0x180017176  lea     rdx, [rbp+var_30]
0x18001717a  mov     rcx, [rbp+var_38]
0x18001717e  xorps   xmm0, xmm0
0x180017181  mov     r9, [rbp+var_28]
0x180017185  xor     r8d, r8d
0x180017188  mov     [rsp+80h+var_50], rdx
0x18001718d  lea     rdx, [rbp+var_20]
0x180017191  mov     qword ptr [rsp+80h+cchWideChar], rdx
0x180017196  lea     rdx, [rbp+var_40]
0x18001719a  mov     [rbp+var_40], eax
0x18001719d  mov     [rbp+var_30], 1
0x1800171a4  movups  [rbp+var_20], xmm0
0x1800171a8  mov     rax, [rcx]
0x1800171ab  mov     [rsp+80h+ppv], rdx
0x1800171b0  lea     edx, [r8+2]
0x1800171b4  mov     rax, [rax+0B0h]
0x1800171bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c0  mov     r15d, eax
0x1800171c3  test    eax, eax
0x1800171c5  js      loc_18001706F
0x1800171cb  cmp     dword ptr [rbp+var_20+0Ch], 55h ; 'U'
0x1800171cf  jle     short loc_1800171E4
0x1800171d1  mov     r13d, dword ptr [rbp+var_20+4]
0x1800171d5  jmp     loc_18001706F
0x1800171da  mov     edi, 8007000Eh
0x1800171df  jmp     loc_1800170E1
0x1800171e4  mov     r15d, edi
0x1800171e7  jmp     loc_18001706F
0x1800171ec  mov     eax, 0FDE9h
0x1800171f1  xor     r15d, r15d
0x1800171f4  cmp     r13d, eax
0x1800171f7  jnz     loc_180017098
0x1800171fd  mov     r14d, eax
0x180017200  jmp     loc_180017098
0x180017205  mov     r9d, [rbx]; cbMultiByte
0x180017208  xor     edx, edx; dwFlags
0x18001720a  mov     r8, [r12]; lpMultiByteStr
0x18001720e  xor     ecx, ecx; CodePage
0x180017210  mov     [rsp+80h+cchWideChar], r15d; cchWideChar
0x180017215  mov     [rsp+80h+ppv], r15; lpWideCharStr
0x18001721a  call    cs:__imp_MultiByteToWideChar
0x180017220  movsxd  rdx, eax
0x180017223  mov     [rsi+8], rdx
0x180017227  test    eax, eax
0x180017229  jz      loc_1800170E1
0x18001722f  mov     r14d, r15d
0x180017232  jmp     loc_18001710A
0x180017237  mov     rdx, r15
0x18001723a  jmp     loc_18001710A
0x18001723f  cmp     [rbx], r15
0x180017242  jnz     loc_1800170E1
0x180017248  jmp     loc_180017163
```
