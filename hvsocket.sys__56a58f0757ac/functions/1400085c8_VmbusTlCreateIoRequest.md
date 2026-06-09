# VmbusTlCreateIoRequest

- ea: `0x1400085c8`
- end: `0x14000876d`
- name: `VmbusTlCreateIoRequest`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140007b00`

## callees

- `0x140001418`
- `0x1400085c8`
- `0x140008774`
- `0x140009cf8`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400086ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400086ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400086e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400086e9`

## string_xrefs

- `0x140008614`: `Failed to create IoLookAsideList.`
- `0x140008647`: `Failed to create IRP.`
- `0x140008656`: `VmbusTlCreateIoRequest`
- `0x140008693`: `VmbusTlCreateIoRequest`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateIoRequest(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  PVOID v10; // rbx
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  void (__fastcall *v14)(PVOID); // rax
  _QWORD *v15; // rdx
  __int64 v16; // rcx
  signed __int64 v17; // rax
  PVOID Entry; // [rsp+48h] [rbp+10h] BYREF
  __int64 v20; // [rsp+58h] [rbp+20h] BYREF

  v20 = 0;
  Entry = 0;
  v5 = VmbusTlCreateObjectFromLookasideList(2, a2 + 192, &Entry);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_8;
    v7 = "Failed to create IoLookAsideList.";
    v8 = (unsigned int)v5;
    v9 = 121;
    goto LABEL_7;
  }
  v6 = VmbusTlCreateIrp(a1, &v20);
  if ( (v6 & 0x80000000) == 0 )
  {
    v15 = Entry;
    v16 = v20;
    *((_QWORD *)Entry + 10) = VmbusTlIoRequestDestructor;
    v15[28] = *(_QWORD *)(v16 + 96);
    v15[29] = v16;
    v17 = _InterlockedIncrement64(&VmbusTlIoRequestId);
    *a3 = v15;
    v15[30] = v17;
    v15[14] = v15 + 13;
    v15[13] = v15 + 13;
    return v6;
  }
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v7 = "Failed to create IRP.";
    v8 = v6;
    v9 = 129;
LABEL_7:
    HvsocketTraceError("VmbusTlCreateIoRequest", v9, v8, v7);
  }
