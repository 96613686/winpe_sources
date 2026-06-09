# CRdpHintManager::PopulateWindowNamesFromRegistry(void)

- ea: `0x140035550`
- end: `0x140035a61`
- name: `?PopulateWindowNamesFromRegistry@CRdpHintManager@@AEAAJXZ`
- size: `1297`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400340a4`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140004cf4`
- `0x140005704`
- `0x140005750`
- `0x140008c9c`
- `0x14000a640`
- `0x14000c7cc`
- `0x140011054`
- `0x140021534`
- `0x1400308a8`
- `0x140030b18`
- `0x1400351b8`
- `0x140035550`
- `0x140035dd8`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035a24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035642`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035642`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140035762`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400358c3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140035762`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400358c3`

## string_xrefs

- `0x140035936`: `StringCchCopy() failed`
- `0x1400355f4`: `OpenCurrentWinStationListenerKey() failed`
- `0x14003595f`: `"CRdpRefCountString::CreateInstance()"`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::PopulateWindowNamesFromRegistry(CRdpHintManager *this)
{
  CRdpRefCountString *v1; // r14
  int v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  DWORD v9; // r12d
  CVPtrList *v10; // r13
  LSTATUS i; // eax
  unsigned int v12; // ecx
  LSTATUS v13; // edi
  unsigned int v14; // eax
  void *v15; // rdi
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // eax
  const wchar_t *v19; // rcx
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  CRdpRefCountString *v26; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[128]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[2048]; // [rsp+170h] [rbp+70h] BYREF

  cchValueName = 128;
  hKey = 0;
  phkResult = 0;
  Type = 0;
  v1 = 0;
  cbData = 2048;
  v26 = 0;
  v3 = CRdpHintManager::OpenCurrentWinStationListenerKey(this, &hKey);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 97;
      v6 = "OpenCurrentWinStationListenerKey() failed";
LABEL_6:
      LODWORD(lpType) = v3;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v6,
        lpType);
    }
    goto LABEL_55;
  }
  if ( RegOpenKeyExW(hKey, L"VideoRemotingWindowNames", 0, 0x20019u, &phkResult) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids, v7, 1);
    }
    v3 = 1;
    goto LABEL_55;
  }
  if ( !phkResult )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v8,
        -2147418113);
    }
    v3 = -2147418113;
    goto LABEL_55;
  }
  v9 = 0;
  memset_0(Data, 0, sizeof(Data));
  memset_0(ValueName, 0, sizeof(ValueName));
  v10 = (CRdpHintManager *)((char *)this + 136);
  CComPtrList<CRdpRefCountString,ComPlainSmartPtr<CRdpRefCountString>>::RemoveAll((CRdpHintManager *)((char *)this + 136));
  for ( i = RegEnumValueW(phkResult, 0, ValueName, &cchValueName, 0, &Type, Data, &cbData);
        ;
        i = RegEnumValueW(phkResult, v9, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
  {
    v13 = i;
    if ( i )
    {
      if ( i != 259 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = L"ERROR_MORE_DATA";
          if ( v13 != 234 )
            v19 = L"[Unknown]";
          WPP_SF_DSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
            v18,
            (__int64)v19,
            v13);
        }
        v3 = -2147467259;
      }
      goto LABEL_55;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v14,
        (__int64)ValueName);
    }
    if ( Type != 1 )
      goto LABEL_31;
    CRdpRefCountString::CreateInstance(v12, &v26);
    v1 = v26;
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
          v17,
          (__int64)"\"CRdpRefCountString::CreateInstance()\"");
      }
      v3 = -2147024882;
      goto LABEL_55;
    }
    v15 = (void *)*((_QWORD *)v26 + 7);
    v16 = *((unsigned int *)v26 + 12);
    memset_0(v15, 0, 2 * v16);
    v3 = StringCchCopyW((unsigned __int16 *)v15, (unsigned int)v16, ValueName);
    if ( v3 < 0 )
      break;
    v3 = CRdpRefCountString::ShrinkToFit((const unsigned __int16 **)v1);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 104;
        v6 = "spCurrentString->ShrinkToFit() failed";
        goto LABEL_6;
      }
      goto LABEL_55;
    }
    if ( CVPtrList::AddTail(v10, v1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 4) + 8LL))(*((_QWORD *)v1 + 4));
LABEL_31:
    ++v9;
    memset_0(Data, 0, sizeof(Data));
    cbData = 2048;
    memset_0(ValueName, 0, sizeof(ValueName));
    cchValueName = 128;
    if ( v1 )
    {
      TCntPtr<CRdpClipMainWnd>::SafeRelease(&v26);
      v1 = 0;
      v26 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 103;
    v6 = "StringCchCopy() failed";
    goto LABEL_6;
  }
LABEL_55:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v26);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140035550  mov     [rsp-8+arg_8], rbx
0x140035555  mov     [rsp-8+arg_10], rsi
0x14003555a  push    rbp
0x14003555b  push    rdi
0x14003555c  push    r12
0x14003555e  push    r13
0x140035560  push    r14
0x140035562  lea     rbp, [rsp-880h]
0x14003556a  sub     rsp, 980h
0x140035571  mov     rax, cs:__security_cookie
0x140035578  xor     rax, rsp
0x14003557b  mov     [rbp+8A0h+var_30], rax
0x140035582  xor     esi, esi
0x140035584  mov     [rsp+9A0h+cchValueName], 80h
0x14003558c  mov     r13d, 800h
0x140035592  mov     [rsp+9A0h+hKey], rsi
0x140035597  lea     rdx, [rsp+9A0h+hKey]; HKEY *
0x14003559c  mov     [rsp+9A0h+var_950], rsi
0x1400355a1  mov     [rsp+9A0h+Type], esi
0x1400355a5  mov     r14d, esi
0x1400355a8  mov     [rsp+9A0h+cbData], r13d
0x1400355ad  mov     rdi, rcx
0x1400355b0  mov     [rsp+9A0h+var_948], rsi
0x1400355b5  call    ?OpenCurrentWinStationListenerKey@CRdpHintManager@@AEAAJPEAPEAUHKEY__@@@Z; CRdpHintManager::OpenCurrentWinStationListenerKey(HKEY__ * *)
0x1400355ba  mov     ebx, eax
0x1400355bc  test    eax, eax
0x1400355be  jns     short loc_140035623
0x1400355c0  mov     rax, cs:WPP_GLOBAL_Control
0x1400355c7  lea     rsi, WPP_GLOBAL_Control
0x1400355ce  cmp     rax, rsi
0x1400355d1  jz      loc_1400359FE
0x1400355d7  test    byte ptr [rax+1Ch], 8
0x1400355db  jz      loc_1400359FE
0x1400355e1  cmp     byte ptr [rax+19h], 2
0x1400355e5  jb      loc_1400359FE
0x1400355eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400355f0  lea     edx, [r14+61h]
0x1400355f4  lea     rcx, aOpencurrentwin; "OpenCurrentWinStationListenerKey() fail"...
0x1400355fb  mov     dword ptr [rsp+9A0h+lpType], ebx
0x1400355ff  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035606  mov     [rsp+9A0h+phkResult], rcx
0x14003560b  mov     r9d, eax
0x14003560e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035615  mov     rcx, [rcx+10h]
0x140035619  call    WPP_SF_DsD
0x14003561e  jmp     loc_1400359FE
0x140035623  mov     rcx, [rsp+9A0h+hKey]; hKey
0x140035628  lea     rax, [rsp+9A0h+var_950]
0x14003562d  mov     r9d, 20019h; samDesired
0x140035633  mov     [rsp+9A0h+phkResult], rax; phkResult
0x140035638  xor     r8d, r8d; ulOptions
0x14003563b  lea     rdx, aVideoremotingw; "VideoRemotingWindowNames"
0x140035642  call    cs:__imp_RegOpenKeyExW
0x140035648  test    eax, eax
0x14003564a  jz      short loc_1400356A1
0x14003564c  mov     rax, cs:WPP_GLOBAL_Control
0x140035653  lea     rsi, WPP_GLOBAL_Control
0x14003565a  cmp     rax, rsi
0x14003565d  jz      short loc_140035697
0x14003565f  test    byte ptr [rax+1Ch], 8
0x140035663  jz      short loc_140035697
0x140035665  cmp     byte ptr [rax+19h], 2
0x140035669  jb      short loc_140035697
0x14003566b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035670  mov     rcx, cs:WPP_GLOBAL_Control
0x140035677  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003567e  mov     edx, 62h ; 'b'
0x140035683  mov     dword ptr [rsp+9A0h+phkResult], 1
0x14003568b  mov     r9d, eax
0x14003568e  mov     rcx, [rcx+10h]
0x140035692  call    WPP_SF_Dd
0x140035697  mov     ebx, 1
0x14003569c  jmp     loc_1400359FE
0x1400356a1  cmp     [rsp+9A0h+var_950], rsi
0x1400356a6  jnz     short loc_1400356FD
0x1400356a8  mov     rax, cs:WPP_GLOBAL_Control
0x1400356af  lea     rsi, WPP_GLOBAL_Control
0x1400356b6  cmp     rax, rsi
0x1400356b9  jz      short loc_1400356F3
0x1400356bb  test    byte ptr [rax+1Ch], 8
0x1400356bf  jz      short loc_1400356F3
0x1400356c1  cmp     byte ptr [rax+19h], 2
0x1400356c5  jb      short loc_1400356F3
0x1400356c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400356cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400356d3  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400356da  mov     edx, 63h ; 'c'
0x1400356df  mov     dword ptr [rsp+9A0h+phkResult], 8000FFFFh
0x1400356e7  mov     r9d, eax
0x1400356ea  mov     rcx, [rcx+10h]
0x1400356ee  call    WPP_SF_Dd
0x1400356f3  mov     ebx, 8000FFFFh
0x1400356f8  jmp     loc_1400359FE
0x1400356fd  mov     r8, r13; Size
0x140035700  lea     rcx, [rbp+8A0h+Data]; void *
0x140035704  xor     edx, edx; Val
0x140035706  mov     r12d, esi
0x140035709  call    memset_0
0x14003570e  xor     edx, edx; Val
0x140035710  lea     rcx, [rsp+9A0h+ValueName]; void *
0x140035715  mov     r8d, 100h; Size
0x14003571b  call    memset_0
0x140035720  lea     r13, [rdi+88h]
0x140035727  mov     rcx, r13; this
0x14003572a  call    ?RemoveAll@?$CComPtrList@VCRdpRefCountString@@V?$ComPlainSmartPtr@VCRdpRefCountString@@@@@@QEAAXXZ; CComPtrList<CRdpRefCountString,ComPlainSmartPtr<CRdpRefCountString>>::RemoveAll(void)
0x14003572f  mov     rcx, [rsp+9A0h+var_950]; hKey
0x140035734  lea     rax, [rsp+9A0h+cbData]
0x140035739  mov     [rsp+9A0h+lpcbData], rax; lpcbData
0x14003573e  lea     r9, [rsp+9A0h+cchValueName]; lpcchValueName
0x140035743  lea     rax, [rbp+8A0h+Data]
0x140035747  xor     edx, edx; dwIndex
0x140035749  mov     [rsp+9A0h+lpData], rax; lpData
0x14003574e  lea     r8, [rsp+9A0h+ValueName]; lpValueName
0x140035753  lea     rax, [rsp+9A0h+Type]
0x140035758  mov     [rsp+9A0h+lpType], rax; lpType
0x14003575d  mov     [rsp+9A0h+phkResult], rsi; lpReserved
0x140035762  call    cs:__imp_RegEnumValueW
0x140035768  lea     rsi, WPP_GLOBAL_Control
0x14003576f  mov     edi, eax
0x140035771  test    eax, eax
0x140035773  jnz     loc_140035991
0x140035779  mov     rax, cs:WPP_GLOBAL_Control
0x140035780  cmp     rax, rsi
0x140035783  jz      short loc_1400357C0
0x140035785  test    dword ptr [rax+1Ch], 200h
0x14003578c  jz      short loc_1400357C0
0x14003578e  cmp     byte ptr [rax+19h], 5
0x140035792  jb      short loc_1400357C0
0x140035794  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035799  lea     rcx, [rsp+9A0h+ValueName]
0x14003579e  mov     r9d, eax
0x1400357a1  mov     [rsp+9A0h+phkResult], rcx
0x1400357a6  lea     edx, [rdi+64h]
0x1400357a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357b0  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400357b7  mov     rcx, [rcx+10h]
0x1400357bb  call    WPP_SF_DS
0x1400357c0  cmp     [rsp+9A0h+Type], 1
0x1400357c5  jnz     short loc_140035840
0x1400357c7  lea     rdx, [rsp+9A0h+var_948]; struct CRdpRefCountString **
0x1400357cc  call    ?CreateInstance@CRdpRefCountString@@SAJKPEAPEAV1@@Z; CRdpRefCountString::CreateInstance(ulong,CRdpRefCountString * *)
0x1400357d1  mov     r14, [rsp+9A0h+var_948]
0x1400357d6  test    r14, r14
0x1400357d9  jz      loc_140035942
0x1400357df  mov     rdi, [r14+38h]
0x1400357e3  mov     ebx, [r14+30h]
0x1400357e7  xor     edx, edx; Val
0x1400357e9  mov     rcx, rdi; void *
0x1400357ec  lea     r8, [rbx+rbx]; Size
0x1400357f0  call    memset_0
0x1400357f5  lea     r8, [rsp+9A0h+ValueName]; unsigned __int16 *
0x1400357fa  mov     edx, ebx; unsigned __int64
0x1400357fc  mov     rcx, rdi; unsigned __int16 *
0x1400357ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140035804  mov     ebx, eax
0x140035806  test    eax, eax
0x140035808  js      loc_140035908
0x14003580e  mov     rcx, r14; this
0x140035811  call    ?ShrinkToFit@CRdpRefCountString@@QEAAJXZ; CRdpRefCountString::ShrinkToFit(void)
0x140035816  mov     ebx, eax
0x140035818  test    eax, eax
0x14003581a  js      loc_1400358CE
0x140035820  mov     rdx, r14; void *
0x140035823  mov     rcx, r13; this
0x140035826  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x14003582b  test    rax, rax
0x14003582e  jz      short loc_140035840
0x140035830  mov     rcx, [r14+20h]
0x140035834  mov     rax, [rcx]
0x140035837  mov     rax, [rax+8]
0x14003583b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035840  mov     edi, 800h
0x140035845  lea     rcx, [rbp+8A0h+Data]; void *
0x140035849  mov     r8d, edi; Size
0x14003584c  xor     edx, edx; Val
0x14003584e  inc     r12d
0x140035851  call    memset_0
0x140035856  xor     edx, edx; Val
0x140035858  mov     [rsp+9A0h+cbData], edi
0x14003585c  mov     r8d, 100h; Size
0x140035862  lea     rcx, [rsp+9A0h+ValueName]; void *
0x140035867  call    memset_0
0x14003586c  mov     [rsp+9A0h+cchValueName], 80h
0x140035874  test    r14, r14
0x140035877  jz      short loc_14003588B
0x140035879  lea     rcx, [rsp+9A0h+var_948]
0x14003587e  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140035883  xor     r14d, r14d
0x140035886  mov     [rsp+9A0h+var_948], r14
0x14003588b  mov     rcx, [rsp+9A0h+var_950]; hKey
0x140035890  lea     rax, [rsp+9A0h+cbData]
0x140035895  mov     [rsp+9A0h+lpcbData], rax; lpcbData
0x14003589a  lea     r9, [rsp+9A0h+cchValueName]; lpcchValueName
0x14003589f  lea     rax, [rbp+8A0h+Data]
0x1400358a3  mov     edx, r12d; dwIndex
0x1400358a6  mov     [rsp+9A0h+lpData], rax; lpData
0x1400358ab  lea     r8, [rsp+9A0h+ValueName]; lpValueName
0x1400358b0  lea     rax, [rsp+9A0h+Type]
0x1400358b5  mov     [rsp+9A0h+lpType], rax; lpType
0x1400358ba  mov     [rsp+9A0h+phkResult], 0; lpReserved
0x1400358c3  call    cs:__imp_RegEnumValueW
0x1400358c9  jmp     loc_14003576F
0x1400358ce  mov     rax, cs:WPP_GLOBAL_Control
0x1400358d5  cmp     rax, rsi
0x1400358d8  jz      loc_1400359FE
0x1400358de  test    byte ptr [rax+1Ch], 8
0x1400358e2  jz      loc_1400359FE
0x1400358e8  cmp     byte ptr [rax+19h], 2
0x1400358ec  jb      loc_1400359FE
0x1400358f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400358f7  mov     edx, 68h ; 'h'
0x1400358fc  lea     rcx, aSpcurrentstrin; "spCurrentString->ShrinkToFit() failed"
0x140035903  jmp     loc_1400355FB
0x140035908  mov     rax, cs:WPP_GLOBAL_Control
0x14003590f  cmp     rax, rsi
0x140035912  jz      loc_1400359FE
0x140035918  test    byte ptr [rax+1Ch], 8
0x14003591c  jz      loc_1400359FE
0x140035922  cmp     byte ptr [rax+19h], 2
0x140035926  jb      loc_1400359FE
0x14003592c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035931  mov     edx, 67h ; 'g'
0x140035936  lea     rcx, aStringcchcopyF_0; "StringCchCopy() failed"
0x14003593d  jmp     loc_1400355FB
0x140035942  mov     rax, cs:WPP_GLOBAL_Control
0x140035949  cmp     rax, rsi
0x14003594c  jz      short loc_14003598A
0x14003594e  test    byte ptr [rax+1Ch], 8
0x140035952  jz      short loc_14003598A
0x140035954  cmp     byte ptr [rax+19h], 2
0x140035958  jb      short loc_14003598A
0x14003595a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003595f  lea     rcx, aCrdprefcountst; "\"CRdpRefCountString::CreateInstance()"...
0x140035966  mov     edx, 65h ; 'e'
0x14003596b  mov     [rsp+9A0h+phkResult], rcx
0x140035970  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035977  mov     rcx, cs:WPP_GLOBAL_Control
0x14003597e  mov     r9d, eax
0x140035981  mov     rcx, [rcx+10h]
0x140035985  call    WPP_SF_Ds
0x14003598a  mov     ebx, 8007000Eh
0x14003598f  jmp     short loc_1400359FE
0x140035991  cmp     edi, 103h
0x140035997  jz      short loc_1400359FE
0x140035999  mov     rax, cs:WPP_GLOBAL_Control
0x1400359a0  cmp     rax, rsi
0x1400359a3  jz      short loc_1400359F9
0x1400359a5  test    dword ptr [rax+1Ch], 200h
0x1400359ac  jz      short loc_1400359F9
0x1400359ae  cmp     byte ptr [rax+19h], 2
0x1400359b2  jb      short loc_1400359F9
0x1400359b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400359b9  lea     rdx, aUnknown; "[Unknown]"
0x1400359c0  mov     dword ptr [rsp+9A0h+lpType], edi
0x1400359c4  cmp     edi, 0EAh
0x1400359ca  lea     rcx, aErrorMoreData; "ERROR_MORE_DATA"
0x1400359d1  mov     r9d, eax
0x1400359d4  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400359db  cmovnz  rcx, rdx
0x1400359df  mov     edx, 69h ; 'i'
0x1400359e4  mov     [rsp+9A0h+phkResult], rcx
0x1400359e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400359f0  mov     rcx, [rcx+10h]
0x1400359f4  call    WPP_SF_DSD
0x1400359f9  mov     ebx, 80004005h
0x1400359fe  mov     rcx, [rsp+9A0h+var_950]; hKey
0x140035a03  test    rcx, rcx
0x140035a06  jz      short loc_140035A17
0x140035a08  call    cs:__imp_RegCloseKey
0x140035a0e  mov     [rsp+9A0h+var_950], 0
0x140035a17  cmp     [rsp+9A0h+hKey], 0
0x140035a1d  jz      short loc_140035A2A
0x140035a1f  mov     rcx, [rsp+9A0h+hKey]; hKey
0x140035a24  call    cs:__imp_RegCloseKey
0x140035a2a  lea     rcx, [rsp+9A0h+var_948]
0x140035a2f  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140035a34  mov     eax, ebx
0x140035a36  mov     rcx, [rbp+8A0h+var_30]
0x140035a3d  xor     rcx, rsp; StackCookie
0x140035a40  call    __security_check_cookie
0x140035a45  lea     r11, [rsp+9A0h+var_20]
0x140035a4d  mov     rbx, [r11+38h]
0x140035a51  mov     rsi, [r11+40h]
0x140035a55  mov     rsp, r11
0x140035a58  pop     r14
0x140035a5a  pop     r13
0x140035a5c  pop     r12
0x140035a5e  pop     rdi
0x140035a5f  pop     rbp
0x140035a60  retn
```
