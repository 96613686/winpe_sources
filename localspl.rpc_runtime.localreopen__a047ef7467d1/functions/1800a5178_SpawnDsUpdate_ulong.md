# SpawnDsUpdate(ulong)

- ea: `0x1800a5178`
- end: `0x1800a5262`
- name: `?SpawnDsUpdate@@YAKK@Z`
- size: `234`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800a2628`
- `0x1800a4f0c`
- `0x1800a5530`

## callees

- `0x18000ef18`
- `0x18003ea2c`
- `0x1800a5178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a524a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a524a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a521e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a521e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a51d6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a51d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5214`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5214`
- `SPOOLSS!DllFreeSplMem` at `0x1800a5209`
- `SPOOLSS!DllFreeSplMem` at `0x1800a5209`
- `SPOOLSS!DllAllocSplMem` at `0x1800a51a4`
- `SPOOLSS!DllAllocSplMem` at `0x1800a51a4`

## string_xrefs

- `0x1800a51f1`: `Failed to start DsUpdate thread.  Error %d`
- `0x1800a51f8`: `SpawnDsUpdate`
- `0x1800a522e`: `SpawnDsUpdate`
- `0x1800a5227`: `Failed to allocate memory for DsUpdate thread data.  Error %d`

## pseudocode

```c
__int64 __fastcall SpawnDsUpdate(int a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi
  HANDLE Thread; // rax
  __int64 LastError; // rbx

  if ( ghDsUpdateThread || (unsigned __int8)IsSystemCurrentlyUpgrading() )
  {
    if ( ghUpdateNow )
      SetEvent(ghUpdateNow);
    LODWORD(LastError) = 170;
  }
  else
  {
    v2 = (_DWORD *)DllAllocSplMem(4);
    v3 = v2;
    if ( v2 )
    {
      *v2 = a1;
      Thread = CreateThread(0, 0, DsUpdate, v2, 0, &gdwDsUpdateThreadId);
      ghDsUpdateThread = Thread;
      if ( Thread )
      {
        CloseHandle(Thread);
        LODWORD(LastError) = 0;
      }
      else
      {
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SpawnDsUpdate",
          L"Failed to start DsUpdate thread.  Error %d",
          LastError);
        DllFreeSplMem(v3);
      }
    }
    else
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SpawnDsUpdate",
        L"Failed to allocate memory for DsUpdate thread data.  Error %d",
        LastError);
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800a5178  mov     [rsp+arg_0], rbx
0x1800a517d  push    rdi
0x1800a517e  sub     rsp, 30h
0x1800a5182  cmp     cs:?ghDsUpdateThread@@3PEAXEA, 0; void * ghDsUpdateThread
0x1800a518a  mov     ebx, ecx
0x1800a518c  jnz     loc_1800A523E
0x1800a5192  call    IsSystemCurrentlyUpgrading
0x1800a5197  test    al, al
0x1800a5199  jnz     loc_1800A523E
0x1800a519f  mov     ecx, 4
0x1800a51a4  call    cs:__imp_DllAllocSplMem
0x1800a51aa  mov     rdi, rax
0x1800a51ad  test    rax, rax
0x1800a51b0  jz      short loc_1800A521E
0x1800a51b2  mov     [rax], ebx
0x1800a51b4  lea     r8, ?DsUpdate@@YAKPEAK@Z; lpStartAddress
0x1800a51bb  lea     rax, ?gdwDsUpdateThreadId@@3KA; ulong gdwDsUpdateThreadId
0x1800a51c2  mov     r9, rdi; lpParameter
0x1800a51c5  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800a51ca  xor     edx, edx; dwStackSize
0x1800a51cc  xor     ecx, ecx; lpThreadAttributes
0x1800a51ce  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800a51d6  call    cs:__imp_CreateThread
0x1800a51dc  mov     cs:?ghDsUpdateThread@@3PEAXEA, rax; void * ghDsUpdateThread
0x1800a51e3  test    rax, rax
0x1800a51e6  jnz     short loc_1800A5211
0x1800a51e8  call    cs:__imp_GetLastError
0x1800a51ee  mov     r8d, eax
0x1800a51f1  lea     rdx, aFailedToStartD; "Failed to start DsUpdate thread.  Error"...
0x1800a51f8  lea     rcx, aSpawndsupdate; "SpawnDsUpdate"
0x1800a51ff  mov     ebx, eax
0x1800a5201  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a5206  mov     rcx, rdi
0x1800a5209  call    cs:__imp_DllFreeSplMem
0x1800a520f  jmp     short loc_1800A5255
0x1800a5211  mov     rcx, rax; hObject
0x1800a5214  call    cs:__imp_CloseHandle
0x1800a521a  xor     ebx, ebx
0x1800a521c  jmp     short loc_1800A5255
0x1800a521e  call    cs:__imp_GetLastError
0x1800a5224  mov     r8d, eax
0x1800a5227  lea     rdx, aFailedToAlloca_12; "Failed to allocate memory for DsUpdate "...
0x1800a522e  lea     rcx, aSpawndsupdate; "SpawnDsUpdate"
0x1800a5235  mov     ebx, eax
0x1800a5237  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a523c  jmp     short loc_1800A5255
0x1800a523e  mov     rcx, cs:?ghUpdateNow@@3PEAXEA; hEvent
0x1800a5245  test    rcx, rcx
0x1800a5248  jz      short loc_1800A5250
0x1800a524a  call    cs:__imp_SetEvent
0x1800a5250  mov     ebx, 0AAh
0x1800a5255  mov     eax, ebx
0x1800a5257  mov     rbx, [rsp+38h+arg_0]
0x1800a525c  add     rsp, 30h
0x1800a5260  pop     rdi
0x1800a5261  retn
```
