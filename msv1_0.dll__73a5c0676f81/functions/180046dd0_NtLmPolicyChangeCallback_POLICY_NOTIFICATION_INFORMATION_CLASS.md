# NtLmPolicyChangeCallback(_POLICY_NOTIFICATION_INFORMATION_CLASS)

- ea: `0x180046dd0`
- end: `0x180046fb1`
- name: `?NtLmPolicyChangeCallback@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z`
- size: `481`
- prototype: `void __fastcall(enum _POLICY_NOTIFICATION_INFORMATION_CLASS)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002ee7c`
- `0x18002fb50`
- `0x180046dd0`
- `0x18004704c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180046e79`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180046e79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046f55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046f55`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046f6b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046f6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046f76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046f76`
- `ntdll!RtlEqualSid` at `0x180046f1d`
- `ntdll!RtlEqualSid` at `0x180046f1d`
- `ntdll!RtlInitUnicodeString` at `0x180046e92`
- `ntdll!RtlInitUnicodeString` at `0x180046e92`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180046e22`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x180046e22`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180046f8b`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180046f8b`

## string_xrefs

- `0x180046f47`: `SECURITY\Cache`

## pseudocode

```c
void __fastcall NtLmPolicyChangeCallback(enum _POLICY_NOTIFICATION_INFORMATION_CLASS a1)
{
  int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  bool v4; // zf
  void *v5; // rdx
  bool v6; // bl
  struct _UNICODE_STRING *v7; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  if ( a1 == PolicyNotifyDnsDomainInformation )
  {
    v7 = 0;
    nSize = 256;
    DestinationString = 0;
    v1 = LsaIQueryInformationPolicyTrusted(12, &v7);
    if ( v1 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v3 = 32;
      goto LABEL_6;
    }
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) )
      Buffer[0] = 0;
    RtlInitUnicodeString(&DestinationString, Buffer);
    v1 = NtLmSetPolicyInfo(
           &DestinationString,
           0,
           v7 + 1,
           v7,
           *(void **)&v7[4].Length,
           PolicyNotifyDnsDomainInformation,
           0);
    if ( v1 < 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v3 = 33;
LABEL_6:
      WPP_SF_d(v2[2], v3, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, (unsigned int)v1);
      goto LABEL_21;
    }
    if ( Sid1 )
    {
      v5 = *(void **)&v7[4].Length;
      v6 = v5 == 0;
      if ( v5 && !RtlEqualSid(Sid1, v5) )
        goto LABEL_19;
      v4 = !v6;
    }
    else
    {
      v4 = *(_QWORD *)&v7[4].Length == 0;
    }
    if ( v4 )
    {
LABEL_21:
      if ( v7 )
        LsaIFree_LSAPR_POLICY_INFORMATION(12);
      return;
    }
LABEL_19:
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SECURITY\\Cache", 0, 2u, &hKey) )
    {
      RegDeleteValueW(hKey, L"NL$Control");
      RegCloseKey(hKey);
    }
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x180046dd0  cmp     ecx, 4
0x180046dd3  jnz     locret_180046FB0
0x180046dd9  mov     [rsp-8+arg_8], rbx
0x180046dde  push    rbp
0x180046ddf  lea     rbp, [rsp-180h]
0x180046de7  sub     rsp, 280h
0x180046dee  mov     rax, cs:__security_cookie
0x180046df5  xor     rax, rsp
0x180046df8  mov     [rbp+180h+var_10], rax
0x180046dff  xorps   xmm0, xmm0
0x180046e02  mov     [rsp+280h+var_240], 0
0x180046e0b  lea     rdx, [rsp+280h+var_240]
0x180046e10  mov     [rsp+280h+nSize], 100h
0x180046e18  mov     ecx, 0Ch
0x180046e1d  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm0
0x180046e22  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x180046e28  test    eax, eax
0x180046e2a  jns     short loc_180046E6A
0x180046e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e33  lea     rdx, WPP_GLOBAL_Control
0x180046e3a  cmp     rcx, rdx
0x180046e3d  jz      loc_180046F7C
0x180046e43  test    byte ptr [rcx+1Ch], 1
0x180046e47  jz      loc_180046F7C
0x180046e4d  mov     edx, 20h ; ' '
0x180046e52  mov     rcx, [rcx+10h]
0x180046e56  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x180046e5d  mov     r9d, eax
0x180046e60  call    WPP_SF_d
0x180046e65  jmp     loc_180046F7C
0x180046e6a  lea     r8, [rsp+280h+nSize]; nSize
0x180046e6f  mov     ecx, 3; NameType
0x180046e74  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x180046e79  call    cs:__imp_GetComputerNameExW
0x180046e7f  test    eax, eax
0x180046e81  jnz     short loc_180046E88
0x180046e83  mov     [rsp+280h+Buffer], ax
0x180046e88  lea     rdx, [rsp+280h+Buffer]; SourceString
0x180046e8d  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x180046e92  call    cs:__imp_RtlInitUnicodeString
0x180046e98  mov     r9, [rsp+280h+var_240]; struct _UNICODE_STRING *
0x180046e9d  lea     rcx, [rsp+280h+DestinationString]; struct _UNICODE_STRING *
0x180046ea2  mov     [rsp+280h+var_250], 0; char
0x180046ea7  xor     edx, edx; struct _UNICODE_STRING *
0x180046ea9  mov     [rsp+280h+var_258], 4; enum _POLICY_NOTIFICATION_INFORMATION_CLASS
0x180046eb1  mov     rax, [r9+40h]
0x180046eb5  lea     r8, [r9+10h]; struct _UNICODE_STRING *
0x180046eb9  mov     [rsp+280h+phkResult], rax; void *
0x180046ebe  call    ?NtLmSetPolicyInfo@@YAJPEAU_UNICODE_STRING@@000PEAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@E@Z; NtLmSetPolicyInfo(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_POLICY_NOTIFICATION_INFORMATION_CLASS,uchar)
0x180046ec3  test    eax, eax
0x180046ec5  jns     short loc_180046EF2
0x180046ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ece  lea     rdx, WPP_GLOBAL_Control
0x180046ed5  cmp     rcx, rdx
0x180046ed8  jz      loc_180046F7C
0x180046ede  test    byte ptr [rcx+1Ch], 1
0x180046ee2  jz      loc_180046F7C
0x180046ee8  mov     edx, 21h ; '!'
0x180046eed  jmp     loc_180046E52
0x180046ef2  mov     rcx, cs:Sid1; Sid1
0x180046ef9  mov     rax, [rsp+280h+var_240]
0x180046efe  test    rcx, rcx
0x180046f01  jnz     short loc_180046F09
0x180046f03  cmp     [rax+40h], rcx
0x180046f07  jmp     short loc_180046F29
0x180046f09  mov     rdx, [rax+40h]; Sid2
0x180046f0d  test    rdx, rdx
0x180046f10  setz    bl
0x180046f13  test    rcx, rcx
0x180046f16  jz      short loc_180046F27
0x180046f18  test    rdx, rdx
0x180046f1b  jz      short loc_180046F27
0x180046f1d  call    cs:__imp_RtlEqualSid
0x180046f23  test    al, al
0x180046f25  jz      short loc_180046F2B
0x180046f27  test    bl, bl
0x180046f29  jz      short loc_180046F7C
0x180046f2b  lea     rax, [rsp+280h+hKey]
0x180046f30  mov     [rsp+280h+hKey], 0
0x180046f39  mov     r9d, 2; samDesired
0x180046f3f  mov     [rsp+280h+phkResult], rax; phkResult
0x180046f44  xor     r8d, r8d; ulOptions
0x180046f47  lea     rdx, aSecurityCache; "SECURITY\\Cache"
0x180046f4e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046f55  call    cs:__imp_RegOpenKeyExW
0x180046f5b  test    eax, eax
0x180046f5d  jnz     short loc_180046F7C
0x180046f5f  mov     rcx, [rsp+280h+hKey]; hKey
0x180046f64  lea     rdx, aNlControl; "NL$Control"
0x180046f6b  call    cs:__imp_RegDeleteValueW
0x180046f71  mov     rcx, [rsp+280h+hKey]; hKey
0x180046f76  call    cs:__imp_RegCloseKey
0x180046f7c  mov     rdx, [rsp+280h+var_240]
0x180046f81  test    rdx, rdx
0x180046f84  jz      short loc_180046F91
0x180046f86  mov     ecx, 0Ch
0x180046f8b  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180046f91  mov     rcx, [rbp+180h+var_10]
0x180046f98  xor     rcx, rsp; StackCookie
0x180046f9b  call    __security_check_cookie
0x180046fa0  mov     rbx, [rsp+280h+arg_8]
0x180046fa8  add     rsp, 280h
0x180046faf  pop     rbp
0x180046fb0  retn
```
