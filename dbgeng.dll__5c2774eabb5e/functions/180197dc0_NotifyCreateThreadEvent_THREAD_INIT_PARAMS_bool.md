# NotifyCreateThreadEvent(THREAD_INIT_PARAMS *,bool)

- ea: `0x180197dc0`
- end: `0x180198156`
- name: `?NotifyCreateThreadEvent@@YAKPEAUTHREAD_INIT_PARAMS@@_N@Z`
- size: `918`
- prototype: `unsigned int __fastcall(struct THREAD_INIT_PARAMS *, bool)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18023a610`
- `0x18023be00`
- `0x18038c548`

## callees

- `0x180071a60`
- `0x1800727b8`
- `0x1800793cc`
- `0x18007ac6c`
- `0x18007c2dc`
- `0x18007d14c`
- `0x18007daa4`
- `0x18008fe74`
- `0x18009cda0`
- `0x1800b717c`
- `0x1800bd580`
- `0x1800c12b8`
- `0x1800cca3c`
- `0x1800f16fc`
- `0x18018ef88`
- `0x180195bac`
- `0x180196b28`
- `0x180197dc0`
- `0x1802d644c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197e41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197f50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019801d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197e41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197f50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18019801d`

## string_xrefs

- `0x1801980e4`: `IDebugEventCallbacks::CreateThread`
- `0x180197df8`: `*** Create thread %x:%x\n`
- `0x180197e4d`: `Create unowned thread `
- `0x180197e79`: `Thread %x not found in create thread notification.\n`
- `0x180197ec5`: `WARNING: Duplicate thread create event for %x:%x\n`
- `0x180197f17`: `Unable to allocate thread record for create thread event\n`
- `0x180197f30`: `Thread %x:%x will be lost\n`
- `0x180197f5c`: `Can't create thread `
- `0x180198132`: `Create thread unable to locate process or thread %x:%x\n`
- `0x180197ffa`: `Thread created: %lx.%lx\n`
- `0x180198037`: `Create thread `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NotifyCreateThreadEvent(struct THREAD_INIT_PARAMS *a1, char a2)
{
  struct ProcessInfo *ProcessBySystemId; // rax
  unsigned int v5; // r9d
  struct ProcessInfo *v6; // rbx
  const wchar_t *v7; // rdx
  __int64 i; // rcx
  ThreadInfo *v10; // rax
  struct DebugClient *v11; // rdx
  bool v12; // cf
  unsigned int v13; // eax
  void **v14; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+40h] [rbp-38h]
  const wchar_t *v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+58h] [rbp-20h]
  __int64 v19; // [rsp+60h] [rbp-18h]

  StartOutLine(8u, 1u);
  VerbOut(L"*** Create thread %x:%x\n", g_EventProcessSysId, g_EventThreadSysId);
  ProcessBySystemId = TargetInfo::FindProcessBySystemId(g_EventTarget, g_EventProcessSysId);
  v6 = ProcessBySystemId;
  if ( !ProcessBySystemId )
  {
    ErrOut(L"Unable to find system process %x\n");
    if ( g_EngNotify )
      return 6;
    GetSystemTimeAsFileTime(&g_LastEventTime);
    v7 = L"Create unowned thread ";
LABEL_22:
    g_LastEventType = 4;
    DbsDynamicString<unsigned short>::CopyStr(&g_LastEventDesc, v7, 0xFFFFFFFFLL);
    DbsDynamicString<unsigned short>::AppendHexNumber((DbsDynamicBuffer *)&g_LastEventDesc, 0);
    DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)&g_LastEventDesc, L" for ");
    DbsDynamicString<unsigned short>::AppendHexNumber((DbsDynamicBuffer *)&g_LastEventDesc, 0);
    return 6;
  }
  if ( a2 )
  {
    if ( !ProcessInfo::FindThreadByHandle(ProcessBySystemId, *((_QWORD *)a1 + 3)) )
    {
      ErrOut(L"Thread %x not found in create thread notification.\n", g_EventThreadSysId);
LABEL_20:
      ErrOut(L"Thread %x:%x will be lost\n", g_EventProcessSysId, g_EventThreadSysId);
      if ( g_EngNotify )
        return 6;
      GetSystemTimeAsFileTime(&g_LastEventTime);
      v7 = L"Can't create thread ";
      goto LABEL_22;
    }
  }
  else
  {
    for ( i = *((_QWORD *)ProcessBySystemId + 46); i; i = *(_QWORD *)(i + 24) )
    {
      if ( ((*((_DWORD *)ProcessBySystemId + 106) & 4) != 0 || *(_QWORD *)(i + 64) == *((_QWORD *)a1 + 3))
        && *(_DWORD *)(i + 36) == g_EventThreadSysId )
      {
        if ( (*((_DWORD *)ProcessBySystemId + 106) & 4) == 0 )
          WarnOut(L"WARNING: Duplicate thread create event for %x:%x\n", v5);
        return 9;
      }
    }
    *(_DWORD *)a1 = g_EventThreadSysId;
    v10 = (ThreadInfo *)operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 )
      v10 = ThreadInfo::ThreadInfo(v10, v6, a1, 0);
    if ( !v10 )
    {
      ErrOut(L"Unable to allocate thread record for create thread event\n");
      goto LABEL_20;
    }
  }
  FindEventProcessThread();
  if ( !g_EventProcess || !g_EventThread )
  {
    ErrOut(L"Create thread unable to locate process or thread %x:%x\n", g_EventProcessSysId, g_EventThreadSysId);
    return 6;
  }
  VerbOut(L"Thread created: %lx.%lx\n", g_EventProcessSysId, g_EventThreadSysId);
  if ( g_EngNotify )
    return 0;
  GetSystemTimeAsFileTime(&g_LastEventTime);
  g_LastEventType = 4;
  DbsDynamicString<unsigned short>::CopyStr(&g_LastEventDesc, L"Create thread ", 0xFFFFFFFFLL);
  DbsDynamicString<unsigned short>::AppendIntNumber(&g_LastEventDesc, *((unsigned int *)g_EventThread + 8), 0);
  DbsDynamicString<unsigned short>::AppendChar((DbsDynamicBuffer *)&g_LastEventDesc);
  DbsDynamicString<unsigned short>::AppendHexNumber((DbsDynamicBuffer *)&g_LastEventDesc, 0);
  ThreadChangedForBreakpoints();
  v12 = LODWORD(qword_180799A64[0]) < 2;
  if ( LODWORD(qword_180799A64[0]) == 2 )
  {
    StartOutLine(1u, 1u);
    dprintf(L"%s\n", g_LastEventDesc);
    v12 = LODWORD(qword_180799A64[0]) < 2;
  }
  v13 = ExecuteEventCommand(v12 ? 6 : 9, v11, dword_180799A80, qword_180799A88);
  v15 = 4;
  v16 = L"IDebugEventCallbacks::CreateThread";
  v14 = &CreateThreadEventApcData::`vftable';
  v17 = *((_QWORD *)a1 + 3);
  v18 = *((_QWORD *)a1 + 2);
  v19 = *((_QWORD *)a1 + 4);
  return SendEvent((struct AnyApcData *)&v14, v13);
}

```

