# ThreadAffinitizedWorkerThread<ProxyWindowCommands>::InitThread(void)

- ea: `0x18005e234`
- end: `0x18005e2e4`
- name: `?InitThread@?$ThreadAffinitizedWorkerThread@W4ProxyWindowCommands@@@@IEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a7480`

## callees

- `0x18005e234`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005e291`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005e291`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e259`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e272`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e259`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005e272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2c9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005e2b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005e2b6`

## pseudocode

```c
signed int __fastcall ThreadAffinitizedWorkerThread<enum ProxyWindowCommands>::InitThread(LPVOID lpParameter)
{
  signed int result; // eax
  HANDLE EventA; // rax
  HANDLE v4; // rax
  HANDLE Thread; // rax

  if ( *((_QWORD *)lpParameter + 3) )
    return -2147024809;
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)lpParameter + 4) = EventA;
  if ( EventA )
  {
    v4 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)lpParameter + 5) = v4;
    if ( v4 )
    {
      GetModuleHandleExA(4u, (LPCSTR)&g_Module, (HMODULE *)lpParameter + 2);
      Thread = CreateThread(0, 0, ThreadAffinitizedWorkerThread<enum MUTEX_COMMANDS>::WorkerThread, lpParameter, 0, 0);
      *((_QWORD *)lpParameter + 3) = Thread;
      if ( Thread )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18005e234  push    rbx
0x18005e236  sub     rsp, 30h
0x18005e23a  cmp     qword ptr [rcx+18h], 0
0x18005e23f  mov     rbx, rcx
0x18005e242  jz      short loc_18005E24F
0x18005e244  mov     eax, 80070057h
0x18005e249  add     rsp, 30h
0x18005e24d  pop     rbx
0x18005e24e  retn
0x18005e24f  xor     r9d, r9d; lpName
0x18005e252  xor     r8d, r8d; bInitialState
0x18005e255  xor     edx, edx; bManualReset
0x18005e257  xor     ecx, ecx; lpEventAttributes
0x18005e259  call    cs:__imp_CreateEventA
0x18005e25f  mov     [rbx+20h], rax
0x18005e263  test    rax, rax
0x18005e266  jz      short loc_18005E2C9
0x18005e268  xor     r9d, r9d; lpName
0x18005e26b  xor     r8d, r8d; bInitialState
0x18005e26e  xor     edx, edx; bManualReset
0x18005e270  xor     ecx, ecx; lpEventAttributes
0x18005e272  call    cs:__imp_CreateEventA
0x18005e278  mov     [rbx+28h], rax
0x18005e27c  test    rax, rax
0x18005e27f  jz      short loc_18005E2C9
0x18005e281  lea     r8, [rbx+10h]; phModule
0x18005e285  mov     ecx, 4; dwFlags
0x18005e28a  lea     rdx, ?g_Module@@3VCModule@@A; lpModuleName
0x18005e291  call    cs:__imp_GetModuleHandleExA
0x18005e297  mov     r9, rbx; lpParameter
0x18005e29a  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18005e2a3  lea     r8, ?WorkerThread@?$ThreadAffinitizedWorkerThread@W4MUTEX_COMMANDS@@@@KAKPEAX@Z; lpStartAddress
0x18005e2aa  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005e2b2  xor     edx, edx; dwStackSize
0x18005e2b4  xor     ecx, ecx; lpThreadAttributes
0x18005e2b6  call    cs:__imp_CreateThread
0x18005e2bc  mov     [rbx+18h], rax
0x18005e2c0  test    rax, rax
0x18005e2c3  jz      short loc_18005E2C9
0x18005e2c5  xor     eax, eax
0x18005e2c7  jmp     short loc_18005E249
0x18005e2c9  call    cs:__imp_GetLastError
0x18005e2cf  test    eax, eax
0x18005e2d1  jle     loc_18005E249
0x18005e2d7  movzx   eax, ax
0x18005e2da  or      eax, 80070000h
0x18005e2df  jmp     loc_18005E249
```
