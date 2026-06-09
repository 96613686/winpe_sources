# _AcquireInitMutex

- ea: `0x180033dc0`
- end: `0x180033e6a`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180033d08`
- `0x18007d850`

## callees

- `0x180033dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033e33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033e33`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033dfb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e42`

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
  if ( !_InterlockedCompareExchange64(&qword_1800A4A38, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_1800A4A38;
      *(_QWORD *)(a1 + 8) = qword_1800A4A38;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_1800A4A38, a1, v3) );
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
0x180033dc0  mov     [rsp+arg_0], rbx
0x180033dc5  push    rdi
0x180033dc6  sub     rsp, 20h
0x180033dca  mov     rbx, rcx
0x180033dcd  mov     qword ptr [rcx+10h], 0
0x180033dd5  mov     qword ptr [rcx+8], 0
0x180033ddd  xor     eax, eax
0x180033ddf  mov     qword ptr [rcx], 0
0x180033de6  lock cmpxchg cs:qword_1800A4A38, rbx
0x180033def  jz      short loc_180033E5A
0x180033df1  xor     r9d, r9d; lpName
0x180033df4  xor     r8d, r8d; bInitialState
0x180033df7  xor     edx, edx; bManualReset
0x180033df9  xor     ecx, ecx; lpEventAttributes
0x180033dfb  call    cs:__imp_CreateEventW
0x180033e01  mov     [rbx], rax
0x180033e04  test    rax, rax
0x180033e07  jz      short loc_180033E58
0x180033e09  mov     rcx, cs:qword_1800A4A38
0x180033e10  mov     [rbx+8], rcx
0x180033e14  mov     rax, rcx
0x180033e17  lock cmpxchg cs:qword_1800A4A38, rbx
0x180033e20  cmp     rcx, rax
0x180033e23  jnz     short loc_180033E09
0x180033e25  test    rcx, rcx
0x180033e28  jz      short loc_180033E3D
0x180033e2a  mov     rcx, [rbx]; hHandle
0x180033e2d  xor     r8d, r8d; bAlertable
0x180033e30  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180033e33  call    cs:__imp_WaitForSingleObjectEx
0x180033e39  mov     edi, eax
0x180033e3b  jmp     short loc_180033E3F
0x180033e3d  xor     edi, edi
0x180033e3f  mov     rcx, [rbx]; hObject
0x180033e42  call    cs:__imp_CloseHandle
0x180033e48  xor     eax, eax
0x180033e4a  mov     qword ptr [rbx], 0
0x180033e51  test    edi, edi
0x180033e53  setz    al
0x180033e56  jmp     short loc_180033E5F
0x180033e58  jmp     short loc_180033E5F
0x180033e5a  mov     eax, 1
0x180033e5f  mov     rbx, [rsp+28h+arg_0]
0x180033e64  add     rsp, 20h
0x180033e68  pop     rdi
0x180033e69  retn
```
