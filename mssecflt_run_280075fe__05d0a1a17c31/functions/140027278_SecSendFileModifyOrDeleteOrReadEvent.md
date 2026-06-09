# SecSendFileModifyOrDeleteOrReadEvent

- ea: `0x140027278`
- end: `0x1400275b1`
- name: `SecSendFileModifyOrDeleteOrReadEvent`
- size: `825`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400271b0`
- `0x140027214`
- `0x1400278c8`

## callees

- `0x140005f34`
- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x14000add8`
- `0x140010080`
- `0x140011650`
- `0x1400260b8`
- `0x140027278`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x140027301`
- `ntoskrnl!IoThreadToProcess` at `0x140027301`
- `ntoskrnl!PsGetThreadId` at `0x1400273a3`
- `ntoskrnl!PsGetThreadId` at `0x140027488`
- `ntoskrnl!PsGetThreadId` at `0x1400273a3`
- `ntoskrnl!PsGetThreadId` at `0x140027488`
- `ntoskrnl!PsGetProcessId` at `0x1400273b5`
- `ntoskrnl!PsGetProcessId` at `0x14002749a`
- `ntoskrnl!PsGetProcessId` at `0x1400273b5`
- `ntoskrnl!PsGetProcessId` at `0x14002749a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400273e1`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400274bd`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400273e1`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400274bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027576`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027576`

## pseudocode

```c
void __fastcall SecSendFileModifyOrDeleteOrReadEvent(
        __int64 a1,
        __int64 a2,
        struct _KTHREAD *a3,
        __int64 a4,
        const EVENT_DESCRIPTOR *EventDescriptor,
        char a6,
        void *a7,
        int a8,
        wchar_t *a9,
        __int64 a10)
{
  struct _KTHREAD *CurrentThread; // r12
  struct _KPROCESS *RequestorProcess; // rax
  struct _KPROCESS *v13; // r13
  __int64 v14; // r8
  int v15; // ecx
  int ThreadId; // r15d
  unsigned int ProcessId; // eax
  volatile signed __int64 *v18; // rbx
  int v19; // r14d
  char ProcessSessionId_0; // di
  int TimeQuadPart; // eax
  int v22; // ecx
  unsigned int v23; // eax
  PSID v24; // r15
  int v25; // r14d
  unsigned int v26; // eax
  volatile signed __int64 *v27; // rbx
  int v28; // esi
  char v29; // di
  int v30; // eax
  int v31; // ecx
  unsigned int v32; // eax
  int v33; // [rsp+80h] [rbp-59h]
  PSID Sid; // [rsp+88h] [rbp-51h]
  PVOID v35; // [rsp+A8h] [rbp-31h] BYREF
  PVOID P; // [rsp+B0h] [rbp-29h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+B8h] [rbp-21h] BYREF
  _BYTE v38[8]; // [rsp+C0h] [rbp-19h] BYREF
  char v39[8]; // [rsp+C8h] [rbp-11h]

  CurrentThread = a3;
  P = 0;
  ListEntry = 0;
  v35 = 0;
  v38[0] = 0;
  *(_QWORD *)v39 = 0;
  if ( a3 || (CurrentThread = *(struct _KTHREAD **)(a1 + 8)) != 0 )
  {
    RequestorProcess = IoThreadToProcess(CurrentThread);
  }
  else
  {
    CurrentThread = KeGetCurrentThread();
    RequestorProcess = (struct _KPROCESS *)SecFltGetRequestorProcess();
  }
  v13 = RequestorProcess;
  if ( (int)SecGetProcessStartKey(RequestorProcess) < 0 )
    goto LABEL_28;
  _mm_lfence();
  LOBYTE(v14) = 1;
  SecGetProcessContextWithAssertions(v13, &ListEntry, v14);
  if ( a7 )
  {
    v35 = a7;
  }
  else
  {
    _mm_lfence();
    SecGetEffectiveTokenUser(CurrentThread, (__int64)ListEntry, &v35, v38, 0);
  }
  if ( (int)SecUnicodeStringToString(a4, &P) < 0 )
  {
LABEL_28:
    SecIncrementInternalErrorCounter();
  }
  else
  {
    _mm_lfence();
    v15 = 0;
    if ( (unsigned int)(a8 - 2) <= 1 )
      v15 = 128;
    v33 = v15;
    if ( v35 )
      Sid = *(PSID *)v35;
    else
      Sid = 0;
    ThreadId = (unsigned int)PsGetThreadId(CurrentThread);
    ProcessId = (unsigned int)PsGetProcessId(v13);
    v18 = (volatile signed __int64 *)SecData;
    v19 = ProcessId;
    ProcessSessionId_0 = PsGetProcessSessionId_0(v13);
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(v13);
    v22 = _InterlockedExchangeAdd64(v18 + 42, 1u) + 1;
    v23 = EventWriteModifyDeleteReadSensitiveFile(
            v22,
            v19,
            TimeQuadPart,
            ThreadId,
            Sid,
            ProcessSessionId_0,
            (wchar_t *)P,
            -1,
            v39[0],
            EventDescriptor,
            a6 < 0,
            a8,
            a9,
            v33,
            a10);
    SecIncrementEtwCounters(v23);
    if ( (a6 & 0x40) != 0 )
    {
      _mm_lfence();
      if ( v35 )
        v24 = *(PSID *)v35;
      else
        v24 = 0;
      v25 = (unsigned int)PsGetThreadId(CurrentThread);
      v26 = (unsigned int)PsGetProcessId(v13);
      v27 = (volatile signed __int64 *)SecData;
      v28 = v26;
      v29 = PsGetProcessSessionId_0(v13);
      v30 = PsGetProcessCreateTimeQuadPart(v13);
      v31 = _InterlockedExchangeAdd64(v27 + 42, 1u) + 1;
      v32 = EventWriteModifyDeleteReadSensitiveFile(
              v31,
              v28,
              v30,
              v25,
              v24,
              v29,
              (wchar_t *)P,
              -1,
              v39[0],
              EventDescriptor,
              0,
              a8,
              a9,
              v33,
              a10);
      SecIncrementEtwCounters(v32);
    }
  }
  if ( P )
    SecFreePool(P, 0x74736353u);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v35 )
  {
    if ( v38[0] )
      ExFreePoolWithTag(v35, 0);
  }
}

