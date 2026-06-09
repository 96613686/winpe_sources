# NMP_CompleteListenAbort(void *)

- ea: `0x1800c6700`
- end: `0x1800c68bd`
- name: `?NMP_CompleteListenAbort@@YAXPEAX@Z`
- size: `445`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c66d0`

## callees

- `0x180022870`
- `0x18004cc10`
- `0x180060e18`
- `0x18006108c`
- `0x180070400`
- `0x1800c6700`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c677f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c67c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6869`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c677f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c67c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6869`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6791`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6878`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6791`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6878`

## pseudocode

```c
void __fastcall NMP_CompleteListenAbort(char *a1)
{
  volatile __int32 *v2; // rdi
  int v3; // ecx
  unsigned int v4; // eax
  __int64 v5; // rsi
  unsigned int v6; // edx
  RPC_THREAD_POOL_IO *v7; // rcx
  void *v8; // rcx
  char *v9; // rdi
  char *v10; // rcx
  SIMPLE_DICT *v11; // rcx
  void *v12; // rsi
  unsigned int v13; // edx
  RPC_THREAD_POOL_IO *v14; // rcx
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF

  CSpinLock::Lock((CSpinLock *)(a1 + 120));
  v2 = (volatile __int32 *)(a1 + 120);
  if ( _InterlockedIncrement((volatile signed __int32 *)a1 + 4) == 1 )
  {
    v5 = *((_QWORD *)a1 + 25);
    *((_QWORD *)a1 + 25) = 0;
    _InterlockedExchange(v2, ((*v2 - 0x10000000) & 0xF0000000) != 0 ? *v2 - 0x10000000 : 0);
    if ( v5 )
    {
      CloseHandle(*(HANDLE *)(v5 + 56));
      WaitForThreadpoolIoCallbacks(**(PTP_IO **)(v5 + 48), 1);
      v7 = *(RPC_THREAD_POOL_IO **)(v5 + 48);
      if ( v7 )
        RPC_THREAD_POOL_IO::`scalar deleting destructor'(v7, v6);
      FreeWrapper((void *)v5);
    }
    CSpinLock::Lock((CSpinLock *)(a1 + 120));
    v8 = (void *)*((_QWORD *)a1 + 33);
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)a1 + 33) = 0;
    }
    v9 = (char *)*((_QWORD *)a1 + 37);
    while ( v9 != a1 + 296 )
    {
      v10 = v9 - 160;
      v9 = *(char **)v9;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 48LL))(v10);
    }
    v2 = (volatile __int32 *)(a1 + 208);
    _InterlockedExchange(
      (volatile __int32 *)a1 + 30,
      ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
LABEL_13:
    CSpinLock::Lock((CSpinLock *)(a1 + 208));
    v15 = 0;
    while ( 1 )
    {
      v12 = SIMPLE_DICT::Next((SIMPLE_DICT *)(a1 + 216), &v15);
      if ( !v12 )
        break;
      SIMPLE_DICT::Delete(v11, v15 - 1);
      if ( *((_QWORD *)v12 + 7) )
      {
        _InterlockedExchange(
          v2,
          ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
        CloseHandle(*((HANDLE *)v12 + 7));
        WaitForThreadpoolIoCallbacks(**((PTP_IO **)v12 + 6), 0);
        v14 = (RPC_THREAD_POOL_IO *)*((_QWORD *)v12 + 6);
        if ( v14 )
          RPC_THREAD_POOL_IO::`scalar deleting destructor'(v14, v13);
        FreeWrapper(v12);
        goto LABEL_13;
      }
    }
    v3 = *((_DWORD *)a1 + 52) - 0x10000000;
    v4 = v3 & 0xF0000000;
  }
  else
  {
    v3 = *v2 - 0x10000000;
    v4 = v3 & 0xF0000000;
  }
  _InterlockedExchange(v2, v4 != 0 ? v3 : 0);
}

