# TS_SECURITY_FIPS_Init

- ea: `0x1800c57f0`
- end: `0x1800c599b`
- name: `TS_SECURITY_FIPS_Init`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006f490`

## callees

- `0x1800c4fcc`
- `0x1800c57f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c582f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c584c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5869`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5886`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5917`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5949`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c597b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c582f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c584c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5869`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5886`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c58fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5917`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5949`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c5962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c597b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c5813`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c5813`

## string_xrefs

- `0x1800c580c`: `advapi32.dll`
- `0x1800c5910`: `CryptCreateHash`

## pseudocode

```c
__int64 __fastcall TS_SECURITY_FIPS_Init(__int64 a1)
{
  unsigned int v2; // edi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax

  v2 = 0;
  if ( (unsigned int)Is_WinXP_or_Later() )
  {
    LibraryW = LoadLibraryW(L"advapi32.dll");
    *(_QWORD *)a1 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "CryptAcquireContextW");
      *(_QWORD *)(a1 + 8) = ProcAddress;
      if ( ProcAddress )
      {
        v5 = GetProcAddress(*(HMODULE *)a1, "CryptReleaseContext");
        *(_QWORD *)(a1 + 16) = v5;
        if ( v5 )
        {
          v6 = GetProcAddress(*(HMODULE *)a1, "CryptGenRandom");
          *(_QWORD *)(a1 + 24) = v6;
          if ( v6 )
          {
            v7 = GetProcAddress(*(HMODULE *)a1, "CryptEncrypt");
            *(_QWORD *)(a1 + 32) = v7;
            if ( v7 )
            {
              v8 = GetProcAddress(*(HMODULE *)a1, "CryptDecrypt");
              *(_QWORD *)(a1 + 40) = v8;
              if ( v8 )
              {
                v9 = GetProcAddress(*(HMODULE *)a1, "CryptImportKey");
                *(_QWORD *)(a1 + 48) = v9;
                if ( v9 )
                {
                  v10 = GetProcAddress(*(HMODULE *)a1, "CryptSetKeyParam");
                  *(_QWORD *)(a1 + 64) = v10;
                  if ( v10 )
                  {
                    v11 = GetProcAddress(*(HMODULE *)a1, "CryptDestroyKey");
                    *(_QWORD *)(a1 + 56) = v11;
                    if ( v11 )
                    {
                      v12 = GetProcAddress(*(HMODULE *)a1, "CryptCreateHash");
                      *(_QWORD *)(a1 + 72) = v12;
                      if ( v12 )
                      {
                        v13 = GetProcAddress(*(HMODULE *)a1, "CryptHashData");
                        *(_QWORD *)(a1 + 80) = v13;
                        if ( v13 )
                        {
                          v14 = GetProcAddress(*(HMODULE *)a1, "CryptSetHashParam");
                          *(_QWORD *)(a1 + 88) = v14;
                          if ( v14 )
                          {
                            v15 = GetProcAddress(*(HMODULE *)a1, "CryptGetHashParam");
                            *(_QWORD *)(a1 + 96) = v15;
                            if ( v15 )
                            {
                              v16 = GetProcAddress(*(HMODULE *)a1, "CryptDestroyHash");
                              *(_QWORD *)(a1 + 104) = v16;
                              return v16 != 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800c57f0  mov     [rsp+arg_0], rbx
0x1800c57f5  push    rdi
0x1800c57f6  sub     rsp, 20h
0x1800c57fa  mov     rbx, rcx
0x1800c57fd  xor     edi, edi
0x1800c57ff  call    ?Is_WinXP_or_Later@@YAHXZ; Is_WinXP_or_Later(void)
0x1800c5804  test    eax, eax
0x1800c5806  jz      loc_1800C598E
0x1800c580c  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800c5813  call    cs:__imp_LoadLibraryW
0x1800c5819  mov     [rbx], rax
0x1800c581c  test    rax, rax
0x1800c581f  jz      loc_1800C598E
0x1800c5825  lea     rdx, aCryptacquireco_0; "CryptAcquireContextW"
0x1800c582c  mov     rcx, rax; hModule
0x1800c582f  call    cs:__imp_GetProcAddress
0x1800c5835  mov     [rbx+8], rax
0x1800c5839  test    rax, rax
0x1800c583c  jz      loc_1800C598E
0x1800c5842  mov     rcx, [rbx]; hModule
0x1800c5845  lea     rdx, aCryptreleaseco_0; "CryptReleaseContext"
0x1800c584c  call    cs:__imp_GetProcAddress
0x1800c5852  mov     [rbx+10h], rax
0x1800c5856  test    rax, rax
0x1800c5859  jz      loc_1800C598E
0x1800c585f  mov     rcx, [rbx]; hModule
0x1800c5862  lea     rdx, aCryptgenrandom_0; "CryptGenRandom"
0x1800c5869  call    cs:__imp_GetProcAddress
0x1800c586f  mov     [rbx+18h], rax
0x1800c5873  test    rax, rax
0x1800c5876  jz      loc_1800C598E
0x1800c587c  mov     rcx, [rbx]; hModule
0x1800c587f  lea     rdx, aCryptencrypt; "CryptEncrypt"
0x1800c5886  call    cs:__imp_GetProcAddress
0x1800c588c  mov     [rbx+20h], rax
0x1800c5890  test    rax, rax
0x1800c5893  jz      loc_1800C598E
0x1800c5899  mov     rcx, [rbx]; hModule
0x1800c589c  lea     rdx, aCryptdecrypt_0; "CryptDecrypt"
0x1800c58a3  call    cs:__imp_GetProcAddress
0x1800c58a9  mov     [rbx+28h], rax
0x1800c58ad  test    rax, rax
0x1800c58b0  jz      loc_1800C598E
0x1800c58b6  mov     rcx, [rbx]; hModule
0x1800c58b9  lea     rdx, aCryptimportkey; "CryptImportKey"
0x1800c58c0  call    cs:__imp_GetProcAddress
0x1800c58c6  mov     [rbx+30h], rax
0x1800c58ca  test    rax, rax
0x1800c58cd  jz      loc_1800C598E
0x1800c58d3  mov     rcx, [rbx]; hModule
0x1800c58d6  lea     rdx, aCryptsetkeypar; "CryptSetKeyParam"
0x1800c58dd  call    cs:__imp_GetProcAddress
0x1800c58e3  mov     [rbx+40h], rax
0x1800c58e7  test    rax, rax
0x1800c58ea  jz      loc_1800C598E
0x1800c58f0  mov     rcx, [rbx]; hModule
0x1800c58f3  lea     rdx, aCryptdestroyke_0; "CryptDestroyKey"
0x1800c58fa  call    cs:__imp_GetProcAddress
0x1800c5900  mov     [rbx+38h], rax
0x1800c5904  test    rax, rax
0x1800c5907  jz      loc_1800C598E
0x1800c590d  mov     rcx, [rbx]; hModule
0x1800c5910  lea     rdx, aCryptcreatehas_1; "CryptCreateHash"
0x1800c5917  call    cs:__imp_GetProcAddress
0x1800c591d  mov     [rbx+48h], rax
0x1800c5921  test    rax, rax
0x1800c5924  jz      short loc_1800C598E
0x1800c5926  mov     rcx, [rbx]; hModule
0x1800c5929  lea     rdx, aCrypthashdata_0; "CryptHashData"
0x1800c5930  call    cs:__imp_GetProcAddress
0x1800c5936  mov     [rbx+50h], rax
0x1800c593a  test    rax, rax
0x1800c593d  jz      short loc_1800C598E
0x1800c593f  mov     rcx, [rbx]; hModule
0x1800c5942  lea     rdx, aCryptsethashpa; "CryptSetHashParam"
0x1800c5949  call    cs:__imp_GetProcAddress
0x1800c594f  mov     [rbx+58h], rax
0x1800c5953  test    rax, rax
0x1800c5956  jz      short loc_1800C598E
0x1800c5958  mov     rcx, [rbx]; hModule
0x1800c595b  lea     rdx, aCryptgethashpa_0; "CryptGetHashParam"
0x1800c5962  call    cs:__imp_GetProcAddress
0x1800c5968  mov     [rbx+60h], rax
0x1800c596c  test    rax, rax
0x1800c596f  jz      short loc_1800C598E
0x1800c5971  mov     rcx, [rbx]; hModule
0x1800c5974  lea     rdx, aCryptdestroyha_0; "CryptDestroyHash"
0x1800c597b  call    cs:__imp_GetProcAddress
0x1800c5981  test    rax, rax
0x1800c5984  mov     [rbx+68h], rax
0x1800c5988  lea     ecx, [rdi+1]
0x1800c598b  cmovnz  edi, ecx
0x1800c598e  mov     rbx, [rsp+28h+arg_0]
0x1800c5993  mov     eax, edi
0x1800c5995  add     rsp, 20h
0x1800c5999  pop     rdi
0x1800c599a  retn
```
