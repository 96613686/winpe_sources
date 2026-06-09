# MRxDAVFastIoRead

- ea: `0x14001ce30`
- end: `0x14001ce95`
- name: `MRxDAVFastIoRead`
- size: `101`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ce56`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ce56`

## pseudocode

```c
char __fastcall MRxDAVFastIoRead(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
{
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v7, 48, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids, CurrentThreadId);
  }
  *(_DWORD *)a7 = -1073741822;
  *(_QWORD *)(a7 + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x14001ce30  push    rbx
0x14001ce32  sub     rsp, 20h
0x14001ce36  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ce3d  lea     rax, WPP_GLOBAL_Control
0x14001ce44  cmp     rbx, rax
0x14001ce47  jz      short loc_14001CE79
0x14001ce49  test    dword ptr [rbx+2Ch], 4000h
0x14001ce50  jz      short loc_14001CE79
0x14001ce52  mov     rbx, [rbx+18h]
0x14001ce56  call    cs:__imp_PsGetCurrentThreadId
0x14001ce5d  nop     dword ptr [rax+rax+00h]
0x14001ce62  mov     edx, 30h ; '0'
0x14001ce67  lea     r8, WPP_7ebb59d433c73ef4df0f91ab4e4668ee_Traceguids
0x14001ce6e  mov     r9, rax
0x14001ce71  mov     rcx, rbx
0x14001ce74  call    WPP_SF_q
0x14001ce79  mov     rax, [rsp+28h+arg_30]
0x14001ce7e  mov     dword ptr [rax], 0C0000002h
0x14001ce84  mov     qword ptr [rax+8], 0
0x14001ce8c  xor     al, al
0x14001ce8e  add     rsp, 20h
0x14001ce92  pop     rbx
0x14001ce93  retn
```
