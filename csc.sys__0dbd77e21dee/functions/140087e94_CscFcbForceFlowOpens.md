# CscFcbForceFlowOpens

- ea: `0x140087e94`
- end: `0x140087f5e`
- name: `CscFcbForceFlowOpens`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140062b70`
- `0x14008caec`

## callees

- `0x1400190ec`
- `0x140087e94`

## import_xrefs

- `rdbss!RxIterateOnFcbOpens` at `0x140087ef0`
- `rdbss!RxIterateOnFcbOpens` at `0x140087ef0`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140087f01`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140087f01`
- `rdbss!RxCreateRxContext` at `0x140087eaf`
- `rdbss!RxCreateRxContext` at `0x140087eaf`

## pseudocode

```c
__int64 __fastcall CscFcbForceFlowOpens(__int64 a1, struct _MRX_FCB_ *a2)
{
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v5; // rdi
  int v6; // esi
  unsigned int v7; // ebx

  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v5 = RxContext;
  if ( RxContext )
  {
    LOWORD(RxContext->RealDevice) = 0;
    v6 = 0;
    RxContext->pFcb = a2;
    RxContext->CurrentIrp = *(PIRP *)(a1 + 40);
    v7 = RxIterateOnFcbOpens(RxContext, a2, 0, CscForceFlowOpenPerFobxCallback, 0, 0);
    RxDereferenceAndDeleteRxContext_Real(v5);
  }
  else
  {
    v7 = -1073741670;
    v6 = 933;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v7, v6);
  return v7;
}

```

## disassembly

```asm
0x140087e94  push    rbx
0x140087e96  push    rbp
0x140087e97  push    rsi
0x140087e98  push    rdi
0x140087e99  sub     rsp, 38h
0x140087e9d  mov     rbp, rdx
0x140087ea0  mov     rbx, rcx
0x140087ea3  mov     rdx, [rcx+50h]; RxDeviceObject
0x140087ea7  mov     r8d, 2; InitialContextFlags
0x140087ead  xor     ecx, ecx; Irp
0x140087eaf  call    cs:__imp_RxCreateRxContext
0x140087eb6  nop     dword ptr [rax+rax+00h]
0x140087ebb  xor     ecx, ecx
0x140087ebd  mov     rdi, rax
0x140087ec0  test    rax, rax
0x140087ec3  jz      short loc_140087F34
0x140087ec5  mov     [rax+20h], cx
0x140087ec9  lea     r9, CscForceFlowOpenPerFobxCallback
0x140087ed0  mov     [rsp+58h+var_30], cl
0x140087ed4  mov     esi, ecx
0x140087ed6  mov     [rax+38h], rbp
0x140087eda  xor     r8d, r8d
0x140087edd  mov     rax, [rbx+28h]
0x140087ee1  mov     rdx, rbp
0x140087ee4  mov     [rsp+58h+var_38], rcx
0x140087ee9  mov     rcx, rdi
0x140087eec  mov     [rdi+28h], rax
0x140087ef0  call    cs:__imp_RxIterateOnFcbOpens
0x140087ef7  nop     dword ptr [rax+rax+00h]
0x140087efc  mov     rcx, rdi; RxContext
0x140087eff  mov     ebx, eax
0x140087f01  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140087f08  nop     dword ptr [rax+rax+00h]
0x140087f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140087f14  lea     rax, WPP_GLOBAL_Control
0x140087f1b  cmp     rcx, rax
0x140087f1e  jz      short loc_140087F28
0x140087f20  mov     edx, [rcx+2Ch]
0x140087f23  test    dl, 20h
0x140087f26  jnz     short loc_140087F40
0x140087f28  mov     eax, ebx
0x140087f2a  add     rsp, 38h
0x140087f2e  pop     rdi
0x140087f2f  pop     rsi
0x140087f30  pop     rbp
0x140087f31  pop     rbx
0x140087f32  retn
0x140087f34  mov     ebx, 0C000009Ah
0x140087f39  mov     esi, 3A5h
0x140087f3e  jmp     short loc_140087F0D
0x140087f40  mov     rcx, [rcx+18h]
0x140087f44  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140087f4b  mov     edx, 0Ch
0x140087f50  mov     dword ptr [rsp+58h+var_38], esi
0x140087f54  mov     r9d, ebx
0x140087f57  call    WPP_SF_Dd
0x140087f5c  jmp     short loc_140087F28
```
