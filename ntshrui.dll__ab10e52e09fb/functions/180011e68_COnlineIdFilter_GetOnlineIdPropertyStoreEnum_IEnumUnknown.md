# COnlineIdFilter::_GetOnlineIdPropertyStoreEnum(IEnumUnknown * *)

- ea: `0x180011e68`
- end: `0x1800120d7`
- name: `?_GetOnlineIdPropertyStoreEnum@COnlineIdFilter@@AEAAJPEAPEAUIEnumUnknown@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(COnlineIdFilter *__hidden this, struct IEnumUnknown **)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060170`
- `0x18006021c`
- `0x180060314`

## callees

- `0x18000f720`
- `0x180011e3c`
- `0x180011e68`
- `0x1800120e0`
- `0x180017410`
- `0x180021870`
- `0x18002299c`
- `0x180022c18`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011fd6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012017`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f8a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f8a`
- `PROPSYS!PropVariantToStringAlloc` at `0x180011f77`
- `PROPSYS!PropVariantToStringAlloc` at `0x180011f77`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COnlineIdFilter::_GetOnlineIdPropertyStoreEnum(COnlineIdFilter *this, struct IEnumUnknown **a2)
{
  HRESULT appended; // edi
  int v5; // eax
  HDPA v6; // rbx
  const struct _GUID *v7; // rdx
  const WCHAR *v8; // rsi
  int i; // r14d
  int v10; // eax
  const WCHAR *Ptr; // rax
  void *v12; // rcx
  struct IEnumUnknown *v13; // rcx
  PWSTR ppszOut; // [rsp+30h] [rbp-50h] BYREF
  struct IEnumUnknown *v16; // [rsp+38h] [rbp-48h] BYREF
  void *v17; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT propvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h]
  __int128 v20; // [rsp+60h] [rbp-20h] BYREF
  __int64 v21; // [rsp+70h] [rbp-10h]
  void *v22; // [rsp+C0h] [rbp+40h] BYREF
  HDPA hdpa; // [rsp+C8h] [rbp+48h] BYREF

  v17 = 0;
  appended = CEnumerableObjectCollection::CreateInstance((int)this, (const struct _GUID *)a2, &v17);
  if ( appended >= 0 )
  {
    v22 = 0;
    v20 = 0;
    v21 = 0;
    hdpa = 0;
    LOWORD(v20) = 31;
    v5 = CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(&hdpa, 5);
    v6 = hdpa;
    if ( v5 )
    {
      v16 = 0;
      *((_QWORD *)&v20 + 1) = L"Connected";
      appended = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const PROPERTYKEY *, __int128 *, struct IEnumUnknown **))(**((_QWORD **)this + 2) + 56LL))(
                   *((_QWORD *)this + 2),
                   0,
                   &PKEY_Keywords,
                   &v20,
                   &v16);
      if ( appended >= 0 )
      {
        do
        {
          if ( (int)SHNextObjectFromEnumUnknown(v16, v7, &v22) < 0 )
            break;
          ppszOut = 0;
          *(_OWORD *)propvar = 0;
          v19 = 0;
          appended = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 40LL))(
                       v22,
                       &PKEY_Identity_UserName,
                       propvar);
          if ( appended >= 0 )
          {
            if ( LOWORD(propvar[0]) )
              appended = PropVariantToStringAlloc(propvar, &ppszOut);
            else
              appended = -2147023728;
            PropVariantClear(propvar);
          }
          if ( appended >= 0 )
          {
            v8 = ppszOut;
            if ( ppszOut )
            {
              appended = 0;
              for ( i = 0; ; ++i )
              {
                v10 = v6 ? *(_DWORD *)v6 : 0;
                if ( i >= v10 )
                  break;
                Ptr = (const WCHAR *)DPA_GetPtr(v6, i);
                if ( CompareStringOrdinal(v8, -1, Ptr, -1, 1) == 2 )
                  goto LABEL_21;
              }
              appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(&hdpa, v8);
              if ( appended >= 0 )
              {
                appended = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)v17 + 40LL))(v17, v22);
                goto LABEL_22;
              }
LABEL_21:
              CoTaskMemFree(ppszOut);
            }
          }
