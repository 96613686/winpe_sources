# FwGetLongPathName

- ea: `0x1800043a0`
- end: `0x1800045dd`
- name: `FwGetLongPathName`
- size: `573`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180002b30`
- `0x180003b30`

## callees

- `0x1800043a0`
- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x180004870`
- `0x1800130bc`
- `0x180017b58`
- `0x18001e1d0`
- `0x18002f674`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800043d8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800043d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045b3`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800044c1`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800044c1`

## string_xrefs

- `0x1800044ff`: `FwGetLongPathName`
- `0x180004517`: `FwGetLongPathName`
- `0x180004571`: `FwGetLongPathName`
- `0x18000457f`: `FwGetLongPathName`
- `0x180004535`: `FwStringCopy`
- `0x18000455f`: `FwStringCopy`
- `0x1800045a1`: `FwStringCopy`
- `0x1800044f8`: `GetLongPathNameW`

## pseudocode

```c
__int64 __fastcall FwGetLongPathName(_WORD *Src, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rdx
  int v7; // edi
  __int64 v8; // rax
  size_t v10; // rdi
  void *v11; // rax
  unsigned int v12; // ebx
  DWORD LongPathNameW; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  DWORD LastError; // eax
  WCHAR szLongPath[264]; // [rsp+30h] [rbp-248h] BYREF

  *a2 = 0;
  if ( !wcschr(Src, 0x7Eu) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, Src);
    *a2 = 0;
    v7 = 0;
    if ( Src )
    {
      v8 = -1;
      while ( Src[++v8] != 0 )
        ;
      if ( (unsigned __int64)(v8 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      {
        v7 = -2147024362;
        FwReportReturnError("FwStringCopy", 2147942934LL);
        v12 = -2147024362;
      }
      else
      {
        v10 = 2 * (v8 + 1);
        v11 = (void *)FwAlloc(v10, v6);
        *a2 = v11;
        if ( v11 )
        {
          memcpy_0(v11, Src, v10);
          v12 = 0;
LABEL_9:
          *a3 = 1;
          return v12;
        }
        v7 = FwReportErrorAsWinError("FwStringCopy", "FwAlloc", 8);
        v12 = v7;
        if ( v7 >= 0 )
          goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (unsigned int)"FwStringCopy", v7);
LABEL_23:
        v16 = (unsigned int)v7;
LABEL_24:
        FwReportReturnError("FwGetLongPathName", v16);
        return FwReportReturnError("FwGetLongPathName", v12);
      }
    }
LABEL_25:
    v12 = v7;
    if ( v7 >= 0 )
      goto LABEL_9;
    goto LABEL_23;
  }
  LongPathNameW = GetLongPathNameW(Src, szLongPath, 0x104u);
  if ( LongPathNameW )
  {
    if ( LongPathNameW >= 0x104 )
    {
      v12 = -2147024809;
      v16 = 2147942487LL;
    }
    else
    {
      v15 = FwStringCopy(szLongPath);
      v12 = v15;
      if ( v15 >= 0 )
        goto LABEL_9;
      v16 = (unsigned int)v15;
    }
    goto LABEL_24;
  }
  LastError = GetLastError();
  if ( LastError - 2 <= 1 )
  {
    *a3 = 0;
    return 0;
  }
  if ( !LastError )
    return 0;
  v17 = FwReportErrorAsWinError("FwGetLongPathName", "GetLongPathNameW", LastError);
  v12 = v17;
  if ( v17 >= 0 )
    return v12;
  return FwReportReturnError("FwGetLongPathName", (unsigned int)v17);
}

