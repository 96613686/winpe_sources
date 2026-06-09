# CleanupLocFiles(std::set<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>> &,uint *)

- ea: `0x140010050`
- end: `0x14001046a`
- name: `?CleanupLocFiles@@YAJAEAV?$set@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@@std@@PEAI@Z`
- size: `1050`
- prototype: `__int64 __fastcall(__int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x14000fc30`
- `0x140010050`
- `0x1400187a6`
- `0x1400187b2`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400100c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400100f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001011b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400100c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400100f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001011b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001010d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400103fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010410`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400100e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001010d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400103fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010410`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001040a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001041e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001040a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001041e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103d6`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010234`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010234`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010175`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010175`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400102e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400102e9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400101ce`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400101ce`

## string_xrefs

- `0x140010372`: `Failed to delete file.`

## pseudocode

```c
__int64 __fastcall CleanupLocFiles(__int64 *a1, int *a2)
{
  int v3; // r13d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rsi
  signed int v6; // ebx
  HANDLE v7; // rax
  void *v8; // r12
  unsigned __int16 *v9; // rdi
  HANDLE v10; // rax
  unsigned int v11; // edx
  void *v12; // rbx
  signed int LastError; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  WCHAR *v16; // r8
  WCHAR *v17; // rax
  WCHAR *v18; // rcx
  __int64 *v19; // r13
  __int64 *v20; // rsi
  __int64 *v21; // rbx
  int v22; // eax
  signed int v23; // eax
  int v24; // r9d
  unsigned int v25; // ecx
  signed int v26; // eax
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  int v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp-A0h]
  HANDLE FirstFileW; // [rsp+68h] [rbp-98h]
  __int64 *v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  const char *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  WCHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-10h] BYREF

  v36 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v31 = 0;
  v3 = 0;
  memset_0(sz, 0, 0x4Au);
  ProcessHeap = GetProcessHeap();
  v34 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  v5 = v34;
  if ( v34 )
  {
    v7 = GetProcessHeap();
    v8 = HeapAlloc(v7, 8u, 0x208u);
    if ( v8 )
    {
      v10 = GetProcessHeap();
      v9 = (unsigned __int16 *)HeapAlloc(v10, 8u, 0x208u);
      if ( v9 )
      {
        if ( a2 )
          *a2 = 0;
        v6 = BuildSiufLocFolderPath(v5, v11);
        if ( v6 >= 0 )
        {
          v6 = StringCchPrintfW(v9, 0x104u, L"%s\\*", v5);
          if ( v6 >= 0 )
          {
            FirstFileW = FindFirstFileW(v9, &FindFileData);
            v12 = FirstFileW;
            if ( FirstFileW == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError == 2 )
              {
LABEL_40:
                v6 = 0;
              }
              else if ( LastError > 0 )
              {
                v6 = (unsigned __int16)LastError | 0x80070000;
              }
            }
            else
            {
              while ( 1 )
              {
                memset_0(&FindFileData, 0, sizeof(FindFileData));
                if ( !FindNextFileW(v12, &FindFileData) )
                  break;
                if ( FindFileData.cFileName[0] != 46 )
                {
                  v14 = 2147483646;
                  v15 = 37;
                  v16 = &FindFileData.cFileName[6];
                  v17 = sz;
                  do
                  {
                    if ( !v14 )
                      break;
                    if ( !*v16 )
                      break;
                    *v17++ = *v16++;
                    --v14;
                    --v15;
                  }
                  while ( v15 );
                  v18 = v17 - 1;
                  if ( v15 )
                    v18 = v17;
                  *v18 = 0;
                  CharLowerBuffW(sz, 0x25u);
                  v19 = (__int64 *)*v36;
                  v20 = (__int64 *)*v36;
                  v21 = *(__int64 **)(*v36 + 8);
                  if ( *((_BYTE *)v21 + 25) )
                    goto LABEL_30;
                  do
                  {
                    if ( memcmp_0((char *)v21 + 26, sz, 0x4Au) >= 0 )
                    {
                      v20 = v21;
                      v21 = (__int64 *)*v21;
                    }
                    else
                    {
                      v21 = (__int64 *)v21[2];
                    }
                  }
                  while ( !*((_BYTE *)v21 + 25) );
                  if ( v20 == v19
                    || (v22 = memcmp_0(sz, (char *)v20 + 26, 0x4Au), v5 = v34, v12 = FirstFileW, v3 = v31, v22 < 0) )
                  {
LABEL_30:
                    memset_0(v8, 0, 0x208u);
                    v5 = v34;
                    v6 = StringCchPrintfW((unsigned __int16 *)v8, 0x104u, L"%s\\%s", v34, FindFileData.cFileName);
                    if ( v6 < 0 )
                    {
                      v3 = v31;
                      goto LABEL_44;
                    }
                    if ( !DeleteFileW((LPCWSTR)v8) )
                    {
                      v23 = GetLastError();
                      v25 = v23;
                      if ( v23 > 0 )
                        v25 = (unsigned __int16)v23 | 0x80070000;
                      if ( (unsigned int)dword_140027000 > 2
                        && (qword_140027010 & 0x400000000000LL) != 0
                        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                      {
                        v37 = 0x1000000;
                        v38 = "CleanupLocFiles";
                        v32 = 935;
                        v39 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
                        v40 = "Failed to delete file.";
                        v33 = v25;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                          v25,
                          (unsigned int)byte_140022041,
                          0,
                          v24,
                          (__int64)&v40,
                          (__int64)&v33,
                          (__int64)&v39,
                          (__int64)&v38,
                          (__int64)&v32,
                          (__int64)&v37);
                      }
                    }
                    v12 = FirstFileW;
                    v3 = ++v31;
                  }
                }
              }
              v26 = GetLastError();
              v6 = v26;
              if ( v26 == 18 )
                goto LABEL_40;
              if ( v26 > 0 )
                v6 = (unsigned __int16)v26 | 0x80070000;
            }
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
LABEL_44:
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v8);
    }
    else
    {
      v9 = 0;
      v6 = -2147024882;
    }
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v5);
    if ( v9 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v9);
    }
  }
  else
  {
    v6 = -2147024882;
  }
  if ( a2 )
    *a2 = v3;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140010050  push    rbp
