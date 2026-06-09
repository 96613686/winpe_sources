# SecObHandleOpenProcessCallback

- ea: `0x14002be2c`
- end: `0x14002c080`
- name: `SecObHandleOpenProcessCallback`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14002c2e0`

## callees

- `0x140006754`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x14000ac04`
- `0x140010080`
- `0x140011650`
- `0x14002b76c`
- `0x14002be2c`
- `0x14003b8bc`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bf68`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bf68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c046`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c046`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002be77`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002be77`

## pseudocode

```c
void __fastcall SecObHandleOpenProcessCallback(__int64 a1)
{
  struct _KPROCESS *v1; // rdi
  PEPROCESS CurrentProcess; // rax
  __int64 v4; // r8
  PEPROCESS v5; // r14
  unsigned __int8 CurrentThreadId; // al
  volatile signed __int64 *v7; // rbx
  struct _SLIST_ENTRY *Next; // rdi
  wchar_t *Str; // r14
  __int64 v10; // r15
  struct _SLIST_ENTRY *v11; // rsi
  __int64 v12; // r13
  void *Sid; // r12
  char ProcessSessionId_0; // al
  unsigned int v15; // eax
  char v16[4]; // [rsp+78h] [rbp-19h]
  char v17[4]; // [rsp+7Ch] [rbp-15h]
  int v18; // [rsp+80h] [rbp-11h]
  PEPROCESS v19; // [rsp+88h] [rbp-9h]
  char v20; // [rsp+90h] [rbp-1h]
  const EVENT_DESCRIPTOR *EventDescriptor; // [rsp+98h] [rbp+7h]
  PSLIST_ENTRY v22; // [rsp+A0h] [rbp+Fh] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+A8h] [rbp+17h] BYREF
  PVOID P; // [rsp+B0h] [rbp+1Fh] BYREF
  char v25[8]; // [rsp+B8h] [rbp+27h] BYREF

  v1 = *(struct _KPROCESS **)(a1 + 8);
  ListEntry = 0;
  v22 = 0;
  P = 0;
  v25[0] = 0;
  CurrentProcess = IoGetCurrentProcess();
  v5 = CurrentProcess;
  v19 = CurrentProcess;
  if ( qword_140020020 || (*(_DWORD *)(a1 + 4) & 1) == 0 )
  {
    LOBYTE(v4) = 1;
    if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v4) < 0 )
      goto LABEL_13;
    if ( v5 == v1 )
      goto LABEL_14;
    if ( (int)SecGetProcessContextByObject(v1, &v22) < 0 )
    {
LABEL_13:
      SecIncrementInternalErrorCounter();
      goto LABEL_14;
    }
    _mm_lfence();
    SecDetPerformProcessAssertionsWithContext(v1, v22, 0);
    if ( (*(_DWORD *)(a1 + 4) & 1) == 0
      && (xmmword_14001B740 & 0x200000) != 0
      && (*(_DWORD *)a1 == 1 || *(_DWORD *)a1 == 2) )
    {
      _mm_lfence();
      *(_DWORD *)v16 = **(_DWORD **)(a1 + 32);
      EventDescriptor = (const EVENT_DESCRIPTOR *)SecIsProcessFilteredByAccessMask(v1, *(unsigned int *)v16);
      if ( EventDescriptor )
      {
        if ( (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v25, 0) >= 0 )
        {
          _mm_lfence();
          *(_DWORD *)v17 = v22[2].Next;
          CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
          v7 = (volatile signed __int64 *)SecData;
          v20 = CurrentThreadId;
          Next = v22[3].Next;
          Str = (wchar_t *)v22[10].Next;
          v10 = *((_QWORD *)&v22[2].Next + 1);
          v11 = ListEntry[3].Next;
          v12 = *((_QWORD *)&ListEntry[2].Next + 1);
          Sid = *(void **)P;
          v18 = (int)ListEntry[2].Next;
          ProcessSessionId_0 = PsGetProcessSessionId_0(v19);
          v15 = EventWriteOpenProcess(
                  EventDescriptor,
                  _InterlockedIncrement64(v7 + 42),
                  v18,
                  v12,
                  v20,
                  Sid,
                  ProcessSessionId_0,
                  v17[0],
                  v10,
                  Str,
                  *(_DWORD *)v16,
                  v11,
                  Next);
          SecIncrementEtwCounters(v15);
          goto LABEL_14;
        }
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v22 )
    SecReleaseProcessContext(v22);
  if ( P )
  {
    if ( v25[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14002be2c  mov     rax, rsp
0x14002be2f  mov     [rax+10h], rbx
0x14002be33  mov     [rax+18h], rsi
0x14002be37  mov     [rax+20h], rdi
0x14002be3b  push    rbp
0x14002be3c  push    r12
0x14002be3e  push    r13
0x14002be40  push    r14
0x14002be42  push    r15
0x14002be44  lea     rbp, [rax-5Fh]
0x14002be48  sub     rsp, 0C0h
0x14002be4f  mov     rax, cs:__security_cookie
0x14002be56  xor     rax, rsp
0x14002be59  mov     [rbp+57h+var_28], rax
0x14002be5d  mov     rdi, [rcx+8]
0x14002be61  xor     r15d, r15d
0x14002be64  mov     [rbp+57h+ListEntry], r15
0x14002be68  mov     rsi, rcx
0x14002be6b  mov     [rbp+57h+var_48], r15
0x14002be6f  mov     [rbp+57h+P], r15
0x14002be73  mov     [rbp+57h+var_30], r15b
0x14002be77  call    cs:__imp_IoGetCurrentProcess
0x14002be7e  nop     dword ptr [rax+rax+00h]
0x14002be83  cmp     cs:qword_140020020, r15
0x14002be8a  mov     r14, rax
0x14002be8d  mov     [rbp+57h+var_60], rax
0x14002be91  jnz     short loc_14002BE9F
0x14002be93  mov     ecx, [rsi+4]
0x14002be96  test    cl, 1
0x14002be99  jnz     loc_14002C019
0x14002be9f  mov     r8b, 1
0x14002bea2  lea     rdx, [rbp+57h+ListEntry]
0x14002bea6  mov     rcx, r14
0x14002bea9  call    SecGetProcessContextWithAssertions
0x14002beae  test    eax, eax
0x14002beb0  js      loc_14002C014
0x14002beb6  cmp     r14, rdi
0x14002beb9  jz      loc_14002C019
0x14002bebf  lea     rdx, [rbp+57h+var_48]
0x14002bec3  mov     rcx, rdi
0x14002bec6  call    SecGetProcessContextByObject
0x14002becb  test    eax, eax
0x14002becd  js      loc_14002C014
0x14002bed3  lfence
0x14002bed6  mov     rdx, [rbp+57h+var_48]
0x14002beda  xor     r8d, r8d
0x14002bedd  mov     rcx, rdi
0x14002bee0  call    SecDetPerformProcessAssertionsWithContext
0x14002bee5  mov     eax, [rsi+4]
0x14002bee8  test    al, 1
0x14002beea  jnz     loc_14002C019
0x14002bef0  test    qword ptr cs:xmmword_14001B740, 200000h
0x14002befb  jz      loc_14002C019
0x14002bf01  mov     eax, [rsi]
0x14002bf03  cmp     eax, 1
0x14002bf06  jz      short loc_14002BF11
0x14002bf08  cmp     eax, 2
0x14002bf0b  jnz     loc_14002C019
0x14002bf11  lfence
0x14002bf14  mov     rax, [rsi+20h]
0x14002bf18  mov     rcx, rdi
0x14002bf1b  mov     eax, [rax]
0x14002bf1d  mov     edx, eax
0x14002bf1f  mov     dword ptr [rbp+57h+var_70], eax
0x14002bf22  call    SecIsProcessFilteredByAccessMask
0x14002bf27  mov     [rbp+57h+EventDescriptor], rax
0x14002bf2b  test    rax, rax
0x14002bf2e  jz      loc_14002C019
0x14002bf34  mov     rcx, gs:188h; Thread
0x14002bf3d  lea     r9, [rbp+57h+var_30]
0x14002bf41  mov     rdx, [rbp+57h+ListEntry]
0x14002bf45  lea     r8, [rbp+57h+P]
0x14002bf49  mov     qword ptr [rsp+0E0h+var_C0], r15; __int64
0x14002bf4e  call    SecGetEffectiveTokenUser
0x14002bf53  test    eax, eax
0x14002bf55  js      loc_14002C014
0x14002bf5b  lfence
0x14002bf5e  mov     rax, [rbp+57h+var_48]
0x14002bf62  mov     eax, [rax+20h]
0x14002bf65  mov     dword ptr [rbp+57h+var_6C], eax
0x14002bf68  call    cs:__imp_PsGetCurrentThreadId
0x14002bf6f  nop     dword ptr [rax+rax+00h]
0x14002bf74  mov     rcx, [rbp+57h+var_48]
0x14002bf78  mov     rdx, [rbp+57h+ListEntry]
0x14002bf7c  mov     rbx, cs:SecData
0x14002bf83  mov     qword ptr [rbp+57h+var_58], rax
0x14002bf87  mov     rdi, [rcx+30h]
0x14002bf8b  mov     r14, [rcx+0A0h]
0x14002bf92  mov     r15, [rcx+28h]
0x14002bf96  mov     rcx, [rbp+57h+P]
0x14002bf9a  mov     eax, [rdx+20h]
0x14002bf9d  mov     rsi, [rdx+30h]
0x14002bfa1  mov     r13, [rdx+28h]
0x14002bfa5  mov     r12, [rcx]
0x14002bfa8  mov     rcx, [rbp+57h+var_60]
0x14002bfac  mov     [rbp+57h+var_68], eax
0x14002bfaf  call    PsGetProcessSessionId_0
0x14002bfb4  mov     edx, 1
0x14002bfb9  lock xadd [rbx+150h], rdx
0x14002bfc2  mov     ecx, dword ptr [rbp+57h+var_70]
0x14002bfc5  inc     rdx
0x14002bfc8  mov     r8d, [rbp+57h+var_68]
0x14002bfcc  mov     r9, r13
0x14002bfcf  mov     qword ptr [rsp+0E0h+var_80], rdi; char
0x14002bfd4  mov     qword ptr [rsp+0E0h+var_88], rsi; char
0x14002bfd9  mov     dword ptr [rsp+0E0h+var_90], ecx; char
0x14002bfdd  mov     ecx, dword ptr [rbp+57h+var_6C]
0x14002bfe0  mov     [rsp+0E0h+Str], r14; Str
0x14002bfe5  mov     qword ptr [rsp+0E0h+var_A0], r15; char
0x14002bfea  mov     dword ptr [rsp+0E0h+var_A8], ecx; char
0x14002bfee  mov     rcx, [rbp+57h+EventDescriptor]; EventDescriptor
0x14002bff2  mov     dword ptr [rsp+0E0h+var_B0], eax; char
0x14002bff6  mov     rax, qword ptr [rbp+57h+var_58]
0x14002bffa  mov     [rsp+0E0h+Sid], r12; Sid
0x14002bfff  mov     dword ptr [rsp+0E0h+var_C0], eax; char
0x14002c003  call    EventWriteOpenProcess
0x14002c008  mov     ecx, eax
0x14002c00a  call    SecIncrementEtwCounters
0x14002c00f  xor     r15d, r15d
0x14002c012  jmp     short loc_14002C019
0x14002c014  call    SecIncrementInternalErrorCounter
0x14002c019  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14002c01d  test    rcx, rcx
0x14002c020  jz      short loc_14002C027
0x14002c022  call    SecReleaseProcessContext
0x14002c027  mov     rcx, [rbp+57h+var_48]; ListEntry
0x14002c02b  test    rcx, rcx
0x14002c02e  jz      short loc_14002C035
0x14002c030  call    SecReleaseProcessContext
0x14002c035  mov     rcx, [rbp+57h+P]; P
0x14002c039  test    rcx, rcx
0x14002c03c  jz      short loc_14002C052
0x14002c03e  cmp     [rbp+57h+var_30], r15b
0x14002c042  jz      short loc_14002C052
0x14002c044  xor     edx, edx; Tag
0x14002c046  call    cs:__imp_ExFreePoolWithTag
0x14002c04d  nop     dword ptr [rax+rax+00h]
0x14002c052  mov     rcx, [rbp+57h+var_28]
0x14002c056  xor     rcx, rsp; StackCookie
0x14002c059  call    __security_check_cookie
0x14002c05e  lea     r11, [rsp+0E0h+var_20]
0x14002c066  mov     rbx, [r11+38h]
0x14002c06a  mov     rsi, [r11+40h]
0x14002c06e  mov     rdi, [r11+48h]
0x14002c072  mov     rsp, r11
0x14002c075  pop     r15
0x14002c077  pop     r14
0x14002c079  pop     r13
0x14002c07b  pop     r12
0x14002c07d  pop     rbp
0x14002c07e  retn
```
