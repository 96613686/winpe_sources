# CAsyncStatementTimeoutHandler::AddAsyncStatement(tagSTMT *)

- ea: `0x100529530`
- end: `0x100529628`
- name: `?AddAsyncStatement@CAsyncStatementTimeoutHandler@@QEAAJPEAUtagSTMT@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(CAsyncStatementTimeoutHandler *__hidden this, struct tagSTMT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100530c14`
- `0x100532acc`

## callees

- `0x100529530`
- `0x100546a24`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1005295ad`
- `KERNEL32!CreateThread` at `0x1005295ad`
- `KERNEL32!SetEvent` at `0x1005295f1`
- `KERNEL32!SetEvent` at `0x1005295f1`
- `KERNEL32!GetLastError` at `0x1005295bc`
- `KERNEL32!GetLastError` at `0x1005295fb`
- `KERNEL32!GetLastError` at `0x1005295bc`
- `KERNEL32!GetLastError` at `0x1005295fb`

## pseudocode

```c
__int64 __fastcall CAsyncStatementTimeoutHandler::AddAsyncStatement(
        CAsyncStatementTimeoutHandler *this,
        struct tagSTMT *a2)
{
  unsigned int v4; // edi
  HANDLE Thread; // rax
  __int64 v6; // r9

  v4 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 5) + 32LL) + 8LL))(*((_QWORD *)this + 5) + 32LL);
  if ( !*((_QWORD *)a2 + 542) )
  {
    *((_QWORD *)a2 + 541) = *((_QWORD *)this + 6);
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = (char *)a2 + 4328;
    *((_QWORD *)this + 6) = (char *)a2 + 4328;
    *((_QWORD *)a2 + 542) = (char *)this + 48;
    if ( !*((_DWORD *)this + 8) )
    {
      *((_DWORD *)this + 8) = 1;
      Thread = CreateThread(0, 0, CAsyncStatementTimeoutHandler::S_TimeoutMonitorThreadProc, this, 0, 0);
      *((_QWORD *)this + 1) = Thread;
      if ( !Thread && GetLastError() == 8 )
      {
        v4 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(0, 4034569, 2147942414LL, v6);
        goto LABEL_10;
      }
    }
    *(_DWORD *)this = 500;
  }
  if ( !SetEvent(*((HANDLE *)this + 3)) )
    GetLastError();
LABEL_10:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 5) + 32LL) + 24LL))(*((_QWORD *)this + 5) + 32LL);
  return v4;
}

```

## disassembly

```asm
0x100529530  mov     [rsp+arg_0], rbx
0x100529535  mov     [rsp+arg_8], rsi
0x10052953a  push    rdi
0x10052953b  sub     rsp, 30h
0x10052953f  mov     rbx, rcx
0x100529542  mov     rsi, rdx
0x100529545  mov     rcx, [rcx+28h]
0x100529549  xor     edi, edi
0x10052954b  add     rcx, 20h ; ' '
0x10052954f  mov     rax, [rcx]
0x100529552  mov     rax, [rax+8]
0x100529556  call    cs:__guard_dispatch_icall_fptr
0x10052955c  cmp     [rsi+10F0h], rdi
0x100529563  jnz     loc_1005295ED
0x100529569  lea     rcx, [rbx+30h]
0x10052956d  mov     rax, [rcx]
0x100529570  lea     rdx, [rsi+10E8h]
0x100529577  mov     [rdx], rax
0x10052957a  mov     rax, [rcx]
0x10052957d  mov     [rax+8], rdx
0x100529581  mov     [rcx], rdx
0x100529584  mov     [rdx+8], rcx
0x100529588  mov     eax, [rbx+20h]
0x10052958b  test    eax, eax
0x10052958d  jnz     short loc_1005295E7
0x10052958f  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x100529594  lea     r8, ?S_TimeoutMonitorThreadProc@CAsyncStatementTimeoutHandler@@CAKPEAX@Z; lpStartAddress
0x10052959b  mov     r9, rbx; lpParameter
0x10052959e  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x1005295a2  xor     edx, edx; dwStackSize
0x1005295a4  mov     dword ptr [rbx+20h], 1
0x1005295ab  xor     ecx, ecx; lpThreadAttributes
0x1005295ad  call    cs:__imp_CreateThread
0x1005295b3  mov     [rbx+8], rax
0x1005295b7  test    rax, rax
0x1005295ba  jnz     short loc_1005295E7
0x1005295bc  call    cs:__imp_GetLastError
0x1005295c2  cmp     eax, 8
0x1005295c5  jnz     short loc_1005295E7
0x1005295c7  test    byte ptr cs:_bidGblFlags, 2
0x1005295ce  mov     r8d, 8007000Eh
0x1005295d4  mov     edi, r8d
0x1005295d7  jz      short loc_100529601
0x1005295d9  mov     edx, 3D9009h
0x1005295de  xor     ecx, ecx
0x1005295e0  call    _bidTraceHR
0x1005295e5  jmp     short loc_100529601
0x1005295e7  mov     dword ptr [rbx], 1F4h
0x1005295ed  mov     rcx, [rbx+18h]; hEvent
0x1005295f1  call    cs:__imp_SetEvent
0x1005295f7  test    eax, eax
0x1005295f9  jnz     short loc_100529601
0x1005295fb  call    cs:__imp_GetLastError
0x100529601  mov     rcx, [rbx+28h]
0x100529605  add     rcx, 20h ; ' '
0x100529609  mov     rdx, [rcx]
0x10052960c  mov     rax, [rdx+18h]
0x100529610  call    cs:__guard_dispatch_icall_fptr
0x100529616  mov     rbx, [rsp+38h+arg_0]
0x10052961b  mov     eax, edi
0x10052961d  mov     rsi, [rsp+38h+arg_8]
0x100529622  add     rsp, 30h
0x100529626  pop     rdi
0x100529627  retn
```
