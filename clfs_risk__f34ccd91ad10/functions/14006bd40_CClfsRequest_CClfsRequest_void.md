# CClfsRequest::~CClfsRequest(void)

- ea: `0x14006bd40`
- end: `0x14006bf5c`
- name: `??1CClfsRequest@@QEAA@XZ`
- size: `540`
- prototype: `void __fastcall(CClfsRequest *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bd10`
- `0x14000cad0`

## callees

- `0x140017f20`
- `0x140033ac0`
- `0x14006bd40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006bedc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006bedc`
- `ntoskrnl!ObfDereferenceObject` at `0x14006be47`
- `ntoskrnl!ObfDereferenceObject` at `0x14006be47`
- `ntoskrnl!IoFreeIrp` at `0x14006beab`
- `ntoskrnl!IoFreeIrp` at `0x14006beab`
- `ntoskrnl!IoFreeMdl` at `0x14006be8e`
- `ntoskrnl!IoFreeMdl` at `0x14006bef7`
- `ntoskrnl!IoFreeMdl` at `0x14006bf16`
- `ntoskrnl!IoFreeMdl` at `0x14006be8e`
- `ntoskrnl!IoFreeMdl` at `0x14006bef7`
- `ntoskrnl!IoFreeMdl` at `0x14006bf16`
- `ntoskrnl!MmUnlockPages` at `0x14006bebc`
- `ntoskrnl!MmUnlockPages` at `0x14006bf40`
- `ntoskrnl!MmUnlockPages` at `0x14006bf4e`
- `ntoskrnl!MmUnlockPages` at `0x14006bebc`
- `ntoskrnl!MmUnlockPages` at `0x14006bf40`
- `ntoskrnl!MmUnlockPages` at `0x14006bf4e`
- `ntoskrnl!IofCompleteRequest` at `0x14006bde9`
- `ntoskrnl!IofCompleteRequest` at `0x14006bde9`

## pseudocode

