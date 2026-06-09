# RealtimeProtection::CSenseCloudCncProxy::GetAadUserInfo(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180083cc8`
- end: `0x1800843f6`
- name: `?GetAadUserInfo@CSenseCloudCncProxy@RealtimeProtection@@AEAAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111@Z`
- size: `1838`
- prototype: `__int64 __fastcall(int, int, int, int, void *, void *)`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005fc80`
- `0x180237110`
- `0x18023792c`
- `0x180238038`

## callees

- `0x180004544`
- `0x180005c28`
- `0x180034420`
- `0x18004b3bc`
- `0x1800809d0`
- `0x180083cc8`
- `0x1800843f8`
- `0x1800844bc`
- `0x180089510`
- `0x1800a9d78`
- `0x1800c79a4`
- `0x1800ca044`
- `0x1800ccd80`
- `0x180101f64`
- `0x180101f6c`
- `0x180105f50`
- `0x180106cc4`
- `0x18010cb40`
- `0x18023a310`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800840e6`
- `KERNEL32!CompareStringOrdinal` at `0x1800840e6`
- `KERNEL32!CloseHandle` at `0x180083d69`
- `KERNEL32!CloseHandle` at `0x1800843cd`
- `KERNEL32!CloseHandle` at `0x180083d69`
- `KERNEL32!CloseHandle` at `0x1800843cd`
- `ADVAPI32!SetThreadToken` at `0x180083d8c`
- `ADVAPI32!SetThreadToken` at `0x180083d8c`
- `ADVAPI32!RevertToSelf` at `0x180083e02`
- `ADVAPI32!RevertToSelf` at `0x1800843bd`
- `ADVAPI32!RevertToSelf` at `0x180083e02`
- `ADVAPI32!RevertToSelf` at `0x1800843bd`
- `Secur32!GetUserNameExW` at `0x180083fc2`
- `Secur32!GetUserNameExW` at `0x180084057`
- `Secur32!GetUserNameExW` at `0x180083fc2`
- `Secur32!GetUserNameExW` at `0x180084057`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RealtimeProtection::CSenseCloudCncProxy::GetAadUserInfo(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        void *a6)
{
  __int64 v7; // rdi
  bool v9; // r15
  int v10; // eax
  int AadJoinInfo; // ebx
  struct _DSREG_JOIN_INFO **v13; // rdx
  __int64 v14; // rbx
  void *v15; // rdx
  void *v16; // rdx
  int AadUserAccountInfo; // r14d
  wchar_t *v18; // r13
  _QWORD *v19; // rax
  PVOID *v20; // rcx
  WCHAR *v21; // rdx
  unsigned __int64 v22; // rcx
  WCHAR *v23; // rax
  size_t v24; // rdi
  const WCHAR *v25; // r8
  const WCHAR *v26; // rcx
  wchar_t *v27; // rdx
  __int128 v28; // xmm2
  __int128 v29; // xmm3
  __int128 v30; // xmm2
  __m128i v31; // xmm3
  struct _RTL_CRITICAL_SECTION *v32; // rdi
  int v33; // r9d
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-130h]
  __int16 v35; // [rsp+D0h] [rbp-80h] BYREF
  bool v36; // [rsp+D2h] [rbp-7Eh] BYREF
  __int64 v37; // [rsp+D8h] [rbp-78h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-68h] BYREF
  int v40; // [rsp+F0h] [rbp-60h] BYREF
  int v41; // [rsp+F4h] [rbp-5Ch] BYREF
  int v42; // [rsp+F8h] [rbp-58h] BYREF
  int v43; // [rsp+FCh] [rbp-54h] BYREF
  int v44; // [rsp+100h] [rbp-50h] BYREF
  int v45; // [rsp+104h] [rbp-4Ch] BYREF
  int v46; // [rsp+108h] [rbp-48h] BYREF
  __int64 v47[2]; // [rsp+110h] [rbp-40h] BYREF
  __int64 v48; // [rsp+120h] [rbp-30h] BYREF
  __int64 v49; // [rsp+128h] [rbp-28h] BYREF
  __int64 v50; // [rsp+130h] [rbp-20h] BYREF
  __int64 v51; // [rsp+138h] [rbp-18h] BYREF
  __int64 v52; // [rsp+140h] [rbp-10h] BYREF
  __int64 v53; // [rsp+148h] [rbp-8h] BYREF
  __int64 v54; // [rsp+150h] [rbp+0h] BYREF
  ULONG nSize; // [rsp+158h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+160h] [rbp+10h] BYREF
  LPWSTR lpNameBuffer[2]; // [rsp+168h] [rbp+18h] BYREF
  __int64 v58; // [rsp+178h] [rbp+28h]
  LPCWCH lpString1[2]; // [rsp+180h] [rbp+30h] BYREF
  __int128 v60; // [rsp+190h] [rbp+40h]
  __int128 v61; // [rsp+1A0h] [rbp+50h] BYREF
  __m128i si128; // [rsp+1B0h] [rbp+60h]

  v7 = a3;
  v39 = a3;
  v37 = a1;
  v9 = 0;
  hObject = 0;
  v10 = CommonUtil::UtilDuplicateToken(&hObject, a2, SecurityImpersonation, 0xCu, bIgnoreCase);
  AadJoinInfo = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
        (unsigned int)v10);
