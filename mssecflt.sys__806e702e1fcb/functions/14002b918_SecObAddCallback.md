# SecObAddCallback

- ea: `0x14002b918`
- end: `0x14002ba4f`
- name: `SecObAddCallback`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c2a4`

## callees

- `0x140011650`
- `0x14002b918`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x14002b99a`
- `ntoskrnl!ObRegisterCallbacks` at `0x14002ba1a`
- `ntoskrnl!ObRegisterCallbacks` at `0x14002ba1a`
- `ntoskrnl!PsThreadType` at `0x14002b9b1`
- `ntoskrnl!ExDesktopObjectType` at `0x14002b9d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002b98e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002b98e`

## pseudocode

```c
NTSTATUS __fastcall SecObAddCallback(PVOID *a1)
{
  NTSTATUS result; // eax
  USHORT v3; // cx
  PVOID RegistrationHandle; // [rsp+20h] [rbp-59h] BYREF
  _OB_CALLBACK_REGISTRATION CallbackRegistration; // [rsp+28h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  POBJECT_TYPE *v7; // [rsp+60h] [rbp-19h] BYREF
  __int128 v8; // [rsp+68h] [rbp-11h]
  __int64 v9; // [rsp+78h] [rbp-1h]
  POBJECT_TYPE *v10; // [rsp+80h] [rbp+7h]
  __int128 v11; // [rsp+88h] [rbp+Fh]
  __int64 v12; // [rsp+98h] [rbp+1Fh]
  POBJECT_TYPE *v13; // [rsp+A0h] [rbp+27h]
  __int128 v14; // [rsp+A8h] [rbp+2Fh]
  __int64 v15; // [rsp+B8h] [rbp+3Fh]

  *(_DWORD *)(&CallbackRegistration.OperationRegistrationCount + 1) = 0;
  result = -1073741823;
  DestinationString = 0;
  v9 = 0;
  v8 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  RegistrationHandle = 0;
  if ( SecData )
  {
    *a1 = 0;
    RtlInitUnicodeString(&DestinationString, L"385600");
    v7 = PsProcessType;
    LODWORD(v8) = v8 | 3;
    LODWORD(v11) = v11 | 3;
    v10 = PsThreadType;
    v3 = 2;
    *((_QWORD *)&v8 + 1) = SecObPreOperationCallback;
    *((_QWORD *)&v11 + 1) = SecObPreOperationCallback;
    if ( (dword_140020004 & 8) != 0 )
    {
      v3 = 3;
      LODWORD(v14) = v14 | 3;
      v13 = ExDesktopObjectType;
      *((_QWORD *)&v14 + 1) = SecObPreOperationCallback;
    }
    CallbackRegistration.OperationRegistrationCount = v3;
    CallbackRegistration.Version = 256;
    CallbackRegistration.RegistrationContext = 0;
    CallbackRegistration.OperationRegistration = (OB_OPERATION_REGISTRATION *)&v7;
    CallbackRegistration.Altitude = DestinationString;
    result = ObRegisterCallbacks(&CallbackRegistration, &RegistrationHandle);
    if ( result >= 0 )
      *a1 = RegistrationHandle;
  }
  return result;
}

```

## disassembly

