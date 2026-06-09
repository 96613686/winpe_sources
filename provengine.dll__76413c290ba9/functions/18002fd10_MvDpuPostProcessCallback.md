# MvDpuPostProcessCallback

- ea: `0x18002fd10`
- end: `0x180030627`
- name: `MvDpuPostProcessCallback`
- size: `2327`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002fd10`

## callees

- `0x1800098dc`
- `0x18000b030`
- `0x180021f40`
- `0x18002fa98`
- `0x18002fcb8`
- `0x18002fd10`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180030167`
- `msvcrt!_wcsicmp` at `0x180030167`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fecf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ff78`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030028`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030116`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030216`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800302d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800303bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030478`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030539`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800305ce`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fecf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ff78`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030028`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030116`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030216`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800302d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800303bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030478`
- `msvcrt!??3@YAXPEAX@Z` at `0x180030539`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800305ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fdd8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002feb8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fef1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff61`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180030011`
- `OLEAUT32!__imp_SysFreeString` at `0x18003004a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800300ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180030142`
- `OLEAUT32!__imp_SysFreeString` at `0x1800301ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18003023c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800303a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800303e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180030461`
- `OLEAUT32!__imp_SysFreeString` at `0x18003049e`
- `OLEAUT32!__imp_SysFreeString` at `0x180030522`
- `OLEAUT32!__imp_SysFreeString` at `0x18003055f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800305b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800305f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fdd8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002feb8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fef1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff61`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180030011`
- `OLEAUT32!__imp_SysFreeString` at `0x18003004a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800300ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180030142`
- `OLEAUT32!__imp_SysFreeString` at `0x1800301ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18003023c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800303a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800303e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180030461`
- `OLEAUT32!__imp_SysFreeString` at `0x18003049e`
- `OLEAUT32!__imp_SysFreeString` at `0x180030522`
- `OLEAUT32!__imp_SysFreeString` at `0x18003055f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800305b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800305f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe66`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MvDpuPostProcessCallback(const struct ProvStateContext *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  const OLECHAR *v11; // rdx
  HRESULT Instance; // eax
  unsigned int v13; // ebx
  struct IConfigManager2URI *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  struct IConfigManager2URI *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  struct IConfigManager2URI *v20; // rcx
  unsigned int i; // esi
  __int64 v22; // r14
  unsigned int j; // ebx
  bool v24; // zf
  int v25; // eax
  unsigned int v26; // edi
  struct IConfigManager2URI *v27; // rcx
  __int64 v28; // rdi
  _WORD *v29; // rcx
  int v30; // eax
  unsigned int v31; // ebx
  struct IConfigManager2URI *v32; // rcx
  int v33; // eax
  unsigned int v34; // ebx
  struct IConfigManager2URI *v35; // rcx
  unsigned int v36; // ebx
  __int64 v37; // r14
  int v38; // eax
  unsigned int v39; // edi
  wchar_t *v40; // rcx
  struct IConfigManager2URI *v41; // rcx
  wchar_t *v42; // rcx
  struct IConfigManager2URI *v43; // rcx
  int v44; // eax
  unsigned int v45; // edi
  wchar_t *v46; // rcx
  struct IConfigManager2URI *v47; // rcx
  wchar_t *v48; // rcx
  struct IConfigManager2URI *v49; // rcx
  int ppv; // [rsp+20h] [rbp-A8h]
  int ppva; // [rsp+20h] [rbp-A8h]
  struct IConfigManager2URI *v52; // [rsp+30h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-90h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-80h] BYREF
  BSTR v56; // [rsp+50h] [rbp-78h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-70h] BYREF
  __int64 v58; // [rsp+60h] [rbp-68h]
  const void *Src[2]; // [rsp+68h] [rbp-60h] BYREF
  __int64 v60; // [rsp+78h] [rbp-50h]
  unsigned __int64 v61; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v58 = a4;
  if ( !a2 )
  {
    v7 = 84;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
      (const char *)0x80004003LL,
      ppv);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v7 = 85;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v7 = 86;
    goto LABEL_3;
  }
  if ( !a1 )
  {
    v7 = 87;
    goto LABEL_3;
  }
  bstrString = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, &bstrString);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v61 = 7;
    v60 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src, (char *)L".", 1u);
    std::wstring::append(Src, (char *)bstrString);
    v11 = (const OLECHAR *)Src;
    if ( v61 >= 8 )
      v11 = (const OLECHAR *)Src[0];
    wil::make_bstr(&v56, v11);
    v52 = 0;
    Instance = CoCreateInstance(
                 &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
                 0,
                 1u,
                 &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
                 (LPVOID *)&v52);
    v13 = Instance;
    if ( Instance >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, BSTR))(*(_QWORD *)v52 + 40LL))(v52, v56);
      v16 = v15;
      if ( v15 >= 0 )
      {
        v57 = 0;
        v18 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)v52 + 136LL))(
                v52,
                &v57);
        v19 = v18;
        if ( v18 >= 0 )
        {
          for ( i = 0; i < 4; ++i )
          {
            v22 = 32LL * (int)i;
            if ( v57 - 2 == *(_DWORD *)((char *)&gc_MvUndoTable + v22 + 24) )
            {
              for ( j = 2; ; ++j )
              {
                v24 = v57 == j;
                if ( v57 <= j )
                  break;
                String1 = 0;
                v25 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, wchar_t **))(*(_QWORD *)v52 + 88LL))(
                        v52,
                        j,
                        &String1);
                v26 = v25;
                if ( v25 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7C,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
                    (const char *)(unsigned int)v25,
                    ppva);
                  v27 = v52;
                  if ( v52 )
                  {
                    v52 = 0;
                    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v27 + 16LL))(v27);
                  }
                  if ( v56 )
                    SysFreeString(v56);
                  if ( v61 >= 8 )
                    operator delete((void *)Src[0]);
                  v61 = 7;
                  v60 = 0;
                  LOWORD(Src[0]) = 0;
                  if ( bstrString )
                    SysFreeString(bstrString);
                  return v26;
                }
                v28 = j - 2;
                if ( _wcsicmp(String1, (*(const wchar_t ***)((char *)&gc_MvUndoTable + v22 + 16))[v28]) )
                {
                  v29 = (_WORD *)(*(_QWORD **)((char *)&gc_MvUndoTable + v22 + 16))[v28];
                  if ( *v29 != 42 || v29[1] )
                  {
                    v24 = v57 == j;
                    break;
                  }
                }
              }
              if ( !v24 )
                continue;
              v30 = MvSaveNodeForUndo(a1, v52);
              v31 = v30;
              if ( v30 >= 0 )
                continue;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x89,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
                (const char *)(unsigned int)v30,
                ppva);
              v32 = v52;
              if ( v52 )
              {
                v52 = 0;
                (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v32 + 16LL))(v32);
              }
              if ( v56 )
                SysFreeString(v56);
              if ( v61 >= 8 )
                operator delete((void *)Src[0]);
              v61 = 7;
              v60 = 0;
              LOWORD(Src[0]) = 0;
              if ( bstrString )
                SysFreeString(bstrString);
              return v31;
            }
          }
          v55 = 0;
          v33 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 200LL))(a2, &v55);
          v34 = v33;
          if ( v33 >= 0 )
          {
            v36 = 0;
            v37 = v58;
            while ( v36 < v55 )
            {
              String1 = 0;
              v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 192LL))(a2, v36, &String1);
              v39 = v38;
              if ( v38 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x94,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
                  (const char *)(unsigned int)v38,
                  ppva);
                v40 = String1;
                if ( String1 )
                {
                  String1 = 0;
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
                }
                v41 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v41 + 16LL))(v41);
                }
                if ( v56 )
                  SysFreeString(v56);
                if ( v61 >= 8 )
                  operator delete((void *)Src[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(Src[0]) = 0;
                if ( bstrString )
                  SysFreeString(bstrString);
                return v39;
              }
              if ( !String1 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x95,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
                  (const char *)0x8007000ELL,
                  ppva);
                v42 = String1;
                if ( String1 )
                {
                  String1 = 0;
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v42 + 16LL))(v42);
                }
                v43 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v43 + 16LL))(v43);
                }
                if ( v56 )
                  SysFreeString(v56);
                if ( v61 >= 8 )
                  operator delete((void *)Src[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(Src[0]) = 0;
                if ( bstrString )
                  SysFreeString(bstrString);
                return 2147942414LL;
              }
              v44 = MvDpuPostProcessCallback(a1, String1, a3, v37);
              v45 = v44;
              if ( v44 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x98,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
                  (const char *)(unsigned int)v44,
                  ppva);
                v46 = String1;
                if ( String1 )
                {
                  String1 = 0;
                  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v46 + 16LL))(v46);
                }
                v47 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v47 + 16LL))(v47);
                }
                if ( v56 )
                  SysFreeString(v56);
                if ( v61 >= 8 )
                  operator delete((void *)Src[0]);
                v61 = 7;
                v60 = 0;
                LOWORD(Src[0]) = 0;
                if ( bstrString )
                  SysFreeString(bstrString);
                return v45;
              }
              v48 = String1;
              if ( String1 )
              {
                String1 = 0;
                (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v48 + 16LL))(v48);
              }
              ++v36;
            }
            v49 = v52;
            if ( v52 )
            {
              v52 = 0;
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v49 + 16LL))(v49);
            }
            if ( v56 )
              SysFreeString(v56);
            if ( v61 >= 8 )
              operator delete((void *)Src[0]);
            v61 = 7;
            v60 = 0;
            LOWORD(Src[0]) = 0;
            if ( bstrString )
              SysFreeString(bstrString);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x90,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
              (const char *)(unsigned int)v33,
              ppva);
            v35 = v52;
            if ( v52 )
            {
              v52 = 0;
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v35 + 16LL))(v35);
            }
            if ( v56 )
              SysFreeString(v56);
            if ( v61 >= 8 )
              operator delete((void *)Src[0]);
            v61 = 7;
            v60 = 0;
            LOWORD(Src[0]) = 0;
            if ( bstrString )
              SysFreeString(bstrString);
            return v34;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
            (const char *)(unsigned int)v18,
            ppva);
          v20 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( v56 )
            SysFreeString(v56);
          if ( v61 >= 8 )
            operator delete((void *)Src[0]);
          v61 = 7;
          v60 = 0;
          LOWORD(Src[0]) = 0;
          if ( bstrString )
            SysFreeString(bstrString);
          return v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
          (const char *)(unsigned int)v15,
          ppva);
        v17 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v17 + 16LL))(v17);
        }
        if ( v56 )
          SysFreeString(v56);
        if ( v61 >= 8 )
          operator delete((void *)Src[0]);
        v61 = 7;
        v60 = 0;
        LOWORD(Src[0]) = 0;
        if ( bstrString )
          SysFreeString(bstrString);
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
      v14 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      if ( v56 )
        SysFreeString(v56);
      if ( v61 >= 8 )
        operator delete((void *)Src[0]);
      v61 = 7;
      v60 = 0;
      LOWORD(Src[0]) = 0;
      if ( bstrString )
        SysFreeString(bstrString);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\mvdpupostprocesscallback.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    if ( bstrString )
      SysFreeString(bstrString);
    return v10;
  }
}

```

