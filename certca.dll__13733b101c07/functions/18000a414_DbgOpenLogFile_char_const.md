# DbgOpenLogFile(char const *)

- ea: `0x18000a414`
- end: `0x18000a620`
- name: `?DbgOpenLogFile@@YAXPEBD@Z`
- size: `524`
- prototype: `void __fastcall(char *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800084d0`
- `0x180008960`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000a414`
- `0x1800129c0`
- `0x180016638`
- `0x180016820`
- `0x18001dfa0`
- `0x180028750`
- `0x1800289f4`
- `0x180028ac8`
- `0x1800382c0`

## import_xrefs

- `msvcrt!fflush` at `0x18000a574`
- `msvcrt!fflush` at `0x18000a574`
- `msvcrt!fclose` at `0x18000a527`
- `msvcrt!fclose` at `0x18000a527`
- `msvcrt!fopen` at `0x18000a4a9`
- `msvcrt!fopen` at `0x18000a4a9`
- `msvcrt!_errno` at `0x18000a592`
- `msvcrt!_errno` at `0x18000a592`
- `msvcrt!fseek` at `0x18000a4fc`
- `msvcrt!fseek` at `0x18000a4fc`
- `msvcrt!ftell` at `0x18000a512`
- `msvcrt!ftell` at `0x18000a512`
- `msvcrt!fwrite` at `0x18000a556`
- `msvcrt!fwrite` at `0x18000a556`
- `msvcrt!getenv` at `0x18000a4ce`
- `msvcrt!getenv` at `0x18000a4ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a48c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a48c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5b2`

## string_xrefs

- `0x18000a55c`: `Opened Log`

## pseudocode

```c
void __fastcall DbgOpenLogFile(char *a1)
{
  char *v1; // rdi
  BOOL v2; // ebx
  int LogFileNameA; // eax
  const char *v4; // rdx
  int v5; // r8d
  char *v6; // rax
  unsigned int v7; // ebx
  int v8; // eax
  const char *v9; // rdx
  int *v10; // rax
  const unsigned __int16 *v11; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-138h] BYREF
  char v13[272]; // [rsp+30h] [rbp-128h] BYREF

  if ( a1 )
  {
    v1 = a1 + 1;
    if ( *a1 != 43 )
      v1 = a1;
    v2 = *a1 == 43;
    LogFileNameA = myGetLogFileNameA(v1, v13);
    if ( LogFileNameA )
      CSPrintErrorLineFile(0x122032Au, LogFileNameA);
    else
      v1 = v13;
    DbgCloseLogFile();
    if ( g_fDBGCSInit )
    {
      EnterCriticalSection(&g_DBGCriticalSection);
      while ( 1 )
      {
        v4 = "at";
        if ( !v2 )
          v4 = "wt";
        g_pfDebugLog = fopen(v1, v4);
        if ( !g_pfDebugLog )
          break;
        if ( !v2 )
          goto LABEL_22;
        v6 = getenv("CERTSRV_LOGMAX");
        if ( !v6 || (v7 = myatolxA(v6), v7 < 0x80000) )
          v7 = 0x80000;
        if ( fseek(g_pfDebugLog, 0, 2) || v7 == -1 || (v8 = ftell(g_pfDebugLog), v8 >= 0) && v7 >= v8 )
        {
          fwrite(
            "\n========================================================================\n",
            0x4Au,
            1u,
            g_pfDebugLog);
LABEL_22:
          DbgLogDateTime("Opened Log");
          DbgLogLocalGMTTimeDiff();
          fflush(g_pfDebugLog);
          goto LABEL_26;
        }
        fclose(g_pfDebugLog);
        v2 = 0;
        g_pfDebugLog = 0;
      }
      hMem = 0;
      myConvertSzToWsz((unsigned __int16 **)&hMem, v1, v5);
      v10 = _errno();
      CSPrintErrorLineFileData2((const unsigned __int16 *)hMem, 0x132032Au, *v10, 0);
      LocalFree(hMem);
      v11 = L"at";
      if ( !v2 )
        v11 = L"wt";
      CSPrintErrorLineFileData2(v11, 0x136032Au, -2147024894, 0);
LABEL_26:
      myReportLogFile(g_pfDebugLog != 0, v9, v1);
      LeaveCriticalSection(&g_DBGCriticalSection);
    }
  }
}

