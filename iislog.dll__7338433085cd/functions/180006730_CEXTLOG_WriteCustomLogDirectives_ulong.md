# CEXTLOG::WriteCustomLogDirectives(ulong)

- ea: `0x180006730`
- end: `0x180006865`
- name: `?WriteCustomLogDirectives@CEXTLOG@@MEAAHK@Z`
- size: `309`
- prototype: `__int64 __fastcall(CEXTLOG *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003b68`
- `0x180006730`
- `0x18000d598`
- `0x18000eca0`

## import_xrefs

- `IisRTL!??1STR@@QEAA@XZ` at `0x180006826`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180006826`
- `IisRTL!PuDbgPrint` at `0x180006819`
- `IisRTL!PuDbgPrint` at `0x180006819`
- `IisRTL!??0STR@@QEAA@PEADKH@Z` at `0x180006779`
- `IisRTL!??0STR@@QEAA@PEADKH@Z` at `0x180006779`
- `IisRTL!?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z` at `0x18000678b`
- `IisRTL!?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z` at `0x18000678b`
- `KERNEL32!SetLastError` at `0x1800067e3`
- `KERNEL32!SetLastError` at `0x1800067e3`

## string_xrefs

- `0x180006812`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`
- `0x1800067f9`: `WriteCustomLogDirectives: Unable to write directives\n`
- `0x180006800`: `CEXTLOG::WriteCustomLogDirectives`

## pseudocode

```c
__int64 __fastcall CEXTLOG::WriteCustomLogDirectives(CEXTLOG *this, int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rsi
  _BYTE v7[32]; // [rsp+30h] [rbp-298h] BYREF
  char *v8; // [rsp+50h] [rbp-278h]
  size_t Size; // [rsp+60h] [rbp-268h]
  char v10[40]; // [rsp+68h] [rbp-260h] BYREF
  char v11[512]; // [rsp+90h] [rbp-238h] BYREF

  v4 = 1;
  if ( *((_QWORD *)this + 7) )
  {
    STR::STR((STR *)v7, v11, 0x200u, 0);
    CACHED_DATETIME_FORMATS::GetFormattedCurrentDateTime((CEXTLOG *)((char *)this + 1584), v10);
    CEXTLOG::BuildCustomLogHeader(
      this,
      *((_DWORD *)this + 724),
      (struct LOG_PROPERTY_INFO **)this + 363,
      v10,
      *((const char **)this + 359),
      (struct STR *)v7);
    v5 = (unsigned int)Size;
    if ( *((_QWORD *)this + 13) >= 0xFFFFFFFF
      || *((_QWORD *)this + 12) + (unsigned __int64)(unsigned int)(Size + a2) < *((unsigned int *)this + 26) )
    {
      if ( (unsigned int)ILOG_FILE::Write(*((ILOG_FILE **)this + 7), v8, (unsigned int)Size) )
      {
        *((_QWORD *)this + 12) += v5;
        goto LABEL_7;
      }
    }
    else
    {
      SetLastError(0x7Au);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
          1132,
          "CEXTLOG::WriteCustomLogDirectives",
          "WriteCustomLogDirectives: Unable to write directives\n");
    }
    v4 = 0;
LABEL_7:
    STR::~STR((STR *)v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180006730  push    rbx
0x180006732  push    rbp
0x180006733  push    rsi
0x180006734  push    rdi
0x180006735  sub     rsp, 2A8h
0x18000673c  mov     rax, cs:__security_cookie
0x180006743  xor     rax, rsp
0x180006746  mov     [rsp+2C8h+var_38], rax
0x18000674e  cmp     qword ptr [rcx+38h], 0
0x180006753  mov     ebp, edx
0x180006755  mov     rbx, rcx
0x180006758  mov     edi, 1
0x18000675d  jz      loc_18000682C
0x180006763  xor     r9d, r9d
0x180006766  lea     rdx, [rsp+2C8h+var_238]
0x18000676e  mov     r8d, 200h
0x180006774  lea     rcx, [rsp+2C8h+var_298]
0x180006779  call    cs:__imp_??0STR@@QEAA@PEADKH@Z; STR::STR(char *,ulong,int)
0x18000677f  lea     rcx, [rbx+630h]
0x180006786  lea     rdx, [rsp+2C8h+var_260]
0x18000678b  call    cs:__imp_?GetFormattedCurrentDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedCurrentDateTime(char *)
0x180006791  mov     edx, [rbx+0B50h]; unsigned int
0x180006797  lea     rax, [rsp+2C8h+var_298]
0x18000679c  mov     [rsp+2C8h+var_2A0], rax; struct STR *
0x1800067a1  lea     r8, [rbx+0B58h]; struct LOG_PROPERTY_INFO **
0x1800067a8  mov     rax, [rbx+0B38h]
0x1800067af  lea     r9, [rsp+2C8h+var_260]; char *
0x1800067b4  mov     rcx, rbx; this
0x1800067b7  mov     [rsp+2C8h+Src], rax; Src
0x1800067bc  call    ?BuildCustomLogHeader@CEXTLOG@@AEAAXKPEAPEAULOG_PROPERTY_INFO@@PEBD1AEAVSTR@@@Z; CEXTLOG::BuildCustomLogHeader(ulong,LOG_PROPERTY_INFO * *,char const *,char const *,STR &)
0x1800067c1  cmp     dword ptr [rbx+6Ch], 0
0x1800067c5  mov     esi, dword ptr [rsp+2C8h+Size]
0x1800067c9  jnz     short loc_18000684A
0x1800067cb  cmp     dword ptr [rbx+68h], 0FFFFFFFFh
0x1800067cf  jz      short loc_18000684A
0x1800067d1  mov     eax, [rbx+68h]
0x1800067d4  lea     ecx, [rsi+rbp]
0x1800067d7  add     rcx, [rbx+60h]
0x1800067db  cmp     rcx, rax
0x1800067de  jb      short loc_18000684A
0x1800067e0  lea     ecx, [rdi+79h]; dwErrCode
0x1800067e3  call    cs:__imp_SetLastError
0x1800067e9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800067f0  jz      short loc_18000681F
0x1800067f2  mov     rcx, cs:g_pDebug
0x1800067f9  lea     rax, aWritecustomlog; "WriteCustomLogDirectives: Unable to wri"...
0x180006800  lea     r9, aCextlogWritecu; "CEXTLOG::WriteCustomLogDirectives"
0x180006807  mov     [rsp+2C8h+Src], rax
0x18000680c  mov     r8d, 46Ch
0x180006812  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x180006819  call    cs:__imp_PuDbgPrint
0x18000681f  xor     edi, edi
0x180006821  lea     rcx, [rsp+2C8h+var_298]
0x180006826  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x18000682c  mov     eax, edi
0x18000682e  mov     rcx, [rsp+2C8h+var_38]
0x180006836  xor     rcx, rsp; StackCookie
0x180006839  call    __security_check_cookie
0x18000683e  add     rsp, 2A8h
0x180006845  pop     rdi
0x180006846  pop     rsi
0x180006847  pop     rbp
0x180006848  pop     rbx
0x180006849  retn
0x18000684a  mov     rdx, [rsp+2C8h+var_278]; Src
0x18000684f  mov     r8d, esi; Size
0x180006852  mov     rcx, [rbx+38h]; this
0x180006856  call    ?Write@ILOG_FILE@@QEAAHPEADK@Z; ILOG_FILE::Write(char *,ulong)
0x18000685b  test    eax, eax
0x18000685d  jz      short loc_18000681F
0x18000685f  add     [rbx+60h], rsi
0x180006863  jmp     short loc_180006821
```
