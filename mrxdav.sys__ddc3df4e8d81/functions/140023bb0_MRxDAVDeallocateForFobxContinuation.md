# MRxDAVDeallocateForFobxContinuation

- ea: `0x140023bb0`
- end: `0x140023caf`
- name: `MRxDAVDeallocateForFobxContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140023bb0`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140023bdf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023c1b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023c7c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023bdf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023c1b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023c7c`

## pseudocode

```c
__int64 __fastcall MRxDAVDeallocateForFobxContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 15, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 16, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeFobxFinalizeRequest,
         (__int64)MRxDAVPrecompleteUserModeFobxFinalizeRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 17, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140023bb0  push    rbx
0x140023bb2  push    rbp
0x140023bb3  push    rsi
0x140023bb4  push    rdi
0x140023bb5  sub     rsp, 38h
0x140023bb9  mov     rdi, rdx
0x140023bbc  mov     rsi, rcx
0x140023bbf  mov     rbx, cs:WPP_GLOBAL_Control
0x140023bc6  lea     rbp, WPP_GLOBAL_Control
0x140023bcd  cmp     rbx, rbp
0x140023bd0  jz      short loc_140023C48
0x140023bd2  test    dword ptr [rbx+2Ch], 4000h
0x140023bd9  jz      short loc_140023C02
0x140023bdb  mov     rbx, [rbx+18h]
0x140023bdf  call    cs:__imp_PsGetCurrentThreadId
0x140023be6  nop     dword ptr [rax+rax+00h]
0x140023beb  mov     edx, 0Fh
0x140023bf0  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023bf7  mov     r9, rax
0x140023bfa  mov     rcx, rbx
0x140023bfd  call    WPP_SF_q
0x140023c02  mov     rbx, cs:WPP_GLOBAL_Control
0x140023c09  cmp     rbx, rbp
0x140023c0c  jz      short loc_140023C48
0x140023c0e  test    dword ptr [rbx+2Ch], 2000h
0x140023c15  jz      short loc_140023C48
0x140023c17  mov     rbx, [rbx+18h]
0x140023c1b  call    cs:__imp_PsGetCurrentThreadId
0x140023c22  nop     dword ptr [rax+rax+00h]
0x140023c27  mov     edx, 10h
0x140023c2c  mov     [rsp+58h+var_30], rdi
0x140023c31  mov     r9, rax
0x140023c34  mov     [rsp+58h+var_38], rsi
0x140023c39  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023c40  mov     rcx, rbx
0x140023c43  call    WPP_SF_qqq
0x140023c48  lea     r9, MRxDAVPrecompleteUserModeFobxFinalizeRequest
0x140023c4f  mov     rdx, rdi
0x140023c52  lea     r8, MRxDAVFormatUserModeFobxFinalizeRequest
0x140023c59  mov     rcx, rsi
0x140023c5c  call    UMRxSubmitAsyncEngUserModeRequest
0x140023c61  mov     edi, eax
0x140023c63  mov     rbx, cs:WPP_GLOBAL_Control
0x140023c6a  cmp     rbx, rbp
0x140023c6d  jz      short loc_140023CA3
0x140023c6f  test    dword ptr [rbx+2Ch], 4000h
0x140023c76  jz      short loc_140023CA3
0x140023c78  mov     rbx, [rbx+18h]
0x140023c7c  call    cs:__imp_PsGetCurrentThreadId
0x140023c83  nop     dword ptr [rax+rax+00h]
0x140023c88  mov     edx, 11h
0x140023c8d  mov     dword ptr [rsp+58h+var_38], edi
0x140023c91  mov     r9, rax
0x140023c94  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023c9b  mov     rcx, rbx
0x140023c9e  call    WPP_SF_qD
0x140023ca3  mov     eax, edi
0x140023ca5  add     rsp, 38h
0x140023ca9  pop     rdi
0x140023caa  pop     rsi
0x140023cab  pop     rbp
0x140023cac  pop     rbx
0x140023cad  retn
```
