# NGENService::ControllerRun(void)

- ea: `0x180005688`
- end: `0x180005af5`
- name: `?ControllerRun@NGENService@@YA_NXZ`
- size: `1133`
- prototype: `bool __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task`

## callers

- `0x18001b1e4`

## callees

- `0x180001e8c`
- `0x18000352c`
- `0x1800035bc`
- `0x1800039ac`
- `0x1800053a0`
- `0x180005688`
- `0x180005d58`
- `0x18002e1d0`
- `0x18002e418`
- `0x180030568`
- `0x18003069c`
- `0x180030d84`
- `0x180032fe8`
- `0x18003303c`
- `0x180036354`
- `0x18003dc30`
- `0x18003f263`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005778`
- `KERNEL32!EnterCriticalSection` at `0x18000579c`
- `KERNEL32!EnterCriticalSection` at `0x180005778`
- `KERNEL32!EnterCriticalSection` at `0x18000579c`
- `KERNEL32!LeaveCriticalSection` at `0x1800057b0`
- `KERNEL32!LeaveCriticalSection` at `0x180005a7c`
- `KERNEL32!LeaveCriticalSection` at `0x1800057b0`
- `KERNEL32!LeaveCriticalSection` at `0x180005a7c`
- `KERNEL32!SetEvent` at `0x180005a5a`
- `KERNEL32!SetEvent` at `0x180005a5a`
- `KERNEL32!ResetEvent` at `0x180005a4d`
- `KERNEL32!ResetEvent` at `0x180005a4d`
- `KERNEL32!WaitForSingleObject` at `0x18000572e`
- `KERNEL32!WaitForSingleObject` at `0x18000574d`
- `KERNEL32!WaitForSingleObject` at `0x18000572e`
- `KERNEL32!WaitForSingleObject` at `0x18000574d`
- `KERNEL32!HeapFree` at `0x180005ab3`
- `KERNEL32!HeapFree` at `0x180005ab3`
- `KERNEL32!GetProcessHeap` at `0x180005a9e`
- `KERNEL32!GetProcessHeap` at `0x180005a9e`

## string_xrefs

- `0x180005925`: `SERVICE_INTERRUPT`
- `0x180005901`: `SERVICEWORKER_INTERRUPT`
- `0x18000595b`: `Service work was interrupted due to the following reason(s): %s (Mask: 0x%02x)\n`
- `0x18000599b`: `ControllerRun(): Handling service interrupt...\n`
- `0x180005a27`: `ControllerRun(): Handling higher priority service worker interrupt...\n`
- `0x180005a6c`: `ControllerRun(): Resuming Listener thread...\n`

## pseudocode

```c
bool __fastcall NGENService::ControllerRun(NGENService *this)
{
  bool v1; // r12
  char v2; // r13
  int v3; // edx
  const unsigned __int16 *v4; // rdx
  NGENService *v5; // rcx
  int v6; // ebx
  const unsigned __int16 *v7; // rdx
  NGENService *v8; // rcx
  unsigned int v9; // esi
  int v10; // ebx
  unsigned int v11; // r15d
  void *v12; // rdi
  size_t v13; // rdi
  size_t v14; // r8
  char v15; // di
  int i; // ebx
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // rbx
  char v19; // al
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  void *v22; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v25; // [rsp+30h] [rbp-D8h]
  size_t v26; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v28; // [rsp+48h] [rbp-C0h]
  size_t Size; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-B0h]
  void *Src; // [rsp+60h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION *v32; // [rsp+68h] [rbp-A0h]
  __int64 v33; // [rsp+70h] [rbp-98h]
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+78h] [rbp-90h]
  char v35; // [rsp+80h] [rbp-88h]
  int v36; // [rsp+88h] [rbp-80h] BYREF
  __int64 v37; // [rsp+8Ch] [rbp-7Ch]
  LPVOID lpMem; // [rsp+98h] [rbp-70h]
  __int16 v39; // [rsp+A0h] [rbp-68h] BYREF

  v1 = 1;
  v2 = 0;
  do
  {
    if ( v2 )
      break;
    v36 = 2;
    v37 = 512;
    lpMem = &v39;
    v39 = 0;
    if ( (int)GenerateVersionedFileNameNoThrow((SString *)&v36) >= 0 )
    {
      while ( 1 )
      {
        SString::ConvertToUnicode((SString *)&v36);
        if ( !(unsigned int)FileExists((const unsigned __int16 *)lpMem)
          || !WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
        {
          break;
        }
        ClrSleepEx(0x3E8u, v3);
      }
    }
    if ( WaitForSingleObject(NGENService::g_hInterruptEvent, 0) )
    {
      NGENService::DebugLog((NGENService *)L"ControllerRun(): About to execute state machine...\n", v4);
      v1 = NGENService::ExecuteControllerStateMachine(v5);
    }
    v32 = &NGENService::ControllerState::m_csControllerState;
    LOBYTE(v33) = 0;
    EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
    LOBYTE(v33) = 1;
    if ( NGENService::g_InterruptMask )
    {
      v34 = &NGENService::ControllerState::m_csControllerState;
      v35 = 0;
      EnterCriticalSection(&NGENService::ControllerState::m_csControllerState);
      v35 = 1;
      v6 = NGENService::ControllerState::m_dwControllerState;
      LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
      if ( ((v6 - 1) & 0xFFFFFFFD) == 0 )
      {
        v26 = 0x200000002LL;
        v9 = 2;
        v10 = 16;
        LODWORD(v27) = 16;
        v28 = (unsigned __int16 *)&SString::s_EmptyBuffer;
        v11 = NGENService::g_InterruptMask;
        Size = 0x200000002LL;
        LODWORD(v30) = 16;
        Src = (void *)&SString::s_EmptyBuffer;
        SString::Clear((SString *)&Size);
        if ( (v30 & 0x10) != 0 )
        {
          v26 = Size;
          v12 = Src;
          v28 = (unsigned __int16 *)Src;
          v10 = v30;
          LODWORD(v27) = v30;
        }
        else
        {
          v13 = (unsigned int)Size;
          if ( (unsigned int)Size > 2 )
          {
            SBuffer::ReallocateBuffer(&v26, (unsigned int)Size, 0);
            v10 = v27;
            v9 = HIDWORD(v26);
          }
          LODWORD(v26) = v13;
          if ( (v10 & 0x10) != 0 )
          {
            SBuffer::ReallocateBuffer(&v26, v9, 1);
            v10 = v27;
          }
          v14 = v13;
          v12 = Src;
          memcpy_0(v28, Src, v14);
        }
        LODWORD(v27) = v30 & 7 | v10 & 0xFFFFFEF8;
        if ( (v30 & 8) != 0 )
          operator delete(v12);
        v15 = 1;
        for ( i = 1; i < 32; i *= 2 )
        {
          if ( (i & v11) != 0 )
          {
            if ( v15 == 1 )
              v15 = 0;
            else
              SString::Append((SString *)&v26, L", ");
            switch ( i )
            {
              case 1:
                v17 = L"SERVICE_INTERRUPT";
                break;
              case 2:
                v17 = L"CLIENT_INTERRUPT";
                break;
              case 4:
                v17 = L"USER_INTERRUPT";
                break;
              case 8:
                v17 = L"DIRTY_ROOTSTORE_INTERRUPT";
                break;
              case 16:
                v17 = L"SERVICEWORKER_INTERRUPT";
                break;
              default:
                v17 = 0;
                break;
            }
            SString::Append((SString *)&v26, v17);
          }
        }
        SString::ConvertToUnicode((SString *)&v26);
        LODWORD(v25) = NGENService::g_InterruptMask;
        v18 = v28;
        NGENService::EventLog(
          0,
          (const unsigned __int16 *)4,
          0x454u,
          (unsigned int)L"Service work was interrupted due to the following reason(s): %s (Mask: 0x%02x)\n",
          v28,
          v25,
          v26);
        if ( (v27 & 8) != 0 )
          operator delete(v18);
      }
      v19 = NGENService::g_InterruptMask;
      if ( (NGENService::g_InterruptMask & 1) != 0 )
      {
        NGENService::DebugLog((NGENService *)L"ControllerRun(): Handling service interrupt...\n", v7);
        v19 = NGENService::g_InterruptMask & 0xFE;
        NGENService::g_InterruptMask &= ~1u;
        v2 = 1;
      }
      if ( (v19 & 4) != 0 )
      {
        NGENService::DebugLog((NGENService *)L"ControllerRun(): Handling user interrupt...\n", v7);
        v19 = NGENService::g_InterruptMask & 0xFB;
        NGENService::g_InterruptMask &= ~4u;
      }
      if ( (v19 & 2) != 0 )
      {
        NGENService::DebugLog((NGENService *)L"ControllerRun(): Handling client interrupt...\n", v7);
        v19 = NGENService::g_InterruptMask & 0xFD;
        NGENService::g_InterruptMask &= ~2u;
      }
      if ( (v19 & 8) != 0 )
      {
        NGENService::ResetDirtyRootStore(v8);
        NGENService::ControllerState::SetAccumulatedWaitIdleTime(0);
        NGENService::DebugLog((NGENService *)L"ControllerRun(): Handling dirty rootstore interrupt...\n", v20);
        v19 = NGENService::g_InterruptMask & 0xF7;
        NGENService::g_InterruptMask &= ~8u;
      }
      if ( (v19 & 0x10) != 0 )
      {
        NGENService::DebugLog(
          (NGENService *)L"ControllerRun(): Handling higher priority service worker interrupt...\n",
          v7);
        NGENService::g_InterruptMask &= ~0x10u;
      }
      NGENService::DebugLog((NGENService *)L"RunController(): ResetInterrupt()\n", v7);
      ResetEvent(NGENService::g_hInterruptEvent);
      SetEvent(NGENService::g_hInterruptProcessedEvent);
      NGENService::ControllerState::Set(0, 7u);
      NGENService::DebugLog((NGENService *)L"ControllerRun(): Resuming Listener thread...\n", v21);
    }
    LeaveCriticalSection(&NGENService::ControllerState::m_csControllerState);
    if ( (v37 & 0x800000000LL) != 0 )
    {
      v22 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v22);
      }
    }
  }
  while ( v1 );
  return v1;
}

