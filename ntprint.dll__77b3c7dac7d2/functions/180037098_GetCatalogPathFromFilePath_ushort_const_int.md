# GetCatalogPathFromFilePath(ushort const *,int)

- ea: `0x180037098`
- end: `0x180037317`
- name: `?GetCatalogPathFromFilePath@@YAPEAGPEBGH@Z`
- size: `639`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800281a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18001c660`
- `0x180036a0c`
- `0x180037058`
- `0x180037098`
- `0x180037b98`
- `0x180037e40`
- `0x180037eec`
- `0x180037f94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180037189`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180037189`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800372cb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800372cb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180037269`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180037269`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037100`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800371d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037100`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800371d1`

## string_xrefs

- `0x180037283`: `Error creating catalog path %ws, %ws.`
- `0x180037251`: `GetCatalogPathFromFilePath`
- `0x18003728a`: `GetCatalogPathFromFilePath`
- `0x1800372ba`: `GetCatalogPathFromFilePath`
- `0x1800372dd`: `GetCatalogPathFromFilePath`
- `0x1800372b3`: `Error allocating memory for catalog path %ws, %ws.`

## pseudocode

```c
unsigned __int16 *__fastcall GetCatalogPathFromFilePath(const unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rbx
  const unsigned __int16 *FileName; // rax
  const unsigned __int16 *v4; // r15
  unsigned __int64 v5; // rdi
  WCHAR *v6; // r12
  BOOL NextFileW; // r13d
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  unsigned int v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+28h] [rbp-D8h]
  unsigned int v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  unsigned int v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  v17 = 0;
  FileName = FindFileName(a1);
  v4 = FileName;
  if ( FileName )
  {
    v5 = 2 * (FileName - a1);
    *(_QWORD *)v16 = v5 + 12;
    v6 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(v5 + 12));
    if ( v6
      && StringCbCopyNExW(v6, v5 + 12, a1, v5, &v17, (unsigned __int64 *)v16, v14) >= 0
      && StringCbCopyExW(v17, *(unsigned __int64 *)v16, L"*.cat", &v17, (unsigned __int64 *)v16, v12) >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      hFindFile = FindFirstFileW(v6, &FindFileData);
      if ( hFindFile != (HANDLE)-1LL )
      {
        NextFileW = 1;
        while ( 1 )
        {
          if ( !NextFileW )
          {
LABEL_21:
            FindClose(hFindFile);
            goto LABEL_23;
          }
          v8 = -1;
          do
            ++v8;
          while ( FindFileData.cFileName[v8] );
          v9 = v8 + 1;
          v10 = v5 + 2 * v9;
          *(_QWORD *)v16 = v10;
          v2 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(v5 + 2 * v9));
          if ( !v2 )
          {
            SplLibTelemetry::WriteDbgTraceError(
              "GetCatalogPathFromFilePath",
              L"Error allocating memory for catalog path %ws, %ws.",
              a1,
              FindFileData.cFileName);
            goto LABEL_21;
          }
          if ( StringCbCopyNExW(v2, v10, a1, v5, &v17, (unsigned __int64 *)v16, v15) < 0
            || StringCbCopyExW(
                 v17,
                 *(unsigned __int64 *)v16,
                 FindFileData.cFileName,
                 &v17,
                 (unsigned __int64 *)v16,
                 v13) < 0 )
          {
            break;
          }
          if ( !(unsigned int)LegacyVerifyFileSignature(a1, v2) )
          {
            NextFileW = FindNextFileW(hFindFile, &FindFileData);
            DllFreeSplMem(v2);
LABEL_17:
            v2 = 0;
            goto LABEL_18;
          }
          SplLibTelemetry::WriteDbgTraceInfo("GetCatalogPathFromFilePath", L"Using catalog file %ws for  %ws", v2, v4);
LABEL_18:
          if ( v2 )
            goto LABEL_21;
        }
        SplLibTelemetry::WriteDbgTraceError(
          "GetCatalogPathFromFilePath",
          L"Error creating catalog path %ws, %ws.",
          a1,
          FindFileData.cFileName);
        DllFreeSplMem(v2);
        NextFileW = 0;
        goto LABEL_17;
      }
      SplLibTelemetry::WriteDbgTraceError("GetCatalogPathFromFilePath", L"No catalog file found for %ws.", v4);
    }
