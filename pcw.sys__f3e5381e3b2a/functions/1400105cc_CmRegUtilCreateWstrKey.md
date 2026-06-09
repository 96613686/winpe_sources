# CmRegUtilCreateWstrKey

- ea: `0x1400105cc`
- end: `0x140010697`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000ff68`
- `0x140010450`

## callees

- `0x140001208`
- `0x1400105cc`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140010658`
- `ntoskrnl!ZwCreateKey` at `0x140010658`

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
0x1400105cc  mov     [rsp-8+arg_18], r9d
0x1400105d1  push    rbp
0x1400105d2  lea     rbp, [rsp-3Fh]
0x1400105d7  sub     rsp, 90h
0x1400105de  mov     r10, rcx
0x1400105e1  xorps   xmm0, xmm0
0x1400105e4  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1400105e8  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1400105ec  call    WdmlibRtlInitUnicodeStringEx
0x1400105f1  test    eax, eax
0x1400105f3  js      loc_14001068D
0x1400105f9  xor     eax, eax
0x1400105fb  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140010603  mov     [rbp+3Fh+arg_18], eax
0x140010606  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14001060a  mov     [rbp+3Fh+KeyHandle], rax
0x14001060e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140010612  lea     rax, [rbp+3Fh+DestinationString]
0x140010616  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14001061e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140010622  xor     r9d, r9d; TitleIndex
0x140010625  mov     rax, [rbp+3Fh+arg_20]
0x140010629  mov     edx, 0F003Fh; DesiredAccess
0x14001062e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x140010632  lea     rax, [rbp+3Fh+arg_18]
0x140010636  mov     [rsp+90h+Disposition], rax; Disposition
0x14001063b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x140010643  mov     [rsp+90h+Class], 0; Class
0x14001064c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x140010650  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x140010658  call    cs:__imp_ZwCreateKey
0x14001065f  nop     dword ptr [rax+rax+00h]
0x140010664  mov     r8d, eax
0x140010667  test    eax, eax
0x140010669  jns     short loc_140010671
0x14001066b  xor     edx, edx
0x14001066d  xor     ecx, ecx
0x14001066f  jmp     short loc_140010678
0x140010671  mov     ecx, [rbp+3Fh+arg_18]
0x140010674  mov     rdx, [rbp+3Fh+KeyHandle]
0x140010678  mov     rax, [rbp+3Fh+arg_30]
0x14001067c  mov     [rax], rdx
0x14001067f  mov     rax, [rbp+3Fh+arg_28]
0x140010683  test    rax, rax
0x140010686  jz      short loc_14001068A
0x140010688  mov     [rax], ecx
0x14001068a  mov     eax, r8d
0x14001068d  add     rsp, 90h
0x140010694  pop     rbp
0x140010695  retn
```
