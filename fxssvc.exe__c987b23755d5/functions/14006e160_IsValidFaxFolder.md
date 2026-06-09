# IsValidFaxFolder

- ea: `0x14006e160`
- end: `0x14006e3e3`
- name: `IsValidFaxFolder`
- size: `643`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000b9bc`
- `0x14001e140`
- `0x140027a58`
- `0x14003ed20`
- `0x14004fdac`
- `0x1400509c8`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140065dbc`
- `0x140066868`
- `0x14006bff4`
- `0x14006e160`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x14006e26d`
- `KERNEL32!GetTempFileNameW` at `0x14006e26d`
- `KERNEL32!GetLastError` at `0x14006e1fb`
- `KERNEL32!GetLastError` at `0x14006e277`
- `KERNEL32!GetLastError` at `0x14006e2d5`
- `KERNEL32!GetLastError` at `0x14006e323`
- `KERNEL32!GetLastError` at `0x14006e353`
- `KERNEL32!GetLastError` at `0x14006e37d`
- `KERNEL32!GetLastError` at `0x14006e1fb`
- `KERNEL32!GetLastError` at `0x14006e277`
- `KERNEL32!GetLastError` at `0x14006e2d5`
- `KERNEL32!GetLastError` at `0x14006e323`
- `KERNEL32!GetLastError` at `0x14006e353`
- `KERNEL32!GetLastError` at `0x14006e37d`
- `KERNEL32!FindFirstFileW` at `0x14006e2c9`
- `KERNEL32!FindFirstFileW` at `0x14006e2c9`
- `KERNEL32!FindClose` at `0x14006e301`
- `KERNEL32!FindClose` at `0x14006e301`
- `KERNEL32!GetFileAttributesW` at `0x14006e241`
- `KERNEL32!GetFileAttributesW` at `0x14006e241`

## pseudocode

```c
__int64 __fastcall IsValidFaxFolder(unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  WCHAR *v3; // rdi
  DWORD v4; // eax
  DWORD v5; // ebx
  DWORD FileAttributesW; // eax
  DWORD v7; // eax
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  HANDLE FirstFileW; // rax
  DWORD v11; // eax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-488h] BYREF
  WCHAR TempFileName[264]; // [rsp+270h] [rbp-238h] BYREF

  memset_0(TempFileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  v2 = (const WCHAR *)ExpandEnvironmentString(a1);
  v3 = (WCHAR *)v2;
  if ( v2 )
  {
    FileAttributesW = GetFileAttributesW(v2);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      }
      goto LABEL_38;
    }
    if ( !GetTempFileNameW(v3, L"TST", 0, TempFileName) )
    {
      v7 = GetLastError();
      v5 = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_38;
      }
      v9 = 89;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v7);
