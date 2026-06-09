# CONFIG_XML_DOM::GenerateDom(PARSE_ERROR_INFO *)

- ea: `0x1800209b0`
- end: `0x180020fb7`
- name: `?GenerateDom@CONFIG_XML_DOM@@AEAAJPEAVPARSE_ERROR_INFO@@@Z`
- size: `1543`
- prototype: `__int64 __fastcall(CONFIG_XML_DOM *__hidden this, struct PARSE_ERROR_INFO *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020534`
- `0x1800213d0`
- `0x180021500`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x180011130`
- `0x180018a88`
- `0x18001c250`
- `0x18001feb8`
- `0x18002014c`
- `0x1800201f4`
- `0x1800203e0`
- `0x1800209b0`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020a5b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020a5b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020cc3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020dae`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020e2a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020cc3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020dae`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180020e2a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180020d7f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180020d7f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180020d6b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180020d6b`
- `XmlLite!CreateXmlReader` at `0x180020a9c`
- `XmlLite!CreateXmlReader` at `0x180020a9c`

## pseudocode

```c
__int64 __fastcall CONFIG_XML_DOM::GenerateDom(CONFIG_XML_DOM *this, struct PARSE_ERROR_INFO *a2)
{
  int ChildData; // ebx
  SMALL_STRU *v4; // r12
  char *v5; // rdi
  XML_READ_BUFFER *v6; // rsi
  XML_READ_BUFFER *v7; // rax
  PREAMBLE_LIST *v8; // r14
  int v9; // eax
  unsigned int v10; // edx
  int v11; // ecx
  unsigned __int16 v12; // dx
  int v13; // eax
  XML_READ_BUFFER *v14; // r12
  int v15; // esi
  struct CONFIG_DOM_NODE *v16; // r13
  int v17; // eax
  unsigned int v18; // esi
  signed int LastError; // eax
  int v20; // eax
  __int64 v21; // r13
  int v23; // [rsp+40h] [rbp-30h] BYREF
  int v24; // [rsp+44h] [rbp-2Ch] BYREF
  void *ppvObject; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v30; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+58h] BYREF

  v28 = 0;
  ppvObject = 0;
  v31 = 0;
  v30 = 0;
  v24 = 0;
  v26 = 0;
  v23 = 0;
  ppv = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = (CONFIG_XML_DOM *)((char *)this + 128);
  v5 = 0;
  v6 = 0;
  ChildData = SMALL_STRU::Copy((CONFIG_XML_DOM *)((char *)this + 128), L"UTF-8");
  if ( ChildData < 0 )
    goto LABEL_71;
  CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage3, &ppv);
  v7 = (XML_READ_BUFFER *)operator new(0x20u);
  if ( !v7 || (v6 = XML_READ_BUFFER::XML_READ_BUFFER(v7, *((unsigned __int8 **)this + 4), *((_DWORD *)this + 7))) == 0 )
  {
LABEL_70:
    ChildData = -2147024888;
    goto LABEL_71;
  }
  ChildData = CreateXmlReader(&stru_180060860, &ppvObject, 0);
  if ( ChildData >= 0 )
  {
    ChildData = (*(__int64 (__fastcall **)(void *, XML_READ_BUFFER *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v6);
    if ( ChildData >= 0 )
    {
      v8 = 0;
      ChildData = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 0, ppv);
      if ( ChildData >= 0 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v9 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v31);
              if ( v9 )
              {
                if ( v9 < 0 )
                  goto LABEL_68;
                if ( v9 == 1 )
                {
                  ChildData = 0;
                  *((_QWORD *)this + 17) = v8;
                  v5 = 0;
                  goto LABEL_71;
                }
              }
              v11 = *((_DWORD *)this + 3);
              if ( (v11 & 1) == 0 )
                break;
              if ( v31 > 0xD )
                break;
              v10 = 8472;
              if ( !_bittest((const int *)&v10, v31) )
                break;
              if ( (*(int (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 128LL))(
                     ppvObject,
                     &v26,
                     &v23) < 0 )
              {
LABEL_68:
                (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvObject + 168LL))(ppvObject, &v30);
                ChildData = -2147024883;
                PARSE_ERROR_INFO::SetErrorInfo(a2, 2147942413LL, 2, 3221228173LL, &v28, v30, this, 0, v23, ppvObject);
                goto LABEL_83;
              }
              if ( !v8 )
              {
                v8 = (PREAMBLE_LIST *)operator new(0x10u);
                if ( !v8 )
                  goto LABEL_69;
                *(_DWORD *)v8 = 0;
                *((_QWORD *)v8 + 1) = 0;
              }
              switch ( v31 )
              {
                case 3u:
                  v12 = 3;
                  break;
                case 4u:
                  v12 = 4;
                  break;
                case 8u:
                  v12 = 1;
                  break;
                case 0xDu:
                  v12 = 2;
                  break;
                default:
                  goto LABEL_82;
              }
              v13 = PREAMBLE_LIST::AddEntry(v8, v12, v26);
LABEL_35:
              ChildData = v13;
              if ( v13 < 0 )
                goto LABEL_83;
            }
            if ( v31 != 17 )
              break;
            *((_DWORD *)this + 3) = v11 | 4;
            if ( (*(int (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                   ppvObject,
                   L"encoding",
                   0) >= 0 )
            {
              ChildData = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 128LL))(
                            ppvObject,
                            &v26,
                            &v23);
              if ( ChildData < 0 )
                goto LABEL_83;
              if ( v23 )
              {
                v13 = SMALL_STRU::Copy(v4, v26);
                goto LABEL_35;
              }
            }
          }
          v14 = v6;
          if ( v31 == 1 )
            break;
          if ( v31 == 15 )
          {
            v20 = *((_DWORD *)this + 16);
            if ( !v20
              || (*((_DWORD *)this + 16) = v20 - 1,
                  (v21 = *((_QWORD *)BUFFER::QueryPtr((CONFIG_XML_DOM *)((char *)this + 72))
                         + *((unsigned int *)this + 16))) == 0) )
            {
LABEL_82:
              ChildData = -2147024883;
LABEL_83:
              v5 = 0;
LABEL_84:
              if ( !v8 )
                goto LABEL_71;
LABEL_85:
              PREAMBLE_LIST::`scalar deleting destructor'(v8, v10);
              goto LABEL_71;
            }
            if ( !v8 )
            {
              v8 = (PREAMBLE_LIST *)operator new(0x10u);
              if ( !v8 )
              {
LABEL_69:
                v5 = 0;
                goto LABEL_70;
              }
              *(_DWORD *)v8 = 0;
              *((_QWORD *)v8 + 1) = 0;
              v5 = 0;
              ChildData = PREAMBLE_LIST::AddEntry(v8, 2u, &szDomain);
              if ( ChildData < 0 )
                goto LABEL_85;
            }
            *(_QWORD *)(v21 + 64) = v8;
