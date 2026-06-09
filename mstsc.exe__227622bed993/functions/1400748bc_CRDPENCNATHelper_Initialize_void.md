# CRDPENCNATHelper::Initialize(void)

- ea: `0x1400748bc`
- end: `0x140074ceb`
- name: `?Initialize@CRDPENCNATHelper@@QEAAJXZ`
- size: `1071`
- prototype: `__int64 __fastcall(CRDPENCNATHelper *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006a890`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x140003b08`
- `0x140003b2c`
- `0x140004388`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x1400748bc`
- `0x140074df4`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400748f4`
- `KERNEL32!GetModuleFileNameW` at `0x1400748f4`
- `KERNEL32!GetCurrentProcessId` at `0x140074a10`
- `KERNEL32!GetCurrentProcessId` at `0x140074a10`
- `KERNEL32!GetLastError` at `0x140074901`
- `KERNEL32!GetLastError` at `0x140074901`
- `ole32!CoCreateInstance` at `0x140074b5a`
- `ole32!CoCreateInstance` at `0x140074b5a`
- `OLEAUT32!__imp_SysAllocString` at `0x140074a9c`
- `OLEAUT32!__imp_SysAllocString` at `0x140074b07`
- `OLEAUT32!__imp_SysAllocString` at `0x140074a9c`
- `OLEAUT32!__imp_SysAllocString` at `0x140074b07`

## string_xrefs

- `0x140074a65`: `Failed to create the map string`
- `0x140074bab`: `Failed to create the UPnPNAT object (0x%08x)`

## pseudocode

```c
__int64 __fastcall CRDPENCNATHelper::Initialize(CRDPENCNATHelper *this)
{
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  wchar_t *v4; // rax
  WCHAR *v5; // rbx
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  BSTR v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  BSTR v14; // rax
  HRESULT Instance; // eax
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  DWORD ppv; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  HRESULT v26; // [rsp+58h] [rbp-A8h] BYREF
  const char *v27; // [rsp+60h] [rbp-A0h] BYREF
  const char *v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !GetModuleFileNameW(0, Filename, 0x105u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_50;
  }
  v4 = wcsrchr_0(Filename, 0x5Cu);
  if ( v4 )
    v5 = v4 + 1;
  else
    v5 = Filename;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = v6 + 47;
  v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 47, 2u));
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        v9,
        -2147024882);
    }
    LastError = -2147024882;
    goto LABEL_50;
  }
  ppv = GetCurrentProcessId();
  LastError = StringCchPrintfW(v8, v7, L"%s(%d)#RDPENC", v5, ppv);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        v10,
        (__int64)"Failed to create the map string",
        LastError);
    }
    goto LABEL_49;
  }
  v11 = SysAllocString(v8);
  *((_QWORD *)this + 6) = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 13;
LABEL_32:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
      v12,
      -2147024882);
LABEL_33:
    LastError = -2147024882;
    goto LABEL_49;
  }
  v14 = SysAllocString(L"TCP");
  *((_QWORD *)this + 7) = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 14;
    goto LABEL_32;
  }
  Instance = CoCreateInstance(&CLSID_UPnPNAT, 0, 1u, &GUID_b171c812_cc76_485a_94d8_b6b3a2794e99, (LPVOID *)this);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v26 = Instance;
      v24 = 79;
      v27 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
      v25 = -2147467259;
      v29[0] = "Failed to create the UPnPNAT object (0x%08x)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140150118,
        (unsigned int)&dword_14013EFE4,
        v16,
        v17,
        (__int64)v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v26);
    }
    LastError = 1;
    goto LABEL_49;
  }
  v18 = (_QWORD *)((char *)this + 8);
  LastError = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, (char *)this + 8);
  if ( LastError >= 0 )
    goto LABEL_46;
  LastError = 1;
  if ( *v18 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 8);
    *v18 = 0;
LABEL_46:
    if ( *v18 )
      goto LABEL_49;
  }
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v25 = 93;
    v29[0] = "Initialize";
    v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
    v24 = -2147467259;
    v27 = "Null port map collection. NAT device unavailable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)&byte_14013EF9F,
      v20,
      v21,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)v29);
  }
LABEL_49:
  operator delete(v8);
  if ( LastError < 0 )
LABEL_50:
    CRDPENCNATHelper::Terminate(this);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400748bc  push    rbp
