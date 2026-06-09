# ScheduleWorkItem

- ea: `0x1400028f0`
- end: `0x14000297e`
- name: `ScheduleWorkItem`
- size: `142`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140005674`
- `0x140005ee0`
- `0x140006a00`
- `0x14000f588`
- `0x14000fbac`
- `0x140011c00`
- `0x1400122b0`
- `0x140014c30`
- `0x140018890`

## callees

- `0x1400028f0`
- `0x140002990`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002951`
- `ntoskrnl!KeSetEvent` at `0x140002951`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002939`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002939`

## pseudocode

```c
__int64 __fastcall ScheduleWorkItem(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // rax

  v8 = MyMemAlloc(48, 1230459984);
  if ( v8 )
  {
    *(_QWORD *)(v8 + 24) = a2;
    *(_QWORD *)(v8 + 32) = a3;
    *(_DWORD *)(v8 + 40) = a4;
    *(_QWORD *)(v8 + 16) = a1;
    ExInterlockedInsertTailList(&WorkItemList, (PLIST_ENTRY)v8, &GlobalThreadLock);
    KeSetEvent(&EventPassiveThread, 0, 0);
    return 0;
  }
  else
  {
    ++dword_14000B480;
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x1400028f0  push    rbx
0x1400028f2  push    rbp
0x1400028f3  push    rsi
0x1400028f4  push    rdi
0x1400028f5  sub     rsp, 28h
0x1400028f9  mov     rsi, rdx
0x1400028fc  mov     rbp, rcx
0x1400028ff  mov     edx, 49575450h
0x140002904  mov     ecx, 30h ; '0'
0x140002909  mov     ebx, r9d
0x14000290c  mov     rdi, r8
0x14000290f  call    MyMemAlloc
0x140002914  test    rax, rax
0x140002917  jz      short loc_140002969
0x140002919  lea     r8, GlobalThreadLock; Lock
0x140002920  mov     [rax+18h], rsi
0x140002924  mov     rdx, rax; ListEntry
0x140002927  mov     [rax+20h], rdi
0x14000292b  lea     rcx, WorkItemList; ListHead
0x140002932  mov     [rax+28h], ebx
0x140002935  mov     [rax+10h], rbp
0x140002939  call    cs:__imp_ExInterlockedInsertTailList
0x140002940  nop     dword ptr [rax+rax+00h]
0x140002945  xor     r8d, r8d; Wait
0x140002948  lea     rcx, EventPassiveThread; Event
0x14000294f  xor     edx, edx; Increment
0x140002951  call    cs:__imp_KeSetEvent
0x140002958  nop     dword ptr [rax+rax+00h]
0x14000295d  xor     eax, eax
0x14000295f  add     rsp, 28h
0x140002963  pop     rdi
0x140002964  pop     rsi
0x140002965  pop     rbp
0x140002966  pop     rbx
0x140002967  retn
0x140002969  inc     cs:dword_14000B480
0x14000296f  mov     eax, 0C0000001h
0x140002974  add     rsp, 28h
0x140002978  pop     rdi
0x140002979  pop     rsi
0x14000297a  pop     rbp
0x14000297b  pop     rbx
0x14000297c  retn
```
