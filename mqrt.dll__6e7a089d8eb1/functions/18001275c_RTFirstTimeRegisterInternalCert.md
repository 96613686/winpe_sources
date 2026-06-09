# RTFirstTimeRegisterInternalCert

- ea: `0x18001275c`
- end: `0x180012ca6`
- name: `RTFirstTimeRegisterInternalCert`
- size: `1354`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016f30`

## callees

- `0x1800087f8`
- `0x18000a33c`
- `0x18000da78`
- `0x180010a58`
- `0x1800113b8`
- `0x180011440`
- `0x180012000`
- `0x18001275c`
- `0x180013c74`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001289a`
- `ADVAPI32!RegOpenKeyExW` at `0x18001289a`
- `ADVAPI32!RegOpenCurrentUser` at `0x18001286f`
- `ADVAPI32!RegOpenCurrentUser` at `0x18001286f`
- `ADVAPI32!RegSetValueExW` at `0x180012b18`
- `ADVAPI32!RegSetValueExW` at `0x180012bcb`
- `ADVAPI32!RegSetValueExW` at `0x180012b18`
- `ADVAPI32!RegSetValueExW` at `0x180012bcb`
- `ADVAPI32!RegQueryValueExW` at `0x1800128e4`
- `ADVAPI32!RegQueryValueExW` at `0x180012929`
- `ADVAPI32!RegQueryValueExW` at `0x180012a7a`
- `ADVAPI32!RegQueryValueExW` at `0x180012ab0`
- `ADVAPI32!RegQueryValueExW` at `0x1800128e4`
- `ADVAPI32!RegQueryValueExW` at `0x180012929`
- `ADVAPI32!RegQueryValueExW` at `0x180012a7a`
- `ADVAPI32!RegQueryValueExW` at `0x180012ab0`
- `KERNEL32!CreateMutexW` at `0x180012968`
- `KERNEL32!CreateMutexW` at `0x180012968`
- `KERNEL32!GetLastError` at `0x18001297a`
- `KERNEL32!GetLastError` at `0x180012a2a`
- `KERNEL32!GetLastError` at `0x180012b77`
- `KERNEL32!GetLastError` at `0x180012c12`
- `KERNEL32!GetLastError` at `0x18001297a`
- `KERNEL32!GetLastError` at `0x180012a2a`
- `KERNEL32!GetLastError` at `0x180012b77`
- `KERNEL32!GetLastError` at `0x180012c12`
- `KERNEL32!ReleaseMutex` at `0x180012b58`
- `KERNEL32!ReleaseMutex` at `0x180012b58`
- `KERNEL32!WaitForSingleObject` at `0x180012a01`
- `KERNEL32!WaitForSingleObject` at `0x180012a01`
- `mqsec!GetFalconKeyValue` at `0x1800127da`
- `mqsec!GetFalconKeyValue` at `0x1800127da`

## string_xrefs