LABEL_66:
            v4 = (CONFIG_XML_DOM *)((char *)this + 128);
            v8 = 0;
          }
          else
          {
            v4 = (CONFIG_XML_DOM *)((char *)this + 128);
          }
        }
        ChildData = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvObject + 168LL))(ppvObject, &v30);
        if ( ChildData < 0 )
          goto LABEL_83;
        ChildData = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 176LL))(ppvObject, &v24);
        if ( ChildData < 0 )
          goto LABEL_83;
        v15 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
        if ( *((_DWORD *)this + 16) )
          v16 = (struct CONFIG_DOM_NODE *)*((_QWORD *)BUFFER::QueryPtr((CONFIG_XML_DOM *)((char *)this + 72))
                                          + (unsigned int)(*((_DWORD *)this + 16) - 1));
        else
          v16 = 0;
        v5 = (char *)operator new(0x48u);
        if ( !v5 )
        {
          ChildData = -2147024888;
          v6 = v14;
          goto LABEL_83;
        }
        v17 = *((_DWORD *)this + 3);
        *(_QWORD *)v5 = &CONFIG_DOM_NODE::`vftable'{for `IConfigDomNode'};
        *((_QWORD *)v5 + 1) = &CONFIG_DOM_NODE::`vftable'{for `IArrayListEntry'};
        *((_DWORD *)v5 + 4) = 1;
        *((_QWORD *)v5 + 3) = 0;
        *((_DWORD *)v5 + 5) = -(v17 & 1) & 1;
        *((_QWORD *)v5 + 4) = 0;
        *((_QWORD *)v5 + 5) = 0;
        *((_QWORD *)v5 + 6) = 0;
        *((_QWORD *)v5 + 7) = 0;
        *((_QWORD *)v5 + 8) = 0;
        ChildData = CONFIG_DOM_NODE::Create((CONFIG_DOM_NODE *)v5, this, v16, (struct IXmlReader *)ppvObject, v8, v30);
        if ( ChildData < 0 )
        {
          v6 = v14;
          goto LABEL_84;
        }
        if ( !v15 )
        {
          v18 = 8 * *((_DWORD *)this + 16) + 8;
          if ( v18 <= BUFFER::QuerySize((CONFIG_XML_DOM *)((char *)this + 72))
            || BUFFER::Resize((CONFIG_XML_DOM *)((char *)this + 72), 4 * v18) )
          {
            *((_QWORD *)BUFFER::QueryPtr((CONFIG_XML_DOM *)((char *)this + 72)) + *((unsigned int *)this + 16)) = v5;
            ++*((_DWORD *)this + 16);
          }
          else
          {
            LastError = GetLastError();
            ChildData = LastError;
            if ( LastError > 0 )
              ChildData = (unsigned __int16)LastError | 0x80070000;
            v6 = v14;
            if ( ChildData < 0 )
              goto LABEL_71;
          }
        }
        if ( v16 )
        {
          ChildData = CONFIG_DOM_NODE::AllocateChildData(v16);
          if ( ChildData >= 0 )
            ChildData = ARRAY_LIST::AddEntry(
                          (ARRAY_LIST *)(*((_QWORD *)v16 + 6) + 8LL),
                          (struct IArrayListEntry *)(v5 + 8),
                          0xFFFFFFFF);
          v6 = v14;
          if ( ChildData < 0 )
            goto LABEL_71;
        }
        else
        {
          *((_QWORD *)this + 15) = v5;
        }
        v6 = v14;
        goto LABEL_66;
      }
    }
  }
