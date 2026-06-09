# PSLookupPropertyHandlerCLSIDAndPath

- ea: `0x180050190`
- end: `0x180050456`
- name: `PSLookupPropertyHandlerCLSIDAndPath`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007b9d0`

## callees

- `0x18002568c`
- `0x180050190`
- `0x18005045c`
- `0x180050500`
- `0x180050544`
- `0x18005063c`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050343`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800503b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050343`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800503b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050233`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800503e8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050233`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800503e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18005020b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18005020b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800503db`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180050426`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800503db`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180050426`

## string_xrefs

- `0x180050319`: `Software\Microsoft\Windows\CurrentVersion\PropertySystem\SystemPropertyHandlers`

## pseudocode

```c
__int64 __fastcall PSLookupPropertyHandlerCLSIDAndPath(const WCHAR *a1, GUID *a2, _DWORD *a3, _QWORD *a4)
{
  LPCLSID v5; // rax
  unsigned int v6; // edx
  const WCHAR *ExtensionW; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  struct wil::details::IFunctorHost *v10; // r8
  LSTATUS ValueW; // eax
  signed int v12; // ecx
  LSTATUS v13; // eax
  signed int v14; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v18; // [rsp+60h] [rbp-A0h]
  LPCLSID pclsid; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpValue; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v21; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER v24; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  void **v27; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-48h] BYREF
  int v29; // [rsp+C4h] [rbp-3Ch]
  _QWORD *v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR *p_lpValue; // [rsp+E8h] [rbp-18h]
  LPCLSID *p_pclsid; // [rsp+F0h] [rbp-10h]
  _DWORD **v35; // [rsp+F8h] [rbp-8h]
  _QWORD *v36; // [rsp+100h] [rbp+0h]
  LARGE_INTEGER *v37; // [rsp+108h] [rbp+8h]
  LARGE_INTEGER *p_PerformanceCount; // [rsp+110h] [rbp+10h]
  WCHAR SubKey[264]; // [rsp+130h] [rbp+30h] BYREF
  _UNKNOWN *retaddr; // [rsp+368h] [rbp+268h]

  pclsid = a2;
  v21 = a3;
  v22 = a4;
  v5 = a2;
  if ( a4 )
  {
    *a4 = 0;
    v5 = pclsid;
  }
  v6 = -2147467261;
  v23 = -2147467261;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        *v5 = GUID_NULL;
        *v21 = 0;
        ExtensionW = PathFindExtensionW(a1);
        v6 = -2147467259;
        lpValue = ExtensionW;
        v23 = -2147467259;
        if ( *ExtensionW )
        {
          PerformanceCount.QuadPart = 0;
          v24.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          LOBYTE(v8) = 2;
          *(_QWORD *)sz = &v23;
          LOBYTE(v9) = 1;
          p_lpValue = &lpValue;
          p_pclsid = &pclsid;
          v35 = &v21;
          v36 = &v22;
          v37 = &v24;
          p_PerformanceCount = &PerformanceCount;
          v17[0] = retaddr;
          v17[1] = "onecoreuap\\shell\\propsys\\getpropertystore.cpp";
          v18 = 420;
          v17[2] = 0;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialPropertyHandlers>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_CentennialPropertyHandlers>::GetImpl'::`2'::impl,
            v9,
            v8);
          v26[0] = &off_1800B1F50;
          v26[1] = sz;
          v27 = &wil::details::FeatureFunctorHost::`vftable';
          wil::ThreadErrorContext::ThreadErrorContext((wil::ThreadErrorContext *)&v28);
          v31 = 8221526;
          v30 = v17;
          wil::details::RunFunctor((wil::details *)v26, (struct wil::details::IFunctor *)&v27, v10);
          if ( v28 )
            *(_DWORD *)(v28 + 16) = v29;
          v6 = v23;
          if ( v23 < 0 )
          {
            pcbData = 78;
            ValueW = RegGetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\SystemPropertyHandlers",
                       lpValue,
                       2u,
                       0,
                       sz,
                       &pcbData);
            v12 = ValueW;
            if ( ValueW )
            {
              sz[0] = 0;
              if ( ValueW > 0 )
                v12 = (unsigned __int16)ValueW | 0x80070000;
            }
            v23 = v12;
            if ( v12 < 0 || (v23 = CLSIDFromString(sz, pclsid), v23 < 0) )
            {
              v23 = StringCchPrintfW(
                      SubKey,
                      0x104u,
                      L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertyHandlers\\%s",
                      lpValue);
              if ( v23 >= 0 )
              {
                pcbData = 78;
                v13 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, 0, 2u, 0, sz, &pcbData);
                v14 = v13;
                if ( v13 )
                {
                  sz[0] = 0;
                  if ( v13 > 0 )
                    v14 = (unsigned __int16)v13 | 0x80070000;
                }
                v23 = v14;
                if ( v14 >= 0 )
                  v23 = CLSIDFromString(sz, pclsid);
              }
            }
            QueryPerformanceCounter(&v24);
            FileExplorerAggregateTelemetry::PropertyLookupWin32Aggregate(PerformanceCount, v24, v23);
            return (unsigned int)v23;
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180050190  push    rbp
0x180050192  push    rbx
0x180050193  lea     rbp, [rsp-258h]
0x18005019b  sub     rsp, 358h
0x1800501a2  mov     rax, cs:__security_cookie
0x1800501a9  xor     rax, rsp
0x1800501ac  mov     [rbp+260h+var_20], rax
0x1800501b3  xor     ebx, ebx
0x1800501b5  mov     [rsp+360h+pclsid], rdx
0x1800501ba  mov     [rsp+360h+var_2E8], r8
0x1800501bf  mov     r10, rdx
0x1800501c2  mov     [rbp+260h+var_2E0], r9
0x1800501c6  mov     rax, rdx
0x1800501c9  test    r9, r9
0x1800501cc  jz      short loc_1800501D6
0x1800501ce  mov     [r9], rbx
0x1800501d1  mov     rax, [rsp+360h+pclsid]
0x1800501d6  mov     edx, 80004003h
0x1800501db  mov     [rbp+260h+var_2D8], edx
0x1800501de  test    rcx, rcx
0x1800501e1  jz      loc_180050402
0x1800501e7  test    r10, r10
0x1800501ea  jz      loc_180050402
0x1800501f0  test    r8, r8
0x1800501f3  jz      loc_180050402
0x1800501f9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180050200  movdqu  xmmword ptr [rax], xmm0
0x180050204  mov     rax, [rsp+360h+var_2E8]
0x180050209  mov     [rax], ebx
0x18005020b  call    cs:__imp_PathFindExtensionW
0x180050211  mov     edx, 80004005h
0x180050216  mov     [rsp+360h+lpValue], rax
0x18005021b  mov     [rbp+260h+var_2D8], edx
0x18005021e  cmp     [rax], bx
0x180050221  jz      loc_180050402
0x180050227  lea     rcx, [rbp+260h+PerformanceCount]; lpPerformanceCount
0x18005022b  mov     qword ptr [rbp+260h+PerformanceCount], rbx
0x18005022f  mov     qword ptr [rbp+260h+var_2D0], rbx
0x180050233  call    cs:__imp_QueryPerformanceCounter
0x180050239  lea     rax, [rbp+260h+var_2D8]
0x18005023d  mov     r8b, 2
0x180050240  mov     qword ptr [rbp+260h+sz], rax
0x180050244  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialPropertyHandlers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialPropertyHandlers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialPropertyHandlers> `wil::Feature<__WilFeatureTraits_Feature_CentennialPropertyHandlers>::GetImpl(void)'::`2'::impl
0x18005024b  lea     rax, [rsp+360h+lpValue]
0x180050250  mov     dl, 1
0x180050252  mov     [rbp+260h+var_278], rax
0x180050256  lea     rax, [rsp+360h+pclsid]
0x18005025b  mov     [rbp+260h+var_270], rax
0x18005025f  lea     rax, [rsp+360h+var_2E8]
0x180050264  mov     [rbp+260h+var_268], rax
0x180050268  lea     rax, [rbp+260h+var_2E0]
0x18005026c  mov     [rbp+260h+var_260], rax
0x180050270  lea     rax, [rbp+260h+var_2D0]
0x180050274  mov     [rbp+260h+var_258], rax
0x180050278  lea     rax, [rbp+260h+PerformanceCount]
0x18005027c  mov     [rbp+260h+var_250], rax
0x180050280  mov     rax, [rbp+268h]
0x180050287  mov     [rsp+360h+var_318], rax
0x18005028c  lea     rax, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180050293  mov     [rsp+360h+var_310], rax
0x180050298  mov     eax, 1A4h
0x18005029d  mov     [rsp+360h+var_300], ax
0x1800502a2  mov     [rsp+360h+var_308], rbx
0x1800502a7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialPropertyHandlers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialPropertyHandlers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800502ac  lea     rax, off_1800B1F50
0x1800502b3  mov     [rbp+260h+var_2C0], rax
0x1800502b7  lea     rcx, [rbp+260h+var_2A8]; this
0x1800502bb  lea     rax, [rbp+260h+sz]
0x1800502bf  mov     [rbp+260h+var_2B8], rax
0x1800502c3  lea     rax, ??_7FeatureFunctorHost@details@wil@@6B@; const wil::details::FeatureFunctorHost::`vftable'
0x1800502ca  mov     [rbp+260h+var_2B0], rax
0x1800502ce  call    ??0ThreadErrorContext@wil@@QEAA@XZ; wil::ThreadErrorContext::ThreadErrorContext(void)
0x1800502d3  lea     rax, [rsp+360h+var_318]
0x1800502d8  mov     [rbp+260h+var_290], 7D7356h
0x1800502df  lea     rdx, [rbp+260h+var_2B0]; struct wil::details::IFunctor *
0x1800502e3  mov     [rbp+260h+var_298], rax
0x1800502e7  lea     rcx, [rbp+260h+var_2C0]; this
0x1800502eb  call    ?RunFunctor@details@wil@@YAJAEAUIFunctor@12@AEAUIFunctorHost@12@@Z; wil::details::RunFunctor(wil::details::IFunctor &,wil::details::IFunctorHost &)
0x1800502f0  mov     rcx, [rbp+260h+var_2A8]
0x1800502f4  test    rcx, rcx
0x1800502f7  jz      short loc_1800502FF
0x1800502f9  mov     eax, [rbp+260h+var_29C]
0x1800502fc  mov     [rcx+10h], eax
0x1800502ff  mov     edx, [rbp+260h+var_2D8]
0x180050302  test    edx, edx
0x180050304  jns     loc_180050402
0x18005030a  mov     r8, [rsp+360h+lpValue]; lpValue
0x18005030f  lea     rax, [rsp+360h+var_320]
0x180050314  mov     [rsp+360h+pcbData], rax; pcbData
0x180050319  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180050320  lea     rax, [rbp+260h+sz]
0x180050324  mov     [rsp+360h+var_320], 4Eh ; 'N'
0x18005032c  mov     [rsp+360h+pvData], rax; pvData
0x180050331  mov     r9d, 2; dwFlags
0x180050337  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005033e  mov     [rsp+360h+pdwType], rbx; pdwType
0x180050343  call    cs:__imp_RegGetValueW
0x180050349  mov     ecx, eax
0x18005034b  test    eax, eax
0x18005034d  jz      short loc_180050359
0x18005034f  mov     [rbp+260h+sz], bx
0x180050353  jg      loc_18005043A
0x180050359  mov     [rbp+260h+var_2D8], ecx
0x18005035c  test    ecx, ecx
0x18005035e  jns     loc_18005041D
0x180050364  mov     r9, [rsp+360h+lpValue]
0x180050369  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180050370  mov     edx, 104h; unsigned __int64
0x180050375  lea     rcx, [rbp+260h+SubKey]; unsigned __int16 *
0x180050379  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005037e  mov     [rbp+260h+var_2D8], eax
0x180050381  test    eax, eax
0x180050383  js      short loc_1800503E4
0x180050385  lea     rax, [rsp+360h+var_320]
0x18005038a  mov     [rsp+360h+var_320], 4Eh ; 'N'
0x180050392  mov     [rsp+360h+pcbData], rax; pcbData
0x180050397  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x18005039b  lea     rax, [rbp+260h+sz]
0x18005039f  mov     r9d, 2; dwFlags
0x1800503a5  mov     [rsp+360h+pvData], rax; pvData
0x1800503aa  xor     r8d, r8d; lpValue
0x1800503ad  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800503b4  mov     [rsp+360h+pdwType], rbx; pdwType
0x1800503b9  call    cs:__imp_RegGetValueW
0x1800503bf  mov     ecx, eax
0x1800503c1  test    eax, eax
0x1800503c3  jz      short loc_1800503CB
0x1800503c5  mov     [rbp+260h+sz], bx
0x1800503c9  jg      short loc_180050448
0x1800503cb  mov     [rbp+260h+var_2D8], ecx
0x1800503ce  test    ecx, ecx
0x1800503d0  js      short loc_1800503E4
0x1800503d2  mov     rdx, [rsp+360h+pclsid]; pclsid
0x1800503d7  lea     rcx, [rbp+260h+sz]; lpsz
0x1800503db  call    cs:__imp_CLSIDFromString
0x1800503e1  mov     [rbp+260h+var_2D8], eax
0x1800503e4  lea     rcx, [rbp+260h+var_2D0]; lpPerformanceCount
0x1800503e8  call    cs:__imp_QueryPerformanceCounter
0x1800503ee  mov     r8d, [rbp+260h+var_2D8]; int
0x1800503f2  mov     rdx, qword ptr [rbp+260h+var_2D0]; union _LARGE_INTEGER
0x1800503f6  mov     rcx, qword ptr [rbp+260h+PerformanceCount]; union _LARGE_INTEGER
0x1800503fa  call    ?PropertyLookupWin32Aggregate@FileExplorerAggregateTelemetry@@SAXT_LARGE_INTEGER@@0J@Z; FileExplorerAggregateTelemetry::PropertyLookupWin32Aggregate(_LARGE_INTEGER,_LARGE_INTEGER,long)
0x1800503ff  mov     edx, [rbp+260h+var_2D8]
0x180050402  mov     eax, edx
0x180050404  mov     rcx, [rbp+260h+var_20]
0x18005040b  xor     rcx, rsp; StackCookie
0x18005040e  call    __security_check_cookie
0x180050413  add     rsp, 358h
0x18005041a  pop     rbx
0x18005041b  pop     rbp
0x18005041c  retn
0x18005041d  mov     rdx, [rsp+360h+pclsid]; pclsid
0x180050422  lea     rcx, [rbp+260h+sz]; lpsz
0x180050426  call    cs:__imp_CLSIDFromString
0x18005042c  mov     [rbp+260h+var_2D8], eax
0x18005042f  mov     ecx, eax
0x180050431  test    eax, eax
0x180050433  jns     short loc_1800503E4
0x180050435  jmp     loc_180050364
0x18005043a  movzx   ecx, ax
0x18005043d  or      ecx, 80070000h
0x180050443  jmp     loc_180050359
0x180050448  movzx   ecx, ax
0x18005044b  or      ecx, 80070000h
0x180050451  jmp     loc_1800503CB
```
