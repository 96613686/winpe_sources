# DifNtCreateEnlistmentWrapper

- ea: `0x140659430`
- end: `0x1406595ec`
- name: `DifNtCreateEnlistmentWrapper`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x140659430`
- `0x1406eb0e0`
- `0x1406f7380`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateEnlistment` at `0x14065955d`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateEnlistment` at `0x14065955d`

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
  __int64 APIThunkContextById; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v17; // si
  _QWORD *i; // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  BOOLEAN v21; // di
  _QWORD *j; // rbx
  _QWORD v24[2]; // [rsp+40h] [rbp-51h] BYREF
  NOTIFICATION_MASK v25; // [rsp+50h] [rbp-41h]
  ULONG v26; // [rsp+54h] [rbp-3Dh]
  OBJECT_ATTRIBUTES *v27; // [rsp+58h] [rbp-39h]
  void *v28; // [rsp+60h] [rbp-31h]
  void *v29; // [rsp+68h] [rbp-29h]
  ACCESS_MASK v30; // [rsp+70h] [rbp-21h]
  HANDLE *v31; // [rsp+78h] [rbp-19h]
  unsigned int Enlistment; // [rsp+80h] [rbp-11h]
  __int64 retaddr; // [rsp+D8h] [rbp+47h]

  memset_0(v24, 0, 0x48u);
  APIThunkContextById = DifGetAPIThunkContextById(538);
  v14 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v15 = *(unsigned int *)(APIThunkContextById + 12);
  if ( (v15 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v15 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers(v15, v12, v13);
  }
  v24[0] = ReturnAddressForWrappers;
LABEL_7:
  v31 = a1;
  v27 = ObjectAttributes;
  v26 = CreateOptions;
  v25 = NotificationMask;
  v24[1] = EnlistmentKey;
  v30 = a2;
  v29 = a3;
  v28 = a4;
  if ( !VfDifRunningWithoutReboot && (v17 = 0, (VfOptionFlags & 0x800) == 0)
    || (v17 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = *(_QWORD **)(v14 + 32); i != (_QWORD *)(v14 + 32); i = (_QWORD *)*i )
    {
      if ( i != (_QWORD *)16 )
        guard_dispatch_icall_no_overrides(v24, v12, v13);
    }
    if ( v17 )
      ExReleaseRundownProtection_0(&DifRebootlessRundown);
  }
LABEL_17:
  Enlistment = NtCreateEnlistment(a1, a2, a3, a4, ObjectAttributes, CreateOptions, NotificationMask, EnlistmentKey);
  if ( v14 )
  {
    if ( !VfDifRunningWithoutReboot && (v21 = 0, (VfOptionFlags & 0x800) == 0)
      || (v21 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v14 + 48); j != (_QWORD *)(v14 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(v24, v19, v20);
      }
      if ( v21 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return Enlistment;
}

```

## disassembly

