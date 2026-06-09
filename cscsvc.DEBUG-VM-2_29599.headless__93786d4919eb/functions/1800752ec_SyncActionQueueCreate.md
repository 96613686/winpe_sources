# SyncActionQueueCreate

- ea: `0x1800752ec`
- end: `0x18007555b`
- name: `SyncActionQueueCreate`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180020514`

## callees

- `0x180004c40`
- `0x180020ef0`
- `0x1800360c0`
- `0x180036394`
- `0x18004ff34`
- `0x1800752ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800754c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800754e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800754c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800754e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075424`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180075413`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180075413`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800753cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800753cf`

## string_xrefs

- `0x180075328`: `SyncActionQueueCreate: Queue: 0x%p DispatchVector: 0x%p`
- `0x18007537f`: `SyncActionQueueCreate: 0x%x`
- `0x180075458`: `SyncActionQueueCreate: 0x%x`
- `0x180075482`: `SyncActionQueueCreate: 0x%x`
- `0x180075520`: `SyncActionQueueCreate: 0x%x`
- `0x1800754ca`: `SyncActionQueueCreate: CreateEvent failed with %d`

## pseudocode

```c
__int64 __fastcall SyncActionQueueCreate(__int64 *a1)
{
  __int64 v2; // rax
  _DWORD *v4; // rbx
  __int64 v5; // rdx
  DWORD LastError; // eax
  __int64 v7; // rbx
  DWORD v8; // eax

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionQueueCreate: Queue: 0x%p DispatchVector: 0x%p", a1, DefaultActionDispatchVector);
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      10,
      WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids,
      a1,
      DefaultActionDispatchVector);
  }
  v2 = SyncAlloc(88);
  *a1 = v2;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncActionQueueCreate: 0x%x", 3221225626LL);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids, 3221225626LL);
    }
    return 3221225626LL;
  }
  *(_DWORD *)(v2 + 16) = 0;
  *(_DWORD *)*a1 = 0;
  v4 = (_DWORD *)*a1;
  *((_QWORD *)v4 + 1) = CreateEventW(0, 1, 1, 0);
  if ( (unsigned __int64)(*(_QWORD *)(*a1 + 8) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      LastError = GetLastError();
      SyncTraceOutputInternal(L"SyncActionQueueCreate: CreateEvent failed with %d", LastError);
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 12);
      v8 = GetLastError();
      WPP_SF_d(v7, 12, WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids, v8);
    }
    SyncFree(*a1);
    *a1 = 0;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) == 0 )
      return 3221225473LL;
    SyncTraceOutputInternal(L"SyncActionQueueCreate: 0x%x", 3221225473LL);
    v5 = 13;
    goto LABEL_24;
  }
  *(_QWORD *)(*a1 + 72) = 0;
  *(_QWORD *)(*a1 + 80) = 0;
  *(_QWORD *)(*a1 + 64) = DefaultActionDispatchVector;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(*a1 + 24), 0x80000400) )
  {
    CloseHandle(*(HANDLE *)(*a1 + 8));
    SyncFree(*a1);
    *a1 = 0;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) == 0 )
      return 3221225473LL;
    SyncTraceOutputInternal(L"SyncActionQueueCreate: 0x%x", 3221225473LL);
    v5 = 14;
LABEL_24:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v5, WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids, 3221225473LL);
    return 3221225473LL;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionQueueCreate: 0x%x", 0);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800752ec  push    rbx
0x1800752ee  push    rsi
0x1800752ef  push    rdi
0x1800752f0  push    r12
0x1800752f2  push    r14
0x1800752f4  sub     rsp, 30h
0x1800752f8  mov     rdi, rcx
0x1800752fb  mov     rax, cs:WPP_GLOBAL_Control
0x180075302  lea     rsi, WPP_GLOBAL_Control
0x180075309  lea     r12, DefaultActionDispatchVector
0x180075310  lea     r14, WPP_e13eed5a073b34eb1370c08c679d6422_Traceguids
0x180075317  cmp     rax, rsi
0x18007531a  jz      short loc_180075354
0x18007531c  test    byte ptr [rax+6Ch], 4
0x180075320  jz      short loc_180075354
0x180075322  mov     rdx, rcx
0x180075325  mov     r8, r12
0x180075328  lea     rcx, aSyncactionqueu; "SyncActionQueueCreate: Queue: 0x%p Disp"...
0x18007532f  call    SyncTraceOutputInternal
0x180075334  mov     rcx, cs:WPP_GLOBAL_Control
0x18007533b  mov     edx, 0Ah
0x180075340  mov     r9, rdi
0x180075343  mov     [rsp+58h+var_38], r12
0x180075348  mov     r8, r14
0x18007534b  mov     rcx, [rcx+60h]
0x18007534f  call    WPP_SF_qq
0x180075354  mov     ecx, 58h ; 'X'
0x180075359  call    SyncAlloc
0x18007535e  mov     [rdi], rax
0x180075361  test    rax, rax
0x180075364  jnz     short loc_1800753B0
0x180075366  mov     rax, cs:WPP_GLOBAL_Control
0x18007536d  mov     ebx, 0C000009Ah
0x180075372  cmp     rax, rsi
0x180075375  jz      short loc_1800753A9
0x180075377  test    byte ptr [rax+6Ch], 8
0x18007537b  jz      short loc_1800753A9
0x18007537d  mov     edx, ebx
0x18007537f  lea     rcx, aSyncactionqueu_17; "SyncActionQueueCreate: 0x%x"
0x180075386  call    SyncTraceOutputInternal
0x18007538b  mov     rcx, cs:WPP_GLOBAL_Control
0x180075392  mov     edx, 0Bh
0x180075397  mov     r9d, 0C000009Ah
0x18007539d  mov     r8, r14
0x1800753a0  mov     rcx, [rcx+60h]
0x1800753a4  call    WPP_SF_d
0x1800753a9  mov     eax, ebx
0x1800753ab  jmp     loc_18007554F
0x1800753b0  mov     dword ptr [rax+10h], 0
0x1800753b7  xor     r9d, r9d; lpName
0x1800753ba  mov     rax, [rdi]
0x1800753bd  xor     ecx, ecx; lpEventAttributes
0x1800753bf  lea     edx, [r9+1]; bManualReset
0x1800753c3  mov     dword ptr [rax], 0
0x1800753c9  mov     r8d, edx; bInitialState
0x1800753cc  mov     rbx, [rdi]
0x1800753cf  call    cs:__imp_CreateEventW
0x1800753d5  mov     [rbx+8], rax
0x1800753d9  mov     rcx, [rdi]
0x1800753dc  mov     rax, [rcx+8]
0x1800753e0  dec     rax
0x1800753e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800753e7  ja      loc_1800754B0
0x1800753ed  mov     qword ptr [rcx+48h], 0
0x1800753f5  mov     edx, 80000400h; dwSpinCount
0x1800753fa  mov     rax, [rdi]
0x1800753fd  mov     qword ptr [rax+50h], 0
0x180075405  mov     rax, [rdi]
0x180075408  mov     [rax+40h], r12
0x18007540c  mov     rcx, [rdi]
0x18007540f  add     rcx, 18h; lpCriticalSection
0x180075413  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180075419  test    eax, eax
0x18007541b  jnz     short loc_18007546E
0x18007541d  mov     rcx, [rdi]
0x180075420  mov     rcx, [rcx+8]; hObject
0x180075424  call    cs:__imp_CloseHandle
0x18007542a  mov     rcx, [rdi]
0x18007542d  call    SyncFree
0x180075432  mov     qword ptr [rdi], 0
0x180075439  mov     rax, cs:WPP_GLOBAL_Control
0x180075440  cmp     rax, rsi
0x180075443  jz      loc_18007554A
0x180075449  test    byte ptr [rax+6Ch], 8
0x18007544d  jz      loc_18007554A
0x180075453  mov     edx, 0C0000001h
0x180075458  lea     rcx, aSyncactionqueu_17; "SyncActionQueueCreate: 0x%x"
0x18007545f  call    SyncTraceOutputInternal
0x180075464  mov     edx, 0Eh
0x180075469  jmp     loc_180075531
0x18007546e  mov     rax, cs:WPP_GLOBAL_Control
0x180075475  cmp     rax, rsi
0x180075478  jz      short loc_1800754A9
0x18007547a  test    byte ptr [rax+6Ch], 8
0x18007547e  jz      short loc_1800754A9
0x180075480  xor     edx, edx
0x180075482  lea     rcx, aSyncactionqueu_17; "SyncActionQueueCreate: 0x%x"
0x180075489  call    SyncTraceOutputInternal
0x18007548e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075495  mov     edx, 0Fh
0x18007549a  xor     r9d, r9d
0x18007549d  mov     r8, r14
0x1800754a0  mov     rcx, [rcx+60h]
0x1800754a4  call    WPP_SF_d
0x1800754a9  xor     eax, eax
0x1800754ab  jmp     loc_18007554F
0x1800754b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800754b7  cmp     rax, rsi
0x1800754ba  jz      short loc_1800754FA
0x1800754bc  test    byte ptr [rax+6Ch], 1
0x1800754c0  jz      short loc_1800754FA
0x1800754c2  call    cs:__imp_GetLastError
0x1800754c8  mov     edx, eax
0x1800754ca  lea     rcx, aSyncactionqueu_27; "SyncActionQueueCreate: CreateEvent fail"...
0x1800754d1  call    SyncTraceOutputInternal
0x1800754d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800754dd  mov     rbx, [rax+60h]
0x1800754e1  call    cs:__imp_GetLastError
0x1800754e7  mov     edx, 0Ch
0x1800754ec  mov     r8, r14
0x1800754ef  mov     r9d, eax
0x1800754f2  mov     rcx, rbx
0x1800754f5  call    WPP_SF_d
0x1800754fa  mov     rcx, [rdi]
0x1800754fd  call    SyncFree
0x180075502  mov     qword ptr [rdi], 0
0x180075509  mov     rax, cs:WPP_GLOBAL_Control
0x180075510  cmp     rax, rsi
0x180075513  jz      short loc_18007554A
0x180075515  test    byte ptr [rax+6Ch], 8
0x180075519  jz      short loc_18007554A
0x18007551b  mov     edx, 0C0000001h
0x180075520  lea     rcx, aSyncactionqueu_17; "SyncActionQueueCreate: 0x%x"
0x180075527  call    SyncTraceOutputInternal
0x18007552c  mov     edx, 0Dh
0x180075531  mov     rcx, cs:WPP_GLOBAL_Control
0x180075538  mov     r9d, 0C0000001h
0x18007553e  mov     r8, r14
0x180075541  mov     rcx, [rcx+60h]
0x180075545  call    WPP_SF_d
0x18007554a  mov     eax, 0C0000001h
0x18007554f  add     rsp, 30h
0x180075553  pop     r14
0x180075555  pop     r12
0x180075557  pop     rdi
0x180075558  pop     rsi
0x180075559  pop     rbx
0x18007555a  retn
```
