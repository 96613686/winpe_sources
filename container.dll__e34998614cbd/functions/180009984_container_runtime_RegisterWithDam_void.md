# container_runtime::RegisterWithDam(void *)

- ea: `0x180009984`
- end: `0x180009a50`
- name: `?RegisterWithDam@container_runtime@@YA_NPEAX@Z`
- size: `204`
- prototype: `bool __fastcall(container_runtime *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800063f0`

## callees

- `0x180009984`
- `0x18000bdec`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009a0c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009a0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800099b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800099b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall container_runtime::RegisterWithDam(container_runtime *this, void *a2)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  container_runtime *InBuffer; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v8; // [rsp+58h] [rbp+10h]

  InBuffer = this;
  FileW = CreateFileW(L"\\\\.\\DamCtrl", 0xC0000000, 0, 0, 3u, 0x80u, 0);
  v3 = FileW;
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( !DeviceIoControl(FileW, 0x22A020u, &InBuffer, 8u, 0, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime.cpp",
      v5);
  if ( v3 )
    CloseHandle(v3);
  return 1;
}

```

## disassembly

```asm
0x180009984  mov     rax, rsp
0x180009987  mov     [rax+8], rcx
0x18000998b  push    rbx
0x18000998c  sub     rsp, 40h
0x180009990  mov     qword ptr [rax-18h], 0
0x180009998  mov     dword ptr [rax-20h], 80h
0x18000999f  mov     dword ptr [rax-28h], 3
0x1800099a6  xor     r9d, r9d; lpSecurityAttributes
0x1800099a9  xor     r8d, r8d; dwShareMode
0x1800099ac  mov     edx, 0C0000000h; dwDesiredAccess
0x1800099b1  lea     rcx, FileName; "\\\\.\\DamCtrl"
0x1800099b8  call    cs:__imp_CreateFileW
0x1800099bf  nop     dword ptr [rax+rax+00h]
0x1800099c4  mov     rbx, rax
0x1800099c7  mov     [rsp+48h+arg_8], rax
0x1800099cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800099d0  jnz     short loc_1800099D6
0x1800099d2  xor     al, al
0x1800099d4  jmp     short loc_180009A37
0x1800099d6  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800099df  mov     [rsp+48h+lpBytesReturned], 0; lpBytesReturned
0x1800099e8  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x1800099f0  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x1800099f9  mov     r9d, 8; nInBufferSize
0x1800099ff  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x180009a04  mov     edx, 22A020h; dwIoControlCode
0x180009a09  mov     rcx, rbx; hDevice
0x180009a0c  call    cs:__imp_DeviceIoControl
0x180009a13  nop     dword ptr [rax+rax+00h]
0x180009a18  mov     rcx, [rsp+48h]; this
0x180009a1d  test    eax, eax
0x180009a1f  jz      short loc_180009A3E
0x180009a21  test    rbx, rbx
0x180009a24  jz      short loc_180009A35
0x180009a26  mov     rcx, rbx; hObject
0x180009a29  call    cs:__imp_CloseHandle
0x180009a30  nop     dword ptr [rax+rax+00h]
0x180009a35  mov     al, 1
0x180009a37  add     rsp, 40h
0x180009a3b  pop     rbx
0x180009a3c  retn
0x180009a3e  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\container"...
0x180009a45  mov     edx, 1EDh; void *
0x180009a4a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
