# SystemSleepDiagnostics::AnalyzeTraces(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x1800427b4`
- end: `0x180042a23`
- name: `?AnalyzeTraces@SystemSleepDiagnostics@@QEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(SystemSleepDiagnostics *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800424e0`

## callees

- `0x1800427b4`
- `0x18004ca90`
- `0x18004d8fc`
- `0x1800871f0`
- `0x1800873d4`
- `0x180087e0c`
- `0x180087f30`
- `0x180088254`
- `0x180088618`
- `0x180088834`
- `0x1800888bc`
- `0x180088a10`
- `0x18008aa9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042892`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180042914`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180042914`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180042881`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180042881`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18004292c`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18004292c`

## pseudocode

```c
__int64 __fastcall SystemSleepDiagnostics::AnalyzeTraces(SystemSleepDiagnostics *this, __int64 *a2)
{
  struct _FILETIME v4; // rax
  unsigned int v5; // esi
  __int64 v6; // rbx
  struct _FILETIME v7; // rax
  WCHAR *v8; // r14
  signed int LastError; // eax
  Session *v10; // rax
  PowerRequest *v11; // rcx
  ULONG64 HandleArray; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME EndTime; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME StartTime; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[216]; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  v4 = (struct _FILETIME)*((_QWORD *)this + 131);
  v5 = 0;
  v6 = *a2;
  EndTime = v4;
  v7 = (struct _FILETIME)*((_QWORD *)this + 130);
  StartTime = v7;
  HandleArray = 0;
  while ( v6 != a2[1] )
  {
    if ( *(_QWORD *)(v6 + 24) <= 7u )
      v8 = (WCHAR *)v6;
    else
      v8 = *(WCHAR **)v6;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = v8;
    Logfile.EventCallback = (PEVENT_CALLBACK)SystemSleepDiagnostics::ProcessTraceCallbackStatic;
    Logfile.LogFileMode = 0x10000000;
    Logfile.Context = this;
    HandleArray = OpenTraceW(&Logfile);
    if ( HandleArray == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError <= 0 )
        goto LABEL_22;
LABEL_8:
      v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    memset_0(v16, 0, 0xD0u);
    v10 = Session::Session((Session *)v16);
    Session::operator=((char *)this + 1088, v10);
    Session::~Session((Session *)v16);
    *((_OWORD *)this + 82) = 0;
    *((_OWORD *)this + 83) = 0;
    *((_OWORD *)this + 84) = 0;
    LastError = ProcessTrace(&HandleArray, 1u, &StartTime, &EndTime);
    if ( LastError )
    {
      if ( LastError > 0 )
        goto LABEL_8;
      v5 = LastError;
    }
    else
    {
      CloseTrace(HandleArray);
      SystemSleepDiagnostics::CloseUncompletedPowerTransitions(this);
      SystemSleepDiagnostics::CloseUncompletedPowerRequests(this);
      SystemSleepDiagnostics::FilterPowerRequestsWhichEndedBeforeUserAway(this);
      if ( *((_BYTE *)this + 1056) || *((_QWORD *)this + 136) && *((_QWORD *)this + 137) && *((_DWORD *)this + 276) )
      {
        if ( *((_QWORD *)this + 134) == *((_QWORD *)this + 135) )
        {
          std::vector<Session>::_Emplace_reallocate<Session const &>(
            (char *)this + 1064,
            *((_QWORD *)this + 134),
            (char *)this + 1088);
        }
        else
        {
          Session::Session(*((Session **)this + 134), (SystemSleepDiagnostics *)((char *)this + 1088));
          *((_QWORD *)this + 134) += 208LL;
        }
      }
      std::_Tree<std::_Tmap_traits<unsigned __int64,PowerRequest,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PowerRequest>>,0>>::clear((char *)this + 1296);
      *((_BYTE *)this + 1360) = 0;
      *((_DWORD *)this + 265) = 0;
      v11 = (PowerRequest *)*((_QWORD *)this + 171);
      if ( v11 != *((PowerRequest **)this + 172) )
      {
        std::_Destroy_range<std::allocator<PowerRequest>>(v11);
        *((_QWORD *)this + 172) = *((_QWORD *)this + 171);
      }
      *((_DWORD *)this + 348) = 0;
    }
LABEL_22:
    v6 += 32;
  }
  return v5;
}

```

## disassembly

