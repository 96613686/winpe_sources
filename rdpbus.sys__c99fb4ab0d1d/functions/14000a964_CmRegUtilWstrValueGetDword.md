# CmRegUtilWstrValueGetDword

- ea: `0x14000a964`
- end: `0x14000aa03`
- name: `CmRegUtilWstrValueGetDword`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009f4c`

## callees

- `0x140002350`
- `0x140002520`
- `0x14000a964`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000a9c6`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a9c6`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilWstrValueGetDword(__int64 a1, const WCHAR *a2, __int64 a3, _DWORD *a4)
{
  NTSTATUS result; // eax
  void *v6; // r10
  int v7; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+48h] [rbp-20h] BYREF
  int v11; // [rsp+4Ch] [rbp-1Ch]
  int v12; // [rsp+54h] [rbp-14h]

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    ResultLength = 0;
    v7 = 0;
    result = ZwQueryValueKey(
               v6,
               &DestinationString,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x10u,
               &ResultLength);
    if ( result >= 0 )
    {
      if ( v11 == 4 )
        v7 = v12;
      else
        result = -1073741788;
    }
    *a4 = v7;
  }
  return result;
}

```

## disassembly

```asm
0x14000a964  mov     [rsp+arg_8], rbx
0x14000a969  push    rdi
0x14000a96a  sub     rsp, 60h
0x14000a96e  mov     rax, cs:__security_cookie
0x14000a975  xor     rax, rsp
0x14000a978  mov     [rsp+68h+var_10], rax
0x14000a97d  mov     r10, rcx
0x14000a980  xorps   xmm0, xmm0
0x14000a983  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000a988  mov     rdi, r9
0x14000a98b  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14000a990  call    WdmlibRtlInitUnicodeStringEx
0x14000a995  test    eax, eax
0x14000a997  js      short loc_14000A9EA
0x14000a999  lea     rax, [rsp+68h+var_38]
0x14000a99e  mov     [rsp+68h+var_38], 0
0x14000a9a6  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14000a9ab  lea     r9, [rsp+68h+KeyValueInformation]; KeyValueInformation
0x14000a9b0  xor     ebx, ebx
0x14000a9b2  mov     [rsp+68h+Length], 10h; Length
0x14000a9ba  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14000a9bf  mov     rcx, r10; KeyHandle
0x14000a9c2  lea     r8d, [rbx+2]; KeyValueInformationClass
0x14000a9c6  call    cs:__imp_ZwQueryValueKey
0x14000a9cd  nop     dword ptr [rax+rax+00h]
0x14000a9d2  test    eax, eax
0x14000a9d4  js      short loc_14000A9E8
0x14000a9d6  cmp     [rsp+68h+var_1C], 4
0x14000a9db  jnz     short loc_14000A9E3
0x14000a9dd  mov     ebx, [rsp+68h+var_14]
0x14000a9e1  jmp     short loc_14000A9E8
0x14000a9e3  mov     eax, 0C0000024h
0x14000a9e8  mov     [rdi], ebx
0x14000a9ea  mov     rcx, [rsp+68h+var_10]
0x14000a9ef  xor     rcx, rsp; StackCookie
0x14000a9f2  call    __security_check_cookie
0x14000a9f7  mov     rbx, [rsp+68h+arg_8]
0x14000a9fc  add     rsp, 60h
0x14000aa00  pop     rdi
0x14000aa01  retn
```
