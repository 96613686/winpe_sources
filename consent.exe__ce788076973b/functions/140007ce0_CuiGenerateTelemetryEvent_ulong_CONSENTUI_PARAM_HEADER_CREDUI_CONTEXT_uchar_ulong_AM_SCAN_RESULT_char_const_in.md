# CuiGenerateTelemetryEvent(ulong,_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,uchar,ulong,_AM_SCAN_RESULT,char const *,__int64)

- ea: `0x140007ce0`
- end: `0x140008278`
- name: `?CuiGenerateTelemetryEvent@@YAKKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@EKW4_AM_SCAN_RESULT@@PEBD_J@Z`
- size: `1432`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, char, unsigned int, unsigned int, char *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000cfdc`

## callees

- `0x1400044e0`
- `0x140007ce0`
- `0x140009010`
- `0x140009070`
- `0x140009e10`
- `0x14000eaa0`
- `0x140010ad3`
- `0x14001bc94`
- `0x14001bdf0`
- `0x14001e050`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140007dd8`
- `msvcrt!wcsrchr` at `0x140007e11`
- `msvcrt!wcsrchr` at `0x140007dd8`
- `msvcrt!wcsrchr` at `0x140007e11`
- `msvcrt!_wcsicmp` at `0x140007ed0`
- `msvcrt!_wcsicmp` at `0x140007ee4`
- `msvcrt!_wcsicmp` at `0x140007ed0`
- `msvcrt!_wcsicmp` at `0x140007ee4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140007db9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140007db9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140007fcf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140007fcf`
- `SHELL32!CommandLineToArgvW` at `0x140007ef9`
- `SHELL32!CommandLineToArgvW` at `0x140007ef9`

## string_xrefs

