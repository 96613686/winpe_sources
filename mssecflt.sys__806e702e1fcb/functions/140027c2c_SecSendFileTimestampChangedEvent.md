# SecSendFileTimestampChangedEvent

- ea: `0x140027c2c`
- end: `0x140027ec4`
- name: `SecSendFileTimestampChangedEvent`
- size: `664`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140025108`

## callees

- `0x140005f34`
- `0x1400065e4`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140010473`
- `0x140011650`
- `0x14002685c`
- `0x140027c2c`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140027d53`
- `ntoskrnl!PsGetThreadId` at `0x140027d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044703`

## pseudocode

```c
void __fastcall SecSendFileTimestampChangedEvent(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3, void *a4)
{
  __int64 RequestorProcess; // rax
  int ProcessContextByObject; // eax
  struct _KTHREAD *Thread; // rbx
  struct _SLIST_ENTRY *v10; // r8
  __int64 v11; // r9
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // r14
  __int64 v18; // r15
  void *Sid; // r12
  __int64 v20; // r13
  __int64 v21; // rcx
  unsigned int v22; // eax
  int Next; // [rsp+94h] [rbp-74h]
  int ThreadId; // [rsp+98h] [rbp-70h]
  PSLIST_ENTRY ListEntry; // [rsp+A0h] [rbp-68h] BYREF
  PVOID v26; // [rsp+A8h] [rbp-60h] BYREF
  PVOID P; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v28[4]; // [rsp+B8h] [rbp-50h] BYREF
  ULONG SessionId; // [rsp+BCh] [rbp-4Ch] BYREF

  SessionId = 0;
  P = 0;
  ListEntry = 0;
  v26 = 0;
  v28[0] = 0;
  if ( (xmmword_14001B740 & 0x10) == 0 )
    return;
  RequestorProcess = SecFltGetRequestorProcess(CallbackData);
  ProcessContextByObject = SecGetProcessContextByObject(RequestorProcess, &ListEntry);
  if ( ProcessContextByObject >= 0 )
  {
    _mm_lfence();
    ProcessContextByObject = FltGetRequestorSessionId_0(CallbackData, &SessionId);
    if ( ProcessContextByObject >= 0 )
    {
      _mm_lfence();
      Thread = CallbackData->Thread;
      if ( !Thread )
        Thread = KeGetCurrentThread();
      if ( a4 )
      {
        v28[0] = 0;
        v26 = a4;
        goto LABEL_9;
      }
      ProcessContextByObject = SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &v26, v28, 0);
      if ( ProcessContextByObject >= 0 )
      {
LABEL_9:
        ProcessContextByObject = SecUnicodeStringToString(*a3 + 8LL, &P);
        if ( ProcessContextByObject >= 0 )
        {
          ThreadId = (unsigned int)PsGetThreadId(Thread);
          Next = (int)ListEntry[2].Next;
          v10 = ListEntry[3].Next;
          v11 = a3[9];
          v12 = a3[8];
          v13 = a3[7];
          v14 = a3[6];
          v15 = a3[4];
          v16 = a3[3];
          v17 = a3[2];
          v18 = a3[1];
          Sid = *(void **)v26;
          v20 = *((_QWORD *)&ListEntry[2].Next + 1);
          v21 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
          v22 = EventWriteTimestampChangedFile(
                  v21,
                  Next,
                  v20,
                  ThreadId,
                  Sid,
                  SessionId,
                  (wchar_t *)P,
                  v18,
                  v17,
                  v16,
                  v15,
                  v14,
                  v13,
                  v12,
                  v11,
                  -1,
                  (char)v10);
          SecIncrementEtwCounters(v22);
          ProcessContextByObject = 0;
        }
      }
    }
  }
  if ( ProcessContextByObject < 0 )
    SecIncrementInternalErrorCounter();
  if ( P )
    SecFreePool(P, 0x74736353u);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v26 )
  {
    if ( v28[0] )
      ExFreePoolWithTag(v26, 0);
  }
}