```c
void __fastcall CClfsRequest::~CClfsRequest(CClfsRequest *this)
{
  volatile signed __int32 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  IRP *v10; // rcx

  *(_QWORD *)this = &CClfsRequest::`vftable';
  v2 = 0;
  v3 = 0;
  if ( *((_QWORD *)this + 19) )
  {
    v2 = (volatile signed __int32 *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 18) )
  {
    v3 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = *((_QWORD *)this + 10);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
  {
    if ( (*(_BYTE *)(v5 + 10) & 2) != 0 )
      MmUnlockPages((PMDL)v5);
    IoFreeMdl(*((PMDL *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  v6 = *((_QWORD *)this + 12);
  if ( v6 )
  {
    if ( (*(_BYTE *)(v6 + 10) & 2) != 0 )
      MmUnlockPages((PMDL)v6);
    IoFreeMdl(*((PMDL *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  v7 = *((_QWORD *)this + 6);
  if ( v7 )
  {
    if ( *(int *)(v7 + 48) >= 0 && *((_BYTE *)this + 24) == 3 )
      *(_QWORD *)(v7 + 56) = *((unsigned int *)this + 66);
    if ( (*((_DWORD *)this + 4) & 0x80u) == 0 || (v10 = (IRP *)*((_QWORD *)this + 6), (v10->Flags & 0x42) != 0) )
    {
      _InterlockedExchange64((volatile __int64 *)(*((_QWORD *)this + 6) + 104LL), 0);
      IofCompleteRequest(*((PIRP *)this + 6), 1);
    }
    else
    {
      IoFreeIrp(v10);
    }
    *((_QWORD *)this + 6) = 0;
  }
  *((CLFS_LSN *)this + 26) = CLFS_LSN_INVALID;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( v2 && _InterlockedExchangeAdd(v2 + 6, 0xFFFFFFFF) == 1 )
  {
    CClfsLogCcb::~CClfsLogCcb((CClfsLogCcb *)v2);
    ExFreeToNPagedLookasideList(&CClfsLogCcb::m_laList, (PVOID)v2);
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 72LL))(v3);
  v8 = (void *)*((_QWORD *)this + 14);
  if ( v8 )
  {
    ObfDereferenceObject(v8);
    *((_QWORD *)this + 14) = 0;
  }
  v9 = *((_QWORD *)this + 37);
  if ( v9 )
  {
    if ( (*(_BYTE *)(v9 + 10) & 2) != 0 )
      MmUnlockPages((PMDL)v9);
    IoFreeMdl(*((PMDL *)this + 37));
  }
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
}

```

## disassembly

```asm
0x14006bd40  push    rbx
0x14006bd42  push    rbp
0x14006bd43  push    rsi
0x14006bd44  push    rdi
0x14006bd45  sub     rsp, 28h
0x14006bd49  xor     ebp, ebp
0x14006bd4b  lea     rax, ??_7CClfsRequest@@6B@; const CClfsRequest::`vftable'
0x14006bd52  mov     [rcx], rax
0x14006bd55  mov     rbx, rcx
0x14006bd58  mov     rax, [rcx+98h]
0x14006bd5f  mov     edi, ebp
0x14006bd61  mov     esi, ebp
0x14006bd63  test    rax, rax
0x14006bd66  jz      short loc_14006BD72
0x14006bd68  mov     rdi, rax
0x14006bd6b  mov     [rcx+98h], rbp
0x14006bd72  mov     rax, [rcx+90h]
0x14006bd79  test    rax, rax
0x14006bd7c  jz      short loc_14006BD88
0x14006bd7e  mov     rsi, rax
0x14006bd81  mov     [rcx+90h], rbp
0x14006bd88  mov     rcx, [rcx+50h]
0x14006bd8c  test    rcx, rcx
0x14006bd8f  jnz     loc_14006BF2B
0x14006bd95  mov     rcx, [rbx+58h]; MemoryDescriptorList
0x14006bd99  test    rcx, rcx
0x14006bd9c  jnz     loc_14006BEED
0x14006bda2  mov     rcx, [rbx+60h]; MemoryDescriptorList
0x14006bda6  test    rcx, rcx
0x14006bda9  jnz     loc_14006BF0C
0x14006bdaf  mov     rcx, [rbx+30h]
0x14006bdb3  test    rcx, rcx
0x14006bdb6  jz      short loc_14006BDF9
0x14006bdb8  cmp     [rcx+30h], ebp
0x14006bdbb  jl      short loc_14006BDCD
0x14006bdbd  cmp     byte ptr [rbx+18h], 3
0x14006bdc1  jnz     short loc_14006BDCD
0x14006bdc3  mov     eax, [rbx+108h]
0x14006bdc9  mov     [rcx+38h], rax
0x14006bdcd  mov     eax, [rbx+10h]
0x14006bdd0  test    al, al
0x14006bdd2  js      loc_14006BE9C
0x14006bdd8  mov     rcx, [rbx+30h]
0x14006bddc  mov     rax, rbp
0x14006bddf  mov     dl, 1; PriorityBoost
0x14006bde1  xchg    rax, [rcx+68h]
0x14006bde5  mov     rcx, [rbx+30h]; Irp
0x14006bde9  call    cs:__imp_IofCompleteRequest
0x14006bdf0  nop     dword ptr [rax+rax+00h]
0x14006bdf5  mov     [rbx+30h], rbp
0x14006bdf9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14006be00  mov     [rbx+0D0h], rax
0x14006be07  mov     [rbx+78h], rbp
0x14006be0b  mov     [rbx+80h], rbp
0x14006be12  test    rdi, rdi
0x14006be15  jz      short loc_14006BE2A
0x14006be17  mov     eax, 0FFFFFFFFh
0x14006be1c  lock xadd [rdi+18h], eax
0x14006be21  cmp     eax, 1
0x14006be24  jz      loc_14006BECA
0x14006be2a  test    rsi, rsi
0x14006be2d  jz      short loc_14006BE3E
0x14006be2f  mov     rax, [rsi]
0x14006be32  mov     rcx, rsi
0x14006be35  mov     rax, [rax+48h]
0x14006be39  call    _guard_dispatch_icall
0x14006be3e  mov     rcx, [rbx+70h]; Object
0x14006be42  test    rcx, rcx
0x14006be45  jz      short loc_14006BE57
0x14006be47  call    cs:__imp_ObfDereferenceObject
0x14006be4e  nop     dword ptr [rax+rax+00h]
0x14006be53  mov     [rbx+70h], rbp
0x14006be57  mov     rcx, [rbx+128h]; MemoryDescriptorList
0x14006be5e  test    rcx, rcx
0x14006be61  jnz     short loc_14006BE81
0x14006be63  mov     [rbx+120h], rbp
0x14006be6a  mov     [rbx+128h], rbp
0x14006be71  mov     [rbx+130h], ebp
0x14006be77  add     rsp, 28h
0x14006be7b  pop     rdi
0x14006be7c  pop     rsi
0x14006be7d  pop     rbp
0x14006be7e  pop     rbx
0x14006be7f  retn
0x14006be81  test    byte ptr [rcx+0Ah], 2
0x14006be85  jnz     short loc_14006BEBC
0x14006be87  mov     rcx, [rbx+128h]; Mdl
0x14006be8e  call    cs:__imp_IoFreeMdl
0x14006be95  nop     dword ptr [rax+rax+00h]
0x14006be9a  jmp     short loc_14006BE63
0x14006be9c  mov     rcx, [rbx+30h]; Irp
0x14006bea0  mov     eax, [rcx+10h]
0x14006bea3  test    al, 42h
0x14006bea5  jnz     loc_14006BDD8
0x14006beab  call    cs:__imp_IoFreeIrp
0x14006beb2  nop     dword ptr [rax+rax+00h]
0x14006beb7  jmp     loc_14006BDF5
0x14006bebc  call    cs:__imp_MmUnlockPages
0x14006bec3  nop     dword ptr [rax+rax+00h]
0x14006bec8  jmp     short loc_14006BE87
0x14006beca  mov     rcx, rdi; this
0x14006becd  call    ??1CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::~CClfsLogCcb(void)
0x14006bed2  mov     rdx, rdi; Entry
0x14006bed5  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006bedc  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006bee3  nop     dword ptr [rax+rax+00h]
0x14006bee8  jmp     loc_14006BE2A
0x14006beed  test    byte ptr [rcx+0Ah], 2
0x14006bef1  jnz     short loc_14006BF40
0x14006bef3  mov     rcx, [rbx+58h]; Mdl
0x14006bef7  call    cs:__imp_IoFreeMdl
0x14006befe  nop     dword ptr [rax+rax+00h]
0x14006bf03  mov     [rbx+58h], rbp
0x14006bf07  jmp     loc_14006BDA2
0x14006bf0c  test    byte ptr [rcx+0Ah], 2
0x14006bf10  jnz     short loc_14006BF4E
0x14006bf12  mov     rcx, [rbx+60h]; Mdl
0x14006bf16  call    cs:__imp_IoFreeMdl
0x14006bf1d  nop     dword ptr [rax+rax+00h]
0x14006bf22  mov     [rbx+60h], rbp
0x14006bf26  jmp     loc_14006BDAF
0x14006bf2b  mov     rax, [rcx]
0x14006bf2e  mov     rax, [rax+8]
0x14006bf32  call    _guard_dispatch_icall
0x14006bf37  mov     [rbx+50h], rbp
0x14006bf3b  jmp     loc_14006BD95
0x14006bf40  call    cs:__imp_MmUnlockPages
0x14006bf47  nop     dword ptr [rax+rax+00h]
0x14006bf4c  jmp     short loc_14006BEF3
0x14006bf4e  call    cs:__imp_MmUnlockPages
0x14006bf55  nop     dword ptr [rax+rax+00h]
0x14006bf5a  jmp     short loc_14006BF12
```
