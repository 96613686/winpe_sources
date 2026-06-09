# CUSTOM_ERROR_HANDLER::WriteDetailedConfigError(INativeSectionException *,STRU *,STRU *)

- ea: `0x1800053e0`
- end: `0x180005982`
- name: `?WriteDetailedConfigError@CUSTOM_ERROR_HANDLER@@AEAAJPEAVINativeSectionException@@PEAVSTRU@@1@Z`
- size: `1442`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, struct INativeSectionException *, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005988`

## callees

- `0x1800053e0`
- `0x180007836`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800055e2`
- `msvcrt!wcsrchr` at `0x1800055e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000564d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000564d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005657`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005699`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800056d2`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005790`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800058f6`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005699`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800056d2`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005790`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x1800058f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000592e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005938`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005942`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000594c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005957`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000592e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005938`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005942`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000594c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005957`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005740`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000574d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005829`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000587b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005906`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005740`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000574d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005829`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000587b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005906`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800056eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005718`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800056eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005718`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x1800056ff`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x18000572c`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005861`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x1800056ff`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x18000572c`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005861`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800057ce`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005924`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800057ce`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005924`
- `iisutil!SAFE_snwprintf` at `0x180005761`
- `iisutil!SAFE_snwprintf` at `0x1800057fd`
- `iisutil!SAFE_snwprintf` at `0x180005814`
- `iisutil!SAFE_snwprintf` at `0x18000588d`
- `iisutil!SAFE_snwprintf` at `0x180005917`
- `iisutil!SAFE_snwprintf` at `0x180005761`
- `iisutil!SAFE_snwprintf` at `0x1800057fd`
- `iisutil!SAFE_snwprintf` at `0x180005814`
- `iisutil!SAFE_snwprintf` at `0x18000588d`
- `iisutil!SAFE_snwprintf` at `0x180005917`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005484`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005484`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005837`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005837`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005856`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180005856`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800058ac`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800058ac`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800058c3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800058c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005455`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000547a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800054e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000550e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005455`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000547a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800054e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000550e`

## string_xrefs