```

## disassembly

```asm
0x180005688  mov     rax, rsp
0x18000568b  mov     [rax+8], rbx
0x18000568f  mov     [rax+10h], rsi
0x180005693  mov     [rax+18h], rdi
0x180005697  mov     [rax+20h], r12
0x18000569b  push    rbp
0x18000569c  push    r13
0x18000569e  push    r15
0x1800056a0  lea     rbp, [rax-1C8h]
0x1800056a7  sub     rsp, 2B0h
0x1800056ae  mov     rax, cs:__security_cookie
0x1800056b5  xor     rax, rsp
0x1800056b8  mov     [rbp+1C0h+var_20], rax
0x1800056bf  mov     r12b, 1
0x1800056c2  xor     edi, edi
0x1800056c4  mov     r13b, dil
0x1800056c7  lea     rsi, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x1800056ce  lea     r15d, [rdi+4]
0x1800056d2  test    r13b, r13b
0x1800056d5  jnz     loc_180005AC2
0x1800056db  and     [rbp+1C0h+var_240], 0
0x1800056e0  mov     [rbp+1C0h+var_240+4], 200h
0x1800056e8  mov     [rbp+1C0h+lpMem], rdi
0x1800056ec  lea     rax, [rbp+1C0h+var_228]
0x1800056f0  mov     [rbp+1C0h+lpMem], rax
0x1800056f4  mov     dword ptr [rbp+1C0h+var_240], 2
0x1800056fb  mov     rax, [rbp+1C0h+lpMem]
0x1800056ff  mov     [rax], di
0x180005702  lea     rcx, [rbp+1C0h+var_240]; this
0x180005706  call    GenerateVersionedFileNameNoThrow
0x18000570b  test    eax, eax
0x18000570d  js      short loc_180005744
0x18000570f  lea     rcx, [rbp+1C0h+var_240]; this
0x180005713  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180005718  mov     rcx, [rbp+1C0h+lpMem]; unsigned __int16 *
0x18000571c  call    ?FileExists@@YAHPEBG@Z; FileExists(ushort const *)
0x180005721  test    eax, eax
0x180005723  jz      short loc_180005744
0x180005725  xor     edx, edx; dwMilliseconds
0x180005727  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x18000572e  call    cs:__imp_WaitForSingleObject
0x180005734  test    eax, eax
0x180005736  jz      short loc_180005744
0x180005738  mov     ecx, 3E8h; unsigned int
0x18000573d  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x180005742  jmp     short loc_18000570F
0x180005744  xor     edx, edx; dwMilliseconds
0x180005746  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hHandle
0x18000574d  call    cs:__imp_WaitForSingleObject
0x180005753  test    eax, eax
0x180005755  jz      short loc_18000576B
0x180005757  lea     rcx, aControllerrunA; "ControllerRun(): About to execute state"...
0x18000575e  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005763  call    ?ExecuteControllerStateMachine@NGENService@@YA_NXZ; NGENService::ExecuteControllerStateMachine(void)
0x180005768  mov     r12b, al
0x18000576b  mov     [rsp+2C0h+var_260], rsi
0x180005770  mov     byte ptr [rsp+2C0h+var_258], dil
0x180005775  mov     rcx, rsi; lpCriticalSection
0x180005778  call    cs:__imp_EnterCriticalSection
0x18000577e  mov     byte ptr [rsp+2C0h+var_258], 1
0x180005783  cmp     cs:?g_InterruptMask@NGENService@@3KA, edi; ulong NGENService::g_InterruptMask
0x180005789  jz      loc_180005A79
0x18000578f  mov     [rsp+2C0h+var_250], rsi
0x180005794  mov     [rsp+2C0h+var_248], dil
0x180005799  mov     rcx, rsi; lpCriticalSection
0x18000579c  call    cs:__imp_EnterCriticalSection
0x1800057a2  mov     [rsp+2C0h+var_248], 1
0x1800057a7  mov     ebx, cs:?m_dwControllerState@ControllerState@NGENService@@1V?$Volatile@K@@A; Volatile<ulong> NGENService::ControllerState::m_dwControllerState
0x1800057ad  mov     rcx, rsi; lpCriticalSection
0x1800057b0  call    cs:__imp_LeaveCriticalSection
0x1800057b6  lea     eax, [rbx-1]
0x1800057b9  test    eax, 0FFFFFFFDh
0x1800057be  setz    al
0x1800057c1  test    al, al
0x1800057c3  jz      loc_180005991
0x1800057c9  mov     dword ptr [rsp+2C0h+var_290], 2
0x1800057d1  mov     esi, 2
0x1800057d6  mov     dword ptr [rsp+2C0h+var_290+4], esi
0x1800057da  lea     ebx, [rsi+0Eh]
0x1800057dd  mov     dword ptr [rsp+2C0h+var_288], ebx
0x1800057e1  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x1800057e8  mov     [rsp+2C0h+var_280], rax
0x1800057ed  mov     r15d, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x1800057f4  mov     dword ptr [rsp+2C0h+Size], esi
0x1800057f8  mov     dword ptr [rsp+2C0h+Size+4], esi
0x1800057fc  mov     dword ptr [rsp+2C0h+var_270], ebx
0x180005800  mov     [rsp+2C0h+Src], rax
0x180005805  lea     rcx, [rsp+2C0h+Size]; this
0x18000580a  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18000580f  nop
0x180005810  test    byte ptr [rsp+2C0h+var_270], bl
0x180005814  jz      short loc_18000583A
0x180005816  mov     eax, dword ptr [rsp+2C0h+Size]
0x18000581a  mov     dword ptr [rsp+2C0h+var_290], eax
0x18000581e  mov     eax, dword ptr [rsp+2C0h+Size+4]
0x180005822  mov     dword ptr [rsp+2C0h+var_290+4], eax
0x180005826  mov     rdi, [rsp+2C0h+Src]
0x18000582b  mov     [rsp+2C0h+var_280], rdi
0x180005830  mov     ebx, dword ptr [rsp+2C0h+var_270]
0x180005834  mov     dword ptr [rsp+2C0h+var_288], ebx
0x180005838  jmp     short loc_18000588E
0x18000583a  mov     edi, dword ptr [rsp+2C0h+Size]
0x18000583e  cmp     edi, 2
0x180005841  jbe     short loc_18000585A
0x180005843  xor     r8d, r8d
0x180005846  mov     edx, edi
0x180005848  lea     rcx, [rsp+2C0h+var_290]
0x18000584d  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180005852  mov     ebx, dword ptr [rsp+2C0h+var_288]
0x180005856  mov     esi, dword ptr [rsp+2C0h+var_290+4]
0x18000585a  mov     dword ptr [rsp+2C0h+var_290], edi
0x18000585e  test    bl, 10h
0x180005861  jz      short loc_180005879
0x180005863  mov     r8d, 1
0x180005869  mov     edx, esi
0x18000586b  lea     rcx, [rsp+2C0h+var_290]
0x180005870  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180005875  mov     ebx, dword ptr [rsp+2C0h+var_288]
0x180005879  mov     r8, rdi; Size
0x18000587c  mov     rdi, [rsp+2C0h+Src]
0x180005881  mov     rdx, rdi; Src
0x180005884  mov     rcx, [rsp+2C0h+var_280]; void *
0x180005889  call    memcpy_0
0x18000588e  mov     eax, dword ptr [rsp+2C0h+var_270]
0x180005892  and     eax, 7
0x180005895  and     ebx, 0FFFFFFF8h
0x180005898  mov     dword ptr [rsp+2C0h+var_288], ebx
0x18000589c  or      ebx, eax
0x18000589e  mov     dword ptr [rsp+2C0h+var_288], ebx
0x1800058a2  btr     ebx, 8
0x1800058a6  mov     dword ptr [rsp+2C0h+var_288], ebx
0x1800058aa  test    byte ptr [rsp+2C0h+var_270], 8
0x1800058af  jz      short loc_1800058B9
0x1800058b1  mov     rcx, rdi; lpMem
0x1800058b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800058b9  mov     dil, 1
0x1800058bc  mov     ebx, 1
0x1800058c1  test    r15d, ebx
0x1800058c4  jz      short loc_180005936
0x1800058c6  cmp     dil, 1
0x1800058ca  jnz     short loc_1800058D1
0x1800058cc  xor     dil, dil
0x1800058cf  jmp     short loc_1800058E2
0x1800058d1  lea     rdx, asc_18004AB08; ", "
0x1800058d8  lea     rcx, [rsp+2C0h+var_290]; this
0x1800058dd  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800058e2  mov     ecx, ebx
0x1800058e4  sub     ecx, 1
0x1800058e7  jz      short loc_180005925
0x1800058e9  sub     ecx, 1
0x1800058ec  jz      short loc_18000591C
0x1800058ee  sub     ecx, 2
0x1800058f1  jz      short loc_180005913
0x1800058f3  sub     ecx, 4
0x1800058f6  jz      short loc_18000590A
0x1800058f8  cmp     ecx, 8
0x1800058fb  jz      short loc_180005901
0x1800058fd  xor     edx, edx
0x1800058ff  jmp     short loc_18000592C
0x180005901  lea     rdx, aServiceworkerI; "SERVICEWORKER_INTERRUPT"
0x180005908  jmp     short loc_18000592C
0x18000590a  lea     rdx, aDirtyRootstore; "DIRTY_ROOTSTORE_INTERRUPT"
0x180005911  jmp     short loc_18000592C
0x180005913  lea     rdx, aUserInterrupt; "USER_INTERRUPT"
0x18000591a  jmp     short loc_18000592C
0x18000591c  lea     rdx, aClientInterrup; "CLIENT_INTERRUPT"
0x180005923  jmp     short loc_18000592C
0x180005925  lea     rdx, aServiceInterru; "SERVICE_INTERRUPT"
0x18000592c  lea     rcx, [rsp+2C0h+var_290]; this
0x180005931  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180005936  add     ebx, ebx
0x180005938  cmp     ebx, 20h ; ' '
0x18000593b  jl      short loc_1800058C1
0x18000593d  lea     rcx, [rsp+2C0h+var_290]; this
0x180005942  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180005947  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x18000594d  mov     dword ptr [rsp+2C0h+var_298], eax
0x180005951  mov     rbx, [rsp+2C0h+var_280]
0x180005956  mov     [rsp+2C0h+var_2A0], rbx; unsigned __int16 *
0x18000595b  lea     r9, aServiceWorkWas; "Service work was interrupted due to the"...
0x180005962  mov     r8d, 454h; unsigned __int16
0x180005968  mov     r15d, 4
0x18000596e  mov     edx, r15d; unsigned __int16 *
0x180005971  xor     ecx, ecx; this
0x180005973  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180005978  nop
0x180005979  test    byte ptr [rsp+2C0h+var_288], 8
0x18000597e  jz      short loc_180005988
0x180005980  mov     rcx, rbx; lpMem
0x180005983  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005988  lea     rsi, ?m_csControllerState@ControllerState@NGENService@@1VCriticalSection@@A; CriticalSection NGENService::ControllerState::m_csControllerState
0x18000598f  xor     edi, edi
0x180005991  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x180005997  test    al, 1
0x180005999  jz      short loc_1800059B9
0x18000599b  lea     rcx, aControllerrunH_2; "ControllerRun(): Handling service inter"...
0x1800059a2  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800059a7  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x1800059ad  and     eax, 0FFFFFFFEh
0x1800059b0  mov     cs:?g_InterruptMask@NGENService@@3KA, eax; ulong NGENService::g_InterruptMask
0x1800059b6  mov     r13b, 1
0x1800059b9  test    r15b, al
0x1800059bc  jz      short loc_1800059D9
0x1800059be  lea     rcx, aControllerrunH_3; "ControllerRun(): Handling user interrup"...
0x1800059c5  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800059ca  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x1800059d0  and     eax, 0FFFFFFFBh
0x1800059d3  mov     cs:?g_InterruptMask@NGENService@@3KA, eax; ulong NGENService::g_InterruptMask
0x1800059d9  test    al, 2
0x1800059db  jz      short loc_1800059F8
0x1800059dd  lea     rcx, aControllerrunH_1; "ControllerRun(): Handling client interr"...
0x1800059e4  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800059e9  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x1800059ef  and     eax, 0FFFFFFFDh
0x1800059f2  mov     cs:?g_InterruptMask@NGENService@@3KA, eax; ulong NGENService::g_InterruptMask
0x1800059f8  test    al, 8
0x1800059fa  jz      short loc_180005A23
0x1800059fc  call    ?ResetDirtyRootStore@NGENService@@YAJXZ; NGENService::ResetDirtyRootStore(void)
0x180005a01  xor     ecx, ecx; unsigned int
0x180005a03  call    ?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z; NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)
0x180005a08  lea     rcx, aControllerrunH_0; "ControllerRun(): Handling dirty rootsto"...
0x180005a0f  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005a14  mov     eax, cs:?g_InterruptMask@NGENService@@3KA; ulong NGENService::g_InterruptMask
0x180005a1a  and     eax, 0FFFFFFF7h
0x180005a1d  mov     cs:?g_InterruptMask@NGENService@@3KA, eax; ulong NGENService::g_InterruptMask
0x180005a23  test    al, 10h
0x180005a25  jz      short loc_180005A3A
0x180005a27  lea     rcx, aControllerrunH; "ControllerRun(): Handling higher priori"...
0x180005a2e  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005a33  and     cs:?g_InterruptMask@NGENService@@3KA, 0FFFFFFEFh; ulong NGENService::g_InterruptMask
0x180005a3a  lea     rcx, aRuncontrollerR; "RunController(): ResetInterrupt()\n"
0x180005a41  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005a46  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hEvent
0x180005a4d  call    cs:__imp_ResetEvent
0x180005a53  mov     rcx, cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA; hEvent
0x180005a5a  call    cs:__imp_SetEvent
0x180005a60  mov     edx, 7; unsigned int
0x180005a65  xor     ecx, ecx; unsigned int
0x180005a67  call    ?Set@ControllerState@NGENService@@SAXKK@Z; NGENService::ControllerState::Set(ulong,ulong)
0x180005a6c  lea     rcx, aControllerrunR; "ControllerRun(): Resuming Listener thre"...
0x180005a73  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180005a78  nop
0x180005a79  mov     rcx, rsi; lpCriticalSection
0x180005a7c  call    cs:__imp_LeaveCriticalSection
0x180005a82  nop
0x180005a83  test    [rbp+1C0h+var_238], 8
0x180005a87  jz      short loc_180005AB9
0x180005a89  mov     rbx, [rbp+1C0h+lpMem]
0x180005a8d  test    rbx, rbx
0x180005a90  jz      short loc_180005AB9
0x180005a92  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180005a99  test    rax, rax
0x180005a9c  jnz     short loc_180005AAB
0x180005a9e  call    cs:__imp_GetProcessHeap
0x180005aa4  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180005aab  mov     r8, rbx; lpMem
0x180005aae  xor     edx, edx; dwFlags
0x180005ab0  mov     rcx, rax; hHeap
0x180005ab3  call    cs:__imp_HeapFree
0x180005ab9  test    r12b, r12b
0x180005abc  jnz     loc_1800056D2
0x180005ac2  mov     al, r12b
0x180005ac5  mov     rcx, [rbp+1C0h+var_20]
0x180005acc  xor     rcx, rsp; StackCookie
0x180005acf  call    __security_check_cookie
0x180005ad4  lea     r11, [rsp+2C0h+var_10]
0x180005adc  mov     rbx, [r11+20h]
0x180005ae0  mov     rsi, [r11+28h]
0x180005ae4  mov     rdi, [r11+30h]
0x180005ae8  mov     r12, [r11+38h]
0x180005aec  mov     rsp, r11
0x180005aef  pop     r15
0x180005af1  pop     r13
0x180005af3  pop     rbp
0x180005af4  retn
```
