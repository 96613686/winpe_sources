# MRxDAVCreate

- ea: `0x140012fa0`
- end: `0x1400130cd`
- name: `MRxDAVCreate`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140012fa0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140012fcc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140013008`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001309a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012fcc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140013008`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001309a`
- `rdbss!RxDisableLocalBuffering` at `0x140013075`
- `rdbss!RxDisableLocalBuffering` at `0x140013075`

## string_xrefs

- `0x140013030`: `MRxDAVCreate`

## pseudocode

```c
__int64 __fastcall MRxDAVCreate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned int v8; // esi
  __int64 v9; // rbx
  HANDLE v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 12, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qq(v6, 13, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v7, a1);
    }
  }
  v8 = UMRxAsyncEngOuterWrapper(a1, a2, a3, 0, MRxDAVCreateContinuation, (__int64)"MRxDAVCreate");
  if ( !v8 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 72) + 152LL) = 2032127;
    *(_DWORD *)(*(_QWORD *)(a1 + 72) + 156LL) = 0;
    RxDisableLocalBuffering(*(_QWORD *)(a1 + 56));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 14, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140012fa0  push    rbx
0x140012fa2  push    rbp
0x140012fa3  push    rsi
0x140012fa4  push    rdi
0x140012fa5  sub     rsp, 38h
0x140012fa9  mov     rdi, rcx
0x140012fac  mov     rbx, cs:WPP_GLOBAL_Control
0x140012fb3  lea     rbp, WPP_GLOBAL_Control
0x140012fba  cmp     rbx, rbp
0x140012fbd  jz      short loc_140013030
0x140012fbf  test    dword ptr [rbx+2Ch], 4000h
0x140012fc6  jz      short loc_140012FEF
0x140012fc8  mov     rbx, [rbx+18h]
0x140012fcc  call    cs:__imp_PsGetCurrentThreadId
0x140012fd3  nop     dword ptr [rax+rax+00h]
0x140012fd8  mov     edx, 0Ch
0x140012fdd  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012fe4  mov     r9, rax
0x140012fe7  mov     rcx, rbx
0x140012fea  call    WPP_SF_q
0x140012fef  mov     rbx, cs:WPP_GLOBAL_Control
0x140012ff6  cmp     rbx, rbp
0x140012ff9  jz      short loc_140013030
0x140012ffb  test    dword ptr [rbx+2Ch], 2000h
0x140013002  jz      short loc_140013030
0x140013004  mov     rbx, [rbx+18h]
0x140013008  call    cs:__imp_PsGetCurrentThreadId
0x14001300f  nop     dword ptr [rax+rax+00h]
0x140013014  mov     edx, 0Dh
0x140013019  mov     [rsp+58h+var_38], rdi
0x14001301e  mov     r9, rax
0x140013021  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140013028  mov     rcx, rbx
0x14001302b  call    WPP_SF_qq
0x140013030  lea     rax, aMrxdavcreate; "MRxDAVCreate"
0x140013037  xor     r9d, r9d
0x14001303a  mov     [rsp+58h+var_30], rax
0x14001303f  mov     rcx, rdi
0x140013042  lea     rax, MRxDAVCreateContinuation
0x140013049  mov     [rsp+58h+var_38], rax
0x14001304e  call    UMRxAsyncEngOuterWrapper
0x140013053  mov     esi, eax
0x140013055  test    eax, eax
0x140013057  jnz     short loc_140013081
0x140013059  mov     rcx, [rdi+48h]
0x14001305d  mov     dword ptr [rcx+98h], 1F01FFh
0x140013067  mov     rcx, [rdi+48h]
0x14001306b  mov     [rcx+9Ch], eax
0x140013071  mov     rcx, [rdi+38h]
0x140013075  call    cs:__imp_RxDisableLocalBuffering
0x14001307c  nop     dword ptr [rax+rax+00h]
0x140013081  mov     rbx, cs:WPP_GLOBAL_Control
0x140013088  cmp     rbx, rbp
0x14001308b  jz      short loc_1400130C1
0x14001308d  test    dword ptr [rbx+2Ch], 4000h
0x140013094  jz      short loc_1400130C1
0x140013096  mov     rbx, [rbx+18h]
0x14001309a  call    cs:__imp_PsGetCurrentThreadId
0x1400130a1  nop     dword ptr [rax+rax+00h]
0x1400130a6  mov     edx, 0Eh
0x1400130ab  mov     dword ptr [rsp+58h+var_38], esi
0x1400130af  mov     r9, rax
0x1400130b2  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400130b9  mov     rcx, rbx
0x1400130bc  call    WPP_SF_qD
0x1400130c1  mov     eax, esi
0x1400130c3  add     rsp, 38h
0x1400130c7  pop     rdi
0x1400130c8  pop     rsi
0x1400130c9  pop     rbp
0x1400130ca  pop     rbx
0x1400130cb  retn
```
