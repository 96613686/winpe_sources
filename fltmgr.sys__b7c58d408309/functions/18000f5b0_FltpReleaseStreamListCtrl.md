# FltpReleaseStreamListCtrl

- ea: `0x18000f5b0`
- end: `0x18000f679`
- name: `FltpReleaseStreamListCtrl`
- size: `201`
- prototype: `void __fastcall(char *Entry)`
- caller_count: `34`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800019a0`
- `0x1800025b0`
- `0x1800047e0`
- `0x180009f80`
- `0x18000d740`
- `0x18000dc10`
- `0x18000e5e0`
- `0x18000eb80`
- `0x180011430`
- `0x180012130`
- `0x1800128f0`
- `0x180013100`
- `0x180017610`
- `0x180017d00`
- `0x180018280`
- `0x18004fbf0`
- `0x180054420`
- `0x1800546e0`
- `0x180054760`
- `0x18005b920`
- `0x180060610`
- `0x180060cd0`
- `0x180061050`
- `0x180061190`
- `0x1800612f0`
- `0x1800614b0`
- `0x180062ba0`
- `0x180062db0`
- `0x180064b40`
- `0x18006ba60`
- `0x18006c900`
- `0x18006ccf0`
- `0x180071ac0`
- `0x1800745f0`

## callees

- `0x18000f5b0`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f62c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f642`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f62c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000f642`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f5e0`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f5f3`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f5e0`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18000f5f3`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000f612`
- `ntoskrnl!IoUninitializeWorkItem` at `0x18000f612`

## pseudocode

```c
void __fastcall FltpReleaseStreamListCtrl(char *Entry)
{
  __int64 v2; // rcx

  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      (_DWORD)Entry,
      (unsigned int)StreamListCtrlSup_c754,
      (unsigned int)"FltpReleaseStreamListCtrl",
      (_DWORD)Entry,
      *((_DWORD *)Entry + 16),
      *((_DWORD *)Entry + 17));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 17, 0xFFFFFFFF) == 1 )
  {
    ExCleanupAutoExpandPushLock(Entry + 72);
    ExCleanupAutoExpandPushLock(Entry + 368);
    v2 = *((_QWORD *)Entry + 45);
    if ( v2 )
    {
      IoUninitializeWorkItem(*(PIO_WORKITEM *)(v2 + 320));
      ExFreeToNPagedLookasideList(&stru_18003F1C0, *((PVOID *)Entry + 45));
    }
    ExFreeToNPagedLookasideList(&stru_18003EB40, Entry);
  }
}

```

## disassembly

```asm
0x18000f5b0  push    rbx
0x18000f5b2  sub     rsp, 30h
0x18000f5b6  test    cs:byte_1800404C2, 1
0x18000f5bd  mov     rbx, rcx
0x18000f5c0  jnz     loc_18000F650
0x18000f5c6  mov     eax, 0FFFFFFFFh
0x18000f5cb  lock xadd [rbx+44h], eax
0x18000f5d0  cmp     eax, 1
0x18000f5d3  jz      short loc_18000F5DC
0x18000f5d5  add     rsp, 30h
0x18000f5d9  pop     rbx
0x18000f5da  retn
0x18000f5dc  lea     rcx, [rbx+48h]
0x18000f5e0  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000f5e7  nop     dword ptr [rax+rax+00h]
0x18000f5ec  lea     rcx, [rbx+170h]
0x18000f5f3  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18000f5fa  nop     dword ptr [rax+rax+00h]
0x18000f5ff  mov     rcx, [rbx+168h]
0x18000f606  test    rcx, rcx
0x18000f609  jz      short loc_18000F638
0x18000f60b  mov     rcx, [rcx+140h]; IoWorkItem
0x18000f612  call    cs:__imp_IoUninitializeWorkItem
0x18000f619  nop     dword ptr [rax+rax+00h]
0x18000f61e  mov     rdx, [rbx+168h]; Entry
0x18000f625  lea     rcx, stru_18003F1C0; Lookaside
0x18000f62c  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000f633  nop     dword ptr [rax+rax+00h]
0x18000f638  mov     rdx, rbx; Entry
0x18000f63b  lea     rcx, stru_18003EB40; Lookaside
0x18000f642  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000f649  nop     dword ptr [rax+rax+00h]
0x18000f64e  jmp     short loc_18000F5D5
0x18000f650  mov     eax, [rcx+44h]
0x18000f653  lea     r8, aFltpreleasestr; "FltpReleaseStreamListCtrl"
0x18000f65a  mov     [rsp+38h+var_10], eax
0x18000f65e  lea     rdx, StreamListCtrlSup_c754
0x18000f665  mov     eax, [rcx+40h]
0x18000f668  mov     r9, rbx
0x18000f66b  mov     [rsp+38h+var_18], eax
0x18000f66f  call    McTemplateU0spdd_EtwWriteTransfer
0x18000f674  jmp     loc_18000F5C6
```
