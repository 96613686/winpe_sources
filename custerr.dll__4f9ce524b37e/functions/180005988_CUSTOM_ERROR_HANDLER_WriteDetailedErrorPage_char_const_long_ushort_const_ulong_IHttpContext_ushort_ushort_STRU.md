# CUSTOM_ERROR_HANDLER::WriteDetailedErrorPage(char const *,long,ushort const *,ulong,IHttpContext *,ushort,ushort,STRU *,STRU *,INativeSectionException *)

- ea: `0x180005988`
- end: `0x18000639c`
- name: `?WriteDetailedErrorPage@CUSTOM_ERROR_HANDLER@@QEAAJPEBDJPEBGKPEAVIHttpContext@@GGPEAVSTRU@@3PEAVINativeSectionException@@@Z`
- size: `2580`
- prototype: `__int64 __usercall@<rax>(CUSTOM_ERROR_HANDLER *__hidden this@<rcx>, const char *@<rdx>, int@<r8d>, const unsigned __int16 *@<r9>, unsigned int, struct IHttpContext *, unsigned __int16, unsigned __int16, struct STRU *, struct STRU *, struct INativeSectionException *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800012c0`

## callees

- `0x18000377c`
- `0x180003acc`
- `0x1800053e0`
- `0x180005988`
- `0x1800063a4`
- `0x18000650c`
- `0x180007836`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005c3f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005c67`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005e26`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180006018`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180006045`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005c3f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005c67`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180005e26`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180006018`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180006045`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800062a6`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800062a6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800062fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006309`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006323`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006330`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000633d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000634a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006357`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006364`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006371`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800062fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006309`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006323`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006330`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000633d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000634a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006357`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006364`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006371`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800062ef`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800062ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800060d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800060ff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006114`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006124`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006134`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006144`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006154`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006164`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006174`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800060d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800060ff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006114`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006124`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006134`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006144`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006154`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006164`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006174`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x18000627f`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x18000627f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006295`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006295`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005c5a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005de2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005c5a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005de2`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005daf`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005df9`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005daf`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180005df9`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005ff5`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180005ff5`
- `iisutil!SAFE_snwprintf` at `0x180005c86`
- `iisutil!SAFE_snwprintf` at `0x180006263`
- `iisutil!SAFE_snwprintf` at `0x180005c86`
- `iisutil!SAFE_snwprintf` at `0x180006263`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005a4b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005a8f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b15`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b22`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b2f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b3c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005a4b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005a8f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b15`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b22`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b2f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005b3c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000605c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000608f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800060b3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000605c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000608f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800060b3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005b49`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180005b49`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180005d24`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180005d24`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005d79`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005d98`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005d79`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005d98`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006074`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800060a2`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800060c6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006074`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800060a2`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800060c6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a73`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005ae0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b08`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005a73`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005ae0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b08`

## string_xrefs

