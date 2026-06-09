# CMapiEnumIDList::Next(ulong,_ITEMID_CHILD * *,ulong *)

- ea: `0x180020b00`
- end: `0x180020f6b`
- name: `?Next@CMapiEnumIDList@@UEAAJKPEAPEAU_ITEMID_CHILD@@PEAK@Z`
- size: `1131`
- prototype: `__int64 __fastcall(CMapiEnumIDList *__hidden this, unsigned int, struct _ITEMID_CHILD **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004100`
- `0x180004120`
- `0x1800047b0`
- `0x180005210`
- `0x180006640`
- `0x1800070ec`
- `0x180014bcc`
- `0x180020864`
- `0x180020b00`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180020d92`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020da6`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f05`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f10`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d92`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020da6`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f05`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f10`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f1b`
- `OLEAUT32!__imp_SysStringLen` at `0x180020cff`
- `OLEAUT32!__imp_SysStringLen` at `0x180020cff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020c8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020cec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020d32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020de0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020ee0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020c8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020cec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020d32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020de0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020ee0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020b69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020b69`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180020ec1`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180020ec1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMapiEnumIDList::Next(
        CMapiEnumIDList *this,
        unsigned int a2,
        struct _ITEMID_CHILD **a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  HRESULT Instance; // esi
  LPVOID *ppv; // rbx
  bool v8; // al
  LPVOID v9; // rcx
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rax
  char *v12; // rax
  char *v13; // r14
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // r15
  unsigned int v16; // eax
  __int64 v17; // rbx
  LONG v18; // eax
  int v19; // eax
  bool v20; // zf
  struct _ITEMID_CHILD *ItemIdList; // rax
  struct _ITEMID_CHILD **v22; // rcx
  unsigned int v23; // r15d
  __int64 v24; // rbx
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-59h] BYREF
  __int64 v27; // [rsp+48h] [rbp-41h] BYREF
  _OWORD v28[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v29; // [rsp+70h] [rbp-19h]
  BSTR bstrString[2]; // [rsp+78h] [rbp-11h] BYREF
  BSTR v31[2]; // [rsp+88h] [rbp-1h]
  struct tagPROPVARIANT v32[3]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int v33; // [rsp+F0h] [rbp+67h] BYREF
  struct _ITEMID_CHILD **v34; // [rsp+100h] [rbp+77h]
  unsigned int *v35; // [rsp+108h] [rbp+7Fh]

  v35 = a4;
  v34 = a3;
  v4 = a2;
  if ( (*((_BYTE *)this + 104) & 0x20) != 0 )
  {
    Instance = 0;
    ppv = (LPVOID *)((char *)this + 64);
    if ( !*((_QWORD *)this + 8) )
    {
      v8 = IsMapiDLL64Bit();
      Instance = CoCreateInstance(
                   &GUID_1af81e4e_fc45_48ee_b236_a2a663494390,
                   0,
                   v8 ? 524292 : 4,
                   &GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67,
                   ppv);
    }
    v9 = *ppv;
    v10 = (_QWORD *)((char *)this + 72);
    if ( v9 && !*v10 )
      Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v9 + 40LL))(
                   v9,
                   *((_QWORD *)this + 11),
                   (char *)this + 72);
    if ( Instance >= 0 && *v10 )
    {
      v11 = 32 * v4;
      if ( !is_mul_ok(v4, 0x20u) )
        v11 = -1;
      v12 = (char *)operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
      v13 = v12;
      v33 = 0;
      if ( v12 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, unsigned int *))(*(_QWORD *)*v10 + 24LL))(
                     *v10,
                     (unsigned int)v4,
                     v12,
                     &v33);
        if ( Instance >= 0 )
        {
          v15 = 0;
          v16 = v33;
          if ( v33 )
          {
            while ( 1 )
            {
              memset(v28, 0, sizeof(v28));
              v29 = 0;
              v17 = 32LL * (unsigned int)v15;
              CComPropVariant::CComPropVariant((CComPropVariant *)v32, *(const wchar_t **)&v13[v17 + 8]);
              Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_ParsingPath, v32);
              if ( Instance < 0 )
                break;
              CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, *(const wchar_t **)&v13[v17]);
              Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_ItemNameDisplay, &pvar);
              PropVariantClear((PROPVARIANT *)&pvar);
              if ( Instance < 0 )
                break;
              v18 = *(_DWORD *)&v13[v17 + 24];
              if ( v18 || *((_DWORD *)this + 27) )
              {
                memset(&pvar, 0, sizeof(pvar));
                pvar.vt = 19;
                pvar.lVal = v18;
                if ( *((_DWORD *)this + 27) )
                  pvar.lVal = v18 | 0x8000;
                Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_SFGAOFlags, &pvar);
                PropVariantClear((PROPVARIANT *)&pvar);
                if ( Instance < 0 )
                  break;
              }
              if ( SysStringLen(*(BSTR *)&v13[v17 + 16]) )
              {
                CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, *(const wchar_t **)&v13[v17 + 16]);
                Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_TooltipText, &pvar);
                PropVariantClear((PROPVARIANT *)&pvar);
              }
              if ( Instance < 0 )
                break;
              *(_OWORD *)bstrString = 0;
              *(_OWORD *)v31 = 0;
              v27 = 0;
              v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 8) + 40LL))(
                      *((_QWORD *)this + 8),
                      *(_QWORD *)&v13[v17 + 8],
                      &v27);
              v20 = v19 == 0;
              if ( v19 >= 0 )
                v20 = (*(unsigned int (__fastcall **)(__int64, __int64, BSTR *, _QWORD))(*(_QWORD *)v27 + 24LL))(
                        v27,
                        1,
                        bstrString,
                        0) == 0;
              if ( v20 )
              {
                SysFreeString(bstrString[0]);
                SysFreeString(bstrString[1]);
                SysFreeString(v31[0]);
                memset(&pvar, 0, sizeof(pvar));
                pvar.vt = 3;
                pvar.lVal = 1;
                Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_HasSubfolders, &pvar);
                PropVariantClear((PROPVARIANT *)&pvar);
              }
              ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v27);
              if ( Instance < 0 )
                break;
              CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, L"MAPI/Folder");
              Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_ItemType, &pvar);
              PropVariantClear((PROPVARIANT *)&pvar);
              if ( Instance < 0 )
                break;
              memset(&pvar, 0, sizeof(pvar));
              pvar.vt = 11;
              pvar.lVal = -1;
              Instance = CPidlMgr::SetProperty((LPVOID *)v28, &PKEY_AllowFolderEnum, &pvar);
              PropVariantClear((PROPVARIANT *)&pvar);
              if ( Instance < 0 )
                break;
              ItemIdList = CPidlMgr::GetItemIdList((CPidlMgr *)v28);
              v22 = v34;
              v34[v15] = ItemIdList;
              if ( !ItemIdList )
              {
                Instance = -2147024882;
                goto LABEL_38;
              }
              PropVariantClear((PROPVARIANT *)v32);
              CPidlMgr::~CPidlMgr((CPidlMgr *)v28);
              v15 = (unsigned int)(v15 + 1);
              v16 = v33;
              if ( (unsigned int)v15 >= v33 )
                goto LABEL_40;
            }
            v22 = v34;
