# GetServerNameFromPath(ushort const *,ulong,ushort *,ushort const * *)

- ea: `0x180008450`
- end: `0x1800085cf`
- name: `?GetServerNameFromPath@@YAJPEBGKPEAGPEAPEBG@Z`
- size: `383`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b740`

## callees

- `0x180008450`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800084e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800084e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008514`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008514`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008522`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008544`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008522`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ef`

## string_xrefs

- `0x1800084d8`: `MPR.DLL`

## pseudocode

```c
signed int __fastcall GetServerNameFromPath(
        const unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 *v6; // rbx
  bool v7; // zf
  unsigned int v8; // r10d
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  HMODULE Library; // rax
  HMODULE v14; // rdi
  signed int result; // eax
  FARPROC ProcAddress; // rax
  int v17; // ebx
  const unsigned __int16 *v18; // r8
  unsigned int v19; // r9d
  unsigned __int16 *i; // rdx
  int v21; // [rsp+58h] [rbp+10h] BYREF

  v21 = a2;
  v6 = a1;
  if ( !a1 )
    return -2147467259;
  v7 = *a1 == 92;
  v8 = 522;
  v21 = 522;
  if ( v7 && a1[1] == 92 )
  {
    v9 = 2147483646;
    v10 = 261;
    v11 = a3;
    do
    {
      if ( !v9 )
        break;
      if ( !*v6 )
        break;
      *v11++ = *v6++;
      --v9;
      --v10;
    }
    while ( v10 );
    v12 = v11 - 1;
    if ( v10 )
      v12 = v11;
    *v12 = 0;
LABEL_18:
    v18 = a3 + 2;
    v19 = 4;
    for ( i = a3 + 2; (unsigned __int64)v19 + 2 <= v8 && *i; ++i )
    {
      if ( *i == 92 )
      {
        *i = 0;
        goto LABEL_26;
      }
      v19 += 2;
    }
    goto LABEL_26;
  }
  Library = LoadLibraryExW(L"MPR.DLL", 0, 0);
  v14 = Library;
  if ( !Library )
    goto LABEL_12;
  ProcAddress = GetProcAddress(Library, "WNetGetUniversalNameW");
  if ( !ProcAddress )
  {
    FreeLibrary(v14);
LABEL_12:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v17 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, unsigned __int16 *, int *))ProcAddress)(
          v6,
          1,
          a3,
          &v21);
  FreeLibrary(v14);
  if ( !v17 )
  {
    v8 = v21;
    if ( (unsigned int)(v21 - 7) <= 0x203 )
      goto LABEL_18;
    return -2147467259;
  }
  if ( v17 == 2250 )
  {
    v18 = 0;
LABEL_26:
    *a4 = v18;
    return 0;
  }
  if ( v17 > 0 )
    return (unsigned __int16)v17 | 0x80070000;
  return v17;
}

