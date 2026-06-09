# IdentityHelper::initialize(void)

- ea: `0x1800235fc`
- end: `0x180023b51`
- name: `?initialize@IdentityHelper@@QEAAJXZ`
- size: `1365`
- prototype: `__int64 __fastcall(IdentityHelper *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180020e00`

## callees

- `0x18000342c`
- `0x18000aae0`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000e754`
- `0x18001426c`
- `0x180022ef0`
- `0x1800235fc`
- `0x1800254a0`

## import_xrefs

- `msvcrt!free` at `0x1800237f8`
- `msvcrt!free` at `0x1800237f8`
- `ADVAPI32!RegCloseKey` at `0x1800239fe`
- `ADVAPI32!RegCloseKey` at `0x1800239fe`
- `ADVAPI32!RegOpenKeyExW` at `0x180023650`
- `ADVAPI32!RegOpenKeyExW` at `0x180023650`
- `ADVAPI32!RegQueryValueExW` at `0x180023764`
- `ADVAPI32!RegQueryValueExW` at `0x1800237e1`
- `ADVAPI32!RegQueryValueExW` at `0x180023764`
- `ADVAPI32!RegQueryValueExW` at `0x1800237e1`

## string_xrefs

- `0x180023681`: `Cannot open the reg key %S, error %ld`
- `0x180023991`: `Cannot read value %S.  error %ld`
- `0x18002392d`: `Cannot read value %S.  Wrong type %ld`
- `0x1800238f9`: `Cannot read value %S.  Wrong Size = %ld`
- `0x18002384e`: `Failed to read the value %S. Error is %ld`
- `0x18002363f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
__int64 __fastcall IdentityHelper::initialize(IdentityHelper *this)
{
  IdentityHelper *v2; // rcx
  LSTATUS v3; // ebx
  int v4; // r9d
  IdentityHelper *v5; // rcx
  signed int v6; // edi
  LSTATUS Value; // ebx
  unsigned __int128 v8; // rax
  BYTE *v9; // rax
  LSTATUS v10; // ebx
  PVOID *v11; // rax
  int v12; // r9d
  int v13; // r9d
  int v14; // edx
  char v15; // al
  int v16; // r9d
  const char *v17; // rbx
  const wchar_t *v18; // rbx
  int v19; // r9d
  IdentityHelper *Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = this;
  if ( IdentityHelper::initialized )
    return 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
         0,
         0x20019u,
         &hKey);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Cannot open the reg key %S, error %ld");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
        v4,
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
        v3);
    }
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
    return (unsigned int)v3;
  }
  v6 = IdentityHelper::IASReadRegistryDword(v2, &hKey, L"User Identity Attribute", 1u, &qword_18003FB04);
  if ( v6 < 0
    || (v6 = IdentityHelper::IASReadRegistryDword(v5, &hKey, L"Override User-Name", 0, &NameMapper::identityHelper),
        v6 < 0) )
  {
LABEL_51:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  LODWORD(Type) = 0;
  cbData = 0;
  Value = RegQueryValueExW(hKey, L"Default User Identity", 0, (LPDWORD)&Type, 0, &cbData);
  if ( Value )
  {
    if ( Value != 2 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S.  error %ld");
        WPP_SF_sSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
          v16,
          (__int64)L"Default User Identity",
          Value);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( Value > 0 )
        v6 = (unsigned __int16)Value | 0x80070000;
      else
        v6 = Value;
      goto LABEL_52;
    }
    *(_QWORD *)(&qword_18003FB04 + 1) = 0;
    cbData = 0;
    goto LABEL_51;
  }
  if ( (_DWORD)Type != 1 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_41;
    }
    WppDbgPrint("Cannot read value %S.  Wrong type %ld");
    v14 = 15;
    v15 = (char)Type;
    goto LABEL_40;
  }
  if ( cbData >= 2 )
  {
    v8 = ((unsigned __int64)cbData >> 1) * (unsigned __int128)2u;
    if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
      *(_QWORD *)&v8 = -1;
    v9 = (BYTE *)operator new[](v8, *((const struct std::nothrow_t **)&v8 + 1));
    *(_QWORD *)(&qword_18003FB04 + 1) = v9;
    if ( !v9 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Default Identity could not be retrieved due toout of memory condition.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids, "NPSSVC");
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      cbData = 0;
      v6 = -2147024882;
      goto LABEL_52;
    }
    v10 = RegQueryValueExW(hKey, L"Default User Identity", 0, (LPDWORD)&Type, v9, &cbData);
    if ( v10 )
    {
      free(*(void **)(&qword_18003FB04 + 1));
      *(_QWORD *)(&qword_18003FB04 + 1) = 0;
      cbData = 0;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      else
        v6 = v10;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_52;
      }
      WppDbgPrint("Failed to read the value %S. Error is %ld");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
        v12,
        (__int64)L"Default User Identity",
        v10);
    }
    goto LABEL_51;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Cannot read value %S.  Wrong Size = %ld");
    v14 = 16;
    v15 = cbData;