LABEL_5:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)AadJoinInfo;
  }
  v47[1] = 0;
  v13 = (struct _DSREG_JOIN_INFO **)hObject;
  v47[0] = (__int64)hObject;
  if ( hObject )
    v9 = SetThreadToken(0, hObject);
  LOBYTE(v47[1]) = v9;
  v35 = 0;
  v38 = 0;
  AadJoinInfo = CommonUtil::UtilGetAadJoinInfo((CommonUtil *)&v38, v13);
  if ( AadJoinInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
        (unsigned int)AadJoinInfo);
    if ( v38 )
      NetFreeAadJoinInformationWrapper(v38);
LABEL_16:
    if ( v9 )
      RevertToSelf();
    goto LABEL_5;
  }
  v14 = v38;
  if ( !v38 )
  {
    AadJoinInfo = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids, 2147500037LL);
    goto LABEL_16;
  }
  v15 = *(void **)(v38 + 16);
  if ( v15 )
    std::wstring::assign(a6, v15);
  v16 = *(void **)(v14 + 32);
  if ( v16 )
    std::wstring::assign(a5, v16);
  *(_OWORD *)lpString1 = 0;
  *(_QWORD *)&v60 = 0;
  *((_QWORD *)&v60 + 1) = 7;
  LOWORD(lpString1[0]) = 0;
  v61 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v61) = 0;
  AadUserAccountInfo = RealtimeProtection::CSenseCloudCncProxy::GetAadUserAccountInfo(v37, a2, lpString1, &v61);
  if ( AadUserAccountInfo >= 0 && (_QWORD)v60 )
    goto LABEL_76;
  nSize = 512;
  *(_OWORD *)lpNameBuffer = 0;
  v58 = 0;
  std::vector<wchar_t>::vector<wchar_t>(lpNameBuffer, 512);
  v18 = 0;
  v19 = *(_QWORD **)(v14 + 88);
  if ( v19 && *v19 )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    v18 = **(wchar_t ***)(v14 + 88);
  }
  else if ( *(_QWORD *)(v14 + 40) )
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    v18 = *(wchar_t **)(v14 + 40);
  }
  else
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *(_DWORD *)v14 != 1 )
  {
    if ( *(_DWORD *)v14 == 2 )
    {
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
        WPP_SF_(v20[2], 56, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids);
      v27 = (wchar_t *)&qword_18025C818;
      if ( v18 )
        v27 = v18;
      std::wstring::assign(lpString1, v27);
      HIBYTE(v35) = 1;
    }
    else
    {
      AadUserAccountInfo = -2147023564;
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
        WPP_SF_d(v20[2], 57, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids, 2147943732LL);
    }
    goto LABEL_75;
  }
  if ( !GetUserNameExW(NameUserPrincipal, lpNameBuffer[0], &nSize) )
  {
    AadUserAccountInfo = HrGetLastFailure();
    if ( AadUserAccountInfo == -2147024662 )
    {
      v37 = (__int64)lpNameBuffer[1];
      v21 = lpNameBuffer[0];
      v22 = lpNameBuffer[1] - lpNameBuffer[0];
      if ( nSize < v22 )
      {
        v23 = &lpNameBuffer[0][nSize];
LABEL_52:
        lpNameBuffer[1] = v23;
        goto LABEL_53;
      }
      if ( nSize > v22 )
      {
        if ( nSize <= (unsigned __int64)((signed __int64)(v58 - (unsigned __int64)lpNameBuffer[0]) >> 1) )
        {
          v24 = 2 * (nSize - v22);
          memset(lpNameBuffer[1], 0, v24);
          v23 = (WCHAR *)(v24 + v37);
          v21 = lpNameBuffer[0];
          goto LABEL_52;
        }
        _mm_lfence();
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(lpNameBuffer, nSize);
        v21 = lpNameBuffer[0];
      }
LABEL_53:
      if ( GetUserNameExW(NameUserPrincipal, v21, &nSize) )
        goto LABEL_56;
      AadUserAccountInfo = HrGetLastFailure();
      v7 = v39;
    }
  }
  if ( AadUserAccountInfo >= 0 )
  {
    std::wstring::assign(lpString1, lpNameBuffer[0]);
    v25 = &qword_18025C818;
    if ( v18 )
      v25 = v18;
    v26 = (const WCHAR *)lpString1;
    if ( *((_QWORD *)&v60 + 1) > 7u )
      v26 = lpString1[0];
    LOBYTE(v35) = CompareStringOrdinal(v26, -1, v25, -1, 1) == 2;
LABEL_75:
    std::vector<wchar_t>::_Tidy(lpNameBuffer);
LABEL_76:
    if ( (LPCWCH *)v7 != lpString1 )
    {
      v28 = *(_OWORD *)v7;
      v29 = *(_OWORD *)(v7 + 16);
      *(_OWORD *)v7 = *(_OWORD *)lpString1;
      *(_OWORD *)(v7 + 16) = v60;
      *(_OWORD *)lpString1 = v28;
      v60 = v29;
    }
    if ( (__int128 *)a4 != &v61 )
    {
      v30 = *(_OWORD *)a4;
      v31 = *(__m128i *)(a4 + 16);
      *(_OWORD *)a4 = v61;
      *(__m128i *)(a4 + 16) = si128;
      v61 = v30;
      si128 = v31;
    }
    v32 = g_pcsAsimovLock;
    if ( g_pcsAsimovLock )
    {
      Mtxlock(g_pcsAsimovLock);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
      {
        v36 = *(_QWORD *)(v39 + 16) == 0;
        if ( *(_QWORD *)(a4 + 24) > 7u )
          a4 = *(_QWORD *)a4;
        v48 = a4;
        v40 = *(_DWORD *)v14;
        v41 = AadUserAccountInfo;
        v42 = *((_DWORD *)g_aAsimov + 18);
        v43 = *((_DWORD *)g_aAsimov + 17);
        v44 = *((_DWORD *)g_aAsimov + 16);
        v45 = *((unsigned __int8 *)g_aAsimov + 60);
        v46 = *((unsigned __int8 *)g_aAsimov + 59);
        LODWORD(v37) = *((unsigned __int8 *)g_aAsimov + 58);
        LODWORD(v39) = *((unsigned __int8 *)g_aAsimov + 57);
        LODWORD(v38) = *((unsigned __int8 *)g_aAsimov + 56);
        v49 = *((_QWORD *)g_aAsimov + 6);
        v50 = *((_QWORD *)g_aAsimov + 5);
        v51 = *((_QWORD *)g_aAsimov + 4);
        v52 = *((_QWORD *)g_aAsimov + 3);
        v53 = *((_QWORD *)g_aAsimov + 2);
        v54 = *((_QWORD *)g_aAsimov + 1);
        v47[0] = 0x2000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>>(
          v33,
          (int)&byte_1802CBA47,
          (__int64)v47,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v50,
          (__int64)&v49,
          (__int64)&v38,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v35 + 1,
          (__int64)&v35,
          (__int64)&v48,
          (__int64)&v36);
      }
      Mtxunlock(v32);
    }
    goto LABEL_87;
  }
