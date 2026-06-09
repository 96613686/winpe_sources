# IsSharedMemoryModeDisabledForCurrentProcessDueToIL(void)

- ea: `0x1800369a0`
- end: `0x180036c8a`
- name: `?IsSharedMemoryModeDisabledForCurrentProcessDueToIL@@YA_NXZ`
- size: `746`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003686c`

## callees

- `0x1800369a0`
- `0x18003f9f0`
- `0x180042800`
- `0x180043100`
- `0x18004c868`
- `0x18004c928`
- `0x18004ca0c`

## import_xrefs

- `ntdll!RtlSidDominates` at `0x180036a99`
- `ntdll!RtlSidDominates` at `0x180036abd`
- `ntdll!RtlSidDominates` at `0x180036a99`
- `ntdll!RtlSidDominates` at `0x180036abd`
- `ntdll!RtlSubAuthoritySid` at `0x180036a49`
- `ntdll!RtlSubAuthoritySid` at `0x180036a7a`
- `ntdll!RtlSubAuthoritySid` at `0x180036b7f`
- `ntdll!RtlSubAuthoritySid` at `0x180036a49`
- `ntdll!RtlSubAuthoritySid` at `0x180036a7a`
- `ntdll!RtlSubAuthoritySid` at `0x180036b7f`
- `ntdll!RtlInitializeSid` at `0x180036a3d`
- `ntdll!RtlInitializeSid` at `0x180036a6e`
- `ntdll!RtlInitializeSid` at `0x180036b73`
- `ntdll!RtlInitializeSid` at `0x180036a3d`
- `ntdll!RtlInitializeSid` at `0x180036a6e`
- `ntdll!RtlInitializeSid` at `0x180036b73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036b3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036b3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036c59`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036a0a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036bff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036a0a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036bff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180036bb6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180036bb6`

## string_xrefs

- `0x180036ae1`: `Software\Microsoft\Ole\AppCompat`
- `0x180036afc`: `AllowStructuredStorageSharedMemoryModeForService`

## pseudocode

