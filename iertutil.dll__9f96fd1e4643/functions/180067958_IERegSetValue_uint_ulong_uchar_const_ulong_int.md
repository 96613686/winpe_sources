# IERegSetValue(uint,ulong,uchar const *,ulong,int)

- ea: `0x180067958`
- end: `0x180067a82`
- name: `?IERegSetValue@@YAJIKPEBEKH@Z`
- size: `298`
- prototype: `int(unsigned int, unsigned int, const unsigned __int8 *, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800687d0`
- `0x180068800`
- `0x1800688f0`

## callees

- `0x18003f5c0`
- `0x180067958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067a50`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067a2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180067a2a`

## pseudocode

```c
__int64 __fastcall IERegSetValue(unsigned int a1, DWORD a2, const unsigned __int8 *a3, DWORD a4, int a5)
{
  __int64 v6; // rbx
  __int64 v10; // rbx
  int v11; // edx
  HKEY v12; // rcx
  const WCHAR *v13; // rdx
  LSTATUS v14; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  v6 = a1;
  IERegInit();
  if ( (unsigned int)v6 >= 0x55 )
    return 2147747588LL;
  v10 = 5 * v6;
  if ( dword_1800E4B90[2 * v10] != a2 )
    return 2147747585LL;
  v11 = *(_DWORD *)((char *)qword_18025DFD8 + (a5 != 0 ? 4 : 0));
  if ( (v11 & dword_1800E4BA4[2 * v10]) != v11 )
    return 2147747584LL;
  v12 = *(HKEY *)((char *)&qword_18029A1A0 + (a5 != 0 ? 8 : 0));
  if ( !v12 )
    return 2147747584LL;
  v13 = (const WCHAR *)qword_1800E4B80[v10];
  hKey = 0;
  if ( RegCreateKeyExW(v12, v13, 0, 0, 0, 2u, 0, &hKey, 0) )
    return 2147747587LL;
  v14 = RegSetValueExW(hKey, (LPCWSTR)qword_1800E4B88[v10], 0, a2, a3, a4);
  RegCloseKey(hKey);
  if ( v14 )
    return 2147747587LL;
  else
    return 0;
}

```

## disassembly

```asm
0x180067958  push    rbx
0x18006795a  push    rbp
0x18006795b  push    rsi
0x18006795c  push    rdi
0x18006795d  push    r14
0x18006795f  sub     rsp, 60h
0x180067963  mov     esi, r9d
0x180067966  mov     ebx, ecx
0x180067968  mov     rbp, r8
0x18006796b  mov     edi, edx
0x18006796d  call    IERegInit
0x180067972  cmp     ebx, 55h ; 'U'
0x180067975  jb      short loc_180067981
0x180067977  mov     eax, 80040704h
0x18006797c  jmp     loc_180067A77
0x180067981  lea     rbx, [rbx+rbx*4]
0x180067985  lea     r14, __ImageBase
0x18006798c  cmp     ds:rva dword_1800E4B90[r14+rbx*8], edi
0x180067994  jz      short loc_1800679A0
0x180067996  mov     eax, 80040701h
0x18006799b  jmp     loc_180067A77
0x1800679a0  mov     r8d, [rsp+88h+arg_20]
0x1800679a8  mov     eax, r8d
0x1800679ab  neg     eax
0x1800679ad  mov     eax, ds:rva dword_1800E4BA4[r14+rbx*8]
0x1800679b5  sbb     rcx, rcx
0x1800679b8  and     ecx, 4
0x1800679bb  mov     edx, [rcx+r14+25DFD8h]
0x1800679c3  and     eax, edx
0x1800679c5  cmp     eax, edx
0x1800679c7  jnz     loc_180067A72
0x1800679cd  neg     r8d
0x1800679d0  sbb     rax, rax
0x1800679d3  and     eax, 8
0x1800679d6  mov     rcx, [rax+r14+29A1A0h]; hKey
0x1800679de  test    rcx, rcx
0x1800679e1  jz      loc_180067A72
0x1800679e7  mov     rdx, ds:rva qword_1800E4B80[r14+rbx*8]; lpSubKey
0x1800679ef  lea     rax, [rsp+88h+hKey]
0x1800679f4  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800679fd  xor     r9d, r9d; lpClass
0x180067a00  mov     [rsp+88h+phkResult], rax; phkResult
0x180067a05  xor     r8d, r8d; Reserved
0x180067a08  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180067a11  mov     [rsp+88h+samDesired], 2; samDesired
0x180067a19  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180067a21  mov     [rsp+88h+hKey], 0
0x180067a2a  call    cs:__imp_RegCreateKeyExW
0x180067a30  test    eax, eax
0x180067a32  jnz     short loc_180067A6B
0x180067a34  mov     rdx, ds:rva qword_1800E4B88[r14+rbx*8]; lpValueName
0x180067a3c  mov     r9d, edi; dwType
0x180067a3f  mov     rcx, [rsp+88h+hKey]; hKey
0x180067a44  xor     r8d, r8d; Reserved
0x180067a47  mov     [rsp+88h+samDesired], esi; cbData
0x180067a4b  mov     qword ptr [rsp+88h+dwOptions], rbp; lpData
0x180067a50  call    cs:__imp_RegSetValueExW
0x180067a56  mov     rcx, [rsp+88h+hKey]; hKey
0x180067a5b  mov     ebx, eax
0x180067a5d  call    cs:__imp_RegCloseKey
0x180067a63  test    ebx, ebx
0x180067a65  jnz     short loc_180067A6B
0x180067a67  xor     eax, eax
0x180067a69  jmp     short loc_180067A77
0x180067a6b  mov     eax, 80040703h
0x180067a70  jmp     short loc_180067A77
0x180067a72  mov     eax, 80040700h
0x180067a77  add     rsp, 60h
0x180067a7b  pop     r14
0x180067a7d  pop     rdi
0x180067a7e  pop     rsi
0x180067a7f  pop     rbp
0x180067a80  pop     rbx
0x180067a81  retn
```
