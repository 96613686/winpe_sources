# ShellProcess::ReaderThread(void)

- ea: `0x1802e788c`
- end: `0x1802e7b21`
- name: `?ReaderThread@ShellProcess@@QEAAKXZ`
- size: `661`
- prototype: `unsigned int __fastcall(ShellProcess *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1802e7b30`

## callees

- `0x1800727b8`
- `0x1800797ec`
- `0x1800f0f40`
- `0x1800f17b0`
- `0x1802e788c`
- `0x180416524`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802e7924`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802e7924`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802e79af`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802e79af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802e7a0d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802e7af3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802e7a0d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802e7af3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802e78e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802e78e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e797c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e797c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7a79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e7abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e7abb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1802e794e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1802e794e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1802e79d4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1802e79d4`

## string_xrefs

- `0x1802e7a99`: `.shell: ReadFile failed, error == %d\n`

## pseudocode

```c
__int64 __fastcall ShellProcess::ReaderThread(HANDLE *this)
{
  HANDLE EventW; // rax
  HANDLE hEvent; // rcx
  int v5; // r15d
  DWORD LastError; // eax
  __int64 v7; // rsi
  DWORD v8; // eax
  __int64 v9; // rdx
  DWORD v10; // eax
  HANDLE *v11; // rbx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handles[2]; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v15; // [rsp+68h] [rbp-98h]
  _BYTE Buffer[272]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  NumberOfBytesRead = 0;
  *(_OWORD *)Handles = 0;
  memset(&Overlapped, 0, 24);
  EventW = CreateEventW(0, 1, 0, 0);
  Overlapped.hEvent = EventW;
  hEvent = EventW;
  if ( !EventW )
    return 8;
  Handles[0] = EventW;
  v5 = 0;
  Handles[1] = this[7];
  v15 = this[9];
  while ( 1 )
  {
    ResetEvent(hEvent);
    if ( ReadFile(this[1], Buffer, 0x103u, &NumberOfBytesRead, &Overlapped) )
    {
      if ( NumberOfBytesRead >= 0x104 )
        goto LABEL_15;
      if ( NumberOfBytesRead >= 0x104uLL )
LABEL_16:
        _report_rangecheckfailure();
      Buffer[NumberOfBytesRead] = 0;
      goto LABEL_14;
    }
    LastError = GetLastError();
    LODWORD(v7) = LastError;
    if ( LastError != 997 )
    {
      if ( LastError == 109 )
        goto LABEL_27;
      v9 = LastError;
      goto LABEL_26;
    }
    LODWORD(v7) = 0;
    FlushCallbacks();
    v8 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        dprintf(L".shell: Process exited\n");
      }
      else if ( v8 == 2 )
      {
        dprintf(L".shell: Exit requested through .shell_quit\n");
        v5 = 1;
      }
      else
      {
        v7 = GetLastError();
        dprintf(L".shell: WaitForMultipleObjectsEx failed; error == %d\n", v7);
      }
      goto LABEL_27;
    }
    if ( !GetOverlappedResult(this[1], &Overlapped, &NumberOfBytesRead, 1) )
      break;
    if ( NumberOfBytesRead >= 0x104 )
    {
LABEL_15:
      v9 = 13;
      LODWORD(v7) = 13;
LABEL_26:
      dprintf(L".shell: ReadFile failed, error == %d\n", v9);
      goto LABEL_27;
    }
    if ( NumberOfBytesRead >= 0x104uLL )
      goto LABEL_16;
    Buffer[NumberOfBytesRead] = 0;
LABEL_14:
    dprintf(L"%hs", Buffer);
    SetEvent(this[5]);
    hEvent = Overlapped.hEvent;
  }
  v10 = GetLastError();
  LODWORD(v7) = v10;
  if ( v10 != 109 )
    dprintf(L".shell: GetOverlappedResult failed, error == %d\n", v10);
LABEL_27:
  DbgCancelIo(this[1]);
  CloseHandle(Overlapped.hEvent);
  if ( (_DWORD)v7 )
  {
    v11 = this + 5;
  }
  else
  {
    v11 = this + 5;
    if ( *this )
    {
      if ( !v5 )
        dprintf(L"Press ENTER to continue\n");
    }
  }
  FlushCallbacks();
  SetEvent(*v11);
  return 0;
}

```

## disassembly

