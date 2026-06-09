# Dhcpv6RegSetOptionRegVal

- ea: `0x180006d58`
- end: `0x180006ed0`
- name: `Dhcpv6RegSetOptionRegVal`
- size: `376`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, DWORD dwType, const BYTE *Buf2, DWORD cbData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028000`

## callees

- `0x180006d58`
- `0x180007564`
- `0x180030980`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006dad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006dad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006e17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006ebd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006e17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006ebd`

## pseudocode

```c
__int64 __fastcall Dhcpv6RegSetOptionRegVal(HKEY hkey, LPCWSTR lpValue, DWORD dwType, const BYTE *Buf2, DWORD cbData)
{
  void *v9; // rbx
  unsigned int ValueW; // edi
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwType[17]; // [rsp+44h] [rbp-44h] BYREF

  pdwType[0] = 0;
  pcbData = 500;
  v9 = (void *)DhcpAlloc(500);
  if ( !v9 )
    goto LABEL_2;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, pdwType, v9, &pcbData);
  if ( ValueW == 234 )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v9);
    v9 = (void *)DhcpAlloc(pcbData);
    if ( !v9 )
    {
LABEL_2:
      ValueW = RegSetValueExW(hkey, lpValue, 0, dwType, Buf2, cbData);
      goto LABEL_3;
    }
    ValueW = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, pdwType, v9, &pcbData);
  }
  if ( ValueW || pcbData != cbData || dwType != pdwType[0] || memcmp_0(v9, Buf2, cbData) )
    goto LABEL_2;
LABEL_3:
  if ( v9 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v9);
  return ValueW;
}

```

## disassembly

```asm
0x180006d58  push    rbx
0x180006d5a  push    rbp
0x180006d5b  push    rsi
0x180006d5c  push    rdi
0x180006d5d  push    r12
0x180006d5f  push    r14
0x180006d61  push    r15
0x180006d63  sub     rsp, 50h
0x180006d67  mov     r15, rcx
0x180006d6a  mov     [rsp+88h+pdwType], 0
0x180006d72  mov     ecx, 1F4h
0x180006d77  mov     r12, r9
0x180006d7a  mov     [rsp+88h+var_48], ecx
0x180006d7e  mov     ebp, r8d
0x180006d81  mov     r14, rdx
0x180006d84  call    DhcpAlloc
0x180006d89  mov     esi, [rsp+88h+arg_20]
0x180006d90  mov     rbx, rax
0x180006d93  test    rax, rax
0x180006d96  jnz     short loc_180006DF0
0x180006d98  mov     [rsp+88h+cbData], esi; cbData
0x180006d9c  mov     r9d, ebp; dwType
0x180006d9f  xor     r8d, r8d; Reserved
0x180006da2  mov     [rsp+88h+lpData], r12; lpData
0x180006da7  mov     rdx, r14; lpValueName
0x180006daa  mov     rcx, r15; hKey
0x180006dad  call    cs:__imp_RegSetValueExW
0x180006db4  nop     dword ptr [rax+rax+00h]
0x180006db9  mov     edi, eax
0x180006dbb  test    rbx, rbx
0x180006dbe  jz      short loc_180006DDE
0x180006dc0  mov     rcx, gs:60h
0x180006dc9  mov     r8, rbx; lpMem
0x180006dcc  xor     edx, edx; dwFlags
0x180006dce  mov     rcx, [rcx+30h]; hHeap
0x180006dd2  call    cs:__imp_HeapFree
0x180006dd9  nop     dword ptr [rax+rax+00h]
0x180006dde  mov     eax, edi
0x180006de0  add     rsp, 50h
0x180006de4  pop     r15
0x180006de6  pop     r14
0x180006de8  pop     r12
0x180006dea  pop     rdi
0x180006deb  pop     rsi
0x180006dec  pop     rbp
0x180006ded  pop     rbx
0x180006dee  retn
0x180006df0  lea     rax, [rsp+88h+var_48]
0x180006df5  mov     r9d, 0FFFFh; dwFlags
0x180006dfb  mov     [rsp+88h+pcbData], rax; pcbData
0x180006e00  mov     r8, r14; lpValue
0x180006e03  lea     rax, [rsp+88h+pdwType]
0x180006e08  mov     qword ptr [rsp+88h+cbData], rbx; pvData
0x180006e0d  xor     edx, edx; lpSubKey
0x180006e0f  mov     [rsp+88h+lpData], rax; pdwType
0x180006e14  mov     rcx, r15; hkey
0x180006e17  call    cs:__imp_RegGetValueW
0x180006e1e  nop     dword ptr [rax+rax+00h]
0x180006e23  mov     edi, eax
0x180006e25  cmp     eax, 0EAh
0x180006e2a  jz      short loc_180006E63
0x180006e2c  test    edi, edi
0x180006e2e  jnz     loc_180006D98
0x180006e34  cmp     [rsp+88h+var_48], esi
0x180006e38  jnz     loc_180006D98
0x180006e3e  cmp     ebp, [rsp+88h+pdwType]
0x180006e42  jnz     loc_180006D98
0x180006e48  mov     r8, rsi; Size
0x180006e4b  mov     rdx, r12; Buf2
0x180006e4e  mov     rcx, rbx; Buf1
0x180006e51  call    memcmp_0
0x180006e56  test    eax, eax
0x180006e58  jz      loc_180006DBB
0x180006e5e  jmp     loc_180006D98
0x180006e63  mov     rcx, gs:60h
0x180006e6c  mov     r8, rbx; lpMem
0x180006e6f  xor     edx, edx; dwFlags
0x180006e71  mov     rcx, [rcx+30h]; hHeap
0x180006e75  call    cs:__imp_HeapFree
0x180006e7c  nop     dword ptr [rax+rax+00h]
0x180006e81  mov     ecx, [rsp+88h+var_48]
0x180006e85  call    DhcpAlloc
0x180006e8a  mov     rbx, rax
0x180006e8d  test    rax, rax
0x180006e90  jz      loc_180006D98
0x180006e96  lea     rax, [rsp+88h+var_48]
0x180006e9b  mov     r9d, 0FFFFh; dwFlags
0x180006ea1  mov     [rsp+88h+pcbData], rax; pcbData
0x180006ea6  mov     r8, r14; lpValue
0x180006ea9  lea     rax, [rsp+88h+pdwType]
0x180006eae  mov     qword ptr [rsp+88h+cbData], rbx; pvData
0x180006eb3  xor     edx, edx; lpSubKey
0x180006eb5  mov     [rsp+88h+lpData], rax; pdwType
0x180006eba  mov     rcx, r15; hkey
0x180006ebd  call    cs:__imp_RegGetValueW
0x180006ec4  nop     dword ptr [rax+rax+00h]
0x180006ec9  mov     edi, eax
0x180006ecb  jmp     loc_180006E2C
```
