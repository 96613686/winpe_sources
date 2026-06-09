# RfsRegQueryValue

- ea: `0x140086128`
- end: `0x1400862f4`
- name: `RfsRegQueryValue`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140086014`

## callees

- `0x140059f00`
- `0x140086128`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140086200`
- `ntoskrnl!ZwQueryValueKey` at `0x140086266`
- `ntoskrnl!ZwQueryValueKey` at `0x140086200`
- `ntoskrnl!ZwQueryValueKey` at `0x140086266`
- `ntoskrnl!ZwOpenKey` at `0x1400861ca`
- `ntoskrnl!ZwOpenKey` at `0x1400861ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086178`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008618b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086178`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008618b`
- `ntoskrnl!ExAllocatePool2` at `0x140086227`
- `ntoskrnl!ExAllocatePool2` at `0x140086227`
- `ntoskrnl!ZwClose` at `0x1400862d2`
- `ntoskrnl!ZwClose` at `0x1400862d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400862bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400862bd`

## string_xrefs

- `0x14008615b`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

## pseudocode

```c
__int64 __fastcall RfsRegQueryValue(__int64 a1, const WCHAR *a2, __int64 a3, void *a4, ULONG *a5)
{
  NTSTATUS v7; // ebx
  _DWORD *Pool2; // rdi
  ULONG v9; // eax
  ULONG *v10; // rbx
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  ValueName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkstation\\Parameters");
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
    if ( v7 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(258, ResultLength, 1383294546);
      if ( Pool2 )
      {
        v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
        if ( v7 >= 0 )
        {
          if ( Pool2[1] == 1 )
          {
            v9 = Pool2[3];
            v10 = a5;
            ResultLength = v9;
            if ( v9 <= *a5 )
            {
              memmove(a4, (char *)Pool2 + (unsigned int)Pool2[2], (unsigned int)Pool2[3]);
              *v10 = Pool2[3];
              v7 = 0;
            }
            else
            {
              *a5 = v9;
              v7 = -1073741789;
            }
          }
          else
          {
            v7 = -1073741788;
          }
        }
        ExFreePoolWithTag(Pool2, 0x52736652u);
      }
      else
      {
        v7 = -1073741670;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140086128  mov     [rsp-18h+arg_8], rbx
0x14008612d  mov     [rsp-18h+arg_10], r8d
0x140086132  mov     [rsp-18h+KeyHandle], rcx
0x140086137  push    rbp
0x140086138  push    rsi
0x140086139  push    rdi
0x14008613a  mov     rbp, rsp
0x14008613d  sub     rsp, 80h
0x140086144  xorps   xmm0, xmm0
0x140086147  lea     rcx, [rbp+DestinationString]; DestinationString
0x14008614b  xor     eax, eax
0x14008614d  mov     rbx, rdx
0x140086150  xorps   xmm1, xmm1
0x140086153  mov     [rbp+KeyHandle], rax
0x140086157  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008615b  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x140086162  mov     [rbp+arg_10], eax
0x140086165  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140086169  mov     rsi, r9
0x14008616c  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140086170  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140086174  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140086178  call    cs:__imp_RtlInitUnicodeString
0x14008617f  nop     dword ptr [rax+rax+00h]
0x140086184  mov     rdx, rbx; SourceString
0x140086187  lea     rcx, [rbp+ValueName]; DestinationString
0x14008618b  call    cs:__imp_RtlInitUnicodeString
0x140086192  nop     dword ptr [rax+rax+00h]
0x140086197  lea     rax, [rbp+DestinationString]
0x14008619b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400861a2  xorps   xmm0, xmm0
0x1400861a5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400861a9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400861ad  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400861b5  mov     edx, 1; DesiredAccess
0x1400861ba  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400861c1  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400861c5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400861ca  call    cs:__imp_ZwOpenKey
0x1400861d1  nop     dword ptr [rax+rax+00h]
0x1400861d6  mov     ebx, eax
0x1400861d8  test    eax, eax
0x1400861da  js      loc_1400862C9
0x1400861e0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400861e4  lea     rax, [rbp+arg_10]
0x1400861e8  xor     r9d, r9d; KeyValueInformation
0x1400861eb  mov     [rsp+80h+ResultLength], rax; ResultLength
0x1400861f0  lea     rdx, [rbp+ValueName]; ValueName
0x1400861f4  mov     [rsp+80h+Length], 0; Length
0x1400861fc  lea     r8d, [r9+1]; KeyValueInformationClass
0x140086200  call    cs:__imp_ZwQueryValueKey
0x140086207  nop     dword ptr [rax+rax+00h]
0x14008620c  mov     ebx, eax
0x14008620e  cmp     eax, 0C0000023h
0x140086213  jnz     loc_1400862C9
0x140086219  mov     edx, [rbp+arg_10]
0x14008621c  mov     ecx, 102h
0x140086221  mov     r8d, 52736652h
0x140086227  call    cs:__imp_ExAllocatePool2
0x14008622e  nop     dword ptr [rax+rax+00h]
0x140086233  mov     rdi, rax
0x140086236  test    rax, rax
0x140086239  jnz     short loc_140086245
0x14008623b  mov     ebx, 0C000009Ah
0x140086240  jmp     loc_1400862C9
0x140086245  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140086249  lea     rax, [rbp+arg_10]
0x14008624d  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140086252  lea     rdx, [rbp+ValueName]; ValueName
0x140086256  mov     eax, [rbp+arg_10]
0x140086259  mov     r9, rdi; KeyValueInformation
0x14008625c  mov     r8d, 1; KeyValueInformationClass
0x140086262  mov     [rsp+80h+Length], eax; Length
0x140086266  call    cs:__imp_ZwQueryValueKey
0x14008626d  nop     dword ptr [rax+rax+00h]
0x140086272  mov     ebx, eax
0x140086274  test    eax, eax
0x140086276  js      short loc_1400862B5
0x140086278  cmp     dword ptr [rdi+4], 1
0x14008627c  jz      short loc_140086285
0x14008627e  mov     ebx, 0C0000024h
0x140086283  jmp     short loc_1400862B5
0x140086285  mov     eax, [rdi+0Ch]
0x140086288  mov     rbx, [rbp+arg_20]
0x14008628c  mov     [rbp+arg_10], eax
0x14008628f  cmp     eax, [rbx]
0x140086291  jbe     short loc_14008629C
0x140086293  mov     [rbx], eax
0x140086295  mov     ebx, 0C0000023h
0x14008629a  jmp     short loc_1400862B5
0x14008629c  mov     edx, [rdi+8]
0x14008629f  mov     rcx, rsi; void *
0x1400862a2  mov     r8d, [rdi+0Ch]; Size
0x1400862a6  add     rdx, rdi; Src
0x1400862a9  call    memmove
0x1400862ae  mov     eax, [rdi+0Ch]
0x1400862b1  mov     [rbx], eax
0x1400862b3  xor     ebx, ebx
0x1400862b5  mov     edx, 52736652h; Tag
0x1400862ba  mov     rcx, rdi; P
0x1400862bd  call    cs:__imp_ExFreePoolWithTag
0x1400862c4  nop     dword ptr [rax+rax+00h]
0x1400862c9  mov     rcx, [rbp+KeyHandle]; Handle
0x1400862cd  test    rcx, rcx
0x1400862d0  jz      short loc_1400862DE
0x1400862d2  call    cs:__imp_ZwClose
0x1400862d9  nop     dword ptr [rax+rax+00h]
0x1400862de  mov     eax, ebx
0x1400862e0  mov     rbx, [rsp+80h+arg_8]
0x1400862e8  add     rsp, 80h
0x1400862ef  pop     rdi
0x1400862f0  pop     rsi
0x1400862f1  pop     rbp
0x1400862f2  retn
```
