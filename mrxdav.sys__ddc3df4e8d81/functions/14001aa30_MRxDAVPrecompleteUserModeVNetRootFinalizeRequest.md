# MRxDAVPrecompleteUserModeVNetRootFinalizeRequest

- ea: `0x14001aa30`
- end: `0x14001abf8`
- name: `MRxDAVPrecompleteUserModeVNetRootFinalizeRequest`
- size: `456`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x14001aa30`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aa6f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aaa5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aaef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ab49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ab8c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001abc4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aa6f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aaa5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001aaef`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ab49`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ab8c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001abc4`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeVNetRootFinalizeRequest(
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
      WPP_SF_q(v8, 84, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 85, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v11, a1, a2);
    }
  }
  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qqq(v12, 86, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v13, a1, a2);
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
        WPP_SF_qD(v16, 87, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v17, v15);
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
      WPP_SF_q(v18, 88, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v19);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    WPP_SF_q(v20, 89, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v21);
  }
  return 1;
}

```

## disassembly

```asm
0x14001aa30  push    rbx
0x14001aa32  push    rbp
0x14001aa33  push    rsi
0x14001aa34  push    rdi
0x14001aa35  push    r12
0x14001aa37  push    r14
0x14001aa39  push    r15
0x14001aa3b  sub     rsp, 30h
0x14001aa3f  mov     rbp, r8
0x14001aa42  mov     rsi, rdx
0x14001aa45  mov     rdi, rcx
0x14001aa48  mov     rbx, cs:WPP_GLOBAL_Control
0x14001aa4f  lea     r14, WPP_GLOBAL_Control
0x14001aa56  lea     r12, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001aa5d  cmp     rbx, r14
0x14001aa60  jz      short loc_14001AACE
0x14001aa62  test    dword ptr [rbx+2Ch], 4000h
0x14001aa69  jz      short loc_14001AA8E
0x14001aa6b  mov     rbx, [rbx+18h]
0x14001aa6f  call    cs:__imp_PsGetCurrentThreadId
0x14001aa76  nop     dword ptr [rax+rax+00h]
0x14001aa7b  mov     edx, 54h ; 'T'
0x14001aa80  mov     r8, r12
0x14001aa83  mov     r9, rax
0x14001aa86  mov     rcx, rbx
0x14001aa89  call    WPP_SF_q
0x14001aa8e  mov     rbx, cs:WPP_GLOBAL_Control
0x14001aa95  cmp     rbx, r14
0x14001aa98  jz      short loc_14001AACE
0x14001aa9a  bt      dword ptr [rbx+2Ch], 0Dh
0x14001aa9f  jnb     short loc_14001AACE
0x14001aaa1  mov     rbx, [rbx+18h]
0x14001aaa5  call    cs:__imp_PsGetCurrentThreadId
0x14001aaac  nop     dword ptr [rax+rax+00h]
0x14001aab1  mov     edx, 55h ; 'U'
0x14001aab6  mov     [rsp+68h+var_40], rsi
0x14001aabb  mov     r9, rax
0x14001aabe  mov     [rsp+68h+var_48], rdi
0x14001aac3  mov     r8, r12
0x14001aac6  mov     rcx, rbx
0x14001aac9  call    WPP_SF_qqq
0x14001aace  cmp     [rsp+68h+arg_20], 0
0x14001aad6  jz      short loc_14001AB18
0x14001aad8  mov     rbx, cs:WPP_GLOBAL_Control
0x14001aadf  cmp     rbx, r14
0x14001aae2  jz      short loc_14001AB18
0x14001aae4  bt      dword ptr [rbx+2Ch], 0Dh
0x14001aae9  jnb     short loc_14001AB18
0x14001aaeb  mov     rbx, [rbx+18h]
0x14001aaef  call    cs:__imp_PsGetCurrentThreadId
0x14001aaf6  nop     dword ptr [rax+rax+00h]
0x14001aafb  mov     edx, 56h ; 'V'
0x14001ab00  mov     [rsp+68h+var_40], rsi
0x14001ab05  mov     r9, rax
0x14001ab08  mov     [rsp+68h+var_48], rdi
0x14001ab0d  mov     r8, r12
0x14001ab10  mov     rcx, rbx
0x14001ab13  call    WPP_SF_qqq
0x14001ab18  mov     rdx, [rbp+278h]
0x14001ab1f  test    rdx, rdx
0x14001ab22  jz      short loc_14001AB6C
0x14001ab24  mov     rcx, rdi
0x14001ab27  call    UMRxFreeSecondaryBuffer
0x14001ab2c  mov     esi, eax
0x14001ab2e  test    eax, eax
0x14001ab30  jz      short loc_14001AB6C
0x14001ab32  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ab39  cmp     rbx, r14
0x14001ab3c  jz      short loc_14001AB6C
0x14001ab3e  bt      dword ptr [rbx+2Ch], 0Dh
0x14001ab43  jnb     short loc_14001AB6C
0x14001ab45  mov     rbx, [rbx+18h]
0x14001ab49  call    cs:__imp_PsGetCurrentThreadId
0x14001ab50  nop     dword ptr [rax+rax+00h]
0x14001ab55  mov     edx, 57h ; 'W'
0x14001ab5a  mov     dword ptr [rsp+68h+var_48], esi
0x14001ab5e  mov     r9, rax
0x14001ab61  mov     r8, r12
0x14001ab64  mov     rcx, rbx
0x14001ab67  call    WPP_SF_qD
0x14001ab6c  cmp     dword ptr [rdi+80h], 0
0x14001ab73  jz      short loc_14001ABAB
0x14001ab75  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ab7c  cmp     rbx, r14
0x14001ab7f  jz      short loc_14001ABE3
0x14001ab81  bt      dword ptr [rbx+2Ch], 0Dh
0x14001ab86  jnb     short loc_14001ABAB
0x14001ab88  mov     rbx, [rbx+18h]
0x14001ab8c  call    cs:__imp_PsGetCurrentThreadId
0x14001ab93  nop     dword ptr [rax+rax+00h]
0x14001ab98  mov     edx, 58h ; 'X'
0x14001ab9d  mov     r8, r12
0x14001aba0  mov     r9, rax
0x14001aba3  mov     rcx, rbx
0x14001aba6  call    WPP_SF_q
0x14001abab  mov     rbx, cs:WPP_GLOBAL_Control
0x14001abb2  cmp     rbx, r14
0x14001abb5  jz      short loc_14001ABE3
0x14001abb7  test    dword ptr [rbx+2Ch], 4000h
0x14001abbe  jz      short loc_14001ABE3
0x14001abc0  mov     rbx, [rbx+18h]
0x14001abc4  call    cs:__imp_PsGetCurrentThreadId
0x14001abcb  nop     dword ptr [rax+rax+00h]
0x14001abd0  mov     edx, 59h ; 'Y'
0x14001abd5  mov     r8, r12
0x14001abd8  mov     r9, rax
0x14001abdb  mov     rcx, rbx
0x14001abde  call    WPP_SF_q
0x14001abe3  mov     eax, 1
0x14001abe8  add     rsp, 30h
0x14001abec  pop     r15
0x14001abee  pop     r14
0x14001abf0  pop     r12
0x14001abf2  pop     rdi
0x14001abf3  pop     rsi
0x14001abf4  pop     rbp
0x14001abf5  pop     rbx
0x14001abf6  retn
```
