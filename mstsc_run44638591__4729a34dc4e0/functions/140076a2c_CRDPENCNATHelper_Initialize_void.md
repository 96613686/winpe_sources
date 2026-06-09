# CRDPENCNATHelper::Initialize(void)

- ea: `0x140076a2c`
- end: `0x140076e5b`
- name: `?Initialize@CRDPENCNATHelper@@QEAAJXZ`
- size: `1071`
- prototype: `__int64 __fastcall(CRDPENCNATHelper *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006ca00`

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
- `0x140076a2c`
- `0x140076f64`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140076a64`
- `KERNEL32!GetModuleFileNameW` at `0x140076a64`
- `KERNEL32!GetCurrentProcessId` at `0x140076b80`
- `KERNEL32!GetCurrentProcessId` at `0x140076b80`
- `KERNEL32!GetLastError` at `0x140076a71`
- `KERNEL32!GetLastError` at `0x140076a71`
- `ole32!CoCreateInstance` at `0x140076cca`
- `ole32!CoCreateInstance` at `0x140076cca`
- `OLEAUT32!__imp_SysAllocString` at `0x140076c0c`
- `OLEAUT32!__imp_SysAllocString` at `0x140076c77`
- `OLEAUT32!__imp_SysAllocString` at `0x140076c0c`
- `OLEAUT32!__imp_SysAllocString` at `0x140076c77`

## string_xrefs

- `0x140076d1b`: `Failed to create the UPnPNAT object (0x%08x)`
- `0x140076bd5`: `Failed to create the map string`

## pseudocode

```c
__int64 __fastcall CRDPENCNATHelper::Initialize(CRDPENCNATHelper *this)
{
  int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  wchar_t *v4; // rax
  WCHAR *v5; // rbx
  __int64 v6; // rax
  size_t v7; // rdi
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
  LastError = StringCchPrintfW(v8, v7, (size_t *)L"%s(%d)#RDPENC", v5, ppv);
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v26 = Instance;
      v24 = 79;
      v27 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
      v25 = -2147467259;
      v29[0] = "Failed to create the UPnPNAT object (0x%08x)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140152118,
        (unsigned int)&dword_14014111C,
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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v25 = 93;
    v29[0] = "Initialize";
    v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
    v24 = -2147467259;
    v27 = "Null port map collection. NAT device unavailable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)&byte_1401410D7,
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
0x140076a2c  push    rbp
0x140076a2e  push    rbx
0x140076a2f  push    rsi
0x140076a30  push    rdi
0x140076a31  push    r14
0x140076a33  push    r15
0x140076a35  lea     rbp, [rsp-1A8h]
0x140076a3d  sub     rsp, 2A8h
0x140076a44  mov     rax, cs:__security_cookie
0x140076a4b  xor     rax, rsp
0x140076a4e  mov     [rbp+1D0h+var_40], rax
0x140076a55  mov     rsi, rcx
0x140076a58  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x140076a5c  xor     ecx, ecx; hModule
0x140076a5e  mov     r8d, 105h; nSize
0x140076a64  call    cs:__imp_GetModuleFileNameW
0x140076a6a  xor     r15d, r15d
0x140076a6d  test    eax, eax
0x140076a6f  jnz     short loc_140076ADB
0x140076a71  call    cs:__imp_GetLastError
0x140076a77  mov     ebx, eax
0x140076a79  mov     rcx, cs:WPP_GLOBAL_Control
0x140076a80  lea     rax, WPP_GLOBAL_Control
0x140076a87  cmp     rcx, rax
0x140076a8a  jz      short loc_140076ABF
0x140076a8c  test    byte ptr [rcx+1Ch], 8
0x140076a90  jz      short loc_140076ABF
0x140076a92  cmp     byte ptr [rcx+19h], 2
0x140076a96  jb      short loc_140076ABF
0x140076a98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140076a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140076aa4  lea     edx, [r15+0Ah]
0x140076aa8  mov     r9d, eax
0x140076aab  mov     dword ptr [rsp+2D0h+ppv], ebx
0x140076aaf  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140076ab6  mov     rcx, [rcx+10h]
0x140076aba  call    WPP_SF_Dd
0x140076abf  test    ebx, ebx
0x140076ac1  jle     short loc_140076ACC
0x140076ac3  movzx   ebx, bx
0x140076ac6  or      ebx, 80070000h
0x140076acc  test    ebx, ebx
0x140076ace  mov     eax, 80004005h
0x140076ad3  cmovns  ebx, eax
0x140076ad6  jmp     loc_140076E32
0x140076adb  mov     edx, 5Ch ; '\'; Ch
0x140076ae0  lea     rcx, [rbp+1D0h+Filename]; Str
0x140076ae4  call    wcsrchr_0
0x140076ae9  mov     rbx, rax
0x140076aec  test    rax, rax
0x140076aef  jnz     short loc_140076AF7
0x140076af1  lea     rbx, [rbp+1D0h+Filename]
0x140076af5  jmp     short loc_140076AFB
0x140076af7  add     rbx, 2
0x140076afb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140076aff  mov     rax, rcx
0x140076b02  inc     rax
0x140076b05  cmp     [rbx+rax*2], r15w
0x140076b0a  jnz     short loc_140076B02
0x140076b0c  lea     rdi, [rax+2Fh]
0x140076b10  mov     eax, 2
0x140076b15  mul     rdi
0x140076b18  cmovb   rax, rcx
0x140076b1c  mov     rcx, rax; Size
0x140076b1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140076b24  mov     r14, rax
0x140076b27  test    rax, rax
0x140076b2a  jnz     short loc_140076B80
0x140076b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140076b33  lea     rax, WPP_GLOBAL_Control
0x140076b3a  cmp     rcx, rax
0x140076b3d  jz      short loc_140076B76
0x140076b3f  test    byte ptr [rcx+1Ch], 8
0x140076b43  jz      short loc_140076B76
0x140076b45  cmp     byte ptr [rcx+19h], 2
0x140076b49  jb      short loc_140076B76
0x140076b4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140076b50  mov     rcx, cs:WPP_GLOBAL_Control
0x140076b57  lea     edx, [r14+0Bh]
0x140076b5b  mov     r9d, eax
0x140076b5e  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x140076b66  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140076b6d  mov     rcx, [rcx+10h]
0x140076b71  call    WPP_SF_Dd
0x140076b76  mov     ebx, 8007000Eh
0x140076b7b  jmp     loc_140076E32
0x140076b80  call    cs:__imp_GetCurrentProcessId
0x140076b86  mov     r9, rbx
0x140076b89  lea     r8, aSDRdpenc; "%s(%d)#RDPENC"
0x140076b90  mov     rdx, rdi; unsigned __int64
0x140076b93  mov     dword ptr [rsp+2D0h+ppv], eax
0x140076b97  mov     rcx, r14; unsigned __int16 *
0x140076b9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140076b9f  mov     ebx, eax
0x140076ba1  test    eax, eax
0x140076ba3  jns     short loc_140076C09
0x140076ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140076bac  lea     rax, WPP_GLOBAL_Control
0x140076bb3  cmp     rcx, rax
0x140076bb6  jz      loc_140076E26
0x140076bbc  test    byte ptr [rcx+1Ch], 8
0x140076bc0  jz      loc_140076E26
0x140076bc6  cmp     byte ptr [rcx+19h], 2
0x140076bca  jb      loc_140076E26
0x140076bd0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140076bd5  lea     rcx, aFailedToCreate_62; "Failed to create the map string"
0x140076bdc  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x140076be0  mov     [rsp+2D0h+ppv], rcx
0x140076be5  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140076bec  mov     rcx, cs:WPP_GLOBAL_Control
0x140076bf3  mov     edx, 0Ch
0x140076bf8  mov     r9d, eax
0x140076bfb  mov     rcx, [rcx+10h]
0x140076bff  call    WPP_SF_DsD
0x140076c04  jmp     loc_140076E26
0x140076c09  mov     rcx, r14; psz
0x140076c0c  call    cs:__imp_SysAllocString
0x140076c12  mov     [rsi+30h], rax
0x140076c16  test    rax, rax
0x140076c19  jnz     short loc_140076C70
0x140076c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c22  lea     rax, WPP_GLOBAL_Control
0x140076c29  cmp     rcx, rax
0x140076c2c  jz      short loc_140076C66
0x140076c2e  test    byte ptr [rcx+1Ch], 8
0x140076c32  jz      short loc_140076C66
0x140076c34  cmp     byte ptr [rcx+19h], 2
0x140076c38  jb      short loc_140076C66
0x140076c3a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140076c3f  mov     edx, 0Dh
0x140076c44  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c4b  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x140076c52  mov     r9d, eax
0x140076c55  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x140076c5d  mov     rcx, [rcx+10h]
0x140076c61  call    WPP_SF_Dd
0x140076c66  mov     ebx, 8007000Eh
0x140076c6b  jmp     loc_140076E26
0x140076c70  lea     rcx, aTcp; "TCP"
0x140076c77  call    cs:__imp_SysAllocString
0x140076c7d  mov     [rsi+38h], rax
0x140076c81  test    rax, rax
0x140076c84  jnz     short loc_140076CB1
0x140076c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c8d  lea     rax, WPP_GLOBAL_Control
0x140076c94  cmp     rcx, rax
0x140076c97  jz      short loc_140076C66
0x140076c99  test    byte ptr [rcx+1Ch], 8
0x140076c9d  jz      short loc_140076C66
0x140076c9f  cmp     byte ptr [rcx+19h], 2
0x140076ca3  jb      short loc_140076C66
0x140076ca5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140076caa  mov     edx, 0Eh
0x140076caf  jmp     short loc_140076C44
0x140076cb1  xor     edx, edx; pUnkOuter
0x140076cb3  mov     [rsp+2D0h+ppv], rsi; ppv
0x140076cb8  lea     r9, _GUID_b171c812_cc76_485a_94d8_b6b3a2794e99; riid
0x140076cbf  lea     rcx, CLSID_UPnPNAT; rclsid
0x140076cc6  lea     r8d, [rdx+1]; dwClsContext
0x140076cca  call    cs:__imp_CoCreateInstance
0x140076cd0  test    eax, eax
0x140076cd2  jns     loc_140076D72
0x140076cd8  mov     ecx, cs:dword_140152118
0x140076cde  cmp     ecx, 2
0x140076ce1  jbe     loc_140076D68
0x140076ce7  mov     [rsp+2D0h+var_278], eax
0x140076ceb  lea     rdx, dword_14014111C
0x140076cf2  lea     rax, aInitialize; "Initialize"
0x140076cf9  mov     [rsp+2D0h+var_280], 4Fh ; 'O'
0x140076d01  mov     [rsp+2D0h+var_270], rax
0x140076d06  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140076d0d  mov     [rsp+2D0h+var_268], rax
0x140076d12  mov     eax, 80004005h
0x140076d17  mov     [rsp+2D0h+var_27C], eax
0x140076d1b  lea     rax, aFailedToCreate_37; "Failed to create the UPnPNAT object (0x"...
0x140076d22  mov     [rsp+2D0h+var_260], rax
0x140076d27  lea     rax, [rsp+2D0h+var_278]
0x140076d2c  mov     [rsp+2D0h+var_288], rax
0x140076d31  lea     rax, [rsp+2D0h+var_270]
0x140076d36  mov     [rsp+2D0h+var_290], rax
0x140076d3b  lea     rax, [rsp+2D0h+var_280]
0x140076d40  mov     [rsp+2D0h+var_298], rax
0x140076d45  lea     rax, [rsp+2D0h+var_268]
0x140076d4a  mov     [rsp+2D0h+var_2A0], rax
0x140076d4f  lea     rax, [rsp+2D0h+var_27C]
0x140076d54  mov     [rsp+2D0h+var_2A8], rax
0x140076d59  lea     rax, [rsp+2D0h+var_260]
0x140076d5e  mov     [rsp+2D0h+ppv], rax
0x140076d63  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140076d68  mov     ebx, 1
0x140076d6d  jmp     loc_140076E26
0x140076d72  mov     rcx, [rsi]
0x140076d75  lea     rdi, [rsi+8]
0x140076d79  mov     rdx, rdi
0x140076d7c  mov     rax, [rcx]
0x140076d7f  mov     rax, [rax+38h]
0x140076d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076d88  mov     ebx, eax
0x140076d8a  test    eax, eax
0x140076d8c  jns     short loc_140076DA3
0x140076d8e  mov     ebx, 1
0x140076d93  cmp     [rdi], r15
0x140076d96  jz      short loc_140076DA8
0x140076d98  mov     rcx, rdi
0x140076d9b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140076da0  mov     [rdi], r15
0x140076da3  cmp     [rdi], r15
0x140076da6  jnz     short loc_140076E26
0x140076da8  mov     eax, cs:dword_140152118
0x140076dae  cmp     eax, 2
0x140076db1  jbe     short loc_140076E26
0x140076db3  lea     rax, aInitialize; "Initialize"
0x140076dba  mov     [rsp+2D0h+var_27C], 5Dh ; ']'
0x140076dc2  mov     [rsp+2D0h+var_260], rax
0x140076dc7  lea     rdx, byte_1401410D7
0x140076dce  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140076dd5  mov     [rsp+2D0h+var_268], rax
0x140076dda  mov     eax, 80004005h
0x140076ddf  mov     [rsp+2D0h+var_280], eax
0x140076de3  lea     rax, aNullPortMapCol; "Null port map collection. NAT device un"...
0x140076dea  mov     [rsp+2D0h+var_270], rax
0x140076def  lea     rax, [rsp+2D0h+var_260]
0x140076df4  mov     [rsp+2D0h+var_290], rax
0x140076df9  lea     rax, [rsp+2D0h+var_27C]
0x140076dfe  mov     [rsp+2D0h+var_298], rax
0x140076e03  lea     rax, [rsp+2D0h+var_268]
0x140076e08  mov     [rsp+2D0h+var_2A0], rax
0x140076e0d  lea     rax, [rsp+2D0h+var_280]
0x140076e12  mov     [rsp+2D0h+var_2A8], rax
0x140076e17  lea     rax, [rsp+2D0h+var_270]
0x140076e1c  mov     [rsp+2D0h+ppv], rax
0x140076e21  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140076e26  mov     rcx, r14; Block
0x140076e29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140076e2e  test    ebx, ebx
0x140076e30  jns     short loc_140076E3A
0x140076e32  mov     rcx, rsi; this
0x140076e35  call    ?Terminate@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Terminate(void)
0x140076e3a  mov     eax, ebx
0x140076e3c  mov     rcx, [rbp+1D0h+var_40]
0x140076e43  xor     rcx, rsp; StackCookie
0x140076e46  call    __security_check_cookie
0x140076e4b  add     rsp, 2A8h
0x140076e52  pop     r15
0x140076e54  pop     r14
0x140076e56  pop     rdi
0x140076e57  pop     rsi
0x140076e58  pop     rbx
0x140076e59  pop     rbp
0x140076e5a  retn
```
