# VmbusTlLoopbackSend

- ea: `0x1400065fc`
- end: `0x1400068a3`
- name: `VmbusTlLoopbackSend`
- size: `679`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400063c0`

## callees

- `0x140003890`
- `0x140006448`
- `0x1400065fc`
- `0x14000975c`
- `0x1400098f4`
- `0x14000a048`
- `0x14000bfe0`
- `0x14000c4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006631`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006631`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400067db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006887`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400067db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006887`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400067c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400067f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006871`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400067c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400067f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006871`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackSend(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  _QWORD *v6; // rax
  _QWORD *v7; // r14
  int v8; // eax
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  void (__fastcall *v12)(__int64); // rax
  signed __int64 v13; // rax
  signed __int64 v14; // rax
  void (__fastcall *v15)(__int64); // rax

  v4 = VmbusTlLoopbackReferenceEndpointDeliveryQueue();
  if ( v4 )
  {
    v6 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 112) + 832LL));
    v7 = v6;
    if ( v6 )
    {
      memset(v6, 0, 0x90u);
      v7[4] = *(_QWORD *)(v4 + 104);
      v7[17] = a2;
      v7[3] = *(_QWORD *)(a2 + 184);
      v7[1] = *(_QWORD *)(*(_QWORD *)(a2 + 224) + 8LL);
      *((_DWORD *)v7 + 4) = *(_DWORD *)(a2 + 176);
      *v7 = 0;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlLoopbackSend",
          332,
          a2,
          *(_QWORD *)(a2 + 8),
          (const int *)"Reference object");
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8)) <= 1 )
        __fastfail(0xEu);
      v8 = VmbusTlQueueAndDeliverData(*(_QWORD *)(v4 + 104), v7);
      v5 = v8;
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceEndpointGuidError(
            (const int *)"VmbusTlLoopbackSend",
            339,
            (unsigned int)v8,
            a1,
            *(_QWORD *)(v4 + 104) + 464LL);
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (const int *)"VmbusTlLoopbackSend",
            340,
            a2,
            *(_QWORD *)(a2 + 8),
            (const int *)"Dereference object");
        v9 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 8), 0xFFFFFFFFFFFFFFFFuLL);
        v10 = v9 <= 1;
        v11 = v9 - 1;
        if ( v10 )
        {
          if ( v11 )
            __fastfail(0xEu);
          v12 = *(void (__fastcall **)(__int64))(a2 + 80);
          if ( v12 )
            v12(a2);
          if ( *(_DWORD *)(a2 + 88) == 1 )
          {
            ExFreePoolWithTag((PVOID)a2, 0x69706E56u);
          }
          else if ( *(_DWORD *)(a2 + 88) == 2 )
          {
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a2 + 96), (PVOID)a2);
          }
        }
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 112) + 832LL), v7);
      }
    }
    else
    {
      v5 = -1073741801;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointError((const int *)"VmbusTlLoopbackSend", 306, 3221225495LL, a1);
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlLoopbackSend",
        347,
        v4,
        *(_QWORD *)(v4 + 8),
        (const int *)"Dereference object");
    v13 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v10 = v13 <= 1;
    v14 = v13 - 1;
    if ( v10 )
    {
      if ( v14 )
        __fastfail(0xEu);
      v15 = *(void (__fastcall **)(__int64))(v4 + 80);
      if ( v15 )
        v15(v4);
      if ( *(_DWORD *)(v4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 96), (PVOID)v4);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741247;
  }
  return v5;
}