- `0x1800060f3`: `https://go.microsoft.com/fwlink/?LinkID=62293`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::WriteDetailedErrorPage(
        const char **this,
        char *a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct IHttpContext *a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        struct STRU *a9,
        struct STRU *a10,
        struct INativeSectionException *a11)
{
  __int64 v14; // rax
  __int64 v15; // r13
  int *v16; // rax
  unsigned __int16 *v17; // r12
  const wchar_t *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  const char *v23; // r8
  __int64 v24; // rdi
  int String; // ebx
  int v26; // eax
  const unsigned __int16 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  const unsigned __int16 *v30; // rsi
  __int64 v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rax
  const unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rbx
  struct IHttpUser *v37; // rax
  unsigned int v38; // edx
  __int64 v39; // rax
  unsigned __int16 *v40; // rax
  wchar_t *v41; // rax
  unsigned __int16 *v42; // r13
  unsigned __int16 *v43; // r12
  unsigned __int16 *v44; // r15
  unsigned __int16 *v45; // rsi
  unsigned __int16 *v46; // r14
  unsigned __int16 *v47; // rdi
  unsigned __int16 *v48; // rbx
  unsigned __int16 *v49; // rax
  unsigned int CCH; // eax
  __int64 v51; // rcx
  unsigned __int16 **v53; // [rsp+30h] [rbp-140h]
  unsigned int v54; // [rsp+38h] [rbp-138h]
  unsigned int *v55; // [rsp+38h] [rbp-138h]
  unsigned int v56; // [rsp+48h] [rbp-128h]
  unsigned int v57; // [rsp+F0h] [rbp-80h] BYREF
  unsigned int v58; // [rsp+F4h] [rbp-7Ch] BYREF
  unsigned int v59; // [rsp+F8h] [rbp-78h] BYREF
  int v60; // [rsp+FCh] [rbp-74h]
  const unsigned __int16 *v61; // [rsp+100h] [rbp-70h] BYREF
  struct STRU *v62; // [rsp+108h] [rbp-68h]
  unsigned int v63; // [rsp+110h] [rbp-60h] BYREF
  unsigned int v64; // [rsp+114h] [rbp-5Ch] BYREF
  unsigned int v65; // [rsp+118h] [rbp-58h] BYREF
  unsigned int v66; // [rsp+11Ch] [rbp-54h] BYREF
  unsigned int v67; // [rsp+120h] [rbp-50h] BYREF
  unsigned int v68; // [rsp+124h] [rbp-4Ch] BYREF
  unsigned int v69; // [rsp+128h] [rbp-48h] BYREF
  struct INativeSectionException *v70; // [rsp+130h] [rbp-40h]
  int v71; // [rsp+138h] [rbp-38h] BYREF
  unsigned __int16 *v72; // [rsp+140h] [rbp-30h] BYREF
  const unsigned __int16 *v73; // [rsp+148h] [rbp-28h] BYREF
  unsigned __int16 *v74; // [rsp+150h] [rbp-20h] BYREF
  unsigned __int16 *v75; // [rsp+158h] [rbp-18h] BYREF
  unsigned __int16 *v76; // [rsp+160h] [rbp-10h] BYREF
  unsigned __int16 *v77; // [rsp+168h] [rbp-8h] BYREF
  unsigned __int16 *v78; // [rsp+170h] [rbp+0h] BYREF
  const unsigned __int16 *v79; // [rsp+178h] [rbp+8h] BYREF
  unsigned __int16 *v80; // [rsp+180h] [rbp+10h] BYREF
  unsigned __int16 *v81; // [rsp+188h] [rbp+18h]
  const unsigned __int16 *v82; // [rsp+190h] [rbp+20h] BYREF
  STRU *v83; // [rsp+198h] [rbp+28h]
  unsigned __int16 *Str; // [rsp+1A0h] [rbp+30h]
  unsigned __int16 *v85; // [rsp+1A8h] [rbp+38h]
  const unsigned __int16 *v86; // [rsp+1B0h] [rbp+40h]
  const wchar_t *v87; // [rsp+1B8h] [rbp+48h]
  int *v88; // [rsp+1C0h] [rbp+50h]
  CUSTOM_ERROR_HANDLER *v89; // [rsp+1C8h] [rbp+58h]
  __int64 v90; // [rsp+1D0h] [rbp+60h]
  __int128 v91; // [rsp+1D8h] [rbp+68h] BYREF
  __int128 v92; // [rsp+1E8h] [rbp+78h]
  _BYTE v93[56]; // [rsp+1F8h] [rbp+88h] BYREF
  _BYTE v94[56]; // [rsp+230h] [rbp+C0h] BYREF
  _BYTE v95[56]; // [rsp+268h] [rbp+F8h] BYREF
  _BYTE v96[56]; // [rsp+2A0h] [rbp+130h] BYREF
  _BYTE v97[56]; // [rsp+2D8h] [rbp+168h] BYREF
  _BYTE v98[56]; // [rsp+310h] [rbp+1A0h] BYREF
  _BYTE v99[56]; // [rsp+348h] [rbp+1D8h] BYREF
  _BYTE v100[56]; // [rsp+380h] [rbp+210h] BYREF
  _BYTE v101[56]; // [rsp+3B8h] [rbp+248h] BYREF
  _BYTE v102[56]; // [rsp+3F0h] [rbp+280h] BYREF
  _BYTE v103[56]; // [rsp+428h] [rbp+2B8h] BYREF
  unsigned __int16 v104[64]; // [rsp+460h] [rbp+2F0h] BYREF
  unsigned __int16 v105[64]; // [rsp+4E0h] [rbp+370h] BYREF
  unsigned __int16 v106[64]; // [rsp+560h] [rbp+3F0h] BYREF
  unsigned __int16 v107[64]; // [rsp+5E0h] [rbp+470h] BYREF

