# NetworkSignature::GetNetworkProperties(wchar_t * *,wchar_t * *)

- ea: `0x180089060`
- end: `0x18008937f`
- name: `?GetNetworkProperties@NetworkSignature@@UEAAJPEAPEA_W0@Z`
- size: `799`
- prototype: `int(NetworkSignature *__hidden this, wchar_t **, wchar_t **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x1800120a0`
- `0x1800127d0`
- `0x180014d80`
- `0x180015650`
- `0x180015710`
- `0x180018968`
- `0x1800355c0`
- `0x180038950`
- `0x1800460dc`
- `0x180047ff4`
- `0x180089060`
- `0x1800a88a0`
- `0x1800aba25`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008916d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008927c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008916d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008927c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008930c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008930c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089259`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall NetworkSignature::GetNetworkProperties(NetworkSignature *this, wchar_t **a2, wchar_t **a3)
{
  unsigned int ValueWithAlloc; // edi
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rax
  __int64 v11; // rbx
  wchar_t *v12; // rax
  __int64 v13; // r14
  __int64 v14; // rsi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-60h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-58h] BYREF
  __int128 v19; // [rsp+48h] [rbp-50h] BYREF
  __int64 v20; // [rsp+58h] [rbp-40h]
  unsigned __int8 v21[8]; // [rsp+60h] [rbp-38h] BYREF

  hKey = 0;
  *(_QWORD *)v21 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids);
  StandbyMonitor::ProcessClientActivity(88);
  if ( !a2 || !a3 )
  {
    ValueWithAlloc = -2147467261;
    goto LABEL_31;
  }
  if ( *((_DWORD *)this + 4) )
  {
    *a2 = 0;
    v19 = 0;
    v20 = 0;
    NetworkPropertyMaps::FindConnectedNetworksBySignature(&v19, (char *)this + 24, 0, 0, 0);
    v8 = *((_QWORD *)&v19 + 1);
    v9 = v19;
    if ( (unsigned __int64)(0x66FD0EB66FD0EB67LL * ((__int64)(*((_QWORD *)&v19 + 1) - v19) >> 3)) >= 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(*((_QWORD *)&v19 + 1), v19, 0x66FD0EB66FD0EB67LL, v7);
      v8 = *((_QWORD *)&v19 + 1);
      v9 = v19;
    }
    if ( v9 == v8 )
    {
      ValueWithAlloc = -2147418113;
      if ( (*((_BYTE *)this + 76) & 3) != 0 )
        goto LABEL_28;
      lpCriticalSection = 0;
      NetworkPropertyMaps::LockProfileStore(&lpCriticalSection);
      ValueWithAlloc = HrOpenSignatureKey((NetworkSignature *)((char *)this + 24), 0x20019u, &hKey);
      if ( !ValueWithAlloc )
      {
        ValueWithAlloc = HrRegQueryValueWithAlloc(hKey, L"DnsSuffix", 0, (unsigned __int8 **)a2, 0);
        if ( !ValueWithAlloc )
        {
          v18 = 8;
          ValueWithAlloc = HrRegQueryValueEx(hKey, L"DefaultGatewayMac", 0, v21, &v18);
        }
        RegCloseKey(hKey);
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      if ( ValueWithAlloc )
        goto LABEL_28;
    }
    else
    {
      v10 = (wchar_t *)CoTaskMemAlloc(0x200u);
      *a2 = v10;
      if ( !v10 )
      {
LABEL_27:
        ValueWithAlloc = -2147024882;
LABEL_28:
        CoTaskMemFree(*a2);
        *a2 = 0;
LABEL_29:
        std::vector<ACTIVE_NETWORK>::_Tidy(&v19);
        goto LABEL_31;
      }
      ValueWithAlloc = 0;
      StringCchCopyW(v10, 0x100u, (const wchar_t *)(v19 + 160));
      v11 = v19;
      memcpy_0(v21, (const void *)(v19 + 672), *(unsigned int *)(v19 + 680));
      v18 = *(_DWORD *)(v11 + 680);
    }
    v12 = (wchar_t *)CoTaskMemAlloc(0x30u);
    *a3 = v12;
    if ( v12 )
    {
      if ( v18 )
      {
        v13 = 0;
        v14 = 0;
        if ( v18 != 1 )
        {
          do
          {
            StringCchPrintfW(&(*a3)[v14], (unsigned int)(24 - v14), L"%02X-", v21[v13]);
            v14 = (unsigned int)(v14 + 3);
            v13 = (unsigned int)(v13 + 1);
          }
          while ( (unsigned int)v13 < v18 - 1 );
        }
        StringCchPrintfW(&(*a3)[v14], (unsigned int)(24 - v14), L"%#02x", v21[v13]);
      }
      else
      {
        StringCchPrintfW(v12, 0x18u, L"00-00-00-00-00-00");
      }
      goto LABEL_29;
    }
    goto LABEL_27;
  }
  ValueWithAlloc = -2147418113;
LABEL_31:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids, ValueWithAlloc);
  return ValueWithAlloc;
}

```

