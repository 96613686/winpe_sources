# OpenGlobalizationUserSettingsKey_ForSingleUserModel

- ea: `0x180010b80`
- end: `0x180010eaa`
- name: `OpenGlobalizationUserSettingsKey_ForSingleUserModel`
- size: `810`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010870`
- `0x180010eb0`
- `0x180011c70`
- `0x180011d10`
- `0x180054f80`
- `0x1800d8850`

## callees

- `0x180010b80`
- `0x18001d490`
- `0x180091a60`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180163a80`

## string_xrefs

- `0x180010bb1`: `\Registry\Machine\System\CurrentControlSet\Control\CommonGlobUserSettings\`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForSingleUserModel(unsigned int a1, HANDLE *a2)
{
  size_t v4; // rax
  int v5; // edi
  size_t v6; // rax
  int v7; // eax
  __int64 v8; // r15
  size_t v9; // rax
  unsigned __int64 v10; // rsi
  HANDLE v11; // rax
  unsigned __int64 v13; // rdi
  size_t v14; // rax
  void *v15; // [rsp+30h] [rbp-49h] BYREF
  __int64 v16; // [rsp+38h] [rbp-41h] BYREF
  void *Src; // [rsp+40h] [rbp-39h]
  __int64 v18; // [rsp+48h] [rbp-31h] BYREF
  void *v19; // [rsp+50h] [rbp-29h]
  __int64 v20; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h] BYREF
  __int64 v23; // [rsp+70h] [rbp-9h]
  __int64 *v24; // [rsp+78h] [rbp-1h]
  __int64 v25; // [rsp+80h] [rbp+7h]
  __int128 v26; // [rsp+88h] [rbp+Fh]
  unsigned int v27; // [rsp+F0h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( !dword_1801CA32C )
  {
    Handle = 0;
    v19 = (void *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\";
    v18 = 0;
    v4 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\");
    v22 = 48;
    v25 = 576;
    v23 = 0;
    v26 = 0;
    if ( v4 >= 0xFFFE )
      LOWORD(v4) = -4;
    LOWORD(v18) = v4;
    WORD1(v18) = v4 + 2;
    v24 = &v18;
    v5 = NtOpenKey(&Handle, a1, &v22);
    if ( v5 < 0 )
      goto LABEL_24;
    v27 = 0;
    v21 = (wchar_t *)L"RedirectedKey";
    v20 = 0;
    v6 = 2 * wcslen(L"RedirectedKey");
    if ( v6 >= 0xFFFE )
      LOWORD(v6) = -4;
    LOWORD(v20) = v6;
    WORD1(v20) = v6 + 2;
    v7 = NtQueryValueKey(Handle, &v20, 2, 0, 0, &v27);
    if ( !v27 || v7 != -1073741789 && v7 != -2147483643 )
    {
      if ( (unsigned __int16)v18 <= 0xAAu )
      {
        v13 = (unsigned __int16)v18;
        memmove(&word_1801C6300, v19, (unsigned __int16)v18);
        if ( v13 + 2 <= 0xAA )
          *(&word_1801C6300 + (v13 >> 1)) = 0;
        dword_1801CA32C = 1;
      }
      v5 = 0;
      *a2 = Handle;
      Handle = 0;
      goto LABEL_24;
    }
    v8 = IdnaMemAlloc(v27);
    if ( !v8 )
    {
      v5 = -1073741801;
LABEL_24:
      if ( Handle )
        NtClose(Handle);
      return (unsigned int)v5;
    }
    v5 = NtQueryValueKey(Handle, &v20, 2, v8, v27, &v27);
    if ( v5 >= 0 )
    {
      if ( *(_DWORD *)(v8 + 4) == 1 )
      {
        v15 = 0;
        v16 = 0;
        Src = (void *)(v8 + 12);
        if ( v8 != -12 )
        {
          v9 = 2 * wcslen((const wchar_t *)(v8 + 12));
          if ( v9 >= 0xFFFE )
            LOWORD(v9) = -4;
          LOWORD(v16) = v9;
          WORD1(v16) = v9 + 2;
        }
        v23 = 0;
        v24 = &v16;
        v22 = 48;
        v25 = 576;
        v26 = 0;
        v5 = NtOpenKey(&v15, a1, &v22);
        if ( v5 < 0 )
          goto LABEL_23;
        if ( (unsigned __int16)v16 <= 0xAAu )
        {
          v10 = (unsigned __int16)v16;
          memmove(&word_1801C6300, Src, (unsigned __int16)v16);
          if ( v10 + 2 <= 0xAA )
            *(&word_1801C6300 + (v10 >> 1)) = 0;
          dword_1801CA32C = 1;
        }
        v11 = v15;
      }
      else
      {
        v11 = Handle;
        Handle = 0;
      }
      *a2 = v11;
    }
LABEL_23:
    RtlpSysVolFree(v8);
    goto LABEL_24;
  }
  v20 = 0;
  v21 = &word_1801C6300;
  v14 = 2 * wcslen(&word_1801C6300);
  v22 = 48;
  v25 = 576;
  v23 = 0;
  v26 = 0;
  if ( v14 >= 0xFFFE )
    LOWORD(v14) = -4;
  LOWORD(v20) = v14;
  WORD1(v20) = v14 + 2;
  v24 = &v20;
  return (unsigned int)NtOpenKey(a2, a1, &v22);
}

```

