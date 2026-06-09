# DllGetClassObject

- ea: `0x180002440`
- end: `0x18000287f`
- name: `DllGetClassObject`
- size: `1087`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002440`
- `0x180002890`
- `0x180002b70`
- `0x180003030`
- `0x180004470`
- `0x180006230`
- `0x180006300`
- `0x1800069c0`
- `0x18000b388`
- `0x180040088`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000253c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800025ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800026d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000253c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800025ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800026d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002780`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct ATL::_ATL_MODULE *v6; // r14
  HINSTANCE v7; // r8
  struct ATL::_ATL_MODULE *v8; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY *v9; // rdx
  int v10; // eax
  HRESULT result; // eax
  __int64 v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // r14
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  __int64 v18; // rax
  CSDTIMetaData *v19; // rax
  CSDTIMetaData *v20; // r14
  unsigned int v21; // edx
  __int64 v22; // rax
  char *v23; // rax
  char *v24; // r14

  *ppv = 0;
  if ( !(_DWORD)g_ModuleWrapper )
  {
    ((void (__fastcall *)(void ***))*off_180072180)(&off_180072180);
    if ( !(_DWORD)g_ModuleWrapper )
    {
      v6 = off_180072178;
      v7 = qword_1800721C0;
      v8 = off_180072178;
      v9 = qword_1800721B8;
      ATL::_pModule = off_180072178;
      *((_QWORD *)off_180072178 + 25) = &ATL::GUID_ATLVer30;
      *(_DWORD *)v8 = 248;
      *((_DWORD *)v8 + 44) = 769;
      v10 = ATL::AtlModuleInit(v8, v9, v7);
      if ( v10 >= 0 )
      {
        *((_DWORD *)v6 + 60) = 1;
        v10 = 0;
      }
      HIDWORD(g_ModuleWrapper) = v10;
      LODWORD(g_ModuleWrapper) = 1;
    }
    ((void (__fastcall *)(void ***))off_180072180[1])(&off_180072180);
  }
  result = HIDWORD(g_ModuleWrapper);
  if ( g_ModuleWrapper >= 0 )
  {
    *ppv = 0;
    v12 = *(_QWORD *)&rclsid->Data1 - clsidSLTIntegrity;
    if ( *(_QWORD *)&rclsid->Data1 == clsidSLTIntegrity )
      v12 = *(_QWORD *)rclsid->Data4 - 0x432C75F800016B1LL;
    if ( !v12 )
    {
      v13 = CoTaskMemAlloc(0x80u);
      v14 = v13;
      if ( v13 )
      {
        v13[3] = 0;
        *((_DWORD *)v13 + 8) = 0;
        v13[5] = 0;
        v13[6] = 0;
        *v13 = &CSLTIntegrity::`vftable'{for `IClassFactory'};
        v13[1] = &CSLTIntegrity::`vftable'{for `ISimpleTableWrite'};
        v13[2] = &CSLTConvert::`vftable'{for `ISimpleTableControl'};
        v13[7] = &CSLTIntegrity::`vftable';
        *((_DWORD *)v13 + 30) = 0;
        *((_DWORD *)v13 + 24) = 0;
        if ( (int)((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))CSLTIntegrity::`vftable'{for `IClassFactory'})(
                    v13,
                    riid,
                    ppv) >= 0 )
          return 0;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v14 + 40LL))(v14, 1);
      }
    }
    *ppv = 0;
    v15 = *(_QWORD *)&rclsid->Data1 - clsidSLTAudit;
    if ( *(_QWORD *)&rclsid->Data1 == clsidSLTAudit )
      v15 = *(_QWORD *)rclsid->Data4 + 0x3728408E2A869D80LL;
    if ( !v15 )
    {
      v16 = CoTaskMemAlloc(0x60u);
      v17 = v16;
      if ( v16 )
      {
        v16[3] = 0;
        *((_DWORD *)v16 + 8) = 0;
        v16[5] = 0;
        v16[6] = 0;
        *v16 = &CSLTAudit::`vftable'{for `IClassFactory'};
        v16[1] = &CSLTAudit::`vftable'{for `ISimpleTableWrite'};
        v16[2] = &CSLTConvert::`vftable'{for `ISimpleTableControl'};
        v16[7] = &CSLTAudit::`vftable';
        if ( (int)((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))CSLTAudit::`vftable'{for `IClassFactory'})(
                    v16,
                    riid,
                    ppv) >= 0 )
          return 0;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v17 + 40LL))(v17, 1);
        *ppv = 0;
      }
    }
    if ( (int)ATL::AtlModuleGetClassObject((struct ATL::_ATL_MODULE *)rclsid, rclsid, riid, ppv) >= 0
      || (int)LtSecGetClassObject(rclsid, riid, ppv) >= 0
      || (int)LtPartGetClassObject(rclsid, riid, ppv) >= 0 )
    {
      return 0;
    }
    *ppv = 0;
    v18 = *(_QWORD *)&rclsid->Data1 - clsidSDTIMetaData;
    if ( *(_QWORD *)&rclsid->Data1 == clsidSDTIMetaData )
      v18 = *(_QWORD *)rclsid->Data4 + 0x381F3DB03FFFBC71LL;
    if ( !v18 )
    {
      v19 = (CSDTIMetaData *)CoTaskMemAlloc(0x70u);
      v20 = v19;
      if ( v19 )
      {
        *((_QWORD *)v19 + 4) = 0;
        *(_QWORD *)v19 = &CSDTIMetaData::`vftable'{for `IClassFactory'};
        *((_DWORD *)v19 + 10) = 0;
        *((_QWORD *)v19 + 1) = &CSDTIMetaData::`vftable'{for `ISimpleDataTableDispenser'};
        *((_QWORD *)v19 + 6) = 0;
        *((_QWORD *)v19 + 2) = &CSDTIMetaData::`vftable'{for `ISimpleTableWrite'};
        *((_QWORD *)v19 + 7) = 0;
        *((_QWORD *)v19 + 3) = &CSDTIMetaData::`vftable'{for `ISimpleTableControl'};
        *((_QWORD *)v19 + 8) = 0;
        *((_QWORD *)v19 + 11) = 0;
        *((_QWORD *)v19 + 12) = 0;
        *((_QWORD *)v19 + 13) = 0;
        if ( (int)((__int64 (__fastcall *)(CSDTIMetaData *, const IID *const, LPVOID *))CSDTIMetaData::`vftable'{for `IClassFactory'})(
                    v19,
                    riid,
                    ppv) >= 0 )
          return 0;
        CSDTIMetaData::`scalar deleting destructor'(v20, v21);
      }
    }
    *ppv = 0;
    v22 = *(_QWORD *)&rclsid->Data1 - clsidSdtEvent;
    if ( *(_QWORD *)&rclsid->Data1 == clsidSdtEvent )
      v22 = *(_QWORD *)rclsid->Data4 - 0x30202C307830F2A3LL;
    if ( v22 || (v23 = (char *)CoTaskMemAlloc(0x80u), (v24 = v23) == 0) )
    {
LABEL_35:
      if ( (int)SLTConvertGetClassObject(rclsid, riid, ppv) < 0
        && (int)LTMiscSDKGetClassObject(rclsid, riid, ppv) < 0
        && (int)SltAppGetClassObject(rclsid, riid, ppv) < 0 )
      {
        return SLTClustGetClassObject(rclsid, riid, ppv);
      }
      return 0;
    }
    *((_QWORD *)v23 + 4) = 0;
    *((_DWORD *)v23 + 10) = 0;
    *((_QWORD *)v23 + 6) = 0;
    *((_QWORD *)v23 + 7) = 0;
    *(_QWORD *)v23 = &CSdtEvent::`vftable'{for `IClassFactory'};
    *((_QWORD *)v23 + 1) = &CSdtEvent::`vftable'{for `ISimpleDataTableDispenser'};
    *((_QWORD *)v23 + 2) = &CSdtEvent::`vftable'{for `ISimpleTableWrite'};
    *((_QWORD *)v23 + 3) = &CSdtEvent::`vftable'{for `ISimpleTableControl'};
    *((_DWORD *)v23 + 16) = 4;
    *((_QWORD *)v23 + 9) = 0;
    *((_QWORD *)v23 + 10) = 0;
    *((_QWORD *)v23 + 11) = 0;
    *((_QWORD *)v23 + 12) = 0;
    *((_QWORD *)v23 + 15) = 0;
    *(GUID *)(v23 + 104) = GUID_NULL;
    if ( (int)((__int64 (__fastcall *)(char *, const IID *const, LPVOID *))CSdtEvent::`vftable'{for `IClassFactory'})(
                v23,
                riid,
                ppv) < 0 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v24 + 40LL))(v24, 1);
      *ppv = 0;
      goto LABEL_35;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002440  mov     [rsp+arg_0], rbx
