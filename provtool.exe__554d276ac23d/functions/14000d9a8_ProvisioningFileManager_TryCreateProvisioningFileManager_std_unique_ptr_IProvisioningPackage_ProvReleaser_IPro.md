# ProvisioningFileManager::TryCreateProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &)

- ea: `0x14000d9a8`
- end: `0x14000dc1c`
- name: `?TryCreateProvisioningFileManager@ProvisioningFileManager@@SA_N$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@AEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@3@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dc24`

## callees

- `0x140002294`
- `0x14000d9a8`
- `0x140010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall ProvisioningFileManager::TryCreateProvisioningFileManager(__int64 **a1, _QWORD *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // esi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 (__fastcall **v10)(__int64, __int64 *); // rax
  int v11; // esi
  __int64 v12; // rbx
  __int64 *v13; // rdi
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  __int64 *v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 **v19; // rdi
  __int64 *v20; // rsi
  __int64 *v21; // rcx
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  __int64 v24; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v25; // [rsp+28h] [rbp-18h]
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  char v27; // [rsp+38h] [rbp-8h]
  __int64 (__fastcall ***v28)(__int64, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp+38h]

  v24 = 0;
  v28 = 0;
  if ( *a2 )
  {
    (**(void (__fastcall ***)(_QWORD, __int64))*a2)(*a2, 1);
    *a2 = 0;
  }
  v4 = *a1;
  v5 = **a1;
  v25 = (__int64 *)&v28;
  v26 = 0;
  v27 = 1;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 104))(v4, 3, &v26);
  if ( v27 )
  {
    v7 = v26;
    v8 = *v25;
    if ( v26 != *v25 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *v25 = v7;
    }
  }
  if ( v6 < 0 )
  {
    if ( v28 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64 *)))(*v28)[1])(v28);
LABEL_11:
    v9 = v24;
LABEL_44:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 80LL))(v9);
    return 0;
  }
  v10 = *v28;
  v25 = &v24;
  v26 = 0;
  v27 = 1;
  v11 = (*v10)((__int64)v28, &v26);
  if ( v27 )
  {
    v12 = v26;
    v13 = v25;
    v14 = *v25;
    if ( v26 != *v25 )
    {
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 80LL))(v14);
      *v13 = v12;
    }
  }
  if ( v11 < 0 )
  {
    if ( v28 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64 *)))(*v28)[1])(v28);
    goto LABEL_11;
  }
  v15 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v29 = v15;
  if ( !v15 )
  {
    if ( v28 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64 *)))(*v28)[1])(v28);
    v9 = v24;
    if ( !v24 )
      return 0;
    goto LABEL_44;
  }
  *v15 = &ProvisioningFileManager::`vftable';
  v15[1] = 0;
  v15[2] = 0;
  v16 = v15 + 2;
  if ( v15 + 2 != &v24 )
  {
    v17 = v24;
    v24 = 0;
    v18 = *v16;
    if ( v17 != *v16 )
    {
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
      *v16 = v17;
    }
  }
  v19 = (__int64 **)(v15 + 1);
  if ( v15 + 1 != a1 )
  {
    v20 = *a1;
    *a1 = 0;
    v21 = *v19;
    if ( v20 != *v19 )
    {
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 128))(v21);
      *v19 = v20;
    }
  }
  v22 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  if ( v15 != (_QWORD *)*a2 )
  {
    if ( v22 )
      (**v22)(v22, 1);
    *a2 = v15;
  }
  if ( v28 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64 *)))(*v28)[1])(v28);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 80LL))(v24);
  return 1;
}

