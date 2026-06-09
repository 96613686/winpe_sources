# UMRxAcquireMidAndFormatHeader

- ea: `0x140025e10`
- end: `0x140026096`
- name: `UMRxAcquireMidAndFormatHeader`
- size: `646`
- prototype: `__int64 __fastcall(char *Context, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140027f1c`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001bc4`
- `0x140025e10`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140025e4d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025e89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025f33`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025f87`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002605b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025e4d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025e89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025f33`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140025f87`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002605b`
- `ntoskrnl!KeInitializeEvent` at `0x140025fb9`
- `ntoskrnl!KeInitializeEvent` at `0x140025fb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002600d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002600d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025ed9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025ed9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025f5f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025fed`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025f5f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025fed`
- `rdbss!RxAssociateContextWithMid` at `0x140025f06`
- `rdbss!RxAssociateContextWithMid` at `0x140025f06`

## pseudocode

```c
__int64 __fastcall UMRxAcquireMidAndFormatHeader(char *Context, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  int v12; // eax
  _QWORD *v13; // r14
  NTSTATUS v14; // ebp
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  _QWORD *v19; // rcx
  signed __int32 v20; // eax
  __int64 v21; // rbx
  HANDLE v22; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 47, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqqq(v10, 48, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v11, a4, Context, a2);
    }
  }
  v12 = *(_DWORD *)(a4 + 16);
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_OWORD *)(a4 + 32) = 0;
  *(_DWORD *)(a4 + 16) = v12;
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 1320));
  _InterlockedIncrement((volatile signed __int32 *)Context + 1);
  v13 = (_QWORD *)(a3 + 1376);
  if ( (_QWORD *)*v13 == v13 )
  {
    v14 = RxAssociateContextWithMid(*(PRX_MID_ATLAS *)(a3 + 1312), Context, (PUSHORT)Context + 210);
    if ( !v14 )
    {
      ExReleaseFastMutex((PFAST_MUTEX)(a3 + 1320));
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      WPP_SF_qD(v15, 49, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v16, v14);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
  {
    v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v18 = PsGetCurrentThreadId();
    WPP_SF_q(v17, 50, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v18);
  }
  KeInitializeEvent((PRKEVENT)(Context + 392), NotificationEvent, 0);
  v19 = *(_QWORD **)(a3 + 1384);
  if ( (_QWORD *)*v19 != v13 )
    __fastfail(3u);
  *((_QWORD *)Context + 46) = v19;
  *((_QWORD *)Context + 45) = v13;
  *v19 = Context + 360;
  *(_QWORD *)(a3 + 1384) = Context + 360;
  ExReleaseFastMutex((PFAST_MUTEX)(a3 + 1320));
  KeWaitForSingleObject(Context + 392, Executive, 1, 0, 0);
LABEL_19:
  *(_QWORD *)a4 = Context;
  v20 = _InterlockedIncrement((volatile signed __int32 *)(a3 + 1624));
  *(_DWORD *)(a4 + 8) = v20;
  *((_DWORD *)Context + 104) = v20;
  *(_WORD *)(a4 + 12) = *((_WORD *)Context + 210);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v22 = PsGetCurrentThreadId();
    WPP_SF_qD(v21, 51, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v22, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140025e10  push    rbx
0x140025e12  push    rbp
0x140025e13  push    rsi
0x140025e14  push    rdi
0x140025e15  push    r12
0x140025e17  push    r13
0x140025e19  push    r14
0x140025e1b  push    r15
0x140025e1d  sub     rsp, 48h
0x140025e21  mov     rsi, r9
0x140025e24  mov     r15, r8
0x140025e27  mov     rbp, rdx
0x140025e2a  mov     rdi, rcx
0x140025e2d  mov     rbx, cs:WPP_GLOBAL_Control
0x140025e34  lea     r13, WPP_GLOBAL_Control
0x140025e3b  cmp     rbx, r13
0x140025e3e  jz      short loc_140025EBB
0x140025e40  test    dword ptr [rbx+2Ch], 800h
0x140025e47  jz      short loc_140025E70
0x140025e49  mov     rbx, [rbx+18h]
0x140025e4d  call    cs:__imp_PsGetCurrentThreadId
0x140025e54  nop     dword ptr [rax+rax+00h]
0x140025e59  mov     edx, 2Fh ; '/'
0x140025e5e  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140025e65  mov     r9, rax
0x140025e68  mov     rcx, rbx
0x140025e6b  call    WPP_SF_q
0x140025e70  mov     rbx, cs:WPP_GLOBAL_Control
0x140025e77  cmp     rbx, r13
0x140025e7a  jz      short loc_140025EBB
0x140025e7c  test    dword ptr [rbx+2Ch], 200h
0x140025e83  jz      short loc_140025EBB
0x140025e85  mov     rbx, [rbx+18h]
0x140025e89  call    cs:__imp_PsGetCurrentThreadId
0x140025e90  nop     dword ptr [rax+rax+00h]
0x140025e95  mov     [rsp+88h+var_58], rbp
0x140025e9a  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140025ea1  mov     r9, rax
0x140025ea4  mov     [rsp+88h+var_60], rdi
0x140025ea9  mov     edx, 30h ; '0'
0x140025eae  mov     [rsp+88h+Timeout], rsi
0x140025eb3  mov     rcx, rbx
0x140025eb6  call    WPP_SF_qqqq
0x140025ebb  mov     eax, [rsi+10h]
0x140025ebe  lea     r12, [r15+528h]
0x140025ec5  xorps   xmm0, xmm0
0x140025ec8  mov     rcx, r12; FastMutex
0x140025ecb  movups  xmmword ptr [rsi], xmm0
0x140025ece  movups  xmmword ptr [rsi+10h], xmm0
0x140025ed2  movups  xmmword ptr [rsi+20h], xmm0
0x140025ed6  mov     [rsi+10h], eax
0x140025ed9  call    cs:__imp_ExAcquireFastMutex
0x140025ee0  nop     dword ptr [rax+rax+00h]
0x140025ee5  lock inc dword ptr [rdi+4]
0x140025ee9  lea     r14, [r15+560h]
0x140025ef0  cmp     [r14], r14
0x140025ef3  jnz     short loc_140025F70
0x140025ef5  mov     rcx, [r15+520h]; MidAtlas
0x140025efc  lea     r8, [rdi+1A4h]; NewMid
0x140025f03  mov     rdx, rdi; Context
0x140025f06  call    cs:__imp_RxAssociateContextWithMid
0x140025f0d  nop     dword ptr [rax+rax+00h]
0x140025f12  mov     ebp, eax
0x140025f14  test    eax, eax
0x140025f16  jz      short loc_140025F5C
0x140025f18  mov     rbx, cs:WPP_GLOBAL_Control
0x140025f1f  cmp     rbx, r13
0x140025f22  jz      loc_140025FAA
0x140025f28  mov     ecx, [rbx+2Ch]
0x140025f2b  test    cl, cl
0x140025f2d  jns     short loc_140025FAA
0x140025f2f  mov     rbx, [rbx+18h]
0x140025f33  call    cs:__imp_PsGetCurrentThreadId
0x140025f3a  nop     dword ptr [rax+rax+00h]
0x140025f3f  mov     edx, 31h ; '1'
0x140025f44  mov     dword ptr [rsp+88h+Timeout], ebp
0x140025f48  mov     r9, rax
0x140025f4b  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140025f52  mov     rcx, rbx
0x140025f55  call    WPP_SF_qD
0x140025f5a  jmp     short loc_140025FAA
0x140025f5c  mov     rcx, r12; FastMutex
0x140025f5f  call    cs:__imp_ExReleaseFastMutex
0x140025f66  nop     dword ptr [rax+rax+00h]
0x140025f6b  jmp     loc_14002601B
0x140025f70  mov     rbx, cs:WPP_GLOBAL_Control
0x140025f77  cmp     rbx, r13
0x140025f7a  jz      short loc_140025FAA
0x140025f7c  mov     eax, [rbx+2Ch]
0x140025f7f  test    al, al
0x140025f81  jns     short loc_140025FAA
0x140025f83  mov     rbx, [rbx+18h]
0x140025f87  call    cs:__imp_PsGetCurrentThreadId
0x140025f8e  nop     dword ptr [rax+rax+00h]
0x140025f93  mov     edx, 32h ; '2'
0x140025f98  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140025f9f  mov     r9, rax
0x140025fa2  mov     rcx, rbx
0x140025fa5  call    WPP_SF_q
0x140025faa  lea     rbx, [rdi+188h]
0x140025fb1  xor     r8d, r8d; State
0x140025fb4  mov     rcx, rbx; Event
0x140025fb7  xor     edx, edx; Type
0x140025fb9  call    cs:__imp_KeInitializeEvent
0x140025fc0  nop     dword ptr [rax+rax+00h]
0x140025fc5  mov     rcx, [r14+8]
0x140025fc9  cmp     [rcx], r14
0x140025fcc  jz      short loc_140025FD5
0x140025fce  mov     ecx, 3
0x140025fd3  int     29h; Win8: RtlFailFast(ecx)
0x140025fd5  lea     rax, [rdi+168h]
0x140025fdc  mov     [rax+8], rcx
0x140025fe0  mov     [rax], r14
0x140025fe3  mov     [rcx], rax
0x140025fe6  mov     rcx, r12; FastMutex
0x140025fe9  mov     [r14+8], rax
0x140025fed  call    cs:__imp_ExReleaseFastMutex
0x140025ff4  nop     dword ptr [rax+rax+00h]
0x140025ff9  xor     r9d, r9d; Alertable
0x140025ffc  mov     [rsp+88h+Timeout], 0; Timeout
0x140026005  mov     r8b, 1; WaitMode
0x140026008  xor     edx, edx; WaitReason
0x14002600a  mov     rcx, rbx; Object
0x14002600d  call    cs:__imp_KeWaitForSingleObject
0x140026014  nop     dword ptr [rax+rax+00h]
0x140026019  xor     ebp, ebp
0x14002601b  mov     [rsi], rdi
0x14002601e  mov     eax, 1
0x140026023  lock xadd [r15+658h], eax
0x14002602c  inc     eax
0x14002602e  mov     [rsi+8], eax
0x140026031  mov     [rdi+1A0h], eax
0x140026037  movzx   eax, word ptr [rdi+1A4h]
0x14002603e  mov     [rsi+0Ch], ax
0x140026042  mov     rbx, cs:WPP_GLOBAL_Control
0x140026049  cmp     rbx, r13
0x14002604c  jz      short loc_140026082
0x14002604e  test    dword ptr [rbx+2Ch], 800h
0x140026055  jz      short loc_140026082
0x140026057  mov     rbx, [rbx+18h]
0x14002605b  call    cs:__imp_PsGetCurrentThreadId
0x140026062  nop     dword ptr [rax+rax+00h]
0x140026067  mov     edx, 33h ; '3'
0x14002606c  mov     dword ptr [rsp+88h+Timeout], ebp
0x140026070  mov     r9, rax
0x140026073  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002607a  mov     rcx, rbx
0x14002607d  call    WPP_SF_qD
0x140026082  mov     eax, ebp
0x140026084  add     rsp, 48h
0x140026088  pop     r15
0x14002608a  pop     r14
0x14002608c  pop     r13
0x14002608e  pop     r12
0x140026090  pop     rdi
0x140026091  pop     rsi
0x140026092  pop     rbp
0x140026093  pop     rbx
0x140026094  retn
```
