# CscDisconnectOpens

- ea: `0x1400801c0`
- end: `0x1400802b3`
- name: `CscDisconnectOpens`
- size: `243`
- prototype: `__int64 __fastcall(__int64, struct _MRX_FCB_ *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400837e0`

## callees

- `0x1400190ec`
- `0x1400801c0`

## import_xrefs

- `rdbss!RxIterateOnFcbOpens` at `0x140080231`
- `rdbss!RxIterateOnFcbOpens` at `0x140080231`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140080242`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140080242`
- `rdbss!RxCreateRxContext` at `0x1400801ef`
- `rdbss!RxCreateRxContext` at `0x1400801ef`

## pseudocode

```c
__int64 __fastcall CscDisconnectOpens(__int64 a1, struct _MRX_FCB_ *a2, __int64 a3)
{
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v7; // rbx
  int v8; // r14d
  unsigned int v9; // edi

  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v7 = RxContext;
  if ( RxContext )
  {
    v8 = 0;
    RxContext->pFcb = a2;
    LOWORD(RxContext->RealDevice) = 0;
    RxContext->CurrentIrp = *(PIRP *)(a1 + 40);
    v9 = RxIterateOnFcbOpens(RxContext, a2, 0, a3, 0, 0);
    RxDereferenceAndDeleteRxContext_Real(v7);
  }
  else
  {
    v9 = -1073741670;
    v8 = 1421;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v9, v8);
  return v9;
}

```

## disassembly

```asm
0x1400801c0  mov     [rsp+arg_18], rdi
0x1400801c5  push    r14
0x1400801c7  sub     rsp, 30h
0x1400801cb  mov     [rsp+38h+arg_0], rbx
0x1400801d0  mov     rdi, rcx
0x1400801d3  mov     [rsp+38h+arg_8], rbp
0x1400801d8  mov     rbp, r8
0x1400801db  mov     [rsp+38h+arg_10], rsi
0x1400801e0  mov     r8d, 2; InitialContextFlags
0x1400801e6  mov     rsi, rdx
0x1400801e9  mov     rdx, [rcx+50h]; RxDeviceObject
0x1400801ed  xor     ecx, ecx; Irp
0x1400801ef  call    cs:__imp_RxCreateRxContext
0x1400801f6  nop     dword ptr [rax+rax+00h]
0x1400801fb  mov     rbx, rax
0x1400801fe  test    rax, rax
0x140080201  jz      loc_140080287
0x140080207  xor     r14d, r14d
0x14008020a  mov     [rax+38h], rsi
0x14008020e  mov     [rax+20h], r14w
0x140080213  mov     r9, rbp
0x140080216  mov     rax, [rdi+28h]
0x14008021a  xor     r8d, r8d
0x14008021d  mov     [rsp+38h+var_10], r14b
0x140080222  mov     rdx, rsi
0x140080225  mov     rcx, rbx
0x140080228  mov     [rbx+28h], rax
0x14008022c  mov     [rsp+38h+var_18], r14
0x140080231  call    cs:__imp_RxIterateOnFcbOpens
0x140080238  nop     dword ptr [rax+rax+00h]
0x14008023d  mov     rcx, rbx; RxContext
0x140080240  mov     edi, eax
0x140080242  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140080249  nop     dword ptr [rax+rax+00h]
0x14008024e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080255  lea     rax, WPP_GLOBAL_Control
0x14008025c  mov     rsi, [rsp+38h+arg_10]
0x140080261  mov     rbp, [rsp+38h+arg_8]
0x140080266  mov     rbx, [rsp+38h+arg_0]
0x14008026b  cmp     rcx, rax
0x14008026e  jz      short loc_140080278
0x140080270  mov     edx, [rcx+2Ch]
0x140080273  test    dl, 20h
0x140080276  jnz     short loc_140080294
0x140080278  mov     eax, edi
0x14008027a  mov     rdi, [rsp+38h+arg_18]
0x14008027f  add     rsp, 30h
0x140080283  pop     r14
0x140080285  retn
0x140080287  mov     edi, 0C000009Ah
0x14008028c  mov     r14d, 58Dh
0x140080292  jmp     short loc_14008024E
0x140080294  mov     rcx, [rcx+18h]
0x140080298  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14008029f  mov     edx, 17h
0x1400802a4  mov     dword ptr [rsp+38h+var_18], r14d
0x1400802a9  mov     r9d, edi
0x1400802ac  call    WPP_SF_Dd
0x1400802b1  jmp     short loc_140080278
```
