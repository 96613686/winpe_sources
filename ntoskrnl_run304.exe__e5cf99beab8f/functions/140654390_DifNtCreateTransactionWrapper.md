# DifNtCreateTransactionWrapper

- ea: `0x140654390`
- end: `0x140654576`
- name: `DifNtCreateTransactionWrapper`
- size: `486`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140654390`
- `0x1406e8590`
- `0x1406f4880`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransaction` at `0x1406544e7`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransaction` at `0x1406544e7`

## pseudocode

```c
__int64 __fastcall DifNtCreateTransactionWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        GUID *a4,
        HANDLE TmHandle,
        ULONG CreateOptions,
        ULONG IsolationLevel,
        ULONG IsolationFlags,
        LARGE_INTEGER *Timeout,
        UNICODE_STRING *Description)
{
  __int64 APIThunkContextById; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r14
  int v17; // ecx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v19; // si
  _QWORD *i; // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  BOOLEAN v23; // di
  _QWORD *j; // rbx
  _QWORD v26[3]; // [rsp+50h] [rbp-61h] BYREF
  ULONG v27; // [rsp+68h] [rbp-49h]
  ULONG v28; // [rsp+6Ch] [rbp-45h]
  ULONG v29; // [rsp+70h] [rbp-41h]
  HANDLE v30; // [rsp+78h] [rbp-39h]
  GUID *v31; // [rsp+80h] [rbp-31h]
  OBJECT_ATTRIBUTES *v32; // [rsp+88h] [rbp-29h]
  ACCESS_MASK v33; // [rsp+90h] [rbp-21h]
  HANDLE *v34; // [rsp+98h] [rbp-19h]
  unsigned int Transaction; // [rsp+A0h] [rbp-11h]
  __int64 retaddr; // [rsp+F8h] [rbp+47h]

  memset_0(v26, 0, 0x58u);
  APIThunkContextById = DifGetAPIThunkContextById(534);
  v16 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v17 = *(_DWORD *)(APIThunkContextById + 12);
  if ( (v17 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v17 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers();
  }
  v26[0] = ReturnAddressForWrappers;
LABEL_7:
  v34 = a1;
  v30 = TmHandle;
  v29 = CreateOptions;
  v28 = IsolationLevel;
  v27 = IsolationFlags;
  v26[2] = Timeout;
  v26[1] = Description;
  v33 = a2;
  v32 = a3;
  v31 = a4;
  if ( !VfDifRunningWithoutReboot && (v19 = 0, (VfOptionFlags & 0x800) == 0)
    || (v19 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = *(_QWORD **)(v16 + 32); i != (_QWORD *)(v16 + 32); i = (_QWORD *)*i )
    {
      if ( i != (_QWORD *)16 )
        guard_dispatch_icall_no_overrides(v26, v14, v15);
    }
    if ( v19 )
      ExReleaseRundownProtection_0(&DifRebootlessRundown);
  }
LABEL_17:
  Transaction = NtCreateTransaction(
                  a1,
                  a2,
                  a3,
                  a4,
                  TmHandle,
                  CreateOptions,
                  IsolationLevel,
                  IsolationFlags,
                  Timeout,
                  Description);
  if ( v16 )
  {
    if ( !VfDifRunningWithoutReboot && (v23 = 0, (VfOptionFlags & 0x800) == 0)
      || (v23 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v16 + 48); j != (_QWORD *)(v16 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(v26, v21, v22);
      }
      if ( v23 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return Transaction;
}

```

## disassembly

```asm
0x140654390  mov     [rsp-8+TransactionHandle], rcx
0x140654395  push    rbp
0x140654396  push    rbx
0x140654397  push    rsi
0x140654398  push    rdi
0x140654399  push    r12
0x14065439b  push    r13
0x14065439d  push    r14
0x14065439f  push    r15
0x1406543a1  lea     rbp, [rsp-7]
0x1406543a6  sub     rsp, 0B8h
0x1406543ad  mov     r13d, edx
0x1406543b0  lea     rcx, [rbp+3Fh+var_A0]; void *
0x1406543b4  xor     edx, edx; Val
0x1406543b6  mov     r12, r8
0x1406543b9  mov     r15, r9
0x1406543bc  lea     r8d, [rdx+58h]; Size
0x1406543c0  call    memset_0
0x1406543c5  mov     ecx, 216h
0x1406543ca  call    DifGetAPIThunkContextById
0x1406543cf  mov     r14, rax
0x1406543d2  test    rax, rax
0x1406543d5  jz      loc_1406544A1
0x1406543db  mov     ecx, [rax+0Ch]
0x1406543de  test    cl, 18h
0x1406543e1  jz      short loc_1406543E9
0x1406543e3  mov     rax, [rbp+47h]
0x1406543e7  jmp     short loc_1406543F3
0x1406543e9  test    cl, 4
0x1406543ec  jz      short loc_1406543F7
0x1406543ee  call    DifGetReturnAddressForWrappers
0x1406543f3  mov     [rbp+3Fh+var_A0], rax
0x1406543f7  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406543fe  mov     rax, [rbp+3Fh+TransactionHandle]
0x140654402  mov     [rbp+3Fh+var_58], rax
0x140654406  mov     rax, [rbp+3Fh+arg_20]
0x14065440a  mov     [rbp+3Fh+var_78], rax
0x14065440e  mov     eax, [rbp+3Fh+arg_28]
0x140654411  mov     [rbp+3Fh+var_80], eax
0x140654414  mov     eax, [rbp+3Fh+arg_30]
0x140654417  mov     [rbp+3Fh+var_84], eax
0x14065441a  mov     eax, [rbp+3Fh+arg_38]
0x140654420  mov     [rbp+3Fh+var_88], eax
0x140654423  mov     rax, [rbp+3Fh+arg_40]
0x14065442a  mov     [rbp+3Fh+var_90], rax
0x14065442e  mov     rax, [rbp+3Fh+arg_48]
0x140654435  mov     [rbp+3Fh+var_98], rax
0x140654439  mov     [rbp+3Fh+var_60], r13d
0x14065443d  mov     [rbp+3Fh+var_68], r12
0x140654441  mov     [rbp+3Fh+var_70], r15
0x140654445  jnz     short loc_140654456
0x140654447  xor     sil, sil
0x14065444a  test    cs:VfOptionFlags, 800h
0x140654454  jz      short loc_140654469
0x140654456  lea     rcx, DifRebootlessRundown; RunRef
0x14065445d  call    ExAcquireRundownProtection_0
0x140654462  mov     sil, al
0x140654465  test    al, al
0x140654467  jz      short loc_1406544A1
0x140654469  lea     rdi, [r14+20h]
0x14065446d  mov     rbx, [rdi]
0x140654470  jmp     short loc_14065448B
0x140654472  lea     rax, [rbx-10h]
0x140654476  test    rax, rax
0x140654479  jz      short loc_140654488
0x14065447b  mov     rax, [rax+8]
0x14065447f  lea     rcx, [rbp+3Fh+var_A0]
0x140654483  call    _guard_dispatch_icall_no_overrides
0x140654488  mov     rbx, [rbx]
0x14065448b  cmp     rbx, rdi
0x14065448e  jnz     short loc_140654472
0x140654490  test    sil, sil
0x140654493  jz      short loc_1406544A1
0x140654495  lea     rcx, DifRebootlessRundown; RunRef
0x14065449c  call    ExReleaseRundownProtection_0
0x1406544a1  mov     rax, [rbp+3Fh+arg_48]
0x1406544a8  mov     r9, r15; Uow
0x1406544ab  mov     rcx, [rbp+3Fh+TransactionHandle]; TransactionHandle
0x1406544af  mov     r8, r12; ObjectAttributes
0x1406544b2  mov     [rsp+0F0h+Description], rax; Description
0x1406544b7  mov     edx, r13d; DesiredAccess
0x1406544ba  mov     rax, [rbp+3Fh+arg_40]
0x1406544c1  mov     [rsp+0F0h+Timeout], rax; Timeout
0x1406544c6  mov     eax, [rbp+3Fh+arg_38]
0x1406544cc  mov     [rsp+0F0h+IsolationFlags], eax; IsolationFlags
0x1406544d0  mov     eax, [rbp+3Fh+arg_30]
0x1406544d3  mov     [rsp+0F0h+IsolationLevel], eax; IsolationLevel
0x1406544d7  mov     eax, [rbp+3Fh+arg_28]
0x1406544da  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x1406544de  mov     rax, [rbp+3Fh+arg_20]
0x1406544e2  mov     [rsp+0F0h+TmHandle], rax; TmHandle
0x1406544e7  call    cs:__imp_NtCreateTransaction
0x1406544ee  nop     dword ptr [rax+rax+00h]
0x1406544f3  mov     [rbp+3Fh+var_50], eax
0x1406544f6  test    r14, r14
0x1406544f9  jz      short loc_14065455E
0x1406544fb  cmp     cs:VfDifRunningWithoutReboot, 0
0x140654502  jnz     short loc_140654513
0x140654504  xor     dil, dil
0x140654507  test    cs:VfOptionFlags, 800h
0x140654511  jz      short loc_140654526
0x140654513  lea     rcx, DifRebootlessRundown; RunRef
0x14065451a  call    ExAcquireRundownProtection_0
0x14065451f  mov     dil, al
0x140654522  test    al, al
0x140654524  jz      short loc_14065455E
0x140654526  lea     rsi, [r14+30h]
0x14065452a  mov     rbx, [rsi]
0x14065452d  jmp     short loc_140654548
0x14065452f  lea     rax, [rbx-10h]
0x140654533  test    rax, rax
0x140654536  jz      short loc_140654545
0x140654538  mov     rax, [rax+8]
0x14065453c  lea     rcx, [rbp+3Fh+var_A0]
0x140654540  call    _guard_dispatch_icall_no_overrides
0x140654545  mov     rbx, [rbx]
0x140654548  cmp     rbx, rsi
0x14065454b  jnz     short loc_14065452F
0x14065454d  test    dil, dil
0x140654550  jz      short loc_14065455E
0x140654552  lea     rcx, DifRebootlessRundown; RunRef
0x140654559  call    ExReleaseRundownProtection_0
0x14065455e  mov     eax, [rbp+3Fh+var_50]
0x140654561  add     rsp, 0B8h
0x140654568  pop     r15
0x14065456a  pop     r14
0x14065456c  pop     r13
0x14065456e  pop     r12
0x140654570  pop     rdi
0x140654571  pop     rsi
0x140654572  pop     rbx
0x140654573  pop     rbp
0x140654574  retn
```
