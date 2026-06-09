# _CQueue::RequestNextMessage_::_1_::catch$3

- ea: `0x14001d552`
- end: `0x14001d61f`
- name: `_CQueue::RequestNextMessage_::_1_::catch$3`
- size: `205`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004538`
- `0x14000752c`
- `0x140007554`
- `0x14001d552`

## import_xrefs

- `KERNEL32!Sleep` at `0x14001d593`
- `KERNEL32!Sleep` at `0x14001d593`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14001d5b3`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14001d5b3`
- `KERNEL32!GetLastError` at `0x14001d5d6`
- `KERNEL32!GetLastError` at `0x14001d5d6`

## pseudocode

```c
__int64 __fastcall CQueue::RequestNextMessage_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids);
  Sleep(0x7D0u);
  v3 = *(_QWORD *)(a2 + 128);
  if ( !PostQueuedCompletionStatus(**(HANDLE **)(v3 + 56), 0, 0xBBBBBBBB, (LPOVERLAPPED)(v3 + 64)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids);
    }
    CReference::Release((CReference *)v3);
  }
  *(_DWORD *)(a2 + 136) = -1072824281;
  return 0;
}

```

## disassembly

```asm
0x14001d552  mov     [rsp+arg_8], rdx
0x14001d557  push    rbx
0x14001d558  push    rbp
0x14001d559  sub     rsp, 48h
0x14001d55d  mov     rbp, rdx
0x14001d560  lea     rax, WPP_GLOBAL_Control
0x14001d567  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d56e  cmp     rcx, rax
0x14001d571  jz      short loc_14001D58E
0x14001d573  test    byte ptr [rcx+1Ch], 1
0x14001d577  jz      short loc_14001D58E
0x14001d579  mov     edx, 10h
0x14001d57e  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x14001d585  mov     rcx, [rcx+10h]
0x14001d589  call    WPP_SF_
0x14001d58e  mov     ecx, 7D0h; dwMilliseconds
0x14001d593  call    cs:__imp_Sleep
0x14001d599  mov     rbx, [rbp+80h]
0x14001d5a0  lea     r9, [rbx+40h]; lpOverlapped
0x14001d5a4  mov     rcx, [rbx+38h]
0x14001d5a8  xor     edx, edx; dwNumberOfBytesTransferred
0x14001d5aa  mov     r8d, 0BBBBBBBBh; dwCompletionKey
0x14001d5b0  mov     rcx, [rcx]; CompletionPort
0x14001d5b3  call    cs:__imp_PostQueuedCompletionStatus
0x14001d5b9  test    eax, eax
0x14001d5bb  jnz     short loc_14001D603
0x14001d5bd  lea     rcx, WPP_GLOBAL_Control
0x14001d5c4  mov     rax, cs:WPP_GLOBAL_Control
0x14001d5cb  cmp     rax, rcx
0x14001d5ce  jz      short loc_14001D5FB
0x14001d5d0  test    byte ptr [rax+1Ch], 1
0x14001d5d4  jz      short loc_14001D5FB
0x14001d5d6  call    cs:__imp_GetLastError
0x14001d5dc  mov     edx, 11h
0x14001d5e1  mov     r9d, eax
0x14001d5e4  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x14001d5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5f2  mov     rcx, [rcx+10h]
0x14001d5f6  call    WPP_SF_d
0x14001d5fb  mov     rcx, rbx; this
0x14001d5fe  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x14001d603  mov     dword ptr [rbp+88h], 0C00E0027h
0x14001d60d  mov     rax, 0
0x14001d617  add     rsp, 48h
0x14001d61b  pop     rbp
0x14001d61c  pop     rbx
0x14001d61d  retn
```
