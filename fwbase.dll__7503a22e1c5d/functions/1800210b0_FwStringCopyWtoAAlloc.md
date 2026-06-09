# FwStringCopyWtoAAlloc

- ea: `0x1800210b0`
- end: `0x1800211d5`
- name: `FwStringCopyWtoAAlloc`
- size: `293`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x1800130bc`
- `0x1800210b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021186`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002112b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180021175`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002112b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180021175`

## string_xrefs

- `0x18002118f`: `FwStringCopyWtoAAlloc`
- `0x1800211ae`: `FwStringCopyWtoAAlloc`

## pseudocode

```c
__int64 __fastcall FwStringCopyWtoAAlloc(LPCWCH lpWideCharStr, DWORD dwFlags, CHAR **a3)
{
  __int64 v6; // rax
  int v7; // r15d
  unsigned int v8; // eax
  __int64 v9; // rdx
  int cbMultiByte; // esi
  CHAR *v11; // rdi
  CHAR *lpMultiByteStr; // rax
  const char *v13; // rbx
  DWORD LastError; // eax
  unsigned int v15; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, lpWideCharStr);
  v6 = -1;
  do
    ++v6;
  while ( lpWideCharStr[v6] );
  v7 = v6 + 1;
  v8 = WideCharToMultiByte(0, dwFlags, lpWideCharStr, v6 + 1, 0, 0, 0, 0);
  cbMultiByte = v8;
  if ( v8 )
  {
    lpMultiByteStr = (CHAR *)FwAlloc(v8, v9);
    v11 = lpMultiByteStr;
    if ( !lpMultiByteStr )
    {
      v13 = "FwAlloc";
      LastError = 8;
      goto LABEL_12;
    }
    if ( WideCharToMultiByte(0, dwFlags, lpWideCharStr, v7, lpMultiByteStr, cbMultiByte, 0, 0) )
    {
      v15 = 0;
      *a3 = v11;
      return v15;
    }
  }
  else
  {
    v11 = 0;
  }
  v13 = "WideCharToMultiByte";
  LastError = GetLastError();
LABEL_12:
  v15 = FwReportErrorAsWinError("FwStringCopyWtoAAlloc", v13, LastError);
  if ( (v15 & 0x80000000) != 0 )
  {
    FwFree(v11);
    return (unsigned int)FwReportReturnError("FwStringCopyWtoAAlloc", v15);
  }
  return v15;
}

```

## disassembly

```asm
0x1800210b0  push    rbx
0x1800210b2  push    rbp
0x1800210b3  push    rsi
0x1800210b4  push    rdi
0x1800210b5  push    r12
0x1800210b7  push    r14
0x1800210b9  push    r15
0x1800210bb  sub     rsp, 40h
0x1800210bf  mov     r14, r8
0x1800210c2  mov     ebp, edx
0x1800210c4  mov     rbx, rcx
0x1800210c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210ce  lea     rax, WPP_GLOBAL_Control
0x1800210d5  cmp     rcx, rax
0x1800210d8  jz      short loc_1800210F8
0x1800210da  test    byte ptr [rcx+1Ch], 4
0x1800210de  jz      short loc_1800210F8
0x1800210e0  mov     rcx, [rcx+10h]
0x1800210e4  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x1800210eb  mov     edx, 0Bh
0x1800210f0  mov     r9, rbx
0x1800210f3  call    WPP_SF_S
0x1800210f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800210fc  xor     r12d, r12d
0x1800210ff  inc     rax
0x180021102  cmp     [rbx+rax*2], r12w
0x180021107  jnz     short loc_1800210FF
0x180021109  mov     [rsp+78h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18002110e  lea     r15d, [rax+1]
0x180021112  mov     [rsp+78h+lpDefaultChar], r12; lpDefaultChar
0x180021117  mov     r9d, r15d; cchWideChar
0x18002111a  mov     [rsp+78h+cbMultiByte], r12d; cbMultiByte
0x18002111f  mov     r8, rbx; lpWideCharStr
0x180021122  mov     edx, ebp; dwFlags
0x180021124  mov     [rsp+78h+lpMultiByteStr], r12; lpMultiByteStr
0x180021129  xor     ecx, ecx; CodePage
0x18002112b  call    cs:__imp_WideCharToMultiByte
0x180021131  mov     esi, eax
0x180021133  test    eax, eax
0x180021135  jnz     short loc_18002113C
0x180021137  mov     rdi, r12
0x18002113a  jmp     short loc_18002117F
0x18002113c  mov     rcx, rsi
0x18002113f  call    FwAlloc
0x180021144  mov     rdi, rax
0x180021147  test    rax, rax
0x18002114a  jnz     short loc_180021158
0x18002114c  lea     rbx, aFwalloc_0; "FwAlloc"
0x180021153  lea     eax, [rdi+8]
0x180021156  jmp     short loc_18002118C
0x180021158  mov     [rsp+78h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18002115d  mov     r9d, r15d; cchWideChar
0x180021160  mov     [rsp+78h+lpDefaultChar], r12; lpDefaultChar
0x180021165  mov     r8, rbx; lpWideCharStr
0x180021168  mov     [rsp+78h+cbMultiByte], esi; cbMultiByte
0x18002116c  mov     edx, ebp; dwFlags
0x18002116e  xor     ecx, ecx; CodePage
0x180021170  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x180021175  call    cs:__imp_WideCharToMultiByte
0x18002117b  test    eax, eax
0x18002117d  jnz     short loc_1800211BE
0x18002117f  lea     rbx, aWidechartomult; "WideCharToMultiByte"
0x180021186  call    cs:__imp_GetLastError
0x18002118c  mov     r8d, eax
0x18002118f  lea     rcx, aFwstringcopywt_0; "FwStringCopyWtoAAlloc"
0x180021196  mov     rdx, rbx
0x180021199  call    FwReportErrorAsWinError
0x18002119e  mov     ebx, eax
0x1800211a0  test    eax, eax
0x1800211a2  jns     short loc_1800211C4
0x1800211a4  mov     rcx, rdi
0x1800211a7  call    FwFree
0x1800211ac  mov     edx, ebx
0x1800211ae  lea     rcx, aFwstringcopywt_0; "FwStringCopyWtoAAlloc"
0x1800211b5  call    FwReportReturnError
0x1800211ba  mov     ebx, eax
0x1800211bc  jmp     short loc_1800211C4
0x1800211be  mov     ebx, r12d
0x1800211c1  mov     [r14], rdi
0x1800211c4  mov     eax, ebx
0x1800211c6  add     rsp, 40h
0x1800211ca  pop     r15
0x1800211cc  pop     r14
0x1800211ce  pop     r12
0x1800211d0  pop     rdi
0x1800211d1  pop     rsi
0x1800211d2  pop     rbp
0x1800211d3  pop     rbx
0x1800211d4  retn
```
