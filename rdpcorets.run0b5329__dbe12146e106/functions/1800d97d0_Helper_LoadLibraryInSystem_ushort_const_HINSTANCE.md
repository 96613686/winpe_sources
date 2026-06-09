# Helper::LoadLibraryInSystem(ushort const *,HINSTANCE__ * *)

- ea: `0x1800d97d0`
- end: `0x1800d9a29`
- name: `?LoadLibraryInSystem@Helper@@SAJPEBGPEAPEAUHINSTANCE__@@@Z`
- size: `601`
- prototype: `signed int __fastcall(const unsigned __int16 *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800e5060`

## callees

- `0x180033da0`
- `0x1800d97d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d982c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d985c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d982c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d985c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d99d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d99d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d983a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d99e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d983a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d99e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d981f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d981f`

## string_xrefs

- `0x1800d984f`: `d3d11.dll`

## pseudocode

```c
signed int __fastcall Helper::LoadLibraryInSystem(const unsigned __int16 *a1, HINSTANCE *a2)
{
  signed int v3; // edi
  size_t v4; // rbp
  signed int LastError; // eax
  const wchar_t *v6; // rsi
  signed int result; // eax
  __int64 v8; // rcx
  WCHAR *v9; // rax
  int v10; // r11d
  __int64 v11; // r9
  const unsigned __int16 *v12; // rcx
  __int64 v13; // r8
  bool v14; // zf
  __int64 v15; // rdx
  WCHAR *v16; // r9
  __int64 v17; // rax
  WCHAR *v18; // rcx
  int v19; // r10d
  __int64 v20; // rcx
  WCHAR *v21; // rax
  __int64 v22; // rbx
  WCHAR *v23; // rdx
  WCHAR *v24; // rcx
  HMODULE Library; // rax
  wchar_t Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( !a2 )
    return -2147467259;
  v3 = 0;
  Buffer[0] = 0;
  GetSystemDirectoryW(Buffer, 0x104u);
  v4 = wcsnlen(Buffer, 0x104u);
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  v6 = L"d3d11.dll";
  if ( v4 + wcsnlen(L"d3d11.dll", 0x104u) + 2 > 0x104 )
    return -2147024774;
  if ( v3 < 0 )
    return v3;
  v8 = 260;
  v9 = Buffer;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = -2147024809;
  if ( v8 )
    v10 = 0;
  v11 = 260 - v8;
  if ( !v8 )
    return v10;
  v12 = L"\\";
  v13 = 2147483646;
  v15 = 260 - v11;
  v14 = v11 == 260;
  v16 = &Buffer[v11];
  v17 = 2147483646;
  if ( !v14 )
  {
    do
    {
      if ( !v17 )
        break;
      if ( !*v12 )
        break;
      *v16++ = *v12++;
      --v17;
      --v15;
    }
    while ( v15 );
  }
  v18 = v16 - 1;
  v19 = -2147024774;
  v10 = -2147024774;
  if ( v15 )
  {
    v18 = v16;
    v10 = 0;
  }
  *v18 = 0;
  if ( !v15 )
    return v10;
  v20 = 260;
  v21 = Buffer;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  if ( !v20 )
    return -2147024809;
  v22 = v20;
  v23 = &Buffer[260 - v20];
  do
  {
    if ( !v13 )
      break;
    if ( !*v6 )
      break;
    *v23++ = *v6++;
    --v13;
    --v22;
  }
  while ( v22 );
  v24 = v23 - 1;
  if ( v22 )
  {
    v24 = v23;
    v19 = 0;
  }
  *v24 = 0;
  if ( !v22 )
    return v19;
  Library = LoadLibraryExW(Buffer, 0, 0x800u);
  *a2 = Library;
  if ( Library )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800d97d0  mov     r11, rsp
0x1800d97d3  push    r14
0x1800d97d5  sub     rsp, 250h
0x1800d97dc  mov     rax, cs:__security_cookie
0x1800d97e3  xor     rax, rsp
0x1800d97e6  mov     [rsp+258h+var_28], rax
0x1800d97ee  mov     r14, rdx
0x1800d97f1  test    rdx, rdx
0x1800d97f4  jz      loc_1800D9A1F
0x1800d97fa  mov     [r11+8], rbx
0x1800d97fe  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800d9803  mov     [r11+18h], rbp
0x1800d9807  xor     eax, eax
0x1800d9809  mov     [r11-10h], rsi
0x1800d980d  mov     ebx, 104h
0x1800d9812  mov     [r11-18h], rdi
0x1800d9816  mov     edx, ebx; uSize
0x1800d9818  xor     edi, edi
0x1800d981a  mov     [rsp+258h+Buffer], ax
0x1800d981f  call    cs:__imp_GetSystemDirectoryW
0x1800d9825  mov     edx, ebx; MaxCount
0x1800d9827  lea     rcx, [rsp+258h+Buffer]; Source
0x1800d982c  call    cs:__imp_wcsnlen
0x1800d9832  mov     rbp, rax
0x1800d9835  test    rax, rax
0x1800d9838  jnz     short loc_1800D984F
0x1800d983a  call    cs:__imp_GetLastError
0x1800d9840  mov     edi, eax
0x1800d9842  test    eax, eax
0x1800d9844  jle     short loc_1800D984F
0x1800d9846  movzx   edi, ax
0x1800d9849  or      edi, 80070000h
0x1800d984f  lea     rsi, aD3d11Dll; "d3d11.dll"
0x1800d9856  mov     rdx, rbx; MaxCount
0x1800d9859  mov     rcx, rsi; Source
0x1800d985c  call    cs:__imp_wcsnlen
0x1800d9862  lea     rcx, [rax+2]
0x1800d9866  add     rcx, rbp
0x1800d9869  mov     rbp, [rsp+258h+arg_10]
0x1800d9871  cmp     rcx, rbx
0x1800d9874  jbe     short loc_1800D98AD
0x1800d9876  mov     eax, 8007007Ah
0x1800d987b  mov     rsi, [rsp+258h+var_10]
0x1800d9883  mov     rbx, [rsp+258h+arg_0]
0x1800d988b  mov     rdi, [rsp+258h+var_18]
0x1800d9893  mov     rcx, [rsp+258h+var_28]
0x1800d989b  xor     rcx, rsp; StackCookie
0x1800d989e  call    __security_check_cookie
0x1800d98a3  add     rsp, 250h
0x1800d98aa  pop     r14
0x1800d98ac  retn
0x1800d98ad  test    edi, edi
0x1800d98af  js      loc_1800D9A18
0x1800d98b5  mov     rcx, rbx
0x1800d98b8  lea     rax, [rsp+258h+Buffer]
0x1800d98bd  nop     dword ptr [rax]
0x1800d98c0  cmp     word ptr [rax], 0
0x1800d98c4  jz      short loc_1800D98D0
0x1800d98c6  add     rax, 2
0x1800d98ca  sub     rcx, 1
0x1800d98ce  jnz     short loc_1800D98C0
0x1800d98d0  xor     eax, eax
0x1800d98d2  mov     edi, 80070057h
0x1800d98d7  test    rcx, rcx
0x1800d98da  mov     r11d, edi
0x1800d98dd  mov     r9, rbx
0x1800d98e0  cmovnz  r11d, eax
0x1800d98e4  sub     r9, rcx
0x1800d98e7  test    rcx, rcx
0x1800d98ea  cmovz   r9, rax
0x1800d98ee  jz      loc_1800D9A10
0x1800d98f4  mov     rdx, rbx
0x1800d98f7  lea     rcx, asc_180158700; "\\"
0x1800d98fe  mov     r8d, 7FFFFFFEh
0x1800d9904  sub     rdx, r9
0x1800d9907  lea     r9, [rsp+r9*2+258h+Buffer]
0x1800d990c  mov     eax, r8d
0x1800d990f  jz      short loc_1800D9935
0x1800d9911  test    rax, rax
0x1800d9914  jz      short loc_1800D9935
0x1800d9916  movzx   r10d, word ptr [rcx]
0x1800d991a  test    r10w, r10w
0x1800d991e  jz      short loc_1800D9935
0x1800d9920  mov     [r9], r10w
0x1800d9924  add     rcx, 2
0x1800d9928  add     r9, 2
0x1800d992c  dec     rax
0x1800d992f  sub     rdx, 1
0x1800d9933  jnz     short loc_1800D9911
0x1800d9935  xor     eax, eax
0x1800d9937  lea     rcx, [r9-2]
0x1800d993b  test    rdx, rdx
0x1800d993e  mov     r10d, 8007007Ah
0x1800d9944  mov     r11d, r10d
0x1800d9947  cmovnz  rcx, r9
0x1800d994b  cmovnz  r11d, eax
0x1800d994f  mov     [rcx], ax
0x1800d9952  jz      loc_1800D9A10
0x1800d9958  mov     rcx, rbx
0x1800d995b  lea     rax, [rsp+258h+Buffer]
0x1800d9960  cmp     word ptr [rax], 0
0x1800d9964  jz      short loc_1800D9970
0x1800d9966  add     rax, 2
0x1800d996a  sub     rcx, 1
0x1800d996e  jnz     short loc_1800D9960
0x1800d9970  xor     eax, eax
0x1800d9972  mov     rdx, rbx
0x1800d9975  test    rcx, rcx
0x1800d9978  cmovnz  edi, eax
0x1800d997b  sub     rdx, rcx
0x1800d997e  test    rcx, rcx
0x1800d9981  cmovz   rdx, rax
0x1800d9985  jz      short loc_1800D9A05
0x1800d9987  sub     rbx, rdx
0x1800d998a  lea     rdx, [rsp+rdx*2+258h+Buffer]
0x1800d998f  jz      short loc_1800D99B2
0x1800d9991  test    r8, r8
0x1800d9994  jz      short loc_1800D99B2
0x1800d9996  movzx   eax, word ptr [rsi]
0x1800d9999  test    ax, ax
0x1800d999c  jz      short loc_1800D99B2
0x1800d999e  mov     [rdx], ax
0x1800d99a1  add     rsi, 2
0x1800d99a5  add     rdx, 2
0x1800d99a9  dec     r8
0x1800d99ac  sub     rbx, 1
0x1800d99b0  jnz     short loc_1800D9991
0x1800d99b2  xor     eax, eax
0x1800d99b4  lea     rcx, [rdx-2]
0x1800d99b8  test    rbx, rbx
0x1800d99bb  cmovnz  rcx, rdx
0x1800d99bf  cmovnz  r10d, eax
0x1800d99c3  mov     [rcx], ax
0x1800d99c6  jz      short loc_1800D9A08
0x1800d99c8  xor     edx, edx; hFile
0x1800d99ca  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x1800d99cf  mov     r8d, 800h; dwFlags
0x1800d99d5  call    cs:__imp_LoadLibraryExW
0x1800d99db  mov     [r14], rax
0x1800d99de  test    rax, rax
0x1800d99e1  jnz     short loc_1800D99FE
0x1800d99e3  call    cs:__imp_GetLastError
0x1800d99e9  test    eax, eax
0x1800d99eb  jle     loc_1800D987B
0x1800d99f1  movzx   eax, ax
0x1800d99f4  or      eax, 80070000h
0x1800d99f9  jmp     loc_1800D987B
0x1800d99fe  xor     eax, eax
0x1800d9a00  jmp     loc_1800D987B
0x1800d9a05  mov     r10d, edi
0x1800d9a08  mov     eax, r10d
0x1800d9a0b  jmp     loc_1800D987B
0x1800d9a10  mov     eax, r11d
0x1800d9a13  jmp     loc_1800D987B
0x1800d9a18  mov     eax, edi
0x1800d9a1a  jmp     loc_1800D987B
0x1800d9a1f  mov     eax, 80004005h
0x1800d9a24  jmp     loc_1800D9893
```
