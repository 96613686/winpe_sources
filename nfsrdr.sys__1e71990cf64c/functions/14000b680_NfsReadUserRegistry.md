# NfsReadUserRegistry

- ea: `0x14000b680`
- end: `0x14000b8ee`
- name: `NfsReadUserRegistry`
- size: `622`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCWSTR@<rdx>, PCWSTR@<r8>, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036354`
- `0x14003677c`
- `0x140036fd0`

## callees

- `0x14000b680`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b711`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b711`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b779`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b779`
- `ntoskrnl!ZwOpenKey` at `0x14000b7ce`
- `ntoskrnl!ZwOpenKey` at `0x14000b7ce`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b864`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b864`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b729`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b837`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b729`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b837`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b89d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b89d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8c7`
- `ntoskrnl!ZwClose` at `0x14000b81a`
- `ntoskrnl!ZwClose` at `0x14000b8ad`
- `ntoskrnl!ZwClose` at `0x14000b81a`
- `ntoskrnl!ZwClose` at `0x14000b8ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000b6eb`
- `ntoskrnl!ExAllocatePool2` at `0x14000b802`
- `ntoskrnl!ExAllocatePool2` at `0x14000b6eb`
- `ntoskrnl!ExAllocatePool2` at `0x14000b802`

## pseudocode