0x140010052  push    rbx
0x140010053  push    rsi
0x140010054  push    rdi
0x140010055  push    r12
0x140010057  push    r13
0x140010059  push    r14
0x14001005b  push    r15
0x14001005d  lea     rbp, [rsp-258h]
0x140010065  sub     rsp, 358h
0x14001006c  mov     rax, cs:__security_cookie
0x140010073  xor     rax, rsp
0x140010076  mov     [rbp+290h+var_50], rax
0x14001007d  mov     r15, rdx
0x140010080  mov     [rsp+390h+var_320], rcx
0x140010085  xor     edx, edx; Val
0x140010087  lea     rcx, [rbp+290h+FindFileData]; void *
0x14001008b  mov     r8d, 250h; Size
0x140010091  call    memset_0
0x140010096  xor     r14d, r14d
0x140010099  lea     rcx, [rbp+290h+sz]; void *
0x14001009d  xor     edx, edx; Val
0x14001009f  mov     [rsp+390h+var_340], r14d
0x1400100a4  mov     r13d, r14d
0x1400100a7  lea     r8d, [r14+4Ah]; Size
0x1400100ab  call    memset_0
0x1400100b0  call    cs:__imp_GetProcessHeap
0x1400100b6  mov     edi, 208h
0x1400100bb  lea     ebx, [r14+8]
0x1400100bf  mov     rcx, rax; hHeap
0x1400100c2  mov     r8d, edi; dwBytes
0x1400100c5  mov     edx, ebx; dwFlags
0x1400100c7  call    cs:__imp_HeapAlloc
0x1400100cd  mov     [rsp+390h+var_330], rax
0x1400100d2  mov     rsi, rax
0x1400100d5  test    rax, rax
0x1400100d8  jnz     short loc_1400100E4
0x1400100da  mov     ebx, 8007000Eh
0x1400100df  jmp     loc_14001043D
0x1400100e4  call    cs:__imp_GetProcessHeap
0x1400100ea  mov     r8, rdi; dwBytes
0x1400100ed  mov     edx, ebx; dwFlags
0x1400100ef  mov     rcx, rax; hHeap
0x1400100f2  call    cs:__imp_HeapAlloc
0x1400100f8  mov     r12, rax
0x1400100fb  test    rax, rax
0x1400100fe  jnz     short loc_14001010D
0x140010100  mov     rdi, r14
0x140010103  mov     ebx, 8007000Eh
0x140010108  jmp     loc_140010410
0x14001010d  call    cs:__imp_GetProcessHeap
0x140010113  mov     r8, rdi; dwBytes
0x140010116  mov     edx, ebx; dwFlags
0x140010118  mov     rcx, rax; hHeap
0x14001011b  call    cs:__imp_HeapAlloc
0x140010121  mov     rdi, rax
0x140010124  test    rax, rax
0x140010127  jnz     short loc_140010133
0x140010129  mov     ebx, 8007000Eh
0x14001012e  jmp     loc_1400103FC
0x140010133  test    r15, r15
0x140010136  jz      short loc_14001013B
0x140010138  mov     [r15], r14d
0x14001013b  mov     rcx, rsi; unsigned __int16 *
0x14001013e  call    ?BuildSiufLocFolderPath@@YAJPEAGI@Z; BuildSiufLocFolderPath(ushort *,uint)
0x140010143  mov     ebx, eax
0x140010145  test    eax, eax
0x140010147  js      loc_1400103FC
0x14001014d  mov     r9, rsi
0x140010150  lea     r8, aS_0; "%s\\*"
0x140010157  mov     edx, 104h; unsigned __int64
0x14001015c  mov     rcx, rdi; unsigned __int16 *
0x14001015f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010164  mov     ebx, eax
0x140010166  test    eax, eax
0x140010168  js      loc_1400103FC
0x14001016e  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x140010172  mov     rcx, rdi; lpFileName
0x140010175  call    cs:__imp_FindFirstFileW
0x14001017b  mov     [rsp+390h+var_328], rax
0x140010180  mov     rbx, rax
0x140010183  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010187  jnz     short loc_1400101B0
0x140010189  call    cs:__imp_GetLastError
0x14001018f  mov     ebx, eax
0x140010191  cmp     eax, 2
0x140010194  jz      loc_1400103E6
0x14001019a  test    eax, eax
0x14001019c  jle     loc_1400103FC
0x1400101a2  movzx   ebx, ax
0x1400101a5  or      ebx, 80070000h
0x1400101ab  jmp     loc_1400103FC
0x1400101b0  mov     r14d, 80070000h
0x1400101b6  xor     edx, edx; Val
0x1400101b8  lea     rcx, [rbp+290h+FindFileData]; void *
0x1400101bc  mov     r8d, 250h; Size
0x1400101c2  call    memset_0
0x1400101c7  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x1400101cb  mov     rcx, rbx; hFindFile
0x1400101ce  call    cs:__imp_FindNextFileW
0x1400101d4  xor     r10d, r10d
0x1400101d7  test    eax, eax
0x1400101d9  jz      loc_1400103D6
0x1400101df  cmp     [rbp+290h+FindFileData.cFileName], 2Eh ; '.'
0x1400101e4  jz      short loc_1400101B6
0x1400101e6  lea     r11d, [r10+25h]
0x1400101ea  mov     ecx, 7FFFFFFEh
0x1400101ef  mov     edx, r11d
0x1400101f2  lea     r8, [rbp+290h+FindFileData.cFileName+0Ch]
0x1400101f6  lea     rax, [rbp+290h+sz]
0x1400101fa  test    rcx, rcx
0x1400101fd  jz      short loc_14001021E
0x1400101ff  movzx   r9d, word ptr [r8]
0x140010203  test    r9w, r9w
0x140010207  jz      short loc_14001021E
0x140010209  mov     [rax], r9w
0x14001020d  add     r8, 2
0x140010211  add     rax, 2
0x140010215  dec     rcx
0x140010218  sub     rdx, 1
0x14001021c  jnz     short loc_1400101FA
0x14001021e  test    rdx, rdx
0x140010221  lea     rcx, [rax-2]
0x140010225  mov     edx, r11d; cchLength
0x140010228  cmovnz  rcx, rax
0x14001022c  mov     [rcx], r10w
0x140010230  lea     rcx, [rbp+290h+sz]; lpsz
0x140010234  call    cs:__imp_CharLowerBuffW
0x14001023a  mov     rax, [rsp+390h+var_320]
0x14001023f  mov     r13, [rax]
0x140010242  mov     rsi, r13
0x140010245  mov     rbx, [r13+8]
0x140010249  cmp     byte ptr [rbx+19h], 0
0x14001024d  jnz     short loc_1400102A7
0x14001024f  lea     rcx, [rbx+1Ah]; Buf1
0x140010253  mov     r8d, 4Ah ; 'J'; Size
0x140010259  lea     rdx, [rbp+290h+sz]; Buf2
0x14001025d  call    memcmp_0
0x140010262  test    eax, eax
0x140010264  jns     short loc_14001026C
0x140010266  mov     rbx, [rbx+10h]
0x14001026a  jmp     short loc_140010272
0x14001026c  mov     rsi, rbx
0x14001026f  mov     rbx, [rbx]
0x140010272  cmp     byte ptr [rbx+19h], 0
0x140010276  jz      short loc_14001024F
0x140010278  cmp     rsi, r13
0x14001027b  jz      short loc_1400102A7
0x14001027d  lea     rdx, [rsi+1Ah]; Buf2
0x140010281  mov     r8d, 4Ah ; 'J'; Size
0x140010287  lea     rcx, [rbp+290h+sz]; Buf1
0x14001028b  call    memcmp_0
0x140010290  mov     rsi, [rsp+390h+var_330]
0x140010295  mov     rbx, [rsp+390h+var_328]
0x14001029a  mov     r13d, [rsp+390h+var_340]
0x14001029f  test    eax, eax
0x1400102a1  jns     loc_1400101B6
0x1400102a7  xor     edx, edx; Val
0x1400102a9  mov     r8d, 208h; Size
0x1400102af  mov     rcx, r12; void *
0x1400102b2  call    memset_0
0x1400102b7  mov     rsi, [rsp+390h+var_330]
0x1400102bc  lea     rax, [rbp+290h+FindFileData.cFileName]
0x1400102c0  mov     r9, rsi
0x1400102c3  mov     [rsp+390h+var_370], rax
0x1400102c8  lea     r8, aSS_0; "%s\\%s"
0x1400102cf  mov     edx, 104h; unsigned __int64
0x1400102d4  mov     rcx, r12; unsigned __int16 *
0x1400102d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400102dc  mov     ebx, eax
0x1400102de  test    eax, eax
0x1400102e0  js      loc_1400103F7
0x1400102e6  mov     rcx, r12; lpFileName
0x1400102e9  call    cs:__imp_DeleteFileW
0x1400102ef  test    eax, eax
0x1400102f1  jnz     loc_1400103BF
0x1400102f7  call    cs:__imp_GetLastError
0x1400102fd  mov     ecx, eax
0x1400102ff  test    eax, eax
0x140010301  jle     short loc_140010309
0x140010303  movzx   ecx, ax
0x140010306  or      ecx, r14d
0x140010309  mov     eax, cs:dword_140027000
0x14001030f  cmp     eax, 2
0x140010312  jbe     loc_1400103BF
0x140010318  mov     rdx, cs:qword_140027018
0x14001031f  mov     r8, 400000000000h
0x140010329  mov     rax, cs:qword_140027010
0x140010330  test    r8, rax
0x140010333  jz      loc_1400103BF
0x140010339  mov     rax, rdx
0x14001033c  and     rax, r8
0x14001033f  cmp     rax, rdx
0x140010342  jnz     short loc_1400103BF
0x140010344  lea     rax, aCleanuplocfile_0; "CleanupLocFiles"
0x14001034b  mov     [rsp+390h+var_318], 1000000h
0x140010354  mov     [rbp+290h+var_310], rax
0x140010358  lea     rdx, byte_140022041
0x14001035f  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010366  mov     [rsp+390h+var_33C], 3A7h
0x14001036e  mov     [rbp+290h+var_308], rax
0x140010372  lea     rax, aFailedToDelete; "Failed to delete file."
0x140010379  mov     [rbp+290h+var_300], rax
0x14001037d  lea     rax, [rsp+390h+var_318]
0x140010382  mov     [rsp+390h+var_348], rax
0x140010387  lea     rax, [rsp+390h+var_33C]
0x14001038c  mov     [rsp+390h+var_350], rax
0x140010391  lea     rax, [rbp+290h+var_310]
0x140010395  mov     [rsp+390h+var_358], rax
0x14001039a  lea     rax, [rbp+290h+var_308]
0x14001039e  mov     [rsp+390h+var_360], rax
0x1400103a3  lea     rax, [rsp+390h+var_338]
0x1400103a8  mov     [rsp+390h+var_368], rax
0x1400103ad  lea     rax, [rbp+290h+var_300]
0x1400103b1  mov     [rsp+390h+var_370], rax
0x1400103b6  mov     [rsp+390h+var_338], ecx
0x1400103ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400103bf  mov     r13d, [rsp+390h+var_340]
0x1400103c4  mov     rbx, [rsp+390h+var_328]
0x1400103c9  inc     r13d
0x1400103cc  mov     [rsp+390h+var_340], r13d
0x1400103d1  jmp     loc_1400101B6
0x1400103d6  call    cs:__imp_GetLastError
0x1400103dc  mov     ebx, eax
0x1400103de  cmp     eax, 12h
0x1400103e1  jnz     short loc_1400103EB
0x1400103e3  xor     r14d, r14d
0x1400103e6  mov     ebx, r14d
0x1400103e9  jmp     short loc_1400103FC
0x1400103eb  test    eax, eax
0x1400103ed  jle     short loc_1400103FC
0x1400103ef  movzx   ebx, ax
0x1400103f2  or      ebx, r14d
0x1400103f5  jmp     short loc_1400103FC
0x1400103f7  mov     r13d, [rsp+390h+var_340]
0x1400103fc  call    cs:__imp_GetProcessHeap
0x140010402  mov     r8, r12; lpMem
0x140010405  xor     edx, edx; dwFlags
0x140010407  mov     rcx, rax; hHeap
0x14001040a  call    cs:__imp_HeapFree
0x140010410  call    cs:__imp_GetProcessHeap
0x140010416  mov     r8, rsi; lpMem
0x140010419  xor     edx, edx; dwFlags
0x14001041b  mov     rcx, rax; hHeap
0x14001041e  call    cs:__imp_HeapFree
0x140010424  test    rdi, rdi
0x140010427  jz      short loc_14001043D
0x140010429  call    cs:__imp_GetProcessHeap
0x14001042f  mov     r8, rdi; lpMem
0x140010432  xor     edx, edx; dwFlags
0x140010434  mov     rcx, rax; hHeap
0x140010437  call    cs:__imp_HeapFree
0x14001043d  test    r15, r15
0x140010440  jz      short loc_140010445
0x140010442  mov     [r15], r13d
0x140010445  mov     eax, ebx
0x140010447  mov     rcx, [rbp+290h+var_50]
0x14001044e  xor     rcx, rsp; StackCookie
0x140010451  call    __security_check_cookie
0x140010456  add     rsp, 358h
0x14001045d  pop     r15
0x14001045f  pop     r14
0x140010461  pop     r13
0x140010463  pop     r12
0x140010465  pop     rdi
0x140010466  pop     rsi
0x140010467  pop     rbx
0x140010468  pop     rbp
0x140010469  retn
```
