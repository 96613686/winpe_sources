# CryptDiagAddActionWithWinHttpLastError

- ea: `0x180019220`
- end: `0x18001932e`
- name: `CryptDiagAddActionWithWinHttpLastError`
- size: `270`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800036dc`
- `0x180003ef0`
- `0x180006420`

## callees

- `0x180019220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001930f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001930f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019237`
- `CRYPT32!I_CertDiagControl` at `0x1800192f4`
- `CRYPT32!I_CertDiagControl` at `0x1800192f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001926c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001926c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800192b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800192b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800192a9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800192a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019307`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019307`

## string_xrefs

- `0x180019261`: `winhttp.dll`

## pseudocode

```c
void __fastcall CryptDiagAddActionWithWinHttpLastError(__int64 a1, void *a2)
{
  DWORD LastError; // eax
  DWORD v4; // ebx
  HMODULE Library; // rdi
  __int64 v6; // [rsp+40h] [rbp-38h] BYREF
  DWORD v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+4Ch] [rbp-2Ch]
  HLOCAL v9; // [rsp+50h] [rbp-28h]
  __int128 v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+68h] [rbp-10h]
  HLOCAL Buffer; // [rsp+88h] [rbp+10h] BYREF

  Buffer = a2;
  LastError = GetLastError();
  Buffer = 0;
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError - 12000 <= 0xC1 )
    {
      Library = LoadLibraryExA("winhttp.dll", 0, 2u);
      if ( Library )
      {
        FormatMessageW(0x900u, Library, v4, 0x400u, (LPWSTR)&Buffer, 0, 0);
        FreeLibrary(Library);
      }
    }
  }
  else
  {
    v4 = -2147418113;
  }
  v6 = a1;
  v7 = v4;
  v8 = 2;
  v9 = Buffer;
  v11 = 0;
  v10 = 0;
  I_CertDiagControl(11, &v6, 0);
  if ( Buffer )
    LocalFree(Buffer);
  SetLastError(v4);
}

```

## disassembly

```asm
0x180019220  mov     [rsp+arg_0], rbx
0x180019225  mov     [rsp+arg_10], rsi
0x18001922a  mov     [rsp+Buffer], rdx
0x18001922f  push    rdi
0x180019230  sub     rsp, 70h
0x180019234  mov     rsi, rcx
0x180019237  call    cs:__imp_GetLastError
0x18001923d  mov     [rsp+78h+Buffer], 0
0x180019249  mov     ebx, eax
0x18001924b  test    eax, eax
0x18001924d  jz      loc_180019327
0x180019253  add     eax, 0FFFFD120h
0x180019258  cmp     eax, 0C1h
0x18001925d  ja      short loc_1800192B8
0x18001925f  xor     edx, edx; hFile
0x180019261  lea     rcx, LibFileName; "winhttp.dll"
0x180019268  lea     r8d, [rdx+2]; dwFlags
0x18001926c  call    cs:__imp_LoadLibraryExA
0x180019272  mov     rdi, rax
0x180019275  test    rax, rax
0x180019278  jz      short loc_1800192B8
0x18001927a  mov     [rsp+78h+Arguments], 0; Arguments
0x180019283  lea     rax, [rsp+78h+Buffer]
0x18001928b  mov     [rsp+78h+nSize], 0; nSize
0x180019293  mov     r9d, 400h; dwLanguageId
0x180019299  mov     r8d, ebx; dwMessageId
0x18001929c  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x1800192a1  mov     rdx, rdi; lpSource
0x1800192a4  mov     ecx, 900h; dwFlags
0x1800192a9  call    cs:__imp_FormatMessageW
0x1800192af  mov     rcx, rdi; hLibModule
0x1800192b2  call    cs:__imp_FreeLibrary
0x1800192b8  mov     rax, [rsp+78h+Buffer]
0x1800192c0  lea     rdx, [rsp+78h+var_38]
0x1800192c5  xor     r8d, r8d
0x1800192c8  mov     [rsp+78h+var_38], rsi
0x1800192cd  xorps   xmm0, xmm0
0x1800192d0  mov     [rsp+78h+var_30], ebx
0x1800192d4  mov     [rsp+78h+var_2C], 2
0x1800192dc  mov     [rsp+78h+var_28], rax
0x1800192e1  lea     ecx, [r8+0Bh]
0x1800192e5  mov     [rsp+78h+var_10], 0
0x1800192ee  movdqu  [rsp+78h+var_20], xmm0
0x1800192f4  call    cs:__imp_I_CertDiagControl
0x1800192fa  mov     rcx, [rsp+78h+Buffer]; hMem
0x180019302  test    rcx, rcx
0x180019305  jz      short loc_18001930D
0x180019307  call    cs:__imp_LocalFree
0x18001930d  mov     ecx, ebx; dwErrCode
0x18001930f  call    cs:__imp_SetLastError
0x180019315  lea     r11, [rsp+78h+var_8]
0x18001931a  mov     rbx, [r11+10h]
0x18001931e  mov     rsi, [r11+20h]
0x180019322  mov     rsp, r11
0x180019325  pop     rdi
0x180019326  retn
0x180019327  mov     ebx, 8000FFFFh
0x18001932c  jmp     short loc_1800192B8
```
