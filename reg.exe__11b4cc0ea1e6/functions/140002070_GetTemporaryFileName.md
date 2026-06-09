# GetTemporaryFileName

- ea: `0x140002070`
- end: `0x14000222d`
- name: `GetTemporaryFileName`
- size: `445`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140004708`
- `0x1400096a8`

## callees

- `0x140002070`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000d7a8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000216b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000216b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000212f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000217a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000212f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000217a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002215`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002215`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140002158`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1400021c7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140002158`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1400021c7`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020aa`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020eb`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020aa`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400020eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002183`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002183`

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
0x140002070  mov     [rsp-28h+arg_0], rbx
0x140002075  push    rbp
0x140002076  push    rsi
0x140002077  push    rdi
0x140002078  push    r14
0x14000207a  push    r15
0x14000207c  mov     rbp, rsp
0x14000207f  sub     rsp, 20h
0x140002083  mov     r15, rcx
0x140002086  mov     edi, 20Ah
0x14000208b  mov     ecx, edi; dwBytes
0x14000208d  call    AllocateMemory
0x140002092  mov     [rbp+arg_8], rax
0x140002096  mov     rbx, rax
0x140002099  test    rax, rax
0x14000209c  jz      loc_14000212A
0x1400020a2  mov     rdx, rax
0x1400020a5  mov     ecx, 104h
0x1400020aa  call    cs:__imp_GetTempPath2W
0x1400020b0  test    eax, eax
0x1400020b2  jz      loc_140002227
0x1400020b8  mov     r14d, 104h
0x1400020be  cmp     eax, r14d
0x1400020c1  jb      short loc_14000210E
0x1400020c3  lea     r14d, [rax+2]
0x1400020c7  lea     edx, ds:2[r14*2]
0x1400020cf  lea     rcx, [rbp+arg_8]
0x1400020d3  call    ReallocateMemory
0x1400020d8  test    eax, eax
0x1400020da  jz      short loc_140002121
0x1400020dc  mov     rbx, [rbp+arg_8]
0x1400020e0  test    rbx, rbx
0x1400020e3  jz      short loc_14000212A
0x1400020e5  mov     rdx, rbx
0x1400020e8  mov     ecx, r14d
0x1400020eb  call    cs:__imp_GetTempPath2W
0x1400020f1  test    eax, eax
0x1400020f3  jz      loc_140002227
0x1400020f9  cmp     eax, r14d
0x1400020fc  jb      short loc_14000210E
0x1400020fe  lea     rcx, [rbp+arg_8]
0x140002102  call    FreeMemory
0x140002107  mov     ecx, 800300FDh
0x14000210c  jmp     short loc_14000212F
0x14000210e  mov     ecx, edi; dwBytes
0x140002110  call    AllocateMemory
0x140002115  mov     [rbp+arg_10], rax
0x140002119  mov     rsi, rax
0x14000211c  test    rax, rax
0x14000211f  jnz     short loc_140002148
0x140002121  lea     rcx, [rbp+arg_8]
0x140002125  call    FreeMemory
0x14000212a  mov     ecx, 0Eh; dwErrCode
0x14000212f  call    cs:__imp_SetLastError
0x140002135  xor     eax, eax
0x140002137  mov     rbx, [rsp+20h+arg_0]
0x14000213c  add     rsp, 20h
0x140002140  pop     r15
0x140002142  pop     r14
0x140002144  pop     rdi
0x140002145  pop     rsi
0x140002146  pop     rbp
0x140002147  retn
0x140002148  mov     r9, rsi; lpTempFileName
0x14000214b  lea     rdx, PrefixString; "REG"
0x140002152  xor     r8d, r8d; uUnique
0x140002155  mov     rcx, rbx; lpPathName
0x140002158  call    cs:__imp_GetTempFileNameW
0x14000215e  test    eax, eax
0x140002160  jnz     loc_140002209
0x140002166  test    r15, r15
0x140002169  jz      short loc_1400021D1
0x14000216b  call    cs:__imp_GetLastError
0x140002171  mov     ecx, 5; dwErrCode
0x140002176  cmp     eax, ecx
0x140002178  jnz     short loc_1400021D1
0x14000217a  call    cs:__imp_SetLastError
0x140002180  mov     rcx, r15; lpString
0x140002183  call    cs:__imp_lstrlenW
0x140002189  lea     edi, [rax-1]
0x14000218c  test    edi, edi
0x14000218e  js      short loc_14000219D
0x140002190  cmp     word ptr [r15+rdi*2], 5Ch ; '\'
0x140002196  jz      short loc_1400021E8
0x140002198  sub     edi, 1
0x14000219b  jns     short loc_140002190
0x14000219d  cmp     edi, 0FFFFFFFFh
0x1400021a0  jnz     short loc_1400021B7
0x1400021a2  mov     r8d, 104h
0x1400021a8  lea     rdx, asc_1400109B8; "."
0x1400021af  mov     rcx, rbx
0x1400021b2  call    StringCopyW
0x1400021b7  mov     r9, rsi; lpTempFileName
0x1400021ba  lea     rdx, PrefixString; "REG"
0x1400021c1  xor     r8d, r8d; uUnique
0x1400021c4  mov     rcx, rbx; lpPathName
0x1400021c7  call    cs:__imp_GetTempFileNameW
0x1400021cd  test    eax, eax
0x1400021cf  jnz     short loc_140002209
0x1400021d1  lea     rcx, [rbp+arg_8]
0x1400021d5  call    FreeMemory
0x1400021da  lea     rcx, [rbp+arg_10]
0x1400021de  call    FreeMemory
0x1400021e3  jmp     loc_140002135
0x1400021e8  cmp     edi, r14d
0x1400021eb  jl      short loc_140002201
0x1400021ed  lea     edx, [rdi+6]
0x1400021f0  lea     rcx, [rbp+arg_8]
0x1400021f4  call    ReallocateMemory
0x1400021f9  test    eax, eax
0x1400021fb  jz      short loc_1400021D1
0x1400021fd  mov     rbx, [rbp+arg_8]
0x140002201  mov     r8d, edi
0x140002204  mov     rdx, r15
0x140002207  jmp     short loc_1400021AF
0x140002209  lea     rcx, [rbp+arg_8]
0x14000220d  call    FreeMemory
0x140002212  mov     rcx, rsi; lpFileName
0x140002215  call    cs:__imp_DeleteFileW
0x14000221b  test    eax, eax
0x14000221d  jz      short loc_140002227
0x14000221f  mov     rax, rsi
0x140002222  jmp     loc_140002137
0x140002227  lea     rcx, [rbp+arg_8]
0x14000222b  jmp     short loc_1400021DE
```
