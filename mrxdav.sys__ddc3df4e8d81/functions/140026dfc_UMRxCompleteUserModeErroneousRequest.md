# UMRxCompleteUserModeErroneousRequest

- ea: `0x140026dfc`
- end: `0x140026f4b`
- name: `UMRxCompleteUserModeErroneousRequest`
- size: `335`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140027f1c`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001bc4`
- `0x14000610c`
- `0x140006880`
- `0x140026dfc`
- `0x140027658`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140026e46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026e80`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026f04`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026e46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026e80`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026f04`

## pseudocode

```c
__int64 __fastcall UMRxCompleteUserModeErroneousRequest(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rsi
  int v8; // ebp
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 (__fastcall *v13)(__int64, __int64, __int64, _QWORD, _DWORD); // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = a1;
  v4 = *(_QWORD *)(a1 + 80);
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 60, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqqq(v11, 61, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12, a3, a1, v4);
    }
  }
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD))(a1 + 384);
  if ( v13 )
    v8 = v13(a1, v4, a3, a4, 0);
  UMRxFinalizeAsyncEngineContext(&v19);
  if ( v8 )
    UMRxAsyncEngineCalldownIrpCompletion(v15, v14, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v17 = PsGetCurrentThreadId();
    WPP_SF_qD(v16, 62, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v17, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140026dfc  mov     [rsp+arg_8], rbx
0x140026e01  mov     [rsp+arg_10], rbp
0x140026e06  mov     [rsp+arg_0], rcx
0x140026e0b  push    rsi
0x140026e0c  push    rdi
0x140026e0d  push    r12
0x140026e0f  push    r14
0x140026e11  push    r15
0x140026e13  sub     rsp, 40h
0x140026e17  mov     rsi, [rcx+50h]
0x140026e1b  mov     r15d, r9d
0x140026e1e  mov     r14, r8
0x140026e21  mov     rdi, rcx
0x140026e24  xor     ebp, ebp
0x140026e26  mov     rbx, cs:WPP_GLOBAL_Control
0x140026e2d  lea     r12, WPP_GLOBAL_Control
0x140026e34  cmp     rbx, r12
0x140026e37  jz      short loc_140026EB2
0x140026e39  test    dword ptr [rbx+2Ch], 800h
0x140026e40  jz      short loc_140026E67
0x140026e42  mov     rbx, [rbx+18h]
0x140026e46  call    cs:__imp_PsGetCurrentThreadId
0x140026e4d  nop     dword ptr [rax+rax+00h]
0x140026e52  lea     edx, [rbp+3Ch]
0x140026e55  mov     rcx, rbx
0x140026e58  mov     r9, rax
0x140026e5b  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026e62  call    WPP_SF_q
0x140026e67  mov     rbx, cs:WPP_GLOBAL_Control
0x140026e6e  cmp     rbx, r12
0x140026e71  jz      short loc_140026EB2
0x140026e73  test    dword ptr [rbx+2Ch], 200h
0x140026e7a  jz      short loc_140026EB2
0x140026e7c  mov     rbx, [rbx+18h]
0x140026e80  call    cs:__imp_PsGetCurrentThreadId
0x140026e87  nop     dword ptr [rax+rax+00h]
0x140026e8c  mov     [rsp+68h+var_38], rsi
0x140026e91  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026e98  mov     r9, rax
0x140026e9b  mov     [rsp+68h+var_40], rdi
0x140026ea0  mov     edx, 3Dh ; '='
0x140026ea5  mov     [rsp+68h+var_48], r14
0x140026eaa  mov     rcx, rbx
0x140026ead  call    WPP_SF_qqqq
0x140026eb2  mov     rax, [rdi+180h]
0x140026eb9  test    rax, rax
0x140026ebc  jz      short loc_140026ED5
0x140026ebe  mov     r9d, r15d
0x140026ec1  mov     dword ptr [rsp+68h+var_48], ebp
0x140026ec5  mov     r8, r14
0x140026ec8  mov     rdx, rsi
0x140026ecb  mov     rcx, rdi
0x140026ece  call    _guard_dispatch_icall
0x140026ed3  mov     ebp, eax
0x140026ed5  lea     rcx, [rsp+68h+arg_0]
0x140026eda  call    UMRxFinalizeAsyncEngineContext
0x140026edf  test    ebp, ebp
0x140026ee1  jz      short loc_140026EEB
0x140026ee3  mov     r8, rsi
0x140026ee6  call    UMRxAsyncEngineCalldownIrpCompletion
0x140026eeb  mov     rbx, cs:WPP_GLOBAL_Control
0x140026ef2  cmp     rbx, r12
0x140026ef5  jz      short loc_140026F2F
0x140026ef7  test    dword ptr [rbx+2Ch], 800h
0x140026efe  jz      short loc_140026F2F
0x140026f00  mov     rbx, [rbx+18h]
0x140026f04  call    cs:__imp_PsGetCurrentThreadId
0x140026f0b  nop     dword ptr [rax+rax+00h]
0x140026f10  mov     edx, 3Eh ; '>'
0x140026f15  mov     dword ptr [rsp+68h+var_48], 0
0x140026f1d  mov     r9, rax
0x140026f20  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026f27  mov     rcx, rbx
0x140026f2a  call    WPP_SF_qD
0x140026f2f  lea     r11, [rsp+68h+var_28]
0x140026f34  xor     eax, eax
0x140026f36  mov     rbx, [r11+38h]
0x140026f3a  mov     rbp, [r11+40h]
0x140026f3e  mov     rsp, r11
0x140026f41  pop     r15
0x140026f43  pop     r14
0x140026f45  pop     r12
0x140026f47  pop     rdi
0x140026f48  pop     rsi
0x140026f49  retn
```
