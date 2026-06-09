# MRxDAVQueryDirectoryContinuation

- ea: `0x14001fa70`
- end: `0x14001fbf8`
- name: `MRxDAVQueryDirectoryContinuation`
- size: `392`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001b64`
- `0x14001fa70`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001faa1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fadb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fb57`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fbc1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001faa1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fadb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fb57`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fbc1`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14001fb2a`
- `rdbss!RxSetMinirdrCancelRoutine` at `0x14001fb2a`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryDirectoryContinuation(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned int v8; // esi
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 23, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 24, WPP_609949de13fe38daba556366630c430b_Traceguids, v7, a1, a2);
    }
  }
  if ( (*(_DWORD *)(a2 + 120) & 0x1000) == 0 )
    goto LABEL_13;
  *(_WORD *)(a1 + 208) |= 1u;
  *(_DWORD *)(a1 + 56) = 1;
  v8 = RxSetMinirdrCancelRoutine((PRX_CONTEXT)a2, MRxDAVCancelRoutine);
  if ( !v8 )
  {
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 184LL) + 3LL) |= 1u;
LABEL_13:
    v8 = UMRxSubmitAsyncEngUserModeRequest(
           a1,
           (_QWORD *)a2,
           (__int64)MRxDAVFormatUserModeQueryDirectoryRequest,
           (__int64)MRxDAVPrecompleteUserModeQueryDirectoryRequest);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qq(v9, 25, WPP_609949de13fe38daba556366630c430b_Traceguids, v10, a1);
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v12 = PsGetCurrentThreadId();
    WPP_SF_qD(v11, 26, WPP_609949de13fe38daba556366630c430b_Traceguids, v12, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14001fa70  push    rbx
0x14001fa72  push    rbp
0x14001fa73  push    rsi
0x14001fa74  push    rdi
0x14001fa75  push    r14
0x14001fa77  push    r15
0x14001fa79  sub     rsp, 38h
0x14001fa7d  mov     rdi, rdx
0x14001fa80  mov     rbp, rcx
0x14001fa83  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fa8a  lea     r15, WPP_GLOBAL_Control
0x14001fa91  cmp     rbx, r15
0x14001fa94  jz      short loc_14001FB08
0x14001fa96  bt      dword ptr [rbx+2Ch], 0Dh
0x14001fa9b  jnb     short loc_14001FAC4
0x14001fa9d  mov     rbx, [rbx+18h]
0x14001faa1  call    cs:__imp_PsGetCurrentThreadId
0x14001faa8  nop     dword ptr [rax+rax+00h]
0x14001faad  mov     edx, 17h
0x14001fab2  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fab9  mov     r9, rax
0x14001fabc  mov     rcx, rbx
0x14001fabf  call    WPP_SF_q
0x14001fac4  mov     rbx, cs:WPP_GLOBAL_Control
0x14001facb  cmp     rbx, r15
0x14001face  jz      short loc_14001FB08
0x14001fad0  bt      dword ptr [rbx+2Ch], 0Dh
0x14001fad5  jnb     short loc_14001FB08
0x14001fad7  mov     rbx, [rbx+18h]
0x14001fadb  call    cs:__imp_PsGetCurrentThreadId
0x14001fae2  nop     dword ptr [rax+rax+00h]
0x14001fae7  mov     edx, 18h
0x14001faec  mov     [rsp+68h+var_40], rdi
0x14001faf1  mov     r9, rax
0x14001faf4  mov     [rsp+68h+var_48], rbp
0x14001faf9  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fb00  mov     rcx, rbx
0x14001fb03  call    WPP_SF_qqq
0x14001fb08  test    dword ptr [rdi+78h], 1000h
0x14001fb0f  jz      short loc_14001FB8F
0x14001fb11  mov     ebx, 1
0x14001fb16  lea     rdx, MRxDAVCancelRoutine; MRxCancelRoutine
0x14001fb1d  or      [rbp+0D0h], bx
0x14001fb24  mov     rcx, rdi; RxContext
0x14001fb27  mov     [rbp+38h], ebx
0x14001fb2a  call    cs:__imp_RxSetMinirdrCancelRoutine
0x14001fb31  nop     dword ptr [rax+rax+00h]
0x14001fb36  mov     esi, eax
0x14001fb38  test    eax, eax
0x14001fb3a  jz      short loc_14001FB81
0x14001fb3c  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fb43  cmp     rbx, r15
0x14001fb46  jz      loc_14001FBE8
0x14001fb4c  bt      dword ptr [rbx+2Ch], 0Dh
0x14001fb51  jnb     short loc_14001FBAA
0x14001fb53  mov     rbx, [rbx+18h]
0x14001fb57  call    cs:__imp_PsGetCurrentThreadId
0x14001fb5e  nop     dword ptr [rax+rax+00h]
0x14001fb63  mov     edx, 19h
0x14001fb68  mov     [rsp+68h+var_48], rbp
0x14001fb6d  mov     r9, rax
0x14001fb70  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fb77  mov     rcx, rbx
0x14001fb7a  call    WPP_SF_qq
0x14001fb7f  jmp     short loc_14001FBAA
0x14001fb81  mov     rax, [rdi+28h]
0x14001fb85  mov     rcx, [rax+0B8h]
0x14001fb8c  or      [rcx+3], bl
0x14001fb8f  lea     r9, MRxDAVPrecompleteUserModeQueryDirectoryRequest
0x14001fb96  mov     rdx, rdi
0x14001fb99  lea     r8, MRxDAVFormatUserModeQueryDirectoryRequest
0x14001fba0  mov     rcx, rbp
0x14001fba3  call    UMRxSubmitAsyncEngUserModeRequest
0x14001fba8  mov     esi, eax
0x14001fbaa  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fbb1  cmp     rbx, r15
0x14001fbb4  jz      short loc_14001FBE8
0x14001fbb6  bt      dword ptr [rbx+2Ch], 0Dh
0x14001fbbb  jnb     short loc_14001FBE8
0x14001fbbd  mov     rbx, [rbx+18h]
0x14001fbc1  call    cs:__imp_PsGetCurrentThreadId
0x14001fbc8  nop     dword ptr [rax+rax+00h]
0x14001fbcd  mov     edx, 1Ah
0x14001fbd2  mov     dword ptr [rsp+68h+var_48], esi
0x14001fbd6  mov     r9, rax
0x14001fbd9  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fbe0  mov     rcx, rbx
0x14001fbe3  call    WPP_SF_qD
0x14001fbe8  mov     eax, esi
0x14001fbea  add     rsp, 38h
0x14001fbee  pop     r15
0x14001fbf0  pop     r14
0x14001fbf2  pop     rdi
0x14001fbf3  pop     rsi
0x14001fbf4  pop     rbp
0x14001fbf5  pop     rbx
0x14001fbf6  retn
```
