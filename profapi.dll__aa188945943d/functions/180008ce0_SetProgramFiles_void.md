# _SetProgramFiles(void * *)

- ea: `0x180008ce0`
- end: `0x1800090e9`
- name: `?_SetProgramFiles@@YAXPEAPEAX@Z`
- size: `1033`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007e40`

## callees

- `0x180008ce0`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ddc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008faa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ddc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008faa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008dce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008df3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008dce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008df3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e83`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008d95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008d95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f8b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008fc5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f8b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008fc5`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180009064`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180009064`
- `ntdll!RtlSetEnvironmentVar` at `0x180008ecc`
- `ntdll!RtlSetEnvironmentVar` at `0x1800090af`
- `ntdll!RtlSetEnvironmentVar` at `0x180008ecc`
- `ntdll!RtlSetEnvironmentVar` at `0x1800090af`
- `ntdll!RtlNtStatusToDosError` at `0x180008ed4`
- `ntdll!RtlNtStatusToDosError` at `0x1800090b7`
- `ntdll!RtlNtStatusToDosError` at `0x180008ed4`
- `ntdll!RtlNtStatusToDosError` at `0x1800090b7`

## pseudocode

```c
void __fastcall _SetProgramFiles(void **a1)
{
  __int64 v1; // r13
  const WCHAR *v2; // r14
  LSTATUS v3; // eax
  bool v4; // sf
  HKEY v5; // rbp
  WCHAR *v6; // r12
  BYTE *v7; // rdi
  LSTATUS v8; // eax
  signed int v9; // esi
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  const WCHAR *v13; // rbx
  WCHAR *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r8
  NTSTATUS v17; // eax
  HANDLE v18; // rax
  LSTATUS v19; // eax
  __int64 v20; // rbx
  DWORD v21; // ebp
  HANDLE v22; // rax
  WCHAR *v23; // rax
  WCHAR *v24; // r14
  DWORD v25; // eax
  DWORD v26; // ebx
  HANDLE v27; // rax
  __int64 v28; // r8
  NTSTATUS v29; // eax
  HANDLE v30; // rax
  DWORD cbData; // [rsp+30h] [rbp-268h] BYREF
  DWORD Type; // [rsp+34h] [rbp-264h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-260h] BYREF
  void **v34; // [rsp+40h] [rbp-258h]
  WCHAR szShortPath[264]; // [rsp+50h] [rbp-248h] BYREF

  v1 = 0;
  v34 = a1;
  do
  {
    hKey = 0;
    v2 = off_180022040[2 * v1];
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hKey);
    v4 = v3 < 0;
    if ( v3 > 0 )
      v4 = 1;
    if ( v4 )
      goto LABEL_24;
    v5 = hKey;
    Type = 0;
    cbData = 0;
    v6 = 0;
    v7 = 0;
    v8 = RegQueryValueExW(hKey, v2, 0, &Type, 0, &cbData);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 >= 0 )
    {
      if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
        goto LABEL_40;
      v10 = cbData;
      ProcessHeap = GetProcessHeap();
      v7 = (BYTE *)HeapAlloc(ProcessHeap, 0, v10);
      if ( v7 )
      {
        v19 = RegQueryValueExW(v5, v2, 0, &Type, v7, &cbData);
        v9 = v19;
        if ( v19 > 0 )
          v9 = (unsigned __int16)v19 | 0x80070000;
        if ( v9 < 0 )
          goto LABEL_13;
        v20 = (cbData >> 1) - 1;
        if ( Type != 2 )
          goto LABEL_35;
        v21 = ExpandEnvironmentStringsW((LPCWSTR)v7, 0, 0);
        if ( !v21 )
          goto LABEL_35;
        v22 = GetProcessHeap();
        v23 = (WCHAR *)HeapAlloc(v22, 0, 2LL * v21);
        v24 = v23;
        if ( v23 )
        {
          v25 = ExpandEnvironmentStringsW((LPCWSTR)v7, v23, v21);
          v26 = v25;
          if ( !v25 || v25 > v21 )
          {
            v9 = -2147024774;
            v30 = GetProcessHeap();
            HeapFree(v30, 0, v24);
            goto LABEL_13;
          }
          v9 = 0;
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v7);
          v20 = v26 - 1;
          v7 = (BYTE *)v24;
LABEL_35:
          if ( !*(_WORD *)&v7[2 * v20] )
          {
            v6 = 0;
            if ( v7 && (_DWORD)v20 != -1 )
            {
              v6 = (WCHAR *)v7;
              *(_WORD *)&v7[2 * (unsigned int)(v20 + 1) - 2] = 0;
            }
            v7 = 0;
            goto LABEL_13;
          }
LABEL_40:
          v9 = -2147024883;
          goto LABEL_13;
        }
      }
      v9 = -2147024882;
    }
