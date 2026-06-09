# PERF_SM_MANAGER::Initialize(int)

- ea: `0x1800027f8`
- end: `0x180002a5d`
- name: `?Initialize@PERF_SM_MANAGER@@QEAAKH@Z`
- size: `613`
- prototype: `unsigned int __fastcall(PERF_SM_MANAGER *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002024`

## callees

- `0x1800018e8`
- `0x18000218c`
- `0x1800027f8`
- `0x180002a64`
- `0x180002b14`
- `0x180002d72`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a08`
- `iisutil!PuDbgPrintError` at `0x180002875`
- `iisutil!PuDbgPrintError` at `0x1800029ce`
- `iisutil!PuDbgPrintError` at `0x180002a52`
- `iisutil!PuDbgPrintError` at `0x180002875`
- `iisutil!PuDbgPrintError` at `0x1800029ce`
- `iisutil!PuDbgPrintError` at `0x180002a52`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002907`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002977`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002907`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002977`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800029f9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800029f9`

## string_xrefs

- `0x18000286a`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x1800029c3`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x180002a47`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18000284a`: `Could not open the perf counters control block memory\n`
- `0x180002937`: `Could not open an event to request counters from WAS\n`
- `0x1800029a3`: `Could not open an event to shutdown shared memory from WAS\n`
- `0x180002a27`: `Could not open the WAS Process to wait on it\n`

## pseudocode

```c
__int64 __fastcall PERF_SM_MANAGER::Initialize(PERF_SM_MANAGER *this)
{
  char *v2; // r14
  signed int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  PERF_SM_MANAGER::PERF_SM_READER *v7; // rbp
  __int64 v8; // r15
  __int64 v9; // rsi
  HANDLE v10; // rax
  signed int LastError; // eax
  const char *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rsi
  HANDLE v15; // rax
  HANDLE v17; // rax
  signed int v18; // eax

  *((_DWORD *)this + 10) = 0;
  PERF_SM_MANAGER::ResetWaitFreshCounterValues(this);
  v2 = (char *)this + 16;
  v3 = OpenMemoryFile(
         L"Global\\IISCounterControlBlock-46382a23-095e-4559-8d63-6fdeaf552c23",
         (void **)this + 3,
         (void **)this + 2);
  v4 = v3;
  if ( !v3 )
  {
    if ( **(_DWORD **)v2 == 1229148233 )
    {
      v5 = operator new(0x98u);
      if ( v5 )
      {
        v6 = v5 + 1;
        *v5 = 2;
        v7 = (PERF_SM_MANAGER::PERF_SM_READER *)(v5 + 1);
        v8 = 2;
        do
        {
          PERF_SM_MANAGER::PERF_SM_READER::PERF_SM_READER(v7);
          v7 = (PERF_SM_MANAGER::PERF_SM_READER *)((char *)v7 + 72);
          --v8;
        }
        while ( v8 );
      }
      else
      {
        v6 = 0;
      }
      *((_QWORD *)this + 4) = v6;
      if ( !v6 )
        return 14;
      v9 = *(_QWORD *)v2;
      if ( !wcsncmp_0((const wchar_t *)(*(_QWORD *)v2 + 8LL), L"Global\\WASPerfCount-", 0x14u) )
      {
        v10 = OpenEventW(2u, 0, (LPCWSTR)(v9 + 8));
        *((_QWORD *)this + 6) = v10;
        if ( !v10 )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_28;
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v12 = "Could not open an event to request counters from WAS\n";
          v13 = 522;
          goto LABEL_27;
        }
        v14 = *(_QWORD *)v2;
        if ( !wcsncmp_0((const wchar_t *)(*(_QWORD *)v2 + 2056LL), L"Global\\WASPerfCount-", 0x14u) )
        {
          v15 = OpenEventW(0x100000u, 0, (LPCWSTR)(v14 + 2056));
          *((_QWORD *)this + 7) = v15;
          if ( !v15 )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_28;
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v12 = "Could not open an event to shutdown shared memory from WAS\n";
            v13 = 549;
LABEL_27:
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
              v13,
              "PERF_SM_MANAGER::Initialize",
              LastError,
              v12);
LABEL_28:
            if ( v4 )
              return v4;
LABEL_29:
            *((_DWORD *)this + 3) = 1;
            return v4;
          }
          v17 = OpenProcess(0x100000u, 0, *(_DWORD *)(*(_QWORD *)v2 + 4LL));
          *((_QWORD *)this + 8) = v17;
          if ( v17 )
            goto LABEL_29;
          v18 = GetLastError();
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            if ( v18 > 0 )
              v18 = (unsigned __int16)v18 | 0x80070000;
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
              568,
              "PERF_SM_MANAGER::Initialize",
              v18,
              "Could not open the WAS Process to wait on it\n");
          }
        }
      }
    }
    return 21;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
      466,
      "PERF_SM_MANAGER::Initialize",
      v3,
      "Could not open the perf counters control block memory\n");
  }
  return v4;
}

