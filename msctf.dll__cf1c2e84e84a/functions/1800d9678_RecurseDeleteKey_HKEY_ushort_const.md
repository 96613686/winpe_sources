# RecurseDeleteKey(HKEY__ *,ushort const *)

- ea: `0x1800d9678`
- end: `0x1800d97a5`
- name: `?RecurseDeleteKey@@YAJPEAUHKEY__@@PEBG@Z`
- size: `301`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800d9678`
- `0x1800d97ac`

## callees

- `0x1800d9678`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d96d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d96d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9763`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d9779`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d9779`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d9754`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d9754`

## pseudocode

```c
__int64 __fastcall RecurseDeleteKey(HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v5; // ebx
  LSTATUS i; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  ftLastWriteTime = 0;
  cchName = 256;
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &hKeya) )
    return 0;
  v5 = 0;
  for ( i = RegEnumKeyExW(hKeya, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
        !i;
        i = RegEnumKeyExW(hKeya, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
  {
    v5 = RecurseDeleteKey(hKeya, Name);
    if ( v5 )
      break;
    cchName = 256;
  }
  RegCloseKey(hKeya);
  if ( !v5 )
    return (unsigned int)RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x1800d9678  mov     [rsp-8+arg_10], rbx
0x1800d967d  push    rbp
0x1800d967e  push    rsi
0x1800d967f  push    rdi
0x1800d9680  lea     rbp, [rsp-170h]
0x1800d9688  sub     rsp, 270h
0x1800d968f  mov     rax, cs:__security_cookie
0x1800d9696  xor     rax, rsp
0x1800d9699  mov     [rbp+180h+var_20], rax
0x1800d96a0  lea     rax, [rsp+280h+hKey]
0x1800d96a5  mov     [rsp+280h+hKey], 0
0x1800d96ae  mov     r9d, 2000000h; samDesired
0x1800d96b4  mov     [rsp+280h+phkResult], rax; phkResult
0x1800d96b9  xor     r8d, r8d; ulOptions
0x1800d96bc  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x1800d96c5  mov     rsi, rdx
0x1800d96c8  mov     [rsp+280h+cchName], 100h
0x1800d96d0  mov     rdi, rcx
0x1800d96d3  call    cs:__imp_RegOpenKeyExW
0x1800d96d9  test    eax, eax
0x1800d96db  jz      short loc_1800D96E4
0x1800d96dd  xor     eax, eax
0x1800d96df  jmp     loc_1800D9783
0x1800d96e4  xor     ebx, ebx
0x1800d96e6  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800d96eb  mov     [rsp+280h+lpftLastWriteTime], rax
0x1800d96f0  mov     [rsp+280h+lpcchClass], rbx
0x1800d96f5  mov     [rsp+280h+lpClass], rbx
0x1800d96fa  mov     [rsp+280h+phkResult], rbx
0x1800d96ff  jmp     short loc_1800D9743
0x1800d9701  mov     rcx, [rsp+280h+hKey]; hKey
0x1800d9706  lea     rdx, [rsp+280h+Name]; lpSubKey
0x1800d970b  call    ?RecurseDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; RecurseDeleteKey(HKEY__ *,ushort const *)
0x1800d9710  mov     ebx, eax
0x1800d9712  test    eax, eax
0x1800d9714  jnz     short loc_1800D975E
0x1800d9716  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800d971b  mov     [rsp+280h+cchName], 100h
0x1800d9723  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800d9728  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800d9731  mov     [rsp+280h+lpClass], 0; lpClass
0x1800d973a  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800d9743  mov     rcx, [rsp+280h+hKey]; hKey
0x1800d9748  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800d974d  lea     r8, [rsp+280h+Name]; lpName
0x1800d9752  xor     edx, edx; dwIndex
0x1800d9754  call    cs:__imp_RegEnumKeyExW
0x1800d975a  test    eax, eax
0x1800d975c  jz      short loc_1800D9701
0x1800d975e  mov     rcx, [rsp+280h+hKey]; hKey
0x1800d9763  call    cs:__imp_RegCloseKey
0x1800d9769  test    ebx, ebx
0x1800d976b  jnz     short loc_1800D9781
0x1800d976d  xor     r9d, r9d; Reserved
0x1800d9770  xor     r8d, r8d; samDesired
0x1800d9773  mov     rdx, rsi; lpSubKey
0x1800d9776  mov     rcx, rdi; hKey
0x1800d9779  call    cs:__imp_RegDeleteKeyExW
0x1800d977f  mov     ebx, eax
0x1800d9781  mov     eax, ebx
0x1800d9783  mov     rcx, [rbp+180h+var_20]
0x1800d978a  xor     rcx, rsp; StackCookie
0x1800d978d  call    __security_check_cookie
0x1800d9792  mov     rbx, [rsp+280h+arg_10]
0x1800d979a  add     rsp, 270h
0x1800d97a1  pop     rdi
0x1800d97a2  pop     rsi
0x1800d97a3  pop     rbp
0x1800d97a4  retn
```
