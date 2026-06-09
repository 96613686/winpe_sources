# PlaliCreateQuery(HKEY__ *,HKEY__ * &)

- ea: `0x18012ea3c`
- end: `0x18012eadc`
- name: `?PlaliCreateQuery@@YAKPEAUHKEY__@@AEAPEAU1@@Z`
- size: `160`
- prototype: `unsigned int(HKEY, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18012e71c`

## callees

- `0x18012ea3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ea7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ea7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012eac9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012eac9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012eabc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18012eabc`

## string_xrefs

- `0x18012ea73`: `System\CurrentControlSet\Services\SysmonLog`

## pseudocode

```c
__int64 __fastcall PlaliCreateQuery(HKEY a1, HKEY *a2)
{
  unsigned int v3; // ebx
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  *a2 = 0;
  v3 = RegOpenKeyExW(a1, L"System\\CurrentControlSet\\Services\\SysmonLog", 0, 0x2001Fu, &hKey);
  if ( !v3 )
  {
    v3 = RegCreateKeyExW(hKey, L"Log Queries", 0, 0, 0, 0x2001Fu, 0, a2, &dwDisposition);
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18012ea3c  mov     rax, rsp
0x18012ea3f  mov     [rax+8], rbx
0x18012ea43  push    rdi
0x18012ea44  sub     rsp, 50h
0x18012ea48  mov     qword ptr [rax+18h], 0
0x18012ea50  mov     rdi, rdx
0x18012ea53  mov     dword ptr [rax+10h], 0
0x18012ea5a  lea     rax, [rax+18h]
0x18012ea5e  mov     qword ptr [rdx], 0
0x18012ea65  mov     r9d, 2001Fh; samDesired
0x18012ea6b  xor     r8d, r8d; ulOptions
0x18012ea6e  mov     [rsp+58h+phkResult], rax; phkResult
0x18012ea73  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sy"...
0x18012ea7a  call    cs:__imp_RegOpenKeyExW
0x18012ea80  mov     ebx, eax
0x18012ea82  test    eax, eax
0x18012ea84  jnz     short loc_18012EACF
0x18012ea86  mov     rcx, [rsp+58h+hKey]; hKey
0x18012ea8b  lea     rax, [rsp+58h+dwDisposition]
0x18012ea90  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18012ea95  lea     rdx, aLogQueries; "Log Queries"
0x18012ea9c  mov     [rsp+58h+var_20], rdi; phkResult
0x18012eaa1  xor     r9d, r9d; lpClass
0x18012eaa4  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18012eaad  xor     r8d, r8d; Reserved
0x18012eab0  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18012eab8  mov     dword ptr [rsp+58h+phkResult], ebx; dwOptions
0x18012eabc  call    cs:__imp_RegCreateKeyExW
0x18012eac2  mov     rcx, [rsp+58h+hKey]; hKey
0x18012eac7  mov     ebx, eax
0x18012eac9  call    cs:__imp_RegCloseKey
0x18012eacf  mov     eax, ebx
0x18012ead1  mov     rbx, [rsp+58h+arg_0]
0x18012ead6  add     rsp, 50h
0x18012eada  pop     rdi
0x18012eadb  retn
```
