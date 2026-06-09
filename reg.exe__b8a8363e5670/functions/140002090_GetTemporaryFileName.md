# GetTemporaryFileName

- ea: `0x140002090`
- end: `0x140002284`
- name: `GetTemporaryFileName`
- size: `500`
- prototype: `WCHAR *__fastcall(WCHAR *lpString)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000496c`
- `0x140009c68`

## callees

- `0x140002090`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000e268`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400021a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400021a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000215b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400021b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000215b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400021b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002266`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002266`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x14000218b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140002212`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x14000218b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140002212`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020ca`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140002111`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020ca`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140002111`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400021c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400021c8`

## pseudocode

```c
WCHAR *__fastcall GetTemporaryFileName(WCHAR *lpString)
{
  WCHAR *Memory; // rax
  WCHAR *v3; // rbx
  unsigned int TempPath2W; // eax
  unsigned int v5; // r14d
  unsigned int v6; // eax
  DWORD v7; // ecx
  WCHAR *v8; // rax
  WCHAR *v9; // rsi
  __int64 v11; // rdi
  __int64 v12; // r8
  wchar_t *v13; // rdx
  WCHAR **v14; // rcx
  WCHAR *v15; // [rsp+58h] [rbp+38h] BYREF
  WCHAR *v16; // [rsp+60h] [rbp+40h] BYREF

  Memory = (WCHAR *)AllocateMemory(0x20Au);
  v15 = Memory;
  v3 = Memory;
  if ( !Memory )
    goto LABEL_11;
  TempPath2W = GetTempPath2W(260, Memory);
  if ( !TempPath2W )
    goto LABEL_32;
  v5 = 260;
  if ( TempPath2W >= 0x104 )
  {
    v5 = TempPath2W + 2;
    if ( !(unsigned int)ReallocateMemory(&v15, 2 * (TempPath2W + 2) + 2) )
    {
LABEL_10:
      FreeMemory(&v15);
      goto LABEL_11;
    }
    v3 = v15;
    if ( !v15 )
    {
LABEL_11:
      v7 = 14;
      goto LABEL_12;
    }
    v6 = GetTempPath2W(v5, v15);
    if ( !v6 )
      goto LABEL_32;
    if ( v6 >= v5 )
    {
      FreeMemory(&v15);
      v7 = -2147286787;
LABEL_12:
      SetLastError(v7);
      return 0;
    }
  }
  v8 = (WCHAR *)AllocateMemory(0x20Au);
  v16 = v8;
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  if ( GetTempFileNameW(v3, L"REG", 0, v8) )
    goto LABEL_30;
  if ( !lpString || GetLastError() != 5 )
    goto LABEL_24;
  SetLastError(5u);
  v11 = (unsigned int)(lstrlenW(lpString) - 1);
  if ( (int)v11 < 0 )
  {
LABEL_20:
    if ( (_DWORD)v11 != -1 )
      goto LABEL_23;
    v12 = 260;
    v13 = L".";
  }
  else
  {
    while ( lpString[v11] != 92 )
    {
      v11 = (unsigned int)(v11 - 1);
      if ( (int)v11 < 0 )
        goto LABEL_20;
    }
    if ( (int)v11 >= (int)v5 )
    {
      if ( !(unsigned int)ReallocateMemory(&v15, (unsigned int)(v11 + 6)) )
        goto LABEL_24;
      v3 = v15;
    }
    v12 = (unsigned int)v11;
    v13 = lpString;
  }
  StringCopyW(v3, v13, v12);
LABEL_23:
  if ( !GetTempFileNameW(v3, L"REG", 0, v9) )
  {
LABEL_24:
    FreeMemory(&v15);
    v14 = &v16;
LABEL_25:
    FreeMemory(v14);
    return 0;
  }
LABEL_30:
  FreeMemory(&v15);
  if ( !DeleteFileW(v9) )
  {
LABEL_32:
    v14 = &v15;
    goto LABEL_25;
  }
  return v9;
}

```

## disassembly

