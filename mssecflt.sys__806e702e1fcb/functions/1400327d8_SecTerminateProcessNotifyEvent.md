# SecTerminateProcessNotifyEvent

- ea: `0x1400327d8`
- end: `0x1400328b1`
- name: `SecTerminateProcessNotifyEvent`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002f6d0`

## callees

- `0x14000885c`
- `0x140031924`
- `0x1400327d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14003283d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003283d`

## pseudocode

```c
void __fastcall SecTerminateProcessNotifyEvent(__int64 a1)
{
  void *Sid; // rbx
  const wchar_t *v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rax
  void **v6; // rax
  int CurrentThreadId; // eax
  unsigned int v8; // eax

  Sid = 0;
  v3 = 0;
  if ( (xmmword_14001B740 & 0x1000000) != 0 )
  {
    if ( *(_WORD *)(a1 + 152) )
      v4 = *(_QWORD *)(a1 + 160);
    else
      v4 = 0;
    v5 = *(_QWORD *)(a1 + 224);
    if ( v5 && *(_WORD *)v5 )
      v3 = *(const wchar_t **)(v5 + 8);
    v6 = *(void ***)(a1 + 296);
    if ( v6 )
      Sid = *v6;
    CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
    v8 = EventWriteTerminateProcess(
           _InterlockedIncrement64((volatile signed __int64 *)SecData + 42),
           *(_DWORD *)(a1 + 32),
           *(_QWORD *)(a1 + 40),
           CurrentThreadId,
           Sid,
           *(_DWORD *)(a1 + 616),
           v4,
           v3,
           *(_QWORD *)(a1 + 48));
    SecIncrementEtwCounters(v8);
  }
}

```

## disassembly

```asm
0x1400327d8  mov     [rsp+arg_0], rbx
0x1400327dd  mov     [rsp+arg_8], rbp
0x1400327e2  mov     [rsp+arg_10], rsi
0x1400327e7  push    rdi
0x1400327e8  sub     rsp, 50h
0x1400327ec  xor     ebx, ebx
0x1400327ee  mov     rdi, rcx
0x1400327f1  test    qword ptr cs:xmmword_14001B740, 1000000h
0x1400327fc  mov     esi, ebx
0x1400327fe  jz      loc_14003289B
0x140032804  cmp     [rcx+98h], bx
0x14003280b  jz      short loc_140032816
0x14003280d  mov     rbp, [rcx+0A0h]
0x140032814  jmp     short loc_140032819
0x140032816  mov     rbp, rbx
0x140032819  mov     rax, [rcx+0E0h]
0x140032820  test    rax, rax
0x140032823  jz      short loc_14003282E
0x140032825  cmp     [rax], bx
0x140032828  jz      short loc_14003282E
0x14003282a  mov     rsi, [rax+8]
0x14003282e  mov     rax, [rcx+128h]
0x140032835  test    rax, rax
0x140032838  jz      short loc_14003283D
0x14003283a  mov     rbx, [rax]
0x14003283d  call    cs:__imp_PsGetCurrentThreadId
0x140032844  nop     dword ptr [rax+rax+00h]
0x140032849  mov     edx, [rdi+20h]; int
0x14003284c  mov     ecx, 1
0x140032851  mov     r10, [rdi+30h]
0x140032855  mov     r11d, [rdi+268h]
0x14003285c  mov     r8, [rdi+28h]; int
0x140032860  mov     r9, cs:SecData
0x140032867  lock xadd [r9+150h], rcx
0x140032870  mov     qword ptr [rsp+58h+var_18], r10; char
0x140032875  inc     rcx; int
0x140032878  mov     [rsp+58h+var_20], rsi; __int64
0x14003287d  mov     r9d, eax; int
0x140032880  mov     [rsp+58h+var_28], rbp; __int64
0x140032885  mov     dword ptr [rsp+58h+var_30], r11d; char
0x14003288a  mov     [rsp+58h+Sid], rbx; Sid
0x14003288f  call    EventWriteTerminateProcess
0x140032894  mov     ecx, eax
0x140032896  call    SecIncrementEtwCounters
0x14003289b  mov     rbx, [rsp+58h+arg_0]
0x1400328a0  mov     rbp, [rsp+58h+arg_8]
0x1400328a5  mov     rsi, [rsp+58h+arg_10]
0x1400328aa  add     rsp, 50h
0x1400328ae  pop     rdi
0x1400328af  retn
```