```

## disassembly

```asm
0x1800c6700  mov     [rsp+arg_8], rbx
0x1800c6705  mov     [rsp+arg_10], rbp
0x1800c670a  push    rsi
0x1800c670b  push    rdi
0x1800c670c  push    r14
0x1800c670e  sub     rsp, 20h
0x1800c6712  mov     rbx, rcx
0x1800c6715  add     rcx, 78h ; 'x'; this
0x1800c6719  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c671e  mov     eax, 1
0x1800c6723  lea     rdi, [rbx+78h]
0x1800c6727  lock xadd [rbx+10h], eax
0x1800c672c  inc     eax
0x1800c672e  cmp     eax, 1
0x1800c6731  jz      short loc_1800C6747
0x1800c6733  mov     ecx, [rdi]
0x1800c6735  add     ecx, 0F0000000h
0x1800c673b  mov     eax, ecx
0x1800c673d  and     eax, 0F0000000h
0x1800c6742  jmp     loc_1800C68A2
0x1800c6747  mov     rsi, [rbx+0C8h]
0x1800c674e  mov     ebp, 0F0000000h
0x1800c6753  mov     qword ptr [rbx+0C8h], 0
0x1800c675e  mov     r8d, [rdi]
0x1800c6761  add     r8d, 0F0000000h
0x1800c6768  mov     eax, r8d
0x1800c676b  and     eax, ebp
0x1800c676d  neg     eax
0x1800c676f  sbb     ecx, ecx
0x1800c6771  and     ecx, r8d
0x1800c6774  xchg    ecx, [rdi]
0x1800c6776  test    rsi, rsi
0x1800c6779  jz      short loc_1800C67AD
0x1800c677b  mov     rcx, [rsi+38h]; hObject
0x1800c677f  call    cs:__imp_CloseHandle
0x1800c6785  mov     rcx, [rsi+30h]
0x1800c6789  mov     edx, 1; fCancelPendingCallbacks
0x1800c678e  mov     rcx, [rcx]; pio
0x1800c6791  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800c6797  mov     rcx, [rsi+30h]; this
0x1800c679b  test    rcx, rcx
0x1800c679e  jz      short loc_1800C67A5
0x1800c67a0  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800c67a5  mov     rcx, rsi; lpMem
0x1800c67a8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c67ad  lea     rcx, [rbx+78h]; this
0x1800c67b1  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c67b6  mov     rcx, [rbx+108h]; hObject
0x1800c67bd  test    rcx, rcx
0x1800c67c0  jz      short loc_1800C67D3
0x1800c67c2  call    cs:__imp_CloseHandle
0x1800c67c8  mov     qword ptr [rbx+108h], 0
0x1800c67d3  lea     rsi, [rbx+128h]
0x1800c67da  mov     rdi, [rsi]
0x1800c67dd  jmp     short loc_1800C67F5
0x1800c67df  lea     rcx, [rdi-0A0h]
0x1800c67e6  mov     rdi, [rdi]
0x1800c67e9  mov     rax, [rcx]
0x1800c67ec  mov     rax, [rax+30h]
0x1800c67f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67f5  cmp     rdi, rsi
0x1800c67f8  jnz     short loc_1800C67DF
0x1800c67fa  mov     edx, [rbx+78h]
0x1800c67fd  lea     rdi, [rbx+0D0h]
0x1800c6804  add     edx, ebp
0x1800c6806  lea     r14, [rbx+0D8h]
0x1800c680d  mov     eax, edx
0x1800c680f  and     eax, ebp
0x1800c6811  neg     eax
0x1800c6813  sbb     ecx, ecx
0x1800c6815  and     ecx, edx
0x1800c6817  xchg    ecx, [rbx+78h]
0x1800c681a  mov     rcx, rdi; this
0x1800c681d  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c6822  mov     [rsp+38h+arg_0], 0
0x1800c682a  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x1800c682f  mov     rcx, r14; this
0x1800c6832  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x1800c6837  mov     rsi, rax
0x1800c683a  test    rax, rax
0x1800c683d  jz      short loc_1800C6896
0x1800c683f  mov     edx, [rsp+38h+arg_0]
0x1800c6843  dec     edx; unsigned int
0x1800c6845  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x1800c684a  cmp     qword ptr [rsi+38h], 0
0x1800c684f  jz      short loc_1800C682A
0x1800c6851  mov     edx, [rbx+0D0h]
0x1800c6857  add     edx, ebp
0x1800c6859  mov     ecx, edx
0x1800c685b  and     ecx, ebp
0x1800c685d  neg     ecx
0x1800c685f  sbb     eax, eax
0x1800c6861  and     eax, edx
0x1800c6863  xchg    eax, [rdi]
0x1800c6865  mov     rcx, [rsi+38h]; hObject
0x1800c6869  call    cs:__imp_CloseHandle
0x1800c686f  mov     rcx, [rsi+30h]
0x1800c6873  xor     edx, edx; fCancelPendingCallbacks
0x1800c6875  mov     rcx, [rcx]; pio
0x1800c6878  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800c687e  mov     rcx, [rsi+30h]; this
0x1800c6882  test    rcx, rcx
0x1800c6885  jz      short loc_1800C688C
0x1800c6887  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800c688c  mov     rcx, rsi; lpMem
0x1800c688f  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c6894  jmp     short loc_1800C681A
0x1800c6896  mov     ecx, [rbx+0D0h]
0x1800c689c  add     ecx, ebp
0x1800c689e  mov     eax, ecx
0x1800c68a0  and     eax, ebp
0x1800c68a2  mov     rbx, [rsp+38h+arg_8]
0x1800c68a7  neg     eax
0x1800c68a9  mov     rbp, [rsp+38h+arg_10]
0x1800c68ae  sbb     edx, edx
0x1800c68b0  and     edx, ecx
0x1800c68b2  xchg    edx, [rdi]
0x1800c68b4  add     rsp, 20h
0x1800c68b8  pop     r14
0x1800c68ba  pop     rdi
0x1800c68bb  pop     rsi
0x1800c68bc  retn
```
