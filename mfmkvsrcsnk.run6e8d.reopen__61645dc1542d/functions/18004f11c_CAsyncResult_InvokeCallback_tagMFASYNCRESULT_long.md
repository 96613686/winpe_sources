# CAsyncResult::InvokeCallback(tagMFASYNCRESULT *,long)

- ea: `0x18004f11c`
- end: `0x18004f1dd`
- name: `?InvokeCallback@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@J@Z`
- size: `193`
- prototype: `void __fastcall(IMFAsyncResult *pResult, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ac70`

## callees

- `0x18004f11c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f1d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f1d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f197`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f1c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f1c7`
- `MFPlat!MFPutWorkItemEx2` at `0x18004f178`
- `MFPlat!MFPutWorkItemEx2` at `0x18004f178`

## pseudocode

```c
void __fastcall CAsyncResult::InvokeCallback(IMFAsyncResult *pResult, int a2)
{
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  DWORD v4; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v7; // sf
  int v8; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = a2;
  LODWORD(pResult[6].lpVtbl) = 0;
  lpVtbl = pResult[5].lpVtbl;
  if ( lpVtbl )
  {
    v8 = 0;
    v9 = 0;
    if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
           lpVtbl,
           &v8,
           &v9) >= 0 )
    {
      v4 = v9;
    }
    else
    {
      v4 = 1;
      v9 = 1;
    }
    MFPutWorkItemEx2(v4, 0, pResult);
    return;
  }
  if ( pResult[7].lpVtbl )
    goto LABEL_14;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&pResult[7], (signed __int64)EventW, 0) )
      CloseHandle(EventW);
    goto LABEL_14;
  }
  LastError = GetLastError();
  v7 = LastError < 0;
  if ( LastError > 0 )
    v7 = 1;
  if ( !v7 )
LABEL_14:
    SetEvent(pResult[7].lpVtbl);
}

```

## disassembly

```asm
0x18004f11c  mov     [rsp+arg_8], edx
0x18004f120  push    rbx
0x18004f121  sub     rsp, 20h
0x18004f125  mov     rbx, rcx
0x18004f128  mov     dword ptr [rcx+30h], 0
0x18004f12f  mov     rcx, [rcx+28h]
0x18004f133  test    rcx, rcx
0x18004f136  jz      short loc_18004F184
0x18004f138  mov     [rsp+28h+arg_0], 0
0x18004f140  lea     r8, [rsp+28h+arg_8]
0x18004f145  mov     [rsp+28h+arg_8], 0
0x18004f14d  lea     rdx, [rsp+28h+arg_0]
0x18004f152  mov     rax, [rcx]
0x18004f155  mov     rax, [rax+18h]
0x18004f159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f15e  test    eax, eax
0x18004f160  jns     short loc_18004F16D
0x18004f162  mov     eax, 1
0x18004f167  mov     [rsp+28h+arg_8], eax
0x18004f16b  jmp     short loc_18004F171
0x18004f16d  mov     eax, [rsp+28h+arg_8]
0x18004f171  mov     r8, rbx; pResult
0x18004f174  xor     edx, edx; Priority
0x18004f176  mov     ecx, eax; dwQueue
0x18004f178  call    cs:__imp_MFPutWorkItemEx2
0x18004f17e  add     rsp, 20h
0x18004f182  pop     rbx
0x18004f183  retn
0x18004f184  cmp     qword ptr [rbx+38h], 0
0x18004f189  jnz     short loc_18004F1CD
0x18004f18b  xor     r9d, r9d; lpName
0x18004f18e  xor     r8d, r8d; bInitialState
0x18004f191  xor     ecx, ecx; lpEventAttributes
0x18004f193  lea     edx, [r9+1]; bManualReset
0x18004f197  call    cs:__imp_CreateEventW
0x18004f19d  mov     rcx, rax; hObject
0x18004f1a0  test    rax, rax
0x18004f1a3  jnz     short loc_18004F1BD
0x18004f1a5  call    cs:__imp_GetLastError
0x18004f1ab  test    eax, eax
0x18004f1ad  jle     short loc_18004F1B9
0x18004f1af  movzx   eax, ax
0x18004f1b2  or      eax, 80070000h
0x18004f1b7  test    eax, eax
0x18004f1b9  js      short loc_18004F1D7
0x18004f1bb  jmp     short loc_18004F1CD
0x18004f1bd  xor     eax, eax
0x18004f1bf  lock cmpxchg [rbx+38h], rcx
0x18004f1c5  jz      short loc_18004F1CD
0x18004f1c7  call    cs:__imp_CloseHandle
0x18004f1cd  mov     rcx, [rbx+38h]; hEvent
0x18004f1d1  call    cs:__imp_SetEvent
0x18004f1d7  add     rsp, 20h
0x18004f1db  pop     rbx
0x18004f1dc  retn
```