LABEL_40:
    WPP_SF_sSl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
      v13,
      (__int64)L"Default User Identity",
      v15);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_41:
  v6 = -2147024809;
LABEL_52:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
    if ( v11 != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)v11 + 25) >= 4u && (*((_BYTE *)v11 + 28) & 4) != 0 )
      {
        WppDbgPrint("User identity attribute: %lu");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)v11 + 25) >= 4u && (*((_BYTE *)v11 + 28) & 4) != 0 )
        {
          v17 = "TRUE";
          WppDbgPrint("Override User-Name: %s");
          if ( !NameMapper::identityHelper )
            v17 = "FALSE";
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
            (unsigned int)"NPSSVC",
            (__int64)v17);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 4u && (*((_BYTE *)v11 + 28) & 4) != 0 )
        {
          v18 = L"<Guest>";
          WppDbgPrint("Default user identity: %S");
          if ( *(_QWORD *)(&qword_18003FB04 + 1) )
            v18 = *(const wchar_t **)(&qword_18003FB04 + 1);
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
            v19,
            (__int64)v18);
        }
      }
    }
    IdentityHelper::initialized = 1;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800235fc  mov     [rsp-28h+arg_10], rbx
0x180023601  mov     [rsp-28h+Type], rcx
0x180023606  push    rbp
0x180023607  push    rdi
0x180023608  push    r12
0x18002360a  push    r14
0x18002360c  push    r15
0x18002360e  mov     rbp, rsp
0x180023611  sub     rsp, 30h
0x180023615  cmp     cs:?initialized@IdentityHelper@@0_NA, 0; bool IdentityHelper::initialized
0x18002361c  jz      short loc_180023625
0x18002361e  xor     eax, eax
0x180023620  jmp     loc_180023B3F
0x180023625  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x18002362d  lea     rax, [rbp+hKey]
0x180023631  mov     [rsp+30h+phkResult], rax; phkResult
0x180023636  mov     r9d, 20019h; samDesired
0x18002363c  xor     r8d, r8d; ulOptions
0x18002363f  lea     rdi, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180023646  mov     rdx, rdi; lpSubKey
0x180023649  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023650  call    cs:__imp_RegOpenKeyExW
0x180023656  mov     ebx, eax
0x180023658  test    eax, eax
0x18002365a  jz      short loc_1800236C6
0x18002365c  lea     r14, WPP_GLOBAL_Control
0x180023663  mov     rax, cs:WPP_GLOBAL_Control
0x18002366a  cmp     rax, r14
0x18002366d  jz      short loc_1800236B2
0x18002366f  cmp     byte ptr [rax+19h], 2
0x180023673  jb      short loc_1800236B2
0x180023675  test    byte ptr [rax+1Ch], 4
0x180023679  jz      short loc_1800236B2
0x18002367b  mov     r8d, ebx
0x18002367e  mov     rdx, rdi
0x180023681  lea     rcx, aCannotOpenTheR; "Cannot open the reg key %S, error %ld"
0x180023688  call    WppDbgPrint
0x18002368d  mov     edx, 0Dh
0x180023692  mov     dword ptr [rsp+30h+lpcbData], ebx
0x180023696  mov     [rsp+30h+phkResult], rdi
0x18002369b  lea     r8, WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids
0x1800236a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236a9  mov     rcx, [rcx+10h]
0x1800236ad  call    WPP_SF_sSl
0x1800236b2  test    ebx, ebx
0x1800236b4  jle     short loc_1800236BF
0x1800236b6  movzx   ebx, bx
0x1800236b9  or      ebx, 80070000h
0x1800236bf  mov     eax, ebx
0x1800236c1  jmp     loc_180023B3F
0x1800236c6  lea     rax, qword_18003FB04
0x1800236cd  mov     [rsp+30h+phkResult], rax; unsigned int *
0x1800236d2  mov     r9d, 1; unsigned int
0x1800236d8  lea     r8, aUserIdentityAt_0; "User Identity Attribute"
0x1800236df  lea     rdx, [rbp+hKey]; HKEY *
0x1800236e3  call    ?IASReadRegistryDword@IdentityHelper@@IEAAJAEAPEAUHKEY__@@PEBGKPEAK@Z; IdentityHelper::IASReadRegistryDword(HKEY__ * &,ushort const *,ulong,ulong *)
0x1800236e8  mov     edi, eax
0x1800236ea  lea     r15, WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids
0x1800236f1  lea     r14, WPP_GLOBAL_Control
0x1800236f8  test    eax, eax
0x1800236fa  js      loc_1800239ED
0x180023700  lea     rax, ?identityHelper@NameMapper@@1VIdentityHelper@@A; IdentityHelper NameMapper::identityHelper
0x180023707  mov     [rsp+30h+phkResult], rax; unsigned int *
0x18002370c  xor     r9d, r9d; unsigned int
0x18002370f  lea     r8, aOverrideUserNa_0; "Override User-Name"
0x180023716  lea     rdx, [rbp+hKey]; HKEY *
0x18002371a  call    ?IASReadRegistryDword@IdentityHelper@@IEAAJAEAPEAUHKEY__@@PEBGKPEAK@Z; IdentityHelper::IASReadRegistryDword(HKEY__ * &,ushort const *,ulong,ulong *)
0x18002371f  mov     edi, eax
0x180023721  test    eax, eax
0x180023723  js      loc_1800239ED
0x180023729  mov     dword ptr [rbp+Type], 0
0x180023730  mov     cs:cbData, 0
0x18002373a  lea     rax, cbData
0x180023741  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180023746  mov     [rsp+30h+phkResult], 0; lpData
0x18002374f  lea     r9, [rbp+Type]; lpType
0x180023753  xor     r8d, r8d; lpReserved
0x180023756  lea     r12, aDefaultUserIde_0; "Default User Identity"
0x18002375d  mov     rdx, r12; lpValueName
0x180023760  mov     rcx, [rbp+hKey]; hKey
0x180023764  call    cs:__imp_RegQueryValueExW
0x18002376a  mov     ebx, eax
0x18002376c  test    eax, eax
0x18002376e  jnz     loc_18002396E
0x180023774  mov     r8d, dword ptr [rbp+Type]
0x180023778  cmp     r8d, 1
0x18002377c  jnz     loc_180023912
0x180023782  mov     r8d, cs:cbData
0x180023789  cmp     r8d, 2
0x18002378d  jb      loc_1800238DE
0x180023793  mov     ecx, r8d
0x180023796  shr     rcx, 1
0x180023799  lea     eax, [rbx+2]
0x18002379c  mul     rcx
0x18002379f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800237a6  cmovb   rax, rcx
0x1800237aa  mov     rcx, rax; Size
0x1800237ad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800237b2  mov     cs:qword_18003FB04+4, rax
0x1800237b9  test    rax, rax
0x1800237bc  jz      loc_180023880
0x1800237c2  lea     rcx, cbData
0x1800237c9  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x1800237ce  mov     [rsp+30h+phkResult], rax; lpData
0x1800237d3  lea     r9, [rbp+Type]; lpType
0x1800237d7  xor     r8d, r8d; lpReserved
0x1800237da  mov     rdx, r12; lpValueName
0x1800237dd  mov     rcx, [rbp+hKey]; hKey
0x1800237e1  call    cs:__imp_RegQueryValueExW
0x1800237e7  mov     ebx, eax
0x1800237e9  test    eax, eax
0x1800237eb  jz      loc_1800239ED
0x1800237f1  mov     rcx, cs:qword_18003FB04+4; Block
0x1800237f8  call    cs:__imp_free
0x1800237fe  mov     cs:qword_18003FB04+4, 0
0x180023809  mov     cs:cbData, 0
0x180023813  test    ebx, ebx
0x180023815  jg      short loc_18002381B
0x180023817  mov     edi, ebx
0x180023819  jmp     short loc_180023824
0x18002381b  movzx   edi, bx
0x18002381e  or      edi, 80070000h
0x180023824  mov     rax, cs:WPP_GLOBAL_Control
0x18002382b  cmp     rax, r14
0x18002382e  jz      loc_1800239F4
0x180023834  cmp     byte ptr [rax+19h], 2
0x180023838  jb      loc_1800239F4
0x18002383e  test    byte ptr [rax+1Ch], 4
0x180023842  jz      loc_1800239F4
0x180023848  mov     r8d, ebx
0x18002384b  mov     rdx, r12
0x18002384e  lea     rcx, aFailedToReadTh; "Failed to read the value %S. Error is %"...
0x180023855  call    WppDbgPrint
0x18002385a  mov     edx, 12h
0x18002385f  mov     dword ptr [rsp+30h+lpcbData], ebx
0x180023863  mov     [rsp+30h+phkResult], r12
0x180023868  mov     r8, r15
0x18002386b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023872  mov     rcx, [rcx+10h]
0x180023876  call    WPP_SF_sSl
0x18002387b  jmp     loc_1800239ED
0x180023880  mov     rax, cs:WPP_GLOBAL_Control
0x180023887  cmp     rax, r14
0x18002388a  jz      short loc_1800238CA
0x18002388c  cmp     byte ptr [rax+19h], 2
0x180023890  jb      short loc_1800238CA
0x180023892  test    byte ptr [rax+1Ch], 4
0x180023896  jz      short loc_1800238CA
0x180023898  lea     rcx, aDefaultIdentit; "Default Identity could not be retrieved"...
0x18002389f  call    WppDbgPrint
0x1800238a4  mov     edx, 11h
0x1800238a9  lea     r9, aNpssvc; "NPSSVC"
0x1800238b0  mov     r8, r15
0x1800238b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238ba  mov     rcx, [rcx+10h]
0x1800238be  call    WPP_SF_s
0x1800238c3  mov     rax, cs:WPP_GLOBAL_Control
0x1800238ca  mov     cs:cbData, 0
0x1800238d4  mov     edi, 8007000Eh
0x1800238d9  jmp     loc_1800239F4
0x1800238de  mov     rax, cs:WPP_GLOBAL_Control
0x1800238e5  cmp     rax, r14
0x1800238e8  jz      short loc_180023964
0x1800238ea  cmp     byte ptr [rax+19h], 2
0x1800238ee  jb      short loc_180023964
0x1800238f0  test    byte ptr [rax+1Ch], 4
0x1800238f4  jz      short loc_180023964
0x1800238f6  mov     rdx, r12
0x1800238f9  lea     rcx, aCannotReadValu_2; "Cannot read value %S.  Wrong Size = %ld"
0x180023900  call    WppDbgPrint
0x180023905  mov     edx, 10h
0x18002390a  mov     eax, cs:cbData
0x180023910  jmp     short loc_180023941
0x180023912  mov     rax, cs:WPP_GLOBAL_Control
0x180023919  cmp     rax, r14
0x18002391c  jz      short loc_180023964
0x18002391e  cmp     byte ptr [rax+19h], 2
0x180023922  jb      short loc_180023964
0x180023924  test    byte ptr [rax+1Ch], 4
0x180023928  jz      short loc_180023964
0x18002392a  mov     rdx, r12
0x18002392d  lea     rcx, aCannotReadValu_0; "Cannot read value %S.  Wrong type %ld"
0x180023934  call    WppDbgPrint
0x180023939  mov     edx, 0Fh
0x18002393e  mov     eax, dword ptr [rbp+Type]
0x180023941  mov     dword ptr [rsp+30h+lpcbData], eax
0x180023945  mov     [rsp+30h+phkResult], r12
0x18002394a  mov     r8, r15
0x18002394d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023954  mov     rcx, [rcx+10h]
0x180023958  call    WPP_SF_sSl
0x18002395d  mov     rax, cs:WPP_GLOBAL_Control
0x180023964  mov     edi, 80070057h
0x180023969  jmp     loc_1800239F4
0x18002396e  cmp     ebx, 2
0x180023971  jz      short loc_1800239D8
0x180023973  mov     rax, cs:WPP_GLOBAL_Control
0x18002397a  cmp     rax, r14
0x18002397d  jz      short loc_1800239C5
0x18002397f  cmp     byte ptr [rax+19h], 2
0x180023983  jb      short loc_1800239C5
0x180023985  test    byte ptr [rax+1Ch], 4
0x180023989  jz      short loc_1800239C5
0x18002398b  mov     r8d, ebx
0x18002398e  mov     rdx, r12
0x180023991  lea     rcx, aCannotReadValu_1; "Cannot read value %S.  error %ld"
0x180023998  call    WppDbgPrint
0x18002399d  mov     edx, 0Eh
0x1800239a2  mov     dword ptr [rsp+30h+lpcbData], ebx
0x1800239a6  mov     [rsp+30h+phkResult], r12
0x1800239ab  mov     r8, r15
0x1800239ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239b5  mov     rcx, [rcx+10h]
0x1800239b9  call    WPP_SF_sSl
0x1800239be  mov     rax, cs:WPP_GLOBAL_Control
0x1800239c5  test    ebx, ebx
0x1800239c7  jg      short loc_1800239CD
0x1800239c9  mov     edi, ebx
0x1800239cb  jmp     short loc_1800239F4
0x1800239cd  movzx   edi, bx
0x1800239d0  or      edi, 80070000h
0x1800239d6  jmp     short loc_1800239F4
0x1800239d8  mov     cs:qword_18003FB04+4, 0
0x1800239e3  mov     cs:cbData, 0
0x1800239ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800239f4  mov     rcx, [rbp+hKey]; hKey
0x1800239f8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800239fc  jz      short loc_180023A0B
0x1800239fe  call    cs:__imp_RegCloseKey
0x180023a04  mov     rax, cs:WPP_GLOBAL_Control
0x180023a0b  test    edi, edi
0x180023a0d  js      loc_180023B3D
0x180023a13  cmp     rax, r14
0x180023a16  jz      loc_180023B36
0x180023a1c  cmp     byte ptr [rax+19h], 4
0x180023a20  jb      short loc_180023A63
0x180023a22  test    byte ptr [rax+1Ch], 4
0x180023a26  jz      short loc_180023A63
0x180023a28  mov     edx, dword ptr cs:qword_18003FB04
0x180023a2e  lea     rcx, aUserIdentityAt; "User identity attribute: %lu"
0x180023a35  call    WppDbgPrint
0x180023a3a  mov     edx, 13h
0x180023a3f  mov     eax, dword ptr cs:qword_18003FB04
0x180023a45  mov     dword ptr [rsp+30h+phkResult], eax
0x180023a49  mov     r8, r15
0x180023a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a53  mov     rcx, [rcx+10h]
0x180023a57  call    WPP_SF_sd
0x180023a5c  mov     rax, cs:WPP_GLOBAL_Control
0x180023a63  cmp     rax, r14
0x180023a66  jz      loc_180023B36
0x180023a6c  cmp     byte ptr [rax+19h], 4
0x180023a70  jb      short loc_180023AD6
0x180023a72  test    byte ptr [rax+1Ch], 4
0x180023a76  jz      short loc_180023AD6
0x180023a78  lea     rbx, aTrue_0; "TRUE"
0x180023a7f  mov     rdx, rbx
0x180023a82  lea     r12, aFalse_0; "FALSE"
0x180023a89  cmp     cs:?identityHelper@NameMapper@@1VIdentityHelper@@A, 0; IdentityHelper NameMapper::identityHelper
0x180023a90  cmovz   rdx, r12
0x180023a94  lea     rcx, aOverrideUserNa; "Override User-Name: %s"
0x180023a9b  call    WppDbgPrint
0x180023aa0  cmp     cs:?identityHelper@NameMapper@@1VIdentityHelper@@A, 0; IdentityHelper NameMapper::identityHelper
0x180023aa7  cmovz   rbx, r12
0x180023aab  mov     edx, 14h
0x180023ab0  mov     [rsp+30h+phkResult], rbx
0x180023ab5  lea     r9, aNpssvc; "NPSSVC"
0x180023abc  mov     r8, r15
0x180023abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ac6  mov     rcx, [rcx+10h]
0x180023aca  call    WPP_SF_ss
0x180023acf  mov     rax, cs:WPP_GLOBAL_Control
0x180023ad6  cmp     rax, r14
0x180023ad9  jz      short loc_180023B36
0x180023adb  cmp     byte ptr [rax+19h], 4
0x180023adf  jb      short loc_180023B36
0x180023ae1  test    byte ptr [rax+1Ch], 4
0x180023ae5  jz      short loc_180023B36
0x180023ae7  mov     rax, cs:qword_18003FB04+4
0x180023aee  lea     rbx, aGuest_0; "<Guest>"
0x180023af5  mov     rdx, rbx
0x180023af8  test    rax, rax
0x180023afb  cmovnz  rdx, rax
0x180023aff  lea     rcx, aDefaultUserIde; "Default user identity: %S"
0x180023b06  call    WppDbgPrint
0x180023b0b  mov     rax, cs:qword_18003FB04+4
0x180023b12  test    rax, rax
0x180023b15  cmovnz  rbx, rax
0x180023b19  mov     edx, 15h
0x180023b1e  mov     [rsp+30h+phkResult], rbx
0x180023b23  mov     r8, r15
0x180023b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b2d  mov     rcx, [rcx+10h]
0x180023b31  call    WPP_SF_sS
0x180023b36  mov     cs:?initialized@IdentityHelper@@0_NA, 1; bool IdentityHelper::initialized
0x180023b3d  mov     eax, edi
0x180023b3f  mov     rbx, [rsp+30h+arg_10]
0x180023b44  add     rsp, 30h
0x180023b48  pop     r15
0x180023b4a  pop     r14
  ... truncated ...
```
