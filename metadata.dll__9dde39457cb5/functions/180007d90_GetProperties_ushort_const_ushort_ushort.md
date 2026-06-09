# GetProperties(ushort const *,ushort * *,ushort * *)

- ea: `0x180007d90`
- end: `0x1800082c5`
- name: `?GetProperties@@YAJPEBGPEAPEAG1@Z`
- size: `1333`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ff10`

## callees

- `0x180007d90`
- `0x180008a14`
- `0x18000f49c`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180007ff0`
- `IisRTL!PuDbgPrintW` at `0x18000822c`
- `IisRTL!PuDbgPrintW` at `0x180007ff0`
- `IisRTL!PuDbgPrintW` at `0x18000822c`

## string_xrefs

- `0x180007fe4`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x180008225`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x18000824c`: `[GetProperties] GetColumnValues (copy) failed with hr = 0x%x. Index: %d\n`

## pseudocode

```c
__int64 __fastcall GetProperties(unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rsi
  char *v7; // r14
  unsigned int v8; // r12d
  int v9; // r13d
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r15d
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // rax
  unsigned int *v16; // r8
  __int64 v17; // rax
  unsigned __int16 *v18; // r12
  int v19; // eax
  unsigned __int16 *v20; // rax
  void **v21; // rdi
  unsigned __int16 *v22; // rax
  unsigned __int16 **v23; // rdi
  unsigned int v24; // r12d
  __int64 v25; // r15
  int v26; // eax
  __int64 v27; // rax
  size_t v28; // rbx
  char *v29; // rdi
  char *v30; // rcx
  size_t v31; // rbx
  unsigned __int16 **v32; // r9
  size_t v33; // rbx
  unsigned __int16 *v34; // rdi
  unsigned __int16 *v35; // rcx
  size_t v36; // rbx
  unsigned __int16 *v37; // rdi
  int v38; // eax
  unsigned __int16 *v39; // r14
  unsigned __int16 *v40; // rsi
  __int64 v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+28h] [rbp-D8h]
  unsigned int v44; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v46; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-B0h] BYREF
  char *v48; // [rsp+58h] [rbp-A8h] BYREF
  int v49; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v50; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v51; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v52; // [rsp+78h] [rbp-88h]
  _QWORD v53[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v54[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int *v56; // [rsp+B8h] [rbp-48h]
  void *Src; // [rsp+C0h] [rbp-40h]
  _BYTE *v58; // [rsp+E0h] [rbp-20h]
  _DWORD *v59; // [rsp+110h] [rbp+10h]
  _DWORD *v60; // [rsp+118h] [rbp+18h]

  v51 = a3;
  v52 = a2;
  v50 = a1;
  memset_0(&v55, 0, 0x90u);
  v54[1] = 2;
  *a2 = 0;
  v53[1] = &v49;
  *a3 = 0;
  v6 = 0;
  v54[0] = 0;
  v7 = 0;
  v54[2] = 1;
  v8 = 0;
  v54[3] = 6;
  v9 = 0;
  v54[4] = 12;
  v54[5] = 13;
  v49 = 0;
  v53[0] = a1;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v44 = 0;
  v45 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)g_pGlobalISTHelper + 5)
                                                                            + 24LL))(
          *((_QWORD *)g_pGlobalISTHelper + 5),
          0,
          v53,
          &v46);
  if ( v10 < 0 )
  {
    v11 = 0;
    if ( v10 != -2145318890 )
      return (unsigned int)v10;
    return v11;
  }
  v12 = v46;
  v13 = 0;
  while ( 1 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, __int64 *))(**((_QWORD **)g_pGlobalISTHelper
                                                                                             + 5)
                                                                                          + 32LL))(
            *((_QWORD *)g_pGlobalISTHelper + 5),
            v12,
            6,
            v54,
            0,
            &v55);
    v11 = v14;
    if ( v14 == -2145318890 )
    {
LABEL_28:
      if ( v9 )
      {
        v20 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v9 + 1), 2u));
        v21 = (void **)v51;
        *v51 = v20;
        if ( !v20 )
          return (unsigned int)-2147024882;
        *v20 = 0;
        v7 = (char *)*v21;
        v48 = (char *)*v21;
      }
      if ( v8 )
      {
        v22 = (unsigned __int16 *)operator new[](saturated_mul(v8 + 1, 2u));
        v23 = v52;
        *v52 = v22;
        if ( !v22 )
          return (unsigned int)-2147024882;
        *v22 = 0;
        v6 = *v23;
        v47 = *v23;
      }
      v24 = v46;
      v25 = 0;
      while ( 1 )
      {
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, __int64 *))(**((_QWORD **)g_pGlobalISTHelper
                                                                                                 + 5)
                                                                                              + 32LL))(
                *((_QWORD *)g_pGlobalISTHelper + 5),
                v24,
                6,
                v54,
                0,
                &v55);
        v11 = v26;
        if ( v26 == -2145318890 )
          break;
        if ( v26 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v43) = v26;
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
              2006,
              "GetProperties",
              L"[GetProperties] GetColumnValues (copy) failed with hr = 0x%x. Index: %d\n",
              v43,
              v24);
          }
          return v11;
        }
        if ( !v25 )
          v25 = v55;
        if ( v25 != v55 )
          goto LABEL_58;
        if ( *v60 != 9989 && (*v59 & 0x10000) == 0 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_WORD *)Src + v27) );
          if ( (*v59 & 0x200) != 0 )
          {
            v28 = 2LL * (unsigned int)v27;
            memcpy_0(v7, Src, v28);
            v29 = &v7[v28];
            v30 = &v7[v28];
            v31 = 2LL * g_cchComma;
            memcpy_0(v30, L",", v31);
            v7 = &v29[v31];
            v48 = &v29[v31];
            v32 = (unsigned __int16 **)&v48;
          }
          else
          {
            v32 = 0;
            if ( v6 )
            {
              v33 = (unsigned int)v27;
              memcpy_0(v6, Src, v33 * 2);
              v34 = &v6[v33];
              v35 = &v6[v33];
              v36 = g_cchComma;
              memcpy_0(v35, L",", v36 * 2);
              v6 = &v34[v36];
              v47 = &v34[v36];
              v32 = &v47;
            }
          }
          if ( (*v58 & 0x40) != 0 )
          {
            v37 = v50;
            v38 = AddFlagValuesToPropertyList(v50, *v56, 0, v32);
            v11 = v38;
            if ( v38 < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrintW(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
                  2083,
                  "GetProperties",
                  L"[GetProperties] AddFlagValuesToPropertyList for %s:%s failed with hr = 0x%x.\n",
                  v37,
                  Src,
                  v38);
              return v11;
            }
            v6 = v47;
            v7 = v48;
          }
        }
        ++v24;
      }
      v11 = 0;
LABEL_58:
      if ( v9 && v7 )
      {
        v39 = (unsigned __int16 *)(v7 - 2);
        if ( v39 < *v51 )
          return (unsigned int)-2147467259;
        *v39 = 0;
      }
      if ( !v44 || !v6 )
        return v11;
      v40 = v6 - 1;
      if ( v40 >= *v52 )
      {
        *v40 = 0;
        return v11;
      }
      return (unsigned int)-2147467259;
    }
    if ( v14 < 0 )
      break;
    if ( !v13 )
      v13 = v55;
    if ( v13 != v55 )
      goto LABEL_28;
    if ( *v60 != 9989 && (*v59 & 0x10000) == 0 )
    {
      if ( (*v59 & 0x200) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *((_WORD *)Src + v15) );
        v16 = (unsigned int *)&v45;
        v9 += v15 + 1;
        v45 = v9;
      }
      else
      {
        v17 = -1;
        do
          ++v17;
        while ( *((_WORD *)Src + v17) );
        v16 = &v44;
        v8 += v17 + 1;
        v44 = v8;
      }
      if ( (*v58 & 0x40) != 0 )
      {
        v18 = v50;
        v19 = AddFlagValuesToPropertyList(v50, *v56, v16, 0);
        v11 = v19;
        if ( v19 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
              1948,
              "GetProperties",
              L"[GetProperties] AddFlagValuesToPropertyList for %s:%s failed with hr = 0x%x.\n",
              v18,
              Src,
              v19);
          return v11;
        }
        v9 = v45;
        v8 = v44;
      }
    }
    ++v12;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v42) = v14;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
      1885,
      "GetProperties",
      L"[GetProperties] GetColumnValues (count) failed with hr = 0x%x. Index: %d\n",
      v42,
      v12);
  }
  return v11;
}

```

