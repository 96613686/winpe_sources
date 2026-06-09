# GetPerformanceRegKey

- ea: `0x14002d330`
- end: `0x14002d3d5`
- name: `GetPerformanceRegKey`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400254b0`
- `0x14002d240`

## callees

- `0x140001020`
- `0x14002d330`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002d3a4`
- `ADVAPI32!RegCloseKey` at `0x14002d3a4`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d371`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d397`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d371`
- `ADVAPI32!RegOpenKeyExW` at `0x14002d397`

## pseudocode

```c
__int64 __fastcall GetPerformanceRegKey(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  if ( !a2 )
    return 13;
  hKey = 0;
  if ( RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
    return 2;
  if ( !hKey )
    return 2;
  v5 = RegOpenKeyExW(hKey, off_14009D7B0, 0, 0x20019u, a3);
  RegCloseKey(hKey);
  if ( v5 || !*a3 )
    return 2;
  else
    return 0;
}

```

## disassembly

```asm
0x14002d330  mov     [rsp+arg_18], rbx
0x14002d335  push    rdi
0x14002d336  sub     rsp, 40h
0x14002d33a  mov     rax, cs:__security_cookie
0x14002d341  xor     rax, rsp
0x14002d344  mov     [rsp+48h+var_10], rax
0x14002d349  mov     rdi, r8
0x14002d34c  test    rdx, rdx
0x14002d34f  jnz     short loc_14002D356
0x14002d351  lea     eax, [rdx+0Dh]
0x14002d354  jmp     short loc_14002D3BD
0x14002d356  and     [rsp+48h+hKey], 0
0x14002d35c  lea     rax, [rsp+48h+hKey]
0x14002d361  mov     ebx, 20019h
0x14002d366  mov     [rsp+48h+phkResult], rax; phkResult
0x14002d36b  mov     r9d, ebx; samDesired
0x14002d36e  xor     r8d, r8d; ulOptions
0x14002d371  call    cs:__imp_RegOpenKeyExW
0x14002d377  test    eax, eax
0x14002d379  jnz     short loc_14002D3B8
0x14002d37b  mov     rcx, [rsp+48h+hKey]; hKey
0x14002d380  test    rcx, rcx
0x14002d383  jz      short loc_14002D3B8
0x14002d385  mov     rdx, cs:off_14009D7B0; lpSubKey
0x14002d38c  mov     r9d, ebx; samDesired
0x14002d38f  xor     r8d, r8d; ulOptions
0x14002d392  mov     [rsp+48h+phkResult], rdi; phkResult
0x14002d397  call    cs:__imp_RegOpenKeyExW
0x14002d39d  mov     rcx, [rsp+48h+hKey]; hKey
0x14002d3a2  mov     ebx, eax
0x14002d3a4  call    cs:__imp_RegCloseKey
0x14002d3aa  test    ebx, ebx
0x14002d3ac  jnz     short loc_14002D3B8
0x14002d3ae  cmp     qword ptr [rdi], 0
0x14002d3b2  jz      short loc_14002D3B8
0x14002d3b4  xor     eax, eax
0x14002d3b6  jmp     short loc_14002D3BD
0x14002d3b8  mov     eax, 2
0x14002d3bd  mov     rcx, [rsp+48h+var_10]
0x14002d3c2  xor     rcx, rsp; StackCookie
0x14002d3c5  call    __security_check_cookie
0x14002d3ca  mov     rbx, [rsp+48h+arg_18]
0x14002d3cf  add     rsp, 40h
0x14002d3d3  pop     rdi
0x14002d3d4  retn
```
