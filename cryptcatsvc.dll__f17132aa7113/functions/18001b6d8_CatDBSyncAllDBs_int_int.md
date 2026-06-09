# _CatDBSyncAllDBs(int,int *)

- ea: `0x18001b6d8`
- end: `0x18001b8ec`
- name: `?_CatDBSyncAllDBs@@YAHHPEAH@Z`
- size: `532`
- prototype: `int(int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019fe0`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001b6d8`
- `0x18001c03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8b8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001b763`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001b763`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001b7f6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001b7f6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001b892`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001b892`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001b82e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001b82e`

## pseudocode

```c
__int64 __fastcall _CatDBSyncAllDBs(unsigned int a1, int *a2)
{
  WCHAR *v4; // rbx
  const unsigned __int16 *v5; // rcx
  const WCHAR *v6; // rax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  WCHAR *v9; // r14
  __int64 FirstFileW; // rdi
  unsigned int v11; // r8d
  unsigned int v12; // ebp
  unsigned int Error; // esi
  WCHAR *v14; // rax
  unsigned int v15; // edx
  unsigned __int16 *v16; // rcx
  unsigned int v17; // edx
  unsigned __int16 *v18; // rcx
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  LSTATUS v21; // eax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  int v25; // [rsp+28h] [rbp-290h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  v4 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = g_pwszCatalogFileBaseDirectory;
  *a2 = 0;
  v6 = _CATDBConstructWSTRPath(v5, L"{????????????????????????????????????}");
  v9 = (WCHAR *)v6;
  if ( !v6 )
  {
    FirstFileW = -1;
    v11 = 2450;
LABEL_3:
    ErrLog_LogError(v8, v7, v11, 0, 0, v25);
    goto LABEL_23;
  }
  v12 = 1;
  FirstFileW = (__int64)FindFirstFileW(v6, &FindFileData);
  if ( FirstFileW != -1 )
  {
    Error = 0;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v14 = _CATDBConstructWSTRPath(g_pwszCatalogFileBaseDirectory, FindFileData.cFileName);
        v4 = v14;
        if ( !v14 )
        {
          ErrLog_LogError(v16, v15, 0x9BBu, 0, 0, v25);
          goto LABEL_23;
        }
        if ( !(unsigned int)_CatDBSyncDB(a1, v14, FindFileData.cFileName, 1, 0, a2) )
        {
          ErrLog_LogError(v18, v17, 0x9C1u, 0, 0, v25);
          goto LABEL_23;
        }
        _CatDBFree(v4);
        v4 = 0;
        if ( *a2 )
          goto LABEL_24;
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    if ( GetLastError() == 18 )
    {
      if ( dword_180032718 )
      {
        dword_180032718 = 0;
        v21 = RegDeleteKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Cryptography\\CatalogDB",
                L"SyncIgnoreCatalogTimeChangesOnce");
        if ( v21 )
          ErrLog_LogError(v23, v22, 0x9EAu, v21, 0, v25);
      }
      v4 = 0;
LABEL_24:
      FindClose((HANDLE)FirstFileW);
LABEL_25:
      if ( !v9 )
        goto LABEL_27;
      goto LABEL_26;
    }
    ErrLog_LogError(v20, v19, 0x9D9u, 0, 0, v25);
    v4 = 0;
LABEL_23:
    Error = _CatDBGetNonzeroLastError();
    v12 = 0;
    if ( FirstFileW == -1 )
      goto LABEL_25;
    goto LABEL_24;
  }
  Error = GetLastError();
  if ( ((Error - 2) & 0xFFFFFFEE) != 0 || Error == 19 )
  {
    v11 = 2475;
    goto LABEL_3;
  }
LABEL_26:
  _CatDBFree(v9);
LABEL_27:
  if ( v4 )
    _CatDBFree(v4);
  if ( !v12 )
    SetLastError(Error);
  return v12;
}

