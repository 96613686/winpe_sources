# UMRxSubmitAsyncEngUserModeRequest

- ea: `0x1400287f4`
- end: `0x140028aeb`
- name: `UMRxSubmitAsyncEngUserModeRequest`
- size: `759`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `14`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140003b10`
- `0x140005490`
- `0x1400115f0`
- `0x1400128a0`
- `0x1400130e0`
- `0x1400191b0`
- `0x140019890`
- `0x14001ae20`
- `0x14001b250`
- `0x14001fa70`
- `0x140022860`
- `0x140022970`
- `0x1400233a0`
- `0x140023bb0`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400273f0`
- `0x140027658`
- `0x1400286f0`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x1400288e1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400288e1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028984`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028984`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002885a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028896`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028949`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400289dc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028a3d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028aa9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002885a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028896`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028949`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400289dc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028a3d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028aa9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028a7a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140028a7a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140028990`
- `ntoskrnl!IoGetCurrentProcess` at `0x140028990`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140028910`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140028910`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140028974`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140028974`
- `ntoskrnl!SeLockSubjectContext` at `0x1400288f1`
- `ntoskrnl!SeLockSubjectContext` at `0x1400288f1`

## pseudocode

```c
__int64 __fastcall UMRxSubmitAsyncEngUserModeRequest(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  char v4; // r14
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v14; // edi
  __int64 v15; // rbx
  HANDLE v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rbx
  HANDLE v24; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+90h] [rbp+40h] BYREF
  struct _LUID AuthenticationId; // [rsp+A0h] [rbp+50h] BYREF

  v27 = a1;
  v4 = *(_BYTE *)(a1 + 208) & 1;
  AuthenticationId = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 24, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqq(v11, 25, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12, a1, a2);
    }
  }
  *(_QWORD *)(a1 + 376) = a3;
  *(_QWORD *)(a1 + 384) = a4;
  if ( v4 )
    *(_DWORD *)(a1 + 52) = 1;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v14 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      WPP_SF_qD(v15, 26, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v16, v14);
    }
  }
  else
  {
    *(struct _LUID *)(a1 + 96) = AuthenticationId;
  }
  SeUnlockSubjectContext(&SubjectContext);
  SeReleaseSubjectContext(&SubjectContext);
  *(_QWORD *)(a1 + 104) = IoGetCurrentProcess();
  *(_QWORD *)(a1 + 112) = KeGetCurrentThread();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  v17 = UMRxEnqueueUserModeCallUp(a1, a2);
  if ( v17 == 259 )
  {
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v17;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v21 = PsGetCurrentThreadId();
        WPP_SF_q(v20, 28, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v21);
      }
    }
    else
    {
      KeWaitForSingleObject((PVOID)(a1 + 448), Executive, 0, 0, 0);
      UMRxResumeAsyncEngineContext(a2);
      v17 = v22;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v24 = PsGetCurrentThreadId();
      WPP_SF_qD(v23, 29, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v24, v17);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      WPP_SF_qD(v18, 27, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v19, v17);
    }
    UMRxFinalizeAsyncEngineContext(&v27);
    *(_DWORD *)(v27 + 128) = v17;
  }
  return v17;
}

