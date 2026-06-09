# FormatLine(ushort const *,ushort * *,char * *)

- ea: `0x14000cf38`
- end: `0x14000d137`
- name: `?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z`
- size: `511`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned __int16 **, char **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001330`
- `0x14000d140`
- `0x14000d178`
- `0x14000d2e0`

## callees

- `0x14000cf38`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000d0e8`
- `OLEAUT32!__imp_SysAllocString` at `0x14000d0e8`
- `KERNEL32!MultiByteToWideChar` at `0x14000d095`
- `KERNEL32!MultiByteToWideChar` at `0x14000d0d6`
- `KERNEL32!MultiByteToWideChar` at `0x14000d095`
- `KERNEL32!MultiByteToWideChar` at `0x14000d0d6`
- `KERNEL32!FormatMessageW` at `0x14000cf96`
- `KERNEL32!FormatMessageW` at `0x14000cf96`
- `KERNEL32!WideCharToMultiByte` at `0x14000cfe1`
- `KERNEL32!WideCharToMultiByte` at `0x14000d042`
- `KERNEL32!WideCharToMultiByte` at `0x14000cfe1`
- `KERNEL32!WideCharToMultiByte` at `0x14000d042`
- `KERNEL32!LocalAlloc` at `0x14000d0ae`
- `KERNEL32!LocalAlloc` at `0x14000d0ae`
- `KERNEL32!LocalFree` at `0x14000d107`
- `KERNEL32!LocalFree` at `0x14000d116`
- `KERNEL32!LocalFree` at `0x14000d107`
- `KERNEL32!LocalFree` at `0x14000d116`
- `KERNEL32!FormatMessageA` at `0x14000d071`
- `KERNEL32!FormatMessageA` at `0x14000d071`
- `KERNEL32!GetLastError` at `0x14000cfa4`
- `KERNEL32!GetLastError` at `0x14000cfa4`

## pseudocode

```c
__int64 __fastcall FormatLine(LPCWCH lpWideCharStr, unsigned __int16 **a2, char **Arguments)
{
  DWORD v6; // eax
  signed int LastError; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  int v14; // eax
  int v15; // ebx
  WCHAR *v16; // rax
  int v17; // ebx
  unsigned __int16 *v18; // rax
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp+8h] BYREF

  *(_QWORD *)Buffer = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( Global::g_fWindowsNT )
  {
    v6 = FormatMessageW(0x500u, lpWideCharStr, 0, 0, Buffer, 0, Arguments);
  }
  else
  {
    v9 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v9 )
      goto LABEL_4;
    v10 = v9 + 15LL;
    if ( v10 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = alloca(v11);
    v13 = alloca(v11);
    if ( !MultiByteStr )
    {
      v8 = -2147024882;
      goto LABEL_19;
    }
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v9, 0, 0) )
      goto LABEL_4;
    if ( !FormatMessageA(0x500u, MultiByteStr, 0, 0, MultiByteStr, 0, Arguments) )
      goto LABEL_4;
    v14 = MultiByteToWideChar(0, 0, *(LPCCH *)MultiByteStr, -1, 0, 0);
    v15 = v14;
    if ( !v14 )
      goto LABEL_4;
    v16 = (WCHAR *)LocalAlloc(0, 2LL * v14);
    *(_QWORD *)Buffer = v16;
    if ( !v16 )
      goto LABEL_4;
    v6 = MultiByteToWideChar(0, 0, *(LPCCH *)MultiByteStr, -1, v16, v15);
  }
  if ( !v6 )
  {
LABEL_4:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  v17 = 0;
  v18 = SysAllocString(*(const OLECHAR **)Buffer);
  *a2 = v18;
  if ( !v18 )
    v17 = -2147024882;
  v8 = v17;
LABEL_19:
  if ( *(_QWORD *)MultiByteStr )
    LocalFree(*(HLOCAL *)MultiByteStr);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return v8;
}

```

## disassembly

