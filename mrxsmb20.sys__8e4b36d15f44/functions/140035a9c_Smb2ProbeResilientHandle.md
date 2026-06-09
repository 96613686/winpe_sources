# Smb2ProbeResilientHandle

- ea: `0x140035a9c`
- end: `0x140035c39`
- name: `Smb2ProbeResilientHandle`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140022e90`

## callees

- `0x140029840`
- `0x140035a18`
- `0x140035a9c`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140035b22`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140035b22`
- `rdbss!RxCreateRxContext` at `0x140035ad7`
- `rdbss!RxCreateRxContext` at `0x140035ad7`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140035c19`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140035c19`
- `mrxsmb!SmbCeInitiateExchange` at `0x140035bb0`
- `mrxsmb!SmbCeInitiateExchange` at `0x140035bb0`
- `mrxsmb!SmbCeInitializeExchange` at `0x140035b82`
- `mrxsmb!SmbCeInitializeExchange` at `0x140035b82`

## pseudocode

```c
void __fastcall Smb2ProbeResilientHandle(_DWORD *a1, struct _MRX_SRV_OPEN_ *a2)
{
  struct _MRX_FCB_ *Context2; // r14
  __int64 v5; // rdi
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v7; // rbx
  int v8; // r8d
  int v9; // eax
  PMRX_SRV_OPEN pRelevantSrvOpen; // rax
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  Context2 = (struct _MRX_FCB_ *)a2->Context2;
  v5 = *(_QWORD *)(*(_QWORD *)&a2->Flags + 296LL);
  RxContext = RxCreateRxContext(0, *((PRDBSS_DEVICE_OBJECT *)a2->ShadowContext->DispatchRoutine + 3), 0x80000000);
  v7 = RxContext;
  if ( RxContext )
  {
    LOBYTE(RxContext->RealDevice) = 27;
    RxContext->pFcb = Context2;
    RxContext->pRelevantSrvOpen = a2;
    RxContext->pFobx = 0;
    v9 = a1[33];
    if ( *(_DWORD *)(v5 + 32) != v9 )
    {
      *(_DWORD *)(v5 + 32) = v9;
      ++a1[30];
      --a1[31];
    }
    if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v5 + 24)) )
    {
      pRelevantSrvOpen = v7->pRelevantSrvOpen;
      v11 = 0;
      if ( (int)SmbCeInitializeExchange(
                  &v11,
                  v7,
                  0,
                  0,
                  0,
                  pRelevantSrvOpen->ShadowContext->DispatchRoutine,
                  1032,
                  &ValidateResilientHandleDispatch) < 0 )
      {
        CompleteResilientHandleReconnect(v7);
      }
      else
      {
        *(_QWORD *)(v11 + 1024) = v5;
        _InterlockedOr((volatile signed __int32 *)(v11 + 68), 0x1400u);
        SmbCeInitiateExchange(v11);
      }
      v7 = 0;
      v8 = 259;
    }
    else
    {
      v8 = -1073741528;
    }
  }
  else
  {
    v8 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids, a2, v8);
  }
  if ( v7 )
    RxDereferenceAndDeleteRxContext_Real(v7);
}

