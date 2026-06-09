# VmbusTlEndpointDestructor

- ea: `0x1400056e0`
- end: `0x140005877`
- name: `VmbusTlEndpointDestructor`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140002b78`
- `0x1400056e0`
- `0x140009b84`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x140005753`
- `ntoskrnl!PsReturnPoolQuota` at `0x140005753`
- `ntoskrnl!ObfDereferenceObject` at `0x140005766`
- `ntoskrnl!ObfDereferenceObject` at `0x140005766`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005851`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005851`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000583b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000583b`
- `NETIO!NetioInsertWorkQueue` at `0x1400057b9`
- `NETIO!NetioInsertWorkQueue` at `0x1400057b9`

## pseudocode

```c
PVOID __fastcall VmbusTlEndpointDestructor(__int64 a1)
{
  ULONG_PTR v2; // rdi
  struct _KPROCESS *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rbx
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax
  PVOID result; // rax

  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceEndpointMessage("Destroying endpoint.", a1);
  if ( *(_DWORD *)(a1 + 104) == 1 )
  {
    v2 = 336;
  }
  else
  {
    if ( *(_DWORD *)(a1 + 104) == 2 )
    {
      v2 = 1136;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 104) == 3 )
      {
        v2 = 432;
        goto LABEL_12;
      }
      v2 = 0;
      if ( *(_DWORD *)(a1 + 104) != 2 )
        goto LABEL_12;
    }
    VmbusTlConnectionDestructor(a1);
  }
LABEL_12:
  v3 = *(struct _KPROCESS **)(a1 + 272);
  if ( v3 )
  {
    PsReturnPoolQuota(v3, (POOL_TYPE)512, v2);
    ObfDereferenceObject(*(PVOID *)(a1 + 272));
    _InterlockedAdd64((volatile signed __int64 *)VmbusProviderContext + 161, -(__int64)v2);
    _InterlockedDecrement64((volatile signed __int64 *)VmbusProviderContext + 162);
    *(_QWORD *)(a1 + 272) = 0;
  }
  v4 = *(_QWORD *)(a1 + 112);
  if ( v4 )
  {
    NetioInsertWorkQueue(v4 + 960, *(_QWORD *)(a1 + 192));
    v5 = *(_QWORD *)(a1 + 112);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlEndpointDestructor",
        275,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Dereference object");
    v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = *(void (__fastcall **)(__int64))(v5 + 80);
      if ( v9 )
        v9(v5);
      if ( *(_DWORD *)(v5 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v5 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
      }
    }
  }
  result = VmbusProviderContext;
  _InterlockedIncrement((volatile signed __int32 *)VmbusProviderContext + 288);
  return result;
}

