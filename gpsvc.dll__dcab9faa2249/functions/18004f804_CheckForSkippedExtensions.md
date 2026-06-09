# CheckForSkippedExtensions

- ea: `0x18004f804`
- end: `0x18004fa27`
- name: `CheckForSkippedExtensions`
- size: `547`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`
- `0x180095704`

## callees

- `0x180003770`
- `0x18004f804`
- `0x18007d320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f910`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004fa08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004fa1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f910`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004fa08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004fa1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fa00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fa00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f8f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f9ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f8f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f9ed`

## pseudocode

```c
__int64 __fastcall CheckForSkippedExtensions(int *a1, int a2)
{
  int v2; // edi
  __int64 i; // rbx
  int v6; // eax
  DWORD LastError; // esi
  int v9; // eax
  int v10; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-378h] BYREF
  WCHAR SubKey[400]; // [rsp+40h] [rbp-368h] BYREF

  v2 = *a1;
  for ( i = *((_QWORD *)a1 + 15); ; i = *(_QWORD *)(i + 168) )
  {
    if ( !i )
      return 1;
    if ( a2 )
    {
      if ( *(_DWORD *)(i + 76) && (v2 & 1) != 0
        || *(_DWORD *)(i + 80) && (v2 & 1) == 0
        || *(_DWORD *)(i + 84) && (v2 & 0x40000) != 0 )
      {
        goto LABEL_24;
      }
LABEL_25:
      v10 = 0;
LABEL_26:
      *(_DWORD *)(i + 120) = v10;
      continue;
    }
    if ( !*(_DWORD *)(i + 88) || (v2 & 0x10000) == 0 )
      goto LABEL_5;
    if ( (v2 & 0x100000) != 0 )
    {
      *(_DWORD *)(i + 128) = 1;
LABEL_5:
      v6 = 0;
      goto LABEL_6;
    }
    v6 = 1;
LABEL_6:
    *(_DWORD *)(i + 120) = v6;
    if ( v6 )
      continue;
    if ( *(_DWORD *)(i + 84) && (v2 & 0x40000) != 0 )
    {
      if ( *(_DWORD *)(i + 108) && (((unsigned int)*a1 >> 18) & 1) != **(_DWORD **)(i + 152) )
        goto LABEL_25;
LABEL_24:
      v10 = 1;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(i + 76) && (v2 & 1) != 0 || *(_DWORD *)(i + 80) && (v2 & 1) == 0 )
      break;
LABEL_7:
    ;
  }
  hKey[0] = 0;
  LastError = GetLastError();
  v9 = StringCchPrintfW(
         SubKey,
         0x190u,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\History\\%ws",
         *(_QWORD *)(i + 8));
  if ( v9 < 0 )
    goto LABEL_40;
  if ( !RegOpenKeyExW(*((HKEY *)a1 + 5), SubKey, 0, 0x20019u, hKey) )
  {
LABEL_39:
    RegCloseKey(hKey[0]);
    SetLastError(LastError);
    *(_DWORD *)(i + 124) = 1;
    goto LABEL_7;
  }
  if ( !*(_DWORD *)(i + 96) || (*(_BYTE *)a1 & 1) != 0 )
  {
LABEL_17:
    SetLastError(LastError);
    *(_DWORD *)(i + 120) = 1;
    goto LABEL_7;
  }
  v9 = StringCchPrintfW(
         SubKey,
         0x190u,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\History\\%ws",
         *((_QWORD *)a1 + 9),
         *(_QWORD *)(i + 8));
  if ( v9 >= 0 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hKey) )
      goto LABEL_17;
    goto LABEL_39;
  }
LABEL_40:
  SetLastError((unsigned __int16)v9);
  return 0;
}

