# GetNameFromValue

- ea: `0x18003d8e0`
- end: `0x18003da6a`
- name: `GetNameFromValue`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180039820`

## callees

- `0x18003d8e0`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18003d9bf`
- `ntdll!NtQueryValueKey` at `0x18003d9bf`
- `ntdll!NtOpenKey` at `0x18003d97b`
- `ntdll!NtOpenKey` at `0x18003d97b`
- `ntdll!NtClose` at `0x18003d9cc`
- `ntdll!NtClose` at `0x18003d9cc`
- `ntdll!wcslen` at `0x18003da30`
- `ntdll!wcslen` at `0x18003da30`
- `ntdll!RtlInitUnicodeString` at `0x18003d93e`
- `ntdll!RtlInitUnicodeString` at `0x18003d996`
- `ntdll!RtlInitUnicodeString` at `0x18003d93e`
- `ntdll!RtlInitUnicodeString` at `0x18003d996`

## string_xrefs

- `0x18003d98b`: `ComputerName`

## pseudocode

```c
__int64 __fastcall GetNameFromValue(void *a1, const WCHAR *a2, char *a3, int *a4)
{
  NTSTATUS v7; // edi
  unsigned int v8; // ecx
  unsigned int v9; // eax
  __int64 v10; // rbx
  int v11; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v19; // [rsp+98h] [rbp-68h]
  unsigned int v20; // [rsp+9Ch] [rbp-64h]

  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeyHandle = 0;
  DestinationString = 0;
  ResultLength = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  v7 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"ComputerName");
    v7 = NtQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x6Cu, &ResultLength);
    NtClose(KeyHandle);
    if ( v7 >= 0 )
    {
      if ( v20 < 2 )
      {
        return (unsigned int)-1073741772;
      }
      else
      {
        v8 = v20 & 0xFFFFFFFE;
        v20 &= ~1u;
        v9 = v20 - 2;
        if ( *(_WORD *)((char *)&ValueName.Buffer + v19 + (unsigned __int64)v20 + 6) )
          v9 = v8;
        else
          v20 -= 2;
        v10 = v9;
        if ( (unsigned int)*a4 < ((unsigned __int64)v9 >> 1) + 1 )
        {
          v7 = -2147483643;
          v11 = (v9 >> 1) + 1;
        }
        else
        {
          memcpy_0(a3, &KeyValueInformation[v19], v9);
          *(_WORD *)&a3[v10] = 0;
          v11 = wcslen((const wchar_t *)a3);
        }
        *a4 = v11;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003d8e0  push    rbp
0x18003d8e2  push    rbx
0x18003d8e3  push    rsi
0x18003d8e4  push    rdi
0x18003d8e5  push    r14
0x18003d8e7  push    r15
0x18003d8e9  lea     rbp, [rsp-18h]
0x18003d8ee  sub     rsp, 118h
0x18003d8f5  mov     rax, cs:__security_cookie
0x18003d8fc  xor     rax, rsp
0x18003d8ff  mov     [rbp+40h+var_40], rax
0x18003d903  xorps   xmm0, xmm0
0x18003d906  mov     rbx, rcx
0x18003d909  xorps   xmm1, xmm1
0x18003d90c  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x18003d911  xor     r15d, r15d
0x18003d914  xor     eax, eax
0x18003d916  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm0
0x18003d91b  mov     r14, r9
0x18003d91e  mov     rsi, r8
0x18003d921  movups  xmmword ptr [rsp+140h+ObjectAttributes+1Ch], xmm0
0x18003d926  mov     [rsp+140h+KeyHandle], r15
0x18003d92b  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x18003d930  mov     [rsp+140h+var_110], r15d
0x18003d935  movups  xmmword ptr [rbp+40h+ValueName.Length], xmm1
0x18003d939  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x18003d93e  call    cs:__imp_RtlInitUnicodeString
0x18003d944  lea     rax, [rsp+140h+DestinationString]
0x18003d949  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x18003d951  xorps   xmm0, xmm0
0x18003d954  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x18003d959  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x18003d95e  mov     [rsp+140h+ObjectAttributes.RootDirectory], rbx
0x18003d963  mov     edx, 20019h; DesiredAccess
0x18003d968  mov     [rsp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x18003d970  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x18003d975  movdqu  xmmword ptr [rsp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d97b  call    cs:__imp_NtOpenKey
0x18003d981  mov     edi, eax
0x18003d983  test    eax, eax
0x18003d985  js      loc_18003DA39
0x18003d98b  lea     rdx, aComputername; "ComputerName"
0x18003d992  lea     rcx, [rbp+40h+ValueName]; DestinationString
0x18003d996  call    cs:__imp_RtlInitUnicodeString
0x18003d99c  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x18003d9a1  lea     rax, [rsp+140h+var_110]
0x18003d9a6  mov     [rsp+140h+ResultLength], rax; ResultLength
0x18003d9ab  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x18003d9af  lea     r8d, [r15+1]; KeyValueInformationClass
0x18003d9b3  mov     [rsp+140h+Length], 6Ch ; 'l'; Length
0x18003d9bb  lea     rdx, [rbp+40h+ValueName]; ValueName
0x18003d9bf  call    cs:__imp_NtQueryValueKey
0x18003d9c5  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x18003d9ca  mov     edi, eax
0x18003d9cc  call    cs:__imp_NtClose
0x18003d9d2  test    edi, edi
0x18003d9d4  js      short loc_18003DA39
0x18003d9d6  mov     eax, [rbp+40h+var_A4]
0x18003d9d9  cmp     eax, 2
0x18003d9dc  jb      loc_18003DA63
0x18003d9e2  mov     r8d, [rbp+40h+var_A8]
0x18003d9e6  and     eax, 0FFFFFFFEh
0x18003d9e9  mov     ecx, eax
0x18003d9eb  add     rax, r8
0x18003d9ee  mov     [rbp+40h+var_A4], ecx
0x18003d9f1  movzx   edx, word ptr [rbp+rax+40h+ValueName.Buffer+6]
0x18003d9f6  lea     eax, [rcx-2]
0x18003d9f9  test    dx, dx
0x18003d9fc  jnz     short loc_18003DA01
0x18003d9fe  mov     [rbp+40h+var_A4], eax
0x18003da01  cmovnz  eax, ecx
0x18003da04  mov     edx, eax
0x18003da06  shr     rdx, 1
0x18003da09  mov     ebx, eax
0x18003da0b  inc     rdx
0x18003da0e  mov     eax, [r14]
0x18003da11  cmp     rax, rdx
0x18003da14  jb      short loc_18003DA57
0x18003da16  lea     rdx, [rbp+40h+KeyValueInformation]
0x18003da1a  mov     rcx, rsi; void *
0x18003da1d  add     rdx, r8; Src
0x18003da20  mov     r8d, ebx; Size
0x18003da23  call    memcpy_0
0x18003da28  mov     rcx, rsi; String
0x18003da2b  mov     [rbx+rsi], r15w
0x18003da30  call    cs:__imp_wcslen
0x18003da36  mov     [r14], eax
0x18003da39  mov     eax, edi
0x18003da3b  mov     rcx, [rbp+40h+var_40]
0x18003da3f  xor     rcx, rsp; StackCookie
0x18003da42  call    __security_check_cookie
0x18003da47  add     rsp, 118h
0x18003da4e  pop     r15
0x18003da50  pop     r14
0x18003da52  pop     rdi
0x18003da53  pop     rsi
0x18003da54  pop     rbx
0x18003da55  pop     rbp
0x18003da56  retn
0x18003da57  shr     ebx, 1
0x18003da59  mov     edi, 80000005h
0x18003da5e  lea     eax, [rbx+1]
0x18003da61  jmp     short loc_18003DA36
0x18003da63  mov     edi, 0C0000034h
0x18003da68  jmp     short loc_18003DA39
```
