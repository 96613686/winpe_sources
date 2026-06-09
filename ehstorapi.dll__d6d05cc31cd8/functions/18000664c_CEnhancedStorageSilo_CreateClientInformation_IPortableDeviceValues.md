# CEnhancedStorageSilo::CreateClientInformation(IPortableDeviceValues * *)

- ea: `0x18000664c`
- end: `0x180006981`
- name: `?CreateClientInformation@CEnhancedStorageSilo@@AEAAXPEAPEAUIPortableDeviceValues@@@Z`
- size: `821`
- prototype: `void(CEnhancedStorageSilo *__hidden this, struct IPortableDeviceValues **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007290`

## callees

- `0x180002064`
- `0x180003864`
- `0x180003924`
- `0x180003c54`
- `0x180003df0`
- `0x180003ed0`
- `0x1800061c8`
- `0x180006528`
- `0x18000664c`
- `0x1800080cc`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000679d`
- `msvcrt!wcsrchr` at `0x18000679d`
- `KERNEL32!GetLastError` at `0x180006734`
- `KERNEL32!GetLastError` at `0x180006734`
- `KERNEL32!GetModuleFileNameW` at `0x18000672a`
- `KERNEL32!GetModuleFileNameW` at `0x18000672a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800066e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800066e1`

## string_xrefs

- `0x1800066b6`: `CEnhancedStorageSilo::CreateClientInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEnhancedStorageSilo::CreateClientInformation(CEnhancedStorageSilo *this, LPVOID *a2)
{
  LPVOID *ppv; // rsi
  HRESULT Instance; // eax
  signed int LastError; // eax
  wchar_t *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // [rsp+30h] [rbp-368h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-360h] BYREF
  __int64 v14; // [rsp+40h] [rbp-358h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-350h] BYREF
  __int64 v16; // [rsp+50h] [rbp-348h] BYREF
  struct IPortableDeviceValues **v17; // [rsp+58h] [rbp-340h]
  _BYTE v18[272]; // [rsp+60h] [rbp-338h] BYREF
  WCHAR Filename[264]; // [rsp+170h] [rbp-228h] BYREF

  ppv = a2;
  v17 = (struct IPortableDeviceValues **)a2;
  v12 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, a2);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v18, "CEnhancedStorageSilo::CreateClientInformation", &v12);
  Instance = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &IID_IPortableDeviceValues, ppv);
  v12 = Instance;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
        (unsigned int)Instance);
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v14);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&Str);
    try
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v14, L"ESAPI");
      if ( GetModuleFileNameW(0, Filename, 0x104u) )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&Str, Filename);
        v5 = wcsrchr(Str, 0x5Cu);
        if ( v5 )
          v6 = v5 - Str;
        else
          LODWORD(v6) = -1;
        ATL::CSimpleStringT<unsigned short,0>::Append(&v14, L"::", 2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          &Str,
          &v16,
          (unsigned int)(v6 + 1),
          (unsigned int)(*((_DWORD *)Str - 4) - (v6 + 1)));
        v7 = v16;
        ATL::CSimpleStringT<unsigned short,0>::Append(&v14, v16, *(unsigned int *)(v16 - 16));
        ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v12 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
            (unsigned int)LastError);
      }
      v8 = v14;
      v9 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)*ppv + 56LL))(
             *ppv,
             &WPD_CLIENT_NAME,
             v14);
      v12 = v9;
      if ( v9 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
          (unsigned int)v9);
    }
    catch ( ATL::CAtlException v15 )
    {
      v12 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v15);
      v8 = v14;
      ppv = (LPVOID *)v17;
    }
    v10 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)*ppv + 56LL))(
            *ppv,
            &WPD_CLIENT_EVENT_COOKIE,
            v8);
    v12 = v10;
    if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
        (unsigned int)v10);
    v11 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)*ppv + 72LL))(
            *ppv,
            &WPD_CLIENT_SECURITY_QUALITY_OF_SERVICE,
            0x20000);
    v12 = v11;
    if ( v11 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
        (unsigned int)v11);
    ATL::CStringData::Release((ATL::CStringData *)(Str - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
  }
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v18);
}

