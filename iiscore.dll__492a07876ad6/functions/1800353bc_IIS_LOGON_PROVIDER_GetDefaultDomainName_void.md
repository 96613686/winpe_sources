# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x1800353bc`
- end: `0x180035602`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `582`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035f10`

## callees

- `0x1800353bc`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18003551c`
- `msvcrt!wcsncpy_s` at `0x18003551c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035594`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035594`
- `ntdll!RtlNtStatusToDosError` at `0x18003545f`
- `ntdll!RtlNtStatusToDosError` at `0x1800354e4`
- `ntdll!RtlNtStatusToDosError` at `0x18003545f`
- `ntdll!RtlNtStatusToDosError` at `0x1800354e4`
- `iisutil!PuDbgPrint` at `0x180035451`
- `iisutil!PuDbgPrint` at `0x1800354d6`
- `iisutil!PuDbgPrint` at `0x180035451`
- `iisutil!PuDbgPrint` at `0x1800354d6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180035490`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180035541`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180035490`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180035541`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800355b1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800355ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800355b1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800355ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003540b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003540b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800355e3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800355e3`

## string_xrefs

- `0x18003543f`: `cannot open lsa policy, error %08lX\n`
- `0x180035438`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800354ca`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

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
0x1800353bc  mov     [rsp-18h+arg_0], rbx
0x1800353c1  push    rbp
0x1800353c2  push    rsi
0x1800353c3  push    rdi
0x1800353c4  mov     rbp, rsp
0x1800353c7  sub     rsp, 70h
0x1800353cb  xor     esi, esi
0x1800353cd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800353d5  mov     rdi, rcx
0x1800353d8  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x1800353dc  xorps   xmm0, xmm0
0x1800353df  mov     [rbp+nSize], esi
0x1800353e2  xor     ecx, ecx; SystemName
0x1800353e4  mov     [rbp+PolicyHandle], rsi
0x1800353e8  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800353ec  mov     [rbp+Buffer], rsi
0x1800353f0  mov     r8d, 20801h; DesiredAccess
0x1800353f6  mov     [rbp+var_40], rsi
0x1800353fa  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800353fe  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180035402  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x180035406  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003540b  call    cs:__imp_LsaOpenPolicy
0x180035412  nop     dword ptr [rax+rax+00h]
0x180035417  mov     ebx, eax
0x180035419  test    eax, eax
0x18003541b  jns     short loc_180035483
0x18003541d  test    byte ptr cs:g_dwDebugFlags, 3
0x180035424  jz      short loc_18003545D
0x180035426  mov     rcx, cs:g_pDebug
0x18003542d  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180035434  mov     [rsp+70h+var_48], eax
0x180035438  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003543f  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180035446  mov     r8d, 140h
0x18003544c  mov     [rsp+70h+var_50], rax
0x180035451  call    cs:__imp_PuDbgPrint
0x180035458  nop     dword ptr [rax+rax+00h]
0x18003545d  mov     ecx, ebx; Status
0x18003545f  call    cs:__imp_RtlNtStatusToDosError
0x180035466  nop     dword ptr [rax+rax+00h]
0x18003546b  mov     ebx, eax
0x18003546d  test    eax, eax
0x18003546f  jle     short loc_18003547A
0x180035471  movzx   ebx, ax
0x180035474  or      ebx, 80070000h
0x18003547a  mov     [rbp+PolicyHandle], rsi
0x18003547e  jmp     loc_1800355A8
0x180035483  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180035487  lea     r8, [rbp+Buffer]; Buffer
0x18003548b  mov     edx, 5; InformationClass
0x180035490  call    cs:__imp_LsaQueryInformationPolicy
0x180035497  nop     dword ptr [rax+rax+00h]
0x18003549c  mov     ebx, eax
0x18003549e  test    eax, eax
0x1800354a0  jns     short loc_180035508
0x1800354a2  test    byte ptr cs:g_dwDebugFlags, 3
0x1800354a9  jz      short loc_1800354E2
0x1800354ab  mov     r8d, 15Bh
0x1800354b1  mov     rcx, cs:g_pDebug
0x1800354b8  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x1800354bf  mov     [rsp+70h+var_48], ebx
0x1800354c3  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x1800354ca  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800354d1  mov     [rsp+70h+var_50], rax
0x1800354d6  call    cs:__imp_PuDbgPrint
0x1800354dd  nop     dword ptr [rax+rax+00h]
0x1800354e2  mov     ecx, ebx; Status
0x1800354e4  call    cs:__imp_RtlNtStatusToDosError
0x1800354eb  nop     dword ptr [rax+rax+00h]
0x1800354f0  mov     ebx, eax
0x1800354f2  test    eax, eax
0x1800354f4  jle     loc_1800355A8
0x1800354fa  movzx   ebx, ax
0x1800354fd  or      ebx, 80070000h
0x180035503  jmp     loc_1800355A8
0x180035508  mov     r8, [rbp+Buffer]
0x18003550c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180035510  mov     edx, 100h; SizeInWords
0x180035515  mov     rcx, rdi; Destination
0x180035518  mov     r8, [r8+8]; Source
0x18003551c  call    cs:__imp_wcsncpy_s
0x180035523  nop     dword ptr [rax+rax+00h]
0x180035528  cmp     eax, 50h ; 'P'
0x18003552b  jnz     short loc_180035534
0x18003552d  mov     ebx, 8007007Ah
0x180035532  jmp     short loc_1800355A8
0x180035534  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180035538  lea     r8, [rbp+var_40]; Buffer
0x18003553c  mov     edx, 3; InformationClass
0x180035541  call    cs:__imp_LsaQueryInformationPolicy
0x180035548  nop     dword ptr [rax+rax+00h]
0x18003554d  mov     ebx, eax
0x18003554f  test    eax, eax
0x180035551  jns     short loc_180035567
0x180035553  test    byte ptr cs:g_dwDebugFlags, 3
0x18003555a  jz      short loc_1800354E2
0x18003555c  mov     r8d, 17Ch
0x180035562  jmp     loc_1800354B1
0x180035567  mov     rax, [rbp+var_40]
0x18003556b  mov     ebx, esi
0x18003556d  cmp     [rax+10h], rsi
0x180035571  jz      short loc_1800355A2
0x180035573  lea     rdx, [rdi+200h]; lpBuffer
0x18003557a  mov     dword ptr [rdi+0A00h], 1
0x180035584  lea     r8, [rbp+nSize]; nSize
0x180035588  mov     [rbp+nSize], 400h
0x18003558f  mov     ecx, 2; NameType
0x180035594  call    cs:__imp_GetComputerNameExW
0x18003559b  nop     dword ptr [rax+rax+00h]
0x1800355a0  jmp     short loc_1800355A8
0x1800355a2  mov     [rdi+0A00h], esi
0x1800355a8  mov     rcx, [rbp+Buffer]; Buffer
0x1800355ac  test    rcx, rcx
0x1800355af  jz      short loc_1800355C1
0x1800355b1  call    cs:__imp_LsaFreeMemory
0x1800355b8  nop     dword ptr [rax+rax+00h]
0x1800355bd  mov     [rbp+Buffer], rsi
0x1800355c1  mov     rcx, [rbp+var_40]; Buffer
0x1800355c5  test    rcx, rcx
0x1800355c8  jz      short loc_1800355DA
0x1800355ca  call    cs:__imp_LsaFreeMemory
0x1800355d1  nop     dword ptr [rax+rax+00h]
0x1800355d6  mov     [rbp+var_40], rsi
0x1800355da  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800355de  test    rcx, rcx
0x1800355e1  jz      short loc_1800355EF
0x1800355e3  call    cs:__imp_LsaClose
0x1800355ea  nop     dword ptr [rax+rax+00h]
0x1800355ef  mov     eax, ebx
0x1800355f1  mov     rbx, [rsp+70h+arg_0]
0x1800355f9  add     rsp, 70h
0x1800355fd  pop     rdi
0x1800355fe  pop     rsi
0x1800355ff  pop     rbp
0x180035600  retn
```