```

## disassembly

```asm
0x140027c2c  mov     r11, rsp
0x140027c2f  push    rbx
0x140027c30  push    rsi
0x140027c31  push    rdi
0x140027c32  push    r12
0x140027c34  push    r13
0x140027c36  push    r14
0x140027c38  push    r15
0x140027c3a  sub     rsp, 0D0h
0x140027c41  mov     rax, cs:__security_cookie
0x140027c48  xor     rax, rsp
0x140027c4b  mov     [rsp+108h+var_48], rax
0x140027c53  mov     rdi, r9
0x140027c56  mov     r15, r8
0x140027c59  mov     rbx, rcx
0x140027c5c  xor     esi, esi
0x140027c5e  mov     [r11-78h], esi
0x140027c62  mov     [r11-4Ch], esi
0x140027c66  mov     [r11-58h], rsi
0x140027c6a  mov     [r11-68h], rsi
0x140027c6e  mov     [r11-60h], rsi
0x140027c72  mov     [r11-50h], sil
0x140027c76  mov     al, byte ptr cs:xmmword_14001B740
0x140027c7c  shr     al, 4
0x140027c7f  test    al, 1
0x140027c81  jz      loc_140027EA0
0x140027c87  call    SecFltGetRequestorProcess
0x140027c8c  mov     rcx, rax
0x140027c8f  lea     rdx, [rsp+108h+ListEntry]
0x140027c97  call    SecGetProcessContextByObject
0x140027c9c  mov     [rsp+108h+var_78], eax
0x140027ca3  test    eax, eax
0x140027ca5  js      loc_140027E49
0x140027cab  lfence
0x140027cae  lea     rdx, [rsp+108h+SessionId]; SessionId
0x140027cb6  mov     rcx, rbx; CallbackData
0x140027cb9  call    FltGetRequestorSessionId_0
0x140027cbe  mov     [rsp+108h+var_78], eax
0x140027cc5  test    eax, eax
0x140027cc7  js      loc_140027E49
0x140027ccd  lfence
0x140027cd0  mov     rbx, [rbx+8]
0x140027cd4  test    rbx, rbx
0x140027cd7  jnz     short loc_140027CE2
0x140027cd9  mov     rbx, gs:188h
0x140027ce2  test    rdi, rdi
0x140027ce5  jz      short loc_140027CF9
0x140027ce7  mov     [rsp+108h+var_50], sil
0x140027cef  mov     [rsp+108h+var_60], rdi
0x140027cf7  jmp     short loc_140027D2D
0x140027cf9  mov     [rsp+108h+Sid], rsi; __int64
0x140027cfe  lea     r9, [rsp+108h+var_50]
0x140027d06  lea     r8, [rsp+108h+var_60]
0x140027d0e  mov     rdx, [rsp+108h+ListEntry]
0x140027d16  mov     rcx, rbx; Thread
0x140027d19  call    SecGetEffectiveTokenUser
0x140027d1e  mov     [rsp+108h+var_78], eax
0x140027d25  test    eax, eax
0x140027d27  js      loc_140027E49
0x140027d2d  mov     rcx, [r15]
0x140027d30  add     rcx, 8
0x140027d34  lea     rdx, [rsp+108h+P]
0x140027d3c  call    SecUnicodeStringToString
0x140027d41  mov     [rsp+108h+var_78], eax
0x140027d48  test    eax, eax
0x140027d4a  js      loc_140027E49
0x140027d50  mov     rcx, rbx; Thread
0x140027d53  call    cs:__imp_PsGetThreadId
0x140027d5a  nop     dword ptr [rax+rax+00h]
0x140027d5f  mov     qword ptr [rsp+108h+var_70], rax
0x140027d67  mov     rdx, [rsp+108h+ListEntry]
0x140027d6f  mov     eax, [rdx+20h]
0x140027d72  mov     [rsp+108h+var_74], eax
0x140027d79  mov     r8, [rdx+30h]
0x140027d7d  mov     r9, [r15+48h]
0x140027d81  mov     r10, [r15+40h]
0x140027d85  mov     r11, [r15+38h]
0x140027d89  mov     rbx, [r15+30h]
0x140027d8d  mov     rdi, [r15+20h]
0x140027d91  mov     rsi, [r15+18h]
0x140027d95  mov     r14, [r15+10h]
0x140027d99  mov     r15, [r15+8]
0x140027d9d  mov     rcx, [rsp+108h+var_60]
0x140027da5  mov     r12, [rcx]
0x140027da8  mov     r13, [rdx+28h]
0x140027dac  mov     rax, cs:SecData
0x140027db3  mov     ecx, 1
0x140027db8  lock xadd [rax+150h], rcx
0x140027dc1  inc     rcx; int
0x140027dc4  mov     qword ptr [rsp+108h+var_88], r8; char
0x140027dcc  mov     dword ptr [rsp+108h+var_90], 0FFFFFFFFh; char
0x140027dd4  mov     qword ptr [rsp+108h+var_98], r9; char
0x140027dd9  mov     qword ptr [rsp+108h+var_A0], r10; char
0x140027dde  mov     qword ptr [rsp+108h+var_A8], r11; char
0x140027de3  mov     qword ptr [rsp+108h+var_B0], rbx; char
0x140027de8  mov     qword ptr [rsp+108h+var_B8], rdi; char
0x140027ded  mov     qword ptr [rsp+108h+var_C0], rsi; char
0x140027df2  mov     qword ptr [rsp+108h+var_C8], r14; char
0x140027df7  mov     qword ptr [rsp+108h+var_D0], r15; char
0x140027dfc  mov     rax, [rsp+108h+P]
0x140027e04  mov     [rsp+108h+Str], rax; Str
0x140027e09  mov     eax, [rsp+108h+SessionId]
0x140027e10  mov     dword ptr [rsp+108h+var_E0], eax; char
0x140027e14  mov     [rsp+108h+Sid], r12; Sid
0x140027e19  mov     r9d, [rsp+108h+var_70]; int
0x140027e21  mov     r8, r13; int
0x140027e24  mov     edx, [rsp+108h+var_74]; int
0x140027e2b  call    EventWriteTimestampChangedFile
0x140027e30  mov     [rsp+108h+var_78], eax
0x140027e37  mov     ecx, eax
0x140027e39  call    SecIncrementEtwCounters
0x140027e3e  xor     esi, esi
0x140027e40  mov     eax, esi
0x140027e42  mov     [rsp+108h+var_78], eax
0x140027e49  test    eax, eax
0x140027e4b  jns     short loc_140027E52
0x140027e4d  call    SecIncrementInternalErrorCounter
0x140027e52  mov     rcx, [rsp+108h+P]; P
0x140027e5a  test    rcx, rcx
0x140027e5d  jz      short loc_140027E69
0x140027e5f  mov     edx, 74736353h; Tag
0x140027e64  call    SecFreePool
0x140027e69  mov     rcx, [rsp+108h+ListEntry]; ListEntry
0x140027e71  test    rcx, rcx
0x140027e74  jz      short loc_140027E7B
0x140027e76  call    SecReleaseProcessContext
0x140027e7b  mov     rcx, [rsp+108h+var_60]; P
0x140027e83  test    rcx, rcx
0x140027e86  jz      short loc_140027EA0
0x140027e88  cmp     [rsp+108h+var_50], sil
0x140027e90  jz      short loc_140027EA0
0x140027e92  xor     edx, edx; Tag
0x140027e94  call    cs:__imp_ExFreePoolWithTag
0x140027e9b  nop     dword ptr [rax+rax+00h]
0x140027ea0  mov     rcx, [rsp+108h+var_48]
0x140027ea8  xor     rcx, rsp; StackCookie
0x140027eab  call    __security_check_cookie
0x140027eb0  add     rsp, 0D0h
0x140027eb7  pop     r15
0x140027eb9  pop     r14
0x140027ebb  pop     r13
0x140027ebd  pop     r12
0x140027ebf  pop     rdi
0x140027ec0  pop     rsi
0x140027ec1  pop     rbx
0x140027ec2  retn
0x1400446a8  push    rbp
0x1400446aa  sub     rsp, 90h
0x1400446b1  mov     rbp, rdx
0x1400446b4  cmp     dword ptr [rbp+90h], 0
0x1400446bb  jge     short loc_1400446C3
0x1400446bd  call    SecIncrementInternalErrorCounter
0x1400446c2  nop
0x1400446c3  mov     rcx, [rbp+0B0h]; P
0x1400446ca  test    rcx, rcx
0x1400446cd  jz      short loc_1400446DA
0x1400446cf  mov     edx, 74736353h; Tag
0x1400446d4  call    SecFreePool
0x1400446d9  nop
0x1400446da  mov     rcx, [rbp+0A0h]; ListEntry
0x1400446e1  test    rcx, rcx
0x1400446e4  jz      short loc_1400446EC
0x1400446e6  call    SecReleaseProcessContext
0x1400446eb  nop
0x1400446ec  mov     rcx, [rbp+0A8h]; P
0x1400446f3  test    rcx, rcx
0x1400446f6  jz      short loc_140044710
0x1400446f8  cmp     byte ptr [rbp+0B8h], 0
0x1400446ff  jz      short loc_140044710
0x140044701  xor     edx, edx; Tag
0x140044703  call    cs:__imp_ExFreePoolWithTag
0x14004470a  nop     dword ptr [rax+rax+00h]
0x14004470f  nop
0x140044710  add     rsp, 90h
0x140044717  pop     rbp
0x140044718  retn
```
