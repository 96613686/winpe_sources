# CEXTLOG::WriteLogDirectives(ulong)

- ea: `0x180007250`
- end: `0x1800073e6`
- name: `?WriteLogDirectives@CEXTLOG@@MEAAHK@Z`
- size: `406`
- prototype: `__int64 __fastcall(CEXTLOG *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004420`
- `0x180007250`
- `0x18000d598`
- `0x18000eca0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180007335`
- `msvcrt!sprintf_s` at `0x180007335`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800073a4`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800073a4`
- `IisRTL!PuDbgPrint` at `0x180007397`
- `IisRTL!PuDbgPrint` at `0x180007397`
- `IisRTL!??0STR@@QEAA@PEADKH@Z` at `0x180007299`
- `IisRTL!??0STR@@QEAA@PEADKH@Z` at `0x180007299`
- `IisRTL!?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z` at `0x1800072bb`
- `IisRTL!?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z` at `0x1800072bb`
- `KERNEL32!SetLastError` at `0x180007361`
- `KERNEL32!SetLastError` at `0x180007361`

## string_xrefs

- `0x180007390`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`
- `0x1800072eb`: `Internet Information Services`
- `0x180007377`: `WriteLogDirectives: Unable to write directives\n`
- `0x18000737e`: `CEXTLOG::WriteLogDirectives`

## pseudocode

```c
__int64 __fastcall CEXTLOG::WriteLogDirectives(ILOG_FILE **this, int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rsi
  _BYTE v8[32]; // [rsp+50h] [rbp-598h] BYREF
  const char *v9; // [rsp+70h] [rbp-578h]
  char v10[40]; // [rsp+88h] [rbp-560h] BYREF
  char v11[256]; // [rsp+B0h] [rbp-538h] BYREF
  char Buffer[1024]; // [rsp+1B0h] [rbp-438h] BYREF

  v4 = 1;
  if ( this[7] )
  {
    STR::STR((STR *)v8, v11, 0x100u, 0);
    CEXTLOG::GetFormatHeader((CEXTLOG *)this, (struct STR *)v8);
    CACHED_DATETIME_FORMATS::GetFormattedCurrentDateTime((CACHED_DATETIME_FORMATS *)(this + 198), v10);
    v5 = -1;
    do
      ++v5;
    while ( v10[v5] );
    v6 = (unsigned int)sprintf_s(
                         Buffer,
                         0x400u,
                         "#Software: Microsoft %s %d.%d\r\n#Version: %s\r\n#Date: %s %s\r\n#Fields: %s\r\n",
                         "Internet Information Services",
                         10,
                         0,
                         "1.0",
                         v10,
                         &v10[v5 + 1],
                         v9);
    if ( (unsigned __int64)this[13] >= 0xFFFFFFFF
      || (unsigned __int64)this[12] + (unsigned int)(v6 + a2) < *((unsigned int *)this + 26) )
    {
      if ( (unsigned int)ILOG_FILE::Write(this[7], Buffer, (unsigned int)v6) )
      {
        this[12] = (ILOG_FILE *)((char *)this[12] + v6);
        goto LABEL_9;
      }
    }
    else
    {
      SetLastError(0x7Au);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
          659,
          "CEXTLOG::WriteLogDirectives",
          "WriteLogDirectives: Unable to write directives\n");
    }
    v4 = 0;
LABEL_9:
    STR::~STR((STR *)v8);
  }
  return v4;
}

