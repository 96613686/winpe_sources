# LockMTA(void)

- ea: `0x180013864`
- end: `0x180013937`
- name: `?LockMTA@@YAXXZ`
- size: `211`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800157b0`

## callees

- `0x180013864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013878`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013878`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001391d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001391d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800138a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800138a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013926`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800138e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800138e7`

## pseudocode

```c
void LockMTA(void)
{
  HANDLE EventW; // rbx
  HANDLE v1; // rdi
  HMODULE v2; // rcx
  _QWORD Parameter[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+58h] [rbp+10h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    phModule = 0;
    if ( GetModuleHandleExW(4u, (LPCWSTR)MTAKeepAliveThread, &phModule) )
    {
      Parameter[0] = phModule;
      ThreadId = 0;
      Parameter[1] = EventW;
      v1 = CreateThread(0, 0, MTAKeepAliveThread, Parameter, 0, &ThreadId);
      if ( v1 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        CloseHandle(v1);
        v2 = 0;
        phModule = 0;
      }
      else
      {
        v2 = phModule;
      }
      if ( v2 )
        FreeLibrary(v2);
    }
    CloseHandle(EventW);
  }
}

```

## disassembly

```asm
0x180013864  mov     [rsp+arg_10], rbx
0x180013869  push    rdi
0x18001386a  sub     rsp, 40h
0x18001386e  xor     r9d, r9d; lpName
0x180013871  xor     r8d, r8d; bInitialState
0x180013874  xor     edx, edx; bManualReset
0x180013876  xor     ecx, ecx; lpEventAttributes
0x180013878  call    cs:__imp_CreateEventW
0x18001387e  mov     rbx, rax
0x180013881  test    rax, rax
0x180013884  jz      loc_18001392C
0x18001388a  lea     r8, [rsp+48h+phModule]; phModule
0x18001388f  mov     [rsp+48h+phModule], 0
0x180013898  lea     rdx, ?MTAKeepAliveThread@@YAKPEAX@Z; lpModuleName
0x18001389f  mov     ecx, 4; dwFlags
0x1800138a4  call    cs:__imp_GetModuleHandleExW
0x1800138aa  test    eax, eax
0x1800138ac  jz      short loc_180013923
0x1800138ae  mov     rax, [rsp+48h+phModule]
0x1800138b3  lea     r9, [rsp+48h+Parameter]; lpParameter
0x1800138b8  mov     [rsp+48h+Parameter], rax
0x1800138bd  lea     r8, ?MTAKeepAliveThread@@YAKPEAX@Z; lpStartAddress
0x1800138c4  lea     rax, [rsp+48h+ThreadId]
0x1800138c9  mov     [rsp+48h+ThreadId], 0
0x1800138d1  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800138d6  xor     edx, edx; dwStackSize
0x1800138d8  xor     ecx, ecx; lpThreadAttributes
0x1800138da  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800138e2  mov     [rsp+48h+var_10], rbx
0x1800138e7  call    cs:__imp_CreateThread
0x1800138ed  mov     rdi, rax
0x1800138f0  test    rax, rax
0x1800138f3  jz      short loc_180013913
0x1800138f5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800138f8  mov     rcx, rbx; hHandle
0x1800138fb  call    cs:__imp_WaitForSingleObject
0x180013901  mov     rcx, rdi; hObject
0x180013904  call    cs:__imp_CloseHandle
0x18001390a  xor     ecx, ecx
0x18001390c  mov     [rsp+48h+phModule], rcx
0x180013911  jmp     short loc_180013918
0x180013913  mov     rcx, [rsp+48h+phModule]; hLibModule
0x180013918  test    rcx, rcx
0x18001391b  jz      short loc_180013923
0x18001391d  call    cs:__imp_FreeLibrary
0x180013923  mov     rcx, rbx; hObject
0x180013926  call    cs:__imp_CloseHandle
0x18001392c  mov     rbx, [rsp+48h+arg_10]
0x180013931  add     rsp, 40h
0x180013935  pop     rdi
0x180013936  retn
```