```asm
0x140002090  mov     [rsp-28h+arg_0], rbx
0x140002095  push    rbp
0x140002096  push    rsi
0x140002097  push    rdi
0x140002098  push    r14
0x14000209a  push    r15
0x14000209c  mov     rbp, rsp
0x14000209f  sub     rsp, 20h
0x1400020a3  mov     r15, rcx
0x1400020a6  mov     edi, 20Ah
0x1400020ab  mov     ecx, edi; dwBytes
0x1400020ad  call    AllocateMemory
0x1400020b2  mov     [rbp+arg_8], rax
0x1400020b6  mov     rbx, rax
0x1400020b9  test    rax, rax
0x1400020bc  jz      loc_140002156
0x1400020c2  mov     rdx, rax
0x1400020c5  mov     ecx, 104h
0x1400020ca  call    cs:__imp_GetTempPath2W
0x1400020d1  nop     dword ptr [rax+rax+00h]
0x1400020d6  test    eax, eax
0x1400020d8  jz      loc_14000227E
0x1400020de  mov     r14d, 104h
0x1400020e4  cmp     eax, r14d
0x1400020e7  jb      short loc_14000213A
0x1400020e9  lea     r14d, [rax+2]
0x1400020ed  lea     edx, ds:2[r14*2]
0x1400020f5  lea     rcx, [rbp+arg_8]
0x1400020f9  call    ReallocateMemory
0x1400020fe  test    eax, eax
0x140002100  jz      short loc_14000214D
0x140002102  mov     rbx, [rbp+arg_8]
0x140002106  test    rbx, rbx
0x140002109  jz      short loc_140002156
0x14000210b  mov     rdx, rbx
0x14000210e  mov     ecx, r14d
0x140002111  call    cs:__imp_GetTempPath2W
0x140002118  nop     dword ptr [rax+rax+00h]
0x14000211d  test    eax, eax
0x14000211f  jz      loc_14000227E
0x140002125  cmp     eax, r14d
0x140002128  jb      short loc_14000213A
0x14000212a  lea     rcx, [rbp+arg_8]
0x14000212e  call    FreeMemory
0x140002133  mov     ecx, 800300FDh
0x140002138  jmp     short loc_14000215B
0x14000213a  mov     ecx, edi; dwBytes
0x14000213c  call    AllocateMemory
0x140002141  mov     [rbp+arg_10], rax
0x140002145  mov     rsi, rax
0x140002148  test    rax, rax
0x14000214b  jnz     short loc_14000217B
0x14000214d  lea     rcx, [rbp+arg_8]
0x140002151  call    FreeMemory
0x140002156  mov     ecx, 0Eh; dwErrCode
0x14000215b  call    cs:__imp_SetLastError
0x140002162  nop     dword ptr [rax+rax+00h]
0x140002167  xor     eax, eax
0x140002169  mov     rbx, [rsp+20h+arg_0]
0x14000216e  add     rsp, 20h
0x140002172  pop     r15
0x140002174  pop     r14
0x140002176  pop     rdi
0x140002177  pop     rsi
0x140002178  pop     rbp
0x140002179  retn
0x14000217b  mov     r9, rsi; lpTempFileName
0x14000217e  lea     rdx, PrefixString; "REG"
0x140002185  xor     r8d, r8d; uUnique
0x140002188  mov     rcx, rbx; lpPathName
0x14000218b  call    cs:__imp_GetTempFileNameW
0x140002192  nop     dword ptr [rax+rax+00h]
0x140002197  test    eax, eax
0x140002199  jnz     loc_14000225A
0x14000219f  test    r15, r15
0x1400021a2  jz      short loc_140002222
0x1400021a4  call    cs:__imp_GetLastError
0x1400021ab  nop     dword ptr [rax+rax+00h]
0x1400021b0  mov     ecx, 5; dwErrCode
0x1400021b5  cmp     eax, ecx
0x1400021b7  jnz     short loc_140002222
0x1400021b9  call    cs:__imp_SetLastError
0x1400021c0  nop     dword ptr [rax+rax+00h]
0x1400021c5  mov     rcx, r15; lpString
0x1400021c8  call    cs:__imp_lstrlenW
0x1400021cf  nop     dword ptr [rax+rax+00h]
0x1400021d4  lea     edi, [rax-1]
0x1400021d7  test    edi, edi
0x1400021d9  js      short loc_1400021E8
0x1400021db  cmp     word ptr [r15+rdi*2], 5Ch ; '\'
0x1400021e1  jz      short loc_140002239
0x1400021e3  sub     edi, 1
0x1400021e6  jns     short loc_1400021DB
0x1400021e8  cmp     edi, 0FFFFFFFFh
0x1400021eb  jnz     short loc_140002202
0x1400021ed  mov     r8d, 104h
0x1400021f3  lea     rdx, asc_1400119B8; "."
0x1400021fa  mov     rcx, rbx
0x1400021fd  call    StringCopyW
0x140002202  mov     r9, rsi; lpTempFileName
0x140002205  lea     rdx, PrefixString; "REG"
0x14000220c  xor     r8d, r8d; uUnique
0x14000220f  mov     rcx, rbx; lpPathName
0x140002212  call    cs:__imp_GetTempFileNameW
0x140002219  nop     dword ptr [rax+rax+00h]
0x14000221e  test    eax, eax
0x140002220  jnz     short loc_14000225A
0x140002222  lea     rcx, [rbp+arg_8]
0x140002226  call    FreeMemory
0x14000222b  lea     rcx, [rbp+arg_10]
0x14000222f  call    FreeMemory
0x140002234  jmp     loc_140002167
0x140002239  cmp     edi, r14d
0x14000223c  jl      short loc_140002252
0x14000223e  lea     edx, [rdi+6]
0x140002241  lea     rcx, [rbp+arg_8]
0x140002245  call    ReallocateMemory
0x14000224a  test    eax, eax
0x14000224c  jz      short loc_140002222
0x14000224e  mov     rbx, [rbp+arg_8]
0x140002252  mov     r8d, edi
0x140002255  mov     rdx, r15
0x140002258  jmp     short loc_1400021FA
0x14000225a  lea     rcx, [rbp+arg_8]
0x14000225e  call    FreeMemory
0x140002263  mov     rcx, rsi; lpFileName
0x140002266  call    cs:__imp_DeleteFileW
0x14000226d  nop     dword ptr [rax+rax+00h]
0x140002272  test    eax, eax
0x140002274  jz      short loc_14000227E
0x140002276  mov     rax, rsi
0x140002279  jmp     loc_140002169
0x14000227e  lea     rcx, [rbp+arg_8]
0x140002282  jmp     short loc_14000222F
```