LABEL_22:
          v12 = v22;
          v22 = 0;
          if ( v12 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        while ( appended >= 0 );
        v13 = v16;
        v16 = 0;
        if ( v13 )
          ((void (__fastcall *)(struct IEnumUnknown *))v13->lpVtbl->Release)(v13);
      }
    }
    else
    {
      appended = -2147024882;
    }
    if ( v6 )
    {
      DPA_DestroyCallback(v6, DPA_CoTaskMemFreeCB<unsigned short>, 0);
      hdpa = 0;
    }
    if ( appended >= 0 )
    {
      appended = (**(__int64 (__fastcall ***)(void *, GUID *, struct IEnumUnknown **))v17)(
                   v17,
                   &GUID_00000100_0000_0000_c000_000000000046,
                   a2);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    CDPA_Base<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM,CTContainer_PolicyUnOwned<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM>>::~CDPA_Base<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM,CTContainer_PolicyUnOwned<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM>>(&hdpa);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180011e68  mov     [rsp-28h+arg_0], rbx
0x180011e6d  push    rbp
0x180011e6e  push    rsi
0x180011e6f  push    rdi
0x180011e70  push    r14
0x180011e72  push    r15
0x180011e74  mov     rbp, rsp
0x180011e77  sub     rsp, 80h
0x180011e7e  mov     r15, rdx
0x180011e81  mov     rsi, rcx
0x180011e84  mov     [rbp+var_40], 0
0x180011e8c  lea     r8, [rbp+var_40]; void **
0x180011e90  call    ?CreateInstance@CEnumerableObjectCollection@@SAJHAEBU_GUID@@PEAPEAX@Z; CEnumerableObjectCollection::CreateInstance(int,_GUID const &,void * *)
0x180011e95  mov     edi, eax
0x180011e97  test    eax, eax
0x180011e99  js      loc_1800120BE
0x180011e9f  mov     [rbp+arg_10], 0
0x180011ea7  xorps   xmm0, xmm0
0x180011eaa  xor     eax, eax
0x180011eac  movups  [rbp+var_20], xmm0
0x180011eb0  mov     [rbp+var_10], rax
0x180011eb4  mov     [rbp+hdpa], rax
0x180011eb8  mov     eax, 1Fh
0x180011ebd  mov     word ptr [rbp+var_20], ax
0x180011ec1  lea     edx, [rax-1Ah]
0x180011ec4  lea     rcx, [rbp+hdpa]
0x180011ec8  call    ?Create@?$CDPA_Base@UIUnknown@@V?$CTContainer_PolicyRelease@UIUnknown@@@@@@QEAAHH@Z; CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(int)
0x180011ecd  mov     rbx, [rbp+hdpa]
0x180011ed1  test    eax, eax
0x180011ed3  jz      loc_180012061
0x180011ed9  mov     [rbp+var_48], 0
0x180011ee1  lea     rax, aConnected; "Connected"
0x180011ee8  mov     qword ptr [rbp+var_20+8], rax
0x180011eec  mov     rcx, [rsi+10h]
0x180011ef0  mov     rax, [rcx]
0x180011ef3  lea     rdx, [rbp+var_48]
0x180011ef7  mov     qword ptr [rsp+80h+bIgnoreCase], rdx
0x180011efc  lea     r9, [rbp+var_20]
0x180011f00  lea     r8, PKEY_Keywords
0x180011f07  xor     edx, edx
0x180011f09  mov     rax, [rax+38h]
0x180011f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f12  mov     edi, eax
0x180011f14  test    eax, eax
0x180011f16  js      loc_180012066
0x180011f1c  lea     r8, [rbp+arg_10]; void **
0x180011f20  mov     rcx, [rbp+var_48]; struct IEnumUnknown *
0x180011f24  call    ?SHNextObjectFromEnumUnknown@@YAJPEAUIEnumUnknown@@AEBU_GUID@@PEAPEAX@Z; SHNextObjectFromEnumUnknown(IEnumUnknown *,_GUID const &,void * *)
0x180011f29  test    eax, eax
0x180011f2b  js      loc_180012042
0x180011f31  mov     rcx, [rbp+arg_10]
0x180011f35  mov     [rbp+ppszOut], 0
0x180011f3d  xorps   xmm0, xmm0
0x180011f40  xor     eax, eax
0x180011f42  movups  xmmword ptr [rbp+propvar], xmm0
0x180011f46  mov     [rbp+var_28], rax
0x180011f4a  mov     rax, [rcx]
0x180011f4d  lea     r8, [rbp+propvar]
0x180011f51  lea     rdx, PKEY_Identity_UserName
0x180011f58  mov     rax, [rax+28h]
0x180011f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f61  mov     edi, eax
0x180011f63  test    eax, eax
0x180011f65  js      short loc_180011F90
0x180011f67  xor     eax, eax
0x180011f69  cmp     ax, word ptr [rbp+propvar]
0x180011f6d  jz      short loc_180011F81
0x180011f6f  lea     rdx, [rbp+ppszOut]; ppszOut
0x180011f73  lea     rcx, [rbp+propvar]; propvar
0x180011f77  call    cs:__imp_PropVariantToStringAlloc
0x180011f7d  mov     edi, eax
0x180011f7f  jmp     short loc_180011F86
0x180011f81  mov     edi, 80070490h
0x180011f86  lea     rcx, [rbp+propvar]; pvar
0x180011f8a  call    cs:__imp_PropVariantClear
0x180011f90  test    edi, edi
0x180011f92  js      loc_18001201D
0x180011f98  mov     rsi, [rbp+ppszOut]
0x180011f9c  test    rsi, rsi
0x180011f9f  jz      short loc_18001201D
0x180011fa1  xor     edi, edi
0x180011fa3  xor     r14d, r14d
0x180011fa6  test    rbx, rbx
0x180011fa9  jz      short loc_180011FAF
0x180011fab  mov     eax, [rbx]
0x180011fad  jmp     short loc_180011FB1
0x180011faf  xor     eax, eax
0x180011fb1  cmp     r14d, eax
0x180011fb4  jge     short loc_180011FE6
0x180011fb6  movsxd  rdx, r14d; i
0x180011fb9  mov     rcx, rbx; hdpa
0x180011fbc  call    DPA_GetPtr
0x180011fc1  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x180011fc9  or      r9d, 0FFFFFFFFh; cchCount2
0x180011fcd  mov     r8, rax; lpString2
0x180011fd0  or      edx, r9d; cchCount1
0x180011fd3  mov     rcx, rsi; lpString1
0x180011fd6  call    cs:__imp_CompareStringOrdinal
0x180011fdc  cmp     eax, 2
0x180011fdf  jz      short loc_180012010
0x180011fe1  inc     r14d
0x180011fe4  jmp     short loc_180011FA6
0x180011fe6  mov     rdx, rsi
0x180011fe9  lea     rcx, [rbp+hdpa]
0x180011fed  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x180011ff2  mov     edi, eax
0x180011ff4  test    eax, eax
0x180011ff6  js      short loc_180012010
0x180011ff8  mov     rcx, [rbp+var_40]
0x180011ffc  mov     rax, [rcx]
0x180011fff  mov     rdx, [rbp+arg_10]
0x180012003  mov     rax, [rax+28h]
0x180012007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001200c  mov     edi, eax
0x18001200e  jmp     short loc_18001201D
0x180012010  mov     rsi, [rbp+ppszOut]
0x180012014  mov     rcx, rsi; pv
0x180012017  call    cs:__imp_CoTaskMemFree
0x18001201d  mov     rcx, [rbp+arg_10]
0x180012021  mov     [rbp+arg_10], 0
0x180012029  test    rcx, rcx
0x18001202c  jz      short loc_18001203A
0x18001202e  mov     rax, [rcx]
0x180012031  mov     rax, [rax+10h]
0x180012035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001203a  test    edi, edi
0x18001203c  jns     loc_180011F1C
0x180012042  mov     rcx, [rbp+var_48]
0x180012046  mov     [rbp+var_48], 0
0x18001204e  test    rcx, rcx
0x180012051  jz      short loc_180012066
0x180012053  mov     rax, [rcx]
0x180012056  mov     rax, [rax+10h]
0x18001205a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001205f  jmp     short loc_180012066
0x180012061  mov     edi, 8007000Eh
0x180012066  test    rbx, rbx
0x180012069  jz      short loc_180012085
0x18001206b  xor     r8d, r8d; pData
0x18001206e  lea     rdx, ??$DPA_CoTaskMemFreeCB@G@@YAHPEAGPEAX@Z; pfnCB
0x180012075  mov     rcx, rbx; hdpa
0x180012078  call    DPA_DestroyCallback
0x18001207d  mov     [rbp+hdpa], 0
0x180012085  test    edi, edi
0x180012087  js      short loc_1800120B5
0x180012089  mov     rcx, [rbp+var_40]
0x18001208d  mov     rax, [rcx]
0x180012090  mov     r8, r15
0x180012093  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x18001209a  mov     rax, [rax]
0x18001209d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a2  mov     edi, eax
0x1800120a4  mov     rcx, [rbp+var_40]
0x1800120a8  mov     rax, [rcx]
0x1800120ab  mov     rax, [rax+10h]
0x1800120af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120b4  nop
0x1800120b5  lea     rcx, [rbp+hdpa]
0x1800120b9  call    ??1?$CDPA_Base@USHARINGENGINE_SHAREABLE_ITEM@CShareEngine@@V?$CTContainer_PolicyUnOwned@USHARINGENGINE_SHAREABLE_ITEM@CShareEngine@@@@@@QEAA@XZ; CDPA_Base<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM,CTContainer_PolicyUnOwned<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM>>::~CDPA_Base<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM,CTContainer_PolicyUnOwned<CShareEngine::SHARINGENGINE_SHAREABLE_ITEM>>(void)
0x1800120be  mov     eax, edi
0x1800120c0  mov     rbx, [rsp+80h+arg_0]
0x1800120c8  add     rsp, 80h
0x1800120cf  pop     r15
0x1800120d1  pop     r14
0x1800120d3  pop     rdi
0x1800120d4  pop     rsi
0x1800120d5  pop     rbp
0x1800120d6  retn
```
