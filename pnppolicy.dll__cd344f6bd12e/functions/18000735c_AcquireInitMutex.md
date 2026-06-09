# _AcquireInitMutex

- ea: `0x18000735c`
- end: `0x180007406`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031c0`
- `0x180007458`

## callees

- `0x18000735c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800073cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800073cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073de`
- `KERNEL32!CreateEventW` at `0x180007397`
- `KERNEL32!CreateEventW` at `0x180007397`

## pseudocode

```c
__int64 __fastcall AcquireInitMutex(signed __int64 a1)
{
  __int64 result; // rax
  signed __int64 v3; // rcx
  DWORD v4; // edi

  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
  if ( !_InterlockedCompareExchange64(&qword_180011768, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_180011768;
      *(_QWORD *)(a1 + 8) = qword_180011768;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_180011768, a1, v3) );
    if ( v3 )
      v4 = WaitForSingleObjectEx(*(HANDLE *)a1, 0xFFFFFFFF, 0);
    else
      v4 = 0;
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    return v4 == 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000735c  mov     [rsp+arg_0], rbx
0x180007361  push    rdi
0x180007362  sub     rsp, 20h
0x180007366  mov     rbx, rcx
0x180007369  mov     qword ptr [rcx+10h], 0
0x180007371  mov     qword ptr [rcx+8], 0
0x180007379  xor     eax, eax
0x18000737b  mov     qword ptr [rcx], 0
0x180007382  lock cmpxchg cs:qword_180011768, rbx
0x18000738b  jz      short loc_1800073F6
0x18000738d  xor     r9d, r9d; lpName
0x180007390  xor     r8d, r8d; bInitialState
0x180007393  xor     edx, edx; bManualReset
0x180007395  xor     ecx, ecx; lpEventAttributes
0x180007397  call    cs:__imp_CreateEventW
0x18000739d  mov     [rbx], rax
0x1800073a0  test    rax, rax
0x1800073a3  jz      short loc_1800073F4
0x1800073a5  mov     rcx, cs:qword_180011768
0x1800073ac  mov     [rbx+8], rcx
0x1800073b0  mov     rax, rcx
0x1800073b3  lock cmpxchg cs:qword_180011768, rbx
0x1800073bc  cmp     rcx, rax
0x1800073bf  jnz     short loc_1800073A5
0x1800073c1  test    rcx, rcx
0x1800073c4  jz      short loc_1800073D9
0x1800073c6  mov     rcx, [rbx]; hHandle
0x1800073c9  xor     r8d, r8d; bAlertable
0x1800073cc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800073cf  call    cs:__imp_WaitForSingleObjectEx
0x1800073d5  mov     edi, eax
0x1800073d7  jmp     short loc_1800073DB
0x1800073d9  xor     edi, edi
0x1800073db  mov     rcx, [rbx]; hObject
0x1800073de  call    cs:__imp_CloseHandle
0x1800073e4  xor     eax, eax
0x1800073e6  mov     qword ptr [rbx], 0
0x1800073ed  test    edi, edi
0x1800073ef  setz    al
0x1800073f2  jmp     short loc_1800073FB
0x1800073f4  jmp     short loc_1800073FB
0x1800073f6  mov     eax, 1
0x1800073fb  mov     rbx, [rsp+28h+arg_0]
0x180007400  add     rsp, 20h
0x180007404  pop     rdi
0x180007405  retn
```
