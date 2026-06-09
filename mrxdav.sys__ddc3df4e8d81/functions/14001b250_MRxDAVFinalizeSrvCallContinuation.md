# MRxDAVFinalizeSrvCallContinuation

- ea: `0x14001b250`
- end: `0x14001b34f`
- name: `MRxDAVFinalizeSrvCallContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x14001b250`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b27f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b2bb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b31c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b27f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b2bb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b31c`

## pseudocode

```c
__int64 __fastcall MRxDAVFinalizeSrvCallContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 56, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 57, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeSrvCallFinalizeRequest,
         (__int64)MRxDAVPrecompleteUserModeSrvCallFinalizeRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 58, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14001b250  push    rbx
0x14001b252  push    rbp
0x14001b253  push    rsi
0x14001b254  push    rdi
0x14001b255  sub     rsp, 38h
0x14001b259  mov     rdi, rdx
0x14001b25c  mov     rsi, rcx
0x14001b25f  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b266  lea     rbp, WPP_GLOBAL_Control
0x14001b26d  cmp     rbx, rbp
0x14001b270  jz      short loc_14001B2E8
0x14001b272  test    dword ptr [rbx+2Ch], 4000h
0x14001b279  jz      short loc_14001B2A2
0x14001b27b  mov     rbx, [rbx+18h]
0x14001b27f  call    cs:__imp_PsGetCurrentThreadId
0x14001b286  nop     dword ptr [rax+rax+00h]
0x14001b28b  mov     edx, 38h ; '8'
0x14001b290  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b297  mov     r9, rax
0x14001b29a  mov     rcx, rbx
0x14001b29d  call    WPP_SF_q
0x14001b2a2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b2a9  cmp     rbx, rbp
0x14001b2ac  jz      short loc_14001B2E8
0x14001b2ae  test    dword ptr [rbx+2Ch], 2000h
0x14001b2b5  jz      short loc_14001B2E8
0x14001b2b7  mov     rbx, [rbx+18h]
0x14001b2bb  call    cs:__imp_PsGetCurrentThreadId
0x14001b2c2  nop     dword ptr [rax+rax+00h]
0x14001b2c7  mov     edx, 39h ; '9'
0x14001b2cc  mov     [rsp+58h+var_30], rdi
0x14001b2d1  mov     r9, rax
0x14001b2d4  mov     [rsp+58h+var_38], rsi
0x14001b2d9  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b2e0  mov     rcx, rbx
0x14001b2e3  call    WPP_SF_qqq
0x14001b2e8  lea     r9, MRxDAVPrecompleteUserModeSrvCallFinalizeRequest
0x14001b2ef  mov     rdx, rdi
0x14001b2f2  lea     r8, MRxDAVFormatUserModeSrvCallFinalizeRequest
0x14001b2f9  mov     rcx, rsi
0x14001b2fc  call    UMRxSubmitAsyncEngUserModeRequest
0x14001b301  mov     edi, eax
0x14001b303  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b30a  cmp     rbx, rbp
0x14001b30d  jz      short loc_14001B343
0x14001b30f  test    dword ptr [rbx+2Ch], 4000h
0x14001b316  jz      short loc_14001B343
0x14001b318  mov     rbx, [rbx+18h]
0x14001b31c  call    cs:__imp_PsGetCurrentThreadId
0x14001b323  nop     dword ptr [rax+rax+00h]
0x14001b328  mov     edx, 3Ah ; ':'
0x14001b32d  mov     dword ptr [rsp+58h+var_38], edi
0x14001b331  mov     r9, rax
0x14001b334  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b33b  mov     rcx, rbx
0x14001b33e  call    WPP_SF_qD
0x14001b343  mov     eax, edi
0x14001b345  add     rsp, 38h
0x14001b349  pop     rdi
0x14001b34a  pop     rsi
0x14001b34b  pop     rbp
0x14001b34c  pop     rbx
0x14001b34d  retn
```
