# PruneDirectoryCache

- ea: `0x1400209b0`
- end: `0x140020aeb`
- name: `PruneDirectoryCache`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140012c40`

## callees

- `0x140008140`
- `0x1400159cc`
- `0x14001837c`
- `0x1400209b0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020a09`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020a30`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020a09`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020a30`
- `ntoskrnl!KeReleaseMutex` at `0x140020a6d`
- `ntoskrnl!KeReleaseMutex` at `0x140020a95`
- `ntoskrnl!KeReleaseMutex` at `0x140020aa6`
- `ntoskrnl!KeReleaseMutex` at `0x140020a6d`
- `ntoskrnl!KeReleaseMutex` at `0x140020a95`
- `ntoskrnl!KeReleaseMutex` at `0x140020aa6`

## pseudocode

```c
_BOOL8 __fastcall PruneDirectoryCache(__int64 a1, struct _KMUTANT *a2, unsigned __int64 a3)
{
  __int64 i; // rbx
  BOOL v7; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  KeWaitForSingleObject(a2, Executive, 0, 0, 0);
  KeWaitForSingleObject((PVOID)(a1 + 2152), Executive, 0, 0, 0);
  for ( i = (__int64)a2[1].MutantListEntry.Blink; i && *(unsigned int *)(a1 + 2340) < a3; i = *(_QWORD *)(i + 16) )
  {
    HacAcquireLock(i);
    if ( *(_QWORD *)(i + 32) )
      DeleteDirCache(a1, i);
    KeReleaseMutex(*(PRKMUTEX *)(i + 40), 0);
  }
  v7 = *(unsigned int *)(a1 + 2340) >= a3;
  KeReleaseMutex((PRKMUTEX)(a1 + 2152), 0);
  KeReleaseMutex(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x1400209b0  push    rbx
0x1400209b2  push    rbp
0x1400209b3  push    rsi
0x1400209b4  push    rdi
0x1400209b5  push    r12
0x1400209b7  push    r14
0x1400209b9  sub     rsp, 38h
0x1400209bd  mov     rsi, r8
0x1400209c0  mov     rbp, rdx
0x1400209c3  mov     rdi, rcx
0x1400209c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400209cd  lea     r12, WPP_GLOBAL_Control
0x1400209d4  cmp     rcx, r12
0x1400209d7  jz      short loc_1400209F5
0x1400209d9  mov     eax, [rcx+2Ch]
0x1400209dc  test    al, 40h
0x1400209de  jz      short loc_1400209F5
0x1400209e0  mov     rcx, [rcx+18h]
0x1400209e4  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x1400209eb  mov     edx, 2Fh ; '/'
0x1400209f0  call    WPP_SF_
0x1400209f5  xor     r9d, r9d; Alertable
0x1400209f8  mov     [rsp+68h+Timeout], 0; Timeout
0x140020a01  xor     r8d, r8d; WaitMode
0x140020a04  xor     edx, edx; WaitReason
0x140020a06  mov     rcx, rbp; Object
0x140020a09  call    cs:__imp_KeWaitForSingleObject
0x140020a10  nop     dword ptr [rax+rax+00h]
0x140020a15  lea     r14, [rdi+868h]
0x140020a1c  mov     [rsp+68h+Timeout], 0; Timeout
0x140020a25  mov     rcx, r14; Object
0x140020a28  xor     r9d, r9d; Alertable
0x140020a2b  xor     r8d, r8d; WaitMode
0x140020a2e  xor     edx, edx; WaitReason
0x140020a30  call    cs:__imp_KeWaitForSingleObject
0x140020a37  nop     dword ptr [rax+rax+00h]
0x140020a3c  mov     rbx, [rbp+58h]
0x140020a40  jmp     short loc_140020A7D
0x140020a42  mov     eax, [rdi+924h]
0x140020a48  cmp     rax, rsi
0x140020a4b  jnb     short loc_140020A82
0x140020a4d  mov     rcx, rbx
0x140020a50  call    HacAcquireLock
0x140020a55  cmp     qword ptr [rbx+20h], 0
0x140020a5a  jz      short loc_140020A67
0x140020a5c  mov     rdx, rbx
0x140020a5f  mov     rcx, rdi
0x140020a62  call    DeleteDirCache
0x140020a67  mov     rcx, [rbx+28h]; Mutex
0x140020a6b  xor     edx, edx; Wait
0x140020a6d  call    cs:__imp_KeReleaseMutex
0x140020a74  nop     dword ptr [rax+rax+00h]
0x140020a79  mov     rbx, [rbx+10h]
0x140020a7d  test    rbx, rbx
0x140020a80  jnz     short loc_140020A42
0x140020a82  mov     eax, [rdi+924h]
0x140020a88  xor     ebx, ebx
0x140020a8a  cmp     rax, rsi
0x140020a8d  mov     rcx, r14; Mutex
0x140020a90  setnb   bl
0x140020a93  xor     edx, edx; Wait
0x140020a95  call    cs:__imp_KeReleaseMutex
0x140020a9c  nop     dword ptr [rax+rax+00h]
0x140020aa1  xor     edx, edx; Wait
0x140020aa3  mov     rcx, rbp; Mutex
0x140020aa6  call    cs:__imp_KeReleaseMutex
0x140020aad  nop     dword ptr [rax+rax+00h]
0x140020ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ab9  cmp     rcx, r12
0x140020abc  jz      short loc_140020ADB
0x140020abe  mov     edx, [rcx+2Ch]
0x140020ac1  test    dl, 40h
0x140020ac4  jz      short loc_140020ADB
0x140020ac6  mov     rcx, [rcx+18h]
0x140020aca  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140020ad1  mov     edx, 30h ; '0'
0x140020ad6  call    WPP_SF_
0x140020adb  mov     eax, ebx
0x140020add  add     rsp, 38h
0x140020ae1  pop     r14
0x140020ae3  pop     r12
0x140020ae5  pop     rdi
0x140020ae6  pop     rsi
0x140020ae7  pop     rbp
0x140020ae8  pop     rbx
0x140020ae9  retn
```
