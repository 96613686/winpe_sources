# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x1800323cc`
- end: `0x1800325c9`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032d9c`

## callees

- `0x1800323cc`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180032508`
- `msvcrt!wcsncpy_s` at `0x180032508`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032574`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032574`
- `ntdll!RtlNtStatusToDosError` at `0x180032463`
- `ntdll!RtlNtStatusToDosError` at `0x1800324d6`
- `ntdll!RtlNtStatusToDosError` at `0x180032463`
- `ntdll!RtlNtStatusToDosError` at `0x1800324d6`
- `iisutil!PuDbgPrint` at `0x18003245b`
- `iisutil!PuDbgPrint` at `0x1800324ce`
- `iisutil!PuDbgPrint` at `0x18003245b`
- `iisutil!PuDbgPrint` at `0x1800324ce`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003248e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032527`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003248e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180032527`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003258b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003259e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003258b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003259e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003241b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003241b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800325b1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800325b1`

## string_xrefs

- `0x180032449`: `cannot open lsa policy, error %08lX\n`
- `0x180032442`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800324c2`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

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
0x1800323cc  mov     [rsp-18h+arg_0], rbx
0x1800323d1  push    rbp
0x1800323d2  push    rsi
0x1800323d3  push    rdi
0x1800323d4  mov     rbp, rsp
0x1800323d7  sub     rsp, 70h
0x1800323db  xor     esi, esi
0x1800323dd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800323e5  mov     rdi, rcx
0x1800323e8  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x1800323ec  xorps   xmm0, xmm0
0x1800323ef  mov     [rbp+nSize], esi
0x1800323f2  xor     ecx, ecx; SystemName
0x1800323f4  mov     [rbp+PolicyHandle], rsi
0x1800323f8  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800323fc  mov     [rbp+Buffer], rsi
0x180032400  mov     r8d, 20801h; DesiredAccess
0x180032406  mov     [rbp+var_40], rsi
0x18003240a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18003240e  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180032412  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x180032416  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003241b  call    cs:__imp_LsaOpenPolicy
0x180032421  mov     ebx, eax
0x180032423  test    eax, eax
0x180032425  jns     short loc_180032481
0x180032427  test    byte ptr cs:g_dwDebugFlags, 3
0x18003242e  jz      short loc_180032461
0x180032430  mov     rcx, cs:g_pDebug
0x180032437  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x18003243e  mov     [rsp+70h+var_48], eax
0x180032442  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180032449  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180032450  mov     r8d, 140h
0x180032456  mov     [rsp+70h+var_50], rax
0x18003245b  call    cs:__imp_PuDbgPrint
0x180032461  mov     ecx, ebx; Status
0x180032463  call    cs:__imp_RtlNtStatusToDosError
0x180032469  mov     ebx, eax
0x18003246b  test    eax, eax
0x18003246d  jle     short loc_180032478
0x18003246f  movzx   ebx, ax
0x180032472  or      ebx, 80070000h
0x180032478  mov     [rbp+PolicyHandle], rsi
0x18003247c  jmp     loc_180032582
0x180032481  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180032485  lea     r8, [rbp+Buffer]; Buffer
0x180032489  mov     edx, 5; InformationClass
0x18003248e  call    cs:__imp_LsaQueryInformationPolicy
0x180032494  mov     ebx, eax
0x180032496  test    eax, eax
0x180032498  jns     short loc_1800324F4
0x18003249a  test    byte ptr cs:g_dwDebugFlags, 3
0x1800324a1  jz      short loc_1800324D4
0x1800324a3  mov     r8d, 15Bh
0x1800324a9  mov     rcx, cs:g_pDebug
0x1800324b0  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x1800324b7  mov     [rsp+70h+var_48], ebx
0x1800324bb  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x1800324c2  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800324c9  mov     [rsp+70h+var_50], rax
0x1800324ce  call    cs:__imp_PuDbgPrint
0x1800324d4  mov     ecx, ebx; Status
0x1800324d6  call    cs:__imp_RtlNtStatusToDosError
0x1800324dc  mov     ebx, eax
0x1800324de  test    eax, eax
0x1800324e0  jle     loc_180032582
0x1800324e6  movzx   ebx, ax
0x1800324e9  or      ebx, 80070000h
0x1800324ef  jmp     loc_180032582
0x1800324f4  mov     r8, [rbp+Buffer]
0x1800324f8  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800324fc  mov     edx, 100h; SizeInWords
0x180032501  mov     rcx, rdi; Destination
0x180032504  mov     r8, [r8+8]; Source
0x180032508  call    cs:__imp_wcsncpy_s
0x18003250e  cmp     eax, 50h ; 'P'
0x180032511  jnz     short loc_18003251A
0x180032513  mov     ebx, 8007007Ah
0x180032518  jmp     short loc_180032582
0x18003251a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18003251e  lea     r8, [rbp+var_40]; Buffer
0x180032522  mov     edx, 3; InformationClass
0x180032527  call    cs:__imp_LsaQueryInformationPolicy
0x18003252d  mov     ebx, eax
0x18003252f  test    eax, eax
0x180032531  jns     short loc_180032547
0x180032533  test    byte ptr cs:g_dwDebugFlags, 3
0x18003253a  jz      short loc_1800324D4
0x18003253c  mov     r8d, 17Ch
0x180032542  jmp     loc_1800324A9
0x180032547  mov     rax, [rbp+var_40]
0x18003254b  mov     ebx, esi
0x18003254d  cmp     [rax+10h], rsi
0x180032551  jz      short loc_18003257C
0x180032553  lea     rdx, [rdi+200h]; lpBuffer
0x18003255a  mov     dword ptr [rdi+0A00h], 1
0x180032564  lea     r8, [rbp+nSize]; nSize
0x180032568  mov     [rbp+nSize], 400h
0x18003256f  mov     ecx, 2; NameType
0x180032574  call    cs:__imp_GetComputerNameExW
0x18003257a  jmp     short loc_180032582
0x18003257c  mov     [rdi+0A00h], esi
0x180032582  mov     rcx, [rbp+Buffer]; Buffer
0x180032586  test    rcx, rcx
0x180032589  jz      short loc_180032595
0x18003258b  call    cs:__imp_LsaFreeMemory
0x180032591  mov     [rbp+Buffer], rsi
0x180032595  mov     rcx, [rbp+var_40]; Buffer
0x180032599  test    rcx, rcx
0x18003259c  jz      short loc_1800325A8
0x18003259e  call    cs:__imp_LsaFreeMemory
0x1800325a4  mov     [rbp+var_40], rsi
0x1800325a8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800325ac  test    rcx, rcx
0x1800325af  jz      short loc_1800325B7
0x1800325b1  call    cs:__imp_LsaClose
0x1800325b7  mov     eax, ebx
0x1800325b9  mov     rbx, [rsp+70h+arg_0]
0x1800325c1  add     rsp, 70h
0x1800325c5  pop     rdi
0x1800325c6  pop     rsi
0x1800325c7  pop     rbp
0x1800325c8  retn
```
