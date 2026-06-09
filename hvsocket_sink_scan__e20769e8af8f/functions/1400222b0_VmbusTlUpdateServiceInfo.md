# VmbusTlUpdateServiceInfo

- ea: `0x1400222b0`
- end: `0x14002262c`
- name: `VmbusTlUpdateServiceInfo`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14001b200`

## callees

- `0x140008c0c`
- `0x14000969c`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140021cb4`
- `0x1400222b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002260c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002260c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022600`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022600`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002245c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002245c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225c3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400222f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400222f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022446`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400225ad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022446`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400225ad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022305`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022305`

## string_xrefs

- `0x14002236c`: `VmbusTlUpdateServiceInfo: Disabling service.`
- `0x140022400`: `VmbusTlUpdateServiceInfo`
- `0x1400224c0`: `VmbusTlUpdateServiceInfo`
- `0x140022530`: `VmbusTlUpdateServiceInfo`
- `0x140022567`: `VmbusTlUpdateServiceInfo`
- `0x1400223a5`: `VmbusTlUpdateServiceInfo: Removing service.`
- `0x1400224e7`: `VmbusTlUpdateServiceInfo: Service created.`

## pseudocode

```c
__int64 __fastcall VmbusTlUpdateServiceInfo(__int64 a1, PNPAGED_LOOKASIDE_LIST *a2)
{
  int updated; // ebp
  bool v5; // r15
  PNPAGED_LOOKASIDE_LIST *v6; // rsi
  PNPAGED_LOOKASIDE_LIST *i; // r14
  PNPAGED_LOOKASIDE_LIST *v8; // rbx
  char v9; // al
  PNPAGED_LOOKASIDE_LIST v10; // rcx
  PNPAGED_LOOKASIDE_LIST **v11; // rdx
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  void (__fastcall *v15)(PNPAGED_LOOKASIDE_LIST *); // rax
  int v16; // eax
  __int64 v17; // rdx
  char *v18; // rbx
  _DWORD *v19; // r8
  signed __int64 v20; // rax
  signed __int64 v21; // rax
  void (__fastcall *v22)(char *); // rax
  PNPAGED_LOOKASIDE_LIST **v23; // rcx
  PVOID Entry; // [rsp+80h] [rbp+8h] BYREF

  Entry = 0;
  updated = 0;
  v5 = memcmp(a2, &HV_GUID_BROADCAST, 0x10u) == 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v6 = (PNPAGED_LOOKASIDE_LIST *)(a1 + 360);
  for ( i = *(PNPAGED_LOOKASIDE_LIST **)(a1 + 360); i != v6; i = (PNPAGED_LOOKASIDE_LIST *)*i )
  {
    v8 = i - 12;
    Entry = i - 12;
    if ( v5 || v8[14] == *a2 && v8[15] == a2[1] )
    {
      v9 = *((_BYTE *)a2 + 16);
      *((_BYTE *)v8 + 128) = v9;
      if ( !v9 )
      {
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceMessage("VmbusTlUpdateServiceInfo: Disabling service.", v8 + 14);
        VmbusTlCloseServiceEndpoints(i - 12, 0);
        if ( !a2[4] && !a2[3] )
        {
          if ( (unsigned int)dword_140013058 > 4 )
            HvsocketTraceMessage("VmbusTlUpdateServiceInfo: Removing service.", v8 + 14);
          v10 = *i;
          if ( (PNPAGED_LOOKASIDE_LIST *)(*i)->L.ListHead.Region != i )
            goto LABEL_49;
          v11 = (PNPAGED_LOOKASIDE_LIST **)v8[13];
          if ( *v11 != i )
            goto LABEL_49;
          *v11 = (PNPAGED_LOOKASIDE_LIST *)v10;
          v10->L.ListHead.Region = (ULONGLONG)v11;
          i[1] = (PNPAGED_LOOKASIDE_LIST)i;
          *i = (PNPAGED_LOOKASIDE_LIST)i;
          if ( (unsigned int)dword_140013058 > 5 )
            HvsocketTraceReferenceCount(
              (unsigned int)"VmbusTlUpdateServiceInfo",
              1139,
              (_DWORD)i - 96,
              (unsigned int)v8[1],
              (__int64)"Dereference object");
          v12 = _InterlockedExchangeAdd64((volatile signed __int64 *)v8 + 1, 0xFFFFFFFFFFFFFFFFuLL);
          v13 = v12 <= 1;
          v14 = v12 - 1;
          if ( v13 )
          {
            if ( v14 )
              __fastfail(0xEu);
            v15 = (void (__fastcall *)(PNPAGED_LOOKASIDE_LIST *))v8[10];
            if ( v15 )
              v15(i - 12);
            if ( *((_DWORD *)v8 + 22) == 1 )
            {
              ExFreePoolWithTag(i - 12, 0x69706E56u);
            }
            else if ( *((_DWORD *)v8 + 22) == 2 )
            {
              ExFreeToNPagedLookasideList(*i, i - 12);
            }
          }
        }
      }
      if ( !v5 )
        goto LABEL_51;
    }
  }
  if ( !v5 )
  {
    v16 = VmbusTlCreateService(&Entry);
    updated = v16;
    if ( v16 >= 0 )
    {
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceMessage("VmbusTlUpdateServiceInfo: Service created.", a2);
      v18 = (char *)Entry;
      v19 = Entry;
      *((_OWORD *)Entry + 7) = *(_OWORD *)a2;
      v19[39] = 0;
      updated = VmbusTlUpdateService(a2, v17, v19);
      if ( updated >= 0 )
      {
        v23 = *(PNPAGED_LOOKASIDE_LIST ***)(a1 + 368);
        if ( *v23 != v6 )
LABEL_49:
          __fastfail(3u);
        *((_QWORD *)v18 + 12) = v6;
        *((_QWORD *)v18 + 13) = v23;
        *v23 = (PNPAGED_LOOKASIDE_LIST *)(v18 + 96);
        *(_QWORD *)(a1 + 368) = v18 + 96;
      }
      else
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceGuidError("VmbusTlUpdateServiceInfo", 1177, (unsigned int)updated, a2);
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlUpdateServiceInfo",
            1178,
            (_DWORD)v18,
            *((_QWORD *)v18 + 1),
            (__int64)"Dereference object");
        v20 = _InterlockedExchangeAdd64((volatile signed __int64 *)v18 + 1, 0xFFFFFFFFFFFFFFFFuLL);
        v13 = v20 <= 1;
        v21 = v20 - 1;
        if ( v13 )
        {
          if ( v21 )
            __fastfail(0xEu);
          v22 = (void (__fastcall *)(char *))*((_QWORD *)v18 + 10);
          if ( v22 )
            v22(v18);
          if ( *((_DWORD *)v18 + 22) == 1 )
          {
            ExFreePoolWithTag(v18, 0x69706E56u);
          }
          else if ( *((_DWORD *)v18 + 22) == 2 )
          {
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v18 + 12), v18);
          }
        }
      }
    }
    else if ( (unsigned int)dword_140013058 > 2 )
    {
      HvsocketTraceServiceError((unsigned int)"VmbusTlUpdateServiceInfo", 1161, v16, (_DWORD)a2, a1 + 232);
    }
  }
