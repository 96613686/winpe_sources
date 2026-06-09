# DbgPrintfVW(ulong,ushort const *,char *)

- ea: `0x180028bec`
- end: `0x180028feb`
- name: `?DbgPrintfVW@@YAHKPEBGPEAD@Z`
- size: `1023`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180007da0`
- `0x180029000`

## callees

- `0x180005f00`
- `0x18000a320`
- `0x180012e80`
- `0x180014ffc`
- `0x18001d1ec`
- `0x1800287c0`
- `0x180028874`
- `0x180028bec`
- `0x180029058`
- `0x1800382c0`
- `0x18003b010`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180028f84`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180028fa1`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180028f84`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180028fa1`
- `msvcrt!fflush` at `0x180028e97`
- `msvcrt!fflush` at `0x180028f2a`
- `msvcrt!fflush` at `0x180028e97`
- `msvcrt!fflush` at `0x180028f2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028da4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028da4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028d07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028ee7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028d07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028d18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028d18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fbf`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180028d6d`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180028d6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028daf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028daf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028f41`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028f41`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180028df1`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180028df1`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180028d56`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180028d56`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180028dfc`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180028dfc`

## pseudocode

```c
__int64 __fastcall DbgPrintfVW(unsigned int a1, const unsigned __int16 *a2, char *a3)
{
  unsigned int v3; // r12d
  char *v4; // rdi
  void *v5; // r15
  int v6; // eax
  const unsigned __int16 *v7; // r8
  char *v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // esi
  HLOCAL v12; // r14
  unsigned __int16 *p_Buffer; // r13
  const char *SSString; // rax
  __int64 v15; // r14
  HANDLE StdHandle; // rax
  __int64 v17; // rsi
  DWORD v18; // eax
  UINT ACP; // eax
  unsigned int v20; // esi
  FILE *v21; // rax
  FILE *v22; // rax
  unsigned int v23; // eax
  char *v24; // rsi
  void (*v25)(const char *); // rsi
  int v27; // [rsp+30h] [rbp-398h]
  int v28; // [rsp+34h] [rbp-394h]
  char *hMem; // [rsp+40h] [rbp-388h]
  BOOL v31; // [rsp+48h] [rbp-380h]
  const char *v32; // [rsp+50h] [rbp-378h]
  char *v33; // [rsp+50h] [rbp-378h]
  void (*v34)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+50h] [rbp-378h]
  DWORD NumberOfCharsWritten; // [rsp+58h] [rbp-370h] BYREF
  char *v36; // [rsp+60h] [rbp-368h]
  char *v37; // [rsp+68h] [rbp-360h]
  __int64 v38; // [rsp+70h] [rbp-358h]
  HLOCAL v39; // [rsp+78h] [rbp-350h]
  char Str[256]; // [rsp+80h] [rbp-348h] BYREF
  char Buffer; // [rsp+180h] [rbp-248h] BYREF

  v37 = a3;
  v3 = 256;
  v4 = Str;
  v36 = Str;
  hMem = 0;
  v5 = 0;
  v39 = 0;
  Str[0] = 0;
  try
  {
    v11 = 256;
    p_Buffer = (unsigned __int16 *)&Buffer;
    NumberOfCharsWritten = 0;
    v38 = 0;
    v28 = 0;
    SSString = DbgGetSSString(a1);
    v32 = SSString;
    while ( 1 )
    {
      *p_Buffer = 0;
      if ( SSString )
      {
        v6 = StringCchPrintfW(p_Buffer, v11, L"%hs: ", SSString);
        if ( v6 )
          goto LABEL_8;
        v7 = a2;
        v8 = v37;
      }
      v9 = -1;
      do
        ++v9;
      while ( p_Buffer[v9] );
      v6 = StringCchVPrintfW(&p_Buffer[(unsigned int)v9], v11 - (unsigned int)v9, v7, v8);
      if ( !v6 )
        goto LABEL_14;
LABEL_8:
      if ( v6 != -2147024774 )
        goto LABEL_14;
      StringCchCopyW(&p_Buffer[v11 - 5], 5u, L"...\n");
      if ( v11 >= 0x20000 )
        goto LABEL_14;
      v10 = 2 * v11;
      v11 = 0x20000;
      if ( v10 < 0x20000 )
        v11 = v10;
      v12 = LocalAlloc(0, 2 * v11);
      if ( !v12 )
      {
LABEL_14:
        v15 = -1;
        do
          ++v15;
        while ( p_Buffer[v15] );
        v27 = v15;
        StdHandle = GetStdHandle(0xFFFFFFF4);
        v17 = (__int64)StdHandle;
        v38 = (__int64)StdHandle;
        if ( StdHandle != (HANDLE)-1LL )
        {
          v18 = GetFileType(StdHandle) & 0xFFFF7FFF;
          if ( v18 )
          {
            if ( v18 != 2 )
              v28 = 1;
          }
          else
          {
            v17 = -1;
            v38 = -1;
          }
        }
        EnterCriticalSection(&g_DBGCriticalSection);
        v31 = IsDebuggerPresent();
        if ( !v31 && (g_dwPrintMask & 0x20) != 0 && v17 != -1 )
        {
          if ( v28 )
          {
            while ( 1 )
            {
              ACP = GetACP();
              if ( DbgConvertWszToSz(ACP, v4, v3, p_Buffer) )
                break;
              StringCchCopyA(&v4[v3 - 5], 5u, "...\n");
              if ( v3 >= 0x20000 )
                break;
              v20 = 0x20000;
              if ( 2 * v3 < 0x20000 )
                v20 = 2 * v3;
              v33 = (char *)LocalAlloc(0, v20);
              if ( !v33 )
                break;
              LocalFree(hMem);
              v4 = v33;
              hMem = v33;
              v36 = v33;
              v3 = v20;
            }
            v21 = _acrt_iob_func(2u);
            fputsStripCR(v4, v21);
            v22 = _acrt_iob_func(2u);
            fflush(v22);
          }
          else
          {
            WriteConsoleW((HANDLE)v17, p_Buffer, v15, &NumberOfCharsWritten, 0);
          }
        }
        while ( !DbgConvertWszToSz(0xFDE9u, v4, v3, p_Buffer) )
        {
          StringCchCopyA(&v4[v3 - 5], 5u, "...\n");
          if ( v3 >= 0x20000 )
            break;
          v23 = 2 * v3;
          v3 = 0x20000;
          if ( v23 < 0x20000 )
            v3 = v23;
          v24 = (char *)LocalAlloc(0, v3);
          if ( !v24 )
            break;
          LocalFree(hMem);
          hMem = v24;
          v4 = v24;
          v36 = v24;
        }
        if ( g_pfDebugLog )
        {
          fputsStripCR(v4, g_pfDebugLog);
          fflush(g_pfDebugLog);
        }
        if ( v31 || g_dwPrintMask )
          OutputDebugStringW(p_Buffer);
        goto LABEL_49;
      }
      LocalFree(v5);
      v5 = v12;
      v39 = v12;
      p_Buffer = (unsigned __int16 *)v12;
      SSString = v32;
      v7 = a2;
      v8 = v37;
    }
  }
  catch ( ... )
  {
    v27 = 0;
    v4 = v36;
    LODWORD(v15) = 0;
  }
LABEL_49:
  LeaveCriticalSection(&g_DBGCriticalSection);
  if ( *v4 )
  {
    v25 = s_pfnLogString;
    if ( s_pfnLogString )
    {
      try
      {
        v34 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
        ((void (__fastcall *)(char *))v25)(v4);
        _set_se_translator(v34);
      }
      catch ( ... )
      {
        s_pfnLogString = 0;
        LODWORD(v15) = v27;
      }
    }
  }
  LocalFree(v39);
  LocalFree(hMem);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180028bec  push    rbx
0x180028bee  push    rsi
0x180028bef  push    rdi
0x180028bf0  push    r12
0x180028bf2  push    r13
0x180028bf4  push    r14
0x180028bf6  push    r15
0x180028bf8  sub     rsp, 390h
0x180028bff  mov     rax, cs:__security_cookie
0x180028c06  xor     rax, rsp
0x180028c09  mov     [rsp+3C8h+var_48], rax
0x180028c11  mov     r9, r8
0x180028c14  mov     [rsp+3C8h+var_360], r8
0x180028c19  mov     r8, rdx
0x180028c1c  mov     [rsp+3C8h+var_380], rdx
0x180028c21  mov     r12d, 100h
0x180028c27  lea     rdi, [rsp+3C8h+Str]
0x180028c2f  mov     [rsp+3C8h+var_368], rdi
0x180028c34  xor     ebx, ebx
0x180028c36  mov     [rsp+3C8h+hMem], rbx
0x180028c3b  mov     r15d, ebx
0x180028c3e  mov     [rsp+3C8h+var_350], rbx
0x180028c43  mov     [rsp+3C8h+var_390], ebx
0x180028c47  mov     [rsp+3C8h+Str], bl
0x180028c4e  mov     esi, r12d
0x180028c51  lea     r13, [rsp+3C8h+Buffer]
0x180028c59  mov     [rsp+3C8h+NumberOfCharsWritten], ebx
0x180028c5d  mov     [rsp+3C8h+var_358], rbx
0x180028c62  mov     [rsp+3C8h+var_394], ebx
0x180028c66  call    ?DbgGetSSString@@YAPEBDK@Z; DbgGetSSString(ulong)
0x180028c6b  mov     [rsp+3C8h+var_378], rax
0x180028c70  mov     r14d, 20000h
0x180028c76  mov     [r13+0], bx
0x180028c7b  test    rax, rax
0x180028c7e  jz      short loc_180028CA2
0x180028c80  mov     edx, esi; unsigned __int64
0x180028c82  mov     r9, rax
0x180028c85  lea     r8, aHs_0; "%hs: "
0x180028c8c  mov     rcx, r13; unsigned __int16 *
0x180028c8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028c94  test    eax, eax
0x180028c96  jnz     short loc_180028CCB
0x180028c98  mov     r8, [rsp+3C8h+var_380]; unsigned __int16 *
0x180028c9d  mov     r9, [rsp+3C8h+var_360]; char *
0x180028ca2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028ca6  inc     rcx
0x180028ca9  cmp     [r13+rcx*2+0], bx
0x180028caf  jnz     short loc_180028CA6
0x180028cb1  mov     edx, esi
0x180028cb3  sub     edx, ecx; unsigned __int64
0x180028cb5  mov     eax, ecx
0x180028cb7  lea     rcx, ds:0[rax*2]
0x180028cbf  add     rcx, r13; unsigned __int16 *
0x180028cc2  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180028cc7  test    eax, eax
0x180028cc9  jz      short loc_180028D3D
0x180028ccb  cmp     eax, 8007007Ah
0x180028cd0  jnz     short loc_180028D3D
0x180028cd2  lea     eax, [rsi-5]
0x180028cd5  lea     rcx, ds:0[rax*2]
0x180028cdd  add     rcx, r13; unsigned __int16 *
0x180028ce0  lea     r8, asc_18006B118; "...\n"
0x180028ce7  mov     edx, 5; unsigned __int64
0x180028cec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028cf1  cmp     esi, r14d
0x180028cf4  jnb     short loc_180028D3D
0x180028cf6  lea     eax, [rsi+rsi]
0x180028cf9  mov     esi, r14d
0x180028cfc  cmp     eax, r14d
0x180028cff  cmovb   esi, eax
0x180028d02  lea     edx, [rsi+rsi]; uBytes
0x180028d05  xor     ecx, ecx; uFlags
0x180028d07  call    cs:__imp_LocalAlloc
0x180028d0d  mov     r14, rax
0x180028d10  test    rax, rax
0x180028d13  jz      short loc_180028D3D
0x180028d15  mov     rcx, r15; hMem
0x180028d18  call    cs:__imp_LocalFree
0x180028d1e  mov     r15, r14
0x180028d21  mov     [rsp+3C8h+var_350], r14
0x180028d26  mov     r13, r14
0x180028d29  mov     rax, [rsp+3C8h+var_378]
0x180028d2e  mov     r8, [rsp+3C8h+var_380]
0x180028d33  mov     r9, [rsp+3C8h+var_360]
0x180028d38  jmp     loc_180028C70
0x180028d3d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180028d41  inc     r14
0x180028d44  cmp     [r13+r14*2+0], bx
0x180028d4a  jnz     short loc_180028D41
0x180028d4c  mov     [rsp+3C8h+var_398], r14d
0x180028d51  mov     ecx, 0FFFFFFF4h; nStdHandle
0x180028d56  call    cs:__imp_GetStdHandle
0x180028d5c  mov     rsi, rax
0x180028d5f  mov     [rsp+3C8h+var_358], rax
0x180028d64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028d68  jz      short loc_180028D97
0x180028d6a  mov     rcx, rax; hFile
0x180028d6d  call    cs:__imp_GetFileType
0x180028d73  and     eax, 0FFFF7FFFh
0x180028d78  mov     r15d, 1
0x180028d7e  jz      short loc_180028D8C
0x180028d80  cmp     eax, 2
0x180028d83  jz      short loc_180028D9D
0x180028d85  mov     [rsp+3C8h+var_394], r15d
0x180028d8a  jmp     short loc_180028D9D
0x180028d8c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028d90  mov     [rsp+3C8h+var_358], rsi
0x180028d95  jmp     short loc_180028D9D
0x180028d97  mov     r15d, 1
0x180028d9d  lea     rcx, ?g_DBGCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028da4  call    cs:__imp_EnterCriticalSection
0x180028daa  mov     [rsp+3C8h+var_390], r15d
0x180028daf  call    cs:__imp_IsDebuggerPresent
0x180028db5  mov     dword ptr [rsp+3C8h+var_380], eax
0x180028db9  test    eax, eax
0x180028dbb  jnz     loc_180028E9D
0x180028dc1  test    byte ptr cs:?g_dwPrintMask@@3KA, 20h; ulong g_dwPrintMask
0x180028dc8  jz      loc_180028E9D
0x180028dce  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180028dd2  jz      loc_180028E9D
0x180028dd8  cmp     [rsp+3C8h+var_394], ebx
0x180028ddc  jnz     short loc_180028DFC
0x180028dde  mov     [rsp+3C8h+lpReserved], rbx; lpReserved
0x180028de3  lea     r9, [rsp+3C8h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x180028de8  mov     r8d, r14d; nNumberOfCharsToWrite
0x180028deb  mov     rdx, r13; lpBuffer
0x180028dee  mov     rcx, rsi; hConsoleOutput
0x180028df1  call    cs:__imp_WriteConsoleW
0x180028df7  jmp     loc_180028E9D
0x180028dfc  call    cs:__imp_GetACP
0x180028e02  mov     ecx, eax; unsigned int
0x180028e04  mov     r9, r13; unsigned __int16 *
0x180028e07  mov     r8d, r12d; int
0x180028e0a  mov     rdx, rdi; char *
0x180028e0d  call    ?DbgConvertWszToSz@@YAKIPEADJPEBG@Z; DbgConvertWszToSz(uint,char *,long,ushort const *)
0x180028e12  test    eax, eax
0x180028e14  jnz     short loc_180028E75
0x180028e16  lea     ecx, [r12-5]
0x180028e1b  add     rcx, rdi; char *
0x180028e1e  lea     r8, asc_18006B124; "...\n"
0x180028e25  lea     edx, [rax+5]; unsigned __int64
0x180028e28  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180028e2d  mov     ecx, 20000h
0x180028e32  cmp     r12d, ecx
0x180028e35  jnb     short loc_180028E75
0x180028e37  lea     eax, [r12+r12]
0x180028e3b  mov     esi, ecx
0x180028e3d  cmp     eax, ecx
0x180028e3f  cmovb   esi, eax
0x180028e42  mov     edx, esi; uBytes
0x180028e44  xor     ecx, ecx; uFlags
0x180028e46  call    cs:__imp_LocalAlloc
0x180028e4c  mov     [rsp+3C8h+var_378], rax
0x180028e51  test    rax, rax
0x180028e54  jz      short loc_180028E75
0x180028e56  mov     rcx, [rsp+3C8h+hMem]; hMem
0x180028e5b  call    cs:__imp_LocalFree
0x180028e61  mov     rdi, [rsp+3C8h+var_378]
0x180028e66  mov     [rsp+3C8h+hMem], rdi
0x180028e6b  mov     [rsp+3C8h+var_368], rdi
0x180028e70  mov     r12d, esi
0x180028e73  jmp     short loc_180028DFC
0x180028e75  mov     ecx, 2; Ix
0x180028e7a  call    __acrt_iob_func
0x180028e7f  mov     rdx, rax; Stream
0x180028e82  mov     rcx, rdi; Str
0x180028e85  call    ?fputsStripCR@@YAXPEBDPEAU_iobuf@@@Z; fputsStripCR(char const *,_iobuf *)
0x180028e8a  mov     ecx, 2; Ix
0x180028e8f  call    __acrt_iob_func
0x180028e94  mov     rcx, rax; Stream
0x180028e97  call    cs:__imp_fflush
0x180028e9d  mov     r9, r13; unsigned __int16 *
0x180028ea0  mov     r8d, r12d; int
0x180028ea3  mov     rdx, rdi; char *
0x180028ea6  mov     ecx, 0FDE9h; unsigned int
0x180028eab  call    ?DbgConvertWszToSz@@YAKIPEADJPEBG@Z; DbgConvertWszToSz(uint,char *,long,ushort const *)
0x180028eb0  test    eax, eax
0x180028eb2  jnz     short loc_180028F0F
0x180028eb4  lea     ecx, [r12-5]
0x180028eb9  add     rcx, rdi; char *
0x180028ebc  lea     r8, asc_18006B124; "...\n"
0x180028ec3  lea     edx, [rax+5]; unsigned __int64
0x180028ec6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180028ecb  mov     ecx, 20000h
0x180028ed0  cmp     r12d, ecx
0x180028ed3  jnb     short loc_180028F0F
0x180028ed5  lea     eax, [r12+r12]
0x180028ed9  mov     r12d, ecx
0x180028edc  cmp     eax, ecx
0x180028ede  cmovb   r12d, eax
0x180028ee2  mov     edx, r12d; uBytes
0x180028ee5  xor     ecx, ecx; uFlags
0x180028ee7  call    cs:__imp_LocalAlloc
0x180028eed  mov     rsi, rax
0x180028ef0  test    rax, rax
0x180028ef3  jz      short loc_180028F0F
0x180028ef5  mov     rcx, [rsp+3C8h+hMem]; hMem
0x180028efa  call    cs:__imp_LocalFree
0x180028f00  mov     [rsp+3C8h+hMem], rsi
0x180028f05  mov     rdi, rsi
0x180028f08  mov     [rsp+3C8h+var_368], rsi
0x180028f0d  jmp     short loc_180028E9D
0x180028f0f  mov     rdx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x180028f16  test    rdx, rdx
0x180028f19  jz      short loc_180028F30
0x180028f1b  mov     rcx, rdi; Str
0x180028f1e  call    ?fputsStripCR@@YAXPEBDPEAU_iobuf@@@Z; fputsStripCR(char const *,_iobuf *)
0x180028f23  mov     rcx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x180028f2a  call    cs:__imp_fflush
0x180028f30  cmp     dword ptr [rsp+3C8h+var_380], ebx
0x180028f34  jnz     short loc_180028F3E
0x180028f36  cmp     cs:?g_dwPrintMask@@3KA, ebx; ulong g_dwPrintMask
0x180028f3c  jz      short loc_180028F48
0x180028f3e  mov     rcx, r13; lpOutputString
0x180028f41  call    cs:__imp_OutputDebugStringW
0x180028f47  nop
0x180028f48  jmp     short loc_180028F5B
0x180028f4a  xor     ebx, ebx
0x180028f4c  mov     rdi, [rsp+3C8h+var_368]
0x180028f51  mov     r14d, [rsp+3C8h+var_398]
0x180028f56  mov     r15d, [rsp+3C8h+var_390]
0x180028f5b  test    r15d, r15d
0x180028f5e  jz      short loc_180028F6D
0x180028f60  lea     rcx, ?g_DBGCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028f67  call    cs:__imp_LeaveCriticalSection
0x180028f6d  cmp     [rdi], bl
0x180028f6f  jz      short loc_180028FAF
0x180028f71  mov     rsi, cs:?s_pfnLogString@@3P6AXPEBD@ZEA; void (*s_pfnLogString)(char const *)
0x180028f78  test    rsi, rsi
0x180028f7b  jz      short loc_180028FAF
0x180028f7d  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x180028f84  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180028f8a  mov     rbx, rax
0x180028f8d  mov     [rsp+3C8h+var_378], rax
0x180028f92  mov     rcx, rdi
0x180028f95  mov     rax, rsi
0x180028f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f9d  nop
0x180028f9e  mov     rcx, rbx
0x180028fa1  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180028fa7  nop
0x180028fa8  jmp     short loc_180028FAF
0x180028faa  mov     r14d, [rsp+3C8h+var_398]
0x180028faf  mov     rcx, [rsp+3C8h+var_350]; hMem
0x180028fb4  call    cs:__imp_LocalFree
0x180028fba  mov     rcx, [rsp+3C8h+hMem]; hMem
0x180028fbf  call    cs:__imp_LocalFree
0x180028fc5  mov     eax, r14d
0x180028fc8  mov     rcx, [rsp+3C8h+var_48]
0x180028fd0  xor     rcx, rsp; StackCookie
0x180028fd3  call    __security_check_cookie
0x180028fd8  add     rsp, 390h
0x180028fdf  pop     r15
0x180028fe1  pop     r14
0x180028fe3  pop     r13
0x180028fe5  pop     r12
0x180028fe7  pop     rdi
0x180028fe8  pop     rsi
0x180028fe9  pop     rbx
0x180028fea  retn
```
