# SecSendUnauthorizedFileOpenAttemptEvent

- ea: `0x1400280f8`
- end: `0x140028280`
- name: `SecSendUnauthorizedFileOpenAttemptEvent`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140023e10`

## callees

- `0x140005638`
- `0x140005f34`
- `0x1400065e4`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x140009b80`
- `0x140011650`
- `0x1400280f8`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400281be`
- `ntoskrnl!PsGetThreadId` at `0x1400281be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002822f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002822f`

## pseudocode

```c
void __fastcall SecSendUnauthorizedFileOpenAttemptEvent(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  __int64 RequestorProcess; // rax
  struct _KTHREAD *CurrentThread; // rbx
  char ThreadId; // al
  int Next; // ebx
  void *Sid; // r11
  struct _SLIST_ENTRY *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  PSLIST_ENTRY ListEntry; // [rsp+50h] [rbp-30h] BYREF
  PVOID P; // [rsp+58h] [rbp-28h] BYREF
  PVOID Str; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-18h] BYREF

  v4 = 0;
  ListEntry = 0;
  P = 0;
  v20[0] = 0;
  Str = 0;
  if ( _bittest64((const signed __int64 *)&xmmword_14001B740, 0x21u) )
  {
    RequestorProcess = SecFltGetRequestorProcess(a1);
    if ( (int)SecGetProcessContextByObject(RequestorProcess, &ListEntry) >= 0 )
    {
      _mm_lfence();
      CurrentThread = *(struct _KTHREAD **)(a1 + 8);
      if ( !CurrentThread )
        CurrentThread = KeGetCurrentThread();
      if ( (int)SecGetEffectiveTokenUser(CurrentThread, (__int64)ListEntry, &P, v20, 0) >= 0 )
      {
        _mm_lfence();
        if ( (unsigned int)(a2 - 2) <= 1 )
        {
          SecUnicodeStringToString(a3, &Str);
          v4 = 128;
        }
        ThreadId = (unsigned __int8)PsGetThreadId(CurrentThread);
        Next = (int)ListEntry[2].Next;
        Sid = *(void **)P;
        v14 = ListEntry[3].Next;
        v15 = *((_QWORD *)&ListEntry[2].Next + 1);
        v16 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
        EventWriteUnauthorizedFileOpenAttempt(v16, Next, v15, (__int64)v14, ThreadId, Sid, a2, (wchar_t *)Str, v4, a4);
      }
    }
    if ( P && v20[0] )
      ExFreePoolWithTag(P, 0);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( Str )
      SecFreePool(Str, 0x74736353u);
  }
}

```

## disassembly

```asm
0x1400280f8  mov     [rsp-28h+arg_8], rbx
0x1400280fd  push    rbp
0x1400280fe  push    rsi
0x1400280ff  push    rdi
0x140028100  push    r14
0x140028102  push    r15
0x140028104  mov     rbp, rsp
0x140028107  sub     rsp, 80h
0x14002810e  mov     rax, cs:__security_cookie
0x140028115  xor     rax, rsp
0x140028118  mov     [rbp+var_10], rax
0x14002811c  xor     esi, esi
0x14002811e  mov     [rbp+ListEntry], 0
0x140028126  bt      qword ptr cs:xmmword_14001B740, 21h ; '!'
0x14002812f  mov     [rbp+P], 0
0x140028137  mov     r15, r9
0x14002813a  mov     [rbp+var_18], 0
0x14002813e  mov     r14, r8
0x140028141  mov     [rbp+var_20], 0
0x140028149  mov     edi, edx
0x14002814b  mov     rbx, rcx
0x14002814e  jnb     loc_14002825C
0x140028154  call    SecFltGetRequestorProcess
0x140028159  mov     rcx, rax
0x14002815c  lea     rdx, [rbp+ListEntry]
0x140028160  call    SecGetProcessContextByObject
0x140028165  test    eax, eax
0x140028167  js      loc_14002821E
0x14002816d  lfence
0x140028170  mov     rbx, [rbx+8]
0x140028174  test    rbx, rbx
0x140028177  jnz     short loc_140028182
0x140028179  mov     rbx, gs:188h
0x140028182  mov     rdx, [rbp+ListEntry]
0x140028186  lea     r9, [rbp+var_18]
0x14002818a  lea     r8, [rbp+P]
0x14002818e  mov     qword ptr [rsp+80h+var_60], rsi; __int64
0x140028193  mov     rcx, rbx; Thread
0x140028196  call    SecGetEffectiveTokenUser
0x14002819b  test    eax, eax
0x14002819d  js      short loc_14002821E
0x14002819f  lfence
0x1400281a2  lea     eax, [rdi-2]
0x1400281a5  cmp     eax, 1
0x1400281a8  ja      short loc_1400281BB
0x1400281aa  lea     rdx, [rbp+var_20]
0x1400281ae  mov     rcx, r14
0x1400281b1  call    SecUnicodeStringToString
0x1400281b6  mov     esi, 80h
0x1400281bb  mov     rcx, rbx; Thread
0x1400281be  call    cs:__imp_PsGetThreadId
0x1400281c5  nop     dword ptr [rax+rax+00h]
0x1400281ca  mov     rdx, [rbp+ListEntry]
0x1400281ce  mov     rcx, [rbp+P]
0x1400281d2  mov     r10, cs:SecData
0x1400281d9  mov     ebx, [rdx+20h]
0x1400281dc  mov     r11, [rcx]
0x1400281df  mov     ecx, 1
0x1400281e4  mov     r9, [rdx+30h]; int
0x1400281e8  mov     r8, [rdx+28h]; int
0x1400281ec  lock xadd [r10+150h], rcx
0x1400281f5  mov     r10, [rbp+var_20]
0x1400281f9  inc     rcx; int
0x1400281fc  mov     [rsp+80h+var_38], r15; __int64
0x140028201  mov     edx, ebx; int
0x140028203  mov     [rsp+80h+var_40], esi; int
0x140028207  mov     [rsp+80h+Str], r10; Str
0x14002820c  mov     dword ptr [rsp+80h+var_50], edi; char
0x140028210  mov     [rsp+80h+Sid], r11; Sid
0x140028215  mov     dword ptr [rsp+80h+var_60], eax; char
0x140028219  call    EventWriteUnauthorizedFileOpenAttempt
0x14002821e  mov     rcx, [rbp+P]; P
0x140028222  test    rcx, rcx
0x140028225  jz      short loc_14002823B
0x140028227  cmp     [rbp+var_18], 0
0x14002822b  jz      short loc_14002823B
0x14002822d  xor     edx, edx; Tag
0x14002822f  call    cs:__imp_ExFreePoolWithTag
0x140028236  nop     dword ptr [rax+rax+00h]
0x14002823b  mov     rcx, [rbp+ListEntry]; ListEntry
0x14002823f  test    rcx, rcx
0x140028242  jz      short loc_140028249
0x140028244  call    SecReleaseProcessContext
0x140028249  mov     rcx, [rbp+var_20]; P
0x14002824d  test    rcx, rcx
0x140028250  jz      short loc_14002825C
0x140028252  mov     edx, 74736353h; Tag
0x140028257  call    SecFreePool
0x14002825c  mov     rcx, [rbp+var_10]
0x140028260  xor     rcx, rsp; StackCookie
0x140028263  call    __security_check_cookie
0x140028268  mov     rbx, [rsp+80h+arg_8]
0x140028270  add     rsp, 80h
0x140028277  pop     r15
0x140028279  pop     r14
0x14002827b  pop     rdi
0x14002827c  pop     rsi
0x14002827d  pop     rbp
0x14002827e  retn
```