- `0x140007eda`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall CuiGenerateTelemetryEvent(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        char *a7,
        __int64 a8)
{
  int v12; // ebx
  unsigned __int16 *v13; // r15
  unsigned int v14; // r14d
  int v15; // eax
  const wchar_t *v16; // rsi
  wchar_t *v17; // rax
  void *v18; // rcx
  const wchar_t *v19; // rbx
  wchar_t *v20; // rax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  const wchar_t *v23; // rax
  const WCHAR *v24; // r15
  LPWSTR *v25; // r15
  const unsigned __int16 *v26; // r10
  __int64 v27; // rdx
  OLECHAR *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  const wchar_t *v31; // r8
  bool v32; // zf
  __int64 v33; // rax
  OLECHAR *v34; // rcx
  wchar_t v35; // r9
  OLECHAR *v36; // rdx
  unsigned __int16 *v37; // rbx
  __int64 *v38; // rcx
  __int64 *v39; // rcx
  __int64 *v40; // rax
  __int64 *v41; // rax
  const unsigned __int16 *v42; // r15
  const unsigned __int16 *v43; // r12
  const unsigned __int16 *v44; // r13
  int v45; // esi
  _DWORD *v46; // rax
  __int64 v47; // rcx
  CUITelemetry *v48; // rcx
  bool v50[4]; // [rsp+B0h] [rbp-80h] BYREF
  int v51; // [rsp+B4h] [rbp-7Ch] BYREF
  int pNumArgs; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v53; // [rsp+BCh] [rbp-74h] BYREF
  unsigned int v54; // [rsp+C0h] [rbp-70h] BYREF
  unsigned int v55; // [rsp+C4h] [rbp-6Ch] BYREF
  unsigned int v56; // [rsp+C8h] [rbp-68h] BYREF
  unsigned int v57; // [rsp+D0h] [rbp-60h] BYREF
  unsigned __int16 *v58; // [rsp+D8h] [rbp-58h]
  int v59; // [rsp+E0h] [rbp-50h] BYREF
  int v60; // [rsp+E4h] [rbp-4Ch] BYREF
  unsigned int v61; // [rsp+E8h] [rbp-48h]
  char *v62; // [rsp+F0h] [rbp-40h] BYREF
  __int64 *v63; // [rsp+F8h] [rbp-38h] BYREF
  OLECHAR *v64; // [rsp+100h] [rbp-30h] BYREF
  __int64 *v65; // [rsp+108h] [rbp-28h] BYREF
  __int64 *v66; // [rsp+110h] [rbp-20h] BYREF
  __int64 *v67; // [rsp+118h] [rbp-18h] BYREF
  char *v68; // [rsp+120h] [rbp-10h]
  __int64 v69; // [rsp+128h] [rbp-8h]
  OLECHAR sz[264]; // [rsp+130h] [rbp+0h] BYREF

  v69 = a3;
  v61 = a1;
  v57 = a1;
  v68 = a7;
  v62 = a7;
  v12 = 1;
  v13 = *(unsigned __int16 **)(a3 + 16);
  v58 = v13;
  memset_0(sz, 0, 0x208u);
  pNumArgs = 0;
  v60 = 0;
  v59 = 0;
  v51 = 0;
  if ( a1 )
  {
    v14 = 1;
    if ( a1 == 1223 )
      v14 = 3;
  }
  else if ( a4 )
  {
    v14 = 5;
  }
  else
  {
    v14 = 4;
    if ( *(_DWORD *)(a2 + 8) )
      v14 = 2;
  }
  v53 = v14;
  v15 = *(_DWORD *)(a2 + 32);
  switch ( v15 )
  {
    case 4:
      if ( StringFromGUID2((const GUID *const)(a2 + 232), sz, 260) < 0 )
        sz[0] = 0;
      v16 = *(const wchar_t **)(a2 + 224);
      v17 = wcsrchr(v16, 0x5Cu);
      v18 = v17 + 1;
      if ( v17 )
        v16 = v17 + 1;
      break;
    case 7:
      v16 = CuipJustFileName(*(unsigned __int16 **)(a2 + 200));
      v19 = *(const wchar_t **)(a2 + 208);
      v20 = wcsrchr(v19, 0x2Fu);
      if ( v20 )
        v19 = v20 + 1;
      StringCchCopyW(sz, v21, v19);
      break;
    case 5:
      v13 = CuipJustFileName(v13);
      v58 = v13;
      v16 = CuipJustFileName(*(unsigned __int16 **)(a2 + 208));
      break;
    case 8:
      v16 = CuipJustFileName(*(unsigned __int16 **)(a2 + 200));
      v13 = *(unsigned __int16 **)(a2 + 224);
      v58 = v13;
      sz[0] = 0;
      StringCchCopyW(sz, v22, *(const unsigned __int16 **)(a2 + 216));
      break;
    default:
      v23 = CuipJustFileName(*(unsigned __int16 **)(a2 + 216));
      v16 = v23;
      if ( *(_DWORD *)a3 <= 1u )
        v13 = (unsigned __int16 *)v23;
      v58 = v13;
      sz[0] = 0;
      v24 = *(const WCHAR **)(a2 + 224);
      if ( v24 && (!_wcsicmp(v23, L"mmc.exe") || !_wcsicmp(v16, L"rundll32.exe")) )
      {
        v25 = CommandLineToArgvW(v24, &pNumArgs);
        if ( v25 )
        {
          if ( pNumArgs > 1 )
          {
            do
            {
              v26 = CuipJustFileName(v25[v12]);
              if ( v12 != 1 )
              {
                v27 = 260;
                v28 = sz;
                do
                {
                  if ( !*v28 )
                    break;
                  ++v28;
                  --v27;
                }
                while ( v27 );
                v29 = 260 - v27;
                if ( !v27 )
                  break;
                v30 = 2147483646;
                v31 = L" ";
                v33 = 260 - v29;
                v32 = v29 == 260;
                v34 = &sz[v29];
                if ( !v32 )
                {
                  do
                  {
                    if ( !v30 )
                      break;
                    v35 = *v31;
                    if ( !*v31 )
                      break;
                    ++v31;
                    *v34++ = v35;
                    --v30;
                    --v33;
                  }
                  while ( v33 );
                }
                v36 = v34 - 1;
                if ( v33 )
                  v36 = v34;
                *v36 = 0;
                if ( !v33 )
                  break;
              }
              if ( StringCchCatW(sz, 0x104u, v26) < 0 )
                break;
              ++v12;
            }
            while ( v12 < pNumArgs );
          }
          GlobalFree(v25);
        }
      }
      v18 = *(void **)(a2 + 24);
      if ( v18 )
        CuipIsTokenLowIL(v18, &v51);
      v13 = v58;
      break;
  }
  if ( v14 != 1 )
  {
    v37 = (unsigned __int16 *)&qword_1400210F8;
    if ( v51 )
    {
      v51 = *(_DWORD *)(a3 + 60);
      v38 = &qword_1400210F8;
      if ( *(_QWORD *)(a3 + 40) )
        v38 = *(__int64 **)(a3 + 40);
      v63 = v38;
      v64 = sz;
      v39 = &qword_1400210F8;
      if ( *(_QWORD *)(a3 + 24) )
        v39 = *(__int64 **)(a3 + 24);
      v65 = v39;
      v54 = *(_DWORD *)a3;
      v40 = &qword_1400210F8;
      if ( v16 )
        v40 = (__int64 *)v16;
      v66 = v40;
      v55 = *(_DWORD *)(a2 + 32);
      v41 = &qword_1400210F8;
      if ( v13 )
        v41 = (__int64 *)v13;
      v67 = v41;
      v50[0] = (*(_DWORD *)(a2 + 48) & 4) != 0;
      v56 = *(_DWORD *)(a2 + 8);
      CUITelemetry::LowILConsentUILaunched<unsigned long &,unsigned long &,unsigned long &,unsigned long,bool,unsigned short const *,unsigned long,unsigned short const *,unsigned long,unsigned short const *,unsigned short const *,unsigned long &,unsigned long &,unsigned long &,enum _AM_SCAN_RESULT &,unsigned short const *,unsigned short &,unsigned long,char const * &,__int64 &>(
        (unsigned int)&v57,
        (unsigned int)&v53,
        a2 + 48,
        (unsigned int)&v56,
        (__int64)v50,
        (__int64)&v67,
        (__int64)&v55,
        (__int64)&v66,
        (__int64)&v54,
        (__int64)&v65,
        (__int64)&v64,
        (__int64)&a5,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)&a6,
        (__int64)&v63,
        a3 + 58,
        (__int64)&v51,
        (__int64)&v62,
        (__int64)&a8);
    }
    v57 = *(_DWORD *)(a3 + 60);
    v42 = (const unsigned __int16 *)&qword_1400210F8;
    if ( *(_QWORD *)(a3 + 40) )
      v42 = *(const unsigned __int16 **)(a3 + 40);
    v43 = (const unsigned __int16 *)&qword_1400210F8;
    if ( *(_QWORD *)(a3 + 24) )
      v43 = *(const unsigned __int16 **)(a3 + 24);
    v56 = *(_DWORD *)a3;
    v44 = (const unsigned __int16 *)&qword_1400210F8;
    if ( v16 )
      v44 = v16;
    v55 = *(_DWORD *)(a2 + 32);
    if ( v58 )
      v37 = v58;
    v45 = (*(_DWORD *)(a2 + 48) >> 2) & 1;
    v54 = *(_DWORD *)(a2 + 8);
    v46 = *(_DWORD **)(wil::details::static_lazy<CUITelemetry>::get(
                         v18,
                         _lambda_118efc2810da81fa517ffdfff2ec5234_::_lambda_invoker_cdecl_)
                     + 8);
    if ( v46 && *v46 )
    {
      wil::details::static_lazy<CUITelemetry>::get(
        v47,
        _lambda_118efc2810da81fa517ffdfff2ec5234_::_lambda_invoker_cdecl_);
      CUITelemetry::ConsentUILaunched_(
        v48,
        v61,
        v14,
        *(_DWORD *)(a2 + 48),
        v54,
        v45,
        v37,
        v55,
        v44,
        v56,
        v43,
        sz,
        a5,
        0,
        0,
        a6,
        v42,
        *(_WORD *)(v69 + 58),
        v57,
        v68,
        a8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007ce0  mov     [rsp-8+arg_18], rbx
0x140007ce5  push    rbp
0x140007ce6  push    rsi
0x140007ce7  push    rdi
0x140007ce8  push    r12
0x140007cea  push    r13
0x140007cec  push    r14
0x140007cee  push    r15
0x140007cf0  lea     rbp, [rsp-220h]
0x140007cf8  sub     rsp, 350h
0x140007cff  mov     rax, cs:__security_cookie
0x140007d06  xor     rax, rsp
0x140007d09  mov     [rbp+250h+var_40], rax
0x140007d10  movzx   esi, r9b
0x140007d14  mov     r13, r8
0x140007d17  mov     [rbp+250h+var_258], r8
0x140007d1b  mov     rdi, rdx
0x140007d1e  mov     r12d, ecx
0x140007d21  mov     [rbp+250h+var_298], ecx
0x140007d24  mov     [rbp+250h+var_2B0], ecx
0x140007d27  mov     rax, [rbp+250h+arg_30]
0x140007d2e  mov     [rbp+250h+var_260], rax
0x140007d32  mov     [rbp+250h+var_290], rax
0x140007d36  mov     ebx, 1
0x140007d3b  mov     r15, [r8+10h]
0x140007d3f  mov     [rbp+250h+var_2A8], r15
0x140007d43  xor     edx, edx; Val
0x140007d45  mov     r8d, 208h; Size
0x140007d4b  lea     rcx, [rbp+250h+sz]; void *
0x140007d4f  call    memset_0
0x140007d54  xor     eax, eax
0x140007d56  mov     [rbp+250h+pNumArgs], eax
0x140007d59  mov     [rbp+250h+var_29C], eax
0x140007d5c  mov     [rbp+250h+var_2A0], eax
0x140007d5f  mov     [rbp+250h+var_2CC], eax
0x140007d62  test    r12d, r12d
0x140007d65  jnz     short loc_140007D89
0x140007d67  test    sil, sil
0x140007d6a  jz      short loc_140007D74
0x140007d6c  mov     r14d, 5
0x140007d72  jmp     short loc_140007D9C
0x140007d74  mov     eax, 2
0x140007d79  mov     r14d, 4
0x140007d7f  cmp     dword ptr [rdi+8], 0
0x140007d83  cmovnz  r14d, eax
0x140007d87  jmp     short loc_140007D9C
0x140007d89  mov     r14d, ebx
0x140007d8c  mov     eax, 3
0x140007d91  cmp     r12d, 4C7h
0x140007d98  cmovz   r14d, eax
0x140007d9c  mov     [rbp+250h+var_2C4], r14d
0x140007da0  mov     eax, [rdi+20h]
0x140007da3  cmp     eax, 4
0x140007da6  jnz     short loc_140007DEE
0x140007da8  lea     rcx, [rdi+0E8h]; rguid
0x140007daf  mov     r8d, 104h; cchMax
0x140007db5  lea     rdx, [rbp+250h+sz]; lpsz
0x140007db9  call    cs:__imp_StringFromGUID2
0x140007dbf  test    eax, eax
0x140007dc1  jns     short loc_140007DC9
0x140007dc3  xor     eax, eax
0x140007dc5  mov     [rbp+250h+sz], ax
0x140007dc9  mov     rsi, [rdi+0E0h]
0x140007dd0  mov     edx, 5Ch ; '\'; Ch
0x140007dd5  mov     rcx, rsi; Str
0x140007dd8  call    cs:__imp_wcsrchr
0x140007dde  lea     rcx, [rax+2]
0x140007de2  test    rax, rax
0x140007de5  cmovnz  rsi, rcx
0x140007de9  jmp     loc_140007FEB
0x140007dee  cmp     eax, 7
0x140007df1  jnz     short loc_140007E33
0x140007df3  mov     rcx, [rdi+0C8h]; unsigned __int16 *
0x140007dfa  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007dff  mov     rsi, rax
0x140007e02  mov     rbx, [rdi+0D0h]
0x140007e09  mov     edx, 2Fh ; '/'; Ch
0x140007e0e  mov     rcx, rbx; Str
0x140007e11  call    cs:__imp_wcsrchr
0x140007e17  lea     rcx, [rax+2]
0x140007e1b  test    rax, rax
0x140007e1e  cmovnz  rbx, rcx
0x140007e22  mov     r8, rbx; unsigned __int16 *
0x140007e25  lea     rcx, [rbp+250h+sz]; unsigned __int16 *
0x140007e29  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007e2e  jmp     loc_140007FEB
0x140007e33  cmp     eax, 5
0x140007e36  jnz     short loc_140007E5B
0x140007e38  mov     rcx, r15; unsigned __int16 *
0x140007e3b  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007e40  mov     r15, rax
0x140007e43  mov     [rbp+250h+var_2A8], rax
0x140007e47  mov     rcx, [rdi+0D0h]; unsigned __int16 *
0x140007e4e  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007e53  mov     rsi, rax
0x140007e56  jmp     loc_140007FEB
0x140007e5b  cmp     eax, 8
0x140007e5e  jnz     short loc_140007E95
0x140007e60  mov     rcx, [rdi+0C8h]; unsigned __int16 *
0x140007e67  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007e6c  mov     rsi, rax
0x140007e6f  mov     r15, [rdi+0E0h]
0x140007e76  mov     [rbp+250h+var_2A8], r15
0x140007e7a  xor     eax, eax
0x140007e7c  mov     [rbp+250h+sz], ax
0x140007e80  mov     r8, [rdi+0D8h]; unsigned __int16 *
0x140007e87  lea     rcx, [rbp+250h+sz]; unsigned __int16 *
0x140007e8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007e90  jmp     loc_140007FEB
0x140007e95  mov     rcx, [rdi+0D8h]; unsigned __int16 *
0x140007e9c  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007ea1  mov     rsi, rax
0x140007ea4  cmp     [r13+0], ebx
0x140007ea8  cmovbe  r15, rax
0x140007eac  mov     [rbp+250h+var_2A8], r15
0x140007eb0  xor     eax, eax
0x140007eb2  mov     [rbp+250h+sz], ax
0x140007eb6  mov     r15, [rdi+0E0h]
0x140007ebd  test    r15, r15
0x140007ec0  jz      loc_140007FD5
0x140007ec6  lea     rdx, aMmcExe; "mmc.exe"
0x140007ecd  mov     rcx, rsi; String1
0x140007ed0  call    cs:__imp__wcsicmp
0x140007ed6  test    eax, eax
0x140007ed8  jz      short loc_140007EF2
0x140007eda  lea     rdx, aRundll32Exe; "rundll32.exe"
0x140007ee1  mov     rcx, rsi; String1
0x140007ee4  call    cs:__imp__wcsicmp
0x140007eea  test    eax, eax
0x140007eec  jnz     loc_140007FD5
0x140007ef2  lea     rdx, [rbp+250h+pNumArgs]; pNumArgs
0x140007ef6  mov     rcx, r15; lpCmdLine
0x140007ef9  call    cs:__imp_CommandLineToArgvW
0x140007eff  mov     r15, rax
0x140007f02  test    rax, rax
0x140007f05  jz      loc_140007FD5
0x140007f0b  cmp     [rbp+250h+pNumArgs], ebx
0x140007f0e  jle     loc_140007FCC
0x140007f14  movsxd  rcx, ebx
0x140007f17  mov     rcx, [r15+rcx*8]; unsigned __int16 *
0x140007f1b  call    ?CuipJustFileName@@YAPEAGPEAG@Z; CuipJustFileName(ushort *)
0x140007f20  mov     r10, rax
0x140007f23  cmp     ebx, 1
0x140007f26  jz      loc_140007FAC
0x140007f2c  mov     edx, 104h
0x140007f31  lea     rcx, [rbp+250h+sz]
0x140007f35  cmp     word ptr [rcx], 0
0x140007f39  jz      short loc_140007F45
0x140007f3b  add     rcx, 2
0x140007f3f  sub     rdx, 1
0x140007f43  jnz     short loc_140007F35
0x140007f45  mov     ecx, 104h
0x140007f4a  sub     rcx, rdx
0x140007f4d  xor     eax, eax
0x140007f4f  test    rdx, rdx
0x140007f52  cmovz   rcx, rax
0x140007f56  jz      short loc_140007FCC
0x140007f58  mov     edx, 7FFFFFFEh
0x140007f5d  lea     r8, asc_1400224D4; " "
0x140007f64  mov     eax, 104h
0x140007f69  sub     rax, rcx
0x140007f6c  lea     rcx, [rbp+rcx*2+250h+sz]
0x140007f71  jz      short loc_140007F97
0x140007f73  test    rdx, rdx
0x140007f76  jz      short loc_140007F97
0x140007f78  movzx   r9d, word ptr [r8]
0x140007f7c  test    r9w, r9w
0x140007f80  jz      short loc_140007F97
0x140007f82  add     r8, 2
0x140007f86  mov     [rcx], r9w
0x140007f8a  add     rcx, 2
0x140007f8e  dec     rdx
0x140007f91  sub     rax, 1
0x140007f95  jnz     short loc_140007F73
0x140007f97  lea     rdx, [rcx-2]
0x140007f9b  test    rax, rax
0x140007f9e  cmovnz  rdx, rcx
0x140007fa2  xor     ecx, ecx
0x140007fa4  mov     [rdx], cx
0x140007fa7  test    rax, rax
0x140007faa  jz      short loc_140007FCC
0x140007fac  mov     r8, r10; unsigned __int16 *
0x140007faf  mov     edx, 104h; unsigned __int64
0x140007fb4  lea     rcx, [rbp+250h+sz]; unsigned __int16 *
0x140007fb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007fbd  test    eax, eax
0x140007fbf  js      short loc_140007FCC
0x140007fc1  inc     ebx
0x140007fc3  cmp     ebx, [rbp+250h+pNumArgs]
0x140007fc6  jl      loc_140007F14
0x140007fcc  mov     rcx, r15; hMem
0x140007fcf  call    cs:__imp_GlobalFree
0x140007fd5  mov     rcx, [rdi+18h]; void *
0x140007fd9  test    rcx, rcx
0x140007fdc  jz      short loc_140007FE7
0x140007fde  lea     rdx, [rbp+250h+var_2CC]; int *
0x140007fe2  call    ?CuipIsTokenLowIL@@YAKPEAXPEAH@Z; CuipIsTokenLowIL(void *,int *)
0x140007fe7  mov     r15, [rbp+250h+var_2A8]
0x140007feb  cmp     r14d, 1
0x140007fef  jz      loc_14000824C
0x140007ff5  lea     rbx, qword_1400210F8
0x140007ffc  cmp     [rbp+250h+var_2CC], 0
0x140008000  jz      loc_14000812D
0x140008006  mov     eax, [r13+3Ch]
0x14000800a  mov     [rbp+250h+var_2CC], eax
0x14000800d  lea     rdx, [r13+3Ah]
0x140008011  mov     rax, [r13+28h]
0x140008015  mov     rcx, rbx
0x140008018  test    rax, rax
0x14000801b  cmovnz  rcx, rax
0x14000801f  mov     [rbp+250h+var_288], rcx
0x140008023  lea     rax, [rbp+250h+sz]
0x140008027  mov     [rbp+250h+var_280], rax
0x14000802b  mov     rax, [r13+18h]
0x14000802f  mov     rcx, rbx
0x140008032  test    rax, rax
0x140008035  cmovnz  rcx, rax
0x140008039  mov     [rbp+250h+var_278], rcx
0x14000803d  mov     eax, [r13+0]
0x140008041  mov     [rbp+250h+var_2C0], eax
0x140008044  mov     rax, rbx
0x140008047  test    rsi, rsi
0x14000804a  cmovnz  rax, rsi
0x14000804e  mov     [rbp+250h+var_270], rax
0x140008052  mov     eax, [rdi+20h]
0x140008055  mov     [rbp+250h+var_2BC], eax
0x140008058  mov     rax, rbx
0x14000805b  test    r15, r15
0x14000805e  cmovnz  rax, r15
0x140008062  mov     [rbp+250h+var_268], rax
0x140008066  lea     r8, [rdi+30h]
0x14000806a  mov     eax, [r8]
0x14000806d  shr     eax, 2
0x140008070  and     al, 1
0x140008072  mov     [rbp+250h+var_2D0], al
0x140008075  mov     eax, [rdi+8]
0x140008078  mov     [rbp+250h+var_2B8], eax
0x14000807b  lea     rax, [rbp+250h+arg_38]
0x140008082  mov     [rsp+380h+var_2E8], rax
0x14000808a  lea     rax, [rbp+250h+var_290]
0x14000808e  mov     qword ptr [rsp+380h+var_2F0], rax
0x140008096  lea     rax, [rbp+250h+var_2CC]
0x14000809a  mov     qword ptr [rsp+380h+var_2F8], rax
0x1400080a2  mov     [rsp+380h+var_300], rdx
0x1400080aa  lea     rax, [rbp+250h+var_288]
0x1400080ae  mov     qword ptr [rsp+380h+var_308], rax
0x1400080b3  lea     rax, [rbp+250h+arg_28]
0x1400080ba  mov     qword ptr [rsp+380h+var_310], rax
0x1400080bf  lea     rax, [rbp+250h+var_2A0]
0x1400080c3  mov     qword ptr [rsp+380h+var_318], rax
0x1400080c8  lea     rax, [rbp+250h+var_29C]
0x1400080cc  mov     qword ptr [rsp+380h+var_320], rax
0x1400080d1  lea     rax, [rbp+250h+arg_20]
0x1400080d8  mov     [rsp+380h+var_328], rax
0x1400080dd  lea     rax, [rbp+250h+var_280]
0x1400080e1  mov     [rsp+380h+var_330], rax
0x1400080e6  lea     rax, [rbp+250h+var_278]
0x1400080ea  mov     qword ptr [rsp+380h+var_338], rax
0x1400080ef  lea     rax, [rbp+250h+var_2C0]
0x1400080f3  mov     [rsp+380h+var_340], rax
0x1400080f8  lea     rax, [rbp+250h+var_270]
0x1400080fc  mov     qword ptr [rsp+380h+var_348], rax
0x140008101  lea     rax, [rbp+250h+var_2BC]
0x140008105  mov     [rsp+380h+var_350], rax
0x14000810a  lea     rax, [rbp+250h+var_268]
0x14000810e  mov     qword ptr [rsp+380h+var_358], rax
0x140008113  lea     rax, [rbp+250h+var_2D0]
0x140008117  mov     qword ptr [rsp+380h+var_360], rax
0x14000811c  lea     r9, [rbp+250h+var_2B8]
0x140008120  lea     rdx, [rbp+250h+var_2C4]
0x140008124  lea     rcx, [rbp+250h+var_2B0]
0x140008128  call    ??$LowILConsentUILaunched@AEAKAEAKAEAKK_NPEBGKPEBGKPEBGPEBGAEAKAEAKAEAKAEAW4_AM_SCAN_RESULT@@PEBGAEAGKAEAPEBDAEA_J@CUITelemetry@@SAXAEAK00$$QEAK$$QEA_N$$QEAPEBG13133000AEAW4_AM_SCAN_RESULT@@3AEAG1AEAPEBDAEA_J@Z; CUITelemetry::LowILConsentUILaunched<ulong &,ulong &,ulong &,ulong,bool,ushort const *,ulong,ushort const *,ulong,ushort const *,ushort const *,ulong &,ulong &,ulong &,_AM_SCAN_RESULT &,ushort const *,ushort &,ulong,char const * &,__int64 &>(ulong &,ulong &,ulong &,ulong &&,bool &&,ushort const * &&,ulong &&,ushort const * &&,ulong &&,ushort const * &&,ushort const * &&,ulong &,ulong &,ulong &,_AM_SCAN_RESULT &,ushort const * &&,ushort &,ulong &&,char const * &,__int64 &)
0x14000812d  mov     eax, [r13+3Ch]
0x140008131  mov     [rbp+250h+var_2B0], eax
0x140008134  mov     rax, [r13+28h]
0x140008138  mov     r15, rbx
0x14000813b  test    rax, rax
0x14000813e  cmovnz  r15, rax
0x140008142  mov     rax, [r13+18h]
0x140008146  mov     r12, rbx
0x140008149  test    rax, rax
0x14000814c  cmovnz  r12, rax
0x140008150  mov     eax, [r13+0]
0x140008154  mov     [rbp+250h+var_2B8], eax
0x140008157  mov     r13, rbx
0x14000815a  test    rsi, rsi
0x14000815d  cmovnz  r13, rsi
0x140008161  mov     eax, [rdi+20h]
0x140008164  mov     [rbp+250h+var_2BC], eax
0x140008167  mov     rax, [rbp+250h+var_2A8]
0x14000816b  test    rax, rax
0x14000816e  cmovnz  rbx, rax
0x140008172  mov     esi, [rdi+30h]
0x140008175  shr     esi, 2
0x140008178  and     esi, 1
0x14000817b  mov     eax, [rdi+8]
0x14000817e  mov     [rbp+250h+var_2C0], eax
0x140008181  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_118efc2810da81fa517ffdfff2ec5234_@@CA@XZ; _lambda_118efc2810da81fa517ffdfff2ec5234_::_lambda_invoker_cdecl_(void)
0x140008188  call    ?get@?$static_lazy@VCUITelemetry@@@details@wil@@QEAAPEAVCUITelemetry@@P6AXXZ@Z; wil::details::static_lazy<CUITelemetry>::get(void (*)(void))
0x14000818d  mov     rax, [rax+8]
  ... truncated ...
```