0x180002445  mov     [rsp+arg_8], rbp
0x18000244a  push    rsi
0x18000244b  push    rdi
0x18000244c  push    r14
0x18000244e  sub     rsp, 20h
0x180002452  xor     ebp, ebp
0x180002454  mov     rbx, r8
0x180002457  mov     [r8], rbp
0x18000245a  mov     rsi, rdx
0x18000245d  cmp     dword ptr cs:?g_ModuleWrapper@@3VCComModuleWrapper@@A, ebp; CComModuleWrapper g_ModuleWrapper
0x180002463  mov     rdi, rcx
0x180002466  jnz     loc_180002506
0x18000246c  mov     rax, cs:off_180072180
0x180002473  lea     rcx, off_180072180
0x18000247a  mov     rax, [rax]
0x18000247d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002482  cmp     dword ptr cs:?g_ModuleWrapper@@3VCComModuleWrapper@@A, ebp; CComModuleWrapper g_ModuleWrapper
0x180002488  jnz     short loc_1800024EF
0x18000248a  mov     r14, cs:off_180072178
0x180002491  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x180002498  mov     r8, cs:qword_1800721C0; HINSTANCE
0x18000249f  mov     rcx, r14; struct ATL::_ATL_MODULE *
0x1800024a2  mov     rdx, cs:qword_1800721B8; struct ATL::_ATL_OBJMAP_ENTRY *
0x1800024a9  mov     cs:?_pModule@ATL@@3PEAVCComModule@1@EA, r14; ATL::CComModule * ATL::_pModule
0x1800024b0  mov     [r14+0C8h], rax
0x1800024b7  mov     dword ptr [r14], 0F8h
0x1800024be  mov     dword ptr [r14+0B0h], 301h
0x1800024c9  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x1800024ce  test    eax, eax
0x1800024d0  js      short loc_1800024DF
0x1800024d2  mov     dword ptr [r14+0F0h], 1
0x1800024dd  mov     eax, ebp
0x1800024df  mov     dword ptr cs:?g_ModuleWrapper@@3VCComModuleWrapper@@A+4, eax; CComModuleWrapper g_ModuleWrapper
0x1800024e5  mov     dword ptr cs:?g_ModuleWrapper@@3VCComModuleWrapper@@A, 1; CComModuleWrapper g_ModuleWrapper
0x1800024ef  mov     rax, cs:off_180072180
0x1800024f6  lea     rcx, off_180072180
0x1800024fd  mov     rax, [rax+8]
0x180002501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002506  mov     eax, dword ptr cs:?g_ModuleWrapper@@3VCComModuleWrapper@@A+4; CComModuleWrapper g_ModuleWrapper
0x18000250c  test    eax, eax
0x18000250e  js      loc_18000286C
0x180002514  mov     [rbx], rbp
0x180002517  mov     rax, [rdi]
0x18000251a  sub     rax, cs:clsidSLTIntegrity
0x180002521  jnz     short loc_18000252E
0x180002523  mov     rax, [rdi+8]
0x180002527  sub     rax, cs:qword_180060C58
0x18000252e  test    rax, rax
0x180002531  jnz     loc_1800025C2
0x180002537  mov     ecx, 80h; cb
0x18000253c  call    cs:__imp_CoTaskMemAlloc
0x180002542  mov     [rsp+38h+arg_10], rax
0x180002547  mov     r14, rax
0x18000254a  test    rax, rax
0x18000254d  jz      short loc_1800025C2
0x18000254f  mov     [rax+18h], rbp
0x180002553  mov     r8, rbx
0x180002556  mov     [rax+20h], ebp
0x180002559  mov     rdx, rsi
0x18000255c  mov     [rax+28h], rbp
0x180002560  mov     rcx, r14
0x180002563  mov     [rax+30h], rbp
0x180002567  lea     rax, ??_7CSLTIntegrity@@6BIClassFactory@@@; const CSLTIntegrity::`vftable'{for `IClassFactory'}
0x18000256e  mov     [r14], rax
0x180002571  lea     rax, ??_7CSLTIntegrity@@6BISimpleTableWrite@@@; const CSLTIntegrity::`vftable'{for `ISimpleTableWrite'}
0x180002578  mov     [r14+8], rax
0x18000257c  lea     rax, ??_7CSLTConvert@@6BISimpleTableControl@@@; const CSLTConvert::`vftable'{for `ISimpleTableControl'}
0x180002583  mov     [r14+10h], rax
0x180002587  lea     rax, ??_7CSLTIntegrity@@6B@; const CSLTIntegrity::`vftable'
0x18000258e  mov     [r14+38h], rax
0x180002592  mov     [r14+78h], ebp
0x180002596  mov     [r14+60h], ebp
0x18000259a  mov     rax, cs:??_7CSLTIntegrity@@6BIClassFactory@@@; const CSLTIntegrity::`vftable'{for `IClassFactory'}
0x1800025a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a6  test    eax, eax
0x1800025a8  jns     loc_18000286A
0x1800025ae  mov     rax, [r14]
0x1800025b1  mov     edx, 1
0x1800025b6  mov     rcx, r14
0x1800025b9  mov     rax, [rax+28h]
0x1800025bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c2  mov     [rbx], rbp
0x1800025c5  mov     rax, [rdi]
0x1800025c8  sub     rax, cs:clsidSLTAudit
0x1800025cf  jnz     short loc_1800025DC
0x1800025d1  mov     rax, [rdi+8]
0x1800025d5  sub     rax, cs:qword_180061050
0x1800025dc  test    rax, rax
0x1800025df  jnz     loc_18000266B
0x1800025e5  mov     ecx, 60h ; '`'; cb
0x1800025ea  call    cs:__imp_CoTaskMemAlloc
0x1800025f0  mov     [rsp+38h+arg_10], rax
0x1800025f5  mov     r14, rax
0x1800025f8  test    rax, rax
0x1800025fb  jz      short loc_18000266B
0x1800025fd  mov     [rax+18h], rbp
0x180002601  mov     r8, rbx
0x180002604  mov     [rax+20h], ebp
0x180002607  mov     rdx, rsi
0x18000260a  mov     [rax+28h], rbp
0x18000260e  mov     rcx, r14
0x180002611  mov     [rax+30h], rbp
0x180002615  lea     rax, ??_7CSLTAudit@@6BIClassFactory@@@; const CSLTAudit::`vftable'{for `IClassFactory'}
0x18000261c  mov     [r14], rax
0x18000261f  lea     rax, ??_7CSLTAudit@@6BISimpleTableWrite@@@; const CSLTAudit::`vftable'{for `ISimpleTableWrite'}
0x180002626  mov     [r14+8], rax
0x18000262a  lea     rax, ??_7CSLTConvert@@6BISimpleTableControl@@@; const CSLTConvert::`vftable'{for `ISimpleTableControl'}
0x180002631  mov     [r14+10h], rax
0x180002635  lea     rax, ??_7CSLTAudit@@6B@; const CSLTAudit::`vftable'
0x18000263c  mov     [r14+38h], rax
0x180002640  mov     rax, cs:??_7CSLTAudit@@6BIClassFactory@@@; const CSLTAudit::`vftable'{for `IClassFactory'}
0x180002647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264c  test    eax, eax
0x18000264e  jns     loc_18000286A
0x180002654  mov     rax, [r14]
0x180002657  mov     edx, 1
0x18000265c  mov     rcx, r14
0x18000265f  mov     rax, [rax+28h]
0x180002663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002668  mov     [rbx], rbp
0x18000266b  mov     r9, rbx; void **
0x18000266e  mov     r8, rsi; struct _GUID *
0x180002671  mov     rdx, rdi; struct _GUID *
0x180002674  call    ?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x180002679  test    eax, eax
0x18000267b  jns     loc_18000286A
0x180002681  mov     r8, rbx
0x180002684  mov     rdx, rsi
0x180002687  mov     rcx, rdi
0x18000268a  call    LtSecGetClassObject
0x18000268f  test    eax, eax
0x180002691  jns     loc_18000286A
0x180002697  mov     r8, rbx
0x18000269a  mov     rdx, rsi
0x18000269d  mov     rcx, rdi
0x1800026a0  call    LtPartGetClassObject
0x1800026a5  test    eax, eax
0x1800026a7  jns     loc_18000286A
0x1800026ad  mov     [rbx], rbp
0x1800026b0  mov     rax, [rdi]
0x1800026b3  sub     rax, cs:clsidSDTIMetaData
0x1800026ba  jnz     short loc_1800026C7
0x1800026bc  mov     rax, [rdi+8]
0x1800026c0  sub     rax, cs:qword_1800611B0
0x1800026c7  test    rax, rax
0x1800026ca  jnz     loc_180002758
0x1800026d0  mov     ecx, 70h ; 'p'; cb
0x1800026d5  call    cs:__imp_CoTaskMemAlloc
0x1800026db  mov     [rsp+38h+arg_10], rax
0x1800026e0  mov     r14, rax
0x1800026e3  test    rax, rax
0x1800026e6  jz      short loc_180002758
0x1800026e8  lea     rax, ??_7CSDTIMetaData@@6BIClassFactory@@@; const CSDTIMetaData::`vftable'{for `IClassFactory'}
0x1800026ef  mov     [r14+20h], rbp
0x1800026f3  mov     [r14], rax
0x1800026f6  mov     r8, rbx
0x1800026f9  lea     rax, ??_7CSDTIMetaData@@6BISimpleDataTableDispenser@@@; const CSDTIMetaData::`vftable'{for `ISimpleDataTableDispenser'}
0x180002700  mov     [r14+28h], ebp
0x180002704  mov     [r14+8], rax
0x180002708  mov     rdx, rsi
0x18000270b  lea     rax, ??_7CSDTIMetaData@@6BISimpleTableWrite@@@; const CSDTIMetaData::`vftable'{for `ISimpleTableWrite'}
0x180002712  mov     [r14+30h], rbp
0x180002716  mov     [r14+10h], rax
0x18000271a  mov     rcx, r14
0x18000271d  lea     rax, ??_7CSDTIMetaData@@6BISimpleTableControl@@@; const CSDTIMetaData::`vftable'{for `ISimpleTableControl'}
0x180002724  mov     [r14+38h], rbp
0x180002728  mov     [r14+18h], rax
0x18000272c  mov     [r14+40h], rbp
0x180002730  mov     [r14+58h], rbp
0x180002734  mov     [r14+60h], rbp
0x180002738  mov     [r14+68h], rbp
0x18000273c  mov     rax, cs:??_7CSDTIMetaData@@6BIClassFactory@@@; const CSDTIMetaData::`vftable'{for `IClassFactory'}
0x180002743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002748  test    eax, eax
0x18000274a  jns     loc_18000286A
0x180002750  mov     rcx, r14; this
0x180002753  call    ??_GCSDTIMetaData@@QEAAPEAXI@Z; CSDTIMetaData::`scalar deleting destructor'(uint)
0x180002758  mov     [rbx], rbp
0x18000275b  mov     rax, [rdi]
0x18000275e  sub     rax, cs:clsidSdtEvent
0x180002765  jnz     short loc_180002772
0x180002767  mov     rax, [rdi+8]
0x18000276b  sub     rax, cs:qword_1800611C0
0x180002772  test    rax, rax
0x180002775  jnz     loc_180002824
0x18000277b  mov     ecx, 80h; cb
0x180002780  call    cs:__imp_CoTaskMemAlloc
0x180002786  mov     r14, rax
0x180002789  test    rax, rax
0x18000278c  jz      loc_180002824
0x180002792  mov     [rax+20h], rbp
0x180002796  mov     r8, rbx
0x180002799  mov     [rax+28h], ebp
0x18000279c  mov     rdx, rsi
0x18000279f  mov     [rax+30h], rbp
0x1800027a3  mov     rcx, r14
0x1800027a6  mov     [rax+38h], rbp
0x1800027aa  lea     rax, ??_7CSdtEvent@@6BIClassFactory@@@; const CSdtEvent::`vftable'{for `IClassFactory'}
0x1800027b1  mov     [r14], rax
0x1800027b4  lea     rax, ??_7CSdtEvent@@6BISimpleDataTableDispenser@@@; const CSdtEvent::`vftable'{for `ISimpleDataTableDispenser'}
0x1800027bb  mov     [r14+8], rax
0x1800027bf  lea     rax, ??_7CSdtEvent@@6BISimpleTableWrite@@@; const CSdtEvent::`vftable'{for `ISimpleTableWrite'}
0x1800027c6  mov     [r14+10h], rax
0x1800027ca  lea     rax, ??_7CSdtEvent@@6BISimpleTableControl@@@; const CSdtEvent::`vftable'{for `ISimpleTableControl'}
0x1800027d1  mov     [r14+18h], rax
0x1800027d5  mov     dword ptr [r14+40h], 4
0x1800027dd  mov     [r14+48h], rbp
0x1800027e1  mov     [r14+50h], rbp
0x1800027e5  mov     [r14+58h], rbp
0x1800027e9  mov     [r14+60h], rbp
0x1800027ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800027f4  mov     [r14+78h], rbp
0x1800027f8  movups  xmmword ptr [r14+68h], xmm0
0x1800027fd  mov     rax, cs:??_7CSdtEvent@@6BIClassFactory@@@; const CSdtEvent::`vftable'{for `IClassFactory'}
0x180002804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002809  test    eax, eax
0x18000280b  jns     short loc_18000286A
0x18000280d  mov     rax, [r14]
0x180002810  mov     edx, 1
0x180002815  mov     rcx, r14
0x180002818  mov     rax, [rax+28h]
0x18000281c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002821  mov     [rbx], rbp
0x180002824  mov     r8, rbx
0x180002827  mov     rdx, rsi
0x18000282a  mov     rcx, rdi
0x18000282d  call    SLTConvertGetClassObject
0x180002832  test    eax, eax
0x180002834  jns     short loc_18000286A
0x180002836  mov     r8, rbx
0x180002839  mov     rdx, rsi
0x18000283c  mov     rcx, rdi
0x18000283f  call    LTMiscSDKGetClassObject
0x180002844  test    eax, eax
0x180002846  jns     short loc_18000286A
0x180002848  mov     r8, rbx
0x18000284b  mov     rdx, rsi
0x18000284e  mov     rcx, rdi
0x180002851  call    SltAppGetClassObject
0x180002856  test    eax, eax
0x180002858  jns     short loc_18000286A
0x18000285a  mov     r8, rbx
0x18000285d  mov     rdx, rsi
0x180002860  mov     rcx, rdi
0x180002863  call    SLTClustGetClassObject
0x180002868  jmp     short loc_18000286C
0x18000286a  xor     eax, eax
0x18000286c  mov     rbx, [rsp+38h+arg_0]
0x180002871  mov     rbp, [rsp+38h+arg_8]
0x180002876  add     rsp, 20h
0x18000287a  pop     r14
0x18000287c  pop     rdi
0x18000287d  pop     rsi
0x18000287e  retn
```
