# FTP_SITE_MANAGER::GetCustomProviderConfiguration(IAppHostElementCollection *,ushort * const,ATTRIBUTE_SAFEARRAY * *)

- ea: `0x18000b888`
- end: `0x18000bda4`
- name: `?GetCustomProviderConfiguration@FTP_SITE_MANAGER@@CAJPEAUIAppHostElementCollection@@QEAGPEAPEAVATTRIBUTE_SAFEARRAY@@@Z`
- size: `1308`
- prototype: `__int64 __fastcall(struct IAppHostElementCollection *, unsigned __int16 *const, struct ATTRIBUTE_SAFEARRAY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18000d8e0`

## callees

- `0x180001210`
- `0x180001250`
- `0x18000b0bc`
- `0x18000b888`
- `0x18002b5bc`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b9b2`
- `msvcrt!_wcsicmp` at `0x18000bbbb`
- `msvcrt!_wcsicmp` at `0x18000b9b2`
- `msvcrt!_wcsicmp` at `0x18000bbbb`
- `KERNEL32!GetUserDefaultLCID` at `0x18000ba94`
- `KERNEL32!GetUserDefaultLCID` at `0x18000ba94`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd0f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd3d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd0f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd26`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd3d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b996`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b9a1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bba1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bc09`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b996`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b9a1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bba1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bc09`
- `OLEAUT32!__imp_VariantInit` at `0x18000b8d6`
- `OLEAUT32!__imp_VariantInit` at `0x18000b8d6`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd4f`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd4f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000bb17`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000bb17`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000bc97`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000bc97`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x18000badd`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x18000badd`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x18000bac3`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x18000bac3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_SITE_MANAGER::GetCustomProviderConfiguration(
        struct IAppHostElementCollection *a1,
        unsigned __int16 *const a2,
        struct ATTRIBUTE_SAFEARRAY **a3)
{
  struct IAppHostElementCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_Count)(IAppHostElementCollection *, DWORD *); // rax
  int RecordInfoFromGuids; // edi
  ATTRIBUTE_SAFEARRAY *v9; // rsi
  unsigned int v10; // r14d
  struct IAppHostElementCollectionVtbl *v11; // rax
  HRESULT (__stdcall *get_Item)(IAppHostElementCollection *, VARIANT, IAppHostElement **); // rax
  UINT v13; // ebx
  _QWORD *v14; // rax
  ULONG v15; // ebx
  LCID UserDefaultLCID; // eax
  SAFEARRAY *Vector; // rax
  ATTRIBUTE_SAFEARRAY *v18; // rbx
  unsigned int v19; // r14d
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64 *, VARIANTARG *, struct IAppHostElement **); // rax
  __int64 v22; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-49h] BYREF
  struct IAppHostElement *v25; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-39h] BYREF
  BSTR v27; // [rsp+48h] [rbp-31h] BYREF
  PVOID pvExtra; // [rsp+50h] [rbp-29h] BYREF
  void *ppvData; // [rsp+58h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG v31[3]; // [rsp+80h] [rbp+7h] BYREF
  ULONG cElements; // [rsp+E0h] [rbp+67h] BYREF
  BSTR pbstr; // [rsp+F0h] [rbp+77h] BYREF
  struct IAppHostElement *v34; // [rsp+F8h] [rbp+7Fh] BYREF

  v25 = 0;
  v26 = 0;
  v34 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  pbstr = 0;
  v27 = 0;
  bstrString = 0;
  get_Count = lpVtbl->get_Count;
  cElements = 0;
  ppvData = 0;
  RecordInfoFromGuids = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, ULONG *))get_Count)(a1, &cElements);
  if ( RecordInfoFromGuids < 0 )
    goto LABEL_38;
  v9 = 0;
  v10 = 0;
  if ( !cElements )
  {
LABEL_10:
    if ( v25 )
    {
      RecordInfoFromGuids = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 **))v25->lpVtbl->get_Collection)(
                              v25,
                              &v26);
      if ( RecordInfoFromGuids < 0 )
        goto LABEL_38;
      RecordInfoFromGuids = (*(__int64 (__fastcall **)(__int64 *, ULONG *))(*v26 + 24))(v26, &cElements);
      if ( RecordInfoFromGuids < 0 )
        goto LABEL_38;
      if ( !cElements )
      {
        RecordInfoFromGuids = 1;
        goto LABEL_38;
      }
      v14 = operator new(0x10u);
      pvExtra = v14;
      v9 = (ATTRIBUTE_SAFEARRAY *)v14;
      if ( !v14 )
      {
        RecordInfoFromGuids = -2147024882;
        goto LABEL_38;
      }
      *v14 = 1;
      v14[1] = 0;
      v15 = cElements;
      pvExtra = 0;
      UserDefaultLCID = GetUserDefaultLCID();
      RecordInfoFromGuids = GetRecordInfoFromGuids(
                              &GUID_a8ac6f3f_3165_41af_9911_511d0772708e,
                              1u,
                              0,
                              UserDefaultLCID,
                              &GUID_9e04226f_e38c_419e_a448_62de3b3a8f43,
                              (IRecordInfo **)&pvExtra);
      if ( RecordInfoFromGuids >= 0 )
      {
        Vector = SafeArrayCreateVectorEx(0x24u, 0, v15, pvExtra);
        *((_QWORD *)v9 + 1) = Vector;
        if ( !Vector )
          RecordInfoFromGuids = -2147024882;
      }
      if ( pvExtra )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)pvExtra + 16LL))(pvExtra);
      if ( RecordInfoFromGuids < 0 )
      {
        v18 = v9;
      }
      else
      {
        RecordInfoFromGuids = SafeArrayAccessData(*((SAFEARRAY **)v9 + 1), &ppvData);
        v18 = v9;
        if ( RecordInfoFromGuids >= 0 )
        {
          *((_DWORD *)v9 + 1) = 1;
          v19 = 0;
          if ( cElements )
          {
            do
            {
              pvarg.lVal = v19;
              pvarg.vt = 19;
              v20 = *v26;
              v31[0].pRecInfo = pvarg.pRecInfo;
              v21 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IAppHostElement **))(v20 + 32);
              *(_OWORD *)&v31[0].vt = *(_OWORD *)&pvarg.vt;
              RecordInfoFromGuids = v21(v26, v31, &v34);
              if ( RecordInfoFromGuids < 0 )
                goto LABEL_52;
              RecordInfoFromGuids = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR *))v34->lpVtbl->get_Name)(
                                      v34,
                                      &pbstr);
              if ( RecordInfoFromGuids < 0 )
                goto LABEL_52;
              if ( SysStringLen(pbstr) != 3 || _wcsicmp(L"add", pbstr) )
              {
                SysFreeString(pbstr);
                pbstr = 0;
                ((void (__fastcall *)(struct IAppHostElement *))v34->lpVtbl->Release)(v34);
                v34 = 0;
              }
              else
              {
                RecordInfoFromGuids = Config_GetStringProperty(v34, L"key", &v27);
                if ( RecordInfoFromGuids < 0 )
                  goto LABEL_52;
                RecordInfoFromGuids = Config_GetStringProperty(v34, L"value", &bstrString);
                if ( RecordInfoFromGuids < 0 )
                  goto LABEL_52;
                if ( !SysStringLen(bstrString) )
                {
                  SysFreeString(bstrString);
                  RecordInfoFromGuids = Config_GetStringProperty(v34, L"encryptedValue", &bstrString);
                  if ( RecordInfoFromGuids < 0 )
                    goto LABEL_52;
                }
                v22 = 2LL * v19;
                *((_QWORD *)ppvData + v22) = v27;
                v27 = 0;
                *((_QWORD *)ppvData + v22 + 1) = bstrString;
                bstrString = 0;
              }
            }
            while ( ++v19 < cElements );
          }
          RecordInfoFromGuids = SafeArrayUnaccessData(*((SAFEARRAY **)v9 + 1));
          if ( RecordInfoFromGuids >= 0 )
          {
            *((_DWORD *)v9 + 1) = 0;
            goto LABEL_37;
          }
        }
      }
