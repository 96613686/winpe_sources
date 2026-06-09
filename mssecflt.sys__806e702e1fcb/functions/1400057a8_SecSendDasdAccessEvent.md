# SecSendDasdAccessEvent

- ea: `0x1400057a8`
- end: `0x14000597e`
- name: `SecSendDasdAccessEvent`
- size: `470`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, char, char, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006fa0`
- `0x140007180`

## callees

- `0x140004e08`
- `0x1400057a8`
- `0x140005f34`
- `0x1400065e4`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140011650`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14000588b`
- `ntoskrnl!PsGetThreadId` at `0x14000588b`
- `ntoskrnl!EtwEventEnabled` at `0x1400057ff`
- `ntoskrnl!EtwEventEnabled` at `0x1400057ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005953`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005953`

## pseudocode

```c
void __fastcall SecSendDasdAccessEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  __int64 RequestorProcess; // rax
  __int64 v12; // r8
  struct _KTHREAD *CurrentThread; // rbx
  char ThreadId; // al
  int Next; // r8d
  struct _SLIST_ENTRY *v16; // r11
  int v17; // esi
  void *Sid; // rdi
  __int64 v19; // r9
  __int64 v20; // rdx
  unsigned int v21; // eax
  char v22[4]; // [rsp+50h] [rbp-41h]
  char v23[4]; // [rsp+60h] [rbp-31h]
  PSLIST_ENTRY ListEntry; // [rsp+70h] [rbp-21h] BYREF
  PVOID P; // [rsp+78h] [rbp-19h] BYREF
  PVOID v26; // [rsp+80h] [rbp-11h] BYREF
  _BYTE v27[8]; // [rsp+88h] [rbp-9h] BYREF

  P = 0;
  ListEntry = 0;
  v26 = 0;
  v27[0] = 0;
  if ( EtwEventEnabled(Microsoft_Windows_SECHandle, EventDescriptor) )
  {
    RequestorProcess = SecFltGetRequestorProcess(a2);
    LOBYTE(v12) = 1;
    if ( (int)SecGetProcessContextWithAssertions(RequestorProcess, &ListEntry, v12) < 0 )
      goto LABEL_9;
    _mm_lfence();
    CurrentThread = *(struct _KTHREAD **)(a2 + 8);
    if ( !CurrentThread )
      CurrentThread = KeGetCurrentThread();
    if ( (int)SecGetEffectiveTokenUser(CurrentThread, (__int64)ListEntry, &v26, v27, 0) < 0
      || a3 && (int)SecUnicodeStringToString(a3, &P) < 0 )
    {
LABEL_9:
      SecIncrementInternalErrorCounter();
    }
    else
    {
      _mm_lfence();
      ThreadId = (unsigned __int8)PsGetThreadId(CurrentThread);
      Next = (int)ListEntry[2].Next;
      v16 = ListEntry[3].Next;
      v17 = *((_DWORD *)&ListEntry[38].Next + 2);
      Sid = *(void **)v26;
      v19 = *((_QWORD *)&ListEntry[2].Next + 1);
      v20 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
      *(_DWORD *)v23 = a7;
      *(_DWORD *)v22 = a6;
      v21 = EventDasdAccessWrite(
              EventDescriptor,
              v20,
              Next,
              v19,
              ThreadId,
              Sid,
              v17,
              (wchar_t *)P,
              a4,
              a5,
              *(_DWORD *)v22,
              v16,
              *(_DWORD *)v23);
      SecIncrementEtwCounters(v21);
    }
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( ListEntry )
      SecReleaseProcessContext(ListEntry);
    if ( v26 )
    {
      if ( v27[0] )
        ExFreePoolWithTag(v26, 0);
    }
  }
}

```

## disassembly

