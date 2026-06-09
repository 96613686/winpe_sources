# CreateToBeRunJobThread(HINSTANCE__ * *)

- ea: `0x180002820`
- end: `0x1800028ea`
- name: `?CreateToBeRunJobThread@@YAHPEAPEAUHINSTANCE__@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800068f0`

## callees

- `0x180002820`
- `0x180004180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002847`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180002847`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000288e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000288e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000289c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000289c`

## pseudocode

```c
__int64 __fastcall CreateToBeRunJobThread(HINSTANCE *a1)
{
  HANDLE v2; // rax
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  if ( hToBeRunJobEvent )
    return 1;
  ThreadId = 0;
  hToBeRunJobEvent = CreateEventA(0, 0, 0, 0);
  if ( hToBeRunJobEvent )
  {
    if ( !hToBeRunJobModule )
    {
      hToBeRunJobModule = *a1;
      *a1 = 0;
    }
    v2 = CreateThread(0, 0x5000u, (LPTHREAD_START_ROUTINE)ToBeRunJobThreadProc, 0, 0, &ThreadId);
    if ( v2 )
    {
      CloseHandle(v2);
      return 1;
    }
    I_UrlCacheCloseHandle(hToBeRunJobEvent);
    hToBeRunJobEvent = 0;
    if ( !*a1 )
    {
      *a1 = hToBeRunJobModule;
      hToBeRunJobModule = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002820  mov     [rsp+arg_0], rbx
0x180002825  push    rdi
0x180002826  sub     rsp, 30h
0x18000282a  cmp     cs:?hToBeRunJobEvent@@3PEAXEA, 0; void * hToBeRunJobEvent
0x180002832  mov     rbx, rcx
0x180002835  jnz     short loc_1800028A2
0x180002837  xor     edi, edi
0x180002839  xor     r9d, r9d; lpName
0x18000283c  xor     r8d, r8d; bInitialState
0x18000283f  mov     [rsp+38h+ThreadId], edi
0x180002843  xor     edx, edx; bManualReset
0x180002845  xor     ecx, ecx; lpEventAttributes
0x180002847  call    cs:__imp_CreateEventA
0x18000284d  mov     cs:?hToBeRunJobEvent@@3PEAXEA, rax; void * hToBeRunJobEvent
0x180002854  test    rax, rax
0x180002857  jz      short loc_1800028CA
0x180002859  cmp     cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * hToBeRunJobModule
0x180002860  jnz     short loc_18000286F
0x180002862  mov     rax, [rbx]
0x180002865  mov     cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hToBeRunJobModule
0x18000286c  mov     [rbx], rdi
0x18000286f  lea     rax, [rsp+38h+ThreadId]
0x180002874  xor     r9d, r9d; lpParameter
0x180002877  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000287c  lea     r8, ?ToBeRunJobThreadProc@@YAKPEAX@Z; lpStartAddress
0x180002883  mov     edx, 5000h; dwStackSize
0x180002888  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x18000288c  xor     ecx, ecx; lpThreadAttributes
0x18000288e  call    cs:__imp_CreateThread
0x180002894  test    rax, rax
0x180002897  jz      short loc_1800028B2
0x180002899  mov     rcx, rax; hObject
0x18000289c  call    cs:__imp_CloseHandle
0x1800028a2  mov     eax, 1
0x1800028a7  mov     rbx, [rsp+38h+arg_0]
0x1800028ac  add     rsp, 30h
0x1800028b0  pop     rdi
0x1800028b1  retn
0x1800028b2  mov     rcx, cs:?hToBeRunJobEvent@@3PEAXEA; hObject
0x1800028b9  call    I_UrlCacheCloseHandle
0x1800028be  mov     cs:?hToBeRunJobEvent@@3PEAXEA, rdi; void * hToBeRunJobEvent
0x1800028c5  cmp     [rbx], rdi
0x1800028c8  jz      short loc_1800028D7
0x1800028ca  mov     rbx, [rsp+38h+arg_0]
0x1800028cf  mov     eax, edi
0x1800028d1  add     rsp, 30h
0x1800028d5  pop     rdi
0x1800028d6  retn
0x1800028d7  mov     rax, cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hToBeRunJobModule
0x1800028de  mov     [rbx], rax
0x1800028e1  mov     cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * hToBeRunJobModule
0x1800028e8  jmp     short loc_1800028CA
```
