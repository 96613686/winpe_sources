# SecObHandleOpenThreadCallback

- ea: `0x14002c080`
- end: `0x14002c2a1`
- name: `SecObHandleOpenThreadCallback`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14002c2e0`

## callees

- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x14000ac04`
- `0x140011650`
- `0x14002b490`
- `0x14002c080`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c1be`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c1be`
- `ntoskrnl!PsGetThreadProcess` at `0x14002c0e1`
- `ntoskrnl!PsGetThreadProcess` at `0x14002c0e1`
- `ntoskrnl!PsGetThreadId` at `0x14002c1af`
- `ntoskrnl!PsGetThreadId` at `0x14002c1af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c26c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c26c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002c0cf`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002c0cf`

## pseudocode

```c
void __fastcall SecObHandleOpenThreadCallback(__int64 a1)
{
  struct _KTHREAD *v1; // r14
  PEPROCESS CurrentProcess; // rdi
  PEPROCESS ThreadProcess; // rsi
  int v5; // r12d
  int Next; // r15d
  char ThreadId; // r14
  int CurrentThreadId; // eax
  unsigned int v9; // eax
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp+7h] BYREF
  PSLIST_ENTRY v11; // [rsp+68h] [rbp+Fh] BYREF
  PVOID P; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v13[8]; // [rsp+78h] [rbp+1Fh] BYREF

  v1 = *(struct _KTHREAD **)(a1 + 8);
  ListEntry = 0;
  v11 = 0;
  P = 0;
  v13[0] = 0;
  CurrentProcess = IoGetCurrentProcess();
  ThreadProcess = PsGetThreadProcess(v1);
  if ( _bittest64((const signed __int64 *)&xmmword_14001B740, 0x29u) )
  {
    if ( (int)SecGetProcessContextByObject(CurrentProcess, &ListEntry) < 0 )
      goto LABEL_10;
    _mm_lfence();
    SecDetPerformProcessAssertionsWithContext(CurrentProcess, ListEntry, 0);
    if ( CurrentProcess == ThreadProcess || (*(_DWORD *)(a1 + 4) & 1) != 0 )
      goto LABEL_11;
    if ( (int)SecGetProcessContextByObject(ThreadProcess, &v11) < 0 )
    {
LABEL_10:
      SecIncrementInternalErrorCounter();
      goto LABEL_11;
    }
    _mm_lfence();
    SecDetPerformProcessAssertionsWithContext(ThreadProcess, v11, 0);
    if ( *(_DWORD *)a1 == 1 || *(_DWORD *)a1 == 2 )
    {
      v5 = **(_DWORD **)(a1 + 32);
      if ( (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v13, 0) >= 0 )
      {
        _mm_lfence();
        Next = (int)v11[2].Next;
        ThreadId = (unsigned __int8)PsGetThreadId(v1);
        CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
        v9 = EventWrite39(
               (unsigned int)_InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u) + 1,
               (int)ListEntry[2].Next,
               *((_QWORD *)&ListEntry[2].Next + 1),
               CurrentThreadId,
               ThreadId,
               *(PSID *)P,
               Next,
               *((_QWORD *)&v11[2].Next + 1),
               v5,
               (char)ListEntry[3].Next,
               (char)v11[3].Next);
        SecIncrementEtwCounters(v9);
        goto LABEL_11;
      }
      goto LABEL_10;
    }
  }
