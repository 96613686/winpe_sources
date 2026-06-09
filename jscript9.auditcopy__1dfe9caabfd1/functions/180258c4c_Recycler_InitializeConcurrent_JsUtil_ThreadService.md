# Recycler::InitializeConcurrent(JsUtil::ThreadService *)

- ea: `0x180258c4c`
- end: `0x180258e0b`
- name: `?InitializeConcurrent@Recycler@@AEAA_NPEAVThreadService@JsUtil@@@Z`
- size: `447`
- prototype: `char __fastcall(Recycler *this, struct JsUtil::ThreadService *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801a9cf0`

## callees

- `0x18001f668`
- `0x18012dca4`
- `0x1801cc168`
- `0x180258c4c`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180258d74`
- `msvcrt!_beginthreadex` at `0x180258d74`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180258dc5`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180258dc5`
- `KERNEL32!CreateEventW` at `0x180258c83`
- `KERNEL32!CreateEventW` at `0x180258d2d`
- `KERNEL32!CreateEventW` at `0x180258c83`
- `KERNEL32!CreateEventW` at `0x180258d2d`

## pseudocode

```c
char __fastcall Recycler::InitializeConcurrent(Recycler *this, struct JsUtil::ThreadService *a2)
{
  HANDLE EventW; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  HANDLE v7; // rax
  void *v8; // rcx
  char pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  char v11; // [rsp+31h] [rbp-27h] BYREF
  char v12; // [rsp+32h] [rbp-26h] BYREF
  char v13; // [rsp+33h] [rbp-25h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h]
  HANDLE Handles[3]; // [rsp+40h] [rbp-18h] BYREF

  v14 = -2;
  *((_QWORD *)this + 44) = a2;
  try
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 1618) = EventW;
    if ( !EventW )
      throw (Js::OutOfMemoryException *)&pExceptionObject;
    v5 = operator new<HeapAllocator>(
           96,
           (__int64)HeapAllocator::Instance,
           (__int64 (__fastcall *)(__int64, __int64))HeapAllocator::Alloc);
    if ( v5 )
    {
      *(_QWORD *)v5 = *((_QWORD *)this + 2037);
      *(_QWORD *)(v5 + 8) = 0;
      *(_QWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 24) = 0;
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = (char *)this + 12712;
      *(_QWORD *)(v5 + 48) = 0;
      *(_BYTE *)(v5 + 56) = 0;
      *(_QWORD *)(v5 + 64) = 0;
      *(_QWORD *)(v5 + 72) = 0;
      *(_DWORD *)(v5 + 80) = 0;
      *(_QWORD *)(v5 + 88) = 0;
    }
    else
    {
      v5 = 0;
    }
    *((_QWORD *)this + 2020) = v5;
    if ( !JsUtil::ThreadService::HasCallback(a2) )
    {
      v7 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 1617) = v7;
      if ( !v7 )
        throw (Js::OutOfMemoryException *)&v11;
      v8 = (void *)_beginthreadex(0, 0x493E0u, (_beginthreadex_proc_type)Recycler::StaticThreadProc, this, 0x10000u, 0);
      *((_QWORD *)this + 1619) = v8;
      if ( !v8 )
        throw (Js::OutOfMemoryException *)&v12;
      Handles[0] = *((HANDLE *)this + 1618);
      Handles[1] = v8;
      if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
      {
        *((_QWORD *)this + 1619) = 0;
        throw (Js::OutOfMemoryException *)&v13;
      }
    }
    *((_DWORD *)this + 27) = 0x200000;
  }
  catch ( Js::OutOfMemoryException )
  {
    if ( *((_QWORD *)this + 2020) )
    {
      DeleteObject<HeapAllocator,ArenaAllocator>(v6, *((ArenaAllocator **)this + 2020));
      *((_QWORD *)this + 2020) = 0;
    }
    if ( *((_QWORD *)this + 1618) )
    {
      CloseHandle(*((HANDLE *)this + 1618));
      *((_QWORD *)this + 1618) = 0;
    }
    if ( *((_QWORD *)this + 1617) )
    {
      CloseHandle(*((HANDLE *)this + 1617));
      *((_QWORD *)this + 1617) = 0;
    }
    *((_QWORD *)this + 44) = 0;
    *(_WORD *)((char *)this + 12911) = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180258c4c  mov     rax, rsp
0x180258c4f  mov     [rax+10h], rdx
0x180258c53  mov     [rax+8], rcx
0x180258c57  push    rdi
0x180258c58  sub     rsp, 50h
0x180258c5c  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180258c64  mov     [rax+18h], rbx
0x180258c68  mov     [rax+20h], rsi
0x180258c6c  mov     rdi, rdx
0x180258c6f  mov     rbx, rcx
0x180258c72  mov     [rcx+160h], rdx
0x180258c79  xor     r9d, r9d; lpName
0x180258c7c  xor     r8d, r8d; bInitialState
0x180258c7f  xor     edx, edx; bManualReset
0x180258c81  xor     ecx, ecx; lpEventAttributes
0x180258c83  call    cs:__imp_CreateEventW
0x180258c8a  nop     dword ptr [rax+rax+00h]
0x180258c8f  mov     [rbx+3290h], rax
0x180258c96  xor     esi, esi
0x180258c98  test    rax, rax
0x180258c9b  jnz     short loc_180258CAE
0x180258c9d  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x180258ca4  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180258ca9  call    _CxxThrowException_0
0x180258cae  lea     r8, ?Alloc@HeapAllocator@@QEAAPEAD_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180258cb5  lea     rdx, ?Instance@HeapAllocator@@2U1@A; HeapAllocator HeapAllocator::Instance
0x180258cbc  mov     ecx, 60h ; '`'
0x180258cc1  call    ??$?2UHeapAllocator@@@@YAPEAX_KPEAUHeapAllocator@@P80@EAAPEAD0@Z@Z; operator new<HeapAllocator>(unsigned __int64,HeapAllocator *,char * (HeapAllocator::*)(unsigned __int64))
0x180258cc6  test    rax, rax
0x180258cc9  jz      short loc_180258D09
0x180258ccb  mov     rcx, [rbx+3FA8h]
0x180258cd2  mov     [rax], rcx
0x180258cd5  mov     [rax+8], rsi
0x180258cd9  mov     [rax+10h], rsi
0x180258cdd  mov     [rax+18h], rsi
0x180258ce1  mov     [rax+20h], rsi
0x180258ce5  lea     rcx, [rbx+31A8h]
0x180258cec  mov     [rax+28h], rcx
0x180258cf0  mov     [rax+30h], rsi
0x180258cf4  mov     [rax+38h], sil
0x180258cf8  mov     [rax+40h], rsi
0x180258cfc  mov     [rax+48h], rsi
0x180258d00  mov     [rax+50h], esi
0x180258d03  mov     [rax+58h], rsi
0x180258d07  jmp     short loc_180258D0C
0x180258d09  mov     rax, rsi
0x180258d0c  mov     [rbx+3F20h], rax
0x180258d13  mov     rcx, rdi; this
0x180258d16  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x180258d1b  test    al, al
0x180258d1d  jnz     loc_180258DED
0x180258d23  xor     r9d, r9d; lpName
0x180258d26  xor     r8d, r8d; bInitialState
0x180258d29  xor     edx, edx; bManualReset
0x180258d2b  xor     ecx, ecx; lpEventAttributes
0x180258d2d  call    cs:__imp_CreateEventW
0x180258d34  nop     dword ptr [rax+rax+00h]
0x180258d39  mov     [rbx+3288h], rax
0x180258d40  test    rax, rax
0x180258d43  jnz     short loc_180258D56
0x180258d45  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x180258d4c  lea     rcx, [rsp+58h+var_27]; pExceptionObject
0x180258d51  call    _CxxThrowException_0
0x180258d56  mov     [rsp+58h+ThrdAddr], rsi; ThrdAddr
0x180258d5b  mov     [rsp+58h+InitFlag], 10000h; InitFlag
0x180258d63  mov     r9, rbx; ArgList
0x180258d66  lea     r8, ?StaticThreadProc@Recycler@@CAIPEAX@Z; StartAddress
0x180258d6d  mov     edx, 493E0h; StackSize
0x180258d72  xor     ecx, ecx; Security
0x180258d74  call    cs:__imp__beginthreadex
0x180258d7b  nop     dword ptr [rax+rax+00h]
0x180258d80  mov     rcx, rax
0x180258d83  mov     [rbx+3298h], rax
0x180258d8a  test    rax, rax
0x180258d8d  jnz     short loc_180258DA0
0x180258d8f  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x180258d96  lea     rcx, [rsp+58h+var_26]; pExceptionObject
0x180258d9b  call    _CxxThrowException_0
0x180258da0  mov     rax, [rbx+3290h]
0x180258da7  mov     [rsp+58h+Handles], rax
0x180258dac  mov     [rsp+58h+var_10], rcx
0x180258db1  mov     [rsp+58h+InitFlag], esi; bAlertable
0x180258db5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180258db9  xor     r8d, r8d; bWaitAll
0x180258dbc  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180258dc1  lea     ecx, [r8+2]; nCount
0x180258dc5  call    cs:__imp_WaitForMultipleObjectsEx
0x180258dcc  nop     dword ptr [rax+rax+00h]
0x180258dd1  test    eax, eax
0x180258dd3  jz      short loc_180258DED
0x180258dd5  mov     [rbx+3298h], rsi
0x180258ddc  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x180258de3  lea     rcx, [rsp+58h+var_25]; pExceptionObject
0x180258de8  call    _CxxThrowException_0
0x180258ded  mov     dword ptr [rbx+6Ch], 200000h
0x180258df4  mov     al, 1
0x180258df6  jmp     short loc_180258DFA
0x180258df8  xor     al, al
0x180258dfa  mov     rbx, [rsp+58h+arg_10]
0x180258dff  mov     rsi, [rsp+58h+arg_18]
0x180258e04  add     rsp, 50h
0x180258e08  pop     rdi
0x180258e09  retn
```