## disassembly

```asm
0x180197dc0  mov     rax, rsp
0x180197dc3  push    rdi
0x180197dc4  sub     rsp, 70h
0x180197dc8  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180197dd0  mov     [rax+8], rbx
0x180197dd4  mov     [rax+10h], rbp
0x180197dd8  mov     bpl, dl
0x180197ddb  mov     rdi, rcx
0x180197dde  mov     edx, 1; unsigned int
0x180197de3  lea     ecx, [rdx+7]; unsigned int
0x180197de6  call    ?StartOutLine@@YAXKK@Z; StartOutLine(ulong,ulong)
0x180197deb  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197df2  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197df8  lea     rcx, aCreateThreadXX; "*** Create thread %x:%x\n"
0x180197dff  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180197e04  mov     r9d, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197e0b  mov     edx, r9d; unsigned int
0x180197e0e  mov     rcx, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; this
0x180197e15  call    ?FindProcessBySystemId@TargetInfo@@QEAAPEAVProcessInfo@@K@Z; TargetInfo::FindProcessBySystemId(ulong)
0x180197e1a  mov     rbx, rax
0x180197e1d  test    rax, rax
0x180197e20  jnz     short loc_180197E59
0x180197e22  lea     rcx, aUnableToFindSy; "Unable to find system process %x\n"
0x180197e29  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x180197e2e  cmp     cs:?g_EngNotify@@3KA, ebx; ulong g_EngNotify
0x180197e34  jnz     loc_18019813E
0x180197e3a  lea     rcx, ?g_LastEventTime@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x180197e41  call    cs:__imp_GetSystemTimeAsFileTime
0x180197e48  nop     dword ptr [rax+rax+00h]
0x180197e4d  lea     rdx, aCreateUnownedT; "Create unowned thread "
0x180197e54  jmp     loc_180197F63
0x180197e59  test    bpl, bpl
0x180197e5c  jz      short loc_180197E8A
0x180197e5e  mov     rdx, [rdi+18h]; unsigned __int64
0x180197e62  mov     rcx, rbx; this
0x180197e65  call    ?FindThreadByHandle@ProcessInfo@@QEAAPEAVThreadInfo@@_K@Z; ProcessInfo::FindThreadByHandle(unsigned __int64)
0x180197e6a  test    rax, rax
0x180197e6d  jnz     loc_180197FCC
0x180197e73  mov     edx, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197e79  lea     rcx, aThreadXNotFoun; "Thread %x not found in create thread no"...
0x180197e80  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x180197e85  jmp     loc_180197F23
0x180197e8a  mov     rcx, [rax+170h]
0x180197e91  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197e98  test    rcx, rcx
0x180197e9b  jz      short loc_180197EDB
0x180197e9d  mov     edx, [rbx+1A8h]
0x180197ea3  and     edx, 4
0x180197ea6  jnz     short loc_180197EB2
0x180197ea8  mov     rax, [rdi+18h]
0x180197eac  cmp     [rcx+40h], rax
0x180197eb0  jnz     short loc_180197EB8
0x180197eb2  cmp     [rcx+24h], r8d
0x180197eb6  jz      short loc_180197EBE
0x180197eb8  mov     rcx, [rcx+18h]
0x180197ebc  jmp     short loc_180197E98
0x180197ebe  test    edx, edx
0x180197ec0  jnz     short loc_180197ED1
0x180197ec2  mov     edx, r9d
0x180197ec5  lea     rcx, aWarningDuplica; "WARNING: Duplicate thread create event "...
0x180197ecc  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x180197ed1  mov     eax, 9
0x180197ed6  jmp     loc_180198143
0x180197edb  mov     [rdi], r8d
0x180197ede  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180197ee5  mov     ecx, 178h; unsigned __int64
0x180197eea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180197eef  mov     [rsp+78h+arg_10], rax
0x180197ef7  test    rax, rax
0x180197efa  jz      short loc_180197F0E
0x180197efc  xor     r9d, r9d; struct ISvcExecutionUnit *
0x180197eff  mov     r8, rdi; struct THREAD_INIT_PARAMS *
0x180197f02  mov     rdx, rbx; struct ProcessInfo *
0x180197f05  mov     rcx, rax; this
0x180197f08  call    ??0ThreadInfo@@QEAA@PEAVProcessInfo@@PEAUTHREAD_INIT_PARAMS@@PEAUISvcExecutionUnit@@@Z; ThreadInfo::ThreadInfo(ProcessInfo *,THREAD_INIT_PARAMS *,ISvcExecutionUnit *)
0x180197f0d  nop
0x180197f0e  test    rax, rax
0x180197f11  jnz     loc_180197FCC
0x180197f17  lea     rcx, aUnableToAlloca_12; "Unable to allocate thread record for cr"...
0x180197f1e  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x180197f23  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197f2a  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197f30  lea     rcx, aThreadXXWillBe; "Thread %x:%x will be lost\n"
0x180197f37  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x180197f3c  cmp     cs:?g_EngNotify@@3KA, 0; ulong g_EngNotify
0x180197f43  jnz     loc_18019813E
0x180197f49  lea     rcx, ?g_LastEventTime@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x180197f50  call    cs:__imp_GetSystemTimeAsFileTime
0x180197f57  nop     dword ptr [rax+rax+00h]
0x180197f5c  lea     rdx, aCanTCreateThre; "Can't create thread "
0x180197f63  lea     rbx, ?g_LastEventDesc@@3V?$DbsDeclDynamicString@G$0MI@$00@@A; DbsDeclDynamicString<ushort,200,1> g_LastEventDesc
0x180197f6a  mov     cs:?g_LastEventType@@3KA, 4; ulong g_LastEventType
0x180197f74  or      r8d, 0FFFFFFFFh
0x180197f78  mov     rcx, rbx
0x180197f7b  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x180197f80  mov     [rsp+78h+var_58], 0; int
0x180197f88  xor     r9d, r9d
0x180197f8b  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197f92  mov     rcx, rbx; this
0x180197f95  call    ?AppendHexNumber@?$DbsDynamicString@G@@QEAAJPEBG_KKK@Z; DbsDynamicString<ushort>::AppendHexNumber(ushort const *,unsigned __int64,ulong,ulong)
0x180197f9a  or      r8d, 0FFFFFFFFh
0x180197f9e  lea     rdx, aFor; " for "
0x180197fa5  mov     rcx, rbx; this
0x180197fa8  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x180197fad  mov     [rsp+78h+var_58], 0; int
0x180197fb5  xor     r9d, r9d
0x180197fb8  mov     r8d, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197fbf  mov     rcx, rbx; this
0x180197fc2  call    ?AppendHexNumber@?$DbsDynamicString@G@@QEAAJPEBG_KKK@Z; DbsDynamicString<ushort>::AppendHexNumber(ushort const *,unsigned __int64,ulong,ulong)
0x180197fc7  jmp     loc_18019813E
0x180197fcc  call    ?FindEventProcessThread@@YAXXZ; FindEventProcessThread(void)
0x180197fd1  cmp     cs:?g_EventProcess@@3PEAVProcessInfo@@EA, 0; ProcessInfo * g_EventProcess
0x180197fd9  jz      loc_180198125
0x180197fdf  cmp     cs:?g_EventThread@@3PEAVThreadInfo@@EA, 0; ThreadInfo * g_EventThread
0x180197fe7  jz      loc_180198125
0x180197fed  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180197ff4  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197ffa  lea     rcx, aThreadCreatedL; "Thread created: %lx.%lx\n"
0x180198001  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180198006  cmp     cs:?g_EngNotify@@3KA, 0; ulong g_EngNotify
0x18019800d  jbe     short loc_180198016
0x18019800f  xor     eax, eax
0x180198011  jmp     loc_180198143
0x180198016  lea     rcx, ?g_LastEventTime@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x18019801d  call    cs:__imp_GetSystemTimeAsFileTime
0x180198024  nop     dword ptr [rax+rax+00h]
0x180198029  mov     cs:?g_LastEventType@@3KA, 4; ulong g_LastEventType
0x180198033  or      r8d, 0FFFFFFFFh
0x180198037  lea     rdx, aCreateThread; "Create thread "
0x18019803e  lea     rbx, ?g_LastEventDesc@@3V?$DbsDeclDynamicString@G$0MI@$00@@A; DbsDeclDynamicString<ushort,200,1> g_LastEventDesc
0x180198045  mov     rcx, rbx
0x180198048  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x18019804d  mov     rax, cs:?g_EventThread@@3PEAVThreadInfo@@EA; ThreadInfo * g_EventThread
0x180198054  mov     edx, [rax+20h]
0x180198057  xor     r8d, r8d
0x18019805a  mov     rcx, rbx
0x18019805d  call    ?AppendIntNumber@?$DbsDynamicString@G@@QEAAJ_KKK@Z; DbsDynamicString<ushort>::AppendIntNumber(unsigned __int64,ulong,ulong)
0x180198062  mov     edx, 3Ah ; ':'
0x180198067  mov     rcx, rbx; this
0x18019806a  call    ?AppendChar@?$DbsDynamicString@G@@QEAAJG@Z; DbsDynamicString<ushort>::AppendChar(ushort)
0x18019806f  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x180198076  mov     [rsp+78h+var_58], 0; int
0x18019807e  xor     r9d, r9d
0x180198081  mov     rcx, rbx; this
0x180198084  call    ?AppendHexNumber@?$DbsDynamicString@G@@QEAAJPEBG_KKK@Z; DbsDynamicString<ushort>::AppendHexNumber(ushort const *,unsigned __int64,ulong,ulong)
0x180198089  call    ?ThreadChangedForBreakpoints@@YAXXZ; ThreadChangedForBreakpoints(void)
0x18019808e  mov     rax, cs:qword_180799A64
0x180198095  cmp     eax, 2
0x180198098  jnz     short loc_1801980C1
0x18019809a  lea     edx, [rax-1]; unsigned int
0x18019809d  mov     ecx, edx; unsigned int
0x18019809f  call    ?StartOutLine@@YAXKK@Z; StartOutLine(ulong,ulong)
0x1801980a4  mov     rdx, cs:?g_LastEventDesc@@3V?$DbsDeclDynamicString@G$0MI@$00@@A; DbsDeclDynamicString<ushort,200,1> g_LastEventDesc
0x1801980ab  lea     rcx, aS_35; "%s\n"
0x1801980b2  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801980b7  mov     rax, cs:qword_180799A64
0x1801980be  cmp     eax, 2
0x1801980c1  sbb     ecx, ecx
0x1801980c3  and     ecx, 0FFFFFFFDh
0x1801980c6  add     ecx, 9; unsigned int
0x1801980c9  mov     r9, cs:qword_180799A88; unsigned __int16 *
0x1801980d0  mov     r8d, cs:dword_180799A80; unsigned int
0x1801980d7  call    ?ExecuteEventCommand@@YAKKPEAVDebugClient@@KPEBG@Z; ExecuteEventCommand(ulong,DebugClient *,ulong,ushort const *)
0x1801980dc  mov     [rsp+78h+var_38], 4
0x1801980e4  lea     rcx, aIdebugeventcal_6; "IDebugEventCallbacks::CreateThread"
0x1801980eb  mov     [rsp+78h+var_30], rcx
0x1801980f0  lea     rcx, ??_7CreateThreadEventApcData@@6B@; const CreateThreadEventApcData::`vftable'
0x1801980f7  mov     [rsp+78h+var_40], rcx
0x1801980fc  mov     rcx, [rdi+18h]
0x180198100  mov     [rsp+78h+var_28], rcx
0x180198105  mov     rcx, [rdi+10h]
0x180198109  mov     [rsp+78h+var_20], rcx
0x18019810e  mov     rcx, [rdi+20h]
0x180198112  mov     [rsp+78h+var_18], rcx
0x180198117  mov     edx, eax; unsigned int
0x180198119  lea     rcx, [rsp+78h+var_40]; struct AnyApcData *
0x18019811e  call    ?SendEvent@@YAKPEAUAnyApcData@@K@Z; SendEvent(AnyApcData *,ulong)
0x180198123  jmp     short loc_180198143
0x180198125  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x18019812c  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180198132  lea     rcx, aCreateThreadUn; "Create thread unable to locate process "...
0x180198139  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18019813e  mov     eax, 6
0x180198143  lea     r11, [rsp+78h+var_8]
0x180198148  mov     rbx, [r11+10h]
0x18019814c  mov     rbp, [r11+18h]
0x180198150  mov     rsp, r11
0x180198153  pop     rdi
0x180198154  retn
```
