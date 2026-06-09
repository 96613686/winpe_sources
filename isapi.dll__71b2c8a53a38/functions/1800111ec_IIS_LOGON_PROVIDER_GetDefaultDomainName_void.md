# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x1800111ec`
- end: `0x1800113e9`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011b80`

## callees

- `0x1800111ec`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180011328`
- `msvcrt!wcsncpy_s` at `0x180011328`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011394`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180011394`
- `iisutil!PuDbgPrint` at `0x18001127b`
- `iisutil!PuDbgPrint` at `0x1800112ee`
- `iisutil!PuDbgPrint` at `0x18001127b`
- `iisutil!PuDbgPrint` at `0x1800112ee`
- `ntdll!RtlNtStatusToDosError` at `0x180011283`
- `ntdll!RtlNtStatusToDosError` at `0x1800112f6`
- `ntdll!RtlNtStatusToDosError` at `0x180011283`
- `ntdll!RtlNtStatusToDosError` at `0x1800112f6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800113d1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800113d1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800112ae`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180011347`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800112ae`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180011347`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800113ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800113be`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800113ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800113be`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001123b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001123b`

## string_xrefs

- `0x180011269`: `cannot open lsa policy, error %08lX\n`
- `0x180011262`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800112e2`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::GetDefaultDomainName(wchar_t *Destination)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  signed int v4; // eax
  unsigned int v5; // ebx
  int v6; // ebx
  __int64 v7; // r8
  signed int v8; // eax
  PVOID v10; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+98h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+30h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  nSize = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v10 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x20801u, &PolicyHandle);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        320,
        "IIS_LOGON_PROVIDER::GetDefaultDomainName",
        "cannot open lsa policy, error %08lX\n",
        v2);
    v4 = RtlNtStatusToDosError(v3);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    PolicyHandle = 0;
    goto LABEL_21;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v6 >= 0 )
  {
    if ( wcsncpy_s(Destination, 0x100u, *((const wchar_t **)Buffer + 1), 0xFFFFFFFFFFFFFFFFuLL) == 80 )
    {
      v5 = -2147024774;
      goto LABEL_21;
    }
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &v10);
    if ( v6 >= 0 )
    {
      v5 = 0;
      if ( *((_QWORD *)v10 + 2) )
      {
        *((_DWORD *)Destination + 640) = 1;
        nSize = 1024;
        GetComputerNameExW(ComputerNameDnsDomain, Destination + 256, &nSize);
      }
      else
      {
        *((_DWORD *)Destination + 640) = 0;
      }
      goto LABEL_21;
    }
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 380;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 347;
  }
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v7,
    "IIS_LOGON_PROVIDER::GetDefaultDomainName",
    "cannot query lsa policy info, error %08lX\n",
    v6);
LABEL_11:
  v8 = RtlNtStatusToDosError(v6);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
LABEL_21:
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v10 )
  {
    LsaFreeMemory(v10);
    v10 = 0;
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x1800111ec  mov     [rsp-18h+arg_0], rbx
0x1800111f1  push    rbp
0x1800111f2  push    rsi
0x1800111f3  push    rdi
0x1800111f4  mov     rbp, rsp
0x1800111f7  sub     rsp, 70h
0x1800111fb  xor     esi, esi
0x1800111fd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180011205  mov     rdi, rcx
0x180011208  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x18001120c  xorps   xmm0, xmm0
0x18001120f  mov     [rbp+nSize], esi
0x180011212  xor     ecx, ecx; SystemName
0x180011214  mov     [rbp+PolicyHandle], rsi
0x180011218  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001121c  mov     [rbp+Buffer], rsi
0x180011220  mov     r8d, 20801h; DesiredAccess
0x180011226  mov     [rbp+var_40], rsi
0x18001122a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001122e  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180011232  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x180011236  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001123b  call    cs:__imp_LsaOpenPolicy
0x180011241  mov     ebx, eax
0x180011243  test    eax, eax
0x180011245  jns     short loc_1800112A1
0x180011247  test    byte ptr cs:g_dwDebugFlags, 3
0x18001124e  jz      short loc_180011281
0x180011250  mov     rcx, cs:g_pDebug
0x180011257  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x18001125e  mov     [rsp+70h+var_48], eax
0x180011262  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180011269  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180011270  mov     r8d, 140h
0x180011276  mov     [rsp+70h+var_50], rax
0x18001127b  call    cs:__imp_PuDbgPrint
0x180011281  mov     ecx, ebx; Status
0x180011283  call    cs:__imp_RtlNtStatusToDosError
0x180011289  mov     ebx, eax
0x18001128b  test    eax, eax
0x18001128d  jle     short loc_180011298
0x18001128f  movzx   ebx, ax
0x180011292  or      ebx, 80070000h
0x180011298  mov     [rbp+PolicyHandle], rsi
0x18001129c  jmp     loc_1800113A2
0x1800112a1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800112a5  lea     r8, [rbp+Buffer]; Buffer
0x1800112a9  mov     edx, 5; InformationClass
0x1800112ae  call    cs:__imp_LsaQueryInformationPolicy
0x1800112b4  mov     ebx, eax
0x1800112b6  test    eax, eax
0x1800112b8  jns     short loc_180011314
0x1800112ba  test    byte ptr cs:g_dwDebugFlags, 3
0x1800112c1  jz      short loc_1800112F4
0x1800112c3  mov     r8d, 15Bh
0x1800112c9  mov     rcx, cs:g_pDebug
0x1800112d0  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x1800112d7  mov     [rsp+70h+var_48], ebx
0x1800112db  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x1800112e2  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800112e9  mov     [rsp+70h+var_50], rax
0x1800112ee  call    cs:__imp_PuDbgPrint
0x1800112f4  mov     ecx, ebx; Status
0x1800112f6  call    cs:__imp_RtlNtStatusToDosError
0x1800112fc  mov     ebx, eax
0x1800112fe  test    eax, eax
0x180011300  jle     loc_1800113A2
0x180011306  movzx   ebx, ax
0x180011309  or      ebx, 80070000h
0x18001130f  jmp     loc_1800113A2
0x180011314  mov     r8, [rbp+Buffer]
0x180011318  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001131c  mov     edx, 100h; SizeInWords
0x180011321  mov     rcx, rdi; Destination
0x180011324  mov     r8, [r8+8]; Source
0x180011328  call    cs:__imp_wcsncpy_s
0x18001132e  cmp     eax, 50h ; 'P'
0x180011331  jnz     short loc_18001133A
0x180011333  mov     ebx, 8007007Ah
0x180011338  jmp     short loc_1800113A2
0x18001133a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001133e  lea     r8, [rbp+var_40]; Buffer
0x180011342  mov     edx, 3; InformationClass
0x180011347  call    cs:__imp_LsaQueryInformationPolicy
0x18001134d  mov     ebx, eax
0x18001134f  test    eax, eax
0x180011351  jns     short loc_180011367
0x180011353  test    byte ptr cs:g_dwDebugFlags, 3
0x18001135a  jz      short loc_1800112F4
0x18001135c  mov     r8d, 17Ch
0x180011362  jmp     loc_1800112C9
0x180011367  mov     rax, [rbp+var_40]
0x18001136b  mov     ebx, esi
0x18001136d  cmp     [rax+10h], rsi
0x180011371  jz      short loc_18001139C
0x180011373  lea     rdx, [rdi+200h]; lpBuffer
0x18001137a  mov     dword ptr [rdi+0A00h], 1
0x180011384  lea     r8, [rbp+nSize]; nSize
0x180011388  mov     [rbp+nSize], 400h
0x18001138f  mov     ecx, 2; NameType
0x180011394  call    cs:__imp_GetComputerNameExW
0x18001139a  jmp     short loc_1800113A2
0x18001139c  mov     [rdi+0A00h], esi
0x1800113a2  mov     rcx, [rbp+Buffer]; Buffer
0x1800113a6  test    rcx, rcx
0x1800113a9  jz      short loc_1800113B5
0x1800113ab  call    cs:__imp_LsaFreeMemory
0x1800113b1  mov     [rbp+Buffer], rsi
0x1800113b5  mov     rcx, [rbp+var_40]; Buffer
0x1800113b9  test    rcx, rcx
0x1800113bc  jz      short loc_1800113C8
0x1800113be  call    cs:__imp_LsaFreeMemory
0x1800113c4  mov     [rbp+var_40], rsi
0x1800113c8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800113cc  test    rcx, rcx
0x1800113cf  jz      short loc_1800113D7
0x1800113d1  call    cs:__imp_LsaClose
0x1800113d7  mov     eax, ebx
0x1800113d9  mov     rbx, [rsp+70h+arg_0]
0x1800113e1  add     rsp, 70h
0x1800113e5  pop     rdi
0x1800113e6  pop     rsi
0x1800113e7  pop     rbp
0x1800113e8  retn
```
