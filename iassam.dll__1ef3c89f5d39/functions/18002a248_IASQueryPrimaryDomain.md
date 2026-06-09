# IASQueryPrimaryDomain

- ea: `0x18002a248`
- end: `0x18002a73f`
- name: `IASQueryPrimaryDomain`
- size: `1271`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18002a088`
- `0x18002a7a0`

## callees

- `0x18000c4a4`
- `0x18000e754`
- `0x1800254a0`
- `0x18002a248`
- `0x18002addc`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18002a48a`
- `msvcrt!_wcsupr` at `0x18002a48a`
- `msvcrt!wcscat_s` at `0x18002a5dd`
- `msvcrt!wcscat_s` at `0x18002a5dd`
- `msvcrt!wcscpy_s` at `0x18002a5c8`
- `msvcrt!wcscpy_s` at `0x18002a617`
- `msvcrt!wcscpy_s` at `0x18002a6b1`
- `msvcrt!wcscpy_s` at `0x18002a5c8`
- `msvcrt!wcscpy_s` at `0x18002a617`
- `msvcrt!wcscpy_s` at `0x18002a6b1`
- `msvcrt!wcsncpy_s` at `0x18002a3df`
- `msvcrt!wcsncpy_s` at `0x18002a683`
- `msvcrt!wcsncpy_s` at `0x18002a3df`
- `msvcrt!wcsncpy_s` at `0x18002a683`
- `ntdll!RtlEqualSid` at `0x18002a3f7`
- `ntdll!RtlEqualSid` at `0x18002a3f7`
- `ntdll!RtlNtStatusToDosError` at `0x18002a716`
- `ntdll!RtlNtStatusToDosError` at `0x18002a716`
- `KERNEL32!LeaveCriticalSection` at `0x18002a703`
- `KERNEL32!LeaveCriticalSection` at `0x18002a703`
- `KERNEL32!EnterCriticalSection` at `0x18002a2b9`
- `KERNEL32!EnterCriticalSection` at `0x18002a2b9`
- `ADVAPI32!LsaFreeMemory` at `0x18002a355`
- `ADVAPI32!LsaFreeMemory` at `0x18002a355`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002a2d6`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002a2d6`
- `ADVAPI32!LsaOpenPolicy` at `0x18002a2a2`
- `ADVAPI32!LsaOpenPolicy` at `0x18002a2a2`
- `ADVAPI32!LsaClose` at `0x18002a70e`
- `ADVAPI32!LsaClose` at `0x18002a70e`
- `SAMLIB!SamQueryInformationUser` at `0x18002a664`
- `SAMLIB!SamQueryInformationUser` at `0x18002a664`
- `SAMLIB!SamFreeMemory` at `0x18002a68e`
- `SAMLIB!SamFreeMemory` at `0x18002a68e`
- `SAMLIB!SamCloseHandle` at `0x18002a699`
- `SAMLIB!SamCloseHandle` at `0x18002a699`

## pseudocode

