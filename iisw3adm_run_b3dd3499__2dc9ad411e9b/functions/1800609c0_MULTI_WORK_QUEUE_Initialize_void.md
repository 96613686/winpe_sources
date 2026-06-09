# MULTI_WORK_QUEUE::Initialize(void)

- ea: `0x1800609c0`
- end: `0x180060a99`
- name: `?Initialize@MULTI_WORK_QUEUE@@QEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(MULTI_WORK_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d2a0`

## callees

- `0x1800609c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180060a1e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180060a1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180060a5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180060a5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180060a69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180060a69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180060a6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180060a6f`

## pseudocode

```c
signed int __fastcall MULTI_WORK_QUEUE::Initialize(MULTI_WORK_QUEUE *this)
{
  struct _TP_POOL *Threadpool; // rax
  signed int result; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v5; // rdx

  *((_DWORD *)this + 4) = 3;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 20) = 72;
  *((_DWORD *)this + 22) = 1;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 12) = Threadpool;
  if ( Threadpool
    && (SetThreadpoolThreadMaximum(Threadpool, 0x32u),
        SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 12), 1u),
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(),
        *((_QWORD *)this + 13) = ThreadpoolCleanupGroup,
        (v5 = ThreadpoolCleanupGroup) != 0) )
  {
    result = 0;
    *((_QWORD *)this + 3) = *((_QWORD *)this + 12);
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 4) = v5;
  }
  else if ( GetLastError() )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x1800609c0  push    rbx
0x1800609c2  sub     rsp, 20h
0x1800609c6  mov     rbx, rcx
0x1800609c9  mov     dword ptr [rcx+10h], 3
0x1800609d0  mov     qword ptr [rcx+18h], 0
0x1800609d8  mov     qword ptr [rcx+20h], 0
0x1800609e0  mov     qword ptr [rcx+28h], 0
0x1800609e8  mov     qword ptr [rcx+30h], 0
0x1800609f0  mov     qword ptr [rcx+38h], 0
0x1800609f8  mov     qword ptr [rcx+40h], 0
0x180060a00  mov     dword ptr [rcx+48h], 0
0x180060a07  mov     dword ptr [rcx+4Ch], 1
0x180060a0e  mov     dword ptr [rcx+50h], 48h ; 'H'
0x180060a15  mov     dword ptr [rcx+58h], 1
0x180060a1c  xor     ecx, ecx; reserved
0x180060a1e  call    cs:__imp_CreateThreadpool
0x180060a24  mov     [rbx+60h], rax
0x180060a28  test    rax, rax
0x180060a2b  jnz     short loc_180060A52
0x180060a2d  call    cs:__imp_GetLastError
0x180060a33  test    eax, eax
0x180060a35  jz      short loc_180060A4B
0x180060a37  call    cs:__imp_GetLastError
0x180060a3d  test    eax, eax
0x180060a3f  jle     short loc_180060A93
0x180060a41  movzx   eax, ax
0x180060a44  or      eax, 80070000h
0x180060a49  jmp     short loc_180060A93
0x180060a4b  mov     eax, 80004005h
0x180060a50  jmp     short loc_180060A93
0x180060a52  mov     edx, 32h ; '2'; cthrdMost
0x180060a57  mov     rcx, rax; ptpp
0x180060a5a  call    cs:__imp_SetThreadpoolThreadMaximum
0x180060a60  mov     rcx, [rbx+60h]; ptpp
0x180060a64  mov     edx, 1; cthrdMic
0x180060a69  call    cs:__imp_SetThreadpoolThreadMinimum
0x180060a6f  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180060a75  mov     [rbx+68h], rax
0x180060a79  mov     rdx, rax
0x180060a7c  test    rax, rax
0x180060a7f  jz      short loc_180060A2D
0x180060a81  mov     rcx, [rbx+60h]
0x180060a85  xor     eax, eax
0x180060a87  mov     [rbx+18h], rcx
0x180060a8b  mov     [rbx+28h], rax
0x180060a8f  mov     [rbx+20h], rdx
0x180060a93  add     rsp, 20h
0x180060a97  pop     rbx
0x180060a98  retn
```
