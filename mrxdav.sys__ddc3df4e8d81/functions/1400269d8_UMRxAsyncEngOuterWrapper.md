# UMRxAsyncEngOuterWrapper

- ea: `0x1400269d8`
- end: `0x140026c09`
- name: `UMRxAsyncEngOuterWrapper`
- size: `561`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16, __int64 (__fastcall *)(__int64, __int64), __int64)`
- caller_count: `17`
- callee_count: `9`
- tags: ``

## callers

- `0x1400052a0`
- `0x14000f120`
- `0x140011440`
- `0x1400116f8`
- `0x140012780`
- `0x140012fa0`
- `0x1400189a0`
- `0x1400195b0`
- `0x14001af40`
- `0x14001c570`
- `0x14001cea0`
- `0x14001f6c0`
- `0x1400220c0`
- `0x140022a80`
- `0x140023530`
- `0x140023950`
- `0x140024030`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140006460`
- `0x140006640`
- `0x140006880`
- `0x14000f9d4`
- `0x1400269d8`
- `0x140027210`
- `0x140027658`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140026a18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026a54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026ab1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026b19`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026b6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026be4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026a18`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026a54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026ab1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026b19`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026b6e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026be4`

## pseudocode

```c
__int64 __fastcall UMRxAsyncEngOuterWrapper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 (__fastcall *a5)(__int64, __int64),
        __int64 a6)
{
  __int64 v8; // r14
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  unsigned int v12; // eax
  int v13; // edx
  int v14; // r8d
  __int64 AsyncEngineContext; // rax
  __int64 v16; // rbx
  unsigned int v17; // edi
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 (__fastcall *v20)(__int64, __int64); // rsi
  __int64 v21; // rbx
  HANDLE v22; // rax
  __int64 v23; // rbx
  HANDLE v24; // rax
  unsigned int v26; // eax
  __int64 v27; // rbx
  unsigned int v28; // eax
  int v29; // edx
  int v30; // r8d
  __int64 v31; // [rsp+80h] [rbp+18h] BYREF

  v31 = a3;
  v8 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 128, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qqs(v11, v13, v14, v12, a1, v8);
    }
  }
  AsyncEngineContext = UMRxCreateAsyncEngineContext(a1);
  v31 = AsyncEngineContext;
  v16 = AsyncEngineContext;
  if ( AsyncEngineContext )
  {
    v20 = a5;
    *(_QWORD *)(AsyncEngineContext + 216) = a5;
    v17 = MRxDAVFormatTheDAVContext(AsyncEngineContext, a4);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v22 = PsGetCurrentThreadId();
        WPP_SF_qD(v21, 131, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v22, v17);
      }
    }
    else
    {
      if ( !v20 )
        goto LABEL_16;
      v26 = v20(v16, a1);
      v17 = v26;
      if ( v26 )
      {
        if ( v26 == 259 )
          goto LABEL_17;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
        {
          v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v28 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qLs(v27, v29, v30, v28, v17, v8);
        }
        goto LABEL_16;
      }
    }
    if ( v17 == 259 )
      goto LABEL_17;
LABEL_16:
    UMRxFinalizeAsyncEngineContext(&v31);
    goto LABEL_17;
  }
  v17 = -1073741670;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
  {
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v19 = PsGetCurrentThreadId();
    WPP_SF_qD(v18, 130, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v19, -1073741670);
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v24 = PsGetCurrentThreadId();
    WPP_SF_qD(v23, 133, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v24, v17);
  }
  return v17;
}

```

## disassembly

