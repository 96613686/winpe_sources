# EapHost::ECPDeviceManager::CheckECPComponentDevice(ATL::CComPtr<IUMBusPDO> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x180011698`
- end: `0x180011ca7`
- name: `?CheckECPComponentDevice@ECPDeviceManager@EapHost@@CA_NAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1551`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180012cf8`

## callees

- `0x180001f60`
- `0x18000ab70`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c40c`
- `0x18000c7b8`
- `0x18000d610`
- `0x180010f00`
- `0x180010fac`
- `0x180011698`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180011714`
- `ntdll!EtwEventEnabled` at `0x1800117ce`
- `ntdll!EtwEventEnabled` at `0x180011899`
- `ntdll!EtwEventEnabled` at `0x180011975`
- `ntdll!EtwEventEnabled` at `0x180011af9`
- `ntdll!EtwEventEnabled` at `0x180011714`
- `ntdll!EtwEventEnabled` at `0x1800117ce`
- `ntdll!EtwEventEnabled` at `0x180011899`
- `ntdll!EtwEventEnabled` at `0x180011975`
- `ntdll!EtwEventEnabled` at `0x180011af9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011959`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011959`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011bb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011bb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c73`

## string_xrefs

- `0x180011721`: `Cannot get hardware ids while checking the component device, 0x%x`

## pseudocode

```c
char __fastcall EapHost::ECPDeviceManager::CheckECPComponentDevice(_QWORD *a1, __int64 a2)
{
  char v3; // r14
  unsigned int v4; // esi
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rbx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rbx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rbx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rbx
  const wchar_t *v20; // rdx
  __int64 v21; // rbx
  unsigned __int64 v22; // r8
  LPCVOID *v23; // rdx
  const wchar_t *v24; // rcx
  char v25; // si
  int v26; // r8d
  int v27; // r9d
  LPCVOID *v29; // rdx
  unsigned __int64 v30; // rcx
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t **v32; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+48h] [rbp-B8h]
  LPCVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h]
  LPCVOID v36[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-70h] BYREF
  size_t N[2]; // [rsp+A0h] [rbp-60h]
  char v40[2048]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = 0;
  v33 = 0;
  *(_OWORD *)pvar = 0;
  v32 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)*a1 + 40LL))(
         *a1,
         &PKEY_Device_HardwareIds,
         pvar);
  if ( v4 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v40, 0x800u, "Cannot get hardware ids while checking the component device, 0x%x", v4) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v40[v7] );
      N[0] = (size_t)v40;
      N[1] = (unsigned int)(v7 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v5,
        v6,
        (__int64)S1);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v9 = 38;
    v10 = v4;
LABEL_31:
    WPP_SF_d(v8[2], v9, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v10);
LABEL_66:
    PropVariantClear(pvar);
    return 0;
  }
  if ( LOWORD(pvar[0]) != 4127 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v40, 0x800u, "The hardware ids are of wrong type 0x%x", LOWORD(pvar[0])) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v40[v13] );
      N[0] = (size_t)v40;
      N[1] = (unsigned int)(v13 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v11,
        v12,
        (__int64)S1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids,
        LOWORD(pvar[0]));
    goto LABEL_66;
  }
  if ( LODWORD(pvar[1]) != 2 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v40, 0x800u, "Wrong number of hardware ids: %d", LODWORD(pvar[1])) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v40[v16] );
      N[0] = (size_t)v40;
      N[1] = (unsigned int)(v16 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v14,
        v15,
        (__int64)S1);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v9 = 40;
    v10 = LODWORD(pvar[1]);
    goto LABEL_31;
  }
  if ( lstrcmpW(v32[1], L"EH\\0") )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v40, 0x800u, "the device does not have correct generic hardware id: %S", v32[1]) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v40[v19] );
      N[0] = (size_t)v40;
      N[1] = (unsigned int)(v19 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v17,
        v18,
        (__int64)S1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, v32[1]);
    goto LABEL_66;
  }
  v20 = *v32;
  *(_OWORD *)lpMem = 0;
  v35 = 0;
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( v20[v22] );
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
    lpMem,
    v20,
    v22);
  if ( (unsigned __int64)v35 <= 3 )
    goto LABEL_51;
  *(_OWORD *)S1 = 0;
  *(_OWORD *)N = 0;
  v23 = lpMem;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    v23 = (LPCVOID *)lpMem[0];
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(S1, v23, 3u);
  v3 = 3;
  v24 = (const wchar_t *)S1;
  if ( N[1] > 7 )
    v24 = S1[0];
  if ( N[0] != 3 || (v25 = 0, wmemcmp(v24, L"EH\\", 3u)) )
