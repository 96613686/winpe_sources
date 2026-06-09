# GetKmdfVersion(ushort const *,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800554f8`
- end: `0x1800557d0`
- name: `?GetKmdfVersion@@YAJPEBGHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `728`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016224`
- `0x180055c90`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18000dcec`
- `0x18000fa50`
- `0x180016440`
- `0x1800538cc`
- `0x1800554f8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800555f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800555f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180055637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180055678`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180055637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180055678`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055798`

## string_xrefs

- `0x18005555d`: `Software\Microsoft\Windows Nt\CurrentVersion\WUDF\Services`
- `0x180055589`: `System\CurrentControlSet\Services`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetKmdfVersion(void *a1, int a2, void *a3)
{
  int v5; // edi
  WCHAR *v6; // rdx
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E8h]
  DWORD cbData; // [rsp+30h] [rbp-D8h] BYREF
  DWORD Type; // [rsp+34h] [rbp-D4h] BYREF
  int v20; // [rsp+38h] [rbp-D0h]
  BYTE v21[4]; // [rsp+3Ch] [rbp-CCh] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR SubKey[8]; // [rsp+50h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A8h]
  unsigned __int16 v26[64]; // [rsp+70h] [rbp-98h] BYREF

  try
  {
    *(_OWORD *)SubKey = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    SubKey[0] = 0;
    hKey = 0;
    *(_DWORD *)Data = 0;
    *(_DWORD *)v21 = 0;
    Type = 0;
    cbData = 0;
    if ( a2 )
    {
      std::wstring::append(SubKey, (void *)L"Software\\Microsoft\\Windows Nt\\CurrentVersion\\WUDF\\Services");
      std::wstring::append(SubKey, (void *)L"\\");
      std::wstring::append(SubKey, a1);
    }
    else
    {
      std::wstring::append(SubKey, L"System\\CurrentControlSet\\Services");
      std::wstring::append(SubKey, (void *)L"\\");
      std::wstring::append(SubKey, a1);
      std::wstring::append(SubKey, L"\\Parameters\\Wdf");
    }
  }
  catch ( std::bad_alloc )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetKmdfVersion", 266, "Out of memory");
    }
    else
    {
      AslLogCallPrintf(2, "GetKmdfVersion", 270, "Out of memory");
      if ( EnableDevInvStdErrLog )
      {
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "Error: %s, %u: ", "GetKmdfVersion", 270);
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "Out of memory");
        v16 = o___acrt_iob_func_0(2u);
        fprintf(v16, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Out of memory");
    }
    v20 = -2147024888;
    v5 = v20;
    goto LABEL_19;
  }
  v5 = -2147467259;
  v6 = *(WCHAR **)SubKey;
  if ( si128.m128i_i64[1] <= 7uLL )
    v6 = SubKey;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"WdfMajorVersion", 0, &Type, Data, &cbData)
      || (Type = 4, cbData = 4, RegQueryValueExW(hKey, L"WdfMinorVersion", 0, &Type, v21, &cbData)) )
    {
      v5 = 0;
    }
    else
    {
      LODWORD(phkResult) = *(_DWORD *)v21;
      v5 = StringCchPrintfW(v26, 0x40u, L"%d.%d", *(unsigned int *)Data, phkResult);
      if ( v5 >= 0 )
      {
        try
        {
          std::wstring::append(a3, v26);
        }
        catch ( std::bad_alloc )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
          {
            AslLogCallPrintf(1, "GetKmdfVersion", 338, "Out of memory");
          }
          else
          {
            AslLogCallPrintf(2, "GetKmdfVersion", 342, "Out of memory");
            if ( EnableDevInvStdErrLog )
            {
              v11 = o___acrt_iob_func_0(2u);
              fprintf(v11, "Error: %s, %u: ", "GetKmdfVersion", 342);
              v12 = o___acrt_iob_func_0(2u);
              fprintf(v12, "Out of memory");
              v13 = o___acrt_iob_func_0(2u);
              fprintf(v13, "\n");
            }
            if ( g_DeviceMapLogFunction )
              TraceMessageCallback(0x2000000, "Out of memory");
          }
          v20 = -2147024888;
          v5 = v20;
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
      {
        AslLogCallPrintf(1, "GetKmdfVersion", 321, "StringCchPrintf failed [%#x]", v5);
      }
      else
      {
        AslLogCallPrintf(2, "GetKmdfVersion", 325, "StringCchPrintf failed: 0x%x", v5);
        if ( EnableDevInvStdErrLog )
        {
          v7 = o___acrt_iob_func_0(2u);
          fprintf(v7, "Error: %s, %u: ", "GetKmdfVersion", 325);
          v8 = o___acrt_iob_func_0(2u);
          fprintf(v8, "StringCchPrintf failed: 0x%x", v5);
          v9 = o___acrt_iob_func_0(2u);
          fprintf(v9, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "StringCchPrintf failed: 0x%x", v5);
      }
    }
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(SubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800554f8  mov     [rsp+arg_8], rbx
0x1800554fd  mov     [rsp+arg_18], rsi
0x180055502  push    rdi
0x180055503  sub     rsp, 100h
0x18005550a  mov     rax, cs:__security_cookie
0x180055511  xor     rax, rsp
0x180055514  mov     [rsp+108h+var_18], rax
0x18005551c  mov     rsi, r8
0x18005551f  mov     rdi, rcx
0x180055522  xorps   xmm0, xmm0
0x180055525  movups  xmmword ptr [rsp+108h+SubKey], xmm0
0x18005552a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180055532  movdqu  [rsp+108h+var_A8], xmm1
0x180055538  xor     ebx, ebx
0x18005553a  mov     [rsp+108h+SubKey], bx
0x18005553f  mov     [rsp+108h+hKey], rbx
0x180055544  mov     dword ptr [rsp+108h+Data], ebx
0x180055548  mov     dword ptr [rsp+108h+var_CC], ebx
0x18005554c  mov     [rsp+108h+Type], ebx
0x180055550  mov     [rsp+108h+cbData], ebx
0x180055554  lea     rcx, [rsp+108h+SubKey]; Src
0x180055559  test    edx, edx
0x18005555b  jz      short loc_180055589
0x18005555d  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Nt\\Curren"...
0x180055564  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180055569  lea     rdx, SubBlock; "\\"
0x180055570  lea     rcx, [rsp+108h+SubKey]; Src
0x180055575  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005557a  mov     rdx, rdi; void *
0x18005557d  lea     rcx, [rsp+108h+SubKey]; Src
0x180055582  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180055587  jmp     short loc_1800555C5
0x180055589  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services"
0x180055590  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180055595  lea     rdx, SubBlock; "\\"
0x18005559c  lea     rcx, [rsp+108h+SubKey]; Src
0x1800555a1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800555a6  mov     rdx, rdi; void *
0x1800555a9  lea     rcx, [rsp+108h+SubKey]; Src
0x1800555ae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800555b3  lea     rdx, aParametersWdf; "\\Parameters\\Wdf"
0x1800555ba  lea     rcx, [rsp+108h+SubKey]; Src
0x1800555bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800555c4  nop
0x1800555c5  mov     edi, 80004005h
0x1800555ca  cmp     qword ptr [rsp+108h+var_A8+8], 7
0x1800555d0  mov     rdx, qword ptr [rsp+108h+SubKey]
0x1800555d5  ja      short loc_1800555DC
0x1800555d7  lea     rdx, [rsp+108h+SubKey]; lpSubKey
0x1800555dc  lea     rax, [rsp+108h+hKey]
0x1800555e1  mov     [rsp+108h+phkResult], rax; phkResult
0x1800555e6  mov     r9d, 20019h; samDesired
0x1800555ec  xor     r8d, r8d; ulOptions
0x1800555ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800555f6  call    cs:__imp_RegOpenKeyExW
0x1800555fc  test    eax, eax
0x1800555fe  jnz     loc_18005578E
0x180055604  lea     edi, [rax+4]
0x180055607  mov     [rsp+108h+Type], edi
0x18005560b  mov     [rsp+108h+cbData], edi
0x18005560f  lea     rax, [rsp+108h+cbData]
0x180055614  mov     [rsp+108h+lpcbData], rax; lpcbData
0x180055619  lea     rax, [rsp+108h+Data]
0x18005561e  mov     [rsp+108h+phkResult], rax; lpData
0x180055623  lea     r9, [rsp+108h+Type]; lpType
0x180055628  xor     r8d, r8d; lpReserved
0x18005562b  lea     rdx, aWdfmajorversio; "WdfMajorVersion"
0x180055632  mov     rcx, [rsp+108h+hKey]; hKey
0x180055637  call    cs:__imp_RegQueryValueExW
0x18005563d  test    eax, eax
0x18005563f  jz      short loc_180055648
0x180055641  mov     edi, ebx
0x180055643  jmp     loc_18005578E
0x180055648  mov     [rsp+108h+Type], edi
0x18005564c  mov     [rsp+108h+cbData], edi
0x180055650  lea     rax, [rsp+108h+cbData]
0x180055655  mov     [rsp+108h+lpcbData], rax; lpcbData
0x18005565a  lea     rax, [rsp+108h+var_CC]
0x18005565f  mov     [rsp+108h+phkResult], rax; lpData
0x180055664  lea     r9, [rsp+108h+Type]; lpType
0x180055669  xor     r8d, r8d; lpReserved
0x18005566c  lea     rdx, aWdfminorversio; "WdfMinorVersion"
0x180055673  mov     rcx, [rsp+108h+hKey]; hKey
0x180055678  call    cs:__imp_RegQueryValueExW
0x18005567e  test    eax, eax
0x180055680  jnz     short loc_180055641
0x180055682  mov     eax, dword ptr [rsp+108h+var_CC]
0x180055686  mov     dword ptr [rsp+108h+phkResult], eax
0x18005568a  mov     r9d, dword ptr [rsp+108h+Data]
0x18005568f  lea     r8, aDD; "%d.%d"
0x180055696  mov     edx, 40h ; '@'; unsigned __int64
0x18005569b  lea     rcx, [rsp+108h+var_98]; unsigned __int16 *
0x1800556a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800556a5  mov     edi, eax
0x1800556a7  test    eax, eax
0x1800556a9  jns     loc_18005577A
0x1800556af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800556b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800556bb  mov     dword ptr [rsp+108h+phkResult], edi
0x1800556bf  lea     rdx, aGetkmdfversion; "GetKmdfVersion"
0x1800556c6  test    al, al
0x1800556c8  jz      short loc_1800556E6
0x1800556ca  lea     r9, aStringcchprint_3; "StringCchPrintf failed [%#x]"
0x1800556d1  mov     r8d, 141h
0x1800556d7  mov     ecx, 1
0x1800556dc  call    AslLogCallPrintf
0x1800556e1  jmp     loc_18005578E
0x1800556e6  lea     rsi, aStringcchprint_6; "StringCchPrintf failed: 0x%x"
0x1800556ed  mov     r9, rsi
0x1800556f0  mov     r8d, 145h
0x1800556f6  mov     ecx, 2
0x1800556fb  call    AslLogCallPrintf
0x180055700  cmp     cs:EnableDevInvStdErrLog, ebx
0x180055706  jz      short loc_18005575F
0x180055708  mov     ecx, 2; Ix
0x18005570d  call    _o___acrt_iob_func_0
0x180055712  mov     rcx, rax; Stream
0x180055715  mov     r9d, 145h
0x18005571b  lea     r8, aGetkmdfversion; "GetKmdfVersion"
0x180055722  lea     rdx, Format; "Error: %s, %u: "
0x180055729  call    fprintf
0x18005572e  mov     ecx, 2; Ix
0x180055733  call    _o___acrt_iob_func_0
0x180055738  mov     rcx, rax; Stream
0x18005573b  mov     r8d, edi
0x18005573e  mov     rdx, rsi; Format
0x180055741  call    fprintf
0x180055746  mov     ecx, 2; Ix
0x18005574b  call    _o___acrt_iob_func_0
0x180055750  mov     rcx, rax; Stream
0x180055753  lea     rdx, asc_18011EAD8; "\n"
0x18005575a  call    fprintf
0x18005575f  cmp     cs:g_DeviceMapLogFunction, rbx
0x180055766  jz      short loc_18005578E
0x180055768  mov     r8d, edi
0x18005576b  mov     rdx, rsi
0x18005576e  mov     ecx, 2000000h
0x180055773  call    TraceMessageCallback
0x180055778  jmp     short loc_18005578E
0x18005577a  lea     rdx, [rsp+108h+var_98]; void *
0x18005577f  mov     rcx, rsi; Src
0x180055782  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180055787  nop
0x180055788  jmp     short loc_18005578E
0x18005578a  mov     edi, [rsp+108h+var_D0]
0x18005578e  mov     rcx, [rsp+108h+hKey]; hKey
0x180055793  test    rcx, rcx
0x180055796  jz      short loc_18005579F
0x180055798  call    cs:__imp_RegCloseKey
0x18005579e  nop
0x18005579f  lea     rcx, [rsp+108h+SubKey]; void *
0x1800557a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800557a9  mov     eax, edi
0x1800557ab  mov     rcx, [rsp+108h+var_18]
0x1800557b3  xor     rcx, rsp; StackCookie
0x1800557b6  call    __security_check_cookie
0x1800557bb  lea     r11, [rsp+108h+var_8]
0x1800557c3  mov     rbx, [r11+18h]
0x1800557c7  mov     rsi, [r11+28h]
0x1800557cb  mov     rsp, r11
0x1800557ce  pop     rdi
0x1800557cf  retn
```
