# SNI_IOCPIOQueue::Post(SOS_IOCompRequest *,ulong)

- ea: `0x10044b0e0`
- end: `0x10044b23b`
- name: `?Post@SNI_IOCPIOQueue@@UEAAKPEAVSOS_IOCompRequest@@K@Z`
- size: `347`
- prototype: `unsigned int(SNI_IOCPIOQueue *__hidden this, struct SOS_IOCompRequest *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x10043a7c4`
- `0x10043a930`
- `0x10044b0e0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x10044b147`
- `KERNEL32!PostQueuedCompletionStatus` at `0x10044b147`
- `KERNEL32!GetLastError` at `0x10044b191`
- `KERNEL32!GetLastError` at `0x10044b191`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNI_IOCPIOQueue::Post(SNI_IOCPIOQueue *this, struct _OVERLAPPED *a2, DWORD a3)
{
  DWORD v5; // ebx
  DWORD LastError; // edi
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = -1;
  v5 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E80A0[0] )
    bidScopeEnterW(&v8, off_1005E80A0[0], a2);
  if ( PostQueuedCompletionStatus(ghIoCompletionPort, a3, 0, a2) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E6730[0] )
      bidTraceW(0, 64512, off_1005E6730[0], 0);
  }
  else
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E6738[0] )
    {
      SniErrorIdFromStringId(0xC3CCu);
      bidTraceW(0, 71680, off_1005E6738[0], 9);
    }
    SNISetLastError(9, LastError, 50124);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E6740[0] )
      bidTraceW(0, 73728, off_1005E6740[0], LastError);
    v5 = LastError;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
  return v5;
}

```

## disassembly

```asm
0x10044b0e0  mov     r11, rsp
0x10044b0e3  push    rdi
0x10044b0e4  sub     rsp, 40h
0x10044b0e8  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10044b0f0  mov     [r11+8], rbx
0x10044b0f4  mov     [r11+10h], rsi
0x10044b0f8  mov     edi, r8d
0x10044b0fb  mov     rsi, rdx
0x10044b0fe  or      qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x10044b103  mov     eax, cs:_bidGblFlags
0x10044b109  mov     ecx, 20004h
0x10044b10e  and     eax, ecx
0x10044b110  xor     ebx, ebx
0x10044b112  cmp     eax, ecx
0x10044b114  jnz     short loc_10044B138
0x10044b116  mov     rax, cs:off_1005E80A0; "<SNI_IOCPIOQueue::Post|API|SNI> pOvl: %"...
0x10044b11d  test    rax, rax
0x10044b120  jz      short loc_10044B138
0x10044b122  mov     r9d, r8d
0x10044b125  mov     r8, rdx
0x10044b128  mov     rdx, cs:off_1005E80A0; "<SNI_IOCPIOQueue::Post|API|SNI> pOvl: %"...
0x10044b12f  lea     rcx, [r11+20h]
0x10044b133  call    _bidScopeEnterW
0x10044b138  mov     r9, rsi; lpOverlapped
0x10044b13b  xor     r8d, r8d; dwCompletionKey
0x10044b13e  mov     edx, edi; dwNumberOfBytesTransferred
0x10044b140  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x10044b147  call    cs:__imp_PostQueuedCompletionStatus
0x10044b14d  test    eax, eax
0x10044b14f  jz      short loc_10044B191
0x10044b151  mov     eax, cs:_bidGblFlags
0x10044b157  mov     ecx, 20002h
0x10044b15c  and     eax, ecx
0x10044b15e  cmp     eax, ecx
0x10044b160  jnz     loc_10044B21F
0x10044b166  mov     rax, cs:off_1005E6730; "<SNI_IOCPIOQueue::Post|RET|SNI> %d{WINE"...
0x10044b16d  test    rax, rax
0x10044b170  jz      loc_10044B21F
0x10044b176  xor     r9d, r9d
0x10044b179  mov     r8, cs:off_1005E6730; "<SNI_IOCPIOQueue::Post|RET|SNI> %d{WINE"...
0x10044b180  mov     edx, 0FC00h
0x10044b185  xor     ecx, ecx
0x10044b187  call    _bidTraceW
0x10044b18c  jmp     loc_10044B21F
0x10044b191  call    cs:__imp_GetLastError
0x10044b197  mov     edi, eax
0x10044b199  mov     esi, 0C3CCh
0x10044b19e  test    byte ptr cs:_bidGblFlags, 2
0x10044b1a5  jz      short loc_10044B1DB
0x10044b1a7  mov     rcx, cs:off_1005E6738; "<SNI_IOCPIOQueue::Post|ERR|SNI> Provide"...
0x10044b1ae  test    rcx, rcx
0x10044b1b1  jz      short loc_10044B1DB
0x10044b1b3  mov     ecx, esi; unsigned int
0x10044b1b5  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10044b1ba  mov     [rsp+48h+var_20], edi
0x10044b1be  mov     [rsp+48h+var_28], eax
0x10044b1c2  mov     r9d, 9
0x10044b1c8  mov     r8, cs:off_1005E6738; "<SNI_IOCPIOQueue::Post|ERR|SNI> Provide"...
0x10044b1cf  mov     edx, 11800h
0x10044b1d4  xor     ecx, ecx
0x10044b1d6  call    _bidTraceW
0x10044b1db  mov     r8d, esi
0x10044b1de  mov     edx, edi
0x10044b1e0  mov     ecx, 9
0x10044b1e5  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044b1ea  mov     eax, cs:_bidGblFlags
0x10044b1f0  mov     ecx, 20002h
0x10044b1f5  and     eax, ecx
0x10044b1f7  cmp     eax, ecx
0x10044b1f9  jnz     short loc_10044B21D
0x10044b1fb  mov     rax, cs:off_1005E6740; "<SNI_IOCPIOQueue::Post|RET|SNI> %d{WINE"...
0x10044b202  test    rax, rax
0x10044b205  jz      short loc_10044B21D
0x10044b207  mov     r9d, edi
0x10044b20a  mov     r8, cs:off_1005E6740; "<SNI_IOCPIOQueue::Post|RET|SNI> %d{WINE"...
0x10044b211  mov     edx, 12000h
0x10044b216  xor     ecx, ecx
0x10044b218  call    _bidTraceW
0x10044b21d  mov     ebx, edi
0x10044b21f  lea     rcx, [rsp+48h+arg_18]; this
0x10044b224  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10044b229  mov     eax, ebx
0x10044b22b  mov     rbx, [rsp+48h+arg_0]
0x10044b230  mov     rsi, [rsp+48h+arg_8]
0x10044b235  add     rsp, 40h
0x10044b239  pop     rdi
0x10044b23a  retn
```