- `0x180005646`: `temp\apppools`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::WriteDetailedConfigError(
        const char **this,
        struct INativeSectionException *a2,
        struct STRU *a3,
        struct STRU *a4)
{
  signed int String; // ebx
  wchar_t *v9; // rcx
  unsigned __int64 v10; // rax
  int v11; // eax
  signed int LastError; // eax
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // esi
  int v17; // eax
  unsigned __int16 *v18; // rbx
  unsigned int CCH; // eax
  unsigned __int16 *v20; // rax
  const struct STRU *v21; // rdx
  unsigned __int16 *v22; // rax
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v29; // [rsp+4Ch] [rbp-B4h] BYREF
  const unsigned __int16 *v30; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v31; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v32; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v33; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v34; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[56]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v38[56]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v39[56]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v40; // [rsp+190h] [rbp+90h] BYREF
  _WORD *v41; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v42[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v43[80]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v44[80]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v45[256]; // [rsp+390h] [rbp+290h] BYREF

  v30 = 0;
  v24 = 0;
  Str = 0;
  memset_0(v42, 0, sizeof(v42));
  STRU::STRU((STRU *)v35, v42, 0x50u);
  memset_0(v43, 0, sizeof(v43));
  STRU::STRU((STRU *)v39, v43, 0x50u);
  STRU::STRU((STRU *)v36);
  v32 = 0;
  v27 = 0;
  v41 = 0;
  v34 = 0;
  v29 = 0;
  v40 = 0;
  v33 = 0;
  v28 = 0;
  v31 = 0;
  v26 = 0;
  memset_0(v44, 0, sizeof(v44));
  STRU::STRU((STRU *)v38, v44, 0x50u);
  memset_0(v45, 0, sizeof(v45));
  STRU::STRU((STRU *)v37, v45, 0x100u);
  String = (*(__int64 (__fastcall **)(struct INativeSectionException *, const unsigned __int16 **))(*(_QWORD *)a2 + 24LL))(
             a2,
             &v30);
  if ( String < 0 )
    goto LABEL_51;
  String = (*(__int64 (__fastcall **)(struct INativeSectionException *, int *))(*(_QWORD *)a2 + 32LL))(a2, &v24);
  if ( String < 0 )
    goto LABEL_51;
  String = (*(__int64 (__fastcall **)(struct INativeSectionException *, wchar_t **))(*(_QWORD *)a2 + 40LL))(a2, &Str);
  if ( String < 0 )
    goto LABEL_51;
  String = (*(__int64 (__fastcall **)(struct INativeSectionException *, char *, __int128 *, _WORD **))(*(_QWORD *)a2 + 48LL))(
             a2,
             (char *)&v40 + 8,
             &v40,
             &v41);
  if ( String < 0 )
    goto LABEL_51;
  if ( !v30 || !Str || !(_QWORD)v40 || !*((_QWORD *)&v40 + 1) || !v41 )
  {
    STRU::Reset(a3);
    goto LABEL_51;
  }
  v9 = wcsrchr(Str, 0x5Cu);
  if ( v9 )
  {
    while ( --v9 > Str )
    {
      if ( *v9 == 92 )
        goto LABEL_15;
    }
    if ( *v9 != 92 )
      goto LABEL_25;
LABEL_15:
    if ( Str + 5 < v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      if ( v10 > 9 )
      {
        v11 = CompareStringOrdinal(v9 - 4, 13, L"temp\\apppools", 13, 1);
        if ( !v11 )
        {
          LastError = GetLastError();
          String = LastError;
          if ( LastError > 0 )
            String = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_51;
        }
        if ( v11 == 2 )
        {
          String = LANG_STRING::GetString(
                     (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                     0x2F96u,
                     this[4],
                     (const unsigned __int16 **)&v31,
                     &v26);
          if ( String < 0 )
            goto LABEL_51;
          Str = v31;
        }
      }
    }
  }
LABEL_25:
  String = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F8Au, this[4], &v32, &v27);
  if ( String >= 0 )
  {
    String = STRU::Copy((STRU *)v38, v30);
    if ( String >= 0 )
    {
      String = STRU::HTMLEncode((STRU *)v38);
      if ( String >= 0 )
      {
        String = STRU::Copy((STRU *)v37, Str);
        if ( String >= 0 )
        {
          String = STRU::HTMLEncode((STRU *)v37);
          if ( String >= 0 )
          {
            v13 = STRU::QueryStr((STRU *)v37);
            v14 = STRU::QueryStr((STRU *)v38);
            String = SAFE_snwprintf(a3, v32, v14, v13);
            if ( String >= 0 )
            {
              String = LANG_STRING::GetString(
                         (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                         0x2F8Bu,
                         this[4],
                         &v33,
                         &v28);
              if ( String >= 0 )
              {
                v15 = v24 == 1;
                v16 = (*v41 != 0) + 2;
                while ( (unsigned int)v15 < v16 )
                {
                  STRU::Reset((STRU *)v35);
                  if ( v31 )
                    v17 = SAFE_snwprintf((struct STRU *)v35, L"%s", *((_QWORD *)&v40 + v15));
                  else
                    v17 = SAFE_snwprintf(
                            (struct STRU *)v35,
                            L"%5d: %s",
                            (unsigned int)(v15 + v24 - 1),
                            *((_QWORD *)&v40 + v15));
                  String = v17;
                  if ( v17 < 0 )
                    goto LABEL_51;
                  v18 = STRU::QueryStr((STRU *)v35);
                  CCH = STRU::QueryCCH((STRU *)v35);
                  if ( v18[CCH - 1] == 13 )
                  {
                    v18[CCH - 1] = 0;
                    STRU::SyncWithBuffer((STRU *)v35);
                  }
                  String = STRU::HTMLEncode((STRU *)v35);
                  if ( String < 0 )
                    goto LABEL_51;
                  if ( (_DWORD)v15 == 1 )
                  {
                    v20 = STRU::QueryStr((STRU *)v35);
                    String = SAFE_snwprintf((struct STRU *)v39, v33, v20);
                    if ( String < 0 )
                      goto LABEL_51;
                    v21 = (const struct STRU *)v39;
                  }
                  else
                  {
                    v21 = (const struct STRU *)v35;
                  }
                  String = STRU::Append((STRU *)v36, v21);
                  if ( String < 0 )
                    goto LABEL_51;
                  String = STRU::Append((STRU *)v36, L"\r\n");
                  if ( String < 0 )
                    goto LABEL_51;
                  v15 = (unsigned int)(v15 + 1);
                }
                String = LANG_STRING::GetString(
                           (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                           0x2F95u,
                           this[4],
                           &v34,
                           &v29);
                if ( String >= 0 )
                {
                  v22 = STRU::QueryStr((STRU *)v36);
                  String = SAFE_snwprintf(a4, v34, v22);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_51:
  STRU::~STRU((STRU *)v37);
  STRU::~STRU((STRU *)v38);
  STRU::~STRU((STRU *)v36);
  STRU::~STRU((STRU *)v39);
  STRU::~STRU((STRU *)v35);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800053e0  push    rbp
0x1800053e2  push    rbx
0x1800053e3  push    rsi
0x1800053e4  push    rdi
0x1800053e5  push    r12
0x1800053e7  push    r13
0x1800053e9  push    r14
0x1800053eb  push    r15
0x1800053ed  lea     rbp, [rsp-4A8h]
0x1800053f5  sub     rsp, 5A8h
0x1800053fc  mov     rax, cs:__security_cookie
0x180005403  xor     rax, rsp
0x180005406  mov     [rbp+4E0h+var_50], rax
0x18000540d  xor     r13d, r13d
0x180005410  mov     rsi, r8
0x180005413  mov     rdi, rdx
0x180005416  mov     [rsp+5E0h+var_590], r13
0x18000541b  mov     r14, rcx
0x18000541e  mov     [rsp+5E0h+var_5B0], r13d
0x180005423  mov     r12d, 0A0h
0x180005429  mov     [rsp+5E0h+Str], r13
0x18000542e  mov     r8d, r12d; Size
0x180005431  lea     rcx, [rbp+4E0h+var_430]; void *
0x180005438  xor     edx, edx; Val
0x18000543a  mov     r15, r9
0x18000543d  call    memset_0
0x180005442  lea     ebx, [r13+50h]
0x180005446  mov     r8d, ebx
0x180005449  lea     rdx, [rbp+4E0h+var_430]
0x180005450  lea     rcx, [rsp+5E0h+var_568]
0x180005455  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000545b  mov     r8d, r12d; Size
0x18000545e  lea     rcx, [rbp+4E0h+var_390]; void *
0x180005465  xor     edx, edx; Val
0x180005467  call    memset_0
0x18000546c  mov     r8d, ebx
0x18000546f  lea     rdx, [rbp+4E0h+var_390]
0x180005476  lea     rcx, [rbp+4E0h+var_488]
0x18000547a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005480  lea     rcx, [rbp+4E0h+var_530]
0x180005484  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000548a  xorps   xmm0, xmm0
0x18000548d  mov     [rsp+5E0h+var_580], r13
0x180005492  xor     eax, eax
0x180005494  mov     [rsp+5E0h+var_59C], r13d
0x180005499  mov     r8d, r12d; Size
0x18000549c  mov     [rbp+4E0h+var_440], rax
0x1800054a3  xor     edx, edx; Val
0x1800054a5  mov     [rsp+5E0h+var_570], r13
0x1800054aa  lea     rcx, [rbp+4E0h+var_2F0]; void *
0x1800054b1  mov     [rsp+5E0h+var_594], r13d
0x1800054b6  movups  [rbp+4E0h+var_450], xmm0
0x1800054bd  mov     [rsp+5E0h+var_578], r13
0x1800054c2  mov     [rsp+5E0h+var_598], r13d
0x1800054c7  mov     [rsp+5E0h+var_588], r13
0x1800054cc  mov     [rsp+5E0h+var_5A0], r13d
0x1800054d1  call    memset_0
0x1800054d6  mov     r8d, ebx
0x1800054d9  lea     rdx, [rbp+4E0h+var_2F0]
0x1800054e0  lea     rcx, [rbp+4E0h+var_4C0]
0x1800054e4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800054ea  xor     edx, edx; Val
0x1800054ec  lea     rcx, [rbp+4E0h+var_250]; void *
0x1800054f3  mov     r8d, 200h; Size
0x1800054f9  call    memset_0
0x1800054fe  lea     r8d, [r12+60h]
0x180005503  lea     rdx, [rbp+4E0h+var_250]
0x18000550a  lea     rcx, [rbp+4E0h+var_4F8]
0x18000550e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005514  mov     rax, [rdi]
0x180005517  lea     rdx, [rsp+5E0h+var_590]
0x18000551c  mov     rcx, rdi
0x18000551f  mov     rax, [rax+18h]
0x180005523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005528  mov     ebx, eax
0x18000552a  test    eax, eax
0x18000552c  js      loc_18000592A
0x180005532  mov     rax, [rdi]
0x180005535  lea     rdx, [rsp+5E0h+var_5B0]
0x18000553a  mov     rcx, rdi
0x18000553d  mov     rax, [rax+20h]
0x180005541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005546  mov     ebx, eax
0x180005548  test    eax, eax
0x18000554a  js      loc_18000592A
0x180005550  mov     rax, [rdi]
0x180005553  lea     rdx, [rsp+5E0h+Str]
0x180005558  mov     rcx, rdi
0x18000555b  mov     rax, [rax+28h]
0x18000555f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005564  mov     ebx, eax
0x180005566  test    eax, eax
0x180005568  js      loc_18000592A
0x18000556e  mov     rax, [rdi]
0x180005571  lea     r9, [rbp+4E0h+var_440]
0x180005578  lea     r8, [rbp+4E0h+var_450]
0x18000557f  mov     rcx, rdi
0x180005582  lea     rdx, [rbp+4E0h+var_450+8]
0x180005589  mov     rax, [rax+30h]
0x18000558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005592  mov     ebx, eax
0x180005594  test    eax, eax
0x180005596  js      loc_18000592A
0x18000559c  cmp     [rsp+5E0h+var_590], r13
0x1800055a1  jz      loc_180005921
0x1800055a7  mov     rcx, [rsp+5E0h+Str]; Str
0x1800055ac  test    rcx, rcx
0x1800055af  jz      loc_180005921
0x1800055b5  cmp     qword ptr [rbp+4E0h+var_450], r13
0x1800055bc  jz      loc_180005921
0x1800055c2  cmp     qword ptr [rbp+4E0h+var_450+8], r13
0x1800055c9  jz      loc_180005921
0x1800055cf  cmp     [rbp+4E0h+var_440], r13
0x1800055d6  jz      loc_180005921
0x1800055dc  lea     ebx, [r13+5Ch]
0x1800055e0  mov     edx, ebx; Ch
0x1800055e2  call    cs:__imp_wcsrchr
0x1800055e8  lea     edx, [rbx-4Fh]; cchCount1
0x1800055eb  mov     rcx, rax
0x1800055ee  lea     r12d, [r13+1]
0x1800055f2  test    rax, rax
0x1800055f5  jz      loc_1800056B3
0x1800055fb  mov     rax, [rsp+5E0h+Str]
0x180005600  jmp     short loc_180005607
0x180005602  cmp     bx, [rcx]
0x180005605  jz      short loc_180005619
0x180005607  sub     rcx, 2
0x18000560b  cmp     rcx, rax
0x18000560e  ja      short loc_180005602
0x180005610  cmp     bx, [rcx]
0x180005613  jnz     loc_1800056B3
0x180005619  add     rax, 0Ah
0x18000561d  cmp     rax, rcx
0x180005620  jnb     loc_1800056B3
0x180005626  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000562a  inc     rax
0x18000562d  cmp     [rcx+rax*2], r13w
0x180005632  jnz     short loc_18000562A
0x180005634  cmp     rax, 9
0x180005638  jbe     short loc_1800056B3
0x18000563a  add     rcx, 0FFFFFFFFFFFFFFF8h; lpString1
0x18000563e  mov     [rsp+5E0h+bIgnoreCase], r12d; bIgnoreCase
0x180005643  mov     r9d, edx; cchCount2
0x180005646  lea     r8, String2; "temp\\apppools"
0x18000564d  call    cs:__imp_CompareStringOrdinal
0x180005653  test    eax, eax
0x180005655  jnz     short loc_180005675
0x180005657  call    cs:__imp_GetLastError
0x18000565d  mov     ebx, eax
0x18000565f  test    eax, eax
0x180005661  jle     loc_18000592A
0x180005667  movzx   ebx, ax
0x18000566a  or      ebx, 80070000h
0x180005670  jmp     loc_18000592A
0x180005675  cmp     eax, 2
0x180005678  jnz     short loc_1800056B3
0x18000567a  mov     r8, [r14+20h]
0x18000567e  lea     rax, [rsp+5E0h+var_5A0]
0x180005683  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x18000568a  lea     r9, [rsp+5E0h+var_588]
0x18000568f  mov     edx, 2F96h
0x180005694  mov     qword ptr [rsp+5E0h+bIgnoreCase], rax
0x180005699  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x18000569f  mov     ebx, eax
0x1800056a1  test    eax, eax
0x1800056a3  js      loc_18000592A
0x1800056a9  mov     rax, [rsp+5E0h+var_588]
0x1800056ae  mov     [rsp+5E0h+Str], rax
0x1800056b3  mov     r8, [r14+20h]
0x1800056b7  lea     rax, [rsp+5E0h+var_59C]
0x1800056bc  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x1800056c3  lea     r9, [rsp+5E0h+var_580]
0x1800056c8  mov     edx, 2F8Ah
0x1800056cd  mov     qword ptr [rsp+5E0h+bIgnoreCase], rax
0x1800056d2  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x1800056d8  mov     ebx, eax
0x1800056da  test    eax, eax
0x1800056dc  js      loc_18000592A
0x1800056e2  mov     rdx, [rsp+5E0h+var_590]
0x1800056e7  lea     rcx, [rbp+4E0h+var_4C0]
0x1800056eb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800056f1  mov     ebx, eax
0x1800056f3  test    eax, eax
0x1800056f5  js      loc_18000592A
0x1800056fb  lea     rcx, [rbp+4E0h+var_4C0]
0x1800056ff  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180005705  mov     ebx, eax
0x180005707  test    eax, eax
0x180005709  js      loc_18000592A
0x18000570f  mov     rdx, [rsp+5E0h+Str]
0x180005714  lea     rcx, [rbp+4E0h+var_4F8]
0x180005718  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000571e  mov     ebx, eax
0x180005720  test    eax, eax
0x180005722  js      loc_18000592A
0x180005728  lea     rcx, [rbp+4E0h+var_4F8]
0x18000572c  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180005732  mov     ebx, eax
0x180005734  test    eax, eax
0x180005736  js      loc_18000592A
0x18000573c  lea     rcx, [rbp+4E0h+var_4F8]
0x180005740  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005746  lea     rcx, [rbp+4E0h+var_4C0]
0x18000574a  mov     rbx, rax
0x18000574d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005753  mov     rdx, [rsp+5E0h+var_580]
0x180005758  mov     r9, rbx
0x18000575b  mov     r8, rax
0x18000575e  mov     rcx, rsi
0x180005761  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180005767  mov     ebx, eax
0x180005769  test    eax, eax
0x18000576b  js      loc_18000592A
0x180005771  mov     r8, [r14+20h]
0x180005775  lea     rax, [rsp+5E0h+var_598]
0x18000577a  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180005781  lea     r9, [rsp+5E0h+var_578]
0x180005786  mov     edx, 2F8Bh
0x18000578b  mov     qword ptr [rsp+5E0h+bIgnoreCase], rax
0x180005790  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180005796  mov     ebx, eax
0x180005798  test    eax, eax
0x18000579a  js      loc_18000592A
0x1800057a0  cmp     [rsp+5E0h+var_5B0], r12d
0x1800057a5  mov     esi, r13d
0x1800057a8  mov     rax, [rbp+4E0h+var_440]
0x1800057af  mov     edi, r13d
0x1800057b2  cmovz   edi, r12d
0x1800057b6  cmp     r13w, [rax]
0x1800057ba  setnz   sil
0x1800057be  add     esi, 2
0x1800057c1  cmp     edi, esi
0x1800057c3  jnb     loc_1800058D7
0x1800057c9  lea     rcx, [rsp+5E0h+var_568]
0x1800057ce  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800057d4  mov     rcx, qword ptr [rbp+rdi*8+4E0h+var_450]
0x1800057dc  cmp     [rsp+5E0h+var_588], r13
0x1800057e1  jnz     short loc_180005805
0x1800057e3  mov     r8d, [rsp+5E0h+var_5B0]
0x1800057e8  lea     rdx, a5dS; "%5d: %s"
0x1800057ef  dec     r8d
0x1800057f2  mov     r9, rcx
0x1800057f5  add     r8d, edi
0x1800057f8  lea     rcx, [rsp+5E0h+var_568]
0x1800057fd  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180005803  jmp     short loc_18000581A
0x180005805  mov     r8, rcx
0x180005808  lea     rdx, aS; "%s"
0x18000580f  lea     rcx, [rsp+5E0h+var_568]
0x180005814  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000581a  mov     ebx, eax
0x18000581c  test    eax, eax
0x18000581e  js      loc_18000592A
0x180005824  lea     rcx, [rsp+5E0h+var_568]
0x180005829  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000582f  lea     rcx, [rsp+5E0h+var_568]
0x180005834  mov     rbx, rax
0x180005837  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000583d  mov     eax, eax
0x18000583f  mov     ecx, 0Dh
0x180005844  cmp     cx, [rbx+rax*2-2]
0x180005849  jnz     short loc_18000585C
0x18000584b  lea     rcx, [rsp+5E0h+var_568]
0x180005850  mov     [rbx+rax*2-2], r13w
0x180005856  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000585c  lea     rcx, [rsp+5E0h+var_568]
0x180005861  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180005867  mov     ebx, eax
0x180005869  test    eax, eax
0x18000586b  js      loc_18000592A
0x180005871  cmp     edi, r12d
0x180005874  jnz     short loc_1800058A3
0x180005876  lea     rcx, [rsp+5E0h+var_568]
0x18000587b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005881  mov     rdx, [rsp+5E0h+var_578]
0x180005886  lea     rcx, [rbp+4E0h+var_488]
0x18000588a  mov     r8, rax
0x18000588d  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180005893  mov     ebx, eax
0x180005895  test    eax, eax
0x180005897  js      loc_18000592A
0x18000589d  lea     rdx, [rbp+4E0h+var_488]
0x1800058a1  jmp     short loc_1800058A8
0x1800058a3  lea     rdx, [rsp+5E0h+var_568]
0x1800058a8  lea     rcx, [rbp+4E0h+var_530]
0x1800058ac  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800058b2  mov     ebx, eax
0x1800058b4  test    eax, eax
0x1800058b6  js      short loc_18000592A
0x1800058b8  lea     rdx, asc_180009AF0; "\r\n"
0x1800058bf  lea     rcx, [rbp+4E0h+var_530]
0x1800058c3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800058c9  mov     ebx, eax
0x1800058cb  test    eax, eax
0x1800058cd  js      short loc_18000592A
0x1800058cf  add     edi, r12d
0x1800058d2  jmp     loc_1800057C1
0x1800058d7  mov     r8, [r14+20h]
0x1800058db  lea     rax, [rsp+5E0h+var_594]
0x1800058e0  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
  ... truncated ...
```