```asm
0x14002b918  mov     [rsp-8+arg_8], rbx
0x14002b91d  push    rbp
0x14002b91e  lea     rbp, [rsp-57h]
0x14002b923  sub     rsp, 0D0h
0x14002b92a  mov     rax, cs:__security_cookie
0x14002b931  xor     rax, rsp
0x14002b934  mov     [rbp+57h+var_10], rax
0x14002b938  xorps   xmm0, xmm0
0x14002b93b  mov     dword ptr [rbp+57h+CallbackRegistration+4], 0
0x14002b942  mov     rbx, rcx
0x14002b945  xorps   xmm1, xmm1
0x14002b948  xor     ecx, ecx
0x14002b94a  mov     eax, 0C0000001h
0x14002b94f  cmp     cs:SecData, rcx
0x14002b956  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002b95a  mov     [rbp+57h+var_58], rcx
0x14002b95e  movups  [rbp+57h+var_68], xmm0
0x14002b962  mov     [rbp+57h+var_38], rcx
0x14002b966  movups  [rbp+57h+var_48], xmm1
0x14002b96a  mov     [rbp+57h+var_30], rcx
0x14002b96e  movups  [rbp+57h+var_28], xmm0
0x14002b972  mov     [rbp+57h+var_18], rcx
0x14002b976  mov     [rbp+57h+RegistrationHandle], rcx
0x14002b97a  jz      loc_14002BA31
0x14002b980  mov     [rbx], rcx
0x14002b983  lea     rdx, a385600; "385600"
0x14002b98a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002b98e  call    cs:__imp_RtlInitUnicodeString
0x14002b995  nop     dword ptr [rax+rax+00h]
0x14002b99a  mov     rax, cs:__imp_PsProcessType
0x14002b9a1  lea     r8, SecObPreOperationCallback
0x14002b9a8  mov     edx, 3
0x14002b9ad  mov     [rbp+57h+var_70], rax
0x14002b9b1  mov     rax, cs:__imp_PsThreadType
0x14002b9b8  or      dword ptr [rbp+57h+var_68], edx
0x14002b9bb  or      dword ptr [rbp+57h+var_48], edx
0x14002b9be  mov     [rbp+57h+var_50], rax
0x14002b9c2  lea     ecx, [rdx-1]
0x14002b9c5  mov     eax, cs:dword_140020004
0x14002b9cb  mov     qword ptr [rbp+57h+var_68+8], r8
0x14002b9cf  mov     qword ptr [rbp+57h+var_48+8], r8
0x14002b9d3  test    al, 8
0x14002b9d5  jz      short loc_14002B9EC
0x14002b9d7  mov     rax, cs:ExDesktopObjectType
0x14002b9de  movzx   ecx, dx
0x14002b9e1  or      dword ptr [rbp+57h+var_28], edx
0x14002b9e4  mov     [rbp+57h+var_30], rax
0x14002b9e8  mov     qword ptr [rbp+57h+var_28+8], r8
0x14002b9ec  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x14002b9f0  mov     eax, 100h
0x14002b9f5  mov     [rbp+57h+CallbackRegistration.OperationRegistrationCount], cx
0x14002b9f9  mov     [rbp+57h+CallbackRegistration.Version], ax
0x14002b9fd  lea     rdx, [rbp+57h+RegistrationHandle]; RegistrationHandle
0x14002ba01  lea     rax, [rbp+57h+var_70]
0x14002ba05  mov     [rbp+57h+CallbackRegistration.RegistrationContext], 0
0x14002ba0d  lea     rcx, [rbp+57h+CallbackRegistration]; CallbackRegistration
0x14002ba11  mov     [rbp+57h+CallbackRegistration.OperationRegistration], rax
0x14002ba15  movdqu  xmmword ptr [rbp+57h+CallbackRegistration.Altitude.Length], xmm0
0x14002ba1a  call    cs:__imp_ObRegisterCallbacks
0x14002ba21  nop     dword ptr [rax+rax+00h]
0x14002ba26  test    eax, eax
0x14002ba28  js      short loc_14002BA31
0x14002ba2a  mov     rcx, [rbp+57h+RegistrationHandle]
0x14002ba2e  mov     [rbx], rcx
0x14002ba31  mov     rcx, [rbp+57h+var_10]
0x14002ba35  xor     rcx, rsp; StackCookie
0x14002ba38  call    __security_check_cookie
0x14002ba3d  mov     rbx, [rsp+0D0h+arg_8]
0x14002ba45  add     rsp, 0D0h
0x14002ba4c  pop     rbp
0x14002ba4d  retn
```
