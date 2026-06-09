# CMsiConfigurationManager::RegisterCustomActionServer(icacCustomActionContext *,uchar const *,int,IMsiCustomAction *,ulong *,IMsiRemoteAPI * *,ulong *)

- ea: `0x18012eaa0`
- end: `0x18012ef2d`
- name: `?RegisterCustomActionServer@CMsiConfigurationManager@@UEAAIPEAW4icacCustomActionContext@@PEBEHPEAUIMsiCustomAction@@PEAKPEAPEAUIMsiRemoteAPI@@3@Z`
- size: `1165`
- prototype: `unsigned int __fastcall(CMsiConfigurationManager *__hidden this, enum icacCustomActionContext *, const unsigned __int8 *, int, struct IMsiCustomAction *, unsigned int *, struct IMsiRemoteAPI **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180027634`
- `0x180045ba4`
- `0x18009d0c0`
- `0x18012eaa0`
- `0x18014b72c`
- `0x18015383c`
- `0x180266010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18012eb84`
- `ADVAPI32!OpenThreadToken` at `0x18012eb84`
- `KERNEL32!CloseHandle` at `0x18012eba3`
- `KERNEL32!CloseHandle` at `0x18012eba3`
- `KERNEL32!LeaveCriticalSection` at `0x18012ec47`
- `KERNEL32!LeaveCriticalSection` at `0x18012ee0a`
- `KERNEL32!LeaveCriticalSection` at `0x18012ee7c`
- `KERNEL32!LeaveCriticalSection` at `0x18012eef1`
- `KERNEL32!LeaveCriticalSection` at `0x18012ec47`
- `KERNEL32!LeaveCriticalSection` at `0x18012ee0a`
- `KERNEL32!LeaveCriticalSection` at `0x18012ee7c`
- `KERNEL32!LeaveCriticalSection` at `0x18012eef1`
- `KERNEL32!EnterCriticalSection` at `0x18012eb15`
- `KERNEL32!EnterCriticalSection` at `0x18012eb15`
- `KERNEL32!GetCurrentThread` at `0x18012eb6a`
- `KERNEL32!GetCurrentThread` at `0x18012eb6a`
- `KERNEL32!SetEvent` at `0x18012ee6d`
- `KERNEL32!SetEvent` at `0x18012ee6d`

## string_xrefs

