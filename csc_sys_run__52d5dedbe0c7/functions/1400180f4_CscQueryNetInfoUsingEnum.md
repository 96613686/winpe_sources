# CscQueryNetInfoUsingEnum

- ea: `0x1400180f4`
- end: `0x140018259`
- name: `CscQueryNetInfoUsingEnum`
- size: `357`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140050dc0`
- `0x1400750a4`

## callees

- `0x1400180f4`
- `0x140018fd0`
- `0x14001b884`
- `0x14002f0f0`

## import_xrefs

- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001820b`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001820b`
- `rdbss!RxCreateRxContext` at `0x14001814b`
- `rdbss!RxCreateRxContext` at `0x14001814b`

## pseudocode

```c
__int64 __fastcall CscQueryNetInfoUsingEnum(__int64 a1, __int64 a2, RXVBO a3)
{
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v7; // rbx
  int v8; // edi
  int v9; // ebp

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      209,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      a1,
      a2);
  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v7 = RxContext;
  if ( RxContext )
  {
    RxContext->LowIoContext.ParamsFor.ReadWrite.ByteOffset = a3;
    *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 56;
    RxContext->pFcb = *(PMRX_FCB *)(a1 + 56);
    RxContext->pFobx = *(PMRX_FOBX *)(a1 + 64);
    RxContext->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a1 + 72);
    LOWORD(RxContext->RealDevice) = 268;
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 120LL) )
    {
      if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
      {
        v8 = -1073741536;
      }
      else
      {
        *(_OWORD *)&RxContext->MRxContext[2] = 0;
        *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
        RxContext->ResumeRoutine = 0;
        v8 = (*(__int64 (__fastcall **)(PRX_CONTEXT, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 120LL))(
               RxContext,
               a2);
        if ( v8 >= 0 )
        {
          v9 = 0;
LABEL_13:
          RxDereferenceAndDeleteRxContext_Real(v7);
          goto LABEL_14;
        }
      }
    }
    else
    {
      v8 = -1073741822;
    }
    v9 = 11122;
    goto LABEL_13;
  }
  v8 = -1073741670;
  v9 = 11086;
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 210, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, a1, v8, v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400180f4  push    rbx
0x1400180f6  push    rbp
0x1400180f7  push    rsi
0x1400180f8  push    rdi
0x1400180f9  push    r14
0x1400180fb  sub     rsp, 30h
0x1400180ff  mov     rbp, r8
0x140018102  mov     rdi, rdx
0x140018105  mov     rsi, rcx
0x140018108  mov     rcx, cs:WPP_GLOBAL_Control
0x14001810f  lea     r14, WPP_GLOBAL_Control
0x140018116  cmp     rcx, r14
0x140018119  jz      short loc_14001813F
0x14001811b  mov     eax, [rcx+2Ch]
0x14001811e  test    al, 20h
0x140018120  jz      short loc_14001813F
0x140018122  mov     rcx, [rcx+18h]
0x140018126  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14001812d  mov     edx, 0D1h
0x140018132  mov     [rsp+58h+var_38], rdi
0x140018137  mov     r9, rsi
0x14001813a  call    WPP_SF_qZ
0x14001813f  mov     rdx, [rsi+50h]; RxDeviceObject
0x140018143  mov     r8d, 2; InitialContextFlags
0x140018149  xor     ecx, ecx; Irp
0x14001814b  call    cs:__imp_RxCreateRxContext
0x140018152  nop     dword ptr [rax+rax+00h]
0x140018157  mov     rbx, rax
0x14001815a  test    rax, rax
0x14001815d  jnz     short loc_14001816E
0x14001815f  mov     edi, 0C000009Ah
0x140018164  mov     ebp, 2B4Eh
0x140018169  jmp     loc_140018217
0x14001816e  mov     [rax+1C8h], rbp
0x140018175  mov     dword ptr [rax+1D8h], 38h ; '8'
0x14001817f  mov     rax, [rsi+38h]
0x140018183  mov     [rbx+38h], rax
0x140018187  mov     rax, [rsi+40h]
0x14001818b  mov     [rbx+40h], rax
0x14001818f  mov     rax, [rsi+48h]
0x140018193  mov     [rbx+48h], rax
0x140018197  mov     word ptr [rbx+20h], 10Ch
0x14001819d  mov     rax, [rsi+50h]
0x1400181a1  mov     rcx, [rax+160h]
0x1400181a8  cmp     qword ptr [rcx+78h], 0
0x1400181ad  jnz     short loc_1400181B6
0x1400181af  mov     edi, 0C0000002h
0x1400181b4  jmp     short loc_140018203
0x1400181b6  mov     eax, [rbx+80h]
0x1400181bc  test    al, 2
0x1400181be  jnz     short loc_1400181FE
0x1400181c0  xor     eax, eax
0x1400181c2  xorps   xmm0, xmm0
0x1400181c5  movups  xmmword ptr [rbx+0D0h], xmm0
0x1400181cc  mov     rdx, rdi
0x1400181cf  movups  xmmword ptr [rbx+0E0h], xmm0
0x1400181d6  mov     [rbx+0F0h], rax
0x1400181dd  mov     rax, [rsi+50h]
0x1400181e1  mov     rcx, [rax+160h]
0x1400181e8  mov     rax, [rcx+78h]
0x1400181ec  mov     rcx, rbx
0x1400181ef  call    _guard_dispatch_icall
0x1400181f4  mov     edi, eax
0x1400181f6  test    eax, eax
0x1400181f8  js      short loc_140018203
0x1400181fa  xor     ebp, ebp
0x1400181fc  jmp     short loc_140018208
0x1400181fe  mov     edi, 0C0000120h
0x140018203  mov     ebp, 2B72h
0x140018208  mov     rcx, rbx; RxContext
0x14001820b  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140018212  nop     dword ptr [rax+rax+00h]
0x140018217  mov     rcx, cs:WPP_GLOBAL_Control
0x14001821e  cmp     rcx, r14
0x140018221  jz      short loc_14001824B
0x140018223  mov     edx, [rcx+2Ch]
0x140018226  test    dl, 20h
0x140018229  jz      short loc_14001824B
0x14001822b  mov     rcx, [rcx+18h]
0x14001822f  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140018236  mov     edx, 0D2h
0x14001823b  mov     [rsp+58h+var_30], ebp
0x14001823f  mov     r9, rsi
0x140018242  mov     dword ptr [rsp+58h+var_38], edi
0x140018246  call    WPP_SF_qDD
0x14001824b  mov     eax, edi
0x14001824d  add     rsp, 30h
0x140018251  pop     r14
0x140018253  pop     rdi
0x140018254  pop     rsi
0x140018255  pop     rbp
0x140018256  pop     rbx
0x140018257  retn
```
