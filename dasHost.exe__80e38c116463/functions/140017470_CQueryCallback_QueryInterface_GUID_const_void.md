# CQueryCallback::QueryInterface(_GUID const &,void * *)

- ea: `0x140017470`
- end: `0x1400175f8`
- name: `?QueryInterface@CQueryCallback@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(CQueryCallback *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140017600`
- `0x140017610`
- `0x140017620`
- `0x140017630`

## callees

- `0x140017470`
- `0x140018f8c`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CQueryCallback::QueryInterface(CQueryCallback *this, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // esi
  unsigned __int64 v7; // rcx
  unsigned int v8; // eax
  struct CProviderImpersonation *v9; // rbx
  struct CProviderImpersonation *v11; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  v6 = 0;
  *a3 = 0;
  if ( *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046 == *(_OWORD *)a2
    || *(_QWORD *)&GUID_48780fb0_e908_4af1_b350_ef52f6a634e6.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_48780fb0_e908_4af1_b350_ef52f6a634e6.Data4 == *(_QWORD *)a2->Data4 )
  {
    (*(void (__fastcall **)(CQueryCallback *))(*(_QWORD *)this + 8LL))(this);
    *a3 = this;
    return v6;
  }
  if ( *(_QWORD *)&GUID_09a26ea8_87fc_4b14_99c8_157168c0070d.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_09a26ea8_87fc_4b14_99c8_157168c0070d.Data4 == *(_QWORD *)a2->Data4 )
  {
    (*(void (__fastcall **)(CQueryCallback *))(*(_QWORD *)this + 8LL))(this);
    v7 = (unsigned __int64)this + 8;
LABEL_22:
    *a3 = (void *)(v7 & -(__int64)(this != 0));
    return v6;
  }
  if ( *(_QWORD *)&GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d.Data4 == *(_QWORD *)a2->Data4 )
  {
    (*(void (__fastcall **)(CQueryCallback *))(*(_QWORD *)this + 8LL))(this);
    v7 = (unsigned __int64)this + 16;
    goto LABEL_22;
  }
  if ( *(_QWORD *)&GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data1 != *(_QWORD *)&a2->Data1
    || *(_QWORD *)GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data4 != *(_QWORD *)a2->Data4 )
  {
    if ( *(_QWORD *)&GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data4 == *(_QWORD *)a2->Data4 )
    {
      (*(void (__fastcall **)(CQueryCallback *))(*(_QWORD *)this + 8LL))(this);
      v7 = (unsigned __int64)this + 32;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( !*((_QWORD *)this + 14) )
    return (unsigned int)-2147467262;
  v11 = 0;
  v8 = CProviderImpersonation::Create(
         (struct IDafPrivImpersonationToken *)(((unsigned __int64)this + 24) & -(__int64)(this != 0)),
         &v11);
  v9 = v11;
  v6 = v8;
  if ( !v8 )
    v6 = (**(__int64 (__fastcall ***)(struct CProviderImpersonation *, const struct _GUID *, void **))v11)(v11, a2, a3);
  if ( v9 )
    (*(void (__fastcall **)(struct CProviderImpersonation *))(*(_QWORD *)v9 + 16LL))(v9);
  return v6;
}

```

## disassembly

```asm
0x140017470  push    rbx
0x140017472  push    rsi
0x140017473  push    rdi
0x140017474  push    r14
0x140017476  sub     rsp, 28h
0x14001747a  mov     r14, r8
0x14001747d  mov     rdi, rdx
0x140017480  mov     rbx, rcx
0x140017483  test    r8, r8
0x140017486  jz      loc_1400175E7
0x14001748c  xor     esi, esi
0x14001748e  mov     [r8], rsi
0x140017491  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140017498  cmp     rax, [rdx]
0x14001749b  jnz     short loc_1400174AA
0x14001749d  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1400174a4  cmp     rax, [rdx+8]
0x1400174a8  jz      short loc_1400174C3
0x1400174aa  mov     rax, qword ptr cs:_GUID_48780fb0_e908_4af1_b350_ef52f6a634e6.Data1
0x1400174b1  cmp     rax, [rdx]
0x1400174b4  jnz     short loc_1400174D7
0x1400174b6  mov     rax, qword ptr cs:_GUID_48780fb0_e908_4af1_b350_ef52f6a634e6.Data4
0x1400174bd  cmp     rax, [rdx+8]
0x1400174c1  jnz     short loc_1400174D7
0x1400174c3  mov     rax, [rcx]
0x1400174c6  mov     rax, [rax+8]
0x1400174ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174cf  mov     [r14], rbx
0x1400174d2  jmp     loc_1400175EC
0x1400174d7  mov     rax, qword ptr cs:_GUID_09a26ea8_87fc_4b14_99c8_157168c0070d.Data1
0x1400174de  cmp     rax, [rdx]
0x1400174e1  jnz     short loc_140017505
0x1400174e3  mov     rax, qword ptr cs:_GUID_09a26ea8_87fc_4b14_99c8_157168c0070d.Data4
0x1400174ea  cmp     rax, [rdx+8]
0x1400174ee  jnz     short loc_140017505
0x1400174f0  mov     rax, [rcx]
0x1400174f3  mov     rax, [rax+8]
0x1400174f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174fc  lea     rcx, [rbx+8]
0x140017500  jmp     loc_1400175D2
0x140017505  mov     rax, qword ptr cs:_GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d.Data1
0x14001750c  cmp     rax, [rdx]
0x14001750f  jnz     short loc_140017533
0x140017511  mov     rax, qword ptr cs:_GUID_f57ecdb0_e405_484f_8d72_3f4b15449b3d.Data4
0x140017518  cmp     rax, [rdx+8]
0x14001751c  jnz     short loc_140017533
0x14001751e  mov     rax, [rcx]
0x140017521  mov     rax, [rax+8]
0x140017525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001752a  lea     rcx, [rbx+10h]
0x14001752e  jmp     loc_1400175D2
0x140017533  mov     rax, qword ptr cs:_GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data1
0x14001753a  cmp     rax, [rdx]
0x14001753d  jnz     short loc_1400175A9
0x14001753f  mov     rax, qword ptr cs:_GUID_a19c25bd_c8bb_4a85_a4c7_5e69a6cf7cd3.Data4
0x140017546  cmp     rax, [rdx+8]
0x14001754a  jnz     short loc_1400175A9
0x14001754c  cmp     [rcx+70h], rsi
0x140017550  jz      loc_1400175E0
0x140017556  lea     rax, [rcx+18h]
0x14001755a  mov     [rsp+48h+arg_10], rsi
0x14001755f  neg     rbx
0x140017562  lea     rdx, [rsp+48h+arg_10]; struct CProviderImpersonation **
0x140017567  sbb     rcx, rcx
0x14001756a  and     rcx, rax; struct IDafPrivImpersonationToken *
0x14001756d  call    ?Create@CProviderImpersonation@@SAJPEAUIDafPrivImpersonationToken@@PEAPEAV1@@Z; CProviderImpersonation::Create(IDafPrivImpersonationToken *,CProviderImpersonation * *)
0x140017572  mov     rbx, [rsp+48h+arg_10]
0x140017577  mov     esi, eax
0x140017579  test    eax, eax
0x14001757b  jnz     short loc_140017593
0x14001757d  mov     rax, [rbx]
0x140017580  mov     r8, r14
0x140017583  mov     rdx, rdi
0x140017586  mov     rcx, rbx
0x140017589  mov     rax, [rax]
0x14001758c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017591  mov     esi, eax
0x140017593  test    rbx, rbx
0x140017596  jz      short loc_1400175EC
0x140017598  mov     rax, [rbx]
0x14001759b  mov     rcx, rbx
0x14001759e  mov     rax, [rax+10h]
0x1400175a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175a7  jmp     short loc_1400175EC
0x1400175a9  mov     rax, qword ptr cs:_GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data1
0x1400175b0  cmp     rax, [rdx]
0x1400175b3  jnz     short loc_1400175E0
0x1400175b5  mov     rax, qword ptr cs:_GUID_6d5140c1_7436_11ce_8034_00aa006009fa.Data4
0x1400175bc  cmp     rax, [rdx+8]
0x1400175c0  jnz     short loc_1400175E0
0x1400175c2  mov     rax, [rcx]
0x1400175c5  mov     rax, [rax+8]
0x1400175c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175ce  lea     rcx, [rbx+20h]
0x1400175d2  neg     rbx
0x1400175d5  sbb     rax, rax
0x1400175d8  and     rax, rcx
0x1400175db  mov     [r14], rax
0x1400175de  jmp     short loc_1400175EC
0x1400175e0  mov     esi, 80004002h
0x1400175e5  jmp     short loc_1400175EC
0x1400175e7  mov     esi, 80070057h
0x1400175ec  mov     eax, esi
0x1400175ee  add     rsp, 28h
0x1400175f2  pop     r14
0x1400175f4  pop     rdi
0x1400175f5  pop     rsi
0x1400175f6  pop     rbx
0x1400175f7  retn
```