## disassembly

```asm
0x18002fd10  push    rbx
0x18002fd12  push    rsi
0x18002fd13  push    rdi
0x18002fd14  push    r12
0x18002fd16  push    r13
0x18002fd18  push    r14
0x18002fd1a  push    r15
0x18002fd1c  sub     rsp, 90h
0x18002fd23  mov     rax, cs:__security_cookie
0x18002fd2a  xor     rax, rsp
0x18002fd2d  mov     [rsp+0C8h+var_40], rax
0x18002fd35  mov     [rsp+0C8h+var_68], r9
0x18002fd3a  mov     r13, r8
0x18002fd3d  mov     r15, rdx
0x18002fd40  mov     r12, rcx
0x18002fd43  xor     edi, edi
0x18002fd45  test    rdx, rdx
0x18002fd48  jnz     short loc_18002FD70
0x18002fd4a  lea     edx, [rdi+54h]; void *
0x18002fd4d  mov     ebx, 80004003h
0x18002fd52  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fd59  mov     r9d, ebx; char *
0x18002fd5c  mov     rcx, [rsp+0C8h]; this
0x18002fd64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd69  mov     eax, ebx
0x18002fd6b  jmp     loc_180030603
0x18002fd70  test    r13, r13
0x18002fd73  jnz     short loc_18002FD7B
0x18002fd75  lea     edx, [r13+55h]
0x18002fd79  jmp     short loc_18002FD4D
0x18002fd7b  test    r9, r9
0x18002fd7e  jnz     short loc_18002FD86
0x18002fd80  lea     edx, [r9+56h]
0x18002fd84  jmp     short loc_18002FD4D
0x18002fd86  test    r12, r12
0x18002fd89  jnz     short loc_18002FD92
0x18002fd8b  lea     edx, [r12+57h]
0x18002fd90  jmp     short loc_18002FD4D
0x18002fd92  mov     [rsp+0C8h+bstrString], rdi
0x18002fd97  mov     rax, [rdx]
0x18002fd9a  lea     rdx, [rsp+0C8h+bstrString]
0x18002fd9f  mov     rcx, r15
0x18002fda2  mov     rax, [rax+50h]
0x18002fda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdab  mov     ebx, eax
0x18002fdad  test    eax, eax
0x18002fdaf  jns     short loc_18002FDE5
0x18002fdb1  mov     rcx, [rsp+0C8h]; this
0x18002fdb9  mov     r9d, eax; char *
0x18002fdbc  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fdc3  mov     edx, 61h ; 'a'; void *
0x18002fdc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fdcd  nop
0x18002fdce  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18002fdd3  test    rcx, rcx
0x18002fdd6  jz      short loc_18002FDDE
0x18002fdd8  call    cs:__imp_SysFreeString
0x18002fdde  mov     eax, ebx
0x18002fde0  jmp     loc_180030603
0x18002fde5  mov     r14d, 7
0x18002fdeb  mov     [rsp+0C8h+var_48], r14
0x18002fdf3  mov     [rsp+0C8h+var_50], rdi
0x18002fdf8  mov     word ptr [rsp+0C8h+Src], di
0x18002fdfd  lea     ebx, [r14-6]
0x18002fe01  mov     r8d, ebx
0x18002fe04  lea     rdx, asc_18004C634; "."
0x18002fe0b  lea     rcx, [rsp+0C8h+Src]; void *
0x18002fe10  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002fe15  nop
0x18002fe16  mov     rdx, [rsp+0C8h+bstrString]; void *
0x18002fe1b  lea     rcx, [rsp+0C8h+Src]; Src
0x18002fe20  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18002fe25  lea     rdx, [rsp+0C8h+Src]
0x18002fe2a  cmp     [rsp+0C8h+var_48], 8
0x18002fe33  cmovnb  rdx, [rsp+0C8h+Src]
0x18002fe39  lea     rcx, [rsp+0C8h+var_78]
0x18002fe3e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002fe43  nop
0x18002fe44  mov     [rsp+0C8h+var_98], rdi
0x18002fe49  lea     rax, [rsp+0C8h+var_98]
0x18002fe4e  mov     qword ptr [rsp+0C8h+ppv], rax; int
0x18002fe53  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x18002fe5a  mov     r8d, ebx; dwClsContext
0x18002fe5d  xor     edx, edx; pUnkOuter
0x18002fe5f  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x18002fe66  call    cs:__imp_CoCreateInstance
0x18002fe6c  mov     ebx, eax
0x18002fe6e  test    eax, eax
0x18002fe70  jns     loc_18002FEFE
0x18002fe76  mov     rcx, [rsp+0C8h]; this
0x18002fe7e  mov     r9d, eax; char *
0x18002fe81  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002fe88  lea     edx, [r14+62h]; void *
0x18002fe8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe91  nop
0x18002fe92  mov     rcx, [rsp+0C8h+var_98]
0x18002fe97  test    rcx, rcx
0x18002fe9a  jz      short loc_18002FEAE
0x18002fe9c  mov     [rsp+0C8h+var_98], rdi
0x18002fea1  mov     rax, [rcx]
0x18002fea4  mov     rax, [rax+10h]
0x18002fea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fead  nop
0x18002feae  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x18002feb3  test    rcx, rcx
0x18002feb6  jz      short loc_18002FEBF
0x18002feb8  call    cs:__imp_SysFreeString
0x18002febe  nop
0x18002febf  cmp     [rsp+0C8h+var_48], 8
0x18002fec8  jb      short loc_18002FED5
0x18002feca  mov     rcx, [rsp+0C8h+Src]
0x18002fecf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002fed5  mov     [rsp+0C8h+var_48], r14
0x18002fedd  mov     [rsp+0C8h+var_50], rdi
0x18002fee2  mov     word ptr [rsp+0C8h+Src], di
0x18002fee7  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18002feec  test    rcx, rcx
0x18002feef  jz      short loc_18002FEF7
0x18002fef1  call    cs:__imp_SysFreeString
0x18002fef7  mov     eax, ebx
0x18002fef9  jmp     loc_180030603
0x18002fefe  mov     rcx, [rsp+0C8h+var_98]
0x18002ff03  mov     rax, [rcx]
0x18002ff06  mov     rdx, [rsp+0C8h+var_78]
0x18002ff0b  mov     rax, [rax+28h]
0x18002ff0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff14  mov     ebx, eax
0x18002ff16  test    eax, eax
0x18002ff18  jns     loc_18002FFA7
0x18002ff1e  mov     rcx, [rsp+0C8h]; this
0x18002ff26  mov     r9d, eax; char *
0x18002ff29  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ff30  mov     edx, 6Ah ; 'j'; void *
0x18002ff35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff3a  nop
0x18002ff3b  mov     rcx, [rsp+0C8h+var_98]
0x18002ff40  test    rcx, rcx
0x18002ff43  jz      short loc_18002FF57
0x18002ff45  mov     [rsp+0C8h+var_98], rdi
0x18002ff4a  mov     rax, [rcx]
0x18002ff4d  mov     rax, [rax+10h]
0x18002ff51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff56  nop
0x18002ff57  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x18002ff5c  test    rcx, rcx
0x18002ff5f  jz      short loc_18002FF68
0x18002ff61  call    cs:__imp_SysFreeString
0x18002ff67  nop
0x18002ff68  cmp     [rsp+0C8h+var_48], 8
0x18002ff71  jb      short loc_18002FF7E
0x18002ff73  mov     rcx, [rsp+0C8h+Src]
0x18002ff78  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002ff7e  mov     [rsp+0C8h+var_48], r14
0x18002ff86  mov     [rsp+0C8h+var_50], rdi
0x18002ff8b  mov     word ptr [rsp+0C8h+Src], di
0x18002ff90  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18002ff95  test    rcx, rcx
0x18002ff98  jz      short loc_18002FFA0
0x18002ff9a  call    cs:__imp_SysFreeString
0x18002ffa0  mov     eax, ebx
0x18002ffa2  jmp     loc_180030603
0x18002ffa7  mov     [rsp+0C8h+var_70], edi
0x18002ffab  mov     rcx, [rsp+0C8h+var_98]
0x18002ffb0  mov     rax, [rcx]
0x18002ffb3  lea     rdx, [rsp+0C8h+var_70]
0x18002ffb8  mov     rax, [rax+88h]
0x18002ffbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffc4  mov     ebx, eax
0x18002ffc6  test    eax, eax
0x18002ffc8  jns     loc_180030057
0x18002ffce  mov     rcx, [rsp+0C8h]; this
0x18002ffd6  mov     r9d, eax; char *
0x18002ffd9  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ffe0  mov     edx, 6Dh ; 'm'; void *
0x18002ffe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ffea  nop
0x18002ffeb  mov     rcx, [rsp+0C8h+var_98]
0x18002fff0  test    rcx, rcx
0x18002fff3  jz      short loc_180030007
0x18002fff5  mov     [rsp+0C8h+var_98], rdi
0x18002fffa  mov     rax, [rcx]
0x18002fffd  mov     rax, [rax+10h]
0x180030001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030006  nop
0x180030007  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x18003000c  test    rcx, rcx
0x18003000f  jz      short loc_180030018
0x180030011  call    cs:__imp_SysFreeString
0x180030017  nop
0x180030018  cmp     [rsp+0C8h+var_48], 8
0x180030021  jb      short loc_18003002E
0x180030023  mov     rcx, [rsp+0C8h+Src]
0x180030028  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003002e  mov     [rsp+0C8h+var_48], r14
0x180030036  mov     [rsp+0C8h+var_50], rdi
0x18003003b  mov     word ptr [rsp+0C8h+Src], di
0x180030040  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x180030045  test    rcx, rcx
0x180030048  jz      short loc_180030050
0x18003004a  call    cs:__imp_SysFreeString
0x180030050  mov     eax, ebx
0x180030052  jmp     loc_180030603
0x180030057  mov     esi, edi
0x180030059  lea     rcx, ?gc_MvUndoTable@@3PAUCspUndoRule@@A; CspUndoRule near * gc_MvUndoTable
0x180030060  cmp     esi, 4
0x180030063  jnb     loc_180030259
0x180030069  movsxd  r14, esi
0x18003006c  shl     r14, 5
0x180030070  mov     eax, [rsp+0C8h+var_70]
0x180030074  add     eax, 0FFFFFFFEh
0x180030077  cmp     eax, [r14+rcx+18h]
0x18003007c  jnz     loc_180030249
0x180030082  mov     ebx, 2
0x180030087  cmp     [rsp+0C8h+var_70], ebx
0x18003008b  jbe     loc_18003019F
0x180030091  mov     [rsp+0C8h+String1], rdi
0x180030096  mov     rcx, [rsp+0C8h+var_98]
0x18003009b  mov     rax, [rcx]
0x18003009e  lea     r8, [rsp+0C8h+String1]
0x1800300a3  mov     edx, ebx
0x1800300a5  mov     rax, [rax+58h]
0x1800300a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ae  mov     edi, eax
0x1800300b0  test    eax, eax
0x1800300b2  jns     loc_18003014F
0x1800300b8  mov     rcx, [rsp+0C8h]; this
0x1800300c0  mov     r9d, eax; char *
0x1800300c3  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800300ca  mov     edx, 7Ch ; '|'; void *
0x1800300cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300d4  nop
0x1800300d5  mov     rcx, [rsp+0C8h+var_98]
0x1800300da  test    rcx, rcx
0x1800300dd  jz      short loc_1800300F5
0x1800300df  mov     [rsp+0C8h+var_98], 0
0x1800300e8  mov     rax, [rcx]
0x1800300eb  mov     rax, [rax+10h]
0x1800300ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f4  nop
0x1800300f5  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x1800300fa  test    rcx, rcx
0x1800300fd  jz      short loc_180030106
0x1800300ff  call    cs:__imp_SysFreeString
0x180030105  nop
0x180030106  cmp     [rsp+0C8h+var_48], 8
0x18003010f  jb      short loc_18003011C
0x180030111  mov     rcx, [rsp+0C8h+Src]
0x180030116  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003011c  mov     [rsp+0C8h+var_48], 7
0x180030128  mov     [rsp+0C8h+var_50], 0
0x180030131  xor     eax, eax
0x180030133  mov     word ptr [rsp+0C8h+Src], ax
0x180030138  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18003013d  test    rcx, rcx
0x180030140  jz      short loc_180030148
0x180030142  call    cs:__imp_SysFreeString
0x180030148  mov     eax, edi
0x18003014a  jmp     loc_180030603
0x18003014f  lea     edi, [rbx-2]
0x180030152  lea     rax, ?gc_MvUndoTable@@3PAUCspUndoRule@@A; CspUndoRule near * gc_MvUndoTable
0x180030159  mov     rdx, [r14+rax+10h]
0x18003015e  mov     rdx, [rdx+rdi*8]; String2
0x180030162  mov     rcx, [rsp+0C8h+String1]; String1
0x180030167  call    cs:__imp__wcsicmp
0x18003016d  test    eax, eax
0x18003016f  jz      loc_180030250
0x180030175  lea     rax, ?gc_MvUndoTable@@3PAUCspUndoRule@@A; CspUndoRule near * gc_MvUndoTable
0x18003017c  mov     rax, [r14+rax+10h]
0x180030181  mov     rcx, [rax+rdi*8]
0x180030185  mov     eax, 2Ah ; '*'
0x18003018a  xor     edi, edi
0x18003018c  cmp     ax, [rcx]
0x18003018f  jnz     short loc_18003019B
0x180030191  cmp     di, [rcx+2]
0x180030195  jz      loc_180030252
0x18003019b  cmp     [rsp+0C8h+var_70], ebx
0x18003019f  jnz     loc_180030249
0x1800301a5  mov     rdx, [rsp+0C8h+var_98]; struct IConfigManager2URI *
0x1800301aa  mov     rcx, r12; struct ProvStateContext *
0x1800301ad  call    ?MvSaveNodeForUndo@@YAJPEBVProvStateContext@@PEAUIConfigManager2URI@@@Z; MvSaveNodeForUndo(ProvStateContext const *,IConfigManager2URI *)
0x1800301b2  mov     ebx, eax
0x1800301b4  test    eax, eax
0x1800301b6  jns     loc_180030249
0x1800301bc  mov     rcx, [rsp+0C8h]; this
0x1800301c4  mov     r9d, eax; char *
0x1800301c7  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800301ce  mov     edx, 89h; void *
0x1800301d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301d8  nop
0x1800301d9  mov     rcx, [rsp+0C8h+var_98]
0x1800301de  test    rcx, rcx
0x1800301e1  jz      short loc_1800301F5
0x1800301e3  mov     [rsp+0C8h+var_98], rdi
0x1800301e8  mov     rax, [rcx]
0x1800301eb  mov     rax, [rax+10h]
0x1800301ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f4  nop
0x1800301f5  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x1800301fa  test    rcx, rcx
0x1800301fd  jz      short loc_180030206
  ... truncated ...
```