```asm
0x140659430  mov     [rsp-8+EnlistmentHandle], rcx
0x140659435  push    rbp
0x140659436  push    rbx
0x140659437  push    rsi
0x140659438  push    rdi
0x140659439  push    r12
0x14065943b  push    r13
0x14065943d  push    r14
0x14065943f  push    r15
0x140659441  lea     rbp, [rsp-7]
0x140659446  sub     rsp, 98h
0x14065944d  mov     r13d, edx
0x140659450  lea     rcx, [rbp+3Fh+var_90]; void *
0x140659454  xor     edx, edx; Val
0x140659456  mov     r12, r8
0x140659459  mov     r15, r9
0x14065945c  lea     r8d, [rdx+48h]; Size
0x140659460  call    memset_0
0x140659465  mov     ecx, 21Ah
0x14065946a  call    DifGetAPIThunkContextById
0x14065946f  mov     r14, rax
0x140659472  test    rax, rax
0x140659475  jz      loc_14065952D
0x14065947b  mov     ecx, [rax+0Ch]
0x14065947e  test    cl, 18h
0x140659481  jz      short loc_140659489
0x140659483  mov     rax, [rbp+47h]
0x140659487  jmp     short loc_140659493
0x140659489  test    cl, 4
0x14065948c  jz      short loc_140659497
0x14065948e  call    DifGetReturnAddressForWrappers
0x140659493  mov     [rbp+3Fh+var_90], rax
0x140659497  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065949e  mov     rax, [rbp+3Fh+EnlistmentHandle]
0x1406594a2  mov     [rbp+3Fh+var_58], rax
0x1406594a6  mov     rax, [rbp+3Fh+arg_20]
0x1406594aa  mov     [rbp+3Fh+var_78], rax
0x1406594ae  mov     eax, [rbp+3Fh+arg_28]
0x1406594b1  mov     [rbp+3Fh+var_7C], eax
0x1406594b4  mov     eax, [rbp+3Fh+arg_30]
0x1406594b7  mov     [rbp+3Fh+var_80], eax
0x1406594ba  mov     rax, [rbp+3Fh+arg_38]
0x1406594c1  mov     [rbp+3Fh+var_88], rax
0x1406594c5  mov     [rbp+3Fh+var_60], r13d
0x1406594c9  mov     [rbp+3Fh+var_68], r12
0x1406594cd  mov     [rbp+3Fh+var_70], r15
0x1406594d1  jnz     short loc_1406594E2
0x1406594d3  xor     sil, sil
0x1406594d6  test    cs:VfOptionFlags, 800h
0x1406594e0  jz      short loc_1406594F5
0x1406594e2  lea     rcx, DifRebootlessRundown; RunRef
0x1406594e9  call    ExAcquireRundownProtection_0
0x1406594ee  mov     sil, al
0x1406594f1  test    al, al
0x1406594f3  jz      short loc_14065952D
0x1406594f5  lea     rdi, [r14+20h]
0x1406594f9  mov     rbx, [rdi]
0x1406594fc  jmp     short loc_140659517
0x1406594fe  lea     rax, [rbx-10h]
0x140659502  test    rax, rax
0x140659505  jz      short loc_140659514
0x140659507  mov     rax, [rax+8]
0x14065950b  lea     rcx, [rbp+3Fh+var_90]
0x14065950f  call    _guard_dispatch_icall_no_overrides
0x140659514  mov     rbx, [rbx]
0x140659517  cmp     rbx, rdi
0x14065951a  jnz     short loc_1406594FE
0x14065951c  test    sil, sil
0x14065951f  jz      short loc_14065952D
0x140659521  lea     rcx, DifRebootlessRundown; RunRef
0x140659528  call    ExReleaseRundownProtection_0
0x14065952d  mov     rax, [rbp+3Fh+arg_38]
0x140659534  mov     r9, r15; TransactionHandle
0x140659537  mov     rcx, [rbp+3Fh+EnlistmentHandle]; EnlistmentHandle
0x14065953b  mov     r8, r12; ResourceManagerHandle
0x14065953e  mov     [rsp+0D0h+EnlistmentKey], rax; EnlistmentKey
0x140659543  mov     edx, r13d; DesiredAccess
0x140659546  mov     eax, [rbp+3Fh+arg_30]
0x140659549  mov     [rsp+0D0h+NotificationMask], eax; NotificationMask
0x14065954d  mov     eax, [rbp+3Fh+arg_28]
0x140659550  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x140659554  mov     rax, [rbp+3Fh+arg_20]
0x140659558  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x14065955d  call    cs:__imp_NtCreateEnlistment
0x140659564  nop     dword ptr [rax+rax+00h]
0x140659569  mov     [rbp+3Fh+var_50], eax
0x14065956c  test    r14, r14
0x14065956f  jz      short loc_1406595D4
0x140659571  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659578  jnz     short loc_140659589
0x14065957a  xor     dil, dil
0x14065957d  test    cs:VfOptionFlags, 800h
0x140659587  jz      short loc_14065959C
0x140659589  lea     rcx, DifRebootlessRundown; RunRef
0x140659590  call    ExAcquireRundownProtection_0
0x140659595  mov     dil, al
0x140659598  test    al, al
0x14065959a  jz      short loc_1406595D4
0x14065959c  lea     rsi, [r14+30h]
0x1406595a0  mov     rbx, [rsi]
0x1406595a3  jmp     short loc_1406595BE
0x1406595a5  lea     rax, [rbx-10h]
0x1406595a9  test    rax, rax
0x1406595ac  jz      short loc_1406595BB
0x1406595ae  mov     rax, [rax+8]
0x1406595b2  lea     rcx, [rbp+3Fh+var_90]
0x1406595b6  call    _guard_dispatch_icall_no_overrides
0x1406595bb  mov     rbx, [rbx]
0x1406595be  cmp     rbx, rsi
0x1406595c1  jnz     short loc_1406595A5
0x1406595c3  test    dil, dil
0x1406595c6  jz      short loc_1406595D4
0x1406595c8  lea     rcx, DifRebootlessRundown; RunRef
0x1406595cf  call    ExReleaseRundownProtection_0
0x1406595d4  mov     eax, [rbp+3Fh+var_50]
0x1406595d7  add     rsp, 98h
0x1406595de  pop     r15
0x1406595e0  pop     r14
0x1406595e2  pop     r13
0x1406595e4  pop     r12
0x1406595e6  pop     rdi
0x1406595e7  pop     rsi
0x1406595e8  pop     rbx
0x1406595e9  pop     rbp
0x1406595ea  retn
```
