# MRxDAVFinalizeSrvCall

- ea: `0x14001af40`
- end: `0x14001b244`
- name: `MRxDAVFinalizeSrvCall`
- size: `772`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001838`
- `0x140002ac4`
- `0x14001af40`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001af84`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001afbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001afff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b046`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b0c2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b12c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b1a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b209`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001af84`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001afbc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001afff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b046`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b0c2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b12c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b1a6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001b209`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b07d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b07d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b1e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001b08f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001b08f`
- `rdbss!RxCreateRxContext` at `0x14001b0f2`
- `rdbss!RxCreateRxContext` at `0x14001b0f2`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001b1d0`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001b1d0`

## pseudocode

```c
__int64 __fastcall MRxDAVFinalizeSrvCall(__int64 a1, unsigned __int8 a2)
{
  struct _RDBSS_DEVICE_OBJECT *v2; // r14
  int v4; // ebp
  __int64 v5; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v7; // rdi
  HANDLE v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rbx
  HANDLE v14; // rax
  unsigned int v16; // edi
  __int64 v17; // rbx
  HANDLE v18; // rax
  PRX_CONTEXT RxContext; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  struct _RX_CONTEXT *v22; // rbp
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // rbx
  HANDLE v28; // rax

  v2 = *(struct _RDBSS_DEVICE_OBJECT **)(a1 + 48);
  v4 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v5, 48, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v8 = PsGetCurrentThreadId();
        WPP_SF_qqD(v7, 49, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v8, a1, v4);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
      {
        v9 = *(_QWORD *)(a1 + 64);
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v11 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZ(v10, 50, (unsigned int)WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v11, v9);
      }
    }
  }
  v12 = *(_QWORD *)(a1 + 32);
  if ( v12 )
  {
    if ( *(_WORD *)(v12 + 26) )
    {
      ExFreePoolWithTag(*(PVOID *)(v12 + 32), 0);
      RtlInitUnicodeString((PUNICODE_STRING)(v12 + 24), 0);
    }
    if ( *(_DWORD *)v12 )
    {
      RxContext = RxCreateRxContext(0, v2, 0);
      v22 = RxContext;
      if ( RxContext )
      {
        RxContext->MRxContext[3] = (PVOID)a1;
        v16 = UMRxAsyncEngOuterWrapper(
                (__int64)RxContext,
                v20,
                v21,
                5u,
                (__int64 (__fastcall *)(__int64, __int64))MRxDAVFinalizeSrvCallContinuation,
                (__int64)"MRxDAVFinalizeSrvCall");
        if ( v16
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v26 = PsGetCurrentThreadId();
          WPP_SF_qD(v25, 54, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v26, v16);
        }
        RxDereferenceAndDeleteRxContext_Real(v22);
      }
      else
      {
        v16 = -1073741670;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v24 = PsGetCurrentThreadId();
          WPP_SF_qD(v23, 53, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v24, -1073741670);
        }
      }
    }
    else
    {
      v16 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v18 = PsGetCurrentThreadId();
        WPP_SF_q(v17, 52, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v18);
      }
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 32), 0);
    *(_QWORD *)(a1 + 32) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v28 = PsGetCurrentThreadId();
      WPP_SF_qD(v27, 55, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v28, v16);
    }
    return v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v14 = PsGetCurrentThreadId();
        WPP_SF_q(v13, 51, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v14);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14001af40  push    rbx
0x14001af42  push    rbp
0x14001af43  push    rsi
0x14001af44  push    rdi
0x14001af45  push    r12
0x14001af47  push    r13
0x14001af49  push    r14
0x14001af4b  push    r15
0x14001af4d  sub     rsp, 38h
0x14001af51  mov     r14, [rcx+30h]
0x14001af55  mov     rsi, rcx
0x14001af58  movzx   ebp, dl
0x14001af5b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001af62  lea     r15, WPP_GLOBAL_Control
0x14001af69  lea     r12, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001af70  cmp     rbx, r15
0x14001af73  jz      loc_14001B023
0x14001af79  bt      dword ptr [rbx+2Ch], 0Eh
0x14001af7e  jnb     short loc_14001AFA3
0x14001af80  mov     rbx, [rbx+18h]
0x14001af84  call    cs:__imp_PsGetCurrentThreadId
0x14001af8b  nop     dword ptr [rax+rax+00h]
0x14001af90  mov     edx, 30h ; '0'
0x14001af95  mov     r8, r12
0x14001af98  mov     r9, rax
0x14001af9b  mov     rcx, rbx
0x14001af9e  call    WPP_SF_q
0x14001afa3  mov     rdi, cs:WPP_GLOBAL_Control
0x14001afaa  cmp     rdi, r15
0x14001afad  jz      short loc_14001B023
0x14001afaf  test    dword ptr [rdi+2Ch], 2000h
0x14001afb6  jz      short loc_14001AFE4
0x14001afb8  mov     rdi, [rdi+18h]
0x14001afbc  call    cs:__imp_PsGetCurrentThreadId
0x14001afc3  nop     dword ptr [rax+rax+00h]
0x14001afc8  mov     edx, 31h ; '1'
0x14001afcd  mov     dword ptr [rsp+78h+var_50], ebp
0x14001afd1  mov     r9, rax
0x14001afd4  mov     [rsp+78h+var_58], rsi
0x14001afd9  mov     r8, r12
0x14001afdc  mov     rcx, rdi
0x14001afdf  call    WPP_SF_qqD
0x14001afe4  mov     rdi, cs:WPP_GLOBAL_Control
0x14001afeb  cmp     rdi, r15
0x14001afee  jz      short loc_14001B023
0x14001aff0  bt      dword ptr [rdi+2Ch], 0Eh
0x14001aff5  jnb     short loc_14001B023
0x14001aff7  mov     rbx, [rsi+40h]
0x14001affb  mov     rdi, [rdi+18h]
0x14001afff  call    cs:__imp_PsGetCurrentThreadId
0x14001b006  nop     dword ptr [rax+rax+00h]
0x14001b00b  mov     edx, 32h ; '2'
0x14001b010  mov     [rsp+78h+var_58], rbx
0x14001b015  mov     r9, rax
0x14001b018  mov     r8, r12
0x14001b01b  mov     rcx, rdi
0x14001b01e  call    WPP_SF_qZ
0x14001b023  mov     rbx, [rsi+20h]
0x14001b027  xor     r12d, r12d
0x14001b02a  test    rbx, rbx
0x14001b02d  jnz     short loc_14001B070
0x14001b02f  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b036  cmp     rbx, r15
0x14001b039  jz      short loc_14001B069
0x14001b03b  bt      dword ptr [rbx+2Ch], 0Eh
0x14001b040  jnb     short loc_14001B069
0x14001b042  mov     rbx, [rbx+18h]
0x14001b046  call    cs:__imp_PsGetCurrentThreadId
0x14001b04d  nop     dword ptr [rax+rax+00h]
0x14001b052  lea     edx, [r12+33h]
0x14001b057  mov     rcx, rbx
0x14001b05a  mov     r9, rax
0x14001b05d  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b064  call    WPP_SF_q
0x14001b069  xor     eax, eax
0x14001b06b  jmp     loc_14001B232
0x14001b070  cmp     [rbx+1Ah], r12w
0x14001b075  jz      short loc_14001B09B
0x14001b077  mov     rcx, [rbx+20h]; P
0x14001b07b  xor     edx, edx; Tag
0x14001b07d  call    cs:__imp_ExFreePoolWithTag
0x14001b084  nop     dword ptr [rax+rax+00h]
0x14001b089  lea     rcx, [rbx+18h]; DestinationString
0x14001b08d  xor     edx, edx; SourceString
0x14001b08f  call    cs:__imp_RtlInitUnicodeString
0x14001b096  nop     dword ptr [rax+rax+00h]
0x14001b09b  cmp     [rbx], r12d
0x14001b09e  jnz     short loc_14001B0EA
0x14001b0a0  mov     edi, r12d
0x14001b0a3  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b0aa  cmp     rbx, r15
0x14001b0ad  jz      loc_14001B1DC
0x14001b0b3  bt      dword ptr [rbx+2Ch], 0Eh
0x14001b0b8  jnb     loc_14001B1DC
0x14001b0be  mov     rbx, [rbx+18h]
0x14001b0c2  call    cs:__imp_PsGetCurrentThreadId
0x14001b0c9  nop     dword ptr [rax+rax+00h]
0x14001b0ce  mov     edx, 34h ; '4'
0x14001b0d3  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b0da  mov     r9, rax
0x14001b0dd  mov     rcx, rbx
0x14001b0e0  call    WPP_SF_q
0x14001b0e5  jmp     loc_14001B1DC
0x14001b0ea  xor     r8d, r8d; InitialContextFlags
0x14001b0ed  mov     rdx, r14; RxDeviceObject
0x14001b0f0  xor     ecx, ecx; Irp
0x14001b0f2  call    cs:__imp_RxCreateRxContext
0x14001b0f9  nop     dword ptr [rax+rax+00h]
0x14001b0fe  mov     rbp, rax
0x14001b101  test    rax, rax
0x14001b104  jnz     short loc_14001B15A
0x14001b106  mov     edi, 0C000009Ah
0x14001b10b  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b112  cmp     rbx, r15
0x14001b115  jz      loc_14001B1DC
0x14001b11b  test    dword ptr [rbx+2Ch], 2000h
0x14001b122  jz      loc_14001B1DC
0x14001b128  mov     rbx, [rbx+18h]
0x14001b12c  call    cs:__imp_PsGetCurrentThreadId
0x14001b133  nop     dword ptr [rax+rax+00h]
0x14001b138  lea     edx, [rbp+35h]
0x14001b13b  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x14001b143  mov     r9, rax
0x14001b146  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b14d  mov     rcx, rbx
0x14001b150  call    WPP_SF_qD
0x14001b155  jmp     loc_14001B1DC
0x14001b15a  mov     [rax+0D8h], rsi
0x14001b161  mov     r9d, 5
0x14001b167  lea     rax, aMrxdavfinalize; "MRxDAVFinalizeSrvCall"
0x14001b16e  mov     rcx, rbp
0x14001b171  mov     [rsp+78h+var_50], rax
0x14001b176  lea     rax, MRxDAVFinalizeSrvCallContinuation
0x14001b17d  mov     [rsp+78h+var_58], rax
0x14001b182  call    UMRxAsyncEngOuterWrapper
0x14001b187  mov     edi, eax
0x14001b189  test    eax, eax
0x14001b18b  jz      short loc_14001B1CD
0x14001b18d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b194  cmp     rbx, r15
0x14001b197  jz      short loc_14001B1CD
0x14001b199  test    dword ptr [rbx+2Ch], 2000h
0x14001b1a0  jz      short loc_14001B1CD
0x14001b1a2  mov     rbx, [rbx+18h]
0x14001b1a6  call    cs:__imp_PsGetCurrentThreadId
0x14001b1ad  nop     dword ptr [rax+rax+00h]
0x14001b1b2  mov     edx, 36h ; '6'
0x14001b1b7  mov     dword ptr [rsp+78h+var_58], edi
0x14001b1bb  mov     r9, rax
0x14001b1be  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b1c5  mov     rcx, rbx
0x14001b1c8  call    WPP_SF_qD
0x14001b1cd  mov     rcx, rbp; RxContext
0x14001b1d0  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14001b1d7  nop     dword ptr [rax+rax+00h]
0x14001b1dc  mov     rcx, [rsi+20h]; P
0x14001b1e0  xor     edx, edx; Tag
0x14001b1e2  call    cs:__imp_ExFreePoolWithTag
0x14001b1e9  nop     dword ptr [rax+rax+00h]
0x14001b1ee  mov     [rsi+20h], r12
0x14001b1f2  mov     rbx, cs:WPP_GLOBAL_Control
0x14001b1f9  cmp     rbx, r15
0x14001b1fc  jz      short loc_14001B230
0x14001b1fe  bt      dword ptr [rbx+2Ch], 0Eh
0x14001b203  jnb     short loc_14001B230
0x14001b205  mov     rbx, [rbx+18h]
0x14001b209  call    cs:__imp_PsGetCurrentThreadId
0x14001b210  nop     dword ptr [rax+rax+00h]
0x14001b215  mov     edx, 37h ; '7'
0x14001b21a  mov     dword ptr [rsp+78h+var_58], edi
0x14001b21e  mov     r9, rax
0x14001b221  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001b228  mov     rcx, rbx
0x14001b22b  call    WPP_SF_qD
0x14001b230  mov     eax, edi
0x14001b232  add     rsp, 38h
0x14001b236  pop     r15
0x14001b238  pop     r14
0x14001b23a  pop     r13
0x14001b23c  pop     r12
0x14001b23e  pop     rdi
0x14001b23f  pop     rsi
0x14001b240  pop     rbp
0x14001b241  pop     rbx
0x14001b242  retn
```
