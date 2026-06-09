# _GetOverlayPackageKeyForLanguage

- ea: `0x18005b0f0`
- end: `0x18005b464`
- name: `_GetOverlayPackageKeyForLanguage`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005ae20`

## callees

- `0x180016bc0`
- `0x18005a9f0`
- `0x18005b0f0`
- `0x18012c830`
- `0x18015e510`
- `0x180162000`
- `0x180163a80`

## string_xrefs

- `0x18005b141`: `\Registry\Machine\`
- `0x18005b180`: `\Registry\Machine\`

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
0x18005b0f0  mov     [rsp-8+arg_10], rbx
0x18005b0f5  mov     [rsp-8+arg_18], rsi
0x18005b0fa  push    rbp
0x18005b0fb  push    rdi
0x18005b0fc  push    r13
0x18005b0fe  push    r14
0x18005b100  push    r15
0x18005b102  lea     rbp, [rsp-390h]
0x18005b10a  sub     rsp, 490h
0x18005b111  mov     rax, cs:__security_cookie
0x18005b118  xor     rax, rsp
0x18005b11b  mov     [rbp+3B0h+var_30], rax
0x18005b122  mov     r15, rdx
0x18005b125  mov     r14, rcx
0x18005b128  test    rcx, rcx
0x18005b12b  jz      loc_18005B456
0x18005b131  lea     rax, [rbp+3B0h+var_230]
0x18005b138  mov     [rsp+4B0h+var_470], 2000000h
0x18005b141  lea     rcx, aRegistryMachin_7; "\\Registry\\Machine\\"
0x18005b148  mov     [rsp+4B0h+var_468], rax
0x18005b14d  call    wcslen
0x18005b152  mov     r13d, 7FFEh
0x18005b158  cmp     rax, r13
0x18005b15b  ja      loc_18005B45D
0x18005b161  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b166  add     ax, ax
0x18005b169  movzx   edi, ax
0x18005b16c  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b171  add     ecx, edi
0x18005b173  cmp     ecx, eax
0x18005b175  ja      loc_18005B45D
0x18005b17b  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b180  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\"
0x18005b187  mov     rax, [rsp+4B0h+var_468]
0x18005b18c  mov     r8d, edi; Size
0x18005b18f  shr     rcx, 1
0x18005b192  mov     ebx, edi
0x18005b194  lea     rsi, [rax+rcx*2]
0x18005b198  mov     rcx, rsi; void *
0x18005b19b  call    memmove
0x18005b1a0  movzx   eax, word ptr [rsp+4B0h+var_470]
0x18005b1a5  add     ax, di
0x18005b1a8  movzx   ecx, ax
0x18005b1ab  mov     word ptr [rsp+4B0h+var_470], ax
0x18005b1b0  inc     ecx
0x18005b1b2  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b1b7  cmp     ecx, eax
0x18005b1b9  jnb     short loc_18005B1C4
0x18005b1bb  shr     rbx, 1
0x18005b1be  xor     eax, eax
0x18005b1c0  mov     [rsi+rbx*2], ax
0x18005b1c4  mov     [rsp+4B0h+var_480], 0; __int64
0x18005b1cd  lea     rax, [rbp+3B0h+String]
0x18005b1d1  mov     [rsp+4B0h+var_488], 200h; int
0x18005b1d9  lea     r8, aSoftwareMicros; "Software\\Microsoft\\LanguageOverlay"
0x18005b1e0  xor     r9d, r9d
0x18005b1e3  mov     [rsp+4B0h+var_490], rax; void *
0x18005b1e8  xor     edx, edx
0x18005b1ea  lea     rcx, aLanguageoverla; "LanguageOverlayKeyName"
0x18005b1f1  call    RtlGetPersistedStateLocation
0x18005b1f6  test    eax, eax
0x18005b1f8  js      loc_18005B42A
0x18005b1fe  lea     rcx, [rbp+3B0h+String]; String
0x18005b202  call    wcslen
0x18005b207  cmp     rax, r13
0x18005b20a  ja      loc_18005B45D
0x18005b210  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b215  add     ax, ax
0x18005b218  movzx   edi, ax
0x18005b21b  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b220  add     ecx, edi
0x18005b222  cmp     ecx, eax
0x18005b224  ja      loc_18005B45D
0x18005b22a  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b22f  lea     rdx, [rbp+3B0h+String]; Src
0x18005b233  mov     rax, [rsp+4B0h+var_468]
0x18005b238  mov     r8d, edi; Size
0x18005b23b  shr     rcx, 1
0x18005b23e  mov     ebx, edi
0x18005b240  lea     rsi, [rax+rcx*2]
0x18005b244  mov     rcx, rsi; void *
0x18005b247  call    memmove
0x18005b24c  movzx   eax, word ptr [rsp+4B0h+var_470]
0x18005b251  add     ax, di
0x18005b254  movzx   ecx, ax
0x18005b257  mov     word ptr [rsp+4B0h+var_470], ax
0x18005b25c  inc     ecx
0x18005b25e  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b263  cmp     ecx, eax
0x18005b265  jnb     short loc_18005B270
0x18005b267  shr     rbx, 1
0x18005b26a  xor     eax, eax
0x18005b26c  mov     [rsi+rbx*2], ax
0x18005b270  lea     rcx, asc_180177BA4; "\\"
0x18005b277  call    wcslen
0x18005b27c  cmp     rax, r13
0x18005b27f  ja      loc_18005B45D
0x18005b285  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b28a  add     ax, ax
0x18005b28d  movzx   edi, ax
0x18005b290  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b295  add     ecx, edi
0x18005b297  cmp     ecx, eax
0x18005b299  ja      loc_18005B45D
0x18005b29f  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b2a4  lea     rdx, asc_180177BA4; "\\"
0x18005b2ab  mov     rax, [rsp+4B0h+var_468]
0x18005b2b0  mov     r8d, edi; Size
0x18005b2b3  shr     rcx, 1
0x18005b2b6  mov     ebx, edi
0x18005b2b8  lea     rsi, [rax+rcx*2]
0x18005b2bc  mov     rcx, rsi; void *
0x18005b2bf  call    memmove
0x18005b2c4  movzx   eax, word ptr [rsp+4B0h+var_470]
0x18005b2c9  add     ax, di
0x18005b2cc  movzx   ecx, ax
0x18005b2cf  mov     word ptr [rsp+4B0h+var_470], ax
0x18005b2d4  inc     ecx
0x18005b2d6  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b2db  cmp     ecx, eax
0x18005b2dd  jnb     short loc_18005B2E8
0x18005b2df  shr     rbx, 1
0x18005b2e2  xor     eax, eax
0x18005b2e4  mov     [rsi+rbx*2], ax
0x18005b2e8  lea     rcx, aOverlaypackage; "OverlayPackages"
0x18005b2ef  call    wcslen
0x18005b2f4  cmp     rax, r13
0x18005b2f7  ja      loc_18005B45D
0x18005b2fd  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b302  add     ax, ax
0x18005b305  movzx   edi, ax
0x18005b308  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b30d  add     ecx, edi
0x18005b30f  cmp     ecx, eax
0x18005b311  ja      loc_18005B45D
0x18005b317  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b31c  lea     rdx, aOverlaypackage; "OverlayPackages"
0x18005b323  mov     rax, [rsp+4B0h+var_468]
0x18005b328  mov     r8d, edi; Size
0x18005b32b  shr     rcx, 1
0x18005b32e  mov     ebx, edi
0x18005b330  lea     rsi, [rax+rcx*2]
0x18005b334  mov     rcx, rsi; void *
0x18005b337  call    memmove
0x18005b33c  movzx   eax, word ptr [rsp+4B0h+var_470]
0x18005b341  add     ax, di
0x18005b344  movzx   ecx, ax
0x18005b347  mov     word ptr [rsp+4B0h+var_470], ax
0x18005b34c  inc     ecx
0x18005b34e  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b353  cmp     ecx, eax
0x18005b355  jnb     short loc_18005B360
0x18005b357  shr     rbx, 1
0x18005b35a  xor     eax, eax
0x18005b35c  mov     [rsi+rbx*2], ax
0x18005b360  lea     rcx, asc_180177BA4; "\\"
0x18005b367  call    wcslen
0x18005b36c  cmp     rax, r13
0x18005b36f  ja      loc_18005B45D
0x18005b375  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b37a  add     ax, ax
0x18005b37d  movzx   edi, ax
0x18005b380  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b385  add     ecx, edi
0x18005b387  cmp     ecx, eax
0x18005b389  ja      loc_18005B45D
0x18005b38f  movzx   ecx, word ptr [rsp+4B0h+var_470]
0x18005b394  lea     rdx, asc_180177BA4; "\\"
0x18005b39b  mov     rax, [rsp+4B0h+var_468]
0x18005b3a0  mov     r8d, edi; Size
0x18005b3a3  shr     rcx, 1
0x18005b3a6  mov     ebx, edi
0x18005b3a8  lea     rsi, [rax+rcx*2]
0x18005b3ac  mov     rcx, rsi; void *
0x18005b3af  call    memmove
0x18005b3b4  movzx   eax, word ptr [rsp+4B0h+var_470]
0x18005b3b9  add     ax, di
0x18005b3bc  movzx   ecx, ax
0x18005b3bf  mov     word ptr [rsp+4B0h+var_470], ax
0x18005b3c4  inc     ecx
0x18005b3c6  movzx   eax, word ptr [rsp+4B0h+var_470+2]
0x18005b3cb  cmp     ecx, eax
0x18005b3cd  jnb     short loc_18005B3D8
0x18005b3cf  shr     rbx, 1
0x18005b3d2  xor     eax, eax
0x18005b3d4  mov     [rsi+rbx*2], ax
0x18005b3d8  mov     rdx, r14
0x18005b3db  lea     rcx, [rsp+4B0h+var_470]
0x18005b3e0  call    RtlAppendUnicodeToString
0x18005b3e5  test    eax, eax
0x18005b3e7  js      short loc_18005B42A
0x18005b3e9  xor     eax, eax
0x18005b3eb  mov     [rsp+4B0h+var_460], 30h ; '0'
0x18005b3f4  mov     [r15], rax
0x18005b3f7  lea     r8, [rsp+4B0h+var_460]
0x18005b3fc  mov     [rsp+4B0h+var_458], rax
0x18005b401  xorps   xmm0, xmm0
0x18005b404  lea     rax, [rsp+4B0h+var_470]
0x18005b409  mov     [rsp+4B0h+var_448], 40h ; '@'
0x18005b412  mov     edx, 20019h
0x18005b417  mov     [rsp+4B0h+var_450], rax
0x18005b41c  mov     rcx, r15
0x18005b41f  movdqu  [rsp+4B0h+var_440], xmm0
0x18005b425  call    NtOpenKey
0x18005b42a  mov     rcx, [rbp+3B0h+var_30]
0x18005b431  xor     rcx, rsp; StackCookie
0x18005b434  call    __security_check_cookie
0x18005b439  lea     r11, [rsp+4B0h+var_20]
0x18005b441  mov     rbx, [r11+40h]
0x18005b445  mov     rsi, [r11+48h]
0x18005b449  mov     rsp, r11
0x18005b44c  pop     r15
0x18005b44e  pop     r14
0x18005b450  pop     r13
0x18005b452  pop     rdi
0x18005b453  pop     rbp
0x18005b454  retn
0x18005b456  mov     eax, 0C000000Dh
0x18005b45b  jmp     short loc_18005B42A
0x18005b45d  mov     eax, 0C0000023h
0x18005b462  jmp     short loc_18005B42A
```