```

## disassembly

```asm
0x140027278  mov     [rsp-8+arg_8], rbx
0x14002727d  push    rbp
0x14002727e  push    rsi
0x14002727f  push    rdi
0x140027280  push    r12
0x140027282  push    r13
0x140027284  push    r14
0x140027286  push    r15
0x140027288  lea     rbp, [rsp-7]
0x14002728d  sub     rsp, 0E0h
0x140027294  mov     rax, cs:__security_cookie
0x14002729b  xor     rax, rsp
0x14002729e  mov     [rbp+37h+var_40], rax
0x1400272a2  mov     rax, [rbp+37h+arg_20]
0x1400272a6  xor     esi, esi
0x1400272a8  mov     rbx, [rbp+37h+arg_30]
0x1400272ac  mov     rdi, r9
0x1400272af  mov     [rbp+37h+var_70], rax
0x1400272b3  mov     r12, r8
0x1400272b6  mov     rax, [rbp+37h+arg_40]
0x1400272bd  mov     [rbp+37h+var_78], rax
0x1400272c1  mov     rax, [rbp+37h+arg_48]
0x1400272c8  mov     [rbp+37h+var_80], rax
0x1400272cc  mov     [rbp+37h+P], rsi
0x1400272d0  mov     [rbp+37h+ListEntry], rsi
0x1400272d4  mov     [rbp+37h+var_68], rsi
0x1400272d8  mov     [rbp+37h+var_50], sil
0x1400272dc  mov     qword ptr [rbp+37h+var_48], rsi
0x1400272e0  test    r8, r8
0x1400272e3  jnz     short loc_1400272FE
0x1400272e5  mov     r12, [rcx+8]
0x1400272e9  test    r12, r12
0x1400272ec  jnz     short loc_1400272FE
0x1400272ee  mov     r12, gs:188h
0x1400272f7  call    SecFltGetRequestorProcess
0x1400272fc  jmp     short loc_14002730D
0x1400272fe  mov     rcx, r12; Thread
0x140027301  call    cs:__imp_IoThreadToProcess
0x140027308  nop     dword ptr [rax+rax+00h]
0x14002730d  lea     rdx, [rbp+37h+var_48]
0x140027311  mov     rcx, rax; Process
0x140027314  mov     r13, rax
0x140027317  call    SecGetProcessStartKey
0x14002731c  test    eax, eax
0x14002731e  js      loc_1400275AA
0x140027324  lfence
0x140027327  mov     r8b, 1
0x14002732a  lea     rdx, [rbp+37h+ListEntry]
0x14002732e  mov     rcx, r13
0x140027331  call    SecGetProcessContextWithAssertions
0x140027336  test    rbx, rbx
0x140027339  jz      short loc_140027341
0x14002733b  mov     [rbp+37h+var_68], rbx
0x14002733f  jmp     short loc_14002735D
0x140027341  lfence
0x140027344  mov     rdx, [rbp+37h+ListEntry]
0x140027348  lea     r9, [rbp+37h+var_50]
0x14002734c  lea     r8, [rbp+37h+var_68]
0x140027350  mov     [rsp+110h+Sid], rsi; __int64
0x140027355  mov     rcx, r12; Thread
0x140027358  call    SecGetEffectiveTokenUser
0x14002735d  lea     rdx, [rbp+37h+P]
0x140027361  mov     rcx, rdi
0x140027364  call    SecUnicodeStringToString
0x140027369  test    eax, eax
0x14002736b  js      loc_1400275AA
0x140027371  lfence
0x140027374  mov     eax, dword ptr [rbp+37h+arg_38]
0x140027377  mov     ecx, esi
0x140027379  add     eax, 0FFFFFFFEh
0x14002737c  mov     edx, 80h
0x140027381  cmp     eax, 1
0x140027384  mov     rax, [rbp+37h+var_68]
0x140027388  cmovbe  ecx, edx
0x14002738b  mov     [rbp+37h+var_90], ecx
0x14002738e  test    rax, rax
0x140027391  jnz     short loc_140027399
0x140027393  mov     [rbp+37h+var_88], rsi
0x140027397  jmp     short loc_1400273A0
0x140027399  mov     rax, [rax]
0x14002739c  mov     [rbp+37h+var_88], rax
0x1400273a0  mov     rcx, r12; Thread
0x1400273a3  call    cs:__imp_PsGetThreadId
0x1400273aa  nop     dword ptr [rax+rax+00h]
0x1400273af  mov     rcx, r13; Process
0x1400273b2  mov     r15, rax
0x1400273b5  call    cs:__imp_PsGetProcessId
0x1400273bc  nop     dword ptr [rax+rax+00h]
0x1400273c1  mov     esi, dword ptr [rbp+37h+arg_28]
0x1400273c4  mov     rcx, r13
0x1400273c7  mov     rbx, cs:SecData
0x1400273ce  mov     r14, rax
0x1400273d1  shr     esi, 7
0x1400273d4  and     esi, 1
0x1400273d7  call    PsGetProcessSessionId_0
0x1400273dc  mov     rcx, r13; Process
0x1400273df  mov     edi, eax
0x1400273e1  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400273e8  nop     dword ptr [rax+rax+00h]
0x1400273ed  mov     r8, rax; int
0x1400273f0  mov     ecx, 1
0x1400273f5  lock xadd [rbx+150h], rcx
0x1400273fe  mov     rax, [rbp+37h+var_80]
0x140027402  inc     rcx; int
0x140027405  mov     rdx, qword ptr [rbp+37h+var_48]
0x140027409  mov     r9d, r15d; int
0x14002740c  mov     [rsp+110h+var_A0], rax; __int64
0x140027411  mov     eax, [rbp+37h+var_90]
0x140027414  mov     [rsp+110h+var_A8], eax; int
0x140027418  mov     rax, [rbp+37h+var_78]
0x14002741c  mov     [rsp+110h+var_B0], rax; wchar_t *
0x140027421  mov     eax, dword ptr [rbp+37h+arg_38]
0x140027424  mov     dword ptr [rsp+110h+var_B8], eax; char
0x140027428  mov     rax, [rbp+37h+var_70]
0x14002742c  mov     dword ptr [rsp+110h+var_C0], esi; char
0x140027430  mov     [rsp+110h+EventDescriptor], rax; EventDescriptor
0x140027435  mov     rax, [rbp+37h+P]
0x140027439  mov     qword ptr [rsp+110h+var_D0], rdx; char
0x14002743e  mov     edx, r14d; int
0x140027441  mov     dword ptr [rsp+110h+var_D8], 0FFFFFFFFh; char
0x140027449  mov     [rsp+110h+Str], rax; Str
0x14002744e  mov     rax, [rbp+37h+var_88]
0x140027452  mov     dword ptr [rsp+110h+var_E8], edi; char
0x140027456  mov     [rsp+110h+Sid], rax; Sid
0x14002745b  call    EventWriteModifyDeleteReadSensitiveFile
0x140027460  mov     ecx, eax
0x140027462  call    SecIncrementEtwCounters
0x140027467  test    [rbp+37h+arg_28], 40h
0x14002746b  jz      loc_140027542
0x140027471  lfence
0x140027474  mov     rax, [rbp+37h+var_68]
0x140027478  test    rax, rax
0x14002747b  jnz     short loc_140027482
0x14002747d  xor     r15d, r15d
0x140027480  jmp     short loc_140027485
0x140027482  mov     r15, [rax]
0x140027485  mov     rcx, r12; Thread
0x140027488  call    cs:__imp_PsGetThreadId
0x14002748f  nop     dword ptr [rax+rax+00h]
0x140027494  mov     rcx, r13; Process
0x140027497  mov     r14, rax
0x14002749a  call    cs:__imp_PsGetProcessId
0x1400274a1  nop     dword ptr [rax+rax+00h]
0x1400274a6  mov     rbx, cs:SecData
0x1400274ad  mov     rcx, r13
0x1400274b0  mov     rsi, rax
0x1400274b3  call    PsGetProcessSessionId_0
0x1400274b8  mov     rcx, r13; Process
0x1400274bb  mov     edi, eax
0x1400274bd  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400274c4  nop     dword ptr [rax+rax+00h]
0x1400274c9  mov     r8, rax; int
0x1400274cc  mov     ecx, 1
0x1400274d1  lock xadd [rbx+150h], rcx
0x1400274da  mov     rax, [rbp+37h+var_80]
0x1400274de  inc     rcx; int
0x1400274e1  mov     rdx, qword ptr [rbp+37h+var_48]
0x1400274e5  mov     r9d, r14d; int
0x1400274e8  mov     [rsp+110h+var_A0], rax; __int64
0x1400274ed  mov     eax, [rbp+37h+var_90]
0x1400274f0  mov     [rsp+110h+var_A8], eax; int
0x1400274f4  mov     rax, [rbp+37h+var_78]
0x1400274f8  mov     [rsp+110h+var_B0], rax; wchar_t *
0x1400274fd  mov     eax, dword ptr [rbp+37h+arg_38]
0x140027500  mov     dword ptr [rsp+110h+var_B8], eax; char
0x140027504  mov     rax, [rbp+37h+var_70]
0x140027508  mov     dword ptr [rsp+110h+var_C0], 0; char
0x140027510  mov     [rsp+110h+EventDescriptor], rax; EventDescriptor
0x140027515  mov     rax, [rbp+37h+P]
0x140027519  mov     qword ptr [rsp+110h+var_D0], rdx; char
0x14002751e  mov     edx, esi; int
0x140027520  mov     dword ptr [rsp+110h+var_D8], 0FFFFFFFFh; char
0x140027528  mov     [rsp+110h+Str], rax; Str
0x14002752d  mov     dword ptr [rsp+110h+var_E8], edi; char
0x140027531  mov     [rsp+110h+Sid], r15; Sid
0x140027536  call    EventWriteModifyDeleteReadSensitiveFile
0x14002753b  mov     ecx, eax
0x14002753d  call    SecIncrementEtwCounters
0x140027542  xor     esi, esi
0x140027544  mov     rcx, [rbp+37h+P]; P
0x140027548  test    rcx, rcx
0x14002754b  jz      short loc_140027557
0x14002754d  mov     edx, 74736353h; Tag
0x140027552  call    SecFreePool
0x140027557  mov     rcx, [rbp+37h+ListEntry]; ListEntry
0x14002755b  test    rcx, rcx
0x14002755e  jz      short loc_140027565
0x140027560  call    SecReleaseProcessContext
0x140027565  mov     rcx, [rbp+37h+var_68]; P
0x140027569  test    rcx, rcx
0x14002756c  jz      short loc_140027582
0x14002756e  cmp     [rbp+37h+var_50], sil
0x140027572  jz      short loc_140027582
0x140027574  xor     edx, edx; Tag
0x140027576  call    cs:__imp_ExFreePoolWithTag
0x14002757d  nop     dword ptr [rax+rax+00h]
0x140027582  mov     rcx, [rbp+37h+var_40]
0x140027586  xor     rcx, rsp; StackCookie
0x140027589  call    __security_check_cookie
0x14002758e  mov     rbx, [rsp+110h+arg_8]
0x140027596  add     rsp, 0E0h
0x14002759d  pop     r15
0x14002759f  pop     r14
0x1400275a1  pop     r13
0x1400275a3  pop     r12
0x1400275a5  pop     rdi
0x1400275a6  pop     rsi
0x1400275a7  pop     rbp
0x1400275a8  retn
0x1400275aa  call    SecIncrementInternalErrorCounter
0x1400275af  jmp     short loc_140027544
```