LABEL_38:
            while ( (_DWORD)v15 )
            {
              LODWORD(v15) = v15 - 1;
              ILFree((LPITEMIDLIST)v22[(unsigned int)v15]);
              v22 = v34;
              v34[(unsigned int)v15] = 0;
            }
            v33 = 0;
            PropVariantClear((PROPVARIANT *)v32);
            CPidlMgr::~CPidlMgr((CPidlMgr *)v28);
            v16 = v33;
          }
LABEL_40:
          v23 = 0;
          if ( v16 )
          {
            do
            {
              v24 = 32LL * v23;
              SysFreeString(*(BSTR *)&v13[v24]);
              SysFreeString(*(BSTR *)&v13[v24 + 8]);
              SysFreeString(*(BSTR *)&v13[v24 + 16]);
              ++v23;
              v16 = v33;
            }
            while ( v23 < v33 );
          }
          if ( Instance >= 0 && v35 )
            *v35 = v16;
        }
        operator delete(v13, v14);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return 1;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180020b00  mov     [rsp-8+arg_18], r9
0x180020b05  mov     [rsp-8+arg_10], r8
0x180020b0a  push    rbp
0x180020b0b  push    rbx
0x180020b0c  push    rsi
0x180020b0d  push    r12
0x180020b0f  push    r13
0x180020b11  push    r14
0x180020b13  push    r15
0x180020b15  lea     rbp, [rsp-27h]
0x180020b1a  sub     rsp, 0B0h
0x180020b21  mov     rax, r9
0x180020b24  mov     r15d, edx
0x180020b27  mov     r13, rcx
0x180020b2a  test    byte ptr [rcx+68h], 20h
0x180020b2e  jz      loc_180020F45
0x180020b34  xor     esi, esi
0x180020b36  lea     rbx, [rcx+40h]
0x180020b3a  cmp     [rbx], rsi
0x180020b3d  jnz     short loc_180020B71
0x180020b3f  call    ?IsMapiDLL64Bit@@YA_NXZ; IsMapiDLL64Bit(void)
0x180020b44  neg     al
0x180020b46  sbb     r8d, r8d
0x180020b49  and     r8d, 80000h
0x180020b50  add     r8d, 4; dwClsContext
0x180020b54  mov     [rsp+0E0h+ppv], rbx; ppv
0x180020b59  lea     r9, _GUID_8da6db1c_8114_40c6_9d97_d2e7e9757d67; riid
0x180020b60  xor     edx, edx; pUnkOuter
0x180020b62  lea     rcx, _GUID_1af81e4e_fc45_48ee_b236_a2a663494390; rclsid
0x180020b69  call    cs:__imp_CoCreateInstance
0x180020b6f  mov     esi, eax
0x180020b71  mov     rcx, [rbx]
0x180020b74  lea     rbx, [r13+48h]
0x180020b78  test    rcx, rcx
0x180020b7b  jz      short loc_180020B98
0x180020b7d  cmp     qword ptr [rbx], 0
0x180020b81  jnz     short loc_180020B98
0x180020b83  mov     rax, [rcx]
0x180020b86  mov     r8, rbx
0x180020b89  mov     rdx, [r13+58h]
0x180020b8d  mov     rax, [rax+28h]
0x180020b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b96  mov     esi, eax
0x180020b98  test    esi, esi
0x180020b9a  js      loc_180020F56
0x180020ba0  cmp     qword ptr [rbx], 0
0x180020ba4  jz      loc_180020F56
0x180020baa  mov     eax, 20h ; ' '
0x180020baf  mul     r15
0x180020bb2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020bb9  cmovb   rax, rcx
0x180020bbd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020bc4  mov     rcx, rax; unsigned __int64
0x180020bc7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020bcc  mov     r14, rax
0x180020bcf  mov     [rbp+57h+arg_0], 0
0x180020bd6  test    rax, rax
0x180020bd9  jnz     short loc_180020BE5
0x180020bdb  mov     esi, 8007000Eh
0x180020be0  jmp     loc_180020F56
0x180020be5  mov     rcx, [rbx]
0x180020be8  mov     rax, [rcx]
0x180020beb  lea     r9, [rbp+57h+arg_0]
0x180020bef  mov     r8, r14
0x180020bf2  mov     edx, r15d
0x180020bf5  mov     rax, [rax+18h]
0x180020bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bfe  mov     esi, eax
0x180020c00  test    eax, eax
0x180020c02  js      loc_180020F3B
0x180020c08  xor     r15d, r15d
0x180020c0b  lea     r12d, [r15+1]
0x180020c0f  mov     eax, [rbp+57h+arg_0]
0x180020c12  test    eax, eax
0x180020c14  jz      loc_180020EF3
0x180020c1a  xorps   xmm0, xmm0
0x180020c1d  movdqu  [rbp+57h+var_90], xmm0
0x180020c22  xorps   xmm1, xmm1
0x180020c25  movdqu  [rbp+57h+var_80], xmm1
0x180020c2a  mov     [rbp+57h+var_70], 0
0x180020c32  mov     ebx, r15d
0x180020c35  shl     rbx, 5
0x180020c39  mov     rdx, [rbx+r14+8]; wchar_t *
0x180020c3e  lea     rcx, [rbp+57h+var_48]; this
0x180020c42  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180020c47  nop
0x180020c48  lea     r8, [rbp+57h+var_48]; struct tagPROPVARIANT *
0x180020c4c  lea     rdx, PKEY_ParsingPath; struct _tagpropertykey *
0x180020c53  lea     rcx, [rbp+57h+var_90]; this
0x180020c57  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020c5c  mov     esi, eax
0x180020c5e  test    eax, eax
0x180020c60  js      loc_180020EB4
0x180020c66  mov     rdx, [rbx+r14]; wchar_t *
0x180020c6a  lea     rcx, [rbp+57h+pvar]; this
0x180020c6e  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180020c73  nop
0x180020c74  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020c78  lea     rdx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x180020c7f  lea     rcx, [rbp+57h+var_90]; this
0x180020c83  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020c88  mov     esi, eax
0x180020c8a  lea     rcx, [rbp+57h+pvar]; pvar
0x180020c8e  call    cs:__imp_PropVariantClear
0x180020c94  test    esi, esi
0x180020c96  js      loc_180020EB4
0x180020c9c  mov     eax, [rbx+r14+18h]
0x180020ca1  test    eax, eax
0x180020ca3  jnz     short loc_180020CAB
0x180020ca5  cmp     [r13+6Ch], eax
0x180020ca9  jz      short loc_180020CFA
0x180020cab  xorps   xmm0, xmm0
0x180020cae  xor     ecx, ecx
0x180020cb0  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180020cb4  mov     [rbp+57h+var_A0], rcx
0x180020cb8  mov     ecx, 13h
0x180020cbd  mov     word ptr [rbp+57h+pvar], cx
0x180020cc1  mov     dword ptr [rbp+57h+pvar+8], eax
0x180020cc4  cmp     dword ptr [r13+6Ch], 0
0x180020cc9  jz      short loc_180020CD2
0x180020ccb  bts     eax, 0Fh
0x180020ccf  mov     dword ptr [rbp+57h+pvar+8], eax
0x180020cd2  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020cd6  lea     rdx, PKEY_SFGAOFlags; struct _tagpropertykey *
0x180020cdd  lea     rcx, [rbp+57h+var_90]; this
0x180020ce1  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020ce6  mov     esi, eax
0x180020ce8  lea     rcx, [rbp+57h+pvar]; pvar
0x180020cec  call    cs:__imp_PropVariantClear
0x180020cf2  test    esi, esi
0x180020cf4  js      loc_180020EB4
0x180020cfa  mov     rcx, [rbx+r14+10h]; pbstr
0x180020cff  call    cs:__imp_SysStringLen
0x180020d05  test    eax, eax
0x180020d07  jz      short loc_180020D38
0x180020d09  mov     rdx, [rbx+r14+10h]; wchar_t *
0x180020d0e  lea     rcx, [rbp+57h+pvar]; this
0x180020d12  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180020d17  nop
0x180020d18  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020d1c  lea     rdx, PKEY_TooltipText; struct _tagpropertykey *
0x180020d23  lea     rcx, [rbp+57h+var_90]; this
0x180020d27  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020d2c  mov     esi, eax
0x180020d2e  lea     rcx, [rbp+57h+pvar]; pvar
0x180020d32  call    cs:__imp_PropVariantClear
0x180020d38  test    esi, esi
0x180020d3a  js      loc_180020EB4
0x180020d40  xorps   xmm0, xmm0
0x180020d43  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x180020d47  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180020d4b  mov     [rbp+57h+var_98], 0
0x180020d53  mov     rcx, [r13+40h]
0x180020d57  mov     rax, [rcx]
0x180020d5a  lea     r8, [rbp+57h+var_98]
0x180020d5e  mov     rdx, [rbx+r14+8]
0x180020d63  mov     rax, [rax+28h]
0x180020d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d6c  test    eax, eax
0x180020d6e  js      short loc_180020D8C
0x180020d70  mov     rcx, [rbp+57h+var_98]
0x180020d74  mov     rax, [rcx]
0x180020d77  xor     r9d, r9d
0x180020d7a  lea     r8, [rbp+57h+bstrString]
0x180020d7e  mov     edx, r12d
0x180020d81  mov     rax, [rax+18h]
0x180020d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d8a  test    eax, eax
0x180020d8c  jnz     short loc_180020DE7
0x180020d8e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180020d92  call    cs:__imp_SysFreeString
0x180020d98  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x180020d9c  call    cs:__imp_SysFreeString
0x180020da2  mov     rcx, [rbp+57h+var_58]; bstrString
0x180020da6  call    cs:__imp_SysFreeString
0x180020dac  xorps   xmm0, xmm0
0x180020daf  xor     eax, eax
0x180020db1  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180020db5  mov     [rbp+57h+var_A0], rax
0x180020db9  mov     eax, 3
0x180020dbe  mov     word ptr [rbp+57h+pvar], ax
0x180020dc2  mov     dword ptr [rbp+57h+pvar+8], r12d
0x180020dc6  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020dca  lea     rdx, PKEY_HasSubfolders; struct _tagpropertykey *
0x180020dd1  lea     rcx, [rbp+57h+var_90]; this
0x180020dd5  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020dda  mov     esi, eax
0x180020ddc  lea     rcx, [rbp+57h+pvar]; pvar
0x180020de0  call    cs:__imp_PropVariantClear
0x180020de6  nop
0x180020de7  lea     rcx, [rbp+57h+var_98]
0x180020deb  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180020df0  test    esi, esi
0x180020df2  js      loc_180020EB4
0x180020df8  lea     rdx, aMapiFolder; "MAPI/Folder"
0x180020dff  lea     rcx, [rbp+57h+pvar]; this
0x180020e03  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180020e08  nop
0x180020e09  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020e0d  lea     rdx, PKEY_ItemType; struct _tagpropertykey *
0x180020e14  lea     rcx, [rbp+57h+var_90]; this
0x180020e18  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020e1d  mov     esi, eax
0x180020e1f  lea     rcx, [rbp+57h+pvar]; pvar
0x180020e23  call    cs:__imp_PropVariantClear
0x180020e29  test    esi, esi
0x180020e2b  js      loc_180020EB4
0x180020e31  xorps   xmm0, xmm0
0x180020e34  xor     eax, eax
0x180020e36  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180020e3a  mov     [rbp+57h+var_A0], rax
0x180020e3e  mov     eax, 0Bh
0x180020e43  mov     word ptr [rbp+57h+pvar], ax
0x180020e47  mov     dword ptr [rbp+57h+pvar+8], 0FFFFFFFFh
0x180020e4e  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180020e52  lea     rdx, PKEY_AllowFolderEnum; struct _tagpropertykey *
0x180020e59  lea     rcx, [rbp+57h+var_90]; this
0x180020e5d  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180020e62  mov     esi, eax
0x180020e64  lea     rcx, [rbp+57h+pvar]; pvar
0x180020e68  call    cs:__imp_PropVariantClear
0x180020e6e  test    esi, esi
0x180020e70  js      short loc_180020EB4
0x180020e72  lea     rcx, [rbp+57h+var_90]; this
0x180020e76  call    ?GetItemIdList@CPidlMgr@@QEAAPEAU_ITEMID_CHILD@@XZ; CPidlMgr::GetItemIdList(void)
0x180020e7b  mov     rcx, [rbp+57h+arg_10]
0x180020e7f  mov     [rcx+r15*8], rax
0x180020e83  test    rax, rax
0x180020e86  jz      short loc_180020EAD
0x180020e88  lea     rcx, [rbp+57h+var_48]; pvar
0x180020e8c  call    cs:__imp_PropVariantClear
0x180020e92  nop
0x180020e93  lea     rcx, [rbp+57h+var_90]; this
0x180020e97  call    ??1CPidlMgr@@QEAA@XZ; CPidlMgr::~CPidlMgr(void)
0x180020e9c  add     r15d, r12d
0x180020e9f  mov     eax, [rbp+57h+arg_0]
0x180020ea2  cmp     r15d, eax
0x180020ea5  jb      loc_180020C1A
0x180020eab  jmp     short loc_180020EF3
0x180020ead  mov     esi, 8007000Eh
0x180020eb2  jmp     short loc_180020ED3
0x180020eb4  mov     rcx, [rbp+57h+arg_10]
0x180020eb8  jmp     short loc_180020ED3
0x180020eba  dec     r15d
0x180020ebd  mov     rcx, [rcx+r15*8]; pidl
0x180020ec1  call    cs:__imp_ILFree
0x180020ec7  mov     rcx, [rbp+57h+arg_10]
0x180020ecb  mov     qword ptr [rcx+r15*8], 0
0x180020ed3  test    r15d, r15d
0x180020ed6  jnz     short loc_180020EBA
0x180020ed8  mov     [rbp+57h+arg_0], r15d
0x180020edc  lea     rcx, [rbp+57h+var_48]; pvar
0x180020ee0  call    cs:__imp_PropVariantClear
0x180020ee6  nop
0x180020ee7  lea     rcx, [rbp+57h+var_90]; this
0x180020eeb  call    ??1CPidlMgr@@QEAA@XZ; CPidlMgr::~CPidlMgr(void)
0x180020ef0  mov     eax, [rbp+57h+arg_0]
0x180020ef3  xor     r15d, r15d
0x180020ef6  test    eax, eax
0x180020ef8  jz      short loc_180020F2C
0x180020efa  mov     ebx, r15d
0x180020efd  shl     rbx, 5
0x180020f01  mov     rcx, [rbx+r14]; bstrString
0x180020f05  call    cs:__imp_SysFreeString
0x180020f0b  mov     rcx, [rbx+r14+8]; bstrString
0x180020f10  call    cs:__imp_SysFreeString
0x180020f16  mov     rcx, [rbx+r14+10h]; bstrString
0x180020f1b  call    cs:__imp_SysFreeString
0x180020f21  add     r15d, r12d
0x180020f24  mov     eax, [rbp+57h+arg_0]
0x180020f27  cmp     r15d, eax
0x180020f2a  jb      short loc_180020EFA
0x180020f2c  test    esi, esi
0x180020f2e  js      short loc_180020F3B
0x180020f30  mov     rcx, [rbp+57h+arg_18]
0x180020f34  test    rcx, rcx
0x180020f37  jz      short loc_180020F3B
0x180020f39  mov     [rcx], eax
0x180020f3b  mov     rcx, r14; void *
0x180020f3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020f43  jmp     short loc_180020F56
0x180020f45  test    rax, rax
0x180020f48  jz      short loc_180020F51
0x180020f4a  mov     dword ptr [r9], 0
0x180020f51  mov     esi, 1
0x180020f56  mov     eax, esi
0x180020f58  add     rsp, 0B0h
0x180020f5f  pop     r15
0x180020f61  pop     r14
0x180020f63  pop     r13
0x180020f65  pop     r12
0x180020f67  pop     rsi
0x180020f68  pop     rbx
0x180020f69  pop     rbp
0x180020f6a  retn
```
