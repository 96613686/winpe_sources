# CleanUpZombieLagCounters(void)

- ea: `0x180005378`
- end: `0x180005764`
- name: `?CleanUpZombieLagCounters@@YAXXZ`
- size: `1004`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180007668`

## callees

- `0x180001008`
- `0x180001098`
- `0x1800011e8`
- `0x180005378`
- `0x1800098f6`
- `0x180009930`

## import_xrefs

- `msvcrt!wcstoul` at `0x180005533`
- `msvcrt!wcstoul` at `0x180005533`
- `msvcrt!wcsstr` at `0x180005501`
- `msvcrt!wcsstr` at `0x18000551a`
- `msvcrt!wcsstr` at `0x180005501`
- `msvcrt!wcsstr` at `0x18000551a`
- `msvcrt!malloc` at `0x1800053c8`
- `msvcrt!malloc` at `0x1800053c8`
- `msvcrt!free` at `0x18000570c`
- `msvcrt!free` at `0x18000570c`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18000554d`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18000554d`
- `KERNEL32!Process32NextW` at `0x18000564a`
- `KERNEL32!Process32NextW` at `0x18000564a`
- `KERNEL32!Process32FirstW` at `0x180005584`
- `KERNEL32!Process32FirstW` at `0x180005584`
- `KERNEL32!CloseHandle` at `0x18000565b`
- `KERNEL32!CloseHandle` at `0x18000565b`
- `ADVAPI32!ControlTraceW` at `0x1800056ac`
- `ADVAPI32!ControlTraceW` at `0x1800056ac`
- `ADVAPI32!QueryAllTracesW` at `0x180005442`
- `ADVAPI32!QueryAllTracesW` at `0x180005442`

## pseudocode

```c
void CleanUpZombieLagCounters(void)
{
  char *v0; // rax
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  char *v4; // rbx
  __int64 i; // r8
  struct _EVENT_TRACE_PROPERTIES *v6; // rax
  PEVENT_TRACE_PROPERTIES v7; // rax
  ULONG v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned __int16 v12; // di
  const wchar_t *v13; // r12
  wchar_t *v14; // rax
  unsigned int v15; // r15d
  HANDLE Toolhelp32Snapshot; // rsi
  int v17; // r14d
  BOOL j; // eax
  __int64 v19; // rax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  ULONG v23; // eax
  int v24; // r8d
  int v25; // r9d
  ULONG v26; // [rsp+30h] [rbp-D0h] BYREF
  ULONG LoggerCount; // [rsp+34h] [rbp-CCh] BYREF
  const char *v28; // [rsp+38h] [rbp-C8h] BYREF
  const char *v29; // [rsp+40h] [rbp-C0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+290h] [rbp+190h] BYREF
  const char *v32; // [rsp+2B0h] [rbp+1B0h]
  __int64 v33; // [rsp+2B8h] [rbp+1B8h]
  ULONG *v34; // [rsp+2C0h] [rbp+1C0h]
  __int64 v35; // [rsp+2C8h] [rbp+1C8h]
  WCHAR *szExeFile; // [rsp+2D0h] [rbp+1D0h]
  int v37; // [rsp+2D8h] [rbp+1D8h]
  int v38; // [rsp+2DCh] [rbp+1DCh]
  PEVENT_TRACE_PROPERTIES PropertyArray[164]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(PropertyArray, 0, sizeof(PropertyArray));
  LoggerCount = 0;
  v0 = (char *)malloc(0xA8CE0u);
  v29 = v0;
  v4 = v0;
  if ( v0 )
  {
    memset_0(v0, 0, 0xA8CE0u);
    for ( i = 0; i != 164; ++i )
    {
      v6 = (struct _EVENT_TRACE_PROPERTIES *)&v4[4216 * i];
      PropertyArray[i] = v6;
      v6->Wnode.BufferSize = 4216;
      PropertyArray[i]->LoggerNameOffset = 120;
      v7 = PropertyArray[i];
      v7->LogFileNameOffset = 2168;
    }
    v8 = QueryAllTracesW(PropertyArray, 0xA4u, &LoggerCount);
    if ( !v8 || v8 == 234 )
    {
      if ( (unsigned int)dword_180012020 > 5 )
      {
        v26 = LoggerCount;
        v28 = "Found sessions";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned int)&unk_18000F56A,
          v10,
          v11,
          (__int64)&v28,
          (__int64)&v26);
      }
      v12 = 0;
      if ( LoggerCount )
      {
        do
        {
          v13 = (const wchar_t *)((char *)PropertyArray[v12] + PropertyArray[v12]->LoggerNameOffset);
          if ( wcsstr(v13, L"ApplicationLag-") )
          {
            v14 = wcsstr(v13, L"ApplicationLag-");
            if ( v14 )
            {
              v15 = wcstoul(v14 + 15, 0, 10);
              if ( v15 - 1 <= 0xFFFFFFFD )
              {
                Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
                if ( Toolhelp32Snapshot )
                {
                  v17 = 0;
                  memset_0(&pe.cntUsage, 0, 0x234u);
                  pe.dwSize = 568;
                  for ( j = Process32FirstW(Toolhelp32Snapshot, &pe); j; j = Process32NextW(Toolhelp32Snapshot, &pe) )
                  {
                    if ( pe.th32ProcessID == v15 )
                    {
                      if ( (unsigned int)dword_180012020 > 5 )
                      {
                        v26 = v15;
                        v19 = -1;
                        do
                          ++v19;
                        while ( pe.szExeFile[v19] );
                        v38 = 0;
                        v37 = 2 * v19 + 2;
                        szExeFile = pe.szExeFile;
                        v34 = &v26;
                        v35 = 4;
                        v32 = "This etw trace is alive";
                        v33 = 24;
                        tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180012020, byte_18000F3E9, 0, 0, 5u, &v31);
                      }
                      v17 = 1;
                    }
                  }
                  CloseHandle(Toolhelp32Snapshot);
                  if ( !v17 )
                  {
                    if ( (unsigned int)dword_180012020 > 4 )
                    {
                      v28 = "Found a zombie ETW trace, stop it";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                        v20,
                        (unsigned int)&unk_18000F255,
                        v21,
                        v22,
                        (__int64)&v28);
                    }
                    v23 = ControlTraceW(0, v13, PropertyArray[v12], 1u);
                    if ( (unsigned int)dword_180012020 > 4 )
                    {
                      v26 = v23;
                      v28 = "Tried to stop zombie ETW Trace";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                        dword_180012020,
                        (unsigned int)&unk_18000F525,
                        v24,
                        v25,
                        (__int64)&v28,
                        (__int64)&v26);
                    }
                  }
                }
              }
            }
          }
          ++v12;
        }
        while ( v12 < LoggerCount );
        v4 = (char *)v29;
      }
    }
    else if ( (unsigned int)dword_180012020 > 2 )
    {
      v26 = v8;
      v28 = "Error calling QueryAllTraces";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_180012020,
        (unsigned int)&unk_18000F29E,
        v10,
        v11,
        (__int64)&v28,
        (__int64)&v26);
    }
    free(v4);
  }
  else if ( (unsigned int)dword_180012020 > 2 )
  {
    v29 = "Error allocating memory for properties.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v1,
      (unsigned int)&unk_18000F137,
      v2,
      v3,
      (__int64)&v29);
  }
}

