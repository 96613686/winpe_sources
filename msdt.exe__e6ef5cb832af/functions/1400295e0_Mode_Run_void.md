# Mode::Run(void)

- ea: `0x1400295e0`
- end: `0x14002971e`
- name: `?Run@Mode@@UEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(Mode *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140028a80`
- `0x140028cb0`
- `0x140029230`
- `0x140029730`
- `0x140029a20`

## callees

- `0x1400039b1`
- `0x140020420`
- `0x1400295e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140029638`
- `KERNEL32!GetLastError` at `0x1400296aa`
- `KERNEL32!GetLastError` at `0x1400296cd`
- `KERNEL32!GetLastError` at `0x140029638`
- `KERNEL32!GetLastError` at `0x1400296aa`
- `KERNEL32!GetLastError` at `0x1400296cd`
- `KERNEL32!CreateEventW` at `0x140029616`
- `KERNEL32!CreateEventW` at `0x140029616`
- `KERNEL32!CreateThread` at `0x14002968d`
- `KERNEL32!CreateThread` at `0x14002968d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mode::Run(Mode *this)
{
  __int64 i; // rbx
  char *EventW; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v6; // r9d
  HANDLE Thread; // rax
  signed int v8; // eax
  signed int v9; // eax

  memset_0(&g_EventsToWorker, 0, 0xE0u);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    EventW = (char *)CreateEventW(0, 0, 0, 0);
    if ( (unsigned int)i >= 0x1C )
      break;
    *(&g_EventsToWorker + i) = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = 52;
LABEL_17:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::Run", v6, v5);
      return v5;
    }
  }
  g_ProgressPageLoaded = EventW;
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = 56;
    goto LABEL_17;
  }
  Thread = CreateThread(0, 0, WorkerThread, 0, 0, 0);
  *((_QWORD *)this + 3) = Thread;
  if ( !Thread || (v5 = 0, Thread == (HANDLE)-1LL) )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = 65;
    goto LABEL_17;
  }
  return v5;
}

```

## disassembly

```asm
0x1400295e0  mov     [rsp+arg_0], rbx
0x1400295e5  mov     [rsp+arg_8], rdi
0x1400295ea  push    r14
0x1400295ec  sub     rsp, 30h
0x1400295f0  mov     rdi, rcx
0x1400295f3  lea     r14, ?g_EventsToWorker@@3PAPEAXA; void * near * g_EventsToWorker
0x1400295fa  mov     rcx, r14; void *
0x1400295fd  xor     edx, edx; Val
0x1400295ff  mov     r8d, 0E0h; Size
0x140029605  call    memset_0
0x14002960a  xor     ebx, ebx
0x14002960c  xor     r9d, r9d; lpName
0x14002960f  xor     r8d, r8d; bInitialState
0x140029612  xor     edx, edx; bManualReset
0x140029614  xor     ecx, ecx; lpEventAttributes
0x140029616  call    cs:__imp_CreateEventW
0x14002961d  nop     dword ptr [rax+rax+00h]
0x140029622  cmp     ebx, 1Ch
0x140029625  jnb     short loc_14002965E
0x140029627  mov     [r14+rbx*8], rax
0x14002962b  dec     rax
0x14002962e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029632  ja      short loc_140029638
0x140029634  inc     ebx
0x140029636  jmp     short loc_14002960C
0x140029638  call    cs:__imp_GetLastError
0x14002963f  nop     dword ptr [rax+rax+00h]
0x140029644  mov     ebx, eax
0x140029646  test    eax, eax
0x140029648  jle     short loc_140029653
0x14002964a  movzx   ebx, ax
0x14002964d  or      ebx, 80070000h
0x140029653  mov     r9d, 34h ; '4'
0x140029659  jmp     loc_1400296EE
0x14002965e  mov     cs:?g_ProgressPageLoaded@@3PEAXEA, rax; void * g_ProgressPageLoaded
0x140029665  dec     rax
0x140029668  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002966c  ja      short loc_1400296CD
0x14002966e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140029677  lea     r8, ?WorkerThread@@YAKPEAX@Z; lpStartAddress
0x14002967e  xor     r9d, r9d; lpParameter
0x140029681  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140029689  xor     edx, edx; dwStackSize
0x14002968b  xor     ecx, ecx; lpThreadAttributes
0x14002968d  call    cs:__imp_CreateThread
0x140029694  nop     dword ptr [rax+rax+00h]
0x140029699  mov     [rdi+18h], rax
0x14002969d  test    rax, rax
0x1400296a0  jz      short loc_1400296AA
0x1400296a2  xor     ebx, ebx
0x1400296a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400296a8  jnz     short loc_14002970A
0x1400296aa  call    cs:__imp_GetLastError
0x1400296b1  nop     dword ptr [rax+rax+00h]
0x1400296b6  mov     ebx, eax
0x1400296b8  test    eax, eax
0x1400296ba  jle     short loc_1400296C5
0x1400296bc  movzx   ebx, ax
0x1400296bf  or      ebx, 80070000h
0x1400296c5  mov     r9d, 41h ; 'A'
0x1400296cb  jmp     short loc_1400296EE
0x1400296cd  call    cs:__imp_GetLastError
0x1400296d4  nop     dword ptr [rax+rax+00h]
0x1400296d9  mov     ebx, eax
0x1400296db  test    eax, eax
0x1400296dd  jle     short loc_1400296E8
0x1400296df  movzx   ebx, ax
0x1400296e2  or      ebx, 80070000h
0x1400296e8  mov     r9d, 38h ; '8'
0x1400296ee  lea     r8, aModeRun; "Mode::Run"
0x1400296f5  mov     [rsp+38h+dwCreationFlags], ebx
0x1400296f9  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140029700  mov     ecx, 1; Level
0x140029705  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002970a  mov     rdi, [rsp+38h+arg_8]
0x14002970f  mov     eax, ebx
0x140029711  mov     rbx, [rsp+38h+arg_0]
0x140029716  add     rsp, 30h
0x14002971a  pop     r14
0x14002971c  retn
```
