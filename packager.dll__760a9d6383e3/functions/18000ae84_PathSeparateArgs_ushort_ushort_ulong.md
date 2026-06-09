# PathSeparateArgs(ushort *,ushort *,ulong)

- ea: `0x18000ae84`
- end: `0x18000aeec`
- name: `?PathSeparateArgs@@YAHPEAG0K@Z`
- size: `104`
- prototype: `__int64 __fastcall(LPWSTR lpsz, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000774c`
- `0x18000b328`

## callees

- `0x1800041d4`
- `0x18000ae84`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18000ae9f`
- `SHLWAPI!PathFileExistsW` at `0x18000ae9f`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18000aedb`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18000aedb`
- `SHLWAPI!PathGetArgsW` at `0x18000aeb6`
- `SHLWAPI!PathGetArgsW` at `0x18000aeb6`
- `SHLWAPI!PathRemoveBlanksW` at `0x18000ae96`
- `SHLWAPI!PathRemoveBlanksW` at `0x18000ae96`

## pseudocode

```c
__int64 __fastcall PathSeparateArgs(LPWSTR lpsz, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // rsi
  LPWSTR ArgsW; // rax

  v3 = a3;
  PathRemoveBlanksW(lpsz);
  if ( PathFileExistsW(lpsz) )
  {
    *a2 = 0;
    return 1;
  }
  else
  {
    ArgsW = PathGetArgsW(lpsz);
    if ( ArgsW )
    {
      if ( *ArgsW )
        *(ArgsW - 1) = 0;
      StringCchCopyW(a2, v3, ArgsW);
    }
    PathUnquoteSpacesW(lpsz);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ae84  push    rbx
0x18000ae86  push    rbp
0x18000ae87  push    rsi
0x18000ae88  push    rdi
0x18000ae89  sub     rsp, 28h
0x18000ae8d  mov     esi, r8d
0x18000ae90  mov     rdi, rdx
0x18000ae93  mov     rbx, rcx
0x18000ae96  call    cs:__imp_PathRemoveBlanksW
0x18000ae9c  mov     rcx, rbx; pszPath
0x18000ae9f  call    cs:__imp_PathFileExistsW
0x18000aea5  xor     ebp, ebp
0x18000aea7  test    eax, eax
0x18000aea9  jz      short loc_18000AEB3
0x18000aeab  mov     [rdi], bp
0x18000aeae  lea     eax, [rbp+1]
0x18000aeb1  jmp     short loc_18000AEE3
0x18000aeb3  mov     rcx, rbx; pszPath
0x18000aeb6  call    cs:__imp_PathGetArgsW
0x18000aebc  test    rax, rax
0x18000aebf  jz      short loc_18000AED8
0x18000aec1  cmp     [rax], bp
0x18000aec4  jz      short loc_18000AECA
0x18000aec6  mov     [rax-2], bp
0x18000aeca  mov     rdx, rsi; unsigned __int64
0x18000aecd  mov     r8, rax; unsigned __int16 *
0x18000aed0  mov     rcx, rdi; unsigned __int16 *
0x18000aed3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aed8  mov     rcx, rbx; lpsz
0x18000aedb  call    cs:__imp_PathUnquoteSpacesW
0x18000aee1  xor     eax, eax
0x18000aee3  add     rsp, 28h
0x18000aee7  pop     rdi
0x18000aee8  pop     rsi
0x18000aee9  pop     rbp
0x18000aeea  pop     rbx
0x18000aeeb  retn
```
