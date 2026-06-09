# CTriggerMonitorPool::CreateIOCompletionPort(void)

- ea: `0x14000b180`
- end: `0x14000b235`
- name: `?CreateIOCompletionPort@CTriggerMonitorPool@@AEAAXXZ`
- size: `181`
- prototype: `void __fastcall(CTriggerMonitorPool *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000bdc0`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x140008034`
- `0x14000a5bc`
- `0x14000b180`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000b1a7`
- `KERNEL32!GetLastError` at `0x14000b1a7`
- `KERNEL32!CreateIoCompletionPort` at `0x14000b195`
- `KERNEL32!CreateIoCompletionPort` at `0x14000b195`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::CreateIOCompletionPort(CTriggerMonitorPool *this)
{
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // ebx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  *((_QWORD *)this + 18) = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids,
      IoCompletionPort);
}

```

## disassembly

```asm
0x14000b180  push    rbx
0x14000b182  sub     rsp, 40h
0x14000b186  mov     rbx, rcx
0x14000b189  xor     r9d, r9d; NumberOfConcurrentThreads
0x14000b18c  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14000b190  xor     r8d, r8d; CompletionKey
0x14000b193  xor     edx, edx; ExistingCompletionPort
0x14000b195  call    cs:__imp_CreateIoCompletionPort
0x14000b19b  mov     [rbx+90h], rax
0x14000b1a2  test    rax, rax
0x14000b1a5  jnz     short loc_14000B1FE
0x14000b1a7  call    cs:__imp_GetLastError
0x14000b1ad  mov     ebx, eax
0x14000b1af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1b6  lea     rdx, WPP_GLOBAL_Control
0x14000b1bd  cmp     rcx, rdx
0x14000b1c0  jz      short loc_14000B1E0
0x14000b1c2  test    byte ptr [rcx+1Ch], 1
0x14000b1c6  jz      short loc_14000B1E0
0x14000b1c8  mov     rcx, [rcx+10h]
0x14000b1cc  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000b1d3  mov     edx, 19h
0x14000b1d8  mov     r9d, eax
0x14000b1db  call    WPP_SF_d
0x14000b1e0  mov     edx, ebx; unsigned int
0x14000b1e2  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000b1e7  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14000b1ec  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x14000b1f3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b1f8  call    _CxxThrowException_0
0x14000b1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b205  lea     rdx, WPP_GLOBAL_Control
0x14000b20c  cmp     rcx, rdx
0x14000b20f  jz      short loc_14000B22F
0x14000b211  test    byte ptr [rcx+1Ch], 4
0x14000b215  jz      short loc_14000B22F
0x14000b217  mov     rcx, [rcx+10h]
0x14000b21b  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000b222  mov     edx, 1Ah
0x14000b227  mov     r9, rax
0x14000b22a  call    WPP_SF_q
0x14000b22f  add     rsp, 40h
0x14000b233  pop     rbx
0x14000b234  retn
```
