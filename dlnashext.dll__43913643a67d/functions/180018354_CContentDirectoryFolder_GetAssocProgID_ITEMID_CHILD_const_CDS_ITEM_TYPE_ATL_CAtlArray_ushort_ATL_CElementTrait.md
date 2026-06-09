# CContentDirectoryFolder::_GetAssocProgID(_ITEMID_CHILD const *,CDS_ITEM_TYPE,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> &,int)

- ea: `0x180018354`
- end: `0x1800185ee`
- name: `?_GetAssocProgID@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4CDS_ITEM_TYPE@@AEAV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@H@Z`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fda8`

## callees

- `0x1800082b4`
- `0x18000ab48`
- `0x18000bc18`
- `0x18000bca4`
- `0x180011930`
- `0x1800125c4`
- `0x18001562c`
- `0x180017650`
- `0x180018354`
- `0x1800197c0`
- `0x18002c988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185b3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800183b4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800183b4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18001849c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x18001849c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018452`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018590`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018452`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180018590`

## string_xrefs

- `0x1800183ea`: `ContentDirectory.`
- `0x1800184ff`: `Directory.Audio`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentDirectoryFolder::_GetAssocProgID(
        CContentDirectoryFolder *a1,
        const struct _ITEMID_CHILD *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v5; // r12
  HRESULT String; // esi
  const unsigned __int16 *v7; // r14
  const unsigned __int16 *v8; // rbx
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // r8
  int MediaTypeFromClass; // eax
  WCHAR *v14; // rbx
  LPWSTR ppwsz; // [rsp+20h] [rbp-258h] BYREF
  int v17; // [rsp+28h] [rbp-250h]
  PCWSTR pszFirst; // [rsp+30h] [rbp-248h] BYREF
  const unsigned __int16 *v19; // [rsp+38h] [rbp-240h]
  PCWSTR v20; // [rsp+40h] [rbp-238h]
  __int64 v21; // [rsp+48h] [rbp-230h]
  WCHAR psz[256]; // [rsp+50h] [rbp-228h] BYREF

  v5 = a4;
  v21 = a4;
  pszFirst = 0;
  String = CContentDirectoryFolder::_GetString(a1, a2, &PKEY_ItemClass, (unsigned __int16 **)&pszFirst);
  if ( String >= 0 )
  {
    String = -2147467259;
    if ( StrStrIW(pszFirst, L"object.") )
    {
      v7 = pszFirst + 7;
      v20 = pszFirst + 7;
      v8 = 0;
      v19 = 0;
      do
      {
        memset_0(psz, 0, sizeof(psz));
        String = StringCchCopyW(psz, 0x100u, L"ContentDirectory.");
        if ( String >= 0 )
        {
          wcslen2(v8);
          v9 = wcslen2(v7);
          String = StringCchCatNW(psz, 0x100u, v7, v9 - v10);
          if ( String >= 0 )
          {
            ppwsz = 0;
            String = SHStrDupW(psz, &ppwsz);
            if ( String >= 0 )
            {
              try
              {
                ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::Add(v5, &ppwsz);
              }
              catch ( std::bad_alloc )
              {
                v17 = -2147024882;
                goto LABEL_8;
              }
              catch ( ... )
              {
                v17 = -2147418113;
LABEL_8:
                CoTaskMemFree(ppwsz);
                String = v17;
                v7 = v20;
                v8 = v19;
                v5 = v21;
              }
              v8 = StrRChrW(pszFirst, v8, 0x2Eu);
              v19 = v8;
              wcslen2(v8);
              v11 = wcslen2(v7);
              if ( v11 < v12 )
                break;
            }
          }
        }
      }
      while ( v8 );
      if ( String >= 0 )
      {
        ppwsz = 0;
        MediaTypeFromClass = CCDSResultsParser::GetMediaTypeFromClass(pszFirst);
        switch ( MediaTypeFromClass )
        {
          case 2:
            if ( a5 )
            {
              v14 = L"audio";
              goto LABEL_22;
            }
            break;
          case 4:
            if ( a5 )
            {
              v14 = (WCHAR *)L"video";
              goto LABEL_22;
            }
            break;
          case 8:
            if ( a5 )
            {
              v14 = L"image";
LABEL_22:
              ppwsz = v14;
              goto LABEL_26;
            }
            break;
          case 32:
          case 64:
            v14 = L"Directory.Audio";
            ppwsz = L"Directory.Audio";
LABEL_27:
            memset_0(psz, 0, sizeof(psz));
            String = StringCchPrintfW(psz, 0x100u, L"SystemFileAssociations\\%s", v14);
            if ( String >= 0 )
            {
              String = SHStrDupW(psz, &ppwsz);
              if ( String >= 0 )
              {
                try
                {
                  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::Add(v5, &ppwsz);
                }
                catch ( std::bad_alloc )
                {
                  v17 = -2147024882;
                  goto LABEL_30;
                }
                catch ( ... )
                {
                  v17 = -2147418113;
LABEL_30:
                  CoTaskMemFree(ppwsz);
                  String = v17;
                }
              }
            }
            goto LABEL_31;
          default:
            break;
        }
        v14 = ppwsz;
LABEL_26:
        if ( !v14 )
          goto LABEL_31;
        goto LABEL_27;
      }
    }
  }
LABEL_31:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pszFirst);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180018354  mov     [rsp+arg_10], rbx
0x180018359  push    rsi
0x18001835a  push    r12
0x18001835c  push    r14
0x18001835e  sub     rsp, 260h
0x180018365  mov     rax, cs:__security_cookie
0x18001836c  xor     rax, rsp
0x18001836f  mov     [rsp+278h+var_28], rax
0x180018377  mov     r12, r9
0x18001837a  mov     [rsp+278h+var_230], r9
0x18001837f  mov     [rsp+278h+pszFirst], 0
0x180018388  lea     r9, [rsp+278h+pszFirst]; unsigned __int16 **
0x18001838d  lea     r8, PKEY_ItemClass; struct _tagpropertykey *
0x180018394  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180018399  mov     esi, eax
0x18001839b  test    eax, eax
0x18001839d  js      loc_1800185BD
0x1800183a3  mov     esi, 80004005h
0x1800183a8  lea     rdx, pszSrch; "object."
0x1800183af  mov     rcx, [rsp+278h+pszFirst]; pszFirst
0x1800183b4  call    cs:__imp_StrStrIW
0x1800183ba  test    rax, rax
0x1800183bd  jz      loc_1800185BD
0x1800183c3  mov     r14, [rsp+278h+pszFirst]
0x1800183c8  add     r14, 0Eh
0x1800183cc  mov     [rsp+278h+var_238], r14
0x1800183d1  xor     ebx, ebx
0x1800183d3  mov     [rsp+278h+var_240], rbx
0x1800183d8  xor     edx, edx; Val
0x1800183da  mov     r8d, 200h; Size
0x1800183e0  lea     rcx, [rsp+278h+psz]; void *
0x1800183e5  call    memset_0
0x1800183ea  lea     r8, aContentdirecto; "ContentDirectory."
0x1800183f1  mov     edx, 100h; unsigned __int64
0x1800183f6  lea     rcx, [rsp+278h+psz]; unsigned __int16 *
0x1800183fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018400  mov     esi, eax
0x180018402  test    eax, eax
0x180018404  js      loc_1800184C2
0x18001840a  mov     rcx, rbx; unsigned __int16 *
0x18001840d  call    ?wcslen2@@YA_KPEBG@Z; wcslen2(ushort const *)
0x180018412  mov     r8, rax
0x180018415  mov     rcx, r14; unsigned __int16 *
0x180018418  call    ?wcslen2@@YA_KPEBG@Z; wcslen2(ushort const *)
0x18001841d  sub     rax, r8
0x180018420  mov     r9, rax; unsigned __int64
0x180018423  mov     r8, r14; unsigned __int16 *
0x180018426  mov     edx, 100h; unsigned __int64
0x18001842b  lea     rcx, [rsp+278h+psz]; unsigned __int16 *
0x180018430  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180018435  mov     esi, eax
0x180018437  test    eax, eax
0x180018439  js      loc_1800184C2
0x18001843f  mov     [rsp+278h+ppwsz], 0
0x180018448  lea     rdx, [rsp+278h+ppwsz]; ppwsz
0x18001844d  lea     rcx, [rsp+278h+psz]; psz
0x180018452  call    cs:__imp_SHStrDupW
0x180018458  mov     esi, eax
0x18001845a  test    eax, eax
0x18001845c  js      short loc_1800184C2
0x18001845e  lea     rdx, [rsp+278h+ppwsz]
0x180018463  mov     rcx, r12
0x180018466  call    ?Add@?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA_KAEBQEAG@Z; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::Add(ushort * const &)
0x18001846b  nop
0x18001846c  jmp     short loc_18001848E
0x18001846e  jmp     short $+2
0x180018470  mov     rcx, [rsp+278h+ppwsz]; pv
0x180018475  call    cs:__imp_CoTaskMemFree
0x18001847b  mov     esi, [rsp+278h+var_250]
0x18001847f  mov     r14, [rsp+278h+var_238]
0x180018484  mov     rbx, [rsp+278h+var_240]
0x180018489  mov     r12, [rsp+278h+var_230]
0x18001848e  mov     r8d, 2Eh ; '.'; wMatch
0x180018494  mov     rdx, rbx; pszEnd
0x180018497  mov     rcx, [rsp+278h+pszFirst]; pszStart
0x18001849c  call    cs:__imp_StrRChrW
0x1800184a2  mov     rbx, rax
0x1800184a5  mov     [rsp+278h+var_240], rax
0x1800184aa  mov     rcx, rax; unsigned __int16 *
0x1800184ad  call    ?wcslen2@@YA_KPEBG@Z; wcslen2(ushort const *)
0x1800184b2  mov     r8, rax
0x1800184b5  mov     rcx, r14; unsigned __int16 *
0x1800184b8  call    ?wcslen2@@YA_KPEBG@Z; wcslen2(ushort const *)
0x1800184bd  cmp     rax, r8
0x1800184c0  jb      short loc_1800184CB
0x1800184c2  test    rbx, rbx
0x1800184c5  jnz     loc_1800183D8
0x1800184cb  test    esi, esi
0x1800184cd  js      loc_1800185BD
0x1800184d3  mov     [rsp+278h+ppwsz], 0
0x1800184dc  mov     rcx, [rsp+278h+pszFirst]
0x1800184e1  call    ?GetMediaTypeFromClass@CCDSResultsParser@@SA?AW4_CDS_MEDIA_TYPE@@PEBG@Z; CCDSResultsParser::GetMediaTypeFromClass(ushort const *)
0x1800184e6  cmp     eax, 2
0x1800184e9  jz      short loc_180018538
0x1800184eb  cmp     eax, 4
0x1800184ee  jz      short loc_180018520
0x1800184f0  cmp     eax, 8
0x1800184f3  jz      short loc_18001850D
0x1800184f5  cmp     eax, 20h ; ' '
0x1800184f8  jz      short loc_1800184FF
0x1800184fa  cmp     eax, 40h ; '@'
0x1800184fd  jnz     short loc_18001854B
0x1800184ff  lea     rbx, aDirectoryAudio; "Directory.Audio"
0x180018506  mov     [rsp+278h+ppwsz], rbx
0x18001850b  jmp     short loc_180018555
0x18001850d  cmp     [rsp+278h+arg_20], 0
0x180018515  jz      short loc_18001854B
0x180018517  lea     rbx, aImage; "image"
0x18001851e  jmp     short loc_180018531
0x180018520  cmp     [rsp+278h+arg_20], 0
0x180018528  jz      short loc_18001854B
0x18001852a  lea     rbx, aVideo_0; "video"
0x180018531  mov     [rsp+278h+ppwsz], rbx
0x180018536  jmp     short loc_180018550
0x180018538  cmp     [rsp+278h+arg_20], 0
0x180018540  jz      short loc_18001854B
0x180018542  lea     rbx, aAudio_0; "audio"
0x180018549  jmp     short loc_180018531
0x18001854b  mov     rbx, [rsp+278h+ppwsz]
0x180018550  test    rbx, rbx
0x180018553  jz      short loc_1800185BD
0x180018555  xor     edx, edx; Val
0x180018557  mov     r8d, 200h; Size
0x18001855d  lea     rcx, [rsp+278h+psz]; void *
0x180018562  call    memset_0
0x180018567  mov     r9, rbx
0x18001856a  lea     r8, aSystemfileasso; "SystemFileAssociations\\%s"
0x180018571  mov     edx, 100h; unsigned __int64
0x180018576  lea     rcx, [rsp+278h+psz]; unsigned __int16 *
0x18001857b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018580  mov     esi, eax
0x180018582  test    eax, eax
0x180018584  js      short loc_1800185BD
0x180018586  lea     rdx, [rsp+278h+ppwsz]; ppwsz
0x18001858b  lea     rcx, [rsp+278h+psz]; psz
0x180018590  call    cs:__imp_SHStrDupW
0x180018596  mov     esi, eax
0x180018598  test    eax, eax
0x18001859a  js      short loc_1800185BD
0x18001859c  lea     rdx, [rsp+278h+ppwsz]
0x1800185a1  mov     rcx, r12
0x1800185a4  call    ?Add@?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA_KAEBQEAG@Z; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::Add(ushort * const &)
0x1800185a9  nop
0x1800185aa  jmp     short loc_1800185BD
0x1800185ac  jmp     short $+2
0x1800185ae  mov     rcx, [rsp+278h+ppwsz]; pv
0x1800185b3  call    cs:__imp_CoTaskMemFree
0x1800185b9  mov     esi, [rsp+278h+var_250]
0x1800185bd  lea     rcx, [rsp+278h+pszFirst]
0x1800185c2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800185c7  mov     eax, esi
0x1800185c9  mov     rcx, [rsp+278h+var_28]
0x1800185d1  xor     rcx, rsp; StackCookie
0x1800185d4  call    __security_check_cookie
0x1800185d9  mov     rbx, [rsp+278h+arg_10]
0x1800185e1  add     rsp, 260h
0x1800185e8  pop     r14
0x1800185ea  pop     r12
0x1800185ec  pop     rsi
0x1800185ed  retn
```
