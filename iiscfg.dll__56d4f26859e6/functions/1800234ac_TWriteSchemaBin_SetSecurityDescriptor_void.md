# TWriteSchemaBin::SetSecurityDescriptor(void)

- ea: `0x1800234ac`
- end: `0x180023db7`
- name: `?SetSecurityDescriptor@TWriteSchemaBin@@AEAAXXZ`
- size: `2315`
- prototype: `void __fastcall(TWriteSchemaBin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800232f0`

## callees

- `0x180002bc4`
- `0x180011b38`
- `0x180012734`
- `0x180017ad8`
- `0x1800234ac`
- `0x18002e110`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800234f0`
- `KERNEL32!LocalAlloc` at `0x1800238fc`
- `KERNEL32!LocalAlloc` at `0x1800234f0`
- `KERNEL32!LocalAlloc` at `0x1800238fc`
- `KERNEL32!GetLastError` at `0x1800235d4`
- `KERNEL32!GetLastError` at `0x1800236ea`
- `KERNEL32!GetLastError` at `0x180023805`
- `KERNEL32!GetLastError` at `0x1800239e3`
- `KERNEL32!GetLastError` at `0x180023ad9`
- `KERNEL32!GetLastError` at `0x180023bca`
- `KERNEL32!GetLastError` at `0x180023cbb`
- `KERNEL32!GetLastError` at `0x1800235d4`
- `KERNEL32!GetLastError` at `0x1800236ea`
- `KERNEL32!GetLastError` at `0x180023805`
- `KERNEL32!GetLastError` at `0x1800239e3`
- `KERNEL32!GetLastError` at `0x180023ad9`
- `KERNEL32!GetLastError` at `0x180023bca`
- `KERNEL32!GetLastError` at `0x180023cbb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800235c6`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800235c6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180023cad`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180023cad`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023acb`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023bbc`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023acb`
- `ADVAPI32!AddAccessAllowedAce` at `0x180023bbc`
- `ADVAPI32!InitializeAcl` at `0x1800239d5`
- `ADVAPI32!InitializeAcl` at `0x1800239d5`
- `ADVAPI32!GetLengthSid` at `0x1800238df`
- `ADVAPI32!GetLengthSid` at `0x1800238ea`
- `ADVAPI32!GetLengthSid` at `0x1800238df`
- `ADVAPI32!GetLengthSid` at `0x1800238ea`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800236dc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800237f7`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800236dc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800237f7`

## string_xrefs

