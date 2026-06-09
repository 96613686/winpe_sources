# CAsyncResult::InvokeCallback(tagMFASYNCRESULT *,long)

- ea: `0x18007b764`
- end: `0x18007b83e`
- name: `?InvokeCallback@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@J@Z`
- size: `218`
- prototype: `void __fastcall(IMFAsyncResult *pResult, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005cf30`
- `0x18006091c`
- `0x1800685f0`
- `0x18007e5c8`
- `0x1800997f0`

## callees

- `0x18007b764`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007b7df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007b7df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007b82b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007b82b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b7f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b81b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b81b`
- `MFPlat!MFPutWorkItemEx2` at `0x18007b7b9`
- `MFPlat!MFPutWorkItemEx2` at `0x18007b7b9`

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

  LODWORD(pResult[6].lpVtbl) = a2;
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
0x18007b764  push    rbx
0x18007b766  sub     rsp, 20h
0x18007b76a  mov     rbx, rcx
0x18007b76d  mov     [rcx+30h], edx
0x18007b770  mov     rcx, [rcx+28h]
0x18007b774  test    rcx, rcx
0x18007b777  jz      short loc_18007B7CC
0x18007b779  mov     [rsp+28h+arg_0], 0
0x18007b781  lea     r8, [rsp+28h+arg_8]
0x18007b786  mov     [rsp+28h+arg_8], 0
0x18007b78e  lea     rdx, [rsp+28h+arg_0]
0x18007b793  mov     rax, [rcx]
0x18007b796  mov     rax, [rax+18h]
0x18007b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b79f  test    eax, eax
0x18007b7a1  jns     short loc_18007B7AE
0x18007b7a3  mov     eax, 1
0x18007b7a8  mov     [rsp+28h+arg_8], eax
0x18007b7ac  jmp     short loc_18007B7B2
0x18007b7ae  mov     eax, [rsp+28h+arg_8]
0x18007b7b2  mov     r8, rbx; pResult
0x18007b7b5  xor     edx, edx; Priority
0x18007b7b7  mov     ecx, eax; dwQueue
0x18007b7b9  call    cs:__imp_MFPutWorkItemEx2
0x18007b7c0  nop     dword ptr [rax+rax+00h]
0x18007b7c5  add     rsp, 20h
0x18007b7c9  pop     rbx
0x18007b7ca  retn
0x18007b7cc  cmp     qword ptr [rbx+38h], 0
0x18007b7d1  jnz     short loc_18007B827
0x18007b7d3  xor     r9d, r9d; lpName
0x18007b7d6  xor     r8d, r8d; bInitialState
0x18007b7d9  xor     ecx, ecx; lpEventAttributes
0x18007b7db  lea     edx, [r9+1]; bManualReset
0x18007b7df  call    cs:__imp_CreateEventW
0x18007b7e6  nop     dword ptr [rax+rax+00h]
0x18007b7eb  mov     rcx, rax; hObject
0x18007b7ee  test    rax, rax
0x18007b7f1  jnz     short loc_18007B811
0x18007b7f3  call    cs:__imp_GetLastError
0x18007b7fa  nop     dword ptr [rax+rax+00h]
0x18007b7ff  test    eax, eax
0x18007b801  jle     short loc_18007B80D
0x18007b803  movzx   eax, ax
0x18007b806  or      eax, 80070000h
0x18007b80b  test    eax, eax
0x18007b80d  js      short loc_18007B837
0x18007b80f  jmp     short loc_18007B827
0x18007b811  xor     eax, eax
0x18007b813  lock cmpxchg [rbx+38h], rcx
0x18007b819  jz      short loc_18007B827
0x18007b81b  call    cs:__imp_CloseHandle
0x18007b822  nop     dword ptr [rax+rax+00h]
0x18007b827  mov     rcx, [rbx+38h]; hEvent
0x18007b82b  call    cs:__imp_SetEvent
0x18007b832  nop     dword ptr [rax+rax+00h]
0x18007b837  add     rsp, 20h
0x18007b83b  pop     rbx
0x18007b83c  retn
```
