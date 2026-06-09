# CxPlatTlsSspiNotifyCallback

- ea: `0x140036b90`
- end: `0x140036cca`
- name: `CxPlatTlsSspiNotifyCallback`
- size: `314`
- prototype: `void __stdcall(SspiAsyncContext *Handle, PVOID CallbackData)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140035908`
- `0x1400368f0`
- `0x140036a90`
- `0x140036b90`
- `0x14003c980`
- `0x14003e928`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140036ca3`
- `ntoskrnl!KeSetEvent` at `0x140036ca3`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140036bef`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140036bef`

## string_xrefs

- `0x140036c3f`: `Completion for SspiAcquireCredentialsHandleAsyncW`

## pseudocode

```c
void __fastcall CxPlatTlsSspiNotifyCallback(SspiAsyncContext *Handle, struct _KEVENT *CallbackData)
{
  struct _LIST_ENTRY *Blink; // rdi
  LONG SignalState; // ebp
  struct _LIST_ENTRY *v5; // r14
  struct _LIST_ENTRY *Flink; // r15
  SECURITY_STATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // esi
  __int128 v11; // xmm1
  LIST_ENTRY WaitListHead; // xmm0
  int v13; // ebp
  __int64 v14; // r8
  _OWORD v15[3]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+60h] [rbp-28h]

  if ( CallbackData )
  {
    Blink = CallbackData[17].Header.WaitListHead.Blink;
    CallbackData[17].Header.WaitListHead.Blink = 0;
    SignalState = CallbackData->Header.SignalState;
    v5 = CallbackData[2].Header.WaitListHead.Blink;
    Flink = CallbackData[2].Header.WaitListHead.Flink;
    v7 = SspiGetAsyncCallStatus(Handle);
    CallbackData[5].Header.LockNV = v7;
    v10 = v7;
    v11 = *(_OWORD *)&CallbackData->Header.WaitListHead.Blink;
    v15[0] = *(_OWORD *)&CallbackData->Header.Lock;
    WaitListHead = CallbackData[1].Header.WaitListHead;
    v15[1] = v11;
    v16 = *(_QWORD *)&CallbackData[2].Header.Lock;
    v15[2] = WaitListHead;
    v13 = SignalState & 2;
    if ( v13 )
      CxPlatTlsFreeAchContext(CallbackData);
    if ( v10 )
    {
      if ( (Microsoft_QuicEnableBits & 4) != 0 )
        McTemplateU0qs_EtwWriteTransfer(v9, v8, v10, "Completion for SspiAcquireCredentialsHandleAsyncW");
      ((void (__fastcall *)(_OWORD *, struct _LIST_ENTRY *, _QWORD, _QWORD))v5)(v15, Flink, v10, 0);
      CxPlatTlsSecConfigDelete((struct _SecHandle *)Blink);
    }
    else
    {
      v14 = 0;
      if ( ((__int64)Blink[1].Flink & 0x40) != 0 )
        v14 = (unsigned int)CxPlatTlsSetClientCertPolicy((PCredHandle)Blink);
      ((void (__fastcall *)(_OWORD *, struct _LIST_ENTRY *, __int64, struct _LIST_ENTRY *))v5)(v15, Flink, v14, Blink);
    }
    if ( !v13 )
      KeSetEvent(CallbackData + 4, 0, 0);
  }
  else if ( (Microsoft_QuicEnableBits & 4) != 0 )
  {
    McTemplateU0s_EtwWriteTransfer(
      (__int64)Handle,
      (const EVENT_DESCRIPTOR *)QuicLibraryError,
      "NULL CallbackData to CxPlatTlsSspiNotifyCallback");
  }
}