LABEL_8:
  v10 = Entry;
  if ( Entry )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlCreateIoRequest",
        147,
        (_DWORD)Entry,
        *((_QWORD *)Entry + 1),
        (__int64)"Dereference object");
    v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)v10 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v12 = v11 <= 1;
    v13 = v11 - 1;
    if ( v12 )
    {
      if ( v13 )
        __fastfail(0xEu);
      v14 = (void (__fastcall *)(PVOID))*((_QWORD *)v10 + 10);
      if ( v14 )
        v14(v10);
      if ( *((_DWORD *)v10 + 22) == 1 )
      {
        ExFreePoolWithTag(v10, 0x69706E56u);
      }
      else if ( *((_DWORD *)v10 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 12), v10);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1400085c8  mov     rax, rsp
0x1400085cb  mov     [rax+8], rbx
0x1400085cf  mov     [rax+18h], rsi
0x1400085d3  push    rdi
0x1400085d4  sub     rsp, 30h
0x1400085d8  mov     rsi, r8
0x1400085db  mov     qword ptr [rax+20h], 0
0x1400085e3  mov     rbx, rcx
0x1400085e6  mov     qword ptr [rax+10h], 0
0x1400085ee  lea     r8, [rax+10h]
0x1400085f2  mov     ecx, 2
0x1400085f7  add     rdx, 0C0h
0x1400085fe  call    VmbusTlCreateObjectFromLookasideList
0x140008603  mov     edi, eax
0x140008605  test    eax, eax
0x140008607  jns     short loc_140008625
0x140008609  mov     ecx, cs:dword_140013058
0x14000860f  cmp     ecx, 2
0x140008612  jbe     short loc_140008662
0x140008614  lea     r9, aFailedToCreate_0; "Failed to create IoLookAsideList."
0x14000861b  mov     r8d, eax
0x14000861e  mov     edx, 79h ; 'y'
0x140008623  jmp     short loc_140008656
0x140008625  lea     rdx, [rsp+38h+arg_18]
0x14000862a  mov     rcx, rbx
0x14000862d  call    VmbusTlCreateIrp
0x140008632  mov     edi, eax
0x140008634  test    eax, eax
0x140008636  jns     loc_14000870D
0x14000863c  mov     eax, cs:dword_140013058
0x140008642  cmp     eax, 2
0x140008645  jbe     short loc_140008662
0x140008647  lea     r9, aFailedToCreate; "Failed to create IRP."
0x14000864e  mov     r8d, edi
0x140008651  mov     edx, 81h
0x140008656  lea     rcx, aVmbustlcreatei_0; "VmbusTlCreateIoRequest"
0x14000865d  call    HvsocketTraceError
0x140008662  mov     rbx, [rsp+38h+Entry]
0x140008667  test    rbx, rbx
0x14000866a  jz      loc_14000875A
0x140008670  mov     eax, cs:dword_140013058
0x140008676  cmp     eax, 5
0x140008679  jbe     short loc_14000869F
0x14000867b  mov     r9, [rbx+8]
0x14000867f  lea     rax, aDereferenceObj; "Dereference object"
0x140008686  mov     r8, rbx
0x140008689  mov     [rsp+38h+var_18], rax
0x14000868e  mov     edx, 93h
0x140008693  lea     rcx, aVmbustlcreatei_0; "VmbusTlCreateIoRequest"
0x14000869a  call    HvsocketTraceReferenceCount
0x14000869f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400086a3  lock xadd [rbx+8], rax
0x1400086a9  sub     rax, 1
0x1400086ad  jg      loc_14000875A
0x1400086b3  test    rax, rax
0x1400086b6  jz      short loc_1400086C4
0x1400086b8  mov     ecx, 0Eh
0x1400086bd  int     29h; Win8: RtlFailFast(ecx)
0x1400086bf  jmp     loc_14000875A
0x1400086c4  mov     rax, [rbx+50h]
0x1400086c8  test    rax, rax
0x1400086cb  jz      short loc_1400086D5
0x1400086cd  mov     rcx, rbx
0x1400086d0  call    _guard_dispatch_icall
0x1400086d5  mov     ecx, [rbx+58h]
0x1400086d8  sub     ecx, 1
0x1400086db  jz      short loc_1400086F7
0x1400086dd  cmp     ecx, 1
0x1400086e0  jnz     short loc_14000875A
0x1400086e2  mov     rcx, [rbx+60h]; Lookaside
0x1400086e6  mov     rdx, rbx; Entry
0x1400086e9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400086f0  nop     dword ptr [rax+rax+00h]
0x1400086f5  jmp     short loc_14000875A
0x1400086f7  mov     edx, 69706E56h; Tag
0x1400086fc  mov     rcx, rbx; P
0x1400086ff  call    cs:__imp_ExFreePoolWithTag
0x140008706  nop     dword ptr [rax+rax+00h]
0x14000870b  jmp     short loc_14000875A
0x14000870d  mov     rdx, [rsp+38h+Entry]
0x140008712  lea     rax, VmbusTlIoRequestDestructor
0x140008719  mov     rcx, [rsp+38h+arg_18]
0x14000871e  mov     [rdx+50h], rax
0x140008722  mov     rax, [rcx+60h]
0x140008726  mov     [rdx+0E0h], rax
0x14000872d  mov     eax, 1
0x140008732  mov     [rdx+0E8h], rcx
0x140008739  lock xadd cs:VmbusTlIoRequestId, rax
0x140008742  inc     rax
0x140008745  mov     [rsi], rdx
0x140008748  mov     [rdx+0F0h], rax
0x14000874f  lea     rax, [rdx+68h]
0x140008753  mov     [rax+8], rax
0x140008757  mov     [rax], rax
0x14000875a  mov     rbx, [rsp+38h+arg_0]
0x14000875f  mov     eax, edi
0x140008761  mov     rsi, [rsp+38h+arg_10]
0x140008766  add     rsp, 30h
0x14000876a  pop     rdi
0x14000876b  retn
```
