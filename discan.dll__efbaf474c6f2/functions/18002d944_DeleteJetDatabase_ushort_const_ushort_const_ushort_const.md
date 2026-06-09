# DeleteJetDatabase(ushort const *,ushort const *,ushort const *)

- ea: `0x18002d944`
- end: `0x18002dcf0`
- name: `?DeleteJetDatabase@@YAXPEBG00@Z`
- size: `940`
- prototype: `void __fastcall(LPCWSTR lpString1, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002e168`

## callees

- `0x180002518`
- `0x180006498`
- `0x1800128c8`
- `0x18002d944`
- `0x18002e61c`
- `0x18002e684`
- `0x18002e6dc`
- `0x1800375ee`
- `0x180037620`

## import_xrefs

- `KERNEL32!FindClose` at `0x18002dbe7`
- `KERNEL32!FindClose` at `0x18002dbe7`
- `KERNEL32!FindNextFileW` at `0x18002db7e`
- `KERNEL32!FindNextFileW` at `0x18002db7e`
- `KERNEL32!FindFirstFileW` at `0x18002daa9`
- `KERNEL32!FindFirstFileW` at `0x18002daa9`
- `KERNEL32!DeleteFileW` at `0x18002d9a0`
- `KERNEL32!DeleteFileW` at `0x18002db20`
- `KERNEL32!DeleteFileW` at `0x18002d9a0`
- `KERNEL32!DeleteFileW` at `0x18002db20`
- `KERNEL32!GetLastError` at `0x18002d9b1`
- `KERNEL32!GetLastError` at `0x18002d9d4`
- `KERNEL32!GetLastError` at `0x18002db49`
- `KERNEL32!GetLastError` at `0x18002db8c`
- `KERNEL32!GetLastError` at `0x18002dbb6`
- `KERNEL32!GetLastError` at `0x18002dc25`
- `KERNEL32!GetLastError` at `0x18002d9b1`
- `KERNEL32!GetLastError` at `0x18002d9d4`
- `KERNEL32!GetLastError` at `0x18002db49`
- `KERNEL32!GetLastError` at `0x18002db8c`
- `KERNEL32!GetLastError` at `0x18002dbb6`
- `KERNEL32!GetLastError` at `0x18002dc25`
- `KERNEL32!lstrcmpiW` at `0x18002da26`
- `KERNEL32!lstrcmpiW` at `0x18002da26`

## pseudocode

```c
void __fastcall DeleteJetDatabase(LPCWSTR lpString1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  size_t *v6; // r8
  char LastError; // al
  __int64 v8; // rdi
  const WCHAR *v9; // rbx
  HRESULT v10; // eax
  unsigned __int64 v11; // rsi
  size_t v12; // r15
  unsigned __int16 *v13; // r14
  HANDLE FirstFileW; // rbx
  int v15; // eax
  _QWORD *v16; // rcx
  int v17; // edx
  wchar_t *cFileName; // r9
  DWORD v19; // eax
  DWORD v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  wchar_t *v23; // r9
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  size_t pcchLength; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpString2[3]; // [rsp+38h] [rbp-C8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  pcchLength = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpString2[0] = lpString1;
  lpString2[1] = a2;
  if ( !DeleteFileW(a3)
    && GetLastError() != 2
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids,
      (_DWORD)a3,
      LastError);
  }
  v8 = 0;
LABEL_8:
  if ( (unsigned int)v8 >= 2 )
    return;
  v9 = lpString2[v8];
  if ( (_DWORD)v8 )
  {
    if ( lpString1 == v9 || !lstrcmpiW(lpString1, lpString2[v8]) )
      return;
  }
  v10 = StringCopyWorkerW(pszDest, 0x104u, v6, v9, cchToCopy);
  if ( v10 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    v22 = 11;
    goto LABEL_53;
  }
  v10 = StringLengthWorkerW(pszDest, 0x104u, &pcchLength);
  if ( v10 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    v22 = 12;
    v23 = pszDest;
LABEL_54:
    WPP_SF_Sd(v21[2], v22, (unsigned int)WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, (_DWORD)v23, v10);
    return;
  }
  v11 = 260 - pcchLength;
  v12 = 2 * pcchLength;
  v13 = &pszDest[pcchLength];
  v10 = StringCchCatW(v13, 260 - pcchLength, L"*");
  if ( v10 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    v22 = 13;
LABEL_53:
    LODWORD(v23) = (_DWORD)v9;
    goto LABEL_54;
  }
  FirstFileW = FindFirstFileW(pszDest, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( v12 >= 0x208 )
          _report_rangecheckfailure();
        *v13 = 0;
        v15 = StringCchCatW(v13, v11, FindFileData.cFileName);
        if ( v15 >= 0 )
        {
          if ( DeleteFileW(pszDest)
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_29;
          }
          LOBYTE(v15) = GetLastError();
          v16 = WPP_GLOBAL_Control;
          cFileName = pszDest;
          v17 = 16;
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_29;
          }
          v17 = 15;
          cFileName = FindFileData.cFileName;
        }
        WPP_SF_Sd(v16[2], v17, (unsigned int)WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, (_DWORD)cFileName, v15);
      }
LABEL_29:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        if ( GetLastError() != 18
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, v19);
        }
        FindClose(FirstFileW);
        v8 = (unsigned int)(v8 + 1);
        goto LABEL_8;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, v20);
  }
}

```

