# LiveUserTargetInfo::ProcessEventException(_DEBUG_EVENT64 *)

- ea: `0x18023c3a0`
- end: `0x18023c879`
- name: `?ProcessEventException@LiveUserTargetInfo@@UEAAKPEAU_DEBUG_EVENT64@@@Z`
- size: `1241`
- prototype: `unsigned int __fastcall(LiveUserTargetInfo *__hidden this, struct _DEBUG_EVENT64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18007cf9c`
- `0x180081918`
- `0x18008d550`
- `0x1800b1544`
- `0x1800b6358`
- `0x1800b94c4`
- `0x1800c3810`
- `0x1800c6d10`
- `0x1800da4a8`
- `0x1800f0f40`
- `0x1801982c8`
- `0x180237d68`
- `0x18023ac80`
- `0x18023bcc4`
- `0x18023c3a0`
- `0x1802e9174`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c6ee`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c79c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c7b6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c7ec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c814`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c6ee`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c79c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c7b6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c7ec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18023c814`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18023c762`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18023c762`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023c521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18023c521`

## string_xrefs

- `0x18023c758`: `ntdll!`
- `0x18023c6e7`: `ntdll`
- `0x18023c7ac`: `LdrpWalkImportDescriptor`
- `0x18023c80a`: `RtlpInterlockedPopEntrySList`
- `0x18023c7e2`: `ExpInterlockedPopEntrySListFault`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LiveUserTargetInfo::ProcessEventException(LiveUserTargetInfo *this, struct _DEBUG_EVENT64 *a2)
{
  unsigned int v4; // ebx
  int v5; // r13d
  struct _EXCEPTION_RECORD64 *v6; // r15
  DWORD ExceptionCode; // edi
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  struct DebugClient *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  DWORD v14; // eax
  unsigned int v15; // eax
  struct ImageInfo *ImageByOffset; // rax
  const wchar_t *v18; // rcx
  int v19; // r9d
  wchar_t *v20; // rbx
  __int64 v21; // rax
  const wchar_t *v22; // rbx
  _QWORD v23[4]; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *String1[3]; // [rsp+58h] [rbp-B0h] BYREF
  char v25; // [rsp+70h] [rbp-98h] BYREF

  v23[3] = -2;
  v4 = 0;
  v5 = 0;
  v6 = (struct _EXCEPTION_RECORD64 *)((char *)a2 + 16);
  OnExceptionEvent((struct _EXCEPTION_RECORD64 *const)((char *)a2 + 16));
  g_ExceptionRecord = *v6;
  ExceptionCode = v6->ExceptionCode;
  v8 = *((_QWORD *)a2 + 4);
  g_TargetEventPcUnsanitized = v8;
  if ( g_EventProcess )
  {
    v9 = SanitizeSymbolAddress(g_Machine, g_EventProcess, v8);
    v8 = g_TargetEventPcUnsanitized;
  }
  else
  {
    v9 = v8;
  }
  g_TargetEventPc = v9;
  EventOut(L"Exception %X at %p (%p)\n", ExceptionCode, v9, v8);
  if ( g_EventToSignal
    && (MEMORY[0x7FFE02D0] & 0x10) == 0
    && !(*(unsigned int (__fastcall **)(LiveUserTargetInfo *, _QWORD))(*(_QWORD *)this + 64LL))(this, 0) )
  {
    LoadDynamicCalls(&g_User32CallsDesc);
  }
  if ( g_EventThread )
  {
    if ( ExceptionCode != 1073741829 )
      goto LABEL_19;
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v13);
    v14 = VDMEvent(a2);
    ExceptionCode = v14;
    if ( v14 )
    {
      if ( v14 == 1073741829 )
      {
        v4 = 2;
        goto LABEL_13;
      }
LABEL_19:
      if ( ExceptionCode != 1073741854 && ExceptionCode != 1073741855 )
      {
        if ( ExceptionCode == -2147483645 )
        {
          if ( g_TidToResume && g_TidResumed )
          {
            g_TidToResume = 0;
            g_TidResumed = 0;
            v4 = 2;
            goto LABEL_16;
          }
        }
        else if ( ExceptionCode != -2147483644 )
        {
          if ( ExceptionCode == -1073741819 )
          {
            if ( *((_DWORD *)a2 + 42) )
            {
              if ( g_EventProcess )
              {
                ImageByOffset = ProcessInfo::FindImageByOffset(g_EventProcess, *((_QWORD *)a2 + 4), 0, 0);
                if ( ImageByOffset )
                {
                  v18 = *((_DWORD *)ImageByOffset + 59) < 2u ? 0LL : (const wchar_t *)*((_QWORD *)ImageByOffset + 28);
                  if ( !_wcsicmp(v18, L"ntdll") )
                  {
                    DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
                      (unsigned int)String1,
                      (unsigned int)&v25,
                      100,
                      v19,
                      1);
                    memset(v23, 0, 24);
                    GetSymbol(*((_QWORD *)a2 + 4), -1, (__int64)String1, (__int64)v23, (__int64)&v23[1]);
                    v20 = String1[0];
                    if ( !_wcsnicmp(String1[0], L"ntdll!", 6u) )
                    {
                      v21 = 7;
                      if ( v20[6] != 95 )
                        v21 = 6;
                      if ( (v22 = &v20[v21], (g_EngOptions & 0x10) != 0)
                        && (!_wcsicmp(v22, L"LdrpSnapThunk") || !_wcsicmp(v22, L"LdrpWalkImportDescriptor"))
                        || !v23[0] && !_wcsicmp(v22, L"ExpInterlockedPopEntrySListFault")
                        || *((_DWORD *)this + 51) == 4102 && !_wcsicmp(v22, L"RtlpInterlockedPopEntrySList") )
                      {
                        v4 = 3;
                        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(String1);
                        goto LABEL_16;
                      }
                    }
                    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(String1);
                  }
                }
              }
            }
          }
          else if ( ExceptionCode == -1073741420 )
          {
            if ( *((_DWORD *)this + 57) == 2 )
            {
              if ( !g_EventTarget || (unsigned int)(*((_DWORD *)g_EventTarget + 1026) - 2) > 1 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v13);
              AnalyzeDeadlock(v11, v6, *((_DWORD *)a2 + 42));
            }
            else
            {
              OutputDeadlock(v6, *((_DWORD *)a2 + 42));
            }
            v5 = 1;
          }
          goto LABEL_14;
        }
      }
      if ( g_EventThread )
      {
        v15 = ProcessBreakpointOrStepException(v6, *((_DWORD *)a2 + 42));
        goto LABEL_15;
      }
LABEL_14:
      v15 = NotifyExceptionEvent(v6, *((_DWORD *)a2 + 42), 1, v5, 0);
LABEL_15:
      v4 = v15;
      goto LABEL_16;
    }
    v4 = 3;
  }
  else if ( ExceptionCode != 1073741829 )
  {
    goto LABEL_19;
  }
LABEL_13:
  if ( !g_EventThread )
    goto LABEL_14;
LABEL_16:
  g_EngDefer |= 1u;
  return v4;
}

```

