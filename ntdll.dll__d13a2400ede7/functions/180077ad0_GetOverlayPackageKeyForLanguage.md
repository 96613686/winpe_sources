# _GetOverlayPackageKeyForLanguage

- ea: `0x180077ad0`
- end: `0x180077e44`
- name: `_GetOverlayPackageKeyForLanguage`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180077800`

## callees

- `0x180016bc0`
- `0x1800773d0`
- `0x180077ad0`
- `0x18012d320`
- `0x18015ed20`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x180077b21`: `\Registry\Machine\`
- `0x180077b60`: `\Registry\Machine\`

## pseudocode

```c
__int64 __fastcall GetOverlayPackageKeyForLanguage(__int64 a1, _QWORD *a2)
{
  size_t v4; // rax
  unsigned int v5; // edi
  char *v6; // rsi
  __int64 result; // rax
  size_t v8; // rax
  unsigned int v9; // edi
  char *v10; // rsi
  size_t v11; // rax
  unsigned int v12; // edi
  char *v13; // rsi
  size_t v14; // rax
  unsigned int v15; // edi
  char *v16; // rsi
  size_t v17; // rax
  unsigned int v18; // edi
  char *v19; // rsi
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  char *v21; // [rsp+48h] [rbp-B8h]
  _QWORD v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h]
  wchar_t String[256]; // [rsp+80h] [rbp-80h] BYREF
  char v25; // [rsp+280h] [rbp+180h] BYREF

  if ( !a1 )
    return 3221225485LL;
  v20 = 0x2000000;
  v21 = &v25;
  v4 = wcslen(L"\\Registry\\Machine\\");
  if ( v4 > 0x7FFE )
    return 3221225507LL;
  v5 = (unsigned __int16)(2 * v4);
  if ( v5 + (unsigned __int16)v20 > WORD1(v20) )
    return 3221225507LL;
  v6 = &v21[2 * ((unsigned __int64)(unsigned __int16)v20 >> 1)];
  memmove(v6, L"\\Registry\\Machine\\", (unsigned __int16)(2 * v4));
  LOWORD(v20) = v5 + v20;
  if ( (unsigned int)(unsigned __int16)v20 + 1 < WORD1(v20) )
    *(_WORD *)&v6[2 * ((unsigned __int64)v5 >> 1)] = 0;
  result = RtlGetPersistedStateLocation((wchar_t *)L"LanguageOverlayKeyName", String, 512, 0);
  if ( (int)result >= 0 )
  {
    v8 = wcslen(String);
    if ( v8 <= 0x7FFE )
    {
      v9 = (unsigned __int16)(2 * v8);
      if ( v9 + (unsigned __int16)v20 <= WORD1(v20) )
      {
        v10 = &v21[2 * ((unsigned __int64)(unsigned __int16)v20 >> 1)];
        memmove(v10, String, (unsigned __int16)(2 * v8));
        LOWORD(v20) = v9 + v20;
        if ( (unsigned int)(unsigned __int16)v20 + 1 < WORD1(v20) )
          *(_WORD *)&v10[2 * ((unsigned __int64)v9 >> 1)] = 0;
        v11 = wcslen(L"\\");
        if ( v11 <= 0x7FFE )
        {
          v12 = (unsigned __int16)(2 * v11);
          if ( v12 + (unsigned __int16)v20 <= WORD1(v20) )
          {
            v13 = &v21[2 * ((unsigned __int64)(unsigned __int16)v20 >> 1)];
            memmove(v13, L"\\", (unsigned __int16)(2 * v11));
            LOWORD(v20) = v12 + v20;
            if ( (unsigned int)(unsigned __int16)v20 + 1 < WORD1(v20) )
              *(_WORD *)&v13[2 * ((unsigned __int64)v12 >> 1)] = 0;
            v14 = wcslen(L"OverlayPackages");
            if ( v14 <= 0x7FFE )
            {
              v15 = (unsigned __int16)(2 * v14);
              if ( v15 + (unsigned __int16)v20 <= WORD1(v20) )
              {
                v16 = &v21[2 * ((unsigned __int64)(unsigned __int16)v20 >> 1)];
                memmove(v16, L"OverlayPackages", (unsigned __int16)(2 * v14));
                LOWORD(v20) = v15 + v20;
                if ( (unsigned int)(unsigned __int16)v20 + 1 < WORD1(v20) )
                  *(_WORD *)&v16[2 * ((unsigned __int64)v15 >> 1)] = 0;
                v17 = wcslen(L"\\");
                if ( v17 <= 0x7FFE )
                {
                  v18 = (unsigned __int16)(2 * v17);
                  if ( v18 + (unsigned __int16)v20 <= WORD1(v20) )
                  {
                    v19 = &v21[2 * ((unsigned __int64)(unsigned __int16)v20 >> 1)];
                    memmove(v19, L"\\", (unsigned __int16)(2 * v17));
                    LOWORD(v20) = v18 + v20;
                    if ( (unsigned int)(unsigned __int16)v20 + 1 < WORD1(v20) )
                      *(_WORD *)&v19[2 * ((unsigned __int64)v18 >> 1)] = 0;
                    result = RtlAppendUnicodeToString(&v20, a1);
                    if ( (int)result >= 0 )
                    {
                      v22[0] = 48;
                      *a2 = 0;
                      v22[1] = 0;
                      v22[3] = 64;
                      v22[2] = &v20;
                      v23 = 0;
                      return NtOpenKey(a2, 131097, v22);
                    }
                    return result;
                  }
                }
              }
            }
          }
        }
      }
    }
    return 3221225507LL;
  }
  return result;
}

