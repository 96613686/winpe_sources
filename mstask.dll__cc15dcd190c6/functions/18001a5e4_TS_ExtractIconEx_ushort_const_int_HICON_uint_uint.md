# TS_ExtractIconEx(ushort const *,int,HICON__ * *,uint,uint)

- ea: `0x18001a5e4`
- end: `0x18001a6b8`
- name: `?TS_ExtractIconEx@@YAIPEBGHPEAPEAUHICON__@@II@Z`
- size: `212`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, int@<edx>, HICON *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010b5c`

## callees

- `0x18001a43c`
- `0x18001a5e4`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a62f`
- `msvcrt!_wcsicmp` at `0x18001a62f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001a61a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001a61a`
- `SHELL32!SHExtractIconsW` at `0x18001a684`
- `SHELL32!SHExtractIconsW` at `0x18001a684`

## pseudocode

```c
__int64 __fastcall TS_ExtractIconEx(WCHAR *a1, __int64 a2, HICON *a3, __int64 a4, unsigned int a5)
{
  const wchar_t *ExtensionW; // rax
  unsigned __int16 *v8; // rcx
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !a1 || !*a1 )
    return 0;
  ExtensionW = PathFindExtensionW(a1);
  if ( !ExtensionW || _wcsicmp(ExtensionW, L".LNK") )
  {
    v8 = a1;
  }
  else
  {
    memset_0(v10, 0, 0x208u);
    ResolveLnk(a1, v10);
    v8 = v10;
  }
  return SHExtractIconsW(v8, 0, a5, a5, a3, 0, 1, 0x2000);
}

```

## disassembly

```asm
0x18001a5e4  mov     [rsp+arg_8], rbx
0x18001a5e9  mov     [rsp+arg_18], rsi
0x18001a5ee  push    rdi
0x18001a5ef  sub     rsp, 260h
0x18001a5f6  mov     rax, cs:__security_cookie
0x18001a5fd  xor     rax, rsp
0x18001a600  mov     [rsp+268h+var_18], rax
0x18001a608  xor     esi, esi
0x18001a60a  mov     rdi, r8
0x18001a60d  mov     rbx, rcx
0x18001a610  test    rcx, rcx
0x18001a613  jz      short loc_18001A691
0x18001a615  cmp     [rcx], si
0x18001a618  jz      short loc_18001A691
0x18001a61a  call    cs:__imp_PathFindExtensionW
0x18001a620  test    rax, rax
0x18001a623  jz      short loc_18001A68C
0x18001a625  lea     rdx, aLnk; ".LNK"
0x18001a62c  mov     rcx, rax; String1
0x18001a62f  call    cs:__imp__wcsicmp
0x18001a635  test    eax, eax
0x18001a637  jnz     short loc_18001A68C
0x18001a639  xor     edx, edx; Val
0x18001a63b  lea     rcx, [rsp+268h+var_228]; void *
0x18001a640  mov     r8d, 208h; Size
0x18001a646  call    memset_0
0x18001a64b  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x18001a650  mov     rcx, rbx; unsigned __int16 *
0x18001a653  call    ?ResolveLnk@@YAXPEBGPEAG_K@Z; ResolveLnk(ushort const *,ushort *,unsigned __int64)
0x18001a658  lea     rcx, [rsp+268h+var_228]
0x18001a65d  mov     r8d, [rsp+268h+arg_20]
0x18001a665  xor     edx, edx
0x18001a667  mov     [rsp+268h+var_230], 2000h
0x18001a66f  mov     r9d, r8d
0x18001a672  mov     [rsp+268h+var_238], 1
0x18001a67a  mov     [rsp+268h+var_240], rsi
0x18001a67f  mov     [rsp+268h+var_248], rdi
0x18001a684  call    cs:__imp_SHExtractIconsW
0x18001a68a  jmp     short loc_18001A693
0x18001a68c  mov     rcx, rbx
0x18001a68f  jmp     short loc_18001A65D
0x18001a691  xor     eax, eax
0x18001a693  mov     rcx, [rsp+268h+var_18]
0x18001a69b  xor     rcx, rsp; StackCookie
0x18001a69e  call    __security_check_cookie
0x18001a6a3  lea     r11, [rsp+268h+var_8]
0x18001a6ab  mov     rbx, [r11+18h]
0x18001a6af  mov     rsi, [r11+28h]
0x18001a6b3  mov     rsp, r11
0x18001a6b6  pop     rdi
0x18001a6b7  retn
```
