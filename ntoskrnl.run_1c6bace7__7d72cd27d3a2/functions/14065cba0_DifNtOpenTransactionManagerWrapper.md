# DifNtOpenTransactionManagerWrapper

- ea: `0x14065cba0`
- end: `0x14065cd34`
- name: `DifNtOpenTransactionManagerWrapper`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065cba0`
- `0x1406eb0e0`
- `0x1406f7380`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransactionManager` at `0x14065cca8`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransactionManager` at `0x14065cca8`

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
  __int64 v13; // rcx
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
    v13 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      ReturnAddressForWrappers = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      ReturnAddressForWrappers = DifGetReturnAddressForWrappers(v13, v10, v11);
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
0x14065cba0  mov     [rsp-40h+TmHandle], rcx
0x14065cba5  push    rbp
0x14065cba6  push    rbx
0x14065cba7  push    rsi
0x14065cba8  push    rdi
0x14065cba9  push    r12
0x14065cbab  push    r13
0x14065cbad  push    r14
0x14065cbaf  push    r15
0x14065cbb1  mov     rbp, rsp
0x14065cbb4  sub     rsp, 78h
0x14065cbb8  mov     r13d, edx
0x14065cbbb  lea     rcx, [rbp+var_48]; void *
0x14065cbbf  xor     edx, edx; Val
0x14065cbc1  mov     r12, r8
0x14065cbc4  mov     r15, r9
0x14065cbc7  lea     r8d, [rdx+40h]; Size
0x14065cbcb  call    memset_0
0x14065cbd0  mov     ecx, 213h
0x14065cbd5  call    DifGetAPIThunkContextById
0x14065cbda  mov     r14, rax
0x14065cbdd  test    rax, rax
0x14065cbe0  jz      loc_14065CC8B
0x14065cbe6  mov     ecx, [rax+0Ch]
0x14065cbe9  test    cl, 18h
0x14065cbec  jz      short loc_14065CBF8
0x14065cbee  mov     rcx, [rbp+40h]
0x14065cbf2  mov     [rbp+var_48], rcx
0x14065cbf6  jmp     short loc_14065CC06
0x14065cbf8  test    cl, 4
0x14065cbfb  jz      short loc_14065CC06
0x14065cbfd  call    DifGetReturnAddressForWrappers
0x14065cc02  mov     [rbp+var_48], rax
0x14065cc06  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065cc0d  mov     rax, [rbp+TmHandle]
0x14065cc11  mov     [rbp+var_18], rax
0x14065cc15  mov     rax, [rbp+arg_20]
0x14065cc19  mov     [rbp+var_38], rax
0x14065cc1d  mov     eax, [rbp+arg_28]
0x14065cc20  mov     [rbp+var_40], eax
0x14065cc23  mov     [rbp+var_20], r13d
0x14065cc27  mov     [rbp+var_28], r12
0x14065cc2b  mov     [rbp+var_30], r15
0x14065cc2f  jnz     short loc_14065CC40
0x14065cc31  xor     sil, sil
0x14065cc34  test    cs:VfOptionFlags, 800h
0x14065cc3e  jz      short loc_14065CC53
0x14065cc40  lea     rcx, DifRebootlessRundown; RunRef
0x14065cc47  call    ExAcquireRundownProtection_0
0x14065cc4c  mov     sil, al
0x14065cc4f  test    al, al
0x14065cc51  jz      short loc_14065CC8B
0x14065cc53  lea     rdi, [r14+20h]
0x14065cc57  mov     rbx, [rdi]
0x14065cc5a  jmp     short loc_14065CC75
0x14065cc5c  lea     rax, [rbx-10h]
0x14065cc60  test    rax, rax
0x14065cc63  jz      short loc_14065CC72
0x14065cc65  mov     rax, [rax+8]
0x14065cc69  lea     rcx, [rbp+var_48]
0x14065cc6d  call    _guard_dispatch_icall_no_overrides
0x14065cc72  mov     rbx, [rbx]
0x14065cc75  cmp     rbx, rdi
0x14065cc78  jnz     short loc_14065CC5C
0x14065cc7a  test    sil, sil
0x14065cc7d  jz      short loc_14065CC8B
0x14065cc7f  lea     rcx, DifRebootlessRundown; RunRef
0x14065cc86  call    ExReleaseRundownProtection_0
0x14065cc8b  mov     eax, [rbp+arg_28]
0x14065cc8e  mov     r9, r15; LogFileName
0x14065cc91  mov     rcx, [rbp+TmHandle]; TmHandle
0x14065cc95  mov     r8, r12; ObjectAttributes
0x14065cc98  mov     [rsp+78h+OpenOptions], eax; OpenOptions
0x14065cc9c  mov     edx, r13d; DesiredAccess
0x14065cc9f  mov     rax, [rbp+arg_20]
0x14065cca3  mov     [rsp+78h+TmIdentity], rax; TmIdentity
0x14065cca8  call    cs:__imp_NtOpenTransactionManager
0x14065ccaf  nop     dword ptr [rax+rax+00h]
0x14065ccb4  mov     [rbp+var_10], eax
0x14065ccb7  test    r14, r14
0x14065ccba  jz      short loc_14065CD1F
0x14065ccbc  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065ccc3  jnz     short loc_14065CCD4
0x14065ccc5  xor     dil, dil
0x14065ccc8  test    cs:VfOptionFlags, 800h
0x14065ccd2  jz      short loc_14065CCE7
0x14065ccd4  lea     rcx, DifRebootlessRundown; RunRef
0x14065ccdb  call    ExAcquireRundownProtection_0
0x14065cce0  mov     dil, al
0x14065cce3  test    al, al
0x14065cce5  jz      short loc_14065CD1F
0x14065cce7  lea     rsi, [r14+30h]
0x14065cceb  mov     rbx, [rsi]
0x14065ccee  jmp     short loc_14065CD09
0x14065ccf0  lea     rax, [rbx-10h]
0x14065ccf4  test    rax, rax
0x14065ccf7  jz      short loc_14065CD06
0x14065ccf9  mov     rax, [rax+8]
0x14065ccfd  lea     rcx, [rbp+var_48]
0x14065cd01  call    _guard_dispatch_icall_no_overrides
0x14065cd06  mov     rbx, [rbx]
0x14065cd09  cmp     rbx, rsi
0x14065cd0c  jnz     short loc_14065CCF0
0x14065cd0e  test    dil, dil
0x14065cd11  jz      short loc_14065CD1F
0x14065cd13  lea     rcx, DifRebootlessRundown; RunRef
0x14065cd1a  call    ExReleaseRundownProtection_0
0x14065cd1f  mov     eax, [rbp+var_10]
0x14065cd22  add     rsp, 78h
0x14065cd26  pop     r15
0x14065cd28  pop     r14
0x14065cd2a  pop     r13
0x14065cd2c  pop     r12
0x14065cd2e  pop     rdi
0x14065cd2f  pop     rsi
0x14065cd30  pop     rbx
0x14065cd31  pop     rbp
0x14065cd32  retn
```
