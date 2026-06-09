# HvSocketXboxProcessNewConnection

- ea: `0x140026080`
- end: `0x1400263c6`
- name: `HvSocketXboxProcessNewConnection`
- size: `838`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400238d0`

## callees

- `0x140001350`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14001bd20`
- `0x140025dd0`
- `0x140026080`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400260f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400260f8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400260ec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400260ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026391`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026391`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400260c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400260c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002629c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002637b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002629c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002637b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400260d8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400260d8`

## pseudocode

```c
void __fastcall HvSocketXboxProcessNewConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbp
  PVOID v5; // rsi
  char v10; // di
  int v11; // edi
  char v12; // bl
  int Object; // eax
  GUID *v14; // r9
  __int64 v15; // r8
  int v16; // edx
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(PVOID); // rax
  __int128 v21; // xmm1
  signed __int64 v22; // rax
  signed __int64 v23; // rax
  void (__fastcall *v24)(PVOID); // rax
  PVOID Entry[2]; // [rsp+40h] [rbp-78h] BYREF
  __int128 v26; // [rsp+50h] [rbp-68h] BYREF
  GUID v27; // [rsp+60h] [rbp-58h] BYREF

  v4 = *(_QWORD *)(a1 + 200);
  v5 = 0;
  Entry[0] = 0;
  v27 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  v10 = *(_BYTE *)(v4 + 120);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  KeLeaveCriticalRegion();
  if ( !v10 )
  {
    v11 = -1073741258;
    v12 = 0;
LABEL_27:
    v21 = *(_OWORD *)(a4 + 20);
    *(_OWORD *)Entry = *(_OWORD *)(a4 + 36);
    v26 = v21;
    HvSocketXboxNotifyConnectResult(a1, (unsigned int)&v26, (unsigned int)Entry, v11, 0);
    if ( v5 && !v12 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"HvSocketXboxProcessNewConnection",
          968,
          (__int64)v5,
          *((_QWORD *)v5 + 1),
          (const int *)"Dereference object");
      v22 = _InterlockedExchangeAdd64((volatile signed __int64 *)v5 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v18 = v22 <= 1;
      v23 = v22 - 1;
      if ( v18 )
      {
        if ( v23 )
          __fastfail(0xEu);
        v24 = (void (__fastcall *)(PVOID))*((_QWORD *)v5 + 10);
        if ( v24 )
          v24(v5);
        if ( *((_DWORD *)v5 + 22) == 1 )
        {
          ExFreePoolWithTag(v5, 0x69706E56u);
        }
        else if ( *((_DWORD *)v5 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v5 + 12), v5);
        }
      }
    }
    return;
  }
  Object = VmbusTlCreateObject(7, 112, Entry);
  v5 = Entry[0];
  v11 = Object;
  if ( Object < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_14;
    v14 = (GUID *)(a1 + 232);
    v15 = (unsigned int)Object;
    v16 = 914;
    goto LABEL_13;
  }
  *((_QWORD *)Entry[0] + 10) = HvsocketXboxDestroyChannelInfo;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"HvSocketXboxProcessNewConnection",
      919,
      (__int64)v5,
      *((_QWORD *)v5 + 1),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)v5 + 1) <= 1 )
    __fastfail(0xEu);
  *((_QWORD *)v5 + 12) = a2;
  *((_QWORD *)v5 + 13) = a3;
  v27 = HV_GUID_CHILDREN;
  v11 = VmbusTlProcessNewConnection(v4, v5, &v27, a4 + 20, &HV_GUID_ZERO, a4 + 36, &HV_GUID_ZERO, 3);
  if ( v11 < 0 && (unsigned int)dword_140013058 > 2 )
  {
    v14 = &v27;
    v15 = (unsigned int)v11;
    v16 = 948;
LABEL_13:
    HvsocketTraceGuidError((const int *)"HvSocketXboxProcessNewConnection", v16, v15, (__int64)v14);
  }
