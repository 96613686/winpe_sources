# CComExport::ExportPartitionAsMSI(_GUID const &,ushort const *,ushort const *,ulong)

- ea: `0x180051f20`
- end: `0x1800524e9`
- name: `?ExportPartitionAsMSI@CComExport@@UEAAJAEBU_GUID@@PEBG1K@Z`
- size: `1481`
- prototype: `int(CComExport *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180050e68`
- `0x180050fd8`
- `0x180051030`
- `0x1800513f8`
- `0x1800516e4`
- `0x180051800`
- `0x180051e30`
- `0x180051f20`
- `0x1800529e0`
- `0x180052bd8`
- `0x180052ea4`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!ServerGetApplicationType` at `0x1800522e5`
- `CLBCatQ!ServerGetApplicationType` at `0x1800522e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005230b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005230b`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800521e2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180052270`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800521e2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180052270`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005221c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180052293`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18005221c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180052293`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800520d6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800520fc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800520d6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800520fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005212d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005215e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005212d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005215e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180052338`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180052338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005207d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005207d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005210f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005210f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800523aa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800523aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052472`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052472`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051fb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051fb6`

## pseudocode

```c
__int64 __fastcall CComExport::ExportPartitionAsMSI(
        CComExport *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  int v6; // r13d
  unsigned __int16 *v7; // r15
  CComExport *v10; // rcx
  int Instance; // edi
  unsigned int v12; // r13d
  int v13; // eax
  int v14; // r14d
  void *v15; // rax
  const WCHAR *v16; // r14
  unsigned int k; // ebx
  const WCHAR *v18; // rcx
  const unsigned __int16 *v20; // rcx
  signed int LastError; // eax
  CComExport *v22; // rcx
  unsigned int j; // ebx
  __int64 v24; // rdi
  CComExport *v25; // rcx
  struct _GUID *v26; // r13
  signed int v27; // eax
  unsigned __int16 *v28; // rbx
  __int64 (__fastcall *v29)(struct ICOMMSIGen *, const unsigned __int16 *, const struct _GUID *, LPVOID, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPOLESTR, unsigned int, int); // rax
  int v30; // eax
  CComExport *v31; // rcx
  unsigned int i; // ebx
  CComExport *v33; // rcx
  int v34; // eax
  int v35; // [rsp+48h] [rbp-B8h]
  int v36; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-90h] BYREF
  struct ICOMMSIGen *v39; // [rsp+78h] [rbp-88h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+88h] [rbp-78h]
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v43; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v44; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v45; // [rsp+A8h] [rbp-58h] BYREF
  LPOLESTR lpsz; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v47; // [rsp+B8h] [rbp-48h]
  OLECHAR sz[40]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v50[526]; // [rsp+112h] [rbp+12h] BYREF

  v47 = a4;
  v41 = 0;
  v36 = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  pv = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  lpsz = 0;
  v39 = 0;
  ppv = 0;
  CComExport::Uninit((CComExport *)((char *)this - 8));
  Instance = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    v16 = a3;
    goto LABEL_13;
  }
  v12 = a5;
  Instance = CComExport::GetPartitionProperties(v10, a2, ppv, a5, (unsigned __int16 **)&pv, &v43, &v44, &v45);
  if ( Instance < 0 )
  {
    v16 = a3;
    v6 = 0;
    goto LABEL_13;
  }
  if ( a4 && *a4 )
  {
    v7 = a4;
  }
  else
  {
    v13 = CComExport::CalculateRSN(0, ppv, &GUID_NULL, (const unsigned __int16 **)&v38);
    v7 = v38;
    Instance = v13;
    if ( v13 < 0 )
      goto LABEL_11;
  }
  Instance = CComExport::GetAppsInPartition((CComExport *)((char *)this - 8), a2, ppv);
  if ( Instance < 0 )
    goto LABEL_11;
  v14 = 1;
  if ( !*((_DWORD *)this + 18) )
  {
    Buffer = 0;
    memset_0(v50, 0, 0x206u);
    v15 = CoTaskMemAlloc(0x78u);
    *((_QWORD *)this + 8) = v15;
    if ( !v15
      || (memset_0(v15, 0, 0x78u), v20 = (const unsigned __int16 *)pv, *((_DWORD *)this + 18) = 1, v20)
      && *v20
      && (*(_QWORD *)(*((_QWORD *)this + 8) + 16LL) = AllocString(v20)) == 0 )
    {
      Instance = -2147024882;
    }
    else if ( GetTempPathW(0x104u, &Buffer) && GetTempFileNameW(&Buffer, L"APL", 0, &Buffer) )
    {
      CComExport::ExportPartition(v22, a2, &Buffer, a5, *((struct CComExport::AppExportInfo **)this + 8));
LABEL_54:
      Instance = StringFromCLSID(a2, &lpsz);
      if ( Instance >= 0 )
      {
        v38 = 0;
        Instance = ATL::CComObject<CGenerateMSI>::CreateInstance(&v38);
        if ( Instance >= 0 )
        {
          v28 = v38;
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 8LL))(v38);
          Instance = (**(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, struct ICOMMSIGen **))v28)(
                       v28,
                       &IID_ICOMMSIGen,
                       &v39);
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v28 + 16LL))(v28);
          if ( Instance >= 0 )
          {
            Instance = CoImpersonateClient();
            if ( Instance >= 0 )
            {
              v35 = v14;
              v16 = a3;
              v29 = *(__int64 (__fastcall **)(struct ICOMMSIGen *, const unsigned __int16 *, const struct _GUID *, LPVOID, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPOLESTR, unsigned int, int))(*(_QWORD *)v39 + 24LL);
              v41 = 1;
              v30 = v29(v39, a3, a2, pv, v44, v43, v45, lpsz, v12, v35);
              v31 = 0;
              Instance = v30;
              if ( v30 < 0 )
              {
                v6 = 0;
                if ( v30 != -2146368499 )
                  Instance = -2146368505;
                goto LABEL_13;
              }
              v36 = 1;
              for ( i = 0; i < *((_DWORD *)this + 18); ++i )
              {
                Instance = CComExport::AddApplicationToMSI(
                             v31,
                             v39,
                             (struct CComExport::AppExportInfo *)(*((_QWORD *)this + 8) + 120LL * i),
                             v7,
                             v12);
                if ( Instance < 0 )
                  goto LABEL_12;
              }
              StringFromGUID2(a2, sz, 40);
              Instance = (*(__int64 (__fastcall **)(struct ICOMMSIGen *, OLECHAR *))(*(_QWORD *)v39 + 96LL))(v39, sz);
              if ( Instance >= 0 )
              {
                if ( (*(int (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v39 + 72LL))(v39) >= 0 )
                {
                  v34 = CComExport::CabMsiFile(v33, a3, v12);
                  if ( v34 )
                    v34 = -2146368505;
                  Instance = v34;
                }
                else
                {
                  Instance = -2146368505;
                }
              }
LABEL_12:
              v6 = v36;
              goto LABEL_13;
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_11:
    v16 = a3;
    goto LABEL_12;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= *((_DWORD *)this + 18) )
    {
      v12 = a5;
      goto LABEL_54;
    }
    Buffer = 0;
    memset_0(v50, 0, 0x206u);
    v24 = *((_QWORD *)this + 8);
    v6 = 0;
    if ( !GetTempPathW(0x104u, &Buffer) || !GetTempFileNameW(&Buffer, L"APL", 0, &Buffer) )
      break;
    v26 = (struct _GUID *)(v24 + 120LL * j);
    Instance = CComExport::ExportApplication(v25, v26, &Buffer, a5 | 0x100, (struct CComExport::AppExportInfo *)v26);
    if ( Instance < 0 )
      goto LABEL_11;
    if ( v14 == 1 )
    {
      LODWORD(v38) = 0;
      Instance = ServerGetApplicationType(ppv, v26, &v38);
      if ( Instance < 0 )
        goto LABEL_11;
      if ( ((unsigned __int8)v38 & 1) == 0 )
        v14 = 2;
    }
  }
  v27 = GetLastError();
  Instance = v27;
  if ( v27 > 0 )
    Instance = (unsigned __int16)v27 | 0x80070000;
  v16 = a3;
LABEL_13:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( Instance < 0 )
  {
    if ( v39 )
    {
      (*(void (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v39 + 72LL))(v39);
      if ( v6 )
        DeleteFileW(v16);
    }
  }
  for ( k = 0; k < *((_DWORD *)this + 18); ++k )
  {
    v18 = *(const WCHAR **)(120LL * k + *((_QWORD *)this + 8) + 80);
    if ( v18 )
      DeleteFileW(v18);
  }
  if ( v41 )
    CoRevertToSelf();
  CoTaskMemFree(pv);
  CoTaskMemFree(v43);
  CoTaskMemFree(v44);
  CoTaskMemFree(v45);
  CoTaskMemFree(lpsz);
  if ( v7 && (!v47 || !*v47) )
    CoTaskMemFree(v7);
  if ( v39 )
    (*(void (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v39 + 16LL))(v39);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180051f20  push    rbp
0x180051f22  push    rbx
0x180051f23  push    rsi
0x180051f24  push    rdi
0x180051f25  push    r12
0x180051f27  push    r13
0x180051f29  push    r14
0x180051f2b  push    r15
0x180051f2d  lea     rbp, [rsp-238h]
0x180051f35  sub     rsp, 338h
0x180051f3c  mov     rax, cs:__security_cookie
0x180051f43  xor     rax, rsp
0x180051f46  mov     [rbp+270h+var_50], rax
0x180051f4d  xor     eax, eax
0x180051f4f  mov     [rbp+270h+var_2B8], r9
0x180051f53  mov     rsi, rcx
0x180051f56  mov     [rbp+270h+var_2E8], eax
0x180051f59  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180051f5d  mov     [rsp+370h+var_310], eax
0x180051f61  mov     r13d, eax
0x180051f64  mov     [rsp+370h+var_300], rax
0x180051f69  mov     r15d, eax
0x180051f6c  mov     [rbp+270h+pv], rax
0x180051f70  mov     [rbp+270h+var_2D8], rax
0x180051f74  mov     r14, r9
0x180051f77  mov     [rbp+270h+var_2D0], rax
0x180051f7b  mov     r12, rdx
0x180051f7e  mov     [rbp+270h+var_2C8], rax
0x180051f82  mov     [rbp+270h+lpsz], rax
0x180051f86  mov     [rsp+370h+var_2F8], rax
0x180051f8b  mov     [rbp+270h+var_2F0], rax
0x180051f8f  mov     [rsp+370h+lpFileName], r8
0x180051f94  call    ?Uninit@CComExport@@IEAAXXZ; CComExport::Uninit(void)
0x180051f99  lea     rax, [rbp+270h+var_2F0]
0x180051f9d  xor     edx, edx; pUnkOuter
0x180051f9f  lea     r9, IID_ISimpleTableDispenser; riid
0x180051fa6  mov     [rsp+370h+ppv], rax; ppv
0x180051fab  lea     r8d, [r15+1]; dwClsContext
0x180051faf  lea     rcx, clsidSTDISP; rclsid
0x180051fb6  call    cs:__imp_CoCreateInstance
0x180051fbc  mov     edi, eax
0x180051fbe  test    eax, eax
0x180051fc0  js      loc_1800524D2
0x180051fc6  mov     r13d, [rbp+270h+arg_20]
0x180051fcd  lea     rax, [rbp+270h+var_2C8]
0x180051fd1  mov     r8, [rbp+270h+var_2F0]; struct ISimpleTableDispenser *
0x180051fd5  mov     r9d, r13d; unsigned int
0x180051fd8  mov     [rsp+370h+var_338], rax; unsigned __int16 **
0x180051fdd  mov     rdx, r12; struct _GUID *
0x180051fe0  lea     rax, [rbp+270h+var_2D0]
0x180051fe4  mov     [rsp+370h+var_340], rax; unsigned __int16 **
0x180051fe9  lea     rax, [rbp+270h+var_2D8]
0x180051fed  mov     [rsp+370h+var_348], rax; unsigned __int16 **
0x180051ff2  lea     rax, [rbp+270h+pv]
0x180051ff6  mov     [rsp+370h+ppv], rax; unsigned __int16 **
0x180051ffb  call    ?GetPartitionProperties@CComExport@@IEAAJAEBU_GUID@@PEAUISimpleTableDispenser@@KPEAPEAG222@Z; CComExport::GetPartitionProperties(_GUID const &,ISimpleTableDispenser *,ulong,ushort * *,ushort * *,ushort * *,ushort * *)
0x180052000  xor     ecx, ecx; this
0x180052002  mov     edi, eax
0x180052004  test    eax, eax
0x180052006  js      loc_1800524DC
0x18005200c  test    r14, r14
0x18005200f  jz      short loc_18005201C
0x180052011  cmp     [r14], cx
0x180052015  jz      short loc_18005201C
0x180052017  mov     r15, r14
0x18005201a  jmp     short loc_18005203C
0x18005201c  mov     rdx, [rbp+270h+var_2F0]; struct ISimpleTableDispenser *
0x180052020  lea     r9, [rsp+370h+var_300]; unsigned __int16 **
0x180052025  lea     r8, GUID_NULL; struct _GUID *
0x18005202c  call    ?CalculateRSN@CComExport@@IEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAPEBG@Z; CComExport::CalculateRSN(ISimpleTableDispenser *,_GUID const &,ushort const * *)
0x180052031  mov     r15, [rsp+370h+var_300]
0x180052036  mov     edi, eax
0x180052038  test    eax, eax
0x18005203a  js      short loc_180052095
0x18005203c  mov     r8, [rbp+270h+var_2F0]; struct ISimpleTableDispenser *
0x180052040  lea     rcx, [rsi-8]; this
0x180052044  mov     rdx, r12; struct _GUID *
0x180052047  call    ?GetAppsInPartition@CComExport@@IEAAJAEBU_GUID@@PEAUISimpleTableDispenser@@@Z; CComExport::GetAppsInPartition(_GUID const &,ISimpleTableDispenser *)
0x18005204c  mov     edi, eax
0x18005204e  test    eax, eax
0x180052050  js      short loc_180052095
0x180052052  xor     edi, edi
0x180052054  mov     ebx, 1
0x180052059  mov     r14d, ebx
0x18005205c  cmp     [rsi+48h], edi
0x18005205f  jnz     loc_180052243
0x180052065  xor     edx, edx; Val
0x180052067  mov     [rbp+270h+Buffer], di
0x18005206b  mov     r8d, 206h; Size
0x180052071  lea     rcx, [rbp+270h+var_25E]; void *
0x180052075  call    memset_0
0x18005207a  lea     ecx, [rbx+77h]; cb
0x18005207d  call    cs:__imp_CoTaskMemAlloc
0x180052083  mov     [rsi+40h], rax
0x180052087  test    rax, rax
0x18005208a  jnz     loc_18005219F
0x180052090  mov     edi, 8007000Eh
0x180052095  mov     r14, [rsp+370h+lpFileName]
0x18005209a  mov     r13d, [rsp+370h+var_310]
0x18005209f  mov     rcx, [rbp+270h+var_2F0]
0x1800520a3  test    rcx, rcx
0x1800520a6  jz      short loc_1800520B4
0x1800520a8  mov     rax, [rcx]
0x1800520ab  mov     rax, [rax+10h]
0x1800520af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520b4  test    edi, edi
0x1800520b6  jns     short loc_1800520DC
0x1800520b8  mov     rcx, [rsp+370h+var_2F8]
0x1800520bd  test    rcx, rcx
0x1800520c0  jz      short loc_1800520DC
0x1800520c2  mov     rax, [rcx]
0x1800520c5  mov     rax, [rax+48h]
0x1800520c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520ce  test    r13d, r13d
0x1800520d1  jz      short loc_1800520DC
0x1800520d3  mov     rcx, r14; lpFileName
0x1800520d6  call    cs:__imp_DeleteFileW
0x1800520dc  xor     r14d, r14d
0x1800520df  mov     ebx, r14d
0x1800520e2  cmp     [rsi+48h], r14d
0x1800520e6  jbe     short loc_180052109
0x1800520e8  mov     eax, ebx
0x1800520ea  imul    rcx, rax, 78h ; 'x'
0x1800520ee  mov     rax, [rsi+40h]
0x1800520f2  mov     rcx, [rcx+rax+50h]; lpFileName
0x1800520f7  test    rcx, rcx
0x1800520fa  jz      short loc_180052102
0x1800520fc  call    cs:__imp_DeleteFileW
0x180052102  inc     ebx
0x180052104  cmp     ebx, [rsi+48h]
0x180052107  jb      short loc_1800520E8
0x180052109  cmp     [rbp+270h+var_2E8], r14d
0x18005210d  jz      short loc_180052115
0x18005210f  call    cs:__imp_CoRevertToSelf
0x180052115  mov     rcx, [rbp+270h+pv]; pv
0x180052119  call    cs:__imp_CoTaskMemFree
0x18005211f  mov     rcx, [rbp+270h+var_2D8]; pv
0x180052123  call    cs:__imp_CoTaskMemFree
0x180052129  mov     rcx, [rbp+270h+var_2D0]; pv
0x18005212d  call    cs:__imp_CoTaskMemFree
0x180052133  mov     rcx, [rbp+270h+var_2C8]; pv
0x180052137  call    cs:__imp_CoTaskMemFree
0x18005213d  mov     rcx, [rbp+270h+lpsz]; pv
0x180052141  call    cs:__imp_CoTaskMemFree
0x180052147  test    r15, r15
0x18005214a  jz      short loc_180052164
0x18005214c  mov     rax, [rbp+270h+var_2B8]
0x180052150  test    rax, rax
0x180052153  jz      short loc_18005215B
0x180052155  cmp     [rax], r14w
0x180052159  jnz     short loc_180052164
0x18005215b  mov     rcx, r15; pv
0x18005215e  call    cs:__imp_CoTaskMemFree
0x180052164  mov     rcx, [rsp+370h+var_2F8]
0x180052169  test    rcx, rcx
0x18005216c  jz      short loc_18005217A
0x18005216e  mov     rax, [rcx]
0x180052171  mov     rax, [rax+10h]
0x180052175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005217a  mov     eax, edi
0x18005217c  mov     rcx, [rbp+270h+var_50]
0x180052183  xor     rcx, rsp; StackCookie
0x180052186  call    __security_check_cookie
0x18005218b  add     rsp, 338h
0x180052192  pop     r15
0x180052194  pop     r14
0x180052196  pop     r13
0x180052198  pop     r12
0x18005219a  pop     rdi
0x18005219b  pop     rsi
0x18005219c  pop     rbx
0x18005219d  pop     rbp
0x18005219e  retn
0x18005219f  xor     edx, edx; Val
0x1800521a1  mov     rcx, rax; void *
0x1800521a4  lea     r8d, [rdx+78h]; Size
0x1800521a8  call    memset_0
0x1800521ad  mov     rcx, [rbp+270h+pv]; Src
0x1800521b1  mov     [rsi+48h], ebx
0x1800521b4  test    rcx, rcx
0x1800521b7  jz      short loc_1800521D9
0x1800521b9  cmp     [rcx], di
0x1800521bc  jz      short loc_1800521D9
0x1800521be  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x1800521c3  mov     rcx, [rsi+40h]
0x1800521c7  mov     [rcx+10h], rax
0x1800521cb  mov     rax, [rsi+40h]
0x1800521cf  cmp     [rax+10h], rdi
0x1800521d3  jz      loc_180052090
0x1800521d9  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x1800521dd  mov     ecx, 104h; nBufferLength
0x1800521e2  call    cs:__imp_GetTempPathW
0x1800521e8  test    eax, eax
0x1800521ea  jnz     short loc_18005220A
0x1800521ec  call    cs:__imp_GetLastError
0x1800521f2  mov     edi, eax
0x1800521f4  test    eax, eax
0x1800521f6  jle     loc_180052095
0x1800521fc  movzx   edi, ax
0x1800521ff  or      edi, 80070000h
0x180052205  jmp     loc_180052095
0x18005220a  lea     r9, [rbp+270h+Buffer]; lpTempFileName
0x18005220e  xor     r8d, r8d; uUnique
0x180052211  lea     rdx, aApl; "APL"
0x180052218  lea     rcx, [rbp+270h+Buffer]; lpPathName
0x18005221c  call    cs:__imp_GetTempFileNameW
0x180052222  test    eax, eax
0x180052224  jz      short loc_1800521EC
0x180052226  mov     rax, [rsi+40h]
0x18005222a  lea     r8, [rbp+270h+Buffer]; unsigned __int16 *
0x18005222e  mov     r9d, r13d; unsigned int
0x180052231  mov     [rsp+370h+ppv], rax; struct CComExport::AppExportInfo *
0x180052236  mov     rdx, r12; struct _GUID *
0x180052239  call    ?ExportPartition@CComExport@@IEAAJAEBU_GUID@@PEBGKPEAUAppExportInfo@1@@Z; CComExport::ExportPartition(_GUID const &,ushort const *,ulong,CComExport::AppExportInfo *)
0x18005223e  jmp     loc_180052331
0x180052243  mov     ebx, edi
0x180052245  cmp     ebx, [rsi+48h]
0x180052248  jnb     loc_18005232A
0x18005224e  xor     edx, edx; Val
0x180052250  mov     [rbp+270h+Buffer], di
0x180052254  mov     r8d, 206h; Size
0x18005225a  lea     rcx, [rbp+270h+var_25E]; void *
0x18005225e  call    memset_0
0x180052263  mov     rdi, [rsi+40h]
0x180052267  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x18005226b  mov     ecx, 104h; nBufferLength
0x180052270  call    cs:__imp_GetTempPathW
0x180052276  xor     r13d, r13d
0x180052279  test    eax, eax
0x18005227b  jz      loc_18005230B
0x180052281  lea     r9, [rbp+270h+Buffer]; lpTempFileName
0x180052285  xor     r8d, r8d; uUnique
0x180052288  lea     rdx, aApl; "APL"
0x18005228f  lea     rcx, [rbp+270h+Buffer]; lpPathName
0x180052293  call    cs:__imp_GetTempFileNameW
0x180052299  test    eax, eax
0x18005229b  jz      short loc_18005230B
0x18005229d  mov     r9d, [rbp+270h+arg_20]
0x1800522a4  lea     r8, [rbp+270h+Buffer]; unsigned __int16 *
0x1800522a8  mov     eax, ebx
0x1800522aa  bts     r9d, 8; unsigned int
0x1800522af  imul    r13, rax, 78h ; 'x'
0x1800522b3  add     r13, rdi
0x1800522b6  mov     rdx, r13; struct _GUID *
0x1800522b9  mov     [rsp+370h+ppv], r13; struct CComExport::AppExportInfo *
0x1800522be  call    ?ExportApplication@CComExport@@IEAAJAEBU_GUID@@PEBGKPEAUAppExportInfo@1@@Z; CComExport::ExportApplication(_GUID const &,ushort const *,ulong,CComExport::AppExportInfo *)
0x1800522c3  xor     ecx, ecx
0x1800522c5  mov     edi, eax
0x1800522c7  test    eax, eax
0x1800522c9  js      loc_180052095
0x1800522cf  cmp     r14d, 1
0x1800522d3  jnz     short loc_180052302
0x1800522d5  mov     dword ptr [rsp+370h+var_300], ecx
0x1800522d9  lea     r8, [rsp+370h+var_300]
0x1800522de  mov     rcx, [rbp+270h+var_2F0]
0x1800522e2  mov     rdx, r13
0x1800522e5  call    cs:__imp_ServerGetApplicationType
0x1800522eb  mov     edi, eax
0x1800522ed  test    eax, eax
0x1800522ef  js      loc_180052095
0x1800522f5  test    byte ptr [rsp+370h+var_300], r14b
0x1800522fa  lea     eax, [r14+1]
0x1800522fe  cmovz   r14d, eax
0x180052302  inc     ebx
0x180052304  xor     edi, edi
0x180052306  jmp     loc_180052245
0x18005230b  call    cs:__imp_GetLastError
0x180052311  mov     edi, eax
0x180052313  test    eax, eax
0x180052315  jle     short loc_180052320
0x180052317  movzx   edi, ax
0x18005231a  or      edi, 80070000h
0x180052320  mov     r14, [rsp+370h+lpFileName]
0x180052325  jmp     loc_18005209F
0x18005232a  mov     r13d, [rbp+270h+arg_20]
0x180052331  lea     rdx, [rbp+270h+lpsz]; lplpsz
0x180052335  mov     rcx, r12; rclsid
0x180052338  call    cs:__imp_StringFromCLSID
0x18005233e  xor     ecx, ecx
0x180052340  mov     edi, eax
0x180052342  test    eax, eax
0x180052344  js      loc_180052095
0x18005234a  mov     [rsp+370h+var_300], rcx
0x18005234f  lea     rcx, [rsp+370h+var_300]
0x180052354  call    ?CreateInstance@?$CComObject@VCGenerateMSI@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGenerateMSI>::CreateInstance(ATL::CComObject<CGenerateMSI> * *)
0x180052359  mov     edi, eax
0x18005235b  test    eax, eax
0x18005235d  js      loc_180052095
0x180052363  mov     rbx, [rsp+370h+var_300]
0x180052368  mov     rcx, rbx
0x18005236b  mov     rax, [rbx]
0x18005236e  mov     rax, [rax+8]
0x180052372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052377  mov     rax, [rbx]
0x18005237a  lea     r8, [rsp+370h+var_2F8]
0x18005237f  lea     rdx, IID_ICOMMSIGen
0x180052386  mov     rcx, rbx
0x180052389  mov     rax, [rax]
0x18005238c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052391  mov     edi, eax
  ... truncated ...
```
