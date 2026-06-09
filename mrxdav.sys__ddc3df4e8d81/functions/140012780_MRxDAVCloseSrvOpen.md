# MRxDAVCloseSrvOpen

- ea: `0x140012780`
- end: `0x140012891`
- name: `MRxDAVCloseSrvOpen`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140012780`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400127b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400127ee`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012857`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400127b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400127ee`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012857`

## string_xrefs

- `0x140012816`: `MRxDAVCloseSrvOpen`

## pseudocode

```c
__int64 __fastcall MRxDAVCloseSrvOpen(__int64 a1, __int64 a2, __int64 a3)
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
      WPP_SF_q(v4, 99, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qq(v6, 100, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v7, a1);
    }
  }
  v8 = UMRxAsyncEngOuterWrapper(a1, a2, a3, 7u, MRxDAVCloseSrvOpenContinuation, (__int64)"MRxDAVCloseSrvOpen");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 101, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140012780  mov     [rsp+arg_0], rbx
0x140012785  mov     [rsp+arg_8], rsi
0x14001278a  push    rdi
0x14001278b  sub     rsp, 30h
0x14001278f  mov     rdi, rcx
0x140012792  mov     rbx, cs:WPP_GLOBAL_Control
0x140012799  lea     rsi, WPP_GLOBAL_Control
0x1400127a0  cmp     rbx, rsi
0x1400127a3  jz      short loc_140012816
0x1400127a5  test    dword ptr [rbx+2Ch], 4000h
0x1400127ac  jz      short loc_1400127D5
0x1400127ae  mov     rbx, [rbx+18h]
0x1400127b2  call    cs:__imp_PsGetCurrentThreadId
0x1400127b9  nop     dword ptr [rax+rax+00h]
0x1400127be  mov     edx, 63h ; 'c'
0x1400127c3  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400127ca  mov     r9, rax
0x1400127cd  mov     rcx, rbx
0x1400127d0  call    WPP_SF_q
0x1400127d5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400127dc  cmp     rbx, rsi
0x1400127df  jz      short loc_140012816
0x1400127e1  test    dword ptr [rbx+2Ch], 2000h
0x1400127e8  jz      short loc_140012816
0x1400127ea  mov     rbx, [rbx+18h]
0x1400127ee  call    cs:__imp_PsGetCurrentThreadId
0x1400127f5  nop     dword ptr [rax+rax+00h]
0x1400127fa  mov     edx, 64h ; 'd'
0x1400127ff  mov     [rsp+38h+var_18], rdi
0x140012804  mov     r9, rax
0x140012807  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14001280e  mov     rcx, rbx
0x140012811  call    WPP_SF_qq
0x140012816  lea     rax, aMrxdavclosesrv; "MRxDAVCloseSrvOpen"
0x14001281d  mov     r9d, 7
0x140012823  mov     [rsp+38h+var_10], rax
0x140012828  mov     rcx, rdi
0x14001282b  lea     rax, MRxDAVCloseSrvOpenContinuation
0x140012832  mov     [rsp+38h+var_18], rax
0x140012837  call    UMRxAsyncEngOuterWrapper
0x14001283c  mov     edi, eax
0x14001283e  mov     rbx, cs:WPP_GLOBAL_Control
0x140012845  cmp     rbx, rsi
0x140012848  jz      short loc_14001287E
0x14001284a  test    dword ptr [rbx+2Ch], 4000h
0x140012851  jz      short loc_14001287E
0x140012853  mov     rbx, [rbx+18h]
0x140012857  call    cs:__imp_PsGetCurrentThreadId
0x14001285e  nop     dword ptr [rax+rax+00h]
0x140012863  mov     edx, 65h ; 'e'
0x140012868  mov     dword ptr [rsp+38h+var_18], edi
0x14001286c  mov     r9, rax
0x14001286f  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012876  mov     rcx, rbx
0x140012879  call    WPP_SF_qD
0x14001287e  mov     rbx, [rsp+38h+arg_0]
0x140012883  mov     eax, edi
0x140012885  mov     rsi, [rsp+38h+arg_8]
0x14001288a  add     rsp, 30h
0x14001288e  pop     rdi
0x14001288f  retn
```
