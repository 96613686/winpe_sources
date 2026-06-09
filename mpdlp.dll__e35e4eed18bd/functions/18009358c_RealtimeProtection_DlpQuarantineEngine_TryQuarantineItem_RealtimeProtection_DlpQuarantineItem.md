# RealtimeProtection::DlpQuarantineEngine::TryQuarantineItem(RealtimeProtection::_DlpQuarantineItem &)

- ea: `0x18009358c`
- end: `0x180093d74`
- name: `?TryQuarantineItem@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@@Z`
- size: `2024`
- prototype: `bool(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180092dc0`

## callees

- `0x180034420`
- `0x180038450`
- `0x1800398a0`
- `0x1800809d0`
- `0x180083a80`
- `0x180089510`
- `0x18009351c`
- `0x18009358c`
- `0x180093d74`
- `0x180093e08`
- `0x180094038`
- `0x1800943fc`
- `0x1801047b4`
- `0x180104c34`
- `0x18010cb40`
- `0x180119740`
- `0x18012736c`
- `0x18013df60`
- `0x18014da1c`
- `0x1801fc75c`
- `0x1801fee68`
- `0x1801ff278`
- `0x180201c60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180093a94`
- `KERNEL32!CloseHandle` at `0x180093a94`
- `ADVAPI32!SetThreadToken` at `0x18009379c`
- `ADVAPI32!SetThreadToken` at `0x18009379c`
- `ADVAPI32!RevertToSelf` at `0x180093c74`
- `ADVAPI32!RevertToSelf` at `0x180093d3f`
- `ADVAPI32!RevertToSelf` at `0x180093c74`
- `ADVAPI32!RevertToSelf` at `0x180093d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall RealtimeProtection::DlpQuarantineEngine::TryQuarantineItem(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2)
{
  struct RealtimeProtection::_DlpQuarantineItem *v2; // r15
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // r9
  __int64 v8; // rax
  const wchar_t *v9; // r13
  _QWORD *v10; // r14
  __int64 v11; // rax
  int v12; // ebx
  RealtimeProtection::DlpQuarantineEngine *v13; // rcx
  void *v14; // rdx
  char v15; // r13
  _QWORD *v16; // rax
  RealtimeProtection::DlpQuarantineEngine *v17; // rcx
  char v18; // bl
  const struct std::filesystem::path *v19; // r8
  char v20; // dl
  __int64 *v21; // rbx
  __int64 v22; // rax
  _BYTE *v23; // r14
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // eax
  const wchar_t *v27; // r9
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  struct _iobuf **v30; // rdx
  const wchar_t *v31; // rcx
  HANDLE *v32; // r14
  int File; // eax
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rdx
  _QWORD *v37; // r9
  _QWORD *v39; // rax
  _QWORD *v40; // r9
  _QWORD *v41; // rax
  _QWORD *v42; // rax
  char v43; // di
  void **v44; // rbx
  _QWORD *v45; // rcx
  const WCHAR *v46; // rcx
  RealtimeProtection::DlpQuarantineEngine *v47; // [rsp+40h] [rbp-148h]
  void **v49; // [rsp+50h] [rbp-138h]
  void **v50; // [rsp+50h] [rbp-138h]
  RealtimeProtection::DlpQuarantineEngine *v52; // [rsp+70h] [rbp-118h]
  char v53; // [rsp+80h] [rbp-108h]
  _BYTE v54[32]; // [rsp+88h] [rbp-100h] BYREF
  char *v55; // [rsp+A8h] [rbp-E0h]
  __int64 *v56; // [rsp+B0h] [rbp-D8h]
  RealtimeProtection::DlpQuarantineEngine *v57; // [rsp+B8h] [rbp-D0h]
  RealtimeProtection::DlpQuarantineEngine *v58; // [rsp+C0h] [rbp-C8h]
  char v59; // [rsp+C8h] [rbp-C0h]
  void *v60; // [rsp+D0h] [rbp-B8h]
  char *v61; // [rsp+D8h] [rbp-B0h]
  _QWORD v62[4]; // [rsp+E0h] [rbp-A8h] BYREF
  const std::filesystem::filesystem_error *v63; // [rsp+100h] [rbp-88h] BYREF
  FILE *Stream; // [rsp+108h] [rbp-80h] BYREF
  char v65; // [rsp+110h] [rbp-78h] BYREF
  _QWORD Src[3]; // [rsp+118h] [rbp-70h] BYREF
  unsigned __int64 v67; // [rsp+130h] [rbp-58h]
  wchar_t *Buffer[4]; // [rsp+138h] [rbp-50h] BYREF

  v2 = a2;
  v52 = this;
  v57 = this;
  v58 = this;
  v62[0] = a2;
  v65 = 0;
  Stream = 0;
  if ( *(_DWORD *)a2 == 7 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 0;
    v4 = 74;
LABEL_25:
    WPP_SF_(v3[2], v4, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids);
    return 0;
  }
  v47 = (struct RealtimeProtection::_DlpQuarantineItem *)((char *)a2 + 48);
  v49 = (void **)((char *)a2 + 48);
  if ( !*((_BYTE *)a2 + 48) )
  {
    v5 = RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(this, a2);
    if ( v5 < 0 )
    {
      *(_DWORD *)v2 = 7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (unsigned int)v5);
      return 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = (_QWORD *)((char *)v2 + 152);
    if ( *((_QWORD *)v2 + 22) > 7u )
      v6 = (_QWORD *)*v6;
    v7 = (_QWORD *)((char *)v2 + 224);
    if ( *((_QWORD *)v2 + 31) > 7u )
      v7 = (_QWORD *)*v7;
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
      (_DWORD)v7,
      (__int64)v6);
  }
  v8 = std::filesystem::path::parent_path((char *)v2 + 272, Buffer);
  v9 = (const wchar_t *)v8;
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v9 = *(const wchar_t **)v8;
  v10 = (_QWORD *)((char *)v2 + 224);
  v11 = std::filesystem::path::parent_path((char *)v2 + 224, v54);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v11 = *(_QWORD *)v11;
  v12 = wcsicmp((const wchar_t *)v11, v9);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v54);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Buffer);
  if ( !v12 )
  {
    *(_DWORD *)v2 = 7;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 0;
    v4 = 77;
    goto LABEL_25;
  }
  v14 = 0;
  if ( *((_DWORD *)v2 + 1) == 3 )
    v14 = (void *)*((_QWORD *)a2 + 90);
  if ( v14 && SetThreadToken(0, v14) )
  {
    v15 = 1;
    v53 = 1;
  }
  else
  {
    v15 = 0;
    v53 = 0;
  }
  if ( !RealtimeProtection::DlpQuarantineEngine::DoesItemToQuarantineExist(v13, v2) )
  {
    *(_DWORD *)v2 = 7;
    goto LABEL_114;
  }
  if ( *((_BYTE *)a2 + 54) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = (_QWORD *)((char *)a2 + 152);
      if ( *((_QWORD *)a2 + 22) > 7u )
        v16 = (_QWORD *)*v16;
      if ( *((_QWORD *)v2 + 31) > 7u )
        v10 = (_QWORD *)*v10;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        (_DWORD)v10,
        (__int64)v16);
    }
    goto LABEL_114;
  }
  v59 = 0;
  v60 = v47;
  v61 = &v65;
  v18 = RealtimeProtection::DlpQuarantineEngine::QuarantineFile(v47, v2, 1u);
  v65 = v18;
  if ( v18 )
  {
    v20 = 1;
  }
  else
  {
    v18 = RealtimeProtection::DlpQuarantineEngine::QuarantineFile(v17, v2, 0);
    v65 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v39 = (_QWORD *)((char *)a2 + 152);
        if ( *((_QWORD *)a2 + 22) > 7u )
          v39 = (_QWORD *)*v39;
        LODWORD(v40) = (_DWORD)v2 + 224;
        if ( *((_QWORD *)v2 + 31) > 7u )
          v40 = (_QWORD *)*v10;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (_DWORD)v40,
          (__int64)v39);
        v18 = v65;
      }
      if ( (*((_BYTE *)v2 + 8) & 1) != 0 )
      {
        *((_BYTE *)a2 + 54) = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v41 = (_QWORD *)((char *)a2 + 152);
          if ( *((_QWORD *)a2 + 22) > 7u )
            v41 = (_QWORD *)*v41;
          if ( *((_QWORD *)v2 + 31) > 7u )
            v10 = (_QWORD *)*v10;
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
            (_DWORD)v10,
            (__int64)v41);
          v18 = v65;
        }
      }
      *((_BYTE *)v47 + 1) = v18;
      goto LABEL_114;
    }
    v20 = 0;
  }
  v55 = (char *)a2 + 50;
  *((_BYTE *)a2 + 50) = v20;
  if ( v18 == 1 && *((_BYTE *)a2 + 537) == 1 )
  {
    try
    {
      v21 = (__int64 *)((char *)v47 + 352);
      v56 = (__int64 *)((char *)v47 + 352);
      std::filesystem::rename(
        (struct RealtimeProtection::_DlpQuarantineItem *)((char *)v2 + 224),
        (RealtimeProtection::DlpQuarantineEngine *)((char *)v47 + 352),
        v19);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v22 = (__int64)v47 + 352;
        if ( *((_QWORD *)v47 + 47) > 7u )
          v22 = *v21;
        if ( *((_QWORD *)v2 + 31) > 7u )
          v10 = (_QWORD *)*v10;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (_DWORD)v10,
          v22);
      }
    }
    catch ( const std::filesystem::filesystem_error *v63 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v44 = v49;
        v43 = 0;
      }
      else
      {
        v42 = (_QWORD *)std::error_code::message((char *)v63 + 24, v54);
        v43 = 1;
        if ( v42[3] > 0xFu )
          v42 = (_QWORD *)*v42;
        v44 = v49;
        v45 = v49 + 44;
        if ( (unsigned __int64)v49[47] > 7 )
          v45 = (_QWORD *)*v45;
        WPP_SF_SSs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v45, (__int64)v42);
      }
      if ( (v43 & 1) != 0 )
        std::string::_Tidy_deallocate(v54);
      v46 = (const WCHAR *)(v44 + 22);
      if ( (unsigned __int64)v44[25] > 7 )
        v46 = *(const WCHAR **)v46;
      DeleteFileW(v46);
      v15 = v53;
      v47 = (RealtimeProtection::DlpQuarantineEngine *)v60;
      v23 = v55;
      v21 = v56;
      v52 = v57;
      v2 = (struct RealtimeProtection::_DlpQuarantineItem *)v62[0];
      goto LABEL_57;
    }
    v23 = (char *)a2 + 50;
LABEL_57:
    std::wstring::wstring(Buffer, (char *)a2 + 504);
    LOBYTE(v24) = *v23;
    v26 = RealtimeProtection::DlpQuarantineEngine::ParseReplacementText(v25, v2, Buffer, v24);
    if ( v26 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v29 = 83;
LABEL_61:
      WPP_SF_d(v28[2], v29, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, (unsigned int)v26);
LABEL_62:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Buffer);
      *((_BYTE *)v47 + 1) = v65;
LABEL_114:
      if ( v15 )
        RevertToSelf();
      return 0;
    }
    v30 = (struct _iobuf **)v21;
    if ( (unsigned __int64)v21[3] > 7 )
      v30 = (struct _iobuf **)*v21;
    v26 = CommonUtil::UtilFileOpen((CommonUtil *)&Stream, v30, L"w+", v27);
    if ( v26 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v29 = 84;
      goto LABEL_61;
    }
    v31 = (const wchar_t *)Buffer;
    if ( Buffer[3] > (wchar_t *)7 )
      v31 = Buffer[0];
    fputws(v31, Stream);
    fclose(Stream);
    if ( !*((_BYTE *)v2 + 1808) )
      goto LABEL_82;
    v50 = (void **)v21;
    if ( (unsigned __int64)v21[3] > 7 )
      v50 = (void **)*v21;
    v32 = (HANDLE *)((char *)v2 + 1800);
    if ( *((_QWORD *)v2 + 225) != -1 )
    {
      CloseHandle(*v32);
      *v32 = (HANDLE)-1LL;
    }
    File = CommonUtil::UtilCreateFile(
             (struct RealtimeProtection::_DlpQuarantineItem *)((char *)v2 + 1800),
             (const WCHAR *)v50,
             (const wchar_t *)0x13019F,
             1u,
             3u,
             0,
             0,
             0);
    if ( File < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        (unsigned int)File);
    if ( !*((_BYTE *)v2 + 1808) || *((_QWORD *)v2 + 225) == -1 )
    {
LABEL_82:
      v34 = (_QWORD *)std::filesystem::path::parent_path((char *)a2 + 192, v62);
      if ( v34[3] > 7u )
        v34 = (_QWORD *)*v34;
      std::wstring::wstring(Src, v34);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
      std::wstring::append(Src, (void *)L"\\");
      v35 = (_QWORD *)std::filesystem::path::filename(v21, v54);
      if ( v35[3] > 7u )
        v35 = (_QWORD *)*v35;
      std::wstring::append(Src, v35);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v54);
      v36 = Src;
      if ( v67 > 7 )
        v36 = (_QWORD *)Src[0];
      std::wstring::wstring(v54, v36);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        (char *)v52 + 64,
        v62,
        v54);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v54);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v37 = Src;
        if ( v67 > 7 )
          LODWORD(v37) = Src[0];
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (_DWORD)v37,
          *((_DWORD *)v58 + 20));
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Buffer);
    v18 = v65;
  }
  *((_BYTE *)v47 + 1) = v18;
  if ( v15 )
    RevertToSelf();
  return v18;
}

```

