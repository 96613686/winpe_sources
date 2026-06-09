# MRxDAVSrvCallWrapper

- ea: `0x14001c570`
- end: `0x14001c739`
- name: `MRxDAVSrvCallWrapper`
- size: `457`
- prototype: `void __fastcall(__int64 Context, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001bdf0`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140006880`
- `0x14001c570`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c59e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c5d8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c65d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c706`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c59e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c5d8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c65d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001c706`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001c6a8`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001c6a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c6bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c6bd`

## string_xrefs

- `0x14001c600`: `MRxDAVCreateSrvCall`

## pseudocode

```c
void __fastcall MRxDAVSrvCallWrapper(__int64 Context, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  int v8; // eax
  int v9; // edi
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rbp
  void (__fastcall *v14)(__int64); // rax
  __int64 v15; // rbx
  HANDLE v16; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 14, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qq(v6, 15, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v7, Context);
    }
  }
  v8 = UMRxAsyncEngOuterWrapper(
         Context,
         a2,
         a3,
         3u,
         (__int64 (__fastcall *)(__int64, __int64))MRxDAVCreateSrvCallContinuation,
         (__int64)"MRxDAVCreateSrvCall");
  v9 = v8;
  if ( v8 && v8 != 259 && v8 != -1073741536 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qD(v10, 16, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v11, v9);
    }
    v12 = *(_QWORD *)(Context + 216);
    v13 = *(_QWORD *)(v12 + 264);
    if ( v13 )
      v13 = *(_QWORD *)(v13 + 32);
    if ( *(_BYTE *)(v13 + 4) )
    {
      SeDeleteClientSecurity(*(_QWORD *)(Context + 224));
      ExFreePoolWithTag(*(PVOID *)(Context + 224), 0);
      *(_QWORD *)(Context + 224) = 0;
      *(_BYTE *)(v13 + 4) = 0;
    }
    v14 = *(void (__fastcall **)(__int64))(v12 + 272);
    *(_DWORD *)(v12 + 280) = v9;
    v14(v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v16 = PsGetCurrentThreadId();
    WPP_SF_qD(v15, 17, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v16, v9);
  }
}

```

## disassembly

```asm
0x14001c570  push    rbx
0x14001c572  push    rbp
0x14001c573  push    rsi
0x14001c574  push    rdi
0x14001c575  push    r15
0x14001c577  sub     rsp, 30h
0x14001c57b  mov     rsi, rcx
0x14001c57e  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c585  lea     r15, WPP_GLOBAL_Control
0x14001c58c  cmp     rbx, r15
0x14001c58f  jz      short loc_14001C600
0x14001c591  test    dword ptr [rbx+2Ch], 4000h
0x14001c598  jz      short loc_14001C5C1
0x14001c59a  mov     rbx, [rbx+18h]
0x14001c59e  call    cs:__imp_PsGetCurrentThreadId
0x14001c5a5  nop     dword ptr [rax+rax+00h]
0x14001c5aa  mov     edx, 0Eh
0x14001c5af  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c5b6  mov     r9, rax
0x14001c5b9  mov     rcx, rbx
0x14001c5bc  call    WPP_SF_q
0x14001c5c1  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c5c8  cmp     rbx, r15
0x14001c5cb  jz      short loc_14001C600
0x14001c5cd  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c5d2  jnb     short loc_14001C600
0x14001c5d4  mov     rbx, [rbx+18h]
0x14001c5d8  call    cs:__imp_PsGetCurrentThreadId
0x14001c5df  nop     dword ptr [rax+rax+00h]
0x14001c5e4  mov     edx, 0Fh
0x14001c5e9  mov     [rsp+58h+var_38], rsi
0x14001c5ee  mov     r9, rax
0x14001c5f1  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c5f8  mov     rcx, rbx
0x14001c5fb  call    WPP_SF_qq
0x14001c600  lea     rax, aMrxdavcreatesr; "MRxDAVCreateSrvCall"
0x14001c607  mov     r9d, 3
0x14001c60d  mov     [rsp+58h+var_30], rax
0x14001c612  mov     rcx, rsi
0x14001c615  lea     rax, MRxDAVCreateSrvCallContinuation
0x14001c61c  mov     [rsp+58h+var_38], rax
0x14001c621  call    UMRxAsyncEngOuterWrapper
0x14001c626  mov     edi, eax
0x14001c628  test    eax, eax
0x14001c62a  jz      loc_14001C6ED
0x14001c630  cmp     eax, 103h
0x14001c635  jz      loc_14001C6ED
0x14001c63b  cmp     eax, 0C0000120h
0x14001c640  jz      loc_14001C6ED
0x14001c646  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c64d  cmp     rbx, r15
0x14001c650  jz      short loc_14001C684
0x14001c652  bt      dword ptr [rbx+2Ch], 0Dh
0x14001c657  jnb     short loc_14001C684
0x14001c659  mov     rbx, [rbx+18h]
0x14001c65d  call    cs:__imp_PsGetCurrentThreadId
0x14001c664  nop     dword ptr [rax+rax+00h]
0x14001c669  mov     edx, 10h
0x14001c66e  mov     dword ptr [rsp+58h+var_38], edi
0x14001c672  mov     r9, rax
0x14001c675  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c67c  mov     rcx, rbx
0x14001c67f  call    WPP_SF_qD
0x14001c684  mov     rbx, [rsi+0D8h]
0x14001c68b  mov     rbp, [rbx+108h]
0x14001c692  test    rbp, rbp
0x14001c695  jz      short loc_14001C69B
0x14001c697  mov     rbp, [rbp+20h]
0x14001c69b  cmp     byte ptr [rbp+4], 0
0x14001c69f  jz      short loc_14001C6D8
0x14001c6a1  mov     rcx, [rsi+0E0h]
0x14001c6a8  call    cs:__imp_SeDeleteClientSecurity
0x14001c6af  nop     dword ptr [rax+rax+00h]
0x14001c6b4  mov     rcx, [rsi+0E0h]; P
0x14001c6bb  xor     edx, edx; Tag
0x14001c6bd  call    cs:__imp_ExFreePoolWithTag
0x14001c6c4  nop     dword ptr [rax+rax+00h]
0x14001c6c9  mov     qword ptr [rsi+0E0h], 0
0x14001c6d4  mov     byte ptr [rbp+4], 0
0x14001c6d8  mov     rax, [rbx+110h]
0x14001c6df  mov     rcx, rbx
0x14001c6e2  mov     [rbx+118h], edi
0x14001c6e8  call    _guard_dispatch_icall
0x14001c6ed  mov     rbx, cs:WPP_GLOBAL_Control
0x14001c6f4  cmp     rbx, r15
0x14001c6f7  jz      short loc_14001C72D
0x14001c6f9  test    dword ptr [rbx+2Ch], 4000h
0x14001c700  jz      short loc_14001C72D
0x14001c702  mov     rbx, [rbx+18h]
0x14001c706  call    cs:__imp_PsGetCurrentThreadId
0x14001c70d  nop     dword ptr [rax+rax+00h]
0x14001c712  mov     edx, 11h
0x14001c717  mov     dword ptr [rsp+58h+var_38], edi
0x14001c71b  mov     r9, rax
0x14001c71e  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001c725  mov     rcx, rbx
0x14001c728  call    WPP_SF_qD
0x14001c72d  add     rsp, 30h
0x14001c731  pop     r15
0x14001c733  pop     rdi
0x14001c734  pop     rsi
0x14001c735  pop     rbp
0x14001c736  pop     rbx
0x14001c737  retn
```
