# CIXaTm::Init(IUnknown *,INameObject *,INameObject *,int,int)

- ea: `0x18000ae50`
- end: `0x18000b234`
- name: `?Init@CIXaTm@@UEAAJPEAUIUnknown@@PEAUINameObject@@1HH@Z`
- size: `996`
- prototype: `__int64 __fastcall(CIXaTm *__hidden this, struct IUnknown *, struct INameObject *, struct INameObject *, bool, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009370`
- `0x18000ae50`
- `0x180016490`
- `0x1800240b0`
- `0x18009b604`
- `0x18009bf70`
- `0x1800b83e2`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000af35`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000af35`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b11f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b185`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b1c3`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b11f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b185`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000b1c3`
- `RPCRT4!UuidFromStringA` at `0x18000af1d`
- `RPCRT4!UuidFromStringA` at `0x18000af1d`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x18000b002`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x18000b002`
- `MSDTCPRX!__imp_DllGetDTCUtilObject` at `0x18000afcf`
- `MSDTCPRX!__imp_DllGetDTCUtilObject` at `0x18000afcf`

## string_xrefs

- `0x18000b1f9`: `com\complus\dtc\dtc\xatm\src\xatm.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CIXaTm::Init(
        CIXaTm *this,
        struct IUnknown *a2,
        struct INameObject *a3,
        struct INameObject *a4,
        int a5,
        int a6)
{
  int v10; // esi
  RPC_CSTR *v11; // rax
  HANDLE EventA; // rax
  HRESULT result; // eax
  const unsigned __int16 *v14; // rcx
  struct INameService *v15; // rdi
  unsigned int v16; // edx
  _DWORD *v17; // rdi
  HRESULT ClassObject; // ebx
  struct ITmInstance *v19; // [rsp+30h] [rbp-58h] BYREF
  LPVOID ppv[10]; // [rsp+38h] [rbp-50h] BYREF
  struct INameService *v21; // [rsp+A0h] [rbp+18h] BYREF

  v21 = 0;
  v19 = 0;
  ppv[0] = 0;
  v10 = a5;
  g_fXaTransactionsAllowed = a5;
  if ( (*(int (__fastcall **)(struct INameObject *, struct ITmInstance **))(*(_QWORD *)a3 + 272LL))(a3, &v19) < 0 )
    return -2147467259;
  g_dwXaTmMinWarmRecoveryInterval = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)v19 + 344LL))(
                                      v19,
                                      L"XaTmMinWarmRecoveryInterval",
                                      15000);
  g_dwXaTmMaxWarmRecoveryInterval = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)v19 + 344LL))(
                                      v19,
                                      L"XaTmMaxWarmRecoveryInterval",
                                      600000);
  (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v19 + 16LL))(v19);
  v11 = (RPC_CSTR *)(*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)a3 + 32LL))(a3);
  if ( UuidFromStringA(*v11, &g_guidXATM) )
    return -2147467259;
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)this + 6) = EventA;
  if ( !EventA )
    return -2147467259;
  if ( memcmp_0(&IID_IXaTmTrace, &IID_IUnknown, 0x10u) && memcmp_0(&IID_IXaTmTrace, &IID_IXaTmTrace, 0x10u) )
  {
    g_pIXaTmTrace = 0;
    return -2147467262;
  }
  g_pIXaTmTrace = (struct IXaTmTrace *)&g_CIXaTmTrace;
  (*(void (**)(void))(g_CIXaTmTrace + 8))();
  result = DllGetDTCUtilObject(&CLSID_DTCUtil, &IID_INameService, &v21);
  if ( !result )
  {
    g_pXINameService = v21;
    result = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, &v21);
    if ( !result )
    {
      g_pXIConnectionManager = v21;
      result = (**(__int64 (__fastcall ***)(struct INameService *, GUID *, struct INameService **))v21)(
                 v21,
                 &IID_IConnectionManagerConfig2,
                 &v21);
      if ( !result )
      {
        v15 = v21;
        LOBYTE(a5) = 0;
        MtxCluIsClusterPresentNonAdmin(v14, (bool *)&a5);
        if ( (_BYTE)a5
          || a6
          || (result = (*(__int64 (__fastcall **)(struct INameService *, __int64))(*(_QWORD *)v15 + 120LL))(v15, 32)) == 0 )
        {
          v17 = operator new(0x48u);
          ppv[1] = v17;
          if ( v17 )
          {
            *(_QWORD *)v17 = &CIConnectionNotify::`vftable';
            CSemExclusiveSL::CSemExclusiveSL((CSemExclusiveSL *)(v17 + 4), v16);
            v17[2] = 0;
          }
          else
          {
            v17 = 0;
          }
          if ( !v17 )
            return -2147024882;
          result = (*(__int64 (__fastcall **)(struct IConnectionManager *, struct INameObject *, _DWORD *, __int64))(*(_QWORD *)g_pXIConnectionManager + 24LL))(
                     g_pXIConnectionManager,
                     a3,
                     v17,
                     1);
          if ( !result )
          {
            if ( !v10 )
              return 0;
            ClassObject = CoGetClassObject(
                            &GUID_3bbe95da_c53f_11d1_b3a2_00a0c9083365,
                            1u,
                            0,
                            &GUID_3bbe95db_c53f_11d1_b3a2_00a0c9083365,
                            ppv);
            if ( ClassObject >= 0 )
            {
              ClassObject = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, _QWORD, struct INameObject *))(*(_QWORD *)ppv[0] + 24LL))(
                              ppv[0],
                              a2,
                              0,
                              a4);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
            }
            if ( ClassObject )
              return ClassObject;
            result = CoGetClassObject(
                       &GUID_3bbe95fb_c53f_11d1_b3a2_00a0c9083365,
                       1u,
                       0,
                       &IID_IClassFactory,
                       &g_pIGatewayInstanceCF);
            if ( g_pIGatewayInstanceCF )
            {
              if ( result >= 0 )
              {
                result = CoGetClassObject(
                           &GUID_3bbe95fe_c53f_11d1_b3a2_00a0c9083365,
                           1u,
                           0,
                           &IID_IClassFactory,
                           &g_pIGatewayInstanceScanCF);
                if ( g_pIGatewayInstanceScanCF )
                {
                  if ( result >= 0 )
                  {
                    result = InitCryptoKey(v19);
                    if ( !result )
                    {
                      if ( g_dwXaTmMinWarmRecoveryInterval > g_dwXaTmMaxWarmRecoveryInterval )
                      {
                        XA_TRACE_WARNING(0x8000D047, "com\\complus\\dtc\\dtc\\xatm\\src\\xatm.cpp", 302);
                        g_dwXaTmMinWarmRecoveryInterval = 15000;
                        g_dwXaTmMaxWarmRecoveryInterval = 600000;
                      }
                      return 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ae50  mov     r11, rsp
0x18000ae53  push    rbx
0x18000ae54  push    rbp
0x18000ae55  push    rsi
0x18000ae56  push    rdi
0x18000ae57  push    r14
0x18000ae59  push    r15
0x18000ae5b  sub     rsp, 58h
0x18000ae5f  mov     rbp, r9
0x18000ae62  mov     rbx, r8
0x18000ae65  mov     r14, rdx
0x18000ae68  mov     rdi, rcx
0x18000ae6b  xor     r15d, r15d
0x18000ae6e  mov     [r11+18h], r15
0x18000ae72  mov     [r11-58h], r15
0x18000ae76  mov     [r11-50h], r15
0x18000ae7a  mov     esi, [rsp+88h+arg_20]
0x18000ae81  mov     cs:?g_fXaTransactionsAllowed@@3HA, esi; int g_fXaTransactionsAllowed
0x18000ae87  mov     rax, [r8]
0x18000ae8a  lea     rdx, [r11-58h]
0x18000ae8e  mov     rcx, r8
0x18000ae91  mov     rax, [rax+110h]
0x18000ae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9d  test    eax, eax
0x18000ae9f  js      loc_18000B222
0x18000aea5  mov     rcx, [rsp+88h+var_58]
0x18000aeaa  mov     rax, [rcx]
0x18000aead  mov     r8d, 3A98h
0x18000aeb3  lea     rdx, aXatmminwarmrec; "XaTmMinWarmRecoveryInterval"
0x18000aeba  mov     rax, [rax+158h]
0x18000aec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec6  mov     cs:?g_dwXaTmMinWarmRecoveryInterval@@3KA, eax; ulong g_dwXaTmMinWarmRecoveryInterval
0x18000aecc  mov     rcx, [rsp+88h+var_58]
0x18000aed1  mov     rax, [rcx]
0x18000aed4  mov     r8d, 927C0h
0x18000aeda  lea     rdx, aXatmmaxwarmrec; "XaTmMaxWarmRecoveryInterval"
0x18000aee1  mov     rax, [rax+158h]
0x18000aee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeed  mov     cs:?g_dwXaTmMaxWarmRecoveryInterval@@3KA, eax; ulong g_dwXaTmMaxWarmRecoveryInterval
0x18000aef3  mov     rcx, [rsp+88h+var_58]
0x18000aef8  mov     rax, [rcx]
0x18000aefb  mov     rax, [rax+10h]
0x18000aeff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af04  mov     rax, [rbx]
0x18000af07  mov     rcx, rbx
0x18000af0a  mov     rax, [rax+20h]
0x18000af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af13  lea     rdx, ?g_guidXATM@@3U_GUID@@A; Uuid
0x18000af1a  mov     rcx, [rax]; StringUuid
0x18000af1d  call    cs:__imp_UuidFromStringA
0x18000af23  test    eax, eax
0x18000af25  jnz     loc_18000B222
0x18000af2b  xor     r9d, r9d; lpName
0x18000af2e  xor     r8d, r8d; bInitialState
0x18000af31  xor     edx, edx; bManualReset
0x18000af33  xor     ecx, ecx; lpEventAttributes
0x18000af35  call    cs:__imp_CreateEventA
0x18000af3b  mov     [rdi+30h], rax
0x18000af3f  test    rax, rax
0x18000af42  jz      loc_18000B222
0x18000af48  mov     r8d, 10h; Size
0x18000af4e  lea     rdx, IID_IUnknown; Buf2
0x18000af55  lea     rcx, IID_IXaTmTrace; Buf1
0x18000af5c  call    memcmp_0
0x18000af61  test    eax, eax
0x18000af63  jz      short loc_18000AF9B
0x18000af65  mov     r8d, 10h; Size
0x18000af6b  lea     rdx, IID_IXaTmTrace; Buf2
0x18000af72  lea     rcx, IID_IXaTmTrace; Buf1
0x18000af79  call    memcmp_0
0x18000af7e  test    eax, eax
0x18000af80  jz      short loc_18000AF9B
0x18000af82  mov     cs:?g_pIXaTmTrace@@3PEAUIXaTmTrace@@EA, r15; IXaTmTrace * g_pIXaTmTrace
0x18000af89  mov     eax, 80004002h
0x18000af8e  add     rsp, 58h
0x18000af92  pop     r15
0x18000af94  pop     r14
0x18000af96  pop     rdi
0x18000af97  pop     rsi
0x18000af98  pop     rbp
0x18000af99  pop     rbx
0x18000af9a  retn
0x18000af9b  lea     rcx, ?g_CIXaTmTrace@@3VCIXaTmTrace@@A; CIXaTmTrace g_CIXaTmTrace
0x18000afa2  mov     cs:?g_pIXaTmTrace@@3PEAUIXaTmTrace@@EA, rcx; IXaTmTrace * g_pIXaTmTrace
0x18000afa9  mov     rax, cs:?g_CIXaTmTrace@@3VCIXaTmTrace@@A; CIXaTmTrace g_CIXaTmTrace
0x18000afb0  mov     rax, [rax+8]
0x18000afb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb9  lea     r8, [rsp+88h+arg_10]
0x18000afc1  lea     rdx, IID_INameService
0x18000afc8  lea     rcx, CLSID_DTCUtil
0x18000afcf  call    cs:__imp_DllGetDTCUtilObject
0x18000afd5  test    eax, eax
0x18000afd7  jnz     loc_18000B227
0x18000afdd  mov     rax, [rsp+88h+arg_10]
0x18000afe5  mov     cs:?g_pXINameService@@3PEAUINameService@@EA, rax; INameService * g_pXINameService
0x18000afec  lea     r8, [rsp+88h+arg_10]
0x18000aff4  lea     rdx, IID_IConnectionManager
0x18000affb  lea     rcx, CLSID_DTCCM
0x18000b002  call    cs:__imp_DllGetDTCConnectionManager
0x18000b008  test    eax, eax
0x18000b00a  jnz     loc_18000B227
0x18000b010  mov     rcx, [rsp+88h+arg_10]
0x18000b018  mov     cs:?g_pXIConnectionManager@@3PEAUIConnectionManager@@EA, rcx; IConnectionManager * g_pXIConnectionManager
0x18000b01f  mov     rax, [rcx]
0x18000b022  lea     r8, [rsp+88h+arg_10]
0x18000b02a  lea     rdx, IID_IConnectionManagerConfig2
0x18000b031  mov     rax, [rax]
0x18000b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b039  test    eax, eax
0x18000b03b  jnz     loc_18000B227
0x18000b041  mov     rdi, [rsp+88h+arg_10]
0x18000b049  mov     byte ptr [rsp+88h+arg_20], r15b
0x18000b051  lea     rdx, [rsp+88h+arg_20]; bool *
0x18000b059  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18000b05e  cmp     byte ptr [rsp+88h+arg_20], r15b
0x18000b066  jnz     short loc_18000B08E
0x18000b068  cmp     [rsp+88h+arg_28], r15d
0x18000b070  jnz     short loc_18000B08E
0x18000b072  mov     rax, [rdi]
0x18000b075  mov     edx, 20h ; ' '
0x18000b07a  mov     rcx, rdi
0x18000b07d  mov     rax, [rax+78h]
0x18000b081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b086  test    eax, eax
0x18000b088  jnz     loc_18000B227
0x18000b08e  mov     ecx, 48h ; 'H'; Size
0x18000b093  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b098  mov     rdi, rax
0x18000b09b  mov     [rsp+88h+var_48], rax
0x18000b0a0  test    rax, rax
0x18000b0a3  jz      short loc_18000B0BE
0x18000b0a5  lea     rax, ??_7CIConnectionNotify@@6B@; const CIConnectionNotify::`vftable'
0x18000b0ac  mov     [rdi], rax
0x18000b0af  lea     rcx, [rdi+10h]; this
0x18000b0b3  call    ??0CSemExclusiveSL@@QEAA@K@Z; CSemExclusiveSL::CSemExclusiveSL(ulong)
0x18000b0b8  mov     [rdi+8], r15d
0x18000b0bc  jmp     short loc_18000B0C1
0x18000b0be  mov     rdi, r15
0x18000b0c1  test    rdi, rdi
0x18000b0c4  jnz     short loc_18000B0D0
0x18000b0c6  mov     eax, 8007000Eh
0x18000b0cb  jmp     loc_18000B227
0x18000b0d0  mov     rcx, cs:?g_pXIConnectionManager@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pXIConnectionManager
0x18000b0d7  mov     rax, [rcx]
0x18000b0da  mov     r9d, 1
0x18000b0e0  mov     r8, rdi
0x18000b0e3  mov     rdx, rbx
0x18000b0e6  mov     rax, [rax+18h]
0x18000b0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ef  test    eax, eax
0x18000b0f1  jnz     loc_18000B227
0x18000b0f7  test    esi, esi
0x18000b0f9  jz      loc_18000B21E
0x18000b0ff  lea     rax, [rsp+88h+var_50]
0x18000b104  mov     [rsp+88h+ppv], rax; ppv
0x18000b109  lea     r9, _GUID_3bbe95db_c53f_11d1_b3a2_00a0c9083365; riid
0x18000b110  xor     r8d, r8d; pvReserved
0x18000b113  mov     edx, 1; dwClsContext
0x18000b118  lea     rcx, _GUID_3bbe95da_c53f_11d1_b3a2_00a0c9083365; rclsid
0x18000b11f  call    cs:__imp_CoGetClassObject
0x18000b125  mov     ebx, eax
0x18000b127  test    eax, eax
0x18000b129  js      short loc_18000B158
0x18000b12b  mov     rcx, [rsp+88h+var_50]
0x18000b130  mov     rax, [rcx]
0x18000b133  mov     r9, rbp
0x18000b136  xor     r8d, r8d
0x18000b139  mov     rdx, r14
0x18000b13c  mov     rax, [rax+18h]
0x18000b140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b145  mov     ebx, eax
0x18000b147  mov     rcx, [rsp+88h+var_50]
0x18000b14c  mov     rax, [rcx]
0x18000b14f  mov     rax, [rax+10h]
0x18000b153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b158  test    ebx, ebx
0x18000b15a  jz      short loc_18000B163
0x18000b15c  mov     eax, ebx
0x18000b15e  jmp     loc_18000B227
0x18000b163  lea     rax, ?g_pIGatewayInstanceCF@@3PEAUIClassFactory@@EA; IClassFactory * g_pIGatewayInstanceCF
0x18000b16a  mov     [rsp+88h+ppv], rax; ppv
0x18000b16f  lea     r9, IID_IClassFactory; riid
0x18000b176  xor     r8d, r8d; pvReserved
0x18000b179  mov     edx, 1; dwClsContext
0x18000b17e  lea     rcx, _GUID_3bbe95fb_c53f_11d1_b3a2_00a0c9083365; rclsid
0x18000b185  call    cs:__imp_CoGetClassObject
0x18000b18b  cmp     cs:?g_pIGatewayInstanceCF@@3PEAUIClassFactory@@EA, 0; IClassFactory * g_pIGatewayInstanceCF
0x18000b193  jz      loc_18000B227
0x18000b199  test    eax, eax
0x18000b19b  js      loc_18000B227
0x18000b1a1  lea     rax, ?g_pIGatewayInstanceScanCF@@3PEAUIClassFactory@@EA; IClassFactory * g_pIGatewayInstanceScanCF
0x18000b1a8  mov     [rsp+88h+ppv], rax; ppv
0x18000b1ad  lea     r9, IID_IClassFactory; riid
0x18000b1b4  xor     r8d, r8d; pvReserved
0x18000b1b7  mov     edx, 1; dwClsContext
0x18000b1bc  lea     rcx, _GUID_3bbe95fe_c53f_11d1_b3a2_00a0c9083365; rclsid
0x18000b1c3  call    cs:__imp_CoGetClassObject
0x18000b1c9  cmp     cs:?g_pIGatewayInstanceScanCF@@3PEAUIClassFactory@@EA, 0; IClassFactory * g_pIGatewayInstanceScanCF
0x18000b1d1  jz      short loc_18000B227
0x18000b1d3  test    eax, eax
0x18000b1d5  js      short loc_18000B227
0x18000b1d7  mov     rcx, [rsp+88h+var_58]; struct ITmInstance *
0x18000b1dc  call    ?InitCryptoKey@@YAJPEAUITmInstance@@@Z; InitCryptoKey(ITmInstance *)
0x18000b1e1  test    eax, eax
0x18000b1e3  jnz     short loc_18000B227
0x18000b1e5  mov     eax, cs:?g_dwXaTmMaxWarmRecoveryInterval@@3KA; ulong g_dwXaTmMaxWarmRecoveryInterval
0x18000b1eb  cmp     cs:?g_dwXaTmMinWarmRecoveryInterval@@3KA, eax; ulong g_dwXaTmMinWarmRecoveryInterval
0x18000b1f1  jbe     short loc_18000B21E
0x18000b1f3  mov     r8d, 12Eh; int
0x18000b1f9  lea     rdx, aComComplusDtcD_55; "com\\complus\\dtc\\dtc\\xatm\\src\\xatm"...
0x18000b200  mov     ecx, 8000D047h; unsigned int
0x18000b205  call    ?XA_TRACE_WARNING@@YAXKPEADH@Z; XA_TRACE_WARNING(ulong,char *,int)
0x18000b20a  mov     cs:?g_dwXaTmMinWarmRecoveryInterval@@3KA, 3A98h; ulong g_dwXaTmMinWarmRecoveryInterval
0x18000b214  mov     cs:?g_dwXaTmMaxWarmRecoveryInterval@@3KA, 927C0h; ulong g_dwXaTmMaxWarmRecoveryInterval
0x18000b21e  xor     eax, eax
0x18000b220  jmp     short loc_18000B227
0x18000b222  mov     eax, 80004005h
0x18000b227  add     rsp, 58h
0x18000b22b  pop     r15
0x18000b22d  pop     r14
0x18000b22f  pop     rdi
0x18000b230  pop     rsi
0x18000b231  pop     rbp
0x18000b232  pop     rbx
0x18000b233  retn
```
