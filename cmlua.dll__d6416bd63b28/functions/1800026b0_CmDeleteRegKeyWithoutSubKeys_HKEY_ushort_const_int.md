# CmDeleteRegKeyWithoutSubKeys(HKEY__ *,ushort const *,int)

- ea: `0x1800026b0`
- end: `0x180002888`
- name: `?CmDeleteRegKeyWithoutSubKeys@@YAJPEAUHKEY__@@PEBGH@Z`
- size: `472`
- prototype: `__int64 __fastcall(HKEY hKey, WCHAR *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003200`

## callees

- `0x1800026b0`
- `0x180003f78`
- `0x180004e1c`

## import_xrefs

- `cmutil!CmFree` at `0x18000286c`
- `cmutil!CmFree` at `0x18000286c`
- `cmutil!CmMalloc` at `0x180002750`
- `cmutil!CmMalloc` at `0x180002750`
- `ADVAPI32!RegCloseKey` at `0x18000285e`
- `ADVAPI32!RegCloseKey` at `0x18000285e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002816`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002816`
- `ADVAPI32!RegDeleteKeyW` at `0x18000283e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000283e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800027ab`
- `ADVAPI32!RegOpenKeyExW` at `0x1800027ab`
- `KERNEL32!lstrlenW` at `0x1800026fe`
- `KERNEL32!lstrlenW` at `0x1800026fe`

## string_xrefs

- `0x18000272e`: `CmDeleteRegKeyWithoutSubKeys() - Arithmetic operation failed: %ld\n`

## pseudocode

```c
__int64 __fastcall CmDeleteRegKeyWithoutSubKeys(HKEY hKey, WCHAR *a2, int a3)
{
  unsigned int v6; // ebx
  int v7; // r15d
  int v8; // eax
  __int64 v9; // r9
  unsigned int v10; // edx
  WCHAR *v11; // rdi
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned __int64 v14; // rax
  wchar_t *v15; // rax
  unsigned __int16 **v16; // r9
  unsigned __int16 v17; // ax
  unsigned __int64 *phkResult; // [rsp+20h] [rbp-78h]
  HKEY hKeya; // [rsp+60h] [rbp-38h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp+8h] BYREF
  DWORD cValues; // [rsp+B8h] [rbp+20h] BYREF

  cSubKeys = 0;
  cValues = 0;
  hKeya = 0;
  v6 = 87;
  if ( !hKey || !a2 )
    return v6;
  v7 = 0;
  v8 = lstrlenW(a2);
  v10 = v8;
  if ( !v8 || a2[v8 - 1] != 92 )
  {
    v11 = a2;
    goto LABEL_13;
  }
  v11 = 0;
  v12 = (unsigned int)(v8 + 1);
  if ( (unsigned int)v12 < v10 || (v13 = v12, v14 = 2 * v12, v14 > 0xFFFFFFFF) )
  {
    v6 = 534;
    MyDbgPrintfW(0xFFFFFFFFLL, L"CmDeleteRegKeyWithoutSubKeys() - Arithmetic operation failed: %ld\n", 2147942934LL, v9);
  }
  else
  {
    v15 = (wchar_t *)CmMalloc((unsigned int)v14);
    v11 = v15;
    if ( v15 )
    {
      v7 = 1;
      v17 = StringCchCopyExW(v15, v13, a2, v16, phkResult, 0x900u);
      v6 = v17;
      if ( v17 )
        goto LABEL_21;
LABEL_13:
      if ( RegOpenKeyExW(hKey, v11, 0, 0xF003Fu, &hKeya)
        || RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) )
      {
        v6 = 2;
      }
      else if ( cSubKeys || !a3 && cValues )
      {
        v6 = 80;
      }
      else
      {
        v6 = RegDeleteKeyW(hKey, v11);
      }
      goto LABEL_21;
    }
    v6 = 8;
  }
LABEL_21:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v7 )
    CmFree(v11);
  return v6;
}

