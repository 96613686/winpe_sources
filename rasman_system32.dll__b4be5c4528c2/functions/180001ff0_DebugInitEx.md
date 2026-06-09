# DebugInitEx

- ea: `0x180001ff0`
- end: `0x1800021f7`
- name: `DebugInitEx`
- size: `519`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001250`
- `0x18000b230`

## callees

- `0x180001ff0`
- `0x1800151ec`
- `0x180015428`
- `0x180015ec8`
- `0x18002739e`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000203e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000203e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020b4`
- `api-ms-win-core-psapi-ansi-l1-1-0!K32GetModuleBaseNameA` at `0x18000205a`
- `api-ms-win-core-psapi-ansi-l1-1-0!K32GetModuleBaseNameA` at `0x18000205a`
- `rtutils!TraceRegisterExA` at `0x180002093`
- `rtutils!TraceRegisterExA` at `0x180002093`

## pseudocode

```c
DWORD DebugInitEx()
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  size_t v2; // rdx
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  CHAR *v6; // rax
  __int64 v7; // r9
  const char *v8; // rdx
  bool v9; // zf
  __int64 v10; // r8
  __int64 v11; // rcx
  CHAR *v12; // r9
  CHAR *v13; // rax
  CHAR BaseName[64]; // [rsp+20h] [rbp-58h] BYREF

  memset_0(BaseName, 0, sizeof(BaseName));
  if ( !NtCurrentTeb()->IsImpersonating && g_dwTraceId == -1 )
  {
    if ( !g_fUserHasSufficientRights )
      return 5;
    CurrentProcess = GetCurrentProcess();
    if ( K32GetModuleBaseNameA(CurrentProcess, 0, BaseName, 0x40u) )
    {
      v4 = 0;
      if ( BaseName[0] )
      {
        do
        {
          if ( BaseName[v4] == 46 )
            break;
          if ( v4 >= 0x3F )
            break;
          ++v4;
        }
        while ( BaseName[v4] );
        if ( v4 >= 0x40 )
          _report_rangecheckfailure();
      }
      BaseName[v4] = 0;
      v5 = 64;
      v6 = BaseName;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      LODWORD(v2) = -2147024809;
      if ( v5 )
        LODWORD(v2) = 0;
      v7 = 64 - v5;
      if ( v5 )
      {
        v8 = "_";
        v10 = v5;
        v9 = v7 == 64;
        v11 = 2147483646;
        v12 = &BaseName[v7];
        if ( !v9 )
        {
          do
          {
            if ( !v11 )
              break;
            if ( !*v8 )
              break;
            *v12++ = *v8++;
            --v11;
            --v10;
          }
          while ( v10 );
        }
        v2 = 2147942522LL;
        if ( v10 )
          v2 = 0;
        v13 = v12 - 1;
        if ( v10 )
          v13 = v12;
        *v13 = 0;
        if ( v10 )
          LODWORD(v2) = StringCchCatA(BaseName, v2, "RASMANCS");
      }
    }
    else
    {
      LastError = GetLastError();
      LODWORD(v2) = LastError;
      if ( LastError > 0 )
        LODWORD(v2) = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (v2 & 0x80000000) != 0LL )
      StringCchCopyA(BaseName, 0x40u, "RASMANCS");
    g_dwTraceId = TraceRegisterExA(BaseName, 0);
    if ( g_dwTraceId == -1 )
    {
      g_fUserHasSufficientRights = 0;
      return GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001ff0  sub     rsp, 78h
0x180001ff4  mov     rax, cs:__security_cookie
0x180001ffb  xor     rax, rsp
0x180001ffe  mov     [rsp+78h+var_18], rax
0x180002003  xor     edx, edx; Val
0x180002005  lea     rcx, [rsp+78h+BaseName]; void *
0x18000200a  mov     r8d, 40h ; '@'; Size
0x180002010  call    memset_0
0x180002015  mov     eax, gs:179Ch
0x18000201d  test    eax, eax
0x18000201f  jnz     loc_1800020EB
0x180002025  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000202c  jnz     loc_1800020EB
0x180002032  cmp     cs:g_fUserHasSufficientRights, eax
0x180002038  jz      loc_1800020D3
0x18000203e  call    cs:__imp_GetCurrentProcess
0x180002045  nop     dword ptr [rax+rax+00h]
0x18000204a  mov     r9d, 40h ; '@'; nSize
0x180002050  lea     r8, [rsp+78h+BaseName]; lpBaseName
0x180002055  mov     rcx, rax; hProcess
0x180002058  xor     edx, edx; hModule
0x18000205a  call    cs:__imp_K32GetModuleBaseNameA
0x180002061  nop     dword ptr [rax+rax+00h]
0x180002066  test    eax, eax
0x180002068  jnz     loc_1800020EF
0x18000206e  call    cs:__imp_GetLastError
0x180002075  nop     dword ptr [rax+rax+00h]
0x18000207a  mov     edx, eax
0x18000207c  test    eax, eax
0x18000207e  jg      loc_1800021CE
0x180002084  test    edx, edx
0x180002086  js      loc_1800021DC
0x18000208c  xor     edx, edx; dwFlags
0x18000208e  lea     rcx, [rsp+78h+BaseName]; lpszCallerName
0x180002093  call    cs:__imp_TraceRegisterExA
0x18000209a  nop     dword ptr [rax+rax+00h]
0x18000209f  mov     cs:g_dwTraceId, eax
0x1800020a5  cmp     eax, 0FFFFFFFFh
0x1800020a8  jnz     short loc_1800020EB
0x1800020aa  mov     cs:g_fUserHasSufficientRights, 0
0x1800020b4  call    cs:__imp_GetLastError
0x1800020bb  nop     dword ptr [rax+rax+00h]
0x1800020c0  mov     rcx, [rsp+78h+var_18]
0x1800020c5  xor     rcx, rsp; StackCookie
0x1800020c8  call    __security_check_cookie
0x1800020cd  add     rsp, 78h
0x1800020d1  retn
0x1800020d3  mov     eax, 5
0x1800020d8  mov     rcx, [rsp+78h+var_18]
0x1800020dd  xor     rcx, rsp; StackCookie
0x1800020e0  call    __security_check_cookie
0x1800020e5  add     rsp, 78h
0x1800020e9  retn
0x1800020eb  xor     eax, eax
0x1800020ed  jmp     short loc_1800020C0
0x1800020ef  xor     eax, eax
0x1800020f1  cmp     [rsp+78h+BaseName], al
0x1800020f5  jz      short loc_180002118
0x1800020f7  cmp     [rsp+rax+78h+BaseName], 2Eh ; '.'
0x1800020fc  jz      short loc_18000210E
0x1800020fe  cmp     rax, 3Fh ; '?'
0x180002102  jnb     short loc_18000210E
0x180002104  inc     rax
0x180002107  cmp     [rsp+rax+78h+BaseName], 0
0x18000210c  jnz     short loc_1800020F7
0x18000210e  cmp     rax, 40h ; '@'
0x180002112  jnb     loc_1800021C8
0x180002118  mov     [rsp+rax+78h+BaseName], 0
0x18000211d  mov     ecx, 40h ; '@'
0x180002122  lea     rax, [rsp+78h+BaseName]
0x180002127  cmp     byte ptr [rax], 0
0x18000212a  jz      short loc_180002135
0x18000212c  inc     rax
0x18000212f  sub     rcx, 1
0x180002133  jnz     short loc_180002127
0x180002135  xor     eax, eax
0x180002137  mov     edx, 80070057h
0x18000213c  test    rcx, rcx
0x18000213f  mov     r9d, 40h ; '@'
0x180002145  cmovnz  edx, eax
0x180002148  sub     r9, rcx
0x18000214b  test    rcx, rcx
0x18000214e  cmovz   r9, rax
0x180002152  jz      loc_180002084
0x180002158  mov     r8d, 40h ; '@'
0x18000215e  lea     rdx, asc_18002A5E4; "_"
0x180002165  sub     r8, r9
0x180002168  mov     ecx, 7FFFFFFEh
0x18000216d  lea     r9, [rsp+r9+78h+BaseName]
0x180002172  jz      short loc_180002192
0x180002174  test    rcx, rcx
0x180002177  jz      short loc_180002192
0x180002179  movzx   eax, byte ptr [rdx]
0x18000217c  test    al, al
0x18000217e  jz      short loc_180002192
0x180002180  mov     [r9], al
0x180002183  inc     rdx
0x180002186  inc     r9
0x180002189  dec     rcx
0x18000218c  sub     r8, 1
0x180002190  jnz     short loc_180002174
0x180002192  xor     eax, eax
0x180002194  mov     edx, 8007007Ah
0x180002199  test    r8, r8
0x18000219c  cmovnz  edx, eax; cchDest
0x18000219f  lea     rax, [r9-1]
0x1800021a3  cmovnz  rax, r9
0x1800021a7  mov     byte ptr [rax], 0
0x1800021aa  jz      loc_180002084
0x1800021b0  lea     r8, pszSrc; "RASMANCS"
0x1800021b7  lea     rcx, [rsp+78h+BaseName]; pszDest
0x1800021bc  call    StringCchCatA
0x1800021c1  mov     edx, eax
0x1800021c3  jmp     loc_180002084
0x1800021c8  call    __report_rangecheckfailure
0x1800021ce  movzx   edx, ax
0x1800021d1  or      edx, 80070000h
0x1800021d7  jmp     loc_180002084
0x1800021dc  lea     r8, pszSrc; "RASMANCS"
0x1800021e3  mov     edx, 40h ; '@'; cchDest
0x1800021e8  lea     rcx, [rsp+78h+BaseName]; pszDest
0x1800021ed  call    StringCchCopyA
0x1800021f2  jmp     loc_18000208C
```