```

## disassembly

```asm
0x14000d9a8  mov     [rsp-28h+arg_10], rbx
0x14000d9ad  push    rbp
0x14000d9ae  push    rsi
0x14000d9af  push    rdi
0x14000d9b0  push    r14
0x14000d9b2  push    r15
0x14000d9b4  mov     rbp, rsp
0x14000d9b7  sub     rsp, 40h
0x14000d9bb  mov     r14, rdx
0x14000d9be  mov     r15, rcx
0x14000d9c1  mov     [rbp+var_20], 0
0x14000d9c9  mov     [rbp+arg_0], 0
0x14000d9d1  mov     rcx, [rdx]
0x14000d9d4  test    rcx, rcx
0x14000d9d7  jz      short loc_14000D9F0
0x14000d9d9  mov     rax, [rcx]
0x14000d9dc  mov     edx, 1
0x14000d9e1  mov     rax, [rax]
0x14000d9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9e9  mov     qword ptr [r14], 0
0x14000d9f0  mov     rcx, [r15]
0x14000d9f3  mov     rax, [rcx]
0x14000d9f6  lea     rdx, [rbp+arg_0]
0x14000d9fa  mov     [rbp+var_18], rdx
0x14000d9fe  mov     [rbp+var_10], 0
0x14000da06  mov     [rbp+var_8], 1
0x14000da0a  lea     r8, [rbp+var_10]
0x14000da0e  mov     edx, 3
0x14000da13  mov     rax, [rax+68h]
0x14000da17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da1c  mov     esi, eax
0x14000da1e  cmp     [rbp+var_8], 0
0x14000da22  jz      short loc_14000DA48
0x14000da24  mov     rbx, [rbp+var_10]
0x14000da28  mov     rdi, [rbp+var_18]
0x14000da2c  mov     rcx, [rdi]
0x14000da2f  cmp     rbx, rcx
0x14000da32  jz      short loc_14000DA48
0x14000da34  test    rcx, rcx
0x14000da37  jz      short loc_14000DA45
0x14000da39  mov     rax, [rcx]
0x14000da3c  mov     rax, [rax+8]
0x14000da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da45  mov     [rdi], rbx
0x14000da48  test    esi, esi
0x14000da4a  jns     short loc_14000DA6B
0x14000da4c  mov     rcx, [rbp+arg_0]
0x14000da50  test    rcx, rcx
0x14000da53  jz      short loc_14000DA62
0x14000da55  mov     rax, [rcx]
0x14000da58  mov     rax, [rax+8]
0x14000da5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da61  nop
0x14000da62  mov     rcx, [rbp+var_20]
0x14000da66  jmp     loc_14000DBF4
0x14000da6b  mov     rcx, [rbp+arg_0]
0x14000da6f  mov     rax, [rcx]
0x14000da72  lea     rdx, [rbp+var_20]
0x14000da76  mov     [rbp+var_18], rdx
0x14000da7a  mov     [rbp+var_10], 0
0x14000da82  mov     [rbp+var_8], 1
0x14000da86  lea     rdx, [rbp+var_10]
0x14000da8a  mov     rax, [rax]
0x14000da8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da92  mov     esi, eax
0x14000da94  cmp     [rbp+var_8], 0
0x14000da98  jz      short loc_14000DABE
0x14000da9a  mov     rbx, [rbp+var_10]
0x14000da9e  mov     rdi, [rbp+var_18]
0x14000daa2  mov     rcx, [rdi]
0x14000daa5  cmp     rbx, rcx
0x14000daa8  jz      short loc_14000DABE
0x14000daaa  test    rcx, rcx
0x14000daad  jz      short loc_14000DABB
0x14000daaf  mov     rax, [rcx]
0x14000dab2  mov     rax, [rax+50h]
0x14000dab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dabb  mov     [rdi], rbx
0x14000dabe  test    esi, esi
0x14000dac0  jns     short loc_14000DADA
0x14000dac2  mov     rcx, [rbp+arg_0]
0x14000dac6  test    rcx, rcx
0x14000dac9  jz      short loc_14000DAD8
0x14000dacb  mov     rax, [rcx]
0x14000dace  mov     rax, [rax+8]
0x14000dad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dad7  nop
0x14000dad8  jmp     short loc_14000DA62
0x14000dada  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dae1  mov     ecx, 18h; unsigned __int64
0x14000dae6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000daeb  mov     rbx, rax
0x14000daee  mov     [rbp+arg_8], rax
0x14000daf2  test    rax, rax
0x14000daf5  jz      loc_14000DBD5
0x14000dafb  lea     rax, ??_7ProvisioningFileManager@@6B@; const ProvisioningFileManager::`vftable'
0x14000db02  mov     [rbx], rax
0x14000db05  mov     qword ptr [rbx+8], 0
0x14000db0d  mov     qword ptr [rbx+10h], 0
0x14000db15  test    rbx, rbx
0x14000db18  jz      loc_14000DBD5
0x14000db1e  lea     rdi, [rbx+10h]
0x14000db22  lea     rax, [rbp+var_20]
0x14000db26  cmp     rdi, rax
0x14000db29  jz      short loc_14000DB53
0x14000db2b  mov     rsi, [rbp+var_20]
0x14000db2f  mov     [rbp+var_20], 0
0x14000db37  mov     rcx, [rdi]
0x14000db3a  cmp     rsi, rcx
0x14000db3d  jz      short loc_14000DB53
0x14000db3f  test    rcx, rcx
0x14000db42  jz      short loc_14000DB50
0x14000db44  mov     rax, [rcx]
0x14000db47  mov     rax, [rax+50h]
0x14000db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db50  mov     [rdi], rsi
0x14000db53  lea     rdi, [rbx+8]
0x14000db57  cmp     rdi, r15
0x14000db5a  jz      short loc_14000DB85
0x14000db5c  mov     rsi, [r15]
0x14000db5f  mov     qword ptr [r15], 0
0x14000db66  mov     rcx, [rdi]
0x14000db69  cmp     rsi, rcx
0x14000db6c  jz      short loc_14000DB85
0x14000db6e  test    rcx, rcx
0x14000db71  jz      short loc_14000DB82
0x14000db73  mov     rax, [rcx]
0x14000db76  mov     rax, [rax+80h]
0x14000db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db82  mov     [rdi], rsi
0x14000db85  mov     rcx, [r14]
0x14000db88  cmp     rbx, rcx
0x14000db8b  jz      short loc_14000DBA5
0x14000db8d  test    rcx, rcx
0x14000db90  jz      short loc_14000DBA2
0x14000db92  mov     rax, [rcx]
0x14000db95  mov     edx, 1
0x14000db9a  mov     rax, [rax]
0x14000db9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dba2  mov     [r14], rbx
0x14000dba5  mov     rcx, [rbp+arg_0]
0x14000dba9  test    rcx, rcx
0x14000dbac  jz      short loc_14000DBBB
0x14000dbae  mov     rax, [rcx]
0x14000dbb1  mov     rax, [rax+8]
0x14000dbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbba  nop
0x14000dbbb  mov     rcx, [rbp+var_20]
0x14000dbbf  test    rcx, rcx
0x14000dbc2  jz      short loc_14000DBD1
0x14000dbc4  mov     rdx, [rcx]
0x14000dbc7  mov     rax, [rdx+50h]
0x14000dbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbd0  nop
0x14000dbd1  mov     al, 1
0x14000dbd3  jmp     short loc_14000DC08
0x14000dbd5  mov     rcx, [rbp+arg_0]
0x14000dbd9  test    rcx, rcx
0x14000dbdc  jz      short loc_14000DBEB
0x14000dbde  mov     rax, [rcx]
0x14000dbe1  mov     rax, [rax+8]
0x14000dbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbea  nop
0x14000dbeb  mov     rcx, [rbp+var_20]
0x14000dbef  test    rcx, rcx
0x14000dbf2  jz      short loc_14000DC06
0x14000dbf4  test    rcx, rcx
0x14000dbf7  jz      short loc_14000DC06
0x14000dbf9  mov     rax, [rcx]
0x14000dbfc  mov     rax, [rax+50h]
0x14000dc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc05  nop
0x14000dc06  xor     al, al
0x14000dc08  mov     rbx, [rsp+40h+arg_10]
0x14000dc10  add     rsp, 40h
0x14000dc14  pop     r15
0x14000dc16  pop     r14
0x14000dc18  pop     rdi
0x14000dc19  pop     rsi
0x14000dc1a  pop     rbp
0x14000dc1b  retn
```
