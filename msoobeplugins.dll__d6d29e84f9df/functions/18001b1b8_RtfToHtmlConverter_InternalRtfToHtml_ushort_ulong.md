# RtfToHtmlConverter::InternalRtfToHtml(ushort *,ulong)

- ea: `0x18001b1b8`
- end: `0x18001b3b3`
- name: `?InternalRtfToHtml@RtfToHtmlConverter@@IEAAJPEAGK@Z`
- size: `507`
- prototype: `int(RtfToHtmlConverter *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001adf0`

## callees

- `0x180003470`
- `0x180008b54`
- `0x18001b1b8`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b2b7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b2b7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b31b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b31b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b37c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b37c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001b236`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001b236`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b26b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b26b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b2a7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b2a7`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001b28a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001b28a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001b324`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001b324`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001b2ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001b2ee`

## pseudocode

```c
__int64 __fastcall RtfToHtmlConverter::InternalRtfToHtml(RtfToHtmlConverter *this, unsigned __int16 *a2)
{
  unsigned __int64 v4; // rax
  HGLOBAL v5; // rbx
  HANDLE FileW; // rax
  wchar_t *v7; // rax
  CHAR *v8; // rax
  __int64 v9; // r8
  unsigned int v10; // esi
  WCHAR TempFileName[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR PathName[264]; // [rsp+250h] [rbp-238h] BYREF

  TempFileName[0] = 0;
  PathName[0] = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !*a2 )
    return (unsigned int)-2147024809;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 <= 4 )
    return (unsigned int)-2147024809;
  v5 = 0;
  if ( *(_DWORD *)this )
  {
    v5 = GlobalAlloc(2u, 0x104u);
    if ( v5 )
    {
      FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
      *((_QWORD *)this + 1) = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        GetTempPath2W(260, PathName);
        GetTempFileNameW(PathName, L"u2h", 0, TempFileName);
        v7 = wcsrchr(TempFileName, 0x2Eu);
        if ( v7 )
          StringCchCopyW(&TempFileName[(int)(v7 - TempFileName) + 1], 259LL - (int)(v7 - TempFileName), L"htm");
        v8 = (CHAR *)GlobalLock(v5);
        if ( v8 )
        {
          WideCharToMultiByte(1u, 0, TempFileName, -1, v8, 260, 0, 0);
          GlobalUnlock(v5);
          v9 = *((_QWORD *)this + 3);
          g_RtfConverter = (HANDLE)*((_QWORD *)this + 1);
          if ( !(*((unsigned __int16 (__fastcall **)(HGLOBAL, _QWORD, __int64, _QWORD, __int16 (__fastcall *)(int *, int)))this
                 + 5))(
                  v5,
                  0,
                  v9,
                  0,
                  FeedExternalRtfToConverter) )
          {
            v10 = 0;
            StringCchCopyW(a2, 0x104u, TempFileName);
LABEL_15:
            GlobalFree(v5);
            return v10;
          }
        }
      }
    }
  }
  v10 = -2147467259;
  if ( v5 )
    goto LABEL_15;
  return v10;
}

```

## disassembly

