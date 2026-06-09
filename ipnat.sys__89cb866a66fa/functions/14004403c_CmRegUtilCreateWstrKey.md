# CmRegUtilCreateWstrKey

- ea: `0x14004403c`
- end: `0x140044107`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400438d8`
- `0x140043dc0`

## callees

- `0x14002811c`
- `0x14004403c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1400440c8`
- `ntoskrnl!ZwCreateKey` at `0x1400440c8`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+7h] BYREF
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
0x14004403c  mov     [rsp-8+arg_18], r9d
0x140044041  push    rbp
0x140044042  lea     rbp, [rsp-3Fh]
0x140044047  sub     rsp, 90h
0x14004404e  mov     r10, rcx
0x140044051  xorps   xmm0, xmm0
0x140044054  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140044058  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x14004405c  call    WdmlibRtlInitUnicodeStringEx
0x140044061  test    eax, eax
0x140044063  js      loc_1400440FD
0x140044069  xor     eax, eax
0x14004406b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140044073  mov     [rbp+3Fh+arg_18], eax
0x140044076  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14004407a  mov     [rbp+3Fh+KeyHandle], rax
0x14004407e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140044082  lea     rax, [rbp+3Fh+DestinationString]
0x140044086  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14004408e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140044092  xor     r9d, r9d; TitleIndex
0x140044095  mov     rax, [rbp+3Fh+arg_20]
0x140044099  mov     edx, 0F003Fh; DesiredAccess
0x14004409e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x1400440a2  lea     rax, [rbp+3Fh+arg_18]
0x1400440a6  mov     [rsp+90h+Disposition], rax; Disposition
0x1400440ab  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x1400440b3  mov     [rsp+90h+Class], 0; Class
0x1400440bc  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x1400440c0  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x1400440c8  call    cs:__imp_ZwCreateKey
0x1400440cf  nop     dword ptr [rax+rax+00h]
0x1400440d4  mov     r8d, eax
0x1400440d7  test    eax, eax
0x1400440d9  jns     short loc_1400440E1
0x1400440db  xor     edx, edx
0x1400440dd  xor     ecx, ecx
0x1400440df  jmp     short loc_1400440E8
0x1400440e1  mov     ecx, [rbp+3Fh+arg_18]
0x1400440e4  mov     rdx, [rbp+3Fh+KeyHandle]
0x1400440e8  mov     rax, [rbp+3Fh+arg_30]
0x1400440ec  mov     [rax], rdx
0x1400440ef  mov     rax, [rbp+3Fh+arg_28]
0x1400440f3  test    rax, rax
0x1400440f6  jz      short loc_1400440FA
0x1400440f8  mov     [rax], ecx
0x1400440fa  mov     eax, r8d
0x1400440fd  add     rsp, 90h
0x140044104  pop     rbp
0x140044105  retn
```
