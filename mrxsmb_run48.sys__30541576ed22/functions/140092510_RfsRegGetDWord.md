# RfsRegGetDWord

- ea: `0x140092510`
- end: `0x140092636`
- name: `RfsRegGetDWord`
- size: `294`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `8`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14001e514`
- `0x14003bb78`
- `0x14003bbe8`
- `0x1400440e4`
- `0x140089f90`
- `0x14008a0b0`
- `0x14008a1ec`
- `0x140090130`

## callees

- `0x140059dc0`
- `0x140092510`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14009260c`
- `ntoskrnl!ZwQueryValueKey` at `0x14009260c`
- `ntoskrnl!ZwOpenKey` at `0x1400925b9`
- `ntoskrnl!ZwOpenKey` at `0x1400925b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009256b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009257e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009256b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009257e`
- `ntoskrnl!ZwClose` at `0x14009261e`
- `ntoskrnl!ZwClose` at `0x14009261e`

## pseudocode

```c
NTSTATUS __fastcall RfsRegGetDWord(PCWSTR SourceString, PCWSTR a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp+7h] BYREF
  UNICODE_STRING ValueName; // [rsp+80h] [rbp+17h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+27h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  *a3 = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ValueName = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    ZwClose(KeyHandle);
    if ( v6 >= 0 )
    {
      if ( DWORD1(KeyValueInformation) == 4 )
      {
        if ( DWORD2(KeyValueInformation) >= 4 )
        {
          *a3 = HIDWORD(KeyValueInformation);
          return 0;
        }
        else
        {
          return -1073741789;
        }
      }
      else
      {
        return -1073741788;
      }
    }
    else
    {
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140092510  mov     [rsp-8+arg_18], rbx
0x140092515  push    rbp
0x140092516  push    rsi
0x140092517  push    rdi
0x140092518  lea     rbp, [rsp-47h]
0x14009251d  sub     rsp, 0B0h
0x140092524  mov     rax, cs:__security_cookie
0x14009252b  xor     rax, rsp
0x14009252e  mov     [rbp+57h+var_20], rax
0x140092532  xorps   xmm0, xmm0
0x140092535  xor     esi, esi
0x140092537  mov     rbx, rdx
0x14009253a  mov     [rbp+57h+KeyHandle], rsi
0x14009253e  mov     rdx, rcx; SourceString
0x140092541  mov     [rbp+57h+var_90], esi
0x140092544  xorps   xmm1, xmm1
0x140092547  mov     [r8], esi
0x14009254a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14009254e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140092552  xor     eax, eax
0x140092554  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140092558  mov     rdi, r8
0x14009255b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14009255f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140092563  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140092567  movups  [rbp+57h+KeyValueInformation], xmm0
0x14009256b  call    cs:__imp_RtlInitUnicodeString
0x140092572  nop     dword ptr [rax+rax+00h]
0x140092577  mov     rdx, rbx; SourceString
0x14009257a  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14009257e  call    cs:__imp_RtlInitUnicodeString
0x140092585  nop     dword ptr [rax+rax+00h]
0x14009258a  lea     rax, [rbp+57h+DestinationString]
0x14009258e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140092595  xorps   xmm0, xmm0
0x140092598  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009259c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400925a0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1400925a4  mov     edx, 1; DesiredAccess
0x1400925a9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400925b0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400925b4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400925b9  call    cs:__imp_ZwOpenKey
0x1400925c0  nop     dword ptr [rax+rax+00h]
0x1400925c5  test    eax, eax
0x1400925c7  jns     short loc_1400925E9
0x1400925c9  mov     rcx, [rbp+57h+var_20]
0x1400925cd  xor     rcx, rsp; StackCookie
0x1400925d0  call    __security_check_cookie
0x1400925d5  mov     rbx, [rsp+0C0h+arg_18]
0x1400925dd  add     rsp, 0B0h
0x1400925e4  pop     rdi
0x1400925e5  pop     rsi
0x1400925e6  pop     rbp
0x1400925e7  retn
0x1400925e9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400925ed  lea     rax, [rbp+57h+var_90]
0x1400925f1  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400925f6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400925fa  mov     r8d, 2; KeyValueInformationClass
0x140092600  mov     [rsp+0C0h+Length], 10h; Length
0x140092608  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14009260c  call    cs:__imp_ZwQueryValueKey
0x140092613  nop     dword ptr [rax+rax+00h]
0x140092618  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14009261c  mov     ebx, eax
0x14009261e  call    cs:__imp_ZwClose
0x140092625  nop     dword ptr [rax+rax+00h]
0x14009262a  test    ebx, ebx
0x14009262c  jns     loc_140096448
0x140092632  mov     eax, ebx
0x140092634  jmp     short loc_1400925C9
0x140096448  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14009644c  jz      short loc_140096458
0x14009644e  mov     eax, 0C0000024h
0x140096453  jmp     loc_1400925C9
0x140096458  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14009645c  jnb     short loc_140096468
0x14009645e  mov     eax, 0C0000023h
0x140096463  jmp     loc_1400925C9
0x140096468  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14009646b  mov     [rdi], eax
0x14009646d  xor     eax, eax
0x14009646f  jmp     loc_1400925C9
```
