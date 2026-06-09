# CCMLuaUtil::DeleteHiddenCmProfileFiles(ushort const *)

- ea: `0x180002af0`
- end: `0x18000308a`
- name: `?DeleteHiddenCmProfileFiles@CCMLuaUtil@@UEAAJPEBG@Z`
- size: `1434`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800029d4`
- `0x180002af0`
- `0x180003f78`
- `0x180004100`
- `0x180004e1c`
- `0x180005486`
- `0x1800054b0`

## import_xrefs

- `cmutil!CmStrrchrW` at `0x180002d31`
- `cmutil!CmStrrchrW` at `0x180002d31`
- `cmutil!CmFree` at `0x180002d8a`
- `cmutil!CmFree` at `0x18000302e`
- `cmutil!CmFree` at `0x180002d8a`
- `cmutil!CmFree` at `0x18000302e`
- `cmutil!CmMalloc` at `0x180002cf5`
- `cmutil!CmMalloc` at `0x180002cf5`
- `KERNEL32!FindFirstFileW` at `0x180002e1e`
- `KERNEL32!FindFirstFileW` at `0x180002e1e`
- `KERNEL32!FindNextFileW` at `0x18000300d`
- `KERNEL32!FindNextFileW` at `0x18000300d`
- `KERNEL32!lstrlenW` at `0x180002ce6`
- `KERNEL32!lstrlenW` at `0x180002ce6`
- `KERNEL32!FindClose` at `0x18000301f`
- `KERNEL32!FindClose` at `0x18000301f`
- `KERNEL32!GetLastError` at `0x180002e2d`
- `KERNEL32!GetLastError` at `0x180002e2d`
- `SHELL32!SHGetFolderPathW` at `0x180002b89`
- `SHELL32!SHGetFolderPathW` at `0x180002c1c`
- `SHELL32!SHGetFolderPathW` at `0x180002b89`
- `SHELL32!SHGetFolderPathW` at `0x180002c1c`

## string_xrefs

- `0x180002c26`: `SHGetFolderPath failed with Error: %x\n`
- `0x180003044`: `Something seriously wrong. The appdata folder is outside User Profile!!\n`
- `0x180003055`: `SHGetFolderPath failed with Error %x\n`
- `0x180002d97`: `Documents Path: %s`
- `0x180002e04`: `szFindPath: %s`
- `0x180002f05`: `TO DELETE - Profile Folder: %s`
- `0x180002f26`: `Error - DeleteFolderRecursively for folder: %d`
- `0x180002fc6`: `TO DELETE - CMP File      : %s`
- `0x180002fe7`: `Error - DeleteFolderRecursively for file: %d`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::DeleteHiddenCmProfileFiles(CCMLuaUtil *this, const unsigned __int16 *a2)
{
  DWORD LastError; // edi
  HRESULT v4; // eax
  __int64 v5; // r9
  __int64 v6; // rdx
  WCHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rsi
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  WCHAR *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // r8
  WCHAR *v17; // rdx
  WCHAR v18; // r9
  WCHAR *v19; // rcx
  unsigned __int64 v20; // r14
  wchar_t *v21; // rax
  unsigned __int16 **v22; // r9
  wchar_t *v23; // rbx
  unsigned __int16 *v24; // rax
  __int64 v25; // r8
  wchar_t *v26; // rax
  wchar_t *v27; // r9
  wchar_t v28; // cx
  wchar_t *v29; // rdx
  __int64 v30; // r9
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // r9
  HANDLE FirstFileW; // r14
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned int v37; // eax
  __int64 v38; // r9
  DWORD v39; // esi
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int v42; // eax
  __int64 v43; // r9
  DWORD v44; // esi
  unsigned __int64 *pszPath; // [rsp+20h] [rbp-E0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v49[528]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR String[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  WCHAR FileName[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v52[528]; // [rsp+B00h] [rbp+A00h] BYREF
  wchar_t v53[264]; // [rsp+D10h] [rbp+C10h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  LastError = 0;
  memset_0(v52, 0, 0x20Au);
  memset_0(v49, 0, 0x20Au);
  memset_0(String, 0, 0x20Au);
  v4 = SHGetFolderPathW(0, 40, 0, 1u, String);
  if ( v4 < 0 )
  {
    v10 = L"SHGetFolderPath failed with Error %x\n";
    goto LABEL_57;
  }
  v6 = 260;
  v7 = String;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0 ? 0x80070057 : 0;
  v9 = (260 - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
  {
    v10 = L"StringCchLength failed with Error %x\n";
LABEL_58:
    MyDbgPrintfW(0xFFFFFFFFLL, v10, v8, v5);
    return LastError;
  }
  memset_0(Buffer, 0, 0x20Au);
  v4 = SHGetFolderPathW(0, 26, 0, 1u, Buffer);
  if ( v4 < 0 )
  {
    v10 = L"SHGetFolderPath failed with Error: %x\n";
LABEL_57:
    v8 = (unsigned int)v4;
    goto LABEL_58;
  }
  v11 = 260;
  v12 = Buffer;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v8 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
    v10 = L"StringCchLength failed with Error: %x\n";
    goto LABEL_58;
  }
  if ( ((260 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64)) <= (unsigned __int64)v9
    || (v13 = &Buffer[v9 + 1]) == 0 )
  {
    MyDbgPrintfW(0xFFFFFFFFLL, L"Something seriously wrong. The appdata folder is outside User Profile!!\n", v8, v5);
    return LastError;
  }
  v14 = 2147483646;
  v15 = 2147483646;
  v16 = 261;
  v17 = (WCHAR *)v52;
  do
  {
    if ( !v15 )
      break;
    v18 = *v13;
    if ( !*v13 )
      break;
    ++v13;
    *v17++ = v18;
    --v15;
    --v16;
  }
  while ( v16 );
  v19 = v17 - 1;
  if ( v16 )
    v19 = v17;
  *v19 = 0;
  v20 = lstrlenW(String) + 1;
  v21 = (wchar_t *)CmMalloc(2 * v20);
  v23 = v21;
  if ( !v21 )
    goto LABEL_53;
  if ( (int)StringCchCopyExW(v21, v20, String, v22, pszPath, 0x100u) < 0 || (v24 = CmStrrchrW(v23, 0x5Cu)) == 0 )
  {
    CmFree(v23);
LABEL_53:
    LOWORD(LastError) = -1;
    return (unsigned __int16)LastError | 0x80070000;
  }
  *v24 = 0;
  v25 = 261;
  v26 = (wchar_t *)v49;
  v27 = v23;
  do
  {
    if ( !v14 )
      break;
    v28 = *v23;
    if ( !*v23 )
      break;
    ++v23;
    *v26++ = v28;
    --v14;
    --v25;
  }
  while ( v25 );
  v29 = v26 - 1;
  if ( v25 )
    v29 = v26;
  *v29 = 0;
  CmFree(v27);
  MyDbgPrintfW(0xFFFFFFFFLL, L"Documents Path: %s", v49, v30);
  memset_0(FileName, 0, 0x20Au);
  v31 = StringCchPrintfExW(FileName, 0x105u, 0, 0, 0x100u, L"%s\\*", v49);
  if ( v31 >= 0 )
  {
    MyDbgPrintfW(0xFFFFFFFFLL, L"szFindPath: %s", FileName, v32);
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0
          && (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
        {
          MyDbgPrintfW(0xFFFFFFFFLL, L"Folder - %s\n", FindFileData.cFileName, v33);
          memset_0(Buffer, 0, 0x20Au);
          if ( (int)StringCchPrintfExW(
                      Buffer,
                      0x105u,
                      0,
                      0,
                      0x100u,
                      L"%s\\%s\\%s\\%s\\%s",
                      v49,
                      FindFileData.cFileName,
                      v52,
                      L"Microsoft\\Network\\Connections\\_hiddencm",
                      a2) < 0 )
          {
            MyDbgPrintfW(0xFFFFFFFFLL, L"StringCchPrintEx on szHiddenProfile failed", v35, v36);
          }
          else
          {
            MyDbgPrintfW(0xFFFFFFFFLL, L"TO DELETE - Profile Folder: %s", Buffer, v36);
            v37 = DeleteFolderRecursively(Buffer);
            v39 = v37;
            if ( v37 )
            {
              MyDbgPrintfW(0xFFFFFFFFLL, L"Error - DeleteFolderRecursively for folder: %d", v37, v38);
              LastError = v39;
            }
          }
          memset_0(v53, 0, 0x20Au);
          if ( (int)StringCchPrintfExW(
                      v53,
                      0x105u,
                      0,
                      0,
                      0x100u,
                      L"%s\\%s\\%s\\%s\\%s.cmp",
                      v49,
                      FindFileData.cFileName,
                      v52,
                      L"Microsoft\\Network\\Connections\\_hiddencm",
                      a2) < 0 )
          {
            MyDbgPrintfW(0xFFFFFFFFLL, L"StringCchPrintEx on szHiddenCmpFile failed", v40, v41);
          }
          else
          {
            MyDbgPrintfW(0xFFFFFFFFLL, L"TO DELETE - CMP File      : %s", v53, v41);
            v42 = DeleteFolderRecursively(v53);
            v44 = v42;
            if ( v42 )
            {
              MyDbgPrintfW(0xFFFFFFFFLL, L"Error - DeleteFolderRecursively for file: %d", v42, v43);
              LastError = v44;
            }
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
    }
  }
  else
  {
    LastError = (unsigned __int16)v31;
  }
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180002af0  push    rbp
0x180002af2  push    rbx
0x180002af3  push    rsi
0x180002af4  push    rdi
0x180002af5  push    r12
0x180002af7  push    r14
0x180002af9  push    r15
0x180002afb  lea     rbp, [rsp-0E30h]
0x180002b03  sub     rsp, 0F30h
0x180002b0a  mov     rax, cs:__security_cookie
0x180002b11  xor     rax, rsp
0x180002b14  mov     [rbp+0E60h+var_40], rax
0x180002b1b  mov     r15, rdx
0x180002b1e  xor     edx, edx; Val
0x180002b20  mov     r8d, 250h; Size
0x180002b26  lea     rcx, [rsp+0F60h+FindFileData]; void *
0x180002b2b  call    memset_0
0x180002b30  xor     r12d, r12d
0x180002b33  mov     edi, r12d
0x180002b36  mov     ebx, 20Ah
0x180002b3b  mov     r8d, ebx; Size
0x180002b3e  xor     edx, edx; Val
0x180002b40  lea     rcx, [rbp+0E60h+var_460]; void *
0x180002b47  call    memset_0
0x180002b4c  mov     r8d, ebx; Size
0x180002b4f  xor     edx, edx; Val
0x180002b51  lea     rcx, [rbp+0E60h+var_A90]; void *
0x180002b58  call    memset_0
0x180002b5d  mov     r8d, ebx; Size
0x180002b60  xor     edx, edx; Val
0x180002b62  lea     rcx, [rbp+0E60h+String]; void *
0x180002b69  call    memset_0
0x180002b6e  lea     rax, [rbp+0E60h+String]
0x180002b75  mov     [rsp+0F60h+pszPath], rax; pszPath
0x180002b7a  lea     r9d, [r12+1]; dwFlags
0x180002b7f  xor     r8d, r8d; hToken
0x180002b82  lea     edx, [r12+28h]; csidl
0x180002b87  xor     ecx, ecx; hwnd
0x180002b89  call    cs:__imp_SHGetFolderPathW
0x180002b8f  test    eax, eax
0x180002b91  js      loc_180003055
0x180002b97  mov     ebx, 104h
0x180002b9c  mov     edx, ebx
0x180002b9e  lea     rax, [rbp+0E60h+String]
0x180002ba5  cmp     [rax], r12w
0x180002ba9  jz      short loc_180002BB5
0x180002bab  add     rax, 2
0x180002baf  sub     rdx, 1
0x180002bb3  jnz     short loc_180002BA5
0x180002bb5  mov     rax, rdx
0x180002bb8  neg     rax
0x180002bbb  sbb     r8d, r8d
0x180002bbe  not     r8d
0x180002bc1  mov     r14d, 80070057h
0x180002bc7  and     r8d, r14d
0x180002bca  mov     rax, rdx
0x180002bcd  mov     rcx, rbx
0x180002bd0  sub     rcx, rdx
0x180002bd3  neg     rax
0x180002bd6  sbb     rsi, rsi
0x180002bd9  and     rsi, rcx
0x180002bdc  test    rdx, rdx
0x180002bdf  jnz     short loc_180002BED
0x180002be1  lea     rdx, aStringcchlengt_0; "StringCchLength failed with Error %x\n"
0x180002be8  jmp     loc_18000305F
0x180002bed  xor     edx, edx; Val
0x180002bef  mov     r8d, 20Ah; Size
0x180002bf5  lea     rcx, [rbp+0E60h+Buffer]; void *
0x180002bfc  call    memset_0
0x180002c01  lea     rax, [rbp+0E60h+Buffer]
0x180002c08  mov     [rsp+0F60h+pszPath], rax; unsigned __int64 *
0x180002c0d  mov     r9d, 1; dwFlags
0x180002c13  xor     r8d, r8d; hToken
0x180002c16  lea     edx, [r9+19h]; csidl
0x180002c1a  xor     ecx, ecx; hwnd
0x180002c1c  call    cs:__imp_SHGetFolderPathW
0x180002c22  test    eax, eax
0x180002c24  jns     short loc_180002C32
0x180002c26  lea     rdx, aShgetfolderpat_0; "SHGetFolderPath failed with Error: %x\n"
0x180002c2d  jmp     loc_18000305C
0x180002c32  mov     rcx, rbx
0x180002c35  lea     rax, [rbp+0E60h+Buffer]
0x180002c3c  cmp     [rax], r12w
0x180002c40  jz      short loc_180002C4C
0x180002c42  add     rax, 2
0x180002c46  sub     rcx, 1
0x180002c4a  jnz     short loc_180002C3C
0x180002c4c  mov     rax, rcx
0x180002c4f  neg     rax
0x180002c52  sbb     r8d, r8d
0x180002c55  not     r8d
0x180002c58  and     r8d, r14d
0x180002c5b  mov     rax, rcx
0x180002c5e  sub     rbx, rcx
0x180002c61  neg     rax
0x180002c64  sbb     rdx, rdx
0x180002c67  and     rdx, rbx
0x180002c6a  test    rcx, rcx
0x180002c6d  jnz     short loc_180002C7B
0x180002c6f  lea     rdx, aStringcchlengt; "StringCchLength failed with Error: %x\n"
0x180002c76  jmp     loc_18000305F
0x180002c7b  cmp     rdx, rsi
0x180002c7e  jbe     loc_180003044
0x180002c84  lea     rax, [rbp+0E60h+var_C9E]
0x180002c8b  lea     rax, [rax+rsi*2]
0x180002c8f  test    rax, rax
0x180002c92  jz      loc_180003044
0x180002c98  mov     esi, 7FFFFFFEh
0x180002c9d  mov     ecx, esi
0x180002c9f  mov     r8d, 105h
0x180002ca5  lea     rdx, [rbp+0E60h+var_460]
0x180002cac  test    rcx, rcx
0x180002caf  jz      short loc_180002CD0
0x180002cb1  movzx   r9d, word ptr [rax]
0x180002cb5  test    r9w, r9w
0x180002cb9  jz      short loc_180002CD0
0x180002cbb  add     rax, 2
0x180002cbf  mov     [rdx], r9w
0x180002cc3  add     rdx, 2
0x180002cc7  dec     rcx
0x180002cca  sub     r8, 1
0x180002cce  jnz     short loc_180002CAC
0x180002cd0  lea     rcx, [rdx-2]
0x180002cd4  test    r8, r8
0x180002cd7  cmovnz  rcx, rdx
0x180002cdb  mov     [rcx], r12w
0x180002cdf  lea     rcx, [rbp+0E60h+String]; lpString
0x180002ce6  call    cs:__imp_lstrlenW
0x180002cec  inc     eax
0x180002cee  movsxd  r14, eax
0x180002cf1  lea     rcx, [r14+r14]
0x180002cf5  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180002cfb  mov     rbx, rax
0x180002cfe  test    rax, rax
0x180002d01  jz      loc_180003034
0x180002d07  mov     dword ptr [rsp+0F60h+var_F38], 100h; unsigned int
0x180002d0f  lea     r8, [rbp+0E60h+String]; unsigned __int16 *
0x180002d16  mov     rdx, r14; unsigned __int64
0x180002d19  mov     rcx, rax; pszDest
0x180002d1c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180002d21  test    eax, eax
0x180002d23  js      loc_18000302B
0x180002d29  mov     edx, 5Ch ; '\'
0x180002d2e  mov     rcx, rbx
0x180002d31  call    cs:__imp_?CmStrrchrW@@YAPEAGPEBGG@Z; CmStrrchrW(ushort const *,ushort)
0x180002d37  test    rax, rax
0x180002d3a  jz      loc_18000302B
0x180002d40  mov     [rax], r12w
0x180002d44  mov     r14d, 105h
0x180002d4a  mov     r8d, r14d
0x180002d4d  lea     rax, [rbp+0E60h+var_A90]
0x180002d54  mov     r9, rbx
0x180002d57  test    rsi, rsi
0x180002d5a  jz      short loc_180002D78
0x180002d5c  movzx   ecx, word ptr [rbx]
0x180002d5f  test    cx, cx
0x180002d62  jz      short loc_180002D78
0x180002d64  add     rbx, 2
0x180002d68  mov     [rax], cx
0x180002d6b  add     rax, 2
0x180002d6f  dec     rsi
0x180002d72  sub     r8, 1
0x180002d76  jnz     short loc_180002D57
0x180002d78  lea     rdx, [rax-2]
0x180002d7c  test    r8, r8
0x180002d7f  cmovnz  rdx, rax
0x180002d83  mov     [rdx], r12w
0x180002d87  mov     rcx, r9
0x180002d8a  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180002d90  lea     r8, [rbp+0E60h+var_A90]
0x180002d97  lea     rdx, aDocumentsPathS; "Documents Path: %s"
0x180002d9e  or      ebx, 0FFFFFFFFh
0x180002da1  mov     ecx, ebx
0x180002da3  call    MyDbgPrintfW
0x180002da8  xor     edx, edx; Val
0x180002daa  mov     r8d, 20Ah; Size
0x180002db0  lea     rcx, [rbp+0E60h+FileName]; void *
0x180002db7  call    memset_0
0x180002dbc  lea     rax, [rbp+0E60h+var_A90]
0x180002dc3  mov     [rsp+0F60h+var_F30], rax
0x180002dc8  lea     rax, aS; "%s\\*"
0x180002dcf  mov     [rsp+0F60h+var_F38], rax; unsigned __int16 *
0x180002dd4  mov     dword ptr [rsp+0F60h+pszPath], 100h; unsigned int
0x180002ddc  xor     r9d, r9d; unsigned __int64 *
0x180002ddf  xor     r8d, r8d; unsigned __int16 **
0x180002de2  mov     rdx, r14; unsigned __int64
0x180002de5  lea     rcx, [rbp+0E60h+FileName]; Buffer
0x180002dec  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180002df1  test    eax, eax
0x180002df3  jns     short loc_180002DFD
0x180002df5  movzx   edi, ax
0x180002df8  jmp     loc_180003025
0x180002dfd  lea     r8, [rbp+0E60h+FileName]
0x180002e04  lea     rdx, aSzfindpathS; "szFindPath: %s"
0x180002e0b  mov     ecx, ebx
0x180002e0d  call    MyDbgPrintfW
0x180002e12  lea     rdx, [rsp+0F60h+FindFileData]; lpFindFileData
0x180002e17  lea     rcx, [rbp+0E60h+FileName]; lpFileName
0x180002e1e  call    cs:__imp_FindFirstFileW
0x180002e24  mov     r14, rax
0x180002e27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002e2b  jnz     short loc_180002E3A
0x180002e2d  call    cs:__imp_GetLastError
0x180002e33  mov     edi, eax
0x180002e35  jmp     loc_180003025
0x180002e3a  test    byte ptr [rsp+0F60h+FindFileData.dwFileAttributes], 10h
0x180002e3f  jz      loc_180003005
0x180002e45  movzx   eax, [rbp+0E60h+FindFileData.cFileName+2]
0x180002e49  cmp     [rbp+0E60h+FindFileData.cFileName], 2Eh ; '.'
0x180002e4e  jnz     short loc_180002E71
0x180002e50  test    ax, ax
0x180002e53  jz      loc_180003005
0x180002e59  cmp     [rbp+0E60h+FindFileData.cFileName], 2Eh ; '.'
0x180002e5e  jnz     short loc_180002E71
0x180002e60  cmp     ax, 2Eh ; '.'
0x180002e64  jnz     short loc_180002E71
0x180002e66  cmp     [rbp+0E60h+FindFileData.cFileName+4], r12w
0x180002e6b  jz      loc_180003005
0x180002e71  lea     r8, [rbp+0E60h+FindFileData.cFileName]
0x180002e75  lea     rdx, aFolderS; "Folder - %s\n"
0x180002e7c  mov     ecx, ebx
0x180002e7e  call    MyDbgPrintfW
0x180002e83  xor     edx, edx; Val
0x180002e85  mov     r8d, 20Ah; Size
0x180002e8b  lea     rcx, [rbp+0E60h+Buffer]; void *
0x180002e92  call    memset_0
0x180002e97  mov     [rsp+0F60h+var_F10], r15
0x180002e9c  lea     rax, aMicrosoftNetwo; "Microsoft\\Network\\Connections\\_hidde"...
0x180002ea3  mov     [rsp+0F60h+var_F18], rax
0x180002ea8  lea     rax, [rbp+0E60h+var_460]
0x180002eaf  mov     [rsp+0F60h+var_F20], rax
0x180002eb4  lea     rax, [rbp+0E60h+FindFileData.cFileName]
0x180002eb8  mov     [rsp+0F60h+var_F28], rax
0x180002ebd  lea     rax, [rbp+0E60h+var_A90]
0x180002ec4  mov     [rsp+0F60h+var_F30], rax
0x180002ec9  lea     rax, aSSSSS; "%s\\%s\\%s\\%s\\%s"
0x180002ed0  mov     [rsp+0F60h+var_F38], rax; unsigned __int16 *
0x180002ed5  mov     dword ptr [rsp+0F60h+pszPath], 100h; unsigned int
0x180002edd  xor     r9d, r9d; unsigned __int64 *
0x180002ee0  xor     r8d, r8d; unsigned __int16 **
0x180002ee3  mov     edx, 105h; unsigned __int64
0x180002ee8  lea     rcx, [rbp+0E60h+Buffer]; Buffer
0x180002eef  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180002ef4  nop
0x180002ef5  shr     eax, 1Fh
0x180002ef8  xor     al, 1
0x180002efa  mov     ecx, ebx
0x180002efc  jz      short loc_180002F38
0x180002efe  lea     r8, [rbp+0E60h+Buffer]
0x180002f05  lea     rdx, aToDeleteProfil; "TO DELETE - Profile Folder: %s"
0x180002f0c  call    MyDbgPrintfW
0x180002f11  lea     rcx, [rbp+0E60h+Buffer]; unsigned __int16 *
0x180002f18  call    ?DeleteFolderRecursively@@YAKPEBG@Z; DeleteFolderRecursively(ushort const *)
0x180002f1d  mov     esi, eax
0x180002f1f  test    eax, eax
0x180002f21  jz      short loc_180002F44
0x180002f23  mov     r8d, eax
0x180002f26  lea     rdx, aErrorDeletefol_0; "Error - DeleteFolderRecursively for fol"...
0x180002f2d  mov     ecx, ebx
0x180002f2f  call    MyDbgPrintfW
0x180002f34  mov     edi, esi
0x180002f36  jmp     short loc_180002F44
0x180002f38  lea     rdx, aStringcchprint; "StringCchPrintEx on szHiddenProfile fai"...
0x180002f3f  call    MyDbgPrintfW
0x180002f44  xor     edx, edx; Val
0x180002f46  mov     r8d, 20Ah; Size
0x180002f4c  lea     rcx, [rbp+0E60h+var_250]; void *
0x180002f53  call    memset_0
0x180002f58  mov     [rsp+0F60h+var_F10], r15
0x180002f5d  lea     rax, aMicrosoftNetwo; "Microsoft\\Network\\Connections\\_hidde"...
0x180002f64  mov     [rsp+0F60h+var_F18], rax
0x180002f69  lea     rax, [rbp+0E60h+var_460]
0x180002f70  mov     [rsp+0F60h+var_F20], rax
0x180002f75  lea     rax, [rbp+0E60h+FindFileData.cFileName]
0x180002f79  mov     [rsp+0F60h+var_F28], rax
0x180002f7e  lea     rax, [rbp+0E60h+var_A90]
0x180002f85  mov     [rsp+0F60h+var_F30], rax
0x180002f8a  lea     rax, aSSSSSCmp; "%s\\%s\\%s\\%s\\%s.cmp"
0x180002f91  mov     [rsp+0F60h+var_F38], rax; unsigned __int16 *
0x180002f96  mov     dword ptr [rsp+0F60h+pszPath], 100h; unsigned int
0x180002f9e  xor     r9d, r9d; unsigned __int64 *
0x180002fa1  xor     r8d, r8d; unsigned __int16 **
0x180002fa4  mov     edx, 105h; unsigned __int64
0x180002fa9  lea     rcx, [rbp+0E60h+var_250]; Buffer
0x180002fb0  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180002fb5  nop
0x180002fb6  shr     eax, 1Fh
0x180002fb9  xor     al, 1
0x180002fbb  mov     ecx, ebx
0x180002fbd  jz      short loc_180002FF9
0x180002fbf  lea     r8, [rbp+0E60h+var_250]
0x180002fc6  lea     rdx, aToDeleteCmpFil; "TO DELETE - CMP File      : %s"
0x180002fcd  call    MyDbgPrintfW
0x180002fd2  lea     rcx, [rbp+0E60h+var_250]; unsigned __int16 *
0x180002fd9  call    ?DeleteFolderRecursively@@YAKPEBG@Z; DeleteFolderRecursively(ushort const *)
0x180002fde  mov     esi, eax
0x180002fe0  test    eax, eax
0x180002fe2  jz      short loc_180003005
0x180002fe4  mov     r8d, eax
0x180002fe7  lea     rdx, aErrorDeletefol; "Error - DeleteFolderRecursively for fil"...
  ... truncated ...
```
