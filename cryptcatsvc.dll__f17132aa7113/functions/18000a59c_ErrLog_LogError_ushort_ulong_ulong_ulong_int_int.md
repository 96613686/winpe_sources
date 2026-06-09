# ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)

- ea: `0x18000a59c`
- end: `0x18000a707`
- name: `?ErrLog_LogError@@YAXPEAGKKKHH@Z`
- size: `363`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `76`
- callee_count: `5`
- tags: ``

## callers

- `0x180001264`
- `0x180001328`
- `0x180001950`
- `0x1800019a0`
- `0x180001ce0`
- `0x180002410`
- `0x180002b90`
- `0x180002fd0`
- `0x180003570`
- `0x1800038f0`
- `0x18000392c`
- `0x180003b80`
- `0x180003c50`
- `0x180003ef0`
- `0x180003f80`
- `0x180004094`
- `0x1800042b0`
- `0x180004a20`
- `0x180004b98`
- `0x18000849c`
- `0x180008888`
- `0x180008a6c`
- `0x180009084`
- `0x1800095cc`
- `0x18000a2bc`
- `0x18000a490`
- `0x18000a918`
- `0x18000aad4`
- `0x18000ad54`
- `0x180012700`
- `0x180012ce0`
- `0x1800131b8`
- `0x180014608`
- `0x1800153dc`
- `0x180017a04`
- `0x1800181f4`
- `0x18001825c`
- `0x1800184c8`
- `0x180018620`
- `0x1800186e8`
- `0x1800187ec`
- `0x1800188dc`
- `0x180018b38`
- `0x1800190f8`
- `0x180019314`
- `0x18001966c`
- `0x180019a7c`
- `0x180019c8c`
- `0x180019fe0`
- `0x18001a290`

## callees