```

## disassembly

```asm
0x18004f804  push    rbx
0x18004f806  push    rbp
0x18004f807  push    rsi
0x18004f808  push    rdi
0x18004f809  push    r12
0x18004f80b  push    r14
0x18004f80d  sub     rsp, 378h
0x18004f814  mov     rax, cs:__security_cookie
0x18004f81b  xor     rax, rsp
0x18004f81e  mov     [rsp+3A8h+var_48], rax
0x18004f826  mov     edi, [rcx]
0x18004f828  mov     ebp, edx
0x18004f82a  mov     rbx, [rcx+78h]
0x18004f82e  mov     r14, rcx
0x18004f831  mov     r12d, 1
0x18004f837  test    rbx, rbx
0x18004f83a  jz      short loc_18004F85F
0x18004f83c  test    ebp, ebp
0x18004f83e  jnz     loc_18004F91F
0x18004f844  cmp     [rbx+58h], ebp
0x18004f847  jnz     loc_18004F950
0x18004f84d  xor     eax, eax
0x18004f84f  mov     [rbx+78h], eax
0x18004f852  test    eax, eax
0x18004f854  jz      short loc_18004F882
0x18004f856  mov     rbx, [rbx+0A8h]
0x18004f85d  jmp     short loc_18004F837
0x18004f85f  mov     eax, r12d
0x18004f862  mov     rcx, [rsp+3A8h+var_48]
0x18004f86a  xor     rcx, rsp; StackCookie
0x18004f86d  call    __security_check_cookie
0x18004f872  add     rsp, 378h
0x18004f879  pop     r14
0x18004f87b  pop     r12
0x18004f87d  pop     rdi
0x18004f87e  pop     rsi
0x18004f87f  pop     rbp
0x18004f880  pop     rbx
0x18004f881  retn
0x18004f882  cmp     dword ptr [rbx+54h], 0
0x18004f886  jz      short loc_18004F892
0x18004f888  bt      edi, 12h
0x18004f88c  jb      loc_18004F974
0x18004f892  cmp     dword ptr [rbx+4Ch], 0
0x18004f896  jnz     loc_18004F990
0x18004f89c  cmp     dword ptr [rbx+50h], 0
0x18004f8a0  jz      short loc_18004F856
0x18004f8a2  test    r12b, dil
0x18004f8a5  jnz     short loc_18004F856
0x18004f8a7  mov     [rsp+3A8h+hKey], 0
0x18004f8b0  call    cs:__imp_GetLastError
0x18004f8b6  mov     r9, [rbx+8]
0x18004f8ba  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f8c1  mov     edx, 190h; unsigned __int64
0x18004f8c6  lea     rcx, [rsp+3A8h+SubKey]; unsigned __int16 *
0x18004f8cb  mov     esi, eax
0x18004f8cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f8d2  test    eax, eax
0x18004f8d4  js      loc_18004FA17
0x18004f8da  mov     rcx, [r14+28h]; hKey
0x18004f8de  lea     rax, [rsp+3A8h+hKey]
0x18004f8e3  mov     r9d, 20019h; samDesired
0x18004f8e9  mov     [rsp+3A8h+phkResult], rax; phkResult
0x18004f8ee  xor     r8d, r8d; ulOptions
0x18004f8f1  lea     rdx, [rsp+3A8h+SubKey]; lpSubKey
0x18004f8f6  call    cs:__imp_RegOpenKeyExW
0x18004f8fc  test    eax, eax
0x18004f8fe  jz      loc_18004F9FB
0x18004f904  cmp     dword ptr [rbx+60h], 0
0x18004f908  jnz     loc_18004F99E
0x18004f90e  mov     ecx, esi; dwErrCode
0x18004f910  call    cs:__imp_SetLastError
0x18004f916  mov     [rbx+78h], r12d
0x18004f91a  jmp     loc_18004F856
0x18004f91f  cmp     dword ptr [rbx+4Ch], 0
0x18004f923  jz      short loc_18004F92A
0x18004f925  test    r12b, dil
0x18004f928  jnz     short loc_18004F941
0x18004f92a  cmp     dword ptr [rbx+50h], 0
0x18004f92e  jz      short loc_18004F935
0x18004f930  test    r12b, dil
0x18004f933  jz      short loc_18004F941
0x18004f935  cmp     dword ptr [rbx+54h], 0
0x18004f939  jz      short loc_18004F946
0x18004f93b  bt      edi, 12h
0x18004f93f  jnb     short loc_18004F946
0x18004f941  mov     eax, r12d
0x18004f944  jmp     short loc_18004F948
0x18004f946  xor     eax, eax
0x18004f948  mov     [rbx+78h], eax
0x18004f94b  jmp     loc_18004F856
0x18004f950  bt      edi, 10h
0x18004f954  jnb     loc_18004F84D
0x18004f95a  bt      edi, 14h
0x18004f95e  jb      short loc_18004F968
0x18004f960  mov     eax, r12d
0x18004f963  jmp     loc_18004F84F
0x18004f968  mov     [rbx+80h], r12d
0x18004f96f  jmp     loc_18004F84D
0x18004f974  mov     ecx, [r14]
0x18004f977  shr     ecx, 12h
0x18004f97a  and     ecx, r12d
0x18004f97d  cmp     dword ptr [rbx+6Ch], 0
0x18004f981  jz      short loc_18004F941
0x18004f983  mov     rax, [rbx+98h]
0x18004f98a  cmp     ecx, [rax]
0x18004f98c  jz      short loc_18004F941
0x18004f98e  jmp     short loc_18004F946
0x18004f990  test    r12b, dil
0x18004f993  jnz     loc_18004F8A7
0x18004f999  jmp     loc_18004F89C
0x18004f99e  test    [r14], r12b
0x18004f9a1  jnz     loc_18004F90E
0x18004f9a7  mov     rax, [rbx+8]
0x18004f9ab  lea     r8, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f9b2  mov     r9, [r14+48h]
0x18004f9b6  lea     rcx, [rsp+3A8h+SubKey]; unsigned __int16 *
0x18004f9bb  mov     edx, 190h; unsigned __int64
0x18004f9c0  mov     [rsp+3A8h+phkResult], rax
0x18004f9c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f9ca  test    eax, eax
0x18004f9cc  js      short loc_18004FA17
0x18004f9ce  lea     rax, [rsp+3A8h+hKey]
0x18004f9d3  mov     r9d, 20019h; samDesired
0x18004f9d9  xor     r8d, r8d; ulOptions
0x18004f9dc  mov     [rsp+3A8h+phkResult], rax; phkResult
0x18004f9e1  lea     rdx, [rsp+3A8h+SubKey]; lpSubKey
0x18004f9e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f9ed  call    cs:__imp_RegOpenKeyExW
0x18004f9f3  test    eax, eax
0x18004f9f5  jnz     loc_18004F90E
0x18004f9fb  mov     rcx, [rsp+3A8h+hKey]; hKey
0x18004fa00  call    cs:__imp_RegCloseKey
0x18004fa06  mov     ecx, esi; dwErrCode
0x18004fa08  call    cs:__imp_SetLastError
0x18004fa0e  mov     [rbx+7Ch], r12d
0x18004fa12  jmp     loc_18004F856
0x18004fa17  movzx   ecx, ax; dwErrCode
0x18004fa1a  call    cs:__imp_SetLastError
0x18004fa20  xor     eax, eax
0x18004fa22  jmp     loc_18004F862
```
