# CWorkManager::SignalJobRunning(CWorkObject *)

- ea: `0x18004a4b8`
- end: `0x18004a65f`
- name: `?SignalJobRunning@CWorkManager@@AEAAHPEAVCWorkObject@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CWorkManager *__hidden this, struct CWorkObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180049570`

## callees

- `0x18001ad74`
- `0x180031f3c`
- `0x1800320d0`
- `0x18004a4b8`
- `0x18004ab1c`
- `0x18004ab90`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x18004a5a0`
- `KERNEL32!DuplicateHandle` at `0x18004a5a0`
- `KERNEL32!GetCurrentProcess` at `0x18004a558`
- `KERNEL32!GetCurrentProcess` at `0x18004a576`
- `KERNEL32!GetCurrentProcess` at `0x18004a558`
- `KERNEL32!GetCurrentProcess` at `0x18004a576`
- `KERNEL32!GetCurrentThread` at `0x18004a567`
- `KERNEL32!GetCurrentThread` at `0x18004a567`
- `KERNEL32!GetLastError` at `0x18004a5b0`
- `KERNEL32!GetLastError` at `0x18004a5b0`
- `KERNEL32!SetLastError` at `0x18004a5c0`
- `KERNEL32!SetLastError` at `0x18004a637`
- `KERNEL32!SetLastError` at `0x18004a5c0`
- `KERNEL32!SetLastError` at `0x18004a637`

## pseudocode

```c
__int64 __fastcall CWorkManager::SignalJobRunning(CWorkManager *this, struct CWorkObject *a2)
{
  DWORD LastError; // ebp
  CCriticalSection *v5; // r15
  PVOID *v6; // rsi
  __int64 *v7; // rax
  __int64 v8; // rbx
  HANDLE CurrentProcess; // rsi
  HANDLE CurrentThread; // rdi
  HANDLE v11; // rax
  HANDLE TargetHandle; // [rsp+78h] [rbp+10h] BYREF
  char v14; // [rsp+80h] [rbp+18h] BYREF

  LastError = 0;
  if ( a2 )
  {
    v5 = (CWorkManager *)((char *)this + 56);
    CCriticalSection::Lock((CWorkManager *)((char *)this + 56));
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, a2);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    TargetHandle = a2;
    v7 = (__int64 *)std::_Tree<std::_Tmap_traits<void *,CWorkManager::WorkMangerInProcessJob,std::less<void *>,std::allocator<std::pair<void * const,CWorkManager::WorkMangerInProcessJob>>,0>>::find(
                      (char *)this + 104,
                      &v14,
                      &TargetHandle);
    v8 = *v7;
    if ( *v7 == *((_QWORD *)this + 13) )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        WPP_SF_q(v6[2], 12, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, a2);
    }
    else if ( !*(_QWORD *)(v8 + 48) )
    {
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      v11 = GetCurrentProcess();
      if ( DuplicateHandle(v11, CurrentThread, CurrentProcess, &TargetHandle, 2u, 0, 0) )
      {
        *(_QWORD *)(v8 + 48) = TargetHandle;
      }
      else
      {
        LastError = GetLastError();
        SetLastError(LastError);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, LastError);
      }
    }
    CCriticalSection::UnLock(v5);
  }
  else
  {
    LastError = 13;
    SetLastError(0xDu);
  }
  return LastError;
}