- `0x18012ed18`: `32bit Impersonated`
- `0x18012ed0f`: `64bit Impersonated`
- `0x18012ed62`: `32bit AIS Impersonated`
- `0x18012ed59`: `64bit AIS Impersonated`

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
0x18012eaa0  push    rbp
0x18012eaa2  push    rbx
0x18012eaa3  push    rsi
0x18012eaa4  push    rdi
0x18012eaa5  push    r12
0x18012eaa7  push    r13
0x18012eaa9  push    r14
0x18012eaab  push    r15
0x18012eaad  mov     rbp, rsp
0x18012eab0  sub     rsp, 78h
0x18012eab4  mov     rdi, rcx
0x18012eab7  mov     r13d, r9d
0x18012eaba  lea     rcx, [rbp+var_18]; this
0x18012eabe  mov     r15, r8
0x18012eac1  mov     rsi, rdx
0x18012eac4  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x18012eac9  xor     ebx, ebx
0x18012eacb  test    rsi, rsi
0x18012eace  jz      loc_18012EF0D
0x18012ead4  test    r15, r15
0x18012ead7  jz      loc_18012EF0D
0x18012eadd  mov     r12, [rbp+arg_20]
0x18012eae1  test    r12, r12
0x18012eae4  jz      loc_18012EF0D
0x18012eaea  cmp     [rbp+arg_28], rbx
0x18012eaee  jz      loc_18012EF0D
0x18012eaf4  cmp     [rbp+arg_30], rbx
0x18012eaf8  jz      loc_18012EF0D
0x18012eafe  cmp     [rbp+arg_38], rbx
0x18012eb05  jz      loc_18012EF0D
0x18012eb0b  lea     r14, [rdi+0C0h]
0x18012eb12  mov     rcx, r14; lpCriticalSection
0x18012eb15  call    cs:__imp_EnterCriticalSection
0x18012eb1c  nop     dword ptr [rax+rax+00h]
0x18012eb21  cmp     [rdi+90h], rbx
0x18012eb28  jz      loc_18012EEAD
0x18012eb2e  cmp     [rdi+110h], ebx
0x18012eb34  jnz     loc_18012EEAD
0x18012eb3a  mov     rax, cs:?I_RpcBindingInqLocalClientPID@RPCRT4@@3P6AJPEAXPEAK@ZEA; long (*RPCRT4::I_RpcBindingInqLocalClientPID)(void *,ulong *)
0x18012eb41  lea     rdx, [rbp+arg_8]
0x18012eb45  xor     ecx, ecx
0x18012eb47  mov     [rbp+arg_8], ebx
0x18012eb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012eb4f  test    eax, eax
0x18012eb51  jnz     loc_18012EE9C
0x18012eb57  mov     eax, [rdi+118h]
0x18012eb5d  cmp     [rbp+arg_8], eax
0x18012eb60  jnz     loc_18012EE9C
0x18012eb66  mov     [rbp+TokenHandle], rbx
0x18012eb6a  call    cs:__imp_GetCurrentThread
0x18012eb71  nop     dword ptr [rax+rax+00h]
0x18012eb76  mov     rcx, rax; ThreadHandle
0x18012eb79  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18012eb7d  lea     edx, [rbx+8]; DesiredAccess
0x18012eb80  lea     r8d, [rbx+1]; OpenAsSelf
0x18012eb84  call    cs:__imp_OpenThreadToken
0x18012eb8b  nop     dword ptr [rax+rax+00h]
0x18012eb90  test    eax, eax
0x18012eb92  jz      short loc_18012EBAF
0x18012eb94  mov     rcx, [rbp+TokenHandle]; void *
0x18012eb98  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18012eb9d  mov     rcx, [rbp+TokenHandle]; hObject
0x18012eba1  mov     bl, al
0x18012eba3  call    cs:__imp_CloseHandle
0x18012ebaa  nop     dword ptr [rax+rax+00h]
0x18012ebaf  cmp     byte ptr [rdi+11Ch], 0
0x18012ebb6  jnz     short loc_18012EBFC
0x18012ebb8  mov     ecx, [rdi+0F8h]
0x18012ebbe  test    bl, bl
0x18012ebc0  jz      short loc_18012EBCC
0x18012ebc2  cmp     ecx, 1
0x18012ebc5  jbe     short loc_18012EBEA
0x18012ebc7  lea     eax, [rcx-6]
0x18012ebca  jmp     short loc_18012EBCF
0x18012ebcc  lea     eax, [rcx-2]
0x18012ebcf  cmp     eax, 3
0x18012ebd2  jbe     short loc_18012EBEA
0x18012ebd4  cmp     [rsi], ecx
0x18012ebd6  jz      short loc_18012EBFC
0x18012ebd8  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18012ebdf  jz      short loc_18012EC44
0x18012ebe1  lea     r9, aCustomActionSe_8; "Custom Action Server rejected - Wrong C"...
0x18012ebe8  jmp     short loc_18012EC12
0x18012ebea  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18012ebf1  jz      short loc_18012EC44
0x18012ebf3  lea     r9, aCustomActionSe_0; "Custom Action Server rejected - Mismatc"...
0x18012ebfa  jmp     short loc_18012EC12
0x18012ebfc  cmp     r13d, 10h
0x18012ec00  jz      short loc_18012EC5D
0x18012ec02  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18012ec09  jz      short loc_18012EC44
0x18012ec0b  lea     r9, aCustomActionSe_12; "Custom Action Server rejected - Invalid"...
0x18012ec12  lea     rax, aNull_0; "(NULL)"
0x18012ec19  xor     edx, edx; unsigned __int16
0x18012ec1b  mov     [rsp+78h+var_30], rax; char *
0x18012ec20  xor     r8d, r8d; int
0x18012ec23  mov     [rsp+78h+var_38], rax; char *
0x18012ec28  mov     [rsp+78h+var_40], rax; char *
0x18012ec2d  mov     [rsp+78h+var_48], rax; char *
0x18012ec32  lea     ecx, [rdx+0Ah]; int
0x18012ec35  mov     [rsp+78h+var_50], rax; char *
0x18012ec3a  mov     [rsp+78h+var_58], rax; char *
0x18012ec3f  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18012ec44  mov     rcx, r14; lpCriticalSection
0x18012ec47  call    cs:__imp_LeaveCriticalSection
0x18012ec4e  nop     dword ptr [rax+rax+00h]
0x18012ec53  mov     ebx, 5
0x18012ec58  jmp     loc_18012EE1B
0x18012ec5d  xor     r13d, r13d
0x18012ec60  mov     edx, r13d
0x18012ec63  cmp     edx, 10h
0x18012ec66  jge     short loc_18012EC95
0x18012ec68  movsxd  rcx, edx
0x18012ec6b  mov     al, [rcx+rdi+0E8h]
0x18012ec72  cmp     [rcx+r15], al
0x18012ec76  jnz     short loc_18012EC7C
0x18012ec78  inc     edx
0x18012ec7a  jmp     short loc_18012EC63
0x18012ec7c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18012ec83  jz      loc_18012EEEE
0x18012ec89  lea     r9, aCustomActionSe_12; "Custom Action Server rejected - Invalid"...
0x18012ec90  jmp     loc_18012EEBC
0x18012ec95  mov     rcx, [rdi+80h]
0x18012ec9c  test    rcx, rcx
0x18012ec9f  jz      loc_18012EE07
0x18012eca5  mov     rax, [rcx]
0x18012eca8  lea     r15, [rdi+110h]
0x18012ecaf  mov     r9, r15
0x18012ecb2  lea     r8, IID_IMsiCustomAction
0x18012ecb9  mov     rdx, r12
0x18012ecbc  mov     rax, [rax+18h]
0x18012ecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ecc5  test    eax, eax
0x18012ecc7  jnz     loc_18012EE07
0x18012eccd  mov     ecx, [rdi+0F8h]
0x18012ecd3  lea     ebx, [rax+5]
0x18012ecd6  cmp     ecx, ebx
0x18012ecd8  jg      short loc_18012ED2A
0x18012ecda  jz      short loc_18012ED21
0x18012ecdc  test    ecx, ecx
0x18012ecde  jz      short loc_18012ED18
0x18012ece0  sub     ecx, 1
0x18012ece3  jz      short loc_18012ED0F
0x18012ece5  sub     ecx, 1
0x18012ece8  jz      short loc_18012ED06
0x18012ecea  sub     ecx, 1
0x18012eced  jz      short loc_18012ECFD
0x18012ecef  cmp     ecx, 1
0x18012ecf2  jnz     short loc_18012ED3E
0x18012ecf4  lea     rcx, a32bitElevatedN; "32bit Elevated Non-remapped"
0x18012ecfb  jmp     short loc_18012ED69
0x18012ecfd  lea     rcx, a64bitElevatedR; "64bit Elevated Remapped"
0x18012ed04  jmp     short loc_18012ED69
0x18012ed06  lea     rcx, a32bitElevatedR; "32bit Elevated Remapped"
0x18012ed0d  jmp     short loc_18012ED69
0x18012ed0f  lea     rcx, a64bitImpersona; "64bit Impersonated"
0x18012ed16  jmp     short loc_18012ED69
0x18012ed18  lea     rcx, a32bitImpersona; "32bit Impersonated"
0x18012ed1f  jmp     short loc_18012ED69
0x18012ed21  lea     rcx, a64bitElevatedN; "64bit Elevated Non-remapped"
0x18012ed28  jmp     short loc_18012ED69
0x18012ed2a  sub     ecx, 6
0x18012ed2d  jz      short loc_18012ED62
0x18012ed2f  sub     ecx, 1
0x18012ed32  jz      short loc_18012ED59
0x18012ed34  sub     ecx, 1
0x18012ed37  jz      short loc_18012ED50
0x18012ed39  cmp     ecx, 1
0x18012ed3c  jz      short loc_18012ED47
0x18012ed3e  lea     rcx, aUnknown_0; "Unknown"
0x18012ed45  jmp     short loc_18012ED69
0x18012ed47  lea     rcx, a64bitEeui; "64bit EEUI"
0x18012ed4e  jmp     short loc_18012ED69
0x18012ed50  lea     rcx, a32bitEeui; "32bit EEUI"
0x18012ed57  jmp     short loc_18012ED69
0x18012ed59  lea     rcx, a64bitAisImpers; "64bit AIS Impersonated"
0x18012ed60  jmp     short loc_18012ED69
0x18012ed62  lea     rcx, a32bitAisImpers; "32bit AIS Impersonated"
0x18012ed69  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18012ed70  jz      short loc_18012EDAB
0x18012ed72  lea     rax, aNull_0; "(NULL)"
0x18012ed79  xor     edx, edx; unsigned __int16
0x18012ed7b  mov     [rsp+78h+var_30], rax; char *
0x18012ed80  lea     r9, aHelloIMYourSCu; "Hello, I'm your %s custom action server"...
0x18012ed87  mov     [rsp+78h+var_38], rax; char *
0x18012ed8c  xor     r8d, r8d; int
0x18012ed8f  mov     [rsp+78h+var_40], rax; char *
0x18012ed94  mov     [rsp+78h+var_48], rax; char *
0x18012ed99  mov     [rsp+78h+var_50], rax; char *
0x18012ed9e  mov     [rsp+78h+var_58], rcx; char *
0x18012eda3  lea     ecx, [rdx+9]; int
0x18012eda6  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18012edab  mov     eax, [rdi+108h]
0x18012edb1  lea     r8, IID_IMsiRemoteAPI
0x18012edb8  mov     rcx, [rbp+arg_28]
0x18012edbc  mov     r9, [rbp+arg_30]
0x18012edc0  mov     [rcx], eax
0x18012edc2  mov     eax, [rdi+114h]
0x18012edc8  mov     rcx, [rbp+arg_38]
0x18012edcf  mov     [rcx], eax
0x18012edd1  mov     rcx, [rdi+80h]
0x18012edd8  mov     edx, [rdi+10Ch]
0x18012edde  mov     rax, [rcx]
0x18012ede1  mov     rax, [rax+28h]
0x18012ede5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012edea  test    eax, eax
0x18012edec  jz      short loc_18012EE2B
0x18012edee  mov     rcx, [rdi+80h]
0x18012edf5  mov     edx, [r15]
0x18012edf8  mov     rax, [rcx]
0x18012edfb  mov     rax, [rax+20h]
0x18012edff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ee04  mov     [r15], r13d
0x18012ee07  mov     rcx, r14; lpCriticalSection
0x18012ee0a  call    cs:__imp_LeaveCriticalSection
0x18012ee11  nop     dword ptr [rax+rax+00h]
0x18012ee16  mov     ebx, 65Bh
0x18012ee1b  lea     rcx, [rbp+var_18]; this
0x18012ee1f  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x18012ee24  mov     eax, ebx
0x18012ee26  jmp     loc_18012EF1B
0x18012ee2b  cmp     [rdi+11Ch], r13b
0x18012ee32  jz      short loc_18012EE66
0x18012ee34  mov     eax, [rdi+0F8h]
0x18012ee3a  test    eax, eax
0x18012ee3c  jnz     short loc_18012EE4F
0x18012ee3e  mov     eax, [rsi]
0x18012ee40  sub     eax, 2
0x18012ee43  test    eax, 0FFFFFFFDh
0x18012ee48  jnz     short loc_18012EE66
0x18012ee4a  mov     [rsi], r13d
0x18012ee4d  jmp     short loc_18012EE66
0x18012ee4f  cmp     eax, 1
0x18012ee52  jnz     short loc_18012EE66
0x18012ee54  mov     eax, [rsi]
0x18012ee56  sub     eax, 3
0x18012ee59  test    eax, 0FFFFFFFDh
0x18012ee5e  jnz     short loc_18012EE66
0x18012ee60  mov     dword ptr [rsi], 1
0x18012ee66  mov     rcx, [rdi+90h]; hEvent
0x18012ee6d  call    cs:__imp_SetEvent
0x18012ee74  nop     dword ptr [rax+rax+00h]
0x18012ee79  mov     rcx, r14; lpCriticalSection
0x18012ee7c  call    cs:__imp_LeaveCriticalSection
0x18012ee83  nop     dword ptr [rax+rax+00h]
0x18012ee88  cmp     [rbp+var_14], r13b
0x18012ee8c  jz      short loc_18012EE98
0x18012ee8e  mov     ecx, 1
0x18012ee93  call    ?StopImpersonateCore@@YA_NW4ImpersonationType@@PEAH@Z; StopImpersonateCore(ImpersonationType,int *)
0x18012ee98  xor     eax, eax
0x18012ee9a  jmp     short loc_18012EF1B
0x18012ee9c  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18012eea2  jz      short loc_18012EEEE
0x18012eea4  lea     r9, aCustomActionSe_6; "Custom Action Server rejected - Unknown"...
0x18012eeab  jmp     short loc_18012EEBC
0x18012eead  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18012eeb3  jz      short loc_18012EEEE
0x18012eeb5  lea     r9, aCustomActionSe_11; "Custom Action Server rejected - Invalid"...
0x18012eebc  lea     rax, aNull_0; "(NULL)"
0x18012eec3  xor     edx, edx; unsigned __int16
0x18012eec5  mov     [rsp+78h+var_30], rax; char *
0x18012eeca  xor     r8d, r8d; int
0x18012eecd  mov     [rsp+78h+var_38], rax; char *
0x18012eed2  mov     [rsp+78h+var_40], rax; char *
0x18012eed7  mov     [rsp+78h+var_48], rax; char *
0x18012eedc  lea     ecx, [rdx+0Ah]; int
0x18012eedf  mov     [rsp+78h+var_50], rax; char *
0x18012eee4  mov     [rsp+78h+var_58], rax; char *
0x18012eee9  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18012eeee  mov     rcx, r14; lpCriticalSection
0x18012eef1  call    cs:__imp_LeaveCriticalSection
0x18012eef8  nop     dword ptr [rax+rax+00h]
0x18012eefd  lea     rcx, [rbp+var_18]; this
0x18012ef01  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x18012ef06  mov     eax, 5
0x18012ef0b  jmp     short loc_18012EF1B
0x18012ef0d  lea     rcx, [rbp+var_18]; this
0x18012ef11  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x18012ef16  mov     eax, 57h ; 'W'
0x18012ef1b  add     rsp, 78h
0x18012ef1f  pop     r15
0x18012ef21  pop     r14
0x18012ef23  pop     r13
0x18012ef25  pop     r12
0x18012ef27  pop     rdi
0x18012ef28  pop     rsi
0x18012ef29  pop     rbx
0x18012ef2a  pop     rbp
0x18012ef2b  retn
```