```asm
0x1800427b4  mov     [rsp-8+arg_8], rbx
0x1800427b9  mov     [rsp-8+arg_10], rsi
0x1800427be  push    rbp
0x1800427bf  push    rdi
0x1800427c0  push    r12
0x1800427c2  push    r14
0x1800427c4  push    r15
0x1800427c6  lea     rbp, [rsp-1E0h]
0x1800427ce  sub     rsp, 2E0h
0x1800427d5  mov     rax, cs:__security_cookie
0x1800427dc  xor     rax, rsp
0x1800427df  mov     [rbp+200h+var_30], rax
0x1800427e6  mov     r12, rdx
0x1800427e9  mov     rdi, rcx
0x1800427ec  xor     edx, edx; Val
0x1800427ee  lea     rcx, [rbp+200h+Logfile]; void *
0x1800427f2  mov     r8d, 1C0h; Size
0x1800427f8  call    memset_0
0x1800427fd  mov     rax, [rdi+418h]
0x180042804  xor     esi, esi
0x180042806  mov     rbx, [r12]
0x18004280a  mov     [rsp+300h+EndTime.dwLowDateTime], eax
0x18004280e  shr     rax, 20h
0x180042812  mov     [rsp+300h+EndTime.dwHighDateTime], eax
0x180042816  mov     rax, [rdi+410h]
0x18004281d  mov     [rsp+300h+StartTime.dwLowDateTime], eax
0x180042821  shr     rax, 20h
0x180042825  mov     [rsp+300h+StartTime.dwHighDateTime], eax
0x180042829  mov     [rsp+300h+HandleArray], 0
0x180042832  cmp     rbx, [r12+8]
0x180042837  jz      loc_1800429F6
0x18004283d  cmp     qword ptr [rbx+18h], 7
0x180042842  jbe     short loc_180042849
0x180042844  mov     r14, [rbx]
0x180042847  jmp     short loc_18004284C
0x180042849  mov     r14, rbx
0x18004284c  xor     edx, edx; Val
0x18004284e  lea     rcx, [rbp+200h+Logfile]; void *
0x180042852  mov     r8d, 1C0h; Size
0x180042858  call    memset_0
0x18004285d  lea     rax, ?ProcessTraceCallbackStatic@SystemSleepDiagnostics@@SAXPEAU_EVENT_RECORD@@@Z; SystemSleepDiagnostics::ProcessTraceCallbackStatic(_EVENT_RECORD *)
0x180042864  mov     [rbp+200h+Logfile.LogFileName], r14
0x180042868  lea     rcx, [rbp+200h+Logfile]; Logfile
0x18004286c  mov     qword ptr [rbp+200h+Logfile.1A8h], rax
0x180042873  mov     dword ptr [rbp+200h+Logfile.1Ch], 10000000h
0x18004287a  mov     [rbp+200h+Logfile.Context], rdi
0x180042881  call    cs:__imp_OpenTraceW
0x180042887  mov     [rsp+300h+HandleArray], rax
0x18004288c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042890  jnz     short loc_1800428B0
0x180042892  call    cs:__imp_GetLastError
0x180042898  mov     esi, eax
0x18004289a  test    eax, eax
0x18004289c  jle     loc_1800429ED
0x1800428a2  movzx   esi, ax
0x1800428a5  or      esi, 80070000h
0x1800428ab  jmp     loc_1800429ED
0x1800428b0  xor     edx, edx; Val
0x1800428b2  lea     rcx, [rsp+300h+var_2C8]; void *
0x1800428b7  mov     r8d, 0D0h; Size
0x1800428bd  call    memset_0
0x1800428c2  lea     rcx, [rsp+300h+var_2C8]; this
0x1800428c7  call    ??0Session@@QEAA@XZ; Session::Session(void)
0x1800428cc  lea     r15, [rdi+440h]
0x1800428d3  mov     rdx, rax
0x1800428d6  mov     rcx, r15
0x1800428d9  call    ??4Session@@QEAAAEAU0@$$QEAU0@@Z; Session::operator=(Session &&)
0x1800428de  lea     rcx, [rsp+300h+var_2C8]; this
0x1800428e3  call    ??1Session@@QEAA@XZ; Session::~Session(void)
0x1800428e8  xorps   xmm0, xmm0
0x1800428eb  lea     r9, [rsp+300h+EndTime]; EndTime
0x1800428f0  movups  xmmword ptr [rdi+520h], xmm0
0x1800428f7  lea     r8, [rsp+300h+StartTime]; StartTime
0x1800428fc  mov     edx, 1; HandleCount
0x180042901  movups  xmmword ptr [rdi+530h], xmm0
0x180042908  lea     rcx, [rsp+300h+HandleArray]; HandleArray
0x18004290d  movups  xmmword ptr [rdi+540h], xmm0
0x180042914  call    cs:__imp_ProcessTrace
0x18004291a  test    eax, eax
0x18004291c  jz      short loc_180042927
0x18004291e  jg      short loc_1800428A2
0x180042920  mov     esi, eax
0x180042922  jmp     loc_1800429ED
0x180042927  mov     rcx, [rsp+300h+HandleArray]; TraceHandle
0x18004292c  call    cs:__imp_CloseTrace
0x180042932  mov     rcx, rdi; this
0x180042935  call    ?CloseUncompletedPowerTransitions@SystemSleepDiagnostics@@QEAAXXZ; SystemSleepDiagnostics::CloseUncompletedPowerTransitions(void)
0x18004293a  mov     rcx, rdi; this
0x18004293d  call    ?CloseUncompletedPowerRequests@SystemSleepDiagnostics@@QEAAXXZ; SystemSleepDiagnostics::CloseUncompletedPowerRequests(void)
0x180042942  mov     rcx, rdi; this
0x180042945  call    ?FilterPowerRequestsWhichEndedBeforeUserAway@SystemSleepDiagnostics@@QEAAXXZ; SystemSleepDiagnostics::FilterPowerRequestsWhichEndedBeforeUserAway(void)
0x18004294a  cmp     byte ptr [rdi+420h], 0
0x180042951  jnz     short loc_18004296C
0x180042953  cmp     qword ptr [r15], 0
0x180042957  jz      short loc_1800429A0
0x180042959  cmp     qword ptr [rdi+448h], 0
0x180042961  jz      short loc_1800429A0
0x180042963  cmp     dword ptr [rdi+450h], 0
0x18004296a  jz      short loc_1800429A0
0x18004296c  lea     r14, [rdi+428h]
0x180042973  mov     rax, [r14+8]
0x180042977  cmp     rax, [r14+10h]
0x18004297b  jz      short loc_180042992
0x18004297d  mov     rdx, r15; struct Session *
0x180042980  mov     rcx, rax; this
0x180042983  call    ??0Session@@QEAA@AEBU0@@Z; Session::Session(Session const &)
0x180042988  add     qword ptr [r14+8], 0D0h
0x180042990  jmp     short loc_1800429A0
0x180042992  mov     r8, r15
0x180042995  mov     rdx, rax
0x180042998  mov     rcx, r14
0x18004299b  call    ??$_Emplace_reallocate@AEBUSession@@@?$vector@USession@@V?$allocator@USession@@@std@@@std@@AEAAPEAUSession@@QEAU2@AEBU2@@Z; std::vector<Session>::_Emplace_reallocate<Session const &>(Session * const,Session const &)
0x1800429a0  lea     rcx, [rdi+510h]
0x1800429a7  call    ?clear@?$_Tree@V?$_Tmap_traits@_KUPowerRequest@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUPowerRequest@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,PowerRequest,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PowerRequest>>,0>>::clear(void)
0x1800429ac  mov     byte ptr [rdi+550h], 0
0x1800429b3  mov     dword ptr [rdi+424h], 0
0x1800429bd  mov     rdx, [rdi+560h]
0x1800429c4  mov     rcx, [rdi+558h]; this
0x1800429cb  cmp     rcx, rdx
0x1800429ce  jz      short loc_1800429E3
0x1800429d0  call    ??$_Destroy_range@V?$allocator@UPowerRequest@@@std@@@std@@YAXPEAUPowerRequest@@QEAU1@AEAV?$allocator@UPowerRequest@@@0@@Z; std::_Destroy_range<std::allocator<PowerRequest>>(PowerRequest *,PowerRequest * const,std::allocator<PowerRequest> &)
0x1800429d5  mov     rax, [rdi+558h]
0x1800429dc  mov     [rdi+560h], rax
0x1800429e3  mov     dword ptr [rdi+570h], 0
0x1800429ed  add     rbx, 20h ; ' '
0x1800429f1  jmp     loc_180042832
0x1800429f6  mov     eax, esi
0x1800429f8  mov     rcx, [rbp+200h+var_30]
0x1800429ff  xor     rcx, rsp; StackCookie
0x180042a02  call    __security_check_cookie
0x180042a07  lea     r11, [rsp+300h+var_20]
0x180042a0f  mov     rbx, [r11+38h]
0x180042a13  mov     rsi, [r11+40h]
0x180042a17  mov     rsp, r11
0x180042a1a  pop     r15
0x180042a1c  pop     r14
0x180042a1e  pop     r12
0x180042a20  pop     rdi
0x180042a21  pop     rbp
0x180042a22  retn
```