```

## disassembly

```asm
0x180008450  mov     rax, rsp
0x180008453  mov     [rax+8], rbx
0x180008457  mov     [rax+18h], rbp
0x18000845b  mov     [rax+10h], edx
0x18000845e  push    rsi
0x18000845f  push    rdi
0x180008460  push    r14
0x180008462  sub     rsp, 30h
0x180008466  xor     ebp, ebp
0x180008468  mov     r14, r9
0x18000846b  mov     rsi, r8
0x18000846e  mov     rbx, rcx
0x180008471  test    rcx, rcx
0x180008474  jz      loc_1800085B7
0x18000847a  cmp     word ptr [rcx], 5Ch ; '\'
0x18000847e  mov     r10d, 20Ah
0x180008484  mov     [rax+10h], r10d
0x180008488  jnz     short loc_1800084D5
0x18000848a  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000848f  jnz     short loc_1800084D5
0x180008491  mov     ecx, 7FFFFFFEh
0x180008496  mov     edx, 105h
0x18000849b  mov     rax, r8
0x18000849e  test    rcx, rcx
0x1800084a1  jz      short loc_1800084C2
0x1800084a3  movzx   r8d, word ptr [rbx]
0x1800084a7  test    r8w, r8w
0x1800084ab  jz      short loc_1800084C2
0x1800084ad  mov     [rax], r8w
0x1800084b1  add     rbx, 2
0x1800084b5  add     rax, 2
0x1800084b9  dec     rcx
0x1800084bc  sub     rdx, 1
0x1800084c0  jnz     short loc_18000849E
0x1800084c2  test    rdx, rdx
0x1800084c5  lea     rcx, [rax-2]
0x1800084c9  cmovnz  rcx, rax
0x1800084cd  mov     [rcx], bp
0x1800084d0  jmp     loc_18000855E
0x1800084d5  xor     r8d, r8d; dwFlags
0x1800084d8  lea     rcx, LibFileName; "MPR.DLL"
0x1800084df  xor     edx, edx; hFile
0x1800084e1  call    cs:__imp_LoadLibraryExW
0x1800084e7  mov     rdi, rax
0x1800084ea  test    rax, rax
0x1800084ed  jnz     short loc_18000850A
0x1800084ef  call    cs:__imp_GetLastError
0x1800084f5  test    eax, eax
0x1800084f7  jle     loc_1800085BC
0x1800084fd  movzx   eax, ax
0x180008500  or      eax, 80070000h
0x180008505  jmp     loc_1800085BC
0x18000850a  lea     rdx, ProcName; "WNetGetUniversalNameW"
0x180008511  mov     rcx, rdi; hModule
0x180008514  call    cs:__imp_GetProcAddress
0x18000851a  test    rax, rax
0x18000851d  jnz     short loc_18000852A
0x18000851f  mov     rcx, rdi; hLibModule
0x180008522  call    cs:__imp_FreeLibrary
0x180008528  jmp     short loc_1800084EF
0x18000852a  lea     r9, [rsp+48h+arg_8]
0x18000852f  mov     r8, rsi
0x180008532  mov     edx, 1
0x180008537  mov     rcx, rbx
0x18000853a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000853f  mov     rcx, rdi; hLibModule
0x180008542  mov     ebx, eax
0x180008544  call    cs:__imp_FreeLibrary
0x18000854a  test    ebx, ebx
0x18000854c  jnz     short loc_180008594
0x18000854e  mov     r10d, [rsp+48h+arg_8]
0x180008553  lea     eax, [r10-7]
0x180008557  cmp     eax, 203h
0x18000855c  ja      short loc_1800085B7
0x18000855e  lea     r8, [rsi+4]
0x180008562  mov     r9d, 4
0x180008568  mov     rdx, r8
0x18000856b  mov     ecx, r9d
0x18000856e  add     rcx, 2
0x180008572  mov     eax, r10d
0x180008575  cmp     rcx, rax
0x180008578  ja      short loc_18000859F
0x18000857a  cmp     [rdx], bp
0x18000857d  jz      short loc_18000859F
0x18000857f  cmp     word ptr [rdx], 5Ch ; '\'
0x180008583  jz      short loc_18000858F
0x180008585  add     rdx, 2
0x180008589  add     r9d, 2
0x18000858d  jmp     short loc_18000856B
0x18000858f  mov     [rdx], bp
0x180008592  jmp     short loc_18000859F
0x180008594  cmp     ebx, 8CAh
0x18000859a  jnz     short loc_1800085A6
0x18000859c  mov     r8, rbp
0x18000859f  mov     [r14], r8
0x1800085a2  xor     eax, eax
0x1800085a4  jmp     short loc_1800085BC
0x1800085a6  test    ebx, ebx
0x1800085a8  jle     short loc_1800085B3
0x1800085aa  movzx   ebx, bx
0x1800085ad  or      ebx, 80070000h
0x1800085b3  mov     eax, ebx
0x1800085b5  jmp     short loc_1800085BC
0x1800085b7  mov     eax, 80004005h
0x1800085bc  mov     rbx, [rsp+48h+arg_0]
0x1800085c1  mov     rbp, [rsp+48h+arg_10]
0x1800085c6  add     rsp, 30h
0x1800085ca  pop     r14
0x1800085cc  pop     rdi
0x1800085cd  pop     rsi
0x1800085ce  retn
```
