# RtlpQueryNlsSystemCodePages

- ea: `0x1800dcb7c`
- end: `0x1800dcde3`
- name: `RtlpQueryNlsSystemCodePages`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800dc48c`

## callees

- `0x18000aab0`
- `0x1800dcb7c`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`

## string_xrefs

- `0x1800dcbb9`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\CodePage`

## pseudocode

```c
__int64 __fastcall RtlpQueryNlsSystemCodePages(_DWORD *a1, _DWORD *a2)
{
  size_t v4; // rax
  size_t v5; // rax
  int v6; // ebx
  size_t v7; // rax
  size_t v8; // rax
  size_t v9; // rax
  int v11; // [rsp+30h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-61h] BYREF
  __int64 v13; // [rsp+40h] [rbp-59h] BYREF
  const wchar_t *v14; // [rsp+48h] [rbp-51h]
  __int16 v15; // [rsp+50h] [rbp-49h] BYREF
  __int16 v16; // [rsp+52h] [rbp-47h]
  int v17; // [rsp+54h] [rbp-45h]
  wchar_t *v18; // [rsp+58h] [rbp-41h]
  _QWORD v19[2]; // [rsp+60h] [rbp-39h] BYREF
  _DWORD v20[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v21; // [rsp+78h] [rbp-21h]
  _QWORD *v22; // [rsp+80h] [rbp-19h]
  int v23; // [rsp+88h] [rbp-11h]
  int v24; // [rsp+8Ch] [rbp-Dh]
  __int128 v25; // [rsp+90h] [rbp-9h]
  _BYTE v26[4]; // [rsp+A0h] [rbp+7h] BYREF
  int v27; // [rsp+A4h] [rbp+Bh]
  wchar_t String[11]; // [rsp+ACh] [rbp+13h] BYREF
  __int16 v29; // [rsp+C2h] [rbp+29h]

  *a1 = 65001;
  *a2 = 65001;
  v11 = 0;
  Handle = 0;
  v22 = 0;
  v19[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\CodePage";
  v24 = 0;
  v19[0] = 0;
  v20[1] = 0;
  v4 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\CodePage");
  v20[0] = 48;
  v21 = 0;
  v23 = 576;
  v25 = 0;
  if ( v4 >= 0xFFFE )
    LOWORD(v4) = -4;
  LOWORD(v19[0]) = v4;
  WORD1(v19[0]) = v4 + 2;
  v22 = v19;
  if ( (int)NtOpenKey(&Handle, 0x80000000LL, v20) < 0 )
    goto LABEL_20;
  v13 = 0;
  v14 = L"ACP";
  v5 = 2 * wcslen(L"ACP");
  if ( v5 >= 0xFFFE )
    LOWORD(v5) = -4;
  LOWORD(v13) = v5;
  WORD1(v13) = v5 + 2;
  v6 = NtQueryValueKey(Handle, &v13, 2, v26, 36, &v11);
  if ( v6 >= 0 )
  {
    if ( v27 != 1 )
      goto LABEL_11;
    v29 = 0;
    v17 = 0;
    v18 = String;
    v7 = 2 * wcslen(String);
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    v15 = v7;
    v16 = v7 + 2;
    v6 = RtlUnicodeStringToInteger(&v15, 10, a1);
    if ( v6 >= 0 )
    {
LABEL_11:
      v13 = 0;
      v14 = L"OEMCP";
      v8 = 2 * wcslen(L"OEMCP");
      if ( v8 >= 0xFFFE )
        LOWORD(v8) = -4;
      LOWORD(v13) = v8;
      WORD1(v13) = v8 + 2;
      v6 = NtQueryValueKey(Handle, &v13, 2, v26, 36, &v11);
      if ( v6 >= 0 && v27 == 1 )
      {
        v29 = 0;
        v17 = 0;
        v18 = String;
        v9 = 2 * wcslen(String);
        if ( v9 >= 0xFFFE )
          LOWORD(v9) = -4;
        v15 = v9;
        v16 = v9 + 2;
        v6 = RtlUnicodeStringToInteger(&v15, 10, a2);
      }
    }
  }
  NtClose(Handle);
  if ( v6 < 0 )
  {
LABEL_20:
    *a1 = 65001;
    *a2 = 65001;
  }
  return 0;
}

```

## disassembly

```asm
0x1800dcb7c  mov     [rsp-8+arg_10], rbx
0x1800dcb81  push    rbp
0x1800dcb82  push    rsi
0x1800dcb83  push    rdi
0x1800dcb84  push    r13
0x1800dcb86  push    r15
0x1800dcb88  lea     rbp, [rsp-37h]
0x1800dcb8d  sub     rsp, 0D0h
0x1800dcb94  mov     rax, cs:__security_cookie
0x1800dcb9b  xor     rax, rsp
0x1800dcb9e  mov     [rbp+57h+var_28], rax
0x1800dcba2  xorps   xmm0, xmm0
0x1800dcba5  mov     dword ptr [rcx], 0FDE9h
0x1800dcbab  xor     eax, eax
0x1800dcbad  mov     dword ptr [rdx], 0FDE9h
0x1800dcbb3  mov     rsi, rcx
0x1800dcbb6  mov     [rbp+57h+var_C0], eax
0x1800dcbb9  lea     rcx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800dcbc0  mov     [rbp+57h+Handle], rax
0x1800dcbc4  movups  [rbp+57h+var_70], xmm0
0x1800dcbc8  mov     [rbp+57h+var_88], rcx
0x1800dcbcc  mov     rdi, rdx
0x1800dcbcf  movups  [rbp+57h+var_70+0Ch], xmm0
0x1800dcbd3  mov     [rbp+57h+var_90], rax
0x1800dcbd7  movups  [rbp+57h+var_80], xmm0
0x1800dcbdb  call    wcslen
0x1800dcbe0  add     rax, rax
0x1800dcbe3  mov     dword ptr [rbp+57h+var_80], 30h ; '0'
0x1800dcbea  mov     ebx, 0FFFCh
0x1800dcbef  mov     qword ptr [rbp+57h+var_80+8], 0
0x1800dcbf7  xorps   xmm0, xmm0
0x1800dcbfa  mov     dword ptr [rbp+57h+var_70+8], 240h
0x1800dcc01  mov     r15d, 2
0x1800dcc07  lea     r8, [rbp+57h+var_80]
0x1800dcc0b  mov     edx, 80000000h
0x1800dcc10  lea     rcx, [rbp+57h+Handle]
0x1800dcc14  lea     r13d, [rbx+2]
0x1800dcc18  cmp     rax, r13
0x1800dcc1b  movdqu  [rbp+57h+var_60], xmm0
0x1800dcc20  cmovnb  rax, rbx
0x1800dcc24  mov     word ptr [rbp+57h+var_90], ax
0x1800dcc28  add     ax, r15w
0x1800dcc2c  mov     word ptr [rbp+57h+var_90+2], ax
0x1800dcc30  lea     rax, [rbp+57h+var_90]
0x1800dcc34  mov     qword ptr [rbp+57h+var_70], rax
0x1800dcc38  call    NtOpenKey
0x1800dcc3d  test    eax, eax
0x1800dcc3f  js      loc_1800DCDD5
0x1800dcc45  lea     rcx, aAcp; "ACP"
0x1800dcc4c  mov     [rbp+57h+var_B0], 0
0x1800dcc54  mov     [rbp+57h+var_A8], rcx
0x1800dcc58  call    wcslen
0x1800dcc5d  mov     rcx, [rbp+57h+Handle]
0x1800dcc61  lea     r9, [rbp+57h+var_50]
0x1800dcc65  add     rax, rax
0x1800dcc68  lea     rdx, [rbp+57h+var_B0]
0x1800dcc6c  cmp     rax, r13
0x1800dcc6f  mov     r8d, r15d
0x1800dcc72  cmovnb  rax, rbx
0x1800dcc76  mov     word ptr [rbp+57h+var_B0], ax
0x1800dcc7a  add     ax, r15w
0x1800dcc7e  mov     word ptr [rbp+57h+var_B0+2], ax
0x1800dcc82  lea     rax, [rbp+57h+var_C0]
0x1800dcc86  mov     [rsp+0F0h+var_C8], rax
0x1800dcc8b  mov     [rsp+0F0h+var_D0], 24h ; '$'
0x1800dcc93  call    NtQueryValueKey
0x1800dcc98  mov     ebx, eax
0x1800dcc9a  test    eax, eax
0x1800dcc9c  js      loc_1800DCDA2
0x1800dcca2  cmp     [rbp+57h+var_4C], 1
0x1800dcca6  jnz     short loc_1800DCCF6
0x1800dcca8  xor     eax, eax
0x1800dccaa  lea     rcx, [rbp+57h+String]; String
0x1800dccae  mov     [rbp+57h+var_2E], ax
0x1800dccb2  mov     [rbp+57h+var_9C], eax
0x1800dccb5  lea     rax, [rbp+57h+String]
0x1800dccb9  mov     [rbp+57h+var_98], rax
0x1800dccbd  call    wcslen
0x1800dccc2  add     rax, rax
0x1800dccc5  lea     ecx, [r13-2]
0x1800dccc9  cmp     rax, r13
0x1800dcccc  lea     edx, [r15+8]
0x1800dccd0  mov     r8, rsi
0x1800dccd3  cmovnb  rax, rcx
0x1800dccd7  lea     rcx, [rbp+57h+var_A0]
0x1800dccdb  mov     [rbp+57h+var_A0], ax
0x1800dccdf  add     ax, r15w
0x1800dcce3  mov     [rbp+57h+var_9E], ax
0x1800dcce7  call    RtlUnicodeStringToInteger
0x1800dccec  mov     ebx, eax
0x1800dccee  test    eax, eax
0x1800dccf0  js      loc_1800DCDA2
0x1800dccf6  lea     rcx, aOemcp; "OEMCP"
0x1800dccfd  mov     [rbp+57h+var_B0], 0
0x1800dcd05  mov     [rbp+57h+var_A8], rcx
0x1800dcd09  call    wcslen
0x1800dcd0e  add     rax, rax
0x1800dcd11  lea     r9, [rbp+57h+var_50]
0x1800dcd15  cmp     rax, r13
0x1800dcd18  lea     rdx, [rbp+57h+var_B0]
0x1800dcd1c  mov     ecx, 0FFFCh
0x1800dcd21  mov     r8d, r15d
0x1800dcd24  cmovnb  rax, rcx
0x1800dcd28  mov     rcx, [rbp+57h+Handle]
0x1800dcd2c  mov     word ptr [rbp+57h+var_B0], ax
0x1800dcd30  add     ax, r15w
0x1800dcd34  mov     word ptr [rbp+57h+var_B0+2], ax
0x1800dcd38  lea     rax, [rbp+57h+var_C0]
0x1800dcd3c  mov     [rsp+0F0h+var_C8], rax
0x1800dcd41  mov     [rsp+0F0h+var_D0], 24h ; '$'
0x1800dcd49  call    NtQueryValueKey
0x1800dcd4e  mov     ebx, eax
0x1800dcd50  test    eax, eax
0x1800dcd52  js      short loc_1800DCDA2
0x1800dcd54  cmp     [rbp+57h+var_4C], 1
0x1800dcd58  jnz     short loc_1800DCDA2
0x1800dcd5a  xor     eax, eax
0x1800dcd5c  lea     rcx, [rbp+57h+String]; String
0x1800dcd60  mov     [rbp+57h+var_2E], ax
0x1800dcd64  mov     [rbp+57h+var_9C], eax
0x1800dcd67  lea     rax, [rbp+57h+String]
0x1800dcd6b  mov     [rbp+57h+var_98], rax
0x1800dcd6f  call    wcslen
0x1800dcd74  add     rax, rax
0x1800dcd77  mov     ecx, 0FFFCh
0x1800dcd7c  cmp     rax, r13
0x1800dcd7f  mov     r8, rdi
0x1800dcd82  mov     edx, 0Ah
0x1800dcd87  cmovnb  rax, rcx
0x1800dcd8b  lea     rcx, [rbp+57h+var_A0]
0x1800dcd8f  mov     [rbp+57h+var_A0], ax
0x1800dcd93  add     ax, r15w
0x1800dcd97  mov     [rbp+57h+var_9E], ax
0x1800dcd9b  call    RtlUnicodeStringToInteger
0x1800dcda0  mov     ebx, eax
0x1800dcda2  mov     rcx, [rbp+57h+Handle]; Handle
0x1800dcda6  call    NtClose
0x1800dcdab  test    ebx, ebx
0x1800dcdad  js      short loc_1800DCDD5
0x1800dcdaf  xor     eax, eax
0x1800dcdb1  mov     rcx, [rbp+57h+var_28]
0x1800dcdb5  xor     rcx, rsp; StackCookie
0x1800dcdb8  call    __security_check_cookie
0x1800dcdbd  mov     rbx, [rsp+0F0h+arg_10]
0x1800dcdc5  add     rsp, 0D0h
0x1800dcdcc  pop     r15
0x1800dcdce  pop     r13
0x1800dcdd0  pop     rdi
0x1800dcdd1  pop     rsi
0x1800dcdd2  pop     rbp
0x1800dcdd3  retn
0x1800dcdd5  mov     dword ptr [rsi], 0FDE9h
0x1800dcddb  mov     dword ptr [rdi], 0FDE9h
0x1800dcde1  jmp     short loc_1800DCDAF
```
