# CAsyncResult::InvokeCallback(tagMFASYNCRESULT *,long)

- ea: `0x18006e9dc`
- end: `0x18006ea9d`
- name: `?InvokeCallback@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@J@Z`
- size: `193`
- prototype: `void __fastcall(IMFAsyncResult *pResult, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057d90`

## callees

- `0x18006e9dc`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ea57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ea57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ea91`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ea91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ea87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ea87`
- `MFPlat!MFPutWorkItemEx2` at `0x18006ea38`
- `MFPlat!MFPutWorkItemEx2` at `0x18006ea38`

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
0x18006e9dc  mov     [rsp+arg_8], edx
0x18006e9e0  push    rbx
0x18006e9e1  sub     rsp, 20h
0x18006e9e5  mov     rbx, rcx
0x18006e9e8  mov     dword ptr [rcx+30h], 0
0x18006e9ef  mov     rcx, [rcx+28h]
0x18006e9f3  test    rcx, rcx
0x18006e9f6  jz      short loc_18006EA44
0x18006e9f8  mov     [rsp+28h+arg_0], 0
0x18006ea00  lea     r8, [rsp+28h+arg_8]
0x18006ea05  mov     [rsp+28h+arg_8], 0
0x18006ea0d  lea     rdx, [rsp+28h+arg_0]
0x18006ea12  mov     rax, [rcx]
0x18006ea15  mov     rax, [rax+18h]
0x18006ea19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea1e  test    eax, eax
0x18006ea20  jns     short loc_18006EA2D
0x18006ea22  mov     eax, 1
0x18006ea27  mov     [rsp+28h+arg_8], eax
0x18006ea2b  jmp     short loc_18006EA31
0x18006ea2d  mov     eax, [rsp+28h+arg_8]
0x18006ea31  mov     r8, rbx; pResult
0x18006ea34  xor     edx, edx; Priority
0x18006ea36  mov     ecx, eax; dwQueue
0x18006ea38  call    cs:__imp_MFPutWorkItemEx2
0x18006ea3e  add     rsp, 20h
0x18006ea42  pop     rbx
0x18006ea43  retn
0x18006ea44  cmp     qword ptr [rbx+38h], 0
0x18006ea49  jnz     short loc_18006EA8D
0x18006ea4b  xor     r9d, r9d; lpName
0x18006ea4e  xor     r8d, r8d; bInitialState
0x18006ea51  xor     ecx, ecx; lpEventAttributes
0x18006ea53  lea     edx, [r9+1]; bManualReset
0x18006ea57  call    cs:__imp_CreateEventW
0x18006ea5d  mov     rcx, rax; hObject
0x18006ea60  test    rax, rax
0x18006ea63  jnz     short loc_18006EA7D
0x18006ea65  call    cs:__imp_GetLastError
0x18006ea6b  test    eax, eax
0x18006ea6d  jle     short loc_18006EA79
0x18006ea6f  movzx   eax, ax
0x18006ea72  or      eax, 80070000h
0x18006ea77  test    eax, eax
0x18006ea79  js      short loc_18006EA97
0x18006ea7b  jmp     short loc_18006EA8D
0x18006ea7d  xor     eax, eax
0x18006ea7f  lock cmpxchg [rbx+38h], rcx
0x18006ea85  jz      short loc_18006EA8D
0x18006ea87  call    cs:__imp_CloseHandle
0x18006ea8d  mov     rcx, [rbx+38h]; hEvent
0x18006ea91  call    cs:__imp_SetEvent
0x18006ea97  add     rsp, 20h
0x18006ea9b  pop     rbx
0x18006ea9c  retn
```