- `0x1800127d3`: `security\AutoRegisterIntCert`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RTFirstTimeRegisterInternalCert(int a1)
{
  __int64 result; // rax
  signed int v3; // ebx
  unsigned __int16 v4; // r8
  HKEY UserRegHandle; // rax
  unsigned __int16 v6; // r8
  HKEY MutexW; // rax
  HKEY v8; // rbx
  signed int v9; // eax
  unsigned __int16 v10; // r8
  DWORD v11; // eax
  signed int v12; // eax
  DWORD v13; // eax
  signed int LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY v17[2]; // [rsp+40h] [rbp-10h] BYREF
  signed int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  result = *(unsigned int *)&::Data;
  if ( !*(_DWORD *)&::Data )
  {
    if ( IsWorkGroupMode() )
    {
      v3 = -1072824273;
      *(_DWORD *)&::Data = -1072824273;
      v4 = 180;
LABEL_4:
      LogMsgHR(v3, (wchar_t *)L"rt/rtintcrt", v4);
      return (unsigned int)v3;
    }
    Data = 1;
    Type = 4;
    cbData = 4;
    if ( !GetFalconKeyValue(L"security\\AutoRegisterIntCert", &Type, &Data, &cbData, 0) && !Data )
    {
      v3 = -1072824273;
      *(_DWORD *)&::Data = -1072824273;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 32, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
        v3 = *(_DWORD *)&::Data;
      }
      if ( v3 >= 0 )
        return (unsigned int)v3;
      v4 = 200;
      goto LABEL_4;
    }
    hKey = 0;
    v17[0] = 0;
    if ( a1 )
    {
      phkResult = 0;
      if ( RegOpenCurrentUser(0x20019u, &phkResult)
        || RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\MSMQ", 0, 0xF003Fu, &hKey) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        *(_DWORD *)&::Data = v3;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            33,
            WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
            (unsigned int)v3);
          v3 = *(_DWORD *)&::Data;
        }
        if ( v3 < 0 )
          LogMsgHR(v3, (wchar_t *)L"rt/rtintcrt", 0xDCu);
        CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
        goto LABEL_64;
      }
      v17[0] = hKey;
      CRegHandle::~CRegHandle((CRegHandle *)&phkResult);
      UserRegHandle = hKey;
    }
    else
    {
      UserRegHandle = (HKEY)GetUserRegHandle();
      hKey = UserRegHandle;
    }
    cbData = 4;
    if ( !RegQueryValueExW(UserRegHandle, L"CertificateRegistered", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v3 = -1072824274;
      *(_DWORD *)&::Data = -1072824274;
      v6 = 240;
      goto LABEL_22;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"AutoRegisterError", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v3 = Data;
      *(_DWORD *)&::Data = Data;
      if ( Data >= 0 )
      {
LABEL_64:
        CRegHandle::~CRegHandle((CRegHandle *)v17);
        return (unsigned int)v3;
      }
      v6 = 260;
LABEL_22:
      LogMsgHR(v3, (wchar_t *)L"rt/rtintcrt", v6);
      goto LABEL_64;
    }
    MutexW = (HKEY)CreateMutexW(0, 0, L"Local\\MsmqRegisterInternalCertificate");
    v8 = MutexW;
    phkResult = MutexW;
    if ( !MutexW )
    {
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      *(_DWORD *)&::Data = v3;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          34,
          WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
          (unsigned int)v3);
        v3 = *(_DWORD *)&::Data;
      }
      if ( v3 >= 0 )
        goto LABEL_32;
      v10 = 280;
LABEL_31:
      LogMsgHR(v3, (wchar_t *)L"rt/rtintcrt", v10);
LABEL_32:
      CHandle::~CHandle((CHandle *)&phkResult);
      goto LABEL_64;
    }
    Data = WaitForSingleObject(MutexW, 0x1D4C0u);
    if ( Data && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 35, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v11);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"CertificateRegistered", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"AutoRegisterError", 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        v12 = *(_DWORD *)&::Data;
      }
      else
      {
        v12 = Data;
        *(_DWORD *)&::Data = Data;
      }
      if ( v12 )
        goto LABEL_47;
      *(_DWORD *)&::Data = MQRegisterCertificate(1u, 0, 0);
      cbData = 4;
      if ( *(int *)&::Data < 0 )
      {
        RegSetValueExW(hKey, L"AutoRegisterError", 0, 4u, &::Data, 4u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            37,
            WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids,
            *(unsigned int *)&::Data);
        goto LABEL_47;
      }
      Data = 1;
      RegSetValueExW(hKey, L"CertificateRegistered", 0, 4u, (const BYTE *)&Data, 4u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 36, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    }
    *(_DWORD *)&::Data = 1074659338;
LABEL_47:
    if ( !ReleaseMutex(v8)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v13);
    }
    v3 = *(_DWORD *)&::Data;
    if ( *(int *)&::Data >= 0 )
      goto LABEL_32;
    v10 = 300;
    goto LABEL_31;
  }
  return result;
}

