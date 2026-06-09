# FormatHResult(long,ushort * *)

- ea: `0x14000cd9c`
- end: `0x14000cf2f`
- name: `?FormatHResult@@YAJJPEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(DWORD dwMessageId, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400058b4`
- `0x1400097d0`
- `0x14000a120`
- `0x140010160`
- `0x1400114e0`
- `0x1400121f0`

## callees

- `0x14000cd9c`

## import_xrefs

- `msvcrt!swprintf_s` at `0x14000ce3d`
- `msvcrt!swprintf_s` at `0x14000ce3d`
- `msvcrt!sprintf_s` at `0x14000ce80`
- `msvcrt!sprintf_s` at `0x14000ce80`
- `OLEAUT32!__imp_SysAllocString` at `0x14000cef9`
- `OLEAUT32!__imp_SysAllocString` at `0x14000cef9`
- `KERNEL32!MultiByteToWideChar` at `0x14000cea5`
- `KERNEL32!MultiByteToWideChar` at `0x14000cee5`
- `KERNEL32!MultiByteToWideChar` at `0x14000cea5`
- `KERNEL32!MultiByteToWideChar` at `0x14000cee5`
- `KERNEL32!FormatMessageW` at `0x14000cdeb`
- `KERNEL32!FormatMessageW` at `0x14000cdeb`
- `KERNEL32!LocalAlloc` at `0x14000cdfe`
- `KERNEL32!LocalAlloc` at `0x14000ce62`
- `KERNEL32!LocalAlloc` at `0x14000cebe`
- `KERNEL32!LocalAlloc` at `0x14000cdfe`
- `KERNEL32!LocalAlloc` at `0x14000ce62`
- `KERNEL32!LocalAlloc` at `0x14000cebe`
- `KERNEL32!LocalFree` at `0x14000cf0b`
- `KERNEL32!LocalFree` at `0x14000cf1a`
- `KERNEL32!LocalFree` at `0x14000cf0b`
- `KERNEL32!LocalFree` at `0x14000cf1a`
- `KERNEL32!FormatMessageA` at `0x14000ce51`
- `KERNEL32!FormatMessageA` at `0x14000ce51`
- `KERNEL32!GetLastError` at `0x14000ce0d`
- `KERNEL32!GetLastError` at `0x14000ce0d`

## pseudocode

```c
__int64 __fastcall FormatHResult(DWORD dwMessageId, unsigned __int16 **a2)
{
  OLECHAR *v4; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  CHAR *v7; // rax
  int v8; // eax
  int v9; // ebx
  OLECHAR *v10; // rax
  CHAR *lpBuffer; // [rsp+70h] [rbp+30h] BYREF
  OLECHAR *Buffer; // [rsp+78h] [rbp+38h] BYREF

  Buffer = 0;
  lpBuffer = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( !FormatMessageW(0x11FFu, 0, dwMessageId, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      v4 = (OLECHAR *)LocalAlloc(0, 0x16u);
      Buffer = v4;
      if ( !v4 )
        goto LABEL_4;
      swprintf_s(v4, 0xBu, L"0x%8X", dwMessageId);
    }
LABEL_13:
    v6 = 0;
    *a2 = SysAllocString(Buffer);
    goto LABEL_14;
  }
  if ( !FormatMessageA(0x11FFu, 0, dwMessageId, 0, (LPSTR)&lpBuffer, 0, 0) )
  {
    v7 = (CHAR *)LocalAlloc(0, 0xBu);
    lpBuffer = v7;
    if ( !v7 )
      goto LABEL_4;
    sprintf_s(v7, 0xBu, "0x%8X", dwMessageId);
  }
  v8 = MultiByteToWideChar(0, 0, lpBuffer, -1, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = (OLECHAR *)LocalAlloc(0, 2LL * v8);
    Buffer = v10;
    if ( v10 )
    {
      if ( MultiByteToWideChar(0, 0, lpBuffer, -1, v10, v9) )
        goto LABEL_13;
    }
  }
LABEL_4:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  if ( lpBuffer )
    LocalFree(lpBuffer);
  if ( Buffer )
    LocalFree(Buffer);
  return v6;
}

```

## disassembly

