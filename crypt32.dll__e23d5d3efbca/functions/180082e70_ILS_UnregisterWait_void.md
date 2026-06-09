# ILS_UnregisterWait(void *)

- ea: `0x180082e70`
- end: `0x180082f09`
- name: `?ILS_UnregisterWait@@YAHPEAX@Z`
- size: `153`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180082bd0`
- `0x180086ca0`

## callees

- `0x180028d60`
- `0x180082e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180082ed6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180082ed6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180082ee4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180082ee4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18011b9e3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18011b9e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180082e80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180082e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b9f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b9f6`

## pseudocode

```c
__int64 __fastcall ILS_UnregisterWait(HLOCAL hMem)
{
  int v1; // ebx
  __int64 i; // rbx
  void *v4; // rcx
  __int64 v6; // rax
  void *v7; // rcx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  v1 = *((_DWORD *)hMem + 2);
  if ( v1 != GetCurrentThreadId() )
  {
    *(_OWORD *)Handles = 0;
    *((_QWORD *)hMem + 7) = CreateEventA(0, 0, 0, 0);
    SetEvent(*((HANDLE *)hMem + 2));
    Handles[0] = *(HANDLE *)hMem;
    v6 = *((_QWORD *)hMem + 7);
    if ( v6 )
      Handles[1] = *((HANDLE *)hMem + 7);
    WaitForMultipleObjectsEx((v6 != 0) + 1, Handles, 0, 0xFFFFFFFF, 0);
    v7 = (void *)*((_QWORD *)hMem + 7);
    if ( v7 )
      CloseHandle(v7);
  }
  CloseHandle(*(HANDLE *)hMem);
  for ( i = 0; i != 2; ++i )
  {
    v4 = (void *)*((_QWORD *)hMem + i + 2);
    if ( v4 )
      CloseHandle(v4);
  }
  PkiDefaultCryptFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x180082e70  mov     [rsp+arg_0], rbx
0x180082e75  push    rdi
0x180082e76  sub     rsp, 40h
0x180082e7a  mov     ebx, [rcx+8]
0x180082e7d  mov     rdi, rcx
0x180082e80  call    cs:__imp_GetCurrentThreadId
0x180082e86  cmp     ebx, eax
0x180082e88  jnz     short loc_180082EC4
0x180082e8a  mov     rcx, [rdi]; hObject
0x180082e8d  call    cs:__imp_CloseHandle
0x180082e93  xor     ebx, ebx
0x180082e95  mov     rcx, [rdi+rbx*8+10h]; hObject
0x180082e9a  test    rcx, rcx
0x180082e9d  jz      short loc_180082EA5
0x180082e9f  call    cs:__imp_CloseHandle
0x180082ea5  inc     rbx
0x180082ea8  cmp     rbx, 2
0x180082eac  jnz     short loc_180082E95
0x180082eae  mov     rcx, rdi; hMem
0x180082eb1  call    PkiDefaultCryptFree
0x180082eb6  lea     eax, [rbx-1]
0x180082eb9  mov     rbx, [rsp+48h+arg_0]
0x180082ebe  add     rsp, 40h
0x180082ec2  pop     rdi
0x180082ec3  retn
0x180082ec4  xorps   xmm0, xmm0
0x180082ec7  xor     r9d, r9d; lpName
0x180082eca  xor     r8d, r8d; bInitialState
0x180082ecd  xor     edx, edx; bManualReset
0x180082ecf  xor     ecx, ecx; lpEventAttributes
0x180082ed1  movups  xmmword ptr [rsp+48h+Handles], xmm0
0x180082ed6  call    cs:__imp_CreateEventA
0x180082edc  mov     [rdi+38h], rax
0x180082ee0  mov     rcx, [rdi+10h]; hEvent
0x180082ee4  call    cs:__imp_SetEvent
0x180082eea  mov     rax, [rdi]
0x180082eed  mov     [rsp+48h+Handles], rax
0x180082ef2  mov     rax, [rdi+38h]
0x180082ef6  test    rax, rax
0x180082ef9  jz      loc_18011B9C6
0x180082eff  mov     [rsp+48h+Handles+8], rax
0x180082f04  jmp     loc_18011B9C6
0x18011b9c6  neg     rax
0x18011b9c9  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18011b9d1  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18011b9d6  sbb     ecx, ecx
0x18011b9d8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18011b9dc  neg     ecx
0x18011b9de  xor     r8d, r8d; bWaitAll
0x18011b9e1  inc     ecx; nCount
0x18011b9e3  call    cs:__imp_WaitForMultipleObjectsEx
0x18011b9e9  mov     rcx, [rdi+38h]; hObject
0x18011b9ed  test    rcx, rcx
0x18011b9f0  jz      loc_180082E8A
0x18011b9f6  call    cs:__imp_CloseHandle
0x18011b9fc  nop
0x18011b9fd  jmp     loc_180082E8A
```
