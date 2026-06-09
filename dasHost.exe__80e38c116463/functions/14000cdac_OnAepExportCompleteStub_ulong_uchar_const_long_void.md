# OnAepExportCompleteStub(ulong,uchar const *,long,void *)

- ea: `0x14000cdac`
- end: `0x14000cee5`
- name: `?OnAepExportCompleteStub@@YAJKPEBEJPEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(size_t Size, const unsigned __int8 *Src, int, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140018720`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x14000cdac`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ce97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ce97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ce04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ce04`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000ce7a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000ce7a`

## pseudocode

```c
__int64 __fastcall OnAepExportCompleteStub(
        size_t Size,
        const unsigned __int8 *Src,
        int a3,
        struct _RTL_CRITICAL_SECTION *a4)
{
  size_t v5; // rbp
  unsigned int v7; // ebx
  void *v8; // rcx
  _DWORD *OwningThread; // rax
  struct _RPC_ASYNC_STATE *v10; // rcx
  RPC_STATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  int v15; // [rsp+28h] [rbp-40h]
  int Reply; // [rsp+80h] [rbp+18h] BYREF

  Reply = a3;
  v5 = (unsigned int)Size;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)Src,
      a3,
      22,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  EnterCriticalSection(a4 + 1);
  if ( LODWORD(a4[2].DebugInfo) )
  {
    v7 = -2147418113;
  }
  else
  {
    *(_QWORD *)a4[2].LockSemaphore = 0;
    *(_QWORD *)a4[2].LockSemaphore = DAF_user_alloc(v5);
    v8 = *(void **)a4[2].LockSemaphore;
    if ( v8 )
    {
      v7 = 0;
      memcpy_0(v8, Src, v5);
      *(_DWORD *)a4[2].OwningThread = v5;
    }
    else
    {
      OwningThread = a4[2].OwningThread;
      v7 = -2147024882;
      Reply = -2147024882;
      *OwningThread = 0;
    }
    v10 = (struct _RPC_ASYNC_STATE *)a4->OwningThread;
    LODWORD(a4[2].DebugInfo) = 1;
    v11 = RpcAsyncCompleteCall(v10, &Reply);
    if ( v11 )
    {
      if ( v11 < 0 )
        v7 = v11;
      else
        v7 = (unsigned __int16)v11 | 0x80010000;
    }
  }
  LeaveCriticalSection(a4 + 1);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v12,
      v13,
      23,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
      v15,
      v7);
  return v7;
}

```

## disassembly

```asm
0x14000cdac  mov     r11, rsp
0x14000cdaf  mov     [r11+8], rbx
0x14000cdb3  mov     [r11+10h], rbp
0x14000cdb7  mov     [r11+18h], r8d
0x14000cdbb  push    rsi
0x14000cdbc  push    rdi
0x14000cdbd  push    r13
0x14000cdbf  push    r14
0x14000cdc1  push    r15
0x14000cdc3  sub     rsp, 40h
0x14000cdc7  mov     rdi, r9
0x14000cdca  mov     ebp, ecx
0x14000cdcc  mov     r15, rdx
0x14000cdcf  lea     rax, WPP_RECORDER_INITIALIZED
0x14000cdd6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000cddd  lea     r13, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000cde4  jz      short loc_14000CE00
0x14000cde6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cded  mov     r9d, 16h; int
0x14000cdf3  mov     [r11-48h], r13
0x14000cdf7  mov     rcx, [rcx+28h]; int
0x14000cdfb  call    WPP_RECORDER_SF_s
0x14000ce00  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000ce04  call    cs:__imp_EnterCriticalSection
0x14000ce0a  cmp     dword ptr [rdi+50h], 0
0x14000ce0e  jz      short loc_14000CE17
0x14000ce10  mov     ebx, 8000FFFFh
0x14000ce15  jmp     short loc_14000CE93
0x14000ce17  mov     rax, [rdi+68h]
0x14000ce1b  mov     rcx, rbp
0x14000ce1e  mov     qword ptr [rax], 0
0x14000ce25  call    DAF_user_alloc
0x14000ce2a  mov     rcx, rax
0x14000ce2d  mov     rax, [rdi+68h]
0x14000ce31  mov     [rax], rcx
0x14000ce34  mov     rax, [rdi+68h]
0x14000ce38  mov     rcx, [rax]; void *
0x14000ce3b  test    rcx, rcx
0x14000ce3e  jnz     short loc_14000CE54
0x14000ce40  mov     rax, [rdi+60h]
0x14000ce44  mov     ebx, 8007000Eh
0x14000ce49  mov     [rsp+68h+Reply], ebx
0x14000ce50  mov     [rax], ecx
0x14000ce52  jmp     short loc_14000CE67
0x14000ce54  xor     ebx, ebx
0x14000ce56  mov     r8, rbp; Size
0x14000ce59  mov     rdx, r15; Src
0x14000ce5c  call    memcpy_0
0x14000ce61  mov     rax, [rdi+60h]
0x14000ce65  mov     [rax], ebp
0x14000ce67  mov     rcx, [rdi+10h]; pAsync
0x14000ce6b  lea     rdx, [rsp+68h+Reply]; Reply
0x14000ce73  mov     dword ptr [rdi+50h], 1
0x14000ce7a  call    cs:__imp_RpcAsyncCompleteCall
0x14000ce80  test    eax, eax
0x14000ce82  jz      short loc_14000CE93
0x14000ce84  js      short loc_14000CE91
0x14000ce86  movzx   ebx, ax
0x14000ce89  or      ebx, 80010000h
0x14000ce8f  jmp     short loc_14000CE93
0x14000ce91  mov     ebx, eax
0x14000ce93  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000ce97  call    cs:__imp_LeaveCriticalSection
0x14000ce9d  lea     rax, WPP_RECORDER_INITIALIZED
0x14000cea4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ceab  jz      short loc_14000CECC
0x14000cead  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ceb4  mov     r9d, 17h; int
0x14000ceba  mov     dword ptr [rsp+68h+var_38], ebx; char
0x14000cebe  mov     [rsp+68h+MessageGuid], r13; MessageGuid
0x14000cec3  mov     rcx, [rcx+28h]; int
0x14000cec7  call    WPP_RECORDER_SF_sd
0x14000cecc  mov     rbp, [rsp+68h+arg_8]
0x14000ced1  mov     eax, ebx
0x14000ced3  mov     rbx, [rsp+68h+arg_0]
0x14000ced8  add     rsp, 40h
0x14000cedc  pop     r15
0x14000cede  pop     r14
0x14000cee0  pop     r13
0x14000cee2  pop     rdi
0x14000cee3  pop     rsi
0x14000cee4  retn
```
