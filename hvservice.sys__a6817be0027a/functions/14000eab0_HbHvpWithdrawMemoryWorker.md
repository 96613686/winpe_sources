# HbHvpWithdrawMemoryWorker

- ea: `0x14000eab0`
- end: `0x14000eb9c`
- name: `HbHvpWithdrawMemoryWorker`
- size: `236`
- prototype: `void __fastcall(PVOID IoObject, struct _IO_REMOVE_LOCK *Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ea28`

## callees

- `0x140002ae0`
- `0x14000eab0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000eb73`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000eb73`
- `ntoskrnl!IoFreeWorkItem` at `0x14000eb5a`
- `ntoskrnl!IoFreeWorkItem` at `0x14000eb5a`
- `winhvr!WinHvWithdrawMemory` at `0x14000eb46`
- `winhvr!WinHvWithdrawMemory` at `0x14000eb46`
- `winhvr!WinHvWaitForWithdrawAllowed` at `0x14000eb28`
- `winhvr!WinHvWaitForWithdrawAllowed` at `0x14000eb28`
- `winhvr!WinHvGetPartitionId` at `0x14000eb06`
- `winhvr!WinHvGetPartitionId` at `0x14000eb06`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemory` at `0x14000eb1c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemory` at `0x14000eb1c`

## pseudocode

```c
void __fastcall HbHvpWithdrawMemoryWorker(PVOID IoObject, struct _IO_REMOVE_LOCK *Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v5; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF

  v7[0] = 1319266201;
  v7[1] = 1243467996;
  v7[2] = 1462752922;
  v7[3] = -1644386514;
  v6 = 0;
  v5 = 0;
  if ( (int)WinHvGetPartitionId(&v5) >= 0 )
  {
    KsrFreePersistedMemory(v7, 0);
    WinHvWaitForWithdrawAllowed();
    WinHvWithdrawMemory(v5, -1, 0x80000000LL, &v6);
  }
  if ( IoWorkItem )
    IoFreeWorkItem(IoWorkItem);
  IoReleaseRemoveLockEx(Context + 2, Context, 0x20u);
}

```

## disassembly

```asm
0x14000eab0  mov     [rsp-8+arg_0], rbx
0x14000eab5  mov     [rsp-8+arg_18], rdi
0x14000eaba  push    rbp
0x14000eabb  mov     rbp, rsp
0x14000eabe  sub     rsp, 50h
0x14000eac2  mov     rax, cs:__security_cookie
0x14000eac9  xor     rax, rsp
0x14000eacc  mov     [rbp+var_10], rax
0x14000ead0  lea     rcx, [rbp+var_30]
0x14000ead4  mov     [rbp+var_20], 4EA26799h
0x14000eadb  mov     rbx, r8
0x14000eade  mov     [rbp+var_1C], 4A1DD0DCh
0x14000eae5  mov     rdi, rdx
0x14000eae8  mov     [rbp+var_18], 572FD69Ah
0x14000eaef  mov     [rbp+var_14], 9DFCA72Eh
0x14000eaf6  mov     [rbp+var_28], 0
0x14000eafe  mov     [rbp+var_30], 0
0x14000eb06  call    cs:__imp_WinHvGetPartitionId
0x14000eb0d  nop     dword ptr [rax+rax+00h]
0x14000eb12  test    eax, eax
0x14000eb14  js      short loc_14000EB52
0x14000eb16  xor     edx, edx
0x14000eb18  lea     rcx, [rbp+var_20]
0x14000eb1c  call    cs:__imp_KsrFreePersistedMemory
0x14000eb23  nop     dword ptr [rax+rax+00h]
0x14000eb28  call    cs:__imp_WinHvWaitForWithdrawAllowed
0x14000eb2f  nop     dword ptr [rax+rax+00h]
0x14000eb34  mov     rcx, [rbp+var_30]
0x14000eb38  lea     r9, [rbp+var_28]
0x14000eb3c  mov     r8d, 80000000h
0x14000eb42  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000eb46  call    cs:__imp_WinHvWithdrawMemory
0x14000eb4d  nop     dword ptr [rax+rax+00h]
0x14000eb52  test    rbx, rbx
0x14000eb55  jz      short loc_14000EB66
0x14000eb57  mov     rcx, rbx; IoWorkItem
0x14000eb5a  call    cs:__imp_IoFreeWorkItem
0x14000eb61  nop     dword ptr [rax+rax+00h]
0x14000eb66  lea     rcx, [rdi+40h]; RemoveLock
0x14000eb6a  mov     r8d, 20h ; ' '; RemlockSize
0x14000eb70  mov     rdx, rdi; Tag
0x14000eb73  call    cs:__imp_IoReleaseRemoveLockEx
0x14000eb7a  nop     dword ptr [rax+rax+00h]
0x14000eb7f  mov     rcx, [rbp+var_10]
0x14000eb83  xor     rcx, rsp; StackCookie
0x14000eb86  call    __security_check_cookie
0x14000eb8b  mov     rbx, [rsp+50h+arg_0]
0x14000eb90  mov     rdi, [rsp+50h+arg_18]
0x14000eb95  add     rsp, 50h
0x14000eb99  pop     rbp
0x14000eb9a  retn
```
