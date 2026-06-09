# MRxDAVFastIoWrite

- ea: `0x140023fc0`
- end: `0x140024025`
- name: `MRxDAVFastIoWrite`
- size: `101`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x140023fc0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140023fe6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023fe6`

## pseudocode

```c
char __fastcall MRxDAVFastIoWrite(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
{
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v7, 51, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids, CurrentThreadId);
  }
  *(_DWORD *)a7 = -1073741822;
  *(_QWORD *)(a7 + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x140023fc0  push    rbx
0x140023fc2  sub     rsp, 20h
0x140023fc6  mov     rbx, cs:WPP_GLOBAL_Control
0x140023fcd  lea     rax, WPP_GLOBAL_Control
0x140023fd4  cmp     rbx, rax
0x140023fd7  jz      short loc_140024009
0x140023fd9  test    dword ptr [rbx+2Ch], 4000h
0x140023fe0  jz      short loc_140024009
0x140023fe2  mov     rbx, [rbx+18h]
0x140023fe6  call    cs:__imp_PsGetCurrentThreadId
0x140023fed  nop     dword ptr [rax+rax+00h]
0x140023ff2  mov     edx, 33h ; '3'
0x140023ff7  lea     r8, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids
0x140023ffe  mov     r9, rax
0x140024001  mov     rcx, rbx
0x140024004  call    WPP_SF_q
0x140024009  mov     rax, [rsp+28h+arg_30]
0x14002400e  mov     dword ptr [rax], 0C0000002h
0x140024014  mov     qword ptr [rax+8], 0
0x14002401c  xor     al, al
0x14002401e  add     rsp, 20h
0x140024022  pop     rbx
0x140024023  retn
```
