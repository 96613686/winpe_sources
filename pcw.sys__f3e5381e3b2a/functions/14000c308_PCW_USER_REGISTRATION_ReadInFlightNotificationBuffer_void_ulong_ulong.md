# PCW_USER_REGISTRATION::ReadInFlightNotificationBuffer(void *,ulong,ulong *)

- ea: `0x14000c308`
- end: `0x14000c45a`
- name: `?ReadInFlightNotificationBuffer@PCW_USER_REGISTRATION@@QEAAJPEAXKPEAK@Z`
- size: `338`
- prototype: `__int64 __fastcall(PCW_USER_REGISTRATION *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a750`

## callees

- `0x14000c308`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c32b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c363`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c32b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c363`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c41a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c43b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c41a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c43b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000c3ad`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000c3ad`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c340`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c374`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c340`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c374`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c3f1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c40e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c42f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c3f1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c40e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c42f`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14000c3de`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14000c3de`

## pseudocode

```c
__int64 __fastcall PCW_USER_REGISTRATION::ReadInFlightNotificationBuffer(
        PCW_USER_REGISTRATION *this,
        void *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rbx
  __int64 CurrentProcess; // rax
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)this + 32, 0);
  v8 = *((_QWORD *)this + 10);
  if ( !v8 || *((_BYTE *)this + 92) )
  {
    ExReleasePushLockExclusiveEx((char *)this + 32, 0);
    KeLeaveCriticalRegion();
    return 3221225860LL;
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v8, 0);
    if ( *(_BYTE *)(v8 + 68) )
    {
      v9 = -1073741536;
    }
    else
    {
      v10 = *(_DWORD *)(v8 + 56);
      if ( v10 <= a3 )
      {
        if ( v10 )
        {
          *a4 = v10;
          v11 = *(unsigned int *)(v8 + 56);
          CurrentProcess = PsGetCurrentProcess();
          v9 = MmCopyVirtualMemory(*(_QWORD *)(v8 + 32), *(_QWORD *)(v8 + 40), CurrentProcess, a2, v11, 0, &v14);
        }
        else
        {
          *a4 = 0;
          v9 = 0;
        }
      }
      else
      {
        *a4 = v10;
        v9 = -2147483643;
      }
    }
    ExReleasePushLockExclusiveEx(v8, 0);
    KeLeaveCriticalRegion();
    ExReleasePushLockExclusiveEx((char *)this + 32, 0);
    KeLeaveCriticalRegion();
    return v9;
  }
}

```

## disassembly

```asm
0x14000c308  mov     rax, rsp
0x14000c30b  push    rbx
0x14000c30c  push    rbp
0x14000c30d  push    rsi
0x14000c30e  push    rdi
0x14000c30f  push    r14
0x14000c311  push    r15
0x14000c313  sub     rsp, 48h
0x14000c317  mov     rbx, r9
0x14000c31a  mov     qword ptr [rax+8], 0
0x14000c322  mov     r14d, r8d
0x14000c325  mov     r15, rdx
0x14000c328  mov     rbp, rcx
0x14000c32b  call    cs:__imp_KeEnterCriticalRegion
0x14000c332  nop     dword ptr [rax+rax+00h]
0x14000c337  lea     rsi, [rbp+20h]
0x14000c33b  xor     edx, edx
0x14000c33d  mov     rcx, rsi
0x14000c340  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c347  nop     dword ptr [rax+rax+00h]
0x14000c34c  mov     rdi, [rbp+50h]
0x14000c350  test    rdi, rdi
0x14000c353  jz      loc_14000C42A
0x14000c359  cmp     byte ptr [rbp+5Ch], 0
0x14000c35d  jnz     loc_14000C42A
0x14000c363  call    cs:__imp_KeEnterCriticalRegion
0x14000c36a  nop     dword ptr [rax+rax+00h]
0x14000c36f  xor     edx, edx
0x14000c371  mov     rcx, rdi
0x14000c374  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c37b  nop     dword ptr [rax+rax+00h]
0x14000c380  cmp     byte ptr [rdi+44h], 0
0x14000c384  jz      short loc_14000C38D
0x14000c386  mov     ebx, 0C0000120h
0x14000c38b  jmp     short loc_14000C3EC
0x14000c38d  mov     eax, [rdi+38h]
0x14000c390  cmp     eax, r14d
0x14000c393  jbe     short loc_14000C39E
0x14000c395  mov     [rbx], eax
0x14000c397  mov     ebx, 80000005h
0x14000c39c  jmp     short loc_14000C3EC
0x14000c39e  test    eax, eax
0x14000c3a0  jnz     short loc_14000C3A8
0x14000c3a2  mov     [rbx], eax
0x14000c3a4  xor     ebx, ebx
0x14000c3a6  jmp     short loc_14000C3EC
0x14000c3a8  mov     [rbx], eax
0x14000c3aa  mov     ebx, [rdi+38h]
0x14000c3ad  call    cs:__imp_PsGetCurrentProcess
0x14000c3b4  nop     dword ptr [rax+rax+00h]
0x14000c3b9  mov     rdx, [rdi+28h]
0x14000c3bd  lea     rcx, [rsp+78h+arg_0]
0x14000c3c5  mov     [rsp+78h+var_48], rcx
0x14000c3ca  mov     r9, r15
0x14000c3cd  mov     rcx, [rdi+20h]
0x14000c3d1  mov     r8, rax
0x14000c3d4  mov     [rsp+78h+var_50], 0
0x14000c3d9  mov     [rsp+78h+var_58], rbx
0x14000c3de  call    cs:__imp_MmCopyVirtualMemory
0x14000c3e5  nop     dword ptr [rax+rax+00h]
0x14000c3ea  mov     ebx, eax
0x14000c3ec  xor     edx, edx
0x14000c3ee  mov     rcx, rdi
0x14000c3f1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c3f8  nop     dword ptr [rax+rax+00h]
0x14000c3fd  call    cs:__imp_KeLeaveCriticalRegion
0x14000c404  nop     dword ptr [rax+rax+00h]
0x14000c409  xor     edx, edx
0x14000c40b  mov     rcx, rsi
0x14000c40e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c415  nop     dword ptr [rax+rax+00h]
0x14000c41a  call    cs:__imp_KeLeaveCriticalRegion
0x14000c421  nop     dword ptr [rax+rax+00h]
0x14000c426  mov     eax, ebx
0x14000c428  jmp     short loc_14000C44C
0x14000c42a  xor     edx, edx
0x14000c42c  mov     rcx, rsi
0x14000c42f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c436  nop     dword ptr [rax+rax+00h]
0x14000c43b  call    cs:__imp_KeLeaveCriticalRegion
0x14000c442  nop     dword ptr [rax+rax+00h]
0x14000c447  mov     eax, 0C0000184h
0x14000c44c  add     rsp, 48h
0x14000c450  pop     r15
0x14000c452  pop     r14
0x14000c454  pop     rdi
0x14000c455  pop     rsi
0x14000c456  pop     rbp
0x14000c457  pop     rbx
0x14000c458  retn
```
