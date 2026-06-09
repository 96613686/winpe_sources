# MRxDAVQueryVolumeInformationContinuation

- ea: `0x140022860`
- end: `0x140022961`
- name: `MRxDAVQueryVolumeInformationContinuation`
- size: `257`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140022860`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140022890`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400228cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002292d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022890`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400228cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002292d`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryVolumeInformationContinuation(__int64 a1, _QWORD *a2)
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
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 91, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 92, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeQueryVolumeInformationRequest,
         (__int64)MRxDAVPrecompleteUserModeQueryVolumeInformationRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 93, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140022860  push    rbx
0x140022862  push    rsi
0x140022863  push    rdi
0x140022864  push    r14
0x140022866  sub     rsp, 38h
0x14002286a  mov     rdi, rdx
0x14002286d  mov     rsi, rcx
0x140022870  mov     rbx, cs:WPP_GLOBAL_Control
0x140022877  lea     r14, WPP_GLOBAL_Control
0x14002287e  cmp     rbx, r14
0x140022881  jz      short loc_1400228F9
0x140022883  test    dword ptr [rbx+2Ch], 2000h
0x14002288a  jz      short loc_1400228B3
0x14002288c  mov     rbx, [rbx+18h]
0x140022890  call    cs:__imp_PsGetCurrentThreadId
0x140022897  nop     dword ptr [rax+rax+00h]
0x14002289c  mov     edx, 5Bh ; '['
0x1400228a1  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400228a8  mov     r9, rax
0x1400228ab  mov     rcx, rbx
0x1400228ae  call    WPP_SF_q
0x1400228b3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400228ba  cmp     rbx, r14
0x1400228bd  jz      short loc_1400228F9
0x1400228bf  test    dword ptr [rbx+2Ch], 2000h
0x1400228c6  jz      short loc_1400228F9
0x1400228c8  mov     rbx, [rbx+18h]
0x1400228cc  call    cs:__imp_PsGetCurrentThreadId
0x1400228d3  nop     dword ptr [rax+rax+00h]
0x1400228d8  mov     edx, 5Ch ; '\'
0x1400228dd  mov     [rsp+58h+var_30], rdi
0x1400228e2  mov     r9, rax
0x1400228e5  mov     [rsp+58h+var_38], rsi
0x1400228ea  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x1400228f1  mov     rcx, rbx
0x1400228f4  call    WPP_SF_qqq
0x1400228f9  lea     r9, MRxDAVPrecompleteUserModeQueryVolumeInformationRequest
0x140022900  mov     rdx, rdi
0x140022903  lea     r8, MRxDAVFormatUserModeQueryVolumeInformationRequest
0x14002290a  mov     rcx, rsi
0x14002290d  call    UMRxSubmitAsyncEngUserModeRequest
0x140022912  mov     edi, eax
0x140022914  mov     rbx, cs:WPP_GLOBAL_Control
0x14002291b  cmp     rbx, r14
0x14002291e  jz      short loc_140022954
0x140022920  test    dword ptr [rbx+2Ch], 2000h
0x140022927  jz      short loc_140022954
0x140022929  mov     rbx, [rbx+18h]
0x14002292d  call    cs:__imp_PsGetCurrentThreadId
0x140022934  nop     dword ptr [rax+rax+00h]
0x140022939  mov     edx, 5Dh ; ']'
0x14002293e  mov     dword ptr [rsp+58h+var_38], edi
0x140022942  mov     r9, rax
0x140022945  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002294c  mov     rcx, rbx
0x14002294f  call    WPP_SF_qD
0x140022954  mov     eax, edi
0x140022956  add     rsp, 38h
0x14002295a  pop     r14
0x14002295c  pop     rdi
0x14002295d  pop     rsi
0x14002295e  pop     rbx
0x14002295f  retn
```