```

## disassembly

```asm
0x180005378  push    rbp
0x18000537a  push    rbx
0x18000537b  push    rsi
0x18000537c  push    rdi
0x18000537d  push    r12
0x18000537f  push    r13
0x180005381  push    r14
0x180005383  push    r15
0x180005385  lea     rbp, [rsp-718h]
0x18000538d  sub     rsp, 818h
0x180005394  mov     rax, cs:__security_cookie
0x18000539b  xor     rax, rsp
0x18000539e  mov     [rbp+750h+var_50], rax
0x1800053a5  xor     edx, edx; Val
0x1800053a7  lea     rcx, [rbp+750h+PropertyArray]; void *
0x1800053ae  mov     r8d, 520h; Size
0x1800053b4  call    memset_0
0x1800053b9  mov     edi, 0A8CE0h
0x1800053be  mov     [rsp+850h+LoggerCount], 0
0x1800053c6  mov     ecx, edi; Size
0x1800053c8  call    cs:__imp_malloc
0x1800053ce  mov     [rsp+850h+var_810], rax
0x1800053d3  mov     rbx, rax
0x1800053d6  test    rax, rax
0x1800053d9  jz      loc_180005714
0x1800053df  mov     r8d, edi; Size
0x1800053e2  xor     edx, edx; Val
0x1800053e4  mov     rcx, rax; void *
0x1800053e7  call    memset_0
0x1800053ec  xor     r8d, r8d
0x1800053ef  mov     edx, 0A4h; PropertyArrayCount
0x1800053f4  lea     esi, [r8+1]
0x1800053f8  imul    rax, r8, 1078h
0x1800053ff  add     rax, rbx
0x180005402  mov     [rbp+r8*8+750h+PropertyArray], rax
0x18000540a  mov     dword ptr [rax], 1078h
0x180005410  mov     rax, [rbp+r8*8+750h+PropertyArray]
0x180005418  mov     dword ptr [rax+74h], 78h ; 'x'
0x18000541f  mov     rax, [rbp+r8*8+750h+PropertyArray]
0x180005427  add     r8, rsi
0x18000542a  mov     dword ptr [rax+70h], 878h
0x180005431  cmp     r8, rdx
0x180005434  jnz     short loc_1800053F8
0x180005436  lea     r8, [rsp+850h+LoggerCount]; LoggerCount
0x18000543b  lea     rcx, [rbp+750h+PropertyArray]; PropertyArray
0x180005442  call    cs:__imp_QueryAllTracesW
0x180005448  test    eax, eax
0x18000544a  jz      short loc_180005497
0x18000544c  cmp     eax, 0EAh
0x180005451  jz      short loc_180005497
0x180005453  mov     ecx, cs:dword_180012020
0x180005459  cmp     ecx, 2
0x18000545c  jbe     loc_180005709
0x180005462  mov     [rsp+850h+var_820], eax
0x180005466  lea     rdx, unk_18000F29E
0x18000546d  lea     rax, aErrorCallingQu; "Error calling QueryAllTraces"
0x180005474  mov     [rsp+850h+var_818], rax
0x180005479  lea     rax, [rsp+850h+var_820]
0x18000547e  mov     [rsp+850h+var_828], rax
0x180005483  lea     rax, [rsp+850h+var_818]
0x180005488  mov     [rsp+850h+var_830], rax
0x18000548d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005492  jmp     loc_180005709
0x180005497  mov     eax, cs:dword_180012020
0x18000549d  cmp     eax, 5
0x1800054a0  jbe     short loc_1800054D6
0x1800054a2  mov     eax, [rsp+850h+LoggerCount]
0x1800054a6  lea     rdx, unk_18000F56A
0x1800054ad  mov     [rsp+850h+var_820], eax
0x1800054b1  lea     rax, aFoundSessions; "Found sessions"
0x1800054b8  mov     [rsp+850h+var_818], rax
0x1800054bd  lea     rax, [rsp+850h+var_820]
0x1800054c2  mov     [rsp+850h+var_828], rax
0x1800054c7  lea     rax, [rsp+850h+var_818]
0x1800054cc  mov     [rsp+850h+var_830], rax
0x1800054d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800054d6  xor     edi, edi
0x1800054d8  cmp     [rsp+850h+LoggerCount], edi
0x1800054dc  jbe     loc_180005709
0x1800054e2  xor     ebx, ebx
0x1800054e4  movzx   r13d, di
0x1800054e8  lea     rdx, aApplicationlag; "ApplicationLag-"
0x1800054ef  mov     rcx, [rbp+r13*8+750h+PropertyArray]
0x1800054f7  mov     r12d, [rcx+74h]
0x1800054fb  add     r12, rcx
0x1800054fe  mov     rcx, r12; Str
0x180005501  call    cs:__imp_wcsstr
0x180005507  test    rax, rax
0x18000550a  jz      loc_1800056F4
0x180005510  lea     rdx, aApplicationlag; "ApplicationLag-"
0x180005517  mov     rcx, r12; Str
0x18000551a  call    cs:__imp_wcsstr
0x180005520  test    rax, rax
0x180005523  jz      loc_1800056F4
0x180005529  xor     edx, edx; EndPtr
0x18000552b  lea     rcx, [rax+1Eh]; String
0x18000552f  lea     r8d, [rdx+0Ah]; Radix
0x180005533  call    cs:__imp_wcstoul
0x180005539  mov     r15d, eax
0x18000553c  lea     ecx, [rax-1]
0x18000553f  cmp     ecx, 0FFFFFFFDh
0x180005542  ja      loc_1800056F4
0x180005548  xor     edx, edx; th32ProcessID
0x18000554a  lea     ecx, [rdx+2]; dwFlags
0x18000554d  call    cs:__imp_CreateToolhelp32Snapshot
0x180005553  mov     rsi, rax
0x180005556  test    rax, rax
0x180005559  jz      loc_1800056EF
0x18000555f  xor     edx, edx; Val
0x180005561  lea     rcx, [rsp+850h+pe.cntUsage]; void *
0x180005566  mov     r8d, 234h; Size
0x18000556c  mov     r14d, ebx
0x18000556f  call    memset_0
0x180005574  lea     rdx, [rsp+850h+pe]; lppe
0x180005579  mov     [rsp+850h+pe.dwSize], 238h
0x180005581  mov     rcx, rsi; hSnapshot
0x180005584  call    cs:__imp_Process32FirstW
0x18000558a  jmp     loc_180005650
0x18000558f  cmp     [rsp+850h+pe.th32ProcessID], r15d
0x180005594  jnz     loc_180005642
0x18000559a  mov     eax, cs:dword_180012020
0x1800055a0  cmp     eax, 5
0x1800055a3  jbe     loc_18000563C
0x1800055a9  mov     [rsp+850h+var_820], r15d
0x1800055ae  lea     rcx, [rsp+850h+pe.szExeFile]
0x1800055b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800055b7  inc     rax
0x1800055ba  cmp     [rcx+rax*2], bx
0x1800055be  jnz     short loc_1800055B7
0x1800055c0  lea     eax, ds:2[rax*2]
0x1800055c7  mov     [rbp+750h+var_574], ebx
0x1800055cd  mov     [rbp+750h+var_578], eax
0x1800055d3  lea     rcx, [rsp+850h+pe.szExeFile]
0x1800055d8  lea     rax, [rsp+850h+var_820]
0x1800055dd  mov     [rbp+750h+var_580], rcx
0x1800055e4  mov     [rbp+750h+var_590], rax
0x1800055eb  lea     rdx, byte_18000F3E9
0x1800055f2  lea     rax, aThisEtwTraceIs; "This etw trace is alive"
0x1800055f9  mov     [rbp+750h+var_588], 4
0x180005604  mov     [rbp+750h+var_5A0], rax
0x18000560b  lea     rcx, dword_180012020
0x180005612  lea     rax, [rbp+750h+var_5C0]
0x180005619  mov     [rbp+750h+var_598], 18h
0x180005624  mov     [rsp+850h+var_828], rax
0x180005629  xor     r9d, r9d
0x18000562c  xor     r8d, r8d
0x18000562f  mov     dword ptr [rsp+850h+var_830], 5
0x180005637  call    _tlgWriteTransfer_EventWriteTransfer
0x18000563c  mov     r14d, 1
0x180005642  lea     rdx, [rsp+850h+pe]; lppe
0x180005647  mov     rcx, rsi; hSnapshot
0x18000564a  call    cs:__imp_Process32NextW
0x180005650  test    eax, eax
0x180005652  jnz     loc_18000558F
0x180005658  mov     rcx, rsi; hObject
0x18000565b  call    cs:__imp_CloseHandle
0x180005661  test    r14d, r14d
0x180005664  jnz     loc_1800056EF
0x18000566a  mov     eax, cs:dword_180012020
0x180005670  cmp     eax, 4
0x180005673  jbe     short loc_180005697
0x180005675  lea     rax, aFoundAZombieEt; "Found a zombie ETW trace, stop it"
0x18000567c  mov     [rsp+850h+var_818], rax
0x180005681  lea     rdx, unk_18000F255
0x180005688  lea     rax, [rsp+850h+var_818]
0x18000568d  mov     [rsp+850h+var_830], rax
0x180005692  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180005697  mov     r8, [rbp+r13*8+750h+PropertyArray]; Properties
0x18000569f  mov     esi, 1
0x1800056a4  mov     r9d, esi; ControlCode
0x1800056a7  mov     rdx, r12; InstanceName
0x1800056aa  xor     ecx, ecx; TraceHandle
0x1800056ac  call    cs:__imp_ControlTraceW
0x1800056b2  mov     ecx, cs:dword_180012020
0x1800056b8  cmp     ecx, 4
0x1800056bb  jbe     short loc_1800056F4
0x1800056bd  mov     [rsp+850h+var_820], eax
0x1800056c1  lea     rdx, unk_18000F525
0x1800056c8  lea     rax, aTriedToStopZom; "Tried to stop zombie ETW Trace"
0x1800056cf  mov     [rsp+850h+var_818], rax
0x1800056d4  lea     rax, [rsp+850h+var_820]
0x1800056d9  mov     [rsp+850h+var_828], rax
0x1800056de  lea     rax, [rsp+850h+var_818]
0x1800056e3  mov     [rsp+850h+var_830], rax
0x1800056e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800056ed  jmp     short loc_1800056F4
0x1800056ef  mov     esi, 1
0x1800056f4  add     di, si
0x1800056f7  movzx   eax, di
0x1800056fa  cmp     eax, [rsp+850h+LoggerCount]
0x1800056fe  jb      loc_1800054E4
0x180005704  mov     rbx, [rsp+850h+var_810]
0x180005709  mov     rcx, rbx; Block
0x18000570c  call    cs:__imp_free
0x180005712  jmp     short loc_180005741
0x180005714  mov     eax, cs:dword_180012020
0x18000571a  cmp     eax, 2
0x18000571d  jbe     short loc_180005741
0x18000571f  lea     rax, aErrorAllocatin; "Error allocating memory for properties."
0x180005726  mov     [rsp+850h+var_810], rax
0x18000572b  lea     rdx, unk_18000F137
0x180005732  lea     rax, [rsp+850h+var_810]
0x180005737  mov     [rsp+850h+var_830], rax
0x18000573c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180005741  mov     rcx, [rbp+750h+var_50]
0x180005748  xor     rcx, rsp; StackCookie
0x18000574b  call    __security_check_cookie
0x180005750  add     rsp, 818h
0x180005757  pop     r15
0x180005759  pop     r14
0x18000575b  pop     r13
0x18000575d  pop     r12
0x18000575f  pop     rdi
0x180005760  pop     rsi
0x180005761  pop     rbx
0x180005762  pop     rbp
0x180005763  retn
```
