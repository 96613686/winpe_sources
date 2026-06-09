# ParseNIPath

- ea: `0x18001c3c4`
- end: `0x18001d271`
- name: `ParseNIPath`
- size: `3757`
- prototype: `__int64 __usercall@<rax>(SString *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dcb0`

## callees

- `0x180001f00`
- `0x180002024`
- `0x180002504`
- `0x180006a2c`
- `0x180008d84`
- `0x1800097e0`
- `0x180009f70`
- `0x18000a214`
- `0x18000af58`
- `0x18000b33c`
- `0x18000b610`
- `0x18000b8dc`
- `0x18000c8a8`
- `0x18001c3c4`
- `0x18002db88`
- `0x18002dc24`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x1800319a0`
- `0x180031a8c`
- `0x180031ae8`
- `0x180031c70`
- `0x180032ef4`
- `0x18003303c`
- `0x18003dc30`

## string_xrefs

- `0x18001c439`: `.ni.dll`
- `0x18001c4f1`: `Invalid path for /noroot uninstall.  The path must refer to a native image created by NGen\n`
- `0x18001c599`: `Invalid native image path: Can't find beginning of native image name\n`
- `0x18001c70f`: `Invalid native image path: Can't find beginning of GUID\n`
- `0x18001d219`: `Invalid native image path: Invalid GUID length\n`
- `0x18001cc24`: `Invalid native image path: Can't find end of NIC version\n`
- `0x18001cc84`: `Invalid native image path: Can't find beginning of NIC version\n`
- `0x18001cd9f`: `Invalid native image path: the image is not in local NIC\n`
- `0x18001cdb5`: `Version not specified for local nic uninstall\n`
- `0x18001ce11`: `Invalid native image path: the image is not in NIC\n`
- `0x18001cec8`: `Invalid native image path: attempting to uninstall 32-bit native image with 64-bit NGen\n`
- `0x18001cecf`: `Invalid native image path: invalid NIC directory name\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=62
__int64 __fastcall ParseNIPath(const unsigned __int16 **this, Root **a2, __int64 a3, char a4, unsigned __int16 *a5)
{
  unsigned int v7; // esi
  int v8; // ebx
  char v9; // di
  const wchar_t *v10; // rdx
  int v12; // eax
  __int32 v13; // ecx
  int v14; // eax
  unsigned __int8 v15; // cl
  char *v16; // r8
  char v17; // bl
  __int64 v18; // rdi
  const wchar_t *v19; // rdx
  __int16 v20; // ax
  __int16 v21; // ax
  __int16 v22; // ax
  __int16 v23; // ax
  __int16 v24; // ax
  bool v25; // bl
  const wchar_t *v26; // rdx
  bool v27; // di
  bool v28; // di
  int v29; // ebx
  unsigned int Count; // eax
  char v31; // r9
  unsigned __int16 *v32; // rbx
  Image *v33; // rcx
  struct RootList *RootList; // rax
  Root *NewRoot; // r15
  Configuration *Configuration; // rdi
  unsigned __int16 *v37; // rbx
  Image *v38; // rcx
  _QWORD *LogicalImage; // rdi
  unsigned __int16 *v40; // rax
  Image *v41; // rcx
  unsigned __int16 *v42; // rbx
  Image *v43; // rcx
  __m128i v44; // [rsp+20h] [rbp-E0h] BYREF
  void *lpMem; // [rsp+30h] [rbp-D0h]
  char v46; // [rsp+38h] [rbp-C8h]
  __m128i v47; // [rsp+40h] [rbp-C0h] BYREF
  void *v48; // [rsp+50h] [rbp-B0h]
  unsigned int v49; // [rsp+58h] [rbp-A8h]
  __m128i v50; // [rsp+60h] [rbp-A0h] BYREF
  void *v51; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v52; // [rsp+78h] [rbp-88h]
  Root **v53; // [rsp+80h] [rbp-80h]
  int v54; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+94h] [rbp-6Ch]
  void *v56; // [rsp+A0h] [rbp-60h]
  __int16 v57; // [rsp+A8h] [rbp-58h] BYREF
  int v58; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v59; // [rsp+2B4h] [rbp+1B4h]
  unsigned __int16 *v60; // [rsp+2C0h] [rbp+1C0h]
  __int16 v61; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v62; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v63; // [rsp+4D4h] [rbp+3D4h]
  unsigned __int16 *v64; // [rsp+4E0h] [rbp+3E0h]
  __int16 v65; // [rsp+4E8h] [rbp+3E8h] BYREF
  unsigned __int16 v66; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int16 v67; // [rsp+6F2h] [rbp+5F2h]
  __int16 v68; // [rsp+6F4h] [rbp+5F4h]
  __int16 v69; // [rsp+6F6h] [rbp+5F6h]
  __int16 v70; // [rsp+6F8h] [rbp+5F8h]
  __int16 v71; // [rsp+6FAh] [rbp+5FAh]
  __int16 v72; // [rsp+6FCh] [rbp+5FCh]
  __int16 v73; // [rsp+6FEh] [rbp+5FEh]
  __int16 v74; // [rsp+700h] [rbp+600h]
  __int16 v75; // [rsp+702h] [rbp+602h]
  __int16 v76; // [rsp+704h] [rbp+604h]
  __int16 v77; // [rsp+706h] [rbp+606h]
  __int16 v78; // [rsp+708h] [rbp+608h]
  __int16 v79; // [rsp+70Ah] [rbp+60Ah]
  __int16 v80; // [rsp+70Ch] [rbp+60Ch]
  __int16 v81; // [rsp+70Eh] [rbp+60Eh]
  __int16 v82; // [rsp+710h] [rbp+610h]
  __int16 v83; // [rsp+712h] [rbp+612h]
  __int16 v84; // [rsp+714h] [rbp+614h]
  __int16 v85; // [rsp+716h] [rbp+616h]
  __int16 v86; // [rsp+718h] [rbp+618h]
  __int16 v87; // [rsp+71Ah] [rbp+61Ah]
  __int16 v88; // [rsp+71Ch] [rbp+61Ch]
  __int16 v89; // [rsp+71Eh] [rbp+61Eh]
  __int16 v90; // [rsp+720h] [rbp+620h]
  __int16 v91; // [rsp+722h] [rbp+622h]
  __int16 v92; // [rsp+724h] [rbp+624h]
  __int16 v93; // [rsp+726h] [rbp+626h]
  __int16 v94; // [rsp+728h] [rbp+628h]
  __int16 v95; // [rsp+72Ah] [rbp+62Ah]
  __int16 v96; // [rsp+72Ch] [rbp+62Ch]
  __int16 v97; // [rsp+72Eh] [rbp+62Eh]
  __int16 v98; // [rsp+730h] [rbp+630h]
  __int16 v99; // [rsp+732h] [rbp+632h]
  __int16 v100; // [rsp+734h] [rbp+634h]
  __int16 v101; // [rsp+736h] [rbp+636h]
  __int16 v102; // [rsp+738h] [rbp+638h]
  int v103; // [rsp+73Ah] [rbp+63Ah]

  v46 = a4;
  v53 = a2;
  v52 = a5;
  v7 = 0;
  v49 = 0;
  *a2 = 0;
  v47.m128i_i64[0] = 0x200000002LL;
  v47.m128i_i32[2] = 16;
  v48 = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)&v47, L".ni.dll");
  v8 = 1;
  v49 = 1;
  if ( (unsigned int)SString::EndsWithCaseInsensitive((SString *)this, (const struct SString *)&v47)
    || (v44.m128i_i64[0] = 0x200000002LL,
        v44.m128i_i32[2] = 16,
        lpMem = (void *)&SString::s_EmptyBuffer,
        SString::Set((SString *)&v44, L".ni.exe"),
        v8 = 3,
        v49 = 3,
        v9 = 1,
        (unsigned int)SString::EndsWithCaseInsensitive((SString *)this, (const struct SString *)&v44)) )
  {
    v9 = 0;
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    v49 = v8;
    if ( (v44.m128i_i8[8] & 8) != 0 )
      operator delete(lpMem);
  }
  if ( (v8 & 1) != 0 )
  {
    v49 = v8 & 0xFFFFFFFE;
    if ( (v47.m128i_i8[8] & 8) != 0 )
      operator delete(v48);
  }
  if ( v9 )
  {
    v10 = L"Invalid path for /noroot uninstall.  The path must refer to a native image created by NGen\n";
LABEL_12:
    Logger::Log(a3, v10, 0);
    return 2147942560LL;
  }
  if ( (~(*((_DWORD *)this + 2) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)this) )
    SString::ConvertToUnicode((SString *)this);
  v12 = *((_DWORD *)this + 2);
  if ( (v12 & 2) != 0
    && ((v12 & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)this) )
  {
    SString::ConvertToUnicode((SString *)this);
  }
  v13 = ((_DWORD)this[1] & 1) == 0;
  v44.m128i_i64[0] = (__int64)this[2] + (((*(_DWORD *)this >> v13) - 1) << v13);
  v44.m128i_i32[2] = v13;
  if ( !(unsigned int)SString::FindBack((SString *)this, (struct SString::CIterator *)&v44, 0x5Cu) )
  {
    v10 = L"Invalid native image path: Can't find beginning of native image name\n";
    goto LABEL_12;
  }
  if ( (~(*((_DWORD *)this + 2) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)this) )
    SString::ConvertToUnicode((SString *)this);
  v14 = *((_DWORD *)this + 2);
  if ( (v14 & 2) != 0
    && ((v14 & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)this) )
  {
    SString::ConvertToUnicode((SString *)this);
  }
  v15 = ((_DWORD)this[1] & 1) == 0;
  v16 = (char *)this[2] + (((*(_DWORD *)this >> v15) - 1) << v15);
  v47.m128i_i32[2] = v15;
  v50.m128i_i64[1] = v47.m128i_i64[1];
  v51 = v48;
  v50.m128i_i64[0] = (__int64)&v16[-7 << v15];
  v47.m128i_i64[1] = v44.m128i_i64[1];
  v48 = lpMem;
  v17 = _mm_cvtsi128_si32(_mm_srli_si128(v44, 8));
  v18 = v44.m128i_i64[0];
  v47.m128i_i64[0] = v44.m128i_i64[0] + (1 << v17);
  v63 = 512;
  v64 = (unsigned __int16 *)&v65;
  v62 = 2;
  v65 = 0;
  SString::Set(
    (SString *)&v62,
    (const struct SString *)this,
    (const struct SString::CIterator *)&v47,
    (const struct SString::CIterator *)&v50);
  v47 = v44;
  v48 = lpMem;
  v44.m128i_i64[0] = (-1 << v17) + v18;
  if ( (unsigned int)SString::FindBack((SString *)this, (struct SString::CIterator *)&v44, 0x5Cu) )
  {
    if ( (unsigned int)((v47.m128i_i64[0] - v44.m128i_i64[0]) >> v47.m128i_i8[8]) - 33 > 0xC
      || (((unsigned __int8)((v47.m128i_i64[0] - v44.m128i_i64[0]) >> v47.m128i_i8[8]) - 1) & 3) != 0 )
    {
      v19 = L"Invalid native image path: Invalid GUID length\n";
      goto LABEL_104;
    }
    v66 = 123;
    if ( v44.m128i_i32[2] )
    {
      v67 = *(_WORD *)((7 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v68 = *(_WORD *)((8 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v69 = *(_WORD *)((5 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v70 = *(_WORD *)((6 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v71 = *(_WORD *)((3 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v72 = *(_WORD *)((4 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v73 = *(_WORD *)((1 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v20 = *(_WORD *)((2 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
    }
    else
    {
      v67 = *(char *)(v44.m128i_i64[0] + 7);
      v68 = *(char *)(v44.m128i_i64[0] + 8);
      v69 = *(char *)(v44.m128i_i64[0] + 5);
      v70 = *(char *)(v44.m128i_i64[0] + 6);
      v71 = *(char *)(v44.m128i_i64[0] + 3);
      v72 = *(char *)(v44.m128i_i64[0] + 4);
      v73 = *(char *)(v44.m128i_i64[0] + 1);
      v20 = *(char *)(v44.m128i_i64[0] + 2);
    }
    v74 = v20;
    v75 = 45;
    if ( v44.m128i_i32[2] )
    {
      v76 = *(_WORD *)((11 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v77 = *(_WORD *)((12 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v78 = *(_WORD *)((9 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v21 = *(_WORD *)((10 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
    }
    else
    {
      v76 = *(char *)(v44.m128i_i64[0] + 11);
      v77 = *(char *)(v44.m128i_i64[0] + 12);
      v78 = *(char *)(v44.m128i_i64[0] + 9);
      v21 = *(char *)(v44.m128i_i64[0] + 10);
    }
    v79 = v21;
    v80 = 45;
    if ( v44.m128i_i32[2] )
    {
      v81 = *(_WORD *)((15 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v82 = *(_WORD *)((16 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v83 = *(_WORD *)((13 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v22 = *(_WORD *)((14 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
    }
    else
    {
      v81 = *(char *)(v44.m128i_i64[0] + 15);
      v82 = *(char *)(v44.m128i_i64[0] + 16);
      v83 = *(char *)(v44.m128i_i64[0] + 13);
      v22 = *(char *)(v44.m128i_i64[0] + 14);
    }
    v84 = v22;
    v85 = 45;
    if ( v44.m128i_i32[2] )
    {
      v86 = *(_WORD *)((17 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v87 = *(_WORD *)((18 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v88 = *(_WORD *)((19 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v23 = *(_WORD *)((20 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
    }
    else
    {
      v86 = *(char *)(v44.m128i_i64[0] + 17);
      v87 = *(char *)(v44.m128i_i64[0] + 18);
      v88 = *(char *)(v44.m128i_i64[0] + 19);
      v23 = *(char *)(v44.m128i_i64[0] + 20);
    }
    v89 = v23;
    v90 = 45;
    if ( v44.m128i_i32[2] )
    {
      v91 = *(_WORD *)((21 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v92 = *(_WORD *)((22 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v93 = *(_WORD *)((23 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v94 = *(_WORD *)((24 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v95 = *(_WORD *)((25 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v96 = *(_WORD *)((26 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v97 = *(_WORD *)((27 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v98 = *(_WORD *)((28 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v99 = *(_WORD *)((29 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v100 = *(_WORD *)((30 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v101 = *(_WORD *)((31 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
      v24 = *(_WORD *)((32 << v44.m128i_i8[8]) + v44.m128i_i64[0]);
    }
    else
    {
      v91 = *(char *)(v44.m128i_i64[0] + 21);
      v92 = *(char *)(v44.m128i_i64[0] + 22);
      v93 = *(char *)(v44.m128i_i64[0] + 23);
      v94 = *(char *)(v44.m128i_i64[0] + 24);
      v95 = *(char *)(v44.m128i_i64[0] + 25);
      v96 = *(char *)(v44.m128i_i64[0] + 26);
      v97 = *(char *)(v44.m128i_i64[0] + 27);
      v98 = *(char *)(v44.m128i_i64[0] + 28);
      v99 = *(char *)(v44.m128i_i64[0] + 29);
      v100 = *(char *)(v44.m128i_i64[0] + 30);
      v101 = *(char *)(v44.m128i_i64[0] + 31);
      v24 = *(char *)(v44.m128i_i64[0] + 32);
    }
    v102 = v24;
    v103 = 125;
    v50.m128i_i64[1] = v44.m128i_i64[1];
    v50.m128i_i64[0] = v44.m128i_i64[0] + (-1 << v44.m128i_i8[8]);
    v47 = v50;
    v48 = lpMem;
    if ( !(unsigned int)SString::FindBack((SString *)this, (struct SString::CIterator *)&v47, 0x5Cu) )
    {
      v19 = L"Invalid native image path: Can't find end of NIC version\n";
      goto LABEL_104;
    }
    v50.m128i_i64[1] = v47.m128i_i64[1];
    v50.m128i_i64[0] = v47.m128i_i64[0] + (-1 << _mm_cvtsi128_si32(_mm_srli_si128(v47, 8)));
    v44 = v50;
    lpMem = v48;
    if ( !(unsigned int)SString::FindBack((SString *)this, (struct SString::CIterator *)&v44, 0x5Cu) )
    {
      v19 = L"Invalid native image path: Can't find beginning of NIC version\n";
      goto LABEL_104;
    }
    v50.m128i_i64[1] = v44.m128i_i64[1];
    v51 = lpMem;
    v50.m128i_i64[0] = v44.m128i_i64[0] + (1 << _mm_cvtsi128_si32(_mm_srli_si128(v44, 8)));
    v55 = 512;
    v56 = &v57;
    v54 = 2;
    v57 = 0;
    SString::Set(
      (SString *)&v54,
      (const struct SString *)this,
      (const struct SString::CIterator *)&v50,
      (const struct SString::CIterator *)&v47);
    v59 = 512;
    v60 = (unsigned __int16 *)&v61;
    v58 = 2;
    v61 = 0;
    v44.m128i_i64[0] = 0x200000002LL;
    v44.m128i_i32[2] = 16;
    lpMem = (void *)&SString::s_EmptyBuffer;
    if ( v46 )
    {
      SString::Set((SString *)&v44, L"NativeImages");
      v25 = (unsigned int)SString::EqualsCaseInsensitive((SString *)&v54, (const struct SString *)&v44) == 0;
      if ( (v44.m128i_i8[8] & 8) != 0 )
        operator delete(lpMem);
      if ( v25 )
      {
        v26 = L"Invalid native image path: the image is not in local NIC\n";
LABEL_73:
        Logger::Log(a3, v26, 0);
        v7 = -2147024736;
LABEL_99:
        if ( (v59 & 0x800000000LL) != 0 )
          operator delete(v60);
        if ( (v55 & 0x800000000LL) != 0 )
          operator delete(v56);
        goto LABEL_105;
      }
      if ( !v52 )
      {
        v26 = L"Version not specified for local nic uninstall\n";
        goto LABEL_73;
      }
      SString::Set((SString *)&v58, v52);
    }
    else
    {
      SString::Set((SString *)&v44, L"NativeImages_v");
      v27 = (unsigned int)SString::BeginsWithCaseInsensitive((SString *)&v54, (const struct SString *)&v44) == 0;
      if ( (v44.m128i_i8[8] & 8) != 0 )
        operator delete(lpMem);
      if ( v27 )
      {
        v26 = L"Invalid native image path: the image is not in NIC\n";
        goto LABEL_73;
      }
      v44.m128i_i64[0] = 0x200000002LL;
      v44.m128i_i32[2] = 16;
      lpMem = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)&v44, L"_64");
      v28 = (unsigned int)SString::EndsWith((SString *)&v54, (const struct SString *)&v44) == 0;
      if ( (v44.m128i_i8[8] & 8) != 0 )
        operator delete(lpMem);
      if ( v28 )
      {
        v44.m128i_i64[0] = 0x200000002LL;
        v44.m128i_i32[2] = 16;
        lpMem = (void *)&SString::s_EmptyBuffer;
        SString::Set((SString *)&v44, L"_32");
        v29 = SString::EndsWith((SString *)&v54, (const struct SString *)&v44);
        if ( (v44.m128i_i8[8] & 8) != 0 )
          operator delete(lpMem);
        v26 = L"Invalid native image path: attempting to uninstall 32-bit native image with 64-bit NGen\n";
        if ( !v29 )
          v26 = L"Invalid native image path: invalid NIC directory name\n";
        goto LABEL_73;
      }
      if ( (~(HIDWORD(v55) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v54) )
        SString::ConvertToUnicode((SString *)&v54);
      if ( (v55 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v54, (unsigned int)v55, 1);
      Count = SString::GetCount((SString *)&v54);
      v31 = BYTE4(v55);
      v50.m128i_i64[0] = (__int64)v56 + (int)(Count << ((v55 & 0x100000000LL) == 0));
      v50.m128i_i32[2] = (v55 & 0x100000000LL) == 0;
      v44.m128i_i64[1] = v50.m128i_i64[1];
      lpMem = v51;
      v44.m128i_i64[0] = v50.m128i_i64[0] + (-3 << ((v55 & 0x100000000LL) == 0));
      if ( (~(HIDWORD(v55) >> 1) & 1) == 0 )
      {
        if ( !(unsigned int)SString::ScanASCII((SString *)&v54) )
          SString::ConvertToUnicode((SString *)&v54);
        v31 = BYTE4(v55);
      }
      if ( (v31 & 0x10) != 0 )
      {
        SBuffer::ReallocateBuffer(&v54, (unsigned int)v55, 1);
        v31 = BYTE4(v55);
      }
      v50.m128i_i64[0] = (__int64)v56;
      v50.m128i_i32[2] = (v31 & 1) == 0;
      v47.m128i_i64[1] = v50.m128i_i64[1];
      v48 = v51;
      v47.m128i_i64[0] = (__int64)v56 + (13 << ((v31 & 1) == 0));
      SString::Set(
        (SString *)&v58,
        (const struct SString *)&v54,
        (const struct SString::CIterator *)&v47,
        (const struct SString::CIterator *)&v44);
    }
    v32 = (unsigned __int16 *)operator new(0x18u);
    v52 = v32;
    if ( v32 )
    {
      SString::ConvertToUnicode((SString *)this);
      v33 = Image::Image((Image *)v32, this[2], 0);
    }
    else
    {
      v33 = 0;
    }
    v47.m128i_i64[0] = (__int64)v33;
    v47.m128i_i32[2] = v33 != 0;
    RootList = GetRootList(0);
    NewRoot = (Root *)RootList::CreateNewRoot((__int64)RootList, (__int64)&v47);
    Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>(v47.m128i_i64);
    Root::SetStatus(NewRoot, 3);
    Configuration = Root::CreateConfiguration(NewRoot);
    SString::ConvertToUnicode((SString *)&v58);
    Configuration::SetRuntimeVersion(Configuration, v60);
    Node::SetStatus(Configuration, 0);
    v37 = (unsigned __int16 *)operator new(0x18u);
    v52 = v37;
    if ( v37 )
    {
      SString::ConvertToUnicode((SString *)this);
      v38 = Image::Image((Image *)v37, this[2], 0);
    }
    else
    {
      v38 = 0;
    }
    v47.m128i_i64[0] = (__int64)v38;
    v47.m128i_i32[2] = v38 != 0;
    LogicalImage = Configuration::CreateLogicalImage(Configuration, v47.m128i_i64);
    Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>(v47.m128i_i64);
    v40 = (unsigned __int16 *)operator new(0x18u);
    v52 = v40;
    if ( v40 )
      v41 = Image::Image((Image *)v40, &v66, 0);
    else
      v41 = 0;
    v44.m128i_i64[0] = (__int64)v41;
    v44.m128i_i32[2] = v41 != 0;
    LogicalImage::SetNativeImage(LogicalImage, &v44);
    Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>(v44.m128i_i64);
    v42 = (unsigned __int16 *)operator new(0x18u);
    v52 = v42;
    if ( v42 )
    {
      SString::ConvertToUnicode((SString *)&v62);
      v43 = Image::Image((Image *)v42, v64, 0);
    }
    else
    {
      v43 = 0;
    }
    v44.m128i_i64[0] = (__int64)v43;
    v44.m128i_i32[2] = v43 != 0;
    LogicalImage::SetDisplayName(LogicalImage, &v44);
    Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>(v44.m128i_i64);
    Node::SetStatus(LogicalImage, 5);
    *v53 = NewRoot;
    goto LABEL_99;
  }
  v19 = L"Invalid native image path: Can't find beginning of GUID\n";
LABEL_104:
  Logger::Log(a3, v19, 0);
  v7 = -2147024736;
LABEL_105:
  if ( (v63 & 0x800000000LL) != 0 )
    operator delete(v64);
  return v7;
}

```

