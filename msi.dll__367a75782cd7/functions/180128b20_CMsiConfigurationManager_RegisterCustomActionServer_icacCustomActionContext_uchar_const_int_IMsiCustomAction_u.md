# CMsiConfigurationManager::RegisterCustomActionServer(icacCustomActionContext *,uchar const *,int,IMsiCustomAction *,ulong *,IMsiRemoteAPI * *,ulong *)

- ea: `0x180128b20`
- end: `0x180128f76`
- name: `?RegisterCustomActionServer@CMsiConfigurationManager@@UEAAIPEAW4icacCustomActionContext@@PEBEHPEAUIMsiCustomAction@@PEAKPEAPEAUIMsiRemoteAPI@@3@Z`
- size: `1110`
- prototype: `__int64 __fastcall(CMsiConfigurationManager *this, enum icacCustomActionContext *, const unsigned __int8 *, int, struct IMsiCustomAction *, unsigned int *, struct IMsiRemoteAPI **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x18000a150`
- `0x180083434`
- `0x1800a9d48`
- `0x180128b20`
- `0x180146568`
- `0x18015238c`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180128bf8`
- `ADVAPI32!OpenThreadToken` at `0x180128bf8`
- `KERNEL32!CloseHandle` at `0x180128c11`
- `KERNEL32!CloseHandle` at `0x180128c11`
- `KERNEL32!LeaveCriticalSection` at `0x180128caf`
- `KERNEL32!LeaveCriticalSection` at `0x180128e6c`
- `KERNEL32!LeaveCriticalSection` at `0x180128ed2`
- `KERNEL32!LeaveCriticalSection` at `0x180128f41`
- `KERNEL32!LeaveCriticalSection` at `0x180128caf`
- `KERNEL32!LeaveCriticalSection` at `0x180128e6c`
- `KERNEL32!LeaveCriticalSection` at `0x180128ed2`
- `KERNEL32!LeaveCriticalSection` at `0x180128f41`
- `KERNEL32!EnterCriticalSection` at `0x180128b95`
- `KERNEL32!EnterCriticalSection` at `0x180128b95`
- `KERNEL32!GetCurrentThread` at `0x180128be4`
- `KERNEL32!GetCurrentThread` at `0x180128be4`
- `KERNEL32!SetEvent` at `0x180128ec9`
- `KERNEL32!SetEvent` at `0x180128ec9`

## string_xrefs

- `0x180128d7a`: `32bit Impersonated`
- `0x180128d71`: `64bit Impersonated`
- `0x180128dc4`: `32bit AIS Impersonated`
- `0x180128dbb`: `64bit AIS Impersonated`

## pseudocode

```c
__int64 __fastcall CMsiConfigurationManager::RegisterCustomActionServer(
        CMsiConfigurationManager *this,
        enum icacCustomActionContext *a2,
        const unsigned __int8 *a3,
        int a4,
        struct IMsiCustomAction *a5,
        unsigned int *a6,
        struct IMsiRemoteAPI **a7,
        unsigned int *a8)
{
  bool v12; // bl
  struct IMsiCustomAction *v13; // r12
  HANDLE CurrentThread; // rax
  unsigned int v15; // ecx
  unsigned int v16; // eax
  const char *v17; // r9
  unsigned int v18; // ebx
  int i; // edx
  const char *v20; // r9
  __int64 v21; // rcx
  _DWORD *v22; // r15
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  const char *v27; // rcx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  struct IMsiRemoteAPI **v31; // r9
  int v33; // eax
  unsigned int v34; // [rsp+50h] [rbp-28h]
  void *v35; // [rsp+58h] [rbp-20h]
  _BYTE v36[8]; // [rsp+60h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-10h] BYREF
  int v38; // [rsp+C8h] [rbp+50h] BYREF

  CCoImpersonate::CCoImpersonate((CCoImpersonate *)v36, (bool)a2);
  v12 = 0;
  if ( !a2 || !a3 || (v13 = a5) == 0 || !a6 || !a7 || !a8 )
  {
    CCoImpersonate::~CCoImpersonate((CCoImpersonate *)v36);
    return 87;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  if ( *((_QWORD *)this + 18) && !*((_DWORD *)this + 68) )
  {
    v38 = 0;
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, int *))RPCRT4::I_RpcBindingInqLocalClientPID)(0, &v38)
      || v38 != *((_DWORD *)this + 70) )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = "Custom Action Server rejected - Unknown Process.";
        goto LABEL_79;
      }
      goto LABEL_80;
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v12 = IsLocalSystemToken(TokenHandle);
      CloseHandle(TokenHandle);
    }
    if ( *((_BYTE *)this + 284) )
      goto LABEL_24;
    v15 = *((_DWORD *)this + 62);
    if ( v12 )
    {
      if ( v15 <= 1 )
        goto LABEL_22;
      v16 = v15 - 6;
    }
    else
    {
      v16 = v15 - 2;
    }
    if ( v16 > 3 )
    {
      if ( *(_DWORD *)a2 != v15 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_28;
        v17 = "Custom Action Server rejected - Wrong Context";
        goto LABEL_27;
      }
LABEL_24:
      if ( a4 != 16 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_28;
        v17 = "Custom Action Server rejected - Invalid Cookie.";
LABEL_27:
        DebugString(10, 0, 0, v17, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v34, v35);
LABEL_28:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
        v18 = 5;
LABEL_64:
        CCoImpersonate::~CCoImpersonate((CCoImpersonate *)v36);
        return v18;
      }
      for ( i = 0; i < 16; ++i )
      {
        if ( a3[i] != *((_BYTE *)this + i + 232) )
        {
          if ( !g_dmDiagnosticMode )
            goto LABEL_80;
          v20 = "Custom Action Server rejected - Invalid Cookie.";
LABEL_79:
          DebugString(10, 0, 0, v20, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", v34, v35);
          goto LABEL_80;
        }
      }
      v21 = *((_QWORD *)this + 16);
      if ( !v21
        || (v22 = (_DWORD *)((char *)this + 272),
            (*(unsigned int (__fastcall **)(__int64, struct IMsiCustomAction *, GUID *, char *))(*(_QWORD *)v21 + 24LL))(
              v21,
              v13,
              &IID_IMsiCustomAction,
              (char *)this + 272)) )
      {
LABEL_63:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
        v18 = 1627;
        goto LABEL_64;
      }
      v23 = *((_DWORD *)this + 62);
      if ( v23 > 5 )
      {
        v28 = v23 - 6;
        if ( !v28 )
        {
          v27 = "32bit AIS Impersonated";
          goto LABEL_59;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v27 = "64bit AIS Impersonated";
          goto LABEL_59;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v27 = "32bit EEUI";
          goto LABEL_59;
        }
        if ( v30 == 1 )
        {
          v27 = "64bit EEUI";
          goto LABEL_59;
        }
      }
      else
      {
        if ( v23 == 5 )
        {
          v27 = "64bit Elevated Non-remapped";
          goto LABEL_59;
        }
        if ( !v23 )
        {
          v27 = "32bit Impersonated";
          goto LABEL_59;
        }
        v24 = v23 - 1;
        if ( !v24 )
        {
          v27 = "64bit Impersonated";
          goto LABEL_59;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          v27 = "32bit Elevated Remapped";
          goto LABEL_59;
        }
        v26 = v25 - 1;
        if ( !v26 )
        {
          v27 = "64bit Elevated Remapped";
          goto LABEL_59;
        }
        if ( v26 == 1 )
        {
          v27 = "32bit Elevated Non-remapped";
LABEL_59:
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              "Hello, I'm your %s custom action server.",
              v27,
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              v34,
              v35);
          v31 = a7;
          *a6 = *((_DWORD *)this + 66);
          *a8 = *((_DWORD *)this + 69);
          if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, GUID *, struct IMsiRemoteAPI **))(**((_QWORD **)this + 16)
                                                                                                + 40LL))(
                  *((_QWORD *)this + 16),
                  *((unsigned int *)this + 67),
                  &IID_IMsiRemoteAPI,
                  v31) )
          {
            if ( *((_BYTE *)this + 284) )
            {
              v33 = *((_DWORD *)this + 62);
              if ( v33 )
              {
                if ( v33 == 1 && ((*(_DWORD *)a2 - 3) & 0xFFFFFFFD) == 0 )
                  *(_DWORD *)a2 = 1;
              }
              else if ( ((*(_DWORD *)a2 - 2) & 0xFFFFFFFD) == 0 )
              {
                *(_DWORD *)a2 = 0;
              }
            }
            SetEvent(*((HANDLE *)this + 18));
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
            if ( v36[4] )
              StopImpersonateCore(1);
            return 0;
          }
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 16) + 32LL))(
            *((_QWORD *)this + 16),
            (unsigned int)*v22);
          *v22 = 0;
          goto LABEL_63;
        }
      }
      v27 = "Unknown";
      goto LABEL_59;
    }
