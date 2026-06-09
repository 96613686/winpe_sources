# MRxDAVDeallocateForFcbContinuation

- ea: `0x140003b10`
- end: `0x140003c0f`
- name: `MRxDAVDeallocateForFcbContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140003b10`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140003b3f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003b7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003bdc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003b3f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003b7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003bdc`

## pseudocode

```c
__int64 __fastcall MRxDAVDeallocateForFcbContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 36, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 37, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeFcbFinalizeRequest,
         (__int64)MRxDAVPrecompleteUserModeFcbFinalizeRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 38, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140003b10  push    rbx
0x140003b12  push    rbp
0x140003b13  push    rsi
0x140003b14  push    rdi
0x140003b15  sub     rsp, 38h
0x140003b19  mov     rdi, rdx
0x140003b1c  mov     rsi, rcx
0x140003b1f  mov     rbx, cs:WPP_GLOBAL_Control
0x140003b26  lea     rbp, WPP_GLOBAL_Control
0x140003b2d  cmp     rbx, rbp
0x140003b30  jz      short loc_140003BA8
0x140003b32  test    dword ptr [rbx+2Ch], 4000h
0x140003b39  jz      short loc_140003B62
0x140003b3b  mov     rbx, [rbx+18h]
0x140003b3f  call    cs:__imp_PsGetCurrentThreadId
0x140003b46  nop     dword ptr [rax+rax+00h]
0x140003b4b  mov     edx, 24h ; '$'
0x140003b50  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003b57  mov     r9, rax
0x140003b5a  mov     rcx, rbx
0x140003b5d  call    WPP_SF_q
0x140003b62  mov     rbx, cs:WPP_GLOBAL_Control
0x140003b69  cmp     rbx, rbp
0x140003b6c  jz      short loc_140003BA8
0x140003b6e  test    dword ptr [rbx+2Ch], 2000h
0x140003b75  jz      short loc_140003BA8
0x140003b77  mov     rbx, [rbx+18h]
0x140003b7b  call    cs:__imp_PsGetCurrentThreadId
0x140003b82  nop     dword ptr [rax+rax+00h]
0x140003b87  mov     edx, 25h ; '%'
0x140003b8c  mov     [rsp+58h+var_30], rdi
0x140003b91  mov     r9, rax
0x140003b94  mov     [rsp+58h+var_38], rsi
0x140003b99  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003ba0  mov     rcx, rbx
0x140003ba3  call    WPP_SF_qqq
0x140003ba8  lea     r9, MRxDAVPrecompleteUserModeFcbFinalizeRequest
0x140003baf  mov     rdx, rdi
0x140003bb2  lea     r8, MRxDAVFormatUserModeFcbFinalizeRequest
0x140003bb9  mov     rcx, rsi
0x140003bbc  call    UMRxSubmitAsyncEngUserModeRequest
0x140003bc1  mov     edi, eax
0x140003bc3  mov     rbx, cs:WPP_GLOBAL_Control
0x140003bca  cmp     rbx, rbp
0x140003bcd  jz      short loc_140003C03
0x140003bcf  test    dword ptr [rbx+2Ch], 4000h
0x140003bd6  jz      short loc_140003C03
0x140003bd8  mov     rbx, [rbx+18h]
0x140003bdc  call    cs:__imp_PsGetCurrentThreadId
0x140003be3  nop     dword ptr [rax+rax+00h]
0x140003be8  mov     edx, 26h ; '&'
0x140003bed  mov     dword ptr [rsp+58h+var_38], edi
0x140003bf1  mov     r9, rax
0x140003bf4  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003bfb  mov     rcx, rbx
0x140003bfe  call    WPP_SF_qD
0x140003c03  mov     eax, edi
0x140003c05  add     rsp, 38h
0x140003c09  pop     rdi
0x140003c0a  pop     rsi
0x140003c0b  pop     rbp
0x140003c0c  pop     rbx
0x140003c0d  retn
```
