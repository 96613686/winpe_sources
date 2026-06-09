# IASRequestThread

- ea: `0x18000cad0`
- end: `0x18000cc66`
- name: `IASRequestThread`
- size: `406`
- prototype: `BOOL __fastcall(LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000cad0`
- `0x180014ba8`
- `0x180014c04`
- `0x180017754`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18000cb6c`
- `msvcrt!_beginthreadex` at `0x18000cb6c`
- `KERNEL32!CloseHandle` at `0x18000cb7a`
- `KERNEL32!CloseHandle` at `0x18000cb7a`
- `KERNEL32!TryEnterCriticalSection` at `0x18000caf8`
- `KERNEL32!TryEnterCriticalSection` at `0x18000caf8`
- `KERNEL32!SwitchToThread` at `0x18000caef`
- `KERNEL32!SwitchToThread` at `0x18000caef`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18000cc0b`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18000cc0b`
- `KERNEL32!ResetEvent` at `0x18000cb91`
- `KERNEL32!ResetEvent` at `0x18000cb91`
- `KERNEL32!EnterCriticalSection` at `0x18000cb07`
- `KERNEL32!EnterCriticalSection` at `0x18000cb07`
- `KERNEL32!LeaveCriticalSection` at `0x18000cbf2`
- `KERNEL32!LeaveCriticalSection` at `0x18000cbf2`

## string_xrefs

- `0x18000cbc9`: `Exceeding thread limits %d`
- `0x18000cc2b`: `Dispatcher already shut down, rejecting the request`

## pseudocode

```c
BOOL __fastcall IASRequestThread(LPOVERLAPPED lpOverlapped)
{
  int v2; // ebx
  BOOL v3; // ebx
  void *v4; // rax
  int v5; // eax
  unsigned int ThrdAddr; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  while ( !TryEnterCriticalSection(&dispatcher) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(&dispatcher);
      break;
    }
    SwitchToThread();
  }
  v3 = dword_180024F40 == 0;
  if ( --dword_180024F20 >= 0 )
  {
LABEL_14:
    if ( (unsigned int)qword_180024F18 < HIDWORD(qword_180024F18) )
      goto LABEL_19;
    goto LABEL_15;
  }
  if ( (unsigned int)qword_180024F18 < HIDWORD(qword_180024F18) )
  {
    if ( !dword_180024F40 )
    {
      ThrdAddr = 0;
      v4 = (void *)_beginthreadex(0, 0, Dispatcher::startRoutine, &dispatcher, 0, &ThrdAddr);
      if ( v4 )
      {
        CloseHandle(v4);
        v5 = qword_180024F18;
        if ( !(_DWORD)qword_180024F18 )
        {
          ResetEvent(hHandle);
          v5 = qword_180024F18;
        }
        LODWORD(qword_180024F18) = v5 + 1;
        ++dword_180024F20;
      }
      goto LABEL_19;
    }
    goto LABEL_14;
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Exceeding thread limits %d");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
LABEL_19:
  LeaveCriticalSection(&dispatcher);
  if ( v3 )
    return PostQueuedCompletionStatus(CompletionPort, 0, 0, lpOverlapped);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Dispatcher already shut down, rejecting the request");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_22c5c903f1703d2be845ba71851dec7d_Traceguids, "NPSSVC");
  }
  return 0;
}