LABEL_38:
      pMemFree(v3);
      return v5;
    }
    FirstFileW = FindFirstFileW(TempFileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      v11 = GetLastError();
      v5 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v13 = 90;
    }
    else
    {
      v5 = 0;
      if ( FindClose(FirstFileW)
        || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v11 = GetLastError();
      v12 = WPP_GLOBAL_Control;
      v13 = 91;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v11);
LABEL_29:
    if ( (unsigned int)SafeDeleteFileByHandle(TempFileName) )
      goto LABEL_38;
    v7 = GetLastError();
    v5 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v9 = 92;
    goto LABEL_17;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x14006e160  mov     [rsp+arg_8], rbx
0x14006e165  mov     [rsp+arg_10], rbp
0x14006e16a  push    rsi
0x14006e16b  push    rdi
0x14006e16c  push    r14
0x14006e16e  sub     rsp, 490h
0x14006e175  mov     rax, cs:__security_cookie
0x14006e17c  xor     rax, rsp
0x14006e17f  mov     [rsp+4A8h+var_28], rax
0x14006e187  mov     rbx, rcx
0x14006e18a  xor     edx, edx; Val
0x14006e18c  lea     rcx, [rsp+4A8h+TempFileName]; void *
0x14006e194  mov     r8d, 208h; Size
0x14006e19a  call    memset_0
0x14006e19f  xor     edx, edx; Val
0x14006e1a1  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x14006e1a6  mov     r8d, 250h; Size
0x14006e1ac  call    memset_0
0x14006e1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e1b8  lea     rbp, WPP_GLOBAL_Control
0x14006e1bf  lea     r14, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e1c6  mov     sil, 2
0x14006e1c9  cmp     rcx, rbp
0x14006e1cc  jz      short loc_14006E1EB
0x14006e1ce  test    [rcx+1Ch], sil
0x14006e1d2  jz      short loc_14006E1EB
0x14006e1d4  cmp     byte ptr [rcx+19h], 5
0x14006e1d8  jb      short loc_14006E1EB
0x14006e1da  mov     rcx, [rcx+10h]
0x14006e1de  mov     edx, 56h ; 'V'
0x14006e1e3  mov     r8, r14
0x14006e1e6  call    WPP_SF_
0x14006e1eb  mov     rcx, rbx; unsigned __int16 *
0x14006e1ee  call    ExpandEnvironmentString
0x14006e1f3  mov     rdi, rax
0x14006e1f6  test    rax, rax
0x14006e1f9  jnz     short loc_14006E23E
0x14006e1fb  call    cs:__imp_GetLastError
0x14006e201  mov     ebx, eax
0x14006e203  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e20a  cmp     rcx, rbp
0x14006e20d  jz      loc_14006E3B9
0x14006e213  test    [rcx+1Ch], sil
0x14006e217  jz      loc_14006E3B9
0x14006e21d  cmp     [rcx+19h], sil
0x14006e221  jb      loc_14006E3B9
0x14006e227  mov     rcx, [rcx+10h]
0x14006e22b  lea     edx, [rdi+57h]
0x14006e22e  mov     r9d, eax
0x14006e231  mov     r8, r14
0x14006e234  call    WPP_SF_d
0x14006e239  jmp     loc_14006E3B9
0x14006e23e  mov     rcx, rdi; lpFileName
0x14006e241  call    cs:__imp_GetFileAttributesW
0x14006e247  cmp     eax, 0FFFFFFFFh
0x14006e24a  jz      loc_14006E37D
0x14006e250  test    al, 10h
0x14006e252  jz      loc_14006E37D
0x14006e258  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x14006e260  xor     r8d, r8d; uUnique
0x14006e263  lea     rdx, PrefixString; "TST"
0x14006e26a  mov     rcx, rdi; lpPathName
0x14006e26d  call    cs:__imp_GetTempFileNameW
0x14006e273  test    eax, eax
0x14006e275  jnz     short loc_14006E2BC
0x14006e277  call    cs:__imp_GetLastError
0x14006e27d  mov     ebx, eax
0x14006e27f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e286  cmp     rcx, rbp
0x14006e289  jz      loc_14006E3B1
0x14006e28f  test    [rcx+1Ch], sil
0x14006e293  jz      loc_14006E3B1
0x14006e299  cmp     [rcx+19h], sil
0x14006e29d  jb      loc_14006E3B1
0x14006e2a3  mov     edx, 59h ; 'Y'
0x14006e2a8  mov     rcx, [rcx+10h]
0x14006e2ac  mov     r9d, eax
0x14006e2af  mov     r8, r14
0x14006e2b2  call    WPP_SF_d
0x14006e2b7  jmp     loc_14006E3B1
0x14006e2bc  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x14006e2c1  lea     rcx, [rsp+4A8h+TempFileName]; lpFileName
0x14006e2c9  call    cs:__imp_FindFirstFileW
0x14006e2cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006e2d3  jnz     short loc_14006E2FC
0x14006e2d5  call    cs:__imp_GetLastError
0x14006e2db  mov     ebx, eax
0x14006e2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e2e4  cmp     rcx, rbp
0x14006e2e7  jz      short loc_14006E342
0x14006e2e9  test    [rcx+1Ch], sil
0x14006e2ed  jz      short loc_14006E342
0x14006e2ef  cmp     [rcx+19h], sil
0x14006e2f3  jb      short loc_14006E342
0x14006e2f5  mov     edx, 5Ah ; 'Z'
0x14006e2fa  jmp     short loc_14006E333
0x14006e2fc  mov     rcx, rax; hFindFile
0x14006e2ff  xor     ebx, ebx
0x14006e301  call    cs:__imp_FindClose
0x14006e307  test    eax, eax
0x14006e309  jnz     short loc_14006E342
0x14006e30b  mov     rax, cs:WPP_GLOBAL_Control
0x14006e312  cmp     rax, rbp
0x14006e315  jz      short loc_14006E342
0x14006e317  test    [rax+1Ch], sil
0x14006e31b  jz      short loc_14006E342
0x14006e31d  cmp     [rax+19h], sil
0x14006e321  jb      short loc_14006E342
0x14006e323  call    cs:__imp_GetLastError
0x14006e329  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e330  lea     edx, [rbx+5Bh]
0x14006e333  mov     rcx, [rcx+10h]
0x14006e337  mov     r9d, eax
0x14006e33a  mov     r8, r14
0x14006e33d  call    WPP_SF_d
0x14006e342  lea     rcx, [rsp+4A8h+TempFileName]; unsigned __int16 *
0x14006e34a  call    ?SafeDeleteFileByHandle@@YAHPEAG@Z; SafeDeleteFileByHandle(ushort *)
0x14006e34f  test    eax, eax
0x14006e351  jnz     short loc_14006E3B1
0x14006e353  call    cs:__imp_GetLastError
0x14006e359  mov     ebx, eax
0x14006e35b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e362  cmp     rcx, rbp
0x14006e365  jz      short loc_14006E3B1
0x14006e367  test    [rcx+1Ch], sil
0x14006e36b  jz      short loc_14006E3B1
0x14006e36d  cmp     [rcx+19h], sil
0x14006e371  jb      short loc_14006E3B1
0x14006e373  mov     edx, 5Ch ; '\'
0x14006e378  jmp     loc_14006E2A8
0x14006e37d  call    cs:__imp_GetLastError
0x14006e383  mov     ebx, eax
0x14006e385  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e38c  cmp     rcx, rbp
0x14006e38f  jz      short loc_14006E3B1
0x14006e391  test    [rcx+1Ch], sil
0x14006e395  jz      short loc_14006E3B1
0x14006e397  cmp     [rcx+19h], sil
0x14006e39b  jb      short loc_14006E3B1
0x14006e39d  mov     rcx, [rcx+10h]
0x14006e3a1  mov     edx, 58h ; 'X'
0x14006e3a6  mov     r9d, eax
0x14006e3a9  mov     r8, r14
0x14006e3ac  call    WPP_SF_d
0x14006e3b1  mov     rcx, rdi; lpMem
0x14006e3b4  call    pMemFree
0x14006e3b9  mov     eax, ebx
0x14006e3bb  mov     rcx, [rsp+4A8h+var_28]
0x14006e3c3  xor     rcx, rsp; StackCookie
0x14006e3c6  call    __security_check_cookie
0x14006e3cb  lea     r11, [rsp+4A8h+var_18]
0x14006e3d3  mov     rbx, [r11+28h]
0x14006e3d7  mov     rbp, [r11+30h]
0x14006e3db  mov     rsp, r11
0x14006e3de  pop     r14
0x14006e3e0  pop     rdi
0x14006e3e1  pop     rsi
0x14006e3e2  retn
```