## disassembly

```asm
0x180089060  mov     [rsp+arg_18], rbx
0x180089065  push    rsi
0x180089066  push    rdi
0x180089067  push    r13
0x180089069  push    r14
0x18008906b  push    r15
0x18008906d  sub     rsp, 70h
0x180089071  mov     rax, cs:__security_cookie
0x180089078  xor     rax, rsp
0x18008907b  mov     [rsp+98h+var_30], rax
0x180089080  mov     r15, r8
0x180089083  mov     rsi, rdx
0x180089086  mov     rbx, rcx
0x180089089  mov     [rsp+98h+hKey], 0
0x180089092  mov     qword ptr [rsp+98h+var_38], 0
0x18008909b  mov     [rsp+98h+var_58], 0
0x1800890a3  lea     r13, WPP_GLOBAL_Control
0x1800890aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800890b1  cmp     rcx, r13
0x1800890b4  jz      short loc_1800890D1
0x1800890b6  test    byte ptr [rcx+1Ch], 8
0x1800890ba  jz      short loc_1800890D1
0x1800890bc  mov     edx, 1Dh
0x1800890c1  lea     r8, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids
0x1800890c8  mov     rcx, [rcx+10h]
0x1800890cc  call    WPP_SF_
0x1800890d1  mov     ecx, 58h ; 'X'
0x1800890d6  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x1800890db  test    rsi, rsi
0x1800890de  jz      loc_180089325
0x1800890e4  test    r15, r15
0x1800890e7  jz      loc_180089325
0x1800890ed  cmp     dword ptr [rbx+10h], 0
0x1800890f1  jnz     short loc_1800890FD
0x1800890f3  mov     edi, 8000FFFFh
0x1800890f8  jmp     loc_18008932A
0x1800890fd  mov     qword ptr [rsi], 0
0x180089104  xorps   xmm0, xmm0
0x180089107  xor     eax, eax
0x180089109  movups  [rsp+98h+var_50], xmm0
0x18008910e  mov     [rsp+98h+var_40], rax
0x180089113  mov     dword ptr [rsp+98h+var_78], eax
0x180089117  xor     r9d, r9d
0x18008911a  xor     r8d, r8d
0x18008911d  lea     rdx, [rbx+18h]
0x180089121  lea     rcx, [rsp+98h+var_50]
0x180089126  call    ?FindConnectedNetworksBySignature@NetworkPropertyMaps@@SA?AV?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@PEBUtagNLA_SIGNATURE@@PEBU_GUID@@1I@Z; NetworkPropertyMaps::FindConnectedNetworksBySignature(tagNLA_SIGNATURE const *,_GUID const *,_GUID const *,uint)
0x18008912b  nop
0x18008912c  mov     rcx, qword ptr [rsp+98h+var_50+8]
0x180089131  mov     rax, rcx
0x180089134  mov     rdx, qword ptr [rsp+98h+var_50]
0x180089139  sub     rax, rdx
0x18008913c  sar     rax, 3
0x180089140  mov     r8, 66FD0EB66FD0EB67h
0x18008914a  imul    rax, r8
0x18008914e  cmp     rax, 2
0x180089152  jb      short loc_180089163
0x180089154  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180089159  mov     rcx, qword ptr [rsp+98h+var_50+8]
0x18008915e  mov     rdx, qword ptr [rsp+98h+var_50]
0x180089163  cmp     rdx, rcx
0x180089166  jz      short loc_1800891C6
0x180089168  mov     ecx, 200h; cb
0x18008916d  call    cs:__imp_CoTaskMemAlloc
0x180089173  mov     [rsi], rax
0x180089176  test    rax, rax
0x180089179  jz      loc_180089304
0x18008917f  xor     edi, edi
0x180089181  mov     r8, qword ptr [rsp+98h+var_50]
0x180089186  add     r8, 0A0h; wchar_t *
0x18008918d  mov     edx, 100h; unsigned __int64
0x180089192  mov     rcx, rax; wchar_t *
0x180089195  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18008919a  mov     rbx, qword ptr [rsp+98h+var_50]
0x18008919f  mov     r8d, [rbx+2A8h]; Size
0x1800891a6  lea     rdx, [rbx+2A0h]; Src
0x1800891ad  lea     rcx, [rsp+98h+var_38]; void *
0x1800891b2  call    memcpy_0
0x1800891b7  mov     eax, [rbx+2A8h]
0x1800891bd  mov     [rsp+98h+var_58], eax
0x1800891c1  jmp     loc_180089277
0x1800891c6  mov     edi, 8000FFFFh
0x1800891cb  test    byte ptr [rbx+4Ch], 3
0x1800891cf  jnz     loc_180089309
0x1800891d5  mov     [rsp+98h+lpCriticalSection], 0
0x1800891de  lea     rcx, [rsp+98h+lpCriticalSection]
0x1800891e3  call    ?LockProfileStore@NetworkPropertyMaps@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; NetworkPropertyMaps::LockProfileStore(void)
0x1800891e8  lea     r8, [rsp+98h+hKey]; HKEY *
0x1800891ed  mov     edx, 20019h; unsigned int
0x1800891f2  lea     rcx, [rbx+18h]; struct tagNLA_SIGNATURE *
0x1800891f6  call    ?HrOpenSignatureKey@@YAJPEAUtagNLA_SIGNATURE@@KPEAPEAUHKEY__@@@Z; HrOpenSignatureKey(tagNLA_SIGNATURE *,ulong,HKEY__ * *)
0x1800891fb  mov     edi, eax
0x1800891fd  test    eax, eax
0x1800891ff  jnz     short loc_18008925F
0x180089201  mov     [rsp+98h+var_78], 0; unsigned int *
0x18008920a  mov     r9, rsi; unsigned __int8 **
0x18008920d  xor     r8d, r8d; lpType
0x180089210  lea     rdx, aDnssuffix; "DnsSuffix"
0x180089217  mov     rcx, [rsp+98h+hKey]; hKey
0x18008921c  call    ?HrRegQueryValueWithAlloc@@YAJPEAUHKEY__@@PEB_WPEAKPEAPEAE2@Z; HrRegQueryValueWithAlloc(HKEY__ *,wchar_t const *,ulong *,uchar * *,ulong *)
0x180089221  mov     edi, eax
0x180089223  test    eax, eax
0x180089225  jnz     short loc_180089254
0x180089227  mov     [rsp+98h+var_58], 8
0x18008922f  lea     rax, [rsp+98h+var_58]
0x180089234  mov     [rsp+98h+var_78], rax; unsigned int *
0x180089239  lea     r9, [rsp+98h+var_38]; unsigned __int8 *
0x18008923e  xor     r8d, r8d; unsigned int *
0x180089241  lea     rdx, aDefaultgateway_0; "DefaultGatewayMac"
0x180089248  mov     rcx, [rsp+98h+hKey]; HKEY
0x18008924d  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x180089252  mov     edi, eax
0x180089254  mov     rcx, [rsp+98h+hKey]; hKey
0x180089259  call    cs:__imp_RegCloseKey
0x18008925f  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x180089264  test    rcx, rcx
0x180089267  jz      short loc_18008926F
0x180089269  call    cs:__imp_LeaveCriticalSection
0x18008926f  test    edi, edi
0x180089271  jnz     loc_180089309
0x180089277  mov     ecx, 30h ; '0'; cb
0x18008927c  call    cs:__imp_CoTaskMemAlloc
0x180089282  mov     [r15], rax
0x180089285  test    rax, rax
0x180089288  jz      short loc_180089304
0x18008928a  mov     ecx, [rsp+98h+var_58]
0x18008928e  test    ecx, ecx
0x180089290  jz      short loc_1800892EE
0x180089292  xor     r14d, r14d
0x180089295  xor     esi, esi
0x180089297  lea     eax, [rcx-1]
0x18008929a  lea     ebx, [rsi+18h]
0x18008929d  test    eax, eax
0x18008929f  jz      short loc_1800892CF
0x1800892a1  movzx   r9d, [rsp+r14+98h+var_38]
0x1800892a7  mov     edx, ebx
0x1800892a9  sub     edx, esi; unsigned __int64
0x1800892ab  mov     rax, [r15]
0x1800892ae  lea     rcx, [rax+rsi*2]; wchar_t *
0x1800892b2  lea     r8, a02x; "%02X-"
0x1800892b9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800892be  add     esi, 3
0x1800892c1  inc     r14d
0x1800892c4  mov     eax, [rsp+98h+var_58]
0x1800892c8  dec     eax
0x1800892ca  cmp     r14d, eax
0x1800892cd  jb      short loc_1800892A1
0x1800892cf  movzx   r9d, [rsp+r14+98h+var_38]
0x1800892d5  sub     ebx, esi
0x1800892d7  mov     edx, ebx; unsigned __int64
0x1800892d9  mov     rax, [r15]
0x1800892dc  lea     rcx, [rax+rsi*2]; wchar_t *
0x1800892e0  lea     r8, a02x_0; "%#02x"
0x1800892e7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800892ec  jmp     short loc_180089319
0x1800892ee  lea     r8, a000000000000; "00-00-00-00-00-00"
0x1800892f5  mov     edx, 18h; unsigned __int64
0x1800892fa  mov     rcx, rax; wchar_t *
0x1800892fd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180089302  jmp     short loc_180089319
0x180089304  mov     edi, 8007000Eh
0x180089309  mov     rcx, [rsi]; pv
0x18008930c  call    cs:__imp_CoTaskMemFree
0x180089312  mov     qword ptr [rsi], 0
0x180089319  lea     rcx, [rsp+98h+var_50]
0x18008931e  call    ?_Tidy@?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@AEAAXXZ; std::vector<ACTIVE_NETWORK>::_Tidy(void)
0x180089323  jmp     short loc_18008932A
0x180089325  mov     edi, 80004003h
0x18008932a  mov     rcx, cs:WPP_GLOBAL_Control
0x180089331  cmp     rcx, r13
0x180089334  jz      short loc_180089354
0x180089336  test    byte ptr [rcx+1Ch], 8
0x18008933a  jz      short loc_180089354
0x18008933c  mov     edx, 1Eh
0x180089341  mov     r9d, edi
0x180089344  lea     r8, WPP_9bff86f1e85230049ed853f94145d0c0_Traceguids
0x18008934b  mov     rcx, [rcx+10h]
0x18008934f  call    WPP_SF_d
0x180089354  mov     eax, edi
0x180089356  jmp     short loc_18008935C
0x180089358  mov     eax, [rsp+98h+var_58]
0x18008935c  mov     rcx, [rsp+98h+var_30]
0x180089361  xor     rcx, rsp; StackCookie
0x180089364  call    __security_check_cookie
0x180089369  mov     rbx, [rsp+98h+arg_18]
0x180089371  add     rsp, 70h
0x180089375  pop     r15
0x180089377  pop     r14
0x180089379  pop     r13
0x18008937b  pop     rdi
0x18008937c  pop     rsi
0x18008937d  retn
```
