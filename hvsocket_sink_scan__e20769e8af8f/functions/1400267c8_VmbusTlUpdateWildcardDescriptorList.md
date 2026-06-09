# VmbusTlUpdateWildcardDescriptorList

- ea: `0x1400267c8`
- end: `0x140026b80`
- name: `VmbusTlUpdateWildcardDescriptorList`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001b140`

## callees

- `0x140009cf8`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000bdd4`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140026694`
- `0x1400267c8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026b2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026b2f`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400268b4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400268b4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026b23`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026aef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026919`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026919`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400269ec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026a90`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400269ec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026a90`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026929`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026929`

## string_xrefs

- `0x140026b51`: `Invalid wildcard descriptor list size.`
- `0x14002698e`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026a0b`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026a42`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026ad1`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026b60`: `VmbusTlUpdateWildcardDescriptorList`
- `0x140026901`: `Invalid service ID found.`

## pseudocode

```c
__int64 __fastcall VmbusTlUpdateWildcardDescriptorList(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r9
  char *v10; // rbx
  __int64 *v11; // rcx
  PNPAGED_LOOKASIDE_LIST **v12; // rdi
  PNPAGED_LOOKASIDE_LIST *v13; // rsi
  PNPAGED_LOOKASIDE_LIST *v14; // rbx
  PNPAGED_LOOKASIDE_LIST v15; // rcx
  PNPAGED_LOOKASIDE_LIST **v16; // rdx
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(PNPAGED_LOOKASIDE_LIST *); // rax
  signed __int64 v21; // rax
  signed __int64 v22; // rax
  void (__fastcall *v23)(char *); // rax
  __int64 i; // [rsp+30h] [rbp-18h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-10h]
  PVOID Entry; // [rsp+98h] [rbp+50h] BYREF

  Entry = 0;
  if ( a2 && a3 && (v5 = a3 / 0x18uLL, a3 == 24 * v5) )
  {
    v6 = 0;
    v26 = &i;
    for ( i = (__int64)&i; (unsigned int)v6 < (unsigned int)v5; v6 = (unsigned int)(v6 + 1) )
    {
      if ( !memcmp((const void *)(a2 + 24 * v6), &HV_GUID_BROADCAST, 0x10u)
        || !memcmp((const void *)(a2 + 24 * v6), &HV_GUID_ZERO, 0x10u) )
      {
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceMessage("Invalid service ID found.", a2 + 24 * v6);
      }
      else
      {
        v8 = VmbusTlCreateWildcardDescriptor(a2 + 24 * v6, &Entry);
        if ( v8 < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceGuidError("VmbusTlUpdateWildcardDescriptorList", 171, (unsigned int)v8, a2 + 24 * v6);
          return (unsigned int)v8;
        }
        v10 = (char *)Entry;
        LOBYTE(v9) = 1;
        LOBYTE(v7) = 1;
        v8 = SeCaptureSecurityDescriptor(*(_QWORD *)(a2 + 24 * v6 + 16), v7, 1, v9, (char *)Entry + 128);
        if ( v8 < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceGuidError("VmbusTlUpdateWildcardDescriptorList", 185, (unsigned int)v8, a2 + 24 * v6);
          if ( (unsigned int)dword_140013058 > 5 )
            HvsocketTraceReferenceCount(
              (unsigned int)"VmbusTlUpdateWildcardDescriptorList",
              190,
              (_DWORD)v10,
              *((_QWORD *)v10 + 1),
              (__int64)"Dereference object");
          v21 = _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 1, 0xFFFFFFFFFFFFFFFFuLL);
          v18 = v21 <= 1;
          v22 = v21 - 1;
          if ( v18 )
          {
            if ( v22 )
              __fastfail(0xEu);
            v23 = (void (__fastcall *)(char *))*((_QWORD *)v10 + 10);
            if ( v23 )
              v23(v10);
            if ( *((_DWORD *)v10 + 22) == 1 )
            {
              ExFreePoolWithTag(v10, 0x69706E56u);
            }
            else if ( *((_DWORD *)v10 + 22) == 2 )
            {
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 12), v10);
            }
          }
          return (unsigned int)v8;
        }
        v11 = v26;
        if ( (__int64 *)*v26 != &i )
LABEL_44:
          __fastfail(3u);
        *((_QWORD *)v10 + 13) = v26;
        *((_QWORD *)v10 + 12) = &i;
        *v11 = (__int64)(v10 + 96);
        v26 = (__int64 *)(v10 + 96);
      }
    }
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v12 = (PNPAGED_LOOKASIDE_LIST **)(a1 + 1416);
    while ( 1 )
    {
      v13 = *v12;
      if ( *v12 == (PNPAGED_LOOKASIDE_LIST *)v12 )
        break;
      v14 = v13 - 12;
      v15 = *v13;
      if ( (PNPAGED_LOOKASIDE_LIST *)(*v13)->L.ListHead.Region != v13 )
        goto LABEL_44;
      v16 = (PNPAGED_LOOKASIDE_LIST **)v13[1];
      if ( *v16 != v13 )
        goto LABEL_44;
      *v16 = (PNPAGED_LOOKASIDE_LIST *)v15;
      v15->L.ListHead.Region = (ULONGLONG)v16;
      v13[1] = (PNPAGED_LOOKASIDE_LIST)v13;
      *v13 = (PNPAGED_LOOKASIDE_LIST)v13;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlUpdateWildcardDescriptorList",
          214,
          (_DWORD)v13 - 96,
          (unsigned int)v14[1],
          (__int64)"Dereference object");
      v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)v14 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v18 = v17 <= 1;
      v19 = v17 - 1;
      if ( v18 )
      {
        if ( v19 )
          __fastfail(0xEu);
        v20 = (void (__fastcall *)(PNPAGED_LOOKASIDE_LIST *))v14[10];
        if ( v20 )
          v20(v13 - 12);
        if ( *((_DWORD *)v14 + 22) == 1 )
        {
          ExFreePoolWithTag(v13 - 12, 0x69706E56u);
        }
        else if ( *((_DWORD *)v14 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*v13, v13 - 12);
        }
      }
    }
    DvAppendList(a1 + 1416, &i);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError(
        "VmbusTlUpdateWildcardDescriptorList",
        141,
        3221225485LL,
        "Invalid wildcard descriptor list size.");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400267c8  push    rbp
0x1400267ca  push    rbx
0x1400267cb  push    rsi
0x1400267cc  push    rdi
0x1400267cd  push    r12
0x1400267cf  push    r13
0x1400267d1  push    r14
0x1400267d3  push    r15
0x1400267d5  mov     rbp, rsp
0x1400267d8  sub     rsp, 48h
0x1400267dc  mov     [rbp+Entry], 0
0x1400267e4  mov     r12, rdx
0x1400267e7  mov     r13, rcx
0x1400267ea  test    rdx, rdx
0x1400267ed  jz      loc_140026B41
0x1400267f3  test    r8d, r8d
0x1400267f6  jz      loc_140026B41
0x1400267fc  mov     r8d, r8d
0x1400267ff  mov     rax, 0AAAAAAAAAAAAAAABh
0x140026809  mul     r8
0x14002680c  mov     r14, rdx
0x14002680f  shr     r14, 4
0x140026813  lea     rax, [r14+r14*2]
0x140026817  shl     rax, 3
0x14002681b  cmp     r8, rax
0x14002681e  jnz     loc_140026B41
0x140026824  lea     rax, [rbp+var_18]
0x140026828  xor     r15d, r15d
0x14002682b  mov     [rbp+var_10], rax
0x14002682f  lea     rax, [rbp+var_18]
0x140026833  mov     [rbp+var_18], rax
0x140026837  test    r14d, r14d
0x14002683a  jz      loc_140026919
0x140026840  lea     rcx, [r15+r15*2]
0x140026844  mov     r8d, 10h; Size
0x14002684a  lea     rsi, [r12+rcx*8]
0x14002684e  mov     rcx, rsi; Buf1
0x140026851  lea     rdx, HV_GUID_BROADCAST; Buf2
0x140026858  call    memcmp
0x14002685d  test    eax, eax
0x14002685f  jz      loc_1400268F3
0x140026865  mov     r8d, 10h; Size
0x14002686b  lea     rdx, HV_GUID_ZERO; Buf2
0x140026872  mov     rcx, rsi; Buf1
0x140026875  call    memcmp
0x14002687a  test    eax, eax
0x14002687c  jz      short loc_1400268F3
0x14002687e  lea     rdx, [rbp+Entry]
0x140026882  mov     rcx, rsi
0x140026885  call    VmbusTlCreateWildcardDescriptor
0x14002688a  mov     edi, eax
0x14002688c  test    eax, eax
0x14002688e  js      loc_140026AC3
0x140026894  mov     rbx, [rbp+Entry]
0x140026898  mov     r8d, 1
0x14002689e  mov     rcx, [rsi+10h]
0x1400268a2  mov     r9b, 1
0x1400268a5  mov     dl, r8b
0x1400268a8  lea     rax, [rbx+80h]
0x1400268af  mov     [rsp+48h+var_28], rax
0x1400268b4  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400268bb  nop     dword ptr [rax+rax+00h]
0x1400268c0  mov     edi, eax
0x1400268c2  test    eax, eax
0x1400268c4  js      loc_1400269FD
0x1400268ca  mov     rcx, [rbp+var_10]
0x1400268ce  lea     rax, [rbp+var_18]
0x1400268d2  cmp     [rcx], rax
0x1400268d5  jnz     loc_140026B0C
0x1400268db  lea     rax, [rbx+60h]
0x1400268df  mov     [rax+8], rcx
0x1400268e3  lea     rdx, [rbp+var_18]
0x1400268e7  mov     [rax], rdx
0x1400268ea  mov     [rcx], rax
0x1400268ed  mov     [rbp+var_10], rax
0x1400268f1  jmp     short loc_14002690D
0x1400268f3  mov     eax, cs:dword_140013058
0x1400268f9  cmp     eax, 4
0x1400268fc  jbe     short loc_14002690D
0x1400268fe  mov     rdx, rsi
0x140026901  lea     rcx, aInvalidService; "Invalid service ID found."
0x140026908  call    HvsocketTraceMessage
0x14002690d  inc     r15d
0x140026910  cmp     r15d, r14d
0x140026913  jb      loc_140026840
0x140026919  call    cs:__imp_KeEnterCriticalRegion
0x140026920  nop     dword ptr [rax+rax+00h]
0x140026925  lea     rcx, [r13+10h]; FastMutex
0x140026929  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026930  nop     dword ptr [rax+rax+00h]
0x140026935  lea     rdi, [r13+588h]
0x14002693c  lea     r15, aDereferenceObj; "Dereference object"
0x140026943  mov     rsi, [rdi]
0x140026946  cmp     rsi, rdi
0x140026949  jz      loc_140026B13
0x14002694f  lea     rbx, [rsi-60h]
0x140026953  lea     rax, [rbx+60h]
0x140026957  mov     rcx, [rax]
0x14002695a  cmp     [rcx+8], rax
0x14002695e  jnz     loc_140026B0C
0x140026964  mov     rdx, [rax+8]
0x140026968  cmp     [rdx], rax
0x14002696b  jnz     loc_140026B0C
0x140026971  mov     [rdx], rcx
0x140026974  mov     [rcx+8], rdx
0x140026978  mov     [rax+8], rax
0x14002697c  mov     [rax], rax
0x14002697f  mov     eax, cs:dword_140013058
0x140026985  cmp     eax, 5
0x140026988  jbe     short loc_1400269A7
0x14002698a  mov     r9, [rbx+8]
0x14002698e  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026995  mov     r8, rbx
0x140026998  mov     [rsp+48h+var_28], r15
0x14002699d  mov     edx, 0D6h
0x1400269a2  call    HvsocketTraceReferenceCount
0x1400269a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400269ab  lock xadd [rbx+8], rax
0x1400269b1  sub     rax, 1
0x1400269b5  jg      short loc_140026943
0x1400269b7  test    rax, rax
0x1400269ba  jnz     loc_140026B00
0x1400269c0  mov     rax, [rbx+50h]
0x1400269c4  test    rax, rax
0x1400269c7  jz      short loc_1400269D1
0x1400269c9  mov     rcx, rbx
0x1400269cc  call    _guard_dispatch_icall
0x1400269d1  mov     edx, [rbx+58h]
0x1400269d4  sub     edx, 1
0x1400269d7  jz      loc_140026AE7
0x1400269dd  cmp     edx, 1
0x1400269e0  jnz     loc_140026943
0x1400269e6  mov     rcx, [rsi]; Lookaside
0x1400269e9  mov     rdx, rbx; Entry
0x1400269ec  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400269f3  nop     dword ptr [rax+rax+00h]
0x1400269f8  jmp     loc_140026943
0x1400269fd  mov     eax, cs:dword_140013058
0x140026a03  cmp     eax, 2
0x140026a06  jbe     short loc_140026A1F
0x140026a08  mov     r9, rsi
0x140026a0b  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026a12  mov     r8d, edi
0x140026a15  mov     edx, 0B9h
0x140026a1a  call    HvsocketTraceGuidError
0x140026a1f  mov     eax, cs:dword_140013058
0x140026a25  cmp     eax, 5
0x140026a28  jbe     short loc_140026A4E
0x140026a2a  mov     r9, [rbx+8]
0x140026a2e  lea     r15, aDereferenceObj; "Dereference object"
0x140026a35  mov     r8, rbx
0x140026a38  mov     [rsp+48h+var_28], r15
0x140026a3d  mov     edx, 0BEh
0x140026a42  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026a49  call    HvsocketTraceReferenceCount
0x140026a4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026a52  lock xadd [rbx+8], rax
0x140026a58  sub     rax, 1
0x140026a5c  jg      loc_140026B3D
0x140026a62  test    rax, rax
0x140026a65  jnz     short loc_140026ABA
0x140026a67  mov     rax, [rbx+50h]
0x140026a6b  test    rax, rax
0x140026a6e  jz      short loc_140026A78
0x140026a70  mov     rcx, rbx
0x140026a73  call    _guard_dispatch_icall
0x140026a78  mov     ecx, [rbx+58h]
0x140026a7b  sub     ecx, 1
0x140026a7e  jz      short loc_140026AA1
0x140026a80  cmp     ecx, 1
0x140026a83  jnz     loc_140026B3D
0x140026a89  mov     rcx, [rbx+60h]; Lookaside
0x140026a8d  mov     rdx, rbx; Entry
0x140026a90  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026a97  nop     dword ptr [rax+rax+00h]
0x140026a9c  jmp     loc_140026B3D
0x140026aa1  mov     edx, 69706E56h; Tag
0x140026aa6  mov     rcx, rbx; P
0x140026aa9  call    cs:__imp_ExFreePoolWithTag
0x140026ab0  nop     dword ptr [rax+rax+00h]
0x140026ab5  jmp     loc_140026B3D
0x140026aba  mov     ecx, 0Eh
0x140026abf  int     29h; Win8: RtlFailFast(ecx)
0x140026ac1  jmp     short loc_140026B3D
0x140026ac3  mov     eax, cs:dword_140013058
0x140026ac9  cmp     eax, 2
0x140026acc  jbe     short loc_140026B3D
0x140026ace  mov     r9, rsi
0x140026ad1  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026ad8  mov     r8d, edi
0x140026adb  mov     edx, 0ABh
0x140026ae0  call    HvsocketTraceGuidError
0x140026ae5  jmp     short loc_140026B3D
0x140026ae7  mov     edx, 69706E56h; Tag
0x140026aec  mov     rcx, rbx; P
0x140026aef  call    cs:__imp_ExFreePoolWithTag
0x140026af6  nop     dword ptr [rax+rax+00h]
0x140026afb  jmp     loc_140026943
0x140026b00  mov     ecx, 0Eh
0x140026b05  int     29h; Win8: RtlFailFast(ecx)
0x140026b07  jmp     loc_140026943
0x140026b0c  mov     ecx, 3
0x140026b11  int     29h; Win8: RtlFailFast(ecx)
0x140026b13  lea     rdx, [rbp+var_18]
0x140026b17  mov     rcx, rdi
0x140026b1a  call    DvAppendList
0x140026b1f  lea     rcx, [r13+10h]; FastMutex
0x140026b23  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026b2a  nop     dword ptr [rax+rax+00h]
0x140026b2f  call    cs:__imp_KeLeaveCriticalRegion
0x140026b36  nop     dword ptr [rax+rax+00h]
0x140026b3b  xor     edi, edi
0x140026b3d  mov     eax, edi
0x140026b3f  jmp     short loc_140026B6E
0x140026b41  mov     ecx, cs:dword_140013058
0x140026b47  mov     ebx, 0C000000Dh
0x140026b4c  cmp     ecx, 2
0x140026b4f  jbe     short loc_140026B6C
0x140026b51  lea     r9, aInvalidWildcar; "Invalid wildcard descriptor list size."
0x140026b58  mov     r8d, ebx
0x140026b5b  mov     edx, 8Dh
0x140026b60  lea     rcx, aVmbustlupdatew; "VmbusTlUpdateWildcardDescriptorList"
0x140026b67  call    HvsocketTraceError
0x140026b6c  mov     eax, ebx
0x140026b6e  add     rsp, 48h
0x140026b72  pop     r15
0x140026b74  pop     r14
0x140026b76  pop     r13
0x140026b78  pop     r12
0x140026b7a  pop     rdi
0x140026b7b  pop     rsi
0x140026b7c  pop     rbx
0x140026b7d  pop     rbp
0x140026b7e  retn
```
