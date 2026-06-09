# SxLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x18001a45c`
- end: `0x18001a628`
- name: `?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `460`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180028714`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a45c`
- `0x18001a630`
- `0x18001c360`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a499`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a532`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a499`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001a532`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a4f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a4f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5b8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a563`

## string_xrefs

- `0x18001a473`: `SxLoadSystem32LibraryEx`

## pseudocode

```c
HINSTANCE __fastcall SxLoadSystem32LibraryEx(const unsigned __int16 *a1, void *a2)
{
  HMODULE Library; // rsi
  UINT SystemDirectoryW; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  UINT v9; // r14d
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned __int64 v12; // r15
  WCHAR *v13; // rax
  unsigned __int16 *v14; // rbx
  __int16 v15; // cx
  DWORD LastFailureAsHRESULT; // eax
  __int64 v18; // rdx
  UINT v19; // ecx
  __int64 v20; // r8
  __int64 v21; // r9
  __int16 v22; // ax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // [rsp+20h] [rbp-48h] BYREF
  __int16 v28; // [rsp+24h] [rbp-44h]
  __int16 v29; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxLoadSystem32LibraryEx", 1812, 1);
  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v9 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5, v7, v8);
    v15 = 1823;
    goto LABEL_6;
  }
  v27 = 0;
  v10 = -1;
  v28 = 1823;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  v12 = v11 + SystemDirectoryW + 1 + 1LL;
  v13 = (WCHAR *)LocalAlloc(0, 2 * v12);
  v14 = v13;
  v15 = 1829;
  if ( !v13 )
  {
    LastFailureAsHRESULT = -2147024882;
LABEL_6:
    v27 = LastFailureAsHRESULT;
    v29 = v15;
    goto LABEL_7;
  }
  v28 = 1829;
  v27 = 0;
  v19 = GetSystemDirectoryW(v13, v9);
  if ( v19 )
  {
    v28 = 1832;
    v22 = 1833;
    if ( v19 < v9 )
    {
      v27 = 0;
      v28 = 1833;
      do
        ++v10;
      while ( v14[v10] );
      if ( v14[v10 - 1] != 92 )
      {
        v27 = StringCchCatW(v14, v12, L"\\");
        v22 = 1837;
        if ( v27 < 0 )
          goto LABEL_13;
        v28 = 1837;
      }
      v27 = StringCchCatW(v14, v12, a1);
      v22 = 1840;
      if ( v27 >= 0 )
      {
        v28 = 1840;
        Library = LoadLibraryExW(v14, 0, 2u);
        if ( Library )
        {
          v27 = 0;
          v28 = 1843;
        }
        else
        {
          v27 = GetLastFailureAsHRESULT(v24, v23, v25, v26);
          v29 = 1843;
        }
        goto LABEL_14;
      }
    }
    else
    {
      v27 = -2147024785;
    }
  }
  else
  {
    v27 = GetLastFailureAsHRESULT(0, v18, v20, v21);
    v22 = 1832;
  }
LABEL_13:
  v29 = v22;
LABEL_14:
  LocalFree(v14);
  if ( Library )
    goto LABEL_8;
  LastFailureAsHRESULT = v27;
LABEL_7:
  SetLastError(LastFailureAsHRESULT);
LABEL_8:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return Library;
}

```

## disassembly

