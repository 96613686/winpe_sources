# CreateLogFileDirectory(ushort const *,ushort * *)

- ea: `0x18000f210`
- end: `0x18000f39a`
- name: `?CreateLogFileDirectory@@YAJPEBGPEAPEAG@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013404`

## callees

- `0x18000f210`
- `0x18001297c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2e6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f297`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f297`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f382`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f382`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f226`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f2dc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f226`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000f2dc`
- `iisutil!PuDbgPrintError` at `0x18000f27f`
- `iisutil!PuDbgPrintError` at `0x18000f379`
- `iisutil!PuDbgPrintError` at `0x18000f27f`
- `iisutil!PuDbgPrintError` at `0x18000f379`

## string_xrefs

- `0x18000f278`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f36e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f254`: `Log File Directory creation failed first ExpandEnvironmentStrings call\n`
- `0x18000f271`: `CreateLogFileDirectory`
- `0x18000f362`: `CreateLogFileDirectory`
- `0x18000f2b7`: `Out of memory allocating the LogFileDirectory space to expand into \n`
- `0x18000f304`: `Log File Directory creation failed second ExpandEnvironmentStrings call\n`

## pseudocode

```c
__int64 __fastcall CreateLogFileDirectory(LPCWSTR lpSrc, unsigned __int16 **a2)
{
  DWORD v4; // eax
  DWORD v5; // esi
  signed int v6; // eax
  unsigned int v7; // ebx
  SIZE_T v8; // rbx
  WCHAR *v9; // rax
  unsigned __int16 *v10; // rdi
  DWORD v11; // eax
  signed int LastError; // eax
  __int64 v13; // rax

  v4 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    v8 = 2 * v4 + 12;
    v9 = (WCHAR *)GlobalAlloc(0, v8);
    v10 = v9;
    if ( v9 )
    {
      v11 = ExpandEnvironmentStringsW(lpSrc, v9, v5);
      if ( v11 )
      {
        if ( v11 > 1 )
        {
          v13 = v11 - 2;
          if ( v10[v13] == 92 )
            v10[(unsigned int)v13] = 0;
        }
        v7 = StringCchCatW(v10, v8 >> 1, L"\\W3SVC");
        if ( (v7 & 0x80000000) == 0 )
        {
          *a2 = v10;
          return v7;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
            6742,
            "CreateLogFileDirectory",
            v7,
            "String concatenation failed\n");
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
            6710,
            "CreateLogFileDirectory",
            v7,
            "Log File Directory creation failed second ExpandEnvironmentStrings call\n");
      }
      GlobalFree(v10);
    }
    else
    {
      v7 = -2147024882;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          6693,
          "CreateLogFileDirectory",
          -2147024882,
          "Out of memory allocating the LogFileDirectory space to expand into \n");
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        6671,
        "CreateLogFileDirectory",
        v7,
        "Log File Directory creation failed first ExpandEnvironmentStrings call\n");
  }
  return v7;
}

