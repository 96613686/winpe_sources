# MRxDAVCreateVNetRootContinuation

- ea: `0x1400191b0`
- end: `0x1400192af`
- name: `MRxDAVCreateVNetRootContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400191b0`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400191df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001921b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001927c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400191df`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001921b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001927c`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateVNetRootContinuation(__int64 a1, _QWORD *a2)
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
      WPP_SF_q(v4, 28, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 29, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         (__int64)MRxDAVFormatUserModeVNetRootCreateRequest,
         (__int64)MRxDAVPrecompleteUserModeVNetRootCreateRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 30, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1400191b0  push    rbx
0x1400191b2  push    rbp
0x1400191b3  push    rsi
0x1400191b4  push    rdi
0x1400191b5  sub     rsp, 38h
0x1400191b9  mov     rdi, rdx
0x1400191bc  mov     rsi, rcx
0x1400191bf  mov     rbx, cs:WPP_GLOBAL_Control
0x1400191c6  lea     rbp, WPP_GLOBAL_Control
0x1400191cd  cmp     rbx, rbp
0x1400191d0  jz      short loc_140019248
0x1400191d2  test    dword ptr [rbx+2Ch], 4000h
0x1400191d9  jz      short loc_140019202
0x1400191db  mov     rbx, [rbx+18h]
0x1400191df  call    cs:__imp_PsGetCurrentThreadId
0x1400191e6  nop     dword ptr [rax+rax+00h]
0x1400191eb  mov     edx, 1Ch
0x1400191f0  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400191f7  mov     r9, rax
0x1400191fa  mov     rcx, rbx
0x1400191fd  call    WPP_SF_q
0x140019202  mov     rbx, cs:WPP_GLOBAL_Control
0x140019209  cmp     rbx, rbp
0x14001920c  jz      short loc_140019248
0x14001920e  test    dword ptr [rbx+2Ch], 2000h
0x140019215  jz      short loc_140019248
0x140019217  mov     rbx, [rbx+18h]
0x14001921b  call    cs:__imp_PsGetCurrentThreadId
0x140019222  nop     dword ptr [rax+rax+00h]
0x140019227  mov     edx, 1Dh
0x14001922c  mov     [rsp+58h+var_30], rdi
0x140019231  mov     r9, rax
0x140019234  mov     [rsp+58h+var_38], rsi
0x140019239  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140019240  mov     rcx, rbx
0x140019243  call    WPP_SF_qqq
0x140019248  lea     r9, MRxDAVPrecompleteUserModeVNetRootCreateRequest
0x14001924f  mov     rdx, rdi
0x140019252  lea     r8, MRxDAVFormatUserModeVNetRootCreateRequest
0x140019259  mov     rcx, rsi
0x14001925c  call    UMRxSubmitAsyncEngUserModeRequest
0x140019261  mov     edi, eax
0x140019263  mov     rbx, cs:WPP_GLOBAL_Control
0x14001926a  cmp     rbx, rbp
0x14001926d  jz      short loc_1400192A3
0x14001926f  test    dword ptr [rbx+2Ch], 4000h
0x140019276  jz      short loc_1400192A3
0x140019278  mov     rbx, [rbx+18h]
0x14001927c  call    cs:__imp_PsGetCurrentThreadId
0x140019283  nop     dword ptr [rax+rax+00h]
0x140019288  mov     edx, 1Eh
0x14001928d  mov     dword ptr [rsp+58h+var_38], edi
0x140019291  mov     r9, rax
0x140019294  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001929b  mov     rcx, rbx
0x14001929e  call    WPP_SF_qD
0x1400192a3  mov     eax, edi
0x1400192a5  add     rsp, 38h
0x1400192a9  pop     rdi
0x1400192aa  pop     rsi
0x1400192ab  pop     rbp
0x1400192ac  pop     rbx
0x1400192ad  retn
```
