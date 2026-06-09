# HsmiRecallAllocatePopulationContext

- ea: `0x140044110`
- end: `0x1400443b5`
- name: `HsmiRecallAllocatePopulationContext`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140003cf0`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x140017e30`
- `0x140017f74`
- `0x14001e280`
- `0x14001e580`
- `0x140044110`
- `0x14004441c`
- `0x140058cbc`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14004435f`
- `ntoskrnl!ObfReferenceObject` at `0x14004435f`
- `ntoskrnl!ExAllocatePool2` at `0x140044281`
- `ntoskrnl!ExAllocatePool2` at `0x140044281`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400441c8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400441c8`
- `FLTMGR!FltReferenceContext` at `0x140044341`
- `FLTMGR!FltReferenceContext` at `0x140044350`
- `FLTMGR!FltReferenceContext` at `0x140044341`
- `FLTMGR!FltReferenceContext` at `0x140044350`

## pseudocode

```c
__int64 __fastcall HsmiRecallAllocatePopulationContext(
        __int64 a1,
        void *a2,
        __int64 a3,
        void *a4,
        struct _FLT_CALLBACK_DATA *CallbackData,
        const void **a6,
        _QWORD *a7)
{
  __int64 v10; // rbx
  __int64 v11; // rdi
  _DWORD *v12; // rax
  _DWORD *v13; // rsi
  __int64 StreamSize; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ecx
  __int64 Pool2; // rax
  __int64 v19; // rbx
  __int64 v20; // r8
  __int64 v23; // [rsp+A0h] [rbp+18h]

  v10 = *(_QWORD *)(*(_QWORD *)(a3 + 16) + 32LL);
  v23 = v10;
  v11 = (unsigned int)HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a3, CallbackData);
  HsmDbgBreakOnStatus(v11);
  if ( (int)v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qLqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_GLOBAL_Control,
        a3,
        *(_DWORD *)(a3 + 28),
        a4,
        v10,
        CallbackData,
        v11);
    }
    return (unsigned int)v11;
  }
  v12 = ExAllocateFromPagedLookasideList(&stru_1400293C0);
  v13 = v12;
  if ( !v12 )
  {
    LODWORD(v11) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a3);
      WPP_SF_qiqqLid(*(_QWORD *)(v15 + 24), v15, v16, CallbackData, v10, a2, a3, *(_DWORD *)(a3 + 28), StreamSize);
    }
LABEL_16:
    HsmpReleaseSyncOpRundownProtection((PFLT_CONTEXT)a3);
    if ( v13 )
      HsmiRecallFreePopulationContext(v13);
    return (unsigned int)v11;
  }
  memset(v12 + 1, 0, 0x54u);
  *v13 = 1666347848;
  v17 = *((unsigned __int16 *)a6 + 1);
  *((_WORD *)v13 + 17) = v17;
  *((_WORD *)v13 + 16) = 0;
  Pool2 = ExAllocatePool2(256, v17, 1934979912);
  *((_QWORD *)v13 + 5) = Pool2;
  v19 = Pool2;
  LODWORD(v11) = Pool2 == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus((unsigned int)v11);
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qLqiqd(WPP_GLOBAL_Control->AttachedDevice, 23, v20, a3, *(_DWORD *)(a3 + 28), a4, v23, CallbackData, v11);
    }
    goto LABEL_16;
  }
  memmove(*((void **)v13 + 5), a6[1], *(unsigned __int16 *)a6);
  *((_WORD *)v13 + 16) = *(_WORD *)a6;
  if ( a2 )
    FltReferenceContext(a2);
  FltReferenceContext((PFLT_CONTEXT)a3);
  ObfReferenceObject(a4);
  *((_QWORD *)v13 + 8) = a1;
  *((_QWORD *)v13 + 1) = 1;
  *((_QWORD *)v13 + 2) = a4;
  *((_QWORD *)v13 + 3) = CallbackData;
  *a7 = v13;
  *((_QWORD *)v13 + 6) = a2;
  *((_QWORD *)v13 + 7) = a3;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140044110  mov     [rsp+arg_8], rbx
0x140044115  mov     [rsp+arg_0], rcx
0x14004411a  push    rbp
0x14004411b  push    rsi
0x14004411c  push    rdi
0x14004411d  push    r12
0x14004411f  push    r13
0x140044121  push    r14
0x140044123  push    r15
0x140044125  sub     rsp, 50h
0x140044129  mov     rax, [r8+10h]
0x14004412d  mov     r15, rdx
0x140044130  mov     r14, [rsp+88h+CallbackData]
0x140044138  mov     rcx, r8; Context
0x14004413b  mov     rdx, r14; CallbackData
0x14004413e  mov     r12, r9
0x140044141  mov     rbp, r8
0x140044144  mov     rbx, [rax+20h]
0x140044148  mov     [rsp+88h+arg_10], rbx
0x140044150  call    HsmpAcquireSyncOpRundownProtection
0x140044155  mov     ecx, eax
0x140044157  mov     edi, eax
0x140044159  call    HsmDbgBreakOnStatus
0x14004415e  test    edi, edi
0x140044160  jns     short loc_1400441C1
0x140044162  mov     r8, cs:WPP_GLOBAL_Control
0x140044169  lea     rax, WPP_GLOBAL_Control
0x140044170  cmp     r8, rax
0x140044173  jz      loc_14004439A
0x140044179  mov     ecx, [r8+2Ch]
0x14004417d  test    cl, 1
0x140044180  jz      loc_14004439A
0x140044186  cmp     byte ptr [r8+29h], 2
0x14004418b  jb      loc_14004439A
0x140044191  mov     eax, [rbp+1Ch]
0x140044194  mov     edx, 15h
0x140044199  mov     rcx, [r8+18h]
0x14004419d  mov     r9, rbp
0x1400441a0  mov     dword ptr [rsp+88h+var_48], edi
0x1400441a4  mov     [rsp+88h+var_50], r14
0x1400441a9  mov     [rsp+88h+var_58], rbx
0x1400441ae  mov     [rsp+88h+var_60], r12
0x1400441b3  mov     dword ptr [rsp+88h+var_68], eax
0x1400441b7  call    WPP_SF_qLqiqd
0x1400441bc  jmp     loc_14004439A
0x1400441c1  lea     rcx, stru_1400293C0; Lookaside
0x1400441c8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400441cf  nop     dword ptr [rax+rax+00h]
0x1400441d4  mov     rsi, rax
0x1400441d7  test    rax, rax
0x1400441da  jnz     short loc_140044248
0x1400441dc  mov     edi, 0C000009Ah
0x1400441e1  mov     ecx, edi
0x1400441e3  call    HsmDbgBreakOnStatus
0x1400441e8  mov     rdx, cs:WPP_GLOBAL_Control
0x1400441ef  lea     rax, WPP_GLOBAL_Control
0x1400441f6  cmp     rdx, rax
0x1400441f9  jz      loc_140044303
0x1400441ff  mov     eax, [rdx+2Ch]
0x140044202  test    al, 1
0x140044204  jz      loc_140044303
0x14004420a  cmp     byte ptr [rdx+29h], 2
0x14004420e  jb      loc_140044303
0x140044214  mov     rcx, rbp
0x140044217  call    HsmpGetStreamSize
0x14004421c  mov     rcx, [rdx+18h]
0x140044220  mov     r9, r14
0x140044223  mov     [rsp+88h+var_48], rax
0x140044228  mov     eax, [rbp+1Ch]
0x14004422b  mov     dword ptr [rsp+88h+var_50], eax
0x14004422f  mov     [rsp+88h+var_58], rbp
0x140044234  mov     [rsp+88h+var_60], r15
0x140044239  mov     [rsp+88h+var_68], rbx
0x14004423e  call    WPP_SF_qiqqLid
0x140044243  jmp     loc_140044303
0x140044248  xor     edx, edx; Val
0x14004424a  lea     rcx, [rax+4]; void *
0x14004424e  lea     r8d, [rdx+54h]; Size
0x140044252  call    memset
0x140044257  mov     r13, [rsp+88h+arg_28]
0x14004425f  xor     eax, eax
0x140044261  mov     dword ptr [rsi], 63527348h
0x140044267  mov     r8d, 73557348h
0x14004426d  movzx   ecx, word ptr [r13+2]
0x140044272  mov     [rsi+22h], cx
0x140044276  mov     edx, ecx
0x140044278  mov     ecx, 100h
0x14004427d  mov     [rsi+20h], ax
0x140044281  call    cs:__imp_ExAllocatePool2
0x140044288  nop     dword ptr [rax+rax+00h]
0x14004428d  mov     rcx, rax
0x140044290  mov     [rsi+28h], rax
0x140044294  neg     rcx
0x140044297  mov     rbx, rax
0x14004429a  sbb     edx, edx
0x14004429c  not     edx
0x14004429e  and     edx, 0C000009Ah
0x1400442a4  mov     ecx, edx
0x1400442a6  mov     edi, edx
0x1400442a8  call    HsmDbgBreakOnStatus
0x1400442ad  test    rbx, rbx
0x1400442b0  jnz     short loc_14004431E
0x1400442b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400442b9  lea     rax, WPP_GLOBAL_Control
0x1400442c0  cmp     rcx, rax
0x1400442c3  jz      short loc_140044303
0x1400442c5  mov     eax, [rcx+2Ch]
0x1400442c8  test    al, 1
0x1400442ca  jz      short loc_140044303
0x1400442cc  cmp     byte ptr [rcx+29h], 2
0x1400442d0  jb      short loc_140044303
0x1400442d2  mov     rax, [rsp+88h+arg_10]
0x1400442da  lea     edx, [rbx+17h]
0x1400442dd  mov     rcx, [rcx+18h]
0x1400442e1  mov     r9, rbp
0x1400442e4  mov     dword ptr [rsp+88h+var_48], edi
0x1400442e8  mov     [rsp+88h+var_50], r14
0x1400442ed  mov     [rsp+88h+var_58], rax
0x1400442f2  mov     eax, [rbp+1Ch]
0x1400442f5  mov     [rsp+88h+var_60], r12
0x1400442fa  mov     dword ptr [rsp+88h+var_68], eax
0x1400442fe  call    WPP_SF_qLqiqd
0x140044303  mov     rcx, rbp; Context
0x140044306  call    HsmpReleaseSyncOpRundownProtection
0x14004430b  test    rsi, rsi
0x14004430e  jz      loc_14004439A
0x140044314  mov     rcx, rsi; Entry
0x140044317  call    HsmiRecallFreePopulationContext
0x14004431c  jmp     short loc_14004439A
0x14004431e  movzx   r8d, word ptr [r13+0]; Size
0x140044323  mov     rdx, [r13+8]; Src
0x140044327  mov     rcx, [rsi+28h]; void *
0x14004432b  call    memmove
0x140044330  movzx   eax, word ptr [r13+0]
0x140044335  mov     [rsi+20h], ax
0x140044339  test    r15, r15
0x14004433c  jz      short loc_14004434D
0x14004433e  mov     rcx, r15; Context
0x140044341  call    cs:__imp_FltReferenceContext
0x140044348  nop     dword ptr [rax+rax+00h]
0x14004434d  mov     rcx, rbp; Context
0x140044350  call    cs:__imp_FltReferenceContext
0x140044357  nop     dword ptr [rax+rax+00h]
0x14004435c  mov     rcx, r12; Object
0x14004435f  call    cs:__imp_ObfReferenceObject
0x140044366  nop     dword ptr [rax+rax+00h]
0x14004436b  mov     rax, [rsp+88h+arg_0]
0x140044373  mov     [rsi+40h], rax
0x140044377  mov     rax, [rsp+88h+arg_30]
0x14004437f  mov     qword ptr [rsi+8], 1
0x140044387  mov     [rsi+10h], r12
0x14004438b  mov     [rsi+18h], r14
0x14004438f  mov     [rax], rsi
0x140044392  mov     [rsi+30h], r15
0x140044396  mov     [rsi+38h], rbp
0x14004439a  mov     rbx, [rsp+88h+arg_8]
0x1400443a2  mov     eax, edi
0x1400443a4  add     rsp, 50h
0x1400443a8  pop     r15
0x1400443aa  pop     r14
0x1400443ac  pop     r13
0x1400443ae  pop     r12
0x1400443b0  pop     rdi
0x1400443b1  pop     rsi
0x1400443b2  pop     rbp
0x1400443b3  retn
```
