# pUtilVPrintfA

- ea: `0x180008b98`
- end: `0x180008ddf`
- name: `pUtilVPrintfA`
- size: `583`
- prototype: `__int64 __fastcall(CHAR *MultiByteString, va_list Args)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800043a0`

## callees

- `0x180008ae0`
- `0x180008b98`
- `0x180008dfe`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180008c8d`
- `msvcrt!_vsnwprintf` at `0x180008d1e`
- `msvcrt!_vsnwprintf` at `0x180008c8d`
- `msvcrt!_vsnwprintf` at `0x180008d1e`
- `ntdll!RtlMultiByteToUnicodeSize` at `0x180008be6`
- `ntdll!RtlMultiByteToUnicodeSize` at `0x180008be6`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180008c43`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180008c43`
- `KERNEL32!SetLastError` at `0x180008dbe`
- `KERNEL32!SetLastError` at `0x180008dbe`
- `KERNEL32!GetLastError` at `0x180008cba`
- `KERNEL32!GetLastError` at `0x180008cba`
- `SETUPAPI!pSetupFree` at `0x180008d98`
- `SETUPAPI!pSetupFree` at `0x180008da1`
- `SETUPAPI!pSetupFree` at `0x180008db4`
- `SETUPAPI!pSetupFree` at `0x180008d98`
- `SETUPAPI!pSetupFree` at `0x180008da1`
- `SETUPAPI!pSetupFree` at `0x180008db4`
- `SETUPAPI!pSetupMalloc` at `0x180008c01`
- `SETUPAPI!pSetupMalloc` at `0x180008c5a`
- `SETUPAPI!pSetupMalloc` at `0x180008c01`
- `SETUPAPI!pSetupMalloc` at `0x180008c5a`
- `SETUPAPI!pSetupRealloc` at `0x180008ce9`
- `SETUPAPI!pSetupRealloc` at `0x180008ce9`

## pseudocode

```c
__int64 __fastcall pUtilVPrintfA(CHAR *MultiByteString, va_list Args)
{
  __int64 v2; // rbp
  DWORD LastError; // ebx
  __int64 BytesInMultiByteString; // rsi
  __int64 v7; // r8
  WCHAR *v8; // rax
  WCHAR *v9; // r12
  int v10; // r13d
  wchar_t *v11; // rax
  wchar_t *v12; // rdi
  unsigned int v13; // eax
  unsigned int v14; // esi
  wchar_t *v15; // rax
  wchar_t *v16; // r14
  size_t v17; // r15
  int v18; // eax
  int v19; // ecx
  ULONG BytesInUnicodeString; // [rsp+70h] [rbp+8h] BYREF
  va_list Argsa; // [rsp+78h] [rbp+10h]

  Argsa = Args;
  v2 = 0;
  BytesInUnicodeString = 0;
  if ( !MultiByteString )
  {
    LastError = 87;
    goto LABEL_42;
  }
  BytesInMultiByteString = -1;
  v7 = -1;
  do
    ++v7;
  while ( MultiByteString[v7] );
  LastError = RtlMultiByteToUnicodeSize(&BytesInUnicodeString, MultiByteString, v7);
  if ( !LastError )
  {
    BytesInUnicodeString += 2;
    v8 = (WCHAR *)pSetupMalloc(BytesInUnicodeString);
    v9 = v8;
    if ( !v8 )
    {
      LastError = 8;
      goto LABEL_42;
    }
    v10 = 0;
    memset_0(v8, 0, BytesInUnicodeString);
    do
      ++BytesInMultiByteString;
    while ( MultiByteString[BytesInMultiByteString] );
    LastError = RtlMultiByteToUnicodeN(v9, BytesInUnicodeString, 0, MultiByteString, BytesInMultiByteString);
    if ( LastError )
      goto LABEL_39;
    v11 = (wchar_t *)pSetupMalloc(4096);
    v12 = v11;
    if ( !v11 )
    {
      LastError = 8;
      goto LABEL_39;
    }
    memset_0(v11, 0, 0x1000u);
    v13 = _vsnwprintf(v12, 0x7FFu, v9, Args);
    if ( v13 < 0x800 )
    {
      if ( v13 == 2047 )
        v12[2047] = 0;
LABEL_16:
      v2 = pUtilUnicodeToAnsiString(v12);
      if ( v2 )
        v10 = 1;
      else
        LastError = GetLastError();
LABEL_37:
      if ( v12 )
        goto LABEL_38;
      goto LABEL_39;
    }
    v14 = 2048;
    v12[2047] = 0;
    while ( 1 )
    {
      if ( v14 > 0x100000 )
      {
        LastError = 122;
        goto LABEL_37;
      }
      v14 *= 2;
      v15 = (wchar_t *)pSetupRealloc(v12, 2 * v14);
      v16 = v15;
      if ( !v15 )
      {
        LastError = 8;
        goto LABEL_37;
      }
      v12 = v15;
      if ( v14 )
      {
        if ( v14 > 0x7FFFFFFF )
        {
          v19 = -2147024809;
          *v15 = 0;
LABEL_32:
          if ( v19 >= 0 )
            goto LABEL_16;
          LastError = (unsigned __int16)v19;
LABEL_38:
          pSetupFree(v12);
LABEL_39:
          pSetupFree(v9);
          if ( !v10 && v2 )
          {
            pSetupFree(v2);
            v2 = 0;
          }
          break;
        }
        v17 = v14 - 1LL;
        v18 = _vsnwprintf(v15, v17, v9, Argsa);
        if ( v18 < 0 || v18 > v17 )
        {
          v19 = -2147024774;
          v16[v17] = 0;
        }
        else
        {
          v19 = 0;
          if ( v18 == v17 )
            v12[v17] = 0;
        }
      }
      else
      {
        v19 = -2147024809;
      }
      if ( v19 != -2147024774 )
        goto LABEL_32;
    }
  }
LABEL_42:
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x180008b98  mov     [rsp+arg_10], rbx
0x180008b9d  mov     [rsp+Args], rdx
0x180008ba2  push    rbp
0x180008ba3  push    rsi
0x180008ba4  push    rdi
0x180008ba5  push    r12
0x180008ba7  push    r13
0x180008ba9  push    r14
0x180008bab  push    r15
0x180008bad  sub     rsp, 30h
0x180008bb1  xor     ebp, ebp
0x180008bb3  mov     [rsp+68h+BytesInUnicodeString], 0
0x180008bbb  mov     r14, rdx
0x180008bbe  mov     rdi, rcx
0x180008bc1  test    rcx, rcx
0x180008bc4  jnz     short loc_180008BCE
0x180008bc6  lea     ebx, [rcx+57h]
0x180008bc9  jmp     loc_180008DBC
0x180008bce  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008bd2  mov     r8, rsi
0x180008bd5  inc     r8; BytesInMultiByteString
0x180008bd8  cmp     [rcx+r8], bpl
0x180008bdc  jnz     short loc_180008BD5
0x180008bde  mov     rdx, rdi; MultiByteString
0x180008be1  lea     rcx, [rsp+68h+BytesInUnicodeString]; BytesInUnicodeString
0x180008be6  call    cs:__imp_RtlMultiByteToUnicodeSize
0x180008bec  mov     ebx, eax
0x180008bee  test    eax, eax
0x180008bf0  jnz     loc_180008DBC
0x180008bf6  mov     ecx, [rsp+68h+BytesInUnicodeString]
0x180008bfa  add     ecx, 2
0x180008bfd  mov     [rsp+68h+BytesInUnicodeString], ecx
0x180008c01  call    cs:__imp_pSetupMalloc
0x180008c07  mov     r12, rax
0x180008c0a  test    rax, rax
0x180008c0d  jnz     short loc_180008C17
0x180008c0f  lea     ebx, [rax+8]
0x180008c12  jmp     loc_180008DBC
0x180008c17  mov     r8d, [rsp+68h+BytesInUnicodeString]; Size
0x180008c1c  xor     r13d, r13d
0x180008c1f  xor     edx, edx; Val
0x180008c21  mov     rcx, r12; void *
0x180008c24  call    memset_0
0x180008c29  inc     rsi
0x180008c2c  cmp     [rdi+rsi], bpl
0x180008c30  jnz     short loc_180008C29
0x180008c32  mov     edx, [rsp+68h+BytesInUnicodeString]; MaxBytesInUnicodeString
0x180008c36  mov     r9, rdi; MultiByteString
0x180008c39  xor     r8d, r8d; BytesInUnicodeString
0x180008c3c  mov     [rsp+68h+BytesInMultiByteString], esi; BytesInMultiByteString
0x180008c40  mov     rcx, r12; UnicodeString
0x180008c43  call    cs:__imp_RtlMultiByteToUnicodeN
0x180008c49  mov     ebx, eax
0x180008c4b  test    eax, eax
0x180008c4d  jnz     loc_180008D9E
0x180008c53  mov     esi, 1000h
0x180008c58  mov     ecx, esi
0x180008c5a  call    cs:__imp_pSetupMalloc
0x180008c60  mov     rdi, rax
0x180008c63  test    rax, rax
0x180008c66  jnz     short loc_180008C70
0x180008c68  lea     ebx, [rax+8]
0x180008c6b  jmp     loc_180008D9E
0x180008c70  mov     r8, rsi; Size
0x180008c73  xor     edx, edx; Val
0x180008c75  mov     rcx, rdi; void *
0x180008c78  call    memset_0
0x180008c7d  mov     esi, 7FFh
0x180008c82  mov     r9, r14; Args
0x180008c85  mov     edx, esi; BufferCount
0x180008c87  mov     r8, r12; Format
0x180008c8a  mov     rcx, rdi; Buffer
0x180008c8d  call    cs:__imp__vsnwprintf
0x180008c93  test    eax, eax
0x180008c95  js      short loc_180008CC7
0x180008c97  cmp     eax, esi
0x180008c99  ja      short loc_180008CC7
0x180008c9b  jnz     short loc_180008CA6
0x180008c9d  xor     eax, eax
0x180008c9f  mov     [rdi+0FFEh], ax
0x180008ca6  mov     rcx, rdi; UnicodeString
0x180008ca9  call    pUtilUnicodeToAnsiString
0x180008cae  mov     rbp, rax
0x180008cb1  test    rax, rax
0x180008cb4  jnz     loc_180008D7C
0x180008cba  call    cs:__imp_GetLastError
0x180008cc0  mov     ebx, eax
0x180008cc2  jmp     loc_180008D90
0x180008cc7  xor     eax, eax
0x180008cc9  mov     esi, 800h
0x180008cce  mov     [rdi+0FFEh], ax
0x180008cd5  cmp     esi, 100000h
0x180008cdb  ja      loc_180008D8B
0x180008ce1  add     esi, esi
0x180008ce3  mov     rcx, rdi
0x180008ce6  lea     edx, [rsi+rsi]
0x180008ce9  call    cs:__imp_pSetupRealloc
0x180008cef  mov     r14, rax
0x180008cf2  test    rax, rax
0x180008cf5  jz      loc_180008D84
0x180008cfb  mov     rdi, rax
0x180008cfe  test    esi, esi
0x180008d00  jz      short loc_180008D4D
0x180008d02  cmp     esi, 7FFFFFFFh
0x180008d08  ja      short loc_180008D64
0x180008d0a  mov     r9, [rsp+68h+Args]; Args
0x180008d0f  mov     r8, r12; Format
0x180008d12  mov     r15d, esi
0x180008d15  mov     rcx, rax; Buffer
0x180008d18  dec     r15
0x180008d1b  mov     rdx, r15; BufferCount
0x180008d1e  call    cs:__imp__vsnwprintf
0x180008d24  test    eax, eax
0x180008d26  js      short loc_180008D3F
0x180008d28  cdqe
0x180008d2a  cmp     rax, r15
0x180008d2d  ja      short loc_180008D3F
0x180008d2f  xor     ecx, ecx
0x180008d31  cmp     rax, r15
0x180008d34  jnz     short loc_180008D56
0x180008d36  xor     eax, eax
0x180008d38  mov     [rdi+r15*2], ax
0x180008d3d  jmp     short loc_180008D56
0x180008d3f  xor     eax, eax
0x180008d41  mov     ecx, 8007007Ah
0x180008d46  mov     [r14+r15*2], ax
0x180008d4b  jmp     short loc_180008D56
0x180008d4d  mov     ecx, 80070057h
0x180008d52  test    esi, esi
0x180008d54  jnz     short loc_180008D64
0x180008d56  cmp     ecx, 8007007Ah
0x180008d5c  jz      loc_180008CD5
0x180008d62  jmp     short loc_180008D6F
0x180008d64  xor     eax, eax
0x180008d66  mov     ecx, 80070057h
0x180008d6b  mov     [r14], ax
0x180008d6f  test    ecx, ecx
0x180008d71  jns     loc_180008CA6
0x180008d77  movzx   ebx, cx
0x180008d7a  jmp     short loc_180008D95
0x180008d7c  mov     r13d, 1
0x180008d82  jmp     short loc_180008D90
0x180008d84  mov     ebx, 8
0x180008d89  jmp     short loc_180008D90
0x180008d8b  mov     ebx, 7Ah ; 'z'
0x180008d90  test    rdi, rdi
0x180008d93  jz      short loc_180008D9E
0x180008d95  mov     rcx, rdi
0x180008d98  call    cs:__imp_pSetupFree
0x180008d9e  mov     rcx, r12
0x180008da1  call    cs:__imp_pSetupFree
0x180008da7  test    r13d, r13d
0x180008daa  jnz     short loc_180008DBC
0x180008dac  test    rbp, rbp
0x180008daf  jz      short loc_180008DBC
0x180008db1  mov     rcx, rbp
0x180008db4  call    cs:__imp_pSetupFree
0x180008dba  xor     ebp, ebp
0x180008dbc  mov     ecx, ebx; dwErrCode
0x180008dbe  call    cs:__imp_SetLastError
0x180008dc4  mov     rbx, [rsp+68h+arg_10]
0x180008dcc  mov     rax, rbp
0x180008dcf  add     rsp, 30h
0x180008dd3  pop     r15
0x180008dd5  pop     r14
0x180008dd7  pop     r13
0x180008dd9  pop     r12
0x180008ddb  pop     rdi
0x180008ddc  pop     rsi
0x180008ddd  pop     rbp
0x180008dde  retn
```