```

## disassembly

```asm
0x18000cad0  push    rbx
0x18000cad2  push    rbp
0x18000cad3  push    rdi
0x18000cad4  push    r14
0x18000cad6  sub     rsp, 38h
0x18000cada  mov     rdi, rcx
0x18000cadd  xor     ebx, ebx
0x18000cadf  lea     rbp, ?dispatcher@@3VDispatcher@@A; Dispatcher dispatcher
0x18000cae6  jmp     short loc_18000CAF5
0x18000cae8  inc     ebx
0x18000caea  cmp     ebx, 64h ; 'd'
0x18000caed  jge     short loc_18000CB04
0x18000caef  call    cs:__imp_SwitchToThread
0x18000caf5  mov     rcx, rbp; lpCriticalSection
0x18000caf8  call    cs:__imp_TryEnterCriticalSection
0x18000cafe  test    eax, eax
0x18000cb00  jz      short loc_18000CAE8
0x18000cb02  jmp     short loc_18000CB0D
0x18000cb04  mov     rcx, rbp; lpCriticalSection
0x18000cb07  call    cs:__imp_EnterCriticalSection
0x18000cb0d  xor     ebx, ebx
0x18000cb0f  cmp     cs:dword_180024F40, ebx
0x18000cb15  setz    bl
0x18000cb18  lea     r14, WPP_GLOBAL_Control
0x18000cb1f  mov     ecx, dword ptr cs:qword_180024F18+4
0x18000cb25  mov     edx, dword ptr cs:qword_180024F18
0x18000cb2b  mov     eax, cs:dword_180024F20
0x18000cb31  sub     eax, 1
0x18000cb34  mov     cs:dword_180024F20, eax
0x18000cb3a  jns     short loc_18000CBAD
0x18000cb3c  cmp     edx, ecx
0x18000cb3e  jnb     short loc_18000CBB1
0x18000cb40  test    ebx, ebx
0x18000cb42  jz      short loc_18000CBAD
0x18000cb44  mov     [rsp+58h+arg_8], 0
0x18000cb4c  lea     rax, [rsp+58h+arg_8]
0x18000cb51  mov     [rsp+58h+ThrdAddr], rax; ThrdAddr
0x18000cb56  mov     [rsp+58h+InitFlag], 0; InitFlag
0x18000cb5e  mov     r9, rbp; ArgList
0x18000cb61  lea     r8, ?startRoutine@Dispatcher@@KAIPEAX@Z; StartAddress
0x18000cb68  xor     edx, edx; StackSize
0x18000cb6a  xor     ecx, ecx; Security
0x18000cb6c  call    cs:__imp__beginthreadex
0x18000cb72  test    rax, rax
0x18000cb75  jz      short loc_18000CBEF
0x18000cb77  mov     rcx, rax; hObject
0x18000cb7a  call    cs:__imp_CloseHandle
0x18000cb80  mov     eax, dword ptr cs:qword_180024F18
0x18000cb86  test    eax, eax
0x18000cb88  jnz     short loc_18000CB9D
0x18000cb8a  mov     rcx, cs:hHandle; hEvent
0x18000cb91  call    cs:__imp_ResetEvent
0x18000cb97  mov     eax, dword ptr cs:qword_180024F18
0x18000cb9d  inc     eax
0x18000cb9f  mov     dword ptr cs:qword_180024F18, eax
0x18000cba5  inc     cs:dword_180024F20
0x18000cbab  jmp     short loc_18000CBEF
0x18000cbad  cmp     edx, ecx
0x18000cbaf  jb      short loc_18000CBEF
0x18000cbb1  mov     rax, cs:WPP_GLOBAL_Control
0x18000cbb8  cmp     rax, r14
0x18000cbbb  jz      short loc_18000CBEF
0x18000cbbd  cmp     byte ptr [rax+19h], 2
0x18000cbc1  jb      short loc_18000CBEF
0x18000cbc3  test    byte ptr [rax+1Ch], 4
0x18000cbc7  jz      short loc_18000CBEF
0x18000cbc9  lea     rcx, aExceedingThrea; "Exceeding thread limits %d"
0x18000cbd0  call    WppDbgPrint
0x18000cbd5  mov     eax, dword ptr cs:qword_180024F18
0x18000cbdb  mov     [rsp+58h+InitFlag], eax
0x18000cbdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbe6  mov     rcx, [rcx+10h]
0x18000cbea  call    WPP_SF_sd
0x18000cbef  mov     rcx, rbp; lpCriticalSection
0x18000cbf2  call    cs:__imp_LeaveCriticalSection
0x18000cbf8  test    ebx, ebx
0x18000cbfa  jz      short loc_18000CC13
0x18000cbfc  mov     r9, rdi; lpOverlapped
0x18000cbff  xor     r8d, r8d; dwCompletionKey
0x18000cc02  xor     edx, edx; dwNumberOfBytesTransferred
0x18000cc04  mov     rcx, cs:CompletionPort; CompletionPort
0x18000cc0b  call    cs:__imp_PostQueuedCompletionStatus
0x18000cc11  jmp     short loc_18000CC5C
0x18000cc13  mov     rax, cs:WPP_GLOBAL_Control
0x18000cc1a  cmp     rax, r14
0x18000cc1d  jz      short loc_18000CC5A
0x18000cc1f  cmp     byte ptr [rax+19h], 2
0x18000cc23  jb      short loc_18000CC5A
0x18000cc25  test    byte ptr [rax+1Ch], 4
0x18000cc29  jz      short loc_18000CC5A
0x18000cc2b  lea     rcx, aDispatcherAlre; "Dispatcher already shut down, rejecting"...
0x18000cc32  call    WppDbgPrint
0x18000cc37  mov     edx, 0Bh
0x18000cc3c  lea     r9, aNpssvc; "NPSSVC"
0x18000cc43  lea     r8, WPP_22c5c903f1703d2be845ba71851dec7d_Traceguids
0x18000cc4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc51  mov     rcx, [rcx+10h]
0x18000cc55  call    WPP_SF_s
0x18000cc5a  xor     eax, eax
0x18000cc5c  add     rsp, 38h
0x18000cc60  pop     r14
0x18000cc62  pop     rdi
0x18000cc63  pop     rbp
0x18000cc64  pop     rbx
0x18000cc65  retn
```