## disassembly

```asm
0x180007d90  mov     [rsp-8+arg_18], rbx
0x180007d95  push    rbp
0x180007d96  push    rsi
0x180007d97  push    rdi
0x180007d98  push    r12
0x180007d9a  push    r13
0x180007d9c  push    r14
0x180007d9e  push    r15
0x180007da0  lea     rbp, [rsp-50h]
0x180007da5  sub     rsp, 150h
0x180007dac  mov     rax, cs:__security_cookie
0x180007db3  xor     rax, rsp
0x180007db6  mov     [rbp+80h+var_40], rax
0x180007dba  mov     rdi, r8
0x180007dbd  mov     [rsp+180h+var_110], r8
0x180007dc2  mov     r15, rdx
0x180007dc5  mov     [rsp+180h+var_108], rdx
0x180007dca  mov     rbx, rcx
0x180007dcd  mov     [rsp+180h+var_118], rcx
0x180007dd2  xor     edx, edx; Val
0x180007dd4  lea     rcx, [rbp+80h+var_D0]; void *
0x180007dd8  mov     r8d, 90h; Size
0x180007dde  call    memset_0
0x180007de3  xor     ecx, ecx
0x180007de5  mov     [rbp+80h+var_EC], 2
0x180007dec  mov     [r15], rcx
0x180007def  lea     rax, [rsp+180h+var_120]
0x180007df4  mov     [rbp+80h+var_F8], rax
0x180007df8  lea     r9, [rsp+180h+var_138]
0x180007dfd  mov     [rdi], rcx
0x180007e00  lea     r8, [rbp+80h+var_100]
0x180007e04  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180007e0b  mov     esi, ecx
0x180007e0d  mov     [rbp+80h+var_F0], ecx
0x180007e10  mov     r14d, ecx
0x180007e13  mov     [rbp+80h+var_E8], 1
0x180007e1a  mov     r12d, ecx
0x180007e1d  mov     [rbp+80h+var_E4], 6
0x180007e24  mov     r13d, ecx
0x180007e27  mov     [rbp+80h+var_E0], 0Ch
0x180007e2e  xor     edx, edx
0x180007e30  mov     [rbp+80h+var_DC], 0Dh
0x180007e37  mov     [rsp+180h+var_120], ecx
0x180007e3b  mov     [rbp+80h+var_100], rbx
0x180007e3f  mov     [rsp+180h+var_138], ecx
0x180007e43  mov     [rsp+180h+var_130], rcx
0x180007e48  mov     [rsp+180h+var_128], rcx
0x180007e4d  mov     [rsp+180h+var_140], ecx
0x180007e51  mov     [rsp+180h+var_13C], ecx
0x180007e55  mov     rcx, [rax+28h]
0x180007e59  mov     rax, [rcx]
0x180007e5c  mov     rax, [rax+18h]
0x180007e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e65  xor     r8d, r8d
0x180007e68  test    eax, eax
0x180007e6a  jns     short loc_180007E7C
0x180007e6c  cmp     eax, 80210816h
0x180007e71  mov     ebx, r8d
0x180007e74  cmovnz  ebx, eax
0x180007e77  jmp     loc_18000829C
0x180007e7c  mov     r15d, [rsp+180h+var_138]
0x180007e81  mov     rdi, r8
0x180007e84  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180007e8b  lea     rdx, [rbp+80h+var_D0]
0x180007e8f  mov     [rsp+180h+var_158], rdx
0x180007e94  lea     r9, [rbp+80h+var_F0]
0x180007e98  mov     [rsp+180h+var_160], r8
0x180007e9d  mov     edx, r15d
0x180007ea0  mov     r8d, 6
0x180007ea6  mov     rcx, [rax+28h]
0x180007eaa  mov     rax, [rcx]
0x180007ead  mov     rax, [rax+20h]
0x180007eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb6  xor     r8d, r8d
0x180007eb9  mov     ebx, eax
0x180007ebb  cmp     eax, 80210816h
0x180007ec0  jz      loc_180007FFB
0x180007ec6  test    eax, eax
0x180007ec8  js      loc_180007FB3
0x180007ece  test    rdi, rdi
0x180007ed1  cmovz   rdi, [rbp+80h+var_D0]
0x180007ed6  cmp     rdi, [rbp+80h+var_D0]
0x180007eda  jnz     loc_180007FFB
0x180007ee0  mov     rax, [rbp+80h+var_68]
0x180007ee4  cmp     dword ptr [rax], 2705h
0x180007eea  jz      loc_180007F81
0x180007ef0  mov     rax, [rbp+80h+var_70]
0x180007ef4  test    dword ptr [rax], 10000h
0x180007efa  jnz     loc_180007F81
0x180007f00  test    dword ptr [rax], 200h
0x180007f06  mov     rcx, [rbp+80h+Src]
0x180007f0a  jz      short loc_180007F2C
0x180007f0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007f10  inc     rax
0x180007f13  cmp     [rcx+rax*2], r8w
0x180007f18  jnz     short loc_180007F10
0x180007f1a  inc     r13d
0x180007f1d  lea     r8, [rsp+180h+var_13C]
0x180007f22  add     r13d, eax
0x180007f25  mov     [rsp+180h+var_13C], r13d
0x180007f2a  jmp     short loc_180007F4A
0x180007f2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007f30  inc     rax
0x180007f33  cmp     [rcx+rax*2], r8w
0x180007f38  jnz     short loc_180007F30
0x180007f3a  inc     r12d
0x180007f3d  lea     r8, [rsp+180h+var_140]; unsigned int *
0x180007f42  add     r12d, eax
0x180007f45  mov     [rsp+180h+var_140], r12d
0x180007f4a  mov     rax, [rbp+80h+var_A0]
0x180007f4e  test    byte ptr [rax], 40h
0x180007f51  jz      short loc_180007F7E
0x180007f53  mov     rdx, [rbp+80h+var_C8]
0x180007f57  xor     r9d, r9d; unsigned __int16 **
0x180007f5a  mov     r12, [rsp+180h+var_118]
0x180007f5f  mov     rcx, r12; unsigned __int16 *
0x180007f62  mov     edx, [rdx]; unsigned int
0x180007f64  call    ?AddFlagValuesToPropertyList@@YAJPEAGKPEAKPEAPEAG@Z; AddFlagValuesToPropertyList(ushort *,ulong,ulong *,ushort * *)
0x180007f69  xor     r8d, r8d
0x180007f6c  mov     ebx, eax
0x180007f6e  test    eax, eax
0x180007f70  js      short loc_180007F89
0x180007f72  mov     r13d, [rsp+180h+var_13C]
0x180007f77  mov     r12d, [rsp+180h+var_140]
0x180007f7c  jmp     short loc_180007F81
0x180007f7e  xor     r8d, r8d
0x180007f81  inc     r15d
0x180007f84  jmp     loc_180007E84
0x180007f89  test    byte ptr cs:g_dwDebugFlags, 3
0x180007f90  jz      loc_18000829C
0x180007f96  mov     [rsp+180h+var_148], eax
0x180007f9a  mov     r8d, 79Ch
0x180007fa0  mov     rax, [rbp+80h+Src]
0x180007fa4  mov     [rsp+180h+var_150], rax
0x180007fa9  mov     [rsp+180h+var_158], r12
0x180007fae  jmp     loc_18000820B
0x180007fb3  test    byte ptr cs:g_dwDebugFlags, 3
0x180007fba  jz      loc_18000829C
0x180007fc0  mov     dword ptr [rsp+180h+var_150], r15d
0x180007fc5  mov     r8d, 75Dh
0x180007fcb  mov     dword ptr [rsp+180h+var_158], eax
0x180007fcf  lea     rax, aGetpropertiesG; "[GetProperties] GetColumnValues (count)"...
0x180007fd6  mov     rcx, cs:g_pDebug
0x180007fdd  lea     r9, aGetproperties; "GetProperties"
0x180007fe4  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x180007feb  mov     [rsp+180h+var_160], rax
0x180007ff0  call    cs:__imp_PuDbgPrintW
0x180007ff6  jmp     loc_18000829C
0x180007ffb  test    r13d, r13d
0x180007ffe  jz      short loc_180008047
0x180008000  lea     ecx, [r13+1]
0x180008004  mov     eax, 2
0x180008009  mul     rcx
0x18000800c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008013  cmovb   rax, rbx
0x180008017  mov     rcx, rax; unsigned __int64
0x18000801a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000801f  mov     rdi, [rsp+180h+var_110]
0x180008024  xor     r8d, r8d
0x180008027  mov     [rdi], rax
0x18000802a  test    rax, rax
0x18000802d  jnz     short loc_180008039
0x18000802f  mov     ebx, 8007000Eh
0x180008034  jmp     loc_18000829C
0x180008039  mov     [rax], r8w
0x18000803d  mov     r14, [rdi]
0x180008040  mov     [rsp+180h+var_128], r14
0x180008045  jmp     short loc_18000804B
0x180008047  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000804b  test    r12d, r12d
0x18000804e  jz      short loc_180008085
0x180008050  lea     ecx, [r12+1]
0x180008055  mov     eax, 2
0x18000805a  mul     rcx
0x18000805d  cmovb   rax, rbx
0x180008061  mov     rcx, rax; unsigned __int64
0x180008064  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008069  mov     rdi, [rsp+180h+var_108]
0x18000806e  xor     r8d, r8d
0x180008071  mov     [rdi], rax
0x180008074  test    rax, rax
0x180008077  jz      short loc_18000802F
0x180008079  mov     [rax], r8w
0x18000807d  mov     rsi, [rdi]
0x180008080  mov     [rsp+180h+var_130], rsi
0x180008085  mov     r12d, [rsp+180h+var_138]
0x18000808a  mov     r15, r8
0x18000808d  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180008094  lea     rdx, [rbp+80h+var_D0]
0x180008098  mov     [rsp+180h+var_158], rdx
0x18000809d  lea     r9, [rbp+80h+var_F0]
0x1800080a1  mov     [rsp+180h+var_160], r8
0x1800080a6  mov     edx, r12d
0x1800080a9  mov     r8d, 6
0x1800080af  mov     rcx, [rax+28h]
0x1800080b3  mov     rax, [rcx]
0x1800080b6  mov     rax, [rax+20h]
0x1800080ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bf  xor     r8d, r8d
0x1800080c2  mov     ebx, eax
0x1800080c4  cmp     eax, 80210816h
0x1800080c9  jz      loc_180008258
0x1800080cf  test    eax, eax
0x1800080d1  js      loc_180008234
0x1800080d7  test    r15, r15
0x1800080da  cmovz   r15, [rbp+80h+var_D0]
0x1800080df  cmp     r15, [rbp+80h+var_D0]
0x1800080e3  jnz     loc_18000825B
0x1800080e9  mov     rax, [rbp+80h+var_68]
0x1800080ed  cmp     dword ptr [rax], 2705h
0x1800080f3  jz      loc_1800081DE
0x1800080f9  mov     rax, [rbp+80h+var_70]
0x1800080fd  mov     ecx, [rax]
0x1800080ff  bt      ecx, 10h
0x180008103  jb      loc_1800081DE
0x180008109  mov     rdx, [rbp+80h+Src]; Src
0x18000810d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008111  inc     rax
0x180008114  cmp     [rdx+rax*2], r8w
0x180008119  jnz     short loc_180008111
0x18000811b  bt      ecx, 9
0x18000811f  jnb     short loc_180008162
0x180008121  mov     eax, eax
0x180008123  mov     rcx, r14; void *
0x180008126  lea     rbx, [rax+rax]
0x18000812a  mov     r8, rbx; Size
0x18000812d  call    memcpy_0
0x180008132  mov     eax, cs:?g_cchComma@@3KA; ulong g_cchComma
0x180008138  lea     rdi, [rbx+r14]
0x18000813c  lea     rdx, asc_180033CF0; ","
0x180008143  mov     rcx, rdi; void *
0x180008146  lea     rbx, [rax+rax]
0x18000814a  mov     r8, rbx; Size
0x18000814d  call    memcpy_0
0x180008152  lea     r14, [rdi+rbx]
0x180008156  mov     [rsp+180h+var_128], r14
0x18000815b  lea     r9, [rsp+180h+var_128]
0x180008160  jmp     short loc_1800081A9
0x180008162  mov     r9, r8
0x180008165  test    rsi, rsi
0x180008168  jz      short loc_1800081AC
0x18000816a  mov     eax, eax
0x18000816c  mov     rcx, rsi; void *
0x18000816f  lea     rbx, [rax+rax]
0x180008173  mov     r8, rbx; Size
0x180008176  call    memcpy_0
0x18000817b  mov     eax, cs:?g_cchComma@@3KA; ulong g_cchComma
0x180008181  lea     rdi, [rbx+rsi]
0x180008185  lea     rdx, asc_180033CF0; ","
0x18000818c  mov     rcx, rdi; void *
0x18000818f  lea     rbx, [rax+rax]
0x180008193  mov     r8, rbx; Size
0x180008196  call    memcpy_0
0x18000819b  lea     rsi, [rdi+rbx]
0x18000819f  mov     [rsp+180h+var_130], rsi
0x1800081a4  lea     r9, [rsp+180h+var_130]; unsigned __int16 **
0x1800081a9  xor     r8d, r8d
0x1800081ac  mov     rax, [rbp+80h+var_A0]
0x1800081b0  test    byte ptr [rax], 40h
0x1800081b3  jz      short loc_1800081DE
0x1800081b5  mov     rdx, [rbp+80h+var_C8]
0x1800081b9  xor     r8d, r8d; unsigned int *
0x1800081bc  mov     rdi, [rsp+180h+var_118]
0x1800081c1  mov     rcx, rdi; unsigned __int16 *
0x1800081c4  mov     edx, [rdx]; unsigned int
0x1800081c6  call    ?AddFlagValuesToPropertyList@@YAJPEAGKPEAKPEAPEAG@Z; AddFlagValuesToPropertyList(ushort *,ulong,ulong *,ushort * *)
0x1800081cb  xor     r8d, r8d
0x1800081ce  mov     ebx, eax
0x1800081d0  test    eax, eax
0x1800081d2  js      short loc_1800081E6
0x1800081d4  mov     rsi, [rsp+180h+var_130]
0x1800081d9  mov     r14, [rsp+180h+var_128]
0x1800081de  inc     r12d
0x1800081e1  jmp     loc_18000808D
0x1800081e6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800081ed  jz      loc_18000829C
0x1800081f3  mov     [rsp+180h+var_148], eax
0x1800081f7  mov     r8d, 823h
0x1800081fd  mov     rax, [rbp+80h+Src]
0x180008201  mov     [rsp+180h+var_150], rax
0x180008206  mov     [rsp+180h+var_158], rdi
0x18000820b  mov     rcx, cs:g_pDebug
0x180008212  lea     rax, aGetpropertiesA; "[GetProperties] AddFlagValuesToProperty"...
0x180008219  lea     r9, aGetproperties; "GetProperties"
0x180008220  mov     [rsp+180h+var_160], rax
0x180008225  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18000822c  call    cs:__imp_PuDbgPrintW
0x180008232  jmp     short loc_18000829C
0x180008234  test    byte ptr cs:g_dwDebugFlags, 3
0x18000823b  jz      short loc_18000829C
0x18000823d  mov     dword ptr [rsp+180h+var_150], r12d
0x180008242  mov     r8d, 7D6h
0x180008248  mov     dword ptr [rsp+180h+var_158], eax
0x18000824c  lea     rax, aGetpropertiesG_0; "[GetProperties] GetColumnValues (copy) "...
0x180008253  jmp     loc_180007FD6
0x180008258  mov     ebx, r8d
0x18000825b  test    r13d, r13d
0x18000825e  jz      short loc_180008277
0x180008260  test    r14, r14
0x180008263  jz      short loc_180008277
  ... truncated ...
```
