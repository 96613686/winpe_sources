# UninitializeKaMeasurements

- ea: `0x1800030a4`
- end: `0x1800032b7`
- name: `UninitializeKaMeasurements`
- size: `531`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x180001e20`
- `0x180001ed8`
- `0x180001f9c`
- `0x180002024`
- `0x1800030a4`
- `0x1800032c0`
- `0x180004010`

## import_xrefs

- `RPCRT4!RpcAsyncCancelCall` at `0x180003140`
- `RPCRT4!RpcAsyncCancelCall` at `0x180003140`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800031b2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800031b2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800030fe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800030fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003176`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003176`

## pseudocode

```c
__int64 __fastcall UninitializeKaMeasurements(__int64 a1)
{
  void *v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // r8
  void *v9; // rcx
  __int64 result; // rax
  int Reply; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  v2 = *(void **)(a1 + 160);
  Reply = 0;
  v3 = UnregisterWaitEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v4, v3);
  }
  if ( *(_DWORD *)(a1 + 16) )
  {
    v5 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)(a1 + 24), 1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v6, v5);
    }
    WaitForSingleObject(*(HANDLE *)(a1 + 72), 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
    }
    v7 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(a1 + 24), &Reply);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v8, v7);
    }
  }
  if ( *(_QWORD *)(a1 + 208) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 192))(*(_QWORD *)(a1 + 168), *(_QWORD *)(a1 + 176));
    FreeNetworkGuidsHelper(*(LPVOID *)(a1 + 208));
    *(_QWORD *)(a1 + 208) = 0;
  }
  if ( *(_QWORD *)(a1 + 216) )
  {
    FreeSampleSetHelper();
    *(_QWORD *)(a1 + 216) = 0;
  }
  v9 = *(void **)(a1 + 144);
  if ( v9 )
  {
    FreeNetworkGuidsHelper(v9);
    *(_QWORD *)(a1 + 144) = 0;
  }
  if ( *(_QWORD *)(a1 + 152) )
  {
    FreeSampleSetHelper();
    *(_QWORD *)(a1 + 152) = 0;
  }
  result = CleanupRpcAsyncState(a1 + 24);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1800030a4  mov     [rsp+arg_8], rbx