LABEL_51:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400222b0  mov     rax, rsp
0x1400222b3  push    rbx
0x1400222b4  push    rbp
0x1400222b5  push    rsi
0x1400222b6  push    rdi
0x1400222b7  push    r12
0x1400222b9  push    r13
0x1400222bb  push    r14
0x1400222bd  push    r15
0x1400222bf  sub     rsp, 38h
0x1400222c3  mov     rdi, rdx
0x1400222c6  mov     qword ptr [rax+8], 0
0x1400222ce  mov     r13, rcx
0x1400222d1  lea     rdx, HV_GUID_BROADCAST; Buf2
0x1400222d8  xor     ebp, ebp
0x1400222da  mov     rcx, rdi; Buf1
0x1400222dd  xor     bl, bl
0x1400222df  lea     r8d, [rbp+10h]; Size
0x1400222e3  call    memcmp
0x1400222e8  test    eax, eax
0x1400222ea  movzx   r15d, bl
0x1400222ee  lea     ecx, [rbp+1]
0x1400222f1  cmovz   r15d, ecx
0x1400222f5  call    cs:__imp_KeEnterCriticalRegion
0x1400222fc  nop     dword ptr [rax+rax+00h]
0x140022301  lea     rcx, [r13+10h]; FastMutex
0x140022305  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002230c  nop     dword ptr [rax+rax+00h]
0x140022311  lea     rsi, [r13+168h]
0x140022318  mov     r14, [rsi]
0x14002231b  jmp     loc_14002247D
0x140022320  lea     rbx, [r14-60h]
0x140022324  mov     [rsp+78h+Entry], rbx
0x14002232c  test    r15b, r15b
0x14002232f  jnz     short loc_14002234C
0x140022331  mov     rax, [rbx+70h]
0x140022335  cmp     rax, [rdi]
0x140022338  jnz     loc_14002247A
0x14002233e  mov     rax, [rbx+78h]
0x140022342  cmp     rax, [rdi+8]
0x140022346  jnz     loc_14002247A
0x14002234c  mov     al, [rdi+10h]
0x14002234f  mov     [rbx+80h], al
0x140022355  test    al, al
0x140022357  jnz     loc_140022471
0x14002235d  mov     eax, cs:dword_140013058
0x140022363  cmp     eax, 4
0x140022366  jbe     short loc_140022378
0x140022368  lea     rdx, [rbx+70h]
0x14002236c  lea     rcx, aVmbustlupdates_6; "VmbusTlUpdateServiceInfo: Disabling ser"...
0x140022373  call    HvsocketTraceMessage
0x140022378  xor     edx, edx
0x14002237a  mov     rcx, rbx
0x14002237d  call    VmbusTlCloseServiceEndpoints
0x140022382  cmp     [rdi+20h], rbp
0x140022386  jnz     loc_140022471
0x14002238c  cmp     [rdi+18h], rbp
0x140022390  jnz     loc_140022471
0x140022396  mov     eax, cs:dword_140013058
0x14002239c  cmp     eax, 4
0x14002239f  jbe     short loc_1400223B1
0x1400223a1  lea     rdx, [rbx+70h]
0x1400223a5  lea     rcx, aVmbustlupdates_0; "VmbusTlUpdateServiceInfo: Removing serv"...
0x1400223ac  call    HvsocketTraceMessage
0x1400223b1  lea     rax, [rbx+60h]
0x1400223b5  mov     rcx, [rax]
0x1400223b8  cmp     [rcx+8], rax
0x1400223bc  jnz     loc_1400225E3
0x1400223c2  mov     rdx, [rax+8]
0x1400223c6  cmp     [rdx], rax
0x1400223c9  jnz     loc_1400225E3
0x1400223cf  mov     [rdx], rcx
0x1400223d2  mov     [rcx+8], rdx
0x1400223d6  mov     [rax+8], rax
0x1400223da  mov     [rax], rax
0x1400223dd  mov     eax, cs:dword_140013058
0x1400223e3  cmp     eax, 5
0x1400223e6  jbe     short loc_14002240C
0x1400223e8  mov     r9, [rbx+8]
0x1400223ec  lea     rax, aDereferenceObj; "Dereference object"
0x1400223f3  mov     r8, rbx
0x1400223f6  mov     [rsp+78h+var_58], rax
0x1400223fb  mov     edx, 473h
0x140022400  lea     rcx, aVmbustlupdates_3; "VmbusTlUpdateServiceInfo"
0x140022407  call    HvsocketTraceReferenceCount
0x14002240c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022410  lock xadd [rbx+8], rax
0x140022416  sub     rax, 1
0x14002241a  jg      short loc_140022471
0x14002241c  test    rax, rax
0x14002241f  jnz     short loc_14002246A
0x140022421  mov     rax, [rbx+50h]
0x140022425  test    rax, rax
0x140022428  jz      short loc_140022432
0x14002242a  mov     rcx, rbx
0x14002242d  call    _guard_dispatch_icall
0x140022432  mov     ecx, [rbx+58h]
0x140022435  sub     ecx, 1
0x140022438  jz      short loc_140022454
0x14002243a  cmp     ecx, 1
0x14002243d  jnz     short loc_140022471
0x14002243f  mov     rcx, [rbx+60h]; Lookaside
0x140022443  mov     rdx, rbx; Entry
0x140022446  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002244d  nop     dword ptr [rax+rax+00h]
0x140022452  jmp     short loc_140022471
0x140022454  mov     edx, 69706E56h; Tag
0x140022459  mov     rcx, rbx; P
0x14002245c  call    cs:__imp_ExFreePoolWithTag
0x140022463  nop     dword ptr [rax+rax+00h]
0x140022468  jmp     short loc_140022471
0x14002246a  mov     ecx, 0Eh
0x14002246f  int     29h; Win8: RtlFailFast(ecx)
0x140022471  test    r15b, r15b
0x140022474  jz      loc_1400225FC
0x14002247a  mov     r14, [r14]
0x14002247d  cmp     r14, rsi
0x140022480  jnz     loc_140022320
0x140022486  test    r15b, r15b
0x140022489  jnz     loc_1400225FC
0x14002248f  lea     rcx, [rsp+78h+Entry]
0x140022497  call    VmbusTlCreateService
0x14002249c  mov     ebp, eax
0x14002249e  test    eax, eax
0x1400224a0  jns     short loc_1400224D9
0x1400224a2  mov     edx, cs:dword_140013058
0x1400224a8  cmp     edx, 2
0x1400224ab  jbe     loc_1400225FC
0x1400224b1  lea     rdx, [r13+0E8h]
0x1400224b8  mov     r9, rdi
0x1400224bb  mov     [rsp+78h+var_58], rdx
0x1400224c0  lea     rcx, aVmbustlupdates_3; "VmbusTlUpdateServiceInfo"
0x1400224c7  mov     edx, 489h
0x1400224cc  mov     r8d, eax
0x1400224cf  call    HvsocketTraceServiceError
0x1400224d4  jmp     loc_1400225FC
0x1400224d9  mov     eax, cs:dword_140013058
0x1400224df  cmp     eax, 4
0x1400224e2  jbe     short loc_1400224F3
0x1400224e4  mov     rdx, rdi
0x1400224e7  lea     rcx, aVmbustlupdates_1; "VmbusTlUpdateServiceInfo: Service creat"...
0x1400224ee  call    HvsocketTraceMessage
0x1400224f3  mov     rbx, [rsp+78h+Entry]
0x1400224fb  mov     rcx, rdi
0x1400224fe  movups  xmm0, xmmword ptr [rdi]
0x140022501  mov     r8, rbx
0x140022504  movdqu  xmmword ptr [rbx+70h], xmm0
0x140022509  mov     dword ptr [rbx+9Ch], 0
0x140022513  call    VmbusTlUpdateService
0x140022518  mov     ebp, eax
0x14002251a  test    eax, eax
0x14002251c  jns     loc_1400225DA
0x140022522  mov     eax, cs:dword_140013058
0x140022528  cmp     eax, 2
0x14002252b  jbe     short loc_140022544
0x14002252d  mov     r9, rdi
0x140022530  lea     rcx, aVmbustlupdates_3; "VmbusTlUpdateServiceInfo"
0x140022537  mov     r8d, ebp
0x14002253a  mov     edx, 499h
0x14002253f  call    HvsocketTraceGuidError
0x140022544  mov     eax, cs:dword_140013058
0x14002254a  cmp     eax, 5
0x14002254d  jbe     short loc_140022573
0x14002254f  mov     r9, [rbx+8]
0x140022553  lea     rax, aDereferenceObj; "Dereference object"
0x14002255a  mov     r8, rbx
0x14002255d  mov     [rsp+78h+var_58], rax
0x140022562  mov     edx, 49Ah
0x140022567  lea     rcx, aVmbustlupdates_3; "VmbusTlUpdateServiceInfo"
0x14002256e  call    HvsocketTraceReferenceCount
0x140022573  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022577  lock xadd [rbx+8], rax
0x14002257d  sub     rax, 1
0x140022581  jg      short loc_1400225FC
0x140022583  test    rax, rax
0x140022586  jnz     short loc_1400225D1
0x140022588  mov     rax, [rbx+50h]
0x14002258c  test    rax, rax
0x14002258f  jz      short loc_140022599
0x140022591  mov     rcx, rbx
0x140022594  call    _guard_dispatch_icall
0x140022599  mov     ecx, [rbx+58h]
0x14002259c  sub     ecx, 1
0x14002259f  jz      short loc_1400225BB
0x1400225a1  cmp     ecx, 1
0x1400225a4  jnz     short loc_1400225FC
0x1400225a6  mov     rcx, [rbx+60h]; Lookaside
0x1400225aa  mov     rdx, rbx; Entry
0x1400225ad  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400225b4  nop     dword ptr [rax+rax+00h]
0x1400225b9  jmp     short loc_1400225FC
0x1400225bb  mov     edx, 69706E56h; Tag
0x1400225c0  mov     rcx, rbx; P
0x1400225c3  call    cs:__imp_ExFreePoolWithTag
0x1400225ca  nop     dword ptr [rax+rax+00h]
0x1400225cf  jmp     short loc_1400225FC
0x1400225d1  mov     ecx, 0Eh
0x1400225d6  int     29h; Win8: RtlFailFast(ecx)
0x1400225d8  jmp     short loc_1400225FC
0x1400225da  mov     rcx, [rsi+8]
0x1400225de  cmp     [rcx], rsi
0x1400225e1  jz      short loc_1400225EA
0x1400225e3  mov     ecx, 3
0x1400225e8  int     29h; Win8: RtlFailFast(ecx)
0x1400225ea  lea     rax, [rbx+60h]
0x1400225ee  mov     [rax], rsi
0x1400225f1  mov     [rax+8], rcx
0x1400225f5  mov     [rcx], rax
0x1400225f8  mov     [rsi+8], rax
0x1400225fc  lea     rcx, [r13+10h]; FastMutex
0x140022600  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022607  nop     dword ptr [rax+rax+00h]
0x14002260c  call    cs:__imp_KeLeaveCriticalRegion
0x140022613  nop     dword ptr [rax+rax+00h]
0x140022618  mov     eax, ebp
0x14002261a  add     rsp, 38h
0x14002261e  pop     r15
0x140022620  pop     r14
0x140022622  pop     r13
0x140022624  pop     r12
0x140022626  pop     rdi
0x140022627  pop     rsi
0x140022628  pop     rbp
0x140022629  pop     rbx
0x14002262a  retn
```