LABEL_23:
    DllFreeSplMem(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x180037098  push    rbp
0x18003709a  push    rbx
0x18003709b  push    rsi
0x18003709c  push    rdi
0x18003709d  push    r12
0x18003709f  push    r13
0x1800370a1  push    r14
0x1800370a3  push    r15
0x1800370a5  lea     rbp, [rsp-1C8h]
0x1800370ad  sub     rsp, 2C8h
0x1800370b4  mov     rax, cs:__security_cookie
0x1800370bb  xor     rax, rsp
0x1800370be  mov     [rbp+200h+var_50], rax
0x1800370c5  xor     r13d, r13d
0x1800370c8  mov     rsi, rcx
0x1800370cb  mov     ebx, r13d
0x1800370ce  mov     [rsp+300h+var_2B8], r13
0x1800370d3  call    ?FindFileName@@YAPEBGPEBG@Z; FindFileName(ushort const *)
0x1800370d8  mov     r15, rax
0x1800370db  test    rax, rax
0x1800370de  jz      loc_1800372F1
0x1800370e4  mov     rdi, rax
0x1800370e7  lea     ecx, [r13+40h]; uFlags
0x1800370eb  sub     rdi, rsi
0x1800370ee  sar     rdi, 1
0x1800370f1  add     rdi, rdi
0x1800370f4  lea     r14, [rdi+0Ch]
0x1800370f8  mov     edx, r14d; uBytes
0x1800370fb  mov     qword ptr [rsp+300h+var_2C0], r14
0x180037100  call    cs:__imp_LocalAlloc
0x180037106  mov     r12, rax
0x180037109  test    rax, rax
0x18003710c  jz      loc_1800372E9
0x180037112  lea     rax, [rsp+300h+var_2C0]
0x180037117  mov     r9, rdi; unsigned __int64
0x18003711a  mov     [rsp+300h+var_2D8], rax; unsigned int
0x18003711f  mov     r8, rsi; unsigned __int16 *
0x180037122  lea     rax, [rsp+300h+var_2B8]
0x180037127  mov     rdx, r14; unsigned __int64
0x18003712a  mov     rcx, r12; unsigned __int16 *
0x18003712d  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x180037132  call    ?StringCbCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCbCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180037137  xor     r14d, r14d
0x18003713a  test    eax, eax
0x18003713c  js      loc_1800372E9
0x180037142  mov     rdx, qword ptr [rsp+300h+var_2C0]; unsigned __int64
0x180037147  lea     rax, [rsp+300h+var_2C0]
0x18003714c  mov     rcx, [rsp+300h+var_2B8]; unsigned __int16 *
0x180037151  lea     r9, [rsp+300h+var_2B8]; unsigned __int16 **
0x180037156  lea     r8, aCat; "*.cat"
0x18003715d  mov     [rsp+300h+var_2E0], rax; unsigned __int64 *
0x180037162  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180037167  test    eax, eax
0x180037169  js      loc_1800372E9
0x18003716f  xor     edx, edx; Val
0x180037171  lea     rcx, [rsp+300h+FindFileData]; void *
0x180037176  mov     r8d, 250h; Size
0x18003717c  call    memset_0
0x180037181  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x180037186  mov     rcx, r12; lpFileName
0x180037189  call    cs:__imp_FindFirstFileW
0x18003718f  mov     [rsp+300h+hFindFile], rax
0x180037194  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037198  jz      loc_1800372D3
0x18003719e  lea     r13d, [rbx+1]
0x1800371a2  test    r13d, r13d
0x1800371a5  jz      loc_1800372C6
0x1800371ab  lea     rcx, [rbp+200h+FindFileData.cFileName]
0x1800371af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800371b3  inc     rax
0x1800371b6  cmp     [rcx+rax*2], r14w
0x1800371bb  jnz     short loc_1800371B3
0x1800371bd  inc     rax
0x1800371c0  mov     ecx, 40h ; '@'; uFlags
0x1800371c5  lea     r14, [rdi+rax*2]
0x1800371c9  mov     edx, r14d; uBytes
0x1800371cc  mov     qword ptr [rsp+300h+var_2C0], r14
0x1800371d1  call    cs:__imp_LocalAlloc
0x1800371d7  mov     rbx, rax
0x1800371da  mov     r8, rsi; unsigned __int16 *
0x1800371dd  test    rax, rax
0x1800371e0  jz      loc_1800372AF
0x1800371e6  lea     rax, [rsp+300h+var_2C0]
0x1800371eb  mov     r9, rdi; unsigned __int64
0x1800371ee  mov     [rsp+300h+var_2D8], rax; unsigned int
0x1800371f3  mov     rdx, r14; unsigned __int64
0x1800371f6  lea     rax, [rsp+300h+var_2B8]
0x1800371fb  mov     rcx, rbx; unsigned __int16 *
0x1800371fe  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x180037203  call    ?StringCbCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCbCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180037208  xor     r14d, r14d
0x18003720b  test    eax, eax
0x18003720d  js      short loc_18003727C
0x18003720f  mov     rdx, qword ptr [rsp+300h+var_2C0]; unsigned __int64
0x180037214  lea     rax, [rsp+300h+var_2C0]
0x180037219  mov     rcx, [rsp+300h+var_2B8]; unsigned __int16 *
0x18003721e  lea     r9, [rsp+300h+var_2B8]; unsigned __int16 **
0x180037223  lea     r8, [rbp+200h+FindFileData.cFileName]; unsigned __int16 *
0x180037227  mov     [rsp+300h+var_2E0], rax; unsigned __int64 *
0x18003722c  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180037231  test    eax, eax
0x180037233  js      short loc_18003727C
0x180037235  mov     rdx, rbx; unsigned __int16 *
0x180037238  mov     rcx, rsi; unsigned __int16 *
0x18003723b  call    ?LegacyVerifyFileSignature@@YAHPEBG0@Z; LegacyVerifyFileSignature(ushort const *,ushort const *)
0x180037240  test    eax, eax
0x180037242  jz      short loc_18003725F
0x180037244  mov     r9, r15
0x180037247  lea     rdx, aUsingCatalogFi; "Using catalog file %ws for  %ws"
0x18003724e  mov     r8, rbx
0x180037251  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x180037258  call    ?WriteDbgTraceInfo@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003725d  jmp     short loc_1800372A4
0x18003725f  mov     rcx, [rsp+300h+hFindFile]; hFindFile
0x180037264  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x180037269  call    cs:__imp_FindNextFileW
0x18003726f  mov     rcx, rbx
0x180037272  mov     r13d, eax
0x180037275  call    DllFreeSplMem
0x18003727a  jmp     short loc_1800372A1
0x18003727c  lea     r9, [rbp+200h+FindFileData.cFileName]
0x180037280  mov     r8, rsi
0x180037283  lea     rdx, aErrorCreatingC; "Error creating catalog path %ws, %ws."
0x18003728a  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x180037291  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037296  mov     rcx, rbx
0x180037299  call    DllFreeSplMem
0x18003729e  mov     r13d, r14d
0x1800372a1  mov     rbx, r14
0x1800372a4  test    rbx, rbx
0x1800372a7  jz      loc_1800371A2
0x1800372ad  jmp     short loc_1800372C6
0x1800372af  lea     r9, [rbp+200h+FindFileData.cFileName]
0x1800372b3  lea     rdx, aErrorAllocatin_0; "Error allocating memory for catalog pat"...
0x1800372ba  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800372c1  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800372c6  mov     rcx, [rsp+300h+hFindFile]; hFindFile
0x1800372cb  call    cs:__imp_FindClose
0x1800372d1  jmp     short loc_1800372E9
0x1800372d3  mov     r8, r15
0x1800372d6  lea     rdx, aNoCatalogFileF; "No catalog file found for %ws."
0x1800372dd  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800372e4  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800372e9  mov     rcx, r12
0x1800372ec  call    DllFreeSplMem
0x1800372f1  mov     rax, rbx
0x1800372f4  mov     rcx, [rbp+200h+var_50]
0x1800372fb  xor     rcx, rsp; StackCookie
0x1800372fe  call    __security_check_cookie
0x180037303  add     rsp, 2C8h
0x18003730a  pop     r15
0x18003730c  pop     r14
0x18003730e  pop     r13
0x180037310  pop     r12
0x180037312  pop     rdi
0x180037313  pop     rsi
0x180037314  pop     rbx
0x180037315  pop     rbp
0x180037316  retn
```
