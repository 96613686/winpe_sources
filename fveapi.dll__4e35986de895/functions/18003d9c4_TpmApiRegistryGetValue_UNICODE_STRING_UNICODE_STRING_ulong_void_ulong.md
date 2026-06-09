# TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)

- ea: `0x18003d9c4`
- end: `0x18003db74`
- name: `?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z`
- size: `432`
- prototype: `int(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039990`
- `0x1800db840`

## callees

- `0x18003d9c4`
- `0x180042044`
- `0x180060196`
- `0x180129010`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18003da25`
- `ntdll!ZwOpenKey` at `0x18003da25`
- `ntdll!ZwQueryValueKey` at `0x18003daaf`
- `ntdll!ZwQueryValueKey` at `0x18003db17`
- `ntdll!ZwQueryValueKey` at `0x18003daaf`
- `ntdll!ZwQueryValueKey` at `0x18003db17`
- `ntdll!NtClose` at `0x18003da74`
- `ntdll!NtClose` at `0x18003da74`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  _BYTE *v9; // r8
  __int64 (__fastcall *v10)(_QWORD, _QWORD); // rax
  PVOID v11; // rdx
  __int64 v12; // rcx
  _DWORD *v14; // rdi
  unsigned int v15; // eax
  PVOID KeyValueInformation; // [rsp+30h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      TpmApiCallbackAlloc(0, ResultLength, &KeyValueInformation);
      if ( KeyValueInformation )
      {
        v14 = KeyValueInformation;
        v8 = ZwQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v14[1] == a3 )
          {
            if ( a4 && (v15 = v14[2], *a5 >= v15) )
            {
              *a5 = v15;
              memcpy_0(a4, v14 + 3, v15);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v14[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      else
      {
        v8 = -1073741801;
      }
    }
  }
  v10 = qword_1801746C8;
  if ( qword_1801746C8 )
  {
    v11 = KeyValueInformation;
    if ( KeyValueInformation )
    {
      v12 = ResultLength;
      v9 = KeyValueInformation;
      if ( ResultLength )
      {
        do
        {
          *v9++ = 0;
          --v12;
        }
        while ( v12 );
      }
    }
    ((void (__fastcall *)(_QWORD, PVOID, _BYTE *))v10)(0, v11, v9);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003d9c4  push    rbp
0x18003d9c6  push    rbx
0x18003d9c7  push    rsi
0x18003d9c8  push    rdi
0x18003d9c9  push    r14
0x18003d9cb  push    r15
0x18003d9cd  mov     rbp, rsp
0x18003d9d0  sub     rsp, 78h
0x18003d9d4  mov     r14d, r8d
0x18003d9d7  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18003d9db  mov     r15, rdx
0x18003d9de  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003d9e6  xorps   xmm0, xmm0
0x18003d9e9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003d9f1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003d9f5  mov     [rbp+arg_0], 0
0x18003d9fc  mov     edx, 20019h; DesiredAccess
0x18003da01  mov     [rbp+KeyHandle], 0
0x18003da09  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18003da0d  mov     [rbp+KeyValueInformation], 0
0x18003da15  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003da1a  mov     rsi, r9
0x18003da1d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003da25  call    cs:__imp_ZwOpenKey
0x18003da2c  nop     dword ptr [rax+rax+00h]
0x18003da31  mov     ebx, eax
0x18003da33  test    eax, eax
0x18003da35  jns     short loc_18003DA90
0x18003da37  mov     rax, cs:qword_1801746C8
0x18003da3e  test    rax, rax
0x18003da41  jz      short loc_18003DA6B
0x18003da43  mov     rdx, [rbp+KeyValueInformation]
0x18003da47  test    rdx, rdx
0x18003da4a  jz      short loc_18003DA64
0x18003da4c  mov     ecx, [rbp+arg_0]
0x18003da4f  mov     r8, rdx
0x18003da52  test    rcx, rcx
0x18003da55  jz      short loc_18003DA64
0x18003da57  mov     byte ptr [r8], 0
0x18003da5b  inc     r8
0x18003da5e  sub     rcx, 1
0x18003da62  jnz     short loc_18003DA57
0x18003da64  xor     ecx, ecx
0x18003da66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da6b  mov     rcx, [rbp+KeyHandle]; Handle
0x18003da6f  test    rcx, rcx
0x18003da72  jz      short loc_18003DA80
0x18003da74  call    cs:__imp_NtClose
0x18003da7b  nop     dword ptr [rax+rax+00h]
0x18003da80  mov     eax, ebx
0x18003da82  add     rsp, 78h
0x18003da86  pop     r15
0x18003da88  pop     r14
0x18003da8a  pop     rdi
0x18003da8b  pop     rsi
0x18003da8c  pop     rbx
0x18003da8d  pop     rbp
0x18003da8e  retn
0x18003da90  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18003da94  lea     rax, [rbp+arg_0]
0x18003da98  xor     r9d, r9d; KeyValueInformation
0x18003da9b  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18003daa0  mov     rdx, r15; ValueName
0x18003daa3  mov     [rsp+78h+Length], 0; Length
0x18003daab  lea     r8d, [r9+2]; KeyValueInformationClass
0x18003daaf  call    cs:__imp_ZwQueryValueKey
0x18003dab6  nop     dword ptr [rax+rax+00h]
0x18003dabb  mov     ecx, 80000000h
0x18003dac0  mov     ebx, eax
0x18003dac2  add     eax, ecx
0x18003dac4  test    ecx, eax
0x18003dac6  jnz     short loc_18003DAD4
0x18003dac8  cmp     ebx, 0C0000023h
0x18003dace  jnz     loc_18003DA37
0x18003dad4  mov     edx, [rbp+arg_0]
0x18003dad7  lea     r8, [rbp+KeyValueInformation]
0x18003dadb  xor     ecx, ecx
0x18003dadd  call    TpmApiCallbackAlloc
0x18003dae2  cmp     [rbp+KeyValueInformation], 0
0x18003dae7  jnz     short loc_18003DAF3
0x18003dae9  mov     ebx, 0C0000017h
0x18003daee  jmp     loc_18003DA37
0x18003daf3  mov     rdi, [rbp+KeyValueInformation]
0x18003daf7  lea     rax, [rbp+arg_0]
0x18003dafb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18003daff  mov     r9, rdi; KeyValueInformation
0x18003db02  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18003db07  mov     r8d, 2; KeyValueInformationClass
0x18003db0d  mov     eax, [rbp+arg_0]
0x18003db10  mov     rdx, r15; ValueName
0x18003db13  mov     [rsp+78h+Length], eax; Length
0x18003db17  call    cs:__imp_ZwQueryValueKey
0x18003db1e  nop     dword ptr [rax+rax+00h]
0x18003db23  mov     ebx, eax
0x18003db25  test    eax, eax
0x18003db27  js      loc_18003DA37
0x18003db2d  cmp     [rdi+4], r14d
0x18003db31  jz      short loc_18003DB3D
0x18003db33  mov     ebx, 0C0000182h
0x18003db38  jmp     loc_18003DA37
0x18003db3d  mov     rcx, [rbp+arg_20]
0x18003db41  test    rsi, rsi
0x18003db44  jz      short loc_18003DB65
0x18003db46  mov     eax, [rdi+8]
0x18003db49  cmp     [rcx], eax
0x18003db4b  jb      short loc_18003DB65
0x18003db4d  mov     [rcx], eax
0x18003db4f  lea     rdx, [rdi+0Ch]; Src
0x18003db53  mov     rcx, rsi; void *
0x18003db56  mov     r8d, eax; Size
0x18003db59  call    memcpy_0
0x18003db5e  xor     ebx, ebx
0x18003db60  jmp     loc_18003DA37
0x18003db65  mov     eax, [rdi+8]
0x18003db68  mov     ebx, 0C0000023h
0x18003db6d  mov     [rcx], eax
0x18003db6f  jmp     loc_18003DA37
```
