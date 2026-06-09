# SecObHandleOpenDesktopCallback

- ea: `0x14002bc14`
- end: `0x14002be2a`
- name: `SecObHandleOpenDesktopCallback`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x14002c2e0`

## callees

- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140010080`
- `0x140011650`
- `0x140021000`
- `0x1400210e0`
- `0x14002b5ec`
- `0x14002bc14`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bd0c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002bd0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdf0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002bc6f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002bd47`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002bc6f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002bd47`

## pseudocode

```c
void __fastcall SecObHandleOpenDesktopCallback(int *a1)
{
  PEPROCESS CurrentProcess; // rax
  __int64 v3; // r8
  int v4; // ebx
  int *v5; // rax
  int v6; // r12d
  int v7; // r13d
  unsigned int CurrentThreadId; // eax
  bool v9; // zf
  volatile signed __int64 *v10; // rbx
  char v11; // di
  struct _SLIST_ENTRY *Next; // r15
  void *Sid; // rsi
  __int64 v14; // r14
  PEPROCESS v15; // rax
  char ProcessSessionId_0; // al
  __int64 v17; // rcx
  unsigned int v18; // eax
  int v19; // [rsp+68h] [rbp-9h]
  int v20; // [rsp+70h] [rbp-1h]
  PSLIST_ENTRY ListEntry; // [rsp+78h] [rbp+7h] BYREF
  _WORD *v22; // [rsp+80h] [rbp+Fh]
  PVOID P; // [rsp+88h] [rbp+17h] BYREF
  PVOID v24; // [rsp+90h] [rbp+1Fh] BYREF
  _BYTE v25[8]; // [rsp+98h] [rbp+27h] BYREF

  v22 = 0;
  P = 0;
  v24 = 0;
  v25[0] = 0;
  ListEntry = 0;
  if ( (xmmword_14001B740 & 0x400000) != 0 )
  {
    CurrentProcess = IoGetCurrentProcess();
    LOBYTE(v3) = 1;
    if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v3) >= 0
      && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &v24, v25, 0) >= 0
      && (int)MpQueryObjectName(*((PVOID *)a1 + 1)) >= 0
      && *v22
      && (int)SecUnicodeStringToString(v22, &P) >= 0
      && ((v4 = *a1, *a1 == 1) || v4 == 2) )
    {
      v5 = (int *)*((_QWORD *)a1 + 4);
      v6 = a1[1];
      v7 = *v5;
      CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
      v9 = v4 == 2;
      v10 = (volatile signed __int64 *)SecData;
      v20 = CurrentThreadId;
      v11 = v9;
      Next = ListEntry[3].Next;
      Sid = *(void **)v24;
      v14 = *((_QWORD *)&ListEntry[2].Next + 1);
      v19 = (int)ListEntry[2].Next;
      v15 = IoGetCurrentProcess();
      ProcessSessionId_0 = PsGetProcessSessionId_0(v15);
      v17 = _InterlockedIncrement64(v10 + 42);
      v18 = EventWriteOpenDesktop(
              v17,
              v19,
              v14,
              v20,
              Sid,
              ProcessSessionId_0,
              (wchar_t *)P,
              v7,
              v11,
              v6 & 1,
              (char)Next);
      SecIncrementEtwCounters(v18);
    }
    else
    {
      SecIncrementInternalErrorCounter();
    }
    if ( v22 )
      MpFreeObjectName();
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( v24 )
    {
      if ( v25[0] )
        ExFreePoolWithTag(v24, 0);
    }
  }
}

```

## disassembly