LABEL_13:
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v7);
    RegCloseKey(hKey);
    if ( v9 >= 0 )
    {
      v13 = off_180022040[2 * v1 + 1];
      if ( v6 && *v6 )
      {
        v14 = v6;
        if ( (CompareStringOrdinal(v13, -1, L"TEMP", -1, 1) == 2 || CompareStringOrdinal(v13, -1, L"TMP", -1, 1) == 2)
          && GetShortPathNameW(v6, szShortPath, 0x104u) - 1 <= 0x102 )
        {
          v14 = szShortPath;
        }
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        v16 = -1;
        do
          ++v16;
        while ( v13[v16] );
        v17 = RtlSetEnvironmentVar(v34, v13, v16, v14, v15);
        RtlNtStatusToDosError(v17);
LABEL_23:
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v6);
        goto LABEL_24;
      }
      v28 = -1;
      do
        ++v28;
      while ( v13[v28] );
      v29 = RtlSetEnvironmentVar(v34, off_180022040[2 * v1 + 1], v28, 0, 0);
      RtlNtStatusToDosError(v29);
    }
    if ( v6 )
      goto LABEL_23;
LABEL_24:
    ++v1;
  }
  while ( v1 != 6 );
}

```

## disassembly

```asm
0x180008ce0  mov     r11, rsp
0x180008ce3  push    rbx
0x180008ce4  push    rdi
0x180008ce5  push    r13
0x180008ce7  push    r14
0x180008ce9  push    r15
0x180008ceb  sub     rsp, 270h
0x180008cf2  mov     rax, cs:__security_cookie
0x180008cf9  xor     rax, rsp
0x180008cfc  mov     [rsp+298h+var_38], rax
0x180008d04  mov     [r11+10h], rbp
0x180008d08  lea     rax, off_180022040; "ProgramFilesDir"
0x180008d0f  xor     ebx, ebx
0x180008d11  mov     [r11+18h], rsi
0x180008d15  mov     r13d, ebx
0x180008d18  mov     [r11+20h], r12
0x180008d1c  mov     [rsp+298h+var_258], rcx
0x180008d21  mov     r15, r13
0x180008d24  mov     [rsp+298h+hKey], rbx
0x180008d29  add     r15, r15
0x180008d2c  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008d33  mov     r9d, 20019h; samDesired
0x180008d39  xor     r8d, r8d; ulOptions
0x180008d3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008d43  mov     r14, [rax+r15*8]
0x180008d47  lea     rax, [rsp+298h+hKey]
0x180008d4c  mov     [rsp+298h+phkResult], rax; phkResult
0x180008d51  call    cs:__imp_RegOpenKeyExW
0x180008d57  test    eax, eax
0x180008d59  jg      loc_180009021
0x180008d5f  js      loc_180008EEE
0x180008d65  mov     rbp, [rsp+298h+hKey]
0x180008d6a  lea     rax, [rsp+298h+cbData]
0x180008d6f  mov     [rsp+298h+lpcbData], rax; lpcbData
0x180008d74  lea     r9, [rsp+298h+Type]; lpType
0x180008d79  mov     rcx, rbp; hKey
0x180008d7c  mov     [rsp+298h+phkResult], rbx; lpData
0x180008d81  xor     r8d, r8d; lpReserved
0x180008d84  mov     [rsp+298h+Type], ebx
0x180008d88  mov     rdx, r14; lpValueName
0x180008d8b  mov     [rsp+298h+cbData], ebx
0x180008d8f  mov     r12, rbx
0x180008d92  mov     rdi, rbx
0x180008d95  call    cs:__imp_RegQueryValueExW
0x180008d9b  mov     esi, eax
0x180008d9d  test    eax, eax
0x180008d9f  jg      loc_180009030
0x180008da5  test    esi, esi
0x180008da7  js      short loc_180008DF3
0x180008da9  mov     eax, [rsp+298h+Type]
0x180008dad  dec     eax
0x180008daf  cmp     eax, 1
0x180008db2  ja      loc_18000904C
0x180008db8  mov     eax, [rsp+298h+cbData]
0x180008dbc  test    eax, eax
0x180008dbe  jz      loc_18000904C
0x180008dc4  test    al, 1
0x180008dc6  jnz     loc_18000904C
0x180008dcc  mov     ebx, eax
0x180008dce  call    cs:__imp_GetProcessHeap
0x180008dd4  mov     r8d, ebx; dwBytes
0x180008dd7  xor     edx, edx; dwFlags
0x180008dd9  mov     rcx, rax; hHeap
0x180008ddc  call    cs:__imp_HeapAlloc
0x180008de2  mov     rdi, rax
0x180008de5  test    rax, rax
0x180008de8  jnz     loc_180008F3F
0x180008dee  mov     esi, 8007000Eh
0x180008df3  call    cs:__imp_GetProcessHeap
0x180008df9  mov     r8, rdi; lpMem
0x180008dfc  xor     edx, edx; dwFlags
0x180008dfe  mov     rcx, rax; hHeap
0x180008e01  call    cs:__imp_HeapFree
0x180008e07  mov     rcx, [rsp+298h+hKey]; hKey
0x180008e0c  call    cs:__imp_RegCloseKey
0x180008e12  test    esi, esi
0x180008e14  js      loc_1800090BD
0x180008e1a  lea     rbx, off_180022040; "ProgramFilesDir"
0x180008e21  mov     rbx, [rbx+r15*8+8]
0x180008e26  test    r12, r12
0x180008e29  jz      loc_180009081
0x180008e2f  cmp     word ptr [r12], 0
0x180008e35  jz      loc_180009081
0x180008e3b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008e41  mov     dword ptr [rsp+298h+phkResult], 1; bIgnoreCase
0x180008e49  mov     edx, r9d; cchCount1
0x180008e4c  lea     r8, String2; "TEMP"
0x180008e53  mov     rcx, rbx; lpString1
0x180008e56  mov     rdi, r12
0x180008e59  call    cs:__imp_CompareStringOrdinal
0x180008e5f  cmp     eax, 2
0x180008e62  jz      loc_180009056
0x180008e68  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008e6e  mov     dword ptr [rsp+298h+phkResult], 1; bIgnoreCase
0x180008e76  mov     edx, r9d; cchCount1
0x180008e79  lea     r8, aTmp; "TMP"
0x180008e80  mov     rcx, rbx; lpString1
0x180008e83  call    cs:__imp_CompareStringOrdinal
0x180008e89  cmp     eax, 2
0x180008e8c  jz      loc_180009056
0x180008e92  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008e99  nop     dword ptr [rax+00000000h]
0x180008ea0  inc     rax
0x180008ea3  cmp     word ptr [rdi+rax*2], 0
0x180008ea8  jnz     short loc_180008EA0
0x180008eaa  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008eb1  inc     r8
0x180008eb4  cmp     word ptr [rbx+r8*2], 0
0x180008eba  jnz     short loc_180008EB1
0x180008ebc  mov     rcx, [rsp+298h+var_258]
0x180008ec1  mov     r9, rdi
0x180008ec4  mov     rdx, rbx
0x180008ec7  mov     [rsp+298h+phkResult], rax
0x180008ecc  call    cs:__imp_RtlSetEnvironmentVar
0x180008ed2  mov     ecx, eax; Status
0x180008ed4  call    cs:__imp_RtlNtStatusToDosError
0x180008eda  call    cs:__imp_GetProcessHeap
0x180008ee0  mov     r8, r12; lpMem
0x180008ee3  xor     edx, edx; dwFlags
0x180008ee5  mov     rcx, rax; hHeap
0x180008ee8  call    cs:__imp_HeapFree
0x180008eee  inc     r13
0x180008ef1  lea     rax, off_180022040; "ProgramFilesDir"
0x180008ef8  mov     ebx, 0
0x180008efd  cmp     r13, 6
0x180008f01  jnz     loc_180008D21
0x180008f07  mov     r12, [rsp+298h+arg_18]
0x180008f0f  mov     rsi, [rsp+298h+arg_10]
0x180008f17  mov     rbp, [rsp+298h+arg_8]
0x180008f1f  mov     rcx, [rsp+298h+var_38]
0x180008f27  xor     rcx, rsp; StackCookie
0x180008f2a  call    __security_check_cookie
0x180008f2f  add     rsp, 270h
0x180008f36  pop     r15
0x180008f38  pop     r14
0x180008f3a  pop     r13
0x180008f3c  pop     rdi
0x180008f3d  pop     rbx
0x180008f3e  retn
0x180008f3f  lea     rax, [rsp+298h+cbData]
0x180008f44  xor     r8d, r8d; lpReserved
0x180008f47  mov     [rsp+298h+lpcbData], rax; lpcbData
0x180008f4c  lea     r9, [rsp+298h+Type]; lpType
0x180008f51  mov     rdx, r14; lpValueName
0x180008f54  mov     [rsp+298h+phkResult], rdi; lpData
0x180008f59  mov     rcx, rbp; hKey
0x180008f5c  call    cs:__imp_RegQueryValueExW
0x180008f62  mov     esi, eax
0x180008f64  test    eax, eax
0x180008f66  jg      loc_18000903E
0x180008f6c  test    esi, esi
0x180008f6e  js      loc_180008DF3
0x180008f74  mov     ebx, [rsp+298h+cbData]
0x180008f78  shr     ebx, 1
0x180008f7a  dec     ebx
0x180008f7c  cmp     [rsp+298h+Type], 2
0x180008f81  jnz     short loc_180008FF8
0x180008f83  xor     r8d, r8d; nSize
0x180008f86  xor     edx, edx; lpDst
0x180008f88  mov     rcx, rdi; lpSrc
0x180008f8b  call    cs:__imp_ExpandEnvironmentStringsW
0x180008f91  mov     ebp, eax
0x180008f93  test    eax, eax
0x180008f95  jz      short loc_180008FF8
0x180008f97  mov     ebx, ebp
0x180008f99  add     rbx, rbx
0x180008f9c  call    cs:__imp_GetProcessHeap
0x180008fa2  mov     r8, rbx; dwBytes
0x180008fa5  xor     edx, edx; dwFlags
0x180008fa7  mov     rcx, rax; hHeap
0x180008faa  call    cs:__imp_HeapAlloc
0x180008fb0  mov     r14, rax
0x180008fb3  test    rax, rax
0x180008fb6  jz      loc_180008DEE
0x180008fbc  mov     r8d, ebp; nSize
0x180008fbf  mov     rdx, rax; lpDst
0x180008fc2  mov     rcx, rdi; lpSrc
0x180008fc5  call    cs:__imp_ExpandEnvironmentStringsW
0x180008fcb  mov     ebx, eax
0x180008fcd  test    eax, eax
0x180008fcf  jz      loc_1800090CB
0x180008fd5  cmp     eax, ebp
0x180008fd7  ja      loc_1800090CB
0x180008fdd  xor     esi, esi
0x180008fdf  call    cs:__imp_GetProcessHeap
0x180008fe5  mov     r8, rdi; lpMem
0x180008fe8  xor     edx, edx; dwFlags
0x180008fea  mov     rcx, rax; hHeap
0x180008fed  call    cs:__imp_HeapFree
0x180008ff3  dec     ebx
0x180008ff5  mov     rdi, r14
0x180008ff8  cmp     word ptr [rdi+rbx*2], 0
0x180008ffd  jnz     short loc_18000904C
0x180008fff  xor     r12d, r12d
0x180009002  test    rdi, rdi
0x180009005  jz      short loc_18000901A
0x180009007  lea     eax, [rbx+1]
0x18000900a  mov     ecx, eax
0x18000900c  test    eax, eax
0x18000900e  jz      short loc_18000901A
0x180009010  xor     eax, eax
0x180009012  mov     r12, rdi
0x180009015  mov     [rdi+rcx*2-2], ax
0x18000901a  xor     edi, edi
0x18000901c  jmp     loc_180008DF3
0x180009021  movzx   eax, ax
0x180009024  or      eax, 80070000h
0x180009029  test    eax, eax
0x18000902b  jmp     loc_180008D5F
0x180009030  movzx   esi, ax
0x180009033  or      esi, 80070000h
0x180009039  jmp     loc_180008DA5
0x18000903e  movzx   esi, ax
0x180009041  or      esi, 80070000h
0x180009047  jmp     loc_180008F6C
0x18000904c  mov     esi, 8007000Dh
0x180009051  jmp     loc_180008DF3
0x180009056  mov     r8d, 104h; cchBuffer
0x18000905c  lea     rdx, [rsp+298h+szShortPath]; lpszShortPath
0x180009061  mov     rcx, r12; lpszLongPath
0x180009064  call    cs:__imp_GetShortPathNameW
0x18000906a  dec     eax
0x18000906c  cmp     eax, 102h
0x180009071  ja      loc_180008E92
0x180009077  lea     rdi, [rsp+298h+szShortPath]
0x18000907c  jmp     loc_180008E92
0x180009081  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009088  nop     dword ptr [rax+rax+00000000h]
0x180009090  inc     r8
0x180009093  cmp     word ptr [rbx+r8*2], 0
0x180009099  jnz     short loc_180009090
0x18000909b  mov     rcx, [rsp+298h+var_258]
0x1800090a0  xor     r9d, r9d
0x1800090a3  mov     rdx, rbx
0x1800090a6  mov     [rsp+298h+phkResult], 0
0x1800090af  call    cs:__imp_RtlSetEnvironmentVar
0x1800090b5  mov     ecx, eax; Status
0x1800090b7  call    cs:__imp_RtlNtStatusToDosError
0x1800090bd  test    r12, r12
0x1800090c0  jnz     loc_180008EDA
0x1800090c6  jmp     loc_180008EEE
0x1800090cb  mov     esi, 8007007Ah
0x1800090d0  call    cs:__imp_GetProcessHeap
0x1800090d6  mov     r8, r14; lpMem
0x1800090d9  xor     edx, edx; dwFlags
0x1800090db  mov     rcx, rax; hHeap
0x1800090de  call    cs:__imp_HeapFree
0x1800090e4  jmp     loc_180008DF3
```
