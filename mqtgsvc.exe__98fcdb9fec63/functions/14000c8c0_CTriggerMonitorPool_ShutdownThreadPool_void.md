# CTriggerMonitorPool::ShutdownThreadPool(void)

- ea: `0x14000c8c0`
- end: `0x14000c9a8`
- name: `?ShutdownThreadPool@CTriggerMonitorPool@@QEAAJXZ`
- size: `232`
- prototype: `__int64 __fastcall(CTriggerMonitorPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d75c`
- `0x14001e594`

## callees

- `0x140006458`
- `0x140007554`
- `0x14000c8c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000c93c`
- `KERNEL32!LeaveCriticalSection` at `0x14000c94d`
- `KERNEL32!LeaveCriticalSection` at `0x14000c93c`
- `KERNEL32!LeaveCriticalSection` at `0x14000c94d`
- `KERNEL32!GetLastError` at `0x14000c913`
- `KERNEL32!GetLastError` at `0x14000c913`
- `KERNEL32!SetEvent` at `0x14000c8f0`
- `KERNEL32!SetEvent` at `0x14000c8f0`
- `KERNEL32!WaitForSingleObject` at `0x14000c95d`
- `KERNEL32!WaitForSingleObject` at `0x14000c95d`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::ShutdownThreadPool(CTriggerMonitorPool *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  CCriticalSection::Lock((struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
  *((_DWORD *)this + 34) = 2;
  if ( !SetEvent(*((HANDLE *)this + 19)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    }
    LeaveCriticalSection(v2);
    return 2147500037LL;
  }
  LeaveCriticalSection(v2);
  if ( WaitForSingleObject(*((HANDLE *)this + 4), 0xFFFFFFFF) == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14000c8c0  mov     [rsp+arg_8], rbx
0x14000c8c5  push    rdi
0x14000c8c6  sub     rsp, 20h
0x14000c8ca  mov     rdi, rcx
0x14000c8cd  lea     rbx, [rcx+60h]
0x14000c8d1  mov     [rsp+28h+arg_0], rbx
0x14000c8d6  mov     rcx, rbx; this
0x14000c8d9  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x14000c8de  nop
0x14000c8df  mov     dword ptr [rdi+88h], 2
0x14000c8e9  mov     rcx, [rdi+98h]; hEvent
0x14000c8f0  call    cs:__imp_SetEvent
0x14000c8f6  test    eax, eax
0x14000c8f8  jnz     short loc_14000C94A
0x14000c8fa  lea     rax, WPP_GLOBAL_Control
0x14000c901  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c908  cmp     rcx, rax
0x14000c90b  jz      short loc_14000C939
0x14000c90d  test    byte ptr [rcx+1Ch], 1
0x14000c911  jz      short loc_14000C939
0x14000c913  call    cs:__imp_GetLastError
0x14000c919  mov     edx, 16h
0x14000c91e  mov     r9d, eax
0x14000c921  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000c928  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c92f  mov     rcx, [rcx+10h]
0x14000c933  call    WPP_SF_d
0x14000c938  nop
0x14000c939  mov     rcx, rbx; lpCriticalSection
0x14000c93c  call    cs:__imp_LeaveCriticalSection
0x14000c942  nop
0x14000c943  mov     eax, 80004005h
0x14000c948  jmp     short loc_14000C99D
0x14000c94a  mov     rcx, rbx; lpCriticalSection
0x14000c94d  call    cs:__imp_LeaveCriticalSection
0x14000c953  nop
0x14000c954  or      ebx, 0FFFFFFFFh
0x14000c957  mov     edx, ebx; dwMilliseconds
0x14000c959  mov     rcx, [rdi+20h]; hHandle
0x14000c95d  call    cs:__imp_WaitForSingleObject
0x14000c963  cmp     eax, ebx
0x14000c965  jnz     short loc_14000C99B
0x14000c967  lea     rax, WPP_GLOBAL_Control
0x14000c96e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c975  cmp     rcx, rax
0x14000c978  jz      short loc_14000C943
0x14000c97a  test    byte ptr [rcx+1Ch], 1
0x14000c97e  jz      short loc_14000C943
0x14000c980  mov     edx, 17h
0x14000c985  or      r9d, 0FFFFFFFFh
0x14000c989  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000c990  mov     rcx, [rcx+10h]
0x14000c994  call    WPP_SF_d
0x14000c999  jmp     short loc_14000C943
0x14000c99b  xor     eax, eax
0x14000c99d  mov     rbx, [rsp+28h+arg_8]
0x14000c9a2  add     rsp, 20h
0x14000c9a6  pop     rdi
0x14000c9a7  retn
```
