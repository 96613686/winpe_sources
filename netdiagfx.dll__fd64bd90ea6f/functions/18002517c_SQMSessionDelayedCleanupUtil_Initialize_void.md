# SQMSessionDelayedCleanupUtil::Initialize(void)

- ea: `0x18002517c`
- end: `0x18002522c`
- name: `?Initialize@SQMSessionDelayedCleanupUtil@@AEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(SQMSessionDelayedCleanupUtil *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800244c0`

## callees

- `0x180024458`
- `0x18002517c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800251d2`
- `KERNEL32!GetLastError` at `0x1800251f1`
- `KERNEL32!GetLastError` at `0x1800251d2`
- `KERNEL32!GetLastError` at `0x1800251f1`
- `KERNEL32!CreateEventW` at `0x18002519c`
- `KERNEL32!CreateEventW` at `0x18002519c`
- `KERNEL32!WaitForSingleObject` at `0x180025208`
- `KERNEL32!WaitForSingleObject` at `0x180025208`
- `KERNEL32!CreateThread` at `0x1800251c3`
- `KERNEL32!CreateThread` at `0x1800251c3`

## pseudocode

```c
__int64 __fastcall SQMSessionDelayedCleanupUtil::Initialize(SQMSessionDelayedCleanupUtil *this)
{
  unsigned int v2; // ebx
  void *v3; // rcx
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  signed int v7; // eax

  v2 = 0;
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    if ( !WaitForSingleObject(v3, 0) )
    {
      SQMSessionDelayedCleanupUtil::Cleanup(this);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 7) = EventW;
    if ( EventW )
    {
      Thread = CreateThread(0, 0, QueueConsumerThread, (char *)this + 16, 0, 0);
      *((_QWORD *)this + 1) = Thread;
      if ( !Thread )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        SQMSessionDelayedCleanupUtil::Cleanup(this);
      }
    }
    else
    {
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002517c  mov     [rsp+arg_0], rbx
0x180025181  push    rdi
0x180025182  sub     rsp, 30h
0x180025186  mov     rdi, rcx
0x180025189  xor     ebx, ebx
0x18002518b  mov     rcx, [rcx+8]; hHandle
0x18002518f  xor     edx, edx; dwMilliseconds
0x180025191  test    rcx, rcx
0x180025194  jnz     short loc_180025208
0x180025196  xor     r9d, r9d; lpName
0x180025199  xor     r8d, r8d; bInitialState
0x18002519c  call    cs:__imp_CreateEventW
0x1800251a2  lea     r9, [rdi+10h]; lpParameter
0x1800251a6  mov     [r9+28h], rax
0x1800251aa  test    rax, rax
0x1800251ad  jz      short loc_1800251F1
0x1800251af  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x1800251b4  lea     r8, ?QueueConsumerThread@@YAKPEAX@Z; lpStartAddress
0x1800251bb  xor     edx, edx; dwStackSize
0x1800251bd  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1800251c1  xor     ecx, ecx; lpThreadAttributes
0x1800251c3  call    cs:__imp_CreateThread
0x1800251c9  mov     [rdi+8], rax
0x1800251cd  test    rax, rax
0x1800251d0  jnz     short loc_18002521F
0x1800251d2  call    cs:__imp_GetLastError
0x1800251d8  mov     ebx, eax
0x1800251da  test    eax, eax
0x1800251dc  jle     short loc_1800251E7
0x1800251de  movzx   ebx, ax
0x1800251e1  or      ebx, 80070000h
0x1800251e7  mov     rcx, rdi; this
0x1800251ea  call    ?Cleanup@SQMSessionDelayedCleanupUtil@@AEAAXXZ; SQMSessionDelayedCleanupUtil::Cleanup(void)
0x1800251ef  jmp     short loc_18002521F
0x1800251f1  call    cs:__imp_GetLastError
0x1800251f7  mov     ebx, eax
0x1800251f9  test    eax, eax
0x1800251fb  jle     short loc_18002521F
0x1800251fd  movzx   ebx, ax
0x180025200  or      ebx, 80070000h
0x180025206  jmp     short loc_18002521F
0x180025208  call    cs:__imp_WaitForSingleObject
0x18002520e  test    eax, eax
0x180025210  jnz     short loc_18002521F
0x180025212  mov     rcx, rdi; this
0x180025215  call    ?Cleanup@SQMSessionDelayedCleanupUtil@@AEAAXXZ; SQMSessionDelayedCleanupUtil::Cleanup(void)
0x18002521a  mov     ebx, 80004005h
0x18002521f  mov     eax, ebx
0x180025221  mov     rbx, [rsp+38h+arg_0]
0x180025226  add     rsp, 30h
0x18002522a  pop     rdi
0x18002522b  retn
```
