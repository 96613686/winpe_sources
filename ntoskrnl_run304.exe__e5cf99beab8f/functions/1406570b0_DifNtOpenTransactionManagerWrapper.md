# DifNtOpenTransactionManagerWrapper

- ea: `0x1406570b0`
- end: `0x140657244`
- name: `DifNtOpenTransactionManagerWrapper`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x1406570b0`
- `0x1406e8590`
- `0x1406f4880`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransactionManager` at `0x1406571b8`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransactionManager` at `0x1406571b8`

## pseudocode

```c
__int64 __fastcall DifNtOpenTransactionManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        UNICODE_STRING *a4,
        GUID *TmIdentity,
        ULONG OpenOptions)
{
  __int64 APIThunkContextById; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r14
  int v13; // ecx
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  BOOLEAN v18; // di
  _QWORD *j; // rbx
  __int64 ReturnAddressForWrappers; // [rsp+30h] [rbp-48h] BYREF
  ULONG v22; // [rsp+38h] [rbp-40h]
  GUID *v23; // [rsp+40h] [rbp-38h]
  UNICODE_STRING *v24; // [rsp+48h] [rbp-30h]
  OBJECT_ATTRIBUTES *v25; // [rsp+50h] [rbp-28h]
  ACCESS_MASK v26; // [rsp+58h] [rbp-20h]
  HANDLE *v27; // [rsp+60h] [rbp-18h]
  unsigned int v28; // [rsp+68h] [rbp-10h]
  __int64 retaddr; // [rsp+B8h] [rbp+40h]

  memset_0(&ReturnAddressForWrappers, 0, 0x40u);
  APIThunkContextById = DifGetAPIThunkContextById(531);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      ReturnAddressForWrappers = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      ReturnAddressForWrappers = DifGetReturnAddressForWrappers();
    }
    v27 = a1;
    v23 = TmIdentity;
    v22 = OpenOptions;
    v26 = a2;
    v25 = a3;
    v24 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v12 + 32); i != (_QWORD *)(v12 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&ReturnAddressForWrappers, v10, v11);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  v28 = NtOpenTransactionManager(a1, a2, a3, a4, TmIdentity, OpenOptions);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v18 = 0, (VfOptionFlags & 0x800) == 0)
      || (v18 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v12 + 48); j != (_QWORD *)(v12 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&ReturnAddressForWrappers, v16, v17);
      }
      if ( v18 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return v28;
}

