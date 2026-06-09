# UMRxPrepareUserModeRequestBuffer

- ea: `0x140027f1c`
- end: `0x1400282cb`
- name: `UMRxPrepareUserModeRequestBuffer`
- size: `943`
- prototype: `__int64 __fastcall(_QWORD *Context, __int64, __int64, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400262c4`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001bc4`
- `0x140006880`
- `0x140025e10`
- `0x140026dfc`
- `0x140027658`
- `0x140027f1c`
- `0x140028af4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140027f67`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027fa3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002801b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028087`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002810b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028165`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400281fc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028289`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027f67`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027fa3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002801b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028087`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002810b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028165`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400281fc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028289`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027fe4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140027fe4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400281b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400281cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028226`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400281b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400281cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028226`

## pseudocode

```c
__int64 __fastcall UMRxPrepareUserModeRequestBuffer(
        _QWORD *Context,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v5; // r14
  _QWORD *v8; // rsi
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // edi
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 (__fastcall *v17)(_QWORD *, __int64, __int64, _QWORD, unsigned int *); // rbx
  __int64 v18; // rbx
  HANDLE v19; // rax
  unsigned int *v20; // r15
  __int64 v21; // r8
  __int64 v22; // rbx
  HANDLE v23; // rax
  int v24; // esi
  __int64 v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // r9
  __int64 v28; // rbx
  HANDLE v29; // rax
  __int64 v30; // rbx
  HANDLE v31; // rax
  _QWORD *v33; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v34; // [rsp+98h] [rbp+20h]

  v34 = a4;
  v33 = Context;
  v5 = Context[10];
  v8 = Context;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 52, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqqq(v11, 53, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12, a3, v8, v5);
    }
  }
  ExAcquireResourceExclusiveLite(&UMRxAsyncEngineContextListLock, 1u);
  if ( *((_DWORD *)v8 + 12) == 1 )
  {
    if ( a2 == *(_QWORD *)(v5 + 80) )
    {
      v17 = (__int64 (__fastcall *)(_QWORD *, __int64, __int64, _QWORD, unsigned int *))v8[47];
      v14 = UMRxAcquireMidAndFormatHeader(v8);
      if ( !v14 )
      {
        v20 = a5;
        if ( !v17 || (v14 = v17(v8, v5, a3, v34, a5 + 2)) == 0 )
        {
          ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
          *v20 = v14;
          goto LABEL_35;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
        {
          v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v23 = PsGetCurrentThreadId();
          WPP_SF_qD(v22, 56, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v23, v14);
        }
        *v20 = v14;
        v24 = UMRxVerifyHeader(a2, a3, v21, &v33);
        if ( v24
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
        {
          v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v26 = PsGetCurrentThreadId();
          WPP_SF_qD(v25, 58, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v26, v24);
        }
        v8 = v33;
        goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = PsGetCurrentThreadId();
        WPP_SF_qD(v18, 55, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v19, v14);
      }
    }
    else
    {
      v14 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v16 = PsGetCurrentThreadId();
        WPP_SF_q(v15, 54, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v16);
      }
    }
    *a5 = v14;
LABEL_27:
    v27 = v34;
    *((_DWORD *)v8 + 32) = v14;
    UMRxCompleteUserModeErroneousRequest(v8, v13, a3, v27);
    ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
    goto LABEL_35;
  }
  v14 = -1073741536;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
  {
    v28 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v29 = PsGetCurrentThreadId();
    WPP_SF_q(v28, 57, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v29);
  }
  ExReleaseResourceLite(&UMRxAsyncEngineContextListLock);
  if ( *((_DWORD *)v8 + 13) )
  {
    UMRxFinalizeAsyncEngineContext(&v33);
    UMRxFinalizeAsyncEngineContext(&v33);
  }
  UMRxFinalizeAsyncEngineContext(&v33);
  *a5 = -1073741536;
LABEL_35:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v31 = PsGetCurrentThreadId();
    WPP_SF_qD(v30, 59, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v31, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x140027f1c  mov     [rsp+arg_8], rbx
0x140027f21  mov     [rsp+arg_18], r9d
0x140027f26  mov     [rsp+arg_0], rcx
0x140027f2b  push    rbp
0x140027f2c  push    rsi
0x140027f2d  push    rdi
0x140027f2e  push    r12
0x140027f30  push    r13
0x140027f32  push    r14
0x140027f34  push    r15
0x140027f36  sub     rsp, 40h
0x140027f3a  mov     r14, [rcx+50h]
0x140027f3e  mov     r13, r8
0x140027f41  mov     r12, rdx
0x140027f44  mov     rsi, rcx
0x140027f47  mov     rbx, cs:WPP_GLOBAL_Control
0x140027f4e  lea     r15, WPP_GLOBAL_Control
0x140027f55  cmp     rbx, r15
0x140027f58  jz      short loc_140027FD5
0x140027f5a  test    dword ptr [rbx+2Ch], 800h
0x140027f61  jz      short loc_140027F8A
0x140027f63  mov     rbx, [rbx+18h]
0x140027f67  call    cs:__imp_PsGetCurrentThreadId
0x140027f6e  nop     dword ptr [rax+rax+00h]
0x140027f73  mov     edx, 34h ; '4'
0x140027f78  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027f7f  mov     r9, rax
0x140027f82  mov     rcx, rbx
0x140027f85  call    WPP_SF_q
0x140027f8a  mov     rbx, cs:WPP_GLOBAL_Control
0x140027f91  cmp     rbx, r15
0x140027f94  jz      short loc_140027FD5
0x140027f96  test    dword ptr [rbx+2Ch], 200h
0x140027f9d  jz      short loc_140027FD5
0x140027f9f  mov     rbx, [rbx+18h]
0x140027fa3  call    cs:__imp_PsGetCurrentThreadId
0x140027faa  nop     dword ptr [rax+rax+00h]
0x140027faf  mov     [rsp+78h+var_48], r14
0x140027fb4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027fbb  mov     r9, rax
0x140027fbe  mov     [rsp+78h+var_50], rsi
0x140027fc3  mov     edx, 35h ; '5'
0x140027fc8  mov     [rsp+78h+var_58], r13
0x140027fcd  mov     rcx, rbx
0x140027fd0  call    WPP_SF_qqqq
0x140027fd5  mov     ebp, 1
0x140027fda  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140027fe1  mov     dl, bpl; Wait
0x140027fe4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140027feb  nop     dword ptr [rax+rax+00h]
0x140027ff0  cmp     [rsi+30h], ebp
0x140027ff3  jnz     loc_1400281E0
0x140027ff9  cmp     r12, [r14+50h]
0x140027ffd  jz      short loc_140028052
0x140027fff  mov     edi, 0C000000Dh
0x140028004  mov     rbx, cs:WPP_GLOBAL_Control
0x14002800b  cmp     rbx, r15
0x14002800e  jz      short loc_14002803C
0x140028010  mov     eax, [rbx+2Ch]
0x140028013  test    al, al
0x140028015  jns     short loc_14002803C
0x140028017  mov     rbx, [rbx+18h]
0x14002801b  call    cs:__imp_PsGetCurrentThreadId
0x140028022  nop     dword ptr [rax+rax+00h]
0x140028027  lea     edx, [rbp+35h]
0x14002802a  mov     rcx, rbx
0x14002802d  mov     r9, rax
0x140028030  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028037  call    WPP_SF_q
0x14002803c  mov     rax, [rsp+78h+arg_20]
0x140028044  lea     r14, WPP_GLOBAL_Control
0x14002804b  mov     [rax], edi
0x14002804d  jmp     loc_140028194
0x140028052  mov     rbx, [rsi+178h]
0x140028059  mov     r9, r13
0x14002805c  mov     r8, r12
0x14002805f  mov     rdx, r14
0x140028062  mov     rcx, rsi; Context
0x140028065  call    UMRxAcquireMidAndFormatHeader
0x14002806a  mov     edi, eax
0x14002806c  test    eax, eax
0x14002806e  jz      short loc_1400280B0
0x140028070  mov     rbx, cs:WPP_GLOBAL_Control
0x140028077  cmp     rbx, r15
0x14002807a  jz      short loc_14002803C
0x14002807c  mov     ecx, [rbx+2Ch]
0x14002807f  test    cl, cl
0x140028081  jns     short loc_14002803C
0x140028083  mov     rbx, [rbx+18h]
0x140028087  call    cs:__imp_PsGetCurrentThreadId
0x14002808e  nop     dword ptr [rax+rax+00h]
0x140028093  mov     edx, 37h ; '7'
0x140028098  mov     dword ptr [rsp+78h+var_58], edi
0x14002809c  mov     r9, rax
0x14002809f  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400280a6  mov     rcx, rbx
0x1400280a9  call    WPP_SF_qD
0x1400280ae  jmp     short loc_14002803C
0x1400280b0  mov     r15, [rsp+78h+arg_20]
0x1400280b8  test    rbx, rbx
0x1400280bb  jz      loc_1400281C5
0x1400280c1  mov     r9d, [rsp+78h+arg_18]
0x1400280c9  lea     rcx, [r15+8]
0x1400280cd  mov     [rsp+78h+var_58], rcx
0x1400280d2  mov     r8, r13
0x1400280d5  mov     rcx, rsi
0x1400280d8  mov     rdx, r14
0x1400280db  mov     rax, rbx
0x1400280de  call    _guard_dispatch_icall
0x1400280e3  mov     edi, eax
0x1400280e5  test    eax, eax
0x1400280e7  jz      loc_1400281C5
0x1400280ed  mov     rbx, cs:WPP_GLOBAL_Control
0x1400280f4  lea     r14, WPP_GLOBAL_Control
0x1400280fb  cmp     rbx, r14
0x1400280fe  jz      short loc_140028132
0x140028100  mov     eax, [rbx+2Ch]
0x140028103  test    al, al
0x140028105  jns     short loc_140028132
0x140028107  mov     rbx, [rbx+18h]
0x14002810b  call    cs:__imp_PsGetCurrentThreadId
0x140028112  nop     dword ptr [rax+rax+00h]
0x140028117  mov     edx, 38h ; '8'
0x14002811c  mov     dword ptr [rsp+78h+var_58], edi
0x140028120  mov     r9, rax
0x140028123  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x14002812a  mov     rcx, rbx
0x14002812d  call    WPP_SF_qD
0x140028132  lea     r9, [rsp+78h+arg_0]
0x14002813a  mov     [r15], edi
0x14002813d  mov     rdx, r13
0x140028140  mov     rcx, r12
0x140028143  call    UMRxVerifyHeader
0x140028148  mov     esi, eax
0x14002814a  test    eax, eax
0x14002814c  jz      short loc_14002818C
0x14002814e  mov     rbx, cs:WPP_GLOBAL_Control
0x140028155  cmp     rbx, r14
0x140028158  jz      short loc_14002818C
0x14002815a  mov     ecx, [rbx+2Ch]
0x14002815d  test    cl, cl
0x14002815f  jns     short loc_14002818C
0x140028161  mov     rbx, [rbx+18h]
0x140028165  call    cs:__imp_PsGetCurrentThreadId
0x14002816c  nop     dword ptr [rax+rax+00h]
0x140028171  mov     edx, 3Ah ; ':'
0x140028176  mov     dword ptr [rsp+78h+var_58], esi
0x14002817a  mov     r9, rax
0x14002817d  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028184  mov     rcx, rbx
0x140028187  call    WPP_SF_qD
0x14002818c  mov     rsi, [rsp+78h+arg_0]
0x140028194  mov     r9d, [rsp+78h+arg_18]
0x14002819c  mov     r8, r13
0x14002819f  mov     rcx, rsi
0x1400281a2  mov     [rsi+80h], edi
0x1400281a8  call    UMRxCompleteUserModeErroneousRequest
0x1400281ad  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x1400281b4  call    cs:__imp_ExReleaseResourceLite
0x1400281bb  nop     dword ptr [rax+rax+00h]
0x1400281c0  jmp     loc_140028270
0x1400281c5  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x1400281cc  call    cs:__imp_ExReleaseResourceLite
0x1400281d3  nop     dword ptr [rax+rax+00h]
0x1400281d8  mov     [r15], edi
0x1400281db  jmp     loc_140028269
0x1400281e0  mov     edi, 0C0000120h
0x1400281e5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400281ec  cmp     rbx, r15
0x1400281ef  jz      short loc_14002821F
0x1400281f1  mov     eax, [rbx+2Ch]
0x1400281f4  test    al, al
0x1400281f6  jns     short loc_14002821F
0x1400281f8  mov     rbx, [rbx+18h]
0x1400281fc  call    cs:__imp_PsGetCurrentThreadId
0x140028203  nop     dword ptr [rax+rax+00h]
0x140028208  mov     edx, 39h ; '9'
0x14002820d  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028214  mov     r9, rax
0x140028217  mov     rcx, rbx
0x14002821a  call    WPP_SF_q
0x14002821f  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140028226  call    cs:__imp_ExReleaseResourceLite
0x14002822d  nop     dword ptr [rax+rax+00h]
0x140028232  cmp     dword ptr [rsi+34h], 0
0x140028236  lea     rcx, [rsp+78h+arg_0]
0x14002823e  jz      short loc_14002825A
0x140028240  call    UMRxFinalizeAsyncEngineContext
0x140028245  lea     rcx, [rsp+78h+arg_0]
0x14002824d  call    UMRxFinalizeAsyncEngineContext
0x140028252  lea     rcx, [rsp+78h+arg_0]
0x14002825a  call    UMRxFinalizeAsyncEngineContext
0x14002825f  mov     rax, [rsp+78h+arg_20]
0x140028267  mov     [rax], edi
0x140028269  lea     r14, WPP_GLOBAL_Control
0x140028270  mov     rbx, cs:WPP_GLOBAL_Control
0x140028277  cmp     rbx, r14
0x14002827a  jz      short loc_1400282B0
0x14002827c  test    dword ptr [rbx+2Ch], 800h
0x140028283  jz      short loc_1400282B0
0x140028285  mov     rbx, [rbx+18h]
0x140028289  call    cs:__imp_PsGetCurrentThreadId
0x140028290  nop     dword ptr [rax+rax+00h]
0x140028295  mov     edx, 3Bh ; ';'
0x14002829a  mov     dword ptr [rsp+78h+var_58], edi
0x14002829e  mov     r9, rax
0x1400282a1  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400282a8  mov     rcx, rbx
0x1400282ab  call    WPP_SF_qD
0x1400282b0  mov     rbx, [rsp+78h+arg_8]
0x1400282b8  mov     eax, edi
0x1400282ba  add     rsp, 40h
0x1400282be  pop     r15
0x1400282c0  pop     r14
0x1400282c2  pop     r13
0x1400282c4  pop     r12
0x1400282c6  pop     rdi
0x1400282c7  pop     rsi
0x1400282c8  pop     rbp
0x1400282c9  retn
```
