# DifNtCreateTransactionWrapper

- ea: `0x140659e80`
- end: `0x14065a066`
- name: `DifNtCreateTransactionWrapper`
- size: `486`
- prototype: `__int64 __fastcall(HANDLE *, ACCESS_MASK, OBJECT_ATTRIBUTES *, GUID *, HANDLE TmHandle, ULONG CreateOptions, ULONG IsolationLevel, ULONG IsolationFlags, LARGE_INTEGER *Timeout, UNICODE_STRING *Description)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x140659e80`
- `0x1406eb0e0`
- `0x1406f7380`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransaction` at `0x140659fd7`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransaction` at `0x140659fd7`

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
  __int64 v16; // r9
  __int64 v17; // r14
  __int64 v18; // rcx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v20; // si
  _QWORD *i; // rbx
  __int64 v22; // rdx
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
  v17 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v18 = *(unsigned int *)(APIThunkContextById + 12);
  if ( (v18 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v18 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers(v18, v14, v15, v16);
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
  if ( !VfDifRunningWithoutReboot && (v20 = 0, (VfOptionFlags & 0x800) == 0)
    || (v20 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = *(_QWORD **)(v17 + 32); i != (_QWORD *)(v17 + 32); i = (_QWORD *)*i )
    {
      if ( i != (_QWORD *)16 )
        guard_dispatch_icall_no_overrides(v26, v14);
    }
    if ( v20 )
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
  if ( v17 )
  {
    if ( !VfDifRunningWithoutReboot && (v23 = 0, (VfOptionFlags & 0x800) == 0)
      || (v23 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v17 + 48); j != (_QWORD *)(v17 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(v26, v22);
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
0x140659e80  mov     [rsp-8+TransactionHandle], rcx
0x140659e85  push    rbp
0x140659e86  push    rbx
0x140659e87  push    rsi
0x140659e88  push    rdi
0x140659e89  push    r12
0x140659e8b  push    r13
0x140659e8d  push    r14
0x140659e8f  push    r15
0x140659e91  lea     rbp, [rsp-7]
0x140659e96  sub     rsp, 0B8h
0x140659e9d  mov     r13d, edx
0x140659ea0  lea     rcx, [rbp+3Fh+var_A0]; void *
0x140659ea4  xor     edx, edx; Val
0x140659ea6  mov     r12, r8
0x140659ea9  mov     r15, r9
0x140659eac  lea     r8d, [rdx+58h]; Size
0x140659eb0  call    memset_0
0x140659eb5  mov     ecx, 216h
0x140659eba  call    DifGetAPIThunkContextById
0x140659ebf  mov     r14, rax
0x140659ec2  test    rax, rax
0x140659ec5  jz      loc_140659F91
0x140659ecb  mov     ecx, [rax+0Ch]
0x140659ece  test    cl, 18h
0x140659ed1  jz      short loc_140659ED9
0x140659ed3  mov     rax, [rbp+47h]
0x140659ed7  jmp     short loc_140659EE3
0x140659ed9  test    cl, 4
0x140659edc  jz      short loc_140659EE7
0x140659ede  call    DifGetReturnAddressForWrappers
0x140659ee3  mov     [rbp+3Fh+var_A0], rax
0x140659ee7  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659eee  mov     rax, [rbp+3Fh+TransactionHandle]
0x140659ef2  mov     [rbp+3Fh+var_58], rax
0x140659ef6  mov     rax, [rbp+3Fh+arg_20]
0x140659efa  mov     [rbp+3Fh+var_78], rax
0x140659efe  mov     eax, [rbp+3Fh+arg_28]
0x140659f01  mov     [rbp+3Fh+var_80], eax
0x140659f04  mov     eax, [rbp+3Fh+arg_30]
0x140659f07  mov     [rbp+3Fh+var_84], eax
0x140659f0a  mov     eax, [rbp+3Fh+arg_38]
0x140659f10  mov     [rbp+3Fh+var_88], eax
0x140659f13  mov     rax, [rbp+3Fh+arg_40]
0x140659f1a  mov     [rbp+3Fh+var_90], rax
0x140659f1e  mov     rax, [rbp+3Fh+arg_48]
0x140659f25  mov     [rbp+3Fh+var_98], rax
0x140659f29  mov     [rbp+3Fh+var_60], r13d
0x140659f2d  mov     [rbp+3Fh+var_68], r12
0x140659f31  mov     [rbp+3Fh+var_70], r15
0x140659f35  jnz     short loc_140659F46
0x140659f37  xor     sil, sil
0x140659f3a  test    cs:VfOptionFlags, 800h
0x140659f44  jz      short loc_140659F59
0x140659f46  lea     rcx, DifRebootlessRundown; RunRef
0x140659f4d  call    ExAcquireRundownProtection_0
0x140659f52  mov     sil, al
0x140659f55  test    al, al
0x140659f57  jz      short loc_140659F91
0x140659f59  lea     rdi, [r14+20h]
0x140659f5d  mov     rbx, [rdi]
0x140659f60  jmp     short loc_140659F7B
0x140659f62  lea     rax, [rbx-10h]
0x140659f66  test    rax, rax
0x140659f69  jz      short loc_140659F78
0x140659f6b  mov     rax, [rax+8]
0x140659f6f  lea     rcx, [rbp+3Fh+var_A0]
0x140659f73  call    _guard_dispatch_icall_no_overrides
0x140659f78  mov     rbx, [rbx]
0x140659f7b  cmp     rbx, rdi
0x140659f7e  jnz     short loc_140659F62
0x140659f80  test    sil, sil
0x140659f83  jz      short loc_140659F91
0x140659f85  lea     rcx, DifRebootlessRundown; RunRef
0x140659f8c  call    ExReleaseRundownProtection_0
0x140659f91  mov     rax, [rbp+3Fh+arg_48]
0x140659f98  mov     r9, r15; Uow
0x140659f9b  mov     rcx, [rbp+3Fh+TransactionHandle]; TransactionHandle
0x140659f9f  mov     r8, r12; ObjectAttributes
0x140659fa2  mov     [rsp+0F0h+Description], rax; Description
0x140659fa7  mov     edx, r13d; DesiredAccess
0x140659faa  mov     rax, [rbp+3Fh+arg_40]
0x140659fb1  mov     [rsp+0F0h+Timeout], rax; Timeout
0x140659fb6  mov     eax, [rbp+3Fh+arg_38]
0x140659fbc  mov     [rsp+0F0h+IsolationFlags], eax; IsolationFlags
0x140659fc0  mov     eax, [rbp+3Fh+arg_30]
0x140659fc3  mov     [rsp+0F0h+IsolationLevel], eax; IsolationLevel
0x140659fc7  mov     eax, [rbp+3Fh+arg_28]
0x140659fca  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x140659fce  mov     rax, [rbp+3Fh+arg_20]
0x140659fd2  mov     [rsp+0F0h+TmHandle], rax; TmHandle
0x140659fd7  call    cs:__imp_NtCreateTransaction
0x140659fde  nop     dword ptr [rax+rax+00h]
0x140659fe3  mov     [rbp+3Fh+var_50], eax
0x140659fe6  test    r14, r14
0x140659fe9  jz      short loc_14065A04E
0x140659feb  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659ff2  jnz     short loc_14065A003
0x140659ff4  xor     dil, dil
0x140659ff7  test    cs:VfOptionFlags, 800h
0x14065a001  jz      short loc_14065A016
0x14065a003  lea     rcx, DifRebootlessRundown; RunRef
0x14065a00a  call    ExAcquireRundownProtection_0
0x14065a00f  mov     dil, al
0x14065a012  test    al, al
0x14065a014  jz      short loc_14065A04E
0x14065a016  lea     rsi, [r14+30h]
0x14065a01a  mov     rbx, [rsi]
0x14065a01d  jmp     short loc_14065A038
0x14065a01f  lea     rax, [rbx-10h]
0x14065a023  test    rax, rax
0x14065a026  jz      short loc_14065A035
0x14065a028  mov     rax, [rax+8]
0x14065a02c  lea     rcx, [rbp+3Fh+var_A0]
0x14065a030  call    _guard_dispatch_icall_no_overrides
0x14065a035  mov     rbx, [rbx]
0x14065a038  cmp     rbx, rsi
0x14065a03b  jnz     short loc_14065A01F
0x14065a03d  test    dil, dil
0x14065a040  jz      short loc_14065A04E
0x14065a042  lea     rcx, DifRebootlessRundown; RunRef
0x14065a049  call    ExReleaseRundownProtection_0
0x14065a04e  mov     eax, [rbp+3Fh+var_50]
0x14065a051  add     rsp, 0B8h
0x14065a058  pop     r15
0x14065a05a  pop     r14
0x14065a05c  pop     r13
0x14065a05e  pop     r12
0x14065a060  pop     rdi
0x14065a061  pop     rsi
0x14065a062  pop     rbx
0x14065a063  pop     rbp
0x14065a064  retn
```