```c
__int64 __fastcall NfsReadUserRegistry(PCUNICODE_STRING SourceString, PCWSTR a2, PCWSTR a3, ULONG a4, void *a5)
{
  NTSTATUS appended; // ebx
  unsigned int *Pool2; // rdi
  void *KeyHandle; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-21h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  ULONG Length; // [rsp+C8h] [rbp+6Fh] BYREF

  Length = a4;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  KeyHandle = 0;
  DestinationString.MaximumLength = SourceString->Length + 512;
  DestinationString.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  Source = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, DestinationString.MaximumLength, 1668507214);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, SourceString);
    if ( !a2 )
      goto LABEL_8;
    RtlInitUnicodeString(&Source, a2);
    if ( *a2 != 92 && DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
    {
      DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
      DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
      DestinationString.Length += 2;
    }
    appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
    if ( appended >= 0 )
    {
LABEL_8:
      DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
      if ( appended >= 0 )
      {
        Length = 20;
        Source = 0;
        Pool2 = (unsigned int *)ExAllocatePool2(258, 20, 1668507214);
        if ( Pool2 )
        {
          RtlInitUnicodeString(&Source, a3);
          appended = ZwQueryValueKey(KeyHandle, &Source, KeyValuePartialInformation, Pool2, Length, &Length);
          if ( appended >= 0 )
          {
            if ( Pool2[2] <= 4 )
              memmove(a5, Pool2 + 3, Pool2[2]);
            else
              appended = -2147483643;
          }
          ExFreePoolWithTag(Pool2, 0x6373664Eu);
          ZwClose(KeyHandle);
        }
        else
        {
          ZwClose(KeyHandle);
          appended = -1073741670;
        }
      }
    }
  }
  else
  {
    appended = -1073741823;
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6373664Eu);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000b680  mov     [rsp-8+arg_0], rbx
0x14000b685  mov     [rsp-8+arg_8], rsi
0x14000b68a  mov     [rsp-8+arg_18], r9d
0x14000b68f  push    rbp
0x14000b690  push    rdi
0x14000b691  push    r14
0x14000b693  lea     rbp, [rsp-37h]
0x14000b698  sub     rsp, 90h
0x14000b69f  xorps   xmm0, xmm0
0x14000b6a2  xor     r14d, r14d
0x14000b6a5  xor     eax, eax
0x14000b6a7  mov     dword ptr [rbp+47h+DestinationString+4], r14d
0x14000b6ab  mov     eax, 200h
0x14000b6b0  mov     [rbp+47h+KeyHandle], r14
0x14000b6b4  add     ax, [rcx]
0x14000b6b7  mov     rdi, rdx
0x14000b6ba  movzx   edx, ax
0x14000b6bd  mov     rsi, r8
0x14000b6c0  mov     rbx, rcx
0x14000b6c3  mov     [rbp+47h+DestinationString.MaximumLength], dx
0x14000b6c7  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x14000b6cb  mov     ecx, 102h
0x14000b6d0  mov     [rbp+47h+DestinationString.Buffer], r14
0x14000b6d4  mov     r8d, 6373664Eh
0x14000b6da  mov     [rbp+47h+DestinationString.Length], r14w
0x14000b6df  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x14000b6e3  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14000b6e7  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x14000b6eb  call    cs:__imp_ExAllocatePool2
0x14000b6f2  nop     dword ptr [rax+rax+00h]
0x14000b6f7  mov     [rbp+47h+DestinationString.Buffer], rax
0x14000b6fb  test    rax, rax
0x14000b6fe  jnz     short loc_14000B70A
0x14000b700  mov     ebx, 0C0000001h
0x14000b705  jmp     loc_14000B8B9
0x14000b70a  mov     rdx, rbx; SourceString
0x14000b70d  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000b711  call    cs:__imp_RtlCopyUnicodeString
0x14000b718  nop     dword ptr [rax+rax+00h]
0x14000b71d  test    rdi, rdi
0x14000b720  jz      short loc_14000B78F
0x14000b722  mov     rdx, rdi; SourceString
0x14000b725  lea     rcx, [rbp+47h+Source]; DestinationString
0x14000b729  call    cs:__imp_RtlInitUnicodeString
0x14000b730  nop     dword ptr [rax+rax+00h]
0x14000b735  cmp     word ptr [rdi], 5Ch ; '\'
0x14000b739  jz      short loc_14000B771
0x14000b73b  movzx   ecx, [rbp+47h+DestinationString.Length]
0x14000b73f  mov     rdx, [rbp+47h+DestinationString.Buffer]
0x14000b743  mov     eax, ecx
0x14000b745  shr     rax, 1
0x14000b748  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x14000b74e  jz      short loc_14000B771
0x14000b750  mov     eax, ecx
0x14000b752  shr     rax, 1
0x14000b755  mov     word ptr [rdx+rax*2], 5Ch ; '\'
0x14000b75b  movzx   edx, [rbp+47h+DestinationString.Length]
0x14000b75f  mov     rax, [rbp+47h+DestinationString.Buffer]
0x14000b763  shr     rdx, 1
0x14000b766  mov     [rax+rdx*2+2], r14w
0x14000b76c  add     [rbp+47h+DestinationString.Length], 2
0x14000b771  lea     rdx, [rbp+47h+Source]; Source
0x14000b775  lea     rcx, [rbp+47h+DestinationString]; Destination
0x14000b779  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000b780  nop     dword ptr [rax+rax+00h]
0x14000b785  mov     ebx, eax
0x14000b787  test    eax, eax
0x14000b789  js      loc_14000B8B9
0x14000b78f  movzx   edx, [rbp+47h+DestinationString.Length]
0x14000b793  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14000b797  mov     rax, [rbp+47h+DestinationString.Buffer]
0x14000b79b  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x14000b79f  shr     rdx, 1
0x14000b7a2  xorps   xmm0, xmm0
0x14000b7a5  mov     [rax+rdx*2], r14w
0x14000b7aa  lea     rax, [rbp+47h+DestinationString]
0x14000b7ae  mov     edx, 80000000h; DesiredAccess
0x14000b7b3  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14000b7b7  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14000b7be  mov     [rbp+47h+ObjectAttributes.RootDirectory], r14
0x14000b7c2  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x14000b7c9  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b7ce  call    cs:__imp_ZwOpenKey
0x14000b7d5  nop     dword ptr [rax+rax+00h]
0x14000b7da  mov     ebx, eax
0x14000b7dc  test    eax, eax
0x14000b7de  js      loc_14000B8B9
0x14000b7e4  xorps   xmm0, xmm0
0x14000b7e7  mov     [rbp+47h+arg_18], 14h
0x14000b7ee  mov     edx, 14h
0x14000b7f3  mov     ecx, 102h
0x14000b7f8  mov     r8d, 6373664Eh
0x14000b7fe  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x14000b802  call    cs:__imp_ExAllocatePool2
0x14000b809  nop     dword ptr [rax+rax+00h]
0x14000b80e  mov     rdi, rax
0x14000b811  test    rax, rax
0x14000b814  jnz     short loc_14000B830
0x14000b816  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x14000b81a  call    cs:__imp_ZwClose
0x14000b821  nop     dword ptr [rax+rax+00h]
0x14000b826  mov     ebx, 0C000009Ah
0x14000b82b  jmp     loc_14000B8B9
0x14000b830  mov     rdx, rsi; SourceString
0x14000b833  lea     rcx, [rbp+47h+Source]; DestinationString
0x14000b837  call    cs:__imp_RtlInitUnicodeString
0x14000b83e  nop     dword ptr [rax+rax+00h]
0x14000b843  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x14000b847  lea     rax, [rbp+47h+arg_18]
0x14000b84b  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14000b850  lea     rdx, [rbp+47h+Source]; ValueName
0x14000b854  mov     eax, [rbp+47h+arg_18]
0x14000b857  mov     r9, rdi; KeyValueInformation
0x14000b85a  mov     r8d, 2; KeyValueInformationClass
0x14000b860  mov     [rsp+0A0h+Length], eax; Length
0x14000b864  call    cs:__imp_ZwQueryValueKey
0x14000b86b  nop     dword ptr [rax+rax+00h]
0x14000b870  mov     ebx, eax
0x14000b872  test    eax, eax
0x14000b874  js      short loc_14000B895
0x14000b876  mov     eax, [rdi+8]
0x14000b879  cmp     eax, 4
0x14000b87c  jbe     short loc_14000B885
0x14000b87e  mov     ebx, 80000005h
0x14000b883  jmp     short loc_14000B895
0x14000b885  mov     rcx, [rbp+47h+arg_20]; void *
0x14000b889  lea     rdx, [rdi+0Ch]; Src
0x14000b88d  mov     r8, rax; Size
0x14000b890  call    memmove
0x14000b895  mov     edx, 6373664Eh; Tag
0x14000b89a  mov     rcx, rdi; P
0x14000b89d  call    cs:__imp_ExFreePoolWithTag
0x14000b8a4  nop     dword ptr [rax+rax+00h]
0x14000b8a9  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x14000b8ad  call    cs:__imp_ZwClose
0x14000b8b4  nop     dword ptr [rax+rax+00h]
0x14000b8b9  mov     rcx, [rbp+47h+DestinationString.Buffer]; P
0x14000b8bd  test    rcx, rcx
0x14000b8c0  jz      short loc_14000B8D3
0x14000b8c2  mov     edx, 6373664Eh; Tag
0x14000b8c7  call    cs:__imp_ExFreePoolWithTag
0x14000b8ce  nop     dword ptr [rax+rax+00h]
0x14000b8d3  lea     r11, [rsp+0A0h+var_10]
0x14000b8db  mov     eax, ebx
0x14000b8dd  mov     rbx, [r11+20h]
0x14000b8e1  mov     rsi, [r11+28h]
0x14000b8e5  mov     rsp, r11
0x14000b8e8  pop     r14
0x14000b8ea  pop     rdi
0x14000b8eb  pop     rbp
0x14000b8ec  retn
```
