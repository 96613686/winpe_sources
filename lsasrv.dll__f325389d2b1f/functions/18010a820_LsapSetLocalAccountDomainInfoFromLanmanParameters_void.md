# LsapSetLocalAccountDomainInfoFromLanmanParameters(void)

- ea: `0x18010a820`
- end: `0x18010aef6`
- name: `?LsapSetLocalAccountDomainInfoFromLanmanParameters@@YAJXZ`
- size: `1750`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a003c`

## callees

- `0x1800b86d0`
- `0x1800b9304`
- `0x1800c7e28`
- `0x180101050`
- `0x1801093e0`
- `0x180109538`
- `0x18010a820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010a9df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010a9df`
- `ntdll!RtlFreeHeap` at `0x18010aa4e`
- `ntdll!RtlFreeHeap` at `0x18010aabe`
- `ntdll!RtlFreeHeap` at `0x18010abbc`
- `ntdll!RtlFreeHeap` at `0x18010ac44`
- `ntdll!RtlFreeHeap` at `0x18010acb7`
- `ntdll!RtlFreeHeap` at `0x18010ae5b`
- `ntdll!RtlFreeHeap` at `0x18010ae7e`
- `ntdll!RtlFreeHeap` at `0x18010aea1`
- `ntdll!RtlFreeHeap` at `0x18010aec4`
- `ntdll!RtlFreeHeap` at `0x18010aa4e`
- `ntdll!RtlFreeHeap` at `0x18010aabe`
- `ntdll!RtlFreeHeap` at `0x18010abbc`
- `ntdll!RtlFreeHeap` at `0x18010ac44`
- `ntdll!RtlFreeHeap` at `0x18010acb7`
- `ntdll!RtlFreeHeap` at `0x18010ae5b`
- `ntdll!RtlFreeHeap` at `0x18010ae7e`
- `ntdll!RtlFreeHeap` at `0x18010aea1`
- `ntdll!RtlFreeHeap` at `0x18010aec4`
- `ntdll!NtOpenKey` at `0x18010a915`
- `ntdll!NtOpenKey` at `0x18010a915`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010aa2c`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010aa9c`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010ac22`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010ac95`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010aa2c`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010aa9c`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010ac22`
- `ntdll!RtlUnicodeStringToInteger` at `0x18010ac95`
- `ntdll!RtlCopySid` at `0x18010adb3`
- `ntdll!RtlCopySid` at `0x18010adb3`
- `ntdll!RtlGetNtProductType` at `0x18010a8c2`
- `ntdll!RtlGetNtProductType` at `0x18010a8c2`
- `ntdll!RtlAllocateHeap` at `0x18010ab1c`
- `ntdll!RtlAllocateHeap` at `0x18010ad14`
- `ntdll!RtlAllocateHeap` at `0x18010ad97`
- `ntdll!RtlAllocateHeap` at `0x18010ab1c`
- `ntdll!RtlAllocateHeap` at `0x18010ad14`
- `ntdll!RtlAllocateHeap` at `0x18010ad97`
- `ntdll!RtlSubAuthoritySid` at `0x18010ab61`
- `ntdll!RtlSubAuthoritySid` at `0x18010ad4f`
- `ntdll!RtlSubAuthoritySid` at `0x18010ab61`
- `ntdll!RtlSubAuthoritySid` at `0x18010ad4f`
- `ntdll!NtClose` at `0x18010ae38`
- `ntdll!NtClose` at `0x18010ae38`
- `ntdll!RtlInitializeSid` at `0x18010ab3e`
- `ntdll!RtlInitializeSid` at `0x18010ad36`
- `ntdll!RtlInitializeSid` at `0x18010ab3e`
- `ntdll!RtlInitializeSid` at `0x18010ad36`
- `ntdll!RtlLengthRequiredSid` at `0x18010aafe`
- `ntdll!RtlLengthRequiredSid` at `0x18010acf6`
- `ntdll!RtlLengthRequiredSid` at `0x18010aafe`
- `ntdll!RtlLengthRequiredSid` at `0x18010acf6`
- `ntdll!RtlLengthSid` at `0x18010ad77`
- `ntdll!RtlLengthSid` at `0x18010ad77`
- `ntdll!RtlInitUnicodeString` at `0x18010a8d9`
- `ntdll!RtlInitUnicodeString` at `0x18010ab97`
- `ntdll!RtlInitUnicodeString` at `0x18010a8d9`
- `ntdll!RtlInitUnicodeString` at `0x18010ab97`