```asm
0x18001b1b8  mov     [rsp+arg_10], rbx
0x18001b1bd  mov     [rsp+arg_18], rbp
0x18001b1c2  push    rsi
0x18001b1c3  push    rdi
0x18001b1c4  push    r14
0x18001b1c6  sub     rsp, 470h
0x18001b1cd  mov     rax, cs:__security_cookie
0x18001b1d4  xor     rax, rsp
0x18001b1d7  mov     [rsp+488h+var_28], rax
0x18001b1df  xor     ebp, ebp
0x18001b1e1  mov     rdi, rdx
0x18001b1e4  mov     [rsp+488h+TempFileName], bp
0x18001b1e9  mov     rsi, rcx
0x18001b1ec  mov     [rsp+488h+PathName], bp
0x18001b1f4  test    rdx, rdx
0x18001b1f7  jz      loc_18001B384
0x18001b1fd  cmp     [rdx], bp
0x18001b200  jz      loc_18001B384
0x18001b206  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b20a  inc     rax
0x18001b20d  cmp     [rdx+rax*2], bp
0x18001b211  jnz     short loc_18001B20A
0x18001b213  cmp     rax, 4
0x18001b217  jbe     loc_18001B384
0x18001b21d  mov     rbx, rbp
0x18001b220  cmp     [rcx], ebp
0x18001b222  jz      loc_18001B36F
0x18001b228  mov     r14d, 104h
0x18001b22e  mov     ecx, 2; uFlags
0x18001b233  mov     edx, r14d; dwBytes
0x18001b236  call    cs:__imp_GlobalAlloc
0x18001b23c  mov     rbx, rax
0x18001b23f  test    rax, rax
0x18001b242  jz      loc_18001B36F
0x18001b248  mov     [rsp+488h+hTemplateFile], rbp; hTemplateFile
0x18001b24d  xor     r9d, r9d; lpSecurityAttributes
0x18001b250  mov     [rsp+488h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001b258  xor     r8d, r8d; dwShareMode
0x18001b25b  mov     edx, 80000000h; dwDesiredAccess
0x18001b260  mov     [rsp+488h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b268  mov     rcx, rdi; lpFileName
0x18001b26b  call    cs:__imp_CreateFileW
0x18001b271  mov     [rsi+8], rax
0x18001b275  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b279  jz      loc_18001B36F
0x18001b27f  lea     rdx, [rsp+488h+PathName]
0x18001b287  mov     ecx, r14d
0x18001b28a  call    cs:__imp_GetTempPath2W
0x18001b290  lea     r9, [rsp+488h+TempFileName]; lpTempFileName
0x18001b295  xor     r8d, r8d; uUnique
0x18001b298  lea     rdx, aU2h; "u2h"
0x18001b29f  lea     rcx, [rsp+488h+PathName]; lpPathName
0x18001b2a7  call    cs:__imp_GetTempFileNameW
0x18001b2ad  mov     edx, 2Eh ; '.'; Ch
0x18001b2b2  lea     rcx, [rsp+488h+TempFileName]; Str
0x18001b2b7  call    cs:__imp_wcsrchr
0x18001b2bd  test    rax, rax
0x18001b2c0  jz      short loc_18001B2EB
0x18001b2c2  lea     rcx, [rsp+488h+TempFileName]
0x18001b2c7  sub     rax, rcx
0x18001b2ca  lea     edx, [r14-1]
0x18001b2ce  sar     rax, 1
0x18001b2d1  lea     rcx, [rsp+488h+var_446]
0x18001b2d6  cdqe
0x18001b2d8  lea     r8, aHtm; "htm"
0x18001b2df  sub     rdx, rax; unsigned __int64
0x18001b2e2  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001b2e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b2eb  mov     rcx, rbx; hMem
0x18001b2ee  call    cs:__imp_GlobalLock
0x18001b2f4  test    rax, rax
0x18001b2f7  jz      short loc_18001B36F
0x18001b2f9  mov     [rsp+488h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18001b2fe  lea     r8, [rsp+488h+TempFileName]; lpWideCharStr
0x18001b303  xor     edx, edx; dwFlags
0x18001b305  mov     [rsp+488h+hTemplateFile], rbp; lpDefaultChar
0x18001b30a  mov     [rsp+488h+dwFlagsAndAttributes], r14d; cbMultiByte
0x18001b30f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001b313  mov     qword ptr [rsp+488h+dwCreationDisposition], rax; lpMultiByteStr
0x18001b318  lea     ecx, [rdx+1]; CodePage
0x18001b31b  call    cs:__imp_WideCharToMultiByte
0x18001b321  mov     rcx, rbx; hMem
0x18001b324  call    cs:__imp_GlobalUnlock
0x18001b32a  mov     rax, [rsi+8]
0x18001b32e  xor     r9d, r9d
0x18001b331  mov     r8, [rsi+18h]
0x18001b335  xor     edx, edx
0x18001b337  mov     cs:?g_RtfConverter@@3URTF_CONVERTER@@A, rax; RTF_CONVERTER g_RtfConverter
0x18001b33e  mov     rcx, rbx
0x18001b341  lea     rax, ?FeedExternalRtfToConverter@@YAFPEAHH@Z; FeedExternalRtfToConverter(int *,int)
0x18001b348  mov     qword ptr [rsp+488h+dwCreationDisposition], rax
0x18001b34d  mov     rax, [rsi+28h]
0x18001b351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b356  test    ax, ax
0x18001b359  jnz     short loc_18001B36F
0x18001b35b  lea     r8, [rsp+488h+TempFileName]; unsigned __int16 *
0x18001b360  mov     rdx, r14; unsigned __int64
0x18001b363  mov     rcx, rdi; unsigned __int16 *
0x18001b366  mov     esi, ebp
0x18001b368  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b36d  jmp     short loc_18001B379
0x18001b36f  mov     esi, 80004005h
0x18001b374  test    rbx, rbx
0x18001b377  jz      short loc_18001B389
0x18001b379  mov     rcx, rbx; hMem
0x18001b37c  call    cs:__imp_GlobalFree
0x18001b382  jmp     short loc_18001B389
0x18001b384  mov     esi, 80070057h
0x18001b389  mov     eax, esi
0x18001b38b  mov     rcx, [rsp+488h+var_28]
0x18001b393  xor     rcx, rsp; StackCookie
0x18001b396  call    __security_check_cookie
0x18001b39b  lea     r11, [rsp+488h+var_18]
0x18001b3a3  mov     rbx, [r11+30h]
0x18001b3a7  mov     rbp, [r11+38h]
0x18001b3ab  mov     rsp, r11
0x18001b3ae  pop     r14
0x18001b3b0  pop     rdi
0x18001b3b1  pop     rsi
0x18001b3b2  retn
```
