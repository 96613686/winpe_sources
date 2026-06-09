# NcaEvCollInsideOutsideInitialize

- ea: `0x180010430`
- end: `0x1800105f9`
- name: `NcaEvCollInsideOutsideInitialize`
- size: `457`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x18000b1e8`
- `0x180010430`
- `0x180010600`
- `0x180018ffc`
- `0x18001cc3e`

## string_xrefs

- `0x180010474`: `EvCollInsideOutside`
- `0x1800105b3`: `EvCollInsideOutside`

## pseudocode

```c
__int64 NcaEvCollInsideOutsideInitialize()
{
  PVOID v0; // rcx
  int v1; // eax
  unsigned int v2; // ebx
  int v3; // edi
  __int64 v4; // rcx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_771a672108da301c4352a042022c0f91_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      (__int64)v0,
      (const EVENT_DESCRIPTOR *)ModuleInitializeStart,
      L"EvCollInsideOutside");
  memset_0(&gNcaEvCollInOut, 0, 0x48u);
  v1 = NcaCriticalSectionCreate(&stru_180028FB0);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_771a672108da301c4352a042022c0f91_Traceguids,
        (unsigned int)v1);
      NcaEvCollInsideOutsideShutdown();
      goto LABEL_23;
    }
    goto LABEL_19;
  }
  v5 = NcaSrcLnkdTriggerRegisterWait(0, &stru_180028CF0, 0, NcaEvCollInsideOutsideCollect, 0, &gNcaEvCollInOut);
  v3 = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v7 = 12;
  }
  else
  {
    v5 = NcaSrcLnkdTriggerRegisterWait(1, &stru_180028D30, 0, NcaEvCollInsideOutsideCollect, 1, &qword_180028FA8);
    v3 = v5;
    if ( !v5 )
      goto LABEL_23;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_19:
      NcaEvCollInsideOutsideShutdown();
      if ( !v3 )
        goto LABEL_23;
      goto LABEL_20;
    }
    v7 = 13;
  }
  WPP_SF_d(v6[2], v7, WPP_771a672108da301c4352a042022c0f91_Traceguids, v5);
  NcaEvCollInsideOutsideShutdown();
LABEL_20:
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  else
    v2 = v3;
