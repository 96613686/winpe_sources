# IIS_LOGON_PROVIDER::InitializeInstance(void)

- ea: `0x180035f10`
- end: `0x180035fed`
- name: `?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ`
- size: `221`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800147d0`

## callees

- `0x1800353bc`
- `0x180035f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035f5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035f91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035f91`

## string_xrefs

- `0x180035f56`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::InitializeInstance(wchar_t *Destination)
{
  LSTATUS v2; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

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
      *((_DWORD *)Destination + 641) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName(Destination);
  if ( (int)result >= 0 )
    *((_DWORD *)Destination + 642) = 1;
  return result;
}

```

## disassembly

```asm
0x180035f10  mov     [rsp-8+arg_0], rbx
0x180035f15  push    rbp
0x180035f16  mov     rbp, rsp
0x180035f19  sub     rsp, 40h
0x180035f1d  mov     rbx, rcx
0x180035f20  mov     [rbp+hKey], 0
0x180035f28  lea     rax, [rbp+hKey]
0x180035f2c  mov     [rbp+Data], 0
0x180035f33  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035f3a  mov     [rsp+40h+phkResult], rax; phkResult
0x180035f3f  mov     r9d, 20019h; samDesired
0x180035f45  mov     [rbp+Type], 0
0x180035f4c  xor     r8d, r8d; ulOptions
0x180035f4f  mov     [rbp+cbData], 4
0x180035f56  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\in"...
0x180035f5d  call    cs:__imp_RegOpenKeyExW
0x180035f64  nop     dword ptr [rax+rax+00h]
0x180035f69  test    eax, eax
0x180035f6b  jnz     short loc_180035FCB
0x180035f6d  mov     rcx, [rbp+hKey]; hKey
0x180035f71  lea     rax, [rbp+cbData]
0x180035f75  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180035f7a  lea     r9, [rbp+Type]; lpType
0x180035f7e  lea     rax, [rbp+Data]
0x180035f82  xor     r8d, r8d; lpReserved
0x180035f85  lea     rdx, aLastpriorityup; "LastPriorityUPNLogon"
0x180035f8c  mov     [rsp+40h+phkResult], rax; lpData
0x180035f91  call    cs:__imp_RegQueryValueExW
0x180035f98  nop     dword ptr [rax+rax+00h]
0x180035f9d  test    eax, eax
0x180035f9f  jnz     short loc_180035FB3
0x180035fa1  cmp     [rbp+Type], 4
0x180035fa5  jnz     short loc_180035FB3
0x180035fa7  cmp     [rbp+Data], eax
0x180035faa  setnz   al
0x180035fad  mov     [rbx+0A04h], eax
0x180035fb3  mov     rcx, [rbp+hKey]; hKey
0x180035fb7  call    cs:__imp_RegCloseKey
0x180035fbe  nop     dword ptr [rax+rax+00h]
0x180035fc3  mov     [rbp+hKey], 0
0x180035fcb  mov     rcx, rbx; Destination
0x180035fce  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x180035fd3  test    eax, eax
0x180035fd5  js      short loc_180035FE1
0x180035fd7  mov     dword ptr [rbx+0A08h], 1
0x180035fe1  mov     rbx, [rsp+40h+arg_0]
0x180035fe6  add     rsp, 40h
0x180035fea  pop     rbp
0x180035feb  retn
```
