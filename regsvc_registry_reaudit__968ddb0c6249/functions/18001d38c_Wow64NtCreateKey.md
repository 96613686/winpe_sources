# Wow64NtCreateKey

- ea: `0x18001d38c`
- end: `0x18001d690`
- name: `Wow64NtCreateKey`
- size: `772`
- prototype: `__int64 __fastcall(void **, ACCESS_MASK, __int128 *, int, PUNICODE_STRING Class, ULONG CreateOptions, int KeySetInformation, PULONG Disposition)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016d3c`
- `0x18001702c`
- `0x1800175ac`
- `0x18001c34c`

## callees

- `0x1800035a0`
- `0x18001d38c`

## import_xrefs

- `ntdll!NtClose` at `0x18001d555`
- `ntdll!NtClose` at `0x18001d5fb`
- `ntdll!NtClose` at `0x18001d662`
- `ntdll!NtClose` at `0x18001d555`
- `ntdll!NtClose` at `0x18001d5fb`
- `ntdll!NtClose` at `0x18001d662`
- `ntdll!RtlFreeHeap` at `0x18001d621`
- `ntdll!RtlFreeHeap` at `0x18001d621`
- `ntdll!NtOpenKeyEx` at `0x18001d495`
- `ntdll!NtOpenKeyEx` at `0x18001d495`
- `ntdll!NtSetInformationKey` at `0x18001d652`
- `ntdll!NtSetInformationKey` at `0x18001d652`
- `ntdll!NtCreateKey` at `0x18001d448`
- `ntdll!NtCreateKey` at `0x18001d544`
- `ntdll!NtCreateKey` at `0x18001d5ea`
- `ntdll!NtCreateKey` at `0x18001d448`
- `ntdll!NtCreateKey` at `0x18001d544`
- `ntdll!NtCreateKey` at `0x18001d5ea`

## pseudocode

