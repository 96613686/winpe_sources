# Region_UpdateShortDate(void)

- ea: `0x1800201d8`
- end: `0x1800202fd`
- name: `?Region_UpdateShortDate@@YAXXZ`
- size: `293`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180014c90`

## callees

- `0x1800201d8`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180020217`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002024d`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180020217`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002024d`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x1800202de`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x1800202de`

## pseudocode

```c
void Region_UpdateShortDate(void)
{
  WCHAR v0; // cx
  int v1; // r9d
  WCHAR *v2; // rdx
  WCHAR *v3; // rax
  WCHAR LCData[64]; // [rsp+20h] [rbp-118h] BYREF
  WCHAR v5[64]; // [rsp+A0h] [rbp-98h] BYREF

  if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x1Fu, LCData, 64) )
  {
    if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x8000001F, v5, 64) )
    {
      v0 = LCData[0];
      if ( LCData[0] )
      {
        v1 = 0;
        v2 = LCData;
        v3 = v5;
        do
        {
          if ( v0 != *v3 )
            break;
          if ( v0 == 121 && v2[1] == 121 && v3[1] == 121 && v3[2] == 121 && v3[3] == 121 )
          {
            ++v2;
            v1 = 1;
            v3 += 3;
          }
          ++v2;
          ++v3;
          v0 = *v2;
        }
        while ( *v2 );
        if ( v1 )
        {
          if ( *v2 == *v3 )
            SetLocaleInfoW(0x400u, 0x1Fu, v5);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800201d8  push    rbx
0x1800201da  sub     rsp, 130h
0x1800201e1  mov     rax, cs:__security_cookie
0x1800201e8  xor     rax, rsp
0x1800201eb  mov     [rsp+138h+var_18], rax
0x1800201f3  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800201f9  lea     r8, [rsp+138h+LCData]; lpLCData
0x1800201fe  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020205  mov     r9d, 40h ; '@'; cchData
0x18002020b  mov     rcx, [rax+rcx*8]
0x18002020f  lea     edx, [r9-21h]; LCType
0x180020213  mov     rcx, [rcx+8]; lpLocaleName
0x180020217  call    cs:__imp_GetLocaleInfoEx
0x18002021d  xor     ebx, ebx
0x18002021f  test    eax, eax
0x180020221  jz      loc_1800202E4
0x180020227  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18002022d  lea     r9d, [rbx+40h]; cchData
0x180020231  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020238  lea     r8, [rsp+138h+var_98]; lpLCData
0x180020240  mov     edx, 8000001Fh; LCType
0x180020245  mov     rcx, [rax+rcx*8]
0x180020249  mov     rcx, [rcx+8]; lpLocaleName
0x18002024d  call    cs:__imp_GetLocaleInfoEx
0x180020253  test    eax, eax
0x180020255  jz      loc_1800202E4
0x18002025b  movzx   ecx, [rsp+138h+LCData]
0x180020260  test    cx, cx
0x180020263  jz      short loc_1800202E4
0x180020265  mov     r9d, ebx
0x180020268  lea     rdx, [rsp+138h+LCData]
0x18002026d  lea     rax, [rsp+138h+var_98]
0x180020275  mov     r10w, 79h ; 'y'
0x18002027a  cmp     cx, [rax]
0x18002027d  jnz     short loc_1800202BF
0x18002027f  cmp     cx, r10w
0x180020283  jnz     short loc_1800202AF
0x180020285  cmp     [rdx+2], r10w
0x18002028a  jnz     short loc_1800202AF
0x18002028c  cmp     [rax+2], r10w
0x180020291  jnz     short loc_1800202AF
0x180020293  cmp     [rax+4], r10w
0x180020298  jnz     short loc_1800202AF
0x18002029a  cmp     [rax+6], r10w
0x18002029f  jnz     short loc_1800202AF
0x1800202a1  add     rdx, 2
0x1800202a5  mov     r9d, 1
0x1800202ab  add     rax, 6
0x1800202af  add     rdx, 2
0x1800202b3  add     rax, 2
0x1800202b7  movzx   ecx, word ptr [rdx]
0x1800202ba  test    cx, cx
0x1800202bd  jnz     short loc_18002027A
0x1800202bf  test    r9d, r9d
0x1800202c2  jz      short loc_1800202E4
0x1800202c4  movzx   eax, word ptr [rax]
0x1800202c7  cmp     [rdx], ax
0x1800202ca  jnz     short loc_1800202E4
0x1800202cc  lea     r8, [rsp+138h+var_98]; lpLCData
0x1800202d4  mov     edx, 1Fh; LCType
0x1800202d9  mov     ecx, 400h; Locale
0x1800202de  call    cs:__imp_SetLocaleInfoW
0x1800202e4  mov     rcx, [rsp+138h+var_18]
0x1800202ec  xor     rcx, rsp; StackCookie
0x1800202ef  call    __security_check_cookie
0x1800202f4  add     rsp, 130h
0x1800202fb  pop     rbx
0x1800202fc  retn
```