```

## disassembly

```asm
0x140035a9c  mov     [rsp+arg_0], rbx
0x140035aa1  mov     [rsp+arg_10], rbp
0x140035aa6  push    rsi
0x140035aa7  push    rdi
0x140035aa8  push    r14
0x140035aaa  sub     rsp, 40h
0x140035aae  mov     rax, [rdx+30h]
0x140035ab2  mov     rbp, rdx
0x140035ab5  mov     r14, [rdx+20h]
0x140035ab9  mov     rsi, rcx
0x140035abc  mov     r8d, 80000000h; InitialContextFlags
0x140035ac2  xor     ecx, ecx; Irp
0x140035ac4  mov     rdi, [rax+128h]
0x140035acb  mov     rax, [rdx+28h]
0x140035acf  mov     rdx, [rax+28h]
0x140035ad3  mov     rdx, [rdx+18h]; RxDeviceObject
0x140035ad7  call    cs:__imp_RxCreateRxContext
0x140035ade  nop     dword ptr [rax+rax+00h]
0x140035ae3  mov     rbx, rax
0x140035ae6  test    rax, rax
0x140035ae9  jnz     short loc_140035AF6
0x140035aeb  mov     r8d, 0C000009Ah
0x140035af1  jmp     loc_140035BD4
0x140035af6  mov     byte ptr [rax+20h], 1Bh
0x140035afa  mov     [rax+38h], r14
0x140035afe  mov     [rax+48h], rbp
0x140035b02  mov     qword ptr [rax+40h], 0
0x140035b0a  mov     eax, [rsi+84h]
0x140035b10  cmp     [rdi+20h], eax
0x140035b13  jz      short loc_140035B1E
0x140035b15  mov     [rdi+20h], eax
0x140035b18  inc     dword ptr [rsi+78h]
0x140035b1b  dec     dword ptr [rsi+7Ch]
0x140035b1e  lea     rcx, [rdi+18h]; RunRef
0x140035b22  call    cs:__imp_ExAcquireRundownProtection
0x140035b29  nop     dword ptr [rax+rax+00h]
0x140035b2e  test    al, al
0x140035b30  jnz     short loc_140035B3D
0x140035b32  mov     r8d, 0C0000128h
0x140035b38  jmp     loc_140035BD4
0x140035b3d  mov     rax, [rbx+48h]
0x140035b41  lea     rcx, ValidateResilientHandleDispatch
0x140035b48  mov     [rsp+58h+var_20], rcx
0x140035b4d  xor     r9d, r9d
0x140035b50  mov     [rsp+58h+arg_8], 0
0x140035b59  lea     rcx, [rsp+58h+arg_8]
0x140035b5e  mov     [rsp+58h+var_28], 408h
0x140035b66  xor     r8d, r8d
0x140035b69  mov     rax, [rax+28h]
0x140035b6d  mov     rdx, rbx
0x140035b70  mov     rax, [rax+28h]
0x140035b74  mov     [rsp+58h+var_30], rax
0x140035b79  mov     [rsp+58h+var_38], 0
0x140035b82  call    cs:__imp_SmbCeInitializeExchange
0x140035b89  nop     dword ptr [rax+rax+00h]
0x140035b8e  test    eax, eax
0x140035b90  js      short loc_140035BBE
0x140035b92  mov     rax, [rsp+58h+arg_8]
0x140035b97  mov     [rax+400h], rdi
0x140035b9e  mov     rax, [rsp+58h+arg_8]
0x140035ba3  lock or dword ptr [rax+44h], 1400h
0x140035bab  mov     rcx, [rsp+58h+arg_8]
0x140035bb0  call    cs:__imp_SmbCeInitiateExchange
0x140035bb7  nop     dword ptr [rax+rax+00h]
0x140035bbc  jmp     short loc_140035BCC
0x140035bbe  mov     r8d, eax
0x140035bc1  mov     rdx, rdi
0x140035bc4  mov     rcx, rbx; RxContext
0x140035bc7  call    CompleteResilientHandleReconnect
0x140035bcc  xor     ebx, ebx
0x140035bce  mov     r8d, 103h
0x140035bd4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140035bdb  lea     rax, WPP_GLOBAL_Control
0x140035be2  cmp     rcx, rax
0x140035be5  jz      short loc_140035C11
0x140035be7  mov     eax, [rcx+2Ch]
0x140035bea  test    al, 40h
0x140035bec  jz      short loc_140035C11
0x140035bee  cmp     byte ptr [rcx+29h], 4
0x140035bf2  jb      short loc_140035C11
0x140035bf4  mov     rcx, [rcx+18h]
0x140035bf8  mov     edx, 0Eh
0x140035bfd  mov     dword ptr [rsp+58h+var_38], r8d
0x140035c02  mov     r9, rbp
0x140035c05  lea     r8, WPP_826bdefea5f439a79d7b4a7e09ca5b98_Traceguids
0x140035c0c  call    WPP_SF_qD
0x140035c11  test    rbx, rbx
0x140035c14  jz      short loc_140035C25
0x140035c16  mov     rcx, rbx; RxContext
0x140035c19  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140035c20  nop     dword ptr [rax+rax+00h]
0x140035c25  mov     rbx, [rsp+58h+arg_0]
0x140035c2a  mov     rbp, [rsp+58h+arg_10]
0x140035c2f  add     rsp, 40h
0x140035c33  pop     r14
0x140035c35  pop     rdi
0x140035c36  pop     rsi
0x140035c37  retn
```