```asm
0x14000cd9c  mov     [rsp-18h+arg_0], rbx
0x14000cda1  push    rbp
0x14000cda2  push    rsi
0x14000cda3  push    rdi
0x14000cda4  mov     rbp, rsp
0x14000cda7  sub     rsp, 40h
0x14000cdab  mov     rsi, rdx
0x14000cdae  mov     [rsp+40h+Arguments], 0; Arguments
0x14000cdb7  xor     edx, edx; lpSource
0x14000cdb9  mov     [rbp+Buffer], 0
0x14000cdc1  xor     r9d, r9d; dwLanguageId
0x14000cdc4  mov     [rbp+arg_10], 0
0x14000cdcc  cmp     cs:?g_fWindowsNT@Global@@2_NA, dl; bool Global::g_fWindowsNT
0x14000cdd2  mov     edi, ecx
0x14000cdd4  mov     r8d, ecx; dwMessageId
0x14000cdd7  mov     [rsp+40h+nSize], edx; nSize
0x14000cddb  mov     ecx, 11FFh; dwFlags
0x14000cde0  jz      short loc_14000CE48
0x14000cde2  lea     rax, [rbp+Buffer]
0x14000cde6  mov     [rsp+40h+lpBuffer], rax; lpBuffer
0x14000cdeb  call    cs:__imp_FormatMessageW
0x14000cdf1  test    eax, eax
0x14000cdf3  jnz     loc_14000CEF3
0x14000cdf9  lea     edx, [rax+16h]; uBytes
0x14000cdfc  xor     ecx, ecx; uFlags
0x14000cdfe  call    cs:__imp_LocalAlloc
0x14000ce04  mov     [rbp+Buffer], rax
0x14000ce08  test    rax, rax
0x14000ce0b  jnz     short loc_14000CE2B
0x14000ce0d  call    cs:__imp_GetLastError
0x14000ce13  mov     ebx, eax
0x14000ce15  test    eax, eax
0x14000ce17  jle     loc_14000CF02
0x14000ce1d  movzx   ebx, ax
0x14000ce20  or      ebx, 80070000h
0x14000ce26  jmp     loc_14000CF02
0x14000ce2b  mov     r9d, edi
0x14000ce2e  lea     r8, a0x8x_0; "0x%8X"
0x14000ce35  mov     edx, 0Bh; BufferCount
0x14000ce3a  mov     rcx, rax; Buffer
0x14000ce3d  call    cs:__imp_swprintf_s
0x14000ce43  jmp     loc_14000CEF3
0x14000ce48  lea     rax, [rbp+arg_10]
0x14000ce4c  mov     [rsp+40h+lpBuffer], rax; lpBuffer
0x14000ce51  call    cs:__imp_FormatMessageA
0x14000ce57  test    eax, eax
0x14000ce59  jnz     short loc_14000CE86
0x14000ce5b  lea     ebx, [rax+0Bh]
0x14000ce5e  xor     ecx, ecx; uFlags
0x14000ce60  mov     edx, ebx; uBytes
0x14000ce62  call    cs:__imp_LocalAlloc
0x14000ce68  mov     [rbp+arg_10], rax
0x14000ce6c  test    rax, rax
0x14000ce6f  jz      short loc_14000CE0D
0x14000ce71  mov     r9d, edi
0x14000ce74  lea     r8, a0x8x; "0x%8X"
0x14000ce7b  mov     edx, ebx; BufferCount
0x14000ce7d  mov     rcx, rax; Buffer
0x14000ce80  call    cs:__imp_sprintf_s
0x14000ce86  mov     r8, [rbp+arg_10]; lpMultiByteStr
0x14000ce8a  or      edi, 0FFFFFFFFh
0x14000ce8d  mov     r9d, edi; cbMultiByte
0x14000ce90  mov     [rsp+40h+nSize], 0; cchWideChar
0x14000ce98  xor     edx, edx; dwFlags
0x14000ce9a  mov     [rsp+40h+lpBuffer], 0; lpWideCharStr
0x14000cea3  xor     ecx, ecx; CodePage
0x14000cea5  call    cs:__imp_MultiByteToWideChar
0x14000ceab  movsxd  rbx, eax
0x14000ceae  test    eax, eax
0x14000ceb0  jz      loc_14000CE0D
0x14000ceb6  mov     rdx, rbx
0x14000ceb9  xor     ecx, ecx; uFlags
0x14000cebb  add     rdx, rdx; uBytes
0x14000cebe  call    cs:__imp_LocalAlloc
0x14000cec4  mov     [rbp+Buffer], rax
0x14000cec8  test    rax, rax
0x14000cecb  jz      loc_14000CE0D
0x14000ced1  mov     r8, [rbp+arg_10]; lpMultiByteStr
0x14000ced5  mov     r9d, edi; cbMultiByte
0x14000ced8  mov     [rsp+40h+nSize], ebx; cchWideChar
0x14000cedc  xor     edx, edx; dwFlags
0x14000cede  xor     ecx, ecx; CodePage
0x14000cee0  mov     [rsp+40h+lpBuffer], rax; lpWideCharStr
0x14000cee5  call    cs:__imp_MultiByteToWideChar
0x14000ceeb  test    eax, eax
0x14000ceed  jz      loc_14000CE0D
0x14000cef3  mov     rcx, [rbp+Buffer]; psz
0x14000cef7  xor     ebx, ebx
0x14000cef9  call    cs:__imp_SysAllocString
0x14000ceff  mov     [rsi], rax
0x14000cf02  mov     rcx, [rbp+arg_10]; hMem
0x14000cf06  test    rcx, rcx
0x14000cf09  jz      short loc_14000CF11
0x14000cf0b  call    cs:__imp_LocalFree
0x14000cf11  mov     rcx, [rbp+Buffer]; hMem
0x14000cf15  test    rcx, rcx
0x14000cf18  jz      short loc_14000CF20
0x14000cf1a  call    cs:__imp_LocalFree
0x14000cf20  mov     eax, ebx
0x14000cf22  mov     rbx, [rsp+40h+arg_0]
0x14000cf27  add     rsp, 40h
0x14000cf2b  pop     rdi
0x14000cf2c  pop     rsi
0x14000cf2d  pop     rbp
0x14000cf2e  retn
```
