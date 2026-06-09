# CmRegUtilCreateWstrKey

- ea: `0x140018b1c`
- end: `0x140018be7`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400183b8`
- `0x1400188a0`

## callees

- `0x140007e0c`
- `0x140018b1c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140018ba8`
- `ntoskrnl!ZwCreateKey` at `0x140018ba8`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  void *v8; // r10
  NTSTATUS v9; // r8d
  void *v10; // rdx
  ULONG v11; // ecx
  void *KeyHandle; // [rsp+40h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+7h] BYREF
  ULONG Disposition; // [rsp+B8h] [rbp+67h] BYREF

  Disposition = a4;
  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    Disposition = 0;
    KeyHandle = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = a5;
    ObjectAttributes.RootDirectory = v8;
    ObjectAttributes.SecurityQualityOfService = 0;
    v9 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v9 >= 0 )
    {
      v11 = Disposition;
      v10 = KeyHandle;
    }
    else
    {
      v10 = 0;
      v11 = 0;
    }
    *a7 = v10;
    if ( a6 )
      *a6 = v11;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140018b1c  mov     [rsp-8+arg_18], r9d
0x140018b21  push    rbp
0x140018b22  lea     rbp, [rsp-3Fh]
0x140018b27  sub     rsp, 90h
0x140018b2e  mov     r10, rcx
0x140018b31  xorps   xmm0, xmm0
0x140018b34  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140018b38  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140018b3c  call    WdmlibRtlInitUnicodeStringEx
0x140018b41  test    eax, eax
0x140018b43  js      loc_140018BDD
0x140018b49  xor     eax, eax
0x140018b4b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140018b53  mov     [rbp+3Fh+arg_18], eax
0x140018b56  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140018b5a  mov     [rbp+3Fh+KeyHandle], rax
0x140018b5e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140018b62  lea     rax, [rbp+3Fh+DestinationString]
0x140018b66  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x140018b6e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140018b72  xor     r9d, r9d; TitleIndex
0x140018b75  mov     rax, [rbp+3Fh+arg_20]
0x140018b79  mov     edx, 0F003Fh; DesiredAccess
0x140018b7e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x140018b82  lea     rax, [rbp+3Fh+arg_18]
0x140018b86  mov     [rsp+90h+Disposition], rax; Disposition
0x140018b8b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x140018b93  mov     [rsp+90h+Class], 0; Class
0x140018b9c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x140018ba0  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x140018ba8  call    cs:__imp_ZwCreateKey
0x140018baf  nop     dword ptr [rax+rax+00h]
0x140018bb4  mov     r8d, eax
0x140018bb7  test    eax, eax
0x140018bb9  jns     short loc_140018BC1
0x140018bbb  xor     edx, edx
0x140018bbd  xor     ecx, ecx
0x140018bbf  jmp     short loc_140018BC8
0x140018bc1  mov     ecx, [rbp+3Fh+arg_18]
0x140018bc4  mov     rdx, [rbp+3Fh+KeyHandle]
0x140018bc8  mov     rax, [rbp+3Fh+arg_30]
0x140018bcc  mov     [rax], rdx
0x140018bcf  mov     rax, [rbp+3Fh+arg_28]
0x140018bd3  test    rax, rax
0x140018bd6  jz      short loc_140018BDA
0x140018bd8  mov     [rax], ecx
0x140018bda  mov     eax, r8d
0x140018bdd  add     rsp, 90h
0x140018be4  pop     rbp
0x140018be5  retn
```
