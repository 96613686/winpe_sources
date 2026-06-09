# VpnHandlePluginCrashReconnect

- ea: `0x1800dad5c`
- end: `0x1800db0a5`
- name: `VpnHandlePluginCrashReconnect`
- size: `841`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d2910`

## callees

- `0x180005e0c`
- `0x180005f1c`
- `0x1800c0ef0`
- `0x1800c85f8`
- `0x1800cad98`
- `0x1800cd880`
- `0x1800dad5c`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e1e64`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x1800daf16`
- `ntdll!RtlIsMultiSessionSku` at `0x1800daf16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db05d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daef1`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800daee7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800daee7`
- `RASAPI32!RasTriggerConnectionEx` at `0x1800daffd`
- `RASAPI32!RasTriggerConnectionEx` at `0x1800daffd`
- `RASAPI32!RasTriggerConnectionWithDetailsEx` at `0x1800dafaf`
- `RASAPI32!RasTriggerConnectionWithDetailsEx` at `0x1800dafaf`

## string_xrefs

- `0x1800daebb`: `GetActiveTokenAndSessionId`
- `0x1800daefb`: `DuplicateToken`
- `0x1800daec2`: `VpnHandlePluginCrashReconnect`
- `0x1800daf05`: `VpnHandlePluginCrashReconnect`

## pseudocode

