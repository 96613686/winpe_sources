# SecSendDasdOpenEvent

- ea: `0x140026d08`
- end: `0x140026ec2`
- name: `SecSendDasdOpenEvent`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14002466c`

## callees

- `0x140005f34`
- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140011650`
- `0x140025b78`
- `0x140026d08`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140026ddc`
- `ntoskrnl!PsGetThreadId` at `0x140026ddc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e97`

## pseudocode

```c
void __fastcall SecSendDasdOpenEvent(__int64 a1, __int64 a2, char a3, char a4, char a5)
{
  __int64 RequestorProcess; // rax
  __int64 v10; // r8
  struct _KTHREAD *CurrentThread; // rbx
  int ThreadId; // eax
  char v13; // bl
  int Next; // r15d
  void *Sid; // rdi
  struct _SLIST_ENTRY *v16; // r11
  int v17; // esi
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // eax
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp-11h] BYREF
  PVOID P; // [rsp+68h] [rbp-9h] BYREF
  PVOID v23; // [rsp+70h] [rbp-1h] BYREF
  _BYTE v24[8]; // [rsp+78h] [rbp+7h] BYREF

  P = 0;
  ListEntry = 0;
  v23 = 0;
  v24[0] = 0;
  if ( (xmmword_14001B740 & 0x20000) != 0 )
  {
    RequestorProcess = SecFltGetRequestorProcess(a1);
    LOBYTE(v10) = 1;
    if ( (int)SecGetProcessContextWithAssertions(RequestorProcess, &ListEntry, v10) < 0 )
      goto LABEL_9;
    _mm_lfence();
    CurrentThread = *(struct _KTHREAD **)(a1 + 8);
    if ( !CurrentThread )
      CurrentThread = KeGetCurrentThread();
    if ( (int)SecGetEffectiveTokenUser(CurrentThread, (__int64)ListEntry, &v23, v24, 0) < 0
      || a2 && (int)SecUnicodeStringToString(a2, &P) < 0 )
    {
LABEL_9:
      SecIncrementInternalErrorCounter();
    }
    else
    {
      _mm_lfence();
      ThreadId = (unsigned int)PsGetThreadId(CurrentThread);
      v13 = a4;
      Next = (int)ListEntry[2].Next;
      Sid = *(void **)v23;
      v16 = ListEntry[3].Next;
      v17 = *((_DWORD *)&ListEntry[38].Next + 2);
      v18 = *((_QWORD *)&ListEntry[2].Next + 1);
      v19 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
      v20 = EventDasdOpenWrite(v19, Next, v18, ThreadId, Sid, v17, (wchar_t *)P, a3, v13, (char)v16, a5);
      SecIncrementEtwCounters(v20);
    }
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( v23 )
    {
      if ( v24[0] )
        ExFreePoolWithTag(v23, 0);
    }
  }
}

