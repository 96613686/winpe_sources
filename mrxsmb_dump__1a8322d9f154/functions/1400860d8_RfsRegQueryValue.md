# RfsRegQueryValue

- ea: `0x1400860d8`
- end: `0x1400862a4`
- name: `RfsRegQueryValue`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140085fc4`

## callees

- `0x140059f00`
- `0x1400860d8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400861b0`
- `ntoskrnl!ZwQueryValueKey` at `0x140086216`
- `ntoskrnl!ZwQueryValueKey` at `0x1400861b0`
- `ntoskrnl!ZwQueryValueKey` at `0x140086216`
- `ntoskrnl!ZwOpenKey` at `0x14008617a`
- `ntoskrnl!ZwOpenKey` at `0x14008617a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086128`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008613b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086128`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008613b`
- `ntoskrnl!ExAllocatePool2` at `0x1400861d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400861d7`
- `ntoskrnl!ZwClose` at `0x140086282`
- `ntoskrnl!ZwClose` at `0x140086282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008626d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008626d`

## string_xrefs

- `0x14008610b`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

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
0x1400860d8  mov     [rsp-18h+arg_8], rbx
0x1400860dd  mov     [rsp-18h+arg_10], r8d
0x1400860e2  mov     [rsp-18h+KeyHandle], rcx
0x1400860e7  push    rbp
0x1400860e8  push    rsi
0x1400860e9  push    rdi
0x1400860ea  mov     rbp, rsp
0x1400860ed  sub     rsp, 80h
0x1400860f4  xorps   xmm0, xmm0
0x1400860f7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400860fb  xor     eax, eax
0x1400860fd  mov     rbx, rdx
0x140086100  xorps   xmm1, xmm1
0x140086103  mov     [rbp+KeyHandle], rax
0x140086107  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008610b  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x140086112  mov     [rbp+arg_10], eax
0x140086115  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140086119  mov     rsi, r9
0x14008611c  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140086120  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140086124  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140086128  call    cs:__imp_RtlInitUnicodeString
0x14008612f  nop     dword ptr [rax+rax+00h]
0x140086134  mov     rdx, rbx; SourceString
0x140086137  lea     rcx, [rbp+ValueName]; DestinationString
0x14008613b  call    cs:__imp_RtlInitUnicodeString
0x140086142  nop     dword ptr [rax+rax+00h]
0x140086147  lea     rax, [rbp+DestinationString]
0x14008614b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140086152  xorps   xmm0, xmm0
0x140086155  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140086159  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14008615d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140086165  mov     edx, 1; DesiredAccess
0x14008616a  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140086171  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140086175  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008617a  call    cs:__imp_ZwOpenKey
0x140086181  nop     dword ptr [rax+rax+00h]
0x140086186  mov     ebx, eax
0x140086188  test    eax, eax
0x14008618a  js      loc_140086279
0x140086190  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140086194  lea     rax, [rbp+arg_10]
0x140086198  xor     r9d, r9d; KeyValueInformation
0x14008619b  mov     [rsp+80h+ResultLength], rax; ResultLength
0x1400861a0  lea     rdx, [rbp+ValueName]; ValueName
0x1400861a4  mov     [rsp+80h+Length], 0; Length
0x1400861ac  lea     r8d, [r9+1]; KeyValueInformationClass
0x1400861b0  call    cs:__imp_ZwQueryValueKey
0x1400861b7  nop     dword ptr [rax+rax+00h]
0x1400861bc  mov     ebx, eax
0x1400861be  cmp     eax, 0C0000023h
0x1400861c3  jnz     loc_140086279
0x1400861c9  mov     edx, [rbp+arg_10]
0x1400861cc  mov     ecx, 102h
0x1400861d1  mov     r8d, 52736652h
0x1400861d7  call    cs:__imp_ExAllocatePool2
0x1400861de  nop     dword ptr [rax+rax+00h]
0x1400861e3  mov     rdi, rax
0x1400861e6  test    rax, rax
0x1400861e9  jnz     short loc_1400861F5
0x1400861eb  mov     ebx, 0C000009Ah
0x1400861f0  jmp     loc_140086279
0x1400861f5  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400861f9  lea     rax, [rbp+arg_10]
0x1400861fd  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140086202  lea     rdx, [rbp+ValueName]; ValueName
0x140086206  mov     eax, [rbp+arg_10]
0x140086209  mov     r9, rdi; KeyValueInformation
0x14008620c  mov     r8d, 1; KeyValueInformationClass
0x140086212  mov     [rsp+80h+Length], eax; Length
0x140086216  call    cs:__imp_ZwQueryValueKey
0x14008621d  nop     dword ptr [rax+rax+00h]
0x140086222  mov     ebx, eax
0x140086224  test    eax, eax
0x140086226  js      short loc_140086265
0x140086228  cmp     dword ptr [rdi+4], 1
0x14008622c  jz      short loc_140086235
0x14008622e  mov     ebx, 0C0000024h
0x140086233  jmp     short loc_140086265
0x140086235  mov     eax, [rdi+0Ch]
0x140086238  mov     rbx, [rbp+arg_20]
0x14008623c  mov     [rbp+arg_10], eax
0x14008623f  cmp     eax, [rbx]
0x140086241  jbe     short loc_14008624C
0x140086243  mov     [rbx], eax
0x140086245  mov     ebx, 0C0000023h
0x14008624a  jmp     short loc_140086265
0x14008624c  mov     edx, [rdi+8]
0x14008624f  mov     rcx, rsi; void *
0x140086252  mov     r8d, [rdi+0Ch]; Size
0x140086256  add     rdx, rdi; Src
0x140086259  call    memmove
0x14008625e  mov     eax, [rdi+0Ch]
0x140086261  mov     [rbx], eax
0x140086263  xor     ebx, ebx
0x140086265  mov     edx, 52736652h; Tag
0x14008626a  mov     rcx, rdi; P
0x14008626d  call    cs:__imp_ExFreePoolWithTag
0x140086274  nop     dword ptr [rax+rax+00h]
0x140086279  mov     rcx, [rbp+KeyHandle]; Handle
0x14008627d  test    rcx, rcx
0x140086280  jz      short loc_14008628E
0x140086282  call    cs:__imp_ZwClose
0x140086289  nop     dword ptr [rax+rax+00h]
0x14008628e  mov     eax, ebx
0x140086290  mov     rbx, [rsp+80h+arg_8]
0x140086298  add     rsp, 80h
0x14008629f  pop     rdi
0x1400862a0  pop     rsi
0x1400862a1  pop     rbp
0x1400862a2  retn
```
