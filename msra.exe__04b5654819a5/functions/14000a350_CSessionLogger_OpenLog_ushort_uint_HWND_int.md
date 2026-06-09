# CSessionLogger::OpenLog(ushort *,uint,HWND__ *,int)

- ea: `0x14000a350`
- end: `0x14000a850`
- name: `?OpenLog@CSessionLogger@@QEAAJPEAGIPEAUHWND__@@H@Z`
- size: `1280`
- prototype: `__int64 __usercall@<rax>(CSessionLogger *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, HWND@<r9>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002ad4c`

## callees

- `0x140002463`
- `0x1400044f8`
- `0x1400080fc`
- `0x14000a350`
- `0x140034ce4`
- `0x140035888`
- `0x140036b80`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14000a7b4`
- `KERNEL32!CreateThread` at `0x14000a7b4`
- `KERNEL32!CreateMutexW` at `0x14000a73e`
- `KERNEL32!CreateMutexW` at `0x14000a73e`
- `KERNEL32!CreateEventW` at `0x14000a6e2`
- `KERNEL32!CreateEventW` at `0x14000a6e2`
- `KERNEL32!CreateDirectoryW` at `0x14000a602`
- `KERNEL32!CreateDirectoryW` at `0x14000a602`
- `KERNEL32!GetLastError` at `0x14000a703`
- `KERNEL32!GetLastError` at `0x14000a717`
- `KERNEL32!GetLastError` at `0x14000a759`
- `KERNEL32!GetLastError` at `0x14000a76d`
- `KERNEL32!GetLastError` at `0x14000a703`
- `KERNEL32!GetLastError` at `0x14000a717`
- `KERNEL32!GetLastError` at `0x14000a759`
- `KERNEL32!GetLastError` at `0x14000a76d`
- `ole32!CoCreateInstance` at `0x14000a3e7`
- `ole32!CoCreateInstance` at `0x14000a3e7`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a6b4`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a6b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a6a4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a7db`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a7ef`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a6a4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a7db`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a7ef`
- `OLEAUT32!__imp_VariantClear` at `0x14000a472`
- `OLEAUT32!__imp_VariantClear` at `0x14000a4d6`
- `OLEAUT32!__imp_VariantClear` at `0x14000a53c`
- `OLEAUT32!__imp_VariantClear` at `0x14000a472`
- `OLEAUT32!__imp_VariantClear` at `0x14000a4d6`
- `OLEAUT32!__imp_VariantClear` at `0x14000a53c`

## string_xrefs