LABEL_51:
    v25 = 1;
  if ( (v3 & 1) != 0 && N[1] > 7 )
    operator delete(S1[0]);
  if ( v25 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v40,
                0x800u,
                "The device unique hardware id does not start with  c_ecpHardwareIdPrefix: %S",
                *v32) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      do
        ++v21;
      while ( v40[v21] );
      N[0] = (size_t)v40;
      N[1] = (unsigned int)(v21 + 1);
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v26,
        v27,
        (__int64)S1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids, *v32);
    if ( *((_QWORD *)&v35 + 1) > 7u )
      operator delete((void *)lpMem[0]);
    goto LABEL_66;
  }
  *(_OWORD *)v36 = 0;
  v37 = 0;
  if ( (unsigned __int64)v35 < 3 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  v29 = lpMem;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    v29 = (LPCVOID *)lpMem[0];
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
    v36,
    (char *)v29 + 6,
    v35 - 3);
  if ( (LPCVOID *)a2 == v36 )
  {
    v30 = *((_QWORD *)&v37 + 1);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 24) > 7u )
      operator delete(*(void **)a2);
    *(_OWORD *)a2 = *(_OWORD *)v36;
    *(_OWORD *)(a2 + 16) = v37;
    v30 = 7;
    LOWORD(v36[0]) = 0;
  }
  if ( v30 > 7 )
    operator delete((void *)v36[0]);
  if ( *((_QWORD *)&v35 + 1) > 7u )
    operator delete((void *)lpMem[0]);
  PropVariantClear(pvar);
  return 1;
}