```

## disassembly

```asm
0x1406570b0  mov     [rsp-40h+TmHandle], rcx
0x1406570b5  push    rbp
0x1406570b6  push    rbx
0x1406570b7  push    rsi
0x1406570b8  push    rdi
0x1406570b9  push    r12
0x1406570bb  push    r13
0x1406570bd  push    r14
0x1406570bf  push    r15
0x1406570c1  mov     rbp, rsp
0x1406570c4  sub     rsp, 78h
0x1406570c8  mov     r13d, edx
0x1406570cb  lea     rcx, [rbp+var_48]; void *
0x1406570cf  xor     edx, edx; Val
0x1406570d1  mov     r12, r8
0x1406570d4  mov     r15, r9
0x1406570d7  lea     r8d, [rdx+40h]; Size
0x1406570db  call    memset_0
0x1406570e0  mov     ecx, 213h
0x1406570e5  call    DifGetAPIThunkContextById
0x1406570ea  mov     r14, rax
0x1406570ed  test    rax, rax
0x1406570f0  jz      loc_14065719B
0x1406570f6  mov     ecx, [rax+0Ch]
0x1406570f9  test    cl, 18h
0x1406570fc  jz      short loc_140657108
0x1406570fe  mov     rcx, [rbp+40h]
0x140657102  mov     [rbp+var_48], rcx
0x140657106  jmp     short loc_140657116
0x140657108  test    cl, 4
0x14065710b  jz      short loc_140657116
0x14065710d  call    DifGetReturnAddressForWrappers
0x140657112  mov     [rbp+var_48], rax
0x140657116  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065711d  mov     rax, [rbp+TmHandle]
0x140657121  mov     [rbp+var_18], rax
0x140657125  mov     rax, [rbp+arg_20]
0x140657129  mov     [rbp+var_38], rax
0x14065712d  mov     eax, [rbp+arg_28]
0x140657130  mov     [rbp+var_40], eax
0x140657133  mov     [rbp+var_20], r13d
0x140657137  mov     [rbp+var_28], r12
0x14065713b  mov     [rbp+var_30], r15
0x14065713f  jnz     short loc_140657150
0x140657141  xor     sil, sil
0x140657144  test    cs:VfOptionFlags, 800h
0x14065714e  jz      short loc_140657163
0x140657150  lea     rcx, DifRebootlessRundown; RunRef
0x140657157  call    ExAcquireRundownProtection_0
0x14065715c  mov     sil, al
0x14065715f  test    al, al
0x140657161  jz      short loc_14065719B
0x140657163  lea     rdi, [r14+20h]
0x140657167  mov     rbx, [rdi]
0x14065716a  jmp     short loc_140657185
0x14065716c  lea     rax, [rbx-10h]
0x140657170  test    rax, rax
0x140657173  jz      short loc_140657182
0x140657175  mov     rax, [rax+8]
0x140657179  lea     rcx, [rbp+var_48]
0x14065717d  call    _guard_dispatch_icall_no_overrides
0x140657182  mov     rbx, [rbx]
0x140657185  cmp     rbx, rdi
0x140657188  jnz     short loc_14065716C
0x14065718a  test    sil, sil
0x14065718d  jz      short loc_14065719B
0x14065718f  lea     rcx, DifRebootlessRundown; RunRef
0x140657196  call    ExReleaseRundownProtection_0
0x14065719b  mov     eax, [rbp+arg_28]
0x14065719e  mov     r9, r15; LogFileName
0x1406571a1  mov     rcx, [rbp+TmHandle]; TmHandle
0x1406571a5  mov     r8, r12; ObjectAttributes
0x1406571a8  mov     [rsp+78h+OpenOptions], eax; OpenOptions
0x1406571ac  mov     edx, r13d; DesiredAccess
0x1406571af  mov     rax, [rbp+arg_20]
0x1406571b3  mov     [rsp+78h+TmIdentity], rax; TmIdentity
0x1406571b8  call    cs:__imp_NtOpenTransactionManager
0x1406571bf  nop     dword ptr [rax+rax+00h]
0x1406571c4  mov     [rbp+var_10], eax
0x1406571c7  test    r14, r14
0x1406571ca  jz      short loc_14065722F
0x1406571cc  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406571d3  jnz     short loc_1406571E4
0x1406571d5  xor     dil, dil
0x1406571d8  test    cs:VfOptionFlags, 800h
0x1406571e2  jz      short loc_1406571F7
0x1406571e4  lea     rcx, DifRebootlessRundown; RunRef
0x1406571eb  call    ExAcquireRundownProtection_0
0x1406571f0  mov     dil, al
0x1406571f3  test    al, al
0x1406571f5  jz      short loc_14065722F
0x1406571f7  lea     rsi, [r14+30h]
0x1406571fb  mov     rbx, [rsi]
0x1406571fe  jmp     short loc_140657219
0x140657200  lea     rax, [rbx-10h]
0x140657204  test    rax, rax
0x140657207  jz      short loc_140657216
0x140657209  mov     rax, [rax+8]
0x14065720d  lea     rcx, [rbp+var_48]
0x140657211  call    _guard_dispatch_icall_no_overrides
0x140657216  mov     rbx, [rbx]
0x140657219  cmp     rbx, rsi
0x14065721c  jnz     short loc_140657200
0x14065721e  test    dil, dil
0x140657221  jz      short loc_14065722F
0x140657223  lea     rcx, DifRebootlessRundown; RunRef
0x14065722a  call    ExReleaseRundownProtection_0
0x14065722f  mov     eax, [rbp+var_10]
0x140657232  add     rsp, 78h
0x140657236  pop     r15
0x140657238  pop     r14
0x14065723a  pop     r13
0x14065723c  pop     r12
0x14065723e  pop     rdi
0x14065723f  pop     rsi
0x140657240  pop     rbx
0x140657241  pop     rbp
0x140657242  retn
```
