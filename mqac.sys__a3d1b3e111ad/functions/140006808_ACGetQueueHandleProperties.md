# ACGetQueueHandleProperties

- ea: `0x140006808`
- end: `0x1400069c1`
- name: `ACGetQueueHandleProperties`
- size: `441`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140006808`
- `0x14000b5d8`
- `0x14000e834`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400068ed`
- `ntoskrnl!ProbeForWrite` at `0x140006942`
- `ntoskrnl!ProbeForWrite` at `0x1400068ed`
- `ntoskrnl!ProbeForWrite` at `0x140006942`

## pseudocode

```c
__int64 __fastcall ACGetQueueHandleProperties(__int64 a1, const struct CQueueBase *a2, bool *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  DriverSecurityContext *v9; // rdi
  volatile void *v10; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 110, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a2);
  }
  v6 = CQueueBase::Validate(a2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = *(DriverSecurityContext **)(*(_QWORD *)(a1 + 32) + 8LL);
    if ( v9 )
    {
      ProbeForWrite(a3, 0x24u, 1u);
      *a3 = (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 20LL) & 2) != 0;
      a3[1] = (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 20LL) & 4) != 0;
      *((_DWORD *)a3 + 1) = (*((_DWORD *)a2 + 14) >> 1) & 1;
      *((_DWORD *)a3 + 2) = (*((_DWORD *)a2 + 14) >> 2) & 1;
      v10 = *(volatile void **)(a3 + 12);
      ProbeForWrite(v10, 0x40u, 1u);
      DriverSecurityContext::CopyTo(
        v9,
        (struct CACSecurityContext *)v10,
        (struct SecurityContextRetrievalState *)(a3 + 20));
      return *((unsigned int *)a3 + 8);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 112, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
      }
      return 3221225506LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        111,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v6,
        a2);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x140006808  mov     [rsp+arg_0], rbx
0x14000680d  mov     [rsp+arg_10], rsi
0x140006812  mov     [rsp+arg_8], rdx
0x140006817  push    rdi
0x140006818  push    r14
0x14000681a  push    r15
0x14000681c  sub     rsp, 40h
0x140006820  mov     r14, r8
0x140006823  mov     rbx, rdx
0x140006826  mov     rsi, rcx
0x140006829  lea     r15, WPP_GLOBAL_Control
0x140006830  mov     rcx, cs:WPP_GLOBAL_Control
0x140006837  cmp     rcx, r15
0x14000683a  jz      short loc_14000685B
0x14000683c  mov     eax, [rcx+6Ch]
0x14000683f  test    al, 4
0x140006841  jz      short loc_14000685B
0x140006843  mov     edx, 6Eh ; 'n'
0x140006848  mov     r9, rbx
0x14000684b  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006852  mov     rcx, [rcx+58h]
0x140006856  call    WPP_SF_q
0x14000685b  mov     rcx, rbx; struct CQueueBase *
0x14000685e  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140006863  mov     edi, eax
0x140006865  test    eax, eax
0x140006867  jns     short loc_1400068A1
0x140006869  mov     rcx, cs:WPP_GLOBAL_Control
0x140006870  cmp     rcx, r15
0x140006873  jz      short loc_14000689A
0x140006875  mov     edx, [rcx+6Ch]
0x140006878  test    dl, 1
0x14000687b  jz      short loc_14000689A
0x14000687d  mov     edx, 6Fh ; 'o'
0x140006882  mov     [rsp+58h+var_38], rbx
0x140006887  mov     r9d, eax
0x14000688a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006891  mov     rcx, [rcx+58h]
0x140006895  call    WPP_SF_Dq
0x14000689a  mov     eax, edi
0x14000689c  jmp     loc_1400069AC
0x1400068a1  mov     rax, [rsi+20h]
0x1400068a5  mov     rdi, [rax+8]
0x1400068a9  test    rdi, rdi
0x1400068ac  jnz     short loc_1400068E1
0x1400068ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068b5  cmp     rcx, r15
0x1400068b8  jz      short loc_1400068D7
0x1400068ba  mov     eax, [rcx+6Ch]
0x1400068bd  test    al, 1
0x1400068bf  jz      short loc_1400068D7
0x1400068c1  lea     edx, [rdi+70h]
0x1400068c4  mov     r9, rsi
0x1400068c7  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400068ce  mov     rcx, [rcx+58h]
0x1400068d2  call    WPP_SF_q
0x1400068d7  mov     eax, 0C0000022h
0x1400068dc  jmp     loc_1400069AC
0x1400068e1  mov     edx, 24h ; '$'; Length
0x1400068e6  lea     r8d, [rdx-23h]; Alignment
0x1400068ea  mov     rcx, r14; Address
0x1400068ed  call    cs:__imp_ProbeForWrite
0x1400068f4  nop     dword ptr [rax+rax+00h]
0x1400068f9  mov     rax, [rsi+20h]
0x1400068fd  mov     ecx, [rax+14h]
0x140006900  shr     ecx, 1
0x140006902  and     cl, 1
0x140006905  mov     [r14], cl
0x140006908  mov     rax, [rsi+20h]
0x14000690c  mov     ecx, [rax+14h]
0x14000690f  shr     ecx, 2
0x140006912  and     cl, 1
0x140006915  mov     [r14+1], cl
0x140006919  mov     eax, [rbx+38h]
0x14000691c  shr     eax, 1
0x14000691e  and     eax, 1
0x140006921  mov     [r14+4], eax
0x140006925  mov     eax, [rbx+38h]
0x140006928  shr     eax, 2
0x14000692b  and     eax, 1
0x14000692e  mov     [r14+8], eax
0x140006932  mov     rbx, [r14+0Ch]
0x140006936  mov     edx, 40h ; '@'; Length
0x14000693b  lea     r8d, [rdx-3Fh]; Alignment
0x14000693f  mov     rcx, rbx; Address
0x140006942  call    cs:__imp_ProbeForWrite
0x140006949  nop     dword ptr [rax+rax+00h]
0x14000694e  lea     r8, [r14+14h]; struct SecurityContextRetrievalState *
0x140006952  mov     rdx, rbx; struct CACSecurityContext *
0x140006955  mov     rcx, rdi; this
0x140006958  call    ?CopyTo@DriverSecurityContext@@QEBAXPEAVCACSecurityContext@@PEAUSecurityContextRetrievalState@@@Z; DriverSecurityContext::CopyTo(CACSecurityContext *,SecurityContextRetrievalState *)
0x14000695d  mov     ebx, [r14+20h]
0x140006961  mov     [rsp+58h+var_28], ebx
0x140006965  jmp     short loc_1400069AA
0x140006967  mov     ebx, eax
0x140006969  mov     [rsp+58h+var_28], eax
0x14000696d  lea     rax, WPP_GLOBAL_Control
0x140006974  mov     rcx, cs:WPP_GLOBAL_Control
0x14000697b  cmp     rcx, rax
0x14000697e  jz      short loc_1400069AA
0x140006980  mov     eax, [rcx+6Ch]
0x140006983  test    al, 1
0x140006985  jz      short loc_1400069AA
0x140006987  mov     edx, 71h ; 'q'
0x14000698c  mov     r8, [rsp+58h+arg_8]
0x140006991  mov     [rsp+58h+var_38], r8
0x140006996  mov     r9d, ebx
0x140006999  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400069a0  mov     rcx, [rcx+58h]
0x1400069a4  call    WPP_SF_Dq
0x1400069a9  nop
0x1400069aa  mov     eax, ebx
0x1400069ac  mov     rbx, [rsp+58h+arg_0]
0x1400069b1  mov     rsi, [rsp+58h+arg_10]
0x1400069b6  add     rsp, 40h
0x1400069ba  pop     r15
0x1400069bc  pop     r14
0x1400069be  pop     rdi
0x1400069bf  retn
```
