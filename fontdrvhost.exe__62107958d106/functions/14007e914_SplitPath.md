# SplitPath

- ea: `0x14007e914`
- end: `0x14007ea65`
- name: `SplitPath`
- size: `337`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14007ee98`

## callees

- `0x140076ef6`
- `0x14007e914`
- `0x1400961dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e964`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e980`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e997`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e9ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e964`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e980`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e997`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007e9ae`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14007e948`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14007e9ce`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14007e948`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14007e9ce`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e9df`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007e9df`

## pseudocode

```c
__int64 __fastcall SplitPath(wchar_t *String1, _BYTE *a2)
{
  unsigned int v4; // r14d
  wchar_t *v5; // rax
  __int64 v6; // r8
  wchar_t *v7; // r15
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  wchar_t *v11; // rax
  wchar_t *v12; // rdx
  __int64 v13; // rax
  wchar_t *v14; // rdx
  __int64 v15; // rax

  v4 = 0;
  if ( String1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      v5 = wcsrchr(String1, 0x2Eu);
      v7 = v5;
      if ( v5 )
      {
        if ( !(unsigned int)_o__wcsicmp(v5, L".PFM", v6) )
          *a2 = 1;
        if ( !(unsigned int)_o__wcsicmp(v7, L".MMM", v8) )
          *a2 = 2;
        if ( !(unsigned int)_o__wcsicmp(v7, L".PFB", v9) )
          *a2 = 3;
        if ( !(unsigned int)_o__wcsicmp(v7, L".OTF", v10) )
          *a2 = 4;
        if ( *a2 )
        {
          if ( wcsrchr(String1, 0x5Cu) )
          {
            v11 = wcschr(String1, 0x3Au);
            if ( v11 )
            {
              v12 = v11 - 1;
              v13 = -1;
              do
                ++v13;
              while ( v12[v13] );
              memmove_0(String1, v12, 2LL * (__int16)(v13 + 1));
            }
            else if ( !wcsncmp_0(String1, L"\\??\\UNC\\", 8u) )
            {
              v14 = String1 + 7;
              v15 = -1;
              do
                ++v15;
              while ( v14[v15] );
              memmove_0(String1 + 1, v14, 2LL * (__int16)(v15 + 1));
              *String1 = 92;
            }
          }
          return 1;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14007e914  push    rbx
0x14007e916  push    rsi
0x14007e917  push    rdi
0x14007e918  push    r12
0x14007e91a  push    r14
0x14007e91c  push    r15
0x14007e91e  sub     rsp, 28h
0x14007e922  mov     rbx, rdx
0x14007e925  mov     rdi, rcx
0x14007e928  xor     r12d, r12d
0x14007e92b  mov     r14d, r12d
0x14007e92e  test    rcx, rcx
0x14007e931  jz      loc_14007EA54
0x14007e937  test    rdx, rdx
0x14007e93a  jz      loc_14007EA54
0x14007e940  mov     [rdx], r12b
0x14007e943  lea     edx, [r12+2Eh]; Ch
0x14007e948  call    cs:__imp_wcsrchr
0x14007e94e  mov     r15, rax
0x14007e951  test    rax, rax
0x14007e954  jz      loc_14007EA54
0x14007e95a  lea     rdx, aPfm; ".PFM"
0x14007e961  mov     rcx, rax
0x14007e964  call    cs:__imp__o__wcsicmp
0x14007e96a  lea     esi, [r12+1]
0x14007e96f  test    eax, eax
0x14007e971  jnz     short loc_14007E976
0x14007e973  mov     [rbx], sil
0x14007e976  lea     rdx, aMmm; ".MMM"
0x14007e97d  mov     rcx, r15
0x14007e980  call    cs:__imp__o__wcsicmp
0x14007e986  test    eax, eax
0x14007e988  jnz     short loc_14007E98D
0x14007e98a  mov     byte ptr [rbx], 2
0x14007e98d  lea     rdx, aPfb; ".PFB"
0x14007e994  mov     rcx, r15
0x14007e997  call    cs:__imp__o__wcsicmp
0x14007e99d  test    eax, eax
0x14007e99f  jnz     short loc_14007E9A4
0x14007e9a1  mov     byte ptr [rbx], 3
0x14007e9a4  lea     rdx, aOtf; ".OTF"
0x14007e9ab  mov     rcx, r15
0x14007e9ae  call    cs:__imp__o__wcsicmp
0x14007e9b4  test    eax, eax
0x14007e9b6  jnz     short loc_14007E9BB
0x14007e9b8  mov     byte ptr [rbx], 4
0x14007e9bb  cmp     [rbx], r12b
0x14007e9be  jz      loc_14007EA54
0x14007e9c4  mov     ebx, 5Ch ; '\'
0x14007e9c9  mov     edx, ebx; Ch
0x14007e9cb  mov     rcx, rdi; Str
0x14007e9ce  call    cs:__imp_wcsrchr
0x14007e9d4  test    rax, rax
0x14007e9d7  jz      short loc_14007EA51
0x14007e9d9  lea     edx, [rbx-22h]; Ch
0x14007e9dc  mov     rcx, rdi; Str
0x14007e9df  call    cs:__imp_wcschr
0x14007e9e5  test    rax, rax
0x14007e9e8  jz      short loc_14007EA10
0x14007e9ea  lea     rdx, [rax-2]; Src
0x14007e9ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007e9f2  inc     rax
0x14007e9f5  cmp     [rdx+rax*2], r12w
0x14007e9fa  jnz     short loc_14007E9F2
0x14007e9fc  add     ax, si
0x14007e9ff  movsx   r8, ax
0x14007ea03  add     r8, r8; Size
0x14007ea06  mov     rcx, rdi; void *
0x14007ea09  call    memmove_0
0x14007ea0e  jmp     short loc_14007EA51
0x14007ea10  mov     r8d, 8; MaxCount
0x14007ea16  lea     rdx, aUnc; "\\??\\UNC\\"
0x14007ea1d  mov     rcx, rdi; String1
0x14007ea20  call    wcsncmp_0
0x14007ea25  test    eax, eax
0x14007ea27  jnz     short loc_14007EA51
0x14007ea29  lea     rdx, [rdi+0Eh]; Src
0x14007ea2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007ea31  inc     rax
0x14007ea34  cmp     [rdx+rax*2], r12w
0x14007ea39  jnz     short loc_14007EA31
0x14007ea3b  add     ax, si
0x14007ea3e  movsx   r8, ax
0x14007ea42  add     r8, r8; Size
0x14007ea45  lea     rcx, [rdi+2]; void *
0x14007ea49  call    memmove_0
0x14007ea4e  mov     [rdi], bx
0x14007ea51  mov     r14d, esi
0x14007ea54  mov     eax, r14d
0x14007ea57  add     rsp, 28h
0x14007ea5b  pop     r15
0x14007ea5d  pop     r14
0x14007ea5f  pop     r12
0x14007ea61  pop     rdi
0x14007ea62  pop     rsi
0x14007ea63  pop     rbx
0x14007ea64  retn
0x140097687  push    rbp
0x140097689  sub     rsp, 20h
0x14009768d  mov     rbp, rdx
0x140097690  add     rsp, 20h
0x140097694  pop     rbp
0x140097695  retn
```
