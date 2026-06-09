# DifNtCreateEnlistmentWrapper

- ea: `0x140653940`
- end: `0x140653afc`
- name: `DifNtCreateEnlistmentWrapper`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140653940`
- `0x1406e8590`
- `0x1406f4880`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateEnlistment` at `0x140653a6d`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateEnlistment` at `0x140653a6d`

## pseudocode

```c
__int64 __fastcall DifNtCreateEnlistmentWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        void *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes,
        ULONG CreateOptions,
        NOTIFICATION_MASK NotificationMask,
        PVOID EnlistmentKey)
{
  __int128 *APIThunkContextById; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int128 *v15; // r14
  __int64 v16; // rcx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v18; // si
  __int128 *i; // rbx
  BOOLEAN v20; // di
  __int128 *j; // rbx
  _QWORD v23[2]; // [rsp+40h] [rbp-51h] BYREF
  NOTIFICATION_MASK v24; // [rsp+50h] [rbp-41h]
  ULONG v25; // [rsp+54h] [rbp-3Dh]
  OBJECT_ATTRIBUTES *v26; // [rsp+58h] [rbp-39h]
  void *v27; // [rsp+60h] [rbp-31h]
  void *v28; // [rsp+68h] [rbp-29h]
  ACCESS_MASK v29; // [rsp+70h] [rbp-21h]
  HANDLE *v30; // [rsp+78h] [rbp-19h]
  unsigned int Enlistment; // [rsp+80h] [rbp-11h]
  __int64 retaddr; // [rsp+D8h] [rbp+47h]

  memset_0(v23, 0, 0x48u);
  APIThunkContextById = DifGetAPIThunkContextById(538);
  v15 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v16 = *((unsigned int *)APIThunkContextById + 3);
  if ( (v16 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v16 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers(v16, v12, v13, v14);
  }
  v23[0] = ReturnAddressForWrappers;
LABEL_7:
  v30 = a1;
  v26 = ObjectAttributes;
  v25 = CreateOptions;
  v24 = NotificationMask;
  v23[1] = EnlistmentKey;
  v29 = a2;
  v28 = a3;
  v27 = a4;
  if ( !VfDifRunningWithoutReboot && (v18 = 0, (VfOptionFlags & 0x800) == 0)
    || (v18 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = (__int128 *)*((_QWORD *)v15 + 4); i != v15 + 2; i = *(__int128 **)i )
    {
      if ( i != (__int128 *)16 )
        guard_dispatch_icall_no_overrides(v23);
    }
    if ( v18 )
      ExReleaseRundownProtection_0(&DifRebootlessRundown);
  }
LABEL_17:
  Enlistment = NtCreateEnlistment(a1, a2, a3, a4, ObjectAttributes, CreateOptions, NotificationMask, EnlistmentKey);
  if ( v15 )
  {
    if ( !VfDifRunningWithoutReboot && (v20 = 0, (VfOptionFlags & 0x800) == 0)
      || (v20 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = (__int128 *)*((_QWORD *)v15 + 6); j != v15 + 3; j = *(__int128 **)j )
      {
        if ( j != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(v23);
      }
      if ( v20 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return Enlistment;
}

```

## disassembly

```asm
0x140653940  mov     [rsp-8+EnlistmentHandle], rcx
0x140653945  push    rbp
0x140653946  push    rbx
0x140653947  push    rsi
0x140653948  push    rdi
0x140653949  push    r12
0x14065394b  push    r13
0x14065394d  push    r14
0x14065394f  push    r15
0x140653951  lea     rbp, [rsp-7]
0x140653956  sub     rsp, 98h
0x14065395d  mov     r13d, edx
0x140653960  lea     rcx, [rbp+3Fh+var_90]; void *
0x140653964  xor     edx, edx; Val
0x140653966  mov     r12, r8
0x140653969  mov     r15, r9
0x14065396c  lea     r8d, [rdx+48h]; Size
0x140653970  call    memset_0
0x140653975  mov     ecx, 21Ah
0x14065397a  call    DifGetAPIThunkContextById
0x14065397f  mov     r14, rax
0x140653982  test    rax, rax
0x140653985  jz      loc_140653A3D
0x14065398b  mov     ecx, [rax+0Ch]
0x14065398e  test    cl, 18h
0x140653991  jz      short loc_140653999
0x140653993  mov     rax, [rbp+47h]
0x140653997  jmp     short loc_1406539A3
0x140653999  test    cl, 4
0x14065399c  jz      short loc_1406539A7
0x14065399e  call    DifGetReturnAddressForWrappers
0x1406539a3  mov     [rbp+3Fh+var_90], rax
0x1406539a7  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406539ae  mov     rax, [rbp+3Fh+EnlistmentHandle]
0x1406539b2  mov     [rbp+3Fh+var_58], rax
0x1406539b6  mov     rax, [rbp+3Fh+arg_20]
0x1406539ba  mov     [rbp+3Fh+var_78], rax
0x1406539be  mov     eax, [rbp+3Fh+arg_28]
0x1406539c1  mov     [rbp+3Fh+var_7C], eax
0x1406539c4  mov     eax, [rbp+3Fh+arg_30]
0x1406539c7  mov     [rbp+3Fh+var_80], eax
0x1406539ca  mov     rax, [rbp+3Fh+arg_38]
0x1406539d1  mov     [rbp+3Fh+var_88], rax
0x1406539d5  mov     [rbp+3Fh+var_60], r13d
0x1406539d9  mov     [rbp+3Fh+var_68], r12
0x1406539dd  mov     [rbp+3Fh+var_70], r15
0x1406539e1  jnz     short loc_1406539F2
0x1406539e3  xor     sil, sil
0x1406539e6  test    cs:VfOptionFlags, 800h
0x1406539f0  jz      short loc_140653A05
0x1406539f2  lea     rcx, DifRebootlessRundown; RunRef
0x1406539f9  call    ExAcquireRundownProtection_0
0x1406539fe  mov     sil, al
0x140653a01  test    al, al
0x140653a03  jz      short loc_140653A3D
0x140653a05  lea     rdi, [r14+20h]
0x140653a09  mov     rbx, [rdi]
0x140653a0c  jmp     short loc_140653A27
0x140653a0e  lea     rax, [rbx-10h]
0x140653a12  test    rax, rax
0x140653a15  jz      short loc_140653A24
0x140653a17  mov     rax, [rax+8]
0x140653a1b  lea     rcx, [rbp+3Fh+var_90]
0x140653a1f  call    _guard_dispatch_icall_no_overrides
0x140653a24  mov     rbx, [rbx]
0x140653a27  cmp     rbx, rdi
0x140653a2a  jnz     short loc_140653A0E
0x140653a2c  test    sil, sil
0x140653a2f  jz      short loc_140653A3D
0x140653a31  lea     rcx, DifRebootlessRundown; RunRef
0x140653a38  call    ExReleaseRundownProtection_0
0x140653a3d  mov     rax, [rbp+3Fh+arg_38]
0x140653a44  mov     r9, r15; TransactionHandle
0x140653a47  mov     rcx, [rbp+3Fh+EnlistmentHandle]; EnlistmentHandle
0x140653a4b  mov     r8, r12; ResourceManagerHandle
0x140653a4e  mov     [rsp+0D0h+EnlistmentKey], rax; EnlistmentKey
0x140653a53  mov     edx, r13d; DesiredAccess
0x140653a56  mov     eax, [rbp+3Fh+arg_30]
0x140653a59  mov     [rsp+0D0h+NotificationMask], eax; NotificationMask
0x140653a5d  mov     eax, [rbp+3Fh+arg_28]
0x140653a60  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x140653a64  mov     rax, [rbp+3Fh+arg_20]
0x140653a68  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x140653a6d  call    cs:__imp_NtCreateEnlistment
0x140653a74  nop     dword ptr [rax+rax+00h]
0x140653a79  mov     [rbp+3Fh+var_50], eax
0x140653a7c  test    r14, r14
0x140653a7f  jz      short loc_140653AE4
0x140653a81  cmp     cs:VfDifRunningWithoutReboot, 0
0x140653a88  jnz     short loc_140653A99
0x140653a8a  xor     dil, dil
0x140653a8d  test    cs:VfOptionFlags, 800h
0x140653a97  jz      short loc_140653AAC
0x140653a99  lea     rcx, DifRebootlessRundown; RunRef
0x140653aa0  call    ExAcquireRundownProtection_0
0x140653aa5  mov     dil, al
0x140653aa8  test    al, al
0x140653aaa  jz      short loc_140653AE4
0x140653aac  lea     rsi, [r14+30h]
0x140653ab0  mov     rbx, [rsi]
0x140653ab3  jmp     short loc_140653ACE
0x140653ab5  lea     rax, [rbx-10h]
0x140653ab9  test    rax, rax
0x140653abc  jz      short loc_140653ACB
0x140653abe  mov     rax, [rax+8]
0x140653ac2  lea     rcx, [rbp+3Fh+var_90]
0x140653ac6  call    _guard_dispatch_icall_no_overrides
0x140653acb  mov     rbx, [rbx]
0x140653ace  cmp     rbx, rsi
0x140653ad1  jnz     short loc_140653AB5
0x140653ad3  test    dil, dil
0x140653ad6  jz      short loc_140653AE4
0x140653ad8  lea     rcx, DifRebootlessRundown; RunRef
0x140653adf  call    ExReleaseRundownProtection_0
0x140653ae4  mov     eax, [rbp+3Fh+var_50]
0x140653ae7  add     rsp, 98h
0x140653aee  pop     r15
0x140653af0  pop     r14
0x140653af2  pop     r13
0x140653af4  pop     r12
0x140653af6  pop     rdi
0x140653af7  pop     rsi
0x140653af8  pop     rbx
0x140653af9  pop     rbp
0x140653afa  retn
```
