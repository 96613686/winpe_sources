# SmbCepDiscardExchange

- ea: `0x140022950`
- end: `0x140022b00`
- name: `SmbCepDiscardExchange`
- size: `432`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003df30`

## callees

- `0x140004360`
- `0x140008e80`
- `0x1400097e0`
- `0x140014400`
- `0x140021130`
- `0x140022950`
- `0x140028230`
- `0x140037eb0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022a61`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140022a61`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400229bf`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400229bf`
- `ntoskrnl!KeBugCheckEx` at `0x1400229a5`
- `ntoskrnl!KeBugCheckEx` at `0x1400229a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a83`

## pseudocode

```c
void __fastcall SmbCepDiscardExchange(unsigned __int64 P)
{
  ULONG_PTR v1; // r14
  unsigned __int16 *v3; // r15
  ULONG_PTR v4; // rdi
  ULONG_PTR v5; // rsi
  __int64 v6; // rbp
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct _LOOKASIDE_LIST_EX *v12; // rdi

  v1 = *(_QWORD *)(P + 72);
  v3 = *(unsigned __int16 **)(P + 80);
  v4 = *(_QWORD *)(P + 88);
  v5 = *(_QWORD *)(P + 96);
  v6 = *(_QWORD *)(v1 + 24);
  SmbCeDissociateExchangeWithCompoundingKey();
  v7 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 2600));
  if ( v7 < 0 )
    KeBugCheckEx(0x27u, 0xA0001u, v6 + 2600, v7, 0);
  if ( !v7 )
    ExUnblockOnAddressPushLockEx(v6 + 2608, 0);
  if ( v4 )
  {
    SmbCeDereferenceVNetRootContext(v4);
  }
  else if ( v3 )
  {
    SmbCeDereferenceSessionEntryEx(v3, 0);
  }
  else
  {
    SmbCeDereferenceServerEntryEx(v1, 0);
  }
  if ( v5 )
    SmbCeDereferenceBindingObject(v5);
  v8 = *(_QWORD *)(P + 472);
  if ( v8 )
    SmbMmFreeSmbBuffer(v8, 1834181464);
  v9 = *(_QWORD *)(P + 480);
  if ( v9 )
    SmbMmFreeSmbBuffer(v9, 1834181464);
  v10 = *(_QWORD *)(P + 488);
  if ( v10 )
    SmbMmFreeSmbBuffer(v10, 1834181464);
  v11 = *(_QWORD *)(P + 496);
  if ( v11 )
    SmbMmFreeSmbBuffer(v11, 1834181464);
  if ( (*(_DWORD *)(P + 68) & 2) == 0 )
  {
    if ( (*(_DWORD *)(P + 68) & 4) != 0 )
    {
      v12 = (struct _LOOKASIDE_LIST_EX *)((char *)SmbMmExchangeLookasideList
                                        + 128 * (unsigned __int64)*(unsigned __int16 *)(P + 34));
      if ( !LOBYTE(v12[3].L.Depth) )
        PplpLazyInitializeLookasideList((__int64)SmbMmExchangeLookasideList, (__int64)&v12[2]);
      ExFreeToLookasideListEx(v12 + 2, (PVOID)(P & 0xFFFFFFFFFFFFF000uLL));
    }
    else
    {
      ExFreePoolWithTag((PVOID)P, 0x6D536358u);
    }
  }
}

```

## disassembly