```

## disassembly

```asm
0x1400056e0  mov     [rsp+arg_0], rbx
0x1400056e5  push    rdi
0x1400056e6  sub     rsp, 30h
0x1400056ea  mov     eax, cs:dword_140013058
0x1400056f0  mov     rbx, rcx
0x1400056f3  cmp     eax, 4
0x1400056f6  jbe     short loc_140005707
0x1400056f8  mov     rdx, rcx
0x1400056fb  lea     rcx, aDestroyingEndp; "Destroying endpoint."
0x140005702  call    HvsocketTraceEndpointMessage
0x140005707  mov     edx, [rbx+68h]
0x14000570a  mov     ecx, edx
0x14000570c  sub     ecx, 1
0x14000570f  jz      short loc_14000573A
0x140005711  sub     ecx, 1
0x140005714  jz      short loc_14000572B
0x140005716  cmp     ecx, 1
0x140005719  jz      short loc_140005724
0x14000571b  xor     edi, edi
0x14000571d  cmp     edx, 2
0x140005720  jnz     short loc_14000573F
0x140005722  jmp     short loc_140005730
0x140005724  mov     edi, 1B0h
0x140005729  jmp     short loc_14000573F
0x14000572b  mov     edi, 470h
0x140005730  mov     rcx, rbx
0x140005733  call    VmbusTlConnectionDestructor
0x140005738  jmp     short loc_14000573F
0x14000573a  mov     edi, 150h
0x14000573f  mov     rcx, [rbx+110h]; Process
0x140005746  test    rcx, rcx
0x140005749  jz      short loc_14000579E
0x14000574b  mov     r8, rdi; Amount
0x14000574e  mov     edx, 200h; PoolType
0x140005753  call    cs:__imp_PsReturnPoolQuota
0x14000575a  nop     dword ptr [rax+rax+00h]
0x14000575f  mov     rcx, [rbx+110h]; Object
0x140005766  call    cs:__imp_ObfDereferenceObject
0x14000576d  nop     dword ptr [rax+rax+00h]
0x140005772  mov     rax, cs:VmbusProviderContext
0x140005779  neg     rdi
0x14000577c  lock add [rax+508h], rdi
0x140005784  mov     rax, cs:VmbusProviderContext
0x14000578b  lock dec qword ptr [rax+510h]
0x140005793  mov     qword ptr [rbx+110h], 0
0x14000579e  mov     rcx, [rbx+70h]
0x1400057a2  test    rcx, rcx
0x1400057a5  jz      loc_14000585D
0x1400057ab  mov     rdx, [rbx+0C0h]
0x1400057b2  add     rcx, 3C0h
0x1400057b9  call    cs:__imp_NetioInsertWorkQueue
0x1400057c0  nop     dword ptr [rax+rax+00h]
0x1400057c5  mov     eax, cs:dword_140013058
0x1400057cb  mov     rbx, [rbx+70h]
0x1400057cf  cmp     eax, 5
0x1400057d2  jbe     short loc_1400057F8
0x1400057d4  mov     r9, [rbx+8]
0x1400057d8  lea     rax, aDereferenceObj; "Dereference object"
0x1400057df  mov     r8, rbx
0x1400057e2  mov     [rsp+38h+var_18], rax
0x1400057e7  mov     edx, 113h
0x1400057ec  lea     rcx, aVmbustlendpoin_0; "VmbusTlEndpointDestructor"
0x1400057f3  call    HvsocketTraceReferenceCount
0x1400057f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400057fc  lock xadd [rbx+8], rax
0x140005802  sub     rax, 1
0x140005806  jg      short loc_14000585D
0x140005808  test    rax, rax
0x14000580b  jz      short loc_140005816
0x14000580d  mov     ecx, 0Eh
0x140005812  int     29h; Win8: RtlFailFast(ecx)
0x140005814  jmp     short loc_14000585D
0x140005816  mov     rax, [rbx+50h]
0x14000581a  test    rax, rax
0x14000581d  jz      short loc_140005827
0x14000581f  mov     rcx, rbx
0x140005822  call    _guard_dispatch_icall
0x140005827  mov     ecx, [rbx+58h]
0x14000582a  sub     ecx, 1
0x14000582d  jz      short loc_140005849
0x14000582f  cmp     ecx, 1
0x140005832  jnz     short loc_14000585D
0x140005834  mov     rcx, [rbx+60h]; Lookaside
0x140005838  mov     rdx, rbx; Entry
0x14000583b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005842  nop     dword ptr [rax+rax+00h]
0x140005847  jmp     short loc_14000585D
0x140005849  mov     edx, 69706E56h; Tag
0x14000584e  mov     rcx, rbx; P
0x140005851  call    cs:__imp_ExFreePoolWithTag
0x140005858  nop     dword ptr [rax+rax+00h]
0x14000585d  mov     rax, cs:VmbusProviderContext
0x140005864  lock inc dword ptr [rax+480h]
0x14000586b  mov     rbx, [rsp+38h+arg_0]
0x140005870  add     rsp, 30h
0x140005874  pop     rdi
0x140005875  retn
```