```c
__int64 __fastcall Wow64NtCreateKey(
        void **a1,
        ACCESS_MASK a2,
        __int128 *a3,
        int a4,
        PUNICODE_STRING Class,
        ULONG CreateOptions,
        int KeySetInformation,
        PULONG Disposition)
{
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  void **v11; // rsi
  __int128 v12; // xmm0
  __int64 result; // rax
  ULONG v14; // r12d
  NTSTATUS v15; // ebx
  __int16 v16; // r15
  PUNICODE_STRING ObjectName; // rax
  unsigned int v18; // esi
  USHORT Length; // di
  WCHAR *v20; // rsi
  struct _UNICODE_STRING *v21; // rdi
  __int16 v22; // r14
  ULONG *v23; // r15
  __int16 v24; // r14
  WCHAR *v25; // rax
  __int16 v26; // ax
  NTSTATUS v27; // edi
  void *KeyHandle; // [rsp+48h] [rbp-49h] BYREF
  PVOID P; // [rsp+50h] [rbp-41h] BYREF
  __int64 v30; // [rsp+58h] [rbp-39h] BYREF
  __int16 v31; // [rsp+60h] [rbp-31h]
  char v32; // [rsp+62h] [rbp-2Fh]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-29h] BYREF
  USHORT v35; // [rsp+E8h] [rbp+57h]
  int v36; // [rsp+F0h] [rbp+5Fh] BYREF

  v36 = a4;
  v8 = *a3;
  v9 = a3[1];
  v30 = 0;
  v31 = 0;
  v32 = 0;
  *(_OWORD *)&ObjectAttributes.Length = v8;
  v11 = a1;
  v12 = a3[2];
  P = 0;
  KeySetInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v12;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = v9;
  LOBYTE(v36) = 0;
  result = ConstructKernelKeyPath(
             a2,
             (__int64)&ObjectAttributes,
             &KeySetInformation,
             (__int64)&v30,
             (bool *)&v36,
             (struct _UNICODE_STRING **)&P);
  if ( (int)result < 0 )
    return result;
  v14 = CreateOptions;
  v15 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, Class, CreateOptions, Disposition);
  if ( v15 == -1073741772 )
  {
    if ( (_BYTE)v30 )
    {
      v16 = WORD2(v30);
      if ( WORD2(v30) )
      {
        ObjectName = ObjectAttributes.ObjectName;
        v18 = WORD1(v30);
        Length = ObjectAttributes.ObjectName->Length;
        if ( WORD1(v30) )
        {
          ObjectAttributes.ObjectName->Length = WORD1(v30);
          v15 = NtOpenKeyEx(&KeyHandle, a2, &ObjectAttributes, v14);
          if ( v15 < 0 )
          {
LABEL_25:
            v11 = a1;
            goto LABEL_26;
          }
          Length -= v18;
          ObjectAttributes.ObjectName->Buffer += (unsigned __int64)v18 >> 1;
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectName = ObjectAttributes.ObjectName;
        }
        else
        {
          v15 = 0;
        }
        v20 = ObjectName->Buffer + 1;
        v35 = Length;
        v21 = Class;
        v22 = v16;
        v23 = Disposition;
        v24 = v22 - 2;
        ObjectName->Buffer = v20;
        ObjectAttributes.ObjectName->MaximumLength -= 2;
        while ( v24 )
        {
          do
          {
            if ( *v20 == 92 )
              break;
            ++v20;
            v24 -= 2;
          }
          while ( v24 );
          ObjectAttributes.ObjectName->Length = 2
                                              * ((__int64)(unsigned int)((_DWORD)v20
                                                                       - LODWORD(ObjectAttributes.ObjectName->Buffer)) >> 1);
          v15 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, v21, v14, v23);
          if ( ObjectAttributes.RootDirectory )
          {
            NtClose(ObjectAttributes.RootDirectory);
            ObjectAttributes.RootDirectory = 0;
          }
          if ( v15 < 0 )
            break;
          v25 = v20 + 1;
          if ( !v24 )
            v25 = v20;
          v20 = v25;
          ObjectAttributes.ObjectName->Buffer = v25;
          ObjectAttributes.RootDirectory = KeyHandle;
          v26 = v24 - 2;
          if ( !v24 )
            v26 = 0;
          v24 = v26;
        }
        if ( v15 >= 0 && v35 != WORD2(v30) )
        {
          ObjectAttributes.ObjectName->Length = v35 - WORD2(v30);
          v15 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, Class, v14, Disposition);
          if ( ObjectAttributes.RootDirectory )
          {
            NtClose(ObjectAttributes.RootDirectory);
            ObjectAttributes.RootDirectory = 0;
          }
        }
        goto LABEL_25;
      }
    }
  }
LABEL_26:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v15 >= 0 )
  {
    if ( (_BYTE)v36 )
    {
      if ( KeySetInformation )
      {
        KeySetInformation &= 0xF01u;
        v27 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
        if ( v27 < 0 )
        {
          NtClose(KeyHandle);
          return (unsigned int)v27;
        }
      }
    }
    *v11 = KeyHandle;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001d38c  mov     rax, rsp
0x18001d38f  mov     [rax+10h], rbx
0x18001d393  mov     [rax+20h], r9d
0x18001d397  mov     [rax+8], rcx
0x18001d39b  push    rbp
0x18001d39c  push    rsi
0x18001d39d  push    rdi
0x18001d39e  push    r12
0x18001d3a0  push    r13
0x18001d3a2  push    r14
0x18001d3a4  push    r15
0x18001d3a6  lea     rbp, [rax-3Fh]
0x18001d3aa  sub     rsp, 90h
0x18001d3b1  movups  xmm0, xmmword ptr [r8]
0x18001d3b5  xor     eax, eax
0x18001d3b7  xor     r14d, r14d
0x18001d3ba  movups  xmm1, xmmword ptr [r8+10h]
0x18001d3bf  mov     [rbp+37h+var_70], rax
0x18001d3c3  lea     r9, [rbp+37h+var_70]
0x18001d3c7  mov     [rbp+37h+var_68], ax
0x18001d3cb  mov     r13d, edx
0x18001d3ce  mov     [rbp+37h+var_66], al
0x18001d3d1  lea     rdx, [rbp+37h+ObjectAttributes]
0x18001d3d5  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x18001d3d9  lea     rax, [rbp+37h+P]
0x18001d3dd  mov     rsi, rcx
0x18001d3e0  movups  xmm0, xmmword ptr [r8+20h]
0x18001d3e5  mov     qword ptr [rsp+0C0h+CreateOptions], rax
0x18001d3ea  lea     r8, [rbp+37h+KeySetInformation]
0x18001d3ee  lea     rax, [rbp+37h+arg_18]
0x18001d3f2  mov     [rbp+37h+P], r14
0x18001d3f6  mov     ecx, r13d
0x18001d3f9  mov     [rbp+37h+KeySetInformation], r14d
0x18001d3fd  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001d401  mov     [rbp+37h+KeyHandle], r14
0x18001d405  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x18001d409  mov     byte ptr [rbp+37h+arg_18], r14b
0x18001d40d  mov     [rsp+0C0h+Class], rax
0x18001d412  call    ConstructKernelKeyPath
0x18001d417  test    eax, eax
0x18001d419  js      loc_18001D675
0x18001d41f  mov     rax, [rbp+37h+Disposition]
0x18001d423  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18001d427  mov     r12d, [rbp+37h+arg_28]
0x18001d42b  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18001d42f  mov     [rsp+30h], rax; Disposition
0x18001d434  xor     r9d, r9d; TitleIndex
0x18001d437  mov     rax, [rbp+37h+arg_20]
0x18001d43b  mov     edx, r13d; DesiredAccess
0x18001d43e  mov     [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x18001d443  mov     [rsp+0C0h+Class], rax; Class
0x18001d448  call    cs:__imp_NtCreateKey
0x18001d44e  mov     ebx, eax
0x18001d450  cmp     eax, 0C0000034h
0x18001d455  jnz     loc_18001D609
0x18001d45b  cmp     byte ptr [rbp+37h+var_70], r14b
0x18001d45f  jz      loc_18001D609
0x18001d465  movzx   r15d, word ptr [rbp+37h+var_70+4]
0x18001d46a  test    r15w, r15w
0x18001d46e  jz      loc_18001D609
0x18001d474  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d478  movzx   esi, word ptr [rbp+37h+var_70+2]
0x18001d47c  movzx   edi, word ptr [rax]
0x18001d47f  test    si, si
0x18001d482  jz      short loc_18001D4C6
0x18001d484  mov     r9d, r12d
0x18001d487  mov     [rax], si
0x18001d48a  lea     r8, [rbp+37h+ObjectAttributes]
0x18001d48e  mov     edx, r13d
0x18001d491  lea     rcx, [rbp+37h+KeyHandle]
0x18001d495  call    cs:__imp_NtOpenKeyEx
0x18001d49b  mov     ebx, eax
0x18001d49d  test    eax, eax
0x18001d49f  js      loc_18001D605
0x18001d4a5  mov     rcx, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d4a9  mov     eax, esi
0x18001d4ab  shr     rax, 1
0x18001d4ae  sub     di, si
0x18001d4b1  add     rax, rax
0x18001d4b4  add     [rcx+8], rax
0x18001d4b8  mov     rax, [rbp+37h+KeyHandle]
0x18001d4bc  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x18001d4c0  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d4c4  jmp     short loc_18001D4C9
0x18001d4c6  mov     ebx, r14d
0x18001d4c9  mov     rsi, [rax+8]
0x18001d4cd  mov     edx, 2
0x18001d4d2  add     rsi, rdx
0x18001d4d5  mov     [rbp+37h+arg_10], di
0x18001d4d9  mov     rdi, [rbp+37h+arg_20]
0x18001d4dd  movzx   r14d, r15w
0x18001d4e1  mov     r15, [rbp+37h+Disposition]
0x18001d4e5  sub     r14w, dx
0x18001d4e9  mov     [rax+8], rsi
0x18001d4ed  mov     r8d, 0FFFEh
0x18001d4f3  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d4f7  add     [rax+2], r8w
0x18001d4fc  test    r14w, r14w
0x18001d500  jz      loc_18001D5A8
0x18001d506  cmp     word ptr [rsi], 5Ch ; '\'
0x18001d50a  jz      short loc_18001D515
0x18001d50c  add     rsi, rdx
0x18001d50f  add     r14w, r8w
0x18001d513  jnz     short loc_18001D506
0x18001d515  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d519  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18001d51d  mov     ecx, esi
0x18001d51f  mov     [rsp+30h], r15; Disposition
0x18001d524  mov     [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x18001d529  xor     r9d, r9d; TitleIndex
0x18001d52c  mov     edx, r13d; DesiredAccess
0x18001d52f  mov     [rsp+0C0h+Class], rdi; Class
0x18001d534  sub     ecx, [rax+8]
0x18001d537  sar     rcx, 1
0x18001d53a  add     cx, cx
0x18001d53d  mov     [rax], cx
0x18001d540  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18001d544  call    cs:__imp_NtCreateKey
0x18001d54a  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x18001d54e  mov     ebx, eax
0x18001d550  test    rcx, rcx
0x18001d553  jz      short loc_18001D561
0x18001d555  call    cs:__imp_NtClose
0x18001d55b  xor     ecx, ecx
0x18001d55d  mov     [rbp+37h+ObjectAttributes.RootDirectory], rcx
0x18001d561  test    ebx, ebx
0x18001d563  js      short loc_18001D5A8
0x18001d565  test    r14w, r14w
0x18001d569  lea     rax, [rsi+2]
0x18001d56d  mov     edx, 2
0x18001d572  mov     r8d, 0FFFEh
0x18001d578  cmovz   rax, rsi
0x18001d57c  mov     rsi, rax
0x18001d57f  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d583  mov     [rax+8], rsi
0x18001d587  mov     rax, [rbp+37h+KeyHandle]
0x18001d58b  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x18001d58f  movzx   eax, r14w
0x18001d593  sub     ax, dx
0x18001d596  test    r14w, r14w
0x18001d59a  cmovz   ax, r14w
0x18001d59f  movzx   r14d, ax
0x18001d5a3  jmp     loc_18001D4FC
0x18001d5a8  movzx   edi, [rbp+37h+arg_10]
0x18001d5ac  xor     r14d, r14d
0x18001d5af  movzx   r15d, word ptr [rbp+37h+var_70+4]
0x18001d5b4  test    ebx, ebx
0x18001d5b6  js      short loc_18001D605
0x18001d5b8  sub     di, r15w
0x18001d5bc  jz      short loc_18001D605
0x18001d5be  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18001d5c2  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18001d5c6  xor     r9d, r9d; TitleIndex
0x18001d5c9  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18001d5cd  mov     edx, r13d; DesiredAccess
0x18001d5d0  mov     [rax], di
0x18001d5d3  mov     rax, [rbp+37h+Disposition]
0x18001d5d7  mov     [rsp+30h], rax; Disposition
0x18001d5dc  mov     rax, [rbp+37h+arg_20]
0x18001d5e0  mov     [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x18001d5e5  mov     [rsp+0C0h+Class], rax; Class
0x18001d5ea  call    cs:__imp_NtCreateKey
0x18001d5f0  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x18001d5f4  mov     ebx, eax
0x18001d5f6  test    rcx, rcx
0x18001d5f9  jz      short loc_18001D605
0x18001d5fb  call    cs:__imp_NtClose
0x18001d601  mov     [rbp+37h+ObjectAttributes.RootDirectory], r14
0x18001d605  mov     rsi, [rbp+37h+arg_0]
0x18001d609  mov     r8, [rbp+37h+P]; P
0x18001d60d  test    r8, r8
0x18001d610  jz      short loc_18001D627
0x18001d612  mov     rcx, gs:60h
0x18001d61b  xor     edx, edx; Flags
0x18001d61d  mov     rcx, [rcx+30h]; HeapHandle
0x18001d621  call    cs:__imp_RtlFreeHeap
0x18001d627  test    ebx, ebx
0x18001d629  js      short loc_18001D673
0x18001d62b  cmp     byte ptr [rbp+37h+arg_18], r14b
0x18001d62f  jz      short loc_18001D66C
0x18001d631  mov     eax, [rbp+37h+KeySetInformation]
0x18001d634  test    eax, eax
0x18001d636  jz      short loc_18001D66C
0x18001d638  mov     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18001d63c  lea     r8, [rbp+37h+KeySetInformation]; KeySetInformation
0x18001d640  mov     r9d, 4; KeySetInformationLength
0x18001d646  and     eax, 0F01h
0x18001d64b  mov     [rbp+37h+KeySetInformation], eax
0x18001d64e  lea     edx, [r9+1]; KeySetInformationClass
0x18001d652  call    cs:__imp_NtSetInformationKey
0x18001d658  mov     edi, eax
0x18001d65a  test    eax, eax
0x18001d65c  jns     short loc_18001D66C
0x18001d65e  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18001d662  call    cs:__imp_NtClose
0x18001d668  mov     eax, edi
0x18001d66a  jmp     short loc_18001D675
0x18001d66c  mov     rax, [rbp+37h+KeyHandle]
0x18001d670  mov     [rsi], rax
0x18001d673  mov     eax, ebx
0x18001d675  mov     rbx, [rsp+0C0h+arg_8]
0x18001d67d  add     rsp, 90h
0x18001d684  pop     r15
0x18001d686  pop     r14
0x18001d688  pop     r13
0x18001d68a  pop     r12
0x18001d68c  pop     rdi
0x18001d68d  pop     rsi
0x18001d68e  pop     rbp
0x18001d68f  retn
```
