# _AcquireInitMutex

- ea: `0x18001fe30`
- end: `0x18001feda`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ff98`
- `0x180020050`

## callees

- `0x18001fe30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fe6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fe6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001fea3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001fea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feb2`

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
  if ( !_InterlockedCompareExchange64(&qword_180032AC0, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_180032AC0;
      *(_QWORD *)(a1 + 8) = qword_180032AC0;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_180032AC0, a1, v3) );
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
0x18001fe30  mov     [rsp+arg_0], rbx
0x18001fe35  push    rdi
0x18001fe36  sub     rsp, 20h
0x18001fe3a  mov     rbx, rcx
0x18001fe3d  mov     qword ptr [rcx+10h], 0
0x18001fe45  mov     qword ptr [rcx+8], 0
0x18001fe4d  xor     eax, eax
0x18001fe4f  mov     qword ptr [rcx], 0
0x18001fe56  lock cmpxchg cs:qword_180032AC0, rbx
0x18001fe5f  jz      short loc_18001FECA
0x18001fe61  xor     r9d, r9d; lpName
0x18001fe64  xor     r8d, r8d; bInitialState
0x18001fe67  xor     edx, edx; bManualReset
0x18001fe69  xor     ecx, ecx; lpEventAttributes
0x18001fe6b  call    cs:__imp_CreateEventW
0x18001fe71  mov     [rbx], rax
0x18001fe74  test    rax, rax
0x18001fe77  jz      short loc_18001FEC8
0x18001fe79  mov     rcx, cs:qword_180032AC0
0x18001fe80  mov     [rbx+8], rcx
0x18001fe84  mov     rax, rcx
0x18001fe87  lock cmpxchg cs:qword_180032AC0, rbx
0x18001fe90  cmp     rcx, rax
0x18001fe93  jnz     short loc_18001FE79
0x18001fe95  test    rcx, rcx
0x18001fe98  jz      short loc_18001FEAD
0x18001fe9a  mov     rcx, [rbx]; hHandle
0x18001fe9d  xor     r8d, r8d; bAlertable
0x18001fea0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001fea3  call    cs:__imp_WaitForSingleObjectEx
0x18001fea9  mov     edi, eax
0x18001feab  jmp     short loc_18001FEAF
0x18001fead  xor     edi, edi
0x18001feaf  mov     rcx, [rbx]; hObject
0x18001feb2  call    cs:__imp_CloseHandle
0x18001feb8  xor     eax, eax
0x18001feba  mov     qword ptr [rbx], 0
0x18001fec1  test    edi, edi
0x18001fec3  setz    al
0x18001fec6  jmp     short loc_18001FECF
0x18001fec8  jmp     short loc_18001FECF
0x18001feca  mov     eax, 1
0x18001fecf  mov     rbx, [rsp+28h+arg_0]
0x18001fed4  add     rsp, 20h
0x18001fed8  pop     rdi
0x18001fed9  retn
```
