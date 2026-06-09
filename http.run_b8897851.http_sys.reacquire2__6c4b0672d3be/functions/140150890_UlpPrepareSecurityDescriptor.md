# UlpPrepareSecurityDescriptor

- ea: `0x140150890`
- end: `0x140150a0b`
- name: `UlpPrepareSecurityDescriptor`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401502e0`

## callees

- `0x1401306cc`
- `0x140150890`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140150934`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140150934`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14015094c`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14015094c`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140150916`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140150916`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1401508fc`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150972`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1401508fc`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140150972`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401509c3`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401509e5`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401509c3`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1401509e5`

## pseudocode

```c
__int64 __fastcall UlpPrepareSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        PSECURITY_DESCRIPTOR *a4,
        ULONG *a5)
{
  ULONG *v5; // r14
  PSECURITY_DESCRIPTOR *v6; // rdi
  char v8; // r12
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  ULONG v12; // r15d
  __int64 v13; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v5 = a5;
  v6 = a4;
  SecurityDescriptor = 0;
  v16 = 0;
  v8 = a2;
  *a3 = 0;
  *v5 = 0;
  *a4 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  LOBYTE(a4) = 1;
  v9 = SeCaptureSecurityDescriptor(a1, a2, 1, a4, &SecurityDescriptor);
  if ( v9 < 0 )
    goto LABEL_13;
  if ( RtlValidSecurityDescriptor(SecurityDescriptor)
    && (v12 = RtlLengthSecurityDescriptor(SecurityDescriptor),
        RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v12, 0)) )
  {
    LOBYTE(v13) = 1;
    v9 = SeCaptureSecurityDescriptor(SecurityDescriptor, 0, 1, v13, &v16);
    if ( v9 < 0 )
    {
LABEL_10:
      v16 = 0;
      goto LABEL_11;
    }
    v9 = UlMapGenericMask(v16);
    if ( v9 >= 0 )
    {
      *a3 = v16;
      *v6 = SecurityDescriptor;
      *v5 = v12;
      SecurityDescriptor = 0;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = -1073741811;
  }
LABEL_11:
  if ( !SecurityDescriptor )
    goto LABEL_14;
  LOBYTE(v10) = 1;
  LOBYTE(v11) = v8;
  SeReleaseSecurityDescriptor(SecurityDescriptor, v11, v10);
LABEL_13:
  SecurityDescriptor = 0;
LABEL_14:
  if ( v16 )
  {
    LOBYTE(v10) = 1;
    SeReleaseSecurityDescriptor(v16, 0, v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140150890  mov     [rsp-28h+arg_8], rbx
0x140150895  mov     [rsp-28h+arg_18], rsi
0x14015089a  push    rbp
0x14015089b  push    rdi
0x14015089c  push    r12
0x14015089e  push    r14
0x1401508a0  push    r15
0x1401508a2  mov     rbp, rsp
0x1401508a5  sub     rsp, 30h
0x1401508a9  mov     r14, [rbp+arg_20]
0x1401508ad  mov     rdi, r9
0x1401508b0  mov     [rbp+SecurityDescriptor], 0
0x1401508b8  mov     rsi, r8
0x1401508bb  mov     [rbp+arg_10], 0
0x1401508c3  mov     r12b, dl
0x1401508c6  mov     qword ptr [r8], 0
0x1401508cd  mov     dword ptr [r14], 0
0x1401508d4  mov     qword ptr [r9], 0
0x1401508db  test    rcx, rcx
0x1401508de  jnz     short loc_1401508EA
0x1401508e0  mov     ebx, 0C000000Dh
0x1401508e5  jmp     loc_1401509F1
0x1401508ea  lea     rax, [rbp+SecurityDescriptor]
0x1401508ee  mov     r9b, 1
0x1401508f1  mov     r8d, 1
0x1401508f7  mov     [rsp+30h+var_10], rax
0x1401508fc  call    cs:__imp_SeCaptureSecurityDescriptor
0x140150903  nop     dword ptr [rax+rax+00h]
0x140150908  mov     ebx, eax
0x14015090a  test    eax, eax
0x14015090c  js      loc_1401509CF
0x140150912  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150916  call    cs:__imp_RtlValidSecurityDescriptor
0x14015091d  nop     dword ptr [rax+rax+00h]
0x140150922  test    al, al
0x140150924  jnz     short loc_140150930
0x140150926  mov     ebx, 0C000000Dh
0x14015092b  jmp     loc_1401509B4
0x140150930  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140150934  call    cs:__imp_RtlLengthSecurityDescriptor
0x14015093b  nop     dword ptr [rax+rax+00h]
0x140150940  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptorInput
0x140150944  xor     r8d, r8d; RequiredInformation
0x140150947  mov     edx, eax; SecurityDescriptorLength
0x140150949  mov     r15d, eax
0x14015094c  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140150953  nop     dword ptr [rax+rax+00h]
0x140150958  test    al, al
0x14015095a  jz      short loc_140150926
0x14015095c  mov     rcx, [rbp+SecurityDescriptor]
0x140150960  lea     rax, [rbp+arg_10]
0x140150964  xor     edx, edx
0x140150966  mov     [rsp+30h+var_10], rax
0x14015096b  mov     r9b, 1
0x14015096e  lea     r8d, [rdx+1]
0x140150972  call    cs:__imp_SeCaptureSecurityDescriptor
0x140150979  nop     dword ptr [rax+rax+00h]
0x14015097e  mov     ebx, eax
0x140150980  test    eax, eax
0x140150982  js      short loc_1401509AC
0x140150984  mov     rcx, [rbp+arg_10]
0x140150988  call    UlMapGenericMask
0x14015098d  mov     ebx, eax
0x14015098f  test    eax, eax
0x140150991  js      short loc_1401509B4
0x140150993  mov     rax, [rbp+arg_10]
0x140150997  mov     [rsi], rax
0x14015099a  mov     rax, [rbp+SecurityDescriptor]
0x14015099e  mov     [rdi], rax
0x1401509a1  mov     [r14], r15d
0x1401509a4  mov     [rbp+SecurityDescriptor], 0
0x1401509ac  mov     [rbp+arg_10], 0
0x1401509b4  mov     rcx, [rbp+SecurityDescriptor]
0x1401509b8  test    rcx, rcx
0x1401509bb  jz      short loc_1401509D7
0x1401509bd  mov     r8b, 1
0x1401509c0  mov     dl, r12b
0x1401509c3  call    cs:__imp_SeReleaseSecurityDescriptor
0x1401509ca  nop     dword ptr [rax+rax+00h]
0x1401509cf  mov     [rbp+SecurityDescriptor], 0
0x1401509d7  mov     rcx, [rbp+arg_10]
0x1401509db  test    rcx, rcx
0x1401509de  jz      short loc_1401509F1
0x1401509e0  mov     r8b, 1
0x1401509e3  xor     edx, edx
0x1401509e5  call    cs:__imp_SeReleaseSecurityDescriptor
0x1401509ec  nop     dword ptr [rax+rax+00h]
0x1401509f1  mov     rsi, [rsp+30h+arg_18]
0x1401509f6  mov     eax, ebx
0x1401509f8  mov     rbx, [rsp+30h+arg_8]
0x1401509fd  add     rsp, 30h
0x140150a01  pop     r15
0x140150a03  pop     r14
0x140150a05  pop     r12
0x140150a07  pop     rdi
0x140150a08  pop     rbp
0x140150a09  retn
```