```asm
0x14002bc14  mov     rax, rsp
0x14002bc17  mov     [rax+10h], rbx
0x14002bc1b  mov     [rax+18h], rsi
0x14002bc1f  mov     [rax+20h], rdi
0x14002bc23  push    rbp
0x14002bc24  push    r12
0x14002bc26  push    r13
0x14002bc28  push    r14
0x14002bc2a  push    r15
0x14002bc2c  lea     rbp, [rax-5Fh]
0x14002bc30  sub     rsp, 0A0h
0x14002bc37  mov     rax, cs:__security_cookie
0x14002bc3e  xor     rax, rsp
0x14002bc41  mov     [rbp+57h+var_28], rax
0x14002bc45  xor     edi, edi
0x14002bc47  mov     r12, rcx
0x14002bc4a  test    qword ptr cs:xmmword_14001B740, 400000h
0x14002bc55  mov     [rbp+57h+var_48], rdi
0x14002bc59  mov     [rbp+57h+P], rdi
0x14002bc5d  mov     [rbp+57h+var_38], rdi
0x14002bc61  mov     [rbp+57h+var_30], dil
0x14002bc65  mov     [rbp+57h+ListEntry], rdi
0x14002bc69  jz      loc_14002BDFC
0x14002bc6f  call    cs:__imp_IoGetCurrentProcess
0x14002bc76  nop     dword ptr [rax+rax+00h]
0x14002bc7b  mov     r8b, 1
0x14002bc7e  lea     rdx, [rbp+57h+ListEntry]
0x14002bc82  mov     rcx, rax
0x14002bc85  call    SecGetProcessContextWithAssertions
0x14002bc8a  test    eax, eax
0x14002bc8c  js      loc_14002BDAB
0x14002bc92  mov     rcx, gs:188h; Thread
0x14002bc9b  lea     r9, [rbp+57h+var_30]
0x14002bc9f  mov     rdx, [rbp+57h+ListEntry]
0x14002bca3  lea     r8, [rbp+57h+var_38]
0x14002bca7  mov     [rsp+0C0h+Sid], rdi; __int64
0x14002bcac  call    SecGetEffectiveTokenUser
0x14002bcb1  test    eax, eax
0x14002bcb3  js      loc_14002BDAB
0x14002bcb9  mov     rcx, [r12+8]; Object
0x14002bcbe  lea     rdx, [rbp+57h+var_48]
0x14002bcc2  call    MpQueryObjectName
0x14002bcc7  test    eax, eax
0x14002bcc9  js      loc_14002BDAB
0x14002bccf  mov     rcx, [rbp+57h+var_48]
0x14002bcd3  cmp     [rcx], di
0x14002bcd6  jz      loc_14002BDAB
0x14002bcdc  lea     rdx, [rbp+57h+P]
0x14002bce0  call    SecUnicodeStringToString
0x14002bce5  test    eax, eax
0x14002bce7  js      loc_14002BDAB
0x14002bced  mov     ebx, [r12]
0x14002bcf1  cmp     ebx, 1
0x14002bcf4  jz      short loc_14002BCFF
0x14002bcf6  cmp     ebx, 2
0x14002bcf9  jnz     loc_14002BDAB
0x14002bcff  mov     rax, [r12+20h]
0x14002bd04  mov     r12d, [r12+4]
0x14002bd09  mov     r13d, [rax]
0x14002bd0c  call    cs:__imp_PsGetCurrentThreadId
0x14002bd13  nop     dword ptr [rax+rax+00h]
0x14002bd18  mov     rdx, [rbp+57h+ListEntry]
0x14002bd1c  and     r12d, 1
0x14002bd20  mov     rcx, [rbp+57h+var_38]
0x14002bd24  cmp     ebx, 2
0x14002bd27  mov     rbx, cs:SecData
0x14002bd2e  mov     qword ptr [rbp+57h+var_58], rax
0x14002bd32  setz    dil
0x14002bd36  mov     eax, [rdx+20h]
0x14002bd39  mov     r15, [rdx+30h]
0x14002bd3d  mov     rsi, [rcx]
0x14002bd40  mov     r14, [rdx+28h]
0x14002bd44  mov     [rbp+57h+var_60], eax
0x14002bd47  call    cs:__imp_IoGetCurrentProcess
0x14002bd4e  nop     dword ptr [rax+rax+00h]
0x14002bd53  mov     rcx, rax
0x14002bd56  call    PsGetProcessSessionId_0
0x14002bd5b  mov     ecx, 1
0x14002bd60  lock xadd [rbx+150h], rcx
0x14002bd69  mov     r9, [rbp+57h+P]
0x14002bd6d  inc     rcx; int
0x14002bd70  mov     edx, [rbp+57h+var_60]; int
0x14002bd73  mov     r8, r14; int
0x14002bd76  mov     qword ptr [rsp+0C0h+var_70], r15; char
0x14002bd7b  mov     dword ptr [rsp+0C0h+var_78], r12d; char
0x14002bd80  mov     dword ptr [rsp+0C0h+var_80], edi; char
0x14002bd84  mov     dword ptr [rsp+0C0h+var_88], r13d; char
0x14002bd89  mov     [rsp+0C0h+Str], r9; Str
0x14002bd8e  mov     r9d, [rbp+57h+var_58]; int
0x14002bd92  mov     dword ptr [rsp+0C0h+var_98], eax; char
0x14002bd96  mov     [rsp+0C0h+Sid], rsi; Sid
0x14002bd9b  call    EventWriteOpenDesktop
0x14002bda0  mov     ecx, eax
0x14002bda2  call    SecIncrementEtwCounters
0x14002bda7  xor     edi, edi
0x14002bda9  jmp     short loc_14002BDB0
0x14002bdab  call    SecIncrementInternalErrorCounter
0x14002bdb0  mov     rcx, [rbp+57h+var_48]
0x14002bdb4  test    rcx, rcx
0x14002bdb7  jz      short loc_14002BDBE
0x14002bdb9  call    MpFreeObjectName
0x14002bdbe  mov     rcx, [rbp+57h+P]; P
0x14002bdc2  test    rcx, rcx
0x14002bdc5  jz      short loc_14002BDD1
0x14002bdc7  mov     edx, 74736353h; Tag
0x14002bdcc  call    SecFreePool
0x14002bdd1  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14002bdd5  test    rcx, rcx
0x14002bdd8  jz      short loc_14002BDDF
0x14002bdda  call    SecReleaseProcessContext
0x14002bddf  mov     rcx, [rbp+57h+var_38]; P
0x14002bde3  test    rcx, rcx
0x14002bde6  jz      short loc_14002BDFC
0x14002bde8  cmp     [rbp+57h+var_30], dil
0x14002bdec  jz      short loc_14002BDFC
0x14002bdee  xor     edx, edx; Tag
0x14002bdf0  call    cs:__imp_ExFreePoolWithTag
0x14002bdf7  nop     dword ptr [rax+rax+00h]
0x14002bdfc  mov     rcx, [rbp+57h+var_28]
0x14002be00  xor     rcx, rsp; StackCookie
0x14002be03  call    __security_check_cookie
0x14002be08  lea     r11, [rsp+0C0h+var_20]
0x14002be10  mov     rbx, [r11+38h]
0x14002be14  mov     rsi, [r11+40h]
0x14002be18  mov     rdi, [r11+48h]
0x14002be1c  mov     rsp, r11
0x14002be1f  pop     r15
0x14002be21  pop     r14
0x14002be23  pop     r13
0x14002be25  pop     r12
0x14002be27  pop     rbp
0x14002be28  retn
```