0x1400748be  push    rbx
0x1400748bf  push    rsi
0x1400748c0  push    rdi
0x1400748c1  push    r14
0x1400748c3  push    r15
0x1400748c5  lea     rbp, [rsp-1A8h]
0x1400748cd  sub     rsp, 2A8h
0x1400748d4  mov     rax, cs:__security_cookie
0x1400748db  xor     rax, rsp
0x1400748de  mov     [rbp+1D0h+var_40], rax
0x1400748e5  mov     rsi, rcx
0x1400748e8  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x1400748ec  xor     ecx, ecx; hModule
0x1400748ee  mov     r8d, 105h; nSize
0x1400748f4  call    cs:__imp_GetModuleFileNameW
0x1400748fa  xor     r15d, r15d
0x1400748fd  test    eax, eax
0x1400748ff  jnz     short loc_14007496B
0x140074901  call    cs:__imp_GetLastError
0x140074907  mov     ebx, eax
0x140074909  mov     rcx, cs:WPP_GLOBAL_Control
0x140074910  lea     rax, WPP_GLOBAL_Control
0x140074917  cmp     rcx, rax
0x14007491a  jz      short loc_14007494F
0x14007491c  test    byte ptr [rcx+1Ch], 8
0x140074920  jz      short loc_14007494F
0x140074922  cmp     byte ptr [rcx+19h], 2
0x140074926  jb      short loc_14007494F
0x140074928  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007492d  mov     rcx, cs:WPP_GLOBAL_Control
0x140074934  lea     edx, [r15+0Ah]
0x140074938  mov     r9d, eax
0x14007493b  mov     dword ptr [rsp+2D0h+ppv], ebx
0x14007493f  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140074946  mov     rcx, [rcx+10h]
0x14007494a  call    WPP_SF_Dd
0x14007494f  test    ebx, ebx
0x140074951  jle     short loc_14007495C
0x140074953  movzx   ebx, bx
0x140074956  or      ebx, 80070000h
0x14007495c  test    ebx, ebx
0x14007495e  mov     eax, 80004005h
0x140074963  cmovns  ebx, eax
0x140074966  jmp     loc_140074CC2
0x14007496b  mov     edx, 5Ch ; '\'; Ch
0x140074970  lea     rcx, [rbp+1D0h+Filename]; Str
0x140074974  call    wcsrchr_0
0x140074979  mov     rbx, rax
0x14007497c  test    rax, rax
0x14007497f  jnz     short loc_140074987
0x140074981  lea     rbx, [rbp+1D0h+Filename]
0x140074985  jmp     short loc_14007498B
0x140074987  add     rbx, 2
0x14007498b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007498f  mov     rax, rcx
0x140074992  inc     rax
0x140074995  cmp     [rbx+rax*2], r15w
0x14007499a  jnz     short loc_140074992
0x14007499c  lea     rdi, [rax+2Fh]
0x1400749a0  mov     eax, 2
0x1400749a5  mul     rdi
0x1400749a8  cmovb   rax, rcx
0x1400749ac  mov     rcx, rax; Size
0x1400749af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400749b4  mov     r14, rax
0x1400749b7  test    rax, rax
0x1400749ba  jnz     short loc_140074A10
0x1400749bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400749c3  lea     rax, WPP_GLOBAL_Control
0x1400749ca  cmp     rcx, rax
0x1400749cd  jz      short loc_140074A06
0x1400749cf  test    byte ptr [rcx+1Ch], 8
0x1400749d3  jz      short loc_140074A06
0x1400749d5  cmp     byte ptr [rcx+19h], 2
0x1400749d9  jb      short loc_140074A06
0x1400749db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400749e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400749e7  lea     edx, [r14+0Bh]
0x1400749eb  mov     r9d, eax
0x1400749ee  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x1400749f6  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x1400749fd  mov     rcx, [rcx+10h]
0x140074a01  call    WPP_SF_Dd
0x140074a06  mov     ebx, 8007000Eh
0x140074a0b  jmp     loc_140074CC2
0x140074a10  call    cs:__imp_GetCurrentProcessId
0x140074a16  mov     r9, rbx
0x140074a19  lea     r8, aSDRdpenc; "%s(%d)#RDPENC"
0x140074a20  mov     rdx, rdi; unsigned __int64
0x140074a23  mov     dword ptr [rsp+2D0h+ppv], eax
0x140074a27  mov     rcx, r14; unsigned __int16 *
0x140074a2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140074a2f  mov     ebx, eax
0x140074a31  test    eax, eax
0x140074a33  jns     short loc_140074A99
0x140074a35  mov     rcx, cs:WPP_GLOBAL_Control
0x140074a3c  lea     rax, WPP_GLOBAL_Control
0x140074a43  cmp     rcx, rax
0x140074a46  jz      loc_140074CB6
0x140074a4c  test    byte ptr [rcx+1Ch], 8
0x140074a50  jz      loc_140074CB6
0x140074a56  cmp     byte ptr [rcx+19h], 2
0x140074a5a  jb      loc_140074CB6
0x140074a60  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140074a65  lea     rcx, aFailedToCreate_62; "Failed to create the map string"
0x140074a6c  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x140074a70  mov     [rsp+2D0h+ppv], rcx
0x140074a75  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140074a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140074a83  mov     edx, 0Ch
0x140074a88  mov     r9d, eax
0x140074a8b  mov     rcx, [rcx+10h]
0x140074a8f  call    WPP_SF_DsD
0x140074a94  jmp     loc_140074CB6
0x140074a99  mov     rcx, r14; psz
0x140074a9c  call    cs:__imp_SysAllocString
0x140074aa2  mov     [rsi+30h], rax
0x140074aa6  test    rax, rax
0x140074aa9  jnz     short loc_140074B00
0x140074aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140074ab2  lea     rax, WPP_GLOBAL_Control
0x140074ab9  cmp     rcx, rax
0x140074abc  jz      short loc_140074AF6
0x140074abe  test    byte ptr [rcx+1Ch], 8
0x140074ac2  jz      short loc_140074AF6
0x140074ac4  cmp     byte ptr [rcx+19h], 2
0x140074ac8  jb      short loc_140074AF6
0x140074aca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140074acf  mov     edx, 0Dh
0x140074ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140074adb  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140074ae2  mov     r9d, eax
0x140074ae5  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x140074aed  mov     rcx, [rcx+10h]
0x140074af1  call    WPP_SF_Dd
0x140074af6  mov     ebx, 8007000Eh
0x140074afb  jmp     loc_140074CB6
0x140074b00  lea     rcx, aTcp; "TCP"
0x140074b07  call    cs:__imp_SysAllocString
0x140074b0d  mov     [rsi+38h], rax
0x140074b11  test    rax, rax
0x140074b14  jnz     short loc_140074B41
0x140074b16  mov     rcx, cs:WPP_GLOBAL_Control
0x140074b1d  lea     rax, WPP_GLOBAL_Control
0x140074b24  cmp     rcx, rax
0x140074b27  jz      short loc_140074AF6
0x140074b29  test    byte ptr [rcx+1Ch], 8
0x140074b2d  jz      short loc_140074AF6
0x140074b2f  cmp     byte ptr [rcx+19h], 2
0x140074b33  jb      short loc_140074AF6
0x140074b35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140074b3a  mov     edx, 0Eh
0x140074b3f  jmp     short loc_140074AD4
0x140074b41  xor     edx, edx; pUnkOuter
0x140074b43  mov     [rsp+2D0h+ppv], rsi; ppv
0x140074b48  lea     r9, _GUID_b171c812_cc76_485a_94d8_b6b3a2794e99; riid
0x140074b4f  lea     rcx, CLSID_UPnPNAT; rclsid
0x140074b56  lea     r8d, [rdx+1]; dwClsContext
0x140074b5a  call    cs:__imp_CoCreateInstance
0x140074b60  test    eax, eax
0x140074b62  jns     loc_140074C02
0x140074b68  mov     ecx, cs:dword_140150118
0x140074b6e  cmp     ecx, 2
0x140074b71  jbe     loc_140074BF8
0x140074b77  mov     [rsp+2D0h+var_278], eax
0x140074b7b  lea     rdx, dword_14013EFE4
0x140074b82  lea     rax, aInitialize; "Initialize"
0x140074b89  mov     [rsp+2D0h+var_280], 4Fh ; 'O'
0x140074b91  mov     [rsp+2D0h+var_270], rax
0x140074b96  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140074b9d  mov     [rsp+2D0h+var_268], rax
0x140074ba2  mov     eax, 80004005h
0x140074ba7  mov     [rsp+2D0h+var_27C], eax
0x140074bab  lea     rax, aFailedToCreate_37; "Failed to create the UPnPNAT object (0x"...
0x140074bb2  mov     [rsp+2D0h+var_260], rax
0x140074bb7  lea     rax, [rsp+2D0h+var_278]
0x140074bbc  mov     [rsp+2D0h+var_288], rax
0x140074bc1  lea     rax, [rsp+2D0h+var_270]
0x140074bc6  mov     [rsp+2D0h+var_290], rax
0x140074bcb  lea     rax, [rsp+2D0h+var_280]
0x140074bd0  mov     [rsp+2D0h+var_298], rax
0x140074bd5  lea     rax, [rsp+2D0h+var_268]
0x140074bda  mov     [rsp+2D0h+var_2A0], rax
0x140074bdf  lea     rax, [rsp+2D0h+var_27C]
0x140074be4  mov     [rsp+2D0h+var_2A8], rax
0x140074be9  lea     rax, [rsp+2D0h+var_260]
0x140074bee  mov     [rsp+2D0h+ppv], rax
0x140074bf3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140074bf8  mov     ebx, 1
0x140074bfd  jmp     loc_140074CB6
0x140074c02  mov     rcx, [rsi]
0x140074c05  lea     rdi, [rsi+8]
0x140074c09  mov     rdx, rdi
0x140074c0c  mov     rax, [rcx]
0x140074c0f  mov     rax, [rax+38h]
0x140074c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140074c18  mov     ebx, eax
0x140074c1a  test    eax, eax
0x140074c1c  jns     short loc_140074C33
0x140074c1e  mov     ebx, 1
0x140074c23  cmp     [rdi], r15
0x140074c26  jz      short loc_140074C38
0x140074c28  mov     rcx, rdi
0x140074c2b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140074c30  mov     [rdi], r15
0x140074c33  cmp     [rdi], r15
0x140074c36  jnz     short loc_140074CB6
0x140074c38  mov     eax, cs:dword_140150118
0x140074c3e  cmp     eax, 2
0x140074c41  jbe     short loc_140074CB6
0x140074c43  lea     rax, aInitialize; "Initialize"
0x140074c4a  mov     [rsp+2D0h+var_27C], 5Dh ; ']'
0x140074c52  mov     [rsp+2D0h+var_260], rax
0x140074c57  lea     rdx, byte_14013EF9F
0x140074c5e  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140074c65  mov     [rsp+2D0h+var_268], rax
0x140074c6a  mov     eax, 80004005h
0x140074c6f  mov     [rsp+2D0h+var_280], eax
0x140074c73  lea     rax, aNullPortMapCol; "Null port map collection. NAT device un"...
0x140074c7a  mov     [rsp+2D0h+var_270], rax
0x140074c7f  lea     rax, [rsp+2D0h+var_260]
0x140074c84  mov     [rsp+2D0h+var_290], rax
0x140074c89  lea     rax, [rsp+2D0h+var_27C]
0x140074c8e  mov     [rsp+2D0h+var_298], rax
0x140074c93  lea     rax, [rsp+2D0h+var_268]
0x140074c98  mov     [rsp+2D0h+var_2A0], rax
0x140074c9d  lea     rax, [rsp+2D0h+var_280]
0x140074ca2  mov     [rsp+2D0h+var_2A8], rax
0x140074ca7  lea     rax, [rsp+2D0h+var_270]
0x140074cac  mov     [rsp+2D0h+ppv], rax
0x140074cb1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140074cb6  mov     rcx, r14; Block
0x140074cb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140074cbe  test    ebx, ebx
0x140074cc0  jns     short loc_140074CCA
0x140074cc2  mov     rcx, rsi; this
0x140074cc5  call    ?Terminate@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Terminate(void)
0x140074cca  mov     eax, ebx
0x140074ccc  mov     rcx, [rbp+1D0h+var_40]
0x140074cd3  xor     rcx, rsp; StackCookie
0x140074cd6  call    __security_check_cookie
0x140074cdb  add     rsp, 2A8h
0x140074ce2  pop     r15
0x140074ce4  pop     r14
0x140074ce6  pop     rdi
0x140074ce7  pop     rsi
0x140074ce8  pop     rbx
0x140074ce9  pop     rbp
0x140074cea  retn
```
