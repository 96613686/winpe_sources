# MRxDAVPrecompleteUserModeVNetRootCreateRequest

- ea: `0x14001a6f0`
- end: `0x14001aa2a`
- name: `MRxDAVPrecompleteUserModeVNetRootCreateRequest`
- size: `826`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001680`
- `0x140001b64`
- `0x14001a6f0`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a744`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a7a1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a7fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a855`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a8af`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a914`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a96e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a9cb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a744`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a7a1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a7fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a855`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a8af`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a914`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a96e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001a9cb`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeVNetRootCreateRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v8; // rsi
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  int v11; // r14d
  __int64 v12; // rbx
  HANDLE v13; // rax
  int v14; // r14d
  __int64 v15; // rbx
  HANDLE v16; // rax
  int v17; // r14d
  __int64 v18; // rbx
  HANDLE v19; // rax
  int v20; // r14d
  __int64 v21; // rbx
  HANDLE v22; // rax
  int v23; // r14d
  __int64 v24; // rbx
  HANDLE v25; // rax
  int v26; // r14d
  __int64 v27; // rbx
  HANDLE v28; // rax
  int v29; // ebp
  __int64 v30; // rbx
  HANDLE v31; // rax

  if ( a5 )
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qqq(v9, 54, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId, a1, a2);
    }
  }
  else
  {
    v8 = *(_QWORD *)(a2 + 216);
    if ( v8 )
      v8 = *(_QWORD *)(v8 + 40);
  }
  if ( *(_QWORD *)(a3 + 632) )
  {
    v11 = UMRxFreeSecondaryBuffer(a1);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        WPP_SF_qD(v12, 55, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v13, v11);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 7080) )
  {
    v14 = UMRxFreeSecondaryBuffer(a1);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v16 = PsGetCurrentThreadId();
        WPP_SF_qD(v15, 56, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v16, v14);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 9168) )
  {
    v17 = UMRxFreeSecondaryBuffer(a1);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = PsGetCurrentThreadId();
        WPP_SF_qD(v18, 57, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v19, v17);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 7104) )
  {
    v20 = UMRxFreeSecondaryBuffer(a1);
    if ( v20
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v22 = PsGetCurrentThreadId();
      WPP_SF_qD(v21, 58, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v22, v20);
    }
    *(_QWORD *)(a3 + 7104) = 0;
  }
  if ( *(_QWORD *)(a3 + 640) )
  {
    v23 = UMRxFreeSecondaryBuffer(a1);
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v25 = PsGetCurrentThreadId();
        WPP_SF_qD(v24, 59, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v25, v23);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 664) )
  {
    v26 = UMRxFreeSecondaryBuffer(a1);
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v28 = PsGetCurrentThreadId();
        WPP_SF_qD(v27, 60, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v28, v26);
      }
    }
  }
  if ( !a5 )
  {
    v29 = *(_DWORD *)(a1 + 128);
    if ( v29 )
    {
      *(_DWORD *)(v8 + 100) = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v31 = PsGetCurrentThreadId();
        WPP_SF_qD(v30, 61, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v31, v29);
      }
    }
    else
    {
      *(_DWORD *)(v8 + 88) = *(_DWORD *)(a3 + 2312);
      *(_DWORD *)(v8 + 92) = *(_DWORD *)(a3 + 2316);
      *(_DWORD *)(v8 + 96) = *(_DWORD *)(a3 + 2320);
      *(_DWORD *)(v8 + 104) = *(_DWORD *)(a3 + 2324);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14001a6f0  push    rbx
0x14001a6f2  push    rbp
0x14001a6f3  push    rsi
0x14001a6f4  push    rdi
0x14001a6f5  push    r12
0x14001a6f7  push    r13
0x14001a6f9  push    r14
0x14001a6fb  sub     rsp, 30h
0x14001a6ff  cmp     [rsp+68h+arg_20], 0
0x14001a707  lea     r13, WPP_GLOBAL_Control
0x14001a70e  mov     rdi, r8
0x14001a711  mov     r14, rdx
0x14001a714  mov     rbp, rcx
0x14001a717  jnz     short loc_14001A72B
0x14001a719  mov     rsi, [rdx+0D8h]
0x14001a720  test    rsi, rsi
0x14001a723  jz      short loc_14001A76F
0x14001a725  mov     rsi, [rsi+28h]
0x14001a729  jmp     short loc_14001A76F
0x14001a72b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a732  xor     esi, esi
0x14001a734  cmp     rbx, r13
0x14001a737  jz      short loc_14001A76F
0x14001a739  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a73e  jnb     short loc_14001A76F
0x14001a740  mov     rbx, [rbx+18h]
0x14001a744  call    cs:__imp_PsGetCurrentThreadId
0x14001a74b  nop     dword ptr [rax+rax+00h]
0x14001a750  lea     edx, [rsi+36h]
0x14001a753  mov     [rsp+68h+var_40], r14
0x14001a758  mov     r9, rax
0x14001a75b  mov     [rsp+68h+var_48], rbp
0x14001a760  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a767  mov     rcx, rbx
0x14001a76a  call    WPP_SF_qqq
0x14001a76f  mov     rdx, [rdi+278h]
0x14001a776  test    rdx, rdx
0x14001a779  jz      short loc_14001A7C9
0x14001a77b  mov     rcx, rbp
0x14001a77e  call    UMRxFreeSecondaryBuffer
0x14001a783  mov     r14d, eax
0x14001a786  test    eax, eax
0x14001a788  jz      short loc_14001A7C9
0x14001a78a  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a791  cmp     rbx, r13
0x14001a794  jz      short loc_14001A7C9
0x14001a796  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a79b  jnb     short loc_14001A7C9
0x14001a79d  mov     rbx, [rbx+18h]
0x14001a7a1  call    cs:__imp_PsGetCurrentThreadId
0x14001a7a8  nop     dword ptr [rax+rax+00h]
0x14001a7ad  mov     edx, 37h ; '7'
0x14001a7b2  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a7b7  mov     r9, rax
0x14001a7ba  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a7c1  mov     rcx, rbx
0x14001a7c4  call    WPP_SF_qD
0x14001a7c9  mov     rdx, [rdi+1BA8h]
0x14001a7d0  test    rdx, rdx
0x14001a7d3  jz      short loc_14001A823
0x14001a7d5  mov     rcx, rbp
0x14001a7d8  call    UMRxFreeSecondaryBuffer
0x14001a7dd  mov     r14d, eax
0x14001a7e0  test    eax, eax
0x14001a7e2  jz      short loc_14001A823
0x14001a7e4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a7eb  cmp     rbx, r13
0x14001a7ee  jz      short loc_14001A823
0x14001a7f0  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a7f5  jnb     short loc_14001A823
0x14001a7f7  mov     rbx, [rbx+18h]
0x14001a7fb  call    cs:__imp_PsGetCurrentThreadId
0x14001a802  nop     dword ptr [rax+rax+00h]
0x14001a807  mov     edx, 38h ; '8'
0x14001a80c  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a811  mov     r9, rax
0x14001a814  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a81b  mov     rcx, rbx
0x14001a81e  call    WPP_SF_qD
0x14001a823  mov     rdx, [rdi+23D0h]
0x14001a82a  test    rdx, rdx
0x14001a82d  jz      short loc_14001A87D
0x14001a82f  mov     rcx, rbp
0x14001a832  call    UMRxFreeSecondaryBuffer
0x14001a837  mov     r14d, eax
0x14001a83a  test    eax, eax
0x14001a83c  jz      short loc_14001A87D
0x14001a83e  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a845  cmp     rbx, r13
0x14001a848  jz      short loc_14001A87D
0x14001a84a  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a84f  jnb     short loc_14001A87D
0x14001a851  mov     rbx, [rbx+18h]
0x14001a855  call    cs:__imp_PsGetCurrentThreadId
0x14001a85c  nop     dword ptr [rax+rax+00h]
0x14001a861  mov     edx, 39h ; '9'
0x14001a866  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a86b  mov     r9, rax
0x14001a86e  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a875  mov     rcx, rbx
0x14001a878  call    WPP_SF_qD
0x14001a87d  mov     rdx, [rdi+1BC0h]
0x14001a884  test    rdx, rdx
0x14001a887  jz      short loc_14001A8E2
0x14001a889  mov     rcx, rbp
0x14001a88c  call    UMRxFreeSecondaryBuffer
0x14001a891  mov     r14d, eax
0x14001a894  test    eax, eax
0x14001a896  jz      short loc_14001A8D7
0x14001a898  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a89f  cmp     rbx, r13
0x14001a8a2  jz      short loc_14001A8D7
0x14001a8a4  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a8a9  jnb     short loc_14001A8D7
0x14001a8ab  mov     rbx, [rbx+18h]
0x14001a8af  call    cs:__imp_PsGetCurrentThreadId
0x14001a8b6  nop     dword ptr [rax+rax+00h]
0x14001a8bb  mov     edx, 3Ah ; ':'
0x14001a8c0  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a8c5  mov     r9, rax
0x14001a8c8  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a8cf  mov     rcx, rbx
0x14001a8d2  call    WPP_SF_qD
0x14001a8d7  mov     qword ptr [rdi+1BC0h], 0
0x14001a8e2  mov     rdx, [rdi+280h]
0x14001a8e9  test    rdx, rdx
0x14001a8ec  jz      short loc_14001A93C
0x14001a8ee  mov     rcx, rbp
0x14001a8f1  call    UMRxFreeSecondaryBuffer
0x14001a8f6  mov     r14d, eax
0x14001a8f9  test    eax, eax
0x14001a8fb  jz      short loc_14001A93C
0x14001a8fd  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a904  cmp     rbx, r13
0x14001a907  jz      short loc_14001A93C
0x14001a909  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a90e  jnb     short loc_14001A93C
0x14001a910  mov     rbx, [rbx+18h]
0x14001a914  call    cs:__imp_PsGetCurrentThreadId
0x14001a91b  nop     dword ptr [rax+rax+00h]
0x14001a920  mov     edx, 3Bh ; ';'
0x14001a925  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a92a  mov     r9, rax
0x14001a92d  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a934  mov     rcx, rbx
0x14001a937  call    WPP_SF_qD
0x14001a93c  mov     rdx, [rdi+298h]
0x14001a943  test    rdx, rdx
0x14001a946  jz      short loc_14001A996
0x14001a948  mov     rcx, rbp
0x14001a94b  call    UMRxFreeSecondaryBuffer
0x14001a950  mov     r14d, eax
0x14001a953  test    eax, eax
0x14001a955  jz      short loc_14001A996
0x14001a957  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a95e  cmp     rbx, r13
0x14001a961  jz      short loc_14001A996
0x14001a963  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a968  jnb     short loc_14001A996
0x14001a96a  mov     rbx, [rbx+18h]
0x14001a96e  call    cs:__imp_PsGetCurrentThreadId
0x14001a975  nop     dword ptr [rax+rax+00h]
0x14001a97a  mov     edx, 3Ch ; '<'
0x14001a97f  mov     dword ptr [rsp+68h+var_48], r14d
0x14001a984  mov     r9, rax
0x14001a987  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a98e  mov     rcx, rbx
0x14001a991  call    WPP_SF_qD
0x14001a996  cmp     [rsp+68h+arg_20], 0
0x14001a99e  mov     r14d, 1
0x14001a9a4  jnz     short loc_14001AA17
0x14001a9a6  mov     ebp, [rbp+80h]
0x14001a9ac  test    ebp, ebp
0x14001a9ae  jz      short loc_14001A9F3
0x14001a9b0  mov     [rsi+64h], r14d
0x14001a9b4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001a9bb  cmp     rbx, r13
0x14001a9be  jz      short loc_14001AA17
0x14001a9c0  bt      dword ptr [rbx+2Ch], 0Dh
0x14001a9c5  jnb     short loc_14001AA17
0x14001a9c7  mov     rbx, [rbx+18h]
0x14001a9cb  call    cs:__imp_PsGetCurrentThreadId
0x14001a9d2  nop     dword ptr [rax+rax+00h]
0x14001a9d7  lea     edx, [r14+3Ch]
0x14001a9db  mov     dword ptr [rsp+68h+var_48], ebp
0x14001a9df  mov     r9, rax
0x14001a9e2  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001a9e9  mov     rcx, rbx
0x14001a9ec  call    WPP_SF_qD
0x14001a9f1  jmp     short loc_14001AA17
0x14001a9f3  mov     ecx, [rdi+908h]
0x14001a9f9  mov     [rsi+58h], ecx
0x14001a9fc  mov     ecx, [rdi+90Ch]
0x14001aa02  mov     [rsi+5Ch], ecx
0x14001aa05  mov     ecx, [rdi+910h]
0x14001aa0b  mov     [rsi+60h], ecx
0x14001aa0e  mov     ecx, [rdi+914h]
0x14001aa14  mov     [rsi+68h], ecx
0x14001aa17  mov     eax, r14d
0x14001aa1a  add     rsp, 30h
0x14001aa1e  pop     r14
0x14001aa20  pop     r13
0x14001aa22  pop     r12
0x14001aa24  pop     rdi
0x14001aa25  pop     rsi
0x14001aa26  pop     rbp
0x14001aa27  pop     rbx
0x14001aa28  retn
```