```

## disassembly

```asm
0x180077ad0  mov     [rsp-8+arg_10], rbx
0x180077ad5  mov     [rsp-8+arg_18], rsi
0x180077ada  push    rbp
0x180077adb  push    rdi
0x180077adc  push    r13
0x180077ade  push    r14
0x180077ae0  push    r15
0x180077ae2  lea     rbp, [rsp-390h]
0x180077aea  sub     rsp, 490h
0x180077af1  mov     rax, cs:__security_cookie
0x180077af8  xor     rax, rsp
0x180077afb  mov     [rbp+3B0h+var_30], rax
0x180077b02  mov     r15, rdx
0x180077b05  mov     r14, rcx
0x180077b08  test    rcx, rcx
0x180077b0b  jz      loc_180077E36
0x180077b11  lea     rax, [rbp+3B0h+var_230]
0x180077b18  mov     [rsp+4B0h+var_470], 2000000h
0x180077b21  lea     rcx, aRegistryMachin_7; "\\Registry\\Machine\\"
0x180077b28  mov     [rsp+4B0h+var_468], rax
0x180077b2d  call    wcslen
0x180077b32  mov     r13d, 7FFEh
0x180077b38  cmp     rax, r13
0x180077b3b  ja      loc_180077E3D
0x180077b41  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077b46  add     ax, ax
0x180077b49  movzx   edi, ax
0x180077b4c  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077b51  add     ecx, edi
0x180077b53  cmp     ecx, eax
0x180077b55  ja      loc_180077E3D
0x180077b5b  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077b60  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\"
0x180077b67  mov     rax, [rsp+4B0h+var_468]
0x180077b6c  mov     r8d, edi; Size
0x180077b6f  shr     rcx, 1
0x180077b72  mov     ebx, edi
0x180077b74  lea     rsi, [rax+rcx*2]
0x180077b78  mov     rcx, rsi; void *
0x180077b7b  call    memmove
0x180077b80  movzx   eax, word ptr [rsp+4B0h+var_470]
0x180077b85  add     ax, di
0x180077b88  movzx   ecx, ax
0x180077b8b  mov     word ptr [rsp+4B0h+var_470], ax
0x180077b90  inc     ecx
0x180077b92  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077b97  cmp     ecx, eax
0x180077b99  jnb     short loc_180077BA4
0x180077b9b  shr     rbx, 1
0x180077b9e  xor     eax, eax
0x180077ba0  mov     [rsi+rbx*2], ax
0x180077ba4  mov     [rsp+4B0h+var_480], 0; __int64
0x180077bad  lea     rax, [rbp+3B0h+String]
0x180077bb1  mov     [rsp+4B0h+var_488], 200h; int
0x180077bb9  lea     r8, aSoftwareMicros; "Software\\Microsoft\\LanguageOverlay"
0x180077bc0  xor     r9d, r9d
0x180077bc3  mov     [rsp+4B0h+var_490], rax; void *
0x180077bc8  xor     edx, edx
0x180077bca  lea     rcx, aLanguageoverla; "LanguageOverlayKeyName"
0x180077bd1  call    RtlGetPersistedStateLocation
0x180077bd6  test    eax, eax
0x180077bd8  js      loc_180077E0A
0x180077bde  lea     rcx, [rbp+3B0h+String]; String
0x180077be2  call    wcslen
0x180077be7  cmp     rax, r13
0x180077bea  ja      loc_180077E3D
0x180077bf0  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077bf5  add     ax, ax
0x180077bf8  movzx   edi, ax
0x180077bfb  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077c00  add     ecx, edi
0x180077c02  cmp     ecx, eax
0x180077c04  ja      loc_180077E3D
0x180077c0a  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077c0f  lea     rdx, [rbp+3B0h+String]; Src
0x180077c13  mov     rax, [rsp+4B0h+var_468]
0x180077c18  mov     r8d, edi; Size
0x180077c1b  shr     rcx, 1
0x180077c1e  mov     ebx, edi
0x180077c20  lea     rsi, [rax+rcx*2]
0x180077c24  mov     rcx, rsi; void *
0x180077c27  call    memmove
0x180077c2c  movzx   eax, word ptr [rsp+4B0h+var_470]
0x180077c31  add     ax, di
0x180077c34  movzx   ecx, ax
0x180077c37  mov     word ptr [rsp+4B0h+var_470], ax
0x180077c3c  inc     ecx
0x180077c3e  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077c43  cmp     ecx, eax
0x180077c45  jnb     short loc_180077C50
0x180077c47  shr     rbx, 1
0x180077c4a  xor     eax, eax
0x180077c4c  mov     [rsi+rbx*2], ax
0x180077c50  lea     rcx, asc_180178554; "\\"
0x180077c57  call    wcslen
0x180077c5c  cmp     rax, r13
0x180077c5f  ja      loc_180077E3D
0x180077c65  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077c6a  add     ax, ax
0x180077c6d  movzx   edi, ax
0x180077c70  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077c75  add     ecx, edi
0x180077c77  cmp     ecx, eax
0x180077c79  ja      loc_180077E3D
0x180077c7f  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077c84  lea     rdx, asc_180178554; "\\"
0x180077c8b  mov     rax, [rsp+4B0h+var_468]
0x180077c90  mov     r8d, edi; Size
0x180077c93  shr     rcx, 1
0x180077c96  mov     ebx, edi
0x180077c98  lea     rsi, [rax+rcx*2]
0x180077c9c  mov     rcx, rsi; void *
0x180077c9f  call    memmove
0x180077ca4  movzx   eax, word ptr [rsp+4B0h+var_470]
0x180077ca9  add     ax, di
0x180077cac  movzx   ecx, ax
0x180077caf  mov     word ptr [rsp+4B0h+var_470], ax
0x180077cb4  inc     ecx
0x180077cb6  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077cbb  cmp     ecx, eax
0x180077cbd  jnb     short loc_180077CC8
0x180077cbf  shr     rbx, 1
0x180077cc2  xor     eax, eax
0x180077cc4  mov     [rsi+rbx*2], ax
0x180077cc8  lea     rcx, aOverlaypackage; "OverlayPackages"
0x180077ccf  call    wcslen
0x180077cd4  cmp     rax, r13
0x180077cd7  ja      loc_180077E3D
0x180077cdd  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077ce2  add     ax, ax
0x180077ce5  movzx   edi, ax
0x180077ce8  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077ced  add     ecx, edi
0x180077cef  cmp     ecx, eax
0x180077cf1  ja      loc_180077E3D
0x180077cf7  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077cfc  lea     rdx, aOverlaypackage; "OverlayPackages"
0x180077d03  mov     rax, [rsp+4B0h+var_468]
0x180077d08  mov     r8d, edi; Size
0x180077d0b  shr     rcx, 1
0x180077d0e  mov     ebx, edi
0x180077d10  lea     rsi, [rax+rcx*2]
0x180077d14  mov     rcx, rsi; void *
0x180077d17  call    memmove
0x180077d1c  movzx   eax, word ptr [rsp+4B0h+var_470]
0x180077d21  add     ax, di
0x180077d24  movzx   ecx, ax
0x180077d27  mov     word ptr [rsp+4B0h+var_470], ax
0x180077d2c  inc     ecx
0x180077d2e  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077d33  cmp     ecx, eax
0x180077d35  jnb     short loc_180077D40
0x180077d37  shr     rbx, 1
0x180077d3a  xor     eax, eax
0x180077d3c  mov     [rsi+rbx*2], ax
0x180077d40  lea     rcx, asc_180178554; "\\"
0x180077d47  call    wcslen
0x180077d4c  cmp     rax, r13
0x180077d4f  ja      loc_180077E3D
0x180077d55  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077d5a  add     ax, ax
0x180077d5d  movzx   edi, ax
0x180077d60  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077d65  add     ecx, edi
0x180077d67  cmp     ecx, eax
0x180077d69  ja      loc_180077E3D
0x180077d6f  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x180077d74  lea     rdx, asc_180178554; "\\"
0x180077d7b  mov     rax, [rsp+4B0h+var_468]
0x180077d80  mov     r8d, edi; Size
0x180077d83  shr     rcx, 1
0x180077d86  mov     ebx, edi
0x180077d88  lea     rsi, [rax+rcx*2]
0x180077d8c  mov     rcx, rsi; void *
0x180077d8f  call    memmove
0x180077d94  movzx   eax, word ptr [rsp+4B0h+var_470]
0x180077d99  add     ax, di
0x180077d9c  movzx   ecx, ax
0x180077d9f  mov     word ptr [rsp+4B0h+var_470], ax
0x180077da4  inc     ecx
0x180077da6  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x180077dab  cmp     ecx, eax
0x180077dad  jnb     short loc_180077DB8
0x180077daf  shr     rbx, 1
0x180077db2  xor     eax, eax
0x180077db4  mov     [rsi+rbx*2], ax
0x180077db8  mov     rdx, r14
0x180077dbb  lea     rcx, [rsp+4B0h+var_470]
0x180077dc0  call    RtlAppendUnicodeToString
0x180077dc5  test    eax, eax
0x180077dc7  js      short loc_180077E0A
0x180077dc9  xor     eax, eax
0x180077dcb  mov     [rsp+4B0h+var_460], 30h ; '0'
0x180077dd4  mov     [r15], rax
0x180077dd7  lea     r8, [rsp+4B0h+var_460]
0x180077ddc  mov     [rsp+4B0h+var_458], rax
0x180077de1  xorps   xmm0, xmm0
0x180077de4  lea     rax, [rsp+4B0h+var_470]
0x180077de9  mov     [rsp+4B0h+var_448], 40h ; '@'
0x180077df2  mov     edx, 20019h
0x180077df7  mov     [rsp+4B0h+var_450], rax
0x180077dfc  mov     rcx, r15
0x180077dff  movdqu  [rsp+4B0h+var_440], xmm0
0x180077e05  call    NtOpenKey
0x180077e0a  mov     rcx, [rbp+3B0h+var_30]
0x180077e11  xor     rcx, rsp; StackCookie
0x180077e14  call    __security_check_cookie
0x180077e19  lea     r11, [rsp+4B0h+var_20]
0x180077e21  mov     rbx, [r11+40h]
0x180077e25  mov     rsi, [r11+48h]
0x180077e29  mov     rsp, r11
0x180077e2c  pop     r15
0x180077e2e  pop     r14
0x180077e30  pop     r13
0x180077e32  pop     rdi
0x180077e33  pop     rbp
0x180077e34  retn
0x180077e36  mov     eax, 0C000000Dh
0x180077e3b  jmp     short loc_180077E0A
0x180077e3d  mov     eax, 0C0000023h
0x180077e42  jmp     short loc_180077E0A
```
