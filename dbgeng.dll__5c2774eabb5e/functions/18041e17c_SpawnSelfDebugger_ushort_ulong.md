# SpawnSelfDebugger(ushort *,ulong)

- ea: `0x18041e17c`
- end: `0x18041e3bf`
- name: `?SpawnSelfDebugger@@YAJPEAGK@Z`
- size: `579`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ef6c0`

## callees

- `0x1800c04b8`
- `0x1800e5b60`
- `0x1800f0f40`
- `0x1800f17b0`
- `0x1801624dc`
- `0x180162548`
- `0x18041e17c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18041e1b6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18041e1b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041e33d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18041e273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18041e273`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18041e32d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18041e32d`
- `api-ms-win-crt-process-l1-1-0!_spawnlp` at `0x18041e2f2`
- `api-ms-win-crt-process-l1-1-0!_spawnlp` at `0x18041e2f2`

## pseudocode

```c
signed int __fastcall SpawnSelfDebugger(unsigned __int16 *a1)
{
  signed int result; // eax
  __int64 v3; // rax
  char *v4; // rcx
  char *v5; // rdx
  char v6; // al
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax
  DWORD nSize; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[16]; // [rsp+58h] [rbp-A8h] BYREF
  char v11[40]; // [rsp+78h] [rbp-88h] BYREF
  char v12; // [rsp+A0h] [rbp-60h] BYREF
  CHAR Filename[95]; // [rsp+A1h] [rbp-5Fh] BYREF
  __int64 v14; // [rsp+100h] [rbp+0h] BYREF

  if ( GetModuleFileNameA(0, Filename, 0x104u) )
  {
    v12 = 34;
    v3 = -1;
    do
      ++v3;
    while ( Filename[v3 - 1] );
    v4 = &Filename[v3 - 1];
    do
    {
      v5 = v4--;
      if ( v4 < &v12 )
        break;
      v6 = *v4;
      if ( *v4 == 92 )
        break;
    }
    while ( v6 != 47 && v6 != 58 );
    if ( v5 > &v12 )
      StringCchCopyA(v4, (unsigned int)&v14 + 166 - (unsigned int)v5, "\"");
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfA(v11, 0x20u, "%d", CurrentProcessId);
    if ( _spawnlp(
           1,
           "cmd.exe",
           "/c",
           "start /d",
           &v12,
           "cdb.exe -server",
           "npipe:icfenable,pipe=cdb_pipe",
           "-p",
           v11,
           0) >= 0 )
    {
      if ( a1 )
      {
        nSize = 16;
        if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
        {
          if ( nSize )
          {
            if ( 2 * (unsigned __int64)nSize >= 0x20 )
              _report_rangecheckfailure();
            Buffer[nSize] = 0;
          }
          else
          {
            StringCchCopyW(Buffer, 0x10u, L"<???>");
          }
        }
        else
        {
          LastError = GetLastError();
          StringCchPrintfW(Buffer, 0x10u, L"<error %d>", LastError);
        }
        return StringCchPrintfW(a1, 0x50u, L"-remote %hs,server=%s", "npipe:icfenable,pipe=cdb_pipe", Buffer);
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  else if ( GetLastError() )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x18041e17c  mov     [rsp-8+arg_8], rbx
0x18041e181  mov     [rsp-8+arg_10], rsi
0x18041e186  push    rbp
0x18041e187  lea     rbp, [rsp-0C0h]
0x18041e18f  sub     rsp, 1C0h
0x18041e196  mov     rax, cs:__security_cookie
0x18041e19d  xor     rax, rsp
0x18041e1a0  mov     [rbp+0C0h+var_10], rax
0x18041e1a7  mov     rbx, rcx
0x18041e1aa  lea     rdx, [rbp+0C0h+Filename]; lpFilename
0x18041e1ae  xor     ecx, ecx; hModule
0x18041e1b0  mov     r8d, 104h; nSize
0x18041e1b6  call    cs:__imp_GetModuleFileNameA
0x18041e1bd  nop     dword ptr [rax+rax+00h]
0x18041e1c2  test    eax, eax
0x18041e1c4  jnz     short loc_18041E21A
0x18041e1c6  call    cs:__imp_GetLastError
0x18041e1cd  nop     dword ptr [rax+rax+00h]
0x18041e1d2  test    eax, eax
0x18041e1d4  jnz     short loc_18041E200
0x18041e1d6  mov     eax, 80004005h
0x18041e1db  mov     rcx, [rbp+0C0h+var_10]
0x18041e1e2  xor     rcx, rsp; StackCookie
0x18041e1e5  call    __security_check_cookie
0x18041e1ea  lea     r11, [rsp+1C0h+var_s0]
0x18041e1f2  mov     rbx, [r11+18h]
0x18041e1f6  mov     rsi, [r11+20h]
0x18041e1fa  mov     rsp, r11
0x18041e1fd  pop     rbp
0x18041e1fe  retn
0x18041e200  call    cs:__imp_GetLastError
0x18041e207  nop     dword ptr [rax+rax+00h]
0x18041e20c  test    eax, eax
0x18041e20e  jle     short loc_18041E1DB
0x18041e210  movzx   eax, ax
0x18041e213  or      eax, 80070000h
0x18041e218  jmp     short loc_18041E1DB
0x18041e21a  mov     [rbp+0C0h+var_120], 22h ; '"'
0x18041e21e  lea     rcx, [rbp+0C0h+var_120]
0x18041e222  or      rax, 0FFFFFFFFFFFFFFFFh
0x18041e226  inc     rax
0x18041e229  cmp     byte ptr [rcx+rax], 0
0x18041e22d  jnz     short loc_18041E226
0x18041e22f  lea     rcx, [rbp+0C0h+var_120]
0x18041e233  add     rcx, rax
0x18041e236  mov     rdx, rcx
0x18041e239  lea     rax, [rbp+0C0h+var_120]
0x18041e23d  dec     rcx; char *
0x18041e240  cmp     rcx, rax
0x18041e243  jb      short loc_18041E253
0x18041e245  mov     al, [rcx]
0x18041e247  cmp     al, 5Ch ; '\'
0x18041e249  jz      short loc_18041E253
0x18041e24b  cmp     al, 2Fh ; '/'
0x18041e24d  jz      short loc_18041E253
0x18041e24f  cmp     al, 3Ah ; ':'
0x18041e251  jnz     short loc_18041E236
0x18041e253  lea     rax, [rbp+0C0h+var_120]
0x18041e257  cmp     rdx, rax
0x18041e25a  jbe     short loc_18041E273
0x18041e25c  lea     rax, [rbp+0C0h+var_1A]
0x18041e263  sub     eax, edx
0x18041e265  lea     r8, asc_1806896A8; "\""
0x18041e26c  mov     edx, eax; unsigned __int64
0x18041e26e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18041e273  call    cs:__imp_GetCurrentProcessId
0x18041e27a  nop     dword ptr [rax+rax+00h]
0x18041e27f  lea     r8, aD_5; "%d"
0x18041e286  mov     edx, 20h ; ' '; unsigned __int64
0x18041e28b  mov     r9d, eax
0x18041e28e  lea     rcx, [rsp+1C0h+var_148]; char *
0x18041e293  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18041e298  mov     [rsp+1C0h+var_178], 0
0x18041e2a1  lea     rax, [rsp+1C0h+var_148]
0x18041e2a6  mov     [rsp+1C0h+var_180], rax
0x18041e2ab  lea     rsi, aNpipeIcfenable; "npipe:icfenable,pipe=cdb_pipe"
0x18041e2b2  lea     rax, aP_0; "-p"
0x18041e2b9  mov     ecx, 1; Mode
0x18041e2be  mov     [rsp+1C0h+var_188], rax
0x18041e2c3  lea     r9, aStartD; "start /d"
0x18041e2ca  lea     rax, aCdbExeServer; "cdb.exe -server"
0x18041e2d1  mov     [rsp+1C0h+var_190], rsi
0x18041e2d6  mov     [rsp+1C0h+var_198], rax
0x18041e2db  lea     r8, Arguments; "/c"
0x18041e2e2  lea     rax, [rbp+0C0h+var_120]
0x18041e2e6  lea     rdx, aCmdExe; "cmd.exe"
0x18041e2ed  mov     [rsp+1C0h+var_1A0], rax
0x18041e2f2  call    cs:__imp__spawnlp
0x18041e2f9  nop     dword ptr [rax+rax+00h]
0x18041e2fe  test    rax, rax
0x18041e301  jns     short loc_18041E30D
0x18041e303  mov     eax, 8007000Eh
0x18041e308  jmp     loc_18041E1DB
0x18041e30d  test    rbx, rbx
0x18041e310  jnz     short loc_18041E319
0x18041e312  xor     eax, eax
0x18041e314  jmp     loc_18041E1DB
0x18041e319  lea     r8, [rsp+1C0h+nSize]; nSize
0x18041e31e  mov     [rsp+1C0h+nSize], 10h
0x18041e326  lea     rdx, [rsp+1C0h+Buffer]; lpBuffer
0x18041e32b  xor     ecx, ecx; NameType
0x18041e32d  call    cs:__imp_GetComputerNameExW
0x18041e334  nop     dword ptr [rax+rax+00h]
0x18041e339  test    eax, eax
0x18041e33b  jnz     short loc_18041E364
0x18041e33d  call    cs:__imp_GetLastError
0x18041e344  nop     dword ptr [rax+rax+00h]
0x18041e349  lea     r8, aErrorD; "<error %d>"
0x18041e350  mov     edx, 10h; unsigned __int64
0x18041e355  mov     r9d, eax
0x18041e358  lea     rcx, [rsp+1C0h+Buffer]; unsigned __int16 *
0x18041e35d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18041e362  jmp     short loc_18041E393
0x18041e364  mov     eax, [rsp+1C0h+nSize]
0x18041e368  test    eax, eax
0x18041e36a  jnz     short loc_18041E382
0x18041e36c  lea     r8, asc_180611CE8; "<???>"
0x18041e373  lea     edx, [rax+10h]; unsigned __int64
0x18041e376  lea     rcx, [rsp+1C0h+Buffer]; wchar_t *
0x18041e37b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18041e380  jmp     short loc_18041E393
0x18041e382  lea     rdx, [rax+rax]
0x18041e386  cmp     rdx, 20h ; ' '
0x18041e38a  jnb     short loc_18041E3B9
0x18041e38c  xor     eax, eax
0x18041e38e  mov     [rsp+rdx+1C0h+Buffer], ax
0x18041e393  lea     rax, [rsp+1C0h+Buffer]
0x18041e398  mov     r9, rsi
0x18041e39b  lea     r8, aRemoteHsServer; "-remote %hs,server=%s"
0x18041e3a2  mov     [rsp+1C0h+var_1A0], rax
0x18041e3a7  mov     edx, 50h ; 'P'; unsigned __int64
0x18041e3ac  mov     rcx, rbx; unsigned __int16 *
0x18041e3af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18041e3b4  jmp     loc_18041E1DB
0x18041e3b9  call    __report_rangecheckfailure
```