```

## disassembly

```asm
0x180011698  mov     [rsp-8+arg_10], rbx
0x18001169d  push    rbp
0x18001169e  push    rsi
0x18001169f  push    rdi
0x1800116a0  push    r14
0x1800116a2  push    r15
0x1800116a4  lea     rbp, [rsp-7C0h]
0x1800116ac  sub     rsp, 8C0h
0x1800116b3  mov     rax, cs:__security_cookie
0x1800116ba  xor     rax, rsp
0x1800116bd  mov     [rbp+7E0h+var_30], rax
0x1800116c4  mov     rdi, rdx
0x1800116c7  xor     r15d, r15d
0x1800116ca  mov     r14d, r15d
0x1800116cd  mov     [rsp+8E0h+var_898], r15d
0x1800116d2  xorps   xmm0, xmm0
0x1800116d5  xor     eax, eax
0x1800116d7  movups  xmmword ptr [rsp+8E0h+pvar], xmm0
0x1800116dc  mov     [rsp+8E0h+var_8A0], rax
0x1800116e1  mov     rcx, [rcx]
0x1800116e4  mov     rax, [rcx]
0x1800116e7  lea     r8, [rsp+8E0h+pvar]
0x1800116ec  lea     rdx, PKEY_Device_HardwareIds
0x1800116f3  mov     rax, [rax+28h]
0x1800116f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116fc  mov     esi, eax
0x1800116fe  test    eax, eax
0x180011700  jz      loc_1800117B0
0x180011706  lea     rdx, DebugErrorEvent
0x18001170d  mov     rcx, cs:eaphost_Context
0x180011714  call    cs:__imp_EtwEventEnabled
0x18001171a  test    al, al
0x18001171c  jz      short loc_180011782
0x18001171e  mov     r9d, esi
0x180011721  lea     r8, aCannotGetHardw; "Cannot get hardware ids while checking "...
0x180011728  mov     edx, 800h; unsigned __int64
0x18001172d  lea     rcx, [rbp+7E0h+var_830]; char *
0x180011731  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011736  test    eax, eax
0x180011738  js      short loc_180011782
0x18001173a  test    cs:byte_180020AC1, 8
0x180011741  jz      short loc_180011782
0x180011743  lea     rax, [rbp+7E0h+var_830]
0x180011747  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001174b  inc     rbx
0x18001174e  cmp     [rax+rbx], r15b
0x180011752  jnz     short loc_18001174B
0x180011754  lea     eax, [rbx+1]
0x180011757  lea     rcx, [rbp+7E0h+var_830]
0x18001175b  mov     [rbp+7E0h+N], rcx
0x18001175f  mov     dword ptr [rbp+7E0h+N+8], eax
0x180011762  mov     dword ptr [rbp+7E0h+N+0Ch], r15d
0x180011766  lea     rax, [rbp+7E0h+S1]
0x18001176a  mov     [rsp+8E0h+var_8C0], rax
0x18001176f  lea     rdx, DebugErrorEvent
0x180011776  lea     rcx, eaphost_Context
0x18001177d  call    McGenEventWrite_EtwEventWriteTransfer
0x180011782  lea     rax, WPP_GLOBAL_Control
0x180011789  mov     rcx, cs:WPP_GLOBAL_Control
0x180011790  cmp     rcx, rax
0x180011793  jz      loc_180011BB2
0x180011799  test    byte ptr [rcx+1Ch], 1
0x18001179d  jz      loc_180011BB2
0x1800117a3  mov     edx, 26h ; '&'
0x1800117a8  mov     r9d, esi
0x1800117ab  jmp     loc_180011934
0x1800117b0  mov     eax, 101Fh
0x1800117b5  cmp     word ptr [rsp+8E0h+pvar], ax
0x1800117ba  jz      loc_180011880
0x1800117c0  lea     rdx, DebugErrorEvent
0x1800117c7  mov     rcx, cs:eaphost_Context
0x1800117ce  call    cs:__imp_EtwEventEnabled
0x1800117d4  test    al, al
0x1800117d6  jz      short loc_18001183F
0x1800117d8  movzx   r9d, word ptr [rsp+8E0h+pvar]
0x1800117de  lea     r8, aTheHardwareIds; "The hardware ids are of wrong type 0x%x"
0x1800117e5  mov     edx, 800h; unsigned __int64
0x1800117ea  lea     rcx, [rbp+7E0h+var_830]; char *
0x1800117ee  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800117f3  test    eax, eax
0x1800117f5  js      short loc_18001183F
0x1800117f7  test    cs:byte_180020AC1, 8
0x1800117fe  jz      short loc_18001183F
0x180011800  lea     rax, [rbp+7E0h+var_830]
0x180011804  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011808  inc     rbx
0x18001180b  cmp     [rax+rbx], r15b
0x18001180f  jnz     short loc_180011808
0x180011811  lea     eax, [rbx+1]
0x180011814  lea     rcx, [rbp+7E0h+var_830]
0x180011818  mov     [rbp+7E0h+N], rcx
0x18001181c  mov     dword ptr [rbp+7E0h+N+8], eax
0x18001181f  mov     dword ptr [rbp+7E0h+N+0Ch], r15d
0x180011823  lea     rax, [rbp+7E0h+S1]
0x180011827  mov     [rsp+8E0h+var_8C0], rax
0x18001182c  lea     rdx, DebugErrorEvent
0x180011833  lea     rcx, eaphost_Context
0x18001183a  call    McGenEventWrite_EtwEventWriteTransfer
0x18001183f  lea     rax, WPP_GLOBAL_Control
0x180011846  mov     rcx, cs:WPP_GLOBAL_Control
0x18001184d  cmp     rcx, rax
0x180011850  jz      loc_180011BB2
0x180011856  test    byte ptr [rcx+1Ch], 1
0x18001185a  jz      loc_180011BB2
0x180011860  movzx   r9d, word ptr [rsp+8E0h+pvar]
0x180011866  mov     edx, 27h ; '''
0x18001186b  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180011872  mov     rcx, [rcx+10h]
0x180011876  call    WPP_SF_d
0x18001187b  jmp     loc_180011BB2
0x180011880  cmp     dword ptr [rsp+8E0h+pvar+8], 2
0x180011885  jz      loc_180011949
0x18001188b  lea     rdx, DebugErrorEvent
0x180011892  mov     rcx, cs:eaphost_Context
0x180011899  call    cs:__imp_EtwEventEnabled
0x18001189f  test    al, al
0x1800118a1  jz      short loc_180011909
0x1800118a3  mov     r9d, dword ptr [rsp+8E0h+pvar+8]
0x1800118a8  lea     r8, aWrongNumberOfH; "Wrong number of hardware ids: %d"
0x1800118af  mov     edx, 800h; unsigned __int64
0x1800118b4  lea     rcx, [rbp+7E0h+var_830]; char *
0x1800118b8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800118bd  test    eax, eax
0x1800118bf  js      short loc_180011909
0x1800118c1  test    cs:byte_180020AC1, 8
0x1800118c8  jz      short loc_180011909
0x1800118ca  lea     rax, [rbp+7E0h+var_830]
0x1800118ce  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800118d2  inc     rbx
0x1800118d5  cmp     [rax+rbx], r15b
0x1800118d9  jnz     short loc_1800118D2
0x1800118db  lea     eax, [rbx+1]
0x1800118de  lea     rcx, [rbp+7E0h+var_830]
0x1800118e2  mov     [rbp+7E0h+N], rcx
0x1800118e6  mov     dword ptr [rbp+7E0h+N+8], eax
0x1800118e9  mov     dword ptr [rbp+7E0h+N+0Ch], r15d
0x1800118ed  lea     rax, [rbp+7E0h+S1]
0x1800118f1  mov     [rsp+8E0h+var_8C0], rax
0x1800118f6  lea     rdx, DebugErrorEvent
0x1800118fd  lea     rcx, eaphost_Context
0x180011904  call    McGenEventWrite_EtwEventWriteTransfer
0x180011909  lea     rax, WPP_GLOBAL_Control
0x180011910  mov     rcx, cs:WPP_GLOBAL_Control
0x180011917  cmp     rcx, rax
0x18001191a  jz      loc_180011BB2
0x180011920  test    byte ptr [rcx+1Ch], 1
0x180011924  jz      loc_180011BB2
0x18001192a  mov     edx, 28h ; '('
0x18001192f  mov     r9d, dword ptr [rsp+8E0h+pvar+8]
0x180011934  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x18001193b  mov     rcx, [rcx+10h]
0x18001193f  call    WPP_SF_d
0x180011944  jmp     loc_180011BB2
0x180011949  lea     rdx, String2; "EH\\0"
0x180011950  mov     rcx, [rsp+8E0h+var_8A0]
0x180011955  mov     rcx, [rcx+8]; lpString1
0x180011959  call    cs:__imp_lstrcmpW
0x18001195f  test    eax, eax
0x180011961  jz      loc_180011A2D
0x180011967  lea     rdx, DebugErrorEvent
0x18001196e  mov     rcx, cs:eaphost_Context
0x180011975  call    cs:__imp_EtwEventEnabled
0x18001197b  test    al, al
0x18001197d  jz      short loc_1800119E9
0x18001197f  mov     r9, [rsp+8E0h+var_8A0]
0x180011984  mov     r9, [r9+8]
0x180011988  lea     r8, aTheDeviceDoesN; "the device does not have correct generi"...
0x18001198f  mov     edx, 800h; unsigned __int64
0x180011994  lea     rcx, [rbp+7E0h+var_830]; char *
0x180011998  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001199d  test    eax, eax
0x18001199f  js      short loc_1800119E9
0x1800119a1  test    cs:byte_180020AC1, 8
0x1800119a8  jz      short loc_1800119E9
0x1800119aa  lea     rax, [rbp+7E0h+var_830]
0x1800119ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800119b2  inc     rbx
0x1800119b5  cmp     [rax+rbx], r15b
0x1800119b9  jnz     short loc_1800119B2
0x1800119bb  lea     eax, [rbx+1]
0x1800119be  lea     rcx, [rbp+7E0h+var_830]
0x1800119c2  mov     [rbp+7E0h+N], rcx
0x1800119c6  mov     dword ptr [rbp+7E0h+N+8], eax
0x1800119c9  mov     dword ptr [rbp+7E0h+N+0Ch], r15d
0x1800119cd  lea     rax, [rbp+7E0h+S1]
0x1800119d1  mov     [rsp+8E0h+var_8C0], rax
0x1800119d6  lea     rdx, DebugErrorEvent
0x1800119dd  lea     rcx, eaphost_Context
0x1800119e4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800119e9  lea     rax, WPP_GLOBAL_Control
0x1800119f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119f7  cmp     rcx, rax
0x1800119fa  jz      loc_180011BB2
0x180011a00  test    byte ptr [rcx+1Ch], 1
0x180011a04  jz      loc_180011BB2
0x180011a0a  mov     edx, 29h ; ')'
0x180011a0f  mov     r9, [rsp+8E0h+var_8A0]
0x180011a14  mov     r9, [r9+8]
0x180011a18  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180011a1f  mov     rcx, [rcx+10h]
0x180011a23  call    WPP_SF_S
0x180011a28  jmp     loc_180011BB2
0x180011a2d  mov     rax, [rsp+8E0h+var_8A0]
0x180011a32  mov     rdx, [rax]
0x180011a35  xorps   xmm0, xmm0
0x180011a38  movups  xmmword ptr [rsp+8E0h+lpMem], xmm0
0x180011a3d  xorps   xmm1, xmm1
0x180011a40  movdqu  [rsp+8E0h+var_880], xmm1
0x180011a46  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011a4a  mov     r8, rbx
0x180011a4d  inc     r8
0x180011a50  cmp     [rdx+r8*2], r15w
0x180011a55  jnz     short loc_180011A4D
0x180011a57  lea     rcx, [rsp+8E0h+lpMem]
0x180011a5c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180011a61  nop
0x180011a62  cmp     qword ptr [rsp+8E0h+var_880], 3
0x180011a68  jbe     short loc_180011AC9
0x180011a6a  xorps   xmm0, xmm0
0x180011a6d  movups  xmmword ptr [rbp+7E0h+S1], xmm0
0x180011a71  xorps   xmm1, xmm1
0x180011a74  movdqu  xmmword ptr [rbp+7E0h+N], xmm1
0x180011a79  lea     rdx, [rsp+8E0h+lpMem]
0x180011a7e  cmp     qword ptr [rsp+8E0h+var_880+8], 7
0x180011a84  cmova   rdx, [rsp+8E0h+lpMem]
0x180011a8a  mov     r8d, 3
0x180011a90  lea     rcx, [rbp+7E0h+S1]
0x180011a94  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180011a99  mov     r14d, 3
0x180011a9f  mov     r8, [rbp+7E0h+N]; N
0x180011aa3  lea     rcx, [rbp+7E0h+S1]
0x180011aa7  cmp     [rbp+7E0h+N+8], 7
0x180011aac  cmova   rcx, [rbp+7E0h+S1]; S1
0x180011ab1  cmp     r8, r14
0x180011ab4  jnz     short loc_180011AC9
0x180011ab6  lea     rdx, aEh; "EH\\"
0x180011abd  call    wmemcmp
0x180011ac2  test    eax, eax
0x180011ac4  mov     sil, r15b
0x180011ac7  jz      short loc_180011ACC
0x180011ac9  mov     sil, 1
0x180011acc  test    r14b, 1
0x180011ad0  jz      short loc_180011AE2
0x180011ad2  cmp     [rbp+7E0h+N+8], 7
0x180011ad7  jbe     short loc_180011AE2
0x180011ad9  mov     rcx, [rbp+7E0h+S1]; lpMem
0x180011add  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011ae2  test    sil, sil
0x180011ae5  jz      loc_180011BC4
0x180011aeb  lea     rdx, DebugErrorEvent
0x180011af2  mov     rcx, cs:eaphost_Context
0x180011af9  call    cs:__imp_EtwEventEnabled
0x180011aff  test    al, al
0x180011b01  jz      short loc_180011B68
0x180011b03  mov     r9, [rsp+8E0h+var_8A0]
0x180011b08  mov     r9, [r9]
0x180011b0b  lea     r8, aTheDeviceUniqu; "The device unique hardware id does not "...
0x180011b12  mov     edx, 800h; unsigned __int64
0x180011b17  lea     rcx, [rbp+7E0h+var_830]; char *
0x180011b1b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011b20  test    eax, eax
0x180011b22  js      short loc_180011B68
0x180011b24  test    cs:byte_180020AC1, 8
0x180011b2b  jz      short loc_180011B68
0x180011b2d  lea     rax, [rbp+7E0h+var_830]
0x180011b31  inc     rbx
0x180011b34  cmp     [rax+rbx], r15b
0x180011b38  jnz     short loc_180011B31
0x180011b3a  lea     eax, [rbx+1]
0x180011b3d  lea     rcx, [rbp+7E0h+var_830]
0x180011b41  mov     [rbp+7E0h+N], rcx
0x180011b45  mov     dword ptr [rbp+7E0h+N+8], eax
0x180011b48  mov     dword ptr [rbp+7E0h+N+0Ch], r15d
0x180011b4c  lea     rax, [rbp+7E0h+S1]
0x180011b50  mov     [rsp+8E0h+var_8C0], rax
0x180011b55  lea     rdx, DebugErrorEvent
0x180011b5c  lea     rcx, eaphost_Context
0x180011b63  call    McGenEventWrite_EtwEventWriteTransfer
0x180011b68  lea     rax, WPP_GLOBAL_Control
0x180011b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b76  cmp     rcx, rax
0x180011b79  jz      short loc_180011B9F
0x180011b7b  test    byte ptr [rcx+1Ch], 1
0x180011b7f  jz      short loc_180011B9F
0x180011b81  mov     edx, 2Ah ; '*'
0x180011b86  mov     r9, [rsp+8E0h+var_8A0]
0x180011b8b  mov     r9, [r9]
0x180011b8e  lea     r8, WPP_599162b70b3f322fdcf3f4c38ef6a4fe_Traceguids
0x180011b95  mov     rcx, [rcx+10h]
0x180011b99  call    WPP_SF_S
0x180011b9e  nop
0x180011b9f  cmp     qword ptr [rsp+8E0h+var_880+8], 7
0x180011ba5  jbe     short loc_180011BB2
0x180011ba7  mov     rcx, [rsp+8E0h+lpMem]; lpMem
0x180011bac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011bb1  nop
0x180011bb2  lea     rcx, [rsp+8E0h+pvar]; pvar
0x180011bb7  call    cs:__imp_PropVariantClear
0x180011bbd  xor     al, al
0x180011bbf  jmp     loc_180011C7B
  ... truncated ...
```
