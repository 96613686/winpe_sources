# PolicyManager::ReadPassportCspPolicy

- ea: `0x180024014`
- end: `0x180024387`
- name: `PolicyManager::ReadPassportCspPolicy`
- size: `883`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ee80`
- `0x180020320`

## callees

- `0x1800046e0`
- `0x18000edb0`
- `0x1800158e0`
- `0x180016538`
- `0x18001a36c`
- `0x180024014`
- `0x180038e9c`
- `0x18003e9a8`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024140`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002420d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024140`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002420d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::ReadPassportCspPolicy(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r8
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  signed int v13; // ebx
  int v14; // ebx
  int v15; // eax
  LSTATUS v17; // [rsp+30h] [rbp-89h] BYREF
  void **v18; // [rsp+38h] [rbp-81h] BYREF
  HKEY v19; // [rsp+40h] [rbp-79h] BYREF
  void **v20; // [rsp+48h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-69h] BYREF
  __int128 v22; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v23[44]; // [rsp+68h] [rbp-51h]
  LPCWSTR lpSubKey[4]; // [rsp+98h] [rbp-21h] BYREF
  LPCWSTR Src[4]; // [rsp+B8h] [rbp-1h] BYREF

  LOBYTE(v22) = 0;
  DWORD1(v22) = 1;
  *((_QWORD *)&v22 + 1) = 1;
  v23[0] = 0;
  *(_QWORD *)&v23[4] = 0x7F00000008LL;
  *(_OWORD *)&v23[12] = 0;
  *(_DWORD *)&v23[28] = 2;
  *(_QWORD *)&v23[32] = 1;
  *(_DWORD *)&v23[40] = 0;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork");
  std::wstring::_Append<unsigned short>(lpSubKey);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::wstring::_Append<unsigned short>(lpSubKey);
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a1 + 2 * v8) );
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::wstring::_Append<unsigned short>(lpSubKey);
  v20 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  phkResult = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v20);
  v9 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &phkResult);
  if ( v10 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v17 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&dword_180061D74,
        0,
        0,
        (__int64)&v17);
    }
    std::wstring::wstring(Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork");
    std::wstring::_Append<unsigned short>(Src);
    do
      ++v6;
    while ( *(_WORD *)(a2 + 2 * v6) );
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    v18 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    v19 = 0;
    Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v18);
    v11 = (const WCHAR *)Src;
    if ( Src[3] > (LPCWSTR)7 )
      v11 = Src[0];
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &v19);
    v13 = v12;
    if ( v12 )
    {
      if ( v12 == 2 )
        goto LABEL_19;
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v17 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)byte_180061CFD,
          0,
          0,
          (__int64)&v17);
      }
      if ( v13 > 0 )
LABEL_19:
        v13 = (unsigned __int16)v13 | 0x80070000;
      v14 = HResultToSecurityStatus(v13);
    }
    else
    {
      v15 = PolicyManager::ReadProPolicyValuesFromRegistry((int)&v18, &v22);
      v14 = v15;
      if ( v15 >= 0 )
      {
        *a3 = v22;
        a3[1] = *(_OWORD *)v23;
        a3[2] = *(_OWORD *)&v23[16];
        *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)&v23[28];
      }
      else if ( (unsigned int)dword_18006E000 > 2 )
      {
        v17 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)word_180061CC2,
          0,
          0,
          (__int64)&v17);
      }
    }
    v18 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v18);
    std::wstring::~wstring(Src);
  }
  else
  {
    v14 = PolicyManager::ReadProPolicyValuesFromRegistry((int)&v20, &v22);
    if ( v14 >= 0 )
    {
      *a3 = v22;
      a3[1] = *(_OWORD *)v23;
      a3[2] = *(_OWORD *)&v23[16];
      *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)&v23[28];
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v17 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)byte_180061D3B,
        0,
        0,
        (__int64)&v17);
    }
  }
  v20 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v20);
  std::wstring::~wstring(lpSubKey);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180024014  push    rbp
0x180024016  push    rbx
0x180024017  push    rsi
0x180024018  push    rdi
0x180024019  push    r13
0x18002401b  push    r14
0x18002401d  push    r15
0x18002401f  lea     rbp, [rsp-27h]
0x180024024  sub     rsp, 0E0h
0x18002402b  mov     rax, cs:__security_cookie
0x180024032  xor     rax, rsp
0x180024035  mov     [rbp+57h+var_38], rax
0x180024039  mov     rdi, r8
0x18002403c  mov     rsi, rdx
0x18002403f  mov     r14, rcx
0x180024042  xor     r15d, r15d
0x180024045  mov     byte ptr [rbp+57h+var_B8], r15b
0x180024049  lea     r13d, [r15+1]
0x18002404d  mov     dword ptr [rbp+57h+var_B8+4], r13d
0x180024051  mov     qword ptr [rbp+57h+var_B8+8], r13
0x180024055  mov     byte ptr [rbp+57h+var_A8], r15b
0x180024059  mov     dword ptr [rbp+57h+var_A8+4], 8
0x180024060  mov     dword ptr [rbp+57h+var_A8+8], 7Fh
0x180024067  xorps   xmm0, xmm0
0x18002406a  movdqu  [rbp+57h+var_A8+0Ch], xmm0
0x18002406f  mov     dword ptr [rbp+57h+var_8C], 2
0x180024076  mov     qword ptr [rbp+57h+var_8C+4], r13
0x18002407a  mov     dword ptr [rbp+57h+var_8C+0Ch], r15d
0x18002407e  lea     rdx, Src; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x180024085  lea     rcx, [rbp+57h+lpSubKey]
0x180024089  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002408e  nop
0x18002408f  mov     r8d, r13d
0x180024092  lea     rdx, asc_180050E74; "\\"
0x180024099  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18002409d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800240a2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800240a6  mov     r8, rbx
0x1800240a9  inc     r8
0x1800240ac  cmp     [rsi+r8*2], r15w
0x1800240b1  jnz     short loc_1800240A9
0x1800240b3  mov     rdx, rsi
0x1800240b6  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1800240ba  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800240bf  mov     r8, r13
0x1800240c2  lea     rdx, asc_180050E74; "\\"
0x1800240c9  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1800240cd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800240d2  mov     r8, rbx
0x1800240d5  inc     r8
0x1800240d8  cmp     [r14+r8*2], r15w
0x1800240dd  jnz     short loc_1800240D5
0x1800240df  mov     rdx, r14
0x1800240e2  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1800240e6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800240eb  mov     r8d, 9
0x1800240f1  lea     rdx, aPolicies; "\\Policies"
0x1800240f8  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1800240fc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180024101  lea     r14, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x180024108  mov     [rbp+57h+var_C8], r14
0x18002410c  mov     [rbp+57h+var_C0], r15
0x180024110  lea     rcx, [rbp+57h+var_C8]
0x180024114  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180024119  lea     rdx, [rbp+57h+lpSubKey]
0x18002411d  cmp     [rbp+57h+var_60], 7
0x180024122  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180024127  lea     rax, [rbp+57h+var_C0]
0x18002412b  mov     [rsp+110h+phkResult], rax; phkResult
0x180024130  mov     r9d, 20019h; samDesired
0x180024136  xor     r8d, r8d; ulOptions
0x180024139  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024140  call    cs:__imp_RegOpenKeyExW
0x180024146  test    eax, eax
0x180024148  jz      loc_1800242EA
0x18002414e  mov     ecx, cs:dword_18006E000
0x180024154  cmp     ecx, 4
0x180024157  jbe     short loc_180024180
0x180024159  mov     [rsp+110h+var_E0], eax
0x18002415d  lea     rax, [rsp+110h+var_E0]
0x180024162  mov     [rsp+110h+phkResult], rax
0x180024167  xor     r9d, r9d
0x18002416a  xor     r8d, r8d
0x18002416d  lea     rdx, dword_180061D74
0x180024174  lea     rcx, dword_18006E000
0x18002417b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180024180  lea     rdx, Src; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x180024187  lea     rcx, [rbp+57h+Src]
0x18002418b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180024190  nop
0x180024191  mov     r8, r13
0x180024194  lea     rdx, asc_180050E74; "\\"
0x18002419b  lea     rcx, [rbp+57h+Src]; Src
0x18002419f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800241a4  inc     rbx
0x1800241a7  cmp     [rsi+rbx*2], r15w
0x1800241ac  jnz     short loc_1800241A4
0x1800241ae  mov     r8, rbx
0x1800241b1  mov     rdx, rsi
0x1800241b4  lea     rcx, [rbp+57h+Src]; Src
0x1800241b8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800241bd  mov     r8d, 10h
0x1800241c3  lea     rdx, aDevicePolicies; "\\Device\\Policies"
0x1800241ca  lea     rcx, [rbp+57h+Src]; Src
0x1800241ce  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800241d3  mov     [rsp+110h+var_D8], r14
0x1800241d8  mov     [rbp+57h+var_D0], r15
0x1800241dc  lea     rcx, [rsp+110h+var_D8]
0x1800241e1  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800241e6  lea     rdx, [rbp+57h+Src]
0x1800241ea  cmp     [rbp+57h+var_40], 7
0x1800241ef  cmova   rdx, [rbp+57h+Src]; lpSubKey
0x1800241f4  lea     rax, [rbp+57h+var_D0]
0x1800241f8  mov     [rsp+110h+phkResult], rax; phkResult
0x1800241fd  mov     r9d, 20019h; samDesired
0x180024203  xor     r8d, r8d; ulOptions
0x180024206  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002420d  call    cs:__imp_RegOpenKeyExW
0x180024213  mov     ebx, eax
0x180024215  test    eax, eax
0x180024217  jz      short loc_180024268
0x180024219  cmp     eax, 2
0x18002421c  jz      short loc_180024254
0x18002421e  mov     eax, cs:dword_18006E000
0x180024224  cmp     eax, 2
0x180024227  jbe     short loc_180024250
0x180024229  mov     [rsp+110h+var_E0], ebx
0x18002422d  lea     rax, [rsp+110h+var_E0]
0x180024232  mov     [rsp+110h+phkResult], rax
0x180024237  xor     r9d, r9d
0x18002423a  xor     r8d, r8d
0x18002423d  lea     rdx, byte_180061CFD
0x180024244  lea     rcx, dword_18006E000
0x18002424b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180024250  test    ebx, ebx
0x180024252  jle     short loc_18002425D
0x180024254  movzx   ebx, bx
0x180024257  or      ebx, 80070000h
0x18002425d  mov     ecx, ebx; int
0x18002425f  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180024264  mov     ebx, eax
0x180024266  jmp     short loc_1800242CF
0x180024268  lea     rdx, [rbp+57h+var_B8]
0x18002426c  lea     rcx, [rsp+110h+var_D8]
0x180024271  call    PolicyManager__ReadProPolicyValuesFromRegistry
0x180024276  mov     ebx, eax
0x180024278  test    eax, eax
0x18002427a  jns     short loc_1800242B0
0x18002427c  mov     ecx, cs:dword_18006E000
0x180024282  cmp     ecx, 2
0x180024285  jbe     short loc_1800242CF
0x180024287  mov     [rsp+110h+var_E0], eax
0x18002428b  lea     rax, [rsp+110h+var_E0]
0x180024290  mov     [rsp+110h+phkResult], rax
0x180024295  xor     r9d, r9d
0x180024298  xor     r8d, r8d
0x18002429b  lea     rdx, word_180061CC2
0x1800242a2  lea     rcx, dword_18006E000
0x1800242a9  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800242ae  jmp     short loc_1800242CF
0x1800242b0  movups  xmm0, [rbp+57h+var_B8]
0x1800242b4  movups  xmmword ptr [rdi], xmm0
0x1800242b7  movups  xmm1, [rbp+57h+var_A8]
0x1800242bb  movups  xmmword ptr [rdi+10h], xmm1
0x1800242bf  movups  xmm0, xmmword ptr [rbp-41h]
0x1800242c3  movups  xmmword ptr [rdi+20h], xmm0
0x1800242c7  movups  xmm1, [rbp+57h+var_8C]
0x1800242cb  movups  xmmword ptr [rdi+2Ch], xmm1
0x1800242cf  mov     [rsp+110h+var_D8], r14
0x1800242d4  lea     rcx, [rsp+110h+var_D8]
0x1800242d9  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800242de  nop
0x1800242df  lea     rcx, [rbp+57h+Src]
0x1800242e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800242e8  jmp     short loc_180024350
0x1800242ea  lea     rdx, [rbp+57h+var_B8]
0x1800242ee  lea     rcx, [rbp+57h+var_C8]
0x1800242f2  call    PolicyManager__ReadProPolicyValuesFromRegistry
0x1800242f7  mov     ebx, eax
0x1800242f9  test    eax, eax
0x1800242fb  jns     short loc_180024331
0x1800242fd  mov     eax, cs:dword_18006E000
0x180024303  cmp     eax, 2
0x180024306  jbe     short loc_180024350
0x180024308  mov     [rsp+110h+var_E0], ebx
0x18002430c  lea     rax, [rsp+110h+var_E0]
0x180024311  mov     [rsp+110h+phkResult], rax
0x180024316  xor     r9d, r9d
0x180024319  xor     r8d, r8d
0x18002431c  lea     rdx, byte_180061D3B
0x180024323  lea     rcx, dword_18006E000
0x18002432a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002432f  jmp     short loc_180024350
0x180024331  movups  xmm0, [rbp+57h+var_B8]
0x180024335  movups  xmmword ptr [rdi], xmm0
0x180024338  movups  xmm1, [rbp+57h+var_A8]
0x18002433c  movups  xmmword ptr [rdi+10h], xmm1
0x180024340  movups  xmm0, xmmword ptr [rbp-41h]
0x180024344  movups  xmmword ptr [rdi+20h], xmm0
0x180024348  movups  xmm1, [rbp+57h+var_8C]
0x18002434c  movups  xmmword ptr [rdi+2Ch], xmm1
0x180024350  mov     [rbp+57h+var_C8], r14
0x180024354  lea     rcx, [rbp+57h+var_C8]
0x180024358  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x18002435d  nop
0x18002435e  lea     rcx, [rbp+57h+lpSubKey]
0x180024362  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024367  mov     eax, ebx
0x180024369  mov     rcx, [rbp+57h+var_38]
0x18002436d  xor     rcx, rsp; StackCookie
0x180024370  call    __security_check_cookie
0x180024375  add     rsp, 0E0h
0x18002437c  pop     r15
0x18002437e  pop     r14
0x180024380  pop     r13
0x180024382  pop     rdi
0x180024383  pop     rsi
0x180024384  pop     rbx
0x180024385  pop     rbp
0x180024386  retn
```