```

## disassembly

```asm
0x18000a414  test    rcx, rcx
0x18000a417  jz      locret_18000A61F
0x18000a41d  mov     [rsp+arg_8], rbx
0x18000a422  push    rdi
0x18000a423  sub     rsp, 150h
0x18000a42a  mov     rax, cs:__security_cookie
0x18000a431  xor     rax, rsp
0x18000a434  mov     [rsp+158h+var_18], rax
0x18000a43c  cmp     byte ptr [rcx], 2Bh ; '+'
0x18000a43f  lea     rdi, [rcx+1]
0x18000a443  lea     rdx, [rsp+158h+var_128]; char *
0x18000a448  cmovnz  rdi, rcx
0x18000a44c  xor     ebx, ebx
0x18000a44e  cmp     byte ptr [rcx], 2Bh ; '+'
0x18000a451  mov     rcx, rdi; char *
0x18000a454  setz    bl
0x18000a457  call    ?myGetLogFileNameA@@YAJPEBDPEADK@Z; myGetLogFileNameA(char const *,char *,ulong)
0x18000a45c  test    eax, eax
0x18000a45e  jz      short loc_18000A46E
0x18000a460  mov     edx, eax; int
0x18000a462  mov     ecx, 122032Ah; unsigned int
0x18000a467  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000a46c  jmp     short loc_18000A473
0x18000a46e  lea     rdi, [rsp+158h+var_128]
0x18000a473  call    ?DbgCloseLogFile@@YAXXZ; DbgCloseLogFile(void)
0x18000a478  cmp     cs:?g_fDBGCSInit@@3HA, 0; int g_fDBGCSInit
0x18000a47f  jz      loc_18000A5FF
0x18000a485  lea     rcx, ?g_DBGCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a48c  call    cs:__imp_EnterCriticalSection
0x18000a492  lea     rax, Mode; "wt"
0x18000a499  test    ebx, ebx
0x18000a49b  lea     rdx, aAt_0; "at"
0x18000a4a2  mov     rcx, rdi; FileName
0x18000a4a5  cmovz   rdx, rax; Mode
0x18000a4a9  call    cs:__imp_fopen
0x18000a4af  mov     cs:?g_pfDebugLog@@3PEAU_iobuf@@EA, rax; _iobuf * g_pfDebugLog
0x18000a4b6  test    rax, rax
0x18000a4b9  jz      loc_18000A57C
0x18000a4bf  test    ebx, ebx
0x18000a4c1  jz      loc_18000A55C
0x18000a4c7  lea     rcx, aCertsrvLogmax; "CERTSRV_LOGMAX"
0x18000a4ce  call    cs:__imp_getenv
0x18000a4d4  test    rax, rax
0x18000a4d7  jz      short loc_18000A4EA
0x18000a4d9  mov     rcx, rax; char *
0x18000a4dc  call    ?myatolxA@@YAKPEBD@Z; myatolxA(char const *)
0x18000a4e1  mov     ebx, eax
0x18000a4e3  cmp     eax, 80000h
0x18000a4e8  jnb     short loc_18000A4EF
0x18000a4ea  mov     ebx, 80000h
0x18000a4ef  mov     rcx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x18000a4f6  xor     edx, edx; Offset
0x18000a4f8  lea     r8d, [rdx+2]; Origin
0x18000a4fc  call    cs:__imp_fseek
0x18000a502  test    eax, eax
0x18000a504  jnz     short loc_18000A53F
0x18000a506  cmp     ebx, 0FFFFFFFFh
0x18000a509  jz      short loc_18000A53F
0x18000a50b  mov     rcx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x18000a512  call    cs:__imp_ftell
0x18000a518  test    eax, eax
0x18000a51a  js      short loc_18000A520
0x18000a51c  cmp     ebx, eax
0x18000a51e  jnb     short loc_18000A53F
0x18000a520  mov     rcx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x18000a527  call    cs:__imp_fclose
0x18000a52d  xor     ebx, ebx
0x18000a52f  mov     cs:?g_pfDebugLog@@3PEAU_iobuf@@EA, 0; _iobuf * g_pfDebugLog
0x18000a53a  jmp     loc_18000A492
0x18000a53f  mov     r9, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x18000a546  lea     rcx, asc_18006B130; "\n====================================="...
0x18000a54d  mov     edx, 4Ah ; 'J'; ElementSize
0x18000a552  lea     r8d, [rdx-49h]; ElementCount
0x18000a556  call    cs:__imp_fwrite
0x18000a55c  lea     rcx, aOpenedLog; "Opened Log"
0x18000a563  call    ?DbgLogDateTime@@YAXPEBD@Z; DbgLogDateTime(char const *)
0x18000a568  call    ?DbgLogLocalGMTTimeDiff@@YAXXZ; DbgLogLocalGMTTimeDiff(void)
0x18000a56d  mov     rcx, cs:?g_pfDebugLog@@3PEAU_iobuf@@EA; Stream
0x18000a574  call    cs:__imp_fflush
0x18000a57a  jmp     short loc_18000A5DF
0x18000a57c  mov     rdx, rdi; char *
0x18000a57f  mov     [rsp+158h+hMem], 0
0x18000a588  lea     rcx, [rsp+158h+hMem]; unsigned __int16 **
0x18000a58d  call    ?myConvertSzToWsz@@YAHPEAPEAGPEBDJ@Z; myConvertSzToWsz(ushort * *,char const *,long)
0x18000a592  call    cs:__imp__errno
0x18000a598  mov     rcx, [rsp+158h+hMem]; unsigned __int16 *
0x18000a59d  xor     r9d, r9d; int
0x18000a5a0  mov     edx, 132032Ah; unsigned int
0x18000a5a5  mov     r8d, [rax]; int
0x18000a5a8  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000a5ad  mov     rcx, [rsp+158h+hMem]; hMem
0x18000a5b2  call    cs:__imp_LocalFree
0x18000a5b8  test    ebx, ebx
0x18000a5ba  lea     rax, aWt; "wt"
0x18000a5c1  lea     rcx, aAt; "at"
0x18000a5c8  mov     edx, 136032Ah; unsigned int
0x18000a5cd  cmovz   rcx, rax; unsigned __int16 *
0x18000a5d1  mov     r8d, 80070002h; int
0x18000a5d7  xor     r9d, r9d; int
0x18000a5da  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000a5df  cmp     cs:?g_pfDebugLog@@3PEAU_iobuf@@EA, 0; _iobuf * g_pfDebugLog
0x18000a5e7  mov     r8, rdi; char *
0x18000a5ea  setnz   cl; bool
0x18000a5ed  call    ?myReportLogFile@@YAX_NPEBD1@Z; myReportLogFile(bool,char const *,char const *)
0x18000a5f2  lea     rcx, ?g_DBGCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a5f9  call    cs:__imp_LeaveCriticalSection
0x18000a5ff  mov     rcx, [rsp+158h+var_18]
0x18000a607  xor     rcx, rsp; StackCookie
0x18000a60a  call    __security_check_cookie
0x18000a60f  mov     rbx, [rsp+158h+arg_8]
0x18000a617  add     rsp, 150h
0x18000a61e  pop     rdi
0x18000a61f  retn
```