LABEL_14:
  v12 = 0;
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"HvSocketXboxProcessNewConnection",
        957,
        (__int64)v5,
        *((_QWORD *)v5 + 1),
        (const int *)"Dereference object");
    v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)v5 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v17 <= 1;
    v19 = v17 - 1;
    if ( v18 )
    {
      if ( v19 )
        __fastfail(0xEu);
      v20 = (void (__fastcall *)(PVOID))*((_QWORD *)v5 + 10);
      v12 = 1;
      if ( v20 )
        v20(v5);
      if ( *((_DWORD *)v5 + 22) == 1 )
      {
        ExFreePoolWithTag(v5, 0x69706E56u);
      }
      else if ( *((_DWORD *)v5 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v5 + 12), v5);
      }
    }
  }
  if ( v11 < 0 )
    goto LABEL_27;
}

```

## disassembly

```asm
0x140026080  mov     [rsp+arg_8], rbx
0x140026085  push    rbp
0x140026086  push    rsi
0x140026087  push    rdi
0x140026088  push    r12
0x14002608a  push    r13
0x14002608c  push    r14
0x14002608e  push    r15
0x140026090  sub     rsp, 80h
0x140026097  mov     rax, cs:__security_cookie
0x14002609e  xor     rax, rsp
0x1400260a1  mov     [rsp+0B8h+var_48], rax
0x1400260a6  mov     rbp, [rcx+0C8h]
0x1400260ad  xorps   xmm0, xmm0
0x1400260b0  xor     esi, esi
0x1400260b2  mov     r13, r9
0x1400260b5  mov     [rsp+0B8h+Entry], rsi
0x1400260ba  mov     r14, r8
0x1400260bd  movups  [rsp+0B8h+var_58], xmm0
0x1400260c2  mov     r15, rdx
0x1400260c5  mov     r12, rcx
0x1400260c8  call    cs:__imp_KeEnterCriticalRegion
0x1400260cf  nop     dword ptr [rax+rax+00h]
0x1400260d4  lea     rcx, [rbp+10h]; FastMutex
0x1400260d8  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400260df  nop     dword ptr [rax+rax+00h]
0x1400260e4  mov     dil, [rbp+78h]
0x1400260e8  lea     rcx, [rbp+10h]; FastMutex
0x1400260ec  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400260f3  nop     dword ptr [rax+rax+00h]
0x1400260f8  call    cs:__imp_KeLeaveCriticalRegion
0x1400260ff  nop     dword ptr [rax+rax+00h]
0x140026104  lea     rbx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x14002610b  test    dil, dil
0x14002610e  jnz     short loc_140026123
0x140026110  mov     edi, 0C0000236h
0x140026115  lea     rbp, aDereferenceObj; "Dereference object"
0x14002611c  xor     bl, bl
0x14002611e  jmp     loc_1400262CF
0x140026123  mov     edx, 70h ; 'p'
0x140026128  lea     r8, [rsp+0B8h+Entry]
0x14002612d  lea     ecx, [rdx-69h]
0x140026130  call    VmbusTlCreateObject
0x140026135  mov     rsi, [rsp+0B8h+Entry]
0x14002613a  mov     edi, eax
0x14002613c  test    eax, eax
0x14002613e  jns     short loc_140026164
0x140026140  mov     ecx, cs:dword_140013058
0x140026146  cmp     ecx, 2
0x140026149  jbe     loc_140026226
0x14002614f  lea     r9, [r12+0E8h]
0x140026157  mov     r8d, eax
0x14002615a  mov     edx, 392h
0x14002615f  jmp     loc_14002621E
0x140026164  lea     rax, HvsocketXboxDestroyChannelInfo
0x14002616b  mov     [rsi+50h], rax
0x14002616f  mov     eax, cs:dword_140013058
0x140026175  cmp     eax, 5
0x140026178  jbe     short loc_14002619A
0x14002617a  mov     r9, [rsi+8]
0x14002617e  lea     rax, aReferenceObjec; "Reference object"
0x140026185  mov     r8, rsi
0x140026188  mov     [rsp+0B8h+var_98], rax
0x14002618d  mov     edx, 397h
0x140026192  mov     rcx, rbx
0x140026195  call    HvsocketTraceReferenceCount
0x14002619a  mov     eax, 1
0x14002619f  lock xadd [rsi+8], rax
0x1400261a5  inc     rax
0x1400261a8  cmp     rax, 1
0x1400261ac  jg      short loc_1400261B5
0x1400261ae  mov     ecx, 0Eh
0x1400261b3  int     29h; Win8: RtlFailFast(ecx)
0x1400261b5  mov     [rsi+60h], r15
0x1400261b9  lea     rcx, HV_GUID_ZERO
0x1400261c0  mov     [rsi+68h], r14
0x1400261c4  lea     rax, [r13+24h]
0x1400261c8  movups  xmm0, xmmword ptr cs:HV_GUID_CHILDREN.Data1
0x1400261cf  mov     [rsp+0B8h+var_80], 3
0x1400261d7  lea     r9, [r13+14h]
0x1400261db  mov     [rsp+0B8h+var_88], rcx
0x1400261e0  lea     r8, [rsp+0B8h+var_58]
0x1400261e5  mov     [rsp+0B8h+var_90], rax
0x1400261ea  mov     rdx, rsi
0x1400261ed  mov     [rsp+0B8h+var_98], rcx
0x1400261f2  mov     rcx, rbp
0x1400261f5  movdqu  [rsp+0B8h+var_58], xmm0
0x1400261fb  call    VmbusTlProcessNewConnection
0x140026200  mov     edi, eax
0x140026202  test    eax, eax
0x140026204  jns     short loc_140026226
0x140026206  mov     eax, cs:dword_140013058
0x14002620c  cmp     eax, 2
0x14002620f  jbe     short loc_140026226
0x140026211  lea     r9, [rsp+0B8h+var_58]
0x140026216  mov     r8d, edi
0x140026219  mov     edx, 3B4h
0x14002621e  mov     rcx, rbx
0x140026221  call    HvsocketTraceGuidError
0x140026226  xor     bl, bl
0x140026228  lea     rbp, aDereferenceObj; "Dereference object"
0x14002622f  test    rsi, rsi
0x140026232  jz      loc_1400262C7
0x140026238  mov     eax, cs:dword_140013058
0x14002623e  cmp     eax, 5
0x140026241  jbe     short loc_140026260
0x140026243  mov     r9, [rsi+8]
0x140026247  lea     rcx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x14002624e  mov     r8, rsi
0x140026251  mov     [rsp+0B8h+var_98], rbp
0x140026256  mov     edx, 3BDh
0x14002625b  call    HvsocketTraceReferenceCount
0x140026260  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026264  lock xadd [rsi+8], rax
0x14002626a  sub     rax, 1
0x14002626e  jg      short loc_1400262C7
0x140026270  test    rax, rax
0x140026273  jnz     short loc_1400262C0
0x140026275  mov     rax, [rsi+50h]
0x140026279  mov     bl, 1
0x14002627b  test    rax, rax
0x14002627e  jz      short loc_140026288
0x140026280  mov     rcx, rsi
0x140026283  call    _guard_dispatch_icall
0x140026288  mov     ecx, [rsi+58h]
0x14002628b  sub     ecx, 1
0x14002628e  jz      short loc_1400262AA
0x140026290  cmp     ecx, 1
0x140026293  jnz     short loc_1400262C7
0x140026295  mov     rcx, [rsi+60h]; Lookaside
0x140026299  mov     rdx, rsi; Entry
0x14002629c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400262a3  nop     dword ptr [rax+rax+00h]
0x1400262a8  jmp     short loc_1400262C7
0x1400262aa  mov     edx, 69706E56h; Tag
0x1400262af  mov     rcx, rsi; P
0x1400262b2  call    cs:__imp_ExFreePoolWithTag
0x1400262b9  nop     dword ptr [rax+rax+00h]
0x1400262be  jmp     short loc_1400262C7
0x1400262c0  mov     ecx, 0Eh
0x1400262c5  int     29h; Win8: RtlFailFast(ecx)
0x1400262c7  test    edi, edi
0x1400262c9  jns     loc_14002639D
0x1400262cf  movups  xmm0, xmmword ptr [r13+24h]
0x1400262d4  mov     r9d, edi
0x1400262d7  lea     r8, [rsp+0B8h+Entry]
0x1400262dc  movups  xmm1, xmmword ptr [r13+14h]
0x1400262e1  lea     rdx, [rsp+0B8h+var_68]
0x1400262e6  mov     byte ptr [rsp+0B8h+var_98], 0
0x1400262eb  mov     rcx, r12
0x1400262ee  movdqu  xmmword ptr [rsp+0B8h+Entry], xmm0
0x1400262f4  movdqu  [rsp+0B8h+var_68], xmm1
0x1400262fa  call    HvSocketXboxNotifyConnectResult
0x1400262ff  test    rsi, rsi
0x140026302  jz      loc_14002639D
0x140026308  test    bl, bl
0x14002630a  jnz     loc_14002639D
0x140026310  mov     eax, cs:dword_140013058
0x140026316  cmp     eax, 5
0x140026319  jbe     short loc_140026338
0x14002631b  mov     r9, [rsi+8]
0x14002631f  lea     rcx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x140026326  mov     r8, rsi
0x140026329  mov     [rsp+0B8h+var_98], rbp
0x14002632e  mov     edx, 3C8h
0x140026333  call    HvsocketTraceReferenceCount
0x140026338  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002633c  lock xadd [rsi+8], rax
0x140026342  sub     rax, 1
0x140026346  jg      short loc_14002639D
0x140026348  test    rax, rax
0x14002634b  jz      short loc_140026356
0x14002634d  mov     ecx, 0Eh
0x140026352  int     29h; Win8: RtlFailFast(ecx)
0x140026354  jmp     short loc_14002639D
0x140026356  mov     rax, [rsi+50h]
0x14002635a  test    rax, rax
0x14002635d  jz      short loc_140026367
0x14002635f  mov     rcx, rsi
0x140026362  call    _guard_dispatch_icall
0x140026367  mov     ecx, [rsi+58h]
0x14002636a  sub     ecx, 1
0x14002636d  jz      short loc_140026389
0x14002636f  cmp     ecx, 1
0x140026372  jnz     short loc_14002639D
0x140026374  mov     rcx, [rsi+60h]; Lookaside
0x140026378  mov     rdx, rsi; Entry
0x14002637b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026382  nop     dword ptr [rax+rax+00h]
0x140026387  jmp     short loc_14002639D
0x140026389  mov     edx, 69706E56h; Tag
0x14002638e  mov     rcx, rsi; P
0x140026391  call    cs:__imp_ExFreePoolWithTag
0x140026398  nop     dword ptr [rax+rax+00h]
0x14002639d  mov     rcx, [rsp+0B8h+var_48]
0x1400263a2  xor     rcx, rsp; StackCookie
0x1400263a5  call    __security_check_cookie
0x1400263aa  mov     rbx, [rsp+0B8h+arg_8]
0x1400263b2  add     rsp, 80h
0x1400263b9  pop     r15
0x1400263bb  pop     r14
0x1400263bd  pop     r13
0x1400263bf  pop     r12
0x1400263c1  pop     rdi
0x1400263c2  pop     rsi
0x1400263c3  pop     rbp
0x1400263c4  retn
```
