# KpsUtf8String2UnicodeString(char *,ushort * *)

- ea: `0x18002b24c`
- end: `0x18002b4da`
- name: `?KpsUtf8String2UnicodeString@@YAKPEADPEAPEAG@Z`
- size: `654`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180027af8`
- `0x18002a5a8`
- `0x18002aae8`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x180026a08`
- `0x18002b24c`
- `0x1800300f4`
- `0x18003012c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3e9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2c6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3d9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2c6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3d9`

## string_xrefs

- `0x18002b312`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002b46b`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsUtf8String2UnicodeString(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  unsigned __int16 *v4; // rsi
  unsigned int v6; // eax
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  int v9; // edx
  int v10; // r9d
  unsigned __int64 v11; // rdi
  WCHAR *lpWideCharStr; // rax
  _QWORD *v13; // rcx
  int v14; // edx
  __int64 cchWideChar; // [rsp+28h] [rbp-20h]

  v2 = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
  if ( !lpMultiByteStr )
  {
    *a2 = 0;
    goto LABEL_35;
  }
  v6 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, 0, 0);
  if ( !v6 )
  {
    LastError = GetLastError();
    v2 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 76;
      LODWORD(cchWideChar) = 1415;
LABEL_10:
      v10 = LastError;
LABEL_11:
      WPP_SF_Dsd(
        v8[2],
        v9,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v10,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        cchWideChar);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( v6 + 1 < v6 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v14 = 77;
    LODWORD(cchWideChar) = 1427;
    goto LABEL_33;
  }
  v11 = 2LL * (v6 + 1);
  if ( v11 > 0xFFFFFFFF )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v14 = 78;
    LODWORD(cchWideChar) = 1439;
LABEL_33:
    WPP_SF_Dsd(
      v13[2],
      v14,
      (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
      -1073741675,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
      cchWideChar);
LABEL_34:
    v2 = -1073741675;
    goto LABEL_35;
  }
  if ( (unsigned int)v11 <= 0xFFFE )
  {
    lpWideCharStr = (WCHAR *)KpsAllocMem((unsigned int)v11);
    v4 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, lpWideCharStr, v11) )
      {
        *a2 = v4;
        v4 = 0;
        goto LABEL_35;
      }
      LastError = GetLastError();
      v2 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 81;
        LODWORD(cchWideChar) = 1471;
        goto LABEL_10;
      }
    }
    else
    {
      v10 = 8;
      v2 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 80;
        LODWORD(cchWideChar) = 1455;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v10 = 8;
    v2 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 79;
      LODWORD(cchWideChar) = 1446;
      goto LABEL_11;
    }
  }
LABEL_35:
  KpsFreeMem(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18002b24c  mov     rax, rsp
0x18002b24f  mov     [rax+8], rbx
0x18002b253  mov     [rax+10h], rbp
0x18002b257  mov     [rax+18h], rsi
0x18002b25b  mov     [rax+20h], rdi
0x18002b25f  push    r12
0x18002b261  push    r14
0x18002b263  push    r15
0x18002b265  sub     rsp, 30h
0x18002b269  xor     ebx, ebx
0x18002b26b  mov     r14, rdx
0x18002b26e  mov     esi, ebx
0x18002b270  mov     rbp, rcx
0x18002b273  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b27a  lea     r15, WPP_GLOBAL_Control
0x18002b281  lea     r12, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b288  cmp     rcx, r15
0x18002b28b  jz      short loc_18002B2A2
0x18002b28d  test    byte ptr [rcx+1Ch], 20h
0x18002b291  jz      short loc_18002B2A2
0x18002b293  mov     rcx, [rcx+10h]
0x18002b297  lea     edx, [rbx+4Bh]
0x18002b29a  mov     r8, r12
0x18002b29d  call    WPP_SF_
0x18002b2a2  test    rbp, rbp
0x18002b2a5  jnz     short loc_18002B2AF
0x18002b2a7  mov     [r14], rbx
0x18002b2aa  jmp     loc_18002B48A
0x18002b2af  mov     dword ptr [rsp+48h+cchWideChar], ebx; cchWideChar
0x18002b2b3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002b2b7  mov     r8, rbp; lpMultiByteStr
0x18002b2ba  mov     [rsp+48h+lpWideCharStr], rbx; lpWideCharStr
0x18002b2bf  xor     edx, edx; dwFlags
0x18002b2c1  mov     ecx, 0FDE9h; CodePage
0x18002b2c6  call    cs:__imp_MultiByteToWideChar
0x18002b2cd  nop     dword ptr [rax+rax+00h]
0x18002b2d2  test    eax, eax
0x18002b2d4  jnz     short loc_18002B32B
0x18002b2d6  call    cs:__imp_GetLastError
0x18002b2dd  nop     dword ptr [rax+rax+00h]
0x18002b2e2  mov     ebx, eax
0x18002b2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2eb  cmp     rcx, r15
0x18002b2ee  jz      loc_18002B48A
0x18002b2f4  test    byte ptr [rcx+1Ch], 1
0x18002b2f8  jz      loc_18002B48A
0x18002b2fe  mov     edx, 4Ch ; 'L'
0x18002b303  mov     dword ptr [rsp+48h+cchWideChar], 587h
0x18002b30b  mov     r9d, eax
0x18002b30e  mov     rcx, [rcx+10h]
0x18002b312  lea     r8, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002b319  mov     [rsp+48h+lpWideCharStr], r8
0x18002b31e  mov     r8, r12
0x18002b321  call    WPP_SF_Dsd
0x18002b326  jmp     loc_18002B48A
0x18002b32b  lea     ecx, [rax+1]
0x18002b32e  cmp     ecx, eax
0x18002b330  jb      loc_18002B448
0x18002b336  mov     edi, ecx
0x18002b338  mov     eax, 0FFFFFFFFh
0x18002b33d  add     rdi, rdi
0x18002b340  cmp     rdi, rax
0x18002b343  ja      loc_18002B427
0x18002b349  cmp     edi, 0FFFEh
0x18002b34f  jbe     short loc_18002B382
0x18002b351  mov     r9d, 8
0x18002b357  mov     ebx, r9d
0x18002b35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b361  cmp     rcx, r15
0x18002b364  jz      loc_18002B48A
0x18002b36a  test    byte ptr [rcx+1Ch], 1
0x18002b36e  jz      loc_18002B48A
0x18002b374  lea     edx, [r9+47h]
0x18002b378  mov     dword ptr [rsp+48h+cchWideChar], 5A6h
0x18002b380  jmp     short loc_18002B30E
0x18002b382  mov     ecx, edi; unsigned __int64
0x18002b384  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18002b389  mov     rsi, rax
0x18002b38c  test    rax, rax
0x18002b38f  jnz     short loc_18002B3C2
0x18002b391  lea     r9d, [rax+8]
0x18002b395  mov     ebx, r9d
0x18002b398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b39f  cmp     rcx, r15
0x18002b3a2  jz      loc_18002B48A
0x18002b3a8  test    byte ptr [rcx+1Ch], 1
0x18002b3ac  jz      loc_18002B48A
0x18002b3b2  lea     edx, [rax+50h]
0x18002b3b5  mov     dword ptr [rsp+48h+cchWideChar], 5AFh
0x18002b3bd  jmp     loc_18002B30E
0x18002b3c2  mov     dword ptr [rsp+48h+cchWideChar], edi; cchWideChar
0x18002b3c6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002b3ca  mov     r8, rbp; lpMultiByteStr
0x18002b3cd  mov     [rsp+48h+lpWideCharStr], rsi; lpWideCharStr
0x18002b3d2  xor     edx, edx; dwFlags
0x18002b3d4  mov     ecx, 0FDE9h; CodePage
0x18002b3d9  call    cs:__imp_MultiByteToWideChar
0x18002b3e0  nop     dword ptr [rax+rax+00h]
0x18002b3e5  test    eax, eax
0x18002b3e7  jnz     short loc_18002B41F
0x18002b3e9  call    cs:__imp_GetLastError
0x18002b3f0  nop     dword ptr [rax+rax+00h]
0x18002b3f5  mov     ebx, eax
0x18002b3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3fe  cmp     rcx, r15
0x18002b401  jz      loc_18002B48A
0x18002b407  test    byte ptr [rcx+1Ch], 1
0x18002b40b  jz      short loc_18002B48A
0x18002b40d  mov     edx, 51h ; 'Q'
0x18002b412  mov     dword ptr [rsp+48h+cchWideChar], 5BFh
0x18002b41a  jmp     loc_18002B30B
0x18002b41f  mov     [r14], rsi
0x18002b422  mov     rsi, rbx
0x18002b425  jmp     short loc_18002B48A
0x18002b427  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b42e  cmp     rcx, r15
0x18002b431  jz      short loc_18002B485
0x18002b433  test    byte ptr [rcx+1Ch], 1
0x18002b437  jz      short loc_18002B485
0x18002b439  mov     edx, 4Eh ; 'N'
0x18002b43e  mov     dword ptr [rsp+48h+cchWideChar], 59Fh
0x18002b446  jmp     short loc_18002B467
0x18002b448  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b44f  cmp     rcx, r15
0x18002b452  jz      short loc_18002B485
0x18002b454  test    byte ptr [rcx+1Ch], 1
0x18002b458  jz      short loc_18002B485
0x18002b45a  mov     edx, 4Dh ; 'M'
0x18002b45f  mov     dword ptr [rsp+48h+cchWideChar], 593h
0x18002b467  mov     rcx, [rcx+10h]
0x18002b46b  lea     r8, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002b472  mov     [rsp+48h+lpWideCharStr], r8
0x18002b477  mov     r9d, 0C0000095h
0x18002b47d  mov     r8, r12
0x18002b480  call    WPP_SF_Dsd
0x18002b485  mov     ebx, 0C0000095h
0x18002b48a  mov     rcx, rsi; lpMem
0x18002b48d  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002b492  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b499  cmp     rcx, r15
0x18002b49c  jz      short loc_18002B4B8
0x18002b49e  test    byte ptr [rcx+1Ch], 20h
0x18002b4a2  jz      short loc_18002B4B8
0x18002b4a4  mov     rcx, [rcx+10h]
0x18002b4a8  mov     edx, 52h ; 'R'
0x18002b4ad  mov     r9d, ebx
0x18002b4b0  mov     r8, r12
0x18002b4b3  call    WPP_SF_D
0x18002b4b8  mov     rbp, [rsp+48h+arg_8]
0x18002b4bd  mov     eax, ebx
0x18002b4bf  mov     rbx, [rsp+48h+arg_0]
0x18002b4c4  mov     rsi, [rsp+48h+arg_10]
0x18002b4c9  mov     rdi, [rsp+48h+arg_18]
0x18002b4ce  add     rsp, 30h
0x18002b4d2  pop     r15
0x18002b4d4  pop     r14
0x18002b4d6  pop     r12
0x18002b4d8  retn
```