```

## disassembly

```asm
0x1400287f4  mov     [rsp-38h+arg_8], rbx
0x1400287f9  mov     [rsp-38h+arg_0], rcx
0x1400287fe  push    rbp
0x1400287ff  push    rsi
0x140028800  push    rdi
0x140028801  push    r12
0x140028803  push    r13
0x140028805  push    r14
0x140028807  push    r15
0x140028809  mov     rbp, rsp
0x14002880c  sub     rsp, 50h
0x140028810  mov     r14b, [rcx+0D0h]
0x140028817  xorps   xmm0, xmm0
0x14002881a  and     r14b, 1
0x14002881e  mov     qword ptr [rbp+AuthenticationId.LowPart], 0
0x140028826  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14002882a  mov     rdi, r9
0x14002882d  mov     r15, r8
0x140028830  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140028834  mov     r12, rdx
0x140028837  mov     rsi, rcx
0x14002883a  mov     rbx, cs:WPP_GLOBAL_Control
0x140028841  lea     r13, WPP_GLOBAL_Control
0x140028848  cmp     rbx, r13
0x14002884b  jz      short loc_1400288C3
0x14002884d  test    dword ptr [rbx+2Ch], 800h
0x140028854  jz      short loc_14002887D
0x140028856  mov     rbx, [rbx+18h]
0x14002885a  call    cs:__imp_PsGetCurrentThreadId
0x140028861  nop     dword ptr [rax+rax+00h]
0x140028866  mov     edx, 18h
0x14002886b  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028872  mov     r9, rax
0x140028875  mov     rcx, rbx
0x140028878  call    WPP_SF_q
0x14002887d  mov     rbx, cs:WPP_GLOBAL_Control
0x140028884  cmp     rbx, r13
0x140028887  jz      short loc_1400288C3
0x140028889  test    dword ptr [rbx+2Ch], 200h
0x140028890  jz      short loc_1400288C3
0x140028892  mov     rbx, [rbx+18h]
0x140028896  call    cs:__imp_PsGetCurrentThreadId
0x14002889d  nop     dword ptr [rax+rax+00h]
0x1400288a2  mov     edx, 19h
0x1400288a7  mov     [rsp+50h+var_28], r12
0x1400288ac  mov     r9, rax
0x1400288af  mov     [rsp+50h+Timeout], rsi
0x1400288b4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400288bb  mov     rcx, rbx
0x1400288be  call    WPP_SF_qqq
0x1400288c3  mov     [rsi+178h], r15
0x1400288ca  mov     [rsi+180h], rdi
0x1400288d1  test    r14b, r14b
0x1400288d4  jz      short loc_1400288DD
0x1400288d6  mov     dword ptr [rsi+34h], 1
0x1400288dd  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400288e1  call    cs:__imp_SeCaptureSubjectContext
0x1400288e8  nop     dword ptr [rax+rax+00h]
0x1400288ed  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400288f1  call    cs:__imp_SeLockSubjectContext
0x1400288f8  nop     dword ptr [rax+rax+00h]
0x1400288fd  mov     rax, [rbp+SubjectContext.ClientToken]
0x140028901  lea     rdx, [rbp+AuthenticationId]; AuthenticationId
0x140028905  mov     rcx, [rbp+SubjectContext.PrimaryToken]
0x140028909  test    rax, rax
0x14002890c  cmovnz  rcx, rax; Token
0x140028910  call    cs:__imp_SeQueryAuthenticationIdToken
0x140028917  nop     dword ptr [rax+rax+00h]
0x14002891c  mov     edi, eax
0x14002891e  test    eax, eax
0x140028920  jnz     short loc_140028930
0x140028922  mov     eax, [rbp+AuthenticationId.HighPart]
0x140028925  mov     [rsi+64h], eax
0x140028928  mov     eax, [rbp+AuthenticationId.LowPart]
0x14002892b  mov     [rsi+60h], eax
0x14002892e  jmp     short loc_140028970
0x140028930  mov     rbx, cs:WPP_GLOBAL_Control
0x140028937  cmp     rbx, r13
0x14002893a  jz      short loc_140028970
0x14002893c  test    dword ptr [rbx+2Ch], 200h
0x140028943  jz      short loc_140028970
0x140028945  mov     rbx, [rbx+18h]
0x140028949  call    cs:__imp_PsGetCurrentThreadId
0x140028950  nop     dword ptr [rax+rax+00h]
0x140028955  mov     edx, 1Ah
0x14002895a  mov     dword ptr [rsp+50h+Timeout], edi
0x14002895e  mov     r9, rax
0x140028961  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028968  mov     rcx, rbx
0x14002896b  call    WPP_SF_qD
0x140028970  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140028974  call    cs:__imp_SeUnlockSubjectContext
0x14002897b  nop     dword ptr [rax+rax+00h]
0x140028980  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140028984  call    cs:__imp_SeReleaseSubjectContext
0x14002898b  nop     dword ptr [rax+rax+00h]
0x140028990  call    cs:__imp_IoGetCurrentProcess
0x140028997  nop     dword ptr [rax+rax+00h]
0x14002899c  mov     [rsi+68h], rax
0x1400289a0  mov     rax, gs:188h
0x1400289a9  mov     [rsi+70h], rax
0x1400289ad  lock inc dword ptr [rsi+4]
0x1400289b1  mov     rdx, r12
0x1400289b4  mov     rcx, rsi
0x1400289b7  call    UMRxEnqueueUserModeCallUp
0x1400289bc  mov     edi, eax
0x1400289be  cmp     eax, 103h
0x1400289c3  jz      short loc_140028A1B
0x1400289c5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400289cc  cmp     rbx, r13
0x1400289cf  jz      short loc_140028A03
0x1400289d1  mov     ecx, [rbx+2Ch]
0x1400289d4  test    cl, cl
0x1400289d6  jns     short loc_140028A03
0x1400289d8  mov     rbx, [rbx+18h]
0x1400289dc  call    cs:__imp_PsGetCurrentThreadId
0x1400289e3  nop     dword ptr [rax+rax+00h]
0x1400289e8  mov     edx, 1Bh
0x1400289ed  mov     dword ptr [rsp+50h+Timeout], edi
0x1400289f1  mov     r9, rax
0x1400289f4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400289fb  mov     rcx, rbx
0x1400289fe  call    WPP_SF_qD
0x140028a03  lea     rcx, [rbp+arg_0]
0x140028a07  call    UMRxFinalizeAsyncEngineContext
0x140028a0c  mov     rax, [rbp+arg_0]
0x140028a10  mov     [rax+80h], edi
0x140028a16  jmp     loc_140028AD0
0x140028a1b  test    r14b, r14b
0x140028a1e  jz      short loc_140028A62
0x140028a20  mov     rbx, cs:WPP_GLOBAL_Control
0x140028a27  cmp     rbx, r13
0x140028a2a  jz      loc_140028AD0
0x140028a30  test    dword ptr [rbx+2Ch], 400h
0x140028a37  jz      short loc_140028A90
0x140028a39  mov     rbx, [rbx+18h]
0x140028a3d  call    cs:__imp_PsGetCurrentThreadId
0x140028a44  nop     dword ptr [rax+rax+00h]
0x140028a49  mov     edx, 1Ch
0x140028a4e  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028a55  mov     r9, rax
0x140028a58  mov     rcx, rbx
0x140028a5b  call    WPP_SF_q
0x140028a60  jmp     short loc_140028A90
0x140028a62  lea     rcx, [rsi+1C0h]; Object
0x140028a69  mov     [rsp+50h+Timeout], 0; Timeout
0x140028a72  xor     r9d, r9d; Alertable
0x140028a75  xor     r8d, r8d; WaitMode
0x140028a78  xor     edx, edx; WaitReason
0x140028a7a  call    cs:__imp_KeWaitForSingleObject
0x140028a81  nop     dword ptr [rax+rax+00h]
0x140028a86  mov     rcx, r12; Context
0x140028a89  call    UMRxResumeAsyncEngineContext
0x140028a8e  mov     edi, eax
0x140028a90  mov     rbx, cs:WPP_GLOBAL_Control
0x140028a97  cmp     rbx, r13
0x140028a9a  jz      short loc_140028AD0
0x140028a9c  test    dword ptr [rbx+2Ch], 800h
0x140028aa3  jz      short loc_140028AD0
0x140028aa5  mov     rbx, [rbx+18h]
0x140028aa9  call    cs:__imp_PsGetCurrentThreadId
0x140028ab0  nop     dword ptr [rax+rax+00h]
0x140028ab5  mov     edx, 1Dh
0x140028aba  mov     dword ptr [rsp+50h+Timeout], edi
0x140028abe  mov     r9, rax
0x140028ac1  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028ac8  mov     rcx, rbx
0x140028acb  call    WPP_SF_qD
0x140028ad0  mov     rbx, [rsp+50h+arg_8]
0x140028ad8  mov     eax, edi
0x140028ada  add     rsp, 50h
0x140028ade  pop     r15
0x140028ae0  pop     r14
0x140028ae2  pop     r13
0x140028ae4  pop     r12
0x140028ae6  pop     rdi
0x140028ae7  pop     rsi
0x140028ae8  pop     rbp
0x140028ae9  retn
```
