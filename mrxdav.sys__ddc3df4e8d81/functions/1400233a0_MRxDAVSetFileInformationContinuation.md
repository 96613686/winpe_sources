# MRxDAVSetFileInformationContinuation

- ea: `0x1400233a0`
- end: `0x14002349f`
- name: `MRxDAVSetFileInformationContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400233a0`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400233cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002340b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002346c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400233cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002340b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002346c`

## pseudocode

```c
__int64 __fastcall MRxDAVSetFileInformationContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 73, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 74, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeSetFileInformationRequest,
         (__int64)MRxDAVPrecompleteUserModeSetFileInformationRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 75, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1400233a0  push    rbx
0x1400233a2  push    rbp
0x1400233a3  push    rsi
0x1400233a4  push    rdi
0x1400233a5  sub     rsp, 38h
0x1400233a9  mov     rdi, rdx
0x1400233ac  mov     rsi, rcx
0x1400233af  mov     rbx, cs:WPP_GLOBAL_Control
0x1400233b6  lea     rbp, WPP_GLOBAL_Control
0x1400233bd  cmp     rbx, rbp
0x1400233c0  jz      short loc_140023438
0x1400233c2  test    dword ptr [rbx+2Ch], 4000h
0x1400233c9  jz      short loc_1400233F2
0x1400233cb  mov     rbx, [rbx+18h]
0x1400233cf  call    cs:__imp_PsGetCurrentThreadId
0x1400233d6  nop     dword ptr [rax+rax+00h]
0x1400233db  mov     edx, 49h ; 'I'
0x1400233e0  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400233e7  mov     r9, rax
0x1400233ea  mov     rcx, rbx
0x1400233ed  call    WPP_SF_q
0x1400233f2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400233f9  cmp     rbx, rbp
0x1400233fc  jz      short loc_140023438
0x1400233fe  test    dword ptr [rbx+2Ch], 2000h
0x140023405  jz      short loc_140023438
0x140023407  mov     rbx, [rbx+18h]
0x14002340b  call    cs:__imp_PsGetCurrentThreadId
0x140023412  nop     dword ptr [rax+rax+00h]
0x140023417  mov     edx, 4Ah ; 'J'
0x14002341c  mov     [rsp+58h+var_30], rdi
0x140023421  mov     r9, rax
0x140023424  mov     [rsp+58h+var_38], rsi
0x140023429  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140023430  mov     rcx, rbx
0x140023433  call    WPP_SF_qqq
0x140023438  lea     r9, MRxDAVPrecompleteUserModeSetFileInformationRequest
0x14002343f  mov     rdx, rdi
0x140023442  lea     r8, MRxDAVFormatUserModeSetFileInformationRequest
0x140023449  mov     rcx, rsi
0x14002344c  call    UMRxSubmitAsyncEngUserModeRequest
0x140023451  mov     edi, eax
0x140023453  mov     rbx, cs:WPP_GLOBAL_Control
0x14002345a  cmp     rbx, rbp
0x14002345d  jz      short loc_140023493
0x14002345f  test    dword ptr [rbx+2Ch], 4000h
0x140023466  jz      short loc_140023493
0x140023468  mov     rbx, [rbx+18h]
0x14002346c  call    cs:__imp_PsGetCurrentThreadId
0x140023473  nop     dword ptr [rax+rax+00h]
0x140023478  mov     edx, 4Bh ; 'K'
0x14002347d  mov     dword ptr [rsp+58h+var_38], edi
0x140023481  mov     r9, rax
0x140023484  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002348b  mov     rcx, rbx
0x14002348e  call    WPP_SF_qD
0x140023493  mov     eax, edi
0x140023495  add     rsp, 38h
0x140023499  pop     rdi
0x14002349a  pop     rsi
0x14002349b  pop     rbp
0x14002349c  pop     rbx
0x14002349d  retn
```
