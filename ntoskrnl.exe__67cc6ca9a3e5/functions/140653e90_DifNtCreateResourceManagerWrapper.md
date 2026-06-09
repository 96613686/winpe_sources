# DifNtCreateResourceManagerWrapper

- ea: `0x140653e90`
- end: `0x140654039`
- name: `DifNtCreateResourceManagerWrapper`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140653e90`
- `0x1406e8590`
- `0x1406f4880`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateResourceManager` at `0x140653faa`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateResourceManager` at `0x140653faa`

## pseudocode

```c
__int64 __fastcall DifNtCreateResourceManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        GUID *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes,
        ULONG CreateOptions,
        UNICODE_STRING *Description)
{
  __int128 *APIThunkContextById; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int128 *v14; // r14
  __int64 v15; // rcx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v17; // si
  __int128 *i; // rbx
  BOOLEAN v19; // di
  __int128 *j; // rbx
  _QWORD v22[2]; // [rsp+40h] [rbp-51h] BYREF
  ULONG v23; // [rsp+50h] [rbp-41h]
  OBJECT_ATTRIBUTES *v24; // [rsp+58h] [rbp-39h]
  GUID *v25; // [rsp+60h] [rbp-31h]
  void *v26; // [rsp+68h] [rbp-29h]
  ACCESS_MASK v27; // [rsp+70h] [rbp-21h]
  HANDLE *v28; // [rsp+78h] [rbp-19h]
  unsigned int ResourceManager; // [rsp+80h] [rbp-11h]
  __int64 retaddr; // [rsp+D8h] [rbp+47h]

  memset_0(v22, 0, 0x48u);
  APIThunkContextById = DifGetAPIThunkContextById(552);
  v14 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v15 = *((unsigned int *)APIThunkContextById + 3);
  if ( (v15 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v15 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers(v15, v11, v12, v13);
  }
  v22[0] = ReturnAddressForWrappers;
LABEL_7:
  v28 = a1;
  v24 = ObjectAttributes;
  v23 = CreateOptions;
  v22[1] = Description;
  v27 = a2;
  v26 = a3;
  v25 = a4;
  if ( !VfDifRunningWithoutReboot && (v17 = 0, (VfOptionFlags & 0x800) == 0)
    || (v17 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = (__int128 *)*((_QWORD *)v14 + 4); i != v14 + 2; i = *(__int128 **)i )
    {
      if ( i != (__int128 *)16 )
        guard_dispatch_icall_no_overrides(v22);
    }
    if ( v17 )
      ExReleaseRundownProtection_0(&DifRebootlessRundown);
  }
LABEL_17:
  ResourceManager = NtCreateResourceManager(a1, a2, a3, a4, ObjectAttributes, CreateOptions, Description);
  if ( v14 )
  {
    if ( !VfDifRunningWithoutReboot && (v19 = 0, (VfOptionFlags & 0x800) == 0)
      || (v19 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = (__int128 *)*((_QWORD *)v14 + 6); j != v14 + 3; j = *(__int128 **)j )
      {
        if ( j != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(v22);
      }
      if ( v19 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return ResourceManager;
}

```

## disassembly

```asm
0x140653e90  mov     [rsp-8+ResourceManagerHandle], rcx
0x140653e95  push    rbp
0x140653e96  push    rbx
0x140653e97  push    rsi
0x140653e98  push    rdi
0x140653e99  push    r12
0x140653e9b  push    r13
0x140653e9d  push    r14
0x140653e9f  push    r15
0x140653ea1  lea     rbp, [rsp-7]
0x140653ea6  sub     rsp, 98h
0x140653ead  mov     r13d, edx
0x140653eb0  lea     rcx, [rbp+3Fh+var_90]; void *
0x140653eb4  xor     edx, edx; Val
0x140653eb6  mov     r12, r8
0x140653eb9  mov     r15, r9
0x140653ebc  lea     r8d, [rdx+48h]; Size
0x140653ec0  call    memset_0
0x140653ec5  mov     ecx, 228h
0x140653eca  call    DifGetAPIThunkContextById
0x140653ecf  mov     r14, rax
0x140653ed2  test    rax, rax
0x140653ed5  jz      loc_140653F84
0x140653edb  mov     ecx, [rax+0Ch]
0x140653ede  test    cl, 18h
0x140653ee1  jz      short loc_140653EE9
0x140653ee3  mov     rax, [rbp+47h]
0x140653ee7  jmp     short loc_140653EF3
0x140653ee9  test    cl, 4
0x140653eec  jz      short loc_140653EF7
0x140653eee  call    DifGetReturnAddressForWrappers
0x140653ef3  mov     [rbp+3Fh+var_90], rax
0x140653ef7  cmp     cs:VfDifRunningWithoutReboot, 0
0x140653efe  mov     rax, [rbp+3Fh+ResourceManagerHandle]
0x140653f02  mov     [rbp+3Fh+var_58], rax
0x140653f06  mov     rax, [rbp+3Fh+arg_20]
0x140653f0a  mov     [rbp+3Fh+var_78], rax
0x140653f0e  mov     eax, [rbp+3Fh+arg_28]
0x140653f11  mov     [rbp+3Fh+var_80], eax
0x140653f14  mov     rax, [rbp+3Fh+arg_30]
0x140653f18  mov     [rbp+3Fh+var_88], rax
0x140653f1c  mov     [rbp+3Fh+var_60], r13d
0x140653f20  mov     [rbp+3Fh+var_68], r12
0x140653f24  mov     [rbp+3Fh+var_70], r15
0x140653f28  jnz     short loc_140653F39
0x140653f2a  xor     sil, sil
0x140653f2d  test    cs:VfOptionFlags, 800h
0x140653f37  jz      short loc_140653F4C
0x140653f39  lea     rcx, DifRebootlessRundown; RunRef
0x140653f40  call    ExAcquireRundownProtection_0
0x140653f45  mov     sil, al
0x140653f48  test    al, al
0x140653f4a  jz      short loc_140653F84
0x140653f4c  lea     rdi, [r14+20h]
0x140653f50  mov     rbx, [rdi]
0x140653f53  jmp     short loc_140653F6E
0x140653f55  lea     rax, [rbx-10h]
0x140653f59  test    rax, rax
0x140653f5c  jz      short loc_140653F6B
0x140653f5e  mov     rax, [rax+8]
0x140653f62  lea     rcx, [rbp+3Fh+var_90]
0x140653f66  call    _guard_dispatch_icall_no_overrides
0x140653f6b  mov     rbx, [rbx]
0x140653f6e  cmp     rbx, rdi
0x140653f71  jnz     short loc_140653F55
0x140653f73  test    sil, sil
0x140653f76  jz      short loc_140653F84
0x140653f78  lea     rcx, DifRebootlessRundown; RunRef
0x140653f7f  call    ExReleaseRundownProtection_0
0x140653f84  mov     rax, [rbp+3Fh+arg_30]
0x140653f88  mov     r9, r15; RmGuid
0x140653f8b  mov     rcx, [rbp+3Fh+ResourceManagerHandle]; ResourceManagerHandle
0x140653f8f  mov     r8, r12; TmHandle
0x140653f92  mov     [rsp+0D0h+Description], rax; Description
0x140653f97  mov     edx, r13d; DesiredAccess
0x140653f9a  mov     eax, [rbp+3Fh+arg_28]
0x140653f9d  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x140653fa1  mov     rax, [rbp+3Fh+arg_20]
0x140653fa5  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x140653faa  call    cs:__imp_NtCreateResourceManager
0x140653fb1  nop     dword ptr [rax+rax+00h]
0x140653fb6  mov     [rbp+3Fh+var_50], eax
0x140653fb9  test    r14, r14
0x140653fbc  jz      short loc_140654021
0x140653fbe  cmp     cs:VfDifRunningWithoutReboot, 0
0x140653fc5  jnz     short loc_140653FD6
0x140653fc7  xor     dil, dil
0x140653fca  test    cs:VfOptionFlags, 800h
0x140653fd4  jz      short loc_140653FE9
0x140653fd6  lea     rcx, DifRebootlessRundown; RunRef
0x140653fdd  call    ExAcquireRundownProtection_0
0x140653fe2  mov     dil, al
0x140653fe5  test    al, al
0x140653fe7  jz      short loc_140654021
0x140653fe9  lea     rsi, [r14+30h]
0x140653fed  mov     rbx, [rsi]
0x140653ff0  jmp     short loc_14065400B
0x140653ff2  lea     rax, [rbx-10h]
0x140653ff6  test    rax, rax
0x140653ff9  jz      short loc_140654008
0x140653ffb  mov     rax, [rax+8]
0x140653fff  lea     rcx, [rbp+3Fh+var_90]
0x140654003  call    _guard_dispatch_icall_no_overrides
0x140654008  mov     rbx, [rbx]
0x14065400b  cmp     rbx, rsi
0x14065400e  jnz     short loc_140653FF2
0x140654010  test    dil, dil
0x140654013  jz      short loc_140654021
0x140654015  lea     rcx, DifRebootlessRundown; RunRef
0x14065401c  call    ExReleaseRundownProtection_0
0x140654021  mov     eax, [rbp+3Fh+var_50]
0x140654024  add     rsp, 98h
0x14065402b  pop     r15
0x14065402d  pop     r14
0x14065402f  pop     r13
0x140654031  pop     r12
0x140654033  pop     rdi
0x140654034  pop     rsi
0x140654035  pop     rbx
0x140654036  pop     rbp
0x140654037  retn
```