LABEL_22:
    if ( !g_dmDiagnosticMode )
      goto LABEL_28;
    v17 = "Custom Action Server rejected - Mismatched Context.";
    goto LABEL_27;
  }
  if ( g_dmDiagnosticMode )
  {
    v20 = "Custom Action Server rejected - Invalid Context.";
    goto LABEL_79;
  }
LABEL_80:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  CCoImpersonate::~CCoImpersonate((CCoImpersonate *)v36);
  return 5;
}

```

## disassembly

```asm
0x180128b20  push    rbp
0x180128b22  push    rbx
0x180128b23  push    rsi
0x180128b24  push    rdi
0x180128b25  push    r12
0x180128b27  push    r13
0x180128b29  push    r14
0x180128b2b  push    r15
0x180128b2d  mov     rbp, rsp
0x180128b30  sub     rsp, 78h
0x180128b34  mov     rdi, rcx
0x180128b37  mov     r13d, r9d
0x180128b3a  lea     rcx, [rbp+var_18]; this
0x180128b3e  mov     r15, r8
0x180128b41  mov     rsi, rdx
0x180128b44  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x180128b49  xor     ebx, ebx
0x180128b4b  test    rsi, rsi
0x180128b4e  jz      loc_180128F57
0x180128b54  test    r15, r15
0x180128b57  jz      loc_180128F57
0x180128b5d  mov     r12, [rbp+arg_20]
0x180128b61  test    r12, r12
0x180128b64  jz      loc_180128F57
0x180128b6a  cmp     [rbp+arg_28], rbx
0x180128b6e  jz      loc_180128F57
0x180128b74  cmp     [rbp+arg_30], rbx
0x180128b78  jz      loc_180128F57
0x180128b7e  cmp     [rbp+arg_38], rbx
0x180128b85  jz      loc_180128F57
0x180128b8b  lea     r14, [rdi+0C0h]
0x180128b92  mov     rcx, r14; lpCriticalSection
0x180128b95  call    cs:__imp_EnterCriticalSection
0x180128b9b  cmp     [rdi+90h], rbx
0x180128ba2  jz      loc_180128EFD
0x180128ba8  cmp     [rdi+110h], ebx
0x180128bae  jnz     loc_180128EFD
0x180128bb4  mov     rax, cs:?I_RpcBindingInqLocalClientPID@RPCRT4@@3P6AJPEAXPEAK@ZEA; long (*RPCRT4::I_RpcBindingInqLocalClientPID)(void *,ulong *)
0x180128bbb  lea     rdx, [rbp+arg_8]
0x180128bbf  xor     ecx, ecx
0x180128bc1  mov     [rbp+arg_8], ebx
0x180128bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128bc9  test    eax, eax
0x180128bcb  jnz     loc_180128EEC
0x180128bd1  mov     eax, [rdi+118h]
0x180128bd7  cmp     [rbp+arg_8], eax
0x180128bda  jnz     loc_180128EEC
0x180128be0  mov     [rbp+TokenHandle], rbx
0x180128be4  call    cs:__imp_GetCurrentThread
0x180128bea  mov     rcx, rax; ThreadHandle
0x180128bed  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180128bf1  lea     edx, [rbx+8]; DesiredAccess
0x180128bf4  lea     r8d, [rbx+1]; OpenAsSelf
0x180128bf8  call    cs:__imp_OpenThreadToken
0x180128bfe  test    eax, eax
0x180128c00  jz      short loc_180128C17
0x180128c02  mov     rcx, [rbp+TokenHandle]; void *
0x180128c06  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180128c0b  mov     rcx, [rbp+TokenHandle]; hObject
0x180128c0f  mov     bl, al
0x180128c11  call    cs:__imp_CloseHandle
0x180128c17  cmp     byte ptr [rdi+11Ch], 0
0x180128c1e  jnz     short loc_180128C64
0x180128c20  mov     ecx, [rdi+0F8h]
0x180128c26  test    bl, bl
0x180128c28  jz      short loc_180128C34
0x180128c2a  cmp     ecx, 1
0x180128c2d  jbe     short loc_180128C52
0x180128c2f  lea     eax, [rcx-6]
0x180128c32  jmp     short loc_180128C37
0x180128c34  lea     eax, [rcx-2]
0x180128c37  cmp     eax, 3
0x180128c3a  jbe     short loc_180128C52
0x180128c3c  cmp     [rsi], ecx
0x180128c3e  jz      short loc_180128C64
0x180128c40  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180128c47  jz      short loc_180128CAC
0x180128c49  lea     r9, aCustomActionSe_8; "Custom Action Server rejected - Wrong C"...
0x180128c50  jmp     short loc_180128C7A
0x180128c52  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180128c59  jz      short loc_180128CAC
0x180128c5b  lea     r9, aCustomActionSe_0; "Custom Action Server rejected - Mismatc"...
0x180128c62  jmp     short loc_180128C7A
0x180128c64  cmp     r13d, 10h
0x180128c68  jz      short loc_180128CBF
0x180128c6a  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180128c71  jz      short loc_180128CAC
0x180128c73  lea     r9, aCustomActionSe_12; "Custom Action Server rejected - Invalid"...
0x180128c7a  lea     rax, aNull_0; "(NULL)"
0x180128c81  xor     edx, edx; unsigned __int16
0x180128c83  mov     [rsp+78h+var_30], rax; char *
0x180128c88  xor     r8d, r8d; int
0x180128c8b  mov     [rsp+78h+var_38], rax; char *
0x180128c90  mov     [rsp+78h+var_40], rax; char *
0x180128c95  mov     [rsp+78h+var_48], rax; char *
0x180128c9a  lea     ecx, [rdx+0Ah]; int
0x180128c9d  mov     [rsp+78h+var_50], rax; char *
0x180128ca2  mov     [rsp+78h+var_58], rax; char *
0x180128ca7  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180128cac  mov     rcx, r14; lpCriticalSection
0x180128caf  call    cs:__imp_LeaveCriticalSection
0x180128cb5  mov     ebx, 5
0x180128cba  jmp     loc_180128E77
0x180128cbf  xor     r13d, r13d
0x180128cc2  mov     edx, r13d
0x180128cc5  cmp     edx, 10h
0x180128cc8  jge     short loc_180128CF7
0x180128cca  movsxd  rcx, edx
0x180128ccd  mov     al, [rcx+rdi+0E8h]
0x180128cd4  cmp     [rcx+r15], al
0x180128cd8  jnz     short loc_180128CDE
0x180128cda  inc     edx
0x180128cdc  jmp     short loc_180128CC5
0x180128cde  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180128ce5  jz      loc_180128F3E
0x180128ceb  lea     r9, aCustomActionSe_12; "Custom Action Server rejected - Invalid"...
0x180128cf2  jmp     loc_180128F0C
0x180128cf7  mov     rcx, [rdi+80h]
0x180128cfe  test    rcx, rcx
0x180128d01  jz      loc_180128E69
0x180128d07  mov     rax, [rcx]
0x180128d0a  lea     r15, [rdi+110h]
0x180128d11  mov     r9, r15
0x180128d14  lea     r8, IID_IMsiCustomAction
0x180128d1b  mov     rdx, r12
0x180128d1e  mov     rax, [rax+18h]
0x180128d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128d27  test    eax, eax
0x180128d29  jnz     loc_180128E69
0x180128d2f  mov     ecx, [rdi+0F8h]
0x180128d35  lea     ebx, [rax+5]
0x180128d38  cmp     ecx, ebx
0x180128d3a  jg      short loc_180128D8C
0x180128d3c  jz      short loc_180128D83
0x180128d3e  test    ecx, ecx
0x180128d40  jz      short loc_180128D7A
0x180128d42  sub     ecx, 1
0x180128d45  jz      short loc_180128D71
0x180128d47  sub     ecx, 1
0x180128d4a  jz      short loc_180128D68
0x180128d4c  sub     ecx, 1
0x180128d4f  jz      short loc_180128D5F
0x180128d51  cmp     ecx, 1
0x180128d54  jnz     short loc_180128DA0
0x180128d56  lea     rcx, a32bitElevatedN; "32bit Elevated Non-remapped"
0x180128d5d  jmp     short loc_180128DCB
0x180128d5f  lea     rcx, a64bitElevatedR; "64bit Elevated Remapped"
0x180128d66  jmp     short loc_180128DCB
0x180128d68  lea     rcx, a32bitElevatedR; "32bit Elevated Remapped"
0x180128d6f  jmp     short loc_180128DCB
0x180128d71  lea     rcx, a64bitImpersona; "64bit Impersonated"
0x180128d78  jmp     short loc_180128DCB
0x180128d7a  lea     rcx, a32bitImpersona; "32bit Impersonated"
0x180128d81  jmp     short loc_180128DCB
0x180128d83  lea     rcx, a64bitElevatedN; "64bit Elevated Non-remapped"
0x180128d8a  jmp     short loc_180128DCB
0x180128d8c  sub     ecx, 6
0x180128d8f  jz      short loc_180128DC4
0x180128d91  sub     ecx, 1
0x180128d94  jz      short loc_180128DBB
0x180128d96  sub     ecx, 1
0x180128d99  jz      short loc_180128DB2
0x180128d9b  cmp     ecx, 1
0x180128d9e  jz      short loc_180128DA9
0x180128da0  lea     rcx, aUnknown_0; "Unknown"
0x180128da7  jmp     short loc_180128DCB
0x180128da9  lea     rcx, a64bitEeui; "64bit EEUI"
0x180128db0  jmp     short loc_180128DCB
0x180128db2  lea     rcx, a32bitEeui; "32bit EEUI"
0x180128db9  jmp     short loc_180128DCB
0x180128dbb  lea     rcx, a64bitAisImpers; "64bit AIS Impersonated"
0x180128dc2  jmp     short loc_180128DCB
0x180128dc4  lea     rcx, a32bitAisImpers; "32bit AIS Impersonated"
0x180128dcb  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180128dd2  jz      short loc_180128E0D
0x180128dd4  lea     rax, aNull_0; "(NULL)"
0x180128ddb  xor     edx, edx; unsigned __int16
0x180128ddd  mov     [rsp+78h+var_30], rax; char *
0x180128de2  lea     r9, aHelloIMYourSCu; "Hello, I'm your %s custom action server"...
0x180128de9  mov     [rsp+78h+var_38], rax; char *
0x180128dee  xor     r8d, r8d; int
0x180128df1  mov     [rsp+78h+var_40], rax; char *
0x180128df6  mov     [rsp+78h+var_48], rax; char *
0x180128dfb  mov     [rsp+78h+var_50], rax; char *
0x180128e00  mov     [rsp+78h+var_58], rcx; char *
0x180128e05  lea     ecx, [rdx+9]; int
0x180128e08  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180128e0d  mov     eax, [rdi+108h]
0x180128e13  lea     r8, IID_IMsiRemoteAPI
0x180128e1a  mov     rcx, [rbp+arg_28]
0x180128e1e  mov     r9, [rbp+arg_30]
0x180128e22  mov     [rcx], eax
0x180128e24  mov     eax, [rdi+114h]
0x180128e2a  mov     rcx, [rbp+arg_38]
0x180128e31  mov     [rcx], eax
0x180128e33  mov     rcx, [rdi+80h]
0x180128e3a  mov     edx, [rdi+10Ch]
0x180128e40  mov     rax, [rcx]
0x180128e43  mov     rax, [rax+28h]
0x180128e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128e4c  test    eax, eax
0x180128e4e  jz      short loc_180128E87
0x180128e50  mov     rcx, [rdi+80h]
0x180128e57  mov     edx, [r15]
0x180128e5a  mov     rax, [rcx]
0x180128e5d  mov     rax, [rax+20h]
0x180128e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128e66  mov     [r15], r13d
0x180128e69  mov     rcx, r14; lpCriticalSection
0x180128e6c  call    cs:__imp_LeaveCriticalSection
0x180128e72  mov     ebx, 65Bh
0x180128e77  lea     rcx, [rbp+var_18]; this
0x180128e7b  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x180128e80  mov     eax, ebx
0x180128e82  jmp     loc_180128F65
0x180128e87  cmp     [rdi+11Ch], r13b
0x180128e8e  jz      short loc_180128EC2
0x180128e90  mov     eax, [rdi+0F8h]
0x180128e96  test    eax, eax
0x180128e98  jnz     short loc_180128EAB
0x180128e9a  mov     eax, [rsi]
0x180128e9c  sub     eax, 2
0x180128e9f  test    eax, 0FFFFFFFDh
0x180128ea4  jnz     short loc_180128EC2
0x180128ea6  mov     [rsi], r13d
0x180128ea9  jmp     short loc_180128EC2
0x180128eab  cmp     eax, 1
0x180128eae  jnz     short loc_180128EC2
0x180128eb0  mov     eax, [rsi]
0x180128eb2  sub     eax, 3
0x180128eb5  test    eax, 0FFFFFFFDh
0x180128eba  jnz     short loc_180128EC2
0x180128ebc  mov     dword ptr [rsi], 1
0x180128ec2  mov     rcx, [rdi+90h]; hEvent
0x180128ec9  call    cs:__imp_SetEvent
0x180128ecf  mov     rcx, r14; lpCriticalSection
0x180128ed2  call    cs:__imp_LeaveCriticalSection
0x180128ed8  cmp     [rbp+var_14], r13b
0x180128edc  jz      short loc_180128EE8
0x180128ede  mov     ecx, 1
0x180128ee3  call    ?StopImpersonateCore@@YA_NW4ImpersonationType@@PEAH@Z; StopImpersonateCore(ImpersonationType,int *)
0x180128ee8  xor     eax, eax
0x180128eea  jmp     short loc_180128F65
0x180128eec  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180128ef2  jz      short loc_180128F3E
0x180128ef4  lea     r9, aCustomActionSe_6; "Custom Action Server rejected - Unknown"...
0x180128efb  jmp     short loc_180128F0C
0x180128efd  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180128f03  jz      short loc_180128F3E
0x180128f05  lea     r9, aCustomActionSe_11; "Custom Action Server rejected - Invalid"...
0x180128f0c  lea     rax, aNull_0; "(NULL)"
0x180128f13  xor     edx, edx; unsigned __int16
0x180128f15  mov     [rsp+78h+var_30], rax; char *
0x180128f1a  xor     r8d, r8d; int
0x180128f1d  mov     [rsp+78h+var_38], rax; char *
0x180128f22  mov     [rsp+78h+var_40], rax; char *
0x180128f27  mov     [rsp+78h+var_48], rax; char *
0x180128f2c  lea     ecx, [rdx+0Ah]; int
0x180128f2f  mov     [rsp+78h+var_50], rax; char *
0x180128f34  mov     [rsp+78h+var_58], rax; char *
0x180128f39  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180128f3e  mov     rcx, r14; lpCriticalSection
0x180128f41  call    cs:__imp_LeaveCriticalSection
0x180128f47  lea     rcx, [rbp+var_18]; this
0x180128f4b  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x180128f50  mov     eax, 5
0x180128f55  jmp     short loc_180128F65
0x180128f57  lea     rcx, [rbp+var_18]; this
0x180128f5b  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x180128f60  mov     eax, 57h ; 'W'
0x180128f65  add     rsp, 78h
0x180128f69  pop     r15
0x180128f6b  pop     r14
0x180128f6d  pop     r13
0x180128f6f  pop     r12
0x180128f71  pop     rdi
0x180128f72  pop     rsi
0x180128f73  pop     rbx
0x180128f74  pop     rbp
0x180128f75  retn
```
