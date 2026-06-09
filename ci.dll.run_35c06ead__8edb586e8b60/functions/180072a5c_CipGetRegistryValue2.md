# CipGetRegistryValue2

- ea: `0x180072a5c`
- end: `0x180072d8e`
- name: `CipGetRegistryValue2`
- size: `818`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066d94`
- `0x1800726a4`
- `0x1800dd30c`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x180072a5c`
- `0x180072d94`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180072cd1`
- `ntoskrnl!ExAllocatePool2` at `0x180072cd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072d55`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072d55`
- `ntoskrnl!ZwClose` at `0x180072bf9`
- `ntoskrnl!ZwClose` at `0x180072d3c`
- `ntoskrnl!ZwClose` at `0x180072bf9`
- `ntoskrnl!ZwClose` at `0x180072d3c`
- `ntoskrnl!ZwOpenKey` at `0x180072b55`
- `ntoskrnl!ZwOpenKey` at `0x180072c7e`
- `ntoskrnl!ZwOpenKey` at `0x180072b55`
- `ntoskrnl!ZwOpenKey` at `0x180072c7e`

## pseudocode

```c
__int64 __fastcall CipGetRegistryValue2(__int64 a1, _WORD *a2, __int64 a3, int a4, _QWORD *a5, _DWORD *a6)
{
  void *Pool2; // rdi
  __int64 v9; // r12
  __int64 v10; // rcx
  _WORD *v11; // rax
  NTSTATUS RegistryValueInternal; // ebx
  unsigned __int16 *v13; // rax
  int v14; // ecx
  int v15; // edx
  _WORD *v16; // rax
  __int16 v17; // r12
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v23; // [rsp+80h] [rbp-80h]
  _DWORD *v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[522]; // [rsp+90h] [rbp-70h] BYREF

  v23 = a5;
  v24 = a6;
  LODWORD(v19) = 0;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  Pool2 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  memset(v25, 0, sizeof(v25));
  v9 = 0x7FFF;
  v21 = 0;
  if ( a2 )
  {
    v10 = 0x7FFF;
    v11 = a2;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
        goto LABEL_7;
    }
    *((_QWORD *)&v21 + 1) = a2;
    LOWORD(v21) = -2 - 2 * v10;
    WORD1(v21) = -2 * v10;
  }
LABEL_7:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( RegistryValueInternal >= 0 )
  {
    if ( !a4 )
    {
      RegistryValueInternal = -1073741582;
      goto LABEL_31;
    }
    if ( (unsigned int)(a4 - 1) >= 2 )
    {
      RegistryValueInternal = -1073741822;
      goto LABEL_31;
    }
    RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, 0, (__int64)&v19);
    if ( RegistryValueInternal == -1073741772 )
    {
      if ( !a2 )
        goto LABEL_31;
      v13 = (unsigned __int16 *)*((_QWORD *)&v21 + 1);
      do
      {
        v14 = *(unsigned __int16 *)((char *)a2 + (_QWORD)v13 - *((_QWORD *)&v21 + 1));
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( !v15 )
        goto LABEL_31;
      ZwClose(KeyHandle);
      KeyHandle = 0;
      v16 = a2;
      v21 = 0;
      while ( *v16 )
      {
        ++v16;
        if ( !--v9 )
          goto LABEL_22;
      }
      v17 = 2 * v9;
      *((_QWORD *)&v21 + 1) = a2;
      LOWORD(v21) = -2 - v17;
      WORD1(v21) = -v17;
LABEL_22:
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( RegistryValueInternal < 0 )
        goto LABEL_31;
      RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, 0, (__int64)&v19);
    }
    if ( RegistryValueInternal == -2147483643 )
    {
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)v19, 1668499779);
      if ( !Pool2 )
      {
        RegistryValueInternal = -1073741801;
        goto LABEL_31;
      }
      RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, (__int64)Pool2, (__int64)&v19);
    }
    if ( RegistryValueInternal >= 0 )
    {
      *v23 = Pool2;
      Pool2 = 0;
      *v24 = v19;
    }
  }
LABEL_31:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  return (unsigned int)RegistryValueInternal;
}

```

## disassembly

