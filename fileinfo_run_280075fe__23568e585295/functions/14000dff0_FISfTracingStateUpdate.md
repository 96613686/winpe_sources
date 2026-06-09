# FISfTracingStateUpdate

- ea: `0x14000dff0`
- end: `0x14000e141`
- name: `FISfTracingStateUpdate`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400148cc`

## callees

- `0x14000dff0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e11d`
- `ntoskrnl!ZwClose` at `0x14000e11d`
- `ntoskrnl!ZwSetValueKey` at `0x14000e0dd`
- `ntoskrnl!ZwSetValueKey` at `0x14000e0dd`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000e0f1`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000e0f1`
- `ntoskrnl!ZwCreateKey` at `0x14000e08a`
- `ntoskrnl!ZwCreateKey` at `0x14000e08a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e02e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e02e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a7`

## string_xrefs

- `0x14000e008`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters`

## pseudocode

```c
__int64 __fastcall FISfTracingStateUpdate(int a1)
{
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+98h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF

  Data = 0;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\PrefetchParameters");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"SfTracingState");
    if ( a1 )
    {
      Data = 1;
      v2 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
      if ( v2 < 0 )
        goto LABEL_8;
      goto LABEL_7;
    }
    v2 = ZwDeleteValueKey(KeyHandle, &DestinationString);
    if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741772 )
LABEL_7:
      v2 = 0;
  }
LABEL_8:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000dff0  mov     [rsp-8+arg_0], rbx
0x14000dff5  mov     [rsp-8+arg_18], rdi
0x14000dffa  push    rbp
0x14000dffb  mov     rbp, rsp
0x14000dffe  sub     rsp, 80h
0x14000e005  xorps   xmm0, xmm0
0x14000e008  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000e00f  xor     eax, eax
0x14000e011  mov     edi, ecx
0x14000e013  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000e017  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e01b  mov     [rbp+Data], eax
0x14000e01e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000e022  mov     [rbp+KeyHandle], rax
0x14000e026  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e02a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000e02e  call    cs:__imp_RtlInitUnicodeString
0x14000e035  nop     dword ptr [rax+rax+00h]
0x14000e03a  lea     rax, [rbp+DestinationString]
0x14000e03e  mov     [rsp+80h+Disposition], 0; Disposition
0x14000e047  xorps   xmm0, xmm0
0x14000e04a  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x14000e052  xor     r9d, r9d; TitleIndex
0x14000e055  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e059  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e05d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e064  mov     edx, 0F003Fh; DesiredAccess
0x14000e069  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000e071  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e075  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000e07c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e081  mov     [rsp+80h+Class], 0; Class
0x14000e08a  call    cs:__imp_ZwCreateKey
0x14000e091  nop     dword ptr [rax+rax+00h]
0x14000e096  mov     ebx, eax
0x14000e098  test    eax, eax
0x14000e09a  js      short loc_14000E114
0x14000e09c  lea     rdx, aSftracingstate; "SfTracingState"
0x14000e0a3  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e0a7  call    cs:__imp_RtlInitUnicodeString
0x14000e0ae  nop     dword ptr [rax+rax+00h]
0x14000e0b3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e0b7  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e0bb  test    edi, edi
0x14000e0bd  jz      short loc_14000E0F1
0x14000e0bf  mov     r9d, 4; Type
0x14000e0c5  mov     [rbp+Data], 1
0x14000e0cc  lea     rax, [rbp+Data]
0x14000e0d0  mov     [rsp+80h+CreateOptions], r9d; DataSize
0x14000e0d5  xor     r8d, r8d; TitleIndex
0x14000e0d8  mov     [rsp+80h+Class], rax; Data
0x14000e0dd  call    cs:__imp_ZwSetValueKey
0x14000e0e4  nop     dword ptr [rax+rax+00h]
0x14000e0e9  mov     ebx, eax
0x14000e0eb  test    eax, eax
0x14000e0ed  js      short loc_14000E114
0x14000e0ef  jmp     short loc_14000E112
0x14000e0f1  call    cs:__imp_ZwDeleteValueKey
0x14000e0f8  nop     dword ptr [rax+rax+00h]
0x14000e0fd  mov     ecx, 80000000h
0x14000e102  mov     ebx, eax
0x14000e104  add     eax, ecx
0x14000e106  test    ecx, eax
0x14000e108  jnz     short loc_14000E112
0x14000e10a  cmp     ebx, 0C0000034h
0x14000e110  jnz     short loc_14000E114
0x14000e112  xor     ebx, ebx
0x14000e114  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e118  test    rcx, rcx
0x14000e11b  jz      short loc_14000E129
0x14000e11d  call    cs:__imp_ZwClose
0x14000e124  nop     dword ptr [rax+rax+00h]
0x14000e129  lea     r11, [rsp+80h+var_s0]
0x14000e131  mov     eax, ebx
0x14000e133  mov     rbx, [r11+10h]
0x14000e137  mov     rdi, [r11+28h]
0x14000e13b  mov     rsp, r11
0x14000e13e  pop     rbp
0x14000e13f  retn
```