## string_xrefs

- `0x18010a8ce`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkstation\Parameters`
- `0x18010a9b0`: `CreatePolicyDatabaseOnFirstBoot`

## pseudocode

```c
__int64 LsapSetLocalAccountDomainInfoFromLanmanParameters(void)
{
  void *v0; // r15
  void *v1; // rsi
  PWSTR Buffer; // rdi
  PWSTR v3; // r14
  NTSTATUS v4; // eax
  NTSTATUS Config; // ebx
  __int64 v6; // rcx
  unsigned int i; // edi
  __int64 v8; // rcx
  ULONG v9; // eax
  PVOID Heap; // rax
  ULONG j; // edi
  PULONG v12; // rax
  __int64 v13; // rcx
  unsigned int k; // edi
  __int64 v15; // rcx
  UCHAR v16; // r14
  unsigned int m; // edi
  __int64 v18; // rcx
  ULONG v19; // eax
  PVOID v20; // rax
  ULONG n; // ebx
  PULONG v22; // rax
  __int64 v23; // rcx
  ULONG v24; // edi
  PVOID v25; // rax
  NTSTATUS v26; // eax
  ULONG Value; // [rsp+40h] [rbp-C0h] BYREF
  PCUNICODE_STRING String; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v31; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+68h] [rbp-98h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+6Ch] [rbp-94h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v35; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v38; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v41; // [rsp+100h] [rbp+0h] BYREF
  void *v42; // [rsp+110h] [rbp+10h]
  _DWORD v43[16]; // [rsp+150h] [rbp+50h]

  ProductType = 0;
  *(_QWORD *)&v35.Length = 0;
  KeyHandle = 0;
  Value = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v38 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v30 = 0;
  String = 0;
  *(_QWORD *)&v31.Length = 0;
  DestinationString = 0;
  LODWORD(v41) = 0;
  memset_0((char *)&v41 + 4, 0, 0x44u);
  v35.Buffer = 0;
  v0 = 0;
  v31.Buffer = 0;
  v1 = 0;
  Buffer = 0;
  v3 = 0;
  RtlGetNtProductType(&ProductType);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkstation\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  Config = v4;
  if ( v4 >= 0 )
  {
    Config = LsapDbGetConfig(KeyHandle, L"Domain", &v35);
    if ( Config < 0 )
    {
LABEL_49:
      Buffer = v35.Buffer;
      goto LABEL_50;
    }
    Config = LsapDbGetConfig(KeyHandle, L"DomainId", &v31);
    if ( Config >= 0 )
    {
      if ( v31.Length
        || (pcbData = 4,
            pvData = 0,
            RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Lsa",
              L"CreatePolicyDatabaseOnFirstBoot",
              0x10u,
              0,
              &pvData,
              &pcbData))
        || !pvData )
      {
        while ( (unsigned int)Buffer < 6 )
        {
          Config = LsapDbGetNextValueToken(&v31, &v30, (struct _UNICODE_STRING **)&String);
          if ( Config < 0 )
            goto LABEL_48;
          Config = RtlUnicodeStringToInteger(String, 0xAu, &Value);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)String);
          if ( Config < 0 )
            goto LABEL_48;
          v6 = (unsigned int)Buffer;
          LODWORD(Buffer) = (_DWORD)Buffer + 1;
          IdentifierAuthority.Value[v6] = Value;
        }
        for ( i = 0; ; ++i )
        {
          Config = LsapDbGetNextValueToken(&v31, &v30, (struct _UNICODE_STRING **)&String);
          if ( Config >= 0 )
          {
            Config = RtlUnicodeStringToInteger(String, 0xAu, &Value);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)String);
          }
          if ( Config == -1073741585 )
            break;
          if ( Config < 0 || i >= 0xF )
            goto LABEL_48;
          LOBYTE(v3) = (_BYTE)v3 + 1;
          v8 = i;
          v43[v8] = Value;
        }
        v9 = RtlLengthRequiredSid((unsigned __int8)v3);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
        v0 = Heap;
        if ( !Heap )
          goto LABEL_48;
        Config = RtlInitializeSid(Heap, &IdentifierAuthority, (UCHAR)v3);
        if ( Config < 0 )
          goto LABEL_48;
        for ( j = 0; j < (unsigned __int8)v3; *v12 = v43[v13] )
        {
          v12 = RtlSubAuthoritySid(v0, j);
          v13 = j++;
        }
      }
      if ( ProductType == NtProductLanManNt )
      {
        v38 = v35;
        v24 = RtlLengthSid(v0);
        v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
        v1 = v25;
        if ( v25 )
        {
          Config = RtlCopySid(v24, v25, v0);
          if ( Config >= 0 )
            goto LABEL_46;
        }
      }
      else
      {
        v30 = 0;
        RtlInitUnicodeString(&v38, L"Account");
        if ( v31.Buffer )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31.Buffer);
          v31.Buffer = 0;
        }
        Config = LsapDbGetConfig(KeyHandle, L"AccountDomainId", &v31);
        if ( Config >= 0 )
        {
          for ( k = 0; k < 6; ++k )
          {
            Config = LsapDbGetNextValueToken(&v31, &v30, (struct _UNICODE_STRING **)&String);
            if ( Config < 0 )
              goto LABEL_48;
            Config = RtlUnicodeStringToInteger(String, 0xAu, &Value);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)String);
            if ( Config < 0 )
              goto LABEL_48;
            v15 = k;
            IdentifierAuthority.Value[v15] = Value;
          }
          v16 = 0;
          for ( m = 0; ; ++m )
          {
            Config = LsapDbGetNextValueToken(&v31, &v30, (struct _UNICODE_STRING **)&String);
            if ( Config >= 0 )
            {
              Config = RtlUnicodeStringToInteger(String, 0xAu, &Value);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)String);
            }
            if ( Config == -1073741585 )
              break;
            if ( Config < 0 || m >= 0xF )
              goto LABEL_48;
            ++v16;
            v18 = m;
            v43[v18] = Value;
          }
          v19 = RtlLengthRequiredSid(v16);
          v20 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
          v1 = v20;
          if ( v20 )
          {
            RtlInitializeSid(v20, &IdentifierAuthority, v16);
            for ( n = 0; n < v16; *v22 = v43[v23] )
            {
              v22 = RtlSubAuthoritySid(v1, n);
              v23 = n++;
            }
LABEL_46:
            v42 = v1;
            v41 = 0;
            Config = LsarSetInformationPolicy(LsapPolicyHandle);
            if ( Config >= 0 )
            {
              Buffer = v35.Buffer;
              LODWORD(v41) = *(_DWORD *)&v35.Length;
              *((_QWORD *)&v41 + 1) = v35.Buffer;
              v42 = v0;
              v26 = LsarSetInformationPolicy(LsapPolicyHandle);
              v3 = v31.Buffer;
              Config = v26;
              goto LABEL_50;
            }
          }
        }
      }
    }