```

## disassembly

```asm
0x180007250  push    rbx
0x180007252  push    rbp
0x180007253  push    rsi
0x180007254  push    rdi
0x180007255  sub     rsp, 5C8h
0x18000725c  mov     rax, cs:__security_cookie
0x180007263  xor     rax, rsp
0x180007266  mov     [rsp+5E8h+var_38], rax
0x18000726e  cmp     qword ptr [rcx+38h], 0
0x180007273  mov     ebp, edx
0x180007275  mov     rbx, rcx
0x180007278  mov     edi, 1
0x18000727d  jz      loc_1800073AA
0x180007283  xor     r9d, r9d
0x180007286  lea     rdx, [rsp+5E8h+var_538]
0x18000728e  mov     r8d, 100h
0x180007294  lea     rcx, [rsp+5E8h+var_598]
0x180007299  call    cs:__imp_??0STR@@QEAA@PEADKH@Z; STR::STR(char *,ulong,int)
0x18000729f  lea     rdx, [rsp+5E8h+var_598]; struct STR *
0x1800072a4  mov     rcx, rbx; this
0x1800072a7  call    ?GetFormatHeader@CEXTLOG@@IEAAXPEAVSTR@@@Z; CEXTLOG::GetFormatHeader(STR *)
0x1800072ac  lea     rcx, [rbx+630h]
0x1800072b3  lea     rdx, [rsp+5E8h+var_560]
0x1800072bb  call    cs:__imp_?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedCurrentDateTime(char *)
0x1800072c1  mov     rcx, [rsp+5E8h+var_578]
0x1800072c6  lea     rdx, [rsp+5E8h+var_560]
0x1800072ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800072d2  inc     rax
0x1800072d5  cmp     byte ptr [rdx+rax], 0
0x1800072d9  jnz     short loc_1800072D2
0x1800072db  mov     [rsp+5E8h+var_5A0], rcx
0x1800072e0  lea     rdx, [rsp+5E8h+var_55F]
0x1800072e8  add     rax, rdx
0x1800072eb  lea     r9, aInternetInform; "Internet Information Services"
0x1800072f2  mov     [rsp+5E8h+var_5A8], rax
0x1800072f7  lea     r8, aSoftwareMicros; "#Software: Microsoft %s %d.%d\r\n#Versi"...
0x1800072fe  lea     rax, [rsp+5E8h+var_560]
0x180007306  mov     edx, 400h; BufferCount
0x18000730b  mov     [rsp+5E8h+var_5B0], rax
0x180007310  lea     rcx, [rsp+5E8h+Buffer]; Buffer
0x180007318  lea     rax, a10; "1.0"
0x18000731f  mov     [rsp+5E8h+var_5B8], rax
0x180007324  mov     [rsp+5E8h+var_5C0], 0
0x18000732d  mov     dword ptr [rsp+5E8h+var_5C8], 0Ah
0x180007335  call    cs:__imp_sprintf_s
0x18000733b  cmp     dword ptr [rbx+6Ch], 0
0x18000733f  mov     esi, eax
0x180007341  jnz     loc_1800073C8
0x180007347  cmp     dword ptr [rbx+68h], 0FFFFFFFFh
0x18000734b  jz      short loc_1800073C8
0x18000734d  mov     eax, [rbx+68h]
0x180007350  lea     ecx, [rsi+rbp]
0x180007353  add     rcx, [rbx+60h]
0x180007357  cmp     rcx, rax
0x18000735a  jb      short loc_1800073C8
0x18000735c  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180007361  call    cs:__imp_SetLastError
0x180007367  test    byte ptr cs:g_dwDebugFlags, 3
0x18000736e  jz      short loc_18000739D
0x180007370  mov     rcx, cs:g_pDebug
0x180007377  lea     rax, aWritelogdirect; "WriteLogDirectives: Unable to write dir"...
0x18000737e  lea     r9, aCextlogWritelo; "CEXTLOG::WriteLogDirectives"
0x180007385  mov     [rsp+5E8h+var_5C8], rax
0x18000738a  mov     r8d, 293h
0x180007390  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x180007397  call    cs:__imp_PuDbgPrint
0x18000739d  xor     edi, edi
0x18000739f  lea     rcx, [rsp+5E8h+var_598]
0x1800073a4  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x1800073aa  mov     eax, edi
0x1800073ac  mov     rcx, [rsp+5E8h+var_38]
0x1800073b4  xor     rcx, rsp; StackCookie
0x1800073b7  call    __security_check_cookie
0x1800073bc  add     rsp, 5C8h
0x1800073c3  pop     rdi
0x1800073c4  pop     rsi
0x1800073c5  pop     rbp
0x1800073c6  pop     rbx
0x1800073c7  retn
0x1800073c8  mov     rcx, [rbx+38h]; this
0x1800073cc  lea     rdx, [rsp+5E8h+Buffer]; Src
0x1800073d4  mov     r8d, esi; Size
0x1800073d7  call    ?Write@ILOG_FILE@@QEAAHPEADK@Z; ILOG_FILE::Write(char *,ulong)
0x1800073dc  test    eax, eax
0x1800073de  jz      short loc_18000739D
0x1800073e0  add     [rbx+60h], rsi
0x1800073e4  jmp     short loc_18000739F
```