```c
ULONG IASQueryPrimaryDomain()
{
  int v0; // ebx
  const wchar_t **v1; // r8
  __int64 v2; // rdx
  PVOID *v3; // rcx
  int v4; // r9d
  int v5; // r9d
  wchar_t *v6; // r8
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rax
  wchar_t *v10; // r15
  rsize_t v11; // r14
  int v12; // r9d
  PVOID Buffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  PVOID PolicyHandle; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[280]; // [rsp+70h] [rbp-90h] BYREF

  PolicyHandle = 0;
  v17 = 0;
  v16 = 0;
  Buffer = 0;
  v0 = LsaOpenPolicy(0, &theObjectAttributes, 1u, &PolicyHandle);
  if ( v0 >= 0 )
  {
    EnterCriticalSection(&critSec);
    Buffer = 0;
    v0 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v0 < 0 )
    {
LABEL_55:
      LeaveCriticalSection(&critSec);
      LsaClose(PolicyHandle);
      return RtlNtStatusToDosError(v0);
    }
    v1 = (const wchar_t **)Buffer;
    if ( !Buffer )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("LsaQueryInformationPolicy succeeded with NULL buffer for PolicyDnsDomainInformation");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids, "NPSSVC");
      }
      v0 = -1073741823;
      goto LABEL_55;
    }
    if ( ppdi )
    {
      LsaFreeMemory(ppdi);
      v1 = (const wchar_t **)Buffer;
    }
    ppdi = v1;
    if ( v1[8] )
    {
      wcsncpy_s(&thePrimaryDomain, 0x10u, v1[1], 0xFu);
      if ( RtlEqualSid(*((PSID *)ppdi + 8), theAccountDomainSid) )
      {
        ourRole = 2;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_26;
        }
        WppDbgPrint("Role: Domain Controller");
        v2 = 12;
      }
      else
      {
        ourRole = 1;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_26;
        }
        WppDbgPrint("Role: Domain member");
        v2 = 13;
      }
    }
    else
    {
      thePrimaryDomain = 0;
      ourRole = 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_26;
      }
      WppDbgPrint("Role: Standalone");
      v2 = 11;
    }
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids, "NPSSVC");
LABEL_26:
    _wcsupr(&thePrimaryDomain);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Primary domain: %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids,
        v4,
        (__int64)&thePrimaryDomain);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    theDnsDomainName = (__int64)ppdi + 16;
    if ( *((_QWORD *)ppdi + 3)
      && v3 != &WPP_GLOBAL_Control
      && *((_BYTE *)v3 + 25) >= 4u
      && (*((_BYTE *)v3 + 28) & 4) != 0 )
    {
      WppDbgPrint("Dns Domain name: %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids,
        v5,
        *(_QWORD *)(theDnsDomainName + 8));
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ourProductType && ourRole )
    {
      v6 = (wchar_t *)&theRegistryDomain;
      if ( !*(_WORD *)&theRegistryDomain )
        v6 = &thePrimaryDomain;
    }
    else
    {
      v6 = &theAccountDomain;
    }
    theDefaultDomain = v6;
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 4u && (*((_BYTE *)v3 + 28) & 4) != 0 )
    {
      WppDbgPrint("Default domain: %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids,
        v7,
        (__int64)theDefaultDomain);
      v6 = theDefaultDomain;
    }
    wcscpy_s(Destination, 0x111u, v6);
    wcscat_s(Destination, 0x111u, L"\\");
    v8 = -1;
    do
      ++v8;
    while ( Destination[v8] );
    v9 = v8;
    v10 = &Destination[v9];
    v11 = 273 - ((v9 * 2) >> 1);
    wcscpy_s(&Destination[v9], v11, L"Guest");
    LODWORD(v15) = 501;
    if ( !(unsigned int)IASSamOpenUser(theDefaultDomain, (__int64)&v15, 0, (__int64)&v17) )
    {
      if ( (int)SamQueryInformationUser(v17, 7, &v16) >= 0 )
      {
        wcsncpy_s(v10, v11, *(const wchar_t **)(v16 + 8), 0x100u);
        SamFreeMemory(v16);
      }
      SamCloseHandle(v17);
    }
    wcscpy_s(&theGuestAccount, 0x111u, Destination);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Guest account: %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids,
        v12,
        (__int64)&theGuestAccount);
    }
    v0 = 0;
    goto LABEL_55;
  }
  return RtlNtStatusToDosError(v0);
}

```

## disassembly

