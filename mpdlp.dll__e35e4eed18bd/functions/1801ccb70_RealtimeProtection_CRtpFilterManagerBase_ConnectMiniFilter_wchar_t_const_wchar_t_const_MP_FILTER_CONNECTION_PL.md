# RealtimeProtection::CRtpFilterManagerBase::ConnectMiniFilter(wchar_t const *,wchar_t const *,_MP_FILTER_CONNECTION_PLUGIN_TYPE)

- ea: `0x1801ccb70`
- end: `0x1801ccff2`
- name: `?ConnectMiniFilter@CRtpFilterManagerBase@RealtimeProtection@@UEAAJPEB_W0W4_MP_FILTER_CONNECTION_PLUGIN_TYPE@@@Z`
- size: `1154`
- prototype: `int __high(const wchar_t *, const wchar_t *, enum _MP_FILTER_CONNECTION_PLUGIN_TYPE)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002b050`
- `0x18003d6c8`
- `0x180046d10`
- `0x180050300`
- `0x180080030`
- `0x1800809d0`
- `0x180089510`
- `0x18010cb40`
- `0x18015af0c`
- `0x18015b124`
- `0x1801ccb70`
- `0x18023a290`

## import_xrefs

- `KERNEL32!Sleep` at `0x1801ccccf`
- `KERNEL32!Sleep` at `0x1801ccccf`
- `KERNEL32!CloseHandle` at `0x1801cce82`
- `KERNEL32!CloseHandle` at `0x1801ccf1d`
- `KERNEL32!CloseHandle` at `0x1801cce82`
- `KERNEL32!CloseHandle` at `0x1801ccf1d`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1801ccdf9`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1801ccdf9`
- `FLTLIB!FilterLoad` at `0x1801ccd0a`
- `FLTLIB!FilterLoad` at `0x1801ccd0a`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CRtpFilterManagerBase::ConnectMiniFilter(
        _QWORD *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        int a4)
{
  int v8; // eax
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int i; // edi
  HRESULT v13; // eax
  PVOID *v14; // rcx
  HRESULT v15; // eax
  const wchar_t *v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  PVOID *v20; // rax
  HANDLE v21; // rcx
  _BYTE v22[16]; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-28h] BYREF
  _DWORD Context[4]; // [rsp+48h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids);
  if ( a1[1] != -1 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 24LL))(a1);
    if ( v8 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids);
      return 1;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids,
        (unsigned int)v8);
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD *, const WCHAR *))(*a1 + 40LL))(a1, a2);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids,
        (unsigned int)v10);
    return v11;
  }
  for ( i = 0; i < 5; ++i )
  {
    if ( i )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids);
      Sleep(0x3E8u);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids, i + 1);
    v13 = FilterLoad(a2);
    v11 = v13;
    if ( v13 == -2147023840 || v13 == -2147024713 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_39;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids,
          (unsigned int)v13);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_36;
    }
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids,
          (unsigned int)v13);
      return v11;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_36:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
        WPP_SF_(v14[2], 29, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids);
    }
LABEL_39:
    Context[1] = 12;
    Context[0] = 2;
    Context[2] = a4;
    hObject = (HANDLE)-1LL;
    v15 = FilterConnectCommunicationPort(a3, 0, Context, 0xCu, 0, &hObject);
    v11 = v15;
    if ( v15 >= 0 )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>(
        v22,
        a1 + 2);
      CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(a1 + 1, &hObject);
      CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>::~CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>(v22);
      v21 = hObject;
      if ( hObject != (HANDLE)-1LL )
        goto LABEL_59;
      goto LABEL_60;
    }
    if ( v15 == -2147024894 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v18 = 31;
        v19 = 2147942402LL;
        goto LABEL_47;
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = 30;
        v19 = (unsigned int)v15;
LABEL_47:
        WPP_SF_d(v17[2], v18, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids, v19);
      }
    }
    if ( (unsigned int)RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(
                         (RealtimeProtection::DlpUtils *)L"MpRtp_IgnoreFilterSendMessageErrors",
                         v16) )
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"MpRtp_IgnoreFilterSendMessageErrors");
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      v21 = hObject;
      v11 = 0;
      if ( hObject != (HANDLE)-1LL )
      {
LABEL_59:
        CloseHandle(v21);
        goto LABEL_60;
      }
