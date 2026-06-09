# CleanupLocFiles(std::set<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>> &,uint *)

- ea: `0x140010638`
- end: `0x140010ac5`
- name: `?CleanupLocFiles@@YAJAEAV?$set@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@@std@@PEAI@Z`
- size: `1165`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x14000b904`
- `0x1400101fc`
- `0x140010638`
- `0x1400195d6`
- `0x1400195e2`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010721`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400106ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010721`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400106d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001070d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400106d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001070d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010a77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001079b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001079b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010a06`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010852`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x140010852`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010781`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010781`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001090d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001090d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400107e6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400107e6`

## string_xrefs

- `0x1400109a2`: `Failed to delete file.`

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
                      if ( (unsigned int)dword_140028000 > 2
                        && (qword_140028010 & 0x400000000000LL) != 0
                        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                      {
                        v37 = 0x1000000;
                        v38 = "CleanupLocFiles";
                        v32 = 935;
                        v39 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
                        v40 = "Failed to delete file.";
                        v33 = v25;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                          v25,
                          (unsigned int)byte_140023049,
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
0x140010638  push    rbp
0x14001063a  push    rbx
0x14001063b  push    rsi
0x14001063c  push    rdi
0x14001063d  push    r12
0x14001063f  push    r13
0x140010641  push    r14
0x140010643  push    r15
0x140010645  lea     rbp, [rsp-258h]
0x14001064d  sub     rsp, 358h
0x140010654  mov     rax, cs:__security_cookie
0x14001065b  xor     rax, rsp
0x14001065e  mov     [rbp+290h+var_50], rax
0x140010665  mov     r15, rdx
0x140010668  mov     [rsp+390h+var_320], rcx
0x14001066d  xor     edx, edx; Val
0x14001066f  lea     rcx, [rbp+290h+FindFileData]; void *
0x140010673  mov     r8d, 250h; Size
0x140010679  call    memset_0
0x14001067e  xor     r14d, r14d
0x140010681  lea     rcx, [rbp+290h+sz]; void *
0x140010685  xor     edx, edx; Val
0x140010687  mov     [rsp+390h+var_340], r14d
0x14001068c  mov     r13d, r14d
0x14001068f  lea     r8d, [r14+4Ah]; Size
0x140010693  call    memset_0
0x140010698  call    cs:__imp_GetProcessHeap
0x14001069f  nop     dword ptr [rax+rax+00h]
0x1400106a4  mov     edi, 208h
0x1400106a9  lea     ebx, [r14+8]
0x1400106ad  mov     rcx, rax; hHeap
0x1400106b0  mov     r8d, edi; dwBytes
0x1400106b3  mov     edx, ebx; dwFlags
0x1400106b5  call    cs:__imp_HeapAlloc
0x1400106bc  nop     dword ptr [rax+rax+00h]
0x1400106c1  mov     [rsp+390h+var_330], rax
0x1400106c6  mov     rsi, rax
0x1400106c9  test    rax, rax
0x1400106cc  jnz     short loc_1400106D8
0x1400106ce  mov     ebx, 8007000Eh
0x1400106d3  jmp     loc_140010A97
0x1400106d8  call    cs:__imp_GetProcessHeap
0x1400106df  nop     dword ptr [rax+rax+00h]
0x1400106e4  mov     r8, rdi; dwBytes
0x1400106e7  mov     edx, ebx; dwFlags
0x1400106e9  mov     rcx, rax; hHeap
0x1400106ec  call    cs:__imp_HeapAlloc
0x1400106f3  nop     dword ptr [rax+rax+00h]
0x1400106f8  mov     r12, rax
0x1400106fb  test    rax, rax
0x1400106fe  jnz     short loc_14001070D
0x140010700  mov     rdi, r14
0x140010703  mov     ebx, 8007000Eh
0x140010708  jmp     loc_140010A52
0x14001070d  call    cs:__imp_GetProcessHeap
0x140010714  nop     dword ptr [rax+rax+00h]
0x140010719  mov     r8, rdi; dwBytes
0x14001071c  mov     edx, ebx; dwFlags
0x14001071e  mov     rcx, rax; hHeap
0x140010721  call    cs:__imp_HeapAlloc
0x140010728  nop     dword ptr [rax+rax+00h]
0x14001072d  mov     rdi, rax
0x140010730  test    rax, rax
0x140010733  jnz     short loc_14001073F
0x140010735  mov     ebx, 8007000Eh
0x14001073a  jmp     loc_140010A32
0x14001073f  test    r15, r15
0x140010742  jz      short loc_140010747
0x140010744  mov     [r15], r14d
0x140010747  mov     rcx, rsi; unsigned __int16 *
0x14001074a  call    ?BuildSiufLocFolderPath@@YAJPEAGI@Z; BuildSiufLocFolderPath(ushort *,uint)
0x14001074f  mov     ebx, eax
0x140010751  test    eax, eax
0x140010753  js      loc_140010A32
0x140010759  mov     r9, rsi
0x14001075c  lea     r8, aS_0; "%s\\*"
0x140010763  mov     edx, 104h; unsigned __int64
0x140010768  mov     rcx, rdi; unsigned __int16 *
0x14001076b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010770  mov     ebx, eax
0x140010772  test    eax, eax
0x140010774  js      loc_140010A32
0x14001077a  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x14001077e  mov     rcx, rdi; lpFileName
0x140010781  call    cs:__imp_FindFirstFileW
0x140010788  nop     dword ptr [rax+rax+00h]
0x14001078d  mov     [rsp+390h+var_328], rax
0x140010792  mov     rbx, rax
0x140010795  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010799  jnz     short loc_1400107C8
0x14001079b  call    cs:__imp_GetLastError
0x1400107a2  nop     dword ptr [rax+rax+00h]
0x1400107a7  mov     ebx, eax
0x1400107a9  cmp     eax, 2
0x1400107ac  jz      loc_140010A1C
0x1400107b2  test    eax, eax
0x1400107b4  jle     loc_140010A32
0x1400107ba  movzx   ebx, ax
0x1400107bd  or      ebx, 80070000h
0x1400107c3  jmp     loc_140010A32
0x1400107c8  mov     r14d, 80070000h
0x1400107ce  xor     edx, edx; Val
0x1400107d0  lea     rcx, [rbp+290h+FindFileData]; void *
0x1400107d4  mov     r8d, 250h; Size
0x1400107da  call    memset_0
0x1400107df  lea     rdx, [rbp+290h+FindFileData]; lpFindFileData
0x1400107e3  mov     rcx, rbx; hFindFile
0x1400107e6  call    cs:__imp_FindNextFileW
0x1400107ed  nop     dword ptr [rax+rax+00h]
0x1400107f2  xor     r10d, r10d
0x1400107f5  test    eax, eax
0x1400107f7  jz      loc_140010A06
0x1400107fd  cmp     [rbp+290h+FindFileData.cFileName], 2Eh ; '.'
0x140010802  jz      short loc_1400107CE
0x140010804  lea     r11d, [r10+25h]
0x140010808  mov     ecx, 7FFFFFFEh
0x14001080d  mov     edx, r11d
0x140010810  lea     r8, [rbp+290h+FindFileData.cFileName+0Ch]
0x140010814  lea     rax, [rbp+290h+sz]
0x140010818  test    rcx, rcx
0x14001081b  jz      short loc_14001083C
0x14001081d  movzx   r9d, word ptr [r8]
0x140010821  test    r9w, r9w
0x140010825  jz      short loc_14001083C
0x140010827  mov     [rax], r9w
0x14001082b  add     r8, 2
0x14001082f  add     rax, 2
0x140010833  dec     rcx
0x140010836  sub     rdx, 1
0x14001083a  jnz     short loc_140010818
0x14001083c  test    rdx, rdx
0x14001083f  lea     rcx, [rax-2]
0x140010843  mov     edx, r11d; cchLength
0x140010846  cmovnz  rcx, rax
0x14001084a  mov     [rcx], r10w
0x14001084e  lea     rcx, [rbp+290h+sz]; lpsz
0x140010852  call    cs:__imp_CharLowerBuffW
0x140010859  nop     dword ptr [rax+rax+00h]
0x14001085e  mov     rax, [rsp+390h+var_320]
0x140010863  mov     r13, [rax]
0x140010866  mov     rsi, r13
0x140010869  mov     rbx, [r13+8]
0x14001086d  cmp     byte ptr [rbx+19h], 0
0x140010871  jnz     short loc_1400108CB
0x140010873  lea     rcx, [rbx+1Ah]; Buf1
0x140010877  mov     r8d, 4Ah ; 'J'; Size
0x14001087d  lea     rdx, [rbp+290h+sz]; Buf2
0x140010881  call    memcmp_0
0x140010886  test    eax, eax
0x140010888  jns     short loc_140010890
0x14001088a  mov     rbx, [rbx+10h]
0x14001088e  jmp     short loc_140010896
0x140010890  mov     rsi, rbx
0x140010893  mov     rbx, [rbx]
0x140010896  cmp     byte ptr [rbx+19h], 0
0x14001089a  jz      short loc_140010873
0x14001089c  cmp     rsi, r13
0x14001089f  jz      short loc_1400108CB
0x1400108a1  lea     rdx, [rsi+1Ah]; Buf2
0x1400108a5  mov     r8d, 4Ah ; 'J'; Size
0x1400108ab  lea     rcx, [rbp+290h+sz]; Buf1
0x1400108af  call    memcmp_0
0x1400108b4  mov     rsi, [rsp+390h+var_330]
0x1400108b9  mov     rbx, [rsp+390h+var_328]
0x1400108be  mov     r13d, [rsp+390h+var_340]
0x1400108c3  test    eax, eax
0x1400108c5  jns     loc_1400107CE
0x1400108cb  xor     edx, edx; Val
0x1400108cd  mov     r8d, 208h; Size
0x1400108d3  mov     rcx, r12; void *
0x1400108d6  call    memset_0
0x1400108db  mov     rsi, [rsp+390h+var_330]
0x1400108e0  lea     rax, [rbp+290h+FindFileData.cFileName]
0x1400108e4  mov     r9, rsi
0x1400108e7  mov     [rsp+390h+var_370], rax
0x1400108ec  lea     r8, aSS_0; "%s\\%s"
0x1400108f3  mov     edx, 104h; unsigned __int64
0x1400108f8  mov     rcx, r12; unsigned __int16 *
0x1400108fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010900  mov     ebx, eax
0x140010902  test    eax, eax
0x140010904  js      loc_140010A2D
0x14001090a  mov     rcx, r12; lpFileName
0x14001090d  call    cs:__imp_DeleteFileW
0x140010914  nop     dword ptr [rax+rax+00h]
0x140010919  test    eax, eax
0x14001091b  jnz     loc_1400109EF
0x140010921  call    cs:__imp_GetLastError
0x140010928  nop     dword ptr [rax+rax+00h]
0x14001092d  mov     ecx, eax
0x14001092f  test    eax, eax
0x140010931  jle     short loc_140010939
0x140010933  movzx   ecx, ax
0x140010936  or      ecx, r14d
0x140010939  mov     eax, cs:dword_140028000
0x14001093f  cmp     eax, 2
0x140010942  jbe     loc_1400109EF
0x140010948  mov     rdx, cs:qword_140028018
0x14001094f  mov     r8, 400000000000h
0x140010959  mov     rax, cs:qword_140028010
0x140010960  test    r8, rax
0x140010963  jz      loc_1400109EF
0x140010969  mov     rax, rdx
0x14001096c  and     rax, r8
0x14001096f  cmp     rax, rdx
0x140010972  jnz     short loc_1400109EF
0x140010974  lea     rax, aCleanuplocfile_0; "CleanupLocFiles"
0x14001097b  mov     [rsp+390h+var_318], 1000000h
0x140010984  mov     [rbp+290h+var_310], rax
0x140010988  lea     rdx, byte_140023049
0x14001098f  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010996  mov     [rsp+390h+var_33C], 3A7h
0x14001099e  mov     [rbp+290h+var_308], rax
0x1400109a2  lea     rax, aFailedToDelete; "Failed to delete file."
0x1400109a9  mov     [rbp+290h+var_300], rax
0x1400109ad  lea     rax, [rsp+390h+var_318]
0x1400109b2  mov     [rsp+390h+var_348], rax
0x1400109b7  lea     rax, [rsp+390h+var_33C]
0x1400109bc  mov     [rsp+390h+var_350], rax
0x1400109c1  lea     rax, [rbp+290h+var_310]
0x1400109c5  mov     [rsp+390h+var_358], rax
0x1400109ca  lea     rax, [rbp+290h+var_308]
0x1400109ce  mov     [rsp+390h+var_360], rax
0x1400109d3  lea     rax, [rsp+390h+var_338]
0x1400109d8  mov     [rsp+390h+var_368], rax
0x1400109dd  lea     rax, [rbp+290h+var_300]
0x1400109e1  mov     [rsp+390h+var_370], rax
0x1400109e6  mov     [rsp+390h+var_338], ecx
0x1400109ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400109ef  mov     r13d, [rsp+390h+var_340]
0x1400109f4  mov     rbx, [rsp+390h+var_328]
0x1400109f9  inc     r13d
0x1400109fc  mov     [rsp+390h+var_340], r13d
0x140010a01  jmp     loc_1400107CE
0x140010a06  call    cs:__imp_GetLastError
0x140010a0d  nop     dword ptr [rax+rax+00h]
0x140010a12  mov     ebx, eax
0x140010a14  cmp     eax, 12h
0x140010a17  jnz     short loc_140010A21
0x140010a19  xor     r14d, r14d
0x140010a1c  mov     ebx, r14d
0x140010a1f  jmp     short loc_140010A32
0x140010a21  test    eax, eax
0x140010a23  jle     short loc_140010A32
0x140010a25  movzx   ebx, ax
0x140010a28  or      ebx, r14d
0x140010a2b  jmp     short loc_140010A32
0x140010a2d  mov     r13d, [rsp+390h+var_340]
0x140010a32  call    cs:__imp_GetProcessHeap
0x140010a39  nop     dword ptr [rax+rax+00h]
0x140010a3e  mov     r8, r12; lpMem
0x140010a41  xor     edx, edx; dwFlags
0x140010a43  mov     rcx, rax; hHeap
0x140010a46  call    cs:__imp_HeapFree
0x140010a4d  nop     dword ptr [rax+rax+00h]
0x140010a52  call    cs:__imp_GetProcessHeap
0x140010a59  nop     dword ptr [rax+rax+00h]
0x140010a5e  mov     r8, rsi; lpMem
0x140010a61  xor     edx, edx; dwFlags
0x140010a63  mov     rcx, rax; hHeap
0x140010a66  call    cs:__imp_HeapFree
0x140010a6d  nop     dword ptr [rax+rax+00h]
0x140010a72  test    rdi, rdi
0x140010a75  jz      short loc_140010A97
0x140010a77  call    cs:__imp_GetProcessHeap
0x140010a7e  nop     dword ptr [rax+rax+00h]
0x140010a83  mov     r8, rdi; lpMem
0x140010a86  xor     edx, edx; dwFlags
0x140010a88  mov     rcx, rax; hHeap
0x140010a8b  call    cs:__imp_HeapFree
0x140010a92  nop     dword ptr [rax+rax+00h]
0x140010a97  test    r15, r15
0x140010a9a  jz      short loc_140010A9F
0x140010a9c  mov     [r15], r13d
0x140010a9f  mov     eax, ebx
0x140010aa1  mov     rcx, [rbp+290h+var_50]
0x140010aa8  xor     rcx, rsp; StackCookie
0x140010aab  call    __security_check_cookie
0x140010ab0  add     rsp, 358h
0x140010ab7  pop     r15
0x140010ab9  pop     r14
0x140010abb  pop     r13
0x140010abd  pop     r12
0x140010abf  pop     rdi
0x140010ac0  pop     rsi
0x140010ac1  pop     rbx
0x140010ac2  pop     rbp
0x140010ac3  retn
```