```c
char __fastcall IsSharedMemoryModeDisabledForCurrentProcessDueToIL(HKEY a1, __int64 a2, unsigned int a3)
{
  int v3; // eax
  const unsigned __int16 *v4; // rdx
  bool v5; // bl
  HANDLE v7; // rbx
  int v8; // eax
  char v9; // [rsp+30h] [rbp-D0h] BYREF
  char v10[3]; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v11; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WINBOOL IsMember; // [rsp+40h] [rbp-C0h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v15; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v21[80]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE SidToCheck[80]; // [rsp+170h] [rbp+70h] BYREF

  v3 = g_whichSharedMemoryDisabledProcessType;
  if ( !g_whichSharedMemoryDisabledProcessType )
  {
    memset_0(TokenInformation, 0, 0x58u);
    ReturnLength = 84;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, TokenInformation, 0x54u, &ReturnLength) )
      return 1;
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
    memset_0(Sid, 0, 0x44u);
    RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(Sid, 0) = 0x2000;
    memset_0(v21, 0, 0x44u);
    RtlInitializeSid(v21, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(v21, 0) = 12288;
    v9 = 1;
    RtlSidDominates(Sid, TokenInformation[0], &v9);
    if ( v9 )
    {
      v3 = 1;
      g_whichSharedMemoryDisabledProcessType = 1;
      goto LABEL_22;
    }
    v10[0] = 1;
    RtlSidDominates(v21, TokenInformation[0], v10);
    if ( !v10[0] )
    {
      g_whichSharedMemoryDisabledProcessType = 3;
      goto LABEL_6;
    }
    *(_DWORD *)v19.Value = 0;
    *(_WORD *)&v19.Value[4] = 1280;
    memset_0(SidToCheck, 0, 0x44u);
    RtlInitializeSid(SidToCheck, &v19, 1u);
    *RtlSubAuthoritySid(SidToCheck, 0) = 4;
    hObject = 0;
    if ( (int)SuspendImpersonate(&hObject) < 0 )
      return 1;
    v7 = hObject;
    IsMember = 0;
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
LABEL_15:
      ResumeImpersonate(v7);
      return 1;
    }
    if ( IsMember )
    {
      v11 = 0;
      v15 = 4;
      if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenElevationType, &v11, 4u, &v15) )
        goto LABEL_15;
      v8 = (v11 != 1) + 1;
    }
    else
    {
      v8 = 3;
    }
    g_whichSharedMemoryDisabledProcessType = v8;
    ResumeImpersonate(v7);
    v3 = g_whichSharedMemoryDisabledProcessType;
  }
LABEL_22:
  if ( v3 == 1 )
    return 0;
LABEL_6:
  hKey = 0;
  if ( RegistryKey::StaticOpen(a1, L"Software\\Microsoft\\Ole\\AppCompat", a3, &hKey) < 0 )
    goto LABEL_24;
  v4 = L"AllowStructuredStorageSharedMemoryModeForElevatedUser";
  v11 = 0;
  if ( g_whichSharedMemoryDisabledProcessType != 2 )
    v4 = L"AllowStructuredStorageSharedMemoryModeForService";
  if ( RegistryKey::ReadDWORDValue((RegistryKey *)&hKey, v4, &v11) < 0 )
  {
LABEL_24:
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    return 1;
  }
  v5 = v11 == 0;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800369a0  mov     [rsp-8+arg_0], rbx
0x1800369a5  mov     [rsp-8+arg_8], rdi
0x1800369aa  push    rbp
0x1800369ab  lea     rbp, [rsp-0D0h]
0x1800369b3  sub     rsp, 1D0h
0x1800369ba  mov     rax, cs:__security_cookie
0x1800369c1  xor     rax, rsp
0x1800369c4  mov     [rbp+0D0h+var_10], rax
0x1800369cb  mov     eax, cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x1800369d1  xor     edi, edi
0x1800369d3  test    eax, eax
0x1800369d5  jnz     loc_180036C3D
0x1800369db  xor     edx, edx; Val
0x1800369dd  lea     r8d, [rax+58h]; Size
0x1800369e1  lea     rcx, [rsp+1D0h+TokenInformation]; void *
0x1800369e6  call    memset_0
0x1800369eb  lea     r9d, [rdi+54h]; TokenInformationLength
0x1800369ef  lea     rax, [rsp+1D0h+var_18C]
0x1800369f4  mov     [rsp+1D0h+var_18C], r9d
0x1800369f9  lea     r8, [rsp+1D0h+TokenInformation]; TokenInformation
0x1800369fe  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x180036a03  lea     edx, [rdi+19h]; TokenInformationClass
0x180036a06  lea     rcx, [rdi-4]; TokenHandle
0x180036a0a  call    cs:__imp_GetTokenInformation
0x180036a10  test    eax, eax
0x180036a12  jz      loc_180036C64
0x180036a18  lea     ebx, [rdi+44h]
0x180036a1b  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], edi
0x180036a1e  mov     r8d, ebx; Size
0x180036a21  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 1000h
0x180036a27  xor     edx, edx; Val
0x180036a29  lea     rcx, [rbp+0D0h+Sid]; void *
0x180036a2d  call    memset_0
0x180036a32  mov     r8b, 1; SubAuthorityCount
0x180036a35  lea     rdx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x180036a39  lea     rcx, [rbp+0D0h+Sid]; Sid
0x180036a3d  call    cs:__imp_RtlInitializeSid
0x180036a43  xor     edx, edx; SubAuthority
0x180036a45  lea     rcx, [rbp+0D0h+Sid]; Sid
0x180036a49  call    cs:__imp_RtlSubAuthoritySid
0x180036a4f  mov     r8d, ebx; Size
0x180036a52  lea     rcx, [rbp+0D0h+var_B0]; void *
0x180036a56  xor     edx, edx; Val
0x180036a58  mov     dword ptr [rax], 2000h
0x180036a5e  call    memset_0
0x180036a63  mov     r8b, 1; SubAuthorityCount
0x180036a66  lea     rdx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x180036a6a  lea     rcx, [rbp+0D0h+var_B0]; Sid
0x180036a6e  call    cs:__imp_RtlInitializeSid
0x180036a74  xor     edx, edx; SubAuthority
0x180036a76  lea     rcx, [rbp+0D0h+var_B0]; Sid
0x180036a7a  call    cs:__imp_RtlSubAuthoritySid
0x180036a80  lea     r8, [rsp+1D0h+var_1A0]
0x180036a85  lea     rcx, [rbp+0D0h+Sid]
0x180036a89  mov     dword ptr [rax], 3000h
0x180036a8f  mov     rdx, [rsp+1D0h+TokenInformation]
0x180036a94  mov     [rsp+1D0h+var_1A0], 1
0x180036a99  call    cs:__imp_RtlSidDominates
0x180036a9f  cmp     [rsp+1D0h+var_1A0], dil
0x180036aa4  jnz     loc_180036C32
0x180036aaa  mov     rdx, [rsp+1D0h+TokenInformation]
0x180036aaf  lea     r8, [rsp+1D0h+var_19F]
0x180036ab4  lea     rcx, [rbp+0D0h+var_B0]
0x180036ab8  mov     [rsp+1D0h+var_19F], 1
0x180036abd  call    cs:__imp_RtlSidDominates
0x180036ac3  cmp     [rsp+1D0h+var_19F], dil
0x180036ac8  jnz     loc_180036B51
0x180036ace  lea     eax, [rdi+3]
0x180036ad1  mov     cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A, eax; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x180036ad7  lea     r9, [rsp+1D0h+hKey]; HKEY *
0x180036adc  mov     [rsp+1D0h+hKey], rdi
0x180036ae1  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Ole\\AppCompat"
0x180036ae8  call    ?StaticOpen@RegistryKey@@CAJPEAUHKEY__@@PEBGKPEAPEAU2@@Z; RegistryKey::StaticOpen(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180036aed  test    eax, eax
0x180036aef  js      loc_180036C4A
0x180036af5  cmp     cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A, 2; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x180036afc  lea     rax, aAllowstructure; "AllowStructuredStorageSharedMemoryModeF"...
0x180036b03  lea     rdx, aAllowstructure_0; "AllowStructuredStorageSharedMemoryModeF"...
0x180036b0a  mov     [rsp+1D0h+var_19C], edi
0x180036b0e  cmovnz  rdx, rax; unsigned __int16 *
0x180036b12  lea     r8, [rsp+1D0h+var_19C]; unsigned int *
0x180036b17  lea     rcx, [rsp+1D0h+hKey]; this
0x180036b1c  call    ?ReadDWORDValue@RegistryKey@@QEBAJPEBGPEAK@Z; RegistryKey::ReadDWORDValue(ushort const *,ulong *)
0x180036b21  test    eax, eax
0x180036b23  js      loc_180036C4A
0x180036b29  cmp     [rsp+1D0h+var_19C], edi
0x180036b2d  mov     rcx, [rsp+1D0h+hKey]
0x180036b32  setz    bl
0x180036b35  test    rcx, rcx
0x180036b38  jz      short loc_180036B4A
0x180036b3a  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180036b3f  call    cs:__imp_RegCloseKey
0x180036b45  mov     [rsp+1D0h+hKey], rdi
0x180036b4a  mov     al, bl
0x180036b4c  jmp     loc_180036C66
0x180036b51  mov     r8, rbx; Size
0x180036b54  mov     dword ptr [rbp+0D0h+var_108.Value], edi
0x180036b57  xor     edx, edx; Val
0x180036b59  mov     word ptr [rbp+0D0h+var_108.Value+4], 500h
0x180036b5f  lea     rcx, [rbp+0D0h+SidToCheck]; void *
0x180036b63  call    memset_0
0x180036b68  mov     r8b, 1; SubAuthorityCount
0x180036b6b  lea     rdx, [rbp+0D0h+var_108]; IdentifierAuthority
0x180036b6f  lea     rcx, [rbp+0D0h+SidToCheck]; Sid
0x180036b73  call    cs:__imp_RtlInitializeSid
0x180036b79  xor     edx, edx; SubAuthority
0x180036b7b  lea     rcx, [rbp+0D0h+SidToCheck]; Sid
0x180036b7f  call    cs:__imp_RtlSubAuthoritySid
0x180036b85  lea     rcx, [rsp+1D0h+hObject]; TokenHandle
0x180036b8a  mov     dword ptr [rax], 4
0x180036b90  mov     [rsp+1D0h+hObject], rdi
0x180036b95  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180036b9a  test    eax, eax
0x180036b9c  js      loc_180036C64
0x180036ba2  mov     rbx, [rsp+1D0h+hObject]
0x180036ba7  lea     r8, [rsp+1D0h+IsMember]; IsMember
0x180036bac  lea     rdx, [rbp+0D0h+SidToCheck]; SidToCheck
0x180036bb0  mov     [rsp+1D0h+IsMember], edi
0x180036bb4  xor     ecx, ecx; TokenHandle
0x180036bb6  call    cs:__imp_CheckTokenMembership
0x180036bbc  test    eax, eax
0x180036bbe  jnz     short loc_180036BCD
0x180036bc0  mov     rcx, rbx; hObject
0x180036bc3  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180036bc8  jmp     loc_180036C64
0x180036bcd  cmp     [rsp+1D0h+IsMember], edi
0x180036bd1  jz      short loc_180036C17
0x180036bd3  mov     r9d, 4; TokenInformationLength
0x180036bd9  mov     [rsp+1D0h+var_19C], edi
0x180036bdd  lea     rax, [rsp+1D0h+var_188]
0x180036be2  mov     [rsp+1D0h+var_188], 4
0x180036bea  lea     r8, [rsp+1D0h+var_19C]; TokenInformation
0x180036bef  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x180036bf4  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180036bfb  lea     edx, [r9+0Eh]; TokenInformationClass
0x180036bff  call    cs:__imp_GetTokenInformation
0x180036c05  test    eax, eax
0x180036c07  jz      short loc_180036BC0
0x180036c09  cmp     [rsp+1D0h+var_19C], 1
0x180036c0e  mov     eax, edi
0x180036c10  setnz   al
0x180036c13  inc     eax
0x180036c15  jmp     short loc_180036C1C
0x180036c17  mov     eax, 3
0x180036c1c  mov     rcx, rbx; hObject
0x180036c1f  mov     cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A, eax; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x180036c25  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180036c2a  mov     eax, cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x180036c30  jmp     short loc_180036C3D
0x180036c32  mov     eax, 1
0x180036c37  mov     cs:?g_whichSharedMemoryDisabledProcessType@@3W4_unnamed_type_g_whichSharedMemoryDisabledProcessType_@@A, eax; _unnamed_type_g_whichSharedMemoryDisabledProcessType_ g_whichSharedMemoryDisabledProcessType
0x180036c3d  cmp     eax, 1
0x180036c40  jnz     loc_180036AD7
0x180036c46  xor     al, al
0x180036c48  jmp     short loc_180036C66
0x180036c4a  mov     rax, [rsp+1D0h+hKey]
0x180036c4f  test    rax, rax
0x180036c52  jz      short loc_180036C64
0x180036c54  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180036c59  call    cs:__imp_RegCloseKey
0x180036c5f  mov     [rsp+1D0h+hKey], rdi
0x180036c64  mov     al, 1
0x180036c66  mov     rcx, [rbp+0D0h+var_10]
0x180036c6d  xor     rcx, rsp; StackCookie
0x180036c70  call    __security_check_cookie
0x180036c75  lea     r11, [rsp+1D0h+var_s0]
0x180036c7d  mov     rbx, [r11+10h]
0x180036c81  mov     rdi, [r11+18h]
0x180036c85  mov     rsp, r11
0x180036c88  pop     rbp
0x180036c89  retn
```
