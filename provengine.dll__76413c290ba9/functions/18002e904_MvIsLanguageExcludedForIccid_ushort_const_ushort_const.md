# MvIsLanguageExcludedForIccid(ushort const *,ushort const *)

- ea: `0x18002e904`
- end: `0x18002ede9`
- name: `?MvIsLanguageExcludedForIccid@@YA_NPEBG0@Z`
- size: `1253`
- prototype: `bool __fastcall(wchar_t *String1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18002ef84`

## callees

- `0x180021cf4`
- `0x18002e904`
- `0x180033630`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002eb69`
- `msvcrt!_wcsnicmp` at `0x18002eb69`
- `msvcrt!_wcsicmp` at `0x18002eab2`
- `msvcrt!_wcsicmp` at `0x18002eb8b`
- `msvcrt!_wcsicmp` at `0x18002eab2`
- `msvcrt!_wcsicmp` at `0x18002eb8b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e969`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e969`
- `XmlLite!CreateXmlReader` at `0x18002e9e8`
- `XmlLite!CreateXmlReader` at `0x18002e9e8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002e9b0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18002e9b0`

## string_xrefs

- `0x18002e94f`: `SimbldIccidTablePath`
- `0x18002e982`: `SimbldIccidTablePath_Legacy`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall MvIsLanguageExcludedForIccid(wchar_t *String1, const unsigned __int16 *a2)
{
  int Configuration; // ebx
  HRESULT v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  size_t v9; // rsi
  char v10; // di
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  size_t v15; // rbx
  int v16; // eax
  int v17; // eax
  const unsigned __int16 *v18; // rax
  int v19; // r8d
  int v20; // edx
  void *v21; // rcx
  IStream *v22; // rcx
  IStream *v24; // rcx
  void *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *String2; // [rsp+28h] [rbp-D8h] BYREF
  IStream *ppstm; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  LODWORD(String2) = 522;
  Configuration = MvGetConfiguration((char *)L"SimbldIccidTablePath", FileName, (unsigned int *)&String2);
  if ( Configuration < 0 || GetFileAttributesW(FileName) == -1 )
  {
    LODWORD(String2) = 522;
    Configuration = MvGetConfiguration((char *)L"SimbldIccidTablePath_Legacy", FileName, (unsigned int *)&String2);
  }
  if ( Configuration < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)Configuration,
      (int)ppvObject);
  ppstm = 0;
  v5 = SHCreateStreamOnFileW(FileName, 0, &ppstm);
  if ( (unsigned int)(v5 + 2147024894) <= 1 )
  {
    v24 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return 0;
  }
  else
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v5,
        (int)ppvObject);
    ppvObject = 0;
    v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v6,
        (int)ppvObject);
    v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v7,
        (int)ppvObject);
    v8 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v8,
        (int)ppvObject);
    v28 = 0;
    v9 = 0;
LABEL_11:
    v10 = 0;
    while ( 1 )
    {
      v11 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v28);
      if ( v11 )
        break;
      String2 = 0;
      if ( v28 == 1 )
      {
        v12 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                &String2,
                0);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
            (const char *)(unsigned int)v12,
            (int)ppvObject);
        if ( _wcsicmp(L"sim", String2) )
        {
          if ( !_wcsicmp(L"iso639", String2) && v9 )
          {
            v16 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                    ppvObject,
                    L"id",
                    0);
            if ( v16 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x18C,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                (const char *)(unsigned int)v16,
                (int)ppvObject);
            if ( v16 == 1 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x18D,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                (const char *)0x80070057LL,
                (int)ppvObject);
            v30 = 0;
            v17 = (*(__int64 (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                    ppvObject,
                    &v30,
                    0);
            if ( v17 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x18F,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
                (const char *)(unsigned int)v17,
                (int)ppvObject);
            v18 = a2;
            do
            {
              v19 = *(const unsigned __int16 *)((char *)v18 + v30 - (_QWORD)a2);
              v20 = *v18 - v19;
              if ( v20 )
                break;
              ++v18;
            }
            while ( v19 );
            if ( !v20 )
              v10 = 1;
          }
        }
        else if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) != 1 )
        {
          v13 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                  ppvObject,
                  L"iccid",
                  0);
          if ( v13 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x17A,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)(unsigned int)v13,
              (int)ppvObject);
          if ( v13 == 1 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)0x80070057LL,
              (int)ppvObject);
          v29 = 0;
          v14 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                  ppvObject,
                  &v29,
                  0);
          if ( v14 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x17D,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
              (const char *)(unsigned int)v14,
              (int)ppvObject);
          v15 = -1;
          do
            ++v15;
          while ( v29[v15] );
          if ( v15 > v9 && !_wcsnicmp(String1, v29, v15) )
          {
            v9 = v15;
            goto LABEL_11;
          }
        }
      }
    }
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
        (const char *)(unsigned int)v11,
        (int)ppvObject);
    v21 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x18002e904  mov     [rsp-8+arg_8], rbx