```

## disassembly

```asm
0x18004a4b8  mov     [rsp+arg_0], rbx
0x18004a4bd  mov     [rsp+arg_18], rbp
0x18004a4c2  push    rsi
0x18004a4c3  push    rdi
0x18004a4c4  push    r12
0x18004a4c6  push    r14
0x18004a4c8  push    r15
0x18004a4ca  sub     rsp, 40h
0x18004a4ce  xor     ebp, ebp
0x18004a4d0  mov     r14, rdx
0x18004a4d3  mov     rdi, rcx
0x18004a4d6  test    rdx, rdx
0x18004a4d9  jz      loc_18004A630
0x18004a4df  lea     r15, [rcx+38h]
0x18004a4e3  mov     rcx, r15; this
0x18004a4e6  call    ?Lock@CCriticalSection@@QEAAXXZ; CCriticalSection::Lock(void)
0x18004a4eb  mov     rsi, cs:WPP_GLOBAL_Control
0x18004a4f2  lea     r12, WPP_GLOBAL_Control
0x18004a4f9  cmp     rsi, r12
0x18004a4fc  jz      short loc_18004A521
0x18004a4fe  test    byte ptr [rsi+1Ch], 20h
0x18004a502  jz      short loc_18004A521
0x18004a504  mov     rcx, [rsi+10h]
0x18004a508  lea     edx, [rbp+0Ah]
0x18004a50b  mov     r9, r14
0x18004a50e  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a515  call    WPP_SF_q
0x18004a51a  mov     rsi, cs:WPP_GLOBAL_Control
0x18004a521  lea     r8, [rsp+68h+TargetHandle]
0x18004a526  mov     [rsp+68h+TargetHandle], r14
0x18004a52b  lea     rdx, [rsp+68h+arg_10]
0x18004a533  lea     rcx, [rdi+68h]
0x18004a537  call    ?find@?$_Tree@V?$_Tmap_traits@PEAXUWorkMangerInProcessJob@CWorkManager@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXUWorkMangerInProcessJob@CWorkManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXUWorkMangerInProcessJob@CWorkManager@@@std@@@std@@@std@@@2@AEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,CWorkManager::WorkMangerInProcessJob,std::less<void *>,std::allocator<std::pair<void * const,CWorkManager::WorkMangerInProcessJob>>,0>>::find(void * const &)
0x18004a53c  mov     rbx, [rax]
0x18004a53f  cmp     rbx, [rdi+68h]
0x18004a543  jz      loc_18004A603
0x18004a549  cmp     [rbx+30h], rbp
0x18004a54d  jnz     loc_18004A626
0x18004a553  mov     [rsp+68h+TargetHandle], rbp
0x18004a558  call    cs:__imp_GetCurrentProcess
0x18004a55f  nop     dword ptr [rax+rax+00h]
0x18004a564  mov     rsi, rax
0x18004a567  call    cs:__imp_GetCurrentThread
0x18004a56e  nop     dword ptr [rax+rax+00h]
0x18004a573  mov     rdi, rax
0x18004a576  call    cs:__imp_GetCurrentProcess
0x18004a57d  nop     dword ptr [rax+rax+00h]
0x18004a582  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x18004a586  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18004a58b  mov     rcx, rax; hSourceProcessHandle
0x18004a58e  mov     [rsp+68h+bInheritHandle], ebp; bInheritHandle
0x18004a592  mov     r8, rsi; hTargetProcessHandle
0x18004a595  mov     [rsp+68h+dwDesiredAccess], 2; dwDesiredAccess
0x18004a59d  mov     rdx, rdi; hSourceHandle
0x18004a5a0  call    cs:__imp_DuplicateHandle
0x18004a5a7  nop     dword ptr [rax+rax+00h]
0x18004a5ac  test    eax, eax
0x18004a5ae  jnz     short loc_18004A5F8
0x18004a5b0  call    cs:__imp_GetLastError
0x18004a5b7  nop     dword ptr [rax+rax+00h]
0x18004a5bc  mov     ecx, eax; dwErrCode
0x18004a5be  mov     ebp, eax
0x18004a5c0  call    cs:__imp_SetLastError
0x18004a5c7  nop     dword ptr [rax+rax+00h]
0x18004a5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5d3  cmp     rcx, r12
0x18004a5d6  jz      short loc_18004A626
0x18004a5d8  test    byte ptr [rcx+1Ch], 40h
0x18004a5dc  jz      short loc_18004A626
0x18004a5de  mov     rcx, [rcx+10h]
0x18004a5e2  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a5e9  mov     edx, 0Bh
0x18004a5ee  mov     r9d, ebp
0x18004a5f1  call    WPP_SF_D
0x18004a5f6  jmp     short loc_18004A626
0x18004a5f8  mov     rax, [rsp+68h+TargetHandle]
0x18004a5fd  mov     [rbx+30h], rax
0x18004a601  jmp     short loc_18004A626
0x18004a603  cmp     rsi, r12
0x18004a606  jz      short loc_18004A626
0x18004a608  test    byte ptr [rsi+1Ch], 20h
0x18004a60c  jz      short loc_18004A626
0x18004a60e  mov     rcx, [rsi+10h]
0x18004a612  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a619  mov     edx, 0Ch
0x18004a61e  mov     r9, r14
0x18004a621  call    WPP_SF_q
0x18004a626  mov     rcx, r15; this
0x18004a629  call    ?UnLock@CCriticalSection@@QEAAXXZ; CCriticalSection::UnLock(void)
0x18004a62e  jmp     short loc_18004A643
0x18004a630  mov     ecx, 0Dh; dwErrCode
0x18004a635  mov     ebp, ecx
0x18004a637  call    cs:__imp_SetLastError
0x18004a63e  nop     dword ptr [rax+rax+00h]
0x18004a643  lea     r11, [rsp+68h+var_28]
0x18004a648  mov     eax, ebp
0x18004a64a  mov     rbx, [r11+30h]
0x18004a64e  mov     rbp, [r11+48h]
0x18004a652  mov     rsp, r11
0x18004a655  pop     r15
0x18004a657  pop     r14
0x18004a659  pop     r12
0x18004a65b  pop     rdi
0x18004a65c  pop     rsi
0x18004a65d  retn
```