```asm
0x180072a5c  mov     [rsp-8+arg_0], rbx
0x180072a61  push    rbp
0x180072a62  push    rsi
0x180072a63  push    rdi
0x180072a64  push    r12
0x180072a66  push    r13
0x180072a68  push    r14
0x180072a6a  push    r15
0x180072a6c  lea     rbp, [rsp-1B0h]
0x180072a74  sub     rsp, 2B0h
0x180072a7b  mov     rax, cs:__security_cookie
0x180072a82  xor     rax, rsp
0x180072a85  mov     [rbp+1E0h+var_40], rax
0x180072a8c  mov     rax, [rbp+1E0h+arg_20]
0x180072a93  lea     rcx, [rbp+1E0h+var_250]; void *
0x180072a97  xor     ebx, ebx
0x180072a99  mov     [rbp+1E0h+var_260], rax
0x180072a9d  mov     rax, [rbp+1E0h+arg_28]
0x180072aa4  mov     r13, r8
0x180072aa7  mov     r14, rdx
0x180072aaa  mov     [rbp+1E0h+var_258], rax
0x180072aae  xor     edx, edx; Val
0x180072ab0  mov     dword ptr [rsp+2E0h+var_2B0], ebx
0x180072ab4  mov     r8d, 20Ah; Size
0x180072aba  mov     [rsp+2E0h+KeyHandle], rbx
0x180072abf  mov     esi, r9d
0x180072ac2  mov     dword ptr [rsp+2E0h+ObjectAttributes+4], ebx
0x180072ac6  mov     edi, ebx
0x180072ac8  mov     dword ptr [rsp+2E0h+ObjectAttributes+1Ch], ebx
0x180072acc  call    memset
0x180072ad1  lea     edx, [rbx+2]
0x180072ad4  xorps   xmm0, xmm0
0x180072ad7  mov     r12d, 7FFFh
0x180072add  mov     r15d, 0FFFEh
0x180072ae3  movups  [rsp+2E0h+var_2A0], xmm0
0x180072ae8  test    r14, r14
0x180072aeb  jz      short loc_180072B1E
0x180072aed  mov     ecx, r12d
0x180072af0  mov     rax, r14
0x180072af3  cmp     [rax], bx
0x180072af6  jz      short loc_180072B03
0x180072af8  add     rax, rdx
0x180072afb  sub     rcx, 1
0x180072aff  jnz     short loc_180072AF3
0x180072b01  jmp     short loc_180072B1E
0x180072b03  add     cx, cx
0x180072b06  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x180072b0b  mov     eax, r15d
0x180072b0e  sub     ax, cx
0x180072b11  mov     word ptr [rsp+2E0h+var_2A0], ax
0x180072b16  add     ax, dx
0x180072b19  mov     word ptr [rsp+2E0h+var_2A0+2], ax
0x180072b1e  lea     rax, [rsp+2E0h+var_2A0]
0x180072b23  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180072b2b  xorps   xmm0, xmm0
0x180072b2e  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180072b33  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180072b38  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rbx
0x180072b3d  mov     edx, 20019h; DesiredAccess
0x180072b42  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x180072b4a  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072b4f  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072b55  call    cs:__imp_ZwOpenKey
0x180072b5c  nop     dword ptr [rax+rax+00h]
0x180072b61  xor     ecx, ecx
0x180072b63  mov     ebx, eax
0x180072b65  test    eax, eax
0x180072b67  js      loc_180072D32
0x180072b6d  test    esi, esi
0x180072b6f  jz      loc_180072D2D
0x180072b75  sub     esi, 1
0x180072b78  jz      short loc_180072B90
0x180072b7a  cmp     esi, 1
0x180072b7d  jz      short loc_180072B89
0x180072b7f  mov     ebx, 0C0000002h
0x180072b84  jmp     loc_180072D32
0x180072b89  mov     esi, 1
0x180072b8e  jmp     short loc_180072B95
0x180072b90  mov     esi, 3
0x180072b95  lea     rax, [rsp+2E0h+var_2B0]
0x180072b9a  xor     r9d, r9d
0x180072b9d  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180072ba2  mov     r8d, esi
0x180072ba5  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x180072baa  mov     rdx, r13
0x180072bad  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072bb2  call    CipGetRegistryValueInternal
0x180072bb7  mov     ebx, eax
0x180072bb9  cmp     eax, 0C0000034h
0x180072bbe  jnz     loc_180072CBA
0x180072bc4  test    r14, r14
0x180072bc7  jz      loc_180072D32
0x180072bcd  mov     rax, qword ptr [rsp+2E0h+var_2A0+8]
0x180072bd2  mov     r8, r14
0x180072bd5  sub     r8, rax
0x180072bd8  movzx   edx, word ptr [rax]
0x180072bdb  movzx   ecx, word ptr [rax+r8]
0x180072be0  sub     edx, ecx
0x180072be2  jnz     short loc_180072BEC
0x180072be4  add     rax, 2
0x180072be8  test    ecx, ecx
0x180072bea  jnz     short loc_180072BD8
0x180072bec  test    edx, edx
0x180072bee  jz      loc_180072D32
0x180072bf4  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180072bf9  call    cs:__imp_ZwClose
0x180072c00  nop     dword ptr [rax+rax+00h]
0x180072c05  xor     ecx, ecx
0x180072c07  xorps   xmm0, xmm0
0x180072c0a  mov     [rsp+2E0h+KeyHandle], rcx
0x180072c0f  mov     rax, r14
0x180072c12  movups  [rsp+2E0h+var_2A0], xmm0
0x180072c17  lea     edx, [rcx+2]
0x180072c1a  cmp     [rax], cx
0x180072c1d  jz      short loc_180072C2A
0x180072c1f  add     rax, rdx
0x180072c22  sub     r12, 1
0x180072c26  jnz     short loc_180072C1A
0x180072c28  jmp     short loc_180072C47
0x180072c2a  add     r12w, r12w
0x180072c2e  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x180072c33  sub     r15w, r12w
0x180072c37  mov     word ptr [rsp+2E0h+var_2A0], r15w
0x180072c3d  add     r15w, dx
0x180072c41  mov     word ptr [rsp+2E0h+var_2A0+2], r15w
0x180072c47  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rcx
0x180072c4c  lea     rax, [rsp+2E0h+var_2A0]
0x180072c51  xorps   xmm0, xmm0
0x180072c54  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180072c59  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072c5e  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180072c66  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180072c6b  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x180072c73  mov     edx, 20019h; DesiredAccess
0x180072c78  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072c7e  call    cs:__imp_ZwOpenKey
0x180072c85  nop     dword ptr [rax+rax+00h]
0x180072c8a  xor     ecx, ecx
0x180072c8c  mov     ebx, eax
0x180072c8e  test    eax, eax
0x180072c90  js      loc_180072D32
0x180072c96  lea     rax, [rsp+2E0h+var_2B0]
0x180072c9b  xor     r9d, r9d
0x180072c9e  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180072ca3  mov     r8d, esi
0x180072ca6  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x180072cab  mov     rdx, r13
0x180072cae  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072cb3  call    CipGetRegistryValueInternal
0x180072cb8  mov     ebx, eax
0x180072cba  cmp     ebx, 80000005h
0x180072cc0  jnz     short loc_180072D12
0x180072cc2  mov     edx, dword ptr [rsp+2E0h+var_2B0]
0x180072cc6  mov     ecx, 102h
0x180072ccb  mov     r8d, 63734943h
0x180072cd1  call    cs:__imp_ExAllocatePool2
0x180072cd8  nop     dword ptr [rax+rax+00h]
0x180072cdd  mov     rdi, rax
0x180072ce0  test    rax, rax
0x180072ce3  jnz     short loc_180072CEC
0x180072ce5  mov     ebx, 0C0000017h
0x180072cea  jmp     short loc_180072D32
0x180072cec  mov     r9d, dword ptr [rsp+2E0h+var_2B0]
0x180072cf1  lea     rax, [rsp+2E0h+var_2B0]
0x180072cf6  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072cfb  mov     r8d, esi
0x180072cfe  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180072d03  mov     rdx, r13
0x180072d06  mov     [rsp+2E0h+var_2C0], rdi; __int64
0x180072d0b  call    CipGetRegistryValueInternal
0x180072d10  mov     ebx, eax
0x180072d12  xor     ecx, ecx
0x180072d14  test    ebx, ebx
0x180072d16  js      short loc_180072D32
0x180072d18  mov     rax, [rbp+1E0h+var_260]
0x180072d1c  mov     [rax], rdi
0x180072d1f  mov     edi, ecx
0x180072d21  mov     rcx, [rbp+1E0h+var_258]
0x180072d25  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x180072d29  mov     [rcx], eax
0x180072d2b  jmp     short loc_180072D32
0x180072d2d  mov     ebx, 0C00000F2h
0x180072d32  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180072d37  test    rcx, rcx
0x180072d3a  jz      short loc_180072D48
0x180072d3c  call    cs:__imp_ZwClose
0x180072d43  nop     dword ptr [rax+rax+00h]
0x180072d48  test    rdi, rdi
0x180072d4b  jz      short loc_180072D61
0x180072d4d  mov     edx, 63734943h; Tag
0x180072d52  mov     rcx, rdi; P
0x180072d55  call    cs:__imp_ExFreePoolWithTag
0x180072d5c  nop     dword ptr [rax+rax+00h]
0x180072d61  mov     eax, ebx
0x180072d63  mov     rcx, [rbp+1E0h+var_40]
0x180072d6a  xor     rcx, rsp; StackCookie
0x180072d6d  call    __security_check_cookie
0x180072d72  mov     rbx, [rsp+2E0h+arg_0]
0x180072d7a  add     rsp, 2B0h
0x180072d81  pop     r15
0x180072d83  pop     r14
0x180072d85  pop     r13
0x180072d87  pop     r12
0x180072d89  pop     rdi
0x180072d8a  pop     rsi
0x180072d8b  pop     rbp
0x180072d8c  retn
```