```asm
0x18002a248  push    rbp
0x18002a24a  push    rbx
0x18002a24b  push    rsi
0x18002a24c  push    rdi
0x18002a24d  push    r12
0x18002a24f  push    r13
0x18002a251  push    r14
0x18002a253  push    r15
0x18002a255  lea     rbp, [rsp-1B8h]
0x18002a25d  sub     rsp, 2B8h
0x18002a264  mov     rax, cs:__security_cookie
0x18002a26b  xor     rax, rsp
0x18002a26e  mov     [rbp+1F0h+var_50], rax
0x18002a275  xor     r12d, r12d
0x18002a278  lea     r9, [rsp+2F0h+PolicyHandle]; PolicyHandle
0x18002a27d  lea     rdx, theObjectAttributes; ObjectAttributes
0x18002a284  mov     [rsp+2F0h+PolicyHandle], r12
0x18002a289  xor     ecx, ecx; SystemName
0x18002a28b  mov     [rsp+2F0h+var_298], r12
0x18002a290  mov     [rsp+2F0h+var_2A0], r12
0x18002a295  lea     edi, [r12+1]
0x18002a29a  mov     [rsp+2F0h+Buffer], r12
0x18002a29f  mov     r8d, edi; DesiredAccess
0x18002a2a2  call    cs:__imp_LsaOpenPolicy
0x18002a2a8  mov     ebx, eax
0x18002a2aa  test    eax, eax
0x18002a2ac  js      loc_18002A714
0x18002a2b2  lea     rcx, critSec; lpCriticalSection
0x18002a2b9  call    cs:__imp_EnterCriticalSection
0x18002a2bf  mov     rcx, [rsp+2F0h+PolicyHandle]; PolicyHandle
0x18002a2c4  lea     r15d, [r12+0Ch]
0x18002a2c9  mov     edx, r15d; InformationClass
0x18002a2cc  mov     [rsp+2F0h+Buffer], r12
0x18002a2d1  lea     r8, [rsp+2F0h+Buffer]; Buffer
0x18002a2d6  call    cs:__imp_LsaQueryInformationPolicy
0x18002a2dc  mov     ebx, eax
0x18002a2de  test    eax, eax
0x18002a2e0  js      loc_18002A6FC
0x18002a2e6  mov     r8, [rsp+2F0h+Buffer]
0x18002a2eb  test    r8, r8
0x18002a2ee  jnz     short loc_18002A349
0x18002a2f0  mov     rax, cs:WPP_GLOBAL_Control
0x18002a2f7  lea     rdi, WPP_GLOBAL_Control
0x18002a2fe  cmp     rax, rdi
0x18002a301  jz      short loc_18002A33F
0x18002a303  cmp     byte ptr [rax+19h], 2
0x18002a307  jb      short loc_18002A33F
0x18002a309  mov     bl, 4
0x18002a30b  test    [rax+1Ch], bl
0x18002a30e  jz      short loc_18002A33F
0x18002a310  lea     rcx, aLsaqueryinform_0; "LsaQueryInformationPolicy succeeded wit"...
0x18002a317  call    WppDbgPrint
0x18002a31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a323  lea     edx, [r12+0Ah]
0x18002a328  lea     r9, aNpssvc; "NPSSVC"
0x18002a32f  lea     r8, WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids
0x18002a336  mov     rcx, [rcx+10h]
0x18002a33a  call    WPP_SF_s
0x18002a33f  mov     ebx, 0C0000001h
0x18002a344  jmp     loc_18002A6FC
0x18002a349  mov     rcx, cs:ppdi; Buffer
0x18002a350  test    rcx, rcx
0x18002a353  jz      short loc_18002A360
0x18002a355  call    cs:__imp_LsaFreeMemory
0x18002a35b  mov     r8, [rsp+2F0h+Buffer]
0x18002a360  lea     rsi, WPP_de1ad516b02f3a8a0ddcf6632b48c879_Traceguids
0x18002a367  mov     cs:ppdi, r8
0x18002a36e  lea     r14, thePrimaryDomain
0x18002a375  mov     bl, 4
0x18002a377  mov     r13d, 0Fh
0x18002a37d  cmp     [r8+40h], r12
0x18002a381  jnz     short loc_18002A3D0
0x18002a383  mov     cs:thePrimaryDomain, r12w
0x18002a38b  mov     cs:ourRole, r12d
0x18002a392  mov     rax, cs:WPP_GLOBAL_Control
0x18002a399  lea     rdi, WPP_GLOBAL_Control
0x18002a3a0  cmp     rax, rdi
0x18002a3a3  jz      loc_18002A487
0x18002a3a9  cmp     [rax+19h], bl
0x18002a3ac  jb      loc_18002A487
0x18002a3b2  test    [rax+1Ch], bl
0x18002a3b5  jz      loc_18002A487
0x18002a3bb  lea     rcx, aRoleStandalone; "Role: Standalone"
0x18002a3c2  call    WppDbgPrint
0x18002a3c7  lea     edx, [r13-4]
0x18002a3cb  jmp     loc_18002A46D
0x18002a3d0  mov     r8, [r8+8]; Source
0x18002a3d4  mov     r9, r13; MaxCount
0x18002a3d7  mov     edx, 10h; SizeInWords
0x18002a3dc  mov     rcx, r14; Destination
0x18002a3df  call    cs:__imp_wcsncpy_s
0x18002a3e5  mov     rcx, cs:ppdi
0x18002a3ec  mov     rdx, cs:theAccountDomainSid; Sid2
0x18002a3f3  mov     rcx, [rcx+40h]; Sid1
0x18002a3f7  call    cs:__imp_RtlEqualSid
0x18002a3fd  test    al, al
0x18002a3ff  jz      short loc_18002A439
0x18002a401  mov     cs:ourRole, 2
0x18002a40b  mov     rax, cs:WPP_GLOBAL_Control
0x18002a412  lea     rdi, WPP_GLOBAL_Control
0x18002a419  cmp     rax, rdi
0x18002a41c  jz      short loc_18002A487
0x18002a41e  cmp     [rax+19h], bl
0x18002a421  jb      short loc_18002A487
0x18002a423  test    [rax+1Ch], bl
0x18002a426  jz      short loc_18002A487
0x18002a428  lea     rcx, aRoleDomainCont; "Role: Domain Controller"
0x18002a42f  call    WppDbgPrint
0x18002a434  mov     edx, r15d
0x18002a437  jmp     short loc_18002A46D
0x18002a439  mov     cs:ourRole, edi
0x18002a43f  mov     rax, cs:WPP_GLOBAL_Control
0x18002a446  lea     rdi, WPP_GLOBAL_Control
0x18002a44d  cmp     rax, rdi
0x18002a450  jz      short loc_18002A487
0x18002a452  cmp     [rax+19h], bl
0x18002a455  jb      short loc_18002A487
0x18002a457  test    [rax+1Ch], bl
0x18002a45a  jz      short loc_18002A487
0x18002a45c  lea     rcx, aRoleDomainMemb; "Role: Domain member"
0x18002a463  call    WppDbgPrint
0x18002a468  mov     edx, 0Dh
0x18002a46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a474  lea     r9, aNpssvc; "NPSSVC"
0x18002a47b  mov     r8, rsi
0x18002a47e  mov     rcx, [rcx+10h]
0x18002a482  call    WPP_SF_s
0x18002a487  mov     rcx, r14; String
0x18002a48a  call    cs:__imp__wcsupr
0x18002a490  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a497  cmp     rcx, rdi
0x18002a49a  jz      short loc_18002A4D9
0x18002a49c  cmp     [rcx+19h], bl
0x18002a49f  jb      short loc_18002A4D9
0x18002a4a1  test    [rcx+1Ch], bl
0x18002a4a4  jz      short loc_18002A4D9
0x18002a4a6  mov     rdx, r14
0x18002a4a9  lea     rcx, aPrimaryDomainS; "Primary domain: %S"
0x18002a4b0  call    WppDbgPrint
0x18002a4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4bc  mov     edx, 0Eh
0x18002a4c1  mov     r8, rsi
0x18002a4c4  mov     [rsp+2F0h+var_2D0], r14
0x18002a4c9  mov     rcx, [rcx+10h]
0x18002a4cd  call    WPP_SF_sS
0x18002a4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4d9  mov     rax, cs:ppdi
0x18002a4e0  add     rax, 10h
0x18002a4e4  mov     cs:theDnsDomainName, rax
0x18002a4eb  mov     rdx, [rax+8]
0x18002a4ef  test    rdx, rdx
0x18002a4f2  jz      short loc_18002A53C
0x18002a4f4  cmp     rcx, rdi
0x18002a4f7  jz      short loc_18002A53C
0x18002a4f9  cmp     [rcx+19h], bl
0x18002a4fc  jb      short loc_18002A53C
0x18002a4fe  test    [rcx+1Ch], bl
0x18002a501  jz      short loc_18002A53C
0x18002a503  lea     rcx, aDnsDomainNameS; "Dns Domain name: %S"
0x18002a50a  call    WppDbgPrint
0x18002a50f  mov     rax, cs:theDnsDomainName
0x18002a516  mov     edx, r13d
0x18002a519  mov     r8, rsi
0x18002a51c  mov     rcx, [rax+8]
0x18002a520  mov     [rsp+2F0h+var_2D0], rcx
0x18002a525  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a52c  mov     rcx, [rcx+10h]
0x18002a530  call    WPP_SF_sS
0x18002a535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a53c  cmp     cs:ourProductType, r12d
0x18002a543  jz      short loc_18002A54E
0x18002a545  cmp     cs:ourRole, r12d
0x18002a54c  jnz     short loc_18002A557
0x18002a54e  lea     r8, theAccountDomain
0x18002a555  jmp     short loc_18002A56A
0x18002a557  cmp     cs:theRegistryDomain, r12w
0x18002a55f  lea     r8, theRegistryDomain
0x18002a566  cmovz   r8, r14
0x18002a56a  mov     cs:theDefaultDomain, r8
0x18002a571  cmp     rcx, rdi
0x18002a574  jz      short loc_18002A5BA
0x18002a576  cmp     [rcx+19h], bl
0x18002a579  jb      short loc_18002A5BA
0x18002a57b  test    [rcx+1Ch], bl
0x18002a57e  jz      short loc_18002A5BA
0x18002a580  mov     rdx, r8
0x18002a583  lea     rcx, aDefaultDomainS; "Default domain: %S"
0x18002a58a  call    WppDbgPrint
0x18002a58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a596  mov     edx, 10h
0x18002a59b  mov     rax, cs:theDefaultDomain
0x18002a5a2  mov     r8, rsi
0x18002a5a5  mov     [rsp+2F0h+var_2D0], rax
0x18002a5aa  mov     rcx, [rcx+10h]
0x18002a5ae  call    WPP_SF_sS
0x18002a5b3  mov     r8, cs:theDefaultDomain; Source
0x18002a5ba  mov     r13d, 111h
0x18002a5c0  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18002a5c5  mov     edx, r13d; SizeInWords
0x18002a5c8  call    cs:__imp_wcscpy_s
0x18002a5ce  lea     r8, asc_180033B18; "\\"
0x18002a5d5  mov     edx, r13d; SizeInWords
0x18002a5d8  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18002a5dd  call    cs:__imp_wcscat_s
0x18002a5e3  lea     rcx, [rsp+2F0h+Destination]
0x18002a5e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a5ec  inc     rax
0x18002a5ef  cmp     [rcx+rax*2], r12w
0x18002a5f4  jnz     short loc_18002A5EC
0x18002a5f6  add     rax, rax
0x18002a5f9  lea     r15, [rsp+2F0h+Destination]
0x18002a5fe  add     r15, rax
0x18002a601  lea     r8, aGuest; "Guest"
0x18002a608  sar     rax, 1
0x18002a60b  mov     r14, r13
0x18002a60e  sub     r14, rax
0x18002a611  mov     rcx, r15; Destination
0x18002a614  mov     rdx, r14; SizeInWords
0x18002a617  call    cs:__imp_wcscpy_s
0x18002a61d  mov     rcx, cs:theDefaultDomain; Source
0x18002a624  lea     rax, [rsp+2F0h+var_298]
0x18002a629  mov     [rsp+2F0h+var_2C0], rax; __int64
0x18002a62e  xor     r9d, r9d
0x18002a631  lea     rax, [rsp+2F0h+var_2A8]
0x18002a636  mov     [rsp+2F0h+var_2C8], r12; __int64
0x18002a63b  xor     edx, edx
0x18002a63d  mov     dword ptr [rsp+2F0h+var_2A8], 1F5h
0x18002a645  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18002a64a  lea     r8d, [r9+1]
0x18002a64e  call    IASSamOpenUser
0x18002a653  test    eax, eax
0x18002a655  jnz     short loc_18002A69F
0x18002a657  mov     rcx, [rsp+2F0h+var_298]
0x18002a65c  lea     r8, [rsp+2F0h+var_2A0]
0x18002a661  lea     edx, [rax+7]
0x18002a664  call    cs:__imp_SamQueryInformationUser
0x18002a66a  test    eax, eax
0x18002a66c  js      short loc_18002A694
0x18002a66e  mov     r8, [rsp+2F0h+var_2A0]
0x18002a673  mov     r9d, 100h; MaxCount
0x18002a679  mov     rdx, r14; SizeInWords
0x18002a67c  mov     rcx, r15; Destination
0x18002a67f  mov     r8, [r8+8]; Source
0x18002a683  call    cs:__imp_wcsncpy_s
0x18002a689  mov     rcx, [rsp+2F0h+var_2A0]
0x18002a68e  call    cs:__imp_SamFreeMemory
0x18002a694  mov     rcx, [rsp+2F0h+var_298]
0x18002a699  call    cs:__imp_SamCloseHandle
0x18002a69f  lea     r14, theGuestAccount
0x18002a6a6  mov     rdx, r13; SizeInWords
0x18002a6a9  mov     rcx, r14; Destination
0x18002a6ac  lea     r8, [rsp+2F0h+Destination]; Source
0x18002a6b1  call    cs:__imp_wcscpy_s
0x18002a6b7  mov     rax, cs:WPP_GLOBAL_Control
0x18002a6be  cmp     rax, rdi
0x18002a6c1  jz      short loc_18002A6F9
0x18002a6c3  cmp     [rax+19h], bl
0x18002a6c6  jb      short loc_18002A6F9
0x18002a6c8  test    [rax+1Ch], bl
0x18002a6cb  jz      short loc_18002A6F9
0x18002a6cd  mov     rdx, r14
0x18002a6d0  lea     rcx, aGuestAccountS; "Guest account: %S"
0x18002a6d7  call    WppDbgPrint
0x18002a6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6e3  mov     edx, 11h
0x18002a6e8  mov     r8, rsi
0x18002a6eb  mov     [rsp+2F0h+var_2D0], r14
0x18002a6f0  mov     rcx, [rcx+10h]
0x18002a6f4  call    WPP_SF_sS
0x18002a6f9  mov     ebx, r12d
0x18002a6fc  lea     rcx, critSec; lpCriticalSection
0x18002a703  call    cs:__imp_LeaveCriticalSection
0x18002a709  mov     rcx, [rsp+2F0h+PolicyHandle]; ObjectHandle
0x18002a70e  call    cs:__imp_LsaClose
0x18002a714  mov     ecx, ebx; Status
0x18002a716  call    cs:__imp_RtlNtStatusToDosError
0x18002a71c  mov     rcx, [rbp+1F0h+var_50]
0x18002a723  xor     rcx, rsp; StackCookie
0x18002a726  call    __security_check_cookie
0x18002a72b  add     rsp, 2B8h
0x18002a732  pop     r15
0x18002a734  pop     r14
0x18002a736  pop     r13
0x18002a738  pop     r12
0x18002a73a  pop     rdi
0x18002a73b  pop     rsi
0x18002a73c  pop     rbx
0x18002a73d  pop     rbp
0x18002a73e  retn
```