LABEL_61:
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 )
        WPP_SF_S(
          v20[2],
          34,
          WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids,
          L"\\MicrosoftMalwareProtectionControlPortWD");
      return v11;
    }
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
  if ( (v11 & 0x80000000) == 0 )
  {
LABEL_60:
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids, v11, i + 1);
  return v11;
}

```

## disassembly

```asm
0x1801ccb70  push    rbp
0x1801ccb72  push    rbx
0x1801ccb73  push    rsi
0x1801ccb74  push    rdi
0x1801ccb75  push    r12
0x1801ccb77  push    r13
0x1801ccb79  push    r14
0x1801ccb7b  push    r15
0x1801ccb7d  mov     rbp, rsp
0x1801ccb80  sub     rsp, 68h
0x1801ccb84  mov     rax, cs:__security_cookie
0x1801ccb8b  xor     rax, rsp
0x1801ccb8e  mov     [rbp+var_10], rax
0x1801ccb92  mov     r13d, r9d
0x1801ccb95  mov     r12, r8
0x1801ccb98  mov     r15, rdx
0x1801ccb9b  mov     rsi, rcx
0x1801ccb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccba5  lea     rdi, WPP_GLOBAL_Control
0x1801ccbac  lea     rbx, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccbb3  cmp     rcx, rdi
0x1801ccbb6  jz      short loc_1801CCBCF
0x1801ccbb8  test    byte ptr [rcx+1Ch], 4
0x1801ccbbc  jz      short loc_1801CCBCF
0x1801ccbbe  mov     rcx, [rcx+10h]
0x1801ccbc2  mov     edx, 14h
0x1801ccbc7  mov     r8, rbx
0x1801ccbca  call    WPP_SF_
0x1801ccbcf  cmp     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x1801ccbd4  jz      short loc_1801CCC3D
0x1801ccbd6  mov     rax, [rsi]
0x1801ccbd9  mov     rcx, rsi
0x1801ccbdc  mov     rax, [rax+18h]
0x1801ccbe0  call    cs:__guard_dispatch_icall_fptr
0x1801ccbe6  test    eax, eax
0x1801ccbe8  js      short loc_1801CCC17
0x1801ccbea  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccbf1  cmp     rcx, rdi
0x1801ccbf4  jz      short loc_1801CCC0D
0x1801ccbf6  test    byte ptr [rcx+1Ch], 4
0x1801ccbfa  jz      short loc_1801CCC0D
0x1801ccbfc  mov     rcx, [rcx+10h]
0x1801ccc00  mov     edx, 15h
0x1801ccc05  mov     r8, rbx
0x1801ccc08  call    WPP_SF_
0x1801ccc0d  mov     eax, 1
0x1801ccc12  jmp     loc_1801CCF5A
0x1801ccc17  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccc1e  cmp     rcx, rdi
0x1801ccc21  jz      short loc_1801CCC3D
0x1801ccc23  test    byte ptr [rcx+1Ch], 1
0x1801ccc27  jz      short loc_1801CCC3D
0x1801ccc29  mov     rcx, [rcx+10h]
0x1801ccc2d  mov     edx, 16h
0x1801ccc32  mov     r9d, eax
0x1801ccc35  mov     r8, rbx
0x1801ccc38  call    WPP_SF_d
0x1801ccc3d  mov     rax, [rsi]
0x1801ccc40  mov     rdx, r15
0x1801ccc43  mov     rcx, rsi
0x1801ccc46  mov     rax, [rax+28h]
0x1801ccc4a  call    cs:__guard_dispatch_icall_fptr
0x1801ccc50  mov     ebx, eax
0x1801ccc52  test    eax, eax
0x1801ccc54  jns     short loc_1801CCC8D
0x1801ccc56  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccc5d  cmp     rcx, rdi
0x1801ccc60  jz      loc_1801CCF58
0x1801ccc66  test    byte ptr [rcx+1Ch], 1
0x1801ccc6a  jz      loc_1801CCF58
0x1801ccc70  mov     rcx, [rcx+10h]
0x1801ccc74  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccc7b  mov     edx, 17h
0x1801ccc80  mov     r9d, eax
0x1801ccc83  call    WPP_SF_d
0x1801ccc88  jmp     loc_1801CCF58
0x1801ccc8d  xor     edi, edi
0x1801ccc8f  cmp     edi, 5
0x1801ccc92  jnb     loc_1801CCFAD
0x1801ccc98  test    edi, edi
0x1801ccc9a  jz      short loc_1801CCCD5
0x1801ccc9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccca3  lea     rax, WPP_GLOBAL_Control
0x1801cccaa  cmp     rcx, rax
0x1801cccad  jz      short loc_1801CCCCA
0x1801cccaf  test    byte ptr [rcx+1Ch], 4
0x1801cccb3  jz      short loc_1801CCCCA
0x1801cccb5  mov     rcx, [rcx+10h]
0x1801cccb9  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801cccc0  mov     edx, 18h
0x1801cccc5  call    WPP_SF_
0x1801cccca  mov     ecx, 3E8h; dwMilliseconds
0x1801ccccf  call    cs:__imp_Sleep
0x1801cccd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cccdc  lea     rax, WPP_GLOBAL_Control
0x1801ccce3  cmp     rcx, rax
0x1801ccce6  jz      short loc_1801CCD07
0x1801ccce8  test    byte ptr [rcx+1Ch], 4
0x1801cccec  jz      short loc_1801CCD07
0x1801cccee  mov     rcx, [rcx+10h]
0x1801cccf2  lea     r9d, [rdi+1]
0x1801cccf6  mov     edx, 19h
0x1801cccfb  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccd02  call    WPP_SF_d
0x1801ccd07  mov     rcx, r15; lpFilterName
0x1801ccd0a  call    cs:__imp_FilterLoad
0x1801ccd10  mov     ebx, eax
0x1801ccd12  cmp     eax, 80070420h
0x1801ccd17  jz      short loc_1801CCD63
0x1801ccd19  cmp     eax, 800700B7h
0x1801ccd1e  jz      short loc_1801CCD63
0x1801ccd20  test    eax, eax
0x1801ccd22  js      loc_1801CCE8F
0x1801ccd28  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccd2f  lea     rbx, WPP_GLOBAL_Control
0x1801ccd36  cmp     rcx, rbx
0x1801ccd39  jz      loc_1801CCDC2
0x1801ccd3f  test    byte ptr [rcx+1Ch], 4
0x1801ccd43  jz      short loc_1801CCDA2
0x1801ccd45  mov     rcx, [rcx+10h]
0x1801ccd49  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccd50  mov     edx, 1Ch
0x1801ccd55  call    WPP_SF_
0x1801ccd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccd61  jmp     short loc_1801CCDA2
0x1801ccd63  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccd6a  lea     rax, WPP_GLOBAL_Control
0x1801ccd71  cmp     rcx, rax
0x1801ccd74  jz      short loc_1801CCDC2
0x1801ccd76  test    byte ptr [rcx+1Ch], 4
0x1801ccd7a  jz      short loc_1801CCD9B
0x1801ccd7c  mov     rcx, [rcx+10h]
0x1801ccd80  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccd87  mov     edx, 1Ah
0x1801ccd8c  mov     r9d, ebx
0x1801ccd8f  call    WPP_SF_d
0x1801ccd94  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccd9b  lea     rbx, WPP_GLOBAL_Control
0x1801ccda2  cmp     rcx, rbx
0x1801ccda5  jz      short loc_1801CCDC2
0x1801ccda7  test    byte ptr [rcx+1Ch], 4
0x1801ccdab  jz      short loc_1801CCDC2
0x1801ccdad  mov     rcx, [rcx+10h]
0x1801ccdb1  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccdb8  mov     edx, 1Dh
0x1801ccdbd  call    WPP_SF_
0x1801ccdc2  xor     ecx, ecx
0x1801ccdc4  mov     [rbp+var_1C], 0Ch
0x1801ccdcb  lea     rax, [rbp+hObject]
0x1801ccdcf  mov     [rbp+Context], 2
0x1801ccdd6  mov     [rsp+68h+hPort], rax; hPort
0x1801ccddb  lea     r8, [rbp+Context]; lpContext
0x1801ccddf  mov     [rsp+68h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1801ccde4  xor     edx, edx; dwOptions
0x1801ccde6  lea     r9d, [rcx+0Ch]; wSizeOfContext
0x1801ccdea  mov     [rbp+var_18], r13d
0x1801ccdee  mov     rcx, r12; lpPortName
0x1801ccdf1  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1801ccdf9  call    cs:__imp_FilterConnectCommunicationPort
0x1801ccdff  mov     ebx, eax
0x1801cce01  test    eax, eax
0x1801cce03  jns     loc_1801CCF77
0x1801cce09  mov     r8d, 80070002h
0x1801cce0f  cmp     eax, r8d
0x1801cce12  jz      short loc_1801CCE37
0x1801cce14  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cce1b  lea     rax, WPP_GLOBAL_Control
0x1801cce22  cmp     rcx, rax
0x1801cce25  jz      short loc_1801CCE68
0x1801cce27  test    byte ptr [rcx+1Ch], 2
0x1801cce2b  jz      short loc_1801CCE68
0x1801cce2d  mov     edx, 1Eh
0x1801cce32  mov     r9d, ebx
0x1801cce35  jmp     short loc_1801CCE58
0x1801cce37  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cce3e  lea     rax, WPP_GLOBAL_Control
0x1801cce45  cmp     rcx, rax
0x1801cce48  jz      short loc_1801CCE68
0x1801cce4a  test    byte ptr [rcx+1Ch], 4
0x1801cce4e  jz      short loc_1801CCE68
0x1801cce50  mov     edx, 1Fh
0x1801cce55  mov     r9d, r8d
0x1801cce58  mov     rcx, [rcx+10h]
0x1801cce5c  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801cce63  call    WPP_SF_d
0x1801cce68  lea     rcx, aMprtpIgnorefil; "MpRtp_IgnoreFilterSendMessageErrors"
0x1801cce6f  call    ?DlpMpLookupMiscConfigFlag@DlpUtils@RealtimeProtection@@YAHPEB_W@Z; RealtimeProtection::DlpUtils::DlpMpLookupMiscConfigFlag(wchar_t const *)
0x1801cce74  test    eax, eax
0x1801cce76  jnz     short loc_1801CCECD
0x1801cce78  mov     rcx, [rbp+hObject]; hObject
0x1801cce7c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801cce80  jz      short loc_1801CCE88
0x1801cce82  call    cs:__imp_CloseHandle
0x1801cce88  inc     edi
0x1801cce8a  jmp     loc_1801CCC8F
0x1801cce8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cce96  lea     rax, WPP_GLOBAL_Control
0x1801cce9d  cmp     rcx, rax
0x1801ccea0  jz      loc_1801CCF58
0x1801ccea6  test    byte ptr [rcx+1Ch], 1
0x1801cceaa  jz      loc_1801CCF58
0x1801cceb0  mov     rcx, [rcx+10h]
0x1801cceb4  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccebb  mov     edx, 1Bh
0x1801ccec0  mov     r9d, ebx
0x1801ccec3  call    WPP_SF_d
0x1801ccec8  jmp     loc_1801CCF58
0x1801ccecd  mov     rax, cs:WPP_GLOBAL_Control
0x1801cced4  lea     rcx, WPP_GLOBAL_Control
0x1801ccedb  cmp     rax, rcx
0x1801ccede  jz      short loc_1801CCF11
0x1801ccee0  test    byte ptr [rax+1Ch], 1
0x1801ccee4  jz      short loc_1801CCF11
0x1801ccee6  lea     rcx, aMprtpIgnorefil; "MpRtp_IgnoreFilterSendMessageErrors"
0x1801cceed  mov     edx, 20h ; ' '
0x1801ccef2  mov     [rsp+68h+lpSecurityAttributes], rcx; __int64
0x1801ccef7  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccefe  mov     rcx, [rax+10h]; LoggerHandle
0x1801ccf02  mov     r9d, ebx
0x1801ccf05  call    WPP_SF_dS
0x1801ccf0a  mov     rax, cs:WPP_GLOBAL_Control
0x1801ccf11  mov     rcx, [rbp+hObject]; hObject
0x1801ccf15  xor     ebx, ebx
0x1801ccf17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801ccf1b  jz      short loc_1801CCF2A
0x1801ccf1d  call    cs:__imp_CloseHandle
0x1801ccf23  mov     rax, cs:WPP_GLOBAL_Control
0x1801ccf2a  lea     rcx, WPP_GLOBAL_Control
0x1801ccf31  cmp     rax, rcx
0x1801ccf34  jz      short loc_1801CCF58
0x1801ccf36  test    byte ptr [rax+1Ch], 4
0x1801ccf3a  jz      short loc_1801CCF58
0x1801ccf3c  mov     rcx, [rax+10h]
0x1801ccf40  lea     r9, aMicrosoftmalwa; "\\MicrosoftMalwareProtectionControlPort"...
0x1801ccf47  mov     edx, 22h ; '"'
0x1801ccf4c  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccf53  call    WPP_SF_S
0x1801ccf58  mov     eax, ebx
0x1801ccf5a  mov     rcx, [rbp+var_10]
0x1801ccf5e  xor     rcx, rsp; StackCookie
0x1801ccf61  call    __security_check_cookie
0x1801ccf66  add     rsp, 68h
0x1801ccf6a  pop     r15
0x1801ccf6c  pop     r14
0x1801ccf6e  pop     r13
0x1801ccf70  pop     r12
0x1801ccf72  pop     rdi
0x1801ccf73  pop     rsi
0x1801ccf74  pop     rbx
0x1801ccf75  pop     rbp
0x1801ccf76  retn
0x1801ccf77  lea     rdx, [rsi+10h]
0x1801ccf7b  lea     rcx, [rbp+var_38]
0x1801ccf7f  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpReadWriteLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpReadWriteLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>(CommonUtil::CMpReadWriteLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>::ENUM_LOCK_INITIAL_STATE)
0x1801ccf84  lea     rdx, [rbp+hObject]
0x1801ccf88  lea     rcx, [rsi+8]
0x1801ccf8c  call    ?Swap@?$CUniqueHandle@UCAutoCloseBCryptHashHandle@CommonUtil@@@CommonUtil@@QEAAXAEAV12@@Z; CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle> &)
0x1801ccf91  lea     rcx, [rbp+var_38]
0x1801ccf95  call    ??1?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpReadWriteLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>::~CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpReadWriteLock>>(void)
0x1801ccf9a  mov     rcx, [rbp+hObject]
0x1801ccf9e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801ccfa2  jz      loc_1801CCF23
0x1801ccfa8  jmp     loc_1801CCF1D
0x1801ccfad  test    ebx, ebx
0x1801ccfaf  jns     loc_1801CCF23
0x1801ccfb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ccfbc  lea     rax, WPP_GLOBAL_Control
0x1801ccfc3  cmp     rcx, rax
0x1801ccfc6  jz      short loc_1801CCF58
0x1801ccfc8  test    byte ptr [rcx+1Ch], 1
0x1801ccfcc  jz      short loc_1801CCF58
0x1801ccfce  mov     rcx, [rcx+10h]
0x1801ccfd2  lea     eax, [rdi+1]
0x1801ccfd5  mov     edx, 21h ; '!'
0x1801ccfda  mov     dword ptr [rsp+68h+lpSecurityAttributes], eax
0x1801ccfde  mov     r9d, ebx
0x1801ccfe1  lea     r8, WPP_cfe10a2b1cfe308824792cf3663065e9_Traceguids
0x1801ccfe8  call    WPP_SF_Dd
0x1801ccfed  jmp     loc_1801CCF58
```