- `0x1800235aa`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180023694`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800237aa`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800238c5`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800239b6`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180023aa3`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180023b99`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180023c8a`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180023d7b`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18002358a`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x1800235b1`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023674`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x18002369b`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x18002378a`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x1800237b1`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x1800238a5`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x1800238cc`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023996`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x1800239bd`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023a83`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023aaa`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023b79`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023ba0`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023c6a`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023c91`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023d5b`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x180023d82`: `inetsrv\iis\mb\config\src\core\schemagen\twriteschemabin.cpp`
- `0x18002363b`: `InitializeSecurityDescriptor`
- `0x180023751`: `AllocateAndInitializeSid`
- `0x18002386c`: `AllocateAndInitializeSid`
- `0x180023a4a`: `InitializeAcl`
- `0x180023b40`: `AddAccessAllowedAce`
- `0x180023c31`: `AddAccessAllowedAce`
- `0x180023d22`: `SetSecurityDescriptorDacl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TWriteSchemaBin::SetSecurityDescriptor(TWriteSchemaBin *this)
{
  HLOCAL v2; // rax
  signed int LastError; // eax
  __int64 v4; // r9
  PSID *v5; // r14
  signed int v6; // eax
  __int64 v7; // r9
  PSID *v8; // r15
  signed int v9; // eax
  __int64 v10; // r9
  PSID v11; // rbx
  DWORD LengthSid; // edi
  DWORD v13; // ebx
  ACL *v14; // rax
  signed int v15; // eax
  __int64 v16; // r9
  signed int v17; // eax
  __int64 v18; // r9
  signed int v19; // eax
  __int64 v20; // r9
  signed int v21; // eax
  __int64 v22; // r9
  _BYTE v23[8]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp+27h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v2 = LocalAlloc(0x40u, 0x28u);
  *((_QWORD *)this + 7) = v2;
  if ( !v2 )
  {
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      2149648481LL,
      3,
      -1073606454,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      82,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x52u,
      0);
  }
  if ( !InitializeSecurityDescriptor(v2, 1u) )
  {
    LastError = GetLastError();
    v4 = (unsigned int)LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v4,
      3,
      -2147348263,
      L"InitializeSecurityDescriptor",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      90,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x5Au,
      0);
  }
  v5 = (PSID *)((char *)this + 72);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 9) )
  {
    v6 = GetLastError();
    v7 = (unsigned int)v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v7,
      3,
      -2147348263,
      L"AllocateAndInitializeSid",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      98,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x62u,
      0);
  }
  v8 = (PSID *)((char *)this + 64);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)this + 8) )
  {
    v9 = GetLastError();
    v10 = (unsigned int)v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v10,
      3,
      -2147348263,
      L"AllocateAndInitializeSid",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      103,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x67u,
      0);
  }
  v11 = *v8;
  LengthSid = GetLengthSid(*v5);
  v13 = LengthSid + GetLengthSid(v11) + 28;
  v14 = (ACL *)LocalAlloc(0x40u, v13);
  *((_QWORD *)this + 6) = v14;
  if ( !v14 )
  {
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      2149648481LL,
      3,
      -1073606454,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      117,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x75u,
      0);
  }
  if ( !InitializeAcl(v14, v13, 2u) )
  {
    v15 = GetLastError();
    v16 = (unsigned int)v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v16,
      3,
      -2147348263,
      L"InitializeAcl",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      122,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x7Au,
      0);
  }
  if ( !AddAccessAllowedAce(*((PACL *)this + 6), 2u, 0x1F01FFu, *v5) )
  {
    v17 = GetLastError();
    v18 = (unsigned int)v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v18,
      3,
      -2147348263,
      L"AddAccessAllowedAce",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      127,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x7Fu,
      0);
  }
  if ( !AddAccessAllowedAce(*((PACL *)this + 6), 2u, 0x1F01FFu, *v8) )
  {
    v19 = GetLastError();
    v20 = (unsigned int)v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v20,
      3,
      -2147348263,
      L"AddAccessAllowedAce",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      132,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x84u,
      0);
  }
  if ( !SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 7), 1, *((PACL *)this + 6), 0) )
  {
    v21 = GetLastError();
    v22 = (unsigned int)v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    v24 = 0;
    CErrorInterceptor::Init(
      v23,
      0,
      0,
      v22,
      3,
      -2147348263,
      L"SetSecurityDescriptorDacl",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)v23,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      140,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v23);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\twriteschemabin.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x8Cu,
      0);
  }
}

```

## disassembly