## disassembly

```asm
0x180010b80  mov     [rsp-8+arg_0], rbx
0x180010b85  push    rbp
0x180010b86  push    rsi
0x180010b87  push    rdi
0x180010b88  push    r12
0x180010b8a  push    r13
0x180010b8c  push    r14
0x180010b8e  push    r15
0x180010b90  lea     rbp, [rsp-27h]
0x180010b95  sub     rsp, 0A0h
0x180010b9c  xor     r15d, r15d
0x180010b9f  mov     r12, rdx
0x180010ba2  cmp     cs:dword_1801CA32C, r15d
0x180010ba9  mov     esi, ecx
0x180010bab  jnz     loc_180010E2A
0x180010bb1  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180010bb8  mov     [rbp+57h+Handle], r15
0x180010bbc  mov     [rbp+57h+var_80], rcx
0x180010bc0  mov     [rbp+57h+var_88], r15
0x180010bc4  call    wcslen
0x180010bc9  add     rax, rax
0x180010bcc  mov     [rbp+57h+var_68], 30h ; '0'
0x180010bd4  mov     r13d, 0FFFCh
0x180010bda  mov     [rbp+57h+var_50], 240h
0x180010be2  xorps   xmm0, xmm0
0x180010be5  mov     [rbp+57h+var_60], r15
0x180010be9  lea     ebx, [r15+2]
0x180010bed  mov     edx, esi
0x180010bef  lea     r8, [rbp+57h+var_68]
0x180010bf3  lea     r14d, [r13+2]
0x180010bf7  cmp     rax, r14
0x180010bfa  lea     rcx, [rbp+57h+Handle]
0x180010bfe  movdqu  [rbp+57h+var_48], xmm0
0x180010c03  cmovnb  rax, r13
0x180010c07  mov     word ptr [rbp+57h+var_88], ax
0x180010c0b  add     ax, bx
0x180010c0e  mov     word ptr [rbp+57h+var_88+2], ax
0x180010c12  lea     rax, [rbp+57h+var_88]
0x180010c16  mov     [rbp+57h+var_58], rax
0x180010c1a  call    NtOpenKey
0x180010c1f  mov     edi, eax
0x180010c21  test    eax, eax
0x180010c23  js      loc_180010D95
0x180010c29  lea     rcx, aRedirectedkey; "RedirectedKey"
0x180010c30  mov     [rbp+57h+arg_10], r15d
0x180010c34  mov     [rbp+57h+var_70], rcx
0x180010c38  mov     [rbp+57h+var_78], r15
0x180010c3c  call    wcslen
0x180010c41  mov     rcx, [rbp+57h+Handle]
0x180010c45  lea     rdx, [rbp+57h+var_78]
0x180010c49  add     rax, rax
0x180010c4c  mov     r8d, ebx
0x180010c4f  cmp     rax, r14
0x180010c52  cmovnb  rax, r13
0x180010c56  xor     r9d, r9d
0x180010c59  mov     word ptr [rbp+57h+var_78], ax
0x180010c5d  add     ax, bx
0x180010c60  mov     word ptr [rbp+57h+var_78+2], ax
0x180010c64  lea     rax, [rbp+57h+arg_10]
0x180010c68  mov     [rsp+0D0h+var_A8], rax
0x180010c6d  mov     [rsp+0D0h+var_B0], r15d
0x180010c72  call    NtQueryValueKey
0x180010c77  mov     ecx, [rbp+57h+arg_10]
0x180010c7a  test    ecx, ecx
0x180010c7c  jz      loc_180010DC8
0x180010c82  cmp     eax, 0C0000023h
0x180010c87  jnz     loc_180010E9A
0x180010c8d  call    IdnaMemAlloc
0x180010c92  mov     r15, rax
0x180010c95  test    rax, rax
0x180010c98  jz      loc_180010DC1
0x180010c9e  mov     ecx, [rbp+57h+arg_10]
0x180010ca1  lea     rax, [rbp+57h+arg_10]
0x180010ca5  mov     [rsp+0D0h+var_A8], rax
0x180010caa  lea     rdx, [rbp+57h+var_78]
0x180010cae  mov     [rsp+0D0h+var_B0], ecx
0x180010cb2  mov     r9, r15
0x180010cb5  mov     rcx, [rbp+57h+Handle]
0x180010cb9  mov     r8d, ebx
0x180010cbc  call    NtQueryValueKey
0x180010cc1  xor     edx, edx
0x180010cc3  mov     edi, eax
0x180010cc5  test    eax, eax
0x180010cc7  js      loc_180010D8D
0x180010ccd  cmp     dword ptr [r15+4], 1
0x180010cd2  jnz     loc_180010E1D
0x180010cd8  lea     rcx, [r15+0Ch]; String
0x180010cdc  mov     [rbp+57h+var_A0], rdx
0x180010ce0  mov     [rbp+57h+var_98], rdx
0x180010ce4  mov     [rbp+57h+Src], rcx
0x180010ce8  test    rcx, rcx
0x180010ceb  jz      short loc_180010D09
0x180010ced  call    wcslen
0x180010cf2  add     rax, rax
0x180010cf5  cmp     rax, r14
0x180010cf8  cmovnb  rax, r13
0x180010cfc  mov     word ptr [rbp+57h+var_98], ax
0x180010d00  add     ax, bx
0x180010d03  mov     word ptr [rbp+57h+var_98+2], ax
0x180010d07  xor     edx, edx
0x180010d09  mov     [rbp+57h+var_60], rdx
0x180010d0d  lea     rax, [rbp+57h+var_98]
0x180010d11  xorps   xmm0, xmm0
0x180010d14  mov     [rbp+57h+var_58], rax
0x180010d18  mov     edx, esi
0x180010d1a  mov     [rbp+57h+var_68], 30h ; '0'
0x180010d22  lea     r8, [rbp+57h+var_68]
0x180010d26  mov     [rbp+57h+var_50], 240h
0x180010d2e  lea     rcx, [rbp+57h+var_A0]
0x180010d32  movdqu  [rbp+57h+var_48], xmm0
0x180010d37  call    NtOpenKey
0x180010d3c  mov     edi, eax
0x180010d3e  test    eax, eax
0x180010d40  js      short loc_180010D8D
0x180010d42  movzx   eax, word ptr [rbp+57h+var_98]
0x180010d46  mov     ebx, 0AAh
0x180010d4b  cmp     bx, ax
0x180010d4e  jb      short loc_180010D85
0x180010d50  mov     rdx, [rbp+57h+Src]; Src
0x180010d54  lea     r14, word_1801C6300
0x180010d5b  mov     rcx, r14; void *
0x180010d5e  mov     r8d, eax; Size
0x180010d61  mov     esi, eax
0x180010d63  call    memmove
0x180010d68  lea     rax, [rsi+2]
0x180010d6c  cmp     rax, rbx
0x180010d6f  ja      short loc_180010D7B
0x180010d71  shr     rsi, 1
0x180010d74  xor     eax, eax
0x180010d76  mov     [r14+rsi*2], ax
0x180010d7b  mov     cs:dword_1801CA32C, 1
0x180010d85  mov     rax, [rbp+57h+var_A0]
0x180010d89  mov     [r12], rax
0x180010d8d  mov     rcx, r15
0x180010d90  call    RtlpSysVolFree
0x180010d95  mov     rcx, [rbp+57h+Handle]; Handle
0x180010d99  test    rcx, rcx
0x180010d9c  jz      short loc_180010DA3
0x180010d9e  call    NtClose
0x180010da3  mov     rbx, [rsp+0D0h+arg_0]
0x180010dab  mov     eax, edi
0x180010dad  add     rsp, 0A0h
0x180010db4  pop     r15
0x180010db6  pop     r14
0x180010db8  pop     r13
0x180010dba  pop     r12
0x180010dbc  pop     rdi
0x180010dbd  pop     rsi
0x180010dbe  pop     rbp
0x180010dbf  retn
0x180010dc1  mov     edi, 0C0000017h
0x180010dc6  jmp     short loc_180010D95
0x180010dc8  movzx   eax, word ptr [rbp+57h+var_88]
0x180010dcc  mov     ebx, 0AAh
0x180010dd1  cmp     bx, ax
0x180010dd4  jb      short loc_180010E09
0x180010dd6  mov     rdx, [rbp+57h+var_80]; Src
0x180010dda  lea     r14, word_1801C6300
0x180010de1  mov     rcx, r14; void *
0x180010de4  mov     r8d, eax; Size
0x180010de7  mov     edi, eax
0x180010de9  call    memmove
0x180010dee  lea     rax, [rdi+2]
0x180010df2  cmp     rax, rbx
0x180010df5  ja      short loc_180010DFF
0x180010df7  shr     rdi, 1
0x180010dfa  mov     [r14+rdi*2], r15w
0x180010dff  mov     cs:dword_1801CA32C, 1
0x180010e09  mov     rax, [rbp+57h+Handle]
0x180010e0d  mov     edi, r15d
0x180010e10  mov     [r12], rax
0x180010e14  mov     [rbp+57h+Handle], r15
0x180010e18  jmp     loc_180010D95
0x180010e1d  mov     rax, [rbp+57h+Handle]
0x180010e21  mov     [rbp+57h+Handle], rdx
0x180010e25  jmp     loc_180010D89
0x180010e2a  lea     r14, word_1801C6300
0x180010e31  mov     [rbp+57h+var_78], r15
0x180010e35  mov     rcx, r14; String
0x180010e38  mov     [rbp+57h+var_70], r14
0x180010e3c  call    wcslen
0x180010e41  add     rax, rax
0x180010e44  mov     [rbp+57h+var_68], 30h ; '0'
0x180010e4c  mov     r13d, 0FFFCh
0x180010e52  mov     [rbp+57h+var_50], 240h
0x180010e5a  xorps   xmm0, xmm0
0x180010e5d  mov     [rbp+57h+var_60], r15
0x180010e61  lea     r8, [rbp+57h+var_68]
0x180010e65  mov     edx, esi
0x180010e67  mov     rcx, r12
0x180010e6a  lea     r14d, [r13+2]
0x180010e6e  cmp     rax, r14
0x180010e71  movdqu  [rbp+57h+var_48], xmm0
0x180010e76  cmovnb  rax, r13
0x180010e7a  mov     word ptr [rbp+57h+var_78], ax
0x180010e7e  add     ax, 2
0x180010e82  mov     word ptr [rbp+57h+var_78+2], ax
0x180010e86  lea     rax, [rbp+57h+var_78]
0x180010e8a  mov     [rbp+57h+var_58], rax
0x180010e8e  call    NtOpenKey
0x180010e93  mov     edi, eax
0x180010e95  jmp     loc_180010DA3
0x180010e9a  cmp     eax, 80000005h
0x180010e9f  jz      loc_180010C8D
0x180010ea5  jmp     loc_180010DC8
```
