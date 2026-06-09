# IsClrDll(ushort const *)

- ea: `0x180086960`
- end: `0x180086ae2`
- name: `?IsClrDll@@YA?AW4CLR_DLL@@PEBG@Z`
- size: `386`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180086724`
- `0x1800bf758`
- `0x1800d9e8c`
- `0x180215f30`

## callees

- `0x180086960`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x180086a8a`
- `api-ms-win-crt-string-l1-1-0!isdigit` at `0x180086a8a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869b6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869da`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869fe`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086a22`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086a46`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086ab8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869b6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869da`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800869fe`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086a22`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086a46`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180086ab8`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086a6d`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180086a6d`

## string_xrefs

- `0x1800869ac`: `mscorwks.dll`
- `0x180086a18`: `mscoree.dll`
- `0x180086a3c`: `clr.dll`
- `0x1800869d0`: `coreclr.dll`
- `0x1800869f4`: `mscorsvr.dll`
- `0x180086aae`: `_app.dll`

## pseudocode

```c
__int64 __fastcall IsClrDll(unsigned __int64 a1)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  const wchar_t *v4; // rbx
  const wchar_t *i; // rdi

  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(a1 + 2 * v2) );
  v3 = (const wchar_t *)(a1 + 2 * v2);
  do
    v4 = v3--;
  while ( (unsigned __int64)v3 >= a1 && *v3 != 92 && *v3 != 47 && *v3 != 58 );
  if ( !_wcsicmp(v4, L"mscorwks.dll") )
    return 2;
  if ( !_wcsicmp(v4, L"coreclr.dll") )
    return 4;
  if ( !_wcsicmp(v4, L"mscorsvr.dll") )
    return 3;
  if ( !_wcsicmp(v4, L"mscoree.dll") )
    return 1;
  if ( !_wcsicmp(v4, L"clr.dll") )
    return 5;
  if ( _wcsnicmp(v4, L"mrt", 3u) )
    return 0;
  for ( i = v4 + 3; isdigit(*i); ++i )
    ;
  if ( (__int64)(((char *)i - (char *)v4 - 6) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
    return 0;
  else
    return _wcsicmp(i, L"_app.dll") == 0 ? 6 : 0;
}

```

## disassembly

```asm
0x180086960  mov     [rsp+arg_0], rbx
0x180086965  mov     [rsp+arg_8], rsi
0x18008696a  push    rdi
0x18008696b  sub     rsp, 20h
0x18008696f  xor     esi, esi
0x180086971  mov     rdx, rcx
0x180086974  test    rcx, rcx
0x180086977  jz      loc_180086ACF
0x18008697d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180086981  inc     rax
0x180086984  cmp     [rcx+rax*2], si
0x180086988  jnz     short loc_180086981
0x18008698a  lea     rcx, [rcx+rax*2]
0x18008698e  mov     rbx, rcx
0x180086991  sub     rcx, 2
0x180086995  cmp     rcx, rdx
0x180086998  jb      short loc_1800869AC
0x18008699a  cmp     word ptr [rcx], 5Ch ; '\'
0x18008699e  jz      short loc_1800869AC
0x1800869a0  cmp     word ptr [rcx], 2Fh ; '/'
0x1800869a4  jz      short loc_1800869AC
0x1800869a6  cmp     word ptr [rcx], 3Ah ; ':'
0x1800869aa  jnz     short loc_18008698E
0x1800869ac  lea     rdx, aMscorwksDll; "mscorwks.dll"
0x1800869b3  mov     rcx, rbx; String1
0x1800869b6  call    cs:__imp__wcsicmp
0x1800869bd  nop     dword ptr [rax+rax+00h]
0x1800869c2  test    eax, eax
0x1800869c4  jnz     short loc_1800869D0
0x1800869c6  mov     eax, 2
0x1800869cb  jmp     loc_180086AD1
0x1800869d0  lea     rdx, aCoreclrDll; "coreclr.dll"
0x1800869d7  mov     rcx, rbx; String1
0x1800869da  call    cs:__imp__wcsicmp
0x1800869e1  nop     dword ptr [rax+rax+00h]
0x1800869e6  test    eax, eax
0x1800869e8  jnz     short loc_1800869F4
0x1800869ea  mov     eax, 4
0x1800869ef  jmp     loc_180086AD1
0x1800869f4  lea     rdx, aMscorsvrDll; "mscorsvr.dll"
0x1800869fb  mov     rcx, rbx; String1
0x1800869fe  call    cs:__imp__wcsicmp
0x180086a05  nop     dword ptr [rax+rax+00h]
0x180086a0a  test    eax, eax
0x180086a0c  jnz     short loc_180086A18
0x180086a0e  mov     eax, 3
0x180086a13  jmp     loc_180086AD1
0x180086a18  lea     rdx, aMscoreeDll; "mscoree.dll"
0x180086a1f  mov     rcx, rbx; String1
0x180086a22  call    cs:__imp__wcsicmp
0x180086a29  nop     dword ptr [rax+rax+00h]
0x180086a2e  test    eax, eax
0x180086a30  jnz     short loc_180086A3C
0x180086a32  mov     eax, 1
0x180086a37  jmp     loc_180086AD1
0x180086a3c  lea     rdx, aClrDll; "clr.dll"
0x180086a43  mov     rcx, rbx; String1
0x180086a46  call    cs:__imp__wcsicmp
0x180086a4d  nop     dword ptr [rax+rax+00h]
0x180086a52  test    eax, eax
0x180086a54  jnz     short loc_180086A5D
0x180086a56  mov     eax, 5
0x180086a5b  jmp     short loc_180086AD1
0x180086a5d  mov     r8d, 3; MaxCount
0x180086a63  lea     rdx, aMrt; "mrt"
0x180086a6a  mov     rcx, rbx; String1
0x180086a6d  call    cs:__imp__wcsnicmp
0x180086a74  nop     dword ptr [rax+rax+00h]
0x180086a79  test    eax, eax
0x180086a7b  jnz     short loc_180086ACF
0x180086a7d  lea     rdi, [rbx+6]
0x180086a81  jmp     short loc_180086A87
0x180086a83  add     rdi, 2
0x180086a87  movzx   ecx, word ptr [rdi]; C
0x180086a8a  call    cs:__imp_isdigit
0x180086a91  nop     dword ptr [rax+rax+00h]
0x180086a96  test    eax, eax
0x180086a98  jnz     short loc_180086A83
0x180086a9a  mov     rax, rdi
0x180086a9d  sub     rax, rbx
0x180086aa0  sub     rax, 6
0x180086aa4  and     rax, 0FFFFFFFFFFFFFFFEh
0x180086aa8  cmp     rax, 6
0x180086aac  jl      short loc_180086ACF
0x180086aae  lea     rdx, aAppDll; "_app.dll"
0x180086ab5  mov     rcx, rdi; String1
0x180086ab8  call    cs:__imp__wcsicmp
0x180086abf  nop     dword ptr [rax+rax+00h]
0x180086ac4  neg     eax
0x180086ac6  sbb     eax, eax
0x180086ac8  not     eax
0x180086aca  and     eax, 6
0x180086acd  jmp     short loc_180086AD1
0x180086acf  xor     eax, eax
0x180086ad1  mov     rbx, [rsp+28h+arg_0]
0x180086ad6  mov     rsi, [rsp+28h+arg_8]
0x180086adb  add     rsp, 20h
0x180086adf  pop     rdi
0x180086ae0  retn
```