## disassembly

```asm
0x18009358c  mov     r11, rsp
0x18009358f  mov     [r11+18h], rbx
0x180093593  mov     [r11+20h], rsi
0x180093597  push    rdi
0x180093598  push    r12
0x18009359a  push    r13
0x18009359c  push    r14
0x18009359e  push    r15
0x1800935a0  sub     rsp, 160h
0x1800935a7  mov     rax, cs:__security_cookie
0x1800935ae  xor     rax, rsp
0x1800935b1  mov     [rsp+188h+var_30], rax
0x1800935b9  mov     r15, rdx
0x1800935bc  mov     [rsp+188h+var_118], rcx
0x1800935c1  mov     [rsp+188h+var_D0], rcx
0x1800935c9  mov     [rsp+188h+var_C8], rcx
0x1800935d1  mov     [rsp+188h+var_A8], rdx
0x1800935d9  mov     [rsp+188h+var_140], rdx
0x1800935de  mov     [rsp+188h+var_128], rdx
0x1800935e3  xor     edi, edi
0x1800935e5  mov     [rsp+188h+var_130], edi
0x1800935e9  mov     [r11-78h], dil
0x1800935ed  mov     [r11-80h], rdi
0x1800935f1  lea     esi, [rdi+7]
0x1800935f4  cmp     [rdx], esi
0x1800935f6  jnz     short loc_180093621
0x1800935f8  lea     r12, WPP_GLOBAL_Control
0x1800935ff  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180093606  cmp     rcx, r12
0x180093609  jz      loc_180093D45
0x18009360f  test    byte ptr [rcx+1Ch], 10h
0x180093613  jz      loc_180093D45
0x180093619  lea     edx, [rdi+4Ah]; struct RealtimeProtection::_DlpQuarantineItem *
0x18009361c  jmp     loc_18009375D
0x180093621  lea     rax, [rdx+30h]
0x180093625  mov     [rsp+188h+var_148], rax
0x18009362a  mov     [rsp+188h+var_138], rax
0x18009362f  cmp     [rax], dil
0x180093632  jnz     short loc_18009367E
0x180093634  call    ?ResolveQuarantineItemPaths@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEAU_DlpQuarantineItem@2@@Z; RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(RealtimeProtection::_DlpQuarantineItem &)
0x180093639  test    eax, eax
0x18009363b  jns     short loc_18009367E
0x18009363d  mov     [r15], esi
0x180093640  lea     r12, WPP_GLOBAL_Control
0x180093647  mov     rcx, cs:WPP_GLOBAL_Control
0x18009364e  cmp     rcx, r12
0x180093651  jz      loc_180093D45
0x180093657  test    byte ptr [rcx+1Ch], 1
0x18009365b  jz      loc_180093D45
0x180093661  mov     edx, 4Bh ; 'K'
0x180093666  mov     r9d, eax
0x180093669  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180093670  mov     rcx, [rcx+10h]
0x180093674  call    WPP_SF_d
0x180093679  jmp     loc_180093D45
0x18009367e  lea     r12, WPP_GLOBAL_Control
0x180093685  mov     rcx, cs:WPP_GLOBAL_Control
0x18009368c  cmp     rcx, r12
0x18009368f  jz      short loc_1800936D1
0x180093691  test    byte ptr [rcx+1Ch], 4
0x180093695  jz      short loc_1800936D1
0x180093697  lea     rax, [r15+98h]
0x18009369e  cmp     [rax+18h], rsi
0x1800936a2  jbe     short loc_1800936A7
0x1800936a4  mov     rax, [rax]
0x1800936a7  lea     r9, [r15+0E0h]
0x1800936ae  cmp     [r9+18h], rsi
0x1800936b2  jbe     short loc_1800936B7
0x1800936b4  mov     r9, [r9]
0x1800936b7  mov     edx, 4Ch ; 'L'
0x1800936bc  mov     qword ptr [rsp+188h+var_168], rax
0x1800936c1  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1800936c8  mov     rcx, [rcx+10h]
0x1800936cc  call    WPP_SF_SS
0x1800936d1  lea     rcx, [r15+110h]
0x1800936d8  lea     rdx, [rsp+188h+Buffer]
0x1800936e0  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1800936e5  mov     r13, rax
0x1800936e8  cmp     [rax+18h], rsi
0x1800936ec  jbe     short loc_1800936F1
0x1800936ee  mov     r13, [rax]
0x1800936f1  lea     r14, [r15+0E0h]
0x1800936f8  lea     rdx, [rsp+188h+var_100]
0x180093700  mov     rcx, r14
0x180093703  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x180093708  cmp     [rax+18h], rsi
0x18009370c  jbe     short loc_180093711
0x18009370e  mov     rax, [rax]
0x180093711  mov     rdx, r13; String2
0x180093714  mov     rcx, rax; String1
0x180093717  call    _wcsicmp
0x18009371c  mov     ebx, eax
0x18009371e  lea     rcx, [rsp+188h+var_100]; void *
0x180093726  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18009372b  nop
0x18009372c  lea     rcx, [rsp+188h+Buffer]; void *
0x180093734  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180093739  test    ebx, ebx
0x18009373b  jnz     short loc_180093772
0x18009373d  mov     [r15], esi
0x180093740  mov     rcx, cs:WPP_GLOBAL_Control
0x180093747  cmp     rcx, r12
0x18009374a  jz      loc_180093D45
0x180093750  test    byte ptr [rcx+1Ch], 2
0x180093754  jz      loc_180093D45
0x18009375a  lea     edx, [rbx+4Dh]
0x18009375d  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180093764  mov     rcx, [rcx+10h]
0x180093768  call    WPP_SF_
0x18009376d  jmp     loc_180093D45
0x180093772  mov     rdx, rdi
0x180093775  cmp     dword ptr [r15+4], 3
0x18009377a  jnz     short loc_180093788
0x18009377c  mov     rdx, [rsp+188h+var_128]
0x180093781  mov     rdx, [rdx+2D0h]; Token
0x180093788  xorps   xmm0, xmm0
0x18009378b  movups  [rsp+188h+var_110], xmm0
0x180093790  mov     qword ptr [rsp+188h+var_110], rdx
0x180093795  test    rdx, rdx
0x180093798  jz      short loc_1800937B3
0x18009379a  xor     ecx, ecx; Thread
0x18009379c  call    cs:__imp_SetThreadToken
0x1800937a2  test    eax, eax
0x1800937a4  jz      short loc_1800937B3
0x1800937a6  mov     r13b, 1
0x1800937a9  mov     byte ptr [rsp+188h+var_110+8], r13b
0x1800937b1  jmp     short loc_1800937BE
0x1800937b3  mov     r13b, dil
0x1800937b6  mov     byte ptr [rsp+188h+var_110+8], dil
0x1800937be  mov     rdx, r15; struct RealtimeProtection::_DlpQuarantineItem *
0x1800937c1  call    ?DoesItemToQuarantineExist@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEBU_DlpQuarantineItem@2@@Z; RealtimeProtection::DlpQuarantineEngine::DoesItemToQuarantineExist(RealtimeProtection::_DlpQuarantineItem const &)
0x1800937c6  test    al, al
0x1800937c8  jnz     short loc_1800937D2
0x1800937ca  mov     [r15], esi
0x1800937cd  jmp     loc_180093D3A
0x1800937d2  mov     rax, [rsp+188h+var_140]
0x1800937d7  cmp     [rax+36h], dil
0x1800937db  jz      short loc_180093831
0x1800937dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800937e4  cmp     rcx, r12
0x1800937e7  jz      loc_180093D3A
0x1800937ed  test    byte ptr [rcx+1Ch], 4
0x1800937f1  jz      loc_180093D3A
0x1800937f7  add     rax, 98h
0x1800937fd  cmp     [rax+18h], rsi
0x180093801  jbe     short loc_180093806
0x180093803  mov     rax, [rax]
0x180093806  cmp     [r14+18h], rsi
0x18009380a  jbe     short loc_18009380F
0x18009380c  mov     r14, [r14]
0x18009380f  mov     edx, 4Eh ; 'N'
0x180093814  mov     qword ptr [rsp+188h+var_168], rax
0x180093819  mov     r9, r14
0x18009381c  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180093823  mov     rcx, [rcx+10h]
0x180093827  call    WPP_SF_SS
0x18009382c  jmp     loc_180093D3A
0x180093831  mov     [rsp+188h+var_C0], dil
0x180093839  mov     rcx, [rsp+188h+var_148]; this
0x18009383e  mov     [rsp+188h+var_B8], rcx
0x180093846  lea     rax, [rsp+188h+var_78]
0x18009384e  mov     [rsp+188h+var_B0], rax
0x180093856  mov     r8b, 1; bool
0x180093859  mov     rdx, r15; struct RealtimeProtection::_DlpQuarantineItem *
0x18009385c  call    ?QuarantineFile@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@_N@Z; RealtimeProtection::DlpQuarantineEngine::QuarantineFile(RealtimeProtection::_DlpQuarantineItem &,bool)
0x180093861  mov     bl, al
0x180093863  mov     [rsp+188h+var_78], al
0x18009386a  test    al, al
0x18009386c  jz      short loc_180093872
0x18009386e  mov     dl, 1
0x180093870  jmp     short loc_180093891
0x180093872  xor     r8d, r8d; bool
0x180093875  mov     rdx, r15; struct RealtimeProtection::_DlpQuarantineItem *
0x180093878  call    ?QuarantineFile@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@_N@Z; RealtimeProtection::DlpQuarantineEngine::QuarantineFile(RealtimeProtection::_DlpQuarantineItem &,bool)
0x18009387d  mov     bl, al
0x18009387f  mov     [rsp+188h+var_78], al
0x180093886  test    al, al
0x180093888  jz      loc_180093C81
0x18009388e  mov     dl, dil
0x180093891  mov     rax, [rsp+188h+var_140]
0x180093896  add     rax, 32h ; '2'
0x18009389a  mov     [rsp+188h+var_120], rax
0x18009389f  mov     cl, bl
0x1800938a1  mov     [rsp+188h+var_E0], rax
0x1800938a9  mov     [rax], dl
0x1800938ab  cmp     bl, 1
0x1800938ae  jnz     loc_180093C67
0x1800938b4  mov     rax, [rsp+188h+var_128]
0x1800938b9  cmp     [rax+219h], bl
0x1800938bf  jnz     loc_180093C67
0x1800938c5  mov     rbx, [rsp+188h+var_148]
0x1800938ca  add     rbx, 160h
0x1800938d1  mov     [rsp+188h+var_D8], rbx
0x1800938d9  mov     rdx, rbx; struct std::filesystem::path *
0x1800938dc  mov     rcx, r14; this
0x1800938df  call    ?rename@filesystem@std@@YAXAEBVpath@12@0@Z; std::filesystem::rename(std::filesystem::path const &,std::filesystem::path const &)
0x1800938e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800938eb  cmp     rcx, r12
0x1800938ee  jz      short loc_180093929
0x1800938f0  test    byte ptr [rcx+1Ch], 10h
0x1800938f4  jz      short loc_180093929
0x1800938f6  mov     rax, rbx
0x1800938f9  cmp     [rbx+18h], rsi
0x1800938fd  jbe     short loc_180093902
0x1800938ff  mov     rax, [rbx]
0x180093902  cmp     [r14+18h], rsi
0x180093906  jbe     short loc_18009390B
0x180093908  mov     r14, [r14]
0x18009390b  mov     edx, 51h ; 'Q'
0x180093910  mov     qword ptr [rsp+188h+var_168], rax
0x180093915  mov     r9, r14
0x180093918  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x18009391f  mov     rcx, [rcx+10h]
0x180093923  call    WPP_SF_SS
0x180093928  nop
0x180093929  mov     r14, [rsp+188h+var_120]
0x18009392e  jmp     short loc_180093976
0x180093930  xor     edi, edi
0x180093932  lea     esi, [rdi+7]
0x180093935  lea     r12, WPP_GLOBAL_Control
0x18009393c  mov     r13b, byte ptr [rsp+188h+var_110+8]
0x180093944  mov     rax, [rsp+188h+var_B8]
0x18009394c  mov     [rsp+188h+var_148], rax; void *
0x180093951  mov     r14, [rsp+188h+var_E0]
0x180093959  mov     rbx, [rsp+188h+var_D8]
0x180093961  mov     rax, [rsp+188h+var_D0]
0x180093969  mov     [rsp+188h+var_118], rax
0x18009396e  mov     r15, [rsp+188h+var_A8]
0x180093976  mov     rdx, [rsp+188h+var_128]
0x18009397b  add     rdx, 1F8h
0x180093982  lea     rcx, [rsp+188h+Buffer]
0x18009398a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009398f  nop
0x180093990  mov     r9b, [r14]
0x180093993  lea     r8, [rsp+188h+Buffer]
0x18009399b  mov     rdx, r15
0x18009399e  call    ?ParseReplacementText@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEBU_DlpQuarantineItem@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; RealtimeProtection::DlpQuarantineEngine::ParseReplacementText(RealtimeProtection::_DlpQuarantineItem const &,std::wstring &,bool)
0x1800939a3  test    eax, eax
0x1800939a5  jns     short loc_1800939F4
0x1800939a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800939ae  cmp     rcx, r12
0x1800939b1  jz      short loc_1800939D2
0x1800939b3  test    byte ptr [rcx+1Ch], 1
0x1800939b7  jz      short loc_1800939D2
0x1800939b9  mov     edx, 53h ; 'S'
0x1800939be  mov     r9d, eax
0x1800939c1  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1800939c8  mov     rcx, [rcx+10h]
0x1800939cc  call    WPP_SF_d
0x1800939d1  nop
0x1800939d2  lea     rcx, [rsp+188h+Buffer]; void *
0x1800939da  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800939df  nop
0x1800939e0  mov     al, [rsp+188h+var_78]
0x1800939e7  mov     rcx, [rsp+188h+var_148]
0x1800939ec  mov     [rcx+1], al
0x1800939ef  jmp     loc_180093D3A
0x1800939f4  mov     rdx, rbx
0x1800939f7  cmp     [rbx+18h], rsi
0x1800939fb  jbe     short loc_180093A00
0x1800939fd  mov     rdx, [rbx]; struct _iobuf **
0x180093a00  lea     r8, aW; "w+"
0x180093a07  lea     rcx, [rsp+188h+Stream]; this
0x180093a0f  call    ?UtilFileOpen@CommonUtil@@YAJPEAPEAU_iobuf@@PEB_W1@Z; CommonUtil::UtilFileOpen(_iobuf * *,wchar_t const *,wchar_t const *)
0x180093a14  test    eax, eax
0x180093a16  jns     short loc_180093A31
0x180093a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a1f  cmp     rcx, r12
0x180093a22  jz      short loc_1800939D2
0x180093a24  test    byte ptr [rcx+1Ch], 1
0x180093a28  jz      short loc_1800939D2
0x180093a2a  mov     edx, 54h ; 'T'
0x180093a2f  jmp     short loc_1800939BE
0x180093a31  lea     rcx, [rsp+188h+Buffer]
0x180093a39  cmp     [rsp+188h+var_38], rsi
0x180093a41  cmova   rcx, [rsp+188h+Buffer]; Buffer
0x180093a4a  mov     rdx, [rsp+188h+Stream]; Stream
0x180093a52  call    fputws
0x180093a57  mov     rcx, [rsp+188h+Stream]; Stream
0x180093a5f  call    fclose
0x180093a64  cmp     [r15+710h], dil
0x180093a6b  jz      loc_180093B15
0x180093a71  mov     [rsp+188h+var_138], rbx
0x180093a76  cmp     [rbx+18h], rsi
0x180093a7a  jbe     short loc_180093A84
0x180093a7c  mov     rax, [rbx]
0x180093a7f  mov     [rsp+188h+var_138], rax
0x180093a84  lea     r14, [r15+708h]
0x180093a8b  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180093a8f  jz      short loc_180093AA1
0x180093a91  mov     rcx, [r14]; hObject
0x180093a94  call    cs:__imp_CloseHandle
0x180093a9a  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180093aa1  mov     [rsp+188h+var_150], rdi; struct _SECURITY_ATTRIBUTES *
0x180093aa6  mov     qword ptr [rsp+188h+var_158], rdi; unsigned int
0x180093aab  mov     [rsp+188h+var_160], edi; unsigned int
0x180093aaf  mov     [rsp+188h+var_168], 3; unsigned int
0x180093ab7  mov     r9d, 1; unsigned int
0x180093abd  mov     r8d, 13019Fh; wchar_t *
0x180093ac3  mov     rdx, [rsp+188h+var_138]; void **
  ... truncated ...
```
