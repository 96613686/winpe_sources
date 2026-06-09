# DifNtOpenResourceManagerWrapper

- ea: `0x140656a80`
- end: `0x140656c0d`
- name: `DifNtOpenResourceManagerWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140656a80`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenResourceManager` at `0x140656b81`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenResourceManager` at `0x140656b81`

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
0x140656a80  mov     [rsp-40h+ResourceManagerHandle], rcx
0x140656a85  push    rbp
0x140656a86  push    rbx
0x140656a87  push    rsi
0x140656a88  push    rdi
0x140656a89  push    r12
0x140656a8b  push    r13
0x140656a8d  push    r14
0x140656a8f  push    r15
0x140656a91  mov     rbp, rsp
0x140656a94  sub     rsp, 78h
0x140656a98  xorps   xmm0, xmm0
0x140656a9b  xor     eax, eax
0x140656a9d  mov     ecx, 229h
0x140656aa2  mov     [rbp+var_18], rax
0x140656aa6  movups  [rbp+var_48], xmm0
0x140656aaa  mov     r15, r9
0x140656aad  mov     r12, r8
0x140656ab0  movups  [rbp+var_38], xmm0
0x140656ab4  mov     r13d, edx
0x140656ab7  movups  [rbp+var_28], xmm0
0x140656abb  call    DifGetAPIThunkContextById
0x140656ac0  mov     r14, rax
0x140656ac3  test    rax, rax
0x140656ac6  jz      loc_140656B6B
0x140656acc  mov     ecx, [rax+0Ch]
0x140656acf  test    cl, 18h
0x140656ad2  jz      short loc_140656ADE
0x140656ad4  mov     rcx, [rbp+40h]
0x140656ad8  mov     qword ptr [rbp+var_48], rcx
0x140656adc  jmp     short loc_140656AEC
0x140656ade  test    cl, 4
0x140656ae1  jz      short loc_140656AEC
0x140656ae3  call    DifGetReturnAddressForWrappers
0x140656ae8  mov     qword ptr [rbp+var_48], rax
0x140656aec  cmp     cs:VfDifRunningWithoutReboot, 0
0x140656af3  mov     rax, [rbp+ResourceManagerHandle]
0x140656af7  mov     qword ptr [rbp+var_28+8], rax
0x140656afb  mov     rax, [rbp+arg_20]
0x140656aff  mov     qword ptr [rbp+var_48+8], rax
0x140656b03  mov     dword ptr [rbp+var_28], r13d
0x140656b07  mov     qword ptr [rbp+var_38+8], r12
0x140656b0b  mov     qword ptr [rbp+var_38], r15
0x140656b0f  jnz     short loc_140656B20
0x140656b11  xor     sil, sil
0x140656b14  test    cs:VfOptionFlags, 800h
0x140656b1e  jz      short loc_140656B33
0x140656b20  lea     rcx, DifRebootlessRundown; RunRef
0x140656b27  call    ExAcquireRundownProtection_0
0x140656b2c  mov     sil, al
0x140656b2f  test    al, al
0x140656b31  jz      short loc_140656B6B
0x140656b33  lea     rdi, [r14+20h]
0x140656b37  mov     rbx, [rdi]
0x140656b3a  jmp     short loc_140656B55
0x140656b3c  lea     rax, [rbx-10h]
0x140656b40  test    rax, rax
0x140656b43  jz      short loc_140656B52
0x140656b45  mov     rax, [rax+8]
0x140656b49  lea     rcx, [rbp+var_48]
0x140656b4d  call    _guard_dispatch_icall_no_overrides
0x140656b52  mov     rbx, [rbx]
0x140656b55  cmp     rbx, rdi
0x140656b58  jnz     short loc_140656B3C
0x140656b5a  test    sil, sil
0x140656b5d  jz      short loc_140656B6B
0x140656b5f  lea     rcx, DifRebootlessRundown; RunRef
0x140656b66  call    ExReleaseRundownProtection_0
0x140656b6b  mov     rax, [rbp+arg_20]
0x140656b6f  mov     r9, r15; ResourceManagerGuid
0x140656b72  mov     rcx, [rbp+ResourceManagerHandle]; ResourceManagerHandle
0x140656b76  mov     r8, r12; TmHandle
0x140656b79  mov     edx, r13d; DesiredAccess
0x140656b7c  mov     [rsp+78h+ObjectAttributes], rax; ObjectAttributes
0x140656b81  call    cs:__imp_NtOpenResourceManager
0x140656b88  nop     dword ptr [rax+rax+00h]
0x140656b8d  mov     dword ptr [rbp+var_18], eax
0x140656b90  test    r14, r14
0x140656b93  jz      short loc_140656BF8
0x140656b95  cmp     cs:VfDifRunningWithoutReboot, 0
0x140656b9c  jnz     short loc_140656BAD
0x140656b9e  xor     dil, dil
0x140656ba1  test    cs:VfOptionFlags, 800h
0x140656bab  jz      short loc_140656BC0
0x140656bad  lea     rcx, DifRebootlessRundown; RunRef
0x140656bb4  call    ExAcquireRundownProtection_0
0x140656bb9  mov     dil, al
0x140656bbc  test    al, al
0x140656bbe  jz      short loc_140656BF8
0x140656bc0  lea     rsi, [r14+30h]
0x140656bc4  mov     rbx, [rsi]
0x140656bc7  jmp     short loc_140656BE2
0x140656bc9  lea     rax, [rbx-10h]
0x140656bcd  test    rax, rax
0x140656bd0  jz      short loc_140656BDF
0x140656bd2  mov     rax, [rax+8]
0x140656bd6  lea     rcx, [rbp+var_48]
0x140656bda  call    _guard_dispatch_icall_no_overrides
0x140656bdf  mov     rbx, [rbx]
0x140656be2  cmp     rbx, rsi
0x140656be5  jnz     short loc_140656BC9
0x140656be7  test    dil, dil
0x140656bea  jz      short loc_140656BF8
0x140656bec  lea     rcx, DifRebootlessRundown; RunRef
0x140656bf3  call    ExReleaseRundownProtection_0
0x140656bf8  mov     eax, dword ptr [rbp+var_18]
0x140656bfb  add     rsp, 78h
0x140656bff  pop     r15
0x140656c01  pop     r14
0x140656c03  pop     r13
0x140656c05  pop     r12
0x140656c07  pop     rdi
0x140656c08  pop     rsi
0x140656c09  pop     rbx
0x140656c0a  pop     rbp
0x140656c0b  retn
```