```

## disassembly

```asm
0x1800043a0  mov     [rsp+arg_18], rbx
0x1800043a5  push    rbp
0x1800043a6  push    rsi
0x1800043a7  push    rdi
0x1800043a8  push    r14
0x1800043aa  push    r15
0x1800043ac  sub     rsp, 250h
0x1800043b3  mov     rax, cs:__security_cookie
0x1800043ba  xor     rax, rsp
0x1800043bd  mov     [rsp+278h+var_38], rax
0x1800043c5  mov     rsi, rdx
0x1800043c8  xor     ebp, ebp
0x1800043ca  mov     [rdx], rbp
0x1800043cd  mov     r14, r8
0x1800043d0  mov     edx, 7Eh ; '~'; Ch
0x1800043d5  mov     rbx, rcx
0x1800043d8  call    cs:__imp_wcschr
0x1800043de  test    rax, rax
0x1800043e1  jnz     loc_1800044B3
0x1800043e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043ee  lea     r15, WPP_GLOBAL_Control
0x1800043f5  cmp     rcx, r15
0x1800043f8  jnz     loc_18000448C
0x1800043fe  mov     [rsi], rbp
0x180004401  mov     edi, ebp
0x180004403  test    rbx, rbx
0x180004406  jz      loc_180004590
0x18000440c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004413  cmp     [rbx+rax*2+2], di
0x180004418  lea     rax, [rax+1]
0x18000441c  jnz     short loc_180004413
0x18000441e  lea     rdi, [rax+1]
0x180004422  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000442c  cmp     rdi, rax
0x18000442f  ja      loc_18000459C
0x180004435  add     rdi, rdi
0x180004438  mov     rcx, rdi
0x18000443b  call    FwAlloc
0x180004440  mov     [rsi], rax
0x180004443  test    rax, rax
0x180004446  jz      loc_180004528
0x18000444c  mov     r8, rdi; Size
0x18000444f  mov     rdx, rbx; Src
0x180004452  mov     rcx, rax; void *
0x180004455  call    memcpy_0
0x18000445a  mov     ebx, ebp
0x18000445c  mov     dword ptr [r14], 1
0x180004463  mov     eax, ebx
0x180004465  mov     rcx, [rsp+278h+var_38]
0x18000446d  xor     rcx, rsp; StackCookie
0x180004470  call    __security_check_cookie
0x180004475  mov     rbx, [rsp+278h+arg_18]
0x18000447d  add     rsp, 250h
0x180004484  pop     r15
0x180004486  pop     r14
0x180004488  pop     rdi
0x180004489  pop     rsi
0x18000448a  pop     rbp
0x18000448b  retn
0x18000448c  test    byte ptr [rcx+1Ch], 4
0x180004490  jz      loc_1800043FE
0x180004496  mov     rcx, [rcx+10h]
0x18000449a  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x1800044a1  mov     edx, 0Dh
0x1800044a6  mov     r9, rbx
0x1800044a9  call    WPP_SF_S
0x1800044ae  jmp     loc_1800043FE
0x1800044b3  mov     r8d, 104h; cchBuffer
0x1800044b9  lea     rdx, [rsp+278h+szLongPath]; lpszLongPath
0x1800044be  mov     rcx, rbx; lpszShortPath
0x1800044c1  call    cs:__imp_GetLongPathNameW
0x1800044c7  test    eax, eax
0x1800044c9  jz      loc_1800045B3
0x1800044cf  cmp     eax, 104h
0x1800044d4  jnb     loc_1800045D4
0x1800044da  mov     rdx, rsi
0x1800044dd  lea     rcx, [rsp+278h+szLongPath]; Src
0x1800044e2  call    FwStringCopy
0x1800044e7  mov     ebx, eax
0x1800044e9  test    eax, eax
0x1800044eb  jns     loc_18000445C
0x1800044f1  mov     edx, eax
0x1800044f3  jmp     short loc_180004571
0x1800044f5  mov     r8d, eax
0x1800044f8  lea     rdx, aGetlongpathnam; "GetLongPathNameW"
0x1800044ff  lea     rcx, aFwgetlongpathn_0; "FwGetLongPathName"
0x180004506  call    FwReportErrorAsWinError
0x18000450b  mov     ebx, eax
0x18000450d  test    eax, eax
0x18000450f  jns     loc_180004463
0x180004515  mov     edx, eax
0x180004517  lea     rcx, aFwgetlongpathn_0; "FwGetLongPathName"
0x18000451e  call    FwReportReturnError
0x180004523  jmp     loc_180004465
0x180004528  mov     r8d, 8
0x18000452e  lea     rdx, aFwalloc_0; "FwAlloc"
0x180004535  lea     rcx, aFwstringcopy_0; "FwStringCopy"
0x18000453c  call    FwReportErrorAsWinError
0x180004541  mov     edi, eax
0x180004543  mov     ebx, eax
0x180004545  test    eax, eax
0x180004547  jns     short loc_180004590
0x180004549  mov     rcx, cs:WPP_GLOBAL_Control
0x180004550  cmp     rcx, r15
0x180004553  jz      short loc_180004590
0x180004555  test    byte ptr [rcx+1Ch], 1
0x180004559  jz      short loc_180004590
0x18000455b  mov     rcx, [rcx+10h]
0x18000455f  lea     r9, aFwstringcopy_0; "FwStringCopy"
0x180004566  mov     [rsp+278h+var_258], edi
0x18000456a  call    WPP_SF_sD
0x18000456f  mov     edx, edi
0x180004571  lea     rcx, aFwgetlongpathn_0; "FwGetLongPathName"
0x180004578  call    FwReportReturnError
0x18000457d  mov     edx, ebx
0x18000457f  lea     rcx, aFwgetlongpathn_0; "FwGetLongPathName"
0x180004586  call    FwReportReturnError
0x18000458b  jmp     loc_180004465
0x180004590  mov     ebx, edi
0x180004592  test    edi, edi
0x180004594  jns     loc_18000445C
0x18000459a  jmp     short loc_18000456F
0x18000459c  mov     edi, 80070216h
0x1800045a1  lea     rcx, aFwstringcopy_0; "FwStringCopy"
0x1800045a8  mov     edx, edi
0x1800045aa  call    FwReportReturnError
0x1800045af  mov     ebx, edi
0x1800045b1  jmp     short loc_180004549
0x1800045b3  call    cs:__imp_GetLastError
0x1800045b9  lea     ecx, [rax-2]
0x1800045bc  cmp     ecx, 1
0x1800045bf  jbe     short loc_1800045CA
0x1800045c1  test    eax, eax
0x1800045c3  jz      short loc_1800045CD
0x1800045c5  jmp     loc_1800044F5
0x1800045ca  mov     [r14], ebp
0x1800045cd  mov     ebx, ebp
0x1800045cf  jmp     loc_180004463
0x1800045d4  mov     ebx, 80070057h
0x1800045d9  mov     edx, ebx
0x1800045db  jmp     short loc_180004571
```
