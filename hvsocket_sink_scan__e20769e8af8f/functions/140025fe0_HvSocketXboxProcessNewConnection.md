# HvSocketXboxProcessNewConnection

- ea: `0x140025fe0`
- end: `0x140026326`
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
- `0x140025d30`
- `0x140025fe0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026058`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026058`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002604c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002604c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026212`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026212`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026028`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026028`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400261fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400262db`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400261fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400262db`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026038`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026038`

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
  __int64 v16; // rdx
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
          (unsigned int)"HvSocketXboxProcessNewConnection",
          968,
          (_DWORD)v5,
          *((_QWORD *)v5 + 1),
          (__int64)"Dereference object");
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
      (unsigned int)"HvSocketXboxProcessNewConnection",
      919,
      (_DWORD)v5,
      *((_QWORD *)v5 + 1),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)v5 + 1) <= 1 )
    __fastfail(0xEu);
  *((_QWORD *)v5 + 12) = a2;
  *((_QWORD *)v5 + 13) = a3;
  v27 = HV_GUID_CHILDREN;
  v11 = VmbusTlProcessNewConnection(
          v4,
          (struct _FAST_MUTEX *)v5,
          (__int64)&v27,
          a4 + 20,
          (__int64)&HV_GUID_ZERO,
          a4 + 36,
          (UUID *)&HV_GUID_ZERO,
          3);
  if ( v11 < 0 && (unsigned int)dword_140013058 > 2 )
  {
    v14 = &v27;
    v15 = (unsigned int)v11;
    v16 = 948;
LABEL_13:
    HvsocketTraceGuidError("HvSocketXboxProcessNewConnection", v16, v15, v14);
  }
LABEL_14:
  v12 = 0;
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketXboxProcessNewConnection",
        957,
        (_DWORD)v5,
        *((_QWORD *)v5 + 1),
        (__int64)"Dereference object");
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
0x140025fe0  mov     [rsp+arg_8], rbx
0x140025fe5  push    rbp
0x140025fe6  push    rsi
0x140025fe7  push    rdi
0x140025fe8  push    r12
0x140025fea  push    r13
0x140025fec  push    r14
0x140025fee  push    r15
0x140025ff0  sub     rsp, 80h
0x140025ff7  mov     rax, cs:__security_cookie
0x140025ffe  xor     rax, rsp
0x140026001  mov     [rsp+0B8h+var_48], rax
0x140026006  mov     rbp, [rcx+0C8h]
0x14002600d  xorps   xmm0, xmm0
0x140026010  xor     esi, esi
0x140026012  mov     r13, r9
0x140026015  mov     [rsp+0B8h+Entry], rsi
0x14002601a  mov     r14, r8
0x14002601d  movups  [rsp+0B8h+var_58], xmm0
0x140026022  mov     r15, rdx
0x140026025  mov     r12, rcx
0x140026028  call    cs:__imp_KeEnterCriticalRegion
0x14002602f  nop     dword ptr [rax+rax+00h]
0x140026034  lea     rcx, [rbp+10h]; FastMutex
0x140026038  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002603f  nop     dword ptr [rax+rax+00h]
0x140026044  mov     dil, [rbp+78h]
0x140026048  lea     rcx, [rbp+10h]; FastMutex
0x14002604c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026053  nop     dword ptr [rax+rax+00h]
0x140026058  call    cs:__imp_KeLeaveCriticalRegion
0x14002605f  nop     dword ptr [rax+rax+00h]
0x140026064  lea     rbx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x14002606b  test    dil, dil
0x14002606e  jnz     short loc_140026083
0x140026070  mov     edi, 0C0000236h
0x140026075  lea     rbp, aDereferenceObj; "Dereference object"
0x14002607c  xor     bl, bl
0x14002607e  jmp     loc_14002622F
0x140026083  mov     edx, 70h ; 'p'
0x140026088  lea     r8, [rsp+0B8h+Entry]
0x14002608d  lea     ecx, [rdx-69h]
0x140026090  call    VmbusTlCreateObject
0x140026095  mov     rsi, [rsp+0B8h+Entry]
0x14002609a  mov     edi, eax
0x14002609c  test    eax, eax
0x14002609e  jns     short loc_1400260C4
0x1400260a0  mov     ecx, cs:dword_140013058
0x1400260a6  cmp     ecx, 2
0x1400260a9  jbe     loc_140026186
0x1400260af  lea     r9, [r12+0E8h]
0x1400260b7  mov     r8d, eax
0x1400260ba  mov     edx, 392h
0x1400260bf  jmp     loc_14002617E
0x1400260c4  lea     rax, HvsocketXboxDestroyChannelInfo
0x1400260cb  mov     [rsi+50h], rax
0x1400260cf  mov     eax, cs:dword_140013058
0x1400260d5  cmp     eax, 5
0x1400260d8  jbe     short loc_1400260FA
0x1400260da  mov     r9, [rsi+8]
0x1400260de  lea     rax, aReferenceObjec; "Reference object"
0x1400260e5  mov     r8, rsi
0x1400260e8  mov     [rsp+0B8h+var_98], rax
0x1400260ed  mov     edx, 397h
0x1400260f2  mov     rcx, rbx
0x1400260f5  call    HvsocketTraceReferenceCount
0x1400260fa  mov     eax, 1
0x1400260ff  lock xadd [rsi+8], rax
0x140026105  inc     rax
0x140026108  cmp     rax, 1
0x14002610c  jg      short loc_140026115
0x14002610e  mov     ecx, 0Eh
0x140026113  int     29h; Win8: RtlFailFast(ecx)
0x140026115  mov     [rsi+60h], r15
0x140026119  lea     rcx, HV_GUID_ZERO
0x140026120  mov     [rsi+68h], r14
0x140026124  lea     rax, [r13+24h]
0x140026128  movups  xmm0, xmmword ptr cs:HV_GUID_CHILDREN.Data1
0x14002612f  mov     [rsp+0B8h+var_80], 3
0x140026137  lea     r9, [r13+14h]
0x14002613b  mov     [rsp+0B8h+var_88], rcx
0x140026140  lea     r8, [rsp+0B8h+var_58]
0x140026145  mov     [rsp+0B8h+var_90], rax
0x14002614a  mov     rdx, rsi
0x14002614d  mov     [rsp+0B8h+var_98], rcx
0x140026152  mov     rcx, rbp
0x140026155  movdqu  [rsp+0B8h+var_58], xmm0
0x14002615b  call    VmbusTlProcessNewConnection
0x140026160  mov     edi, eax
0x140026162  test    eax, eax
0x140026164  jns     short loc_140026186
0x140026166  mov     eax, cs:dword_140013058
0x14002616c  cmp     eax, 2
0x14002616f  jbe     short loc_140026186
0x140026171  lea     r9, [rsp+0B8h+var_58]
0x140026176  mov     r8d, edi
0x140026179  mov     edx, 3B4h
0x14002617e  mov     rcx, rbx
0x140026181  call    HvsocketTraceGuidError
0x140026186  xor     bl, bl
0x140026188  lea     rbp, aDereferenceObj; "Dereference object"
0x14002618f  test    rsi, rsi
0x140026192  jz      loc_140026227
0x140026198  mov     eax, cs:dword_140013058
0x14002619e  cmp     eax, 5
0x1400261a1  jbe     short loc_1400261C0
0x1400261a3  mov     r9, [rsi+8]
0x1400261a7  lea     rcx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x1400261ae  mov     r8, rsi
0x1400261b1  mov     [rsp+0B8h+var_98], rbp
0x1400261b6  mov     edx, 3BDh
0x1400261bb  call    HvsocketTraceReferenceCount
0x1400261c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400261c4  lock xadd [rsi+8], rax
0x1400261ca  sub     rax, 1
0x1400261ce  jg      short loc_140026227
0x1400261d0  test    rax, rax
0x1400261d3  jnz     short loc_140026220
0x1400261d5  mov     rax, [rsi+50h]
0x1400261d9  mov     bl, 1
0x1400261db  test    rax, rax
0x1400261de  jz      short loc_1400261E8
0x1400261e0  mov     rcx, rsi
0x1400261e3  call    _guard_dispatch_icall
0x1400261e8  mov     ecx, [rsi+58h]
0x1400261eb  sub     ecx, 1
0x1400261ee  jz      short loc_14002620A
0x1400261f0  cmp     ecx, 1
0x1400261f3  jnz     short loc_140026227
0x1400261f5  mov     rcx, [rsi+60h]; Lookaside
0x1400261f9  mov     rdx, rsi; Entry
0x1400261fc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026203  nop     dword ptr [rax+rax+00h]
0x140026208  jmp     short loc_140026227
0x14002620a  mov     edx, 69706E56h; Tag
0x14002620f  mov     rcx, rsi; P
0x140026212  call    cs:__imp_ExFreePoolWithTag
0x140026219  nop     dword ptr [rax+rax+00h]
0x14002621e  jmp     short loc_140026227
0x140026220  mov     ecx, 0Eh
0x140026225  int     29h; Win8: RtlFailFast(ecx)
0x140026227  test    edi, edi
0x140026229  jns     loc_1400262FD
0x14002622f  movups  xmm0, xmmword ptr [r13+24h]
0x140026234  mov     r9d, edi
0x140026237  lea     r8, [rsp+0B8h+Entry]
0x14002623c  movups  xmm1, xmmword ptr [r13+14h]
0x140026241  lea     rdx, [rsp+0B8h+var_68]
0x140026246  mov     byte ptr [rsp+0B8h+var_98], 0
0x14002624b  mov     rcx, r12
0x14002624e  movdqu  xmmword ptr [rsp+0B8h+Entry], xmm0
0x140026254  movdqu  [rsp+0B8h+var_68], xmm1
0x14002625a  call    HvSocketXboxNotifyConnectResult
0x14002625f  test    rsi, rsi
0x140026262  jz      loc_1400262FD
0x140026268  test    bl, bl
0x14002626a  jnz     loc_1400262FD
0x140026270  mov     eax, cs:dword_140013058
0x140026276  cmp     eax, 5
0x140026279  jbe     short loc_140026298
0x14002627b  mov     r9, [rsi+8]
0x14002627f  lea     rcx, aHvsocketxboxpr_1; "HvSocketXboxProcessNewConnection"
0x140026286  mov     r8, rsi
0x140026289  mov     [rsp+0B8h+var_98], rbp
0x14002628e  mov     edx, 3C8h
0x140026293  call    HvsocketTraceReferenceCount
0x140026298  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002629c  lock xadd [rsi+8], rax
0x1400262a2  sub     rax, 1
0x1400262a6  jg      short loc_1400262FD
0x1400262a8  test    rax, rax
0x1400262ab  jz      short loc_1400262B6
0x1400262ad  mov     ecx, 0Eh
0x1400262b2  int     29h; Win8: RtlFailFast(ecx)
0x1400262b4  jmp     short loc_1400262FD
0x1400262b6  mov     rax, [rsi+50h]
0x1400262ba  test    rax, rax
0x1400262bd  jz      short loc_1400262C7
0x1400262bf  mov     rcx, rsi
0x1400262c2  call    _guard_dispatch_icall
0x1400262c7  mov     ecx, [rsi+58h]
0x1400262ca  sub     ecx, 1
0x1400262cd  jz      short loc_1400262E9
0x1400262cf  cmp     ecx, 1
0x1400262d2  jnz     short loc_1400262FD
0x1400262d4  mov     rcx, [rsi+60h]; Lookaside
0x1400262d8  mov     rdx, rsi; Entry
0x1400262db  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400262e2  nop     dword ptr [rax+rax+00h]
0x1400262e7  jmp     short loc_1400262FD
0x1400262e9  mov     edx, 69706E56h; Tag
0x1400262ee  mov     rcx, rsi; P
0x1400262f1  call    cs:__imp_ExFreePoolWithTag
0x1400262f8  nop     dword ptr [rax+rax+00h]
0x1400262fd  mov     rcx, [rsp+0B8h+var_48]
0x140026302  xor     rcx, rsp; StackCookie
0x140026305  call    __security_check_cookie
0x14002630a  mov     rbx, [rsp+0B8h+arg_8]
0x140026312  add     rsp, 80h
0x140026319  pop     r15
0x14002631b  pop     r14
0x14002631d  pop     r13
0x14002631f  pop     r12
0x140026321  pop     rdi
0x140026322  pop     rsi
0x140026323  pop     rbp
0x140026324  retn
```
