# DifNtOpenResourceManagerWrapper

- ea: `0x14065c570`
- end: `0x14065c6fd`
- name: `DifNtOpenResourceManagerWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065c570`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenResourceManager` at `0x14065c671`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenResourceManager` at `0x14065c671`

## pseudocode

```c
__int64 __fastcall DifNtOpenResourceManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        GUID *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes)
{
  __int64 APIThunkContextById; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r14
  int v13; // ecx
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  BOOLEAN v19; // di
  _QWORD *j; // rbx
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  __int128 v23; // [rsp+40h] [rbp-38h]
  __int128 v24; // [rsp+50h] [rbp-28h]
  __int64 v25; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v25 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(553);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      *(_QWORD *)&v22 = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      *(_QWORD *)&v22 = DifGetReturnAddressForWrappers();
    }
    *((_QWORD *)&v24 + 1) = a1;
    *((_QWORD *)&v22 + 1) = ObjectAttributes;
    LODWORD(v24) = a2;
    *((_QWORD *)&v23 + 1) = a3;
    *(_QWORD *)&v23 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v12 + 32); i != (_QWORD *)(v12 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v9, v10, v11);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v25) = NtOpenResourceManager(a1, a2, a3, a4, ObjectAttributes);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v19 = 0, (VfOptionFlags & 0x800) == 0)
      || (v19 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v12 + 48); j != (_QWORD *)(v12 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v16, v17, v18);
      }
      if ( v19 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14065c570  mov     [rsp-40h+ResourceManagerHandle], rcx
0x14065c575  push    rbp
0x14065c576  push    rbx
0x14065c577  push    rsi
0x14065c578  push    rdi
0x14065c579  push    r12
0x14065c57b  push    r13
0x14065c57d  push    r14
0x14065c57f  push    r15
0x14065c581  mov     rbp, rsp
0x14065c584  sub     rsp, 78h
0x14065c588  xorps   xmm0, xmm0
0x14065c58b  xor     eax, eax
0x14065c58d  mov     ecx, 229h
0x14065c592  mov     [rbp+var_18], rax
0x14065c596  movups  [rbp+var_48], xmm0
0x14065c59a  mov     r15, r9
0x14065c59d  mov     r12, r8
0x14065c5a0  movups  [rbp+var_38], xmm0
0x14065c5a4  mov     r13d, edx
0x14065c5a7  movups  [rbp+var_28], xmm0
0x14065c5ab  call    DifGetAPIThunkContextById
0x14065c5b0  mov     r14, rax
0x14065c5b3  test    rax, rax
0x14065c5b6  jz      loc_14065C65B
0x14065c5bc  mov     ecx, [rax+0Ch]
0x14065c5bf  test    cl, 18h
0x14065c5c2  jz      short loc_14065C5CE
0x14065c5c4  mov     rcx, [rbp+40h]
0x14065c5c8  mov     qword ptr [rbp+var_48], rcx
0x14065c5cc  jmp     short loc_14065C5DC
0x14065c5ce  test    cl, 4
0x14065c5d1  jz      short loc_14065C5DC
0x14065c5d3  call    DifGetReturnAddressForWrappers
0x14065c5d8  mov     qword ptr [rbp+var_48], rax
0x14065c5dc  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065c5e3  mov     rax, [rbp+ResourceManagerHandle]
0x14065c5e7  mov     qword ptr [rbp+var_28+8], rax
0x14065c5eb  mov     rax, [rbp+arg_20]
0x14065c5ef  mov     qword ptr [rbp+var_48+8], rax
0x14065c5f3  mov     dword ptr [rbp+var_28], r13d
0x14065c5f7  mov     qword ptr [rbp+var_38+8], r12
0x14065c5fb  mov     qword ptr [rbp+var_38], r15
0x14065c5ff  jnz     short loc_14065C610
0x14065c601  xor     sil, sil
0x14065c604  test    cs:VfOptionFlags, 800h
0x14065c60e  jz      short loc_14065C623
0x14065c610  lea     rcx, DifRebootlessRundown; RunRef
0x14065c617  call    ExAcquireRundownProtection_0
0x14065c61c  mov     sil, al
0x14065c61f  test    al, al
0x14065c621  jz      short loc_14065C65B
0x14065c623  lea     rdi, [r14+20h]
0x14065c627  mov     rbx, [rdi]
0x14065c62a  jmp     short loc_14065C645
0x14065c62c  lea     rax, [rbx-10h]
0x14065c630  test    rax, rax
0x14065c633  jz      short loc_14065C642
0x14065c635  mov     rax, [rax+8]
0x14065c639  lea     rcx, [rbp+var_48]
0x14065c63d  call    _guard_dispatch_icall_no_overrides
0x14065c642  mov     rbx, [rbx]
0x14065c645  cmp     rbx, rdi
0x14065c648  jnz     short loc_14065C62C
0x14065c64a  test    sil, sil
0x14065c64d  jz      short loc_14065C65B
0x14065c64f  lea     rcx, DifRebootlessRundown; RunRef
0x14065c656  call    ExReleaseRundownProtection_0
0x14065c65b  mov     rax, [rbp+arg_20]
0x14065c65f  mov     r9, r15; ResourceManagerGuid
0x14065c662  mov     rcx, [rbp+ResourceManagerHandle]; ResourceManagerHandle
0x14065c666  mov     r8, r12; TmHandle
0x14065c669  mov     edx, r13d; DesiredAccess
0x14065c66c  mov     [rsp+78h+ObjectAttributes], rax; ObjectAttributes
0x14065c671  call    cs:__imp_NtOpenResourceManager
0x14065c678  nop     dword ptr [rax+rax+00h]
0x14065c67d  mov     dword ptr [rbp+var_18], eax
0x14065c680  test    r14, r14
0x14065c683  jz      short loc_14065C6E8
0x14065c685  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065c68c  jnz     short loc_14065C69D
0x14065c68e  xor     dil, dil
0x14065c691  test    cs:VfOptionFlags, 800h
0x14065c69b  jz      short loc_14065C6B0
0x14065c69d  lea     rcx, DifRebootlessRundown; RunRef
0x14065c6a4  call    ExAcquireRundownProtection_0
0x14065c6a9  mov     dil, al
0x14065c6ac  test    al, al
0x14065c6ae  jz      short loc_14065C6E8
0x14065c6b0  lea     rsi, [r14+30h]
0x14065c6b4  mov     rbx, [rsi]
0x14065c6b7  jmp     short loc_14065C6D2
0x14065c6b9  lea     rax, [rbx-10h]
0x14065c6bd  test    rax, rax
0x14065c6c0  jz      short loc_14065C6CF
0x14065c6c2  mov     rax, [rax+8]
0x14065c6c6  lea     rcx, [rbp+var_48]
0x14065c6ca  call    _guard_dispatch_icall_no_overrides
0x14065c6cf  mov     rbx, [rbx]
0x14065c6d2  cmp     rbx, rsi
0x14065c6d5  jnz     short loc_14065C6B9
0x14065c6d7  test    dil, dil
0x14065c6da  jz      short loc_14065C6E8
0x14065c6dc  lea     rcx, DifRebootlessRundown; RunRef
0x14065c6e3  call    ExReleaseRundownProtection_0
0x14065c6e8  mov     eax, dword ptr [rbp+var_18]
0x14065c6eb  add     rsp, 78h
0x14065c6ef  pop     r15
0x14065c6f1  pop     r14
0x14065c6f3  pop     r13
0x14065c6f5  pop     r12
0x14065c6f7  pop     rdi
0x14065c6f8  pop     rsi
0x14065c6f9  pop     rbx
0x14065c6fa  pop     rbp
0x14065c6fb  retn
```
