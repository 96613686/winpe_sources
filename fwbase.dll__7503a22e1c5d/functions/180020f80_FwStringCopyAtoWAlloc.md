# FwStringCopyAtoWAlloc

- ea: `0x180020f80`
- end: `0x1800210a4`
- name: `FwStringCopyAtoWAlloc`
- size: `292`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18000c060`
- `0x180020f80`
- `0x180021528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002105a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002105a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020fdf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021049`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020fdf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180021049`

## string_xrefs

- `0x180021005`: `FwStringCopyAtoWAlloc`
- `0x180021063`: `FwStringCopyAtoWAlloc`
- `0x180021082`: `FwStringCopyAtoWAlloc`

## pseudocode

```c
__int64 __fastcall FwStringCopyAtoWAlloc(LPCCH lpMultiByteStr, DWORD dwFlags, WCHAR **a3)
{
  WCHAR *v6; // rdi
  unsigned int v7; // eax
  int cchWideChar; // ebp
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  WCHAR *lpWideCharStr; // rax
  const char *v13; // rbx
  DWORD LastError; // eax
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, lpMultiByteStr);
  v6 = 0;
  v16 = 0;
  v7 = MultiByteToWideChar(0, dwFlags, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v7;
  if ( v7 )
  {
    v9 = FwSizeTMultiply(v7, 2, &v16);
    v11 = v9;
    if ( v9 < 0 )
    {
      FwReportReturnError("FwStringCopyAtoWAlloc", (unsigned int)v9);
LABEL_12:
      FwFree(v6);
      return (unsigned int)FwReportReturnError("FwStringCopyAtoWAlloc", v11);
    }
    lpWideCharStr = (WCHAR *)FwAlloc(v16, v10);
    v6 = lpWideCharStr;
    if ( !lpWideCharStr )
    {
      v13 = "FwAlloc";
      LastError = 8;
      goto LABEL_11;
    }
    if ( MultiByteToWideChar(0, dwFlags, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
    {
      *a3 = v6;
      return v11;
    }
  }
  v13 = "MultiByteToWideChar";
  LastError = GetLastError();
LABEL_11:
  v11 = FwReportErrorAsWinError("FwStringCopyAtoWAlloc", v13, LastError);
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_12;
  return v11;
}

```

## disassembly

```asm
0x180020f80  push    rbx
0x180020f82  push    rbp
0x180020f83  push    rsi
0x180020f84  push    rdi
0x180020f85  push    r14
0x180020f87  push    r15
0x180020f89  sub     rsp, 38h
0x180020f8d  mov     r14, r8
0x180020f90  mov     r15d, edx
0x180020f93  mov     rsi, rcx
0x180020f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f9d  lea     rax, WPP_GLOBAL_Control
0x180020fa4  cmp     rcx, rax
0x180020fa7  jz      short loc_180020FC0
0x180020fa9  test    byte ptr [rcx+1Ch], 4
0x180020fad  jz      short loc_180020FC0
0x180020faf  mov     rcx, [rcx+10h]
0x180020fb3  mov     edx, 0Ah
0x180020fb8  mov     r9, rsi
0x180020fbb  call    WPP_SF_s
0x180020fc0  xor     edi, edi
0x180020fc2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180020fc6  mov     [rsp+68h+cchWideChar], edi; cchWideChar
0x180020fca  mov     r8, rsi; lpMultiByteStr
0x180020fcd  mov     edx, r15d; dwFlags
0x180020fd0  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x180020fd5  xor     ecx, ecx; CodePage
0x180020fd7  mov     [rsp+68h+arg_18], rdi
0x180020fdf  call    cs:__imp_MultiByteToWideChar
0x180020fe5  mov     ebp, eax
0x180020fe7  test    eax, eax
0x180020fe9  jz      short loc_180021053
0x180020feb  mov     ecx, ebp
0x180020fed  lea     r8, [rsp+68h+arg_18]
0x180020ff5  lea     edx, [rdi+2]
0x180020ff8  call    FwSizeTMultiply
0x180020ffd  mov     ebx, eax
0x180020fff  test    eax, eax
0x180021001  jns     short loc_180021013
0x180021003  mov     edx, eax
0x180021005  lea     rcx, aFwstringcopyat_0; "FwStringCopyAtoWAlloc"
0x18002100c  call    FwReportReturnError
0x180021011  jmp     short loc_180021078
0x180021013  mov     rcx, [rsp+68h+arg_18]
0x18002101b  call    FwAlloc
0x180021020  mov     rdi, rax
0x180021023  test    rax, rax
0x180021026  jnz     short loc_180021034
0x180021028  lea     rbx, aFwalloc_0; "FwAlloc"
0x18002102f  lea     eax, [rdi+8]
0x180021032  jmp     short loc_180021060
0x180021034  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x180021038  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002103c  mov     r8, rsi; lpMultiByteStr
0x18002103f  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x180021044  mov     edx, r15d; dwFlags
0x180021047  xor     ecx, ecx; CodePage
0x180021049  call    cs:__imp_MultiByteToWideChar
0x18002104f  test    eax, eax
0x180021051  jnz     short loc_180021092
0x180021053  lea     rbx, aMultibytetowid; "MultiByteToWideChar"
0x18002105a  call    cs:__imp_GetLastError
0x180021060  mov     r8d, eax
0x180021063  lea     rcx, aFwstringcopyat_0; "FwStringCopyAtoWAlloc"
0x18002106a  mov     rdx, rbx
0x18002106d  call    FwReportErrorAsWinError
0x180021072  mov     ebx, eax
0x180021074  test    eax, eax
0x180021076  jns     short loc_180021095
0x180021078  mov     rcx, rdi
0x18002107b  call    FwFree
0x180021080  mov     edx, ebx
0x180021082  lea     rcx, aFwstringcopyat_0; "FwStringCopyAtoWAlloc"
0x180021089  call    FwReportReturnError
0x18002108e  mov     ebx, eax
0x180021090  jmp     short loc_180021095
0x180021092  mov     [r14], rdi
0x180021095  mov     eax, ebx
0x180021097  add     rsp, 38h
0x18002109b  pop     r15
0x18002109d  pop     r14
0x18002109f  pop     rdi
0x1800210a0  pop     rsi
0x1800210a1  pop     rbp
0x1800210a2  pop     rbx
0x1800210a3  retn
```