```

## disassembly

```asm
0x1400065fc  push    rbx
0x1400065fe  push    rbp
0x1400065ff  push    rsi
0x140006600  push    rdi
0x140006601  push    r13
0x140006603  push    r14
0x140006605  sub     rsp, 38h
0x140006609  mov     rdi, rdx
0x14000660c  mov     rbp, rcx
0x14000660f  call    VmbusTlLoopbackReferenceEndpointDeliveryQueue
0x140006614  mov     rbx, rax
0x140006617  test    rax, rax
0x14000661a  jnz     short loc_140006626
0x14000661c  mov     esi, 0C0000241h
0x140006621  jmp     loc_140006893
0x140006626  mov     rcx, [rbp+70h]
0x14000662a  add     rcx, 340h; Lookaside
0x140006631  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140006638  nop     dword ptr [rax+rax+00h]
0x14000663d  mov     r14, rax
0x140006640  mov     r13d, 0Eh
0x140006646  test    rax, rax
0x140006649  jnz     short loc_14000667B
0x14000664b  mov     eax, cs:dword_140013058
0x140006651  mov     esi, 0C0000017h
0x140006656  cmp     eax, 2
0x140006659  jbe     loc_140006801
0x14000665f  mov     r9, rbp
0x140006662  lea     rcx, aVmbustlloopbac_5; "VmbusTlLoopbackSend"
0x140006669  mov     r8d, esi
0x14000666c  mov     edx, 132h
0x140006671  call    HvsocketTraceEndpointError
0x140006676  jmp     loc_140006801
0x14000667b  xor     edx, edx; Val
0x14000667d  mov     r8d, 90h; Size
0x140006683  mov     rcx, r14; void *
0x140006686  call    memset
0x14000668b  mov     rax, [rbx+68h]
0x14000668f  mov     [r14+20h], rax
0x140006693  mov     [r14+88h], rdi
0x14000669a  mov     rax, [rdi+0B8h]
0x1400066a1  mov     [r14+18h], rax
0x1400066a5  mov     rax, [rdi+0E0h]
0x1400066ac  mov     rcx, [rax+8]
0x1400066b0  mov     [r14+8], rcx
0x1400066b4  mov     eax, [rdi+0B0h]
0x1400066ba  mov     [r14+10h], eax
0x1400066be  mov     qword ptr [r14], 0
0x1400066c5  mov     eax, cs:dword_140013058
0x1400066cb  cmp     eax, 5
0x1400066ce  jbe     short loc_1400066F4
0x1400066d0  mov     r9, [rdi+8]
0x1400066d4  lea     rax, aReferenceObjec; "Reference object"
0x1400066db  mov     r8, rdi
0x1400066de  mov     [rsp+68h+var_48], rax
0x1400066e3  mov     edx, 14Ch
0x1400066e8  lea     rcx, aVmbustlloopbac_5; "VmbusTlLoopbackSend"
0x1400066ef  call    HvsocketTraceReferenceCount
0x1400066f4  mov     eax, 1
0x1400066f9  lock xadd [rdi+8], rax
0x1400066ff  inc     rax
0x140006702  cmp     rax, 1
0x140006706  jg      short loc_14000670D
0x140006708  mov     rcx, r13
0x14000670b  int     29h; Win8: RtlFailFast(ecx)
0x14000670d  mov     rcx, [rbx+68h]
0x140006711  mov     rdx, r14
0x140006714  call    VmbusTlQueueAndDeliverData
0x140006719  mov     esi, eax
0x14000671b  test    eax, eax
0x14000671d  jns     loc_140006801
0x140006723  mov     ecx, cs:dword_140013058
0x140006729  cmp     ecx, 2
0x14000672c  jbe     short loc_140006755
0x14000672e  mov     rcx, [rbx+68h]
0x140006732  mov     r9, rbp
0x140006735  add     rcx, 1D0h
0x14000673c  mov     r8d, eax
0x14000673f  mov     [rsp+68h+var_48], rcx
0x140006744  mov     edx, 153h
0x140006749  lea     rcx, aVmbustlloopbac_5; "VmbusTlLoopbackSend"
0x140006750  call    HvsocketTraceEndpointGuidError
0x140006755  mov     eax, cs:dword_140013058
0x14000675b  cmp     eax, 5
0x14000675e  jbe     short loc_140006784
0x140006760  mov     r9, [rdi+8]
0x140006764  lea     rax, aDereferenceObj; "Dereference object"
0x14000676b  mov     r8, rdi
0x14000676e  mov     [rsp+68h+var_48], rax
0x140006773  mov     edx, 154h
0x140006778  lea     rcx, aVmbustlloopbac_5; "VmbusTlLoopbackSend"
0x14000677f  call    HvsocketTraceReferenceCount
0x140006784  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006788  lock xadd [rdi+8], rax
0x14000678e  sub     rax, 1
0x140006792  jg      short loc_1400067E7
0x140006794  test    rax, rax
0x140006797  jz      short loc_1400067A0
0x140006799  mov     rcx, r13
0x14000679c  int     29h; Win8: RtlFailFast(ecx)
0x14000679e  jmp     short loc_1400067E7
0x1400067a0  mov     rax, [rdi+50h]
0x1400067a4  test    rax, rax
0x1400067a7  jz      short loc_1400067B1
0x1400067a9  mov     rcx, rdi
0x1400067ac  call    _guard_dispatch_icall
0x1400067b1  mov     ecx, [rdi+58h]
0x1400067b4  sub     ecx, 1
0x1400067b7  jz      short loc_1400067D3
0x1400067b9  cmp     ecx, 1
0x1400067bc  jnz     short loc_1400067E7
0x1400067be  mov     rcx, [rdi+60h]; Lookaside
0x1400067c2  mov     rdx, rdi; Entry
0x1400067c5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400067cc  nop     dword ptr [rax+rax+00h]
0x1400067d1  jmp     short loc_1400067E7
0x1400067d3  mov     edx, 69706E56h; Tag
0x1400067d8  mov     rcx, rdi; P
0x1400067db  call    cs:__imp_ExFreePoolWithTag
0x1400067e2  nop     dword ptr [rax+rax+00h]
0x1400067e7  mov     rcx, [rbp+70h]
0x1400067eb  mov     rdx, r14; Entry
0x1400067ee  add     rcx, 340h; Lookaside
0x1400067f5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400067fc  nop     dword ptr [rax+rax+00h]
0x140006801  mov     eax, cs:dword_140013058
0x140006807  cmp     eax, 5
0x14000680a  jbe     short loc_140006830
0x14000680c  mov     r9, [rbx+8]
0x140006810  lea     rax, aDereferenceObj; "Dereference object"
0x140006817  mov     r8, rbx
0x14000681a  mov     [rsp+68h+var_48], rax
0x14000681f  mov     edx, 15Bh
0x140006824  lea     rcx, aVmbustlloopbac_5; "VmbusTlLoopbackSend"
0x14000682b  call    HvsocketTraceReferenceCount
0x140006830  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006834  lock xadd [rbx+8], rax
0x14000683a  sub     rax, 1
0x14000683e  jg      short loc_140006893
0x140006840  test    rax, rax
0x140006843  jz      short loc_14000684C
0x140006845  mov     rcx, r13
0x140006848  int     29h; Win8: RtlFailFast(ecx)
0x14000684a  jmp     short loc_140006893
0x14000684c  mov     rax, [rbx+50h]
0x140006850  test    rax, rax
0x140006853  jz      short loc_14000685D
0x140006855  mov     rcx, rbx
0x140006858  call    _guard_dispatch_icall
0x14000685d  mov     ecx, [rbx+58h]
0x140006860  sub     ecx, 1
0x140006863  jz      short loc_14000687F
0x140006865  cmp     ecx, 1
0x140006868  jnz     short loc_140006893
0x14000686a  mov     rcx, [rbx+60h]; Lookaside
0x14000686e  mov     rdx, rbx; Entry
0x140006871  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006878  nop     dword ptr [rax+rax+00h]
0x14000687d  jmp     short loc_140006893
0x14000687f  mov     edx, 69706E56h; Tag
0x140006884  mov     rcx, rbx; P
0x140006887  call    cs:__imp_ExFreePoolWithTag
0x14000688e  nop     dword ptr [rax+rax+00h]
0x140006893  mov     eax, esi
0x140006895  add     rsp, 38h
0x140006899  pop     r14
0x14000689b  pop     r13
0x14000689d  pop     rdi
0x14000689e  pop     rsi
0x14000689f  pop     rbp
0x1400068a0  pop     rbx
0x1400068a1  retn
```