```asm
0x1400057a8  push    rbp
0x1400057aa  push    rbx
0x1400057ab  push    rsi
0x1400057ac  push    rdi
0x1400057ad  push    r12
0x1400057af  push    r14
0x1400057b1  push    r15
0x1400057b3  lea     rbp, [rsp-0Fh]
0x1400057b8  sub     rsp, 0A0h
0x1400057bf  mov     rax, cs:__security_cookie
0x1400057c6  xor     rax, rsp
0x1400057c9  mov     [rbp+3Fh+var_40], rax
0x1400057cd  mov     rbx, rdx
0x1400057d0  mov     [rbp+3Fh+P], 0
0x1400057d8  mov     rdx, rcx; EventDescriptor
0x1400057db  mov     [rbp+3Fh+ListEntry], 0
0x1400057e3  mov     r15, rcx
0x1400057e6  mov     [rbp+3Fh+var_50], 0
0x1400057ee  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400057f5  mov     r12, r9
0x1400057f8  mov     rdi, r8
0x1400057fb  mov     [rbp+3Fh+var_48], 0
0x1400057ff  call    cs:__imp_EtwEventEnabled
0x140005806  nop     dword ptr [rax+rax+00h]
0x14000580b  test    al, al
0x14000580d  jz      loc_14000595F
0x140005813  mov     rcx, rbx
0x140005816  call    SecFltGetRequestorProcess
0x14000581b  mov     rcx, rax
0x14000581e  lea     rdx, [rbp+3Fh+ListEntry]
0x140005822  mov     r8b, 1
0x140005825  call    SecGetProcessContextWithAssertions
0x14000582a  test    eax, eax
0x14000582c  js      loc_14000591C
0x140005832  lfence
0x140005835  mov     rbx, [rbx+8]
0x140005839  test    rbx, rbx
0x14000583c  jnz     short loc_140005847
0x14000583e  mov     rbx, gs:188h
0x140005847  mov     rdx, [rbp+3Fh+ListEntry]
0x14000584b  lea     r9, [rbp+3Fh+var_48]
0x14000584f  lea     r8, [rbp+3Fh+var_50]
0x140005853  mov     qword ptr [rsp+0D0h+var_B0], 0; __int64
0x14000585c  mov     rcx, rbx; Thread
0x14000585f  call    SecGetEffectiveTokenUser
0x140005864  test    eax, eax
0x140005866  js      loc_14000591C
0x14000586c  test    rdi, rdi
0x14000586f  jz      short loc_140005885
0x140005871  lea     rdx, [rbp+3Fh+P]
0x140005875  mov     rcx, rdi
0x140005878  call    SecUnicodeStringToString
0x14000587d  test    eax, eax
0x14000587f  js      loc_14000591C
0x140005885  lfence
0x140005888  mov     rcx, rbx; Thread
0x14000588b  call    cs:__imp_PsGetThreadId
0x140005892  nop     dword ptr [rax+rax+00h]
0x140005897  mov     rdx, [rbp+3Fh+ListEntry]
0x14000589b  mov     r14, rax
0x14000589e  mov     rcx, [rbp+3Fh+var_50]
0x1400058a2  movzx   r10d, [rbp+3Fh+arg_30]
0x1400058a7  movzx   ebx, [rbp+3Fh+arg_28]
0x1400058ab  mov     r8d, [rdx+20h]
0x1400058af  mov     r11, [rdx+30h]
0x1400058b3  mov     esi, [rdx+268h]
0x1400058b9  mov     rdi, [rcx]
0x1400058bc  mov     r9, [rdx+28h]
0x1400058c0  mov     edx, 1
0x1400058c5  mov     rcx, cs:SecData
0x1400058cc  lock xadd [rcx+150h], rdx
0x1400058d5  mov     rax, [rbp+3Fh+arg_20]
0x1400058d9  inc     rdx
0x1400058dc  mov     dword ptr [rsp+0D0h+var_70], r10d; char
0x1400058e1  mov     rcx, r15; EventDescriptor
0x1400058e4  mov     qword ptr [rsp+0D0h+var_78], r11; char
0x1400058e9  mov     dword ptr [rsp+0D0h+var_80], ebx; char
0x1400058ed  mov     qword ptr [rsp+0D0h+var_88], rax; char
0x1400058f2  mov     rax, [rbp+3Fh+P]
0x1400058f6  mov     qword ptr [rsp+0D0h+var_90], r12; char
0x1400058fb  mov     [rsp+0D0h+Str], rax; Str
0x140005900  mov     dword ptr [rsp+0D0h+var_A0], esi; char
0x140005904  mov     [rsp+0D0h+Sid], rdi; Sid
0x140005909  mov     dword ptr [rsp+0D0h+var_B0], r14d; char
0x14000590e  call    EventDasdAccessWrite
0x140005913  mov     ecx, eax
0x140005915  call    SecIncrementEtwCounters
0x14000591a  jmp     short loc_140005921
0x14000591c  call    SecIncrementInternalErrorCounter
0x140005921  mov     rcx, [rbp+3Fh+P]; P
0x140005925  test    rcx, rcx
0x140005928  jz      short loc_140005934
0x14000592a  mov     edx, 74736353h; Tag
0x14000592f  call    SecFreePool
0x140005934  mov     rcx, [rbp+3Fh+ListEntry]; ListEntry
0x140005938  test    rcx, rcx
0x14000593b  jz      short loc_140005942
0x14000593d  call    SecReleaseProcessContext
0x140005942  mov     rcx, [rbp+3Fh+var_50]; P
0x140005946  test    rcx, rcx
0x140005949  jz      short loc_14000595F
0x14000594b  cmp     [rbp+3Fh+var_48], 0
0x14000594f  jz      short loc_14000595F
0x140005951  xor     edx, edx; Tag
0x140005953  call    cs:__imp_ExFreePoolWithTag
0x14000595a  nop     dword ptr [rax+rax+00h]
0x14000595f  mov     rcx, [rbp+3Fh+var_40]
0x140005963  xor     rcx, rsp; StackCookie
0x140005966  call    __security_check_cookie
0x14000596b  add     rsp, 0A0h
0x140005972  pop     r15
0x140005974  pop     r14
0x140005976  pop     r12
0x140005978  pop     rdi
0x140005979  pop     rsi
0x14000597a  pop     rbx
0x14000597b  pop     rbp
0x14000597c  retn
```