## disassembly

```asm
0x18001c3c4  mov     [rsp-8+arg_18], rbx
0x18001c3c9  push    rbp
0x18001c3ca  push    rsi
0x18001c3cb  push    rdi
0x18001c3cc  push    r12
0x18001c3ce  push    r13
0x18001c3d0  push    r14
0x18001c3d2  push    r15
0x18001c3d4  lea     rbp, [rsp-650h]
0x18001c3dc  sub     rsp, 750h
0x18001c3e3  mov     rax, cs:__security_cookie
0x18001c3ea  xor     rax, rsp
0x18001c3ed  mov     [rbp+680h+var_40], rax
0x18001c3f4  mov     [rsp+780h+var_748], r9b
0x18001c3f9  mov     r12, r8
0x18001c3fc  mov     [rbp+680h+var_700], rdx
0x18001c400  mov     r14, rcx
0x18001c403  mov     rax, [rbp+680h+arg_20]
0x18001c40a  mov     [rsp+780h+var_708], rax
0x18001c40f  xor     esi, esi
0x18001c411  mov     [rsp+780h+var_728], esi
0x18001c415  mov     [rdx], rsi
0x18001c418  lea     r15d, [rsi+2]
0x18001c41c  mov     dword ptr [rsp+780h+var_740], r15d
0x18001c421  mov     dword ptr [rsp+780h+var_740+4], r15d
0x18001c426  lea     edi, [rsi+10h]
0x18001c429  mov     dword ptr [rsp+780h+var_740+8], edi
0x18001c42d  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18001c434  mov     [rsp+780h+var_730], rax
0x18001c439  lea     rdx, aNiDll; ".ni.dll"
0x18001c440  lea     rcx, [rsp+780h+var_740]; this
0x18001c445  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001c44a  nop
0x18001c44b  lea     r13d, [rsi+1]
0x18001c44f  mov     ebx, r13d
0x18001c452  mov     [rsp+780h+var_728], ebx
0x18001c456  lea     rdx, [rsp+780h+var_740]; struct SString *
0x18001c45b  mov     rcx, r14; this
0x18001c45e  call    ?EndsWithCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::EndsWithCaseInsensitive(SString const &)
0x18001c463  test    eax, eax
0x18001c465  jnz     short loc_18001C4AE
0x18001c467  mov     dword ptr [rsp+780h+var_760], r15d
0x18001c46c  mov     dword ptr [rsp+780h+var_760+4], r15d
0x18001c471  mov     dword ptr [rsp+780h+var_760+8], edi
0x18001c475  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18001c47c  mov     [rsp+780h+lpMem], rax
0x18001c481  lea     rdx, aNiExe; ".ni.exe"
0x18001c488  lea     rcx, [rsp+780h+var_760]; this
0x18001c48d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001c492  nop
0x18001c493  lea     ebx, [rsi+3]
0x18001c496  mov     [rsp+780h+var_728], ebx
0x18001c49a  lea     rdx, [rsp+780h+var_760]; struct SString *
0x18001c49f  mov     rcx, r14; this
0x18001c4a2  call    ?EndsWithCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::EndsWithCaseInsensitive(SString const &)
0x18001c4a7  test    eax, eax
0x18001c4a9  mov     dil, r13b
0x18001c4ac  jz      short loc_18001C4B1
0x18001c4ae  mov     dil, sil
0x18001c4b1  test    r15b, bl
0x18001c4b4  jz      short loc_18001C4CF
0x18001c4b6  and     ebx, 0FFFFFFFDh
0x18001c4b9  mov     [rsp+780h+var_728], ebx
0x18001c4bd  test    byte ptr [rsp+780h+var_760+8], 8
0x18001c4c2  jz      short loc_18001C4CF
0x18001c4c4  mov     rcx, [rsp+780h+lpMem]; lpMem
0x18001c4c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c4ce  nop
0x18001c4cf  test    r13b, bl
0x18001c4d2  jz      short loc_18001C4EC
0x18001c4d4  and     ebx, 0FFFFFFFEh
0x18001c4d7  mov     [rsp+780h+var_728], ebx
0x18001c4db  test    byte ptr [rsp+780h+var_740+8], 8
0x18001c4e0  jz      short loc_18001C4EC
0x18001c4e2  mov     rcx, [rsp+780h+var_730]; lpMem
0x18001c4e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c4ec  test    dil, dil
0x18001c4ef  jz      short loc_18001C50D
0x18001c4f1  lea     rdx, aInvalidPathFor; "Invalid path for /noroot uninstall.  Th"...
0x18001c4f8  xor     r8d, r8d
0x18001c4fb  mov     rcx, r12
0x18001c4fe  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x18001c503  mov     eax, 800700A0h
0x18001c508  jmp     loc_18001D247
0x18001c50d  mov     eax, [r14+8]
0x18001c511  shr     eax, 1
0x18001c513  not     eax
0x18001c515  test    r13b, al
0x18001c518  jnz     short loc_18001C52E
0x18001c51a  mov     rcx, r14; this
0x18001c51d  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18001c522  test    eax, eax
0x18001c524  jnz     short loc_18001C52E
0x18001c526  mov     rcx, r14; this
0x18001c529  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001c52e  mov     eax, [r14+8]
0x18001c532  mov     r15d, 7
0x18001c538  test    al, 2
0x18001c53a  jz      short loc_18001C560
0x18001c53c  and     eax, r15d
0x18001c53f  cmp     al, r15b
0x18001c542  jnz     short loc_18001C54C
0x18001c544  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x18001c54a  jz      short loc_18001C560
0x18001c54c  mov     rcx, r14; this
0x18001c54f  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18001c554  test    eax, eax
0x18001c556  jnz     short loc_18001C560
0x18001c558  mov     rcx, r14; this
0x18001c55b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001c560  mov     ecx, [r14+8]
0x18001c564  not     ecx
0x18001c566  and     ecx, r13d
0x18001c569  mov     eax, [r14]
0x18001c56c  shr     eax, cl
0x18001c56e  sub     eax, r13d
0x18001c571  shl     eax, cl
0x18001c573  cdqe
0x18001c575  add     rax, [r14+10h]
0x18001c579  mov     qword ptr [rsp+780h+var_760], rax
0x18001c57e  mov     dword ptr [rsp+780h+var_760+8], ecx
0x18001c582  mov     r8d, 5Ch ; '\'; unsigned __int16
0x18001c588  lea     rdx, [rsp+780h+var_760]; struct SString::CIterator *
0x18001c58d  mov     rcx, r14; this
0x18001c590  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@G@Z; SString::FindBack(SString::CIterator &,ushort)
0x18001c595  test    eax, eax
0x18001c597  jnz     short loc_18001C5A5
0x18001c599  lea     rdx, aInvalidNativeI; "Invalid native image path: Can't find b"...
0x18001c5a0  jmp     loc_18001C4F8
0x18001c5a5  mov     eax, [r14+8]
0x18001c5a9  shr     eax, 1
0x18001c5ab  not     eax
0x18001c5ad  test    r13b, al
0x18001c5b0  jnz     short loc_18001C5C6
0x18001c5b2  mov     rcx, r14; this
0x18001c5b5  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18001c5ba  test    eax, eax
0x18001c5bc  jnz     short loc_18001C5C6
0x18001c5be  mov     rcx, r14; this
0x18001c5c1  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001c5c6  mov     eax, [r14+8]
0x18001c5ca  test    al, 2
0x18001c5cc  jz      short loc_18001C5F2
0x18001c5ce  and     eax, r15d
0x18001c5d1  cmp     al, r15b
0x18001c5d4  jnz     short loc_18001C5DE
0x18001c5d6  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x18001c5dc  jz      short loc_18001C5F2
0x18001c5de  mov     rcx, r14; this
0x18001c5e1  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18001c5e6  test    eax, eax
0x18001c5e8  jnz     short loc_18001C5F2
0x18001c5ea  mov     rcx, r14; this
0x18001c5ed  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001c5f2  mov     ecx, [r14+8]
0x18001c5f6  not     ecx
0x18001c5f8  and     ecx, r13d
0x18001c5fb  mov     eax, [r14]
0x18001c5fe  shr     eax, cl
0x18001c600  sub     eax, r13d
0x18001c603  shl     eax, cl
0x18001c605  movsxd  r8, eax
0x18001c608  add     r8, [r14+10h]
0x18001c60c  mov     qword ptr [rsp+780h+var_740], r8
0x18001c611  mov     dword ptr [rsp+780h+var_740+8], ecx
0x18001c615  movups  xmm0, [rsp+780h+var_740]
0x18001c61a  movups  [rsp+780h+var_720], xmm0
0x18001c61f  movsd   xmm1, [rsp+780h+var_730]
0x18001c625  movsd   [rsp+780h+var_710], xmm1
0x18001c62b  mov     eax, 0FFFFFFF9h
0x18001c630  shl     eax, cl
0x18001c632  movsxd  rcx, eax
0x18001c635  add     rcx, r8
0x18001c638  mov     qword ptr [rsp+780h+var_720], rcx
0x18001c63d  movups  xmm1, [rsp+780h+var_760]
0x18001c642  movups  [rsp+780h+var_740], xmm1
0x18001c647  movsd   xmm0, [rsp+780h+lpMem]
0x18001c64d  movsd   [rsp+780h+var_730], xmm0
0x18001c653  movdqa  xmm0, xmm1
0x18001c657  psrldq  xmm0, 8
0x18001c65c  movd    ebx, xmm0
0x18001c660  mov     ecx, ebx
0x18001c662  mov     eax, r13d
0x18001c665  shl     eax, cl
0x18001c667  movsxd  rcx, eax
0x18001c66a  movq    rdi, xmm1
0x18001c66f  add     rcx, rdi
0x18001c672  mov     qword ptr [rsp+780h+var_740], rcx
0x18001c677  mov     [rbp+680h+var_2B0], rsi
0x18001c67e  mov     [rbp+680h+var_2B0+4], 200h
0x18001c689  mov     [rbp+680h+var_2A0], rsi
0x18001c690  lea     rax, [rbp+680h+var_298]
0x18001c697  mov     [rbp+680h+var_2A0], rax
0x18001c69e  mov     dword ptr [rbp+680h+var_2B0], 2
0x18001c6a8  mov     rax, [rbp+680h+var_2A0]
0x18001c6af  mov     [rax], si
0x18001c6b2  lea     r9, [rsp+780h+var_720]; struct SString::CIterator *
0x18001c6b7  lea     r8, [rsp+780h+var_740]; struct SString::CIterator *
0x18001c6bc  mov     rdx, r14; struct SString *
0x18001c6bf  lea     rcx, [rbp+680h+var_2B0]; this
0x18001c6c6  call    ?Set@SString@@QEAAXAEBV1@AEBVCIterator@1@1@Z; SString::Set(SString const &,SString::CIterator const &,SString::CIterator const &)
0x18001c6cb  nop
0x18001c6cc  movups  xmm0, [rsp+780h+var_760]
0x18001c6d1  movups  [rsp+780h+var_740], xmm0
0x18001c6d6  movsd   xmm0, [rsp+780h+lpMem]
0x18001c6dc  movsd   [rsp+780h+var_730], xmm0
0x18001c6e2  mov     ecx, ebx
0x18001c6e4  or      r13d, 0FFFFFFFFh
0x18001c6e8  mov     eax, r13d
0x18001c6eb  shl     eax, cl
0x18001c6ed  cdqe
0x18001c6ef  add     rdi, rax
0x18001c6f2  mov     qword ptr [rsp+780h+var_760], rdi
0x18001c6f7  lea     edi, [r13+5Dh]
0x18001c6fb  mov     r8d, edi; unsigned __int16
0x18001c6fe  lea     rdx, [rsp+780h+var_760]; struct SString::CIterator *
0x18001c703  mov     rcx, r14; this
0x18001c706  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@G@Z; SString::FindBack(SString::CIterator &,ushort)
0x18001c70b  test    eax, eax
0x18001c70d  jnz     short loc_18001C71B
0x18001c70f  lea     rdx, aInvalidNativeI_1; "Invalid native image path: Can't find b"...
0x18001c716  jmp     loc_18001D220
0x18001c71b  mov     r8, qword ptr [rsp+780h+var_740]
0x18001c720  mov     rdx, qword ptr [rsp+780h+var_760]
0x18001c725  sub     r8, rdx
0x18001c728  mov     ecx, dword ptr [rsp+780h+var_740+8]
0x18001c72c  sar     r8, cl
0x18001c72f  dec     r8d
0x18001c732  lea     eax, [r8-20h]
0x18001c736  mov     r9d, 0Ch
0x18001c73c  cmp     eax, r9d
0x18001c73f  ja      loc_18001D219
0x18001c745  test    r8b, 3
0x18001c749  jnz     loc_18001D219
0x18001c74f  lea     eax, [r9+6Fh]
0x18001c753  mov     [rbp+680h+var_90], ax
0x18001c75a  mov     r8d, dword ptr [rsp+780h+var_760+8]
0x18001c75f  test    r8d, r8d
0x18001c762  jnz     short loc_18001C7BE
0x18001c764  movsx   eax, byte ptr [rdx+7]
0x18001c768  mov     [rbp+680h+var_8E], ax
0x18001c76f  movsx   eax, byte ptr [rdx+8]
0x18001c773  mov     [rbp+680h+var_8C], ax
0x18001c77a  movsx   eax, byte ptr [rdx+5]
0x18001c77e  mov     [rbp+680h+var_8A], ax
0x18001c785  movsx   eax, byte ptr [rdx+6]
0x18001c789  mov     [rbp+680h+var_88], ax
0x18001c790  movsx   eax, byte ptr [rdx+3]
0x18001c794  mov     [rbp+680h+var_86], ax
0x18001c79b  movsx   eax, byte ptr [rdx+4]
0x18001c79f  mov     [rbp+680h+var_84], ax
0x18001c7a6  movsx   eax, byte ptr [rdx+1]
0x18001c7aa  mov     [rbp+680h+var_82], ax
0x18001c7b1  movsx   eax, byte ptr [rdx+2]
0x18001c7b5  lea     r15d, [r9-0Ah]
0x18001c7b9  jmp     loc_18001C870
0x18001c7be  mov     ecx, r8d
0x18001c7c1  shl     r15d, cl
0x18001c7c4  movsxd  rax, r15d
0x18001c7c7  movzx   ecx, word ptr [rax+rdx]
0x18001c7cb  mov     [rbp+680h+var_8E], cx
0x18001c7d2  mov     ecx, r8d
0x18001c7d5  mov     eax, 8
0x18001c7da  shl     eax, cl
0x18001c7dc  cdqe
0x18001c7de  movzx   ecx, word ptr [rax+rdx]
0x18001c7e2  mov     [rbp+680h+var_8C], cx
0x18001c7e9  mov     ecx, r8d
0x18001c7ec  mov     eax, 5
0x18001c7f1  shl     eax, cl
0x18001c7f3  cdqe
0x18001c7f5  movzx   ecx, word ptr [rax+rdx]
0x18001c7f9  mov     [rbp+680h+var_8A], cx
0x18001c800  mov     ecx, r8d
0x18001c803  mov     eax, 6
0x18001c808  shl     eax, cl
0x18001c80a  cdqe
0x18001c80c  movzx   ecx, word ptr [rax+rdx]
0x18001c810  mov     [rbp+680h+var_88], cx
0x18001c817  mov     ecx, r8d
0x18001c81a  mov     eax, 3
0x18001c81f  shl     eax, cl
0x18001c821  cdqe
0x18001c823  movzx   ecx, word ptr [rax+rdx]
0x18001c827  mov     [rbp+680h+var_86], cx
0x18001c82e  mov     ecx, r8d
0x18001c831  mov     eax, 4
0x18001c836  shl     eax, cl
0x18001c838  cdqe
0x18001c83a  movzx   ecx, word ptr [rax+rdx]
0x18001c83e  mov     [rbp+680h+var_84], cx
0x18001c845  mov     ecx, r8d
0x18001c848  mov     eax, 1
0x18001c84d  shl     eax, cl
0x18001c84f  cdqe
0x18001c851  movzx   ecx, word ptr [rax+rdx]
0x18001c855  mov     [rbp+680h+var_82], cx
0x18001c85c  mov     ecx, r8d
0x18001c85f  mov     r15d, 2
0x18001c865  mov     eax, r15d
  ... truncated ...
```