```

## disassembly

```asm
0x140036b90  mov     [rsp+arg_0], rbx
0x140036b95  mov     [rsp+arg_8], rbp
0x140036b9a  mov     [rsp+arg_10], rsi
0x140036b9f  push    rdi
0x140036ba0  push    r14
0x140036ba2  push    r15
0x140036ba4  sub     rsp, 70h
0x140036ba8  mov     rbx, rdx
0x140036bab  test    rdx, rdx
0x140036bae  jnz     short loc_140036BD5
0x140036bb0  test    cs:Microsoft_QuicEnableBits, 4
0x140036bb7  jz      loc_140036CAF
0x140036bbd  lea     r8, aNullCallbackda; "NULL CallbackData to CxPlatTlsSspiNotif"...
0x140036bc4  lea     rdx, QuicLibraryError
0x140036bcb  call    McTemplateU0s_EtwWriteTransfer
0x140036bd0  jmp     loc_140036CAF
0x140036bd5  mov     rdi, [rdx+1A8h]
0x140036bdc  and     qword ptr [rdx+1A8h], 0
0x140036be4  mov     ebp, [rdx+4]
0x140036be7  mov     r14, [rdx+40h]
0x140036beb  mov     r15, [rdx+38h]
0x140036bef  call    cs:__imp_SspiGetAsyncCallStatus
0x140036bf6  nop     dword ptr [rax+rax+00h]
0x140036bfb  mov     [rbx+78h], eax
0x140036bfe  mov     esi, eax
0x140036c00  movups  xmm0, xmmword ptr [rbx]
0x140036c03  movups  xmm1, xmmword ptr [rbx+10h]
0x140036c07  movups  [rsp+88h+var_58], xmm0
0x140036c0c  movups  xmm0, xmmword ptr [rbx+20h]
0x140036c10  movups  [rsp+88h+var_48], xmm1
0x140036c15  movsd   xmm1, qword ptr [rbx+30h]
0x140036c1a  movsd   [rsp+88h+var_28], xmm1
0x140036c20  movups  [rsp+88h+var_38], xmm0
0x140036c25  and     ebp, 2
0x140036c28  jz      short loc_140036C32
0x140036c2a  mov     rcx, rbx; P
0x140036c2d  call    CxPlatTlsFreeAchContext
0x140036c32  test    esi, esi
0x140036c34  jz      short loc_140036C6E
0x140036c36  test    cs:Microsoft_QuicEnableBits, 4
0x140036c3d  jz      short loc_140036C4E
0x140036c3f  lea     r9, aCompletionForS; "Completion for SspiAcquireCredentialsHa"...
0x140036c46  mov     r8d, esi
0x140036c49  call    McTemplateU0qs_EtwWriteTransfer
0x140036c4e  xor     r9d, r9d
0x140036c51  lea     rcx, [rsp+88h+var_58]
0x140036c56  mov     r8d, esi
0x140036c59  mov     rdx, r15
0x140036c5c  mov     rax, r14
0x140036c5f  call    _guard_dispatch_icall
0x140036c64  mov     rcx, rdi; P
0x140036c67  call    CxPlatTlsSecConfigDelete
0x140036c6c  jmp     short loc_140036C96
0x140036c6e  mov     eax, [rdi+10h]
0x140036c71  xor     r8d, r8d
0x140036c74  test    al, 40h
0x140036c76  jz      short loc_140036C83
0x140036c78  mov     rcx, rdi; phCredential
0x140036c7b  call    CxPlatTlsSetClientCertPolicy
0x140036c80  mov     r8d, eax
0x140036c83  mov     r9, rdi
0x140036c86  lea     rcx, [rsp+88h+var_58]
0x140036c8b  mov     rdx, r15
0x140036c8e  mov     rax, r14
0x140036c91  call    _guard_dispatch_icall
0x140036c96  test    ebp, ebp
0x140036c98  jnz     short loc_140036CAF
0x140036c9a  lea     rcx, [rbx+60h]; Event
0x140036c9e  xor     r8d, r8d; Wait
0x140036ca1  xor     edx, edx; Increment
0x140036ca3  call    cs:__imp_KeSetEvent
0x140036caa  nop     dword ptr [rax+rax+00h]
0x140036caf  lea     r11, [rsp+88h+var_18]
0x140036cb4  mov     rbx, [r11+20h]
0x140036cb8  mov     rbp, [r11+28h]
0x140036cbc  mov     rsi, [r11+30h]
0x140036cc0  mov     rsp, r11
0x140036cc3  pop     r15
0x140036cc5  pop     r14
0x140036cc7  pop     rdi
0x140036cc8  retn
```