- `0x180008f08`
- `0x18000a59c`
- `0x18000be40`
- `0x18001f6b8`
- `0x18001f968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6de`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000a5fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000a5fd`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x18000a625`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x18000a625`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18000a666`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18000a666`

## pseudocode

```c
void __fastcall ErrLog_LogError(unsigned __int16 *a1, __int64 a2, int a3, int a4, int a5)
{
  DWORD LastError; // edi
  int TimeFormatA; // eax
  const char *v9; // r8
  int v10; // eax
  CHAR *lpTimeStr; // [rsp+20h] [rbp-358h]
  __int64 cchTime; // [rsp+28h] [rbp-350h]
  int v13; // [rsp+30h] [rbp-348h]
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-338h] BYREF
  CHAR TimeStr[256]; // [rsp+50h] [rbp-328h] BYREF
  char v16[512]; // [rsp+150h] [rbp-228h] BYREF

  SystemTime = 0;
  LastError = GetLastError();
  if ( !g_fErrLogInitialized )
    ErrLog_Initialize();
  if ( g_fLogWarnings || !a5 )
  {
    GetLocalTime(&SystemTime);
    TimeFormatA = GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 256);
    if ( (unsigned int)(TimeFormatA - 1) <= 0xFF )
    {
      lpTimeStr = &TimeStr[TimeFormatA];
      *(lpTimeStr - 1) = 32;
      GetDateFormatA(0x400u, 1u, &SystemTime, 0, lpTimeStr, 256 - TimeFormatA);
      if ( !a4 )
        a4 = LastError;
      if ( (a4 & 0x1FFF0000) == 0xE5E0000 )
      {
        v9 = "CatalogDB: %s: %s at line #%u encountered JET error %d\r\n";
        v10 = -(unsigned __int16)a4;
        if ( a4 >= 0 )
          v10 = (unsigned __int16)a4;
        v13 = v10;
      }
      else
      {
        v13 = a4;
        v9 = "CatalogDB: %s: %s at line #%u encountered error 0x%.8lx\r\n";
      }
      LODWORD(cchTime) = a3;
      StringCchPrintfA(v16, 0x200u, v9, TimeStr, "catdbsvc.cpp", cchTime, v13);
      _WriteErrorOut(0, v16, 0);
    }
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x18000a59c  mov     [rsp+arg_0], rbx
0x18000a5a1  push    rbp
0x18000a5a2  push    rsi
0x18000a5a3  push    rdi
0x18000a5a4  sub     rsp, 360h
0x18000a5ab  mov     rax, cs:__security_cookie
0x18000a5b2  xor     rax, rsp
0x18000a5b5  mov     [rsp+378h+var_28], rax
0x18000a5bd  mov     ebx, r9d
0x18000a5c0  mov     ebp, r8d
0x18000a5c3  call    cs:__imp_GetLastError
0x18000a5c9  cmp     cs:?g_fErrLogInitialized@@3HA, 0; int g_fErrLogInitialized
0x18000a5d0  xorps   xmm0, xmm0
0x18000a5d3  movups  xmmword ptr [rsp+378h+SystemTime.wYear], xmm0
0x18000a5d8  mov     edi, eax
0x18000a5da  jnz     short loc_18000A5E1
0x18000a5dc  call    ?ErrLog_Initialize@@YAXXZ; ErrLog_Initialize(void)
0x18000a5e1  cmp     cs:?g_fLogWarnings@@3HA, 0; int g_fLogWarnings
0x18000a5e8  jnz     short loc_18000A5F8
0x18000a5ea  cmp     [rsp+378h+arg_20], 0
0x18000a5f2  jnz     loc_18000A6E4
0x18000a5f8  lea     rcx, [rsp+378h+SystemTime]; lpSystemTime
0x18000a5fd  call    cs:__imp_GetLocalTime
0x18000a603  lea     rax, [rsp+378h+TimeStr]
0x18000a608  mov     esi, 100h
0x18000a60d  mov     dword ptr [rsp+378h+cchTime], esi; cchTime
0x18000a611  lea     r8, [rsp+378h+SystemTime]; lpTime
0x18000a616  xor     r9d, r9d; lpFormat
0x18000a619  mov     [rsp+378h+lpTimeStr], rax; lpTimeStr
0x18000a61e  xor     edx, edx; dwFlags
0x18000a620  mov     ecx, 400h; Locale
0x18000a625  call    cs:__imp_GetTimeFormatA
0x18000a62b  lea     edx, [rax-1]
0x18000a62e  cmp     edx, 0FFh
0x18000a634  ja      loc_18000A6DC
0x18000a63a  movsxd  rdx, eax
0x18000a63d  lea     r8, [rsp+378h+TimeStr]
0x18000a642  add     r8, rdx
0x18000a645  xor     r9d, r9d; lpFormat
0x18000a648  sub     esi, eax
0x18000a64a  mov     ecx, 400h; Locale
0x18000a64f  mov     dword ptr [rsp+378h+cchTime], esi; cchDate
0x18000a653  mov     [rsp+378h+lpTimeStr], r8; lpDateStr
0x18000a658  mov     byte ptr [r8-1], 20h ; ' '
0x18000a65d  lea     edx, [r9+1]; dwFlags
0x18000a661  lea     r8, [rsp+378h+SystemTime]; lpDate
0x18000a666  call    cs:__imp_GetDateFormatA
0x18000a66c  test    ebx, ebx
0x18000a66e  lea     r9, [rsp+378h+TimeStr]
0x18000a673  mov     edx, 200h; unsigned __int64
0x18000a678  cmovz   ebx, edi
0x18000a67b  mov     eax, ebx
0x18000a67d  and     eax, 1FFF0000h
0x18000a682  cmp     eax, 0E5E0000h
0x18000a687  jnz     short loc_18000A6A2
0x18000a689  movzx   ecx, bx
0x18000a68c  lea     r8, aCatalogdbSSAtL; "CatalogDB: %s: %s at line #%u encounter"...
0x18000a693  mov     eax, ecx
0x18000a695  neg     eax
0x18000a697  test    ebx, ebx
0x18000a699  cmovns  eax, ecx
0x18000a69c  mov     [rsp+378h+var_348], eax
0x18000a6a0  jmp     short loc_18000A6AD
0x18000a6a2  mov     [rsp+378h+var_348], ebx
0x18000a6a6  lea     r8, aCatalogdbSSAtL_0; "CatalogDB: %s: %s at line #%u encounter"...
0x18000a6ad  lea     rax, aCatdbsvcCpp; "catdbsvc.cpp"
0x18000a6b4  mov     dword ptr [rsp+378h+cchTime], ebp
0x18000a6b8  lea     rcx, [rsp+378h+var_228]; char *
0x18000a6c0  mov     [rsp+378h+lpTimeStr], rax
0x18000a6c5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a6ca  xor     r8d, r8d; int
0x18000a6cd  lea     rdx, [rsp+378h+var_228]; char *
0x18000a6d5  xor     ecx, ecx; unsigned __int16 *
0x18000a6d7  call    ?_WriteErrorOut@@YAXPEAGPEADH@Z; _WriteErrorOut(ushort *,char *,int)
0x18000a6dc  mov     ecx, edi; dwErrCode
0x18000a6de  call    cs:__imp_SetLastError
0x18000a6e4  mov     rcx, [rsp+378h+var_28]
0x18000a6ec  xor     rcx, rsp; StackCookie
0x18000a6ef  call    __security_check_cookie
0x18000a6f4  mov     rbx, [rsp+378h+arg_0]
0x18000a6fc  add     rsp, 360h
0x18000a703  pop     rdi
0x18000a704  pop     rsi
0x18000a705  pop     rbp
0x18000a706  retn
```
