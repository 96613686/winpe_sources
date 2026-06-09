# CAsyncResult::InvokeCallback(tagMFASYNCRESULT *,long)

- ea: `0x18005131c`
- end: `0x1800513fd`
- name: `?InvokeCallback@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@J@Z`
- size: `225`
- prototype: `void __fastcall(IMFAsyncResult *pResult, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x18005131c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800513ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800513ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005139e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005139e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800513da`
- `MFPlat!MFPutWorkItemEx2` at `0x180051378`
- `MFPlat!MFPutWorkItemEx2` at `0x180051378`

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
0x18005131c  mov     [rsp+arg_8], edx
0x180051320  push    rbx
0x180051321  sub     rsp, 20h
0x180051325  mov     rbx, rcx
0x180051328  mov     dword ptr [rcx+30h], 0
0x18005132f  mov     rcx, [rcx+28h]
0x180051333  test    rcx, rcx
0x180051336  jz      short loc_18005138B
0x180051338  mov     [rsp+28h+arg_0], 0
0x180051340  lea     r8, [rsp+28h+arg_8]
0x180051345  mov     [rsp+28h+arg_8], 0
0x18005134d  lea     rdx, [rsp+28h+arg_0]
0x180051352  mov     rax, [rcx]
0x180051355  mov     rax, [rax+18h]
0x180051359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005135e  test    eax, eax
0x180051360  jns     short loc_18005136D
0x180051362  mov     eax, 1
0x180051367  mov     [rsp+28h+arg_8], eax
0x18005136b  jmp     short loc_180051371
0x18005136d  mov     eax, [rsp+28h+arg_8]
0x180051371  mov     r8, rbx; pResult
0x180051374  xor     edx, edx; Priority
0x180051376  mov     ecx, eax; dwQueue
0x180051378  call    cs:__imp_MFPutWorkItemEx2
0x18005137f  nop     dword ptr [rax+rax+00h]
0x180051384  add     rsp, 20h
0x180051388  pop     rbx
0x180051389  retn
0x18005138b  cmp     qword ptr [rbx+38h], 0
0x180051390  jnz     short loc_1800513E6
0x180051392  xor     r9d, r9d; lpName
0x180051395  xor     r8d, r8d; bInitialState
0x180051398  xor     ecx, ecx; lpEventAttributes
0x18005139a  lea     edx, [r9+1]; bManualReset
0x18005139e  call    cs:__imp_CreateEventW
0x1800513a5  nop     dword ptr [rax+rax+00h]
0x1800513aa  mov     rcx, rax; hObject
0x1800513ad  test    rax, rax
0x1800513b0  jnz     short loc_1800513D0
0x1800513b2  call    cs:__imp_GetLastError
0x1800513b9  nop     dword ptr [rax+rax+00h]
0x1800513be  test    eax, eax
0x1800513c0  jle     short loc_1800513CC
0x1800513c2  movzx   eax, ax
0x1800513c5  or      eax, 80070000h
0x1800513ca  test    eax, eax
0x1800513cc  js      short loc_1800513F6
0x1800513ce  jmp     short loc_1800513E6
0x1800513d0  xor     eax, eax
0x1800513d2  lock cmpxchg [rbx+38h], rcx
0x1800513d8  jz      short loc_1800513E6
0x1800513da  call    cs:__imp_CloseHandle
0x1800513e1  nop     dword ptr [rax+rax+00h]
0x1800513e6  mov     rcx, [rbx+38h]; hEvent
0x1800513ea  call    cs:__imp_SetEvent
0x1800513f1  nop     dword ptr [rax+rax+00h]
0x1800513f6  add     rsp, 20h
0x1800513fa  pop     rbx
0x1800513fb  retn
```
