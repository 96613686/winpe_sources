# PathCchIsRoot

- ea: `0x18000ff24`
- end: `0x180010045`
- name: `PathCchIsRoot`
- size: `289`
- prototype: `BOOL __stdcall(PCWSTR pszPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18000f040`
- `0x18001004c`

## callees

- `0x18000f81c`
- `0x18000f8b4`
- `0x18000f960`
- `0x18000ff24`
- `0x180018434`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000ff52`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000ffef`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000ff52`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000ffef`

## pseudocode

```c
BOOL __stdcall PathCchIsRoot(PCWSTR pszPath)
{
  __int64 v2; // rcx
  _WORD *v3; // rax
  __int16 v4; // cx
  int v5; // edx

  if ( pszPath )
  {
    v2 = *pszPath;
    if ( (_WORD)v2 )
    {
      if ( (unsigned int)_o_iswalpha(v2) && StrIsEqualCaseInsensitive(pszPath + 1, L":\\", 3)
        || *pszPath == 92 && !pszPath[1] )
      {
        return 1;
      }
      if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
      {
        v3 = 0;
        v4 = MEMORY[0];
        if ( MEMORY[0] )
        {
          v5 = 0;
          while ( v4 != 92 || ++v5 <= 1 && v3[1] )
          {
            v4 = *++v3;
            if ( !*v3 )
              return 1;
          }
          return 0;
        }
        return 1;
      }
      if ( !wcsncmp_0(pszPath, L"\\\\?\\", 4u)
        && (unsigned int)_o_iswalpha(pszPath[4])
        && StrIsEqualCaseInsensitive(pszPath + 5, L":\\", 3)
        || PathIsVolumeGUIDWorker(pszPath) && pszPath[48] == 92 && !pszPath[49] )
      {
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ff24  mov     [rsp+arg_8], rbx
0x18000ff29  mov     [rsp+arg_10], rsi
0x18000ff2e  push    rdi
0x18000ff2f  sub     rsp, 20h
0x18000ff33  xor     esi, esi
0x18000ff35  mov     rbx, rcx
0x18000ff38  mov     [rsp+28h+arg_0], rsi
0x18000ff3d  test    rcx, rcx
0x18000ff40  jz      loc_180010033
0x18000ff46  movzx   ecx, word ptr [rcx]
0x18000ff49  test    cx, cx
0x18000ff4c  jz      loc_180010033
0x18000ff52  call    cs:__imp__o_iswalpha
0x18000ff58  lea     rdi, [rbx+2]
0x18000ff5c  test    eax, eax
0x18000ff5e  jz      short loc_18000FF7B
0x18000ff60  lea     r8d, [rsi+3]; int
0x18000ff64  mov     rcx, rdi; unsigned __int16 *
0x18000ff67  lea     rdx, asc_18001EDDC; ":\\"
0x18000ff6e  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18000ff73  test    al, al
0x18000ff75  jnz     loc_18001002C
0x18000ff7b  cmp     word ptr [rbx], 5Ch ; '\'
0x18000ff7f  jnz     short loc_18000FF8A
0x18000ff81  cmp     [rdi], si
0x18000ff84  jz      loc_18001002C
0x18000ff8a  lea     r8, IsBackslash
0x18000ff91  mov     rcx, rbx; unsigned __int16 *
0x18000ff94  lea     rdx, [rsp+28h+arg_0]
0x18000ff99  call    PathIsUnc2
0x18000ff9e  test    eax, eax
0x18000ffa0  jz      short loc_18000FFD2
0x18000ffa2  mov     rax, [rsp+28h+arg_0]
0x18000ffa7  movzx   ecx, word ptr [rax]
0x18000ffaa  test    cx, cx
0x18000ffad  jz      short loc_18001002C
0x18000ffaf  mov     edx, esi
0x18000ffb1  cmp     cx, 5Ch ; '\'
0x18000ffb5  jnz     short loc_18000FFC4
0x18000ffb7  inc     edx
0x18000ffb9  cmp     edx, 1
0x18000ffbc  jg      short loc_180010033
0x18000ffbe  cmp     [rax+2], si
0x18000ffc2  jz      short loc_180010033
0x18000ffc4  add     rax, 2
0x18000ffc8  movzx   ecx, word ptr [rax]
0x18000ffcb  test    cx, cx
0x18000ffce  jnz     short loc_18000FFB1
0x18000ffd0  jmp     short loc_18001002C
0x18000ffd2  mov     r8d, 4; MaxCount
0x18000ffd8  lea     rdx, asc_18001EE88; "\\\\?\\"
0x18000ffdf  mov     rcx, rbx; String1
0x18000ffe2  call    wcsncmp_0
0x18000ffe7  test    eax, eax
0x18000ffe9  jnz     short loc_180010013
0x18000ffeb  movzx   ecx, word ptr [rbx+8]
0x18000ffef  call    cs:__imp__o_iswalpha
0x18000fff5  test    eax, eax
0x18000fff7  jz      short loc_180010013
0x18000fff9  lea     rcx, [rbx+0Ah]; unsigned __int16 *
0x18000fffd  mov     r8d, 3; int
0x180010003  lea     rdx, asc_18001EDDC; ":\\"
0x18001000a  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18001000f  test    al, al
0x180010011  jnz     short loc_18001002C
0x180010013  mov     rcx, rbx; unsigned __int16 *
0x180010016  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18001001b  test    al, al
0x18001001d  jz      short loc_180010033
0x18001001f  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x180010024  jnz     short loc_180010033
0x180010026  cmp     [rbx+62h], si
0x18001002a  jnz     short loc_180010033
0x18001002c  mov     eax, 1
0x180010031  jmp     short loc_180010035
0x180010033  xor     eax, eax
0x180010035  mov     rbx, [rsp+28h+arg_8]
0x18001003a  mov     rsi, [rsp+28h+arg_10]
0x18001003f  add     rsp, 20h
0x180010043  pop     rdi
0x180010044  retn
```
