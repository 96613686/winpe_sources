# DebugInitEx

- ea: `0x180001fd0`
- end: `0x1800021b3`
- name: `DebugInitEx`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001320`
- `0x18000b010`

## callees

- `0x180001fd0`
- `0x18001487c`
- `0x180014a40`
- `0x180015528`
- `0x1800263ce`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000201a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000201a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000203a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000203a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002074`
- `api-ms-win-core-psapi-ansi-l1-1-0!K32GetModuleBaseNameA` at `0x180002030`
- `api-ms-win-core-psapi-ansi-l1-1-0!K32GetModuleBaseNameA` at `0x180002030`
- `rtutils!TraceRegisterExA` at `0x180002059`
- `rtutils!TraceRegisterExA` at `0x180002059`

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
0x180001fd0  sub     rsp, 78h
0x180001fd4  mov     rax, cs:__security_cookie
0x180001fdb  xor     rax, rsp
0x180001fde  mov     [rsp+78h+var_18], rax
0x180001fe3  xor     edx, edx; Val
0x180001fe5  lea     rcx, [rsp+78h+BaseName]; void *
0x180001fea  mov     r8d, 40h ; '@'; Size
0x180001ff0  call    memset_0
0x180001ff5  mov     eax, gs:179Ch
0x180001ffd  test    eax, eax
0x180001fff  jnz     loc_1800020A3
0x180002005  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000200c  jnz     loc_1800020A3
0x180002012  cmp     cs:g_fUserHasSufficientRights, eax
0x180002018  jz      short loc_18000208C
0x18000201a  call    cs:__imp_GetCurrentProcess
0x180002020  mov     r9d, 40h ; '@'; nSize
0x180002026  lea     r8, [rsp+78h+BaseName]; lpBaseName
0x18000202b  mov     rcx, rax; hProcess
0x18000202e  xor     edx, edx; hModule
0x180002030  call    cs:__imp_K32GetModuleBaseNameA
0x180002036  test    eax, eax
0x180002038  jnz     short loc_1800020A7
0x18000203a  call    cs:__imp_GetLastError
0x180002040  mov     edx, eax
0x180002042  test    eax, eax
0x180002044  jg      loc_18000218A
0x18000204a  test    edx, edx
0x18000204c  js      loc_180002198
0x180002052  xor     edx, edx; dwFlags
0x180002054  lea     rcx, [rsp+78h+BaseName]; lpszCallerName
0x180002059  call    cs:__imp_TraceRegisterExA
0x18000205f  mov     cs:g_dwTraceId, eax
0x180002065  cmp     eax, 0FFFFFFFFh
0x180002068  jnz     short loc_1800020A3
0x18000206a  mov     cs:g_fUserHasSufficientRights, 0
0x180002074  call    cs:__imp_GetLastError
0x18000207a  mov     rcx, [rsp+78h+var_18]
0x18000207f  xor     rcx, rsp; StackCookie
0x180002082  call    __security_check_cookie
0x180002087  add     rsp, 78h
0x18000208b  retn
0x18000208c  mov     eax, 5
0x180002091  mov     rcx, [rsp+78h+var_18]
0x180002096  xor     rcx, rsp; StackCookie
0x180002099  call    __security_check_cookie
0x18000209e  add     rsp, 78h
0x1800020a2  retn
0x1800020a3  xor     eax, eax
0x1800020a5  jmp     short loc_18000207A
0x1800020a7  xor     eax, eax
0x1800020a9  cmp     [rsp+78h+BaseName], al
0x1800020ad  jz      short loc_1800020D1
0x1800020af  nop
0x1800020b0  cmp     [rsp+rax+78h+BaseName], 2Eh ; '.'
0x1800020b5  jz      short loc_1800020C7
0x1800020b7  cmp     rax, 3Fh ; '?'
0x1800020bb  jnb     short loc_1800020C7
0x1800020bd  inc     rax
0x1800020c0  cmp     [rsp+rax+78h+BaseName], 0
0x1800020c5  jnz     short loc_1800020B0
0x1800020c7  cmp     rax, 40h ; '@'
0x1800020cb  jnb     loc_180002184
0x1800020d1  mov     [rsp+rax+78h+BaseName], 0
0x1800020d6  mov     ecx, 40h ; '@'
0x1800020db  lea     rax, [rsp+78h+BaseName]
0x1800020e0  cmp     byte ptr [rax], 0
0x1800020e3  jz      short loc_1800020EE
0x1800020e5  inc     rax
0x1800020e8  sub     rcx, 1
0x1800020ec  jnz     short loc_1800020E0
0x1800020ee  xor     eax, eax
0x1800020f0  mov     edx, 80070057h
0x1800020f5  test    rcx, rcx
0x1800020f8  mov     r9d, 40h ; '@'
0x1800020fe  cmovnz  edx, eax
0x180002101  sub     r9, rcx
0x180002104  test    rcx, rcx
0x180002107  cmovz   r9, rax
0x18000210b  jz      loc_18000204A
0x180002111  mov     r8d, 40h ; '@'
0x180002117  lea     rdx, asc_180029624; "_"
0x18000211e  sub     r8, r9
0x180002121  mov     ecx, 7FFFFFFEh
0x180002126  lea     r9, [rsp+r9+78h+BaseName]
0x18000212b  jz      short loc_18000214E
0x18000212d  nop     dword ptr [rax]
0x180002130  test    rcx, rcx
0x180002133  jz      short loc_18000214E
0x180002135  movzx   eax, byte ptr [rdx]
0x180002138  test    al, al
0x18000213a  jz      short loc_18000214E
0x18000213c  mov     [r9], al
0x18000213f  inc     rdx
0x180002142  inc     r9
0x180002145  dec     rcx
0x180002148  sub     r8, 1
0x18000214c  jnz     short loc_180002130
0x18000214e  xor     eax, eax
0x180002150  mov     edx, 8007007Ah
0x180002155  test    r8, r8
0x180002158  cmovnz  edx, eax; cchDest
0x18000215b  lea     rax, [r9-1]
0x18000215f  cmovnz  rax, r9
0x180002163  mov     byte ptr [rax], 0
0x180002166  jz      loc_18000204A
0x18000216c  lea     r8, pszSrc; "RASMANCS"
0x180002173  lea     rcx, [rsp+78h+BaseName]; pszDest
0x180002178  call    StringCchCatA
0x18000217d  mov     edx, eax
0x18000217f  jmp     loc_18000204A
0x180002184  call    __report_rangecheckfailure
0x18000218a  movzx   edx, ax
0x18000218d  or      edx, 80070000h
0x180002193  jmp     loc_18000204A
0x180002198  lea     r8, pszSrc; "RASMANCS"
0x18000219f  mov     edx, 40h ; '@'; cchDest
0x1800021a4  lea     rcx, [rsp+78h+BaseName]; pszDest
0x1800021a9  call    StringCchCopyA
0x1800021ae  jmp     loc_180002052
```
