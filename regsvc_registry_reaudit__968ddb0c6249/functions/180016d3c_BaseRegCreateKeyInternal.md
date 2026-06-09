# BaseRegCreateKeyInternal

- ea: `0x180016d3c`
- end: `0x180017025`
- name: `BaseRegCreateKeyInternal`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019290`

## callees

- `0x180007740`
- `0x180016d3c`
- `0x18001702c`
- `0x180017688`
- `0x1800176d8`
- `0x18001d38c`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180016ed1`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180016ed1`
- `ntdll!RtlNtStatusToDosError` at `0x180016efd`
- `ntdll!RtlNtStatusToDosError` at `0x180016efd`
- `ntdll!NtClose` at `0x180016ef5`
- `ntdll!NtClose` at `0x180016fb2`
- `ntdll!NtClose` at `0x180016ef5`
- `ntdll!NtClose` at `0x180016fb2`
- `ntdll!NtQueryKey` at `0x180016fa6`
- `ntdll!NtQueryKey` at `0x180016fa6`

## pseudocode

```c
ULONG __fastcall BaseRegCreateKeyInternal(
        void *a1,
        unsigned __int16 *a2,
        struct _UNICODE_STRING *a3,
        ULONG a4,
        ACCESS_MASK a5,
        __int64 a6,
        char a7,
        void **a8,
        _DWORD *a9)
{
  ULONG v9; // ebx
  HANDLE v12; // r9
  HANDLE v13; // rdi
  __int64 v14; // rcx
  BOOL v15; // edx
  int v16; // r8d
  NTSTATUS MultipartKey; // ebx
  int v18; // ecx
  int v19; // r14d
  int v20; // eax
  void *v21; // rcx
  int v23; // eax
  int v24; // [rsp+30h] [rbp-B1h]
  void *v25; // [rsp+48h] [rbp-99h]
  ULONG v27; // [rsp+54h] [rbp-8Dh] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-89h] BYREF
  void *v29; // [rsp+60h] [rbp-81h]
  ULONG ResultLength; // [rsp+68h] [rbp-79h] BYREF
  _DWORD *v31; // [rsp+70h] [rbp-71h]
  __int128 v32; // [rsp+78h] [rbp-69h] BYREF
  unsigned __int16 *v33; // [rsp+88h] [rbp-59h]
  int v34; // [rsp+90h] [rbp-51h]
  int v35; // [rsp+94h] [rbp-4Dh]
  __int64 v36; // [rsp+98h] [rbp-49h]
  __int64 v37; // [rsp+A0h] [rbp-41h]
  __int128 KeyInformation; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-29h]
  __int64 v40; // [rsp+C8h] [rbp-19h]

  v9 = a4;
  v31 = a9;
  v29 = a1;
  DWORD1(v32) = 0;
  v12 = a1;
  v35 = 0;
  v13 = 0;
  v27 = 0;
  v40 = 0;
  ResultLength = 0;
  KeyInformation = 0;
  v39 = 0;
  if ( !a2
    || *a2 < 2u
    || (v14 = *((_QWORD *)a2 + 1)) == 0
    || (*(_BYTE *)a2 & 1) != 0
    || *(_WORD *)(v14 + 2 * ((unsigned __int64)*a2 >> 1) - 2)
    || !a8
    || !a3
    || (a3->Length & 1) != 0
    || a3->Length && !a3->Buffer )
  {
    MultipartKey = -1073741811;
    goto LABEL_32;
  }
  v15 = 0;
  if ( (a7 & 1) != 0 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    v15 = (a7 & 2) != 0;
  }
  *a8 = 0;
  *a2 -= 2;
  if ( **((_WORD **)a2 + 1) == 92 )
  {
    MultipartKey = -1073741767;
    return RtlNtStatusToDosError(MultipartKey);
  }
  if ( a3->Length )
    a3->Length -= 2;
  v18 = 64;
  if ( a6 && *(_BYTE *)(a6 + 24) )
    v18 = 66;
  Handle = v12;
  v19 = v18 | 0x100;
  v13 = v12;
  if ( (v9 & 8) == 0 )
    v19 = v18;
  if ( v16 )
  {
    v20 = OpenMachineKey(&Handle);
  }
  else
  {
    if ( !v15 )
      goto LABEL_27;
    v20 = OpenUserKey(&Handle);
  }
  v13 = Handle;
  MultipartKey = v20;
  if ( v20 >= 0 )
  {
    v9 = a4;
LABEL_27:
    if ( a6 )
    {
      v21 = *(void **)(a6 + 8);
      if ( v21 )
      {
        if ( !RtlValidRelativeSecurityDescriptor(v21, *(_DWORD *)(a6 + 16), 0) )
        {
          MultipartKey = -1073741811;
          goto LABEL_31;
        }
      }
    }
    LODWORD(v32) = 48;
    *((_QWORD *)&v32 + 1) = v13;
    v34 = v19;
    v33 = a2;
    if ( a6 )
      v36 = *(_QWORD *)(a6 + 8);
    else
      v36 = 0;
    v37 = 0;
    v23 = Wow64NtCreateKey(a8, a5, &v32, (int)v12, a3, v9, v24, &v27);
    MultipartKey = v23;
    if ( v23 == 1073741846 )
    {
      MultipartKey = NtQueryKey(*a8, KeyCachedInformation, &KeyInformation, 0x28u, &ResultLength);
      NtClose(*a8);
      if ( MultipartKey >= 0 )
      {
        *a8 = (void *)SDWORD1(v39);
        goto LABEL_45;
      }
    }
    else if ( v23 >= 0 )
    {
LABEL_45:
      if ( v31 )
        *v31 = v27;
      goto LABEL_31;
    }
    MultipartKey = BaseRegCreateMultipartKey(
                     (__int64)v13,
                     (__int64)a2,
                     (__int64)a3,
                     a4,
                     a5,
                     a6,
                     (__int64 *)a8,
                     v31,
                     v19,
                     v25);
  }
