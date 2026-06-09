# TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)

- ea: `0x180039990`
- end: `0x180039c37`
- name: `?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z`
- size: `679`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039824`

## callees

- `0x180039990`
- `0x18003d9c4`
- `0x180042044`
- `0x180129010`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x180039a38`
- `ntdll!ZwOpenKey` at `0x180039a38`
- `ntdll!ZwQueryValueKey` at `0x180039b16`
- `ntdll!ZwQueryValueKey` at `0x180039b7b`
- `ntdll!ZwQueryValueKey` at `0x180039b16`
- `ntdll!ZwQueryValueKey` at `0x180039b7b`
- `ntdll!RtlInitUnicodeString` at `0x1800399d8`
- `ntdll!RtlInitUnicodeString` at `0x1800399ef`
- `ntdll!RtlInitUnicodeString` at `0x1800399d8`
- `ntdll!RtlInitUnicodeString` at `0x1800399ef`
- `ntdll!NtClose` at `0x180039a93`
- `ntdll!NtClose` at `0x180039a93`

## string_xrefs

- `0x1800399c6`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetAlgorithmProvider(unsigned __int16 **a1, unsigned int *a2)
{
  unsigned int v4; // esi
  NTSTATUS v5; // ebx
  int Value; // edi
  __int64 v7; // rax
  _BYTE *v8; // rcx
  __int64 v9; // rcx
  _BYTE *v10; // rax
  _DWORD *v12; // r14
  unsigned int v13; // r8d
  _WORD *v14; // rax
  void *KeyHandle; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v20; // [rsp+E8h] [rbp+6Fh] BYREF
  void *v21; // [rsp+F0h] [rbp+77h] BYREF
  PVOID KeyValueInformation; // [rsp+F8h] [rbp+7Fh] BYREF

  *a1 = 0;
  *a2 = 0;
  v21 = 0;
  DestinationString = 0;
  v4 = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
  RtlInitUnicodeString(&ValueName, L"AlgorithmProvider");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  Value = -1073741801;
  if ( v5 >= 0 )
  {
    v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -1073741789 )
    {
      TpmApiCallbackAlloc(0, ResultLength, &KeyValueInformation);
      if ( KeyValueInformation )
      {
        v12 = KeyValueInformation;
        v5 = ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v5 >= 0 )
        {
          if ( v12[1] == 1 )
          {
            v4 = v12[2];
            v5 = -1073741789;
          }
          else
          {
            v5 = -1073741438;
          }
        }
      }
      else
      {
        v5 = -1073741801;
      }
    }
  }
  if ( qword_1801746C8 )
  {
    if ( KeyValueInformation )
    {
      v7 = ResultLength;
      v8 = KeyValueInformation;
      if ( ResultLength )
      {
        do
        {
          *v8++ = 0;
          --v7;
        }
        while ( v7 );
      }
    }
    ((void (__fastcall *)(_QWORD))qword_1801746C8)(0);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v5 == -1073741789 )
  {
    TpmApiCallbackAlloc(0, v4, &v21);
    if ( v21 )
    {
      v20 = v4;
      Value = TpmApiRegistryGetValue(&DestinationString, &ValueName, 1u, v21, &v20);
      if ( Value >= 0 )
      {
        v13 = v20;
        if ( v20 != v4 || v20 < 2 || (v20 & 1) != 0 )
        {
          Value = -1073741811;
        }
        else
        {
          v14 = v21;
          *a2 = v20;
          v14[((unsigned __int64)v13 >> 1) - 1] = 0;
          *a1 = (unsigned __int16 *)v21;
          v21 = 0;
        }
      }
    }
  }
  else
  {
    Value = v5;
  }
  if ( qword_1801746C8 )
  {
    if ( v21 )
    {
      v9 = v4;
      v10 = v21;
      if ( v4 )
      {
        do
        {
          *v10++ = 0;
          --v9;
        }
        while ( v9 );
      }
    }
    ((void (__fastcall *)(_QWORD))qword_1801746C8)(0);
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180039990  push    rbp
0x180039992  push    rbx
0x180039993  push    rsi
0x180039994  push    rdi
0x180039995  push    r12
0x180039997  push    r13
0x180039999  push    r14
0x18003999b  push    r15
0x18003999d  lea     rbp, [rsp-1Fh]
0x1800399a2  sub     rsp, 98h
0x1800399a9  xor     r13d, r13d
0x1800399ac  mov     r15, rdx
0x1800399af  mov     [rcx], r13
0x1800399b2  mov     r12, rcx
0x1800399b5  mov     [rdx], r13d
0x1800399b8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800399bc  xorps   xmm0, xmm0
0x1800399bf  mov     [rbp+57h+arg_10], r13
0x1800399c3  xorps   xmm1, xmm1
0x1800399c6  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800399cd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800399d1  mov     esi, r13d
0x1800399d4  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1800399d8  call    cs:__imp_RtlInitUnicodeString
0x1800399df  nop     dword ptr [rax+rax+00h]
0x1800399e4  lea     rdx, aAlgorithmprovi; "AlgorithmProvider"
0x1800399eb  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800399ef  call    cs:__imp_RtlInitUnicodeString
0x1800399f6  nop     dword ptr [rax+rax+00h]
0x1800399fb  lea     rax, [rbp+57h+DestinationString]
0x1800399ff  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180039a07  xorps   xmm0, xmm0
0x180039a0a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180039a0e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180039a12  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180039a1a  mov     edx, 20019h; DesiredAccess
0x180039a1f  mov     [rbp+57h+arg_0], r13d
0x180039a23  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180039a27  mov     [rbp+57h+KeyHandle], r13
0x180039a2b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180039a30  mov     [rbp+57h+KeyValueInformation], r13
0x180039a34  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180039a38  call    cs:__imp_ZwOpenKey
0x180039a3f  nop     dword ptr [rax+rax+00h]
0x180039a44  mov     ebx, eax
0x180039a46  mov     edi, 0C0000017h
0x180039a4b  test    eax, eax
0x180039a4d  jns     loc_180039AF9
0x180039a53  cmp     cs:qword_1801746C8, r13
0x180039a5a  jz      short loc_180039A8A
0x180039a5c  mov     rdx, [rbp+57h+KeyValueInformation]
0x180039a60  test    rdx, rdx
0x180039a63  jz      short loc_180039A7C
0x180039a65  mov     eax, [rbp+57h+arg_0]
0x180039a68  mov     rcx, rdx
0x180039a6b  test    rax, rax
0x180039a6e  jz      short loc_180039A7C
0x180039a70  mov     [rcx], r13b
0x180039a73  inc     rcx
0x180039a76  sub     rax, 1
0x180039a7a  jnz     short loc_180039A70
0x180039a7c  mov     rax, cs:qword_1801746C8
0x180039a83  xor     ecx, ecx
0x180039a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a8a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180039a8e  test    rcx, rcx
0x180039a91  jz      short loc_180039A9F
0x180039a93  call    cs:__imp_NtClose
0x180039a9a  nop     dword ptr [rax+rax+00h]
0x180039a9f  cmp     ebx, 0C0000023h
0x180039aa5  jz      loc_180039BB0
0x180039aab  mov     edi, ebx
0x180039aad  cmp     cs:qword_1801746C8, r13
0x180039ab4  jz      short loc_180039AE2
0x180039ab6  mov     rdx, [rbp+57h+arg_10]
0x180039aba  test    rdx, rdx
0x180039abd  jz      short loc_180039AD4
0x180039abf  mov     ecx, esi
0x180039ac1  mov     rax, rdx
0x180039ac4  test    esi, esi
0x180039ac6  jz      short loc_180039AD4
0x180039ac8  mov     [rax], r13b
0x180039acb  inc     rax
0x180039ace  sub     rcx, 1
0x180039ad2  jnz     short loc_180039AC8
0x180039ad4  mov     rax, cs:qword_1801746C8
0x180039adb  xor     ecx, ecx
0x180039add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ae2  mov     eax, edi
0x180039ae4  add     rsp, 98h
0x180039aeb  pop     r15
0x180039aed  pop     r14
0x180039aef  pop     r13
0x180039af1  pop     r12
0x180039af3  pop     rdi
0x180039af4  pop     rsi
0x180039af5  pop     rbx
0x180039af6  pop     rbp
0x180039af7  retn
0x180039af9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180039afd  lea     rax, [rbp+57h+arg_0]
0x180039b01  xor     r9d, r9d; KeyValueInformation
0x180039b04  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180039b09  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180039b0d  mov     [rsp+0D0h+Length], r13d; Length
0x180039b12  lea     r8d, [r9+2]; KeyValueInformationClass
0x180039b16  call    cs:__imp_ZwQueryValueKey
0x180039b1d  nop     dword ptr [rax+rax+00h]
0x180039b22  mov     ecx, 80000000h
0x180039b27  mov     ebx, eax
0x180039b29  add     eax, ecx
0x180039b2b  test    ecx, eax
0x180039b2d  jnz     short loc_180039B3B
0x180039b2f  cmp     ebx, 0C0000023h
0x180039b35  jnz     loc_180039A53
0x180039b3b  mov     edx, [rbp+57h+arg_0]
0x180039b3e  lea     r8, [rbp+57h+KeyValueInformation]
0x180039b42  xor     ecx, ecx
0x180039b44  call    TpmApiCallbackAlloc
0x180039b49  cmp     [rbp+57h+KeyValueInformation], r13
0x180039b4d  jnz     short loc_180039B56
0x180039b4f  mov     ebx, edi
0x180039b51  jmp     loc_180039A53
0x180039b56  mov     r14, [rbp+57h+KeyValueInformation]
0x180039b5a  lea     rax, [rbp+57h+arg_0]
0x180039b5e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180039b62  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180039b66  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180039b6b  mov     r9, r14; KeyValueInformation
0x180039b6e  mov     eax, [rbp+57h+arg_0]
0x180039b71  mov     r8d, 2; KeyValueInformationClass
0x180039b77  mov     [rsp+0D0h+Length], eax; Length
0x180039b7b  call    cs:__imp_ZwQueryValueKey
0x180039b82  nop     dword ptr [rax+rax+00h]
0x180039b87  mov     ebx, eax
0x180039b89  test    eax, eax
0x180039b8b  js      loc_180039A53
0x180039b91  cmp     dword ptr [r14+4], 1
0x180039b96  jz      short loc_180039BA2
0x180039b98  mov     ebx, 0C0000182h
0x180039b9d  jmp     loc_180039A53
0x180039ba2  mov     esi, [r14+8]
0x180039ba6  mov     ebx, 0C0000023h
0x180039bab  jmp     loc_180039A53
0x180039bb0  lea     r8, [rbp+57h+arg_10]
0x180039bb4  mov     edx, esi
0x180039bb6  xor     ecx, ecx
0x180039bb8  call    TpmApiCallbackAlloc
0x180039bbd  cmp     [rbp+57h+arg_10], r13
0x180039bc1  jz      loc_180039AAD
0x180039bc7  mov     r9, [rbp+57h+arg_10]; void *
0x180039bcb  lea     rax, [rbp+57h+arg_8]
0x180039bcf  mov     r8d, 1; unsigned int
0x180039bd5  mov     qword ptr [rsp+0D0h+Length], rax; unsigned int *
0x180039bda  lea     rdx, [rbp+57h+ValueName]; struct _UNICODE_STRING *
0x180039bde  mov     [rbp+57h+arg_8], esi
0x180039be1  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180039be5  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x180039bea  mov     edi, eax
0x180039bec  test    eax, eax
0x180039bee  js      loc_180039AAD
0x180039bf4  mov     r8d, [rbp+57h+arg_8]
0x180039bf8  cmp     r8d, esi
0x180039bfb  jnz     short loc_180039C2D
0x180039bfd  cmp     r8d, 2
0x180039c01  jb      short loc_180039C2D
0x180039c03  test    r8b, 1
0x180039c07  jnz     short loc_180039C2D
0x180039c09  mov     rax, [rbp+57h+arg_10]
0x180039c0d  mov     edx, r8d
0x180039c10  shr     rdx, 1
0x180039c13  mov     [r15], r8d
0x180039c16  mov     [rax+rdx*2-2], r13w
0x180039c1c  mov     rax, [rbp+57h+arg_10]
0x180039c20  mov     [r12], rax
0x180039c24  mov     [rbp+57h+arg_10], r13
0x180039c28  jmp     loc_180039AAD
0x180039c2d  mov     edi, 0C000000Dh
0x180039c32  jmp     loc_180039AAD
```
