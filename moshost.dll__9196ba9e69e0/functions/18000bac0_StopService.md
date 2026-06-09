# StopService

- ea: `0x18000bac0`
- end: `0x18000bc14`
- name: `StopService`
- size: `340`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18000bac0`
- `0x18000bc1c`
- `0x18000bcc0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bbef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bbef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bb9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bb9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbbe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000bbdb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000bbdb`

## pseudocode

```c
__int64 StopService()
{
  FARPROC ProcAddress; // rax
  void (__fastcall *v1)(__int64); // rbx
  DWORD v2; // ebx

  if ( qword_180018650 )
  {
    ProcAddress = GetProcAddress(hModule, "PowerSettingUnregisterNotification");
    v1 = (void (__fastcall *)(__int64))ProcAddress;
    if ( ProcAddress )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(qword_180018650);
      v1(qword_180018600);
      v1(qword_180018660);
      v1(qword_180018608);
      v1(qword_180018620);
      v1(qword_180018658);
      v1(qword_180018610);
      qword_180018650 = 0;
      qword_180018600 = 0;
      qword_180018660 = 0;
      qword_180018608 = 0;
      qword_180018620 = 0;
      qword_180018658 = 0;
      qword_180018610 = 0;
    }
  }
  if ( hModule )
  {
    FreeLibrary(hModule);
    hModule = 0;
  }
  v2 = UninitializeService(0);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  qword_180018668 = 0;
  UnregisterWaitEx(WaitHandle, 0);
  WaitHandle = 0;
  free(Block);
  Block = 0;
  return SvcFrameworkUpdateServiceStatus(1u, v2, 0);
}

```

## disassembly

```asm
0x18000bac0  mov     [rsp+arg_0], rbx
0x18000bac5  push    rdi
0x18000bac6  sub     rsp, 20h
0x18000baca  xor     edi, edi
0x18000bacc  cmp     cs:qword_180018650, rdi
0x18000bad3  jz      loc_18000BB90
0x18000bad9  mov     rcx, cs:hModule; hModule
0x18000bae0  lea     rdx, aPowersettingun; "PowerSettingUnregisterNotification"
0x18000bae7  call    cs:__imp_GetProcAddress
0x18000baed  mov     rbx, rax
0x18000baf0  test    rax, rax
0x18000baf3  jz      loc_18000BB90
0x18000baf9  mov     rcx, cs:qword_180018650
0x18000bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb05  mov     rcx, cs:qword_180018600
0x18000bb0c  mov     rax, rbx
0x18000bb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb14  mov     rcx, cs:qword_180018660
0x18000bb1b  mov     rax, rbx
0x18000bb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb23  mov     rcx, cs:qword_180018608
0x18000bb2a  mov     rax, rbx
0x18000bb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb32  mov     rcx, cs:qword_180018620
0x18000bb39  mov     rax, rbx
0x18000bb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb41  mov     rcx, cs:qword_180018658
0x18000bb48  mov     rax, rbx
0x18000bb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb50  mov     rcx, cs:qword_180018610
0x18000bb57  mov     rax, rbx
0x18000bb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5f  mov     cs:qword_180018650, rdi
0x18000bb66  mov     cs:qword_180018600, rdi
0x18000bb6d  mov     cs:qword_180018660, rdi
0x18000bb74  mov     cs:qword_180018608, rdi
0x18000bb7b  mov     cs:qword_180018620, rdi
0x18000bb82  mov     cs:qword_180018658, rdi
0x18000bb89  mov     cs:qword_180018610, rdi
0x18000bb90  mov     rcx, cs:hModule; hLibModule
0x18000bb97  test    rcx, rcx
0x18000bb9a  jz      short loc_18000BBA9
0x18000bb9c  call    cs:__imp_FreeLibrary
0x18000bba2  mov     cs:hModule, rdi
0x18000bba9  xor     ecx, ecx; int
0x18000bbab  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x18000bbb0  mov     rcx, cs:hObject; hObject
0x18000bbb7  mov     ebx, eax
0x18000bbb9  test    rcx, rcx
0x18000bbbc  jz      short loc_18000BBCB
0x18000bbbe  call    cs:__imp_CloseHandle
0x18000bbc4  mov     cs:hObject, rdi
0x18000bbcb  mov     rcx, cs:WaitHandle; WaitHandle
0x18000bbd2  xor     edx, edx; CompletionEvent
0x18000bbd4  mov     cs:qword_180018668, rdi
0x18000bbdb  call    cs:__imp_UnregisterWaitEx
0x18000bbe1  mov     rcx, cs:Block; Block
0x18000bbe8  mov     cs:WaitHandle, rdi
0x18000bbef  call    cs:__imp_free
0x18000bbf5  xor     r8d, r8d; unsigned int
0x18000bbf8  mov     cs:Block, rdi
0x18000bbff  mov     edx, ebx; unsigned int
0x18000bc01  lea     ecx, [r8+1]; unsigned int
0x18000bc05  mov     rbx, [rsp+28h+arg_0]
0x18000bc0a  add     rsp, 20h
0x18000bc0e  pop     rdi
0x18000bc0f  jmp     ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
```