LABEL_31:
  v12 = v29;
LABEL_32:
  if ( v13 && v13 != v12 )
    NtClose(v13);
  return RtlNtStatusToDosError(MultipartKey);
}

```

## disassembly

```asm
0x180016d3c  push    rbp
0x180016d3e  push    rbx
0x180016d3f  push    rsi
0x180016d40  push    rdi
0x180016d41  push    r12
0x180016d43  push    r13
0x180016d45  push    r14
0x180016d47  push    r15
0x180016d49  lea     rbp, [rsp-7]
0x180016d4e  sub     rsp, 0E8h
0x180016d55  mov     rax, cs:__security_cookie
0x180016d5c  xor     rax, rsp
0x180016d5f  mov     [rbp+3Fh+var_50], rax
0x180016d63  mov     rax, [rbp+3Fh+arg_40]
0x180016d6a  xor     r10d, r10d
0x180016d6d  mov     rsi, [rbp+3Fh+arg_28]
0x180016d71  mov     ebx, r9d
0x180016d74  mov     r13, [rbp+3Fh+arg_38]
0x180016d7b  xorps   xmm0, xmm0
0x180016d7e  mov     [rbp+3Fh+var_B0], rax
0x180016d82  mov     r12, r8
0x180016d85  xor     eax, eax
0x180016d87  mov     [rsp+120h+var_D0], ebx
0x180016d8b  mov     [rsp+120h+var_C0], rcx
0x180016d90  mov     r15, rdx
0x180016d93  mov     [rbp+3Fh+var_A4], r10d
0x180016d97  mov     r9, rcx
0x180016d9a  mov     [rbp+3Fh+var_8C], r10d
0x180016d9e  mov     edi, r10d
0x180016da1  mov     [rsp+120h+var_CC], r10d
0x180016da6  mov     [rbp+3Fh+var_58], rax
0x180016daa  mov     [rbp+3Fh+var_B8], r10d
0x180016dae  movups  [rbp+3Fh+KeyInformation], xmm0
0x180016db2  movups  [rbp+3Fh+var_68], xmm0
0x180016db6  test    rdx, rdx
0x180016db9  jz      loc_18001701B
0x180016dbf  cmp     word ptr [rdx], 2
0x180016dc3  jb      loc_18001701B
0x180016dc9  mov     rcx, [rdx+8]
0x180016dcd  test    rcx, rcx
0x180016dd0  jz      loc_18001701B
0x180016dd6  lea     r11d, [rax+1]
0x180016dda  test    [rdx], r11b
0x180016ddd  jnz     loc_18001701B
0x180016de3  movzx   eax, word ptr [rdx]
0x180016de6  shr     rax, 1
0x180016de9  cmp     [rcx+rax*2-2], r10w
0x180016def  jnz     loc_18001701B
0x180016df5  test    r13, r13
0x180016df8  jz      loc_18001701B
0x180016dfe  test    r8, r8
0x180016e01  jz      loc_18001701B
0x180016e07  test    [r8], r11b
0x180016e0a  jnz     loc_18001701B
0x180016e10  cmp     [r8], r10w
0x180016e14  jz      short loc_180016E20
0x180016e16  cmp     [r8+8], r10
0x180016e1a  jz      loc_18001701B
0x180016e20  mov     edx, r10d
0x180016e23  test    [rbp+3Fh+arg_30], r11b
0x180016e27  jz      short loc_180016E2E
0x180016e29  mov     r8d, r11d
0x180016e2c  jmp     short loc_180016E39
0x180016e2e  test    [rbp+3Fh+arg_30], 2
0x180016e32  mov     r8d, r10d
0x180016e35  cmovnz  edx, r11d
0x180016e39  mov     [r13+0], r10
0x180016e3d  mov     eax, 0FFFEh
0x180016e42  add     [r15], ax
0x180016e46  mov     rax, [r15+8]
0x180016e4a  cmp     word ptr [rax], 5Ch ; '\'
0x180016e4e  jnz     short loc_180016E5A
0x180016e50  mov     ebx, 0C0000039h
0x180016e55  jmp     loc_180016EFB
0x180016e5a  movzx   eax, word ptr [r12]
0x180016e5f  test    ax, ax
0x180016e62  jz      short loc_180016E6D
0x180016e64  sub     ax, 2
0x180016e68  mov     [r12], ax
0x180016e6d  mov     ecx, 40h ; '@'
0x180016e72  test    rsi, rsi
0x180016e75  jz      short loc_180016E81
0x180016e77  cmp     [rsi+18h], r10b
0x180016e7b  lea     eax, [rcx+2]
0x180016e7e  cmovnz  ecx, eax
0x180016e81  mov     r14d, ecx
0x180016e84  mov     [rsp+120h+Handle], r9
0x180016e89  bts     r14d, 8
0x180016e8e  mov     rdi, r9
0x180016e91  test    bl, 8
0x180016e94  cmovz   r14d, ecx
0x180016e98  test    r8d, r8d
0x180016e9b  jz      loc_180016F23
0x180016ea1  lea     rcx, [rsp+120h+Handle]
0x180016ea6  call    OpenMachineKey
0x180016eab  mov     rdi, [rsp+120h+Handle]
0x180016eb0  xor     r10d, r10d
0x180016eb3  mov     ebx, eax
0x180016eb5  test    eax, eax
0x180016eb7  js      short loc_180016EE3
0x180016eb9  mov     ebx, [rsp+120h+var_D0]
0x180016ebd  test    rsi, rsi
0x180016ec0  jz      short loc_180016F36
0x180016ec2  mov     rcx, [rsi+8]; SecurityDescriptorInput
0x180016ec6  test    rcx, rcx
0x180016ec9  jz      short loc_180016F36
0x180016ecb  mov     edx, [rsi+10h]; SecurityDescriptorLength
0x180016ece  xor     r8d, r8d; RequiredInformation
0x180016ed1  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180016ed7  xor     r10d, r10d
0x180016eda  test    al, al
0x180016edc  jnz     short loc_180016F36
0x180016ede  mov     ebx, 0C000000Dh
0x180016ee3  mov     r9, [rsp+120h+var_C0]
0x180016ee8  test    rdi, rdi
0x180016eeb  jz      short loc_180016EFB
0x180016eed  cmp     rdi, r9
0x180016ef0  jz      short loc_180016EFB
0x180016ef2  mov     rcx, rdi; Handle
0x180016ef5  call    cs:__imp_NtClose
0x180016efb  mov     ecx, ebx; Status
0x180016efd  call    cs:__imp_RtlNtStatusToDosError
0x180016f03  mov     rcx, [rbp+3Fh+var_50]
0x180016f07  xor     rcx, rsp; StackCookie
0x180016f0a  call    __security_check_cookie
0x180016f0f  add     rsp, 0E8h
0x180016f16  pop     r15
0x180016f18  pop     r14
0x180016f1a  pop     r13
0x180016f1c  pop     r12
0x180016f1e  pop     rdi
0x180016f1f  pop     rsi
0x180016f20  pop     rbx
0x180016f21  pop     rbp
0x180016f22  retn
0x180016f23  test    edx, edx
0x180016f25  jz      short loc_180016EBD
0x180016f27  lea     rcx, [rsp+120h+Handle]
0x180016f2c  call    OpenUserKey
0x180016f31  jmp     loc_180016EAB
0x180016f36  mov     [rbp+3Fh+var_A8], 30h ; '0'
0x180016f3d  mov     [rbp+3Fh+var_A0], rdi
0x180016f41  mov     [rbp+3Fh+var_90], r14d
0x180016f45  mov     [rbp+3Fh+var_98], r15
0x180016f49  test    rsi, rsi
0x180016f4c  jz      short loc_180016F58
0x180016f4e  mov     rax, [rsi+8]
0x180016f52  mov     [rbp+3Fh+var_88], rax
0x180016f56  jmp     short loc_180016F5C
0x180016f58  mov     [rbp+3Fh+var_88], r10
0x180016f5c  mov     edx, [rbp+3Fh+arg_20]
0x180016f5f  lea     rax, [rsp+120h+var_CC]
0x180016f64  mov     [rsp+120h+var_E8], rax
0x180016f69  lea     r8, [rbp+3Fh+var_A8]
0x180016f6d  mov     dword ptr [rsp+120h+var_F8], ebx
0x180016f71  mov     rcx, r13
0x180016f74  mov     [rsp+120h+ResultLength], r12
0x180016f79  mov     [rbp+3Fh+var_80], r10
0x180016f7d  call    Wow64NtCreateKey
0x180016f82  mov     ebx, eax
0x180016f84  cmp     eax, 40000016h
0x180016f89  jnz     short loc_180016FC6
0x180016f8b  mov     rcx, [r13+0]; KeyHandle
0x180016f8f  lea     rax, [rbp+3Fh+var_B8]
0x180016f93  mov     r9d, 28h ; '('; Length
0x180016f99  mov     [rsp+120h+ResultLength], rax; ResultLength
0x180016f9e  lea     r8, [rbp+3Fh+KeyInformation]; KeyInformation
0x180016fa2  lea     edx, [r9-24h]; KeyInformationClass
0x180016fa6  call    cs:__imp_NtQueryKey
0x180016fac  mov     rcx, [r13+0]; Handle
0x180016fb0  mov     ebx, eax
0x180016fb2  call    cs:__imp_NtClose
0x180016fb8  test    ebx, ebx
0x180016fba  js      short loc_180016FE2
0x180016fbc  movsxd  rax, dword ptr [rbp+3Fh+var_68+4]
0x180016fc0  mov     [r13+0], rax
0x180016fc4  jmp     short loc_180016FCA
0x180016fc6  test    eax, eax
0x180016fc8  js      short loc_180016FE2
0x180016fca  mov     rcx, [rbp+3Fh+var_B0]
0x180016fce  test    rcx, rcx
0x180016fd1  jz      loc_180016EE3
0x180016fd7  mov     eax, [rsp+120h+var_CC]
0x180016fdb  mov     [rcx], eax
0x180016fdd  jmp     loc_180016EE3
0x180016fe2  mov     rcx, [rbp+3Fh+var_B0]
0x180016fe6  mov     r8, r12
0x180016fe9  mov     eax, [rbp+3Fh+arg_20]
0x180016fec  mov     rdx, r15
0x180016fef  mov     r9d, [rsp+120h+var_D0]
0x180016ff4  mov     [rsp+120h+var_E0], r14d
0x180016ff9  mov     [rsp+120h+var_E8], rcx
0x180016ffe  mov     rcx, rdi
0x180017001  mov     [rsp+120h+var_F0], r13
0x180017006  mov     [rsp+120h+var_F8], rsi
0x18001700b  mov     dword ptr [rsp+120h+ResultLength], eax
0x18001700f  call    BaseRegCreateMultipartKey
0x180017014  mov     ebx, eax
0x180017016  jmp     loc_180016EE3
0x18001701b  mov     ebx, 0C000000Dh
0x180017020  jmp     loc_180016EE8
```
