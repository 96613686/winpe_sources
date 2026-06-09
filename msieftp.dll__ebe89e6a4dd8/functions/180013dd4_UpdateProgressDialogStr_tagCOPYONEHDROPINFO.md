# UpdateProgressDialogStr(tagCOPYONEHDROPINFO *)

- ea: `0x180013dd4`
- end: `0x180013f18`
- name: `?UpdateProgressDialogStr@@YAJPEAUtagCOPYONEHDROPINFO@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct tagCOPYONEHDROPINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180012920`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x180013dd4`
- `0x180023f04`
- `0x180028010`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ea3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013ea3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013e1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013e1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013eeb`

## pseudocode

```c
__int64 __fastcall UpdateProgressDialogStr(struct tagCOPYONEHDROPINFO *a1)
{
  __int64 v2; // rbx
  WCHAR *v3; // rdx
  WCHAR *v4; // rax
  __int64 v5; // rcx
  WCHAR *v6; // rcx
  __int64 v7; // r8
  HLOCAL hMem; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = 260;
  if ( !Buffer )
    LoadStringW(g_hinst, 0x47u, &Buffer, 260);
  StringCchPrintfW(pszPath, 0x104u, &Buffer, *((_QWORD *)a1 + 2));
  (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)a1 + 8) + 80LL))(*((_QWORD *)a1 + 8), 1, pszPath);
  v3 = (WCHAR *)*((_QWORD *)a1 + 1);
  v4 = pszPath;
  v5 = 2147483646;
  do
  {
    if ( !v5 )
      break;
    if ( !*v3 )
      break;
    *v4++ = *v3++;
    --v5;
    --v2;
  }
  while ( v2 );
  v6 = v4 - 1;
  if ( v2 )
    v6 = v4;
  *v6 = 0;
  PathRemoveFileSpecW(pszPath);
  v7 = *((_QWORD *)a1 + 3);
  hMem = 0;
  if ( (int)CreateFromToStr((unsigned __int16 **)&hMem, pszPath, v7) >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, HLOCAL))(**((_QWORD **)a1 + 8) + 80LL))(*((_QWORD *)a1 + 8), 2, hMem);
    LocalFree(hMem);
  }
  return 0;
}

```

## disassembly

```asm
0x180013dd4  mov     [rsp+arg_8], rbx
0x180013dd9  mov     [rsp+arg_10], rsi
0x180013dde  push    rdi
0x180013ddf  sub     rsp, 260h
0x180013de6  mov     rax, cs:__security_cookie
0x180013ded  xor     rax, rsp
0x180013df0  mov     [rsp+268h+var_18], rax
0x180013df8  xor     esi, esi
0x180013dfa  mov     rdi, rcx
0x180013dfd  cmp     cs:Buffer, si
0x180013e04  mov     ebx, 104h
0x180013e09  jnz     short loc_180013E25
0x180013e0b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180013e12  lea     r8, Buffer; lpBuffer
0x180013e19  mov     r9d, ebx; cchBufferMax
0x180013e1c  lea     edx, [rsi+47h]; uID
0x180013e1f  call    cs:__imp_LoadStringW
0x180013e25  mov     r9, [rdi+10h]
0x180013e29  lea     r8, Buffer; unsigned __int16 *
0x180013e30  mov     rdx, rbx; unsigned __int64
0x180013e33  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x180013e38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013e3d  mov     rcx, [rdi+40h]
0x180013e41  lea     r8, [rsp+268h+pszPath]
0x180013e46  xor     r9d, r9d
0x180013e49  mov     [rsp+268h+var_248], rsi
0x180013e4e  mov     rax, [rcx]
0x180013e51  lea     edx, [r9+1]
0x180013e55  mov     rax, [rax+50h]
0x180013e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5e  mov     rdx, [rdi+8]
0x180013e62  lea     rax, [rsp+268h+pszPath]
0x180013e67  mov     ecx, 7FFFFFFEh
0x180013e6c  test    rcx, rcx
0x180013e6f  jz      short loc_180013E90
0x180013e71  movzx   r8d, word ptr [rdx]
0x180013e75  test    r8w, r8w
0x180013e79  jz      short loc_180013E90
0x180013e7b  mov     [rax], r8w
0x180013e7f  add     rdx, 2
0x180013e83  add     rax, 2
0x180013e87  dec     rcx
0x180013e8a  sub     rbx, 1
0x180013e8e  jnz     short loc_180013E6C
0x180013e90  lea     rcx, [rax-2]
0x180013e94  test    rbx, rbx
0x180013e97  cmovnz  rcx, rax
0x180013e9b  mov     [rcx], si
0x180013e9e  lea     rcx, [rsp+268h+pszPath]; pszPath
0x180013ea3  call    cs:__imp_PathRemoveFileSpecW
0x180013ea9  mov     r8, [rdi+18h]
0x180013ead  lea     rdx, [rsp+268h+pszPath]
0x180013eb2  lea     rcx, [rsp+268h+hMem]; unsigned __int16 **
0x180013eb7  mov     [rsp+268h+hMem], rsi
0x180013ebc  call    ?CreateFromToStr@@YAJPEAPEAGZZ; CreateFromToStr(ushort * *,...)
0x180013ec1  test    eax, eax
0x180013ec3  js      short loc_180013EF1
0x180013ec5  mov     rcx, [rdi+40h]
0x180013ec9  xor     r9d, r9d
0x180013ecc  mov     r8, [rsp+268h+hMem]
0x180013ed1  mov     [rsp+268h+var_248], rsi
0x180013ed6  mov     rax, [rcx]
0x180013ed9  lea     edx, [r9+2]
0x180013edd  mov     rax, [rax+50h]
0x180013ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ee6  mov     rcx, [rsp+268h+hMem]; hMem
0x180013eeb  call    cs:__imp_LocalFree
0x180013ef1  xor     eax, eax
0x180013ef3  mov     rcx, [rsp+268h+var_18]
0x180013efb  xor     rcx, rsp; StackCookie
0x180013efe  call    __security_check_cookie
0x180013f03  lea     r11, [rsp+268h+var_8]
0x180013f0b  mov     rbx, [r11+18h]
0x180013f0f  mov     rsi, [r11+20h]
0x180013f13  mov     rsp, r11
0x180013f16  pop     rdi
0x180013f17  retn
```
