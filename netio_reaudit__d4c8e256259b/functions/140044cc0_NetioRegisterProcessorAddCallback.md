# NetioRegisterProcessorAddCallback

- ea: `0x140044cc0`
- end: `0x140044d8d`
- name: `NetioRegisterProcessorAddCallback`
- size: `205`
- prototype: `__int64 __fastcall(PCALLBACK_OBJECT *CallbackObject, PCALLBACK_FUNCTION CallbackFunction, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140044cc0`
- `0x1400459e0`

## import_xrefs

- `ntoskrnl!ExRegisterCallback` at `0x140044d5d`
- `ntoskrnl!ExRegisterCallback` at `0x140044d5d`
- `ntoskrnl!ExCreateCallback` at `0x140044d42`
- `ntoskrnl!ExCreateCallback` at `0x140044d42`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044cf7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140044cf7`

## pseudocode

```c
__int64 __fastcall NetioRegisterProcessorAddCallback(
        PCALLBACK_OBJECT *CallbackObject,
        PCALLBACK_FUNCTION CallbackFunction,
        PVOID CallbackContext)
{
  NTSTATUS v6; // ebx
  struct _CALLBACK_OBJECT *v7; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Callback\\ProcessorAdd");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)CallbackObject = 0;
  CallbackObject[2] = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ExCreateCallback(CallbackObject, &ObjectAttributes, 0, 0);
  if ( v6 < 0 )
    goto LABEL_4;
  v7 = (struct _CALLBACK_OBJECT *)ExRegisterCallback(*CallbackObject, CallbackFunction, CallbackContext);
  CallbackObject[1] = v7;
  if ( !v7 )
  {
    v6 = -1073741823;
LABEL_4:
    NetioUnRegisterProcessorAddCallback(CallbackObject);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140044cc0  push    rbp
0x140044cc2  push    rbx
0x140044cc3  push    rsi
0x140044cc4  push    rdi
0x140044cc5  push    r14
0x140044cc7  mov     rbp, rsp
0x140044cca  sub     rsp, 60h
0x140044cce  xorps   xmm0, xmm0
0x140044cd1  mov     r14, rdx
0x140044cd4  mov     rdi, rcx
0x140044cd7  lea     rdx, aCallbackProces; "\\Callback\\ProcessorAdd"
0x140044cde  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140044ce2  xor     eax, eax
0x140044ce4  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044ce8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140044cec  mov     rsi, r8
0x140044cef  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140044cf3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140044cf7  call    cs:__imp_RtlInitUnicodeString
0x140044cfe  nop     dword ptr [rax+rax+00h]
0x140044d03  lea     rax, [rbp+DestinationString]
0x140044d07  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140044d0e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140044d12  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x140044d16  xorps   xmm1, xmm1
0x140044d19  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140044d21  xor     eax, eax
0x140044d23  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140044d2a  xorps   xmm0, xmm0
0x140044d2d  xor     r9d, r9d; AllowMultipleCallbacks
0x140044d30  movups  xmmword ptr [rdi], xmm1
0x140044d33  xor     r8d, r8d; Create
0x140044d36  mov     [rdi+10h], rax
0x140044d3a  mov     rcx, rdi; CallbackObject
0x140044d3d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140044d42  call    cs:__imp_ExCreateCallback
0x140044d49  nop     dword ptr [rax+rax+00h]
0x140044d4e  mov     ebx, eax
0x140044d50  test    eax, eax
0x140044d52  js      short loc_140044D77
0x140044d54  mov     rcx, [rdi]; CallbackObject
0x140044d57  mov     r8, rsi; CallbackContext
0x140044d5a  mov     rdx, r14; CallbackFunction
0x140044d5d  call    cs:__imp_ExRegisterCallback
0x140044d64  nop     dword ptr [rax+rax+00h]
0x140044d69  mov     [rdi+8], rax
0x140044d6d  test    rax, rax
0x140044d70  jnz     short loc_140044D7F
0x140044d72  mov     ebx, 0C0000001h
0x140044d77  mov     rcx, rdi
0x140044d7a  call    NetioUnRegisterProcessorAddCallback
0x140044d7f  mov     eax, ebx
0x140044d81  add     rsp, 60h
0x140044d85  pop     r14
0x140044d87  pop     rdi
0x140044d88  pop     rsi
0x140044d89  pop     rbx
0x140044d8a  pop     rbp
0x140044d8b  retn
```