- `0x14000a403`: `CSessionLogger::OpenLog`
- `0x14000a5be`: `CSessionLogger::OpenLog`
- `0x14000a62d`: `CSessionLogger::OpenLog`
- `0x14000a674`: `%s\%s.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSessionLogger::OpenLog(LPVOID *this, unsigned __int16 *a2, __int64 a3, HWND a4, int a5)
{
  LPVOID v7; // rcx
  HRESULT Instance; // eax
  CEventLogger *v9; // rcx
  int v10; // ebx
  unsigned int v11; // r9d
  LPVOID v12; // rcx
  __int64 v13; // rax
  CEventLogger *v14; // rcx
  LPVOID v15; // rcx
  __int64 v16; // rax
  CEventLogger *v17; // rcx
  LPVOID v18; // rcx
  __int64 v19; // rax
  CEventLogger *v20; // rcx
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v22; // rcx
  OLECHAR *v23; // rsi
  signed int TimeStamp; // eax
  CEventLogger *v25; // rcx
  OLECHAR *v26; // r14
  unsigned int v27; // r9d
  OLECHAR *v28; // rcx
  BSTR v29; // rax
  HANDLE EventW; // rax
  CEventLogger *v31; // rcx
  signed int LastError; // eax
  HANDLE MutexW; // rax
  CEventLogger *v34; // rcx
  signed int v35; // eax
  HANDLE v36; // rax
  int v37; // edx
  __int16 v39; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpPathName; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v44; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz[1024]; // [rsp+90h] [rbp-70h] BYREF

  v39 = -1;
  ThreadId = 0;
  memset_0(psz, 0, sizeof(psz));
  lpPathName = 0;
  bstrString = 0;
  v7 = *this;
  if ( *this )
  {
    *this = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &IID_IXMLDOMDocument, this);
  v10 = Instance;
  if ( Instance < 0 )
  {
    v11 = 76;
LABEL_5:
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
      v11,
      L"CSessionLogger::OpenLog",
      Instance);
    return (unsigned int)v10;
  }
  v12 = *this;
  v13 = *(_QWORD *)*this;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v44 = pvarg;
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v13 + 640))(v12, L"ProhibitDTD", &v44);
  VariantClear(&pvarg);
  if ( v10 < 0 )
  {
    CEventLogger::LogError(
      v14,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
      0x4Eu,
      L"CSessionLogger::OpenLog",
      v10);
    return (unsigned int)v10;
  }
  v15 = *this;
  v16 = *(_QWORD *)*this;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v44 = pvarg;
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v16 + 640))(v15, L"AllowXsltScript", &v44);
  VariantClear(&pvarg);
  if ( v10 < 0 )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
      0x4Fu,
      L"CSessionLogger::OpenLog",
      v10);
    return (unsigned int)v10;
  }
  v18 = *this;
  v19 = *(_QWORD *)*this;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v44 = pvarg;
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v19 + 640))(
          v18,
          L"AllowDocumentFunction",
          &v44);
  VariantClear(&pvarg);
  if ( v10 < 0 )
  {
    CEventLogger::LogError(
      v20,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
      0x50u,
      L"CSessionLogger::OpenLog",
      v10);
    return (unsigned int)v10;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)*this + 520LL))(
               *this,
               qword_140064220,
               &v39);
  v10 = Instance;
  if ( Instance < 0 )
  {
    v11 = 83;
    goto LABEL_5;
  }
  *((_DWORD *)this + 9) = a5;
  DirectoryAsBSTR = GetDirectoryAsBSTR(5, (unsigned __int16 **)&lpPathName, L"\\Remote Assistance Logs");
  v10 = DirectoryAsBSTR;
  v23 = (OLECHAR *)lpPathName;
  if ( DirectoryAsBSTR >= 0 )
  {
    if ( !lpPathName )
    {
      v10 = -2147024882;
      CEventLogger::LogError(
        v22,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
        0x63u,
        L"CSessionLogger::OpenLog",
        0x8007000E);
      return (unsigned int)v10;
    }
    CreateDirectoryW(lpPathName, 0);
    TimeStamp = MakeTimeStamp(&bstrString);
    v10 = TimeStamp;
    v26 = bstrString;
    if ( TimeStamp < 0 )
    {
      v27 = 105;
LABEL_22:
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
        v27,
        L"CSessionLogger::OpenLog",
        TimeStamp);
LABEL_43:
      if ( v26 )
        SysFreeString(v26);
      goto LABEL_45;
    }
    if ( !bstrString )
    {
      v10 = -2147024882;
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
        0x6Au,
        L"CSessionLogger::OpenLog",
        0x8007000E);
      goto LABEL_45;
    }
    TimeStamp = StringCchPrintfW(psz, 0x400u, L"%s\\%s.xml", v23, bstrString);
    v10 = TimeStamp;
    if ( TimeStamp < 0 )
    {
      v27 = 112;
      goto LABEL_22;
    }
    v28 = (OLECHAR *)this[1];
    if ( psz != v28 )
    {
      SysFreeString(v28);
      v29 = SysAllocString(psz);
      this[1] = v29;
      if ( !v29 )
        ATL::AtlThrowImpl(-2147024882);
    }
    *((_DWORD *)this + 4) = 1035;
    this[3] = a4;
    EventW = CreateEventW(0, 0, 0, 0);
    this[6] = EventW;
    if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( v10 >= 0 )
          goto LABEL_35;
      }
      else
      {
        v10 = -2147467259;
      }
      CEventLogger::LogError(
        v31,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
        0x84u,
        L"CSessionLogger::OpenLog",
        v10);
      goto LABEL_43;
    }
LABEL_35:
    MutexW = CreateMutexW(0, 0, 0);
    this[8] = MutexW;
    if ( (((unsigned __int64)MutexW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( GetLastError() )
      {
        v35 = GetLastError();
        v10 = v35;
        if ( v35 > 0 )
          v10 = (unsigned __int16)v35 | 0x80070000;
        if ( v10 >= 0 )
          goto LABEL_40;
      }
      else
      {
        v10 = -2147467259;
      }
      CEventLogger::LogError(
        v34,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
        0x87u,
        L"CSessionLogger::OpenLog",
        v10);
      goto LABEL_43;
    }
LABEL_40:
    *((_DWORD *)this + 14) = 1;
    v36 = CreateThread(0, 0, CSessionLogger::StaticThreadProc, this, 0, &ThreadId);
    this[5] = v36;
    v37 = v10;
    if ( !v36 )
      v37 = -2147467259;
    v10 = v37;
    goto LABEL_43;
  }
  CEventLogger::LogError(
    v22,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\sessionlogger.cpp",
    0x62u,
    L"CSessionLogger::OpenLog",
    DirectoryAsBSTR);
LABEL_45:
  if ( v23 )
    SysFreeString(v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a350  push    rbp
0x14000a352  push    rbx
0x14000a353  push    rsi
0x14000a354  push    rdi
0x14000a355  push    r14
0x14000a357  push    r15
0x14000a359  lea     rbp, [rsp-7A8h]
0x14000a361  sub     rsp, 8A8h
0x14000a368  mov     rax, cs:__security_cookie
0x14000a36f  xor     rax, rsp
0x14000a372  mov     [rbp+7D0h+var_40], rax
0x14000a379  mov     r15, r9
0x14000a37c  mov     rdi, rcx
0x14000a37f  or      esi, 0FFFFFFFFh
0x14000a382  mov     [rsp+8D0h+var_8A0], si
0x14000a387  mov     [rsp+8D0h+ThreadId], 0
0x14000a38f  xor     edx, edx; Val
0x14000a391  mov     r8d, 800h; Size
0x14000a397  lea     rcx, [rbp+7D0h+psz]; void *
0x14000a39b  call    memset_0
0x14000a3a0  mov     [rsp+8D0h+lpPathName], 0
0x14000a3a9  mov     [rsp+8D0h+bstrString], 0
0x14000a3b2  mov     rcx, [rdi]
0x14000a3b5  test    rcx, rcx
0x14000a3b8  jz      short loc_14000A3CE
0x14000a3ba  mov     qword ptr [rdi], 0
0x14000a3c1  mov     rax, [rcx]
0x14000a3c4  mov     rax, [rax+10h]
0x14000a3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3cd  nop
0x14000a3ce  mov     [rsp+8D0h+ppv], rdi; ppv
0x14000a3d3  lea     r9, IID_IXMLDOMDocument; riid
0x14000a3da  xor     edx, edx; pUnkOuter
0x14000a3dc  lea     r8d, [rdx+17h]; dwClsContext
0x14000a3e0  lea     rcx, CLSID_DOMDocument60; rclsid
0x14000a3e7  call    cs:__imp_CoCreateInstance
0x14000a3ee  nop     dword ptr [rax+rax+00h]
0x14000a3f3  mov     ebx, eax
0x14000a3f5  test    eax, eax
0x14000a3f7  jns     short loc_14000A427
0x14000a3f9  mov     r9d, 4Ch ; 'L'; unsigned int
0x14000a3ff  mov     dword ptr [rsp+8D0h+lpThreadId], eax; unsigned int
0x14000a403  lea     rax, aCsessionlogger_0; "CSessionLogger::OpenLog"
0x14000a40a  mov     [rsp+8D0h+ppv], rax; unsigned __int16 *
0x14000a40f  lea     r8, aBaseDiagnosisR_11; "base\\diagnosis\\ra\\ui\\sessionlogger."...
0x14000a416  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000a41d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000a422  jmp     loc_14000A7FB
0x14000a427  mov     rcx, [rdi]
0x14000a42a  mov     rax, [rcx]
0x14000a42d  mov     r14d, 0Bh
0x14000a433  mov     word ptr [rsp+8D0h+pvarg], r14w
0x14000a439  mov     word ptr [rsp+8D0h+pvarg+8], si
0x14000a43e  movups  xmm0, xmmword ptr [rsp+8D0h+pvarg]
0x14000a443  movaps  [rsp+8D0h+var_860], xmm0
0x14000a448  movsd   xmm1, qword ptr [rsp+8D0h+pvarg+10h]
0x14000a44e  movsd   [rbp+7D0h+var_850], xmm1
0x14000a453  lea     r8, [rsp+8D0h+var_860]
0x14000a458  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x14000a45f  mov     rax, [rax+280h]
0x14000a466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a46b  mov     ebx, eax
0x14000a46d  lea     rcx, [rsp+8D0h+pvarg]; pvarg
0x14000a472  call    cs:__imp_VariantClear
0x14000a479  nop     dword ptr [rax+rax+00h]
0x14000a47e  test    ebx, ebx
0x14000a480  jns     short loc_14000A48F
0x14000a482  mov     dword ptr [rsp+8D0h+lpThreadId], ebx
0x14000a486  lea     r9d, [r14+43h]
0x14000a48a  jmp     loc_14000A403
0x14000a48f  mov     rcx, [rdi]
0x14000a492  mov     rax, [rcx]
0x14000a495  mov     word ptr [rsp+8D0h+pvarg], r14w
0x14000a49b  xor     edx, edx
0x14000a49d  mov     word ptr [rsp+8D0h+pvarg+8], dx
0x14000a4a2  movups  xmm0, xmmword ptr [rsp+8D0h+pvarg]
0x14000a4a7  movaps  [rsp+8D0h+var_860], xmm0
0x14000a4ac  movsd   xmm1, qword ptr [rsp+8D0h+pvarg+10h]
0x14000a4b2  movsd   [rbp+7D0h+var_850], xmm1
0x14000a4b7  lea     r8, [rsp+8D0h+var_860]
0x14000a4bc  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14000a4c3  mov     rax, [rax+280h]
0x14000a4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4cf  mov     ebx, eax
0x14000a4d1  lea     rcx, [rsp+8D0h+pvarg]; pvarg
0x14000a4d6  call    cs:__imp_VariantClear
0x14000a4dd  nop     dword ptr [rax+rax+00h]
0x14000a4e2  test    ebx, ebx
0x14000a4e4  jns     short loc_14000A4F5
0x14000a4e6  mov     dword ptr [rsp+8D0h+lpThreadId], ebx
0x14000a4ea  mov     r9d, 4Fh ; 'O'
0x14000a4f0  jmp     loc_14000A403
0x14000a4f5  mov     rcx, [rdi]
0x14000a4f8  mov     rax, [rcx]
0x14000a4fb  mov     word ptr [rsp+8D0h+pvarg], r14w
0x14000a501  xor     edx, edx
0x14000a503  mov     word ptr [rsp+8D0h+pvarg+8], dx
0x14000a508  movups  xmm0, xmmword ptr [rsp+8D0h+pvarg]
0x14000a50d  movaps  [rsp+8D0h+var_860], xmm0
0x14000a512  movsd   xmm1, qword ptr [rsp+8D0h+pvarg+10h]
0x14000a518  movsd   [rbp+7D0h+var_850], xmm1
0x14000a51d  lea     r8, [rsp+8D0h+var_860]
0x14000a522  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x14000a529  mov     rax, [rax+280h]
0x14000a530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a535  mov     ebx, eax
0x14000a537  lea     rcx, [rsp+8D0h+pvarg]; pvarg
0x14000a53c  call    cs:__imp_VariantClear
0x14000a543  nop     dword ptr [rax+rax+00h]
0x14000a548  test    ebx, ebx
0x14000a54a  jns     short loc_14000A55B
0x14000a54c  mov     dword ptr [rsp+8D0h+lpThreadId], ebx
0x14000a550  mov     r9d, 50h ; 'P'
0x14000a556  jmp     loc_14000A403
0x14000a55b  mov     rcx, [rdi]
0x14000a55e  mov     rax, [rcx]
0x14000a561  lea     r8, [rsp+8D0h+var_8A0]
0x14000a566  mov     rdx, cs:qword_140064220
0x14000a56d  mov     rax, [rax+208h]
0x14000a574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a579  mov     ebx, eax
0x14000a57b  test    eax, eax
0x14000a57d  jns     short loc_14000A58A
0x14000a57f  mov     r9d, 53h ; 'S'
0x14000a585  jmp     loc_14000A3FF
0x14000a58a  mov     eax, [rbp+7D0h+arg_20]
0x14000a590  mov     [rdi+24h], eax
0x14000a593  lea     r8, aRemoteAssistan_0; "\\Remote Assistance Logs"
0x14000a59a  lea     rdx, [rsp+8D0h+lpPathName]; unsigned __int16 **
0x14000a59f  mov     ecx, 5; csidl
0x14000a5a4  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14000a5a9  mov     ebx, eax
0x14000a5ab  mov     rsi, [rsp+8D0h+lpPathName]
0x14000a5b0  test    eax, eax
0x14000a5b2  jns     short loc_14000A5E2
0x14000a5b4  mov     dword ptr [rsp+8D0h+lpThreadId], eax; unsigned int
0x14000a5b8  mov     r9d, 62h ; 'b'; unsigned int
0x14000a5be  lea     rax, aCsessionlogger_0; "CSessionLogger::OpenLog"
0x14000a5c5  mov     [rsp+8D0h+ppv], rax; unsigned __int16 *
0x14000a5ca  lea     r8, aBaseDiagnosisR_11; "base\\diagnosis\\ra\\ui\\sessionlogger."...
0x14000a5d1  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000a5d8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000a5dd  jmp     loc_14000A7E7
0x14000a5e2  test    rsi, rsi
0x14000a5e5  jnz     short loc_14000A5FD
0x14000a5e7  mov     ebx, 8007000Eh
0x14000a5ec  mov     dword ptr [rsp+8D0h+lpThreadId], 8007000Eh
0x14000a5f4  lea     r9d, [rsi+63h]
0x14000a5f8  jmp     loc_14000A403
0x14000a5fd  xor     edx, edx; lpSecurityAttributes
0x14000a5ff  mov     rcx, rsi; lpPathName
0x14000a602  call    cs:__imp_CreateDirectoryW
0x14000a609  nop     dword ptr [rax+rax+00h]
0x14000a60e  lea     rcx, [rsp+8D0h+bstrString]; unsigned __int16 **
0x14000a613  call    ?MakeTimeStamp@@YAJPEAPEAG@Z; MakeTimeStamp(ushort * *)
0x14000a618  mov     ebx, eax
0x14000a61a  mov     r14, [rsp+8D0h+bstrString]
0x14000a61f  test    eax, eax
0x14000a621  jns     short loc_14000A651
0x14000a623  mov     r9d, 69h ; 'i'; unsigned int
0x14000a629  mov     dword ptr [rsp+8D0h+lpThreadId], eax; unsigned int
0x14000a62d  lea     rax, aCsessionlogger_0; "CSessionLogger::OpenLog"
0x14000a634  mov     [rsp+8D0h+ppv], rax; unsigned __int16 *
0x14000a639  lea     r8, aBaseDiagnosisR_11; "base\\diagnosis\\ra\\ui\\sessionlogger."...
0x14000a640  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14000a647  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000a64c  jmp     loc_14000A7D3
0x14000a651  test    r14, r14
0x14000a654  jnz     short loc_14000A66C
0x14000a656  mov     ebx, 8007000Eh
0x14000a65b  mov     dword ptr [rsp+8D0h+lpThreadId], 8007000Eh
0x14000a663  lea     r9d, [r14+6Ah]
0x14000a667  jmp     loc_14000A5BE
0x14000a66c  mov     [rsp+8D0h+ppv], r14
0x14000a671  mov     r9, rsi
0x14000a674  lea     r8, aSSXml; "%s\\%s.xml"
0x14000a67b  mov     edx, 400h; unsigned __int64
0x14000a680  lea     rcx, [rbp+7D0h+psz]; unsigned __int16 *
0x14000a684  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a689  mov     ebx, eax
0x14000a68b  test    eax, eax
0x14000a68d  jns     short loc_14000A697
0x14000a68f  mov     r9d, 70h ; 'p'
0x14000a695  jmp     short loc_14000A629
0x14000a697  mov     rcx, [rdi+8]; bstrString
0x14000a69b  lea     rax, [rbp+7D0h+psz]
0x14000a69f  cmp     rax, rcx
0x14000a6a2  jz      short loc_14000A6CD
0x14000a6a4  call    cs:__imp_SysFreeString
0x14000a6ab  nop     dword ptr [rax+rax+00h]
0x14000a6b0  lea     rcx, [rbp+7D0h+psz]; psz
0x14000a6b4  call    cs:__imp_SysAllocString
0x14000a6bb  nop     dword ptr [rax+rax+00h]
0x14000a6c0  mov     [rdi+8], rax
0x14000a6c4  test    rax, rax
0x14000a6c7  jz      loc_14000A845
0x14000a6cd  mov     dword ptr [rdi+10h], 40Bh
0x14000a6d4  mov     [rdi+18h], r15
0x14000a6d8  xor     r9d, r9d; lpName
0x14000a6db  xor     r8d, r8d; bInitialState
0x14000a6de  xor     edx, edx; bManualReset
0x14000a6e0  xor     ecx, ecx; lpEventAttributes
0x14000a6e2  call    cs:__imp_CreateEventW
0x14000a6e9  nop     dword ptr [rax+rax+00h]
0x14000a6ee  mov     [rdi+30h], rax
0x14000a6f2  inc     rax
0x14000a6f5  mov     r15d, 80070000h
0x14000a6fb  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000a701  jnz     short loc_14000A737
0x14000a703  call    cs:__imp_GetLastError
0x14000a70a  nop     dword ptr [rax+rax+00h]
0x14000a70f  test    eax, eax
0x14000a711  jz      loc_14000A81D
0x14000a717  call    cs:__imp_GetLastError
0x14000a71e  nop     dword ptr [rax+rax+00h]
0x14000a723  mov     ebx, eax
0x14000a725  test    eax, eax
0x14000a727  jle     short loc_14000A72F
0x14000a729  movzx   ebx, ax
0x14000a72c  or      ebx, r15d
0x14000a72f  test    ebx, ebx
0x14000a731  js      loc_14000A822
0x14000a737  xor     r8d, r8d; lpName
0x14000a73a  xor     edx, edx; bInitialOwner
0x14000a73c  xor     ecx, ecx; lpMutexAttributes
0x14000a73e  call    cs:__imp_CreateMutexW
0x14000a745  nop     dword ptr [rax+rax+00h]
0x14000a74a  mov     [rdi+40h], rax
0x14000a74e  inc     rax
0x14000a751  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000a757  jnz     short loc_14000A78D
0x14000a759  call    cs:__imp_GetLastError
0x14000a760  nop     dword ptr [rax+rax+00h]
0x14000a765  test    eax, eax
0x14000a767  jz      loc_14000A831
0x14000a76d  call    cs:__imp_GetLastError
0x14000a774  nop     dword ptr [rax+rax+00h]
0x14000a779  mov     ebx, eax
0x14000a77b  test    eax, eax
0x14000a77d  jle     short loc_14000A785
0x14000a77f  movzx   ebx, ax
0x14000a782  or      ebx, r15d
0x14000a785  test    ebx, ebx
0x14000a787  js      loc_14000A836
0x14000a78d  mov     dword ptr [rdi+38h], 1
0x14000a794  lea     rax, [rsp+8D0h+ThreadId]
0x14000a799  mov     [rsp+8D0h+lpThreadId], rax; lpThreadId
0x14000a79e  mov     dword ptr [rsp+8D0h+ppv], 0; dwCreationFlags
0x14000a7a6  mov     r9, rdi; lpParameter
0x14000a7a9  lea     r8, ?StaticThreadProc@CSessionLogger@@SAKPEAPEAX@Z; lpStartAddress
0x14000a7b0  xor     edx, edx; dwStackSize
0x14000a7b2  xor     ecx, ecx; lpThreadAttributes
0x14000a7b4  call    cs:__imp_CreateThread
0x14000a7bb  nop     dword ptr [rax+rax+00h]
0x14000a7c0  mov     [rdi+28h], rax
0x14000a7c4  mov     edx, ebx
0x14000a7c6  mov     ebx, 80004005h
0x14000a7cb  test    rax, rax
0x14000a7ce  cmovz   edx, ebx
0x14000a7d1  mov     ebx, edx
0x14000a7d3  test    r14, r14
0x14000a7d6  jz      short loc_14000A7E7
0x14000a7d8  mov     rcx, r14; bstrString
0x14000a7db  call    cs:__imp_SysFreeString
0x14000a7e2  nop     dword ptr [rax+rax+00h]
0x14000a7e7  test    rsi, rsi
0x14000a7ea  jz      short loc_14000A7FB
0x14000a7ec  mov     rcx, rsi; bstrString
0x14000a7ef  call    cs:__imp_SysFreeString
0x14000a7f6  nop     dword ptr [rax+rax+00h]
0x14000a7fb  mov     eax, ebx
0x14000a7fd  mov     rcx, [rbp+7D0h+var_40]
0x14000a804  xor     rcx, rsp; StackCookie
0x14000a807  call    __security_check_cookie
0x14000a80c  add     rsp, 8A8h
0x14000a813  pop     r15
0x14000a815  pop     r14
0x14000a817  pop     rdi
0x14000a818  pop     rsi
0x14000a819  pop     rbx
0x14000a81a  pop     rbp
0x14000a81b  retn
0x14000a81d  mov     ebx, 80004005h
0x14000a822  mov     dword ptr [rsp+8D0h+lpThreadId], ebx
0x14000a826  mov     r9d, 84h
0x14000a82c  jmp     loc_14000A62D
0x14000a831  mov     ebx, 80004005h
0x14000a836  mov     dword ptr [rsp+8D0h+lpThreadId], ebx
0x14000a83a  mov     r9d, 87h
0x14000a840  jmp     loc_14000A62D
0x14000a845  mov     ecx, 8007000Eh; int
0x14000a84a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
