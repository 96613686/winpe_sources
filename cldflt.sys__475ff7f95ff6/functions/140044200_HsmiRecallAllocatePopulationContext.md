# HsmiRecallAllocatePopulationContext

- ea: `0x140044200`
- end: `0x1400444a5`
- name: `HsmiRecallAllocatePopulationContext`
- size: `677`
- prototype: `__int64 __fastcall(__int64, void *, __int64, void *, struct _FLT_CALLBACK_DATA *CallbackData, const void **, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140003cf0`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x140017eb0`
- `0x140017ff4`
- `0x14001e300`
- `0x14001e600`
- `0x140044200`
- `0x14004450c`
- `0x140058ddc`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14004444f`
- `ntoskrnl!ObfReferenceObject` at `0x14004444f`
- `ntoskrnl!ExAllocatePool2` at `0x140044371`
- `ntoskrnl!ExAllocatePool2` at `0x140044371`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400442b8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400442b8`
- `FLTMGR!FltReferenceContext` at `0x140044431`
- `FLTMGR!FltReferenceContext` at `0x140044440`
- `FLTMGR!FltReferenceContext` at `0x140044431`
- `FLTMGR!FltReferenceContext` at `0x140044440`

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
  unsigned int v11; // edi
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
  v11 = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a3, CallbackData);
  HsmDbgBreakOnStatus(v11);
  if ( (v11 & 0x80000000) != 0 )
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
    return v11;
  }
  v12 = ExAllocateFromPagedLookasideList(&stru_1400293C0);
  v13 = v12;
  if ( !v12 )
  {
    v11 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
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
    return v11;
  }
  memset(v12 + 1, 0, 0x54u);
  *v13 = 1666347848;
  v17 = *((unsigned __int16 *)a6 + 1);
  *((_WORD *)v13 + 17) = v17;
  *((_WORD *)v13 + 16) = 0;
  Pool2 = ExAllocatePool2(256, v17, 1934979912);
  *((_QWORD *)v13 + 5) = Pool2;
  v19 = Pool2;
  v11 = Pool2 == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v11);
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
  return v11;
}

```

## disassembly

