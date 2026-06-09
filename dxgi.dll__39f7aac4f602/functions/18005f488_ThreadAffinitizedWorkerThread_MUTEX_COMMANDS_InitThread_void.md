# ThreadAffinitizedWorkerThread<MUTEX_COMMANDS>::InitThread(void)

- ea: `0x18005f488`
- end: `0x18005f534`
- name: `?InitThread@?$ThreadAffinitizedWorkerThread@W4MUTEX_COMMANDS@@@@IEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180081180`

## callees

- `0x18005f488`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005f4f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005f4f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005f4ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005f4d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005f4ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005f4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005f51d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005f51d`

## pseudocode

```c
signed int __fastcall ThreadAffinitizedWorkerThread<enum MUTEX_COMMANDS>::InitThread(LPVOID lpParameter)
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
0x18005f488  push    rbx
0x18005f48a  sub     rsp, 30h
0x18005f48e  cmp     qword ptr [rcx+18h], 0
0x18005f493  mov     rbx, rcx
0x18005f496  jz      short loc_18005F4A2
0x18005f498  mov     eax, 80070057h
0x18005f49d  jmp     loc_18005F52E
0x18005f4a2  xor     r9d, r9d; lpName
0x18005f4a5  xor     r8d, r8d; bInitialState
0x18005f4a8  xor     edx, edx; bManualReset
0x18005f4aa  xor     ecx, ecx; lpEventAttributes
0x18005f4ac  call    cs:__imp_CreateEventA
0x18005f4b2  mov     [rbx+20h], rax
0x18005f4b6  test    rax, rax
0x18005f4b9  jnz     short loc_18005F4CF
0x18005f4bb  call    cs:__imp_GetLastError
0x18005f4c1  test    eax, eax
0x18005f4c3  jle     short loc_18005F52E
0x18005f4c5  movzx   eax, ax
0x18005f4c8  or      eax, 80070000h
0x18005f4cd  jmp     short loc_18005F52E
0x18005f4cf  xor     r9d, r9d; lpName
0x18005f4d2  xor     r8d, r8d; bInitialState
0x18005f4d5  xor     edx, edx; bManualReset
0x18005f4d7  xor     ecx, ecx; lpEventAttributes
0x18005f4d9  call    cs:__imp_CreateEventA
0x18005f4df  mov     [rbx+28h], rax
0x18005f4e3  test    rax, rax
0x18005f4e6  jz      short loc_18005F4BB
0x18005f4e8  lea     r8, [rbx+10h]; phModule
0x18005f4ec  mov     ecx, 4; dwFlags
0x18005f4f1  lea     rdx, ?g_Module@@3VCModule@@A; lpModuleName
0x18005f4f8  call    cs:__imp_GetModuleHandleExA
0x18005f4fe  mov     r9, rbx; lpParameter
0x18005f501  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18005f50a  lea     r8, ?WorkerThread@?$ThreadAffinitizedWorkerThread@W4MUTEX_COMMANDS@@@@KAKPEAX@Z; lpStartAddress
0x18005f511  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005f519  xor     edx, edx; dwStackSize
0x18005f51b  xor     ecx, ecx; lpThreadAttributes
0x18005f51d  call    cs:__imp_CreateThread
0x18005f523  mov     [rbx+18h], rax
0x18005f527  test    rax, rax
0x18005f52a  jz      short loc_18005F4BB
0x18005f52c  xor     eax, eax
0x18005f52e  add     rsp, 30h
0x18005f532  pop     rbx
0x18005f533  retn
```
