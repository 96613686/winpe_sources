# NcaServiceAsyncStartupRoutine(void *)

- ea: `0x180004400`
- end: `0x180004677`
- name: `?NcaServiceAsyncStartupRoutine@@YAKPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800024b0`
- `0x1800033bc`
- `0x180004400`
- `0x180004680`
- `0x180004cec`
- `0x180004f04`
- `0x180019784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004590`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004449`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004449`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045b3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004618`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045b3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800045c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004618`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000454e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000454e`

## string_xrefs

- `0x180004491`: `NcaServiceAsyncStartupRoutine`

## pseudocode

```c
__int64 __fastcall NcaServiceAsyncStartupRoutine(PVOID Parameter)
{
  int v1; // edi
  int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  PVOID *v5; // rcx
  __int64 v6; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  _InterlockedIncrement(&dword_180028AE8);
  ResetEvent(qword_180028AD8);
  v1 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  v2 = NcaComponentsInitialize(4, &off_18001F170);
  v3 = v2;
  if ( v2 < 0 )
    goto LABEL_8;
  byte_180028B6D = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  ServiceStatus.dwControlsAccepted = 1025;
  v2 = NcaServiceChangeState(4u);
  v3 = v2;
  if ( v2 < 0 )
    goto LABEL_8;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_(v4[2], 14, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  }
  v2 = NcaComponentsInitialize(22, off_18001F010);
  v3 = v2;
  if ( v2 < 0 )
  {
LABEL_8:
    NcaReportReturnError("NcaServiceAsyncStartupRoutine", (unsigned int)v2);
  }
  else
  {
    EnterCriticalSection(&stru_180028AF0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    byte_180028B6E = 1;
    v1 = 1;
    LeaveCriticalSection(&stru_180028AF0);
  }
  if ( _InterlockedExchangeAdd(&dword_180028AE8, 0xFFFFFFFF) == 1 )
    SetEvent(hHandle);
  SetEvent(qword_180028AD8);
  if ( (v3 & 0x80000000) != 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = NcaHResultToWindowsError(v3);
    v3 = NcaServiceSetStatus();
  }
  if ( !v1 )
  {
    SetEvent(hEvent);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_36;
    v6 = 17;
    goto LABEL_35;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = 16;
LABEL_35:
    WPP_SF_(v5[2], v6, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_(v5[2], 18, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x180004400  push    rbx
0x180004402  push    rsi
0x180004403  push    rdi
0x180004404  push    r14
0x180004406  sub     rsp, 28h
0x18000440a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004411  lea     rsi, WPP_GLOBAL_Control
0x180004418  lea     r14, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x18000441f  cmp     rcx, rsi
0x180004422  jz      short loc_18000443B
0x180004424  test    byte ptr [rcx+1Ch], 8
0x180004428  jz      short loc_18000443B
0x18000442a  mov     rcx, [rcx+10h]
0x18000442e  mov     edx, 0Ah
0x180004433  mov     r8, r14
0x180004436  call    WPP_SF_
0x18000443b  lock inc cs:dword_180028AE8
0x180004442  mov     rcx, cs:qword_180028AD8; hEvent
0x180004449  call    cs:__imp_ResetEvent
0x180004450  nop     dword ptr [rax+rax+00h]
0x180004455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000445c  xor     edi, edi
0x18000445e  cmp     rcx, rsi
0x180004461  jz      short loc_180004478
0x180004463  test    byte ptr [rcx+1Ch], 4
0x180004467  jz      short loc_180004478
0x180004469  mov     rcx, [rcx+10h]
0x18000446d  lea     edx, [rdi+0Bh]
0x180004470  mov     r8, r14
0x180004473  call    WPP_SF_
0x180004478  lea     rdx, off_18001F170
0x18000447f  mov     ecx, 4
0x180004484  call    NcaComponentsInitialize
0x180004489  mov     ebx, eax
0x18000448b  test    eax, eax
0x18000448d  jns     short loc_1800044A2
0x18000448f  mov     edx, eax
0x180004491  lea     rcx, aNcaserviceasyn; "NcaServiceAsyncStartupRoutine"
0x180004498  call    NcaReportReturnError
0x18000449d  jmp     loc_18000459C
0x1800044a2  mov     cs:byte_180028B6D, 1
0x1800044a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b0  cmp     rcx, rsi
0x1800044b3  jz      short loc_1800044CC
0x1800044b5  test    byte ptr [rcx+1Ch], 4
0x1800044b9  jz      short loc_1800044CC
0x1800044bb  mov     rcx, [rcx+10h]
0x1800044bf  mov     edx, 0Ch
0x1800044c4  mov     r8, r14
0x1800044c7  call    WPP_SF_
0x1800044cc  mov     ecx, 4; unsigned int
0x1800044d1  mov     cs:ServiceStatus.dwControlsAccepted, 401h
0x1800044db  call    ?NcaServiceChangeState@@YAJK@Z; NcaServiceChangeState(ulong)
0x1800044e0  mov     ebx, eax
0x1800044e2  test    eax, eax
0x1800044e4  js      short loc_18000448F
0x1800044e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044ed  cmp     rcx, rsi
0x1800044f0  jz      short loc_18000452C
0x1800044f2  test    byte ptr [rcx+1Ch], 4
0x1800044f6  jz      short loc_180004510
0x1800044f8  mov     rcx, [rcx+10h]
0x1800044fc  mov     edx, 0Dh
0x180004501  mov     r8, r14
0x180004504  call    WPP_SF_
0x180004509  mov     rcx, cs:WPP_GLOBAL_Control
0x180004510  cmp     rcx, rsi
0x180004513  jz      short loc_18000452C
0x180004515  test    byte ptr [rcx+1Ch], 4
0x180004519  jz      short loc_18000452C
0x18000451b  mov     rcx, [rcx+10h]
0x18000451f  mov     edx, 0Eh
0x180004524  mov     r8, r14
0x180004527  call    WPP_SF_
0x18000452c  lea     rdx, off_18001F010
0x180004533  mov     ecx, 16h
0x180004538  call    NcaComponentsInitialize
0x18000453d  mov     ebx, eax
0x18000453f  test    eax, eax
0x180004541  js      loc_18000448F
0x180004547  lea     rcx, stru_180028AF0; lpCriticalSection
0x18000454e  call    cs:__imp_EnterCriticalSection
0x180004555  nop     dword ptr [rax+rax+00h]
0x18000455a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004561  cmp     rcx, rsi
0x180004564  jz      short loc_18000457D
0x180004566  test    byte ptr [rcx+1Ch], 4
0x18000456a  jz      short loc_18000457D
0x18000456c  mov     rcx, [rcx+10h]
0x180004570  mov     edx, 0Fh
0x180004575  mov     r8, r14
0x180004578  call    WPP_SF_
0x18000457d  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004584  mov     cs:byte_180028B6E, 1
0x18000458b  mov     edi, 1
0x180004590  call    cs:__imp_LeaveCriticalSection
0x180004597  nop     dword ptr [rax+rax+00h]
0x18000459c  or      eax, 0FFFFFFFFh
0x18000459f  lock xadd cs:dword_180028AE8, eax
0x1800045a7  cmp     eax, 1
0x1800045aa  jnz     short loc_1800045BF
0x1800045ac  mov     rcx, cs:hHandle; hEvent
0x1800045b3  call    cs:__imp_SetEvent
0x1800045ba  nop     dword ptr [rax+rax+00h]
0x1800045bf  mov     rcx, cs:qword_180028AD8; hEvent
0x1800045c6  call    cs:__imp_SetEvent
0x1800045cd  nop     dword ptr [rax+rax+00h]
0x1800045d2  test    ebx, ebx
0x1800045d4  jns     short loc_1800045F4
0x1800045d6  mov     ecx, ebx
0x1800045d8  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x1800045e2  call    NcaHResultToWindowsError
0x1800045e7  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x1800045ed  call    ?NcaServiceSetStatus@@YAJXZ; NcaServiceSetStatus(void)
0x1800045f2  mov     ebx, eax
0x1800045f4  test    edi, edi
0x1800045f6  jz      short loc_180004611
0x1800045f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045ff  cmp     rcx, rsi
0x180004602  jz      short loc_18000466A
0x180004604  test    byte ptr [rcx+1Ch], 4
0x180004608  jz      short loc_18000464E
0x18000460a  mov     edx, 10h
0x18000460f  jmp     short loc_18000463B
0x180004611  mov     rcx, cs:hEvent; hEvent
0x180004618  call    cs:__imp_SetEvent
0x18000461f  nop     dword ptr [rax+rax+00h]
0x180004624  mov     rcx, cs:WPP_GLOBAL_Control
0x18000462b  cmp     rcx, rsi
0x18000462e  jz      short loc_18000466A
0x180004630  test    byte ptr [rcx+1Ch], 4
0x180004634  jz      short loc_18000464E
0x180004636  mov     edx, 11h
0x18000463b  mov     rcx, [rcx+10h]
0x18000463f  mov     r8, r14
0x180004642  call    WPP_SF_
0x180004647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000464e  cmp     rcx, rsi
0x180004651  jz      short loc_18000466A
0x180004653  test    byte ptr [rcx+1Ch], 8
0x180004657  jz      short loc_18000466A
0x180004659  mov     rcx, [rcx+10h]
0x18000465d  mov     edx, 12h
0x180004662  mov     r8, r14
0x180004665  call    WPP_SF_
0x18000466a  mov     eax, ebx
0x18000466c  add     rsp, 28h
0x180004670  pop     r14
0x180004672  pop     rdi
0x180004673  pop     rsi
0x180004674  pop     rbx
0x180004675  retn
```
