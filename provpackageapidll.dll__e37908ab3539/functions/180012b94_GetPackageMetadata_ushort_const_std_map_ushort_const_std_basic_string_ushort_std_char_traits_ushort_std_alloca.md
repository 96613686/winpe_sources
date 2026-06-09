# GetPackageMetadata(ushort const *,std::map<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180012b94`
- end: `0x180012fc1`
- name: `?GetPackageMetadata@@YAJPEBGAEAV?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z`
- size: `1069`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d24`
- `0x18000907c`

## callees

- `0x180001510`
- `0x180002110`
- `0x180006014`
- `0x18000637c`
- `0x180006648`
- `0x180010154`
- `0x180010294`
- `0x180012b94`
- `0x1800130cc`
- `0x180018458`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012e86`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180012e86`

## string_xrefs

- `0x180012bf1`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012ccb`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012e99`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012f09`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180012f25`: `    Failed to read node type`

## pseudocode

```c
__int64 __fastcall GetPackageMetadata(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  struct IXmlReader *v7; // rcx
  struct IStream *v8; // rcx
  int v10; // eax
  int v11; // eax
  struct IXmlReader *v12; // rcx
  struct IStream *v13; // rcx
  int v14; // eax
  __int64 v15; // rbx
  _OWORD *v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  void **v22; // r9
  char *v23; // rsi
  __int64 v24; // rbx
  struct IXmlReader *v25; // rcx
  struct IStream *v26; // rcx
  struct IXmlReader *v27; // rcx
  struct IStream *v28; // rcx
  struct IXmlReader *v29; // rcx
  struct IStream *v30; // rcx
  struct IXmlReader *ppvObject; // [rsp+30h] [rbp-69h] BYREF
  struct IStream *v32; // [rsp+38h] [rbp-61h] BYREF
  int v33; // [rsp+40h] [rbp-59h] BYREF
  __int64 v34; // [rsp+48h] [rbp-51h] BYREF
  __int64 v35; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v37; // [rsp+68h] [rbp-31h]
  __int128 v38; // [rsp+70h] [rbp-29h] BYREF
  __int128 v39; // [rsp+80h] [rbp-19h]
  void *Src[2]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v41; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]

  v32 = 0;
  ppvObject = 0;
  v5 = SetupInput(&v32, &ppvObject, a1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v34 = 0;
    while ( !((unsigned int (__fastcall *)(struct IXmlReader *))ppvObject->lpVtbl->IsEOF)(ppvObject) )
    {
      v33 = 0;
      v10 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))ppvObject->lpVtbl->Read)(ppvObject, &v33);
      v6 = v10;
      if ( v10 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetPackageMetadata",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          685,
          v10);
        ProvPackageLog(3, L"    Failed to read node type");
        v27 = ppvObject;
        if ( ppvObject )
        {
          ppvObject = 0;
          ((void (__fastcall *)(struct IXmlReader *))v27->lpVtbl->Release)(v27);
        }
        v28 = v32;
        if ( v32 )
        {
          v32 = 0;
          ((void (__fastcall *)(struct IStream *))v28->lpVtbl->Release)(v28);
        }
        return v6;
      }
      if ( v33 == 1 )
      {
        v11 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))ppvObject->lpVtbl->GetLocalName)(
                ppvObject,
                &v34,
                0);
        v6 = v11;
        if ( v11 < 0 )
        {
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "GetPackageMetadata",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
            690,
            v11);
          ProvPackageLog(3, L"    Failed to get element local name");
          v12 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            ((void (__fastcall *)(struct IXmlReader *))v12->lpVtbl->Release)(v12);
          }
          v13 = v32;
          if ( v32 )
          {
            v32 = 0;
            ((void (__fastcall *)(struct IStream *))v13->lpVtbl->Release)(v13);
          }
          return v6;
        }
      }
      else if ( v33 == 3 )
      {
        v35 = 0;
        v14 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))ppvObject->lpVtbl->GetValue)(
                ppvObject,
                &v35,
                0);
        v6 = v14;
        if ( v14 < 0 )
        {
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "GetPackageMetadata",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
            697,
            v14);
          ProvPackageLog(3, L"    Failed to get metadata value");
          v25 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            ((void (__fastcall *)(struct IXmlReader *))v25->lpVtbl->Release)(v25);
          }
          v26 = v32;
          if ( v32 )
          {
            v32 = 0;
            ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
          }
          return v6;
        }
        if ( v34 )
        {
          std::wstring::wstring(Src, v35);
          std::wstring::wstring(&v38, v34);
          if ( a3[1] == 0x555555555555555LL )
            std::_Xlength_error("list too long");
          v15 = *a3;
          v36[1] = a3;
          v37 = 0;
          v16 = operator new(0x30u);
          v16[1] = v38;
          v16[2] = v39;
          *(_QWORD *)&v39 = 0;
          *((_QWORD *)&v39 + 1) = 7;
          LOWORD(v38) = 0;
          ++a3[1];
          v17 = *(_QWORD **)(v15 + 8);
          *(_QWORD *)v16 = v15;
          *((_QWORD *)v16 + 1) = v17;
          v37 = 0;
          *(_QWORD *)(v15 + 8) = v16;
          *v17 = v16;
          std::wstring::~wstring(&v38);
          v18 = (_QWORD *)(*(_QWORD *)(*a3 + 8LL) + 16LL);
          if ( *(_QWORD *)(*(_QWORD *)(*a3 + 8LL) + 40LL) > 7u )
            v18 = (_QWORD *)*v18;
          v36[0] = v18;
          v19 = std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::operator[](
                  a2,
                  v36);
          if ( (void **)v19 != Src )
          {
            v21 = v41;
            v22 = Src;
            if ( v42 > 7 )
              v22 = (void **)Src[0];
            if ( v41 > *(_QWORD *)(v19 + 24) )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v19,
                v41,
                v20,
                v22);
            }
            else
            {
              if ( *(_QWORD *)(v19 + 24) <= 7u )
                v23 = (char *)v19;
              else
                v23 = *(char **)v19;
              *(_QWORD *)(v19 + 16) = v41;
              v24 = 2 * v21;
              memmove_0(v23, v22, 2 * v21);
              *(_WORD *)&v23[v24] = 0;
            }
          }
          std::wstring::~wstring(Src);
        }
      }
    }
    v29 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v29->lpVtbl->Release)(v29);
    }
    v30 = v32;
    if ( v32 )
    {
      v32 = 0;
      ((void (__fastcall *)(struct IStream *))v30->lpVtbl->Release)(v30);
    }
    return 0;
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetPackageMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      677,
      v5);
    ProvPackageLog(3, L"    Failed to setup input");
    v7 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      ((void (__fastcall *)(struct IXmlReader *))v7->lpVtbl->Release)(v7);
    }
    v8 = v32;
    if ( v32 )
    {
      v32 = 0;
      ((void (__fastcall *)(struct IStream *))v8->lpVtbl->Release)(v8);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180012b94  push    rbp
0x180012b96  push    rbx
0x180012b97  push    rsi
0x180012b98  push    rdi
0x180012b99  push    r12
0x180012b9b  push    r14
0x180012b9d  push    r15
0x180012b9f  lea     rbp, [rsp-27h]
0x180012ba4  sub     rsp, 0C0h
0x180012bab  mov     rax, cs:__security_cookie
0x180012bb2  xor     rax, rsp
0x180012bb5  mov     [rbp+57h+var_40], rax
0x180012bb9  mov     r14, r8
0x180012bbc  mov     r15, rdx
0x180012bbf  xor     r12d, r12d
0x180012bc2  mov     [rbp+57h+var_B8], r12
0x180012bc6  mov     [rbp+57h+ppvObject], r12
0x180012bca  mov     r8, rcx; unsigned __int16 *
0x180012bcd  lea     rdx, [rbp+57h+ppvObject]; ppvObject
0x180012bd1  lea     rcx, [rbp+57h+var_B8]; struct IStream **
0x180012bd5  call    ?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z; SetupInput(IStream * *,IXmlReader * *,ushort const *)
0x180012bda  mov     ebx, eax
0x180012bdc  lea     edi, [r12+3]
0x180012be1  test    eax, eax
0x180012be3  jns     short loc_180012C57
0x180012be5  mov     [rsp+0F0h+var_C8], eax
0x180012be9  mov     [rsp+0F0h+var_D0], 2A5h
0x180012bf1  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012bf8  lea     r8, aGetpackagemeta; "GetPackageMetadata"
0x180012bff  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012c06  mov     ecx, edi
0x180012c08  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012c0d  lea     rdx, aFailedToSetupI; "    Failed to setup input"
0x180012c14  mov     ecx, edi
0x180012c16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012c1b  nop
0x180012c1c  mov     rcx, [rbp+57h+ppvObject]
0x180012c20  test    rcx, rcx
0x180012c23  jz      short loc_180012C36
0x180012c25  mov     [rbp+57h+ppvObject], r12
0x180012c29  mov     rax, [rcx]
0x180012c2c  mov     rax, [rax+10h]
0x180012c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c35  nop
0x180012c36  mov     rcx, [rbp+57h+var_B8]
0x180012c3a  test    rcx, rcx
0x180012c3d  jz      short loc_180012C50
0x180012c3f  mov     [rbp+57h+var_B8], r12
0x180012c43  mov     rax, [rcx]
0x180012c46  mov     rax, [rax+10h]
0x180012c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c4f  nop
0x180012c50  mov     eax, ebx
0x180012c52  jmp     loc_180012FA3
0x180012c57  mov     [rbp+57h+var_A8], r12
0x180012c5b  mov     rcx, [rbp+57h+ppvObject]
0x180012c5f  mov     rax, [rcx]
0x180012c62  mov     rax, [rax+0C8h]
0x180012c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c6e  test    eax, eax
0x180012c70  jnz     loc_180012F6D
0x180012c76  mov     [rbp+57h+var_B0], r12d
0x180012c7a  mov     rcx, [rbp+57h+ppvObject]
0x180012c7e  mov     rax, [rcx]
0x180012c81  lea     rdx, [rbp+57h+var_B0]
0x180012c85  mov     rax, [rax+30h]
0x180012c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c8e  mov     ebx, eax
0x180012c90  test    eax, eax
0x180012c92  js      loc_180012EFD
0x180012c98  cmp     [rbp+57h+var_B0], 1
0x180012c9c  jnz     loc_180012D2F
0x180012ca2  mov     rcx, [rbp+57h+ppvObject]
0x180012ca6  mov     rax, [rcx]
0x180012ca9  xor     r8d, r8d
0x180012cac  lea     rdx, [rbp+57h+var_A8]
0x180012cb0  mov     rax, [rax+70h]
0x180012cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb9  mov     ebx, eax
0x180012cbb  test    eax, eax
0x180012cbd  jns     short loc_180012C5B
0x180012cbf  mov     [rsp+0F0h+var_C8], eax
0x180012cc3  mov     [rsp+0F0h+var_D0], 2B2h
0x180012ccb  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012cd2  lea     r8, aGetpackagemeta; "GetPackageMetadata"
0x180012cd9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012ce0  mov     ecx, edi
0x180012ce2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012ce7  lea     rdx, aFailedToGetEle; "    Failed to get element local name"
0x180012cee  mov     ecx, edi
0x180012cf0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012cf5  nop
0x180012cf6  mov     rcx, [rbp+57h+ppvObject]
0x180012cfa  test    rcx, rcx
0x180012cfd  jz      short loc_180012D10
0x180012cff  mov     [rbp+57h+ppvObject], r12
0x180012d03  mov     rax, [rcx]
0x180012d06  mov     rax, [rax+10h]
0x180012d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d0f  nop
0x180012d10  mov     rcx, [rbp+57h+var_B8]
0x180012d14  test    rcx, rcx
0x180012d17  jz      short loc_180012D2A
0x180012d19  mov     [rbp+57h+var_B8], r12
0x180012d1d  mov     rax, [rcx]
0x180012d20  mov     rax, [rax+10h]
0x180012d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d29  nop
0x180012d2a  jmp     loc_180012C50
0x180012d2f  cmp     [rbp+57h+var_B0], edi
0x180012d32  jnz     loc_180012C5B
0x180012d38  mov     [rbp+57h+var_A0], r12
0x180012d3c  mov     rcx, [rbp+57h+ppvObject]
0x180012d40  mov     rax, [rcx]
0x180012d43  xor     r8d, r8d
0x180012d46  lea     rdx, [rbp+57h+var_A0]
0x180012d4a  mov     rax, [rax+80h]
0x180012d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d56  mov     ebx, eax
0x180012d58  test    eax, eax
0x180012d5a  js      loc_180012E8D
0x180012d60  cmp     [rbp+57h+var_A8], r12
0x180012d64  jz      loc_180012C5B
0x180012d6a  mov     rdx, [rbp+57h+var_A0]
0x180012d6e  lea     rcx, [rbp+57h+Src]
0x180012d72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012d77  nop
0x180012d78  mov     rdx, [rbp+57h+var_A8]
0x180012d7c  lea     rcx, [rbp+57h+var_80]
0x180012d80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012d85  nop
0x180012d86  mov     rax, 555555555555555h
0x180012d90  cmp     [r14+8], rax
0x180012d94  jz      loc_180012E7F
0x180012d9a  mov     rbx, [r14]
0x180012d9d  mov     [rbp+57h+var_90], r14
0x180012da1  mov     [rbp+57h+var_88], r12
0x180012da5  mov     ecx, 30h ; '0'; Size
0x180012daa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012daf  mov     rdx, rax
0x180012db2  movups  xmm0, [rbp+57h+var_80]
0x180012db6  movups  xmmword ptr [rax+10h], xmm0
0x180012dba  movups  xmm1, [rbp+57h+var_70]
0x180012dbe  movups  xmmword ptr [rax+20h], xmm1
0x180012dc2  mov     qword ptr [rbp+57h+var_70], r12
0x180012dc6  mov     qword ptr [rbp+57h+var_70+8], 7
0x180012dce  mov     word ptr [rbp+57h+var_80], r12w
0x180012dd3  inc     qword ptr [r14+8]
0x180012dd7  mov     rax, [rbx+8]
0x180012ddb  mov     [rdx], rbx
0x180012dde  mov     [rdx+8], rax
0x180012de2  mov     [rbp+57h+var_88], r12
0x180012de6  mov     [rbx+8], rdx
0x180012dea  mov     [rax], rdx
0x180012ded  lea     rcx, [rbp+57h+var_80]
0x180012df1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012df6  mov     rax, [r14]
0x180012df9  mov     rcx, [rax+8]
0x180012dfd  add     rcx, 10h
0x180012e01  cmp     qword ptr [rcx+18h], 7
0x180012e06  jbe     short loc_180012E0B
0x180012e08  mov     rcx, [rcx]
0x180012e0b  mov     [rbp+57h+var_98], rcx
0x180012e0f  lea     rdx, [rbp+57h+var_98]
0x180012e13  mov     rcx, r15
0x180012e16  call    ??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z; std::map<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>>::operator[](ushort const * &&)
0x180012e1b  lea     rcx, [rbp+57h+Src]
0x180012e1f  cmp     rax, rcx
0x180012e22  jz      short loc_180012E71
0x180012e24  mov     rdx, [rbp+57h+var_50]
0x180012e28  lea     r9, [rbp+57h+Src]
0x180012e2c  cmp     [rbp+57h+var_48], 7
0x180012e31  cmova   r9, [rbp+57h+Src]
0x180012e36  cmp     rdx, [rax+18h]
0x180012e3a  ja      short loc_180012E68
0x180012e3c  cmp     qword ptr [rax+18h], 7
0x180012e41  jbe     short loc_180012E48
0x180012e43  mov     rsi, [rax]
0x180012e46  jmp     short loc_180012E4B
0x180012e48  mov     rsi, rax
0x180012e4b  mov     [rax+10h], rdx
0x180012e4f  lea     rbx, [rdx+rdx]
0x180012e53  mov     r8, rbx; Size
0x180012e56  mov     rdx, r9; Src
0x180012e59  mov     rcx, rsi; void *
0x180012e5c  call    memmove_0
0x180012e61  mov     [rsi+rbx], r12w
0x180012e66  jmp     short loc_180012E71
0x180012e68  mov     rcx, rax
0x180012e6b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180012e70  nop
0x180012e71  lea     rcx, [rbp+57h+Src]
0x180012e75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012e7a  jmp     loc_180012C5B
0x180012e7f  lea     rcx, aListTooLong; "list too long"
0x180012e86  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180012e8d  mov     [rsp+0F0h+var_C8], ebx
0x180012e91  mov     [rsp+0F0h+var_D0], 2B9h
0x180012e99  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012ea0  lea     r8, aGetpackagemeta; "GetPackageMetadata"
0x180012ea7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012eae  mov     ecx, edi
0x180012eb0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012eb5  lea     rdx, aFailedToGetMet; "    Failed to get metadata value"
0x180012ebc  mov     ecx, edi
0x180012ebe  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012ec3  nop
0x180012ec4  mov     rcx, [rbp+57h+ppvObject]
0x180012ec8  test    rcx, rcx
0x180012ecb  jz      short loc_180012EDE
0x180012ecd  mov     [rbp+57h+ppvObject], r12
0x180012ed1  mov     rax, [rcx]
0x180012ed4  mov     rax, [rax+10h]
0x180012ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012edd  nop
0x180012ede  mov     rcx, [rbp+57h+var_B8]
0x180012ee2  test    rcx, rcx
0x180012ee5  jz      short loc_180012EF8
0x180012ee7  mov     [rbp+57h+var_B8], r12
0x180012eeb  mov     rax, [rcx]
0x180012eee  mov     rax, [rax+10h]
0x180012ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ef7  nop
0x180012ef8  jmp     loc_180012C50
0x180012efd  mov     [rsp+0F0h+var_C8], ebx
0x180012f01  mov     [rsp+0F0h+var_D0], 2ADh
0x180012f09  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180012f10  lea     r8, aGetpackagemeta; "GetPackageMetadata"
0x180012f17  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180012f1e  mov     ecx, edi
0x180012f20  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012f25  lea     rdx, aFailedToReadNo; "    Failed to read node type"
0x180012f2c  mov     ecx, edi
0x180012f2e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180012f33  nop
0x180012f34  mov     rcx, [rbp+57h+ppvObject]
0x180012f38  test    rcx, rcx
0x180012f3b  jz      short loc_180012F4E
0x180012f3d  mov     [rbp+57h+ppvObject], r12
0x180012f41  mov     rax, [rcx]
0x180012f44  mov     rax, [rax+10h]
0x180012f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f4d  nop
0x180012f4e  mov     rcx, [rbp+57h+var_B8]
0x180012f52  test    rcx, rcx
0x180012f55  jz      short loc_180012F68
0x180012f57  mov     [rbp+57h+var_B8], r12
0x180012f5b  mov     rax, [rcx]
0x180012f5e  mov     rax, [rax+10h]
0x180012f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f67  nop
0x180012f68  jmp     loc_180012C50
0x180012f6d  mov     rcx, [rbp+57h+ppvObject]
0x180012f71  test    rcx, rcx
0x180012f74  jz      short loc_180012F87
0x180012f76  mov     [rbp+57h+ppvObject], r12
0x180012f7a  mov     rax, [rcx]
0x180012f7d  mov     rax, [rax+10h]
0x180012f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f86  nop
0x180012f87  mov     rcx, [rbp+57h+var_B8]
0x180012f8b  test    rcx, rcx
0x180012f8e  jz      short loc_180012FA1
0x180012f90  mov     [rbp+57h+var_B8], r12
0x180012f94  mov     rax, [rcx]
0x180012f97  mov     rax, [rax+10h]
0x180012f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fa0  nop
0x180012fa1  xor     eax, eax
0x180012fa3  mov     rcx, [rbp+57h+var_40]
0x180012fa7  xor     rcx, rsp; StackCookie
0x180012faa  call    __security_check_cookie
0x180012faf  add     rsp, 0C0h
0x180012fb6  pop     r15
0x180012fb8  pop     r14
0x180012fba  pop     r12
0x180012fbc  pop     rdi
0x180012fbd  pop     rsi
0x180012fbe  pop     rbx
0x180012fbf  pop     rbp
0x180012fc0  retn
```