```

## disassembly

```asm
0x18000664c  mov     [rsp+arg_0], rbx
0x180006651  mov     [rsp+arg_10], rsi
0x180006656  push    rdi
0x180006657  sub     rsp, 390h
0x18000665e  mov     rax, cs:__security_cookie
0x180006665  xor     rax, rsp
0x180006668  mov     [rsp+398h+var_18], rax
0x180006670  mov     rsi, rdx
0x180006673  mov     [rsp+398h+var_340], rdx
0x180006678  mov     [rsp+398h+var_368], 0
0x180006680  lea     rdi, WPP_GLOBAL_Control
0x180006687  mov     rcx, cs:WPP_GLOBAL_Control
0x18000668e  cmp     rcx, rdi
0x180006691  jz      short loc_1800066B1
0x180006693  test    byte ptr [rcx+1Ch], 10h
0x180006697  jz      short loc_1800066B1
0x180006699  mov     edx, 3Bh ; ';'
0x18000669e  mov     r9, rsi
0x1800066a1  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800066a8  mov     rcx, [rcx+10h]
0x1800066ac  call    WPP_SF_q
0x1800066b1  lea     r8, [rsp+398h+var_368]; int *
0x1800066b6  lea     rdx, aCenhancedstora_4; "CEnhancedStorageSilo::CreateClientInfor"...
0x1800066bd  lea     rcx, [rsp+398h+var_338]; this
0x1800066c2  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x1800066c7  nop
0x1800066c8  mov     [rsp+398h+ppv], rsi; ppv
0x1800066cd  lea     r9, IID_IPortableDeviceValues; riid
0x1800066d4  xor     edx, edx; pUnkOuter
0x1800066d6  lea     r8d, [rdx+1]; dwClsContext
0x1800066da  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x1800066e1  call    cs:__imp_CoCreateInstance
0x1800066e7  mov     [rsp+398h+var_368], eax
0x1800066eb  test    eax, eax
0x1800066ed  js      loc_180006927
0x1800066f3  lea     rcx, [rsp+398h+var_358]
0x1800066f8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800066fd  nop
0x1800066fe  lea     rcx, [rsp+398h+Str]
0x180006703  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006708  nop
0x180006709  lea     rdx, aEsapi; "ESAPI"
0x180006710  lea     rcx, [rsp+398h+var_358]
0x180006715  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000671a  mov     r8d, 104h; nSize
0x180006720  lea     rdx, [rsp+398h+Filename]; lpFilename
0x180006728  xor     ecx, ecx; hModule
0x18000672a  call    cs:__imp_GetModuleFileNameW
0x180006730  test    eax, eax
0x180006732  jnz     short loc_180006781
0x180006734  call    cs:__imp_GetLastError
0x18000673a  test    eax, eax
0x18000673c  jle     short loc_180006746
0x18000673e  movzx   eax, ax
0x180006741  or      eax, 80070000h
0x180006746  mov     [rsp+398h+var_368], eax
0x18000674a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006751  cmp     rcx, rdi
0x180006754  jz      loc_18000680F
0x18000675a  test    byte ptr [rcx+1Ch], 4
0x18000675e  jz      loc_18000680F
0x180006764  mov     edx, 3Ch ; '<'
0x180006769  mov     r9d, eax
0x18000676c  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006773  mov     rcx, [rcx+10h]
0x180006777  call    WPP_SF_d
0x18000677c  jmp     loc_18000680F
0x180006781  lea     rdx, [rsp+398h+Filename]
0x180006789  lea     rcx, [rsp+398h+Str]
0x18000678e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180006793  mov     edx, 5Ch ; '\'; Ch
0x180006798  mov     rcx, [rsp+398h+Str]; Str
0x18000679d  call    cs:__imp_wcsrchr
0x1800067a3  mov     rbx, rax
0x1800067a6  test    rax, rax
0x1800067a9  jnz     short loc_1800067B0
0x1800067ab  or      ebx, 0FFFFFFFFh
0x1800067ae  jmp     short loc_1800067B8
0x1800067b0  sub     rbx, [rsp+398h+Str]
0x1800067b5  sar     rbx, 1
0x1800067b8  mov     r8d, 2
0x1800067be  lea     rdx, asc_18000F65C; "::"
0x1800067c5  lea     rcx, [rsp+398h+var_358]
0x1800067ca  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800067cf  lea     r8d, [rbx+1]
0x1800067d3  mov     rax, [rsp+398h+Str]
0x1800067d8  mov     r9d, [rax-10h]
0x1800067dc  sub     r9d, r8d
0x1800067df  lea     rdx, [rsp+398h+var_348]
0x1800067e4  lea     rcx, [rsp+398h+Str]
0x1800067e9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1800067ee  nop
0x1800067ef  mov     rbx, [rsp+398h+var_348]
0x1800067f4  mov     r8d, [rbx-10h]
0x1800067f8  mov     rdx, rbx
0x1800067fb  lea     rcx, [rsp+398h+var_358]
0x180006800  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180006805  nop
0x180006806  lea     rcx, [rbx-18h]; this
0x18000680a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000680f  mov     rcx, [rsi]
0x180006812  mov     rax, [rcx]
0x180006815  mov     rbx, [rsp+398h+var_358]
0x18000681a  mov     r8, rbx
0x18000681d  lea     rdx, WPD_CLIENT_NAME
0x180006824  mov     rax, [rax+38h]
0x180006828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682d  mov     [rsp+398h+var_368], eax
0x180006831  test    eax, eax
0x180006833  jns     short loc_180006860
0x180006835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000683c  cmp     rcx, rdi
0x18000683f  jz      short loc_180006860
0x180006841  test    byte ptr [rcx+1Ch], 4
0x180006845  jz      short loc_180006860
0x180006847  mov     edx, 3Dh ; '='
0x18000684c  mov     r9d, eax
0x18000684f  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006856  mov     rcx, [rcx+10h]
0x18000685a  call    WPP_SF_d
0x18000685f  nop
0x180006860  jmp     short loc_180006873
0x180006862  lea     rdi, WPP_GLOBAL_Control
0x180006869  mov     rbx, [rsp+398h+var_358]
0x18000686e  mov     rsi, [rsp+398h+var_340]
0x180006873  mov     rcx, [rsi]
0x180006876  mov     rax, [rcx]
0x180006879  mov     r8, rbx
0x18000687c  lea     rdx, WPD_CLIENT_EVENT_COOKIE
0x180006883  mov     rax, [rax+38h]
0x180006887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000688c  mov     [rsp+398h+var_368], eax
0x180006890  test    eax, eax
0x180006892  jns     short loc_1800068BE
0x180006894  mov     rcx, cs:WPP_GLOBAL_Control
0x18000689b  cmp     rcx, rdi
0x18000689e  jz      short loc_1800068BE
0x1800068a0  test    byte ptr [rcx+1Ch], 4
0x1800068a4  jz      short loc_1800068BE
0x1800068a6  mov     edx, 3Fh ; '?'
0x1800068ab  mov     r9d, eax
0x1800068ae  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800068b5  mov     rcx, [rcx+10h]
0x1800068b9  call    WPP_SF_d
0x1800068be  mov     rcx, [rsi]
0x1800068c1  mov     rax, [rcx]
0x1800068c4  mov     r8d, 20000h
0x1800068ca  lea     rdx, WPD_CLIENT_SECURITY_QUALITY_OF_SERVICE
0x1800068d1  mov     rax, [rax+48h]
0x1800068d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068da  mov     [rsp+398h+var_368], eax
0x1800068de  test    eax, eax
0x1800068e0  jns     short loc_18000690D
0x1800068e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068e9  cmp     rcx, rdi
0x1800068ec  jz      short loc_18000690D
0x1800068ee  test    byte ptr [rcx+1Ch], 4
0x1800068f2  jz      short loc_18000690D
0x1800068f4  mov     edx, 40h ; '@'
0x1800068f9  mov     r9d, eax
0x1800068fc  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006903  mov     rcx, [rcx+10h]
0x180006907  call    WPP_SF_d
0x18000690c  nop
0x18000690d  mov     rcx, [rsp+398h+Str]
0x180006912  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006916  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000691b  nop
0x18000691c  lea     rcx, [rbx-18h]; this
0x180006920  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006925  jmp     short loc_180006952
0x180006927  mov     rcx, cs:WPP_GLOBAL_Control
0x18000692e  cmp     rcx, rdi
0x180006931  jz      short loc_180006952
0x180006933  test    byte ptr [rcx+1Ch], 2
0x180006937  jz      short loc_180006952
0x180006939  mov     edx, 41h ; 'A'
0x18000693e  mov     r9d, eax
0x180006941  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006948  mov     rcx, [rcx+10h]
0x18000694c  call    WPP_SF_d
0x180006951  nop
0x180006952  lea     rcx, [rsp+398h+var_338]; this
0x180006957  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x18000695c  mov     rcx, [rsp+398h+var_18]
0x180006964  xor     rcx, rsp; StackCookie
0x180006967  call    __security_check_cookie
0x18000696c  lea     r11, [rsp+398h+var_8]
0x180006974  mov     rbx, [r11+10h]
0x180006978  mov     rsi, [r11+20h]
0x18000697c  mov     rsp, r11
0x18000697f  pop     rdi
0x180006980  retn
```