LABEL_11:
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v11 )
    SecReleaseProcessContext(v11);
  if ( P )
  {
    if ( v13[0] )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14002c080  mov     [rsp-8+arg_8], rbx
0x14002c085  mov     [rsp-8+arg_10], rsi
0x14002c08a  push    rbp
0x14002c08b  push    rdi
0x14002c08c  push    r12
0x14002c08e  push    r14
0x14002c090  push    r15
0x14002c092  lea     rbp, [rsp-37h]
0x14002c097  sub     rsp, 90h
0x14002c09e  mov     rax, cs:__security_cookie
0x14002c0a5  xor     rax, rsp
0x14002c0a8  mov     [rbp+57h+var_30], rax
0x14002c0ac  mov     r14, [rcx+8]
0x14002c0b0  mov     rbx, rcx
0x14002c0b3  mov     [rbp+57h+ListEntry], 0
0x14002c0bb  mov     [rbp+57h+var_48], 0
0x14002c0c3  mov     [rbp+57h+P], 0
0x14002c0cb  mov     [rbp+57h+var_38], 0
0x14002c0cf  call    cs:__imp_IoGetCurrentProcess
0x14002c0d6  nop     dword ptr [rax+rax+00h]
0x14002c0db  mov     rcx, r14; Thread
0x14002c0de  mov     rdi, rax
0x14002c0e1  call    cs:__imp_PsGetThreadProcess
0x14002c0e8  nop     dword ptr [rax+rax+00h]
0x14002c0ed  bt      qword ptr cs:xmmword_14001B740, 29h ; ')'
0x14002c0f6  mov     rsi, rax
0x14002c0f9  jnb     loc_14002C23F
0x14002c0ff  lea     rdx, [rbp+57h+ListEntry]
0x14002c103  mov     rcx, rdi
0x14002c106  call    SecGetProcessContextByObject
0x14002c10b  test    eax, eax
0x14002c10d  js      loc_14002C23A
0x14002c113  lfence
0x14002c116  mov     rdx, [rbp+57h+ListEntry]
0x14002c11a  xor     r8d, r8d
0x14002c11d  mov     rcx, rdi
0x14002c120  call    SecDetPerformProcessAssertionsWithContext
0x14002c125  cmp     rdi, rsi
0x14002c128  jz      loc_14002C23F
0x14002c12e  mov     eax, [rbx+4]
0x14002c131  test    al, 1
0x14002c133  jnz     loc_14002C23F
0x14002c139  lea     rdx, [rbp+57h+var_48]
0x14002c13d  mov     rcx, rsi
0x14002c140  call    SecGetProcessContextByObject
0x14002c145  test    eax, eax
0x14002c147  js      loc_14002C23A
0x14002c14d  lfence
0x14002c150  mov     rdx, [rbp+57h+var_48]
0x14002c154  xor     r8d, r8d
0x14002c157  mov     rcx, rsi
0x14002c15a  call    SecDetPerformProcessAssertionsWithContext
0x14002c15f  mov     eax, [rbx]
0x14002c161  cmp     eax, 1
0x14002c164  jz      short loc_14002C16F
0x14002c166  cmp     eax, 2
0x14002c169  jnz     loc_14002C23F
0x14002c16f  mov     rax, [rbx+20h]
0x14002c173  lea     r9, [rbp+57h+var_38]
0x14002c177  mov     rcx, gs:188h; Thread
0x14002c180  lea     r8, [rbp+57h+P]
0x14002c184  mov     rdx, [rbp+57h+ListEntry]
0x14002c188  mov     qword ptr [rsp+0B0h+var_90], 0; __int64
0x14002c191  mov     r12d, [rax]
0x14002c194  call    SecGetEffectiveTokenUser
0x14002c199  test    eax, eax
0x14002c19b  js      loc_14002C23A
0x14002c1a1  lfence
0x14002c1a4  mov     rax, [rbp+57h+var_48]
0x14002c1a8  mov     rcx, r14; Thread
0x14002c1ab  mov     r15d, [rax+20h]
0x14002c1af  call    cs:__imp_PsGetThreadId
0x14002c1b6  nop     dword ptr [rax+rax+00h]
0x14002c1bb  mov     r14, rax
0x14002c1be  call    cs:__imp_PsGetCurrentThreadId
0x14002c1c5  nop     dword ptr [rax+rax+00h]
0x14002c1ca  mov     rcx, [rbp+57h+var_48]
0x14002c1ce  mov     rdx, [rbp+57h+ListEntry]
0x14002c1d2  mov     r9, cs:SecData
0x14002c1d9  mov     r10, [rcx+30h]
0x14002c1dd  mov     rbx, [rcx+28h]
0x14002c1e1  mov     rcx, [rbp+57h+P]
0x14002c1e5  mov     esi, [rdx+20h]
0x14002c1e8  mov     r11, [rdx+30h]
0x14002c1ec  mov     r8, [rdx+28h]; int
0x14002c1f0  mov     rdi, [rcx]
0x14002c1f3  mov     ecx, 1
0x14002c1f8  lock xadd [r9+150h], rcx
0x14002c201  mov     qword ptr [rsp+0B0h+var_60], r10; char
0x14002c206  inc     rcx; int
0x14002c209  mov     qword ptr [rsp+0B0h+var_68], r11; char
0x14002c20e  mov     r9d, eax; int
0x14002c211  mov     dword ptr [rsp+0B0h+var_70], r12d; char
0x14002c216  mov     edx, esi; int
0x14002c218  mov     qword ptr [rsp+0B0h+var_78], rbx; char
0x14002c21d  mov     dword ptr [rsp+0B0h+var_80], r15d; char
0x14002c222  mov     [rsp+0B0h+Sid], rdi; Sid
0x14002c227  mov     dword ptr [rsp+0B0h+var_90], r14d; char
0x14002c22c  call    EventWrite39
0x14002c231  mov     ecx, eax
0x14002c233  call    SecIncrementEtwCounters
0x14002c238  jmp     short loc_14002C23F
0x14002c23a  call    SecIncrementInternalErrorCounter
0x14002c23f  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14002c243  test    rcx, rcx
0x14002c246  jz      short loc_14002C24D
0x14002c248  call    SecReleaseProcessContext
0x14002c24d  mov     rcx, [rbp+57h+var_48]; ListEntry
0x14002c251  test    rcx, rcx
0x14002c254  jz      short loc_14002C25B
0x14002c256  call    SecReleaseProcessContext
0x14002c25b  mov     rcx, [rbp+57h+P]; P
0x14002c25f  test    rcx, rcx
0x14002c262  jz      short loc_14002C278
0x14002c264  cmp     [rbp+57h+var_38], 0
0x14002c268  jz      short loc_14002C278
0x14002c26a  xor     edx, edx; Tag
0x14002c26c  call    cs:__imp_ExFreePoolWithTag
0x14002c273  nop     dword ptr [rax+rax+00h]
0x14002c278  mov     rcx, [rbp+57h+var_30]
0x14002c27c  xor     rcx, rsp; StackCookie
0x14002c27f  call    __security_check_cookie
0x14002c284  lea     r11, [rsp+0B0h+var_20]
0x14002c28c  mov     rbx, [r11+38h]
0x14002c290  mov     rsi, [r11+40h]
0x14002c294  mov     rsp, r11
0x14002c297  pop     r15
0x14002c299  pop     r14
0x14002c29b  pop     r12
0x14002c29d  pop     rdi
0x14002c29e  pop     rbp
0x14002c29f  retn
```