```

## disassembly

```asm
0x18001275c  mov     [rsp-18h+arg_0], rbx
0x180012761  push    rbp
0x180012762  push    rdi
0x180012763  push    r14
0x180012765  mov     rbp, rsp
0x180012768  sub     rsp, 50h
0x18001276c  mov     ebx, ecx
0x18001276e  mov     eax, cs:Data
0x180012774  test    eax, eax
0x180012776  jnz     loc_180012C98
0x18001277c  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x180012781  test    al, al
0x180012783  jz      short loc_1800127A9
0x180012785  mov     ebx, 0C00E002Fh
0x18001278a  mov     cs:Data, ebx
0x180012790  mov     r8d, 0B4h; unsigned __int16
0x180012796  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x18001279d  mov     ecx, ebx; int
0x18001279f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800127a4  jmp     loc_180012C96
0x1800127a9  mov     [rbp+Data], 1
0x1800127b0  mov     r14d, 4
0x1800127b6  mov     [rbp+Type], r14d
0x1800127ba  mov     [rbp+cbData], r14d
0x1800127be  mov     [rsp+50h+var_30], 0
0x1800127c7  lea     r9, [rbp+cbData]
0x1800127cb  lea     r8, [rbp+Data]
0x1800127cf  lea     rdx, [rbp+Type]
0x1800127d3  lea     rcx, aSecurityAutore; "security\\AutoRegisterIntCert"
0x1800127da  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x1800127e0  test    eax, eax
0x1800127e2  jnz     short loc_18001283F
0x1800127e4  cmp     [rbp+Data], eax
0x1800127e7  jnz     short loc_18001283F
0x1800127e9  mov     ebx, 0C00E002Fh
0x1800127ee  mov     cs:Data, ebx
0x1800127f4  lea     rdi, WPP_GLOBAL_Control
0x1800127fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012802  cmp     rcx, rdi
0x180012805  jz      short loc_18001282C
0x180012807  test    [rcx+10Ch], r14b
0x18001280e  jz      short loc_18001282C
0x180012810  lea     edx, [rax+20h]
0x180012813  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x18001281a  mov     rcx, [rcx+100h]
0x180012821  call    WPP_SF_
0x180012826  mov     ebx, cs:Data
0x18001282c  test    ebx, ebx
0x18001282e  jns     loc_180012C96
0x180012834  mov     r8d, 0C8h
0x18001283a  jmp     loc_180012796
0x18001283f  mov     [rbp+hKey], 0
0x180012847  mov     [rbp+var_10], 0
0x18001284f  test    ebx, ebx
0x180012851  jnz     short loc_18001285E
0x180012853  call    GetUserRegHandle
0x180012858  mov     [rbp+hKey], rax
0x18001285c  jmp     short loc_1800128BD
0x18001285e  mov     [rbp+phkResult], 0
0x180012866  lea     rdx, [rbp+phkResult]; phkResult
0x18001286a  mov     ecx, 20019h; samDesired
0x18001286f  call    cs:__imp_RegOpenCurrentUser
0x180012875  test    eax, eax
0x180012877  jnz     loc_180012C12
0x18001287d  lea     rax, [rbp+hKey]
0x180012881  mov     [rsp+50h+var_30], rax; phkResult
0x180012886  mov     r9d, 0F003Fh; samDesired
0x18001288c  xor     r8d, r8d; ulOptions
0x18001288f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ"
0x180012896  mov     rcx, [rbp+phkResult]; hKey
0x18001289a  call    cs:__imp_RegOpenKeyExW
0x1800128a0  test    eax, eax
0x1800128a2  jnz     loc_180012C12
0x1800128a8  mov     rax, [rbp+hKey]
0x1800128ac  mov     [rbp+var_10], rax
0x1800128b0  lea     rcx, [rbp+phkResult]; this
0x1800128b4  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x1800128b9  mov     rax, [rbp+hKey]
0x1800128bd  mov     [rbp+cbData], r14d
0x1800128c1  lea     rcx, [rbp+cbData]
0x1800128c5  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x1800128ca  lea     rcx, [rbp+Data]
0x1800128ce  mov     [rsp+50h+var_30], rcx; lpData
0x1800128d3  lea     r9, [rbp+Type]; lpType
0x1800128d7  xor     r8d, r8d; lpReserved
0x1800128da  lea     rdx, ValueName; "CertificateRegistered"
0x1800128e1  mov     rcx, rax; hKey
0x1800128e4  call    cs:__imp_RegQueryValueExW
0x1800128ea  test    eax, eax
0x1800128ec  jnz     short loc_180012901
0x1800128ee  mov     ebx, 0C00E002Eh
0x1800128f3  mov     cs:Data, ebx
0x1800128f9  mov     r8d, 0F0h
0x1800128ff  jmp     short loc_18001294A
0x180012901  mov     [rbp+cbData], r14d
0x180012905  lea     rax, [rbp+cbData]
0x180012909  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001290e  lea     rax, [rbp+Data]
0x180012912  mov     [rsp+50h+var_30], rax; lpData
0x180012917  lea     r9, [rbp+Type]; lpType
0x18001291b  xor     r8d, r8d; lpReserved
0x18001291e  lea     rdx, aAutoregisterer; "AutoRegisterError"
0x180012925  mov     rcx, [rbp+hKey]; hKey
0x180012929  call    cs:__imp_RegQueryValueExW
0x18001292f  test    eax, eax
0x180012931  jnz     short loc_18001295D
0x180012933  mov     ebx, [rbp+Data]
0x180012936  mov     cs:Data, ebx
0x18001293c  test    ebx, ebx
0x18001293e  jns     loc_180012C8D
0x180012944  mov     r8d, 104h; unsigned __int16
0x18001294a  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012951  mov     ecx, ebx; int
0x180012953  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012958  jmp     loc_180012C8D
0x18001295d  lea     r8, Name; "Local\\MsmqRegisterInternalCertificate"
0x180012964  xor     edx, edx; bInitialOwner
0x180012966  xor     ecx, ecx; lpMutexAttributes
0x180012968  call    cs:__imp_CreateMutexW
0x18001296e  mov     rbx, rax
0x180012971  mov     [rbp+phkResult], rax
0x180012975  test    rax, rax
0x180012978  jnz     short loc_1800129F9
0x18001297a  call    cs:__imp_GetLastError
0x180012980  mov     ebx, eax
0x180012982  test    eax, eax
0x180012984  jle     short loc_18001298F
0x180012986  movzx   ebx, ax
0x180012989  or      ebx, 80070000h
0x18001298f  mov     cs:Data, ebx
0x180012995  lea     rdi, WPP_GLOBAL_Control
0x18001299c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129a3  cmp     rcx, rdi
0x1800129a6  jz      short loc_1800129D2
0x1800129a8  test    byte ptr [rcx+10Ch], 1
0x1800129af  jz      short loc_1800129D2
0x1800129b1  mov     edx, 22h ; '"'
0x1800129b6  mov     r9d, ebx
0x1800129b9  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x1800129c0  mov     rcx, [rcx+100h]
0x1800129c7  call    WPP_SF_d
0x1800129cc  mov     ebx, cs:Data
0x1800129d2  test    ebx, ebx
0x1800129d4  jns     short loc_1800129EB
0x1800129d6  mov     r8d, 118h; unsigned __int16
0x1800129dc  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x1800129e3  mov     ecx, ebx; int
0x1800129e5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800129ea  nop
0x1800129eb  lea     rcx, [rbp+phkResult]; this
0x1800129ef  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1800129f4  jmp     loc_180012C8D
0x1800129f9  mov     edx, 1D4C0h; dwMilliseconds
0x1800129fe  mov     rcx, rbx; hHandle
0x180012a01  call    cs:__imp_WaitForSingleObject
0x180012a07  mov     [rbp+Data], eax
0x180012a0a  lea     rdi, WPP_GLOBAL_Control
0x180012a11  test    eax, eax
0x180012a13  jz      short loc_180012A52
0x180012a15  mov     rax, cs:WPP_GLOBAL_Control
0x180012a1c  cmp     rax, rdi
0x180012a1f  jz      short loc_180012A52
0x180012a21  test    byte ptr [rax+10Ch], 1
0x180012a28  jz      short loc_180012A52
0x180012a2a  call    cs:__imp_GetLastError
0x180012a30  mov     edx, 23h ; '#'
0x180012a35  mov     r9d, eax
0x180012a38  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a46  mov     rcx, [rcx+100h]
0x180012a4d  call    WPP_SF_d
0x180012a52  mov     [rbp+cbData], r14d
0x180012a56  lea     rax, [rbp+cbData]
0x180012a5a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180012a5f  lea     rax, [rbp+Data]
0x180012a63  mov     [rsp+50h+var_30], rax; lpData
0x180012a68  lea     r9, [rbp+Type]; lpType
0x180012a6c  xor     r8d, r8d; lpReserved
0x180012a6f  lea     rdx, ValueName; "CertificateRegistered"
0x180012a76  mov     rcx, [rbp+hKey]; hKey
0x180012a7a  call    cs:__imp_RegQueryValueExW
0x180012a80  test    eax, eax
0x180012a82  jz      loc_180012B4B
0x180012a88  mov     [rbp+cbData], r14d
0x180012a8c  lea     rax, [rbp+cbData]
0x180012a90  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180012a95  lea     rax, [rbp+Data]
0x180012a99  mov     [rsp+50h+var_30], rax; lpData
0x180012a9e  lea     r9, [rbp+Type]; lpType
0x180012aa2  xor     r8d, r8d; lpReserved
0x180012aa5  lea     rdx, aAutoregisterer; "AutoRegisterError"
0x180012aac  mov     rcx, [rbp+hKey]; hKey
0x180012ab0  call    cs:__imp_RegQueryValueExW
0x180012ab6  test    eax, eax
0x180012ab8  jnz     short loc_180012AC5
0x180012aba  mov     eax, [rbp+Data]
0x180012abd  mov     cs:Data, eax
0x180012ac3  jmp     short loc_180012ACB
0x180012ac5  mov     eax, cs:Data
0x180012acb  test    eax, eax
0x180012acd  jnz     loc_180012B55
0x180012ad3  xor     r8d, r8d; dwCertBufferLength
0x180012ad6  xor     edx, edx; lpCertBuffer
0x180012ad8  lea     ecx, [rax+1]; dwFlags
0x180012adb  call    MQRegisterCertificate
0x180012ae0  mov     cs:Data, eax
0x180012ae6  mov     [rbp+cbData], r14d
0x180012aea  mov     dword ptr [rsp+50h+lpcbData], r14d; cbData
0x180012aef  mov     r9d, r14d; dwType
0x180012af2  xor     r8d, r8d; Reserved
0x180012af5  mov     rcx, [rbp+hKey]; hKey
0x180012af9  test    eax, eax
0x180012afb  js      loc_180012BB8
0x180012b01  mov     [rbp+Data], 1
0x180012b08  lea     rax, [rbp+Data]
0x180012b0c  mov     [rsp+50h+var_30], rax; lpData
0x180012b11  lea     rdx, ValueName; "CertificateRegistered"
0x180012b18  call    cs:__imp_RegSetValueExW
0x180012b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b25  cmp     rcx, rdi
0x180012b28  jz      short loc_180012B4B
0x180012b2a  test    [rcx+10Ch], r14b
0x180012b31  jz      short loc_180012B4B
0x180012b33  mov     edx, 24h ; '$'
0x180012b38  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012b3f  mov     rcx, [rcx+100h]
0x180012b46  call    WPP_SF_
0x180012b4b  mov     cs:Data, 400E000Ah
0x180012b55  mov     rcx, rbx; hMutex
0x180012b58  call    cs:__imp_ReleaseMutex
0x180012b5e  test    eax, eax
0x180012b60  jnz     short loc_180012B9F
0x180012b62  mov     rax, cs:WPP_GLOBAL_Control
0x180012b69  cmp     rax, rdi
0x180012b6c  jz      short loc_180012B9F
0x180012b6e  test    byte ptr [rax+10Ch], 1
0x180012b75  jz      short loc_180012B9F
0x180012b77  call    cs:__imp_GetLastError
0x180012b7d  mov     edx, 26h ; '&'
0x180012b82  mov     r9d, eax
0x180012b85  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b93  mov     rcx, [rcx+100h]
0x180012b9a  call    WPP_SF_d
0x180012b9f  mov     ebx, cs:Data
0x180012ba5  test    ebx, ebx
0x180012ba7  jns     loc_1800129EB
0x180012bad  mov     r8d, 12Ch
0x180012bb3  jmp     loc_1800129DC
0x180012bb8  lea     rax, Data
0x180012bbf  mov     [rsp+50h+var_30], rax; lpData
0x180012bc4  lea     rdx, aAutoregisterer; "AutoRegisterError"
0x180012bcb  call    cs:__imp_RegSetValueExW
0x180012bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bd8  cmp     rcx, rdi
0x180012bdb  jz      loc_180012B55
0x180012be1  test    byte ptr [rcx+10Ch], 1
0x180012be8  jz      loc_180012B55
0x180012bee  mov     edx, 25h ; '%'
0x180012bf3  mov     r9d, cs:Data
0x180012bfa  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012c01  mov     rcx, [rcx+100h]
0x180012c08  call    WPP_SF_d
0x180012c0d  jmp     loc_180012B55
0x180012c12  call    cs:__imp_GetLastError
0x180012c18  mov     ebx, eax
0x180012c1a  test    eax, eax
0x180012c1c  jle     short loc_180012C27
0x180012c1e  movzx   ebx, ax
0x180012c21  or      ebx, 80070000h
0x180012c27  mov     cs:Data, ebx
0x180012c2d  lea     rdi, WPP_GLOBAL_Control
0x180012c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c3b  cmp     rcx, rdi
0x180012c3e  jz      short loc_180012C6A
0x180012c40  test    byte ptr [rcx+10Ch], 1
0x180012c47  jz      short loc_180012C6A
0x180012c49  mov     edx, 21h ; '!'
0x180012c4e  mov     r9d, ebx
0x180012c51  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012c58  mov     rcx, [rcx+100h]
0x180012c5f  call    WPP_SF_d
0x180012c64  mov     ebx, cs:Data
0x180012c6a  test    ebx, ebx
0x180012c6c  jns     short loc_180012C83
0x180012c6e  mov     r8d, 0DCh; unsigned __int16
0x180012c74  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012c7b  mov     ecx, ebx; int
0x180012c7d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012c82  nop
0x180012c83  lea     rcx, [rbp+phkResult]; this
0x180012c87  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180012c8c  nop
0x180012c8d  lea     rcx, [rbp+var_10]; this
0x180012c91  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180012c96  mov     eax, ebx
0x180012c98  mov     rbx, [rsp+50h+arg_0]
0x180012c9d  add     rsp, 50h
0x180012ca1  pop     r14
0x180012ca3  pop     rdi
  ... truncated ...
```