LABEL_23:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(
      v4,
      (const EVENT_DESCRIPTOR *)ModuleInitializeEnd,
      L"EvCollInsideOutside",
      (int)v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_771a672108da301c4352a042022c0f91_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180010430  push    rbx
0x180010432  push    rbp
0x180010433  push    rdi
0x180010434  push    r14
0x180010436  sub     rsp, 38h
0x18001043a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010441  lea     rbp, WPP_GLOBAL_Control
0x180010448  lea     r14, WPP_771a672108da301c4352a042022c0f91_Traceguids
0x18001044f  cmp     rcx, rbp
0x180010452  jz      short loc_18001046B
0x180010454  test    byte ptr [rcx+1Ch], 8
0x180010458  jz      short loc_18001046B
0x18001045a  mov     rcx, [rcx+10h]
0x18001045e  mov     edx, 0Ah
0x180010463  mov     r8, r14
0x180010466  call    WPP_SF_
0x18001046b  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180010472  jz      short loc_180010487
0x180010474  lea     r8, aEvcollinsideou; "EvCollInsideOutside"
0x18001047b  lea     rdx, ModuleInitializeStart
0x180010482  call    McTemplateU0z_EventWriteTransfer
0x180010487  xor     edx, edx; Val
0x180010489  lea     rdi, ?gNcaEvCollInOut@@3UNCA_EVCOLL_INOUT_COMPONENT_@@A; NCA_EVCOLL_INOUT_COMPONENT_ gNcaEvCollInOut
0x180010490  mov     rcx, rdi; void *
0x180010493  lea     r8d, [rdx+48h]; Size
0x180010497  call    memset_0
0x18001049c  lea     rcx, stru_180028FB0; lpCriticalSection
0x1800104a3  call    NcaCriticalSectionCreate
0x1800104a8  mov     ebx, eax
0x1800104aa  test    eax, eax
0x1800104ac  jns     short loc_1800104E6
0x1800104ae  xor     edi, edi
0x1800104b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104b7  cmp     rcx, rbp
0x1800104ba  jz      loc_18001058D
0x1800104c0  test    byte ptr [rcx+1Ch], 1
0x1800104c4  jz      loc_18001058D
0x1800104ca  mov     rcx, [rcx+10h]
0x1800104ce  lea     edx, [rdi+0Bh]
0x1800104d1  mov     r9d, eax
0x1800104d4  mov     r8, r14
0x1800104d7  call    WPP_SF_d
0x1800104dc  call    NcaEvCollInsideOutsideShutdown
0x1800104e1  jmp     loc_1800105A7
0x1800104e6  mov     [rsp+58h+var_30], rdi
0x1800104eb  lea     r9, ?NcaEvCollInsideOutsideCollect@@YAXPEAX000@Z; NcaEvCollInsideOutsideCollect(void *,void *,void *,void *)
0x1800104f2  xor     r8d, r8d
0x1800104f5  mov     [rsp+58h+var_38], 0
0x1800104fe  lea     rdx, stru_180028CF0
0x180010505  xor     ecx, ecx
0x180010507  call    NcaSrcLnkdTriggerRegisterWait
0x18001050c  mov     edi, eax
0x18001050e  test    eax, eax
0x180010510  jz      short loc_18001053F
0x180010512  mov     rcx, cs:WPP_GLOBAL_Control
0x180010519  cmp     rcx, rbp
0x18001051c  jz      short loc_18001058D
0x18001051e  test    byte ptr [rcx+1Ch], 1
0x180010522  jz      short loc_18001058D
0x180010524  mov     edx, 0Ch
0x180010529  mov     rcx, [rcx+10h]
0x18001052d  mov     r9d, eax
0x180010530  mov     r8, r14
0x180010533  call    WPP_SF_d
0x180010538  call    NcaEvCollInsideOutsideShutdown
0x18001053d  jmp     short loc_180010596
0x18001053f  xor     r8d, r8d
0x180010542  lea     rax, qword_180028FA8
0x180010549  mov     [rsp+58h+var_30], rax
0x18001054e  lea     r9, ?NcaEvCollInsideOutsideCollect@@YAXPEAX000@Z; NcaEvCollInsideOutsideCollect(void *,void *,void *,void *)
0x180010555  lea     rdx, stru_180028D30
0x18001055c  mov     [rsp+58h+var_38], 1
0x180010565  lea     ecx, [r8+1]
0x180010569  call    NcaSrcLnkdTriggerRegisterWait
0x18001056e  mov     edi, eax
0x180010570  test    eax, eax
0x180010572  jz      short loc_1800105A7
0x180010574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001057b  cmp     rcx, rbp
0x18001057e  jz      short loc_18001058D
0x180010580  test    byte ptr [rcx+1Ch], 1
0x180010584  jz      short loc_18001058D
0x180010586  mov     edx, 0Dh
0x18001058b  jmp     short loc_180010529
0x18001058d  call    NcaEvCollInsideOutsideShutdown
0x180010592  test    edi, edi
0x180010594  jz      short loc_1800105A7
0x180010596  test    edi, edi
0x180010598  jg      short loc_18001059E
0x18001059a  mov     ebx, edi
0x18001059c  jmp     short loc_1800105A7
0x18001059e  movzx   ebx, di
0x1800105a1  or      ebx, 80070000h
0x1800105a7  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800105ae  jz      short loc_1800105C6
0x1800105b0  movsxd  r9, ebx
0x1800105b3  lea     r8, aEvcollinsideou; "EvCollInsideOutside"
0x1800105ba  lea     rdx, ModuleInitializeEnd
0x1800105c1  call    McTemplateU0zx_EventWriteTransfer
0x1800105c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105cd  cmp     rcx, rbp
0x1800105d0  jz      short loc_1800105EC
0x1800105d2  test    byte ptr [rcx+1Ch], 8
0x1800105d6  jz      short loc_1800105EC
0x1800105d8  mov     rcx, [rcx+10h]
0x1800105dc  mov     edx, 0Fh
0x1800105e1  mov     r9d, ebx
0x1800105e4  mov     r8, r14
0x1800105e7  call    WPP_SF_d
0x1800105ec  mov     eax, ebx
0x1800105ee  add     rsp, 38h
0x1800105f2  pop     r14
0x1800105f4  pop     rdi
0x1800105f5  pop     rbp
0x1800105f6  pop     rbx
0x1800105f7  retn
```