## disassembly

```asm
0x18023c3a0  mov     rax, rsp
0x18023c3a3  push    rbp
0x18023c3a4  push    rdi
0x18023c3a5  push    r12
0x18023c3a7  push    r13
0x18023c3a9  push    r15
0x18023c3ab  lea     rbp, [rax-68h]
0x18023c3af  sub     rsp, 140h
0x18023c3b6  mov     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFEh
0x18023c3bf  mov     [rax+18h], rbx
0x18023c3c3  mov     [rax+20h], rsi
0x18023c3c7  mov     rax, cs:__security_cookie
0x18023c3ce  xor     rax, rsp
0x18023c3d1  mov     [rbp+60h+var_30], rax
0x18023c3d5  mov     rsi, rdx
0x18023c3d8  mov     r12, rcx
0x18023c3db  xor     ebx, ebx
0x18023c3dd  mov     r13d, ebx
0x18023c3e0  lea     r15, [rdx+10h]
0x18023c3e4  mov     rcx, r15; struct _EXCEPTION_RECORD64 *
0x18023c3e7  call    ?OnExceptionEvent@@YAXQEAU_EXCEPTION_RECORD64@@@Z; OnExceptionEvent(_EXCEPTION_RECORD64 * const)
0x18023c3ec  movups  xmm0, xmmword ptr [r15]
0x18023c3f0  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A, xmm0; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c3f7  movups  xmm1, xmmword ptr [r15+10h]
0x18023c3fc  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+10h, xmm1; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c403  movups  xmm0, xmmword ptr [r15+20h]
0x18023c408  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+20h, xmm0; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c40f  movups  xmm1, xmmword ptr [r15+30h]
0x18023c414  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+30h, xmm1; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c41b  movups  xmm0, xmmword ptr [r15+40h]
0x18023c420  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+40h, xmm0; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c427  movups  xmm1, xmmword ptr [r15+50h]
0x18023c42c  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+50h, xmm1; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c433  movups  xmm0, xmmword ptr [r15+60h]
0x18023c438  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+60h, xmm0; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c43f  movups  xmm1, xmmword ptr [r15+70h]
0x18023c444  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+70h, xmm1; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c44b  movups  xmm0, xmmword ptr [r15+80h]
0x18023c453  movups  xmmword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+80h, xmm0; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c45a  mov     rax, [r15+90h]
0x18023c461  mov     qword ptr cs:?g_ExceptionRecord@@3U_EXCEPTION_RECORD64@@A+90h, rax; _EXCEPTION_RECORD64 g_ExceptionRecord
0x18023c468  mov     edi, [r15]
0x18023c46b  mov     r9, [rsi+20h]
0x18023c46f  mov     cs:?g_TargetEventPcUnsanitized@@3_KA, r9; unsigned __int64 g_TargetEventPcUnsanitized
0x18023c476  mov     rdx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18023c47d  test    rdx, rdx
0x18023c480  jz      short loc_18023C49A
0x18023c482  mov     r8, r9; unsigned __int64
0x18023c485  mov     rcx, cs:?g_Machine@@3PEAVMachineInfo@@EA; struct MachineInfo *
0x18023c48c  call    ?SanitizeSymbolAddress@@YA_KPEAVMachineInfo@@PEAVProcessInfo@@_K@Z; SanitizeSymbolAddress(MachineInfo *,ProcessInfo *,unsigned __int64)
0x18023c491  mov     r9, cs:?g_TargetEventPcUnsanitized@@3_KA; unsigned __int64 g_TargetEventPcUnsanitized
0x18023c498  jmp     short loc_18023C49D
0x18023c49a  mov     rax, r9
0x18023c49d  mov     cs:?g_TargetEventPc@@3_KA, rax; unsigned __int64 g_TargetEventPc
0x18023c4a4  mov     r8, rax
0x18023c4a7  mov     edx, edi
0x18023c4a9  lea     rcx, aExceptionXAtPP; "Exception %X at %p (%p)\n"
0x18023c4b0  call    ?EventOut@@YAXPEBGZZ; EventOut(ushort const *,...)
0x18023c4b5  cmp     cs:?g_EventToSignal@@3PEAXEA, rbx; void * g_EventToSignal
0x18023c4bc  jz      loc_18023C55A
0x18023c4c2  test    byte ptr ds:7FFE02D0h, 10h
0x18023c4ca  jnz     loc_18023C55A
0x18023c4d0  mov     rax, [r12]
0x18023c4d4  xor     edx, edx
0x18023c4d6  mov     rcx, r12
0x18023c4d9  mov     rax, [rax+40h]
0x18023c4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023c4e2  test    eax, eax
0x18023c4e4  jnz     short loc_18023C55A
0x18023c4e6  lea     rcx, ?g_User32CallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_User32CallsDesc
0x18023c4ed  call    LoadDynamicCalls
0x18023c4f2  test    eax, eax
0x18023c4f4  jnz     short loc_18023C55A
0x18023c4f6  mov     rax, cs:qword_18082DE80
0x18023c4fd  test    rax, rax
0x18023c500  jz      short loc_18023C55A
0x18023c502  mov     rax, cs:qword_18082DE78
0x18023c509  test    rax, rax
0x18023c50c  jz      short loc_18023C55A
0x18023c50e  mov     rax, cs:qword_18082DE88
0x18023c515  test    rax, rax
0x18023c518  jz      short loc_18023C55A
0x18023c51a  mov     rbx, cs:qword_18082DE78
0x18023c521  call    cs:__imp_GetCurrentThreadId
0x18023c528  nop     dword ptr [rax+rax+00h]
0x18023c52d  mov     ecx, eax
0x18023c52f  mov     rax, rbx
0x18023c532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023c537  mov     rbx, rax
0x18023c53a  mov     rax, cs:qword_18082DE80
0x18023c541  mov     rcx, rbx
0x18023c544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023c549  mov     rax, cs:qword_18082DE88
0x18023c550  mov     rcx, rbx
0x18023c553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023c558  xor     ebx, ebx
0x18023c55a  cmp     cs:?g_EventThread@@3PEAVThreadInfo@@EA, rbx; ThreadInfo * g_EventThread
0x18023c561  jz      loc_18023C5F6
0x18023c567  cmp     edi, 40000005h
0x18023c56d  jnz     loc_18023C600
0x18023c573  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18023c578  mov     rcx, rsi; struct _DEBUG_EVENT64 *
0x18023c57b  call    ?VDMEvent@@YAKPEAU_DEBUG_EVENT64@@@Z; VDMEvent(_DEBUG_EVENT64 *)
0x18023c580  mov     edi, eax
0x18023c582  test    eax, eax
0x18023c584  jz      short loc_18023C5EF
0x18023c586  cmp     eax, 40000005h
0x18023c58b  jnz     short loc_18023C600
0x18023c58d  mov     ebx, 2
0x18023c592  cmp     cs:?g_EventThread@@3PEAVThreadInfo@@EA, r13; ThreadInfo * g_EventThread
0x18023c599  jnz     short loc_18023C5BD
0x18023c59b  mov     [rsp+160h+var_140], 0; struct ISvcExceptionInformation *
0x18023c5a4  mov     r9d, r13d; int
0x18023c5a7  mov     r8d, 1; int
0x18023c5ad  mov     edx, [rsi+0A8h]; unsigned int
0x18023c5b3  mov     rcx, r15; struct _EXCEPTION_RECORD64 *
0x18023c5b6  call    ?NotifyExceptionEvent@@YAKPEAU_EXCEPTION_RECORD64@@KHHPEAUISvcExceptionInformation@@@Z; NotifyExceptionEvent(_EXCEPTION_RECORD64 *,ulong,int,int,ISvcExceptionInformation *)
0x18023c5bb  mov     ebx, eax
0x18023c5bd  or      cs:?g_EngDefer@@3KA, 1; ulong g_EngDefer
0x18023c5c4  mov     eax, ebx
0x18023c5c6  mov     rcx, [rbp+60h+var_30]
0x18023c5ca  xor     rcx, rsp; StackCookie
0x18023c5cd  call    __security_check_cookie
0x18023c5d2  lea     r11, [rsp+160h+var_20]
0x18023c5da  mov     rbx, [r11+40h]
0x18023c5de  mov     rsi, [r11+48h]
0x18023c5e2  mov     rsp, r11
0x18023c5e5  pop     r15
0x18023c5e7  pop     r13
0x18023c5e9  pop     r12
0x18023c5eb  pop     rdi
0x18023c5ec  pop     rbp
0x18023c5ed  retn
0x18023c5ef  mov     ebx, 3
0x18023c5f4  jmp     short loc_18023C592
0x18023c5f6  cmp     edi, 40000005h
0x18023c5fc  jz      short loc_18023C592
0x18023c5fe  xor     ebx, ebx
0x18023c600  cmp     edi, 4000001Eh
0x18023c606  jz      loc_18023C859
0x18023c60c  cmp     edi, 4000001Fh
0x18023c612  jz      loc_18023C859
0x18023c618  cmp     edi, 80000003h
0x18023c61e  jz      loc_18023C833
0x18023c624  cmp     edi, 80000004h
0x18023c62a  jz      loc_18023C859
0x18023c630  cmp     edi, 0C0000005h
0x18023c636  jz      short loc_18023C69B
0x18023c638  cmp     edi, 0C0000194h
0x18023c63e  jnz     loc_18023C59B
0x18023c644  mov     ebx, 2
0x18023c649  cmp     [r12+0E4h], ebx
0x18023c651  jnz     short loc_18023C682
0x18023c653  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x18023c65a  test    rax, rax
0x18023c65d  jz      short loc_18023C66C
0x18023c65f  mov     eax, [rax+1008h]
0x18023c665  sub     eax, ebx
0x18023c667  cmp     eax, 1
0x18023c66a  jbe     short loc_18023C671
0x18023c66c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18023c671  mov     r8d, [rsi+0A8h]; unsigned int
0x18023c678  mov     rdx, r15; struct _EXCEPTION_RECORD64 *
0x18023c67b  call    ?AnalyzeDeadlock@@YAXPEAVDebugClient@@PEAU_EXCEPTION_RECORD64@@K@Z; AnalyzeDeadlock(DebugClient *,_EXCEPTION_RECORD64 *,ulong)
0x18023c680  jmp     short loc_18023C690
0x18023c682  mov     edx, [rsi+0A8h]; unsigned int
0x18023c688  mov     rcx, r15; struct _EXCEPTION_RECORD64 *
0x18023c68b  call    ?OutputDeadlock@@YAXPEAU_EXCEPTION_RECORD64@@K@Z; OutputDeadlock(_EXCEPTION_RECORD64 *,ulong)
0x18023c690  mov     r13d, 1
0x18023c696  jmp     loc_18023C59B
0x18023c69b  cmp     [rsi+0A8h], ebx
0x18023c6a1  jz      loc_18023C59B
0x18023c6a7  mov     rcx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; this
0x18023c6ae  test    rcx, rcx
0x18023c6b1  jz      loc_18023C59B
0x18023c6b7  xor     r9d, r9d; int
0x18023c6ba  xor     r8d, r8d; int
0x18023c6bd  mov     rdx, [rsi+20h]; unsigned __int64
0x18023c6c1  call    ?FindImageByOffset@ProcessInfo@@QEAAPEAVImageInfo@@_KHH@Z; ProcessInfo::FindImageByOffset(unsigned __int64,int,int)
0x18023c6c6  test    rax, rax
0x18023c6c9  jz      loc_18023C59B
0x18023c6cf  mov     ebx, 2
0x18023c6d4  cmp     [rax+0ECh], ebx
0x18023c6da  jb      short loc_18023C6E5
0x18023c6dc  mov     rcx, [rax+0E0h]
0x18023c6e3  jmp     short loc_18023C6E7
0x18023c6e5  xor     ecx, ecx; String1
0x18023c6e7  lea     rdx, aNtdll_0; "ntdll"
0x18023c6ee  call    cs:__imp__wcsicmp
0x18023c6f5  nop     dword ptr [rax+rax+00h]
0x18023c6fa  test    eax, eax
0x18023c6fc  jnz     loc_18023C59B
0x18023c702  mov     byte ptr [rsp+160h+var_140], 1
0x18023c707  lea     r8d, [rax+64h]
0x18023c70b  lea     rdx, [rsp+160h+var_F8]
0x18023c710  lea     rcx, [rsp+160h+String1]
0x18023c715  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x18023c71a  nop
0x18023c71b  mov     qword ptr [rsp+160h+var_130], 0
0x18023c724  xorps   xmm0, xmm0
0x18023c727  movdqu  xmmword ptr [rsp+160h+var_130+8], xmm0
0x18023c72d  lea     rax, [rsp+160h+var_130+8]
0x18023c732  mov     [rsp+160h+var_140], rax; __int64
0x18023c737  lea     r9, [rsp+160h+var_130]; __int64
0x18023c73c  lea     r8, [rsp+160h+String1]; __int64
0x18023c741  or      edx, 0FFFFFFFFh; int
0x18023c744  mov     rcx, [rsi+20h]; int
0x18023c748  call    ?GetSymbol@@YAH_KKPEAV?$DbsDynamicString@G@@PEA_KV?$shared_ptr@USYMBOL_INFO_AND_NAME@@@std@@@Z; GetSymbol(unsigned __int64,ulong,DbsDynamicString<ushort> *,unsigned __int64 *,std::shared_ptr<SYMBOL_INFO_AND_NAME>)
0x18023c74d  mov     rbx, [rsp+160h+String1]
0x18023c752  mov     r8d, 6; MaxCount
0x18023c758  lea     rdx, aNtdll; "ntdll!"
0x18023c75f  mov     rcx, rbx; String1
0x18023c762  call    cs:__imp__wcsnicmp
0x18023c769  nop     dword ptr [rax+rax+00h]
0x18023c76e  test    eax, eax
0x18023c770  jnz     loc_18023C824
0x18023c776  mov     eax, 0Eh
0x18023c77b  lea     ecx, [rax-2]
0x18023c77e  cmp     word ptr [rbx+0Ch], 5Fh ; '_'
0x18023c783  cmovnz  eax, ecx
0x18023c786  add     rbx, rax
0x18023c789  test    byte ptr cs:?g_EngOptions@@3KA, 10h; ulong g_EngOptions
0x18023c790  jz      short loc_18023C7DA
0x18023c792  lea     rdx, aLdrpsnapthunk; "LdrpSnapThunk"
0x18023c799  mov     rcx, rbx; String1
0x18023c79c  call    cs:__imp__wcsicmp
0x18023c7a3  nop     dword ptr [rax+rax+00h]
0x18023c7a8  test    eax, eax
0x18023c7aa  jz      short loc_18023C7C6
0x18023c7ac  lea     rdx, aLdrpwalkimport; "LdrpWalkImportDescriptor"
0x18023c7b3  mov     rcx, rbx; String1
0x18023c7b6  call    cs:__imp__wcsicmp
0x18023c7bd  nop     dword ptr [rax+rax+00h]
0x18023c7c2  test    eax, eax
0x18023c7c4  jnz     short loc_18023C7DA
0x18023c7c6  mov     ebx, 3
0x18023c7cb  lea     rcx, [rsp+160h+String1]
0x18023c7d0  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18023c7d5  jmp     loc_18023C5BD
0x18023c7da  cmp     qword ptr [rsp+160h+var_130], 0
0x18023c7e0  jnz     short loc_18023C7FC
0x18023c7e2  lea     rdx, aExpinterlocked; "ExpInterlockedPopEntrySListFault"
0x18023c7e9  mov     rcx, rbx; String1
0x18023c7ec  call    cs:__imp__wcsicmp
0x18023c7f3  nop     dword ptr [rax+rax+00h]
0x18023c7f8  test    eax, eax
0x18023c7fa  jz      short loc_18023C7C6
0x18023c7fc  cmp     dword ptr [r12+0CCh], 1006h
0x18023c808  jnz     short loc_18023C824
0x18023c80a  lea     rdx, aRtlpinterlocke; "RtlpInterlockedPopEntrySList"
0x18023c811  mov     rcx, rbx; String1
0x18023c814  call    cs:__imp__wcsicmp
0x18023c81b  nop     dword ptr [rax+rax+00h]
0x18023c820  test    eax, eax
0x18023c822  jz      short loc_18023C7C6
0x18023c824  lea     rcx, [rsp+160h+String1]
0x18023c829  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18023c82e  jmp     loc_18023C59B
0x18023c833  cmp     cs:?g_TidToResume@@3KA, ebx; ulong g_TidToResume
0x18023c839  jz      short loc_18023C859
0x18023c83b  cmp     cs:?g_TidResumed@@3HA, ebx; int g_TidResumed
0x18023c841  jz      short loc_18023C859
0x18023c843  mov     cs:?g_TidToResume@@3KA, ebx; ulong g_TidToResume
0x18023c849  mov     cs:?g_TidResumed@@3HA, ebx; int g_TidResumed
0x18023c84f  mov     ebx, 2
0x18023c854  jmp     loc_18023C5BD
0x18023c859  cmp     cs:?g_EventThread@@3PEAVThreadInfo@@EA, rbx; ThreadInfo * g_EventThread
0x18023c860  jz      loc_18023C59B
0x18023c866  mov     edx, [rsi+0A8h]; unsigned int
0x18023c86c  mov     rcx, r15; struct _EXCEPTION_RECORD64 *
0x18023c86f  call    ?ProcessBreakpointOrStepException@@YAKPEAU_EXCEPTION_RECORD64@@K@Z; ProcessBreakpointOrStepException(_EXCEPTION_RECORD64 *,ulong)
0x18023c874  jmp     loc_18023C5BB
```