```

## disassembly

```asm
0x18001b6d8  mov     [rsp+arg_10], rbx
0x18001b6dd  mov     [rsp+arg_18], rbp
0x18001b6e2  push    rsi
0x18001b6e3  push    rdi
0x18001b6e4  push    r12
0x18001b6e6  push    r14
0x18001b6e8  push    r15
0x18001b6ea  sub     rsp, 290h
0x18001b6f1  mov     rax, cs:__security_cookie
0x18001b6f8  xor     rax, rsp
0x18001b6fb  mov     [rsp+2B8h+var_38], rax
0x18001b703  mov     r15, rdx
0x18001b706  mov     r12d, ecx
0x18001b709  xor     edx, edx; Val
0x18001b70b  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x18001b710  mov     r8d, 250h; Size
0x18001b716  xor     ebx, ebx
0x18001b718  call    memset_0
0x18001b71d  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x18001b724  lea     rdx, asc_180024D90; "{????????????????????????????????????}"
0x18001b72b  mov     [r15], ebx
0x18001b72e  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001b733  mov     r14, rax
0x18001b736  test    rax, rax
0x18001b739  jnz     short loc_18001B756
0x18001b73b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b73f  mov     r8d, 992h; unsigned int
0x18001b745  mov     [rsp+2B8h+var_298], ebx; int
0x18001b749  xor     r9d, r9d; unsigned int
0x18001b74c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b751  jmp     loc_18001B880
0x18001b756  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x18001b75b  mov     rcx, r14; lpFileName
0x18001b75e  mov     ebp, 1
0x18001b763  call    cs:__imp_FindFirstFileW
0x18001b769  mov     rdi, rax
0x18001b76c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b770  jnz     short loc_18001B795
0x18001b772  call    cs:__imp_GetLastError
0x18001b778  mov     esi, eax
0x18001b77a  add     eax, 0FFFFFFFEh
0x18001b77d  test    eax, 0FFFFFFEEh
0x18001b782  jnz     short loc_18001B78D
0x18001b784  cmp     esi, 13h
0x18001b787  jnz     loc_18001B89D
0x18001b78d  mov     r8d, 9ABh
0x18001b793  jmp     short loc_18001B745
0x18001b795  xor     esi, esi
0x18001b797  test    byte ptr [rsp+2B8h+FindFileData.dwFileAttributes], 10h
0x18001b79c  jz      short loc_18001B7EE
0x18001b79e  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; unsigned __int16 *
0x18001b7a5  lea     rdx, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x18001b7aa  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001b7af  mov     rbx, rax
0x18001b7b2  test    rax, rax
0x18001b7b5  jz      loc_18001B85D
0x18001b7bb  mov     [rsp+2B8h+var_290], r15; int
0x18001b7c0  lea     r8, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x18001b7c5  mov     r9d, ebp; int
0x18001b7c8  mov     [rsp+2B8h+var_298], esi; int
0x18001b7cc  mov     rdx, rax; unsigned __int16 *
0x18001b7cf  mov     ecx, r12d; int
0x18001b7d2  call    ?_CatDBSyncDB@@YAHHPEBG0HHPEAH@Z; _CatDBSyncDB(int,ushort const *,ushort const *,int,int,int *)
0x18001b7d7  test    eax, eax
0x18001b7d9  jz      short loc_18001B84E
0x18001b7db  mov     rcx, rbx; void *
0x18001b7de  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001b7e3  xor     ebx, ebx
0x18001b7e5  cmp     [r15], ebx
0x18001b7e8  jnz     loc_18001B88F
0x18001b7ee  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x18001b7f3  mov     rcx, rdi; hFindFile
0x18001b7f6  call    cs:__imp_FindNextFileW
0x18001b7fc  test    eax, eax
0x18001b7fe  jnz     short loc_18001B797
0x18001b800  call    cs:__imp_GetLastError
0x18001b806  cmp     eax, 12h
0x18001b809  jnz     short loc_18001B86C
0x18001b80b  cmp     cs:dword_180032718, esi
0x18001b811  jz      short loc_18001B84A
0x18001b813  lea     r8, aSyncignorecata; "SyncIgnoreCatalogTimeChangesOnce"
0x18001b81a  mov     cs:dword_180032718, esi
0x18001b820  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Cryptography\\Cata"...
0x18001b827  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b82e  call    cs:__imp_RegDeleteKeyValueW
0x18001b834  test    eax, eax
0x18001b836  jz      short loc_18001B84A
0x18001b838  mov     r9d, eax; unsigned int
0x18001b83b  mov     [rsp+2B8h+var_298], esi; int
0x18001b83f  mov     r8d, 9EAh; unsigned int
0x18001b845  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b84a  xor     ebx, ebx
0x18001b84c  jmp     short loc_18001B88F
0x18001b84e  mov     [rsp+2B8h+var_298], esi
0x18001b852  mov     r8d, 9C1h
0x18001b858  jmp     loc_18001B749
0x18001b85d  mov     [rsp+2B8h+var_298], esi
0x18001b861  mov     r8d, 9BBh
0x18001b867  jmp     loc_18001B749
0x18001b86c  xor     r9d, r9d; unsigned int
0x18001b86f  mov     [rsp+2B8h+var_298], esi; int
0x18001b873  mov     r8d, 9D9h; unsigned int
0x18001b879  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b87e  xor     ebx, ebx
0x18001b880  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001b885  mov     esi, eax
0x18001b887  xor     ebp, ebp
0x18001b889  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b88d  jz      short loc_18001B898
0x18001b88f  mov     rcx, rdi; hFindFile
0x18001b892  call    cs:__imp_FindClose
0x18001b898  test    r14, r14
0x18001b89b  jz      short loc_18001B8A5
0x18001b89d  mov     rcx, r14; void *
0x18001b8a0  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001b8a5  test    rbx, rbx
0x18001b8a8  jz      short loc_18001B8B2
0x18001b8aa  mov     rcx, rbx; void *
0x18001b8ad  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001b8b2  test    ebp, ebp
0x18001b8b4  jnz     short loc_18001B8BE
0x18001b8b6  mov     ecx, esi; dwErrCode
0x18001b8b8  call    cs:__imp_SetLastError
0x18001b8be  mov     eax, ebp
0x18001b8c0  mov     rcx, [rsp+2B8h+var_38]
0x18001b8c8  xor     rcx, rsp; StackCookie
0x18001b8cb  call    __security_check_cookie
0x18001b8d0  lea     r11, [rsp+2B8h+var_28]
0x18001b8d8  mov     rbx, [r11+40h]
0x18001b8dc  mov     rbp, [r11+48h]
0x18001b8e0  mov     rsp, r11
0x18001b8e3  pop     r15
0x18001b8e5  pop     r14
0x18001b8e7  pop     r12
0x18001b8e9  pop     rdi
0x18001b8ea  pop     rsi
0x18001b8eb  retn
```
