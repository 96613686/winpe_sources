# Win32LiveSystemProvider::GetOsInfo(ulong *,ulong *,ulong *,ulong *,ushort *,ushort *,ushort *)

- ea: `0x180013340`
- end: `0x1800134df`
- name: `?GetOsInfo@Win32LiveSystemProvider@@UEAAJPEAK000PEAG11@Z`
- size: `415`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800249e0`

## callees

- `0x180001710`
- `0x180002164`
- `0x1800021f4`
- `0x180013340`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180013498`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180013498`
- `ntdll!RtlGetVersion` at `0x1800133b4`
- `ntdll!RtlGetVersion` at `0x1800133b4`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18001341e`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18001341e`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800134ad`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800134ad`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180013472`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180013472`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::GetOsInfo(
        Win32LiveSystemProvider *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8)
{
  NTSTATUS Version; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v17; // [rsp+158h] [rbp+58h]
  unsigned __int8 v18; // [rsp+15Ah] [rbp+5Ah]
  BYTE Data[16]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v20; // [rsp+170h] [rbp+70h]
  __int64 v21; // [rsp+180h] [rbp+80h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
    return Version | 0x10000000;
  *a2 = VersionInformation.dwPlatformId;
  *a3 = VersionInformation.dwMajorVersion;
  *a4 = VersionInformation.dwMinorVersion;
  *a5 = VersionInformation.dwBuildNumber;
  *a7 = v18;
  *a8 = v17;
  *a6 = 0;
  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    v21 = 0;
    cbData = 40;
    *(_OWORD *)Data = 0;
    v20 = 0;
    if ( !RegQueryValueExA(hKey, "CurrentType", 0, &Type, Data, &cbData) && Data[0] )
    {
      strlwr_s((char *)Data, 0x28u);
      if ( strstr((const char *)Data, "checked") )
        *a6 = 12;
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180013340  mov     [rsp-8+arg_0], rbx
0x180013345  push    rbp
0x180013346  push    rsi
0x180013347  push    rdi
0x180013348  push    r12
0x18001334a  push    r13
0x18001334c  push    r14
0x18001334e  push    r15
0x180013350  lea     rbp, [rsp-90h]
0x180013358  sub     rsp, 190h
0x18001335f  mov     rax, cs:__security_cookie
0x180013366  xor     rax, rsp
0x180013369  mov     [rbp+0C0h+var_38], rax
0x180013370  mov     r15, [rbp+0C0h+arg_20]
0x180013377  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x18001337c  mov     rbx, [rbp+0C0h+arg_28]
0x180013383  mov     rsi, r8
0x180013386  mov     r12, [rbp+0C0h+arg_30]
0x18001338d  mov     rdi, rdx
0x180013390  mov     r13, [rbp+0C0h+arg_38]
0x180013397  xor     edx, edx; Val
0x180013399  mov     r8d, 118h; Size
0x18001339f  mov     r14, r9
0x1800133a2  call    memset_0
0x1800133a7  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x1800133ac  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800133b4  call    cs:__imp_RtlGetVersion
0x1800133ba  test    eax, eax
0x1800133bc  jns     short loc_1800133C7
0x1800133be  bts     eax, 1Ch
0x1800133c2  jmp     loc_1800134B5
0x1800133c7  mov     eax, [rsp+1C0h+VersionInformation.dwPlatformId]
0x1800133cb  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800133d2  mov     [rdi], eax
0x1800133d4  mov     r9d, 20019h; samDesired
0x1800133da  mov     eax, [rsp+1C0h+VersionInformation.dwMajorVersion]
0x1800133de  xor     edi, edi
0x1800133e0  mov     [rsi], eax
0x1800133e2  xor     r8d, r8d; ulOptions
0x1800133e5  mov     eax, [rsp+1C0h+VersionInformation.dwMinorVersion]
0x1800133e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800133f0  mov     [r14], eax
0x1800133f3  mov     eax, [rsp+1C0h+VersionInformation.dwBuildNumber]
0x1800133f7  mov     [r15], eax
0x1800133fa  movzx   eax, [rbp+0C0h+var_66]
0x1800133fe  mov     [r12], ax
0x180013403  movzx   eax, [rbp+0C0h+var_68]
0x180013407  mov     [r13+0], ax
0x18001340c  lea     rax, [rsp+1C0h+hKey]
0x180013411  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180013416  mov     [rbx], di
0x180013419  mov     [rsp+1C0h+hKey], rdi
0x18001341e  call    cs:__imp_RegOpenKeyExA
0x180013424  test    eax, eax
0x180013426  jnz     loc_1800134B3
0x18001342c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180013431  lea     esi, [rdi+28h]
0x180013434  xor     eax, eax
0x180013436  mov     [rsp+1C0h+Type], edi
0x18001343a  mov     [rbp+0C0h+var_40], rax
0x180013441  lea     r9, [rsp+1C0h+Type]; lpType
0x180013446  xorps   xmm0, xmm0
0x180013449  mov     [rsp+1C0h+cbData], esi
0x18001344d  lea     rax, [rsp+1C0h+cbData]
0x180013452  xor     r8d, r8d; lpReserved
0x180013455  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18001345a  lea     rdx, aCurrenttype; "CurrentType"
0x180013461  lea     rax, [rbp+0C0h+Data]
0x180013465  mov     [rsp+1C0h+phkResult], rax; lpData
0x18001346a  movups  xmmword ptr [rbp+0C0h+Data], xmm0
0x18001346e  movups  [rbp+0C0h+var_50], xmm0
0x180013472  call    cs:__imp_RegQueryValueExA
0x180013478  test    eax, eax
0x18001347a  jnz     short loc_1800134A8
0x18001347c  cmp     [rbp+0C0h+Data], dil
0x180013480  jz      short loc_1800134A8
0x180013482  mov     edx, esi; Size
0x180013484  lea     rcx, [rbp+0C0h+Data]; String
0x180013488  call    _strlwr_s
0x18001348d  lea     rdx, aChecked; "checked"
0x180013494  lea     rcx, [rbp+0C0h+Data]; Str
0x180013498  call    cs:__imp_strstr
0x18001349e  test    rax, rax
0x1800134a1  jz      short loc_1800134A8
0x1800134a3  mov     word ptr [rbx], 0Ch
0x1800134a8  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800134ad  call    cs:__imp_RegCloseKey
0x1800134b3  xor     eax, eax
0x1800134b5  mov     rcx, [rbp+0C0h+var_38]
0x1800134bc  xor     rcx, rsp; StackCookie
0x1800134bf  call    __security_check_cookie
0x1800134c4  mov     rbx, [rsp+1C0h+arg_0]
0x1800134cc  add     rsp, 190h
0x1800134d3  pop     r15
0x1800134d5  pop     r14
0x1800134d7  pop     r13
0x1800134d9  pop     r12
0x1800134db  pop     rdi
0x1800134dc  pop     rsi
0x1800134dd  pop     rbp
0x1800134de  retn
```