```asm
0x140022950  push    rbx
0x140022952  push    rbp
0x140022953  push    rsi
0x140022954  push    rdi
0x140022955  push    r14
0x140022957  push    r15
0x140022959  sub     rsp, 38h
0x14002295d  mov     r14, [rcx+48h]
0x140022961  mov     rbx, rcx
0x140022964  mov     r15, [rcx+50h]
0x140022968  mov     rdi, [rcx+58h]
0x14002296c  mov     rsi, [rcx+60h]
0x140022970  mov     rbp, [r14+18h]
0x140022974  call    SmbCeDissociateExchangeWithCompoundingKey
0x140022979  lea     r8, [rbp+0A28h]; BugCheckParameter2
0x140022980  mov     eax, 0FFFFFFFFh
0x140022985  lock xadd [r8], eax
0x14002298a  sub     eax, 1
0x14002298d  jns     short loc_1400229B2
0x14002298f  movsxd  r9, eax; BugCheckParameter3
0x140022992  mov     edx, 0A0001h; BugCheckParameter1
0x140022997  mov     ecx, 27h ; '''; BugCheckCode
0x14002299c  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x1400229a5  call    cs:__imp_KeBugCheckEx
0x1400229b2  test    eax, eax
0x1400229b4  jnz     short loc_1400229CB
0x1400229b6  lea     rcx, [rbp+0A30h]
0x1400229bd  xor     edx, edx
0x1400229bf  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400229c6  nop     dword ptr [rax+rax+00h]
0x1400229cb  test    rdi, rdi
0x1400229ce  jz      loc_140022A9F
0x1400229d4  mov     rcx, rdi; BugCheckParameter2
0x1400229d7  call    SmbCeDereferenceVNetRootContext
0x1400229dc  test    rsi, rsi
0x1400229df  jnz     loc_140022AB7
0x1400229e5  mov     rcx, [rbx+1D8h]
0x1400229ec  test    rcx, rcx
0x1400229ef  jnz     loc_140022AC4
0x1400229f5  mov     rcx, [rbx+1E0h]
0x1400229fc  test    rcx, rcx
0x1400229ff  jnz     loc_140022AD3
0x140022a05  mov     rcx, [rbx+1E8h]
0x140022a0c  test    rcx, rcx
0x140022a0f  jnz     loc_140022AE2
0x140022a15  mov     rcx, [rbx+1F0h]
0x140022a1c  test    rcx, rcx
0x140022a1f  jnz     loc_140022AF1
0x140022a25  mov     eax, [rbx+44h]
0x140022a28  test    al, 2
0x140022a2a  jnz     short loc_140022A6D
0x140022a2c  mov     eax, [rbx+44h]
0x140022a2f  test    al, 4
0x140022a31  jz      short loc_140022A7B
0x140022a33  movzx   edi, word ptr [rbx+22h]
0x140022a37  mov     rcx, cs:SmbMmExchangeLookasideList
0x140022a3e  shl     rdi, 7
0x140022a42  add     rdi, rcx
0x140022a45  movzx   eax, byte ptr [rdi+130h]
0x140022a4c  test    al, al
0x140022a4e  jz      short loc_140022A91
0x140022a50  and     rbx, 0FFFFFFFFFFFFF000h
0x140022a57  lea     rcx, [rdi+0C0h]; Lookaside
0x140022a5e  mov     rdx, rbx; Entry
0x140022a61  call    cs:__imp_ExFreeToLookasideListEx
0x140022a68  nop     dword ptr [rax+rax+00h]
0x140022a6d  add     rsp, 38h
0x140022a71  pop     r15
0x140022a73  pop     r14
0x140022a75  pop     rdi
0x140022a76  pop     rsi
0x140022a77  pop     rbp
0x140022a78  pop     rbx
0x140022a79  retn
0x140022a7b  mov     edx, 6D536358h; Tag
0x140022a80  mov     rcx, rbx; P
0x140022a83  call    cs:__imp_ExFreePoolWithTag
0x140022a8a  nop     dword ptr [rax+rax+00h]
0x140022a8f  jmp     short loc_140022A6D
0x140022a91  lea     rdx, [rdi+0C0h]
0x140022a98  call    PplpLazyInitializeLookasideList
0x140022a9d  jmp     short loc_140022A50
0x140022a9f  xor     edx, edx
0x140022aa1  test    r15, r15
0x140022aa4  jz      loc_14005EED6
0x140022aaa  mov     rcx, r15; BugCheckParameter2
0x140022aad  call    SmbCeDereferenceSessionEntryEx
0x140022ab2  jmp     loc_1400229DC
0x140022ab7  mov     rcx, rsi; BugCheckParameter2
0x140022aba  call    SmbCeDereferenceBindingObject
0x140022abf  jmp     loc_1400229E5
0x140022ac4  mov     edx, 6D536358h
0x140022ac9  call    SmbMmFreeSmbBuffer
0x140022ace  jmp     loc_1400229F5
0x140022ad3  mov     edx, 6D536358h
0x140022ad8  call    SmbMmFreeSmbBuffer
0x140022add  jmp     loc_140022A05
0x140022ae2  mov     edx, 6D536358h
0x140022ae7  call    SmbMmFreeSmbBuffer
0x140022aec  jmp     loc_140022A15
0x140022af1  mov     edx, 6D536358h
0x140022af6  call    SmbMmFreeSmbBuffer
0x140022afb  jmp     loc_140022A25
0x14005eed6  mov     rcx, r14; BugCheckParameter2
0x14005eed9  call    SmbCeDereferenceServerEntryEx
0x14005eede  nop
0x14005eedf  jmp     loc_1400229DC
```