LABEL_52:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18, 0xFFFFFFFF) == 1 )
      {
        ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY(v18);
        operator delete(v18);
      }
      goto LABEL_38;
    }
LABEL_37:
    *a3 = v9;
    goto LABEL_38;
  }
  while ( 1 )
  {
    pvarg.vt = 19;
    v11 = a1->lpVtbl;
    pvarg.lVal = v10;
    get_Item = v11->get_Item;
    v31[0] = pvarg;
    RecordInfoFromGuids = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, VARIANTARG *, struct IAppHostElement **))get_Item)(
                            a1,
                            v31,
                            &v25);
    if ( RecordInfoFromGuids < 0 )
      break;
    RecordInfoFromGuids = Config_GetStringProperty(v25, L"name", &pbstr);
    if ( RecordInfoFromGuids < 0 )
      break;
    v13 = SysStringLen(pbstr);
    if ( v13 == SysStringLen(a2) && !_wcsicmp(pbstr, a2) )
    {
      SysFreeString(pbstr);
      pbstr = 0;
      goto LABEL_10;
    }
    SysFreeString(pbstr);
    pbstr = 0;
    ((void (__fastcall *)(struct IAppHostElement *))v25->lpVtbl->Release)(v25);
    ++v10;
    v25 = 0;
    if ( v10 >= cElements )
      goto LABEL_37;
  }
