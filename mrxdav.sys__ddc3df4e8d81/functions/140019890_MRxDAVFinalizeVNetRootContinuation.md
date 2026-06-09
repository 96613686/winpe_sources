# MRxDAVFinalizeVNetRootContinuation

- ea: `0x140019890`
- end: `0x14001998f`
- name: `MRxDAVFinalizeVNetRootContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140019890`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400198bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400198fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001995c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400198bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400198fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001995c`

## pseudocode

```c
__int64 __fastcall MRxDAVFinalizeVNetRootContinuation(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned int v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 75, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 76, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeVNetRootFinalizeRequest,
         (__int64)MRxDAVPrecompleteUserModeVNetRootFinalizeRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 77, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140019890  push    rbx
0x140019892  push    rbp
0x140019893  push    rsi
0x140019894  push    rdi
0x140019895  sub     rsp, 38h
0x140019899  mov     rdi, rdx
0x14001989c  mov     rsi, rcx
0x14001989f  mov     rbx, cs:WPP_GLOBAL_Control
0x1400198a6  lea     rbp, WPP_GLOBAL_Control
0x1400198ad  cmp     rbx, rbp
0x1400198b0  jz      short loc_140019928
0x1400198b2  test    dword ptr [rbx+2Ch], 4000h
0x1400198b9  jz      short loc_1400198E2
0x1400198bb  mov     rbx, [rbx+18h]
0x1400198bf  call    cs:__imp_PsGetCurrentThreadId
0x1400198c6  nop     dword ptr [rax+rax+00h]
0x1400198cb  mov     edx, 4Bh ; 'K'
0x1400198d0  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400198d7  mov     r9, rax
0x1400198da  mov     rcx, rbx
0x1400198dd  call    WPP_SF_q
0x1400198e2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400198e9  cmp     rbx, rbp
0x1400198ec  jz      short loc_140019928
0x1400198ee  test    dword ptr [rbx+2Ch], 2000h
0x1400198f5  jz      short loc_140019928
0x1400198f7  mov     rbx, [rbx+18h]
0x1400198fb  call    cs:__imp_PsGetCurrentThreadId
0x140019902  nop     dword ptr [rax+rax+00h]
0x140019907  mov     edx, 4Ch ; 'L'
0x14001990c  mov     [rsp+58h+var_30], rdi
0x140019911  mov     r9, rax
0x140019914  mov     [rsp+58h+var_38], rsi
0x140019919  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140019920  mov     rcx, rbx
0x140019923  call    WPP_SF_qqq
0x140019928  lea     r9, MRxDAVPrecompleteUserModeVNetRootFinalizeRequest
0x14001992f  mov     rdx, rdi
0x140019932  lea     r8, MRxDAVFormatUserModeVNetRootFinalizeRequest
0x140019939  mov     rcx, rsi
0x14001993c  call    UMRxSubmitAsyncEngUserModeRequest
0x140019941  mov     edi, eax
0x140019943  mov     rbx, cs:WPP_GLOBAL_Control
0x14001994a  cmp     rbx, rbp
0x14001994d  jz      short loc_140019983
0x14001994f  test    dword ptr [rbx+2Ch], 4000h
0x140019956  jz      short loc_140019983
0x140019958  mov     rbx, [rbx+18h]
0x14001995c  call    cs:__imp_PsGetCurrentThreadId
0x140019963  nop     dword ptr [rax+rax+00h]
0x140019968  mov     edx, 4Dh ; 'M'
0x14001996d  mov     dword ptr [rsp+58h+var_38], edi
0x140019971  mov     r9, rax
0x140019974  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001997b  mov     rcx, rbx
0x14001997e  call    WPP_SF_qD
0x140019983  mov     eax, edi
0x140019985  add     rsp, 38h
0x140019989  pop     rdi
0x14001998a  pop     rsi
0x14001998b  pop     rbp
0x14001998c  pop     rbx
0x14001998d  retn
```
