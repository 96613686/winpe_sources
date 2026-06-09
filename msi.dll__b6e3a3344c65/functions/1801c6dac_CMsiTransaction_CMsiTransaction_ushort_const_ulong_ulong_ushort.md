# CMsiTransaction::CMsiTransaction(ushort const *,ulong,ulong,ushort *)

- ea: `0x1801c6dac`
- end: `0x1801c71be`
- name: `??0CMsiTransaction@@IEAA@PEBGKKPEAG@Z`
- size: `1042`
- prototype: `CMsiTransaction *__usercall@<rax>(CMsiTransaction *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18011105c`

## callees

- `0x18000a150`
- `0x18001e9f8`
- `0x180022120`
- `0x180025904`
- `0x18004295c`
- `0x180066074`
- `0x180068680`
- `0x1800a5fc4`
- `0x1800c2854`
- `0x1800cc4dc`
- `0x1800cddb0`
- `0x180127748`
- `0x180134e3c`
- `0x180143d60`
- `0x1801c6dac`
- `0x1801cbdd4`
- `0x18025a9f6`
- `0x18025c010`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x1801c6f6d`
- `ntdll!RtlRandomEx` at `0x1801c6f6d`
- `KERNEL32!CloseHandle` at `0x1801c7011`
- `KERNEL32!CloseHandle` at `0x1801c7073`
- `KERNEL32!CloseHandle` at `0x1801c7011`
- `KERNEL32!CloseHandle` at `0x1801c7073`
- `KERNEL32!GetTickCount` at `0x1801c6eb2`
- `KERNEL32!GetTickCount` at `0x1801c6eb2`
- `KERNEL32!GetLastError` at `0x1801c6fe4`
- `KERNEL32!GetLastError` at `0x1801c70a0`
- `KERNEL32!GetLastError` at `0x1801c7148`
- `KERNEL32!GetLastError` at `0x1801c6fe4`
- `KERNEL32!GetLastError` at `0x1801c70a0`
- `KERNEL32!GetLastError` at `0x1801c7148`
- `KERNEL32!CreateEventW` at `0x1801c6fda`
- `KERNEL32!CreateEventW` at `0x1801c705a`
- `KERNEL32!CreateEventW` at `0x1801c6fda`
- `KERNEL32!CreateEventW` at `0x1801c705a`
- `KERNEL32!OpenProcess` at `0x1801c7139`
- `KERNEL32!OpenProcess` at `0x1801c7139`

## string_xrefs

- `0x1801c6f77`: `Global\MSI%u`

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
0x1801c6dac  mov     [rsp-8+arg_8], rbx
0x1801c6db1  mov     [rsp-8+arg_18], r9d
0x1801c6db6  push    rbp
0x1801c6db7  push    rsi
0x1801c6db8  push    rdi
0x1801c6db9  push    r12
0x1801c6dbb  push    r13
0x1801c6dbd  push    r14
0x1801c6dbf  push    r15
0x1801c6dc1  lea     rbp, [rsp-1Fh]
0x1801c6dc6  sub     rsp, 90h
0x1801c6dcd  lea     rax, ??_7CMsiTransaction@@6B@; const CMsiTransaction::`vftable'
0x1801c6dd4  mov     rbx, rcx
0x1801c6dd7  mov     [rcx], rax
0x1801c6dda  mov     r15d, r8d
0x1801c6ddd  add     rcx, 8; this
0x1801c6de1  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801c6de6  xor     r13d, r13d
0x1801c6de9  mov     [rbx+10h], r15d
0x1801c6ded  mov     [rbx+14h], r13d
0x1801c6df1  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801c6df8  mov     [rbx+20h], r13
0x1801c6dfc  lea     rsi, [rbx+18h]
0x1801c6e00  mov     [rsi], r13d
0x1801c6e03  lea     r12, [rbx+60h]
0x1801c6e07  mov     [rbx+28h], r13
0x1801c6e0b  mov     [rbx+30h], r13
0x1801c6e0f  mov     [rbx+38h], r13
0x1801c6e13  mov     [rbx+40h], r13
0x1801c6e17  mov     [rbx+48h], r13
0x1801c6e1b  mov     [r12], rax
0x1801c6e1f  mov     [rbx+68h], r13b
0x1801c6e23  mov     [rbx+6Ch], r13d
0x1801c6e27  mov     [rbx+70h], r13
0x1801c6e2b  mov     [rbx+78h], r13b
0x1801c6e2f  mov     [rbx+7Ch], r13
0x1801c6e33  mov     [rbx+94h], r13
0x1801c6e3a  mov     [rbx+9Ch], r13
0x1801c6e41  mov     [rbx+2B0h], r13
0x1801c6e48  mov     [rbx+2C0h], r13
0x1801c6e4f  mov     [rbx+2C8h], r13
0x1801c6e56  mov     [rbx+2D0h], r13
0x1801c6e5d  mov     [rbx+2D8h], r13
0x1801c6e64  mov     [rbx+2F8h], r13
0x1801c6e6b  mov     [rbx+300h], r13
0x1801c6e72  mov     [rbx+308h], r13d
0x1801c6e79  mov     [rbx+310h], r13
0x1801c6e80  mov     [rbx+318h], r13
0x1801c6e87  mov     [rbx+320h], r13
0x1801c6e8e  mov     [rbx+328h], r13
0x1801c6e95  mov     [rbx+330h], r13
0x1801c6e9c  mov     [rbx+338h], r13
0x1801c6ea3  mov     [rbx+340h], r13
0x1801c6eaa  mov     [rbx+348h], r13w
0x1801c6eb2  call    cs:__imp_GetTickCount
0x1801c6eb8  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801c6ebf  mov     [rbp+4Fh+Seed], eax
0x1801c6ec2  jz      short loc_1801C6EFD
0x1801c6ec4  lea     rax, aNull_0; "(NULL)"
0x1801c6ecb  xor     edx, edx; unsigned __int16
0x1801c6ecd  mov     [rsp+0C0h+var_78], rax; char *
0x1801c6ed2  lea     r9, aBeginningMulti; "Beginning Multi-Package transaction."
0x1801c6ed9  mov     [rsp+0C0h+var_80], rax; char *
0x1801c6ede  xor     r8d, r8d; int
0x1801c6ee1  mov     [rsp+0C0h+var_88], rax; char *
0x1801c6ee6  mov     [rsp+0C0h+var_90], rax; char *
0x1801c6eeb  lea     ecx, [rdx+0Ah]; int
0x1801c6eee  mov     [rsp+0C0h+var_98], rax; char *
0x1801c6ef3  mov     [rsp+0C0h+var_A0], rax; char *
0x1801c6ef8  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x1801c6efd  lock inc dword ptr [rbx+7Ch]
0x1801c6f01  xorps   xmm0, xmm0
0x1801c6f04  mov     [rbx+84h], r13b
0x1801c6f0b  xor     eax, eax
0x1801c6f0d  mov     [rbx+0A4h], r13w
0x1801c6f15  movups  xmmword ptr [rbp+4Fh+EventAttributes.nLength], xmm0
0x1801c6f19  mov     qword ptr [rbp+4Fh+EventAttributes.bInheritHandle], rax
0x1801c6f1d  lea     rdx, [rbp+4Fh+pExceptionObject]
0x1801c6f21  xor     r9d, r9d
0x1801c6f24  mov     [rbp+4Fh+EventAttributes.nLength], 18h
0x1801c6f2b  xor     r8d, r8d
0x1801c6f2e  mov     [rbp+4Fh+EventAttributes.bInheritHandle], r13d
0x1801c6f32  lea     rcx, [rbp+4Fh+EventAttributes.lpSecurityDescriptor]
0x1801c6f36  mov     [rbp+4Fh+pExceptionObject], r13d
0x1801c6f3a  call    ?GetSecureSecurityDescriptor@@YAKPEAPEADPEAIW4Bool@@_N@Z; GetSecureSecurityDescriptor(char * *,uint *,Bool,bool)
0x1801c6f3f  test    eax, eax
0x1801c6f41  jz      short loc_1801C6F57
0x1801c6f43  lea     rdx, _TI1K; pThrowInfo
0x1801c6f4a  mov     [rbp+4Fh+pExceptionObject], eax
0x1801c6f4d  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c6f51  call    _CxxThrowException_0
0x1801c6f57  mov     r14d, r13d
0x1801c6f5a  mov     edi, r13d
0x1801c6f5d  cmp     edi, 0FFFFh
0x1801c6f63  jge     loc_1801C70CA
0x1801c6f69  lea     rcx, [rbp+4Fh+Seed]; Seed
0x1801c6f6d  call    cs:__imp_RtlRandomEx
0x1801c6f73  mov     rcx, [rbp+4Fh+arg_20]; unsigned __int16 *
0x1801c6f77  lea     r8, aGlobalMsiU; "Global\\MSI%u"
0x1801c6f7e  mov     r9d, eax
0x1801c6f81  mov     eax, 80808081h
0x1801c6f86  mul     r9d
0x1801c6f89  shr     edx, 7
0x1801c6f8c  imul    eax, edx, 0FFh
0x1801c6f92  mov     edx, 104h; unsigned __int64
0x1801c6f97  sub     r9d, eax
0x1801c6f9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801c6f9f  test    eax, eax
0x1801c6fa1  js      loc_1801C70F0
0x1801c6fa7  mov     rdx, [rbp+4Fh+arg_20]
0x1801c6fab  mov     rcx, r12
0x1801c6fae  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801c6fb3  mov     dl, 1; bool
0x1801c6fb5  lea     rcx, [rbp+4Fh+var_58]; this
0x1801c6fb9  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801c6fbe  mov     rcx, [r12]
0x1801c6fc2  mov     rax, [rcx]
0x1801c6fc5  mov     rax, [rax+50h]
0x1801c6fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c6fce  mov     r9, rax; lpName
0x1801c6fd1  lea     rcx, [rbp+4Fh+EventAttributes]; lpEventAttributes
0x1801c6fd5  xor     r8d, r8d; bInitialState
0x1801c6fd8  xor     edx, edx; bManualReset
0x1801c6fda  call    cs:__imp_CreateEventW
0x1801c6fe0  mov     [rbx+40h], rax
0x1801c6fe4  call    cs:__imp_GetLastError
0x1801c6fea  lea     rcx, [rbp+4Fh+var_58]; this
0x1801c6fee  mov     r13d, eax
0x1801c6ff1  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801c6ff6  mov     rcx, [rbx+40h]; hObject
0x1801c6ffa  lea     rdx, [rcx-1]
0x1801c6ffe  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801c7002  ja      loc_1801C7099
0x1801c7008  cmp     r13d, 0B7h
0x1801c700f  jnz     short loc_1801C7020
0x1801c7011  call    cs:__imp_CloseHandle
0x1801c7017  xor     r13d, r13d
0x1801c701a  mov     [rbx+40h], r13
0x1801c701e  jmp     short loc_1801C7099
0x1801c7020  mov     rdx, r12; struct MsiString *
0x1801c7023  lea     rcx, [rbp+4Fh+var_60]; this
0x1801c7027  call    ??0MsiString@@QEAA@AEBV0@@Z; MsiString::MsiString(MsiString const &)
0x1801c702c  lea     rdx, aEt_0; "ET"
0x1801c7033  lea     rcx, [rbp+4Fh+var_60]
0x1801c7037  call    ??YMsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator+=(ushort const *)
0x1801c703c  mov     rcx, [rbp+4Fh+var_60]
0x1801c7040  mov     rax, [rcx]
0x1801c7043  mov     rax, [rax+50h]
0x1801c7047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c704c  xor     r8d, r8d; bInitialState
0x1801c704f  lea     rcx, [rbp+4Fh+EventAttributes]; lpEventAttributes
0x1801c7053  mov     r9, rax; lpName
0x1801c7056  lea     edx, [r8+1]; bManualReset
0x1801c705a  call    cs:__imp_CreateEventW
0x1801c7060  mov     [rbx+48h], rax
0x1801c7064  inc     rax
0x1801c7067  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801c706d  jnz     short loc_1801C70BA
0x1801c706f  mov     rcx, [rbx+40h]; hObject
0x1801c7073  call    cs:__imp_CloseHandle
0x1801c7079  xor     r13d, r13d
0x1801c707c  mov     [rbx+40h], r13
0x1801c7080  cmp     r14d, 3
0x1801c7084  ja      short loc_1801C70A0
0x1801c7086  mov     rcx, [rbp+4Fh+var_60]
0x1801c708a  inc     r14d
0x1801c708d  mov     rax, [rcx]
0x1801c7090  mov     rax, [rax+10h]
0x1801c7094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7099  inc     edi
0x1801c709b  jmp     loc_1801C6F5D
0x1801c70a0  call    cs:__imp_GetLastError
0x1801c70a6  lea     rdx, _TI1K; pThrowInfo
0x1801c70ad  mov     [rbp+4Fh+pExceptionObject], eax
0x1801c70b0  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c70b4  call    _CxxThrowException_0
0x1801c70ba  mov     rcx, [rbp+4Fh+var_60]
0x1801c70be  mov     rax, [rcx]
0x1801c70c1  mov     rax, [rax+10h]
0x1801c70c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c70ca  mov     r8d, [rbp+4Fh+arg_18]; unsigned int
0x1801c70ce  xor     edx, edx; bool
0x1801c70d0  mov     rcx, rbx; this
0x1801c70d3  call    ?SetUserToken@CMsiTransaction@@QEAAI_NK@Z; CMsiTransaction::SetUserToken(bool,ulong)
0x1801c70d8  test    eax, eax
0x1801c70da  jz      short loc_1801C7108
0x1801c70dc  lea     rdx, _TI1K; pThrowInfo
0x1801c70e3  mov     [rbp+4Fh+pExceptionObject], eax
0x1801c70e6  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c70ea  call    _CxxThrowException_0
0x1801c70f0  lea     rdx, _TI1J; pThrowInfo
0x1801c70f7  mov     [rbp+4Fh+pExceptionObject], 57h ; 'W'
0x1801c70fe  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c7102  call    _CxxThrowException_0
0x1801c7108  xor     edx, edx; void **
0x1801c710a  mov     rcx, rsi; unsigned int *
0x1801c710d  call    ?GetCallerInfo@CMsiTransaction@@SAKPEAKPEAPEAX@Z; CMsiTransaction::GetCallerInfo(ulong *,void * *)
0x1801c7112  test    eax, eax
0x1801c7114  jz      short loc_1801C712A
0x1801c7116  lea     rdx, _TI1K; pThrowInfo
0x1801c711d  mov     [rbp+4Fh+pExceptionObject], eax
0x1801c7120  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c7124  call    _CxxThrowException_0
0x1801c712a  test    r15d, r15d
0x1801c712d  jns     short loc_1801C7162
0x1801c712f  mov     r8d, [rsi]; dwProcessId
0x1801c7132  xor     edx, edx; bInheritHandle
0x1801c7134  mov     ecx, 100000h; dwDesiredAccess
0x1801c7139  call    cs:__imp_OpenProcess
0x1801c713f  mov     [rbx+20h], rax
0x1801c7143  test    rax, rax
0x1801c7146  jnz     short loc_1801C7162
0x1801c7148  call    cs:__imp_GetLastError
0x1801c714e  lea     rdx, _TI1K; pThrowInfo
0x1801c7155  mov     [rbp+4Fh+pExceptionObject], eax
0x1801c7158  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x1801c715c  call    _CxxThrowException_0
0x1801c7162  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x1801c7167  mov     [rbx+54h], rax
0x1801c716b  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x1801c7170  mov     [rbx+2B8h], rax
0x1801c7177  call    ?CreateConfigurationManager@@YAPEAVIMsiConfigurationManager@@XZ; CreateConfigurationManager(void)
0x1801c717c  mov     [rbp+4Fh+var_58], rax
0x1801c7180  mov     rdx, rax
0x1801c7183  test    rax, rax
0x1801c7186  jz      short loc_1801C7197
0x1801c7188  mov     rcx, [rax]
0x1801c718b  mov     rax, [rcx+8]
0x1801c718f  mov     rcx, rdx
0x1801c7192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7197  lea     rcx, [rbp+4Fh+var_58]
0x1801c719b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801c71a0  mov     rax, rbx
0x1801c71a3  mov     rbx, [rsp+0C0h+arg_8]
0x1801c71ab  add     rsp, 90h
0x1801c71b2  pop     r15
0x1801c71b4  pop     r14
0x1801c71b6  pop     r13
0x1801c71b8  pop     r12
0x1801c71ba  pop     rdi
0x1801c71bb  pop     rsi
0x1801c71bc  pop     rbp
0x1801c71bd  retn
```