LABEL_38:
  if ( v34 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    v26 = 0;
  }
  if ( v25 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v27 )
  {
    SysFreeString(v27);
    v27 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( pbstr )
  {
    SysFreeString(pbstr);
    pbstr = 0;
  }
  VariantClear(&pvarg);
  return (unsigned int)RecordInfoFromGuids;
}

```

## disassembly

```asm
0x18000b888  mov     [rsp-8+arg_8], rbx
0x18000b88d  push    rbp
0x18000b88e  push    rsi
0x18000b88f  push    rdi
0x18000b890  push    r12
0x18000b892  push    r13
0x18000b894  push    r14
0x18000b896  push    r15
0x18000b898  lea     rbp, [rsp-27h]
0x18000b89d  sub     rsp, 0A0h
0x18000b8a4  mov     r15, rcx
0x18000b8a7  mov     [rbp+57h+var_98], 0
0x18000b8af  xorps   xmm0, xmm0
0x18000b8b2  mov     [rbp+57h+var_90], 0
0x18000b8ba  xor     eax, eax
0x18000b8bc  mov     [rbp+57h+arg_18], 0
0x18000b8c4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000b8c8  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000b8cc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000b8d0  mov     r13, r8
0x18000b8d3  mov     r12, rdx
0x18000b8d6  call    cs:__imp_VariantInit
0x18000b8dc  mov     qword ptr [r13+0], 0
0x18000b8e4  lea     rdx, [rbp+57h+cElements]
0x18000b8e8  mov     rax, [r15]
0x18000b8eb  mov     rcx, r15
0x18000b8ee  mov     [rbp+57h+pbstr], 0
0x18000b8f6  mov     [rbp+57h+var_88], 0
0x18000b8fe  mov     [rbp+57h+bstrString], 0
0x18000b906  mov     rax, [rax+18h]
0x18000b90a  mov     [rbp+57h+cElements], 0
0x18000b911  mov     [rbp+57h+ppvData], 0
0x18000b919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91e  mov     edi, eax
0x18000b920  test    eax, eax
0x18000b922  js      loc_18000BCAF
0x18000b928  xor     esi, esi
0x18000b92a  xor     r14d, r14d
0x18000b92d  lea     eax, [rsi+13h]
0x18000b930  cmp     [rbp+57h+cElements], esi
0x18000b933  jbe     loc_18000BA03
0x18000b939  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000b93e  lea     r8, [rbp+57h+var_98]
0x18000b942  mov     word ptr [rbp+57h+pvarg], ax
0x18000b946  lea     rdx, [rbp+57h+var_50]
0x18000b94a  mov     rax, [r15]
0x18000b94d  mov     rcx, r15
0x18000b950  mov     dword ptr [rbp+57h+pvarg+8], r14d
0x18000b954  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000b958  mov     rax, [rax+20h]
0x18000b95c  movaps  [rbp+57h+var_50], xmm0
0x18000b960  movsd   [rbp+57h+var_40], xmm1
0x18000b965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b96a  mov     edi, eax
0x18000b96c  test    eax, eax
0x18000b96e  js      loc_18000BCAF
0x18000b974  mov     rcx, [rbp+57h+var_98]; struct IAppHostElement *
0x18000b978  lea     r8, [rbp+57h+pbstr]; unsigned __int16 **
0x18000b97c  lea     rdx, aName; "name"
0x18000b983  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000b988  mov     edi, eax
0x18000b98a  test    eax, eax
0x18000b98c  js      loc_18000BCAF
0x18000b992  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18000b996  call    cs:__imp_SysStringLen
0x18000b99c  mov     rcx, r12; pbstr
0x18000b99f  mov     ebx, eax
0x18000b9a1  call    cs:__imp_SysStringLen
0x18000b9a7  cmp     ebx, eax
0x18000b9a9  jnz     short loc_18000B9BC
0x18000b9ab  mov     rcx, [rbp+57h+pbstr]; String1
0x18000b9af  mov     rdx, r12; String2
0x18000b9b2  call    cs:__imp__wcsicmp
0x18000b9b8  test    eax, eax
0x18000b9ba  jz      short loc_18000B9F5
0x18000b9bc  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000b9c0  call    cs:__imp_SysFreeString
0x18000b9c6  mov     rcx, [rbp+57h+var_98]
0x18000b9ca  mov     [rbp+57h+pbstr], rsi
0x18000b9ce  mov     rax, [rcx]
0x18000b9d1  mov     rax, [rax+10h]
0x18000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9da  inc     r14d
0x18000b9dd  mov     [rbp+57h+var_98], rsi
0x18000b9e1  cmp     r14d, [rbp+57h+cElements]
0x18000b9e5  jnb     loc_18000BCAB
0x18000b9eb  mov     eax, 13h
0x18000b9f0  jmp     loc_18000B939
0x18000b9f5  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000b9f9  call    cs:__imp_SysFreeString
0x18000b9ff  mov     [rbp+57h+pbstr], rsi
0x18000ba03  mov     rcx, [rbp+57h+var_98]
0x18000ba07  test    rcx, rcx
0x18000ba0a  jz      loc_18000BCAB
0x18000ba10  mov     rax, [rcx]
0x18000ba13  lea     rdx, [rbp+57h+var_90]
0x18000ba17  mov     rax, [rax+20h]
0x18000ba1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba20  mov     edi, eax
0x18000ba22  test    eax, eax
0x18000ba24  js      loc_18000BCAF
0x18000ba2a  mov     rcx, [rbp+57h+var_90]
0x18000ba2e  lea     rdx, [rbp+57h+cElements]
0x18000ba32  mov     rax, [rcx]
0x18000ba35  mov     rax, [rax+18h]
0x18000ba39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3e  mov     edi, eax
0x18000ba40  test    eax, eax
0x18000ba42  js      loc_18000BCAF
0x18000ba48  cmp     [rbp+57h+cElements], esi
0x18000ba4b  jnz     short loc_18000BA57
0x18000ba4d  mov     edi, 1
0x18000ba52  jmp     loc_18000BCAF
0x18000ba57  mov     ecx, 10h; Size
0x18000ba5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba61  mov     [rbp+57h+pvExtra], rax
0x18000ba65  mov     rsi, rax
0x18000ba68  test    rax, rax
0x18000ba6b  jz      loc_18000BD9A
0x18000ba71  mov     qword ptr [rax], 1
0x18000ba78  mov     qword ptr [rax+8], 0
0x18000ba80  test    rax, rax
0x18000ba83  jz      loc_18000BD9A
0x18000ba89  mov     ebx, [rbp+57h+cElements]
0x18000ba8c  mov     [rbp+57h+pvExtra], 0
0x18000ba94  call    cs:__imp_GetUserDefaultLCID
0x18000ba9a  xor     r8d, r8d; uVerMinor
0x18000ba9d  lea     rcx, _GUID_a8ac6f3f_3165_41af_9911_511d0772708e; rGuidTypeLib
0x18000baa4  mov     r9d, eax; lcid
0x18000baa7  lea     rax, [rbp+57h+pvExtra]
0x18000baab  mov     [rsp+0D0h+ppRecInfo], rax; ppRecInfo
0x18000bab0  lea     rax, _GUID_9e04226f_e38c_419e_a448_62de3b3a8f43
0x18000bab7  mov     [rsp+0D0h+rGuidTypeInfo], rax; rGuidTypeInfo
0x18000babc  lea     r12d, [r8+1]
0x18000bac0  mov     edx, r12d; uVerMajor
0x18000bac3  call    cs:__imp_GetRecordInfoFromGuids
0x18000bac9  mov     edi, eax
0x18000bacb  test    eax, eax
0x18000bacd  js      short loc_18000BAF2
0x18000bacf  mov     r9, [rbp+57h+pvExtra]; pvExtra
0x18000bad3  lea     ecx, [r12+23h]; vt
0x18000bad8  mov     r8d, ebx; cElements
0x18000badb  xor     edx, edx; lLbound
0x18000badd  call    cs:__imp_SafeArrayCreateVectorEx
0x18000bae3  test    rax, rax
0x18000bae6  mov     [rsi+8], rax
0x18000baea  mov     ecx, 8007000Eh
0x18000baef  cmovz   edi, ecx
0x18000baf2  mov     rcx, [rbp+57h+pvExtra]
0x18000baf6  test    rcx, rcx
0x18000baf9  jz      short loc_18000BB07
0x18000bafb  mov     rax, [rcx]
0x18000bafe  mov     rax, [rax+10h]
0x18000bb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb07  test    edi, edi
0x18000bb09  js      loc_18000BD72
0x18000bb0f  mov     rcx, [rsi+8]; psa
0x18000bb13  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18000bb17  call    cs:__imp_SafeArrayAccessData
0x18000bb1d  mov     edi, eax
0x18000bb1f  mov     rbx, rsi
0x18000bb22  test    eax, eax
0x18000bb24  js      loc_18000BD75
0x18000bb2a  mov     [rsi+4], r12d
0x18000bb2e  xor     r14d, r14d
0x18000bb31  xor     r15d, r15d
0x18000bb34  cmp     [rbp+57h+cElements], r15d
0x18000bb38  jbe     loc_18000BC93
0x18000bb3e  mov     rcx, [rbp+57h+var_90]
0x18000bb42  lea     r8, [rbp+57h+arg_18]
0x18000bb46  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000bb4b  lea     rdx, [rbp+57h+var_50]
0x18000bb4f  mov     dword ptr [rbp+57h+pvarg+8], r14d
0x18000bb53  mov     eax, 13h
0x18000bb58  mov     word ptr [rbp+57h+pvarg], ax
0x18000bb5c  mov     rax, [rcx]
0x18000bb5f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000bb63  movsd   [rbp+57h+var_40], xmm1
0x18000bb68  mov     rax, [rax+20h]
0x18000bb6c  movaps  [rbp+57h+var_50], xmm0
0x18000bb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb75  mov     edi, eax
0x18000bb77  test    eax, eax
0x18000bb79  js      loc_18000BD75
0x18000bb7f  mov     rcx, [rbp+57h+arg_18]
0x18000bb83  lea     rdx, [rbp+57h+pbstr]
0x18000bb87  mov     rax, [rcx]
0x18000bb8a  mov     rax, [rax+18h]
0x18000bb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb93  mov     edi, eax
0x18000bb95  test    eax, eax
0x18000bb97  js      loc_18000BD75
0x18000bb9d  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18000bba1  call    cs:__imp_SysStringLen
0x18000bba7  cmp     eax, 3
0x18000bbaa  jnz     loc_18000BC64
0x18000bbb0  mov     rdx, [rbp+57h+pbstr]; String2
0x18000bbb4  lea     rcx, aAdd; "add"
0x18000bbbb  call    cs:__imp__wcsicmp
0x18000bbc1  test    eax, eax
0x18000bbc3  jnz     loc_18000BC64
0x18000bbc9  mov     rcx, [rbp+57h+arg_18]; struct IAppHostElement *
0x18000bbcd  lea     r8, [rbp+57h+var_88]; unsigned __int16 **
0x18000bbd1  lea     rdx, aKey; "key"
0x18000bbd8  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000bbdd  mov     edi, eax
0x18000bbdf  test    eax, eax
0x18000bbe1  js      loc_18000BD75
0x18000bbe7  mov     rcx, [rbp+57h+arg_18]; struct IAppHostElement *
0x18000bbeb  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000bbef  lea     rdx, aValue; "value"
0x18000bbf6  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000bbfb  mov     edi, eax
0x18000bbfd  test    eax, eax
0x18000bbff  js      loc_18000BD75
0x18000bc05  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18000bc09  call    cs:__imp_SysStringLen
0x18000bc0f  test    eax, eax
0x18000bc11  jnz     short loc_18000BC3B
0x18000bc13  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000bc17  call    cs:__imp_SysFreeString
0x18000bc1d  mov     rcx, [rbp+57h+arg_18]; struct IAppHostElement *
0x18000bc21  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000bc25  lea     rdx, aEncryptedvalue; "encryptedValue"
0x18000bc2c  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000bc31  mov     edi, eax
0x18000bc33  test    eax, eax
0x18000bc35  js      loc_18000BD75
0x18000bc3b  mov     rcx, [rbp+57h+var_88]
0x18000bc3f  mov     rax, [rbp+57h+ppvData]
0x18000bc43  mov     edx, r14d
0x18000bc46  add     rdx, rdx
0x18000bc49  mov     [rax+rdx*8], rcx
0x18000bc4d  mov     rcx, [rbp+57h+bstrString]
0x18000bc51  mov     rax, [rbp+57h+ppvData]
0x18000bc55  mov     [rbp+57h+var_88], r15
0x18000bc59  mov     [rax+rdx*8+8], rcx
0x18000bc5e  mov     [rbp+57h+bstrString], r15
0x18000bc62  jmp     short loc_18000BC86
0x18000bc64  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000bc68  call    cs:__imp_SysFreeString
0x18000bc6e  mov     rcx, [rbp+57h+arg_18]
0x18000bc72  mov     [rbp+57h+pbstr], r15
0x18000bc76  mov     rax, [rcx]
0x18000bc79  mov     rax, [rax+10h]
0x18000bc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc82  mov     [rbp+57h+arg_18], r15
0x18000bc86  add     r14d, r12d
0x18000bc89  cmp     r14d, [rbp+57h+cElements]
0x18000bc8d  jb      loc_18000BB3E
0x18000bc93  mov     rcx, [rsi+8]; psa
0x18000bc97  call    cs:__imp_SafeArrayUnaccessData
0x18000bc9d  mov     edi, eax
0x18000bc9f  test    eax, eax
0x18000bca1  js      loc_18000BD75
0x18000bca7  mov     [rsi+4], r15d
0x18000bcab  mov     [r13+0], rsi
0x18000bcaf  mov     rcx, [rbp+57h+arg_18]
0x18000bcb3  test    rcx, rcx
0x18000bcb6  jz      short loc_18000BCCC
0x18000bcb8  mov     rax, [rcx]
0x18000bcbb  mov     rax, [rax+10h]
0x18000bcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc4  mov     [rbp+57h+arg_18], 0
0x18000bccc  mov     rcx, [rbp+57h+var_90]
0x18000bcd0  test    rcx, rcx
0x18000bcd3  jz      short loc_18000BCE9
0x18000bcd5  mov     rax, [rcx]
0x18000bcd8  mov     rax, [rax+10h]
0x18000bcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bce1  mov     [rbp+57h+var_90], 0
0x18000bce9  mov     rcx, [rbp+57h+var_98]
0x18000bced  test    rcx, rcx
0x18000bcf0  jz      short loc_18000BD06
0x18000bcf2  mov     rax, [rcx]
0x18000bcf5  mov     rax, [rax+10h]
0x18000bcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcfe  mov     [rbp+57h+var_98], 0
0x18000bd06  mov     rcx, [rbp+57h+var_88]; bstrString
0x18000bd0a  test    rcx, rcx
0x18000bd0d  jz      short loc_18000BD1D
0x18000bd0f  call    cs:__imp_SysFreeString
0x18000bd15  mov     [rbp+57h+var_88], 0
0x18000bd1d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000bd21  test    rcx, rcx
0x18000bd24  jz      short loc_18000BD34
0x18000bd26  call    cs:__imp_SysFreeString
0x18000bd2c  mov     [rbp+57h+bstrString], 0
0x18000bd34  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000bd38  test    rcx, rcx
0x18000bd3b  jz      short loc_18000BD4B
0x18000bd3d  call    cs:__imp_SysFreeString
0x18000bd43  mov     [rbp+57h+pbstr], 0
0x18000bd4b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000bd4f  call    cs:__imp_VariantClear
0x18000bd55  mov     rbx, [rsp+0D0h+arg_8]
0x18000bd5d  mov     eax, edi
0x18000bd5f  add     rsp, 0A0h
0x18000bd66  pop     r15
0x18000bd68  pop     r14
  ... truncated ...
```
