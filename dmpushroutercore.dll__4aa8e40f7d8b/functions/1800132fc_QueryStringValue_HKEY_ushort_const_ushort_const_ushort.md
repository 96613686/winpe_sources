# QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x1800132fc`
- end: `0x180013451`
- name: `?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `341`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012860`
- `0x1800129e8`
- `0x180012bec`
- `0x180014468`
- `0x180016110`
- `0x180018060`

## callees

- `0x1800132fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013438`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013438`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800133e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800133e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013346`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013346`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001340a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001340a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800133b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800133b3`

## pseudocode

```c
__int64 __fastcall QueryStringValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, BYTE **a4)
{
  BYTE *v4; // rdi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  bool v10; // cc
  DWORD v11; // ecx
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  v4 = 0;
  cbData = 0;
  Type = 0;
  *a4 = 0;
  hKey = a1;
  if ( a2 )
  {
    v8 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    v9 = v8;
    v10 = v8 <= 0;
    if ( v8 )
      goto LABEL_3;
    a1 = hKey;
  }
  v8 = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData);
  v9 = v8;
  v10 = v8 <= 0;
  if ( !v8 )
  {
    if ( Type - 1 > 1 )
    {
      v9 = -2147024809;
      goto LABEL_15;
    }
    v11 = cbData + 2;
    if ( cbData + 2 < cbData )
    {
      cbData = -1;
      v9 = -2147024362;
      goto LABEL_15;
    }
    cbData += 2;
    v4 = (BYTE *)LocalAlloc(0x40u, v11);
    if ( !v4 )
    {
      v9 = -2147024882;
      goto LABEL_15;
    }
    v8 = RegQueryValueExW(hKey, a3, 0, &Type, v4, &cbData);
    v9 = v8;
    v10 = v8 <= 0;
    if ( !v8 )
    {
      *a4 = v4;
      v4 = 0;
      goto LABEL_15;
    }
  }
LABEL_3:
  if ( !v10 )
    v9 = (unsigned __int16)v8 | 0x80070000;
LABEL_15:
  LocalFree(v4);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147024882 )
    v9 = 1;
  if ( hKey && a2 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1800132fc  mov     [rsp-28h+arg_10], rbx
0x180013301  push    rbp
0x180013302  push    rsi
0x180013303  push    rdi
0x180013304  push    r14
0x180013306  push    r15
0x180013308  mov     rbp, rsp
0x18001330b  sub     rsp, 30h
0x18001330f  xor     edi, edi
0x180013311  mov     [rbp+cbData], 0
0x180013318  mov     [rbp+Type], 0
0x18001331f  mov     rsi, r9
0x180013322  mov     [r9], rdi
0x180013325  mov     r14, r8
0x180013328  mov     [rbp+hKey], rcx
0x18001332c  mov     r15, rdx
0x18001332f  test    rdx, rdx
0x180013332  jz      short loc_18001336A
0x180013334  lea     rax, [rbp+hKey]
0x180013338  mov     r9d, 20019h; samDesired
0x18001333e  xor     r8d, r8d; ulOptions
0x180013341  mov     [rsp+30h+phkResult], rax; phkResult
0x180013346  call    cs:__imp_RegOpenKeyExW
0x18001334c  mov     ebx, eax
0x18001334e  test    eax, eax
0x180013350  jz      short loc_180013366
0x180013352  jle     loc_180013407
0x180013358  movzx   ebx, ax
0x18001335b  or      ebx, 80070000h
0x180013361  jmp     loc_180013407
0x180013366  mov     rcx, [rbp+hKey]; hKey
0x18001336a  lea     rax, [rbp+cbData]
0x18001336e  xor     r8d, r8d; lpReserved
0x180013371  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180013376  lea     r9, [rbp+Type]; lpType
0x18001337a  mov     rdx, r14; lpValueName
0x18001337d  mov     [rsp+30h+phkResult], rdi; lpData
0x180013382  call    cs:__imp_RegQueryValueExW
0x180013388  mov     ebx, eax
0x18001338a  test    eax, eax
0x18001338c  jnz     short loc_180013352
0x18001338e  mov     eax, [rbp+Type]
0x180013391  dec     eax
0x180013393  cmp     eax, 1
0x180013396  jbe     short loc_18001339F
0x180013398  mov     ebx, 80070057h
0x18001339d  jmp     short loc_180013407
0x18001339f  mov     eax, [rbp+cbData]
0x1800133a2  lea     ecx, [rax+2]
0x1800133a5  cmp     ecx, eax
0x1800133a7  jb      short loc_1800133FB
0x1800133a9  mov     [rbp+cbData], ecx
0x1800133ac  mov     edx, ecx; uBytes
0x1800133ae  mov     ecx, 40h ; '@'; uFlags
0x1800133b3  call    cs:__imp_LocalAlloc
0x1800133b9  mov     rdi, rax
0x1800133bc  test    rax, rax
0x1800133bf  jnz     short loc_1800133C8
0x1800133c1  mov     ebx, 8007000Eh
0x1800133c6  jmp     short loc_180013407
0x1800133c8  mov     rcx, [rbp+hKey]; hKey
0x1800133cc  lea     rax, [rbp+cbData]
0x1800133d0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800133d5  lea     r9, [rbp+Type]; lpType
0x1800133d9  xor     r8d, r8d; lpReserved
0x1800133dc  mov     [rsp+30h+phkResult], rdi; lpData
0x1800133e1  mov     rdx, r14; lpValueName
0x1800133e4  call    cs:__imp_RegQueryValueExW
0x1800133ea  mov     ebx, eax
0x1800133ec  test    eax, eax
0x1800133ee  jnz     loc_180013352
0x1800133f4  mov     [rsi], rdi
0x1800133f7  xor     edi, edi
0x1800133f9  jmp     short loc_180013407
0x1800133fb  mov     [rbp+cbData], 0FFFFFFFFh
0x180013402  mov     ebx, 80070216h
0x180013407  mov     rcx, rdi; hMem
0x18001340a  call    cs:__imp_LocalFree
0x180013410  mov     ecx, 80000000h
0x180013415  lea     eax, [rbx+rcx]
0x180013418  test    ecx, eax
0x18001341a  jnz     short loc_18001342A
0x18001341c  cmp     ebx, 8007000Eh
0x180013422  mov     eax, 1
0x180013427  cmovnz  ebx, eax
0x18001342a  mov     rcx, [rbp+hKey]; hKey
0x18001342e  test    rcx, rcx
0x180013431  jz      short loc_18001343E
0x180013433  test    r15, r15
0x180013436  jz      short loc_18001343E
0x180013438  call    cs:__imp_RegCloseKey
0x18001343e  mov     eax, ebx
0x180013440  mov     rbx, [rsp+30h+arg_10]
0x180013445  add     rsp, 30h
0x180013449  pop     r15
0x18001344b  pop     r14
0x18001344d  pop     rdi
0x18001344e  pop     rsi
0x18001344f  pop     rbp
0x180013450  retn
```
