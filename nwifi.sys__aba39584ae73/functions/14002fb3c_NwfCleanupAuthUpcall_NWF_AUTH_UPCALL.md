# NwfCleanupAuthUpcall(NWF_AUTH_UPCALL *)

- ea: `0x14002fb3c`
- end: `0x14002fc23`
- name: `?NwfCleanupAuthUpcall@@YAXPEAUNWF_AUTH_UPCALL@@@Z`
- size: `231`
- prototype: `void __fastcall(PIO_CSQ Csq)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400205d8`

## callees

- `0x14002fb3c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002fbd9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002fbd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc06`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc06`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fb91`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fb91`
- `ntoskrnl!IofCompleteRequest` at `0x14002fb6b`
- `ntoskrnl!IofCompleteRequest` at `0x14002fb6b`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14002fb7c`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14002fb7c`

## pseudocode

```c
void __fastcall NwfCleanupAuthUpcall(PIO_CSQ Csq)
{
  PIO_CSQ v1; // rbx
  PIRP v2; // rax
  void (__fastcall **p_CsqReleaseLock)(_IO_CSQ *, unsigned __int8); // rdi
  void (__fastcall *v4)(_IO_CSQ *, unsigned __int8); // rax
  void (__fastcall *v5)(_IO_CSQ *, unsigned __int8); // rcx
  ULONG *v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rax

  v1 = Csq;
  LODWORD(Csq[1].CsqRemoveIrp) = 1;
  while ( 1 )
  {
    v2 = IoCsqRemoveNextIrp(Csq, 0);
    if ( !v2 )
      break;
    v2->IoStatus.Status = -1073741248;
    v2->IoStatus.Information = 0;
    IofCompleteRequest(v2, 0);
    Csq = v1;
  }
  LOBYTE(v1[1].CsqInsertIrp) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v1[1].Type);
  p_CsqReleaseLock = &v1[1].CsqReleaseLock;
  while ( 1 )
  {
    v4 = *p_CsqReleaseLock;
    if ( (char *)*p_CsqReleaseLock == (char *)p_CsqReleaseLock )
      break;
    if ( *((void (__fastcall ***)(_IO_CSQ *, unsigned __int8))v4 + 1) != p_CsqReleaseLock
      || (v5 = *(void (__fastcall **)(_IO_CSQ *, unsigned __int8))v4,
          *(void (__fastcall **)(_IO_CSQ *, unsigned __int8))(*(_QWORD *)v4 + 8LL) != v4) )
    {
      __fastfail(3u);
    }
    *p_CsqReleaseLock = v5;
    *((_QWORD *)v5 + 1) = p_CsqReleaseLock;
    if ( v4 )
    {
      v6 = (ULONG *)((char *)v4 - 16);
      v7 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)v4 - 2);
      if ( v7 )
        ExFreeToNPagedLookasideList(v7, v6);
      else
        ExFreePoolWithTag(v6, v6[2]);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&v1[1].Type, (KIRQL)v1[1].CsqInsertIrp);
}

```

## disassembly

```asm
0x14002fb3c  mov     [rsp+arg_0], rbx
0x14002fb41  mov     [rsp+arg_8], rsi
0x14002fb46  push    rdi
0x14002fb47  sub     rsp, 20h
0x14002fb4b  mov     rbx, rcx
0x14002fb4e  mov     dword ptr [rcx+50h], 1
0x14002fb55  jmp     short loc_14002FB7A
0x14002fb57  xor     edx, edx; PriorityBoost
0x14002fb59  mov     dword ptr [rax+30h], 0C0000240h
0x14002fb60  mov     rcx, rax; Irp
0x14002fb63  mov     qword ptr [rax+38h], 0
0x14002fb6b  call    cs:__imp_IofCompleteRequest
0x14002fb72  nop     dword ptr [rax+rax+00h]
0x14002fb77  mov     rcx, rbx; Csq
0x14002fb7a  xor     edx, edx; PeekContext
0x14002fb7c  call    cs:__imp_IoCsqRemoveNextIrp
0x14002fb83  nop     dword ptr [rax+rax+00h]
0x14002fb88  test    rax, rax
0x14002fb8b  jnz     short loc_14002FB57
0x14002fb8d  lea     rcx, [rbx+40h]; SpinLock
0x14002fb91  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fb98  nop     dword ptr [rax+rax+00h]
0x14002fb9d  mov     [rbx+48h], al
0x14002fba0  lea     rdi, [rbx+68h]
0x14002fba4  mov     rax, [rdi]
0x14002fba7  cmp     rax, rdi
0x14002fbaa  jz      short loc_14002FBFF
0x14002fbac  cmp     [rax+8], rdi
0x14002fbb0  jnz     short loc_14002FBF8
0x14002fbb2  mov     rcx, [rax]
0x14002fbb5  cmp     [rcx+8], rax
0x14002fbb9  jnz     short loc_14002FBF8
0x14002fbbb  mov     [rdi], rcx
0x14002fbbe  mov     [rcx+8], rdi
0x14002fbc2  test    rax, rax
0x14002fbc5  jz      short loc_14002FBA4
0x14002fbc7  lea     rcx, [rax-10h]; P
0x14002fbcb  mov     rax, [rcx]
0x14002fbce  test    rax, rax
0x14002fbd1  jz      short loc_14002FBE7
0x14002fbd3  mov     rdx, rcx; Entry
0x14002fbd6  mov     rcx, rax; Lookaside
0x14002fbd9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002fbe0  nop     dword ptr [rax+rax+00h]
0x14002fbe5  jmp     short loc_14002FBA4
0x14002fbe7  mov     edx, [rcx+8]; Tag
0x14002fbea  call    cs:__imp_ExFreePoolWithTag
0x14002fbf1  nop     dword ptr [rax+rax+00h]
0x14002fbf6  jmp     short loc_14002FBA4
0x14002fbf8  mov     ecx, 3
0x14002fbfd  int     29h; Win8: RtlFailFast(ecx)
0x14002fbff  mov     dl, [rbx+48h]; NewIrql
0x14002fc02  lea     rcx, [rbx+40h]; SpinLock
0x14002fc06  call    cs:__imp_KeReleaseSpinLock
0x14002fc0d  nop     dword ptr [rax+rax+00h]
0x14002fc12  mov     rbx, [rsp+28h+arg_0]
0x14002fc17  mov     rsi, [rsp+28h+arg_8]
0x14002fc1c  add     rsp, 20h
0x14002fc20  pop     rdi
0x14002fc21  retn
```
