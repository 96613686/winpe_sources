# SendControlToService(SC_HANDLE__ *,ulong,ulong *)

- ea: `0x140003fec`
- end: `0x14000410b`
- name: `?SendControlToService@@YAJPEAUSC_HANDLE__@@KPEAK@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x140004628`

## callees

- `0x140001014`
- `0x140001054`
- `0x140003fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004086`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004086`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004072`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000409c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000409c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000404a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400040b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000404a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400040b7`

## pseudocode

```c
__int64 __fastcall SendControlToService(struct SC_HANDLE__ *a1, __int64 a2, unsigned int *a3)
{
  DWORD v6; // r14d
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rdi
  DWORD TickCount; // ebp
  HANDLE v10; // rax
  void *v11; // r15
  unsigned int v12; // ebx
  DWORD v13; // eax
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+78h] [rbp+10h] BYREF

  ThreadId = 0;
  if ( !a3 )
    return 2147942487LL;
  v6 = *a3;
  v7 = (volatile signed __int32 *)operator new(0x18u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 1) = 2;
    *((_DWORD *)v7 + 2) = 1;
    *((_QWORD *)v7 + 2) = a1;
    *v7 = 0;
    TickCount = GetTickCount();
    v10 = CreateThread(0, 0, ControlServiceThread, (LPVOID)v8, 0, &ThreadId);
    v11 = v10;
    if ( v10 )
    {
      if ( WaitForSingleObject(v10, v6) )
        v12 = -2147023843;
      else
        v12 = *v8;
      CloseHandle(v11);
      if ( _InterlockedExchangeAdd(v8 + 1, 0xFFFFFFFF) == 1 )
        operator delete((void *)v8);
      v13 = GetTickCount();
      if ( v13 > TickCount )
      {
        if ( v13 - TickCount > v6 )
          *a3 = 0;
        else
          *a3 += TickCount - v13;
      }
    }
    else
    {
      operator delete((void *)v8);
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return v12;
}

```

## disassembly

```asm
0x140003fec  mov     [rsp+ThreadId], edx
0x140003ff0  push    rbx
0x140003ff1  push    rbp
0x140003ff2  push    rsi
0x140003ff3  push    rdi
0x140003ff4  push    r14
0x140003ff6  push    r15
0x140003ff8  sub     rsp, 38h
0x140003ffc  mov     [rsp+68h+ThreadId], 0
0x140004004  mov     rsi, r8
0x140004007  mov     rbx, rcx
0x14000400a  test    r8, r8
0x14000400d  jnz     short loc_140004019
0x14000400f  mov     eax, 80070057h
0x140004014  jmp     loc_1400040FE
0x140004019  mov     r14d, [r8]
0x14000401c  mov     ecx, 18h; Size
0x140004021  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004026  mov     rdi, rax
0x140004029  test    rax, rax
0x14000402c  jz      loc_1400040F7
0x140004032  mov     dword ptr [rax+4], 2
0x140004039  mov     dword ptr [rax+8], 1
0x140004040  mov     [rax+10h], rbx
0x140004044  mov     dword ptr [rax], 0
0x14000404a  call    cs:__imp_GetTickCount
0x140004050  mov     r9, rdi; lpParameter
0x140004053  lea     r8, ControlServiceThread; lpStartAddress
0x14000405a  mov     ebp, eax
0x14000405c  xor     edx, edx; dwStackSize
0x14000405e  lea     rax, [rsp+68h+ThreadId]
0x140004063  xor     ecx, ecx; lpThreadAttributes
0x140004065  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x14000406a  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x140004072  call    cs:__imp_CreateThread
0x140004078  mov     r15, rax
0x14000407b  test    rax, rax
0x14000407e  jz      short loc_1400040D8
0x140004080  mov     edx, r14d; dwMilliseconds
0x140004083  mov     rcx, rax; hHandle
0x140004086  call    cs:__imp_WaitForSingleObject
0x14000408c  test    eax, eax
0x14000408e  jnz     short loc_140004094
0x140004090  mov     ebx, [rdi]
0x140004092  jmp     short loc_140004099
0x140004094  mov     ebx, 8007041Dh
0x140004099  mov     rcx, r15; hObject
0x14000409c  call    cs:__imp_CloseHandle
0x1400040a2  or      eax, 0FFFFFFFFh
0x1400040a5  lock xadd [rdi+4], eax
0x1400040aa  cmp     eax, 1
0x1400040ad  jnz     short loc_1400040B7
0x1400040af  mov     rcx, rdi; Block
0x1400040b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400040b7  call    cs:__imp_GetTickCount
0x1400040bd  cmp     eax, ebp
0x1400040bf  jbe     short loc_1400040FC
0x1400040c1  mov     ecx, eax
0x1400040c3  sub     ecx, ebp
0x1400040c5  cmp     ecx, r14d
0x1400040c8  ja      short loc_1400040D0
0x1400040ca  sub     ebp, eax
0x1400040cc  add     [rsi], ebp
0x1400040ce  jmp     short loc_1400040FC
0x1400040d0  mov     dword ptr [rsi], 0
0x1400040d6  jmp     short loc_1400040FC
0x1400040d8  mov     rcx, rdi; Block
0x1400040db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400040e0  call    cs:__imp_GetLastError
0x1400040e6  mov     ebx, eax
0x1400040e8  test    eax, eax
0x1400040ea  jle     short loc_1400040FC
0x1400040ec  movzx   ebx, ax
0x1400040ef  or      ebx, 80070000h
0x1400040f5  jmp     short loc_1400040FC
0x1400040f7  mov     ebx, 80070008h
0x1400040fc  mov     eax, ebx
0x1400040fe  add     rsp, 38h
0x140004102  pop     r15
0x140004104  pop     r14
0x140004106  pop     rdi
0x140004107  pop     rsi
0x140004108  pop     rbp
0x140004109  pop     rbx
0x14000410a  retn
```