0x18002e909  mov     [rsp-8+arg_10], rsi
0x18002e90e  push    rbp
0x18002e90f  push    rdi
0x18002e910  push    r12
0x18002e912  push    r14
0x18002e914  push    r15
0x18002e916  lea     rbp, [rsp-170h]
0x18002e91e  sub     rsp, 270h
0x18002e925  mov     rax, cs:__security_cookie
0x18002e92c  xor     rax, rsp
0x18002e92f  mov     [rbp+190h+var_30], rax
0x18002e936  mov     r14, rdx
0x18002e939  mov     r15, rcx
0x18002e93c  mov     edi, 20Ah
0x18002e941  mov     dword ptr [rsp+290h+String2], edi
0x18002e945  lea     r8, [rsp+290h+String2]; unsigned int *
0x18002e94a  lea     rdx, [rsp+290h+FileName]; pvData
0x18002e94f  lea     rcx, ?gc_wszSimbldIccidLookupPath@@3QBGB; "SimbldIccidTablePath"
0x18002e956  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18002e95b  mov     ebx, eax
0x18002e95d  xor     r12d, r12d
0x18002e960  test    eax, eax
0x18002e962  js      short loc_18002E974
0x18002e964  lea     rcx, [rsp+290h+FileName]; lpFileName
0x18002e969  call    cs:__imp_GetFileAttributesW
0x18002e96f  cmp     eax, 0FFFFFFFFh
0x18002e972  jnz     short loc_18002E990
0x18002e974  mov     dword ptr [rsp+290h+String2], edi
0x18002e978  lea     r8, [rsp+290h+String2]; unsigned int *
0x18002e97d  lea     rdx, [rsp+290h+FileName]; pvData
0x18002e982  lea     rcx, ?gc_wszSimbldIccidLookupPath_Legacy@@3QBGB; "SimbldIccidTablePath_Legacy"
0x18002e989  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18002e98e  mov     ebx, eax
0x18002e990  mov     rcx, [rbp+198h]; this
0x18002e997  test    ebx, ebx
0x18002e999  js      loc_18002ECE7
0x18002e99f  mov     [rsp+290h+ppstm], r12
0x18002e9a4  lea     r8, [rsp+290h+ppstm]; ppstm
0x18002e9a9  xor     edx, edx; grfMode
0x18002e9ab  lea     rcx, [rsp+290h+FileName]; pszFile
0x18002e9b0  call    cs:__imp_SHCreateStreamOnFileW
0x18002e9b6  lea     ecx, [rax+7FF8FFFEh]
0x18002e9bc  cmp     ecx, 1
0x18002e9bf  jbe     loc_18002EC89
0x18002e9c5  mov     rcx, [rbp+198h]; this
0x18002e9cc  test    eax, eax
0x18002e9ce  js      loc_18002ECFC
0x18002e9d4  mov     [rsp+290h+ppvObject], r12; int
0x18002e9d9  xor     r8d, r8d; pMalloc
0x18002e9dc  lea     rdx, [rsp+290h+ppvObject]; ppvObject
0x18002e9e1  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18002e9e8  call    cs:__imp_CreateXmlReader
0x18002e9ee  mov     rcx, [rbp+198h]; this
0x18002e9f5  test    eax, eax
0x18002e9f7  js      loc_18002ED11
0x18002e9fd  mov     rcx, [rsp+290h+ppvObject]
0x18002ea02  mov     rax, [rcx]
0x18002ea05  xor     r8d, r8d
0x18002ea08  lea     edx, [r8+4]
0x18002ea0c  mov     rax, [rax+28h]
0x18002ea10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea15  mov     rcx, [rbp+198h]; this
0x18002ea1c  test    eax, eax
0x18002ea1e  js      loc_18002ED26
0x18002ea24  mov     rcx, [rsp+290h+ppvObject]
0x18002ea29  mov     rax, [rcx]
0x18002ea2c  mov     rdx, [rsp+290h+ppstm]
0x18002ea31  mov     rax, [rax+18h]
0x18002ea35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea3a  mov     rcx, [rbp+198h]; this
0x18002ea41  test    eax, eax
0x18002ea43  js      loc_18002ED3B
0x18002ea49  mov     [rsp+290h+var_258], r12d
0x18002ea4e  mov     rsi, r12
0x18002ea51  mov     dil, r12b
0x18002ea54  mov     rcx, [rsp+290h+ppvObject]
0x18002ea59  mov     rax, [rcx]
0x18002ea5c  lea     rdx, [rsp+290h+var_258]
0x18002ea61  mov     rax, [rax+30h]
0x18002ea65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea6a  test    eax, eax
0x18002ea6c  jnz     loc_18002EC3D
0x18002ea72  mov     [rsp+290h+String2], r12
0x18002ea77  cmp     [rsp+290h+var_258], 1
0x18002ea7c  jnz     short loc_18002EA54
0x18002ea7e  mov     rcx, [rsp+290h+ppvObject]
0x18002ea83  mov     rax, [rcx]
0x18002ea86  xor     r8d, r8d
0x18002ea89  lea     rdx, [rsp+290h+String2]
0x18002ea8e  mov     rax, [rax+70h]
0x18002ea92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea97  mov     rcx, [rbp+198h]; this
0x18002ea9e  test    eax, eax
0x18002eaa0  js      loc_18002EDD4
0x18002eaa6  mov     rdx, [rsp+290h+String2]; String2
0x18002eaab  lea     rcx, ?gc_wszSim@@3QBGB; "sim"
0x18002eab2  call    cs:__imp__wcsicmp
0x18002eab8  test    eax, eax
0x18002eaba  jnz     loc_18002EB7F
0x18002eac0  mov     rcx, [rsp+290h+ppvObject]
0x18002eac5  mov     rax, [rcx]
0x18002eac8  mov     rax, [rax+0A0h]
0x18002eacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ead4  cmp     eax, 1
0x18002ead7  jz      loc_18002EA54
0x18002eadd  mov     rcx, [rsp+290h+ppvObject]
0x18002eae2  mov     rax, [rcx]
0x18002eae5  xor     r8d, r8d
0x18002eae8  lea     rdx, ?gc_wszICCID@@3QBGB; "iccid"
0x18002eaef  mov     rax, [rax+50h]
0x18002eaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaf8  mov     rcx, [rbp+198h]; this
0x18002eaff  test    eax, eax
0x18002eb01  js      loc_18002ED7D
0x18002eb07  mov     rcx, [rbp+198h]; this
0x18002eb0e  cmp     eax, 1
0x18002eb11  jz      loc_18002ED65
0x18002eb17  mov     [rsp+290h+var_250], r12
0x18002eb1c  mov     rcx, [rsp+290h+ppvObject]
0x18002eb21  mov     rax, [rcx]
0x18002eb24  xor     r8d, r8d
0x18002eb27  lea     rdx, [rsp+290h+var_250]
0x18002eb2c  mov     rax, [rax+80h]
0x18002eb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb38  mov     rcx, [rbp+198h]; this
0x18002eb3f  test    eax, eax
0x18002eb41  js      loc_18002ED50
0x18002eb47  mov     rdx, [rsp+290h+var_250]; String2
0x18002eb4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002eb50  inc     rbx
0x18002eb53  cmp     [rdx+rbx*2], r12w
0x18002eb58  jnz     short loc_18002EB50
0x18002eb5a  cmp     rbx, rsi
0x18002eb5d  jbe     loc_18002EA54
0x18002eb63  mov     r8, rbx; MaxCount
0x18002eb66  mov     rcx, r15; String1
0x18002eb69  call    cs:__imp__wcsnicmp
0x18002eb6f  test    eax, eax
0x18002eb71  jnz     loc_18002EA54
0x18002eb77  mov     rsi, rbx
0x18002eb7a  jmp     loc_18002EA51
0x18002eb7f  mov     rdx, [rsp+290h+String2]; String2
0x18002eb84  lea     rcx, ?gc_wszISO639@@3QBGB; "iso639"
0x18002eb8b  call    cs:__imp__wcsicmp
0x18002eb91  test    eax, eax
0x18002eb93  jnz     loc_18002EA54
0x18002eb99  test    rsi, rsi
0x18002eb9c  jz      loc_18002EA54
0x18002eba2  mov     rcx, [rsp+290h+ppvObject]
0x18002eba7  mov     rax, [rcx]
0x18002ebaa  xor     r8d, r8d
0x18002ebad  lea     rdx, ?gc_wszid@@3QBGB; "id"
0x18002ebb4  mov     rax, [rax+50h]
0x18002ebb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebbd  mov     rcx, [rbp+198h]; this
0x18002ebc4  test    eax, eax
0x18002ebc6  js      loc_18002EDBF
0x18002ebcc  mov     rcx, [rbp+198h]; this
0x18002ebd3  cmp     eax, 1
0x18002ebd6  jz      loc_18002EDA7
0x18002ebdc  mov     [rsp+290h+var_248], r12
0x18002ebe1  mov     rcx, [rsp+290h+ppvObject]
0x18002ebe6  mov     rax, [rcx]
0x18002ebe9  xor     r8d, r8d
0x18002ebec  lea     rdx, [rsp+290h+var_248]
0x18002ebf1  mov     rax, [rax+80h]
0x18002ebf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebfd  mov     rcx, [rbp+198h]; this
0x18002ec04  test    eax, eax
0x18002ec06  js      loc_18002ED92
0x18002ec0c  mov     rax, r14
0x18002ec0f  mov     rcx, [rsp+290h+var_248]
0x18002ec14  sub     rcx, r14
0x18002ec17  movzx   edx, word ptr [rax]
0x18002ec1a  movzx   r8d, word ptr [rax+rcx]
0x18002ec1f  sub     edx, r8d
0x18002ec22  jnz     short loc_18002EC2D
0x18002ec24  add     rax, 2
0x18002ec28  test    r8d, r8d
0x18002ec2b  jnz     short loc_18002EC17
0x18002ec2d  test    edx, edx
0x18002ec2f  jnz     loc_18002EA54
0x18002ec35  mov     dil, 1
0x18002ec38  jmp     loc_18002EA54
0x18002ec3d  mov     rcx, [rbp+198h]; this
0x18002ec44  test    eax, eax
0x18002ec46  js      loc_18002ECD2
0x18002ec4c  mov     rcx, [rsp+290h+ppvObject]
0x18002ec51  test    rcx, rcx
0x18002ec54  jz      short loc_18002EC68
0x18002ec56  mov     [rsp+290h+ppvObject], r12
0x18002ec5b  mov     rax, [rcx]
0x18002ec5e  mov     rax, [rax+10h]
0x18002ec62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec67  nop
0x18002ec68  mov     rcx, [rsp+290h+ppstm]
0x18002ec6d  test    rcx, rcx
0x18002ec70  jz      short loc_18002EC84
0x18002ec72  mov     [rsp+290h+ppstm], r12
0x18002ec77  mov     rdx, [rcx]
0x18002ec7a  mov     rax, [rdx+10h]
0x18002ec7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec83  nop
0x18002ec84  mov     al, dil
0x18002ec87  jmp     short loc_18002ECA7
0x18002ec89  mov     rcx, [rsp+290h+ppstm]
0x18002ec8e  test    rcx, rcx
0x18002ec91  jz      short loc_18002ECA5
0x18002ec93  mov     [rsp+290h+ppstm], r12
0x18002ec98  mov     rax, [rcx]
0x18002ec9b  mov     rax, [rax+10h]
0x18002ec9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eca4  nop
0x18002eca5  xor     al, al
0x18002eca7  mov     rcx, [rbp+190h+var_30]
0x18002ecae  xor     rcx, rsp; StackCookie
0x18002ecb1  call    __security_check_cookie
0x18002ecb6  lea     r11, [rsp+290h+var_20]
0x18002ecbe  mov     rbx, [r11+38h]
0x18002ecc2  mov     rsi, [r11+40h]
0x18002ecc6  mov     rsp, r11
0x18002ecc9  pop     r15
0x18002eccb  pop     r14
0x18002eccd  pop     r12
0x18002eccf  pop     rdi
0x18002ecd0  pop     rbp
0x18002ecd1  retn
0x18002ecd2  mov     r9d, eax; char *
0x18002ecd5  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ecdc  mov     edx, 19Ch; void *
0x18002ece1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ece7  mov     r9d, ebx; char *
0x18002ecea  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ecf1  mov     edx, 154h; void *
0x18002ecf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ecfc  mov     r9d, eax; char *
0x18002ecff  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed06  mov     edx, 15Dh; void *
0x18002ed0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed11  mov     r9d, eax; char *
0x18002ed14  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed1b  mov     edx, 160h; void *
0x18002ed20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed26  mov     r9d, eax; char *
0x18002ed29  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed30  mov     edx, 161h; void *
0x18002ed35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed3b  mov     r9d, eax; char *
0x18002ed3e  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed45  mov     edx, 162h; void *
0x18002ed4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed50  mov     r9d, eax; char *
0x18002ed53  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed5a  mov     edx, 17Dh; void *
0x18002ed5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed65  mov     r9d, 80070057h; char *
0x18002ed6b  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed72  mov     edx, 17Bh; void *
0x18002ed77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed7d  mov     r9d, eax; char *
0x18002ed80  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed87  mov     edx, 17Ah; void *
0x18002ed8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ed92  mov     r9d, eax; char *
0x18002ed95  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ed9c  mov     edx, 18Fh; void *
0x18002eda1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002eda7  mov     r9d, 80070057h; char *
0x18002edad  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002edb4  mov     edx, 18Dh; void *
0x18002edb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002edbf  mov     r9d, eax; char *
0x18002edc2  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002edc9  mov     edx, 18Ch; void *
0x18002edce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002edd4  mov     r9d, eax; char *
0x18002edd7  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002edde  mov     edx, 16Eh; void *
0x18002ede3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
