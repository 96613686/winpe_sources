# FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)

- ea: `0x1800383a4`
- end: `0x180038467`
- name: `?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z`
- size: `195`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800381e8`
- `0x180038220`
- `0x180038470`
- `0x180040dd4`

## callees

- `0x1800383a4`
- `0x18004d900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003841a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003841a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003843f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003843f`

## pseudocode

```c
__int64 __fastcall FastRegSetValueEx(HKEY hKey, LPCWSTR lpValueName, __int64 a3, const BYTE *a4, unsigned int a5)
{
  unsigned int Value; // ebx
  DWORD cbData[4]; // [rsp+30h] [rbp-258h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-248h] BYREF

  cbData[0] = 520;
  Value = RegQueryValueExW(hKey, lpValueName, 0, 0, Data, cbData);
  if ( Value || cbData[0] != 2LL * a5 || (unsigned int)_o__wcsnicmp(Data, a4, a5) )
    return (unsigned int)RegSetValueExW(hKey, lpValueName, 0, 1u, a4, 2 * a5);
  return Value;
}

```

## disassembly

```asm
0x1800383a4  push    rbx
0x1800383a6  push    rbp
0x1800383a7  push    rsi
0x1800383a8  push    rdi
0x1800383a9  push    r14
0x1800383ab  sub     rsp, 260h
0x1800383b2  mov     rax, cs:__security_cookie
0x1800383b9  xor     rax, rsp
0x1800383bc  mov     [rsp+288h+var_38], rax
0x1800383c4  lea     rax, [rsp+288h+cbData]
0x1800383c9  mov     [rsp+288h+cbData], 208h
0x1800383d1  mov     [rsp+288h+lpcbData], rax; lpcbData
0x1800383d6  mov     rsi, r9
0x1800383d9  lea     rax, [rsp+288h+Data]
0x1800383de  xor     r9d, r9d; lpType
0x1800383e1  xor     r8d, r8d; lpReserved
0x1800383e4  mov     [rsp+288h+lpData], rax; lpData
0x1800383e9  mov     r14, rdx
0x1800383ec  mov     rbp, rcx
0x1800383ef  call    cs:__imp_RegQueryValueExW
0x1800383f5  mov     edi, [rsp+288h+arg_20]
0x1800383fc  mov     ebx, eax
0x1800383fe  test    eax, eax
0x180038400  jnz     short loc_180038424
0x180038402  mov     ecx, [rsp+288h+cbData]
0x180038406  lea     rdx, [rdi+rdi]
0x18003840a  mov     r8d, edi
0x18003840d  cmp     rcx, rdx
0x180038410  jnz     short loc_180038424
0x180038412  mov     rdx, rsi
0x180038415  lea     rcx, [rsp+288h+Data]
0x18003841a  call    cs:__imp__o__wcsnicmp
0x180038420  test    eax, eax
0x180038422  jz      short loc_180038447
0x180038424  lea     eax, [rdi+rdi]
0x180038427  mov     r9d, 1; dwType
0x18003842d  mov     dword ptr [rsp+288h+lpcbData], eax; cbData
0x180038431  xor     r8d, r8d; Reserved
0x180038434  mov     rdx, r14; lpValueName
0x180038437  mov     [rsp+288h+lpData], rsi; lpData
0x18003843c  mov     rcx, rbp; hKey
0x18003843f  call    cs:__imp_RegSetValueExW
0x180038445  mov     ebx, eax
0x180038447  mov     eax, ebx
0x180038449  mov     rcx, [rsp+288h+var_38]
0x180038451  xor     rcx, rsp; StackCookie
0x180038454  call    __security_check_cookie
0x180038459  add     rsp, 260h
0x180038460  pop     r14
0x180038462  pop     rdi
0x180038463  pop     rsi
0x180038464  pop     rbp
0x180038465  pop     rbx
0x180038466  retn
```
