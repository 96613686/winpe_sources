# IIS_LOGON_PROVIDER::InitializeInstance(void)

- ea: `0x180011b80`
- end: `0x180011c4b`
- name: `?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000e1bc`

## callees

- `0x1800111ec`
- `0x180011b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011c00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011c00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011bd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011bd2`

## string_xrefs

- `0x180011baf`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::InitializeInstance(IIS_LOGON_PROVIDER *this)
{
  wchar_t *v1; // rbx
  LSTATUS v2; // eax
  __int64 result; // rax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int v5; // [rsp+54h] [rbp+1Ch]
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v5 = HIDWORD(this);
  v1 = ISAPI_REQUEST::sm_pLogonProvider;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"LastPriorityUPNLogon", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      *((_DWORD *)v1 + 641) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName(v1);
  if ( (int)result >= 0 )
    *((_DWORD *)v1 + 642) = 1;
  return result;
}

```

## disassembly

```asm
0x180011b80  mov     qword ptr [rsp-10h+Type], rcx
0x180011b85  push    rbp
0x180011b86  push    rbx
0x180011b87  mov     rbp, rsp
0x180011b8a  sub     rsp, 38h
0x180011b8e  mov     rbx, cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA; IIS_LOGON_PROVIDER * ISAPI_REQUEST::sm_pLogonProvider
0x180011b95  lea     rax, [rbp+hKey]
0x180011b99  mov     r9d, 20019h; samDesired
0x180011b9f  mov     [rsp+38h+phkResult], rax; phkResult
0x180011ba4  xor     r8d, r8d; ulOptions
0x180011ba7  mov     [rbp+hKey], 0
0x180011baf  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\in"...
0x180011bb6  mov     [rbp+Data], 0
0x180011bbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011bc4  mov     [rbp+Type], 0
0x180011bcb  mov     [rbp+cbData], 4
0x180011bd2  call    cs:__imp_RegOpenKeyExW
0x180011bd8  test    eax, eax
0x180011bda  jnz     short loc_180011C2E
0x180011bdc  mov     rcx, [rbp+hKey]; hKey
0x180011be0  lea     rax, [rbp+cbData]
0x180011be4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180011be9  lea     r9, [rbp+Type]; lpType
0x180011bed  lea     rax, [rbp+Data]
0x180011bf1  xor     r8d, r8d; lpReserved
0x180011bf4  lea     rdx, aLastpriorityup; "LastPriorityUPNLogon"
0x180011bfb  mov     [rsp+38h+phkResult], rax; lpData
0x180011c00  call    cs:__imp_RegQueryValueExW
0x180011c06  test    eax, eax
0x180011c08  jnz     short loc_180011C1C
0x180011c0a  cmp     [rbp+Type], 4
0x180011c0e  jnz     short loc_180011C1C
0x180011c10  cmp     [rbp+Data], eax
0x180011c13  setnz   al
0x180011c16  mov     [rbx+0A04h], eax
0x180011c1c  mov     rcx, [rbp+hKey]; hKey
0x180011c20  call    cs:__imp_RegCloseKey
0x180011c26  mov     [rbp+hKey], 0
0x180011c2e  mov     rcx, rbx; Destination
0x180011c31  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x180011c36  test    eax, eax
0x180011c38  js      short loc_180011C44
0x180011c3a  mov     dword ptr [rbx+0A08h], 1
0x180011c44  add     rsp, 38h
0x180011c48  pop     rbx
0x180011c49  pop     rbp
0x180011c4a  retn
```
