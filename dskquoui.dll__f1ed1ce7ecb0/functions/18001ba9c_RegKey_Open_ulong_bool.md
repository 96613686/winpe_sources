# RegKey::Open(ulong,bool)

- ea: `0x18001ba9c`
- end: `0x18001bb32`
- name: `?Open@RegKey@@QEBAJK_N@Z`
- size: `150`
- prototype: `int(RegKey *__hidden this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009b34`
- `0x18000c224`
- `0x18000fc54`

## callees

- `0x18001ba9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bb04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bb04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bac0`

## pseudocode

```c
LSTATUS __fastcall RegKey::Open(RegKey *this, REGSAM a2, char a3)
{
  HKEY *phkResult; // rdi
  HKEY v5; // rcx
  LPCWSTR *v8; // rdx
  HKEY v9; // rcx
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+90h] [rbp+18h] BYREF

  phkResult = (HKEY *)((char *)this + 16);
  v5 = (HKEY)*((_QWORD *)this + 2);
  if ( v5 )
  {
    *phkResult = 0;
    RegCloseKey(v5);
  }
  v8 = (LPCWSTR *)*((_QWORD *)this + 4);
  v9 = (HKEY)*((_QWORD *)this + 1);
  if ( a3 )
  {
    dwDisposition = 0;
    result = RegCreateKeyExW(v9, *v8, 0, 0, 0, a2, 0, phkResult, &dwDisposition);
  }
  else
  {
    result = RegOpenKeyExW(v9, *v8, 0, a2, phkResult);
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001ba9c  push    rbx
0x18001ba9e  push    rbp
0x18001ba9f  push    rsi
0x18001baa0  push    rdi
0x18001baa1  sub     rsp, 58h
0x18001baa5  lea     rdi, [rcx+10h]
0x18001baa9  mov     rbx, rcx
0x18001baac  mov     rcx, [rdi]; hKey
0x18001baaf  mov     sil, r8b
0x18001bab2  mov     ebp, edx
0x18001bab4  test    rcx, rcx
0x18001bab7  jz      short loc_18001BAC6
0x18001bab9  mov     qword ptr [rdi], 0
0x18001bac0  call    cs:__imp_RegCloseKey
0x18001bac6  mov     rdx, [rbx+20h]
0x18001baca  xor     r8d, r8d; ulOptions
0x18001bacd  mov     rcx, [rbx+8]; hKey
0x18001bad1  test    sil, sil
0x18001bad4  jz      short loc_18001BB0C
0x18001bad6  lea     rax, [rsp+78h+dwDisposition]
0x18001bade  mov     [rsp+78h+dwDisposition], r8d
0x18001bae6  mov     rdx, [rdx]; lpSubKey
0x18001bae9  xor     r9d, r9d; lpClass
0x18001baec  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001baf1  mov     [rsp+78h+phkResult], rdi; phkResult
0x18001baf6  mov     [rsp+78h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18001bafb  mov     [rsp+78h+samDesired], ebp; samDesired
0x18001baff  mov     [rsp+78h+dwOptions], r8d; dwOptions
0x18001bb04  call    cs:__imp_RegCreateKeyExW
0x18001bb0a  jmp     short loc_18001BB1D
0x18001bb0c  mov     rdx, [rdx]; lpSubKey
0x18001bb0f  mov     r9d, ebp; samDesired
0x18001bb12  mov     qword ptr [rsp+78h+dwOptions], rdi; phkResult
0x18001bb17  call    cs:__imp_RegOpenKeyExW
0x18001bb1d  test    eax, eax
0x18001bb1f  jle     short loc_18001BB29
0x18001bb21  movzx   eax, ax
0x18001bb24  or      eax, 80070000h
0x18001bb29  add     rsp, 58h
0x18001bb2d  pop     rdi
0x18001bb2e  pop     rsi
0x18001bb2f  pop     rbp
0x18001bb30  pop     rbx
0x18001bb31  retn
```