```asm
0x1800234ac  mov     [rsp-8+arg_8], rbx
0x1800234b1  mov     [rsp-8+arg_10], rsi
0x1800234b6  push    rbp
0x1800234b7  push    rdi
0x1800234b8  push    r12
0x1800234ba  push    r14
0x1800234bc  push    r15
0x1800234be  lea     rbp, [rsp-37h]
0x1800234c3  sub     rsp, 0D0h
0x1800234ca  mov     rax, cs:__security_cookie
0x1800234d1  xor     rax, rsp
0x1800234d4  mov     [rbp+57h+var_28], rax
0x1800234d8  mov     rsi, rcx
0x1800234db  xor     r12d, r12d
0x1800234de  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800234e2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800234e8  lea     edx, [r12+28h]; uBytes
0x1800234ed  lea     ecx, [rdx+18h]; uFlags
0x1800234f0  call    cs:__imp_LocalAlloc
0x1800234f6  mov     [rsi+38h], rax
0x1800234fa  test    rax, rax
0x1800234fd  jnz     loc_1800235BE
0x180023503  mov     [rbp+57h+var_38], r12
0x180023507  or      eax, 0FFFFFFFFh
0x18002350a  mov     [rsp+0F0h+var_50], eax
0x180023511  mov     [rsp+0F0h+var_58], eax
0x180023518  mov     [rsp+0F0h+var_70], r12d
0x180023520  mov     [rsp+0F0h+var_78], r12
0x180023525  mov     [rsp+0F0h+var_80], eax
0x180023529  mov     [rsp+0F0h+var_88], eax
0x18002352d  mov     [rsp+0F0h+var_90], r12d
0x180023532  mov     [rsp+0F0h+var_98], r12
0x180023537  mov     dword ptr [rsp+0F0h+pSid], r12d
0x18002353c  lea     rax, word_180034198
0x180023543  mov     qword ptr [rsp+0F0h+nSubAuthority7], rax
0x180023548  mov     qword ptr [rsp+0F0h+nSubAuthority6], rax
0x18002354d  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x180023552  mov     qword ptr [rsp+0F0h+nSubAuthority4], rax
0x180023557  mov     [rsp+0F0h+nSubAuthority3], 0C00210CAh
0x18002355f  mov     [rsp+0F0h+nSubAuthority2], 3
0x180023567  mov     r9d, 80210861h
0x18002356d  xor     r8d, r8d
0x180023570  xor     edx, edx
0x180023572  lea     rcx, [rbp+57h+var_40]
0x180023576  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18002357b  nop
0x18002357c  lea     ebx, [r12+52h]
0x180023581  mov     r9d, 400000h; unsigned int
0x180023587  mov     r8d, ebx; unsigned int
0x18002358a  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180023591  lea     rcx, [rbp+57h+var_40]; this
0x180023595  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18002359a  nop
0x18002359b  lea     rcx, [rbp+57h+var_40]; this
0x18002359f  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x1800235a4  xor     r9d, r9d; unsigned int
0x1800235a7  mov     r8d, ebx; unsigned int
0x1800235aa  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x1800235b1  lea     rcx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800235b8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800235be  mov     edx, 1; dwRevision
0x1800235c3  mov     rcx, rax; pSecurityDescriptor
0x1800235c6  call    cs:__imp_InitializeSecurityDescriptor
0x1800235cc  test    eax, eax
0x1800235ce  jnz     loc_1800236A8
0x1800235d4  call    cs:__imp_GetLastError
0x1800235da  mov     r9d, eax
0x1800235dd  test    eax, eax
0x1800235df  jle     short loc_1800235EC
0x1800235e1  movzx   r9d, ax
0x1800235e5  or      r9d, 80070000h
0x1800235ec  mov     [rbp+57h+var_38], r12
0x1800235f0  or      eax, 0FFFFFFFFh
0x1800235f3  mov     [rsp+0F0h+var_50], eax
0x1800235fa  mov     [rsp+0F0h+var_58], eax
0x180023601  mov     [rsp+0F0h+var_70], r12d
0x180023609  mov     [rsp+0F0h+var_78], r12
0x18002360e  mov     [rsp+0F0h+var_80], eax
0x180023612  mov     [rsp+0F0h+var_88], eax
0x180023616  mov     [rsp+0F0h+var_90], r12d
0x18002361b  mov     [rsp+0F0h+var_98], r12
0x180023620  mov     dword ptr [rsp+0F0h+pSid], r12d
0x180023625  lea     rax, word_180034198
0x18002362c  mov     qword ptr [rsp+0F0h+nSubAuthority7], rax
0x180023631  mov     qword ptr [rsp+0F0h+nSubAuthority6], rax
0x180023636  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x18002363b  lea     rax, aInitializesecu; "InitializeSecurityDescriptor"
0x180023642  mov     qword ptr [rsp+0F0h+nSubAuthority4], rax
0x180023647  mov     [rsp+0F0h+nSubAuthority3], 800210D9h
0x18002364f  mov     [rsp+0F0h+nSubAuthority2], 3
0x180023657  xor     r8d, r8d
0x18002365a  xor     edx, edx
0x18002365c  lea     rcx, [rbp+57h+var_40]
0x180023660  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180023665  nop
0x180023666  mov     ebx, 5Ah ; 'Z'
0x18002366b  mov     r9d, 400000h; unsigned int
0x180023671  mov     r8d, ebx; unsigned int
0x180023674  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002367b  lea     rcx, [rbp+57h+var_40]; this
0x18002367f  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180023684  nop
0x180023685  lea     rcx, [rbp+57h+var_40]; this
0x180023689  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18002368e  xor     r9d, r9d; unsigned int
0x180023691  mov     r8d, ebx; unsigned int
0x180023694  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x18002369b  lea     rcx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800236a2  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800236a8  lea     r14, [rsi+48h]
0x1800236ac  mov     [rsp+0F0h+pSid], r14; pSid
0x1800236b1  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x1800236b6  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x1800236bb  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x1800236c0  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x1800236c5  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x1800236ca  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x1800236cf  xor     r9d, r9d; nSubAuthority1
0x1800236d2  lea     r8d, [r9+12h]; nSubAuthority0
0x1800236d6  mov     dl, 1; nSubAuthorityCount
0x1800236d8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800236dc  call    cs:__imp_AllocateAndInitializeSid
0x1800236e2  test    eax, eax
0x1800236e4  jnz     loc_1800237BE
0x1800236ea  call    cs:__imp_GetLastError
0x1800236f0  mov     r9d, eax
0x1800236f3  test    eax, eax
0x1800236f5  jle     short loc_180023702
0x1800236f7  movzx   r9d, ax
0x1800236fb  or      r9d, 80070000h
0x180023702  mov     [rbp+57h+var_38], r12
0x180023706  or      eax, 0FFFFFFFFh
0x180023709  mov     [rsp+0F0h+var_50], eax
0x180023710  mov     [rsp+0F0h+var_58], eax
0x180023717  mov     [rsp+0F0h+var_70], r12d
0x18002371f  mov     [rsp+0F0h+var_78], r12
0x180023724  mov     [rsp+0F0h+var_80], eax
0x180023728  mov     [rsp+0F0h+var_88], eax
0x18002372c  mov     [rsp+0F0h+var_90], r12d
0x180023731  mov     [rsp+0F0h+var_98], r12
0x180023736  mov     dword ptr [rsp+0F0h+pSid], r12d
0x18002373b  lea     rax, word_180034198
0x180023742  mov     qword ptr [rsp+0F0h+nSubAuthority7], rax
0x180023747  mov     qword ptr [rsp+0F0h+nSubAuthority6], rax
0x18002374c  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x180023751  lea     rax, aAllocateandini; "AllocateAndInitializeSid"
0x180023758  mov     qword ptr [rsp+0F0h+nSubAuthority4], rax
0x18002375d  mov     [rsp+0F0h+nSubAuthority3], 800210D9h
0x180023765  mov     [rsp+0F0h+nSubAuthority2], 3
0x18002376d  xor     r8d, r8d
0x180023770  xor     edx, edx
0x180023772  lea     rcx, [rbp+57h+var_40]
0x180023776  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18002377b  nop
0x18002377c  mov     ebx, 62h ; 'b'
0x180023781  mov     r9d, 400000h; unsigned int
0x180023787  mov     r8d, ebx; unsigned int
0x18002378a  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180023791  lea     rcx, [rbp+57h+var_40]; this
0x180023795  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18002379a  nop
0x18002379b  lea     rcx, [rbp+57h+var_40]; this
0x18002379f  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x1800237a4  xor     r9d, r9d; unsigned int
0x1800237a7  mov     r8d, ebx; unsigned int
0x1800237aa  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x1800237b1  lea     rcx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800237b8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800237be  lea     r15, [rsi+40h]
0x1800237c2  mov     [rsp+0F0h+pSid], r15; pSid
0x1800237c7  mov     [rsp+0F0h+nSubAuthority7], r12d; nSubAuthority7
0x1800237cc  mov     [rsp+0F0h+nSubAuthority6], r12d; nSubAuthority6
0x1800237d1  mov     [rsp+0F0h+nSubAuthority5], r12d; nSubAuthority5
0x1800237d6  mov     [rsp+0F0h+nSubAuthority4], r12d; nSubAuthority4
0x1800237db  mov     [rsp+0F0h+nSubAuthority3], r12d; nSubAuthority3
0x1800237e0  mov     [rsp+0F0h+nSubAuthority2], r12d; nSubAuthority2
0x1800237e5  mov     r9d, 220h; nSubAuthority1
0x1800237eb  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800237f1  mov     dl, 2; nSubAuthorityCount
0x1800237f3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800237f7  call    cs:__imp_AllocateAndInitializeSid
0x1800237fd  test    eax, eax
0x1800237ff  jnz     loc_1800238D9
0x180023805  call    cs:__imp_GetLastError
0x18002380b  mov     r9d, eax
0x18002380e  test    eax, eax
0x180023810  jle     short loc_18002381D
0x180023812  movzx   r9d, ax
0x180023816  or      r9d, 80070000h
0x18002381d  mov     [rbp+57h+var_38], r12
0x180023821  or      eax, 0FFFFFFFFh
0x180023824  mov     [rsp+0F0h+var_50], eax
0x18002382b  mov     [rsp+0F0h+var_58], eax
0x180023832  mov     [rsp+0F0h+var_70], r12d
0x18002383a  mov     [rsp+0F0h+var_78], r12
0x18002383f  mov     [rsp+0F0h+var_80], eax
0x180023843  mov     [rsp+0F0h+var_88], eax
0x180023847  mov     [rsp+0F0h+var_90], r12d
0x18002384c  mov     [rsp+0F0h+var_98], r12
0x180023851  mov     dword ptr [rsp+0F0h+pSid], r12d
0x180023856  lea     rax, word_180034198
0x18002385d  mov     qword ptr [rsp+0F0h+nSubAuthority7], rax
0x180023862  mov     qword ptr [rsp+0F0h+nSubAuthority6], rax
0x180023867  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x18002386c  lea     rax, aAllocateandini; "AllocateAndInitializeSid"
0x180023873  mov     qword ptr [rsp+0F0h+nSubAuthority4], rax
0x180023878  mov     [rsp+0F0h+nSubAuthority3], 800210D9h
0x180023880  mov     [rsp+0F0h+nSubAuthority2], 3
0x180023888  xor     r8d, r8d
0x18002388b  xor     edx, edx
0x18002388d  lea     rcx, [rbp+57h+var_40]
0x180023891  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180023896  nop
0x180023897  mov     ebx, 67h ; 'g'
0x18002389c  mov     r9d, 400000h; unsigned int
0x1800238a2  mov     r8d, ebx; unsigned int
0x1800238a5  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800238ac  lea     rcx, [rbp+57h+var_40]; this
0x1800238b0  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x1800238b5  nop
0x1800238b6  lea     rcx, [rbp+57h+var_40]; this
0x1800238ba  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x1800238bf  xor     r9d, r9d; unsigned int
0x1800238c2  mov     r8d, ebx; unsigned int
0x1800238c5  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x1800238cc  lea     rcx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800238d3  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800238d9  mov     rbx, [r15]
0x1800238dc  mov     rcx, [r14]; pSid
0x1800238df  call    cs:__imp_GetLengthSid
0x1800238e5  mov     edi, eax
0x1800238e7  mov     rcx, rbx; pSid
0x1800238ea  call    cs:__imp_GetLengthSid
0x1800238f0  lea     ebx, [rax+1Ch]
0x1800238f3  add     ebx, edi
0x1800238f5  mov     edx, ebx; uBytes
0x1800238f7  mov     ecx, 40h ; '@'; uFlags
0x1800238fc  call    cs:__imp_LocalAlloc
0x180023902  mov     [rsi+30h], rax
0x180023906  test    rax, rax
0x180023909  jnz     loc_1800239CA
0x18002390f  mov     [rbp+57h+var_38], r12
0x180023913  or      eax, 0FFFFFFFFh
0x180023916  mov     [rsp+0F0h+var_50], eax
0x18002391d  mov     [rsp+0F0h+var_58], eax
0x180023924  mov     [rsp+0F0h+var_70], r12d
0x18002392c  mov     [rsp+0F0h+var_78], r12
0x180023931  mov     [rsp+0F0h+var_80], eax
0x180023935  mov     [rsp+0F0h+var_88], eax
0x180023939  mov     [rsp+0F0h+var_90], r12d
0x18002393e  mov     [rsp+0F0h+var_98], r12
0x180023943  mov     dword ptr [rsp+0F0h+pSid], r12d
0x180023948  lea     rax, word_180034198
0x18002394f  mov     qword ptr [rsp+0F0h+nSubAuthority7], rax
0x180023954  mov     qword ptr [rsp+0F0h+nSubAuthority6], rax
0x180023959  mov     qword ptr [rsp+0F0h+nSubAuthority5], rax
0x18002395e  mov     qword ptr [rsp+0F0h+nSubAuthority4], rax
0x180023963  mov     [rsp+0F0h+nSubAuthority3], 0C00210CAh
0x18002396b  mov     [rsp+0F0h+nSubAuthority2], 3
0x180023973  mov     r9d, 80210861h
0x180023979  xor     r8d, r8d
0x18002397c  xor     edx, edx
0x18002397e  lea     rcx, [rbp+57h+var_40]
0x180023982  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180023987  nop
0x180023988  mov     ebx, 75h ; 'u'
0x18002398d  mov     r9d, 400000h; unsigned int
0x180023993  mov     r8d, ebx; unsigned int
0x180023996  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002399d  lea     rcx, [rbp+57h+var_40]; this
0x1800239a1  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x1800239a6  nop
0x1800239a7  lea     rcx, [rbp+57h+var_40]; this
0x1800239ab  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x1800239b0  xor     r9d, r9d; unsigned int
0x1800239b3  mov     r8d, ebx; unsigned int
0x1800239b6  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x1800239bd  lea     rcx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800239c4  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800239ca  mov     r8d, 2; dwAclRevision
0x1800239d0  mov     edx, ebx; nAclLength
0x1800239d2  mov     rcx, rax; pAcl
0x1800239d5  call    cs:__imp_InitializeAcl
0x1800239db  test    eax, eax
0x1800239dd  jnz     loc_180023AB7
0x1800239e3  call    cs:__imp_GetLastError
0x1800239e9  mov     r9d, eax
0x1800239ec  test    eax, eax
0x1800239ee  jle     short loc_1800239FB
0x1800239f0  movzx   r9d, ax
0x1800239f4  or      r9d, 80070000h
0x1800239fb  mov     [rbp+57h+var_38], r12
0x1800239ff  or      eax, 0FFFFFFFFh
0x180023a02  mov     [rsp+0F0h+var_50], eax
0x180023a09  mov     [rsp+0F0h+var_58], eax
0x180023a10  mov     [rsp+0F0h+var_70], r12d
0x180023a18  mov     [rsp+0F0h+var_78], r12
0x180023a1d  mov     [rsp+0F0h+var_80], eax
0x180023a21  mov     [rsp+0F0h+var_88], eax
0x180023a25  mov     [rsp+0F0h+var_90], r12d
  ... truncated ...
```