```

## disassembly

```asm
0x18000f210  push    rbx
0x18000f212  push    rbp
0x18000f213  push    rsi
0x18000f214  push    rdi
0x18000f215  push    r14
0x18000f217  sub     rsp, 30h
0x18000f21b  mov     r14, rdx
0x18000f21e  xor     r8d, r8d; nSize
0x18000f221  xor     edx, edx; lpDst
0x18000f223  mov     rbp, rcx
0x18000f226  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f22c  mov     esi, eax
0x18000f22e  test    eax, eax
0x18000f230  jnz     short loc_18000F28A
0x18000f232  call    cs:__imp_GetLastError
0x18000f238  mov     ebx, eax
0x18000f23a  test    eax, eax
0x18000f23c  jle     short loc_18000F247
0x18000f23e  movzx   ebx, ax
0x18000f241  or      ebx, 80070000h
0x18000f247  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f24e  jz      loc_18000F38D
0x18000f254  lea     rax, aLogFileDirecto_1; "Log File Directory creation failed firs"...
0x18000f25b  mov     r8d, 1A0Fh
0x18000f261  mov     [rsp+58h+var_30], rax
0x18000f266  mov     [rsp+58h+var_38], ebx
0x18000f26a  mov     rcx, cs:g_pDebug
0x18000f271  lea     r9, aCreatelogfiled; "CreateLogFileDirectory"
0x18000f278  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f27f  call    cs:__imp_PuDbgPrintError
0x18000f285  jmp     loc_18000F38D
0x18000f28a  lea     eax, ds:0Ch[rax*2]
0x18000f291  xor     ecx, ecx; uFlags
0x18000f293  mov     edx, eax; dwBytes
0x18000f295  mov     ebx, eax
0x18000f297  call    cs:__imp_GlobalAlloc
0x18000f29d  mov     rdi, rax
0x18000f2a0  test    rax, rax
0x18000f2a3  jnz     short loc_18000F2D3
0x18000f2a5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f2ac  mov     ebx, 8007000Eh
0x18000f2b1  jz      loc_18000F38D
0x18000f2b7  lea     rax, aOutOfMemoryAll; "Out of memory allocating the LogFileDir"...
0x18000f2be  mov     r8d, 1A25h
0x18000f2c4  mov     [rsp+58h+var_30], rax
0x18000f2c9  mov     [rsp+58h+var_38], 8007000Eh
0x18000f2d1  jmp     short loc_18000F26A
0x18000f2d3  mov     r8d, esi; nSize
0x18000f2d6  mov     rdx, rdi; lpDst
0x18000f2d9  mov     rcx, rbp; lpSrc
0x18000f2dc  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f2e2  test    eax, eax
0x18000f2e4  jnz     short loc_18000F313
0x18000f2e6  call    cs:__imp_GetLastError
0x18000f2ec  mov     ebx, eax
0x18000f2ee  test    eax, eax
0x18000f2f0  jle     short loc_18000F2FB
0x18000f2f2  movzx   ebx, ax
0x18000f2f5  or      ebx, 80070000h
0x18000f2fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f302  jz      short loc_18000F37F
0x18000f304  lea     rax, aLogFileDirecto; "Log File Directory creation failed seco"...
0x18000f30b  mov     r8d, 1A36h
0x18000f311  jmp     short loc_18000F35B
0x18000f313  cmp     eax, 1
0x18000f316  jbe     short loc_18000F32A
0x18000f318  add     eax, 0FFFFFFFEh
0x18000f31b  mov     ecx, eax
0x18000f31d  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x18000f322  jnz     short loc_18000F32A
0x18000f324  xor     eax, eax
0x18000f326  mov     [rdi+rcx*2], ax
0x18000f32a  shr     rbx, 1
0x18000f32d  lea     r8, aW3svc_1; "\\W3SVC"
0x18000f334  mov     rdx, rbx; unsigned __int64
0x18000f337  mov     rcx, rdi; unsigned __int16 *
0x18000f33a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f33f  mov     ebx, eax
0x18000f341  test    eax, eax
0x18000f343  jns     short loc_18000F38A
0x18000f345  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f34c  jz      short loc_18000F37F
0x18000f34e  lea     rax, aStringConcaten; "String concatenation failed\n"
0x18000f355  mov     r8d, 1A56h
0x18000f35b  mov     rcx, cs:g_pDebug
0x18000f362  lea     r9, aCreatelogfiled; "CreateLogFileDirectory"
0x18000f369  mov     [rsp+58h+var_30], rax
0x18000f36e  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f375  mov     [rsp+58h+var_38], ebx
0x18000f379  call    cs:__imp_PuDbgPrintError
0x18000f37f  mov     rcx, rdi; hMem
0x18000f382  call    cs:__imp_GlobalFree
0x18000f388  jmp     short loc_18000F38D
0x18000f38a  mov     [r14], rdi
0x18000f38d  mov     eax, ebx
0x18000f38f  add     rsp, 30h
0x18000f393  pop     r14
0x18000f395  pop     rdi
0x18000f396  pop     rsi
0x18000f397  pop     rbp
0x18000f398  pop     rbx
0x18000f399  retn
```