```

## disassembly

```asm
0x1800026b0  mov     rax, rsp
0x1800026b3  mov     [rax+10h], rbx
0x1800026b7  push    rbp
0x1800026b8  push    rsi
0x1800026b9  push    rdi
0x1800026ba  push    r14
0x1800026bc  push    r15
0x1800026be  sub     rsp, 70h
0x1800026c2  mov     dword ptr [rax+8], 0
0x1800026c9  mov     r14d, r8d
0x1800026cc  mov     dword ptr [rax+20h], 0
0x1800026d3  mov     rsi, rdx
0x1800026d6  mov     qword ptr [rax-38h], 0
0x1800026de  mov     rbp, rcx
0x1800026e1  mov     ebx, 57h ; 'W'
0x1800026e6  test    rcx, rcx
0x1800026e9  jz      loc_180002872
0x1800026ef  test    rdx, rdx
0x1800026f2  jz      loc_180002872
0x1800026f8  mov     rcx, rdx; lpString
0x1800026fb  xor     r15d, r15d
0x1800026fe  call    cs:__imp_lstrlenW
0x180002704  mov     edx, eax
0x180002706  test    eax, eax
0x180002708  jz      loc_18000278F
0x18000270e  lea     ecx, [rax-1]
0x180002711  lea     eax, [rbx+5]
0x180002714  cmp     ax, [rsi+rcx*2]
0x180002718  jnz     short loc_18000278F
0x18000271a  xor     edi, edi
0x18000271c  lea     eax, [rdx+1]
0x18000271f  mov     ecx, 0FFFFFFFFh
0x180002724  cmp     eax, edx
0x180002726  jnb     short loc_180002744
0x180002728  mov     r8d, 80070216h
0x18000272e  lea     rdx, aCmdeleteregkey; "CmDeleteRegKeyWithoutSubKeys() - Arithm"...
0x180002735  mov     ebx, 216h
0x18000273a  call    MyDbgPrintfW
0x18000273f  jmp     loc_180002854
0x180002744  mov     ebx, eax
0x180002746  add     rax, rax
0x180002749  cmp     rax, rcx
0x18000274c  ja      short loc_180002728
0x18000274e  mov     ecx, eax
0x180002750  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180002756  mov     rdi, rax
0x180002759  test    rax, rax
0x18000275c  jz      short loc_180002785
0x18000275e  mov     r8, rsi; unsigned __int16 *
0x180002761  mov     dword ptr [rsp+98h+lpcbMaxSubKeyLen], 900h; unsigned int
0x180002769  mov     edx, ebx; unsigned __int64
0x18000276b  mov     rcx, rax; pszDest
0x18000276e  mov     r15d, 1
0x180002774  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180002779  movzx   ebx, ax
0x18000277c  test    ebx, ebx
0x18000277e  jz      short loc_180002792
0x180002780  jmp     loc_180002854
0x180002785  mov     ebx, 8
0x18000278a  jmp     loc_180002854
0x18000278f  mov     rdi, rsi
0x180002792  lea     rax, [rsp+98h+hKey]
0x180002797  mov     r9d, 0F003Fh; samDesired
0x18000279d  xor     r8d, r8d; ulOptions
0x1800027a0  mov     [rsp+98h+phkResult], rax; phkResult
0x1800027a5  mov     rdx, rdi; lpSubKey
0x1800027a8  mov     rcx, rbp; hKey
0x1800027ab  call    cs:__imp_RegOpenKeyExW
0x1800027b1  test    eax, eax
0x1800027b3  jnz     loc_18000284F
0x1800027b9  mov     rcx, [rsp+98h+hKey]; hKey
0x1800027be  lea     rax, [rsp+98h+cValues]
0x1800027c6  mov     [rsp+98h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800027cf  xor     r9d, r9d; lpReserved
0x1800027d2  mov     [rsp+98h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800027db  xor     r8d, r8d; lpcchClass
0x1800027de  mov     [rsp+98h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800027e7  xor     edx, edx; lpClass
0x1800027e9  mov     [rsp+98h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800027f2  mov     [rsp+98h+lpcValues], rax; lpcValues
0x1800027f7  lea     rax, [rsp+98h+cSubKeys]
0x1800027ff  mov     [rsp+98h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180002808  mov     [rsp+98h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180002811  mov     [rsp+98h+phkResult], rax; lpcSubKeys
0x180002816  call    cs:__imp_RegQueryInfoKeyW
0x18000281c  test    eax, eax
0x18000281e  jnz     short loc_18000284F
0x180002820  cmp     [rsp+98h+cSubKeys], eax
0x180002827  jnz     short loc_180002848
0x180002829  test    r14d, r14d
0x18000282c  jnz     short loc_180002838
0x18000282e  cmp     [rsp+98h+cValues], r14d
0x180002836  jnz     short loc_180002848
0x180002838  mov     rdx, rdi; lpSubKey
0x18000283b  mov     rcx, rbp; hKey
0x18000283e  call    cs:__imp_RegDeleteKeyW
0x180002844  mov     ebx, eax
0x180002846  jmp     short loc_180002854
0x180002848  mov     ebx, 50h ; 'P'
0x18000284d  jmp     short loc_180002854
0x18000284f  mov     ebx, 2
0x180002854  mov     rcx, [rsp+98h+hKey]; hKey
0x180002859  test    rcx, rcx
0x18000285c  jz      short loc_180002864
0x18000285e  call    cs:__imp_RegCloseKey
0x180002864  test    r15d, r15d
0x180002867  jz      short loc_180002872
0x180002869  mov     rcx, rdi
0x18000286c  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180002872  mov     eax, ebx
0x180002874  mov     rbx, [rsp+98h+arg_8]
0x18000287c  add     rsp, 70h
0x180002880  pop     r15
0x180002882  pop     r14
0x180002884  pop     rdi
0x180002885  pop     rsi
0x180002886  pop     rbp
0x180002887  retn
```
