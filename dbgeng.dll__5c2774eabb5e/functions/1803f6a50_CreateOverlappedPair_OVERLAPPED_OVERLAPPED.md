# CreateOverlappedPair(_OVERLAPPED *,_OVERLAPPED *)

- ea: `0x1803f6a50`
- end: `0x1803f6b07`
- name: `?CreateOverlappedPair@@YAJPEAU_OVERLAPPED@@0@Z`
- size: `183`
- prototype: `__int64 __fastcall(struct _OVERLAPPED *, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180430c80`

## callees

- `0x1803f6a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1803f6a80`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1803f6ad2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1803f6a80`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1803f6ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f6aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f6aeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f6aeb`

## pseudocode

```c
signed int __fastcall CreateOverlappedPair(struct _OVERLAPPED *a1, struct _OVERLAPPED *a2)
{
  HANDLE EventA; // rax
  signed int result; // eax
  HANDLE v6; // rax

  *(_OWORD *)&a1->Internal = 0;
  *(_OWORD *)&a1->Offset = 0;
  *(_OWORD *)&a2->Internal = 0;
  *(_OWORD *)&a2->Offset = 0;
  EventA = CreateEventA(0, 1, 0, 0);
  a1->hEvent = EventA;
  if ( EventA )
  {
    v6 = CreateEventA(0, 1, 0, 0);
    a2->hEvent = v6;
    if ( v6 )
      return 0;
    CloseHandle(a1->hEvent);
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1803f6a50  mov     [rsp+arg_0], rbx
0x1803f6a55  push    rdi
0x1803f6a56  sub     rsp, 20h
0x1803f6a5a  xorps   xmm0, xmm0
0x1803f6a5d  xorps   xmm1, xmm1
0x1803f6a60  movups  xmmword ptr [rcx], xmm0
0x1803f6a63  xor     r9d, r9d; lpName
0x1803f6a66  mov     rdi, rdx
0x1803f6a69  movups  xmmword ptr [rcx+10h], xmm0
0x1803f6a6d  mov     rbx, rcx
0x1803f6a70  xor     r8d, r8d; bInitialState
0x1803f6a73  movups  xmmword ptr [rdx], xmm1
0x1803f6a76  xor     ecx, ecx; lpEventAttributes
0x1803f6a78  movups  xmmword ptr [rdx+10h], xmm1
0x1803f6a7c  lea     edx, [r9+1]; bManualReset
0x1803f6a80  call    cs:__imp_CreateEventA
0x1803f6a87  nop     dword ptr [rax+rax+00h]
0x1803f6a8c  mov     [rbx+18h], rax
0x1803f6a90  test    rax, rax
0x1803f6a93  jnz     short loc_1803F6AC6
0x1803f6a95  call    cs:__imp_GetLastError
0x1803f6a9c  nop     dword ptr [rax+rax+00h]
0x1803f6aa1  test    eax, eax
0x1803f6aa3  jnz     short loc_1803F6AAC
0x1803f6aa5  mov     eax, 80004005h
0x1803f6aaa  jmp     short loc_1803F6AFB
0x1803f6aac  call    cs:__imp_GetLastError
0x1803f6ab3  nop     dword ptr [rax+rax+00h]
0x1803f6ab8  test    eax, eax
0x1803f6aba  jle     short loc_1803F6AFB
0x1803f6abc  movzx   eax, ax
0x1803f6abf  or      eax, 80070000h
0x1803f6ac4  jmp     short loc_1803F6AFB
0x1803f6ac6  xor     r9d, r9d; lpName
0x1803f6ac9  xor     r8d, r8d; bInitialState
0x1803f6acc  xor     ecx, ecx; lpEventAttributes
0x1803f6ace  lea     edx, [r9+1]; bManualReset
0x1803f6ad2  call    cs:__imp_CreateEventA
0x1803f6ad9  nop     dword ptr [rax+rax+00h]
0x1803f6ade  mov     [rdi+18h], rax
0x1803f6ae2  test    rax, rax
0x1803f6ae5  jnz     short loc_1803F6AF9
0x1803f6ae7  mov     rcx, [rbx+18h]; hObject
0x1803f6aeb  call    cs:__imp_CloseHandle
0x1803f6af2  nop     dword ptr [rax+rax+00h]
0x1803f6af7  jmp     short loc_1803F6A95
0x1803f6af9  xor     eax, eax
0x1803f6afb  mov     rbx, [rsp+28h+arg_0]
0x1803f6b00  add     rsp, 20h
0x1803f6b04  pop     rdi
0x1803f6b05  retn
```