## disassembly

```asm
0x18002d944  push    rbp
0x18002d946  push    rbx
0x18002d947  push    rsi
0x18002d948  push    rdi
0x18002d949  push    r12
0x18002d94b  push    r14
0x18002d94d  push    r15
0x18002d94f  lea     rbp, [rsp-3C0h]
0x18002d957  sub     rsp, 4C0h
0x18002d95e  mov     rax, cs:__security_cookie
0x18002d965  xor     rax, rsp
0x18002d968  mov     [rbp+3F0h+var_40], rax
0x18002d96f  mov     rdi, r8
0x18002d972  mov     [rsp+4F0h+pcchLength], 0
0x18002d97b  mov     rbx, rdx
0x18002d97e  mov     r12, rcx
0x18002d981  xor     edx, edx; Val
0x18002d983  lea     rcx, [rsp+4F0h+FindFileData]; void *
0x18002d988  mov     r8d, 250h; Size
0x18002d98e  call    memset_0
0x18002d993  mov     rcx, rdi; lpFileName
0x18002d996  mov     [rsp+4F0h+lpString2], r12
0x18002d99b  mov     [rsp+4F0h+var_4B0], rbx
0x18002d9a0  call    cs:__imp_DeleteFileW
0x18002d9a6  lea     rsi, WPP_GLOBAL_Control
0x18002d9ad  test    eax, eax
0x18002d9af  jnz     short loc_18002D9FD
0x18002d9b1  call    cs:__imp_GetLastError
0x18002d9b7  cmp     eax, 2
0x18002d9ba  jz      short loc_18002D9FD
0x18002d9bc  mov     rax, cs:WPP_GLOBAL_Control
0x18002d9c3  cmp     rax, rsi
0x18002d9c6  jz      short loc_18002D9FD
0x18002d9c8  test    byte ptr [rax+1Ch], 1
0x18002d9cc  jz      short loc_18002D9FD
0x18002d9ce  cmp     byte ptr [rax+19h], 2
0x18002d9d2  jb      short loc_18002D9FD
0x18002d9d4  call    cs:__imp_GetLastError
0x18002d9da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9e1  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002d9e8  mov     edx, 0Ah
0x18002d9ed  mov     dword ptr [rsp+4F0h+cchToCopy], eax; cchToCopy
0x18002d9f1  mov     r9, rdi
0x18002d9f4  mov     rcx, [rcx+10h]
0x18002d9f8  call    WPP_SF_Sd
0x18002d9fd  xor     edi, edi
0x18002d9ff  mov     r14d, 104h
0x18002da05  cmp     edi, 2
0x18002da08  jnb     loc_18002DCCF
0x18002da0e  mov     rbx, [rsp+rdi*8+4F0h+lpString2]
0x18002da13  test    edi, edi
0x18002da15  jz      short loc_18002DA34
0x18002da17  cmp     r12, rbx
0x18002da1a  jz      loc_18002DCCF
0x18002da20  mov     rdx, rbx; lpString2
0x18002da23  mov     rcx, r12; lpString1
0x18002da26  call    cs:__imp_lstrcmpiW
0x18002da2c  test    eax, eax
0x18002da2e  jz      loc_18002DCCF
0x18002da34  mov     r9, rbx; pszSrc
0x18002da37  lea     rcx, [rbp+3F0h+pszDest]; pszDest
0x18002da3e  mov     rdx, r14; cchDest
0x18002da41  call    StringCopyWorkerW
0x18002da46  test    eax, eax
0x18002da48  js      loc_18002DC9B
0x18002da4e  lea     r8, [rsp+4F0h+pcchLength]; pcchLength
0x18002da53  mov     rdx, r14; cchMax
0x18002da56  lea     rcx, [rbp+3F0h+pszDest]; psz
0x18002da5d  call    StringLengthWorkerW
0x18002da62  test    eax, eax
0x18002da64  js      loc_18002DC75
0x18002da6a  mov     rax, [rsp+4F0h+pcchLength]
0x18002da6f  lea     r8, asc_18003F010; "*"
0x18002da76  mov     rsi, r14
0x18002da79  lea     r14, [rbp+3F0h+pszDest]
0x18002da80  sub     rsi, rax
0x18002da83  mov     rdx, rsi; unsigned __int64
0x18002da86  lea     r15, [rax+rax]
0x18002da8a  add     r14, r15
0x18002da8d  mov     rcx, r14; unsigned __int16 *
0x18002da90  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002da95  test    eax, eax
0x18002da97  js      loc_18002DC4F
0x18002da9d  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18002daa2  lea     rcx, [rbp+3F0h+pszDest]; lpFileName
0x18002daa9  call    cs:__imp_FindFirstFileW
0x18002daaf  mov     rbx, rax
0x18002dab2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002dab6  jz      loc_18002DBFA
0x18002dabc  test    byte ptr [rsp+4F0h+FindFileData.dwFileAttributes], 10h
0x18002dac1  jnz     loc_18002DB76
0x18002dac7  cmp     r15, 208h
0x18002dace  jnb     loc_18002DBF4
0x18002dad4  xor     ecx, ecx
0x18002dad6  lea     r8, [rsp+4F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002dadb  mov     [r14], cx
0x18002dadf  mov     rdx, rsi; unsigned __int64
0x18002dae2  mov     rcx, r14; unsigned __int16 *
0x18002dae5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002daea  test    eax, eax
0x18002daec  jns     short loc_18002DB19
0x18002daee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daf5  lea     rdx, WPP_GLOBAL_Control
0x18002dafc  cmp     rcx, rdx
0x18002daff  jz      short loc_18002DB76
0x18002db01  test    byte ptr [rcx+1Ch], 1
0x18002db05  jz      short loc_18002DB76
0x18002db07  cmp     byte ptr [rcx+19h], 2
0x18002db0b  jb      short loc_18002DB76
0x18002db0d  mov     edx, 0Fh
0x18002db12  lea     r9, [rsp+4F0h+FindFileData.cFileName]
0x18002db17  jmp     short loc_18002DB62
0x18002db19  lea     rcx, [rbp+3F0h+pszDest]; lpFileName
0x18002db20  call    cs:__imp_DeleteFileW
0x18002db26  test    eax, eax
0x18002db28  jnz     short loc_18002DB76
0x18002db2a  mov     rax, cs:WPP_GLOBAL_Control
0x18002db31  lea     rcx, WPP_GLOBAL_Control
0x18002db38  cmp     rax, rcx
0x18002db3b  jz      short loc_18002DB76
0x18002db3d  test    byte ptr [rax+1Ch], 1
0x18002db41  jz      short loc_18002DB76
0x18002db43  cmp     byte ptr [rax+19h], 2
0x18002db47  jb      short loc_18002DB76
0x18002db49  call    cs:__imp_GetLastError
0x18002db4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db56  lea     r9, [rbp+3F0h+pszDest]
0x18002db5d  mov     edx, 10h
0x18002db62  mov     rcx, [rcx+10h]
0x18002db66  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002db6d  mov     dword ptr [rsp+4F0h+cchToCopy], eax
0x18002db71  call    WPP_SF_Sd
0x18002db76  lea     rdx, [rsp+4F0h+FindFileData]; lpFindFileData
0x18002db7b  mov     rcx, rbx; hFindFile
0x18002db7e  call    cs:__imp_FindNextFileW
0x18002db84  test    eax, eax
0x18002db86  jnz     loc_18002DABC
0x18002db8c  call    cs:__imp_GetLastError
0x18002db92  cmp     eax, 12h
0x18002db95  jz      short loc_18002DBDD
0x18002db97  mov     rax, cs:WPP_GLOBAL_Control
0x18002db9e  lea     rsi, WPP_GLOBAL_Control
0x18002dba5  cmp     rax, rsi
0x18002dba8  jz      short loc_18002DBE4
0x18002dbaa  test    byte ptr [rax+1Ch], 1
0x18002dbae  jz      short loc_18002DBE4
0x18002dbb0  cmp     byte ptr [rax+19h], 2
0x18002dbb4  jb      short loc_18002DBE4
0x18002dbb6  call    cs:__imp_GetLastError
0x18002dbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbc3  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002dbca  mov     edx, 11h
0x18002dbcf  mov     r9d, eax
0x18002dbd2  mov     rcx, [rcx+10h]
0x18002dbd6  call    WPP_SF_d
0x18002dbdb  jmp     short loc_18002DBE4
0x18002dbdd  lea     rsi, WPP_GLOBAL_Control
0x18002dbe4  mov     rcx, rbx; hFindFile
0x18002dbe7  call    cs:__imp_FindClose
0x18002dbed  inc     edi
0x18002dbef  jmp     loc_18002D9FF
0x18002dbf4  call    __report_rangecheckfailure
0x18002dbfa  mov     rax, cs:WPP_GLOBAL_Control
0x18002dc01  lea     rcx, WPP_GLOBAL_Control
0x18002dc08  cmp     rax, rcx
0x18002dc0b  jz      loc_18002DCCF
0x18002dc11  test    byte ptr [rax+1Ch], 1
0x18002dc15  jz      loc_18002DCCF
0x18002dc1b  cmp     byte ptr [rax+19h], 2
0x18002dc1f  jb      loc_18002DCCF
0x18002dc25  call    cs:__imp_GetLastError
0x18002dc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc32  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002dc39  mov     edx, 0Eh
0x18002dc3e  mov     r9d, eax
0x18002dc41  mov     rcx, [rcx+10h]
0x18002dc45  call    WPP_SF_d
0x18002dc4a  jmp     loc_18002DCCF
0x18002dc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc56  lea     rdx, WPP_GLOBAL_Control
0x18002dc5d  cmp     rcx, rdx
0x18002dc60  jz      short loc_18002DCCF
0x18002dc62  test    byte ptr [rcx+1Ch], 1
0x18002dc66  jz      short loc_18002DCCF
0x18002dc68  cmp     byte ptr [rcx+19h], 2
0x18002dc6c  jb      short loc_18002DCCF
0x18002dc6e  mov     edx, 0Dh
0x18002dc73  jmp     short loc_18002DCB8
0x18002dc75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc7c  cmp     rcx, rsi
0x18002dc7f  jz      short loc_18002DCCF
0x18002dc81  test    byte ptr [rcx+1Ch], 1
0x18002dc85  jz      short loc_18002DCCF
0x18002dc87  cmp     byte ptr [rcx+19h], 2
0x18002dc8b  jb      short loc_18002DCCF
0x18002dc8d  mov     edx, 0Ch
0x18002dc92  lea     r9, [rbp+3F0h+pszDest]
0x18002dc99  jmp     short loc_18002DCBB
0x18002dc9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dca2  cmp     rcx, rsi
0x18002dca5  jz      short loc_18002DCCF
0x18002dca7  test    byte ptr [rcx+1Ch], 1
0x18002dcab  jz      short loc_18002DCCF
0x18002dcad  cmp     byte ptr [rcx+19h], 2
0x18002dcb1  jb      short loc_18002DCCF
0x18002dcb3  mov     edx, 0Bh
0x18002dcb8  mov     r9, rbx
0x18002dcbb  mov     rcx, [rcx+10h]
0x18002dcbf  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002dcc6  mov     dword ptr [rsp+4F0h+cchToCopy], eax
0x18002dcca  call    WPP_SF_Sd
0x18002dccf  mov     rcx, [rbp+3F0h+var_40]
0x18002dcd6  xor     rcx, rsp; StackCookie
0x18002dcd9  call    __security_check_cookie
0x18002dcde  add     rsp, 4C0h
0x18002dce5  pop     r15
0x18002dce7  pop     r14
0x18002dce9  pop     r12
0x18002dceb  pop     rdi
0x18002dcec  pop     rsi
0x18002dced  pop     rbx
0x18002dcee  pop     rbp
0x18002dcef  retn
```
