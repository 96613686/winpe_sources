# RfsRegGetDWord

- ea: `0x1400924c0`
- end: `0x1400925e6`
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
- `0x140089f40`
- `0x14008a060`
- `0x14008a19c`
- `0x1400900e0`

## callees

- `0x140059dc0`
- `0x1400924c0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400925bc`
- `ntoskrnl!ZwQueryValueKey` at `0x1400925bc`
- `ntoskrnl!ZwOpenKey` at `0x140092569`
- `ntoskrnl!ZwOpenKey` at `0x140092569`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009251b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009252e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009251b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009252e`
- `ntoskrnl!ZwClose` at `0x1400925ce`
- `ntoskrnl!ZwClose` at `0x1400925ce`

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
0x1400924c0  mov     [rsp-8+arg_18], rbx
0x1400924c5  push    rbp
0x1400924c6  push    rsi
0x1400924c7  push    rdi
0x1400924c8  lea     rbp, [rsp-47h]
0x1400924cd  sub     rsp, 0B0h
0x1400924d4  mov     rax, cs:__security_cookie
0x1400924db  xor     rax, rsp
0x1400924de  mov     [rbp+57h+var_20], rax
0x1400924e2  xorps   xmm0, xmm0
0x1400924e5  xor     esi, esi
0x1400924e7  mov     rbx, rdx
0x1400924ea  mov     [rbp+57h+KeyHandle], rsi
0x1400924ee  mov     rdx, rcx; SourceString
0x1400924f1  mov     [rbp+57h+var_90], esi
0x1400924f4  xorps   xmm1, xmm1
0x1400924f7  mov     [r8], esi
0x1400924fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400924fe  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140092502  xor     eax, eax
0x140092504  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140092508  mov     rdi, r8
0x14009250b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14009250f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140092513  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140092517  movups  [rbp+57h+KeyValueInformation], xmm0
0x14009251b  call    cs:__imp_RtlInitUnicodeString
0x140092522  nop     dword ptr [rax+rax+00h]
0x140092527  mov     rdx, rbx; SourceString
0x14009252a  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14009252e  call    cs:__imp_RtlInitUnicodeString
0x140092535  nop     dword ptr [rax+rax+00h]
0x14009253a  lea     rax, [rbp+57h+DestinationString]
0x14009253e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140092545  xorps   xmm0, xmm0
0x140092548  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009254c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140092550  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140092554  mov     edx, 1; DesiredAccess
0x140092559  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140092560  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140092564  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140092569  call    cs:__imp_ZwOpenKey
0x140092570  nop     dword ptr [rax+rax+00h]
0x140092575  test    eax, eax
0x140092577  jns     short loc_140092599
0x140092579  mov     rcx, [rbp+57h+var_20]
0x14009257d  xor     rcx, rsp; StackCookie
0x140092580  call    __security_check_cookie
0x140092585  mov     rbx, [rsp+0C0h+arg_18]
0x14009258d  add     rsp, 0B0h
0x140092594  pop     rdi
0x140092595  pop     rsi
0x140092596  pop     rbp
0x140092597  retn
0x140092599  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009259d  lea     rax, [rbp+57h+var_90]
0x1400925a1  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400925a6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400925aa  mov     r8d, 2; KeyValueInformationClass
0x1400925b0  mov     [rsp+0C0h+Length], 10h; Length
0x1400925b8  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400925bc  call    cs:__imp_ZwQueryValueKey
0x1400925c3  nop     dword ptr [rax+rax+00h]
0x1400925c8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400925cc  mov     ebx, eax
0x1400925ce  call    cs:__imp_ZwClose
0x1400925d5  nop     dword ptr [rax+rax+00h]
0x1400925da  test    ebx, ebx
0x1400925dc  jns     loc_1400963F8
0x1400925e2  mov     eax, ebx
0x1400925e4  jmp     short loc_140092579
0x1400963f8  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400963fc  jz      short loc_140096408
0x1400963fe  mov     eax, 0C0000024h
0x140096403  jmp     loc_140092579
0x140096408  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14009640c  jnb     short loc_140096418
0x14009640e  mov     eax, 0C0000023h
0x140096413  jmp     loc_140092579
0x140096418  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14009641b  mov     [rdi], eax
0x14009641d  xor     eax, eax
0x14009641f  jmp     loc_140092579
```