```asm
0x140044200  mov     [rsp+arg_8], rbx
0x140044205  mov     [rsp+arg_0], rcx
0x14004420a  push    rbp
0x14004420b  push    rsi
0x14004420c  push    rdi
0x14004420d  push    r12
0x14004420f  push    r13
0x140044211  push    r14
0x140044213  push    r15
0x140044215  sub     rsp, 50h
0x140044219  mov     rax, [r8+10h]
0x14004421d  mov     r15, rdx
0x140044220  mov     r14, [rsp+88h+CallbackData]
0x140044228  mov     rcx, r8; Context
0x14004422b  mov     rdx, r14; CallbackData
0x14004422e  mov     r12, r9
0x140044231  mov     rbp, r8
0x140044234  mov     rbx, [rax+20h]
0x140044238  mov     [rsp+88h+arg_10], rbx
0x140044240  call    HsmpAcquireSyncOpRundownProtection
0x140044245  mov     ecx, eax
0x140044247  mov     edi, eax
0x140044249  call    HsmDbgBreakOnStatus
0x14004424e  test    edi, edi
0x140044250  jns     short loc_1400442B1
0x140044252  mov     r8, cs:WPP_GLOBAL_Control
0x140044259  lea     rax, WPP_GLOBAL_Control
0x140044260  cmp     r8, rax
0x140044263  jz      loc_14004448A
0x140044269  mov     ecx, [r8+2Ch]
0x14004426d  test    cl, 1
0x140044270  jz      loc_14004448A
0x140044276  cmp     byte ptr [r8+29h], 2
0x14004427b  jb      loc_14004448A
0x140044281  mov     eax, [rbp+1Ch]
0x140044284  mov     edx, 15h
0x140044289  mov     rcx, [r8+18h]
0x14004428d  mov     r9, rbp
0x140044290  mov     dword ptr [rsp+88h+var_48], edi
0x140044294  mov     [rsp+88h+var_50], r14
0x140044299  mov     [rsp+88h+var_58], rbx
0x14004429e  mov     [rsp+88h+var_60], r12
0x1400442a3  mov     dword ptr [rsp+88h+var_68], eax
0x1400442a7  call    WPP_SF_qLqiqd
0x1400442ac  jmp     loc_14004448A
0x1400442b1  lea     rcx, stru_1400293C0; Lookaside
0x1400442b8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400442bf  nop     dword ptr [rax+rax+00h]
0x1400442c4  mov     rsi, rax
0x1400442c7  test    rax, rax
0x1400442ca  jnz     short loc_140044338
0x1400442cc  mov     edi, 0C000009Ah
0x1400442d1  mov     ecx, edi
0x1400442d3  call    HsmDbgBreakOnStatus
0x1400442d8  mov     rdx, cs:WPP_GLOBAL_Control
0x1400442df  lea     rax, WPP_GLOBAL_Control
0x1400442e6  cmp     rdx, rax
0x1400442e9  jz      loc_1400443F3
0x1400442ef  mov     eax, [rdx+2Ch]
0x1400442f2  test    al, 1
0x1400442f4  jz      loc_1400443F3
0x1400442fa  cmp     byte ptr [rdx+29h], 2
0x1400442fe  jb      loc_1400443F3
0x140044304  mov     rcx, rbp
0x140044307  call    HsmpGetStreamSize
0x14004430c  mov     rcx, [rdx+18h]
0x140044310  mov     r9, r14
0x140044313  mov     [rsp+88h+var_48], rax
0x140044318  mov     eax, [rbp+1Ch]
0x14004431b  mov     dword ptr [rsp+88h+var_50], eax
0x14004431f  mov     [rsp+88h+var_58], rbp
0x140044324  mov     [rsp+88h+var_60], r15
0x140044329  mov     [rsp+88h+var_68], rbx
0x14004432e  call    WPP_SF_qiqqLid
0x140044333  jmp     loc_1400443F3
0x140044338  xor     edx, edx; Val
0x14004433a  lea     rcx, [rax+4]; void *
0x14004433e  lea     r8d, [rdx+54h]; Size
0x140044342  call    memset
0x140044347  mov     r13, [rsp+88h+arg_28]
0x14004434f  xor     eax, eax
0x140044351  mov     dword ptr [rsi], 63527348h
0x140044357  mov     r8d, 73557348h
0x14004435d  movzx   ecx, word ptr [r13+2]
0x140044362  mov     [rsi+22h], cx
0x140044366  mov     edx, ecx
0x140044368  mov     ecx, 100h
0x14004436d  mov     [rsi+20h], ax
0x140044371  call    cs:__imp_ExAllocatePool2
0x140044378  nop     dword ptr [rax+rax+00h]
0x14004437d  mov     rcx, rax
0x140044380  mov     [rsi+28h], rax
0x140044384  neg     rcx
0x140044387  mov     rbx, rax
0x14004438a  sbb     edx, edx
0x14004438c  not     edx
0x14004438e  and     edx, 0C000009Ah
0x140044394  mov     ecx, edx
0x140044396  mov     edi, edx
0x140044398  call    HsmDbgBreakOnStatus
0x14004439d  test    rbx, rbx
0x1400443a0  jnz     short loc_14004440E
0x1400443a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400443a9  lea     rax, WPP_GLOBAL_Control
0x1400443b0  cmp     rcx, rax
0x1400443b3  jz      short loc_1400443F3
0x1400443b5  mov     eax, [rcx+2Ch]
0x1400443b8  test    al, 1
0x1400443ba  jz      short loc_1400443F3
0x1400443bc  cmp     byte ptr [rcx+29h], 2
0x1400443c0  jb      short loc_1400443F3
0x1400443c2  mov     rax, [rsp+88h+arg_10]
0x1400443ca  lea     edx, [rbx+17h]
0x1400443cd  mov     rcx, [rcx+18h]
0x1400443d1  mov     r9, rbp
0x1400443d4  mov     dword ptr [rsp+88h+var_48], edi
0x1400443d8  mov     [rsp+88h+var_50], r14
0x1400443dd  mov     [rsp+88h+var_58], rax
0x1400443e2  mov     eax, [rbp+1Ch]
0x1400443e5  mov     [rsp+88h+var_60], r12
0x1400443ea  mov     dword ptr [rsp+88h+var_68], eax
0x1400443ee  call    WPP_SF_qLqiqd
0x1400443f3  mov     rcx, rbp; Context
0x1400443f6  call    HsmpReleaseSyncOpRundownProtection
0x1400443fb  test    rsi, rsi
0x1400443fe  jz      loc_14004448A
0x140044404  mov     rcx, rsi; Entry
0x140044407  call    HsmiRecallFreePopulationContext
0x14004440c  jmp     short loc_14004448A
0x14004440e  movzx   r8d, word ptr [r13+0]; Size
0x140044413  mov     rdx, [r13+8]; Src
0x140044417  mov     rcx, [rsi+28h]; void *
0x14004441b  call    memmove
0x140044420  movzx   eax, word ptr [r13+0]
0x140044425  mov     [rsi+20h], ax
0x140044429  test    r15, r15
0x14004442c  jz      short loc_14004443D
0x14004442e  mov     rcx, r15; Context
0x140044431  call    cs:__imp_FltReferenceContext
0x140044438  nop     dword ptr [rax+rax+00h]
0x14004443d  mov     rcx, rbp; Context
0x140044440  call    cs:__imp_FltReferenceContext
0x140044447  nop     dword ptr [rax+rax+00h]
0x14004444c  mov     rcx, r12; Object
0x14004444f  call    cs:__imp_ObfReferenceObject
0x140044456  nop     dword ptr [rax+rax+00h]
0x14004445b  mov     rax, [rsp+88h+arg_0]
0x140044463  mov     [rsi+40h], rax
0x140044467  mov     rax, [rsp+88h+arg_30]
0x14004446f  mov     qword ptr [rsi+8], 1
0x140044477  mov     [rsi+10h], r12
0x14004447b  mov     [rsi+18h], r14
0x14004447f  mov     [rax], rsi
0x140044482  mov     [rsi+30h], r15
0x140044486  mov     [rsi+38h], rbp
0x14004448a  mov     rbx, [rsp+88h+arg_8]
0x140044492  mov     eax, edi
0x140044494  add     rsp, 50h
0x140044498  pop     r15
0x14004449a  pop     r14
0x14004449c  pop     r13
0x14004449e  pop     r12
0x1400444a0  pop     rdi
0x1400444a1  pop     rsi
0x1400444a2  pop     rbp
0x1400444a3  retn
```