```asm
0x1802e788c  push    rbp
0x1802e788e  push    rbx
0x1802e788f  push    rsi
0x1802e7890  push    rdi
0x1802e7891  push    r14
0x1802e7893  push    r15
0x1802e7895  lea     rbp, [rsp-98h]
0x1802e789d  sub     rsp, 198h
0x1802e78a4  mov     rax, cs:__security_cookie
0x1802e78ab  xor     rax, rsp
0x1802e78ae  mov     [rbp+0C0h+var_40], rax
0x1802e78b5  xor     eax, eax
0x1802e78b7  xorps   xmm0, xmm0
0x1802e78ba  mov     rdi, rcx
0x1802e78bd  mov     [rsp+1C0h+var_158], rax
0x1802e78c2  xor     r9d, r9d; lpName
0x1802e78c5  mov     [rsp+1C0h+NumberOfBytesRead], eax
0x1802e78c9  xor     r8d, r8d; bInitialState
0x1802e78cc  xor     ecx, ecx; lpEventAttributes
0x1802e78ce  lea     r14d, [rax+1]
0x1802e78d2  mov     edx, r14d; bManualReset
0x1802e78d5  movups  xmmword ptr [rsp+1C0h+Handles], xmm0
0x1802e78da  movups  xmmword ptr [rsp+1C0h+Overlapped.Internal], xmm0
0x1802e78df  movups  xmmword ptr [rsp+1C0h+Overlapped.10h], xmm0
0x1802e78e4  call    cs:__imp_CreateEventW
0x1802e78eb  nop     dword ptr [rax+rax+00h]
0x1802e78f0  mov     [rsp+1C0h+Overlapped.hEvent], rax
0x1802e78f5  mov     rcx, rax; hEvent
0x1802e78f8  test    rax, rax
0x1802e78fb  jnz     short loc_1802E7905
0x1802e78fd  lea     eax, [rcx+8]
0x1802e7900  jmp     loc_1802E7B01
0x1802e7905  mov     [rsp+1C0h+Handles], rax
0x1802e790a  xor     r15d, r15d
0x1802e790d  mov     rax, [rdi+38h]
0x1802e7911  mov     ebx, 104h
0x1802e7916  mov     [rsp+1C0h+Handles+8], rax
0x1802e791b  mov     rax, [rdi+48h]
0x1802e791f  mov     [rsp+1C0h+var_158], rax
0x1802e7924  call    cs:__imp_ResetEvent
0x1802e792b  nop     dword ptr [rax+rax+00h]
0x1802e7930  mov     rcx, [rdi+8]; hFile
0x1802e7934  lea     rax, [rsp+1C0h+Overlapped]
0x1802e7939  lea     r9, [rsp+1C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1802e793e  mov     [rsp+1C0h+lpOverlapped], rax; lpOverlapped
0x1802e7943  mov     r8d, 103h; nNumberOfBytesToRead
0x1802e7949  lea     rdx, [rsp+1C0h+Buffer]; lpBuffer
0x1802e794e  call    cs:__imp_ReadFile
0x1802e7955  nop     dword ptr [rax+rax+00h]
0x1802e795a  test    eax, eax
0x1802e795c  jz      short loc_1802E797C
0x1802e795e  cmp     [rsp+1C0h+NumberOfBytesRead], ebx
0x1802e7962  jnb     loc_1802E7A23
0x1802e7968  mov     eax, [rsp+1C0h+NumberOfBytesRead]
0x1802e796c  cmp     rax, rbx
0x1802e796f  jnb     loc_1802E7A2C
0x1802e7975  mov     [rsp+rax+1C0h+Buffer], r15b
0x1802e797a  jmp     short loc_1802E79F8
0x1802e797c  call    cs:__imp_GetLastError
0x1802e7983  nop     dword ptr [rax+rax+00h]
0x1802e7988  mov     esi, eax
0x1802e798a  cmp     eax, 3E5h
0x1802e798f  jnz     loc_1802E7A92
0x1802e7995  xor     esi, esi
0x1802e7997  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1802e799c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1802e79a0  mov     dword ptr [rsp+1C0h+lpOverlapped], esi; bAlertable
0x1802e79a4  xor     r8d, r8d; bWaitAll
0x1802e79a7  lea     rdx, [rsp+1C0h+Handles]; lpHandles
0x1802e79ac  lea     ecx, [rsi+3]; nCount
0x1802e79af  call    cs:__imp_WaitForMultipleObjectsEx
0x1802e79b6  nop     dword ptr [rax+rax+00h]
0x1802e79bb  test    eax, eax
0x1802e79bd  jnz     loc_1802E7A50
0x1802e79c3  mov     rcx, [rdi+8]; hFile
0x1802e79c7  lea     r8, [rsp+1C0h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x1802e79cc  mov     r9d, r14d; bWait
0x1802e79cf  lea     rdx, [rsp+1C0h+Overlapped]; lpOverlapped
0x1802e79d4  call    cs:__imp_GetOverlappedResult
0x1802e79db  nop     dword ptr [rax+rax+00h]
0x1802e79e0  test    eax, eax
0x1802e79e2  jz      short loc_1802E7A32
0x1802e79e4  cmp     [rsp+1C0h+NumberOfBytesRead], ebx
0x1802e79e8  jnb     short loc_1802E7A23
0x1802e79ea  mov     eax, [rsp+1C0h+NumberOfBytesRead]
0x1802e79ee  cmp     rax, rbx
0x1802e79f1  jnb     short loc_1802E7A2C
0x1802e79f3  mov     [rsp+rax+1C0h+Buffer], sil
0x1802e79f8  lea     rdx, [rsp+1C0h+Buffer]
0x1802e79fd  lea     rcx, aHs_6; "%hs"
0x1802e7a04  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e7a09  mov     rcx, [rdi+28h]; hEvent
0x1802e7a0d  call    cs:__imp_SetEvent
0x1802e7a14  nop     dword ptr [rax+rax+00h]
0x1802e7a19  mov     rcx, [rsp+1C0h+Overlapped.hEvent]
0x1802e7a1e  jmp     loc_1802E7924
0x1802e7a23  mov     edx, 0Dh
0x1802e7a28  mov     esi, edx
0x1802e7a2a  jmp     short loc_1802E7A99
0x1802e7a2c  call    __report_rangecheckfailure
0x1802e7a32  call    cs:__imp_GetLastError
0x1802e7a39  nop     dword ptr [rax+rax+00h]
0x1802e7a3e  mov     esi, eax
0x1802e7a40  cmp     eax, 6Dh ; 'm'
0x1802e7a43  jz      short loc_1802E7AA5
0x1802e7a45  mov     edx, eax
0x1802e7a47  lea     rcx, aShellGetoverla; ".shell: GetOverlappedResult failed, err"...
0x1802e7a4e  jmp     short loc_1802E7AA0
0x1802e7a50  cmp     eax, r14d
0x1802e7a53  jnz     short loc_1802E7A63
0x1802e7a55  lea     rcx, aShellProcessEx; ".shell: Process exited\n"
0x1802e7a5c  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e7a61  jmp     short loc_1802E7AA5
0x1802e7a63  cmp     eax, 2
0x1802e7a66  jnz     short loc_1802E7A79
0x1802e7a68  lea     rcx, aShellExitReque; ".shell: Exit requested through .shell_q"...
0x1802e7a6f  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e7a74  mov     r15d, r14d
0x1802e7a77  jmp     short loc_1802E7AA5
0x1802e7a79  call    cs:__imp_GetLastError
0x1802e7a80  nop     dword ptr [rax+rax+00h]
0x1802e7a85  mov     esi, eax
0x1802e7a87  lea     rcx, aShellWaitformu; ".shell: WaitForMultipleObjectsEx failed"...
0x1802e7a8e  mov     edx, eax
0x1802e7a90  jmp     short loc_1802E7AA0
0x1802e7a92  cmp     eax, 6Dh ; 'm'
0x1802e7a95  jz      short loc_1802E7AA5
0x1802e7a97  mov     edx, eax
0x1802e7a99  lea     rcx, aShellReadfileF; ".shell: ReadFile failed, error == %d\n"
0x1802e7aa0  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e7aa5  mov     rcx, [rdi+8]; void *
0x1802e7aa9  mov     r14, rdi
0x1802e7aac  mov     ebx, 28h ; '('
0x1802e7ab1  call    ?DbgCancelIo@@YAHPEAX@Z; DbgCancelIo(void *)
0x1802e7ab6  mov     rcx, [rsp+1C0h+Overlapped.hEvent]; hObject
0x1802e7abb  call    cs:__imp_CloseHandle
0x1802e7ac2  nop     dword ptr [rax+rax+00h]
0x1802e7ac7  test    esi, esi
0x1802e7ac9  jnz     short loc_1802E7AE8
0x1802e7acb  cmp     qword ptr [rdi], 0
0x1802e7acf  lea     rbx, [rdi+28h]
0x1802e7ad3  jz      short loc_1802E7AEB
0x1802e7ad5  test    r15d, r15d
0x1802e7ad8  jnz     short loc_1802E7AEB
0x1802e7ada  lea     rcx, aPressEnterToCo; "Press ENTER to continue\n"
0x1802e7ae1  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e7ae6  jmp     short loc_1802E7AEB
0x1802e7ae8  add     rbx, r14
0x1802e7aeb  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1802e7af0  mov     rcx, [rbx]; hEvent
0x1802e7af3  call    cs:__imp_SetEvent
0x1802e7afa  nop     dword ptr [rax+rax+00h]
0x1802e7aff  xor     eax, eax
0x1802e7b01  mov     rcx, [rbp+0C0h+var_40]
0x1802e7b08  xor     rcx, rsp; StackCookie
0x1802e7b0b  call    __security_check_cookie
0x1802e7b10  add     rsp, 198h
0x1802e7b17  pop     r15
0x1802e7b19  pop     r14
0x1802e7b1b  pop     rdi
0x1802e7b1c  pop     rsi
0x1802e7b1d  pop     rbx
0x1802e7b1e  pop     rbp
0x1802e7b1f  retn
```