```

## disassembly

```asm
0x140026d08  push    rbp
0x140026d0a  push    rbx
0x140026d0b  push    rsi
0x140026d0c  push    rdi
0x140026d0d  push    r12
0x140026d0f  push    r14
0x140026d11  push    r15
0x140026d13  lea     rbp, [rsp-1Fh]
0x140026d18  sub     rsp, 90h
0x140026d1f  mov     rax, cs:__security_cookie
0x140026d26  xor     rax, rsp
0x140026d29  mov     [rbp+4Fh+var_40], rax
0x140026d2d  test    qword ptr cs:xmmword_14001B740, 20000h
0x140026d38  mov     r12d, r8d
0x140026d3b  movzx   esi, r9b
0x140026d3f  mov     rdi, rdx
0x140026d42  mov     rbx, rcx
0x140026d45  mov     [rbp+4Fh+P], 0
0x140026d4d  mov     [rbp+4Fh+ListEntry], 0
0x140026d55  mov     [rbp+4Fh+var_50], 0
0x140026d5d  mov     [rbp+4Fh+var_48], 0
0x140026d61  jz      loc_140026EA3
0x140026d67  call    SecFltGetRequestorProcess
0x140026d6c  mov     rcx, rax
0x140026d6f  lea     rdx, [rbp+4Fh+ListEntry]
0x140026d73  mov     r8b, 1
0x140026d76  call    SecGetProcessContextWithAssertions
0x140026d7b  test    eax, eax
0x140026d7d  js      loc_140026E60
0x140026d83  lfence
0x140026d86  mov     rbx, [rbx+8]
0x140026d8a  test    rbx, rbx
0x140026d8d  jnz     short loc_140026D98
0x140026d8f  mov     rbx, gs:188h
0x140026d98  mov     rdx, [rbp+4Fh+ListEntry]
0x140026d9c  lea     r9, [rbp+4Fh+var_48]
0x140026da0  lea     r8, [rbp+4Fh+var_50]
0x140026da4  mov     [rsp+0C0h+Sid], 0; __int64
0x140026dad  mov     rcx, rbx; Thread
0x140026db0  call    SecGetEffectiveTokenUser
0x140026db5  test    eax, eax
0x140026db7  js      loc_140026E60
0x140026dbd  test    rdi, rdi
0x140026dc0  jz      short loc_140026DD6
0x140026dc2  lea     rdx, [rbp+4Fh+P]
0x140026dc6  mov     rcx, rdi
0x140026dc9  call    SecUnicodeStringToString
0x140026dce  test    eax, eax
0x140026dd0  js      loc_140026E60
0x140026dd6  lfence
0x140026dd9  mov     rcx, rbx; Thread
0x140026ddc  call    cs:__imp_PsGetThreadId
0x140026de3  nop     dword ptr [rax+rax+00h]
0x140026de8  mov     rdx, [rbp+4Fh+ListEntry]
0x140026dec  mov     ebx, esi
0x140026dee  mov     rcx, [rbp+4Fh+var_50]
0x140026df2  mov     r14, rax
0x140026df5  movzx   r10d, [rbp+4Fh+arg_20]
0x140026dfa  mov     r9, cs:SecData
0x140026e01  mov     r15d, [rdx+20h]
0x140026e05  mov     rdi, [rcx]
0x140026e08  mov     ecx, 1
0x140026e0d  mov     r11, [rdx+30h]
0x140026e11  mov     esi, [rdx+268h]
0x140026e17  mov     r8, [rdx+28h]; int
0x140026e1b  lock xadd [r9+150h], rcx
0x140026e24  mov     rax, [rbp+4Fh+P]
0x140026e28  inc     rcx; int
0x140026e2b  mov     dword ptr [rsp+0C0h+var_70], r10d; char
0x140026e30  mov     r9d, r14d; int
0x140026e33  mov     qword ptr [rsp+0C0h+var_78], r11; char
0x140026e38  mov     edx, r15d; int
0x140026e3b  mov     dword ptr [rsp+0C0h+var_80], ebx; char
0x140026e3f  mov     dword ptr [rsp+0C0h+var_88], r12d; char
0x140026e44  mov     [rsp+0C0h+Str], rax; Str
0x140026e49  mov     dword ptr [rsp+0C0h+var_98], esi; char
0x140026e4d  mov     [rsp+0C0h+Sid], rdi; Sid
0x140026e52  call    EventDasdOpenWrite
0x140026e57  mov     ecx, eax
0x140026e59  call    SecIncrementEtwCounters
0x140026e5e  jmp     short loc_140026E65
0x140026e60  call    SecIncrementInternalErrorCounter
0x140026e65  mov     rcx, [rbp+4Fh+P]; P
0x140026e69  test    rcx, rcx
0x140026e6c  jz      short loc_140026E78
0x140026e6e  mov     edx, 74736353h; Tag
0x140026e73  call    SecFreePool
0x140026e78  mov     rcx, [rbp+4Fh+ListEntry]; ListEntry
0x140026e7c  test    rcx, rcx
0x140026e7f  jz      short loc_140026E86
0x140026e81  call    SecReleaseProcessContext
0x140026e86  mov     rcx, [rbp+4Fh+var_50]; P
0x140026e8a  test    rcx, rcx
0x140026e8d  jz      short loc_140026EA3
0x140026e8f  cmp     [rbp+4Fh+var_48], 0
0x140026e93  jz      short loc_140026EA3
0x140026e95  xor     edx, edx; Tag
0x140026e97  call    cs:__imp_ExFreePoolWithTag
0x140026e9e  nop     dword ptr [rax+rax+00h]
0x140026ea3  mov     rcx, [rbp+4Fh+var_40]
0x140026ea7  xor     rcx, rsp; StackCookie
0x140026eaa  call    __security_check_cookie
0x140026eaf  add     rsp, 90h
0x140026eb6  pop     r15
0x140026eb8  pop     r14
0x140026eba  pop     r12
0x140026ebc  pop     rdi
0x140026ebd  pop     rsi
0x140026ebe  pop     rbx
0x140026ebf  pop     rbp
0x140026ec0  retn
```