LABEL_48:
    v3 = v31.Buffer;
    goto LABEL_49;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x20) != 0 )
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      49,
      (unsigned int)&WPP_74ca3e4e2daa38964e82adfb4672289a_Traceguids,
      (unsigned int)&DestinationString,
      v4);
LABEL_50:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  if ( v1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  return (unsigned int)Config;
}

```

## disassembly

```asm
0x18010a820  push    rbp
0x18010a822  push    rbx
0x18010a823  push    rsi
0x18010a824  push    rdi
0x18010a825  push    r12
0x18010a827  push    r13
0x18010a829  push    r14
0x18010a82b  push    r15
0x18010a82d  lea     rbp, [rsp-0A8h]
0x18010a835  sub     rsp, 1A8h
0x18010a83c  mov     rax, cs:__security_cookie
0x18010a843  xor     rax, rsp
0x18010a846  mov     [rbp+0E0h+var_50], rax
0x18010a84d  xor     r13d, r13d
0x18010a850  lea     rcx, [rbp+0E0h+var_E0+4]; void *
0x18010a854  xorps   xmm1, xmm1
0x18010a857  mov     [rsp+1E0h+ProductType], r13d
0x18010a85c  xorps   xmm0, xmm0
0x18010a85f  mov     qword ptr [rbp+0E0h+var_160.Length], r13
0x18010a863  xor     eax, eax
0x18010a865  mov     [rsp+1E0h+KeyHandle], r13
0x18010a86a  lea     r8d, [r13+44h]; Size
0x18010a86e  mov     [rsp+1E0h+Value], r13d
0x18010a873  xor     edx, edx; Val
0x18010a875  mov     dword ptr [rbp+0E0h+IdentifierAuthority.Value], eax
0x18010a878  movups  xmmword ptr [rbp+0E0h+var_130.Length], xmm0
0x18010a87c  mov     word ptr [rbp+0E0h+IdentifierAuthority.Value+4], ax
0x18010a880  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm1
0x18010a884  mov     [rsp+1E0h+var_190], r13d
0x18010a889  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm1
0x18010a88d  mov     [rsp+1E0h+String], r13
0x18010a892  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18010a896  mov     qword ptr [rsp+1E0h+var_188.Length], r13
0x18010a89b  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18010a89f  mov     dword ptr [rbp+0E0h+var_E0], r13d
0x18010a8a3  call    memset_0
0x18010a8a8  lea     rcx, [rsp+1E0h+ProductType]; ProductType
0x18010a8ad  mov     [rbp+0E0h+var_160.Buffer], r13
0x18010a8b1  mov     r15d, r13d
0x18010a8b4  mov     [rsp+1E0h+var_188.Buffer], r13
0x18010a8b9  mov     esi, r13d
0x18010a8bc  mov     edi, r13d
0x18010a8bf  mov     r14d, r13d
0x18010a8c2  call    cs:__imp_RtlGetNtProductType
0x18010a8c9  nop     dword ptr [rax+rax+00h]
0x18010a8ce  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x18010a8d5  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x18010a8d9  call    cs:__imp_RtlInitUnicodeString
0x18010a8e0  nop     dword ptr [rax+rax+00h]
0x18010a8e5  lea     rax, [rbp+0E0h+DestinationString]
0x18010a8e9  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x18010a8f0  xorps   xmm0, xmm0
0x18010a8f3  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x18010a8f7  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x18010a8fb  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], r13
0x18010a8ff  mov     edx, 20019h; DesiredAccess
0x18010a904  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18010a90b  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18010a910  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010a915  call    cs:__imp_NtOpenKey
0x18010a91c  nop     dword ptr [rax+rax+00h]
0x18010a921  mov     ebx, eax
0x18010a923  test    eax, eax
0x18010a925  jns     short loc_18010A959
0x18010a927  mov     rcx, cs:WPP_GLOBAL_Control
0x18010a92e  test    byte ptr [rcx+6Ch], 20h
0x18010a932  jz      loc_18010AE2E
0x18010a938  mov     rcx, [rcx+60h]
0x18010a93c  lea     edx, [r13+31h]
0x18010a940  lea     r9, [rbp+0E0h+DestinationString]
0x18010a944  mov     dword ptr [rsp+1E0h+pdwType], eax
0x18010a948  lea     r8, WPP_74ca3e4e2daa38964e82adfb4672289a_Traceguids
0x18010a94f  call    WPP_SF_ZD
0x18010a954  jmp     loc_18010AE2E
0x18010a959  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18010a95e  lea     r8, [rbp+0E0h+var_160]; struct _UNICODE_STRING *
0x18010a962  lea     rdx, aDomain; "Domain"
0x18010a969  call    ?LsapDbGetConfig@@YAJPEAXPEBGPEAU_UNICODE_STRING@@@Z; LsapDbGetConfig(void *,ushort const *,_UNICODE_STRING *)
0x18010a96e  mov     ebx, eax
0x18010a970  test    eax, eax
0x18010a972  js      loc_18010AE2A
0x18010a978  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18010a97d  lea     r8, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010a982  lea     rdx, aDomainid; "DomainId"
0x18010a989  call    ?LsapDbGetConfig@@YAJPEAXPEBGPEAU_UNICODE_STRING@@@Z; LsapDbGetConfig(void *,ushort const *,_UNICODE_STRING *)
0x18010a98e  mov     ebx, eax
0x18010a990  test    eax, eax
0x18010a992  js      loc_18010AE25
0x18010a998  cmp     [rsp+1E0h+var_188.Length], r13w
0x18010a99e  jnz     short loc_18010A9FA
0x18010a9a0  lea     rax, [rbp+0E0h+var_150]
0x18010a9a4  mov     [rbp+0E0h+var_150], 4
0x18010a9ab  mov     [rsp+1E0h+pcbData], rax; pcbData
0x18010a9b0  lea     r8, aCreatepolicyda; "CreatePolicyDatabaseOnFirstBoot"
0x18010a9b7  lea     rax, [rsp+1E0h+var_178]
0x18010a9bc  mov     [rsp+1E0h+var_178], r13d
0x18010a9c1  mov     [rsp+1E0h+pvData], rax; pvData
0x18010a9c6  lea     rdx, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Lsa"
0x18010a9cd  mov     r9d, 10h; dwFlags
0x18010a9d3  mov     [rsp+1E0h+pdwType], r13; pdwType
0x18010a9d8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18010a9df  call    cs:__imp_RegGetValueW
0x18010a9e6  nop     dword ptr [rax+rax+00h]
0x18010a9eb  test    eax, eax
0x18010a9ed  jnz     short loc_18010A9FA
0x18010a9ef  cmp     [rsp+1E0h+var_178], r13d
0x18010a9f4  jnz     loc_18010AB7C
0x18010a9fa  cmp     edi, 6
0x18010a9fd  jnb     short loc_18010AA70
0x18010a9ff  lea     r8, [rsp+1E0h+String]; struct _UNICODE_STRING **
0x18010aa04  lea     rdx, [rsp+1E0h+var_190]; unsigned int *
0x18010aa09  lea     rcx, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010aa0e  call    ?LsapDbGetNextValueToken@@YAJPEAU_UNICODE_STRING@@PEAKPEAPEAU1@@Z; LsapDbGetNextValueToken(_UNICODE_STRING *,ulong *,_UNICODE_STRING * *)
0x18010aa13  mov     ebx, eax
0x18010aa15  test    eax, eax
0x18010aa17  js      loc_18010AE25
0x18010aa1d  mov     rcx, [rsp+1E0h+String]; String
0x18010aa22  lea     r8, [rsp+1E0h+Value]; Value
0x18010aa27  mov     edx, 0Ah; Base
0x18010aa2c  call    cs:__imp_RtlUnicodeStringToInteger
0x18010aa33  nop     dword ptr [rax+rax+00h]
0x18010aa38  mov     rcx, gs:60h
0x18010aa41  xor     edx, edx; Flags
0x18010aa43  mov     r8, [rsp+1E0h+String]; P
0x18010aa48  mov     ebx, eax
0x18010aa4a  mov     rcx, [rcx+30h]; HeapHandle
0x18010aa4e  call    cs:__imp_RtlFreeHeap
0x18010aa55  nop     dword ptr [rax+rax+00h]
0x18010aa5a  test    ebx, ebx
0x18010aa5c  js      loc_18010AE25
0x18010aa62  mov     al, byte ptr [rsp+1E0h+Value]
0x18010aa66  mov     ecx, edi
0x18010aa68  inc     edi
0x18010aa6a  mov     [rbp+rcx+0E0h+IdentifierAuthority.Value], al
0x18010aa6e  jmp     short loc_18010A9FA
0x18010aa70  mov     edi, r13d
0x18010aa73  lea     r8, [rsp+1E0h+String]; struct _UNICODE_STRING **
0x18010aa78  lea     rdx, [rsp+1E0h+var_190]; unsigned int *
0x18010aa7d  lea     rcx, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010aa82  call    ?LsapDbGetNextValueToken@@YAJPEAU_UNICODE_STRING@@PEAKPEAPEAU1@@Z; LsapDbGetNextValueToken(_UNICODE_STRING *,ulong *,_UNICODE_STRING * *)
0x18010aa87  mov     ebx, eax
0x18010aa89  test    eax, eax
0x18010aa8b  js      short loc_18010AACA
0x18010aa8d  mov     rcx, [rsp+1E0h+String]; String
0x18010aa92  lea     r8, [rsp+1E0h+Value]; Value
0x18010aa97  mov     edx, 0Ah; Base
0x18010aa9c  call    cs:__imp_RtlUnicodeStringToInteger
0x18010aaa3  nop     dword ptr [rax+rax+00h]
0x18010aaa8  mov     rcx, gs:60h
0x18010aab1  xor     edx, edx; Flags
0x18010aab3  mov     r8, [rsp+1E0h+String]; P
0x18010aab8  mov     ebx, eax
0x18010aaba  mov     rcx, [rcx+30h]; HeapHandle
0x18010aabe  call    cs:__imp_RtlFreeHeap
0x18010aac5  nop     dword ptr [rax+rax+00h]
0x18010aaca  cmp     ebx, 0C00000EFh
0x18010aad0  jz      short loc_18010AAF7
0x18010aad2  test    ebx, ebx
0x18010aad4  js      loc_18010AE25
0x18010aada  cmp     edi, 0Fh
0x18010aadd  jnb     loc_18010AE25
0x18010aae3  mov     eax, [rsp+1E0h+Value]
0x18010aae7  inc     r14b
0x18010aaea  mov     ecx, edi
0x18010aaec  inc     edi
0x18010aaee  mov     [rbp+rcx*4+0E0h+var_90], eax
0x18010aaf2  jmp     loc_18010AA73
0x18010aaf7  movzx   r12d, r14b
0x18010aafb  mov     ecx, r12d; SubAuthorityCount
0x18010aafe  call    cs:__imp_RtlLengthRequiredSid
0x18010ab05  nop     dword ptr [rax+rax+00h]
0x18010ab0a  mov     rcx, gs:60h
0x18010ab13  xor     edx, edx; Flags
0x18010ab15  mov     r8d, eax; Size
0x18010ab18  mov     rcx, [rcx+30h]; HeapHandle
0x18010ab1c  call    cs:__imp_RtlAllocateHeap
0x18010ab23  nop     dword ptr [rax+rax+00h]
0x18010ab28  mov     r15, rax
0x18010ab2b  test    rax, rax
0x18010ab2e  jz      loc_18010AE25
0x18010ab34  mov     r8b, r14b; SubAuthorityCount
0x18010ab37  lea     rdx, [rbp+0E0h+IdentifierAuthority]; IdentifierAuthority
0x18010ab3b  mov     rcx, rax; Sid
0x18010ab3e  call    cs:__imp_RtlInitializeSid
0x18010ab45  nop     dword ptr [rax+rax+00h]
0x18010ab4a  mov     ebx, eax
0x18010ab4c  test    eax, eax
0x18010ab4e  js      loc_18010AE25
0x18010ab54  mov     edi, r13d
0x18010ab57  test    r14b, r14b
0x18010ab5a  jz      short loc_18010AB7C
0x18010ab5c  mov     edx, edi; SubAuthority
0x18010ab5e  mov     rcx, r15; Sid
0x18010ab61  call    cs:__imp_RtlSubAuthoritySid
0x18010ab68  nop     dword ptr [rax+rax+00h]
0x18010ab6d  mov     ecx, edi
0x18010ab6f  inc     edi
0x18010ab71  mov     edx, [rbp+rcx*4+0E0h+var_90]
0x18010ab75  mov     [rax], edx
0x18010ab77  cmp     edi, r12d
0x18010ab7a  jb      short loc_18010AB5C
0x18010ab7c  cmp     [rsp+1E0h+ProductType], 2
0x18010ab81  jz      loc_18010AD6B
0x18010ab87  lea     rdx, aAccount; "Account"
0x18010ab8e  mov     [rsp+1E0h+var_190], r13d
0x18010ab93  lea     rcx, [rbp+0E0h+var_130]; DestinationString
0x18010ab97  call    cs:__imp_RtlInitUnicodeString
0x18010ab9e  nop     dword ptr [rax+rax+00h]
0x18010aba3  mov     r8, [rsp+1E0h+var_188.Buffer]; P
0x18010aba8  test    r8, r8
0x18010abab  jz      short loc_18010ABCD
0x18010abad  mov     rcx, gs:60h
0x18010abb6  xor     edx, edx; Flags
0x18010abb8  mov     rcx, [rcx+30h]; HeapHandle
0x18010abbc  call    cs:__imp_RtlFreeHeap
0x18010abc3  nop     dword ptr [rax+rax+00h]
0x18010abc8  mov     [rsp+1E0h+var_188.Buffer], r13
0x18010abcd  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18010abd2  lea     r8, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010abd7  lea     rdx, aAccountdomaini; "AccountDomainId"
0x18010abde  call    ?LsapDbGetConfig@@YAJPEAXPEBGPEAU_UNICODE_STRING@@@Z; LsapDbGetConfig(void *,ushort const *,_UNICODE_STRING *)
0x18010abe3  mov     ebx, eax
0x18010abe5  test    eax, eax
0x18010abe7  js      loc_18010AE25
0x18010abed  mov     edi, r13d
0x18010abf0  cmp     edi, 6
0x18010abf3  jnb     short loc_18010AC66
0x18010abf5  lea     r8, [rsp+1E0h+String]; struct _UNICODE_STRING **
0x18010abfa  lea     rdx, [rsp+1E0h+var_190]; unsigned int *
0x18010abff  lea     rcx, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010ac04  call    ?LsapDbGetNextValueToken@@YAJPEAU_UNICODE_STRING@@PEAKPEAPEAU1@@Z; LsapDbGetNextValueToken(_UNICODE_STRING *,ulong *,_UNICODE_STRING * *)
0x18010ac09  mov     ebx, eax
0x18010ac0b  test    eax, eax
0x18010ac0d  js      loc_18010AE25
0x18010ac13  mov     rcx, [rsp+1E0h+String]; String
0x18010ac18  lea     r8, [rsp+1E0h+Value]; Value
0x18010ac1d  mov     edx, 0Ah; Base
0x18010ac22  call    cs:__imp_RtlUnicodeStringToInteger
0x18010ac29  nop     dword ptr [rax+rax+00h]
0x18010ac2e  mov     rcx, gs:60h
0x18010ac37  xor     edx, edx; Flags
0x18010ac39  mov     r8, [rsp+1E0h+String]; P
0x18010ac3e  mov     ebx, eax
0x18010ac40  mov     rcx, [rcx+30h]; HeapHandle
0x18010ac44  call    cs:__imp_RtlFreeHeap
0x18010ac4b  nop     dword ptr [rax+rax+00h]
0x18010ac50  test    ebx, ebx
0x18010ac52  js      loc_18010AE25
0x18010ac58  mov     al, byte ptr [rsp+1E0h+Value]
0x18010ac5c  mov     ecx, edi
0x18010ac5e  inc     edi
0x18010ac60  mov     [rbp+rcx+0E0h+IdentifierAuthority.Value], al
0x18010ac64  jmp     short loc_18010ABF0
0x18010ac66  mov     r14b, r13b
0x18010ac69  mov     edi, r13d
0x18010ac6c  lea     r8, [rsp+1E0h+String]; struct _UNICODE_STRING **
0x18010ac71  lea     rdx, [rsp+1E0h+var_190]; unsigned int *
0x18010ac76  lea     rcx, [rsp+1E0h+var_188]; struct _UNICODE_STRING *
0x18010ac7b  call    ?LsapDbGetNextValueToken@@YAJPEAU_UNICODE_STRING@@PEAKPEAPEAU1@@Z; LsapDbGetNextValueToken(_UNICODE_STRING *,ulong *,_UNICODE_STRING * *)
0x18010ac80  mov     ebx, eax
0x18010ac82  test    eax, eax
0x18010ac84  js      short loc_18010ACC3
0x18010ac86  mov     rcx, [rsp+1E0h+String]; String
0x18010ac8b  lea     r8, [rsp+1E0h+Value]; Value
0x18010ac90  mov     edx, 0Ah; Base
0x18010ac95  call    cs:__imp_RtlUnicodeStringToInteger
0x18010ac9c  nop     dword ptr [rax+rax+00h]
0x18010aca1  mov     rcx, gs:60h
0x18010acaa  xor     edx, edx; Flags
0x18010acac  mov     r8, [rsp+1E0h+String]; P
0x18010acb1  mov     ebx, eax
0x18010acb3  mov     rcx, [rcx+30h]; HeapHandle
0x18010acb7  call    cs:__imp_RtlFreeHeap
0x18010acbe  nop     dword ptr [rax+rax+00h]
0x18010acc3  cmp     ebx, 0C00000EFh
0x18010acc9  jz      short loc_18010ACF0
0x18010accb  test    ebx, ebx
0x18010accd  js      loc_18010AE25
0x18010acd3  cmp     edi, 0Fh
0x18010acd6  jnb     loc_18010AE25
0x18010acdc  mov     eax, [rsp+1E0h+Value]
0x18010ace0  inc     r14b
0x18010ace3  mov     ecx, edi
0x18010ace5  inc     edi
0x18010ace7  mov     [rbp+rcx*4+0E0h+var_90], eax
0x18010aceb  jmp     loc_18010AC6C
0x18010acf0  movzx   edi, r14b
0x18010acf4  mov     ecx, edi; SubAuthorityCount
0x18010acf6  call    cs:__imp_RtlLengthRequiredSid
0x18010acfd  nop     dword ptr [rax+rax+00h]
0x18010ad02  mov     rcx, gs:60h
0x18010ad0b  xor     edx, edx; Flags
0x18010ad0d  mov     r8d, eax; Size
0x18010ad10  mov     rcx, [rcx+30h]; HeapHandle
0x18010ad14  call    cs:__imp_RtlAllocateHeap
0x18010ad1b  nop     dword ptr [rax+rax+00h]
0x18010ad20  mov     rsi, rax
0x18010ad23  test    rax, rax
0x18010ad26  jz      loc_18010AE25
0x18010ad2c  mov     r8b, r14b; SubAuthorityCount
  ... truncated ...
```
