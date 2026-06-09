# VmbusTlDissociateConnectionFromService

- ea: `0x140008e7c`
- end: `0x14000905a`
- name: `VmbusTlDissociateConnectionFromService`
- size: `478`
- prototype: `void __fastcall(char *P)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140009060`

## callees

- `0x140008e7c`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f02`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008ef6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008ef6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009045`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009045`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008e96`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008e96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140008f87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000902f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140008f87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000902f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008ea6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008ea6`

## string_xrefs

- `0x140008f2b`: `VmbusTlDissociateConnectionFromService`
- `0x140008fc3`: `VmbusTlDissociateConnectionFromService`

## pseudocode

```c
void __fastcall VmbusTlDissociateConnectionFromService(char *P)
{
  __int64 v1; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  __int64 v6; // rbx
  signed __int64 v7; // rax
  bool v8; // cc
  signed __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax
  signed __int64 v11; // rax
  signed __int64 v12; // rax
  void (__fastcall *v13)(char *); // rax

  v1 = *((_QWORD *)P + 109);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v1 + 16));
  v3 = P + 120;
  v4 = *((_QWORD *)P + 15);
  if ( *(char **)(v4 + 8) != P + 120 || (v5 = (_QWORD *)*((_QWORD *)P + 16), (_QWORD *)*v5 != v3) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  *((_QWORD *)P + 16) = P + 120;
  *v3 = v3;
  --*(_DWORD *)(*((_QWORD *)P + 109) + 304LL);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)P + 109) + 16LL));
  KeLeaveCriticalRegion();
  v6 = *((_QWORD *)P + 109);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlDissociateConnectionFromService",
      261,
      *((_QWORD *)P + 109),
      *(_QWORD *)(v6 + 8),
      (const int *)"Dereference object");
  v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v6 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v8 = v7 <= 1;
  v9 = v7 - 1;
  if ( v8 )
  {
    if ( v9 )
      __fastfail(0xEu);
    v10 = *(void (__fastcall **)(__int64))(v6 + 80);
    if ( v10 )
      v10(v6);
    if ( *(_DWORD *)(v6 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v6, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v6 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v6 + 96), (PVOID)v6);
    }
  }
  *((_QWORD *)P + 109) = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlDissociateConnectionFromService",
      268,
      (__int64)P,
      *((_QWORD *)P + 1),
      (const int *)"Dereference object");
  v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v8 = v11 <= 1;
  v12 = v11 - 1;
  if ( v8 )
  {
    if ( v12 )
      __fastfail(0xEu);
    v13 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
    if ( v13 )
      v13(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
}

```

## disassembly

```asm
0x140008e7c  mov     [rsp+arg_0], rbx
0x140008e81  mov     [rsp+arg_8], rdi
0x140008e86  push    r15
0x140008e88  sub     rsp, 30h
0x140008e8c  mov     rbx, [rcx+368h]
0x140008e93  mov     rdi, rcx
0x140008e96  call    cs:__imp_KeEnterCriticalRegion
0x140008e9d  nop     dword ptr [rax+rax+00h]
0x140008ea2  lea     rcx, [rbx+10h]; FastMutex
0x140008ea6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008ead  nop     dword ptr [rax+rax+00h]
0x140008eb2  lea     rax, [rdi+78h]
0x140008eb6  mov     rdx, [rax]
0x140008eb9  cmp     [rdx+8], rax
0x140008ebd  jnz     loc_140009053
0x140008ec3  mov     rcx, [rax+8]
0x140008ec7  cmp     [rcx], rax
0x140008eca  jnz     loc_140009053
0x140008ed0  mov     [rcx], rdx
0x140008ed3  mov     [rdx+8], rcx
0x140008ed7  mov     [rax+8], rax
0x140008edb  mov     [rax], rax
0x140008ede  mov     rax, [rdi+368h]
0x140008ee5  dec     dword ptr [rax+130h]
0x140008eeb  mov     rcx, [rdi+368h]
0x140008ef2  add     rcx, 10h; FastMutex
0x140008ef6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008efd  nop     dword ptr [rax+rax+00h]
0x140008f02  call    cs:__imp_KeLeaveCriticalRegion
0x140008f09  nop     dword ptr [rax+rax+00h]
0x140008f0e  mov     eax, cs:dword_140013058
0x140008f14  lea     r15, aDereferenceObj; "Dereference object"
0x140008f1b  mov     rbx, [rdi+368h]
0x140008f22  cmp     eax, 5
0x140008f25  jbe     short loc_140008F44
0x140008f27  mov     r9, [rbx+8]
0x140008f2b  lea     rcx, aVmbustldissoci_3; "VmbusTlDissociateConnectionFromService"
0x140008f32  mov     r8, rbx
0x140008f35  mov     [rsp+38h+var_18], r15
0x140008f3a  mov     edx, 105h
0x140008f3f  call    HvsocketTraceReferenceCount
0x140008f44  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008f48  lock xadd [rbx+8], rax
0x140008f4e  sub     rax, 1
0x140008f52  jg      short loc_140008FA9
0x140008f54  test    rax, rax
0x140008f57  jz      short loc_140008F62
0x140008f59  mov     ecx, 0Eh
0x140008f5e  int     29h; Win8: RtlFailFast(ecx)
0x140008f60  jmp     short loc_140008FA9
0x140008f62  mov     rax, [rbx+50h]
0x140008f66  test    rax, rax
0x140008f69  jz      short loc_140008F73
0x140008f6b  mov     rcx, rbx
0x140008f6e  call    _guard_dispatch_icall
0x140008f73  mov     ecx, [rbx+58h]
0x140008f76  sub     ecx, 1
0x140008f79  jz      short loc_140008F95
0x140008f7b  cmp     ecx, 1
0x140008f7e  jnz     short loc_140008FA9
0x140008f80  mov     rcx, [rbx+60h]; Lookaside
0x140008f84  mov     rdx, rbx; Entry
0x140008f87  call    cs:__imp_ExFreeToNPagedLookasideList
0x140008f8e  nop     dword ptr [rax+rax+00h]
0x140008f93  jmp     short loc_140008FA9
0x140008f95  mov     edx, 69706E56h; Tag
0x140008f9a  mov     rcx, rbx; P
0x140008f9d  call    cs:__imp_ExFreePoolWithTag
0x140008fa4  nop     dword ptr [rax+rax+00h]
0x140008fa9  mov     qword ptr [rdi+368h], 0
0x140008fb4  mov     eax, cs:dword_140013058
0x140008fba  cmp     eax, 5
0x140008fbd  jbe     short loc_140008FDC
0x140008fbf  mov     r9, [rdi+8]
0x140008fc3  lea     rcx, aVmbustldissoci_3; "VmbusTlDissociateConnectionFromService"
0x140008fca  mov     r8, rdi
0x140008fcd  mov     [rsp+38h+var_18], r15
0x140008fd2  mov     edx, 10Ch
0x140008fd7  call    HvsocketTraceReferenceCount
0x140008fdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008fe0  lock xadd [rdi+8], rax
0x140008fe6  sub     rax, 1
0x140008fea  jg      short loc_140008FF8
0x140008fec  test    rax, rax
0x140008fef  jz      short loc_14000900A
0x140008ff1  mov     ecx, 0Eh
0x140008ff6  int     29h; Win8: RtlFailFast(ecx)
0x140008ff8  mov     rbx, [rsp+38h+arg_0]
0x140008ffd  mov     rdi, [rsp+38h+arg_8]
0x140009002  add     rsp, 30h
0x140009006  pop     r15
0x140009008  retn
0x14000900a  mov     rax, [rdi+50h]
0x14000900e  test    rax, rax
0x140009011  jz      short loc_14000901B
0x140009013  mov     rcx, rdi
0x140009016  call    _guard_dispatch_icall
0x14000901b  mov     ecx, [rdi+58h]
0x14000901e  sub     ecx, 1
0x140009021  jz      short loc_14000903D
0x140009023  cmp     ecx, 1
0x140009026  jnz     short loc_140008FF8
0x140009028  mov     rcx, [rdi+60h]; Lookaside
0x14000902c  mov     rdx, rdi; Entry
0x14000902f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140009036  nop     dword ptr [rax+rax+00h]
0x14000903b  jmp     short loc_140008FF8
0x14000903d  mov     edx, 69706E56h; Tag
0x140009042  mov     rcx, rdi; P
0x140009045  call    cs:__imp_ExFreePoolWithTag
0x14000904c  nop     dword ptr [rax+rax+00h]
0x140009051  jmp     short loc_140008FF8
0x140009053  mov     ecx, 3
0x140009058  int     29h; Win8: RtlFailFast(ecx)
```