```asm
0x14000cf38  push    rbp
0x14000cf3a  push    rbx
0x14000cf3b  push    rsi
0x14000cf3c  push    rdi
0x14000cf3d  push    r14
0x14000cf3f  push    r15
0x14000cf41  sub     rsp, 68h
0x14000cf45  lea     rbp, [rsp+40h]
0x14000cf4a  mov     rax, cs:__security_cookie
0x14000cf51  xor     rax, rbp
0x14000cf54  mov     [rbp+50h+var_40], rax
0x14000cf58  xor     r15d, r15d
0x14000cf5b  mov     rsi, r8
0x14000cf5e  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x14000cf65  mov     r14, rdx
0x14000cf68  mov     rdi, rcx
0x14000cf6b  mov     qword ptr [rbp+50h+Buffer], r15
0x14000cf6f  mov     qword ptr [rbp+50h+MultiByteStr], r15
0x14000cf73  jz      short loc_14000CFC2
0x14000cf75  mov     [rsp+90h+Arguments], r8; Arguments
0x14000cf7a  lea     rax, [rbp+50h+Buffer]
0x14000cf7e  mov     rdx, rcx; lpSource
0x14000cf81  mov     [rsp+90h+nSize], r15d; nSize
0x14000cf86  xor     r8d, r8d; dwMessageId
0x14000cf89  mov     [rsp+90h+lpBuffer], rax; lpBuffer
0x14000cf8e  mov     ecx, 500h; dwFlags
0x14000cf93  xor     r9d, r9d; dwLanguageId
0x14000cf96  call    cs:__imp_FormatMessageW
0x14000cf9c  test    eax, eax
0x14000cf9e  jnz     loc_14000D0E1
0x14000cfa4  call    cs:__imp_GetLastError
0x14000cfaa  mov     edi, eax
0x14000cfac  test    eax, eax
0x14000cfae  jle     loc_14000D0FE
0x14000cfb4  movzx   edi, ax
0x14000cfb7  or      edi, 80070000h
0x14000cfbd  jmp     loc_14000D0FE
0x14000cfc2  mov     [rsp+90h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x14000cfc7  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000cfcb  mov     [rsp+90h+Arguments], r15; lpDefaultChar
0x14000cfd0  mov     r8, rdi; lpWideCharStr
0x14000cfd3  mov     [rsp+90h+nSize], r15d; cbMultiByte
0x14000cfd8  xor     edx, edx; dwFlags
0x14000cfda  xor     ecx, ecx; CodePage
0x14000cfdc  mov     [rsp+90h+lpBuffer], r15; lpMultiByteStr
0x14000cfe1  call    cs:__imp_WideCharToMultiByte
0x14000cfe7  movsxd  rdx, eax
0x14000cfea  test    eax, eax
0x14000cfec  jz      short loc_14000CFA4
0x14000cfee  lea     rcx, [rdx+0Fh]
0x14000cff2  cmp     rcx, rdx
0x14000cff5  ja      short loc_14000D001
0x14000cff7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000d001  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000d005  mov     rax, rcx
0x14000d008  call    _alloca_probe
0x14000d00d  sub     rsp, rcx
0x14000d010  lea     rbx, [rsp+90h+MultiByteStr]
0x14000d015  test    rbx, rbx
0x14000d018  jnz     short loc_14000D024
0x14000d01a  mov     edi, 8007000Eh
0x14000d01f  jmp     loc_14000D0FE
0x14000d024  mov     [rsp+90h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x14000d029  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000d02d  mov     [rsp+90h+Arguments], r15; lpDefaultChar
0x14000d032  mov     r8, rdi; lpWideCharStr
0x14000d035  mov     [rsp+90h+nSize], edx; cbMultiByte
0x14000d039  xor     ecx, ecx; CodePage
0x14000d03b  xor     edx, edx; dwFlags
0x14000d03d  mov     [rsp+90h+lpBuffer], rbx; lpMultiByteStr
0x14000d042  call    cs:__imp_WideCharToMultiByte
0x14000d048  test    eax, eax
0x14000d04a  jz      loc_14000CFA4
0x14000d050  mov     [rsp+90h+Arguments], rsi; Arguments
0x14000d055  lea     rax, [rbp+50h+MultiByteStr]
0x14000d059  mov     [rsp+90h+nSize], r15d; nSize
0x14000d05e  xor     r9d, r9d; dwLanguageId
0x14000d061  xor     r8d, r8d; dwMessageId
0x14000d064  mov     [rsp+90h+lpBuffer], rax; lpBuffer
0x14000d069  mov     rdx, rbx; lpSource
0x14000d06c  mov     ecx, 500h; dwFlags
0x14000d071  call    cs:__imp_FormatMessageA
0x14000d077  test    eax, eax
0x14000d079  jz      loc_14000CFA4
0x14000d07f  mov     r8, qword ptr [rbp+50h+MultiByteStr]; lpMultiByteStr
0x14000d083  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14000d087  mov     [rsp+90h+nSize], r15d; cchWideChar
0x14000d08c  xor     edx, edx; dwFlags
0x14000d08e  xor     ecx, ecx; CodePage
0x14000d090  mov     [rsp+90h+lpBuffer], r15; lpWideCharStr
0x14000d095  call    cs:__imp_MultiByteToWideChar
0x14000d09b  movsxd  rbx, eax
0x14000d09e  test    eax, eax
0x14000d0a0  jz      loc_14000CFA4
0x14000d0a6  mov     rdx, rbx
0x14000d0a9  xor     ecx, ecx; uFlags
0x14000d0ab  add     rdx, rdx; uBytes
0x14000d0ae  call    cs:__imp_LocalAlloc
0x14000d0b4  mov     qword ptr [rbp+50h+Buffer], rax
0x14000d0b8  test    rax, rax
0x14000d0bb  jz      loc_14000CFA4
0x14000d0c1  mov     r8, qword ptr [rbp+50h+MultiByteStr]; lpMultiByteStr
0x14000d0c5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14000d0c9  mov     [rsp+90h+nSize], ebx; cchWideChar
0x14000d0cd  xor     edx, edx; dwFlags
0x14000d0cf  xor     ecx, ecx; CodePage
0x14000d0d1  mov     [rsp+90h+lpBuffer], rax; lpWideCharStr
0x14000d0d6  call    cs:__imp_MultiByteToWideChar
0x14000d0dc  jmp     loc_14000CF9C
0x14000d0e1  mov     rcx, qword ptr [rbp+50h+Buffer]; psz
0x14000d0e5  mov     ebx, r15d
0x14000d0e8  call    cs:__imp_SysAllocString
0x14000d0ee  mov     edi, 8007000Eh
0x14000d0f3  mov     [r14], rax
0x14000d0f6  test    rax, rax
0x14000d0f9  cmovz   ebx, edi
0x14000d0fc  mov     edi, ebx
0x14000d0fe  mov     rcx, qword ptr [rbp+50h+MultiByteStr]; hMem
0x14000d102  test    rcx, rcx
0x14000d105  jz      short loc_14000D10D
0x14000d107  call    cs:__imp_LocalFree
0x14000d10d  mov     rcx, qword ptr [rbp+50h+Buffer]; hMem
0x14000d111  test    rcx, rcx
0x14000d114  jz      short loc_14000D11C
0x14000d116  call    cs:__imp_LocalFree
0x14000d11c  mov     eax, edi
0x14000d11e  mov     rcx, [rbp+50h+var_40]
0x14000d122  xor     rcx, rbp; StackCookie
0x14000d125  call    __security_check_cookie
0x14000d12a  lea     rsp, [rbp+28h]
0x14000d12e  pop     r15
0x14000d130  pop     r14
0x14000d132  pop     rdi
0x14000d133  pop     rsi
0x14000d134  pop     rbx
0x14000d135  pop     rbp
0x14000d136  retn
```
