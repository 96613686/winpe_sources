# SyncEnumTree

- ea: `0x18007c808`
- end: `0x18007ca30`
- name: `SyncEnumTree`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800749e8`

## callees

- `0x180011ef0`
- `0x1800360c0`
- `0x180036394`
- `0x180071318`
- `0x1800728c4`
- `0x18007c808`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c9d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c9d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c9c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c9c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c9b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007c9b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c969`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c969`

## pseudocode

```c
__int64 __fastcall SyncEnumTree(void *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, TOKEN_TYPE a6)
{
  CObjectMonitor *v9; // rax
  unsigned int v11; // ebx
  unsigned int v12; // edi
  __int64 v13; // [rsp+28h] [rbp-40h]
  HANDLE hEvent[2]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+50h] [rbp-18h]

  *(_OWORD *)hEvent = 0;
  v15 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTree: phdl: 0x%p shdl: 0x%p Args: 0x%p", a1, a2, a3);
      v13 = a3;
      WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, a1, a2);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTree: mode: 0x%x callback_args: 0x%p Depth: %d", 13, a5, (unsigned int)a6);
      WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, 13, a5, a6);
    }
  }
  if ( a6 == TokenPrimary )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, __int64))(a3 + 16))(a5, 0, 0, 0, 0, v13);
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTree: 0x%x", 0);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    LODWORD(hEvent[0]) = 1;
    v15 = 0;
    hEvent[1] = CreateEventW(0, 0, 0, 0);
    v11 = hEvent[1] != 0 ? 13 : 5;
    v12 = SyncEnumTreeInternal(a1, a2, a3, v11, a5, (__int64)hEvent, a6);
    if ( (v11 & 8) != 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)hEvent, 0xFFFFFFFF) == 1 )
        SetEvent(hEvent[1]);
      WaitForSingleObject(hEvent[1], 0xFFFFFFFF);
      v12 = v15;
    }
    if ( hEvent[1] )
      CloseHandle(hEvent[1]);
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTree: 0x%x", 0);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 57, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, 0);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x18007c808  push    rbp
0x18007c80a  push    rbx
0x18007c80b  push    rsi
0x18007c80c  push    rdi
0x18007c80d  push    r12
0x18007c80f  push    r13
0x18007c811  push    r14
0x18007c813  push    r15
0x18007c815  mov     rbp, rsp
0x18007c818  sub     rsp, 68h
0x18007c81c  xor     eax, eax
0x18007c81e  xorps   xmm0, xmm0
0x18007c821  movups  xmmword ptr [rbp+hEvent], xmm0
0x18007c825  mov     [rbp+var_18], eax
0x18007c828  mov     r14, r8
0x18007c82b  mov     r15, rdx
0x18007c82e  mov     r12, rcx
0x18007c831  mov     rax, cs:WPP_GLOBAL_Control
0x18007c838  lea     r13, WPP_GLOBAL_Control
0x18007c83f  mov     edi, [rbp+arg_28]
0x18007c842  mov     rsi, [rbp+arg_20]
0x18007c846  cmp     rax, r13
0x18007c849  jz      loc_18007C8E4
0x18007c84f  test    byte ptr [rax+6Ch], 4
0x18007c853  jz      short loc_18007C89A
0x18007c855  mov     r9, r8
0x18007c858  mov     r8, rdx
0x18007c85b  mov     rdx, rcx
0x18007c85e  lea     rcx, aSyncenumtreePh; "SyncEnumTree: phdl: 0x%p shdl: 0x%p Arg"...
0x18007c865  call    SyncTraceOutputInternal
0x18007c86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c871  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x18007c878  mov     edx, 36h ; '6'
0x18007c87d  mov     [rsp+68h+var_40], r14
0x18007c882  mov     r9, r12
0x18007c885  mov     [rsp+68h+var_48], r15
0x18007c88a  mov     rcx, [rcx+60h]
0x18007c88e  call    WPP_SF_qqq
0x18007c893  mov     rax, cs:WPP_GLOBAL_Control
0x18007c89a  cmp     rax, r13
0x18007c89d  jz      short loc_18007C8E4
0x18007c89f  test    byte ptr [rax+6Ch], 4
0x18007c8a3  jz      short loc_18007C8E4
0x18007c8a5  mov     ebx, 0Dh
0x18007c8aa  lea     rcx, aSyncenumtreeMo; "SyncEnumTree: mode: 0x%x callback_args:"...
0x18007c8b1  mov     edx, ebx
0x18007c8b3  mov     r9d, edi
0x18007c8b6  mov     r8, rsi
0x18007c8b9  call    SyncTraceOutputInternal
0x18007c8be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c8c5  lea     edx, [rbx+2Ah]
0x18007c8c8  mov     dword ptr [rsp+68h+var_40], edi
0x18007c8cc  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x18007c8d3  mov     r9d, ebx
0x18007c8d6  mov     [rsp+68h+var_48], rsi
0x18007c8db  mov     rcx, [rcx+60h]
0x18007c8df  call    WPP_SF_dqd
0x18007c8e4  cmp     edi, 1
0x18007c8e7  jnz     short loc_18007C949
0x18007c8e9  mov     rax, [r14+10h]
0x18007c8ed  xor     r9d, r9d
0x18007c8f0  xor     r8d, r8d
0x18007c8f3  mov     dword ptr [rsp+68h+var_48], 0
0x18007c8fb  xor     edx, edx
0x18007c8fd  mov     rcx, rsi
0x18007c900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c905  mov     rax, cs:WPP_GLOBAL_Control
0x18007c90c  cmp     rax, r13
0x18007c90f  jz      short loc_18007C942
0x18007c911  test    byte ptr [rax+6Ch], 8
0x18007c915  jz      short loc_18007C942
0x18007c917  xor     edx, edx
0x18007c919  lea     rcx, aSyncenumtree0x; "SyncEnumTree: 0x%x"
0x18007c920  call    SyncTraceOutputInternal
0x18007c925  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c92c  lea     edx, [rdi+37h]
0x18007c92f  xor     r9d, r9d
0x18007c932  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x18007c939  mov     rcx, [rcx+60h]
0x18007c93d  call    WPP_SF_d
0x18007c942  xor     eax, eax
0x18007c944  jmp     loc_18007CA1F
0x18007c949  xor     r9d, r9d; lpName
0x18007c94c  mov     [rbp+hEvent+8], 0
0x18007c954  xor     r8d, r8d; bInitialState
0x18007c957  mov     dword ptr [rbp+hEvent], 1
0x18007c95e  xor     edx, edx; bManualReset
0x18007c960  mov     [rbp+var_18], 0
0x18007c967  xor     ecx, ecx; lpEventAttributes
0x18007c969  call    cs:__imp_CreateEventW
0x18007c96f  mov     [rsp+68h+var_38], edi
0x18007c973  mov     r8, r14
0x18007c976  mov     [rbp+hEvent+8], rax
0x18007c97a  mov     rdx, r15
0x18007c97d  neg     rax
0x18007c980  mov     rcx, r12
0x18007c983  lea     rax, [rbp+hEvent]
0x18007c987  sbb     ebx, ebx
0x18007c989  mov     [rsp+68h+var_40], rax
0x18007c98e  and     ebx, 8
0x18007c991  mov     [rsp+68h+var_48], rsi
0x18007c996  add     ebx, 5
0x18007c999  mov     r9d, ebx
0x18007c99c  call    SyncEnumTreeInternal
0x18007c9a1  mov     edi, eax
0x18007c9a3  test    bl, 8
0x18007c9a6  jz      short loc_18007C9CF
0x18007c9a8  or      eax, 0FFFFFFFFh
0x18007c9ab  lock xadd dword ptr [rbp+hEvent], eax
0x18007c9b0  cmp     eax, 1
0x18007c9b3  jnz     short loc_18007C9BF
0x18007c9b5  mov     rcx, [rbp+hEvent+8]; hEvent
0x18007c9b9  call    cs:__imp_SetEvent
0x18007c9bf  mov     rcx, [rbp+hEvent+8]; hHandle
0x18007c9c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007c9c6  call    cs:__imp_WaitForSingleObject
0x18007c9cc  mov     edi, [rbp+var_18]
0x18007c9cf  mov     rcx, [rbp+hEvent+8]; hObject
0x18007c9d3  test    rcx, rcx
0x18007c9d6  jz      short loc_18007C9DE
0x18007c9d8  call    cs:__imp_CloseHandle
0x18007c9de  mov     rax, cs:WPP_GLOBAL_Control
0x18007c9e5  cmp     rax, r13
0x18007c9e8  jz      short loc_18007CA1D
0x18007c9ea  test    byte ptr [rax+6Ch], 8
0x18007c9ee  jz      short loc_18007CA1D
0x18007c9f0  xor     edx, edx
0x18007c9f2  lea     rcx, aSyncenumtree0x; "SyncEnumTree: 0x%x"
0x18007c9f9  call    SyncTraceOutputInternal
0x18007c9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca05  lea     r8, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids
0x18007ca0c  mov     edx, 39h ; '9'
0x18007ca11  xor     r9d, r9d
0x18007ca14  mov     rcx, [rcx+60h]
0x18007ca18  call    WPP_SF_d
0x18007ca1d  mov     eax, edi
0x18007ca1f  add     rsp, 68h
0x18007ca23  pop     r15
0x18007ca25  pop     r14
0x18007ca27  pop     r13
0x18007ca29  pop     r12
0x18007ca2b  pop     rdi
0x18007ca2c  pop     rsi
0x18007ca2d  pop     rbx
0x18007ca2e  pop     rbp
0x18007ca2f  retn
```