0x1800030a9  mov     [rsp+arg_10], rdi
0x1800030ae  push    r15
0x1800030b0  sub     rsp, 20h
0x1800030b4  mov     rbx, rcx
0x1800030b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030be  lea     r15, WPP_GLOBAL_Control
0x1800030c5  cmp     rcx, r15
0x1800030c8  jz      short loc_1800030EB
0x1800030ca  test    byte ptr [rcx+1Ch], 1
0x1800030ce  jz      short loc_1800030EB
0x1800030d0  cmp     byte ptr [rcx+19h], 6
0x1800030d4  jb      short loc_1800030EB
0x1800030d6  mov     rcx, [rcx+10h]
0x1800030da  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x1800030e1  mov     edx, 27h ; '''
0x1800030e6  call    WPP_SF_
0x1800030eb  mov     rcx, [rbx+0A0h]; WaitHandle
0x1800030f2  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800030f6  mov     [rsp+28h+Reply], 0
0x1800030fe  call    cs:__imp_UnregisterWaitEx
0x180003104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000310b  cmp     rcx, r15
0x18000310e  jz      short loc_18000312D
0x180003110  test    byte ptr [rcx+1Ch], 1
0x180003114  jz      short loc_18000312D
0x180003116  cmp     byte ptr [rcx+19h], 5
0x18000311a  jb      short loc_18000312D
0x18000311c  mov     rcx, [rcx+10h]
0x180003120  mov     edx, 28h ; '('
0x180003125  mov     r9d, eax
0x180003128  call    WPP_SF_D
0x18000312d  cmp     dword ptr [rbx+10h], 0
0x180003131  jz      loc_1800031E1
0x180003137  mov     edx, 1; fAbort
0x18000313c  lea     rcx, [rbx+18h]; pAsync
0x180003140  call    cs:__imp_RpcAsyncCancelCall
0x180003146  mov     rcx, cs:WPP_GLOBAL_Control
0x18000314d  cmp     rcx, r15
0x180003150  jz      short loc_18000316F
0x180003152  test    byte ptr [rcx+1Ch], 1
0x180003156  jz      short loc_18000316F
0x180003158  cmp     byte ptr [rcx+19h], 5
0x18000315c  jb      short loc_18000316F
0x18000315e  mov     rcx, [rcx+10h]
0x180003162  mov     edx, 29h ; ')'
0x180003167  mov     r9d, eax
0x18000316a  call    WPP_SF_D
0x18000316f  mov     rcx, [rbx+48h]; hHandle
0x180003173  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003176  call    cs:__imp_WaitForSingleObject
0x18000317c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003183  cmp     rcx, r15
0x180003186  jz      short loc_1800031A9
0x180003188  test    byte ptr [rcx+1Ch], 1
0x18000318c  jz      short loc_1800031A9
0x18000318e  cmp     byte ptr [rcx+19h], 5
0x180003192  jb      short loc_1800031A9
0x180003194  mov     rcx, [rcx+10h]
0x180003198  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x18000319f  mov     edx, 2Ah ; '*'
0x1800031a4  call    WPP_SF_
0x1800031a9  lea     rdx, [rsp+28h+Reply]; Reply
0x1800031ae  lea     rcx, [rbx+18h]; pAsync
0x1800031b2  call    cs:__imp_RpcAsyncCompleteCall
0x1800031b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031bf  cmp     rcx, r15
0x1800031c2  jz      short loc_1800031E1
0x1800031c4  test    byte ptr [rcx+1Ch], 1
0x1800031c8  jz      short loc_1800031E1
0x1800031ca  cmp     byte ptr [rcx+19h], 5
0x1800031ce  jb      short loc_1800031E1
0x1800031d0  mov     rcx, [rcx+10h]
0x1800031d4  mov     edx, 2Bh ; '+'
0x1800031d9  mov     r9d, eax
0x1800031dc  call    WPP_SF_D
0x1800031e1  cmp     qword ptr [rbx+0D0h], 0
0x1800031e9  jz      short loc_18000321C
0x1800031eb  mov     rdx, [rbx+0B0h]
0x1800031f2  mov     rcx, [rbx+0A8h]
0x1800031f9  mov     rax, [rbx+0C0h]
0x180003200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003205  mov     rcx, [rbx+0D0h]; lpMem
0x18000320c  call    FreeNetworkGuidsHelper
0x180003211  mov     qword ptr [rbx+0D0h], 0
0x18000321c  mov     rcx, [rbx+0D8h]
0x180003223  test    rcx, rcx
0x180003226  jz      short loc_180003238
0x180003228  call    FreeSampleSetHelper
0x18000322d  mov     qword ptr [rbx+0D8h], 0
0x180003238  mov     rcx, [rbx+90h]; lpMem
0x18000323f  test    rcx, rcx
0x180003242  jz      short loc_180003254
0x180003244  call    FreeNetworkGuidsHelper
0x180003249  mov     qword ptr [rbx+90h], 0
0x180003254  mov     rcx, [rbx+98h]
0x18000325b  test    rcx, rcx
0x18000325e  jz      short loc_180003270
0x180003260  call    FreeSampleSetHelper
0x180003265  mov     qword ptr [rbx+98h], 0
0x180003270  lea     rcx, [rbx+18h]
0x180003274  call    CleanupRpcAsyncState
0x180003279  mov     rcx, cs:WPP_GLOBAL_Control
0x180003280  cmp     rcx, r15
0x180003283  jz      short loc_1800032A6
0x180003285  test    byte ptr [rcx+1Ch], 1
0x180003289  jz      short loc_1800032A6
0x18000328b  cmp     byte ptr [rcx+19h], 6
0x18000328f  jb      short loc_1800032A6
0x180003291  mov     rcx, [rcx+10h]
0x180003295  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x18000329c  mov     edx, 2Ch ; ','
0x1800032a1  call    WPP_SF_
0x1800032a6  mov     rbx, [rsp+28h+arg_8]
0x1800032ab  mov     rdi, [rsp+28h+arg_10]
0x1800032b0  add     rsp, 20h
0x1800032b4  pop     r15
0x1800032b6  retn
```