LABEL_56:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
      (unsigned int)AadUserAccountInfo);
  std::vector<wchar_t>::_Tidy(lpNameBuffer);
LABEL_87:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v61);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString1);
  NetFreeAadJoinInformationWrapper(v14);
  if ( v9 )
    RevertToSelf();
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)AadUserAccountInfo;
}

```

## disassembly

```asm
0x180083cc8  push    rbp
0x180083cca  push    rbx
0x180083ccb  push    rsi
0x180083ccc  push    rdi
0x180083ccd  push    r12
0x180083ccf  push    r13
0x180083cd1  push    r14
0x180083cd3  push    r15
0x180083cd5  lea     rbp, [rsp-88h]
0x180083cdd  sub     rsp, 1D8h
0x180083ce4  mov     rax, cs:__security_cookie
0x180083ceb  xor     rax, rsp
0x180083cee  mov     [rbp+0C0h+var_50], rax
0x180083cf2  mov     r12, r9
0x180083cf5  mov     rdi, r8
0x180083cf8  mov     [rbp+0C0h+var_128], r8
0x180083cfc  mov     rsi, rdx
0x180083cff  mov     [rbp+0C0h+var_138], rcx
0x180083d03  mov     r13, [rbp+0C0h+arg_20]
0x180083d0a  mov     r14, [rbp+0C0h+arg_28]
0x180083d11  xor     r15d, r15d
0x180083d14  mov     [rbp+0C0h+hObject], r15
0x180083d18  lea     r9d, [r15+0Ch]; dwDesiredAccess
0x180083d1c  lea     r8d, [r15+2]; ImpersonationLevel
0x180083d20  lea     rcx, [rbp+0C0h+hObject]; phNewToken
0x180083d24  call    ?UtilDuplicateToken@CommonUtil@@YAJPEAPEAXPEAXW4_SECURITY_IMPERSONATION_LEVEL@@K@Z; CommonUtil::UtilDuplicateToken(void * *,void *,_SECURITY_IMPERSONATION_LEVEL,ulong)
0x180083d29  mov     ebx, eax
0x180083d2b  test    eax, eax
0x180083d2d  jns     short loc_180083D76
0x180083d2f  lea     rsi, WPP_GLOBAL_Control
0x180083d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180083d3d  cmp     rcx, rsi
0x180083d40  jz      short loc_180083D60
0x180083d42  test    byte ptr [rcx+1Ch], 1
0x180083d46  jz      short loc_180083D60
0x180083d48  lea     edx, [r15+31h]
0x180083d4c  mov     r9d, eax
0x180083d4f  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083d56  mov     rcx, [rcx+10h]
0x180083d5a  call    WPP_SF_d
0x180083d5f  nop
0x180083d60  mov     rcx, [rbp+0C0h+hObject]; hObject
0x180083d64  test    rcx, rcx
0x180083d67  jz      short loc_180083D6F
0x180083d69  call    cs:__imp_CloseHandle
0x180083d6f  mov     eax, ebx
0x180083d71  jmp     loc_1800843D6
0x180083d76  xorps   xmm0, xmm0
0x180083d79  movups  xmmword ptr [rbp+0C0h+var_100], xmm0
0x180083d7d  mov     rdx, [rbp+0C0h+hObject]; Token
0x180083d81  mov     [rbp+0C0h+var_100], rdx
0x180083d85  test    rdx, rdx
0x180083d88  jz      short loc_180083D99
0x180083d8a  xor     ecx, ecx; Thread
0x180083d8c  call    cs:__imp_SetThreadToken
0x180083d92  test    eax, eax
0x180083d94  jz      short loc_180083D99
0x180083d96  mov     r15b, 1
0x180083d99  mov     byte ptr [rbp+0C0h+var_100+8], r15b
0x180083d9d  xor     eax, eax
0x180083d9f  mov     byte ptr [rbp+0C0h+var_140], al
0x180083da2  mov     byte ptr [rbp+0C0h+var_140+1], al
0x180083da5  mov     [rbp+0C0h+var_130], rax
0x180083da9  lea     rcx, [rbp+0C0h+var_130]; this
0x180083dad  call    ?UtilGetAadJoinInfo@CommonUtil@@YAJPEAPEAU_DSREG_JOIN_INFO@@@Z; CommonUtil::UtilGetAadJoinInfo(_DSREG_JOIN_INFO * *)
0x180083db2  mov     ebx, eax
0x180083db4  xor     eax, eax
0x180083db6  test    ebx, ebx
0x180083db8  jns     short loc_180083E0D
0x180083dba  lea     rsi, WPP_GLOBAL_Control
0x180083dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180083dc8  cmp     rcx, rsi
0x180083dcb  jz      short loc_180083DEA
0x180083dcd  test    byte ptr [rcx+1Ch], 1
0x180083dd1  jz      short loc_180083DEA
0x180083dd3  lea     edx, [rax+32h]
0x180083dd6  mov     r9d, ebx
0x180083dd9  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083de0  mov     rcx, [rcx+10h]
0x180083de4  call    WPP_SF_d
0x180083de9  nop
0x180083dea  mov     rcx, [rbp+0C0h+var_130]
0x180083dee  test    rcx, rcx
0x180083df1  jz      short loc_180083DF9
0x180083df3  call    NetFreeAadJoinInformationWrapper
0x180083df8  nop
0x180083df9  test    r15b, r15b
0x180083dfc  jz      loc_180083D60
0x180083e02  call    cs:__imp_RevertToSelf
0x180083e08  jmp     loc_180083D60
0x180083e0d  mov     rbx, [rbp+0C0h+var_130]
0x180083e11  test    rbx, rbx
0x180083e14  jnz     short loc_180083E4F
0x180083e16  lea     rsi, WPP_GLOBAL_Control
0x180083e1d  mov     ebx, 80004005h
0x180083e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e29  cmp     rcx, rsi
0x180083e2c  jz      short loc_180083E4D
0x180083e2e  test    byte ptr [rcx+1Ch], 2
0x180083e32  jz      short loc_180083E4D
0x180083e34  mov     edx, 33h ; '3'
0x180083e39  mov     r9d, ebx
0x180083e3c  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083e43  mov     rcx, [rcx+10h]
0x180083e47  call    WPP_SF_d
0x180083e4c  nop
0x180083e4d  jmp     short loc_180083DF9
0x180083e4f  mov     rdx, [rbx+10h]; Src
0x180083e53  test    rdx, rdx
0x180083e56  jz      short loc_180083E62
0x180083e58  mov     rcx, r14; void *
0x180083e5b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180083e60  xor     eax, eax
0x180083e62  mov     rdx, [rbx+20h]; Src
0x180083e66  test    rdx, rdx
0x180083e69  jz      short loc_180083E75
0x180083e6b  mov     rcx, r13; void *
0x180083e6e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180083e73  xor     eax, eax
0x180083e75  xorps   xmm0, xmm0
0x180083e78  movups  xmmword ptr [rbp+0C0h+lpString1], xmm0
0x180083e7c  mov     qword ptr [rbp+0C0h+var_80], rax
0x180083e80  mov     qword ptr [rbp+0C0h+var_80+8], 7
0x180083e88  mov     word ptr [rbp+0C0h+lpString1], ax
0x180083e8c  movups  [rbp+0C0h+var_70], xmm0
0x180083e90  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180083e98  movdqu  [rbp+0C0h+var_60], xmm1
0x180083e9d  mov     word ptr [rbp+0C0h+var_70], ax
0x180083ea1  lea     r9, [rbp+0C0h+var_70]
0x180083ea5  lea     r8, [rbp+0C0h+lpString1]
0x180083ea9  mov     rdx, rsi
0x180083eac  mov     rcx, [rbp+0C0h+var_138]
0x180083eb0  call    ?GetAadUserAccountInfo@CSenseCloudCncProxy@RealtimeProtection@@AEAAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; RealtimeProtection::CSenseCloudCncProxy::GetAadUserAccountInfo(void *,std::wstring &,std::wstring &)
0x180083eb5  mov     r14d, eax
0x180083eb8  xor     esi, esi
0x180083eba  test    eax, eax
0x180083ebc  js      short loc_180083EC8
0x180083ebe  cmp     qword ptr [rbp+0C0h+var_80], rsi
0x180083ec2  jnz     loc_18008416D
0x180083ec8  mov     edx, 200h
0x180083ecd  mov     [rbp+0C0h+nSize], edx
0x180083ed0  xorps   xmm0, xmm0
0x180083ed3  xor     eax, eax
0x180083ed5  movups  xmmword ptr [rbp+0C0h+lpNameBuffer], xmm0
0x180083ed9  mov     [rbp+0C0h+var_98], rax
0x180083edd  lea     rcx, [rbp+0C0h+lpNameBuffer]
0x180083ee1  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180083ee6  nop
0x180083ee7  mov     r13, rsi
0x180083eea  mov     rax, [rbx+58h]
0x180083eee  test    rax, rax
0x180083ef1  jz      short loc_180083F36
0x180083ef3  cmp     [rax], rsi
0x180083ef6  jz      short loc_180083F36
0x180083ef8  lea     rsi, WPP_GLOBAL_Control
0x180083eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f06  cmp     rcx, rsi
0x180083f09  jz      short loc_180083F2D
0x180083f0b  test    byte ptr [rcx+1Ch], 4
0x180083f0f  jz      short loc_180083F2D
0x180083f11  mov     edx, 34h ; '4'
0x180083f16  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083f1d  mov     rcx, [rcx+10h]
0x180083f21  call    WPP_SF_
0x180083f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f2d  mov     rax, [rbx+58h]
0x180083f31  mov     r13, [rax]
0x180083f34  jmp     short loc_180083FAC
0x180083f36  cmp     [rbx+28h], rsi
0x180083f3a  jz      short loc_180083F77
0x180083f3c  lea     rsi, WPP_GLOBAL_Control
0x180083f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f4a  cmp     rcx, rsi
0x180083f4d  jz      short loc_180083F71
0x180083f4f  test    byte ptr [rcx+1Ch], 4
0x180083f53  jz      short loc_180083F71
0x180083f55  mov     edx, 35h ; '5'
0x180083f5a  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083f61  mov     rcx, [rcx+10h]
0x180083f65  call    WPP_SF_
0x180083f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f71  mov     r13, [rbx+28h]
0x180083f75  jmp     short loc_180083FAC
0x180083f77  lea     rsi, WPP_GLOBAL_Control
0x180083f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f85  cmp     rcx, rsi
0x180083f88  jz      short loc_180083FAC
0x180083f8a  test    byte ptr [rcx+1Ch], 2
0x180083f8e  jz      short loc_180083FAC
0x180083f90  mov     edx, 36h ; '6'
0x180083f95  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180083f9c  mov     rcx, [rcx+10h]
0x180083fa0  call    WPP_SF_
0x180083fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180083fac  cmp     dword ptr [rbx], 1
0x180083faf  jnz     loc_1800840F5
0x180083fb5  lea     r8, [rbp+0C0h+nSize]; nSize
0x180083fb9  mov     rdx, [rbp+0C0h+lpNameBuffer]; lpNameBuffer
0x180083fbd  mov     ecx, 8; NameFormat
0x180083fc2  call    cs:__imp_GetUserNameExW
0x180083fc8  test    al, al
0x180083fca  jnz     loc_18008406D
0x180083fd0  call    HrGetLastFailure
0x180083fd5  mov     r14d, eax
0x180083fd8  cmp     eax, 800700EAh
0x180083fdd  jnz     loc_18008406D
0x180083fe3  mov     edi, [rbp+0C0h+nSize]
0x180083fe6  mov     r9, [rbp+0C0h+lpNameBuffer+8]
0x180083fea  mov     [rbp+0C0h+var_138], r9
0x180083fee  mov     rcx, r9
0x180083ff1  mov     rdx, [rbp+0C0h+lpNameBuffer]
0x180083ff5  sub     rcx, rdx
0x180083ff8  sar     rcx, 1
0x180083ffb  cmp     rdi, rcx
0x180083ffe  jnb     short loc_180084006
0x180084000  lea     rax, [rdx+rdi*2]
0x180084004  jmp     short loc_18008404A
0x180084006  jbe     short loc_18008404E
0x180084008  mov     rax, [rbp+0C0h+var_98]
0x18008400c  sub     rax, rdx
0x18008400f  sar     rax, 1
0x180084012  cmp     rdi, rax
0x180084015  jbe     short loc_18008402C
0x180084017  lfence
0x18008401a  mov     rdx, rdi
0x18008401d  lea     rcx, [rbp+0C0h+lpNameBuffer]
0x180084021  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180084026  mov     rdx, [rbp+0C0h+lpNameBuffer]
0x18008402a  jmp     short loc_18008404E
0x18008402c  sub     rdi, rcx
0x18008402f  add     rdi, rdi
0x180084032  mov     r8, rdi; Size
0x180084035  xor     edx, edx; Val
0x180084037  mov     rcx, r9; void *
0x18008403a  call    memset
0x18008403f  mov     rax, [rbp+0C0h+var_138]
0x180084043  add     rax, rdi
0x180084046  mov     rdx, [rbp+0C0h+lpNameBuffer]; lpNameBuffer
0x18008404a  mov     [rbp+0C0h+lpNameBuffer+8], rax
0x18008404e  lea     r8, [rbp+0C0h+nSize]; nSize
0x180084052  mov     ecx, 8; NameFormat
0x180084057  call    cs:__imp_GetUserNameExW
0x18008405d  test    al, al
0x18008405f  jnz     short loc_180084072
0x180084061  call    HrGetLastFailure
0x180084066  mov     r14d, eax
0x180084069  mov     rdi, [rbp+0C0h+var_128]
0x18008406d  test    r14d, r14d
0x180084070  jns     short loc_1800840AB
0x180084072  mov     rcx, cs:WPP_GLOBAL_Control
0x180084079  cmp     rcx, rsi
0x18008407c  jz      short loc_18008409D
0x18008407e  test    byte ptr [rcx+1Ch], 1
0x180084082  jz      short loc_18008409D
0x180084084  mov     edx, 37h ; '7'
0x180084089  mov     r9d, r14d
0x18008408c  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180084093  mov     rcx, [rcx+10h]
0x180084097  call    WPP_SF_d
0x18008409c  nop
0x18008409d  lea     rcx, [rbp+0C0h+lpNameBuffer]
0x1800840a1  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800840a6  jmp     loc_18008439B
0x1800840ab  mov     rdx, [rbp+0C0h+lpNameBuffer]; Src
0x1800840af  lea     rcx, [rbp+0C0h+lpString1]; void *
0x1800840b3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800840b8  lea     r8, qword_18025C818
0x1800840bf  xor     esi, esi
0x1800840c1  test    r13, r13
0x1800840c4  cmovnz  r8, r13; lpString2
0x1800840c8  lea     rcx, [rbp+0C0h+lpString1]
0x1800840cc  cmp     qword ptr [rbp+0C0h+var_80+8], 7
0x1800840d1  cmova   rcx, [rbp+0C0h+lpString1]; lpString1
0x1800840d6  mov     [rsp+210h+bIgnoreCase], 1; bIgnoreCase
0x1800840de  or      eax, 0FFFFFFFFh
0x1800840e1  mov     r9d, eax; cchCount2
0x1800840e4  mov     edx, eax; cchCount1
0x1800840e6  call    cs:__imp_CompareStringOrdinal
0x1800840ec  cmp     eax, 2
0x1800840ef  setz    byte ptr [rbp+0C0h+var_140]
0x1800840f3  jmp     short loc_180084164
0x1800840f5  cmp     dword ptr [rbx], 2
0x1800840f8  jnz     short loc_180084139
0x1800840fa  cmp     rcx, rsi
0x1800840fd  jz      short loc_18008411A
0x1800840ff  test    byte ptr [rcx+1Ch], 2
0x180084103  jz      short loc_18008411A
0x180084105  mov     edx, 38h ; '8'
0x18008410a  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180084111  mov     rcx, [rcx+10h]
0x180084115  call    WPP_SF_
0x18008411a  lea     rdx, qword_18025C818
0x180084121  xor     esi, esi
0x180084123  test    r13, r13
0x180084126  cmovnz  rdx, r13; Src
0x18008412a  lea     rcx, [rbp+0C0h+lpString1]; void *
0x18008412e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180084133  mov     byte ptr [rbp+0C0h+var_140+1], 1
0x180084137  jmp     short loc_180084164
0x180084139  mov     r14d, 80070534h
  ... truncated ...
```
