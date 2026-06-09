# MRxDAVCreateSrvCallContinuation

- ea: `0x14001ae20`
- end: `0x14001af35`
- name: `MRxDAVCreateSrvCallContinuation`
- size: `277`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x14001ae20`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ae4f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ae8b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001af02`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ae4f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ae8b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001af02`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateSrvCallContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 18, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 19, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v7, a1, a2);
    }
  }
  *(_DWORD *)(a1 + 56) = 0;
  *(_WORD *)(a1 + 208) |= 1u;
  *(_DWORD *)(a1 + 64) = 1;
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeSrvCallCreateRequest,
         (__int64)MRxDAVPrecompleteUserModeSrvCallCreateRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 20, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14001ae20  push    rbx
0x14001ae22  push    rbp
0x14001ae23  push    rsi
0x14001ae24  push    rdi
0x14001ae25  sub     rsp, 38h
0x14001ae29  mov     rsi, rdx
0x14001ae2c  mov     rdi, rcx
0x14001ae2f  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ae36  lea     rbp, WPP_GLOBAL_Control
0x14001ae3d  cmp     rbx, rbp
0x14001ae40  jz      short loc_14001AEB8
0x14001ae42  test    dword ptr [rbx+2Ch], 4000h
0x14001ae49  jz      short loc_14001AE72
0x14001ae4b  mov     rbx, [rbx+18h]
0x14001ae4f  call    cs:__imp_PsGetCurrentThreadId
0x14001ae56  nop     dword ptr [rax+rax+00h]
0x14001ae5b  mov     edx, 12h
0x14001ae60  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001ae67  mov     r9, rax
0x14001ae6a  mov     rcx, rbx
0x14001ae6d  call    WPP_SF_q
0x14001ae72  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ae79  cmp     rbx, rbp
0x14001ae7c  jz      short loc_14001AEB8
0x14001ae7e  test    dword ptr [rbx+2Ch], 2000h
0x14001ae85  jz      short loc_14001AEB8
0x14001ae87  mov     rbx, [rbx+18h]
0x14001ae8b  call    cs:__imp_PsGetCurrentThreadId
0x14001ae92  nop     dword ptr [rax+rax+00h]
0x14001ae97  mov     edx, 13h
0x14001ae9c  mov     [rsp+58h+var_30], rsi
0x14001aea1  mov     r9, rax
0x14001aea4  mov     [rsp+58h+var_38], rdi
0x14001aea9  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001aeb0  mov     rcx, rbx
0x14001aeb3  call    WPP_SF_qqq
0x14001aeb8  mov     eax, 1
0x14001aebd  mov     dword ptr [rdi+38h], 0
0x14001aec4  or      [rdi+0D0h], ax
0x14001aecb  lea     r9, MRxDAVPrecompleteUserModeSrvCallCreateRequest
0x14001aed2  lea     r8, MRxDAVFormatUserModeSrvCallCreateRequest
0x14001aed9  mov     [rdi+40h], eax
0x14001aedc  mov     rdx, rsi
0x14001aedf  mov     rcx, rdi
0x14001aee2  call    UMRxSubmitAsyncEngUserModeRequest
0x14001aee7  mov     edi, eax
0x14001aee9  mov     rbx, cs:WPP_GLOBAL_Control
0x14001aef0  cmp     rbx, rbp
0x14001aef3  jz      short loc_14001AF29
0x14001aef5  test    dword ptr [rbx+2Ch], 4000h
0x14001aefc  jz      short loc_14001AF29
0x14001aefe  mov     rbx, [rbx+18h]
0x14001af02  call    cs:__imp_PsGetCurrentThreadId
0x14001af09  nop     dword ptr [rax+rax+00h]
0x14001af0e  mov     edx, 14h
0x14001af13  mov     dword ptr [rsp+58h+var_38], edi
0x14001af17  mov     r9, rax
0x14001af1a  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001af21  mov     rcx, rbx
0x14001af24  call    WPP_SF_qD
0x14001af29  mov     eax, edi
0x14001af2b  add     rsp, 38h
0x14001af2f  pop     rdi
0x14001af30  pop     rsi
0x14001af31  pop     rbp
0x14001af32  pop     rbx
0x14001af33  retn
```
