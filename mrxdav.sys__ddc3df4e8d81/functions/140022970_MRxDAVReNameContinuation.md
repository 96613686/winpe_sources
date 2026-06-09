# MRxDAVReNameContinuation

- ea: `0x140022970`
- end: `0x140022a6f`
- name: `MRxDAVReNameContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140022970`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002299f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400229db`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022a3c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002299f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400229db`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022a3c`

## pseudocode

```c
__int64 __fastcall MRxDAVReNameContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 47, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 48, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeReNameRequest,
         (__int64)MRxDAVPrecompleteUserModeReNameRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 49, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140022970  push    rbx
0x140022972  push    rbp
0x140022973  push    rsi
0x140022974  push    rdi
0x140022975  sub     rsp, 38h
0x140022979  mov     rdi, rdx
0x14002297c  mov     rsi, rcx
0x14002297f  mov     rbx, cs:WPP_GLOBAL_Control
0x140022986  lea     rbp, WPP_GLOBAL_Control
0x14002298d  cmp     rbx, rbp
0x140022990  jz      short loc_140022A08
0x140022992  test    dword ptr [rbx+2Ch], 4000h
0x140022999  jz      short loc_1400229C2
0x14002299b  mov     rbx, [rbx+18h]
0x14002299f  call    cs:__imp_PsGetCurrentThreadId
0x1400229a6  nop     dword ptr [rax+rax+00h]
0x1400229ab  mov     edx, 2Fh ; '/'
0x1400229b0  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400229b7  mov     r9, rax
0x1400229ba  mov     rcx, rbx
0x1400229bd  call    WPP_SF_q
0x1400229c2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400229c9  cmp     rbx, rbp
0x1400229cc  jz      short loc_140022A08
0x1400229ce  test    dword ptr [rbx+2Ch], 2000h
0x1400229d5  jz      short loc_140022A08
0x1400229d7  mov     rbx, [rbx+18h]
0x1400229db  call    cs:__imp_PsGetCurrentThreadId
0x1400229e2  nop     dword ptr [rax+rax+00h]
0x1400229e7  mov     edx, 30h ; '0'
0x1400229ec  mov     [rsp+58h+var_30], rdi
0x1400229f1  mov     r9, rax
0x1400229f4  mov     [rsp+58h+var_38], rsi
0x1400229f9  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022a00  mov     rcx, rbx
0x140022a03  call    WPP_SF_qqq
0x140022a08  lea     r9, MRxDAVPrecompleteUserModeReNameRequest
0x140022a0f  mov     rdx, rdi
0x140022a12  lea     r8, MRxDAVFormatUserModeReNameRequest
0x140022a19  mov     rcx, rsi
0x140022a1c  call    UMRxSubmitAsyncEngUserModeRequest
0x140022a21  mov     edi, eax
0x140022a23  mov     rbx, cs:WPP_GLOBAL_Control
0x140022a2a  cmp     rbx, rbp
0x140022a2d  jz      short loc_140022A63
0x140022a2f  test    dword ptr [rbx+2Ch], 4000h
0x140022a36  jz      short loc_140022A63
0x140022a38  mov     rbx, [rbx+18h]
0x140022a3c  call    cs:__imp_PsGetCurrentThreadId
0x140022a43  nop     dword ptr [rax+rax+00h]
0x140022a48  mov     edx, 31h ; '1'
0x140022a4d  mov     dword ptr [rsp+58h+var_38], edi
0x140022a51  mov     r9, rax
0x140022a54  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140022a5b  mov     rcx, rbx
0x140022a5e  call    WPP_SF_qD
0x140022a63  mov     eax, edi
0x140022a65  add     rsp, 38h
0x140022a69  pop     rdi
0x140022a6a  pop     rsi
0x140022a6b  pop     rbp
0x140022a6c  pop     rbx
0x140022a6d  retn
```
