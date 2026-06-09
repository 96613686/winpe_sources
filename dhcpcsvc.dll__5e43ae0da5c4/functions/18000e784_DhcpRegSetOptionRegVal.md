# DhcpRegSetOptionRegVal

- ea: `0x18000e784`
- end: `0x18000e8a8`
- name: `DhcpRegSetOptionRegVal`
- size: `292`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, DWORD dwType, void *Buf2, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e1e0`

## callees

- `0x180001f90`
- `0x180002160`
- `0x18000e784`
- `0x180010aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e7f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e841`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e7f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e87f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e87f`

## pseudocode

```c
__int64 __fastcall DhcpRegSetOptionRegVal(
        HKEY hKey,
        LPCWSTR lpValueName,
        __int64 dwType,
        const BYTE *Buf2,
        size_t Size)
{
  DWORD v7; // r14d
  PVOID pvData; // rbx
  unsigned int ValueW; // edi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 pdwType; // [rsp+40h] [rbp-18h] BYREF
  PVOID v15[2]; // [rsp+48h] [rbp-10h] BYREF

  pdwType = 500;
  v7 = dwType;
  pvData = (PVOID)DhcpAlloc(500, lpValueName, dwType);
  v15[0] = pvData;
  if ( !pvData )
    goto LABEL_8;
  ValueW = RegGetValueW(hKey, 0, lpValueName, 0xFFFFu, (LPDWORD)&pdwType + 1, pvData, (LPDWORD)&pdwType);
  if ( ValueW == 234 )
  {
    DhcpFree(v15);
    v15[0] = (PVOID)DhcpAlloc((unsigned int)pdwType, v11, v12);
    pvData = v15[0];
    if ( !v15[0] )
    {
LABEL_8:
      ValueW = RegSetValueExW(hKey, lpValueName, 0, v7, Buf2, Size);
      goto LABEL_9;
    }
    ValueW = RegGetValueW(hKey, 0, lpValueName, 0xFFFFu, (LPDWORD)&pdwType + 1, v15[0], (LPDWORD)&pdwType);
  }
  if ( ValueW || __PAIR64__(v7, Size) != pdwType || memcmp_0(pvData, Buf2, (unsigned int)Size) )
    goto LABEL_8;
LABEL_9:
  if ( pvData )
    DhcpFree(v15);
  return ValueW;
}

```

## disassembly

```asm
0x18000e784  push    rbp
0x18000e786  push    rbx
0x18000e787  push    rsi
0x18000e788  push    rdi
0x18000e789  push    r12
0x18000e78b  push    r13
0x18000e78d  push    r14
0x18000e78f  push    r15
0x18000e791  mov     rbp, rsp
0x18000e794  sub     rsp, 58h
0x18000e798  mov     r12, rcx
0x18000e79b  mov     dword ptr [rbp+var_18+4], 0
0x18000e7a2  mov     ecx, 1F4h
0x18000e7a7  mov     r13, r9
0x18000e7aa  mov     dword ptr [rbp+var_18], ecx
0x18000e7ad  mov     r14d, r8d
0x18000e7b0  mov     r15, rdx
0x18000e7b3  call    DhcpAlloc
0x18000e7b8  mov     esi, dword ptr [rbp+Size]
0x18000e7bb  mov     rbx, rax
0x18000e7be  mov     [rbp+var_10], rax
0x18000e7c2  test    rax, rax
0x18000e7c5  jz      loc_18000E86A
0x18000e7cb  lea     rax, [rbp+var_18]
0x18000e7cf  mov     r9d, 0FFFFh; dwFlags
0x18000e7d5  mov     [rsp+58h+pcbData], rax; pcbData
0x18000e7da  mov     r8, r15; lpValue
0x18000e7dd  lea     rax, [rbp+var_18+4]
0x18000e7e1  mov     [rsp+58h+pvData], rbx; pvData
0x18000e7e6  xor     edx, edx; lpSubKey
0x18000e7e8  mov     [rsp+58h+pdwType], rax; pdwType
0x18000e7ed  mov     rcx, r12; hkey
0x18000e7f0  call    cs:__imp_RegGetValueW
0x18000e7f6  mov     edi, eax
0x18000e7f8  cmp     eax, 0EAh
0x18000e7fd  jnz     short loc_18000E849
0x18000e7ff  lea     rcx, [rbp+var_10]
0x18000e803  call    DhcpFree
0x18000e808  mov     ecx, dword ptr [rbp+var_18]
0x18000e80b  call    DhcpAlloc
0x18000e810  mov     [rbp+var_10], rax
0x18000e814  mov     rbx, rax
0x18000e817  test    rax, rax
0x18000e81a  jz      short loc_18000E86A
0x18000e81c  lea     rax, [rbp+var_18]
0x18000e820  mov     r9d, 0FFFFh; dwFlags
0x18000e826  mov     [rsp+58h+pcbData], rax; pcbData
0x18000e82b  mov     r8, r15; lpValue
0x18000e82e  lea     rax, [rbp+var_18+4]
0x18000e832  mov     [rsp+58h+pvData], rbx; pvData
0x18000e837  xor     edx, edx; lpSubKey
0x18000e839  mov     [rsp+58h+pdwType], rax; pdwType
0x18000e83e  mov     rcx, r12; hkey
0x18000e841  call    cs:__imp_RegGetValueW
0x18000e847  mov     edi, eax
0x18000e849  test    edi, edi
0x18000e84b  jnz     short loc_18000E86A
0x18000e84d  cmp     dword ptr [rbp+var_18], esi
0x18000e850  jnz     short loc_18000E86A
0x18000e852  cmp     r14d, dword ptr [rbp+var_18+4]
0x18000e856  jnz     short loc_18000E86A
0x18000e858  mov     r8, rsi; Size
0x18000e85b  mov     rdx, r13; Buf2
0x18000e85e  mov     rcx, rbx; Buf1
0x18000e861  call    memcmp_0
0x18000e866  test    eax, eax
0x18000e868  jz      short loc_18000E887
0x18000e86a  mov     dword ptr [rsp+58h+pvData], esi; cbData
0x18000e86e  mov     r9d, r14d; dwType
0x18000e871  xor     r8d, r8d; Reserved
0x18000e874  mov     [rsp+58h+pdwType], r13; lpData
0x18000e879  mov     rdx, r15; lpValueName
0x18000e87c  mov     rcx, r12; hKey
0x18000e87f  call    cs:__imp_RegSetValueExW
0x18000e885  mov     edi, eax
0x18000e887  test    rbx, rbx
0x18000e88a  jz      short loc_18000E895
0x18000e88c  lea     rcx, [rbp+var_10]
0x18000e890  call    DhcpFree
0x18000e895  mov     eax, edi
0x18000e897  add     rsp, 58h
0x18000e89b  pop     r15
0x18000e89d  pop     r14
0x18000e89f  pop     r13
0x18000e8a1  pop     r12
0x18000e8a3  pop     rdi
0x18000e8a4  pop     rsi
0x18000e8a5  pop     rbx
0x18000e8a6  pop     rbp
0x18000e8a7  retn
```