```asm
0x1400269d8  mov     [rsp+arg_10], r8
0x1400269dd  push    rbx
0x1400269de  push    rbp
0x1400269df  push    rsi
0x1400269e0  push    rdi
0x1400269e1  push    r14
0x1400269e3  push    r15
0x1400269e5  sub     rsp, 38h
0x1400269e9  movzx   edi, r9w
0x1400269ed  mov     rbp, rcx
0x1400269f0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400269f7  lea     r15, WPP_GLOBAL_Control
0x1400269fe  mov     r14, [rsp+68h+arg_28]
0x140026a06  cmp     rbx, r15
0x140026a09  jz      short loc_140026A75
0x140026a0b  test    dword ptr [rbx+2Ch], 800h
0x140026a12  jz      short loc_140026A3B
0x140026a14  mov     rbx, [rbx+18h]
0x140026a18  call    cs:__imp_PsGetCurrentThreadId
0x140026a1f  nop     dword ptr [rax+rax+00h]
0x140026a24  mov     edx, 80h
0x140026a29  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026a30  mov     r9, rax
0x140026a33  mov     rcx, rbx
0x140026a36  call    WPP_SF_q
0x140026a3b  mov     rbx, cs:WPP_GLOBAL_Control
0x140026a42  cmp     rbx, r15
0x140026a45  jz      short loc_140026A75
0x140026a47  test    dword ptr [rbx+2Ch], 200h
0x140026a4e  jz      short loc_140026A75
0x140026a50  mov     rbx, [rbx+18h]
0x140026a54  call    cs:__imp_PsGetCurrentThreadId
0x140026a5b  nop     dword ptr [rax+rax+00h]
0x140026a60  mov     [rsp+68h+var_40], r14
0x140026a65  mov     rcx, rbx
0x140026a68  mov     r9, rax
0x140026a6b  mov     [rsp+68h+var_48], rbp
0x140026a70  call    WPP_SF_qqs
0x140026a75  mov     rcx, rbp
0x140026a78  call    UMRxCreateAsyncEngineContext
0x140026a7d  mov     [rsp+68h+arg_10], rax
0x140026a85  mov     rbx, rax
0x140026a88  test    rax, rax
0x140026a8b  jnz     short loc_140026ADE
0x140026a8d  mov     edi, 0C000009Ah
0x140026a92  mov     rbx, cs:WPP_GLOBAL_Control
0x140026a99  cmp     rbx, r15
0x140026a9c  jz      loc_140026B55
0x140026aa2  mov     eax, [rbx+2Ch]
0x140026aa5  test    al, al
0x140026aa7  jns     loc_140026B55
0x140026aad  mov     rbx, [rbx+18h]
0x140026ab1  call    cs:__imp_PsGetCurrentThreadId
0x140026ab8  nop     dword ptr [rax+rax+00h]
0x140026abd  mov     edx, 82h
0x140026ac2  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x140026aca  mov     r9, rax
0x140026acd  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026ad4  mov     rcx, rbx
0x140026ad7  call    WPP_SF_qD
0x140026adc  jmp     short loc_140026B55
0x140026ade  mov     rsi, [rsp+68h+arg_20]
0x140026ae6  movzx   edx, di
0x140026ae9  mov     rcx, rbx
0x140026aec  mov     [rax+0D8h], rsi
0x140026af3  call    MRxDAVFormatTheDAVContext
0x140026af8  mov     edi, eax
0x140026afa  test    eax, eax
0x140026afc  jz      loc_140026BA5
0x140026b02  mov     rbx, cs:WPP_GLOBAL_Control
0x140026b09  cmp     rbx, r15
0x140026b0c  jz      short loc_140026B40
0x140026b0e  mov     ecx, [rbx+2Ch]
0x140026b11  test    cl, cl
0x140026b13  jns     short loc_140026B40
0x140026b15  mov     rbx, [rbx+18h]
0x140026b19  call    cs:__imp_PsGetCurrentThreadId
0x140026b20  nop     dword ptr [rax+rax+00h]
0x140026b25  mov     edx, 83h
0x140026b2a  mov     dword ptr [rsp+68h+var_48], edi
0x140026b2e  mov     r9, rax
0x140026b31  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026b38  mov     rcx, rbx
0x140026b3b  call    WPP_SF_qD
0x140026b40  cmp     edi, 103h
0x140026b46  jz      short loc_140026B55
0x140026b48  lea     rcx, [rsp+68h+arg_10]
0x140026b50  call    UMRxFinalizeAsyncEngineContext
0x140026b55  mov     rbx, cs:WPP_GLOBAL_Control
0x140026b5c  cmp     rbx, r15
0x140026b5f  jz      short loc_140026B95
0x140026b61  test    dword ptr [rbx+2Ch], 800h
0x140026b68  jz      short loc_140026B95
0x140026b6a  mov     rbx, [rbx+18h]
0x140026b6e  call    cs:__imp_PsGetCurrentThreadId
0x140026b75  nop     dword ptr [rax+rax+00h]
0x140026b7a  mov     edx, 85h
0x140026b7f  mov     dword ptr [rsp+68h+var_48], edi
0x140026b83  mov     r9, rax
0x140026b86  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026b8d  mov     rcx, rbx
0x140026b90  call    WPP_SF_qD
0x140026b95  mov     eax, edi
0x140026b97  add     rsp, 38h
0x140026b9b  pop     r15
0x140026b9d  pop     r14
0x140026b9f  pop     rdi
0x140026ba0  pop     rsi
0x140026ba1  pop     rbp
0x140026ba2  pop     rbx
0x140026ba3  retn
0x140026ba5  test    rsi, rsi
0x140026ba8  jz      short loc_140026B48
0x140026baa  mov     rdx, rbp
0x140026bad  mov     rcx, rbx
0x140026bb0  mov     rax, rsi
0x140026bb3  call    _guard_dispatch_icall
0x140026bb8  mov     edi, eax
0x140026bba  test    eax, eax
0x140026bbc  jz      short loc_140026B40
0x140026bbe  cmp     eax, 103h
0x140026bc3  jz      short loc_140026B55
0x140026bc5  mov     rbx, cs:WPP_GLOBAL_Control
0x140026bcc  cmp     rbx, r15
0x140026bcf  jz      loc_140026B48
0x140026bd5  mov     eax, [rbx+2Ch]
0x140026bd8  test    al, al
0x140026bda  jns     loc_140026B48
0x140026be0  mov     rbx, [rbx+18h]
0x140026be4  call    cs:__imp_PsGetCurrentThreadId
0x140026beb  nop     dword ptr [rax+rax+00h]
0x140026bf0  mov     [rsp+68h+var_40], r14
0x140026bf5  mov     rcx, rbx
0x140026bf8  mov     r9, rax
0x140026bfb  mov     dword ptr [rsp+68h+var_48], edi
0x140026bff  call    WPP_SF_qLs
0x140026c04  jmp     loc_140026B48
```