LABEL_71:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 168LL))(v5, 1);
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(XML_READ_BUFFER *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)ChildData;
}

```

## disassembly

```asm
0x1800209b0  mov     [rsp-38h+arg_0], rbx
0x1800209b5  mov     [rsp-38h+arg_8], rdx
0x1800209ba  push    rbp
0x1800209bb  push    rsi
0x1800209bc  push    rdi
0x1800209bd  push    r12
0x1800209bf  push    r13
0x1800209c1  push    r14
0x1800209c3  push    r15
0x1800209c5  mov     rbp, rsp
0x1800209c8  sub     rsp, 70h
0x1800209cc  mov     [rbp+var_10], 0
0x1800209d4  mov     r15, rcx
0x1800209d7  mov     [rbp+ppvObject], 0
0x1800209df  mov     [rbp+arg_18], 0
0x1800209e6  mov     [rbp+arg_10], 0
0x1800209ed  mov     [rbp+var_2C], 0
0x1800209f4  mov     [rbp+var_20], 0
0x1800209fc  mov     [rbp+var_30], 0
0x180020a03  mov     [rbp+var_18], 0
0x180020a0b  test    rdx, rdx
0x180020a0e  jnz     short loc_180020A1A
0x180020a10  mov     ebx, 80070057h
0x180020a15  jmp     loc_180020F71
0x180020a1a  lea     r12, [rcx+80h]
0x180020a21  xor     edi, edi
0x180020a23  mov     rcx, r12; this
0x180020a26  lea     rdx, aUtf8; "UTF-8"
0x180020a2d  xor     esi, esi
0x180020a2f  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180020a34  mov     ebx, eax
0x180020a36  test    eax, eax
0x180020a38  js      loc_180020F07
0x180020a3e  lea     rax, [rbp+var_18]
0x180020a42  xor     edx, edx; pUnkOuter
0x180020a44  lea     r9, IID_IMultiLanguage3; riid
0x180020a4b  mov     [rsp+70h+ppv], rax; ppv
0x180020a50  lea     r8d, [rdi+1]; dwClsContext
0x180020a54  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180020a5b  call    cs:__imp_CoCreateInstance
0x180020a61  lea     ecx, [rdi+20h]; Size
0x180020a64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020a69  test    rax, rax
0x180020a6c  jz      loc_180020F02
0x180020a72  mov     rdx, [r15+20h]; unsigned __int8 *
0x180020a76  mov     rcx, rax; this
0x180020a79  mov     r8d, [r15+1Ch]; unsigned int
0x180020a7d  call    ??0XML_READ_BUFFER@@QEAA@PEAEK@Z; XML_READ_BUFFER::XML_READ_BUFFER(uchar *,ulong)
0x180020a82  mov     rsi, rax
0x180020a85  test    rax, rax
0x180020a88  jz      loc_180020F02
0x180020a8e  xor     r8d, r8d; pMalloc
0x180020a91  lea     rdx, [rbp+ppvObject]; ppvObject
0x180020a95  lea     rcx, stru_180060860; riid
0x180020a9c  call    cs:__imp_CreateXmlReader
0x180020aa2  mov     ebx, eax
0x180020aa4  test    eax, eax
0x180020aa6  js      loc_180020F07
0x180020aac  mov     rcx, [rbp+ppvObject]
0x180020ab0  mov     rdx, rsi
0x180020ab3  mov     rax, [rcx]
0x180020ab6  mov     rax, [rax+18h]
0x180020aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020abf  mov     ebx, eax
0x180020ac1  test    eax, eax
0x180020ac3  js      loc_180020F07
0x180020ac9  mov     rcx, [rbp+ppvObject]
0x180020acd  xor     edx, edx
0x180020acf  mov     r8, [rbp+var_18]
0x180020ad3  xor     r14d, r14d
0x180020ad6  mov     rax, [rcx]
0x180020ad9  mov     rax, [rax+28h]
0x180020add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ae2  mov     ebx, eax
0x180020ae4  test    eax, eax
0x180020ae6  js      loc_180020F07
0x180020aec  lea     ebx, [rdi+4]
0x180020aef  lea     edi, [rbx-2]
0x180020af2  jmp     loc_180020E95
0x180020af7  lea     r12, [r15+80h]
0x180020afe  mov     rcx, [rbp+ppvObject]
0x180020b02  lea     rdx, [rbp+arg_18]
0x180020b06  mov     rax, [rcx]
0x180020b09  mov     rax, [rax+30h]
0x180020b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b12  test    eax, eax
0x180020b14  jz      short loc_180020B25
0x180020b16  js      loc_180020EAD
0x180020b1c  cmp     eax, 1
0x180020b1f  jz      loc_180020EA0
0x180020b25  mov     ecx, [r15+0Ch]
0x180020b29  mov     eax, [rbp+arg_18]
0x180020b2c  test    cl, 1
0x180020b2f  jz      loc_180020BCF
0x180020b35  cmp     eax, 0Dh
0x180020b38  ja      loc_180020BCF
0x180020b3e  mov     edx, 2118h
0x180020b43  bt      edx, eax
0x180020b46  jnb     loc_180020BCF
0x180020b4c  mov     rcx, [rbp+ppvObject]
0x180020b50  lea     r8, [rbp+var_30]
0x180020b54  lea     rdx, [rbp+var_20]
0x180020b58  mov     rax, [rcx]
0x180020b5b  mov     rax, [rax+80h]
0x180020b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b67  test    eax, eax
0x180020b69  js      loc_180020EAD
0x180020b6f  test    r14, r14
0x180020b72  jnz     short loc_180020B92
0x180020b74  lea     ecx, [r14+10h]; Size
0x180020b78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020b7d  mov     r14, rax
0x180020b80  test    rax, rax
0x180020b83  jz      loc_180020F00
0x180020b89  xor     eax, eax
0x180020b8b  mov     [r14], eax
0x180020b8e  mov     [r14+8], rax
0x180020b92  mov     ecx, [rbp+arg_18]
0x180020b95  sub     ecx, r13d
0x180020b98  jz      short loc_180020BBD
0x180020b9a  sub     ecx, 1
0x180020b9d  jz      short loc_180020BB8
0x180020b9f  sub     ecx, ebx
0x180020ba1  jz      short loc_180020BB1
0x180020ba3  cmp     ecx, 5
0x180020ba6  jnz     loc_180020F9A
0x180020bac  movzx   edx, di
0x180020baf  jmp     short loc_180020BC1
0x180020bb1  mov     edx, 1
0x180020bb6  jmp     short loc_180020BC1
0x180020bb8  movzx   edx, bx
0x180020bbb  jmp     short loc_180020BC1
0x180020bbd  movzx   edx, r13w; unsigned __int16
0x180020bc1  mov     r8, [rbp+var_20]; unsigned __int16 *
0x180020bc5  mov     rcx, r14; this
0x180020bc8  call    ?AddEntry@PREAMBLE_LIST@@QEAAJGPEBG@Z; PREAMBLE_LIST::AddEntry(ushort,ushort const *)
0x180020bcd  jmp     short loc_180020C3C
0x180020bcf  cmp     eax, 11h
0x180020bd2  jnz     short loc_180020C50
0x180020bd4  or      ecx, ebx
0x180020bd6  lea     rdx, aEncoding; "encoding"
0x180020bdd  mov     [r15+0Ch], ecx
0x180020be1  xor     r8d, r8d
0x180020be4  mov     rcx, [rbp+ppvObject]
0x180020be8  mov     rax, [rcx]
0x180020beb  mov     rax, [rax+50h]
0x180020bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf4  test    eax, eax
0x180020bf6  js      loc_180020AFE
0x180020bfc  mov     rcx, [rbp+ppvObject]
0x180020c00  lea     r8, [rbp+var_30]
0x180020c04  lea     rdx, [rbp+var_20]
0x180020c08  mov     rax, [rcx]
0x180020c0b  mov     rax, [rax+80h]
0x180020c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c17  mov     ebx, eax
0x180020c19  test    eax, eax
0x180020c1b  js      loc_180020F9F
0x180020c21  cmp     [rbp+var_30], 0
0x180020c25  mov     ebx, 4
0x180020c2a  jz      loc_180020AFE
0x180020c30  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180020c34  mov     rcx, r12; this
0x180020c37  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180020c3c  mov     ebx, eax
0x180020c3e  test    eax, eax
0x180020c40  js      loc_180020F9F
0x180020c46  mov     ebx, 4
0x180020c4b  jmp     loc_180020AFE
0x180020c50  mov     r12, rsi
0x180020c53  cmp     eax, 1
0x180020c56  jnz     loc_180020E0B
0x180020c5c  mov     rcx, [rbp+ppvObject]
0x180020c60  lea     rdx, [rbp+arg_10]
0x180020c64  mov     rax, [rcx]
0x180020c67  mov     rax, [rax+0A8h]
0x180020c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c73  mov     ebx, eax
0x180020c75  test    eax, eax
0x180020c77  js      loc_180020F9F
0x180020c7d  mov     rcx, [rbp+ppvObject]
0x180020c81  lea     rdx, [rbp+var_2C]
0x180020c85  mov     rax, [rcx]
0x180020c88  mov     rax, [rax+0B0h]
0x180020c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c94  mov     ebx, eax
0x180020c96  test    eax, eax
0x180020c98  js      loc_180020F9F
0x180020c9e  mov     rcx, [rbp+ppvObject]
0x180020ca2  mov     rax, [rcx]
0x180020ca5  mov     rax, [rax+0A0h]
0x180020cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb1  cmp     dword ptr [r15+40h], 0
0x180020cb6  mov     esi, eax
0x180020cb8  jnz     short loc_180020CBF
0x180020cba  xor     r13d, r13d
0x180020cbd  jmp     short loc_180020CD3
0x180020cbf  lea     rcx, [r15+48h]
0x180020cc3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180020cc9  mov     ecx, [r15+40h]
0x180020ccd  dec     ecx
0x180020ccf  mov     r13, [rax+rcx*8]
0x180020cd3  mov     ecx, 48h ; 'H'; Size
0x180020cd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020cdd  xor     ebx, ebx
0x180020cdf  mov     rdi, rax
0x180020ce2  test    rax, rax
0x180020ce5  jz      loc_180020F90
0x180020ceb  mov     eax, [r15+0Ch]
0x180020cef  lea     rcx, ??_7CONFIG_DOM_NODE@@6BIConfigDomNode@@@; const CONFIG_DOM_NODE::`vftable'{for `IConfigDomNode'}
0x180020cf6  mov     [rdi], rcx
0x180020cf9  mov     r8, r13; struct CONFIG_DOM_NODE *
0x180020cfc  shr     eax, 1
0x180020cfe  lea     rcx, ??_7CONFIG_DOM_NODE@@6BIArrayListEntry@@@; const CONFIG_DOM_NODE::`vftable'{for `IArrayListEntry'}
0x180020d05  mov     [rdi+8], rcx
0x180020d09  mov     rdx, r15; struct CONFIG_XML_DOM *
0x180020d0c  sbb     eax, eax
0x180020d0e  mov     dword ptr [rdi+10h], 1
0x180020d15  and     eax, 1
0x180020d18  mov     [rdi+18h], rbx
0x180020d1c  mov     [rdi+14h], eax
0x180020d1f  mov     rcx, rdi; this
0x180020d22  mov     [rdi+20h], rbx
0x180020d26  mov     [rdi+28h], rbx
0x180020d2a  mov     [rdi+30h], rbx
0x180020d2e  mov     [rdi+38h], rbx
0x180020d32  mov     [rdi+40h], rbx
0x180020d36  mov     eax, [rbp+arg_10]
0x180020d39  mov     r9, [rbp+ppvObject]; struct IXmlReader *
0x180020d3d  mov     [rsp+70h+var_48], eax; unsigned int
0x180020d41  mov     [rsp+70h+ppv], r14; struct PREAMBLE_LIST *
0x180020d46  call    ?Create@CONFIG_DOM_NODE@@QEAAJPEAVCONFIG_XML_DOM@@PEAV1@PEAUIXmlReader@@PEAVPREAMBLE_LIST@@K@Z; CONFIG_DOM_NODE::Create(CONFIG_XML_DOM *,CONFIG_DOM_NODE *,IXmlReader *,PREAMBLE_LIST *,ulong)
0x180020d4b  mov     ebx, eax
0x180020d4d  test    eax, eax
0x180020d4f  js      loc_180020F8B
0x180020d55  test    esi, esi
0x180020d57  jnz     short loc_180020DC0
0x180020d59  mov     eax, [r15+40h]
0x180020d5d  lea     rbx, [r15+48h]
0x180020d61  mov     rcx, rbx
0x180020d64  lea     esi, ds:8[rax*8]
0x180020d6b  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180020d71  cmp     esi, eax
0x180020d73  jbe     short loc_180020DAB
0x180020d75  lea     edx, ds:0[rsi*4]
0x180020d7c  mov     rcx, rbx
0x180020d7f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180020d85  test    al, al
0x180020d87  jnz     short loc_180020DAB
0x180020d89  call    cs:__imp_GetLastError
0x180020d8f  mov     ebx, eax
0x180020d91  test    eax, eax
0x180020d93  jle     short loc_180020D9E
0x180020d95  movzx   ebx, ax
0x180020d98  or      ebx, 80070000h
0x180020d9e  mov     rsi, r12
0x180020da1  test    ebx, ebx
0x180020da3  js      loc_180020F07
0x180020da9  jmp     short loc_180020DC0
0x180020dab  mov     rcx, rbx
0x180020dae  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180020db4  mov     ecx, [r15+40h]
0x180020db8  mov     [rax+rcx*8], rdi
0x180020dbc  inc     dword ptr [r15+40h]
0x180020dc0  test    r13, r13
0x180020dc3  jnz     short loc_180020DCB
0x180020dc5  mov     [r15+78h], rdi
0x180020dc9  jmp     short loc_180020DFB
0x180020dcb  mov     rcx, r13; this
0x180020dce  call    ?AllocateChildData@CONFIG_DOM_NODE@@QEAAJXZ; CONFIG_DOM_NODE::AllocateChildData(void)
0x180020dd3  mov     ebx, eax
0x180020dd5  test    eax, eax
0x180020dd7  js      short loc_180020DF0
0x180020dd9  mov     rcx, [r13+30h]
0x180020ddd  lea     rdx, [rdi+8]; struct IArrayListEntry *
0x180020de1  add     rcx, 8; this
0x180020de5  or      r8d, 0FFFFFFFFh; unsigned int
0x180020de9  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180020dee  mov     ebx, eax
0x180020df0  mov     rsi, r12
0x180020df3  test    ebx, ebx
0x180020df5  js      loc_180020F07
0x180020dfb  mov     ebx, 4
0x180020e00  mov     rsi, r12
0x180020e03  lea     edi, [rbx-2]
0x180020e06  jmp     loc_180020E8B
0x180020e0b  cmp     eax, 0Fh
0x180020e0e  jnz     loc_180020AF7
0x180020e14  mov     eax, [r15+40h]
0x180020e18  test    eax, eax
0x180020e1a  jz      loc_180020F9A
0x180020e20  dec     eax
0x180020e22  lea     rcx, [r15+48h]
0x180020e26  mov     [r15+40h], eax
0x180020e2a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180020e30  mov     ecx, [r15+40h]
0x180020e34  mov     r13, [rax+rcx*8]
0x180020e38  test    r13, r13
0x180020e3b  jz      loc_180020F9A
0x180020e41  test    r14, r14
  ... truncated ...
```
