# CMsiTransaction::CMsiTransaction(ushort const *,ulong,ulong,ushort *)

- ea: `0x1801cf58c`
- end: `0x1801cf9de`
- name: `??0CMsiTransaction@@IEAA@PEBGKKPEAG@Z`
- size: `1106`
- prototype: `CMsiTransaction *__usercall@<rax>(CMsiTransaction *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ebbc`

## callees

- `0x180005af8`
- `0x18000d6d8`
- `0x180010ac0`
- `0x180014528`
- `0x180027634`
- `0x180067fec`
- `0x18008c93c`
- `0x1800ae46c`
- `0x1800c8268`
- `0x1800d04fc`
- `0x1800d7594`
- `0x18012be04`
- `0x18013a028`
- `0x180148a30`
- `0x1801cf58c`
- `0x1801d4694`
- `0x1802650ad`
- `0x180266010`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x1801cf753`
- `ntdll!RtlRandomEx` at `0x1801cf753`
- `KERNEL32!CloseHandle` at `0x1801cf809`
- `KERNEL32!CloseHandle` at `0x1801cf87a`
- `KERNEL32!CloseHandle` at `0x1801cf809`
- `KERNEL32!CloseHandle` at `0x1801cf87a`
- `KERNEL32!GetTickCount` at `0x1801cf692`
- `KERNEL32!GetTickCount` at `0x1801cf692`
- `KERNEL32!GetLastError` at `0x1801cf7d6`
- `KERNEL32!GetLastError` at `0x1801cf8ad`
- `KERNEL32!GetLastError` at `0x1801cf961`
- `KERNEL32!GetLastError` at `0x1801cf7d6`
- `KERNEL32!GetLastError` at `0x1801cf8ad`
- `KERNEL32!GetLastError` at `0x1801cf961`
- `KERNEL32!CreateEventW` at `0x1801cf7c6`
- `KERNEL32!CreateEventW` at `0x1801cf85b`
- `KERNEL32!CreateEventW` at `0x1801cf7c6`
- `KERNEL32!CreateEventW` at `0x1801cf85b`
- `KERNEL32!OpenProcess` at `0x1801cf94c`
- `KERNEL32!OpenProcess` at `0x1801cf94c`

## string_xrefs

- `0x1801cf763`: `Global\MSI%u`

## pseudocode

```c
CMsiTransaction *__fastcall CMsiTransaction::CMsiTransaction(
        CMsiTransaction *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  ulong SecureSecurityDescriptor; // eax
  unsigned int v8; // r14d
  int i; // edi
  ULONG v10; // eax
  const WCHAR *v11; // rax
  DWORD LastError; // r13d
  char *v13; // rcx
  const WCHAR *v14; // rax
  HANDLE v15; // rax
  unsigned int v16; // eax
  unsigned int CallerInfo; // eax
  HANDLE v18; // rax
  struct IMsiConfigurationManager *ConfigurationManager; // rax
  unsigned int v21; // [rsp+50h] [rbp-21h]
  void *v22; // [rsp+58h] [rbp-19h]
  __int64 v23; // [rsp+60h] [rbp-11h] BYREF
  struct IMsiConfigurationManager *v24; // [rsp+68h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+70h] [rbp-1h] BYREF
  ULONG Seed; // [rsp+D0h] [rbp+5Fh] BYREF
  ulong pExceptionObject; // [rsp+E0h] [rbp+6Fh] BYREF
  unsigned int v28; // [rsp+E8h] [rbp+77h]

  v28 = a4;
  *(_QWORD *)this = &CMsiTransaction::`vftable';
  MsiString::MsiString((CMsiTransaction *)((char *)this + 8), a2);
  *((_QWORD *)this + 2) = (unsigned int)a3;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 12) = &MsiString::s_NullString;
  *((_BYTE *)this + 104) = 0;
  *((_DWORD *)this + 27) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *(_QWORD *)((char *)this + 148) = 0;
  *(_QWORD *)((char *)this + 156) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_DWORD *)this + 194) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_WORD *)this + 420) = 0;
  Seed = GetTickCount();
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      "Beginning Multi-Package transaction.",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      v21,
      v22);
  _InterlockedIncrement((volatile signed __int32 *)this + 31);
  *((_BYTE *)this + 132) = 0;
  *((_WORD *)this + 82) = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  EventAttributes.nLength = 24;
  pExceptionObject = 0;
  SecureSecurityDescriptor = GetSecureSecurityDescriptor(&EventAttributes.lpSecurityDescriptor, &pExceptionObject, 0, 0);
  if ( SecureSecurityDescriptor )
  {
    pExceptionObject = SecureSecurityDescriptor;
    throw &pExceptionObject;
  }
  v8 = 0;
  for ( i = 0; i < 0xFFFF; ++i )
  {
    v10 = RtlRandomEx(&Seed);
    if ( (int)StringCchPrintfW(a5, 0x104u, L"Global\\MSI%u", v10 % 0xFF) < 0 )
    {
      pExceptionObject = 87;
      throw (long *)&pExceptionObject;
    }
    MsiString::operator=((char *)this + 96, a5);
    CElevate::CElevate((CElevate *)&v24, 1);
    v11 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 80LL))(*((_QWORD *)this + 12));
    *((_QWORD *)this + 8) = CreateEventW(&EventAttributes, 0, 0, v11);
    LastError = GetLastError();
    CElevate::~CElevate((CElevate *)&v24);
    v13 = (char *)*((_QWORD *)this + 8);
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( LastError == 183 )
      {
        CloseHandle(v13);
        *((_QWORD *)this + 8) = 0;
      }
      else
      {
        MsiString::MsiString((MsiString *)&v23, (CMsiTransaction *)((char *)this + 96));
        MsiString::operator+=(&v23, L"ET");
        v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 80LL))(v23);
        v15 = CreateEventW(&EventAttributes, 1, 0, v14);
        *((_QWORD *)this + 9) = v15;
        if ( (((unsigned __int64)v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          break;
        }
        CloseHandle(*((HANDLE *)this + 8));
        *((_QWORD *)this + 8) = 0;
        if ( v8 > 3 )
        {
          pExceptionObject = GetLastError();
          throw &pExceptionObject;
        }
        ++v8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
  }
  v16 = CMsiTransaction::SetUserToken(this, 0, v28);
  if ( v16 )
  {
    pExceptionObject = v16;
    throw &pExceptionObject;
  }
  CallerInfo = CMsiTransaction::GetCallerInfo((unsigned int *)this + 6, 0);
  if ( CallerInfo )
  {
    pExceptionObject = CallerInfo;
    throw &pExceptionObject;
  }
  if ( a3 < 0 )
  {
    v18 = OpenProcess(0x100000u, 0, *((_DWORD *)this + 6));
    *((_QWORD *)this + 4) = v18;
    if ( !v18 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
  }
  *(struct _FILETIME *)((char *)this + 84) = GetCurrentFileTime();
  *((_QWORD *)this + 87) = LoadServices();
  ConfigurationManager = CreateConfigurationManager();
  v24 = ConfigurationManager;
  if ( ConfigurationManager )
    (*(void (__fastcall **)(struct IMsiConfigurationManager *))(*(_QWORD *)ConfigurationManager + 8LL))(ConfigurationManager);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v24);
  return this;
}

```

## disassembly

```asm
0x1801cf58c  mov     [rsp-8+arg_8], rbx
0x1801cf591  mov     [rsp-8+arg_18], r9d
0x1801cf596  push    rbp
0x1801cf597  push    rsi
0x1801cf598  push    rdi
0x1801cf599  push    r12
0x1801cf59b  push    r13
0x1801cf59d  push    r14
0x1801cf59f  push    r15
0x1801cf5a1  lea     rbp, [rsp-1Fh]
0x1801cf5a6  sub     rsp, 90h
0x1801cf5ad  lea     rax, ??_7CMsiTransaction@@6B@; const CMsiTransaction::`vftable'
0x1801cf5b4  mov     rbx, rcx
0x1801cf5b7  mov     [rcx], rax
0x1801cf5ba  mov     r15d, r8d
0x1801cf5bd  add     rcx, 8; this
0x1801cf5c1  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801cf5c6  xor     r13d, r13d
0x1801cf5c9  mov     [rbx+10h], r15d
0x1801cf5cd  mov     [rbx+14h], r13d
0x1801cf5d1  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801cf5d8  mov     [rbx+20h], r13
0x1801cf5dc  lea     rsi, [rbx+18h]
0x1801cf5e0  mov     [rsi], r13d
0x1801cf5e3  lea     r12, [rbx+60h]
0x1801cf5e7  mov     [rbx+28h], r13
0x1801cf5eb  mov     [rbx+30h], r13
0x1801cf5ef  mov     [rbx+38h], r13
0x1801cf5f3  mov     [rbx+40h], r13
0x1801cf5f7  mov     [rbx+48h], r13
0x1801cf5fb  mov     [r12], rax
0x1801cf5ff  mov     [rbx+68h], r13b
0x1801cf603  mov     [rbx+6Ch], r13d
0x1801cf607  mov     [rbx+70h], r13
0x1801cf60b  mov     [rbx+78h], r13b
0x1801cf60f  mov     [rbx+7Ch], r13
0x1801cf613  mov     [rbx+94h], r13
0x1801cf61a  mov     [rbx+9Ch], r13
0x1801cf621  mov     [rbx+2B0h], r13
0x1801cf628  mov     [rbx+2C0h], r13
0x1801cf62f  mov     [rbx+2C8h], r13
0x1801cf636  mov     [rbx+2D0h], r13
0x1801cf63d  mov     [rbx+2D8h], r13
0x1801cf644  mov     [rbx+2F8h], r13
0x1801cf64b  mov     [rbx+300h], r13
0x1801cf652  mov     [rbx+308h], r13d
0x1801cf659  mov     [rbx+310h], r13
0x1801cf660  mov     [rbx+318h], r13
0x1801cf667  mov     [rbx+320h], r13
0x1801cf66e  mov     [rbx+328h], r13
0x1801cf675  mov     [rbx+330h], r13
0x1801cf67c  mov     [rbx+338h], r13
0x1801cf683  mov     [rbx+340h], r13
0x1801cf68a  mov     [rbx+348h], r13w
0x1801cf692  call    cs:__imp_GetTickCount
0x1801cf699  nop     dword ptr [rax+rax+00h]
0x1801cf69e  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801cf6a5  mov     [rbp+4Fh+Seed], eax
0x1801cf6a8  jz      short loc_1801CF6E3
0x1801cf6aa  lea     rax, aNull_0; "(NULL)"
0x1801cf6b1  xor     edx, edx; unsigned __int16
0x1801cf6b3  mov     [rsp+0C0h+var_78], rax; char *
0x1801cf6b8  lea     r9, aBeginningMulti; "Beginning Multi-Package transaction."
0x1801cf6bf  mov     [rsp+0C0h+var_80], rax; char *
0x1801cf6c4  xor     r8d, r8d; int
0x1801cf6c7  mov     [rsp+0C0h+var_88], rax; char *
0x1801cf6cc  mov     [rsp+0C0h+var_90], rax; char *
0x1801cf6d1  lea     ecx, [rdx+0Ah]; int
0x1801cf6d4  mov     [rsp+0C0h+var_98], rax; char *
0x1801cf6d9  mov     [rsp+0C0h+var_A0], rax; char *
0x1801cf6de  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801cf6e3  lock inc dword ptr [rbx+7Ch]
0x1801cf6e7  xorps   xmm0, xmm0
0x1801cf6ea  mov     [rbx+84h], r13b
0x1801cf6f1  xor     eax, eax
0x1801cf6f3  mov     [rbx+0A4h], r13w
0x1801cf6fb  movups  xmmword ptr [rbp+4Fh+EventAttributes.nLength], xmm0
0x1801cf6ff  mov     qword ptr [rbp+4Fh+EventAttributes.bInheritHandle], rax
0x1801cf703  lea     rdx, [rbp+4Fh+pExceptionObject]
0x1801cf707  xor     r9d, r9d
0x1801cf70a  mov     [rbp+4Fh+EventAttributes.nLength], 18h
0x1801cf711  xor     r8d, r8d
0x1801cf714  mov     [rbp+4Fh+EventAttributes.bInheritHandle], r13d
0x1801cf718  lea     rcx, [rbp+4Fh+EventAttributes.lpSecurityDescriptor]
0x1801cf71c  mov     [rbp+4Fh+pExceptionObject], r13d
0x1801cf720  call    ?GetSecureSecurityDescriptor@@YAKPEAPEADPEAIW4Bool@@_N@Z; GetSecureSecurityDescriptor(char * *,uint *,Bool,bool)
0x1801cf725  test    eax, eax
0x1801cf727  jz      short loc_1801CF73D
0x1801cf729  lea     rdx, _TI1K; pThrowInfo
0x1801cf730  mov     [rbp+4Fh+pExceptionObject], eax
0x1801cf733  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf737  call    _CxxThrowException_0
0x1801cf73d  mov     r14d, r13d
0x1801cf740  mov     edi, r13d
0x1801cf743  cmp     edi, 0FFFFh
0x1801cf749  jge     loc_1801CF8DD
0x1801cf74f  lea     rcx, [rbp+4Fh+Seed]; Seed
0x1801cf753  call    cs:__imp_RtlRandomEx
0x1801cf75a  nop     dword ptr [rax+rax+00h]
0x1801cf75f  mov     rcx, [rbp+4Fh+arg_20]; unsigned __int16 *
0x1801cf763  lea     r8, aGlobalMsiU; "Global\\MSI%u"
0x1801cf76a  mov     r9d, eax
0x1801cf76d  mov     eax, 80808081h
0x1801cf772  mul     r9d
0x1801cf775  shr     edx, 7
0x1801cf778  imul    eax, edx, 0FFh
0x1801cf77e  mov     edx, 104h; unsigned __int64
0x1801cf783  sub     r9d, eax
0x1801cf786  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801cf78b  test    eax, eax
0x1801cf78d  js      loc_1801CF903
0x1801cf793  mov     rdx, [rbp+4Fh+arg_20]
0x1801cf797  mov     rcx, r12
0x1801cf79a  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801cf79f  mov     dl, 1; bool
0x1801cf7a1  lea     rcx, [rbp+4Fh+var_58]; this
0x1801cf7a5  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801cf7aa  mov     rcx, [r12]
0x1801cf7ae  mov     rax, [rcx]
0x1801cf7b1  mov     rax, [rax+50h]
0x1801cf7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf7ba  mov     r9, rax; lpName
0x1801cf7bd  lea     rcx, [rbp+4Fh+EventAttributes]; lpEventAttributes
0x1801cf7c1  xor     r8d, r8d; bInitialState
0x1801cf7c4  xor     edx, edx; bManualReset
0x1801cf7c6  call    cs:__imp_CreateEventW
0x1801cf7cd  nop     dword ptr [rax+rax+00h]
0x1801cf7d2  mov     [rbx+40h], rax
0x1801cf7d6  call    cs:__imp_GetLastError
0x1801cf7dd  nop     dword ptr [rax+rax+00h]
0x1801cf7e2  lea     rcx, [rbp+4Fh+var_58]; this
0x1801cf7e6  mov     r13d, eax
0x1801cf7e9  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801cf7ee  mov     rcx, [rbx+40h]; hObject
0x1801cf7f2  lea     rdx, [rcx-1]
0x1801cf7f6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801cf7fa  ja      loc_1801CF8A6
0x1801cf800  cmp     r13d, 0B7h
0x1801cf807  jnz     short loc_1801CF821
0x1801cf809  call    cs:__imp_CloseHandle
0x1801cf810  nop     dword ptr [rax+rax+00h]
0x1801cf815  xor     r13d, r13d
0x1801cf818  mov     [rbx+40h], r13
0x1801cf81c  jmp     loc_1801CF8A6
0x1801cf821  mov     rdx, r12; struct MsiString *
0x1801cf824  lea     rcx, [rbp+4Fh+var_60]; this
0x1801cf828  call    ??0MsiString@@QEAA@AEBV0@@Z; MsiString::MsiString(MsiString const &)
0x1801cf82d  lea     rdx, aEt_0; "ET"
0x1801cf834  lea     rcx, [rbp+4Fh+var_60]
0x1801cf838  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x1801cf83d  mov     rcx, [rbp+4Fh+var_60]
0x1801cf841  mov     rax, [rcx]
0x1801cf844  mov     rax, [rax+50h]
0x1801cf848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf84d  xor     r8d, r8d; bInitialState
0x1801cf850  lea     rcx, [rbp+4Fh+EventAttributes]; lpEventAttributes
0x1801cf854  mov     r9, rax; lpName
0x1801cf857  lea     edx, [r8+1]; bManualReset
0x1801cf85b  call    cs:__imp_CreateEventW
0x1801cf862  nop     dword ptr [rax+rax+00h]
0x1801cf867  mov     [rbx+48h], rax
0x1801cf86b  inc     rax
0x1801cf86e  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801cf874  jnz     short loc_1801CF8CD
0x1801cf876  mov     rcx, [rbx+40h]; hObject
0x1801cf87a  call    cs:__imp_CloseHandle
0x1801cf881  nop     dword ptr [rax+rax+00h]
0x1801cf886  xor     r13d, r13d
0x1801cf889  mov     [rbx+40h], r13
0x1801cf88d  cmp     r14d, 3
0x1801cf891  ja      short loc_1801CF8AD
0x1801cf893  mov     rcx, [rbp+4Fh+var_60]
0x1801cf897  inc     r14d
0x1801cf89a  mov     rax, [rcx]
0x1801cf89d  mov     rax, [rax+10h]
0x1801cf8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf8a6  inc     edi
0x1801cf8a8  jmp     loc_1801CF743
0x1801cf8ad  call    cs:__imp_GetLastError
0x1801cf8b4  nop     dword ptr [rax+rax+00h]
0x1801cf8b9  lea     rdx, _TI1K; pThrowInfo
0x1801cf8c0  mov     [rbp+4Fh+pExceptionObject], eax
0x1801cf8c3  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf8c7  call    _CxxThrowException_0
0x1801cf8cd  mov     rcx, [rbp+4Fh+var_60]
0x1801cf8d1  mov     rax, [rcx]
0x1801cf8d4  mov     rax, [rax+10h]
0x1801cf8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf8dd  mov     r8d, [rbp+4Fh+arg_18]; unsigned int
0x1801cf8e1  xor     edx, edx; bool
0x1801cf8e3  mov     rcx, rbx; this
0x1801cf8e6  call    ?SetUserToken@CMsiTransaction@@QEAAI_NK@Z; CMsiTransaction::SetUserToken(bool,ulong)
0x1801cf8eb  test    eax, eax
0x1801cf8ed  jz      short loc_1801CF91B
0x1801cf8ef  lea     rdx, _TI1K; pThrowInfo
0x1801cf8f6  mov     [rbp+4Fh+pExceptionObject], eax
0x1801cf8f9  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf8fd  call    _CxxThrowException_0
0x1801cf903  lea     rdx, _TI1J; pThrowInfo
0x1801cf90a  mov     [rbp+4Fh+pExceptionObject], 57h ; 'W'
0x1801cf911  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf915  call    _CxxThrowException_0
0x1801cf91b  xor     edx, edx; void **
0x1801cf91d  mov     rcx, rsi; unsigned int *
0x1801cf920  call    ?GetCallerInfo@CMsiTransaction@@SAKPEAKPEAPEAX@Z; CMsiTransaction::GetCallerInfo(ulong *,void * *)
0x1801cf925  test    eax, eax
0x1801cf927  jz      short loc_1801CF93D
0x1801cf929  lea     rdx, _TI1K; pThrowInfo
0x1801cf930  mov     [rbp+4Fh+pExceptionObject], eax
0x1801cf933  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf937  call    _CxxThrowException_0
0x1801cf93d  test    r15d, r15d
0x1801cf940  jns     short loc_1801CF981
0x1801cf942  mov     r8d, [rsi]; dwProcessId
0x1801cf945  xor     edx, edx; bInheritHandle
0x1801cf947  mov     ecx, 100000h; dwDesiredAccess
0x1801cf94c  call    cs:__imp_OpenProcess
0x1801cf953  nop     dword ptr [rax+rax+00h]
0x1801cf958  mov     [rbx+20h], rax
0x1801cf95c  test    rax, rax
0x1801cf95f  jnz     short loc_1801CF981
0x1801cf961  call    cs:__imp_GetLastError
0x1801cf968  nop     dword ptr [rax+rax+00h]
0x1801cf96d  lea     rdx, _TI1K; pThrowInfo
0x1801cf974  mov     [rbp+4Fh+pExceptionObject], eax
0x1801cf977  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801cf97b  call    _CxxThrowException_0
0x1801cf981  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x1801cf986  mov     [rbx+54h], rax
0x1801cf98a  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x1801cf98f  mov     [rbx+2B8h], rax
0x1801cf996  call    ?CreateConfigurationManager@@YAPEAVIMsiConfigurationManager@@XZ; CreateConfigurationManager(void)
0x1801cf99b  mov     [rbp+4Fh+var_58], rax
0x1801cf99f  mov     rdx, rax
0x1801cf9a2  test    rax, rax
0x1801cf9a5  jz      short loc_1801CF9B6
0x1801cf9a7  mov     rcx, [rax]
0x1801cf9aa  mov     rax, [rcx+8]
0x1801cf9ae  mov     rcx, rdx
0x1801cf9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf9b6  lea     rcx, [rbp+4Fh+var_58]
0x1801cf9ba  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801cf9bf  mov     rax, rbx
0x1801cf9c2  mov     rbx, [rsp+0C0h+arg_8]
0x1801cf9ca  add     rsp, 90h
0x1801cf9d1  pop     r15
0x1801cf9d3  pop     r14
0x1801cf9d5  pop     r13
0x1801cf9d7  pop     r12
0x1801cf9d9  pop     rdi
0x1801cf9da  pop     rsi
0x1801cf9db  pop     rbp
0x1801cf9dc  retn
```
