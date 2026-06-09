# GetRegistryValue(ushort *,ushort * *,_RAREGHIVE)

- ea: `0x140035b20`
- end: `0x140035cfd`
- name: `?GetRegistryValue@@YAJPEAGPEAPEAGW4_RAREGHIVE@@@Z`
- size: `477`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000ea24`
- `0x14001c458`
- `0x140035d04`
- `0x14003af44`

## callees

- `0x1400020f4`
- `0x140002463`
- `0x140034ce4`
- `0x140035b20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140035ce0`
- `ADVAPI32!RegCloseKey` at `0x140035ce0`
- `ADVAPI32!RegOpenKeyExW` at `0x140035bb7`
- `ADVAPI32!RegOpenKeyExW` at `0x140035bb7`
- `ADVAPI32!RegQueryValueExW` at `0x140035bfe`
- `ADVAPI32!RegQueryValueExW` at `0x140035ca4`
- `ADVAPI32!RegQueryValueExW` at `0x140035bfe`
- `ADVAPI32!RegQueryValueExW` at `0x140035ca4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140035cb9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140035cb9`

## string_xrefs

- `0x140035c5a`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x140035b8d`: `Software\policies\Microsoft\Windows NT\Terminal Services`
- `0x140035b72`: `SYSTEM\CurrentControlSet\Services\W32Time\Parameters`
- `0x140035c40`: `GetRegistryValue`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(const WCHAR *a1, BYTE **a2, int a3)
{
  __int64 v4; // rcx
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  bool v13; // cc
  unsigned __int64 v14; // rax
  BYTE *v15; // rax
  CEventLogger *v16; // rcx
  BYTE *v17; // rdi
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 0;
  v4 = -2147483647;
  v6 = a3 - 2;
  if ( !v6 )
  {
    v10 = L"System\\CurrentControlSet\\Control\\Remote Assistance";
    goto LABEL_12;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services";
    goto LABEL_12;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v10 = L"Software\\Clients\\Mail";
    goto LABEL_12;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v10 = L"Software\\Clients\\Mail";
    goto LABEL_13;
  }
  if ( v9 == 1 )
  {
    v10 = L"SYSTEM\\CurrentControlSet\\Services\\W32Time\\Parameters";
LABEL_12:
    v4 = -2147483646;
    goto LABEL_13;
  }
  v10 = L"Software\\Microsoft\\Remote Assistance";
LABEL_13:
  v11 = RegOpenKeyExW((HKEY)v4, v10, 0, 1u, &hKey);
  v12 = v11;
  v13 = v11 <= 0;
  if ( v11 || (v11 = RegQueryValueExW(hKey, a1, 0, 0, 0, &cbData), v12 = v11, v13 = v11 <= 0, v11) )
  {
    if ( v13 )
      goto LABEL_26;
    v12 = (unsigned __int16)v11;
    goto LABEL_16;
  }
  v14 = 2 * (cbData + 2LL);
  if ( !is_mul_ok(cbData + 2LL, 2u) )
    v14 = -1;
  v15 = (BYTE *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v17 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    CEventLogger::LogError(
      v16,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x1E3u,
      L"GetRegistryValue",
      0x8007000E);
    goto LABEL_26;
  }
  memset_0(v15, 0, cbData + 2LL);
  v12 = RegQueryValueExW(hKey, a1, 0, 0, v17, &cbData);
  if ( v12 )
  {
    operator delete[](v17);
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12;
LABEL_16:
      v12 |= 0x80070000;
    }
  }
  else
  {
    v12 = 0;
    *a2 = v17;
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140035b20  mov     [rsp+arg_0], rbx
0x140035b25  push    rsi
0x140035b26  push    rdi
0x140035b27  push    r14
0x140035b29  sub     rsp, 30h
0x140035b2d  mov     [rsp+48h+hKey], 0
0x140035b36  mov     rsi, rcx
0x140035b39  mov     [rsp+48h+cbData], 0
0x140035b41  mov     rcx, 0FFFFFFFF80000001h
0x140035b48  mov     r14, rdx
0x140035b4b  sub     r8d, 2
0x140035b4f  jz      short loc_140035B96
0x140035b51  sub     r8d, 1
0x140035b55  jz      short loc_140035B8D
0x140035b57  sub     r8d, 1
0x140035b5b  jz      short loc_140035B84
0x140035b5d  sub     r8d, 1
0x140035b61  jz      short loc_140035B7B
0x140035b63  cmp     r8d, 1
0x140035b67  jz      short loc_140035B72
0x140035b69  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x140035b70  jmp     short loc_140035BA4
0x140035b72  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\W3"...
0x140035b79  jmp     short loc_140035B9D
0x140035b7b  lea     rdx, aSoftwareClient; "Software\\Clients\\Mail"
0x140035b82  jmp     short loc_140035BA4
0x140035b84  lea     rdx, aSoftwareClient; "Software\\Clients\\Mail"
0x140035b8b  jmp     short loc_140035B9D
0x140035b8d  lea     rdx, aSoftwarePolici; "Software\\policies\\Microsoft\\Windows "...
0x140035b94  jmp     short loc_140035B9D
0x140035b96  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Rem"...
0x140035b9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140035ba4  lea     rax, [rsp+48h+hKey]
0x140035ba9  mov     r9d, 1; samDesired
0x140035baf  xor     r8d, r8d; ulOptions
0x140035bb2  mov     [rsp+48h+phkResult], rax; phkResult
0x140035bb7  call    cs:__imp_RegOpenKeyExW
0x140035bbe  nop     dword ptr [rax+rax+00h]
0x140035bc3  mov     ebx, eax
0x140035bc5  test    eax, eax
0x140035bc7  jz      short loc_140035BDD
0x140035bc9  jle     loc_140035CD6
0x140035bcf  movzx   ebx, ax
0x140035bd2  or      ebx, 80070000h
0x140035bd8  jmp     loc_140035CD6
0x140035bdd  mov     rcx, [rsp+48h+hKey]; hKey
0x140035be2  lea     rax, [rsp+48h+cbData]
0x140035be7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140035bec  xor     r9d, r9d; lpType
0x140035bef  xor     r8d, r8d; lpReserved
0x140035bf2  mov     [rsp+48h+phkResult], 0; lpData
0x140035bfb  mov     rdx, rsi; lpValueName
0x140035bfe  call    cs:__imp_RegQueryValueExW
0x140035c05  nop     dword ptr [rax+rax+00h]
0x140035c0a  mov     ebx, eax
0x140035c0c  test    eax, eax
0x140035c0e  jnz     short loc_140035BC9
0x140035c10  mov     ecx, [rsp+48h+cbData]
0x140035c14  lea     eax, [rbx+2]
0x140035c17  add     rcx, 2
0x140035c1b  mul     rcx
0x140035c1e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140035c25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035c2c  cmovb   rax, rcx
0x140035c30  mov     rcx, rax; unsigned __int64
0x140035c33  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140035c38  mov     rdi, rax
0x140035c3b  test    rax, rax
0x140035c3e  jnz     short loc_140035C74
0x140035c40  lea     rax, aGetregistryval; "GetRegistryValue"
0x140035c47  mov     dword ptr [rsp+48h+lpcbData], 8007000Eh; unsigned int
0x140035c4f  mov     r9d, 1E3h; unsigned int
0x140035c55  mov     [rsp+48h+phkResult], rax; unsigned __int16 *
0x140035c5a  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x140035c61  mov     ebx, 8007000Eh
0x140035c66  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140035c6d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140035c72  jmp     short loc_140035CD6
0x140035c74  mov     r8d, [rsp+48h+cbData]
0x140035c79  xor     edx, edx; Val
0x140035c7b  add     r8, 2; Size
0x140035c7f  mov     rcx, rdi; void *
0x140035c82  call    memset_0
0x140035c87  mov     rcx, [rsp+48h+hKey]; hKey
0x140035c8c  lea     rax, [rsp+48h+cbData]
0x140035c91  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140035c96  xor     r9d, r9d; lpType
0x140035c99  xor     r8d, r8d; lpReserved
0x140035c9c  mov     [rsp+48h+phkResult], rdi; lpData
0x140035ca1  mov     rdx, rsi; lpValueName
0x140035ca4  call    cs:__imp_RegQueryValueExW
0x140035cab  nop     dword ptr [rax+rax+00h]
0x140035cb0  mov     ebx, eax
0x140035cb2  test    eax, eax
0x140035cb4  jz      short loc_140035CD1
0x140035cb6  mov     rcx, rdi
0x140035cb9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140035cc0  nop     dword ptr [rax+rax+00h]
0x140035cc5  test    ebx, ebx
0x140035cc7  jle     short loc_140035CD6
0x140035cc9  movzx   ebx, bx
0x140035ccc  jmp     loc_140035BD2
0x140035cd1  xor     ebx, ebx
0x140035cd3  mov     [r14], rdi
0x140035cd6  mov     rcx, [rsp+48h+hKey]; hKey
0x140035cdb  test    rcx, rcx
0x140035cde  jz      short loc_140035CEC
0x140035ce0  call    cs:__imp_RegCloseKey
0x140035ce7  nop     dword ptr [rax+rax+00h]
0x140035cec  mov     eax, ebx
0x140035cee  mov     rbx, [rsp+48h+arg_0]
0x140035cf3  add     rsp, 30h
0x140035cf7  pop     r14
0x140035cf9  pop     rdi
0x140035cfa  pop     rsi
0x140035cfb  retn
```
