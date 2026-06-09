# VmbusTlProviderCancel

- ea: `0x1400209c0`
- end: `0x140020b6b`
- name: `VmbusTlProviderCancel`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001fa0`
- `0x1400058d0`
- `0x1400073d0`
- `0x140009834`
- `0x140009cf8`
- `0x14000a048`
- `0x14000bfe0`
- `0x1400209c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020aae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020aae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020a98`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020a98`

## pseudocode

```c
__int64 __fastcall VmbusTlProviderCancel(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rax
  void (__fastcall *v6)(__int64); // rax
  __int64 v7; // rax

  v2 = *(_QWORD *)(a2 + 16);
  if ( v2 )
  {
    if ( (int)VmbusTlStartCancelConnection(a1, *(_QWORD *)(a2 + 16)) < 0 )
    {
      if ( *(_QWORD *)a2 )
        (*(void (__fastcall **)(_QWORD, __int64))a2)(*(_QWORD *)(a2 + 8), 3221225473LL);
    }
    else
    {
      VmbusTlCommonCancelConnection((PVOID)v2);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlProviderCancel",
          801,
          v2,
          *(_QWORD *)(v2 + 8),
          (__int64)"Dereference object");
      v5 = _InterlockedDecrement64((volatile signed __int64 *)(v2 + 8));
      if ( v5 <= 0 )
      {
        if ( v5 )
          __fastfail(0xEu);
        v6 = *(void (__fastcall **)(__int64))(v2 + 80);
        if ( v6 )
          v6(v2);
        if ( *(_DWORD *)(v2 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v2, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v2 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v2 + 96), (PVOID)v2);
        }
      }
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlProviderCancel",
          802,
          v2,
          *(_QWORD *)(v2 + 304),
          (__int64)"Cancel reference. (deref)");
      v7 = _InterlockedDecrement64((volatile signed __int64 *)(v2 + 304));
      if ( v7 <= 0 )
      {
        if ( v7 )
          __fastfail(0xEu);
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", v2, 9);
        VmbusTlQueueEndpointAction(v2, v2 + 200, 9, 0);
      }
    }
    return 259;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlProviderCancel", 790, 3221225485LL, "Missing context.");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400209c0  mov     [rsp+arg_0], rbx
0x1400209c5  push    rdi
0x1400209c6  sub     rsp, 30h
0x1400209ca  mov     rbx, [rdx+10h]
0x1400209ce  mov     rdi, rdx
0x1400209d1  test    rbx, rbx
0x1400209d4  jnz     short loc_140020A08
0x1400209d6  mov     ecx, cs:dword_140013058
0x1400209dc  mov     ebx, 0C000000Dh
0x1400209e1  cmp     ecx, 2
0x1400209e4  jbe     short loc_140020A01
0x1400209e6  lea     r9, aMissingContext; "Missing context."
0x1400209ed  mov     r8d, ebx
0x1400209f0  mov     edx, 316h
0x1400209f5  lea     rcx, aVmbustlprovide_2; "VmbusTlProviderCancel"
0x1400209fc  call    HvsocketTraceError
0x140020a01  mov     eax, ebx
0x140020a03  jmp     loc_140020B5F
0x140020a08  mov     rdx, rbx
0x140020a0b  call    VmbusTlStartCancelConnection
0x140020a10  test    eax, eax
0x140020a12  js      loc_140020B44
0x140020a18  xor     r8d, r8d
0x140020a1b  mov     rdx, rdi
0x140020a1e  mov     rcx, rbx
0x140020a21  call    VmbusTlCommonCancelConnection
0x140020a26  mov     eax, cs:dword_140013058
0x140020a2c  cmp     eax, 5
0x140020a2f  jbe     short loc_140020A55
0x140020a31  mov     r9, [rbx+8]
0x140020a35  lea     rax, aDereferenceObj; "Dereference object"
0x140020a3c  mov     r8, rbx
0x140020a3f  mov     [rsp+38h+var_18], rax
0x140020a44  mov     edx, 321h
0x140020a49  lea     rcx, aVmbustlprovide_2; "VmbusTlProviderCancel"
0x140020a50  call    HvsocketTraceReferenceCount
0x140020a55  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140020a59  mov     rax, rdi
0x140020a5c  lock xadd [rbx+8], rax
0x140020a62  add     rax, rdi
0x140020a65  test    rax, rax
0x140020a68  jg      short loc_140020ABA
0x140020a6a  jz      short loc_140020A73
0x140020a6c  lea     ecx, [rdi+0Fh]
0x140020a6f  int     29h; Win8: RtlFailFast(ecx)
0x140020a71  jmp     short loc_140020ABA
0x140020a73  mov     rax, [rbx+50h]
0x140020a77  test    rax, rax
0x140020a7a  jz      short loc_140020A84
0x140020a7c  mov     rcx, rbx
0x140020a7f  call    _guard_dispatch_icall
0x140020a84  mov     ecx, [rbx+58h]
0x140020a87  sub     ecx, 1
0x140020a8a  jz      short loc_140020AA6
0x140020a8c  cmp     ecx, 1
0x140020a8f  jnz     short loc_140020ABA
0x140020a91  mov     rcx, [rbx+60h]; Lookaside
0x140020a95  mov     rdx, rbx; Entry
0x140020a98  call    cs:__imp_ExFreeToNPagedLookasideList
0x140020a9f  nop     dword ptr [rax+rax+00h]
0x140020aa4  jmp     short loc_140020ABA
0x140020aa6  mov     edx, 69706E56h; Tag
0x140020aab  mov     rcx, rbx; P
0x140020aae  call    cs:__imp_ExFreePoolWithTag
0x140020ab5  nop     dword ptr [rax+rax+00h]
0x140020aba  mov     eax, cs:dword_140013058
0x140020ac0  cmp     eax, 5
0x140020ac3  jbe     short loc_140020AEC
0x140020ac5  mov     r9, [rbx+130h]
0x140020acc  lea     rax, aCancelReferenc_0; "Cancel reference. (deref)"
0x140020ad3  mov     r8, rbx
0x140020ad6  mov     [rsp+38h+var_18], rax
0x140020adb  mov     edx, 322h
0x140020ae0  lea     rcx, aVmbustlprovide_2; "VmbusTlProviderCancel"
0x140020ae7  call    HvsocketTraceReferenceCount
0x140020aec  mov     rax, rdi
0x140020aef  lock xadd [rbx+130h], rax
0x140020af8  add     rax, rdi
0x140020afb  test    rax, rax
0x140020afe  jg      short loc_140020B5A
0x140020b00  jz      short loc_140020B0B
0x140020b02  mov     ecx, 0Eh
0x140020b07  int     29h; Win8: RtlFailFast(ecx)
0x140020b09  jmp     short loc_140020B5A
0x140020b0b  mov     eax, cs:dword_140013058
0x140020b11  mov     edi, 9
0x140020b16  cmp     eax, 4
0x140020b19  jbe     short loc_140020B2D
0x140020b1b  mov     r8d, edi
0x140020b1e  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140020b25  mov     rdx, rbx
0x140020b28  call    HvsocketTraceEndpointEvent
0x140020b2d  lea     rdx, [rbx+0C8h]
0x140020b34  xor     r9d, r9d
0x140020b37  mov     r8d, edi
0x140020b3a  mov     rcx, rbx
0x140020b3d  call    VmbusTlQueueEndpointAction
0x140020b42  jmp     short loc_140020B5A
0x140020b44  mov     rax, [rdi]
0x140020b47  test    rax, rax
0x140020b4a  jz      short loc_140020B5A
0x140020b4c  mov     rcx, [rdi+8]
0x140020b50  mov     edx, 0C0000001h
0x140020b55  call    _guard_dispatch_icall
0x140020b5a  mov     eax, 103h
0x140020b5f  mov     rbx, [rsp+38h+arg_0]
0x140020b64  add     rsp, 30h
0x140020b68  pop     rdi
0x140020b69  retn
```