```c
double VpnHandlePluginCrashReconnect()
{
  HANDLE v0; // rdi
  int v1; // ebx
  __int64 v2; // r14
  __int64 v3; // rsi
  void *v4; // r15
  double result; // xmm0_8
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  unsigned int ActiveTokenAndSessionId; // eax
  __int64 v9; // rcx
  DWORD LastError; // eax
  const char *v11; // rdx
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  _DWORD v14[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v15; // [rsp+58h] [rbp-31h]
  __int64 v16; // [rsp+60h] [rbp-29h]
  __int64 v17; // [rsp+68h] [rbp-21h]
  __int128 v18; // [rsp+70h] [rbp-19h]
  __int128 v19; // [rsp+80h] [rbp-9h]
  __int128 v20; // [rsp+A0h] [rbp+17h]
  DWORD v21; // [rsp+F0h] [rbp+67h] BYREF
  void *DuplicateTokenHandle; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+100h] [rbp+77h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+108h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 306, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  v0 = 0;
  DuplicateTokenHandle = 0;
  ExistingTokenHandle = 0;
  v23 = 0;
  v21 = 0;
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  v1 = xmmword_18010E9B0;
  v2 = xmmword_18010E9C0;
  v3 = *((_QWORD *)&xmmword_18010E9B0 + 1);
  v4 = (void *)*((_QWORD *)&xmmword_18010E9C0 + 1);
  v14[1] = DWORD1(xmmword_18010E9B0);
  v18 = xmmword_18010E9D0;
  v19 = 0;
  v20 = 0;
  *(_QWORD *)&xmmword_18010E9B0 = 0;
  *(_QWORD *)&xmmword_18010E9C0 = 0;
  DWORD1(xmmword_18010E9D0) = 0;
  v14[0] = v1;
  v15 = *((_QWORD *)&xmmword_18010E9B0 + 1);
  v16 = v2;
  v17 = *((_QWORD *)&xmmword_18010E9C0 + 1);
  *((_QWORD *)&xmmword_18010E9B0 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  *((_QWORD *)&xmmword_18010E9C0 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  result = VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( !v1 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      v7 = 307;
LABEL_8:
      result = WPP_SF_(v6[1].Flink, v7, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  ActiveTokenAndSessionId = GetActiveTokenAndSessionId(v4, &v21, &ExistingTokenHandle);
  if ( ActiveTokenAndSessionId )
  {
    VpnReportError("VpnHandlePluginCrashReconnect", "GetActiveTokenAndSessionId", ActiveTokenAndSessionId);
    v0 = ExistingTokenHandle;
    goto LABEL_32;
  }
  v0 = ExistingTokenHandle;
  if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v11 = "DuplicateToken";
LABEL_14:
      VpnReportError("VpnHandlePluginCrashReconnect", v11, LastError);
      goto LABEL_32;
    }
  }
  if ( (unsigned __int8)RtlIsMultiSessionSku(v9)
    || !(unsigned int)IsTokenForDefaultAccount((__int64)DuplicateTokenHandle) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl'::`2'::impl) )
    {
      ExistingTokenHandle = (HANDLE)0x100000004LL;
      LastError = RasTriggerConnectionWithDetailsEx(
                    v2,
                    v3,
                    DuplicateTokenHandle,
                    v21,
                    0x100000004LL,
                    &v23,
                    int_RasTriggerConnectionCallback,
                    0,
                    0);
      if ( LastError )
      {
        v11 = "RasTriggerConnectionWithDetailsEx for crash reconnect";
        goto LABEL_14;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
      {
        goto LABEL_32;
      }
      v13 = 309;
    }
    else
    {
      LastError = RasTriggerConnectionEx(
                    v2,
                    v3,
                    DuplicateTokenHandle,
                    v21,
                    &v23,
                    int_RasTriggerConnectionCallback,
                    0,
                    0);
      if ( LastError )
      {
        v11 = "RasTriggerConnectionEx for crash reconnect";
        goto LABEL_14;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
      {
        goto LABEL_32;
      }
      v13 = 310;
    }
    WPP_SF_q(v12[1].Flink, v13, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v23);
    goto LABEL_32;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    v7 = 308;
    goto LABEL_8;
  }
LABEL_32:
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( v0 )
    CloseHandle(v0);
  int_FreePluginCrashRecordFields(v14);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    return WPP_SF_(WPP_GLOBAL_Control[1].Flink, 311, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800dad5c  push    rbp
0x1800dad5e  push    rbx
0x1800dad5f  push    rsi
0x1800dad60  push    rdi
0x1800dad61  push    r13
0x1800dad63  push    r14
0x1800dad65  push    r15
0x1800dad67  lea     rbp, [rsp-27h]
0x1800dad6c  sub     rsp, 0B0h
0x1800dad73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dad7a  lea     r13, WPP_GLOBAL_Control
0x1800dad81  cmp     rcx, r13
0x1800dad84  jz      short loc_1800DADA1
0x1800dad86  test    byte ptr [rcx+1Ch], 8
0x1800dad8a  jz      short loc_1800DADA1
0x1800dad8c  mov     rcx, [rcx+10h]
0x1800dad90  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dad97  mov     edx, 132h
0x1800dad9c  call    WPP_SF_
0x1800dada1  xor     edi, edi
0x1800dada3  mov     [rbp+57h+DuplicateTokenHandle], 0
0x1800dadab  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800dadb2  mov     [rbp+57h+ExistingTokenHandle], rdi
0x1800dadb6  mov     [rbp+57h+arg_10], rdi
0x1800dadba  mov     [rbp+57h+arg_0], 0
0x1800dadc1  call    VpnCriticalSectionEnter
0x1800dadc6  mov     eax, dword ptr cs:xmmword_18010E9B0+4
0x1800dadcc  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800dadd3  mov     ebx, dword ptr cs:xmmword_18010E9B0
0x1800dadd9  xorps   xmm1, xmm1
0x1800daddc  mov     r14, qword ptr cs:xmmword_18010E9C0
0x1800dade3  xorps   xmm0, xmm0
0x1800dade6  mov     rsi, qword ptr cs:xmmword_18010E9B0+8
0x1800daded  mov     r15, qword ptr cs:xmmword_18010E9C0+8
0x1800dadf4  mov     [rbp+57h+var_8C], eax
0x1800dadf7  mov     eax, dword ptr cs:xmmword_18010E9D0
0x1800dadfd  mov     dword ptr [rbp+57h+var_70], eax
0x1800dae00  mov     eax, dword ptr cs:xmmword_18010E9D0+4
0x1800dae06  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800dae09  mov     rax, qword ptr cs:xmmword_18010E9D0+8
0x1800dae10  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800dae14  movups  [rbp+57h+var_60], xmm1
0x1800dae18  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1800dae1b  movups  [rbp+57h+var_40], xmm1
0x1800dae1f  mov     dword ptr cs:xmmword_18010E9B0+4, eax
0x1800dae25  mov     eax, dword ptr [rbp+57h+var_40+4]
0x1800dae28  movss   dword ptr cs:xmmword_18010E9B0, xmm1
0x1800dae30  movsd   qword ptr cs:xmmword_18010E9C0, xmm1
0x1800dae38  psrldq  xmm0, 8
0x1800dae3d  psrldq  xmm1, 8
0x1800dae42  mov     dword ptr cs:xmmword_18010E9D0+4, eax
0x1800dae48  mov     [rbp+57h+var_90], ebx
0x1800dae4b  mov     [rbp+57h+var_88], rsi
0x1800dae4f  mov     [rbp+57h+var_80], r14
0x1800dae53  mov     [rbp+57h+var_78], r15
0x1800dae57  movq    qword ptr cs:xmmword_18010E9B0+8, xmm0
0x1800dae5f  movq    qword ptr cs:xmmword_18010E9C0+8, xmm1
0x1800dae67  call    VpnCriticalSectionLeave
0x1800dae6c  test    ebx, ebx
0x1800dae6e  jnz     short loc_1800DAEA4
0x1800dae70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae77  cmp     rcx, r13
0x1800dae7a  jz      loc_1800DB03E
0x1800dae80  test    byte ptr [rcx+1Ch], 4
0x1800dae84  jz      loc_1800DB03E
0x1800dae8a  mov     edx, 133h
0x1800dae8f  mov     rcx, [rcx+10h]
0x1800dae93  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800dae9a  call    WPP_SF_
0x1800dae9f  jmp     loc_1800DB03E
0x1800daea4  lea     r8, [rbp+57h+ExistingTokenHandle]
0x1800daea8  mov     rcx, r15; Buf2
0x1800daeab  lea     rdx, [rbp+57h+arg_0]
0x1800daeaf  call    GetActiveTokenAndSessionId
0x1800daeb4  test    eax, eax
0x1800daeb6  jz      short loc_1800DAED7
0x1800daeb8  mov     r8d, eax
0x1800daebb  lea     rdx, aGetactivetoken; "GetActiveTokenAndSessionId"
0x1800daec2  lea     rcx, aVpnhandleplugi; "VpnHandlePluginCrashReconnect"
0x1800daec9  call    VpnReportError
0x1800daece  mov     rdi, [rbp+57h+ExistingTokenHandle]
0x1800daed2  jmp     loc_1800DB03E
0x1800daed7  mov     rdi, [rbp+57h+ExistingTokenHandle]
0x1800daedb  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800daedf  mov     rcx, rdi; ExistingTokenHandle
0x1800daee2  mov     edx, 2; ImpersonationLevel
0x1800daee7  call    cs:__imp_DuplicateToken
0x1800daeed  test    eax, eax
0x1800daeef  jnz     short loc_1800DAF16
0x1800daef1  call    cs:__imp_GetLastError
0x1800daef7  test    eax, eax
0x1800daef9  jz      short loc_1800DAF16
0x1800daefb  lea     rdx, aDuplicatetoken; "DuplicateToken"
0x1800daf02  mov     r8d, eax
0x1800daf05  lea     rcx, aVpnhandleplugi; "VpnHandlePluginCrashReconnect"
0x1800daf0c  call    VpnReportError
0x1800daf11  jmp     loc_1800DB03E
0x1800daf16  call    cs:__imp_RtlIsMultiSessionSku
0x1800daf1c  test    al, al
0x1800daf1e  jnz     short loc_1800DAF51
0x1800daf20  mov     rcx, [rbp+57h+DuplicateTokenHandle]
0x1800daf24  call    IsTokenForDefaultAccount
0x1800daf29  test    eax, eax
0x1800daf2b  jz      short loc_1800DAF51
0x1800daf2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daf34  cmp     rcx, r13
0x1800daf37  jz      loc_1800DB03E
0x1800daf3d  test    byte ptr [rcx+1Ch], 4
0x1800daf41  jz      loc_1800DB03E
0x1800daf47  mov     edx, 134h
0x1800daf4c  jmp     loc_1800DAE8F
0x1800daf51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl(void)'::`2'::impl
0x1800daf58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(void)
0x1800daf5d  mov     r9d, [rbp+57h+arg_0]
0x1800daf61  test    al, al
0x1800daf63  mov     r8, [rbp+57h+DuplicateTokenHandle]
0x1800daf67  lea     rax, ?int_RasTriggerConnectionCallback@@YAKPEAUHRASCONN__@@KK@Z; int_RasTriggerConnectionCallback(HRASCONN__ *,ulong,ulong)
0x1800daf6e  mov     rdx, rsi
0x1800daf71  mov     rcx, r14
0x1800daf74  jz      short loc_1800DAFDE
0x1800daf76  mov     [rsp+0E0h+var_A0], 0
0x1800daf7f  mov     dword ptr [rsp+0E0h+var_A8], 0
0x1800daf87  mov     [rsp+0E0h+var_B0], rax
0x1800daf8c  lea     rax, [rbp+57h+arg_10]
0x1800daf90  mov     [rsp+0E0h+var_B8], rax
0x1800daf95  mov     dword ptr [rbp+57h+ExistingTokenHandle], 4
0x1800daf9c  mov     dword ptr [rbp+57h+ExistingTokenHandle+4], 1
0x1800dafa6  mov     rax, [rbp+57h+ExistingTokenHandle]
0x1800dafaa  mov     [rsp+0E0h+var_C0], rax
0x1800dafaf  call    cs:__imp_RasTriggerConnectionWithDetailsEx
0x1800dafb5  test    eax, eax
0x1800dafb7  jz      short loc_1800DAFC5
0x1800dafb9  lea     rdx, aRastriggerconn_2; "RasTriggerConnectionWithDetailsEx for c"...
0x1800dafc0  jmp     loc_1800DAF02
0x1800dafc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dafcc  cmp     rcx, r13
0x1800dafcf  jz      short loc_1800DB03E
0x1800dafd1  test    byte ptr [rcx+1Ch], 4
0x1800dafd5  jz      short loc_1800DB03E
0x1800dafd7  mov     edx, 135h
0x1800dafdc  jmp     short loc_1800DB02A
0x1800dafde  mov     [rsp+0E0h+var_A8], 0
0x1800dafe7  mov     dword ptr [rsp+0E0h+var_B0], 0
0x1800dafef  mov     [rsp+0E0h+var_B8], rax
0x1800daff4  lea     rax, [rbp+57h+arg_10]
0x1800daff8  mov     [rsp+0E0h+var_C0], rax
0x1800daffd  call    cs:__imp_RasTriggerConnectionEx
0x1800db003  test    eax, eax
0x1800db005  jz      short loc_1800DB013
0x1800db007  lea     rdx, aRastriggerconn_0; "RasTriggerConnectionEx for crash reconn"...
0x1800db00e  jmp     loc_1800DAF02
0x1800db013  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db01a  cmp     rcx, r13
0x1800db01d  jz      short loc_1800DB03E
0x1800db01f  test    byte ptr [rcx+1Ch], 4
0x1800db023  jz      short loc_1800DB03E
0x1800db025  mov     edx, 136h
0x1800db02a  mov     r9, [rbp+57h+arg_10]
0x1800db02e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db035  mov     rcx, [rcx+10h]
0x1800db039  call    WPP_SF_q
0x1800db03e  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x1800db042  test    rcx, rcx
0x1800db045  jz      short loc_1800DB055
0x1800db047  call    cs:__imp_CloseHandle
0x1800db04d  mov     [rbp+57h+DuplicateTokenHandle], 0
0x1800db055  test    rdi, rdi
0x1800db058  jz      short loc_1800DB063
0x1800db05a  mov     rcx, rdi; hObject
0x1800db05d  call    cs:__imp_CloseHandle
0x1800db063  lea     rcx, [rbp+57h+var_90]
0x1800db067  call    int_FreePluginCrashRecordFields
0x1800db06c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db073  cmp     rcx, r13
0x1800db076  jz      short loc_1800DB093
0x1800db078  test    byte ptr [rcx+1Ch], 8
0x1800db07c  jz      short loc_1800DB093
0x1800db07e  mov     rcx, [rcx+10h]
0x1800db082  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db089  mov     edx, 137h
0x1800db08e  call    WPP_SF_
0x1800db093  add     rsp, 0B0h
0x1800db09a  pop     r15
0x1800db09c  pop     r14
0x1800db09e  pop     r13
0x1800db0a0  pop     rdi
0x1800db0a1  pop     rsi
0x1800db0a2  pop     rbx
0x1800db0a3  pop     rbp
0x1800db0a4  retn
```
