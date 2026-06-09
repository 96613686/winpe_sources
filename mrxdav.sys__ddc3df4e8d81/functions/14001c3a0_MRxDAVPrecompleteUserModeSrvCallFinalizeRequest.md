# MRxDAVPrecompleteUserModeSrvCallFinalizeRequest

- ea: `0x14001c3a0`
- end: `0x14001c568`
- name: `MRxDAVPrecompleteUserModeSrvCallFinalizeRequest`
- size: `456`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x14001c3a0`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c3df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c415`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c45f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c4b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c4fc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c534`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c3df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c415`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c45f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c4b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c4fc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c534`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeSrvCallFinalizeRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  void *v14; // rdx
  int v15; // esi
  __int64 v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 63, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 64, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v11, a1, a2);
    }
  }
  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qqq(v12, 65, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v13, a1, a2);
  }
  v14 = *(void **)(a3 + 632);
  if ( v14 )
  {
    v15 = UMRxFreeSecondaryBuffer(a1, v14);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v17 = PsGetCurrentThreadId();
        WPP_SF_qD(v16, 66, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v17, v15);
      }
    }
  }
  if ( *(_DWORD *)(a1 + 128) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 1;
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      WPP_SF_q(v18, 67, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v19);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    WPP_SF_q(v20, 68, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v21);
  }
  return 1;
}

```

## disassembly

```asm
0x14001c3a0  push    rbx
0x14001c3a2  push    rbp
0x14001c3a3  push    rsi
0x14001c3a4  push    rdi
0x14001c3a5  push    r12
0x14001c3a7  push    r14
0x14001c3a9  push    r15
0x14001c3ab  sub     rsp, 30h
0x14001c3af  mov     rbp, r8
0x14001c3b2  mov     rsi, rdx
0x14001c3b5  mov     rdi, rcx
0x14001c3b8  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c3bf  lea     r14, WPP_GLOBAL_Control
0x14001c3c6  lea     r12, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c3cd  cmp     rbx, r14
0x14001c3d0  jz      short loc_14001C43E
0x14001c3d2  test    dword ptr [rbx+2Ch], 4000h
0x14001c3d9  jz      short loc_14001C3FE
0x14001c3db  mov     rbx, [rbx+18h]
0x14001c3df  call    cs:__imp_PsGetCurrentThreadId
0x14001c3e6  nop     dword ptr [rax+rax+00h]
0x14001c3eb  mov     edx, 3Fh ; '?'
0x14001c3f0  mov     r8, r12
0x14001c3f3  mov     r9, rax
0x14001c3f6  mov     rcx, rbx
0x14001c3f9  call    WPP_SF_q
0x14001c3fe  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c405  cmp     rbx, r14
0x14001c408  jz      short loc_14001C43E
0x14001c40a  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c40f  jnb     short loc_14001C43E
0x14001c411  mov     rbx, [rbx+18h]
0x14001c415  call    cs:__imp_PsGetCurrentThreadId
0x14001c41c  nop     dword ptr [rax+rax+00h]
0x14001c421  mov     edx, 40h ; '@'
0x14001c426  mov     [rsp+68h+var_40], rsi
0x14001c42b  mov     r9, rax
0x14001c42e  mov     [rsp+68h+var_48], rdi
0x14001c433  mov     r8, r12
0x14001c436  mov     rcx, rbx
0x14001c439  call    WPP_SF_qqq
0x14001c43e  cmp     [rsp+68h+arg_20], 0
0x14001c446  jz      short loc_14001C488
0x14001c448  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c44f  cmp     rbx, r14
0x14001c452  jz      short loc_14001C488
0x14001c454  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c459  jnb     short loc_14001C488
0x14001c45b  mov     rbx, [rbx+18h]
0x14001c45f  call    cs:__imp_PsGetCurrentThreadId
0x14001c466  nop     dword ptr [rax+rax+00h]
0x14001c46b  mov     edx, 41h ; 'A'
0x14001c470  mov     [rsp+68h+var_40], rsi
0x14001c475  mov     r9, rax
0x14001c478  mov     [rsp+68h+var_48], rdi
0x14001c47d  mov     r8, r12
0x14001c480  mov     rcx, rbx
0x14001c483  call    WPP_SF_qqq
0x14001c488  mov     rdx, [rbp+278h]
0x14001c48f  test    rdx, rdx
0x14001c492  jz      short loc_14001C4DC
0x14001c494  mov     rcx, rdi
0x14001c497  call    UMRxFreeSecondaryBuffer
0x14001c49c  mov     esi, eax
0x14001c49e  test    eax, eax
0x14001c4a0  jz      short loc_14001C4DC
0x14001c4a2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c4a9  cmp     rbx, r14
0x14001c4ac  jz      short loc_14001C4DC
0x14001c4ae  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c4b3  jnb     short loc_14001C4DC
0x14001c4b5  mov     rbx, [rbx+18h]
0x14001c4b9  call    cs:__imp_PsGetCurrentThreadId
0x14001c4c0  nop     dword ptr [rax+rax+00h]
0x14001c4c5  mov     edx, 42h ; 'B'
0x14001c4ca  mov     dword ptr [rsp+68h+var_48], esi
0x14001c4ce  mov     r9, rax
0x14001c4d1  mov     r8, r12
0x14001c4d4  mov     rcx, rbx
0x14001c4d7  call    WPP_SF_qD
0x14001c4dc  cmp     dword ptr [rdi+80h], 0
0x14001c4e3  jz      short loc_14001C51B
0x14001c4e5  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c4ec  cmp     rbx, r14
0x14001c4ef  jz      short loc_14001C553
0x14001c4f1  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c4f6  jnb     short loc_14001C51B
0x14001c4f8  mov     rbx, [rbx+18h]
0x14001c4fc  call    cs:__imp_PsGetCurrentThreadId
0x14001c503  nop     dword ptr [rax+rax+00h]
0x14001c508  mov     edx, 43h ; 'C'
0x14001c50d  mov     r8, r12
0x14001c510  mov     r9, rax
0x14001c513  mov     rcx, rbx
0x14001c516  call    WPP_SF_q
0x14001c51b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c522  cmp     rbx, r14
0x14001c525  jz      short loc_14001C553
0x14001c527  test    dword ptr [rbx+2Ch], 4000h
0x14001c52e  jz      short loc_14001C553
0x14001c530  mov     rbx, [rbx+18h]
0x14001c534  call    cs:__imp_PsGetCurrentThreadId
0x14001c53b  nop     dword ptr [rax+rax+00h]
0x14001c540  mov     edx, 44h ; 'D'
0x14001c545  mov     r8, r12
0x14001c548  mov     r9, rax
0x14001c54b  mov     rcx, rbx
0x14001c54e  call    WPP_SF_q
0x14001c553  mov     eax, 1
0x14001c558  add     rsp, 30h
0x14001c55c  pop     r15
0x14001c55e  pop     r14
0x14001c560  pop     r12
0x14001c562  pop     rdi
0x14001c563  pop     rsi
0x14001c564  pop     rbp
0x14001c565  pop     rbx
0x14001c566  retn
```
