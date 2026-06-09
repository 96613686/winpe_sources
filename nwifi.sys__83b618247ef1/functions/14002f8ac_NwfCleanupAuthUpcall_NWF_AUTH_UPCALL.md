# NwfCleanupAuthUpcall(NWF_AUTH_UPCALL *)

- ea: `0x14002f8ac`
- end: `0x14002f993`
- name: `?NwfCleanupAuthUpcall@@YAXPEAUNWF_AUTH_UPCALL@@@Z`
- size: `231`
- prototype: `void __fastcall(PIO_CSQ Csq)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400205d8`

## callees

- `0x14002f8ac`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f949`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f949`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f95a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f95a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f976`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f976`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f901`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f901`
- `ntoskrnl!IofCompleteRequest` at `0x14002f8db`
- `ntoskrnl!IofCompleteRequest` at `0x14002f8db`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14002f8ec`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14002f8ec`

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
0x14002f8ac  mov     [rsp+arg_0], rbx
0x14002f8b1  mov     [rsp+arg_8], rsi
0x14002f8b6  push    rdi
0x14002f8b7  sub     rsp, 20h
0x14002f8bb  mov     rbx, rcx
0x14002f8be  mov     dword ptr [rcx+50h], 1
0x14002f8c5  jmp     short loc_14002F8EA
0x14002f8c7  xor     edx, edx; PriorityBoost
0x14002f8c9  mov     dword ptr [rax+30h], 0C0000240h
0x14002f8d0  mov     rcx, rax; Irp
0x14002f8d3  mov     qword ptr [rax+38h], 0
0x14002f8db  call    cs:__imp_IofCompleteRequest
0x14002f8e2  nop     dword ptr [rax+rax+00h]
0x14002f8e7  mov     rcx, rbx; Csq
0x14002f8ea  xor     edx, edx; PeekContext
0x14002f8ec  call    cs:__imp_IoCsqRemoveNextIrp
0x14002f8f3  nop     dword ptr [rax+rax+00h]
0x14002f8f8  test    rax, rax
0x14002f8fb  jnz     short loc_14002F8C7
0x14002f8fd  lea     rcx, [rbx+40h]; SpinLock
0x14002f901  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f908  nop     dword ptr [rax+rax+00h]
0x14002f90d  mov     [rbx+48h], al
0x14002f910  lea     rdi, [rbx+68h]
0x14002f914  mov     rax, [rdi]
0x14002f917  cmp     rax, rdi
0x14002f91a  jz      short loc_14002F96F
0x14002f91c  cmp     [rax+8], rdi
0x14002f920  jnz     short loc_14002F968
0x14002f922  mov     rcx, [rax]
0x14002f925  cmp     [rcx+8], rax
0x14002f929  jnz     short loc_14002F968
0x14002f92b  mov     [rdi], rcx
0x14002f92e  mov     [rcx+8], rdi
0x14002f932  test    rax, rax
0x14002f935  jz      short loc_14002F914
0x14002f937  lea     rcx, [rax-10h]; P
0x14002f93b  mov     rax, [rcx]
0x14002f93e  test    rax, rax
0x14002f941  jz      short loc_14002F957
0x14002f943  mov     rdx, rcx; Entry
0x14002f946  mov     rcx, rax; Lookaside
0x14002f949  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002f950  nop     dword ptr [rax+rax+00h]
0x14002f955  jmp     short loc_14002F914
0x14002f957  mov     edx, [rcx+8]; Tag
0x14002f95a  call    cs:__imp_ExFreePoolWithTag
0x14002f961  nop     dword ptr [rax+rax+00h]
0x14002f966  jmp     short loc_14002F914
0x14002f968  mov     ecx, 3
0x14002f96d  int     29h; Win8: RtlFailFast(ecx)
0x14002f96f  mov     dl, [rbx+48h]; NewIrql
0x14002f972  lea     rcx, [rbx+40h]; SpinLock
0x14002f976  call    cs:__imp_KeReleaseSpinLock
0x14002f97d  nop     dword ptr [rax+rax+00h]
0x14002f982  mov     rbx, [rsp+28h+arg_0]
0x14002f987  mov     rsi, [rsp+28h+arg_8]
0x14002f98c  add     rsp, 20h
0x14002f990  pop     rdi
0x14002f991  retn
```
