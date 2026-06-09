# SendMapiMessage(MapiMessageW *)

- ea: `0x180067b1c`
- end: `0x180067bf3`
- name: `?SendMapiMessage@@YAJPEAUMapiMessageW@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct MapiMessageW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800679b0`

## callees

- `0x1800098dc`
- `0x180067b1c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067bdb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067bdb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067b5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067b5c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180067b35`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180067b35`

## string_xrefs

- `0x180067b2e`: `mapi32.dll`

## pseudocode

```c
__int64 __fastcall SendMapiMessage(struct MapiMessageW *a1)
{
  HMODULE LibraryW; // rdi
  int Error; // ebx
  FARPROC ProcAddress; // rax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax

  LibraryW = LoadLibraryW(L"mapi32.dll");
  if ( LibraryW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    ProcAddress = GetProcAddress(LibraryW, "MAPISendMailW");
    if ( !ProcAddress )
    {
      Error = ResultFromKnownLastError();
      goto LABEL_21;
    }
    Error = 1;
    v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct MapiMessageW *, __int64, _DWORD))ProcAddress)(0, 0, a1, 73, 0);
    if ( v5 > 0xA )
    {
      v9 = v5 - 14;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 3;
          if ( !v11 )
            goto LABEL_11;
          v12 = v11 - 3;
          if ( v12 && v12 != 4 )
            goto LABEL_21;
        }
      }
      Error = -2147024809;
      goto LABEL_21;
    }
    if ( v5 != 10 )
    {
      if ( !v5 )
      {
        Error = 0;
        goto LABEL_21;
      }
      v6 = v5 - 1;
      if ( !v6 )
        goto LABEL_21;
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 == 2 )
LABEL_11:
            Error = -2147024882;
LABEL_21:
          FreeLibrary(LibraryW);
          return (unsigned int)Error;
        }
      }
    }
    Error = -2147467259;
    goto LABEL_21;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180067b1c  mov     [rsp+arg_0], rbx
0x180067b21  mov     [rsp+arg_8], rsi
0x180067b26  push    rdi
0x180067b27  sub     rsp, 30h
0x180067b2b  mov     rsi, rcx
0x180067b2e  lea     rcx, aMapi32Dll; "mapi32.dll"
0x180067b35  call    cs:__imp_LoadLibraryW
0x180067b3b  mov     rdi, rax
0x180067b3e  test    rax, rax
0x180067b41  jnz     short loc_180067B52
0x180067b43  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067b48  mov     ebx, eax
0x180067b4a  test    eax, eax
0x180067b4c  js      loc_180067BE1
0x180067b52  lea     rdx, aMapisendmailw; "MAPISendMailW"
0x180067b59  mov     rcx, rdi; hModule
0x180067b5c  call    cs:__imp_GetProcAddress
0x180067b62  test    rax, rax
0x180067b65  jz      short loc_180067BD1
0x180067b67  mov     ebx, 1
0x180067b6c  mov     [rsp+38h+var_18], 0
0x180067b74  mov     r8, rsi
0x180067b77  xor     edx, edx
0x180067b79  xor     ecx, ecx
0x180067b7b  lea     r9d, [rbx+48h]
0x180067b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b84  cmp     eax, 0Ah
0x180067b87  ja      short loc_180067BB2
0x180067b89  jz      short loc_180067BAB
0x180067b8b  test    eax, eax
0x180067b8d  jz      short loc_180067BA7
0x180067b8f  sub     eax, ebx
0x180067b91  jz      short loc_180067BD8
0x180067b93  sub     eax, ebx
0x180067b95  jz      short loc_180067BAB
0x180067b97  sub     eax, ebx
0x180067b99  jz      short loc_180067BAB
0x180067b9b  cmp     eax, 2
0x180067b9e  jnz     short loc_180067BD8
0x180067ba0  mov     ebx, 8007000Eh
0x180067ba5  jmp     short loc_180067BD8
0x180067ba7  xor     ebx, ebx
0x180067ba9  jmp     short loc_180067BD8
0x180067bab  mov     ebx, 80004005h
0x180067bb0  jmp     short loc_180067BD8
0x180067bb2  sub     eax, 0Eh
0x180067bb5  jz      short loc_180067BCA
0x180067bb7  sub     eax, ebx
0x180067bb9  jz      short loc_180067BCA
0x180067bbb  sub     eax, 3
0x180067bbe  jz      short loc_180067BA0
0x180067bc0  sub     eax, 3
0x180067bc3  jz      short loc_180067BCA
0x180067bc5  cmp     eax, 4
0x180067bc8  jnz     short loc_180067BD8
0x180067bca  mov     ebx, 80070057h
0x180067bcf  jmp     short loc_180067BD8
0x180067bd1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067bd6  mov     ebx, eax
0x180067bd8  mov     rcx, rdi; hLibModule
0x180067bdb  call    cs:__imp_FreeLibrary
0x180067be1  mov     rsi, [rsp+38h+arg_8]
0x180067be6  mov     eax, ebx
0x180067be8  mov     rbx, [rsp+38h+arg_0]
0x180067bed  add     rsp, 30h
0x180067bf1  pop     rdi
0x180067bf2  retn
```