```

## disassembly

```asm
0x1800027f8  push    rbx
0x1800027fa  push    rbp
0x1800027fb  push    rsi
0x1800027fc  push    rdi
0x1800027fd  push    r14
0x1800027ff  push    r15
0x180002801  sub     rsp, 38h
0x180002805  mov     rdi, rcx
0x180002808  mov     dword ptr [rcx+28h], 0
0x18000280f  call    ?ResetWaitFreshCounterValues@PERF_SM_MANAGER@@AEAAXXZ; PERF_SM_MANAGER::ResetWaitFreshCounterValues(void)
0x180002814  lea     r14, [rdi+10h]
0x180002818  mov     r8, r14; void **
0x18000281b  lea     rdx, [rdi+18h]; void **
0x18000281f  lea     rcx, Name; "Global\\IISCounterControlBlock-46382a23"...
0x180002826  call    ?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z; OpenMemoryFile(ushort const *,void * *,void * *)
0x18000282b  mov     ebx, eax
0x18000282d  test    eax, eax
0x18000282f  jz      short loc_180002880
0x180002831  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002838  jz      loc_1800029DF
0x18000283e  test    eax, eax
0x180002840  jle     short loc_18000284A
0x180002842  movzx   eax, ax
0x180002845  or      eax, 80070000h
0x18000284a  lea     rcx, aCouldNotOpenTh; "Could not open the perf counters contro"...
0x180002851  mov     r8d, 1D2h
0x180002857  mov     [rsp+68h+var_40], rcx
0x18000285c  lea     r9, aPerfSmManagerI; "PERF_SM_MANAGER::Initialize"
0x180002863  mov     rcx, cs:g_pDebug
0x18000286a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002871  mov     [rsp+68h+var_48], eax
0x180002875  call    cs:__imp_PuDbgPrintError
0x18000287b  jmp     loc_1800029DF
0x180002880  mov     rax, [r14]
0x180002883  cmp     dword ptr [rax], 49435049h
0x180002889  jz      short loc_180002895
0x18000288b  mov     ebx, 15h
0x180002890  jmp     loc_1800029DF
0x180002895  mov     ecx, 98h; Size
0x18000289a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000289f  test    rax, rax
0x1800028a2  jz      short loc_1800028CC
0x1800028a4  lea     rsi, [rax+8]
0x1800028a8  mov     qword ptr [rax], 2
0x1800028af  mov     rbp, rsi
0x1800028b2  mov     r15d, 2
0x1800028b8  mov     rcx, rbp; this
0x1800028bb  call    ??0PERF_SM_READER@PERF_SM_MANAGER@@QEAA@XZ; PERF_SM_MANAGER::PERF_SM_READER::PERF_SM_READER(void)
0x1800028c0  add     rbp, 48h ; 'H'
0x1800028c4  sub     r15, 1
0x1800028c8  jnz     short loc_1800028B8
0x1800028ca  jmp     short loc_1800028CE
0x1800028cc  xor     esi, esi
0x1800028ce  mov     [rdi+20h], rsi
0x1800028d2  test    rsi, rsi
0x1800028d5  jnz     short loc_1800028DF
0x1800028d7  lea     ebx, [rsi+0Eh]
0x1800028da  jmp     loc_1800029DF
0x1800028df  mov     rsi, [r14]
0x1800028e2  lea     rdx, aGlobalWasperfc; "Global\\WASPerfCount-"
0x1800028e9  mov     ebp, 14h
0x1800028ee  mov     r8d, ebp; MaxCount
0x1800028f1  lea     rcx, [rsi+8]; String1
0x1800028f5  call    wcsncmp_0
0x1800028fa  test    eax, eax
0x1800028fc  jnz     short loc_18000288B
0x1800028fe  lea     r8, [rsi+8]; lpName
0x180002902  xor     edx, edx; bInheritHandle
0x180002904  lea     ecx, [rbp-12h]; dwDesiredAccess
0x180002907  call    cs:__imp_OpenEventW
0x18000290d  mov     [rdi+30h], rax
0x180002911  test    rax, rax
0x180002914  jnz     short loc_180002946
0x180002916  call    cs:__imp_GetLastError
0x18000291c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002923  mov     ebx, eax
0x180002925  jz      loc_1800029D4
0x18000292b  test    eax, eax
0x18000292d  jle     short loc_180002937
0x18000292f  movzx   eax, ax
0x180002932  or      eax, 80070000h
0x180002937  lea     rcx, aCouldNotOpenAn_0; "Could not open an event to request coun"...
0x18000293e  mov     r8d, 20Ah
0x180002944  jmp     short loc_1800029B0
0x180002946  mov     rsi, [r14]
0x180002949  lea     rdx, aGlobalWasperfc; "Global\\WASPerfCount-"
0x180002950  mov     r8d, ebp; MaxCount
0x180002953  lea     rcx, [rsi+808h]; String1
0x18000295a  call    wcsncmp_0
0x18000295f  test    eax, eax
0x180002961  jnz     loc_18000288B
0x180002967  lea     r8, [rsi+808h]; lpName
0x18000296e  xor     edx, edx; bInheritHandle
0x180002970  mov     esi, 100000h
0x180002975  mov     ecx, esi; dwDesiredAccess
0x180002977  call    cs:__imp_OpenEventW
0x18000297d  mov     [rdi+38h], rax
0x180002981  test    rax, rax
0x180002984  jnz     short loc_1800029EE
0x180002986  call    cs:__imp_GetLastError
0x18000298c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002993  mov     ebx, eax
0x180002995  jz      short loc_1800029D4
0x180002997  test    eax, eax
0x180002999  jle     short loc_1800029A3
0x18000299b  movzx   eax, ax
0x18000299e  or      eax, 80070000h
0x1800029a3  lea     rcx, aCouldNotOpenAn; "Could not open an event to shutdown sha"...
0x1800029aa  mov     r8d, 225h
0x1800029b0  mov     [rsp+68h+var_40], rcx
0x1800029b5  lea     r9, aPerfSmManagerI; "PERF_SM_MANAGER::Initialize"
0x1800029bc  mov     rcx, cs:g_pDebug
0x1800029c3  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800029ca  mov     [rsp+68h+var_48], eax
0x1800029ce  call    cs:__imp_PuDbgPrintError
0x1800029d4  test    ebx, ebx
0x1800029d6  jnz     short loc_1800029DF
0x1800029d8  mov     dword ptr [rdi+0Ch], 1
0x1800029df  mov     eax, ebx
0x1800029e1  add     rsp, 38h
0x1800029e5  pop     r15
0x1800029e7  pop     r14
0x1800029e9  pop     rdi
0x1800029ea  pop     rsi
0x1800029eb  pop     rbp
0x1800029ec  pop     rbx
0x1800029ed  retn
0x1800029ee  mov     r8, [r14]
0x1800029f1  xor     edx, edx; bInheritHandle
0x1800029f3  mov     ecx, esi; dwDesiredAccess
0x1800029f5  mov     r8d, [r8+4]; dwProcessId
0x1800029f9  call    cs:__imp_OpenProcess
0x1800029ff  mov     [rdi+40h], rax
0x180002a03  test    rax, rax
0x180002a06  jnz     short loc_1800029D8
0x180002a08  call    cs:__imp_GetLastError
0x180002a0e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002a15  jz      loc_18000288B
0x180002a1b  test    eax, eax
0x180002a1d  jle     short loc_180002A27
0x180002a1f  movzx   eax, ax
0x180002a22  or      eax, 80070000h
0x180002a27  lea     rcx, aCouldNotOpenTh_0; "Could not open the WAS Process to wait "...
0x180002a2e  mov     r8d, 238h
0x180002a34  mov     [rsp+68h+var_40], rcx
0x180002a39  lea     r9, aPerfSmManagerI; "PERF_SM_MANAGER::Initialize"
0x180002a40  mov     rcx, cs:g_pDebug
0x180002a47  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002a4e  mov     [rsp+68h+var_48], eax
0x180002a52  call    cs:__imp_PuDbgPrintError
0x180002a58  jmp     loc_18000288B
```