  v62 = a9;
  v83 = a10;
  v60 = a3;
  v89 = (CUSTOM_ERROR_HANDLER *)this;
  v70 = a11;
  v61 = 0;
  v58 = 0;
  memset_0(v104, 0, sizeof(v104));
  STRU::STRU((STRU *)v103, v104, 0x40u);
  v73 = 0;
  v57 = 0;
  STRU::STRU((STRU *)v93);
  memset_0(v105, 0, sizeof(v105));
  STRU::STRU((STRU *)v94, v105, 0x40u);
  v72 = 0;
  v63 = 0;
  STRU::STRU((STRU *)v102);
  v80 = 0;
  v74 = 0;
  v67 = 0;
  v76 = 0;
  v66 = 0;
  v75 = 0;
  v65 = 0;
  v78 = 0;
  v64 = 0;
  v77 = 0;
  v59 = 0;
  memset_0(v106, 0, sizeof(v106));
  STRU::STRU((STRU *)v101, v106, 0x40u);
  memset_0(v107, 0, sizeof(v107));
  STRU::STRU((STRU *)v100, v107, 0x40u);
  STRU::STRU((STRU *)v97);
  STRU::STRU((STRU *)v99);
  STRU::STRU((STRU *)v95);
  STRU::STRU((STRU *)v98);
  STRA::STRA((STRA *)v96);
  v82 = 0;
  v14 = *(_QWORD *)a6;
  v68 = 0;
  v79 = 0;
  v69 = 0;
  v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v14 + 32))(a6);
  v90 = v15;
  v71 = 0;
  v16 = &dword_180009DAC;
  v17 = (unsigned __int16 *)&::Str;
  v91 = 0;
  if ( a2 )
    v16 = (int *)a2;
  v88 = v16;
  v18 = &::Str;
  if ( a4 )
    v18 = a4;
  v87 = v18;
  v92 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  *(_QWORD *)(v19 + 256) = "text/html; charset=utf-8";
  *(_WORD *)(v19 + 248) = 24;
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  *(_QWORD *)(v20 + 64) = "private";
  *(_WORD *)(v20 + 56) = 7;
  v21 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 8LL))(a6);
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v23 = this[4];
  v24 = v22;
  if ( *(_WORD *)(v22 + 46) )
  {
    String = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F92u, v23, &v61, &v58);
    if ( String < 0 )
      goto LABEL_49;
    v26 = SAFE_snwprintf((struct STRU *)v103, v61, v24 + 48);
  }
  else
  {
    String = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F91u, v23, &v61, &v58);
    if ( String < 0 )
      goto LABEL_49;
    v26 = STRU::Copy((STRU *)v103, v61);
  }
  String = v26;
  if ( v26 >= 0 )
  {
    v27 = CUSTOM_ERROR_HANDLER::NotificationToString((CUSTOM_ERROR_HANDLER *)this, a5);
    v28 = *(_QWORD *)a6;
    v86 = v27;
    v29 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v28 + 24))(a6);
    v30 = *(const unsigned __int16 **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29) + 72);
    v31 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 24LL))(a6);
    v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 24LL))(a6);
    v33 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32) + 70);
    v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
    String = STRU::Copy((STRU *)v93, v30, ((unsigned __int64)*(unsigned __int16 *)(v34 + 64) - v33) >> 1);
    if ( String >= 0 )
    {
      String = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const unsigned __int16 **, unsigned int *))(*(_QWORD *)a6 + 128LL))(
                 a6,
                 "QUERY_STRING",
                 &v73,
                 &v57);
      if ( String >= 0 )
      {
        if ( !v57
          || (String = STRU::Append((STRU *)v93, L"?", 1u), String >= 0)
          && (String = STRU::Append((STRU *)v93, v73, v57), String >= 0) )
        {
          String = STRU::HTMLEncode((STRU *)v93);
          if ( String >= 0 )
          {
            v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a6 + 168LL))(
                                              a6,
                                              0);
            if ( !v35
              || (String = STRU::Copy((STRU *)v94, v35), String >= 0)
              && (String = STRU::HTMLEncode((STRU *)v94), String >= 0) )
            {
              String = LANG_STRING::GetString(
                         (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                         0x2F8Du,
                         this[4],
                         (const unsigned __int16 **)&v72,
                         &v63);
              if ( String >= 0 )
              {
                v36 = v72;
                v37 = (struct IHttpUser *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 48LL))(a6);
                String = CUSTOM_ERROR_HANDLER::WriteDetailedLogonUserMethod(
                           (CUSTOM_ERROR_HANDLER *)this,
                           v38,
                           v37,
                           v36,
                           (struct STRU *)v102,
                           (const unsigned __int16 **)&v80);
                if ( String >= 0 )
                {
                  if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 192LL))(a6) )
                  {
                    v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a6 + 192LL))(a6);
                    v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 80LL))(v39);
                  }
                  if ( !*v17 )
                    v17 = v72;
                  v85 = v17;
                  String = CUSTOM_ERROR_HANDLER::FindDetailedErrorResourcesWrapper(
                             (CUSTOM_ERROR_HANDLER *)this,
                             a7,
                             a8,
                             v60,
                             (const unsigned __int16 **)&v74,
                             &v67,
                             (const unsigned __int16 **)&v76,
                             &v66,
                             (const unsigned __int16 **)&v75,
                             &v65,
                             (const unsigned __int16 **)&v78,
                             &v64,
                             (const unsigned __int16 **)&v77,
                             &v59);
                  if ( String >= 0 )
                  {
                    v40 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 200LL))(
                                                v15,
                                                0);
                    v81 = v40;
                    if ( !v40 || !*v40 )
                      v81 = v74;
                    String = CUSTOM_ERROR_HANDLER::WriteDetailedFrebKBCauseSolution(
                               (CUSTOM_ERROR_HANDLER *)this,
                               v62,
                               (struct STRU *)v101,
                               v77,
                               v59,
                               (struct STRU *)v100,
                               v76,
                               v54,
                               v75,
                               v56,
                               (struct STRU *)v97);
                    if ( String >= 0 )
                    {
                      if ( v70 )
                      {
                        String = CUSTOM_ERROR_HANDLER::WriteDetailedConfigError(
                                   (CUSTOM_ERROR_HANDLER *)this,
                                   v70,
                                   (struct STRU *)v99,
                                   (struct STRU *)v95);
                        if ( String < 0 )
                          goto LABEL_49;
                        STRU::Reset((STRU *)v97);
                      }
                      String = LANG_STRING::GetString(
                                 (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                                 0x2F89u,
                                 this[4],
                                 &v82,
                                 &v68);
                      if ( String >= 0 )
                      {
                        String = LANG_STRING::GetString(
                                   (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                                   0x2F94u,
                                   this[4],
                                   &v79,
                                   &v69);
                        if ( String >= 0 )
                        {
                          if ( (STRU::QueryCCH((STRU *)v93) <= 0x1000 || STRU::SetLen((STRU *)v93, 0x1000u))
                            && (STRU::QueryCCH((STRU *)v94) <= 0x1000 || STRU::SetLen((STRU *)v94, 0x1000u))
                            && (STRU::QueryCCH((STRU *)v95) <= 0x1000 || STRU::SetLen((STRU *)v95, 0x1000u)) )
                          {
                            Str = STRU::QueryStr((STRU *)v100);
                            LODWORD(v70) = CUSTOM_ERROR_HANDLER::sm_dwOSBuildNumber;
                            if ( v83 )
                              v41 = STRU::QueryStr(v83);
                            else
                              v41 = L"https://go.microsoft.com/fwlink/?LinkID=62293";
                            v42 = v78;
                            v62 = (struct STRU *)v41;
                            v43 = STRU::QueryStr((STRU *)v95);
                            v44 = STRU::QueryStr((STRU *)v101);
                            v45 = STRU::QueryStr((STRU *)v102);
                            v46 = STRU::QueryStr((STRU *)v94);
                            v47 = STRU::QueryStr((STRU *)v93);
                            v48 = STRU::QueryStr((STRU *)v99);
                            v49 = STRU::QueryStr((STRU *)v97);
                            LODWORD(v55) = a8;
                            LODWORD(v53) = a7;
                            String = SAFE_snwprintf(
                                       (struct STRU *)v98,
                                       v82,
                                       a7,
                                       a8,
                                       v88,
                                       v79,
                                       v53,
                                       v55,
                                       v88,
                                       v81,
                                       v49,
                                       v87,
                                       v86,
                                       v85,
                                       v60,
                                       v48,
                                       v47,
                                       v46,
                                       v80,
                                       v45,
                                       v44,
                                       v43,
                                       v42,
                                       v62,
                                       a7,
                                       a8,
                                       v60,
                                       (_DWORD)v70,
                                       Str);
                            if ( String >= 0 )
                            {
                              String = STRA::CopyWToUTF8Unescaped((STRA *)v96, (const struct STRU *)v98);
                              if ( String >= 0 )
                              {
                                LODWORD(v91) = 0;
                                *((_QWORD *)&v91 + 1) = STRA::QueryStr((STRA *)v96);
                                CCH = STRA::QueryCCH((STRA *)v96);
                                v51 = v90;
                                LODWORD(v92) = CCH;
                                *((_DWORD *)v89 + 6) = 0;
                                String = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, _DWORD, int *, _QWORD))(*(_QWORD *)v51 + 168LL))(
                                           v51,
                                           &v91,
                                           1,
                                           0,
                                           0,
                                           &v71,
                                           0);
                              }
                            }
                          }
                          else
                          {
                            String = -2147024883;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_49:
  STRA::~STRA((STRA *)v96);
  STRU::~STRU((STRU *)v98);
  STRU::~STRU((STRU *)v95);
  STRU::~STRU((STRU *)v99);
  STRU::~STRU((STRU *)v97);
  STRU::~STRU((STRU *)v100);
  STRU::~STRU((STRU *)v101);
  STRU::~STRU((STRU *)v102);
  STRU::~STRU((STRU *)v94);
  STRU::~STRU((STRU *)v93);
  STRU::~STRU((STRU *)v103);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180005988  push    rbp
0x18000598a  push    rbx
0x18000598b  push    rsi
0x18000598c  push    rdi
0x18000598d  push    r12
0x18000598f  push    r13
0x180005991  push    r14
0x180005993  push    r15
0x180005995  lea     rbp, [rsp-508h]
0x18000599d  sub     rsp, 678h
0x1800059a4  mov     rax, cs:__security_cookie
0x1800059ab  xor     rax, rsp
0x1800059ae  mov     [rbp+540h+var_50], rax
0x1800059b5  mov     rax, [rbp+540h+arg_40]
0x1800059bc  mov     rbx, rdx
0x1800059bf  mov     esi, [rbp+540h+arg_20]
0x1800059c5  mov     r15, rcx
0x1800059c8  mov     r14, [rbp+540h+arg_28]
0x1800059cf  mov     r13d, 80h
0x1800059d5  mov     [rbp+540h+var_5A8], rax
0x1800059d9  xor     edx, edx; Val
0x1800059db  mov     rax, [rbp+540h+arg_48]
0x1800059e2  mov     rdi, r9
0x1800059e5  mov     [rbp+540h+var_518], rax
0x1800059e9  mov     rax, [rbp+540h+arg_50]
0x1800059f0  mov     [rbp+540h+var_5B4], r8d
0x1800059f4  mov     r8d, r13d; Size
0x1800059f7  mov     [rbp+540h+var_4E8], rcx
0x1800059fb  lea     rcx, [rbp+540h+var_250]; void *
0x180005a02  mov     [rbp+540h+var_580], rax
0x180005a06  mov     [rbp+540h+var_5B0], 0
0x180005a0e  mov     [rbp+540h+var_5BC], 0
0x180005a15  call    memset_0
0x180005a1a  lea     r12d, [r13-40h]
0x180005a1e  mov     r8d, r12d
0x180005a21  lea     rdx, [rbp+540h+var_250]
0x180005a28  lea     rcx, [rbp+540h+var_288]
0x180005a2f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005a35  lea     rcx, [rbp+540h+var_4B8]
0x180005a3c  mov     [rbp+540h+var_568], 0
0x180005a44  mov     [rbp+540h+var_5C0], 0
0x180005a4b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005a51  mov     r8d, r13d; Size
0x180005a54  lea     rcx, [rbp+540h+var_1D0]; void *
0x180005a5b  xor     edx, edx; Val
0x180005a5d  call    memset_0
0x180005a62  mov     r8d, r12d
0x180005a65  lea     rdx, [rbp+540h+var_1D0]
0x180005a6c  lea     rcx, [rbp+540h+var_480]
0x180005a73  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005a79  lea     rcx, [rbp+540h+var_2C0]
0x180005a80  mov     [rbp+540h+var_570], 0
0x180005a88  mov     [rbp+540h+var_5A0], 0
0x180005a8f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005a95  xor     eax, eax
0x180005a97  lea     rcx, [rbp+540h+var_150]; void *
0x180005a9e  mov     r8d, r13d; Size
0x180005aa1  mov     [rbp+540h+var_530], rax
0x180005aa5  xor     edx, edx; Val
0x180005aa7  mov     [rbp+540h+var_560], rax
0x180005aab  mov     [rbp+540h+var_590], eax
0x180005aae  mov     [rbp+540h+var_550], rax
0x180005ab2  mov     [rbp+540h+var_594], eax
0x180005ab5  mov     [rbp+540h+var_558], rax
0x180005ab9  mov     [rbp+540h+var_598], eax
0x180005abc  mov     [rbp+540h+var_540], rax
0x180005ac0  mov     [rbp+540h+var_59C], eax
0x180005ac3  mov     [rbp+540h+var_548], rax
0x180005ac7  mov     [rbp+540h+var_5B8], eax
0x180005aca  call    memset_0
0x180005acf  mov     r8d, r12d
0x180005ad2  lea     rdx, [rbp+540h+var_150]
0x180005ad9  lea     rcx, [rbp+540h+var_2F8]
0x180005ae0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005ae6  mov     r8d, r13d; Size
0x180005ae9  lea     rcx, [rbp+540h+var_D0]; void *
0x180005af0  xor     edx, edx; Val
0x180005af2  call    memset_0
0x180005af7  mov     r8d, r12d
0x180005afa  lea     rdx, [rbp+540h+var_D0]
0x180005b01  lea     rcx, [rbp+540h+var_330]
0x180005b08  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005b0e  lea     rcx, [rbp+540h+var_3D8]
0x180005b15  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005b1b  lea     rcx, [rbp+540h+var_368]
0x180005b22  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005b28  lea     rcx, [rbp+540h+var_448]
0x180005b2f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005b35  lea     rcx, [rbp+540h+var_3A0]
0x180005b3c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005b42  lea     rcx, [rbp+540h+var_410]
0x180005b49  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180005b4f  xor     r12d, r12d
0x180005b52  mov     [rbp+540h+var_520], r12
0x180005b56  mov     rax, [r14]
0x180005b59  mov     rcx, r14
0x180005b5c  mov     [rbp+540h+var_58C], r12d
0x180005b60  mov     [rbp+540h+var_538], r12
0x180005b64  mov     [rbp+540h+var_588], r12d
0x180005b68  mov     rax, [rax+20h]
0x180005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b71  mov     r13, rax
0x180005b74  mov     [rbp+540h+var_4E0], rax
0x180005b78  mov     [rbp+540h+var_578], r12d
0x180005b7c  lea     rax, dword_180009DAC
0x180005b83  xorps   xmm0, xmm0
0x180005b86  lea     r12, Str
0x180005b8d  test    rbx, rbx
0x180005b90  mov     rcx, r13
0x180005b93  movups  [rbp+540h+var_4D8], xmm0
0x180005b97  cmovnz  rax, rbx
0x180005b9b  test    rdi, rdi
0x180005b9e  mov     [rbp+540h+var_4F0], rax
0x180005ba2  mov     rax, r12
0x180005ba5  cmovnz  rax, rdi
0x180005ba9  mov     [rbp+540h+var_4F8], rax
0x180005bad  movups  [rbp+540h+var_4C8], xmm0
0x180005bb1  mov     rax, [r13+0]
0x180005bb5  mov     rax, [rax+8]
0x180005bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbe  lea     rcx, aTextHtmlCharse; "text/html; charset=utf-8"
0x180005bc5  mov     [rax+100h], rcx
0x180005bcc  mov     rcx, r13
0x180005bcf  mov     word ptr [rax+0F8h], 18h
0x180005bd8  mov     rax, [r13+0]
0x180005bdc  mov     rax, [rax+8]
0x180005be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be5  lea     rcx, aPrivate; "private"
0x180005bec  mov     [rax+40h], rcx
0x180005bf0  mov     rcx, r14
0x180005bf3  mov     word ptr [rax+38h], 7
0x180005bf9  mov     rax, [r14]
0x180005bfc  mov     rax, [rax+8]
0x180005c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c05  mov     rdx, rax
0x180005c08  mov     rcx, [rax]
0x180005c0b  mov     rax, [rcx+10h]
0x180005c0f  mov     rcx, rdx
0x180005c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c17  mov     r8, [r15+20h]
0x180005c1b  lea     r9, [rbp+540h+var_5B0]
0x180005c1f  xor     ecx, ecx
0x180005c21  mov     rdi, rax
0x180005c24  cmp     cx, [rax+2Eh]
0x180005c28  lea     rax, [rbp+540h+var_5BC]
0x180005c2c  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180005c33  mov     [rsp+6B0h+var_690], rax
0x180005c38  jnz     short loc_180005C62
0x180005c3a  mov     edx, 2F91h
0x180005c3f  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180005c45  mov     ebx, eax
0x180005c47  test    eax, eax
0x180005c49  js      loc_1800062E8
0x180005c4f  mov     rdx, [rbp+540h+var_5B0]
0x180005c53  lea     rcx, [rbp+540h+var_288]
0x180005c5a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005c60  jmp     short loc_180005C8C
0x180005c62  mov     edx, 2F92h
0x180005c67  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180005c6d  mov     ebx, eax
0x180005c6f  test    eax, eax
0x180005c71  js      loc_1800062E8
0x180005c77  mov     rdx, [rbp+540h+var_5B0]
0x180005c7b  lea     r8, [rdi+30h]
0x180005c7f  lea     rcx, [rbp+540h+var_288]
0x180005c86  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x180005c8c  mov     ebx, eax
0x180005c8e  test    eax, eax
0x180005c90  js      loc_1800062E8
0x180005c96  mov     edx, esi; unsigned int
0x180005c98  mov     rcx, r15; this
0x180005c9b  call    ?NotificationToString@CUSTOM_ERROR_HANDLER@@AEAAPEBGK@Z; CUSTOM_ERROR_HANDLER::NotificationToString(ulong)
0x180005ca0  mov     rcx, [r14]
0x180005ca3  mov     [rbp+540h+var_500], rax
0x180005ca7  mov     rax, [rcx+18h]
0x180005cab  mov     rcx, r14
0x180005cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb3  mov     rdx, rax
0x180005cb6  mov     rcx, [rax]
0x180005cb9  mov     rax, [rcx+8]
0x180005cbd  mov     rcx, rdx
0x180005cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc5  mov     rcx, r14
0x180005cc8  mov     rsi, [rax+48h]
0x180005ccc  mov     rax, [r14]
0x180005ccf  mov     rax, [rax+18h]
0x180005cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd8  mov     rcx, [r14]
0x180005cdb  mov     rdi, rax
0x180005cde  mov     rax, [rcx+18h]
0x180005ce2  mov     rcx, r14
0x180005ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cea  mov     rdx, rax
0x180005ced  mov     rcx, [rax]
0x180005cf0  mov     rax, [rcx+8]
0x180005cf4  mov     rcx, rdx
0x180005cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfc  mov     rcx, rdi
0x180005cff  movzx   ebx, word ptr [rax+46h]
0x180005d03  mov     rax, [rdi]
0x180005d06  mov     rax, [rax+8]
0x180005d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d0f  mov     rdx, rsi
0x180005d12  lea     rcx, [rbp+540h+var_4B8]
0x180005d19  movzx   r8d, word ptr [rax+40h]
0x180005d1e  sub     r8, rbx
0x180005d21  shr     r8, 1
0x180005d24  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180005d2a  mov     ebx, eax
0x180005d2c  test    eax, eax
0x180005d2e  js      loc_1800062E8
0x180005d34  mov     rax, [r14]
0x180005d37  lea     r9, [rbp+540h+var_5C0]
0x180005d3b  lea     r8, [rbp+540h+var_568]
0x180005d3f  mov     rcx, r14
0x180005d42  lea     rdx, aQueryString; "QUERY_STRING"
0x180005d49  mov     rax, [rax+80h]
0x180005d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d55  mov     ebx, eax
0x180005d57  test    eax, eax
0x180005d59  js      loc_1800062E8
0x180005d5f  cmp     [rbp+540h+var_5C0], 0
0x180005d63  jbe     short loc_180005DA8
0x180005d65  mov     r8d, 1
0x180005d6b  lea     rdx, asc_180009B30; "?"
0x180005d72  lea     rcx, [rbp+540h+var_4B8]
0x180005d79  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180005d7f  mov     ebx, eax
0x180005d81  test    eax, eax
0x180005d83  js      loc_1800062E8
0x180005d89  mov     r8d, [rbp+540h+var_5C0]
0x180005d8d  lea     rcx, [rbp+540h+var_4B8]
0x180005d94  mov     rdx, [rbp+540h+var_568]
0x180005d98  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180005d9e  mov     ebx, eax
0x180005da0  test    eax, eax
0x180005da2  js      loc_1800062E8
0x180005da8  lea     rcx, [rbp+540h+var_4B8]
0x180005daf  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180005db5  mov     ebx, eax
0x180005db7  test    eax, eax
0x180005db9  js      loc_1800062E8
0x180005dbf  mov     rax, [r14]
0x180005dc2  xor     edx, edx
0x180005dc4  mov     rcx, r14
0x180005dc7  mov     rax, [rax+0A8h]
0x180005dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd3  test    rax, rax
0x180005dd6  jz      short loc_180005E09
0x180005dd8  mov     rdx, rax
0x180005ddb  lea     rcx, [rbp+540h+var_480]
0x180005de2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005de8  mov     ebx, eax
0x180005dea  test    eax, eax
0x180005dec  js      loc_1800062E8
0x180005df2  lea     rcx, [rbp+540h+var_480]
0x180005df9  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180005dff  mov     ebx, eax
0x180005e01  test    eax, eax
0x180005e03  js      loc_1800062E8
0x180005e09  mov     r8, [r15+20h]
0x180005e0d  lea     rax, [rbp+540h+var_5A0]
0x180005e11  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180005e18  lea     r9, [rbp+540h+var_570]
0x180005e1c  mov     edx, 2F8Dh
0x180005e21  mov     [rsp+6B0h+var_690], rax
0x180005e26  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180005e2c  mov     ebx, eax
0x180005e2e  test    eax, eax
0x180005e30  js      loc_1800062E8
0x180005e36  mov     rax, [r14]
0x180005e39  mov     rcx, r14
0x180005e3c  mov     rbx, [rbp+540h+var_570]
0x180005e40  mov     rax, [rax+30h]
0x180005e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e49  lea     rcx, [rbp+540h+var_530]
0x180005e4d  mov     r9, rbx; unsigned __int16 *
0x180005e50  mov     [rsp+6B0h+var_688], rcx; unsigned __int16 **
0x180005e55  mov     r8, rax; struct IHttpUser *
0x180005e58  lea     rcx, [rbp+540h+var_2C0]
0x180005e5f  mov     [rsp+6B0h+var_690], rcx; struct STRU *
0x180005e64  mov     rcx, r15; this
0x180005e67  call    ?WriteDetailedLogonUserMethod@CUSTOM_ERROR_HANDLER@@AEAAJKPEAVIHttpUser@@PEBGPEAVSTRU@@PEAPEBG@Z; CUSTOM_ERROR_HANDLER::WriteDetailedLogonUserMethod(ulong,IHttpUser *,ushort const *,STRU *,ushort const * *)
0x180005e6c  mov     ebx, eax
0x180005e6e  test    eax, eax
0x180005e70  js      loc_1800062E8
0x180005e76  mov     rax, [r14]
0x180005e79  mov     rcx, r14
0x180005e7c  mov     rax, [rax+0C0h]
0x180005e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e88  test    rax, rax
0x180005e8b  jz      short loc_180005EB4
0x180005e8d  mov     rax, [r14]
0x180005e90  mov     rcx, r14
0x180005e93  mov     rax, [rax+0C0h]
0x180005e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9f  mov     rdx, rax
0x180005ea2  mov     rcx, [rax]
0x180005ea5  mov     rax, [rcx+50h]
0x180005ea9  mov     rcx, rdx
  ... truncated ...
```
