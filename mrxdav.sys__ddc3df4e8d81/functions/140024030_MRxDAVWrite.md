# MRxDAVWrite

- ea: `0x140024030`
- end: `0x1400241a4`
- name: `MRxDAVWrite`
- size: `372`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140024030`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140024062`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002409e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140024104`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002416a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140024062`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002409e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140024104`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002416a`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400240c9`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400240c9`

## string_xrefs

- `0x140024129`: `MRxDAVWrite`

## pseudocode

```c
__int64 __fastcall MRxDAVWrite(PRX_CONTEXT RxContext)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 10, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 11, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids, v5, RxContext);
    }
  }
  if ( RxLowIoGetBufferAddress(RxContext) || !*((_DWORD *)&RxContext->9 + 42) )
  {
    v8 = UMRxAsyncEngOuterWrapper(
           (_DWORD)RxContext,
           v6,
           v7,
           10,
           (__int64)MRxDAVWriteContinuation,
           (__int64)"MRxDAVWrite");
  }
  else
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_q(v9, 12, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids, v10);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qD(v11, 13, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids, v12, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140024030  mov     [rsp+arg_0], rbx
0x140024035  mov     [rsp+arg_8], rsi
0x14002403a  push    rdi
0x14002403b  sub     rsp, 30h
0x14002403f  mov     rdi, rcx
0x140024042  mov     rbx, cs:WPP_GLOBAL_Control
0x140024049  lea     rsi, WPP_GLOBAL_Control
0x140024050  cmp     rbx, rsi
0x140024053  jz      short loc_1400240C6
0x140024055  test    dword ptr [rbx+2Ch], 4000h
0x14002405c  jz      short loc_140024085
0x14002405e  mov     rbx, [rbx+18h]
0x140024062  call    cs:__imp_PsGetCurrentThreadId
0x140024069  nop     dword ptr [rax+rax+00h]
0x14002406e  mov     edx, 0Ah
0x140024073  lea     r8, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids
0x14002407a  mov     r9, rax
0x14002407d  mov     rcx, rbx
0x140024080  call    WPP_SF_q
0x140024085  mov     rbx, cs:WPP_GLOBAL_Control
0x14002408c  cmp     rbx, rsi
0x14002408f  jz      short loc_1400240C6
0x140024091  test    dword ptr [rbx+2Ch], 2000h
0x140024098  jz      short loc_1400240C6
0x14002409a  mov     rbx, [rbx+18h]
0x14002409e  call    cs:__imp_PsGetCurrentThreadId
0x1400240a5  nop     dword ptr [rax+rax+00h]
0x1400240aa  mov     edx, 0Bh
0x1400240af  mov     [rsp+38h+var_18], rdi
0x1400240b4  mov     r9, rax
0x1400240b7  lea     r8, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids
0x1400240be  mov     rcx, rbx
0x1400240c1  call    WPP_SF_qq
0x1400240c6  mov     rcx, rdi; RxContext
0x1400240c9  call    cs:__imp_RxLowIoGetBufferAddress
0x1400240d0  nop     dword ptr [rax+rax+00h]
0x1400240d5  test    rax, rax
0x1400240d8  jnz     short loc_140024129
0x1400240da  cmp     [rdi+238h], eax
0x1400240e0  jz      short loc_140024129
0x1400240e2  mov     edi, 0C000009Ah
0x1400240e7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400240ee  cmp     rbx, rsi
0x1400240f1  jz      loc_140024191
0x1400240f7  test    dword ptr [rbx+2Ch], 2000h
0x1400240fe  jz      short loc_140024151
0x140024100  mov     rbx, [rbx+18h]
0x140024104  call    cs:__imp_PsGetCurrentThreadId
0x14002410b  nop     dword ptr [rax+rax+00h]
0x140024110  mov     edx, 0Ch
0x140024115  lea     r8, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids
0x14002411c  mov     r9, rax
0x14002411f  mov     rcx, rbx
0x140024122  call    WPP_SF_q
0x140024127  jmp     short loc_140024151
0x140024129  lea     rax, aMrxdavwrite; "MRxDAVWrite"
0x140024130  mov     r9d, 0Ah
0x140024136  mov     [rsp+38h+var_10], rax
0x14002413b  mov     rcx, rdi
0x14002413e  lea     rax, MRxDAVWriteContinuation
0x140024145  mov     [rsp+38h+var_18], rax
0x14002414a  call    UMRxAsyncEngOuterWrapper
0x14002414f  mov     edi, eax
0x140024151  mov     rbx, cs:WPP_GLOBAL_Control
0x140024158  cmp     rbx, rsi
0x14002415b  jz      short loc_140024191
0x14002415d  test    dword ptr [rbx+2Ch], 4000h
0x140024164  jz      short loc_140024191
0x140024166  mov     rbx, [rbx+18h]
0x14002416a  call    cs:__imp_PsGetCurrentThreadId
0x140024171  nop     dword ptr [rax+rax+00h]
0x140024176  mov     edx, 0Dh
0x14002417b  mov     dword ptr [rsp+38h+var_18], edi
0x14002417f  mov     r9, rax
0x140024182  lea     r8, WPP_c6c96f65293737b7d983954373aaa2c0_Traceguids
0x140024189  mov     rcx, rbx
0x14002418c  call    WPP_SF_qD
0x140024191  mov     rbx, [rsp+38h+arg_0]
0x140024196  mov     eax, edi
0x140024198  mov     rsi, [rsp+38h+arg_8]
0x14002419d  add     rsp, 30h
0x1400241a1  pop     rdi
0x1400241a2  retn
```
