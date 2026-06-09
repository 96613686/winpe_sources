# GetConfiguredServiceIdentity(void * *)

- ea: `0x14000c388`
- end: `0x14000c579`
- name: `?GetConfiguredServiceIdentity@@YAJPEAPEAX@Z`
- size: `497`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000c100`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x14000c388`
- `0x140024cc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000c400`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c400`
- `ntoskrnl!ZwOpenKey` at `0x14000c3da`
- `ntoskrnl!ZwOpenKey` at `0x14000c3da`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c436`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c4ca`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c436`
- `ntoskrnl!ZwQueryValueKey` at `0x14000c4ca`
- `ntoskrnl!ZwClose` at `0x14000c45a`
- `ntoskrnl!ZwClose` at `0x14000c48f`
- `ntoskrnl!ZwClose` at `0x14000c4dc`
- `ntoskrnl!ZwClose` at `0x14000c45a`
- `ntoskrnl!ZwClose` at `0x14000c48f`
- `ntoskrnl!ZwClose` at `0x14000c4dc`
- `ntoskrnl!RtlValidSid` at `0x14000c538`
- `ntoskrnl!RtlValidSid` at `0x14000c538`

## string_xrefs

- `0x14000c3f1`: `ServiceIdentity`

## pseudocode

```c
NTSTATUS __fastcall GetConfiguredServiceIdentity(void **a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  _DWORD *v5; // rbx
  NTSTATUS v6; // edi
  void *v7; // rax
  void *v8; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &g_RegistryPath;
  ObjectAttributes.RootDirectory = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"ServiceIdentity");
    ResultLength = 0;
    v3 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    v4 = v3;
    if ( v3 < 0 && v3 != -2147483643 && v3 != -1073741789 )
    {
      ZwClose(KeyHandle);
      return v4;
    }
    v5 = operator new(ResultLength, 0x100u, 0x5141514Du, LowPoolPriority);
    if ( !v5 )
    {
      ZwClose(KeyHandle);
      operator delete(0);
      return -1073741670;
    }
    v6 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v5, ResultLength, &ResultLength);
    ZwClose(KeyHandle);
    if ( v6 < 0 )
      goto LABEL_16;
    if ( v5[1] == 3 )
    {
      v7 = operator new((unsigned int)v5[2], 0x100u, 0x5141514Du, LowPoolPriority);
      v8 = v7;
      if ( !v7 )
      {
        operator delete(0);
        v6 = -1073741670;
        goto LABEL_16;
      }
      memmove(v7, v5 + 3, (unsigned int)v5[2]);
      if ( RtlValidSid(v8) )
      {
        *a1 = v8;
        operator delete(0);
        v6 = 0;
        goto LABEL_16;
      }
      operator delete(v8);
    }
    v6 = -1073741438;
LABEL_16:
    operator delete(v5);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000c388  mov     [rsp-18h+arg_0], rbx
0x14000c38d  push    rbp
0x14000c38e  push    rsi
0x14000c38f  push    rdi
0x14000c390  mov     rbp, rsp
0x14000c393  sub     rsp, 70h
0x14000c397  mov     rsi, rcx
0x14000c39a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000c3a2  lea     rax, ?g_RegistryPath@@3U_UNICODE_STRING@@A; _UNICODE_STRING g_RegistryPath
0x14000c3a9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000c3b1  xorps   xmm0, xmm0
0x14000c3b4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000c3b8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000c3bc  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000c3c4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000c3c8  mov     [rbp+KeyHandle], 0
0x14000c3d0  mov     edx, 1; DesiredAccess
0x14000c3d5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c3da  call    cs:__imp_ZwOpenKey
0x14000c3e1  nop     dword ptr [rax+rax+00h]
0x14000c3e6  test    eax, eax
0x14000c3e8  js      loc_14000C568
0x14000c3ee  xorps   xmm0, xmm0
0x14000c3f1  lea     rdx, SourceString; "ServiceIdentity"
0x14000c3f8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c3fc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000c400  call    cs:__imp_RtlInitUnicodeString
0x14000c407  nop     dword ptr [rax+rax+00h]
0x14000c40c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000c410  lea     rax, [rbp+arg_8]
0x14000c414  xor     r9d, r9d; KeyValueInformation
0x14000c417  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14000c41c  lea     rdx, [rbp+DestinationString]; ValueName
0x14000c420  mov     [rbp+arg_8], 0
0x14000c427  mov     [rsp+70h+Length], 0; Length
0x14000c42f  lea     edi, [r9+2]
0x14000c433  mov     r8d, edi; KeyValueInformationClass
0x14000c436  call    cs:__imp_ZwQueryValueKey
0x14000c43d  nop     dword ptr [rax+rax+00h]
0x14000c442  mov     ebx, eax
0x14000c444  test    eax, eax
0x14000c446  jns     short loc_14000C46D
0x14000c448  cmp     eax, 80000005h
0x14000c44d  jz      short loc_14000C46D
0x14000c44f  cmp     eax, 0C0000023h
0x14000c454  jz      short loc_14000C46D
0x14000c456  mov     rcx, [rbp+KeyHandle]; Handle
0x14000c45a  call    cs:__imp_ZwClose
0x14000c461  nop     dword ptr [rax+rax+00h]
0x14000c466  mov     eax, ebx
0x14000c468  jmp     loc_14000C568
0x14000c46d  mov     ecx, [rbp+arg_8]; unsigned __int64
0x14000c470  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000c473  mov     edx, 100h; unsigned __int64
0x14000c478  mov     r8d, 5141514Dh; unsigned int
0x14000c47e  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000c483  mov     rbx, rax
0x14000c486  test    rax, rax
0x14000c489  jnz     short loc_14000C4AC
0x14000c48b  mov     rcx, [rbp+KeyHandle]; Handle
0x14000c48f  call    cs:__imp_ZwClose
0x14000c496  nop     dword ptr [rax+rax+00h]
0x14000c49b  xor     ecx, ecx; void *
0x14000c49d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c4a2  mov     eax, 0C000009Ah
0x14000c4a7  jmp     loc_14000C568
0x14000c4ac  mov     eax, [rbp+arg_8]
0x14000c4af  lea     rcx, [rbp+arg_8]
0x14000c4b3  mov     [rsp+70h+ResultLength], rcx; ResultLength
0x14000c4b8  lea     rdx, [rbp+DestinationString]; ValueName
0x14000c4bc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000c4c0  mov     r9, rbx; KeyValueInformation
0x14000c4c3  mov     r8d, edi; KeyValueInformationClass
0x14000c4c6  mov     [rsp+70h+Length], eax; Length
0x14000c4ca  call    cs:__imp_ZwQueryValueKey
0x14000c4d1  nop     dword ptr [rax+rax+00h]
0x14000c4d6  mov     rcx, [rbp+KeyHandle]; Handle
0x14000c4da  mov     edi, eax
0x14000c4dc  call    cs:__imp_ZwClose
0x14000c4e3  nop     dword ptr [rax+rax+00h]
0x14000c4e8  test    edi, edi
0x14000c4ea  js      short loc_14000C55E
0x14000c4ec  cmp     dword ptr [rbx+4], 3
0x14000c4f0  jz      short loc_14000C4F9
0x14000c4f2  mov     edi, 0C0000182h
0x14000c4f7  jmp     short loc_14000C55E
0x14000c4f9  mov     ecx, [rbx+8]; unsigned __int64
0x14000c4fc  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000c4ff  mov     edx, 100h; unsigned __int64
0x14000c504  mov     r8d, 5141514Dh; unsigned int
0x14000c50a  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000c50f  mov     rdi, rax
0x14000c512  test    rax, rax
0x14000c515  jnz     short loc_14000C525
0x14000c517  xor     ecx, ecx; void *
0x14000c519  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c51e  mov     edi, 0C000009Ah
0x14000c523  jmp     short loc_14000C55E
0x14000c525  mov     r8d, [rbx+8]; Size
0x14000c529  lea     rdx, [rbx+0Ch]; Src
0x14000c52d  mov     rcx, rdi; void *
0x14000c530  call    memmove
0x14000c535  mov     rcx, rdi; Sid
0x14000c538  call    cs:__imp_RtlValidSid
0x14000c53f  nop     dword ptr [rax+rax+00h]
0x14000c544  test    al, al
0x14000c546  jnz     short loc_14000C552
0x14000c548  mov     rcx, rdi; void *
0x14000c54b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c550  jmp     short loc_14000C4F2
0x14000c552  xor     ecx, ecx; void *
0x14000c554  mov     [rsi], rdi
0x14000c557  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c55c  xor     edi, edi
0x14000c55e  mov     rcx, rbx; void *
0x14000c561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c566  mov     eax, edi
0x14000c568  mov     rbx, [rsp+70h+arg_0]
0x14000c570  add     rsp, 70h
0x14000c574  pop     rdi
0x14000c575  pop     rsi
0x14000c576  pop     rbp
0x14000c577  retn
```
