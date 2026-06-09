# DhcpRegSetOptionRegVal

- ea: `0x1800062f4`
- end: `0x180006431`
- name: `DhcpRegSetOptionRegVal`
- size: `317`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, DWORD dwType, const BYTE *Buf2, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800438b0`

## callees

- `0x1800057f0`
- `0x1800062f4`
- `0x180006440`
- `0x180047e30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800063d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800063d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006364`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006424`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006364`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006424`

## pseudocode

```c
__int64 __fastcall DhcpRegSetOptionRegVal(HKEY hkey, LPCWSTR lpValue, DWORD dwType, const BYTE *Buf2, size_t Size)
{
  void *pvData; // rbx
  unsigned int ValueW; // edi
  __int64 pdwType; // [rsp+40h] [rbp-48h] BYREF
  LPVOID v13; // [rsp+48h] [rbp-40h] BYREF

  pdwType = 500;
  pvData = DhcpAlloc(0x1F4u);
  v13 = pvData;
  if ( !pvData )
    goto LABEL_9;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, (LPDWORD)&pdwType + 1, pvData, (LPDWORD)&pdwType);
  if ( ValueW == 234 )
  {
    DhcpPunycodeFree(&v13);
    pvData = DhcpAlloc((unsigned int)pdwType);
    if ( !pvData )
    {
LABEL_9:
      ValueW = RegSetValueExW(hkey, lpValue, 0, dwType, Buf2, Size);
      goto LABEL_6;
    }
    ValueW = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, (LPDWORD)&pdwType + 1, pvData, (LPDWORD)&pdwType);
  }
  if ( ValueW || __PAIR64__(dwType, Size) != pdwType || memcmp_0(pvData, Buf2, (unsigned int)Size) )
    goto LABEL_9;
LABEL_6:
  if ( pvData )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, pvData);
  return ValueW;
}

```

## disassembly

```asm
0x1800062f4  push    rbx
0x1800062f6  push    rbp
0x1800062f7  push    rsi
0x1800062f8  push    rdi
0x1800062f9  push    r12
0x1800062fb  push    r14
0x1800062fd  push    r15
0x1800062ff  sub     rsp, 50h
0x180006303  mov     r15, rcx
0x180006306  mov     dword ptr [rsp+88h+var_48+4], 0
0x18000630e  mov     ecx, 1F4h
0x180006313  mov     r12, r9
0x180006316  mov     dword ptr [rsp+88h+var_48], ecx
0x18000631a  mov     ebp, r8d
0x18000631d  mov     r14, rdx
0x180006320  call    DhcpAlloc
0x180006325  mov     esi, dword ptr [rsp+88h+Size]
0x18000632c  mov     rbx, rax
0x18000632f  mov     [rsp+88h+var_40], rax
0x180006334  test    rax, rax
0x180006337  jz      loc_1800063C3
0x18000633d  lea     rax, [rsp+88h+var_48]
0x180006342  mov     r9d, 0FFFFh; dwFlags
0x180006348  mov     [rsp+88h+pcbData], rax; pcbData
0x18000634d  mov     r8, r14; lpValue
0x180006350  lea     rax, [rsp+88h+var_48+4]
0x180006355  mov     [rsp+88h+pvData], rbx; pvData
0x18000635a  xor     edx, edx; lpSubKey
0x18000635c  mov     [rsp+88h+pdwType], rax; pdwType
0x180006361  mov     rcx, r15; hkey
0x180006364  call    cs:__imp_RegGetValueW
0x18000636a  mov     edi, eax
0x18000636c  cmp     eax, 0EAh
0x180006371  jz      short loc_1800063E2
0x180006373  test    edi, edi
0x180006375  jnz     short loc_1800063C3
0x180006377  cmp     dword ptr [rsp+88h+var_48], esi
0x18000637b  jnz     short loc_1800063C3
0x18000637d  cmp     ebp, dword ptr [rsp+88h+var_48+4]
0x180006381  jnz     short loc_1800063C3
0x180006383  mov     r8, rsi; Size
0x180006386  mov     rdx, r12; Buf2
0x180006389  mov     rcx, rbx; Buf1
0x18000638c  call    memcmp_0
0x180006391  test    eax, eax
0x180006393  jnz     short loc_1800063C3
0x180006395  test    rbx, rbx
0x180006398  jz      short loc_1800063B2
0x18000639a  mov     rcx, gs:60h
0x1800063a3  mov     r8, rbx; lpMem
0x1800063a6  xor     edx, edx; dwFlags
0x1800063a8  mov     rcx, [rcx+30h]; hHeap
0x1800063ac  call    cs:__imp_HeapFree
0x1800063b2  mov     eax, edi
0x1800063b4  add     rsp, 50h
0x1800063b8  pop     r15
0x1800063ba  pop     r14
0x1800063bc  pop     r12
0x1800063be  pop     rdi
0x1800063bf  pop     rsi
0x1800063c0  pop     rbp
0x1800063c1  pop     rbx
0x1800063c2  retn
0x1800063c3  mov     dword ptr [rsp+88h+pvData], esi; cbData
0x1800063c7  mov     r9d, ebp; dwType
0x1800063ca  xor     r8d, r8d; Reserved
0x1800063cd  mov     [rsp+88h+pdwType], r12; lpData
0x1800063d2  mov     rdx, r14; lpValueName
0x1800063d5  mov     rcx, r15; hKey
0x1800063d8  call    cs:__imp_RegSetValueExW
0x1800063de  mov     edi, eax
0x1800063e0  jmp     short loc_180006395
0x1800063e2  lea     rcx, [rsp+88h+var_40]
0x1800063e7  call    DhcpPunycodeFree
0x1800063ec  mov     ecx, dword ptr [rsp+88h+var_48]
0x1800063f0  call    DhcpAlloc
0x1800063f5  mov     rbx, rax
0x1800063f8  test    rax, rax
0x1800063fb  jz      short loc_1800063C3
0x1800063fd  lea     rax, [rsp+88h+var_48]
0x180006402  mov     r9d, 0FFFFh; dwFlags
0x180006408  mov     [rsp+88h+pcbData], rax; pcbData
0x18000640d  mov     r8, r14; lpValue
0x180006410  lea     rax, [rsp+88h+var_48+4]
0x180006415  mov     [rsp+88h+pvData], rbx; pvData
0x18000641a  xor     edx, edx; lpSubKey
0x18000641c  mov     [rsp+88h+pdwType], rax; pdwType
0x180006421  mov     rcx, r15; hkey
0x180006424  call    cs:__imp_RegGetValueW
0x18000642a  mov     edi, eax
0x18000642c  jmp     loc_180006373
```