```asm
0x18001a45c  push    rbp
0x18001a45e  push    rbx
0x18001a45f  push    rsi
0x18001a460  push    rdi
0x18001a461  push    r12
0x18001a463  push    r13
0x18001a465  push    r14
0x18001a467  push    r15
0x18001a469  mov     rbp, rsp
0x18001a46c  sub     rsp, 68h
0x18001a470  mov     r12, rcx
0x18001a473  lea     rdx, aSxloadsystem32; "SxLoadSystem32LibraryEx"
0x18001a47a  lea     rcx, [rbp+var_48]; this
0x18001a47e  mov     r9d, 1; unsigned __int16
0x18001a484  mov     r8d, 714h; unsigned __int16
0x18001a48a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a48f  xor     r13d, r13d
0x18001a492  xor     edx, edx; uSize
0x18001a494  xor     ecx, ecx; lpBuffer
0x18001a496  mov     esi, r13d
0x18001a499  call    cs:__imp_GetSystemDirectoryW
0x18001a49f  mov     r14d, eax
0x18001a4a2  test    eax, eax
0x18001a4a4  jz      short loc_18001A518
0x18001a4a6  mov     ecx, 71Fh
0x18001a4ab  mov     [rbp+var_48], r13d
0x18001a4af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001a4b3  mov     [rbp+var_44], cx
0x18001a4b7  mov     rdx, rdi
0x18001a4ba  inc     rdx
0x18001a4bd  cmp     [r12+rdx*2], r13w
0x18001a4c2  jnz     short loc_18001A4BA
0x18001a4c4  lea     r15d, [rax+1]
0x18001a4c8  xor     ecx, ecx; uFlags
0x18001a4ca  inc     r15
0x18001a4cd  add     r15, rdx
0x18001a4d0  lea     rdx, [r15+r15]; uBytes
0x18001a4d4  call    cs:__imp_LocalAlloc
0x18001a4da  mov     rbx, rax
0x18001a4dd  mov     ecx, 725h
0x18001a4e2  test    rax, rax
0x18001a4e5  jnz     short loc_18001A524
0x18001a4e7  mov     eax, 8007000Eh
0x18001a4ec  mov     [rbp+var_48], eax
0x18001a4ef  mov     [rbp+var_42], cx
0x18001a4f3  mov     ecx, eax; dwErrCode
0x18001a4f5  call    cs:__imp_SetLastError
0x18001a4fb  lea     rcx, [rbp+var_48]; this
0x18001a4ff  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a504  mov     rax, rsi
0x18001a507  add     rsp, 68h
0x18001a50b  pop     r15
0x18001a50d  pop     r14
0x18001a50f  pop     r13
0x18001a511  pop     r12
0x18001a513  pop     rdi
0x18001a514  pop     rsi
0x18001a515  pop     rbx
0x18001a516  pop     rbp
0x18001a517  retn
0x18001a518  call    GetLastFailureAsHRESULT
0x18001a51d  mov     ecx, 71Fh
0x18001a522  jmp     short loc_18001A4EC
0x18001a524  mov     [rbp+var_44], cx
0x18001a528  mov     edx, r14d; uSize
0x18001a52b  mov     rcx, rbx; lpBuffer
0x18001a52e  mov     [rbp+var_48], r13d
0x18001a532  call    cs:__imp_GetSystemDirectoryW
0x18001a538  mov     ecx, eax
0x18001a53a  test    eax, eax
0x18001a53c  jz      loc_18001A5D9
0x18001a542  mov     eax, 728h
0x18001a547  mov     [rbp+var_44], ax
0x18001a54b  mov     eax, 729h
0x18001a550  cmp     ecx, r14d
0x18001a553  jb      short loc_18001A573
0x18001a555  mov     [rbp+var_48], 8007006Fh
0x18001a55c  mov     [rbp+var_42], ax
0x18001a560  mov     rcx, rbx; hMem
0x18001a563  call    cs:__imp_LocalFree
0x18001a569  test    rsi, rsi
0x18001a56c  jnz     short loc_18001A4FB
0x18001a56e  mov     eax, [rbp+var_48]
0x18001a571  jmp     short loc_18001A4F3
0x18001a573  mov     [rbp+var_48], r13d
0x18001a577  mov     [rbp+var_44], ax
0x18001a57b  inc     rdi
0x18001a57e  cmp     [rbx+rdi*2], r13w
0x18001a583  jnz     short loc_18001A57B
0x18001a585  mov     eax, 5Ch ; '\'
0x18001a58a  cmp     ax, [rbx+rdi*2-2]
0x18001a58f  jnz     short loc_18001A5FD
0x18001a591  mov     r8, r12; unsigned __int16 *
0x18001a594  mov     rdx, r15; unsigned __int64
0x18001a597  mov     rcx, rbx; unsigned __int16 *
0x18001a59a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a59f  mov     [rbp+var_48], eax
0x18001a5a2  test    eax, eax
0x18001a5a4  mov     eax, 730h
0x18001a5a9  js      short loc_18001A55C
0x18001a5ab  xor     edx, edx; hFile
0x18001a5ad  mov     [rbp+var_44], ax
0x18001a5b1  mov     rcx, rbx; lpLibFileName
0x18001a5b4  lea     r8d, [rdx+2]; dwFlags
0x18001a5b8  call    cs:__imp_LoadLibraryExW
0x18001a5be  mov     rsi, rax
0x18001a5c1  test    rax, rax
0x18001a5c4  jnz     short loc_18001A5EB
0x18001a5c6  call    GetLastFailureAsHRESULT
0x18001a5cb  mov     ecx, 733h
0x18001a5d0  mov     [rbp+var_48], eax
0x18001a5d3  mov     [rbp+var_42], cx
0x18001a5d7  jmp     short loc_18001A560
0x18001a5d9  call    GetLastFailureAsHRESULT
0x18001a5de  mov     [rbp+var_48], eax
0x18001a5e1  mov     eax, 728h
0x18001a5e6  jmp     loc_18001A55C
0x18001a5eb  mov     ecx, 733h
0x18001a5f0  mov     [rbp+var_48], r13d
0x18001a5f4  mov     [rbp+var_44], cx
0x18001a5f8  jmp     loc_18001A560
0x18001a5fd  lea     r8, asc_180070370; "\\"
0x18001a604  mov     rdx, r15; unsigned __int64
0x18001a607  mov     rcx, rbx; unsigned __int16 *
0x18001a60a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a60f  mov     [rbp+var_48], eax
0x18001a612  test    eax, eax
0x18001a614  mov     eax, 72Dh
0x18001a619  js      loc_18001A55C
0x18001a61f  mov     [rbp+var_44], ax
0x18001a623  jmp     loc_18001A591
```
