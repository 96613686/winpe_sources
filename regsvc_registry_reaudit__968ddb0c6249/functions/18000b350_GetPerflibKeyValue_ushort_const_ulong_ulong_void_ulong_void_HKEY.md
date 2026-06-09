# GetPerflibKeyValue(ushort const *,ulong,ulong,void *,ulong,void *,HKEY__ * *)

- ea: `0x18000b350`
- end: `0x18000b500`
- name: `?GetPerflibKeyValue@@YAJPEBGKKPEAXK1PEAPEAUHKEY__@@@Z`
- size: `432`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, void *@<r9>, unsigned int, void *, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f640`

## callees

- `0x180005da0`
- `0x180008050`
- `0x18000b350`
- `0x18001e431`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000b454`
- `ntdll!NtQueryValueKey` at `0x18000b454`
- `ntdll!NtOpenKey` at `0x18000b407`
- `ntdll!NtOpenKey` at `0x18000b407`
- `ntdll!RtlInitUnicodeString` at `0x18000b3c1`
- `ntdll!RtlInitUnicodeString` at `0x18000b3ce`
- `ntdll!RtlInitUnicodeString` at `0x18000b3c1`
- `ntdll!RtlInitUnicodeString` at `0x18000b3ce`
- `ntdll!NtClose` at `0x18000b4c2`
- `ntdll!NtClose` at `0x18000b4c2`

## string_xrefs

- `0x18000b3b6`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
__int64 __fastcall GetPerflibKeyValue(
        PCWSTR SourceString,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int a5,
        _DWORD *a6,
        HKEY *a7)
{
  HKEY *v7; // r14
  ULONG Length; // esi
  unsigned int v11; // edi
  int v12; // r15d
  _DWORD *v13; // rbx
  NTSTATUS v14; // eax
  void *KeyHandle; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  ULONG ResultLength; // [rsp+D8h] [rbp+5Fh] BYREF

  v7 = a7;
  ResultLength = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  if ( !a7 || (KeyHandle = *a7) == 0 )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    RtlInitUnicodeString(&ValueName, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
      goto LABEL_20;
  }
  Length = 1024;
  v11 = 0;
  ResultLength = 1024;
  v12 = 1;
  v13 = (_DWORD *)operator new(1024);
  if ( v13 )
  {
    while ( 1 )
    {
      v14 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v13, Length, &ResultLength);
      v11 = v14;
      if ( v14 != -2147483643 )
        break;
      operator delete(v13);
      v13 = (_DWORD *)operator new(ResultLength);
      if ( !v13 )
      {
        v11 = -1073741801;
        goto LABEL_14;
      }
      Length = ResultLength;
    }
    if ( v14 >= 0 )
    {
      if ( v13[1] == 4 && v13[2] <= 4u )
      {
        memcpy_0(a4, v13 + 3, (unsigned int)v13[2]);
        v12 = 0;
      }
      v11 = 0;
    }
LABEL_14:
    if ( v13 )
      operator delete(v13);
  }
  if ( v7 )
    *v7 = (HKEY)KeyHandle;
  else
    NtClose(KeyHandle);
  if ( v12 )
  {
LABEL_20:
    v11 = 0;
    *a4 = *a6;
  }
  return v11;
}

```

## disassembly

```asm
0x18000b350  mov     rax, rsp
0x18000b353  mov     [rax+8], rbx
0x18000b357  mov     [rax+10h], rsi
0x18000b35b  mov     [rax+18h], r8d
0x18000b35f  push    rbp
0x18000b360  push    rdi
0x18000b361  push    r12
0x18000b363  push    r14
0x18000b365  push    r15
0x18000b367  lea     rbp, [rax-47h]
0x18000b36b  sub     rsp, 90h
0x18000b372  mov     r14, [rbp+3Fh+arg_30]
0x18000b376  xorps   xmm0, xmm0
0x18000b379  mov     [rbp+3Fh+arg_10], 0
0x18000b380  xorps   xmm1, xmm1
0x18000b383  mov     [rbp+3Fh+KeyHandle], 0
0x18000b38b  mov     r12, r9
0x18000b38e  mov     rbx, rcx
0x18000b391  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x18000b395  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x18000b399  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b39d  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18000b3a1  movups  xmmword ptr [rbp+3Fh+ValueName.Length], xmm1
0x18000b3a5  test    r14, r14
0x18000b3a8  jz      short loc_18000B3B6
0x18000b3aa  mov     rax, [r14]
0x18000b3ad  mov     [rbp+3Fh+KeyHandle], rax
0x18000b3b1  test    rax, rax
0x18000b3b4  jnz     short loc_18000B415
0x18000b3b6  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18000b3bd  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18000b3c1  call    cs:__imp_RtlInitUnicodeString
0x18000b3c7  mov     rdx, rbx; SourceString
0x18000b3ca  lea     rcx, [rbp+3Fh+ValueName]; DestinationString
0x18000b3ce  call    cs:__imp_RtlInitUnicodeString
0x18000b3d4  lea     rax, [rbp+3Fh+DestinationString]
0x18000b3d8  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18000b3df  xorps   xmm0, xmm0
0x18000b3e2  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x18000b3e6  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18000b3ea  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], 0
0x18000b3f2  mov     edx, 20019h; DesiredAccess
0x18000b3f7  mov     [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18000b3fe  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x18000b402  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b407  call    cs:__imp_NtOpenKey
0x18000b40d  test    eax, eax
0x18000b40f  js      loc_18000B4D6
0x18000b415  mov     esi, 400h
0x18000b41a  xor     edi, edi
0x18000b41c  mov     ecx, esi
0x18000b41e  mov     [rbp+3Fh+arg_10], esi
0x18000b421  lea     r15d, [rdi+1]
0x18000b425  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000b42a  mov     rbx, rax
0x18000b42d  test    rax, rax
0x18000b430  jz      loc_18000B4B9
0x18000b436  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x18000b43a  lea     rax, [rbp+3Fh+arg_10]
0x18000b43e  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x18000b443  lea     rdx, [rbp+3Fh+ValueName]; ValueName
0x18000b447  mov     r9, rbx; KeyValueInformation
0x18000b44a  mov     [rsp+0B0h+Length], esi; Length
0x18000b44e  mov     r8d, 2; KeyValueInformationClass
0x18000b454  call    cs:__imp_NtQueryValueKey
0x18000b45a  mov     edi, eax
0x18000b45c  cmp     eax, 80000005h
0x18000b461  jnz     short loc_18000B487
0x18000b463  mov     rcx, rbx; Block
0x18000b466  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b46b  mov     ecx, [rbp+3Fh+arg_10]
0x18000b46e  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000b473  mov     rbx, rax
0x18000b476  test    rax, rax
0x18000b479  jz      short loc_18000B480
0x18000b47b  mov     esi, [rbp+3Fh+arg_10]
0x18000b47e  jmp     short loc_18000B436
0x18000b480  mov     edi, 0C0000017h
0x18000b485  jmp     short loc_18000B4AC
0x18000b487  test    eax, eax
0x18000b489  js      short loc_18000B4AC
0x18000b48b  cmp     dword ptr [rbx+4], 4
0x18000b48f  jnz     short loc_18000B4AA
0x18000b491  cmp     dword ptr [rbx+8], 4
0x18000b495  ja      short loc_18000B4AA
0x18000b497  mov     r8d, [rbx+8]; Size
0x18000b49b  lea     rdx, [rbx+0Ch]; Src
0x18000b49f  mov     rcx, r12; void *
0x18000b4a2  call    memcpy_0
0x18000b4a7  xor     r15d, r15d
0x18000b4aa  xor     edi, edi
0x18000b4ac  test    rbx, rbx
0x18000b4af  jz      short loc_18000B4B9
0x18000b4b1  mov     rcx, rbx; Block
0x18000b4b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b4b9  test    r14, r14
0x18000b4bc  jnz     short loc_18000B4CA
0x18000b4be  mov     rcx, [rbp+3Fh+KeyHandle]; Handle
0x18000b4c2  call    cs:__imp_NtClose
0x18000b4c8  jmp     short loc_18000B4D1
0x18000b4ca  mov     rax, [rbp+3Fh+KeyHandle]
0x18000b4ce  mov     [r14], rax
0x18000b4d1  test    r15d, r15d
0x18000b4d4  jz      short loc_18000B4E2
0x18000b4d6  mov     rax, [rbp+3Fh+arg_28]
0x18000b4da  xor     edi, edi
0x18000b4dc  mov     ecx, [rax]
0x18000b4de  mov     [r12], ecx
0x18000b4e2  lea     r11, [rsp+0B0h+var_20]
0x18000b4ea  mov     eax, edi
0x18000b4ec  mov     rbx, [r11+30h]
0x18000b4f0  mov     rsi, [r11+38h]
0x18000b4f4  mov     rsp, r11
0x18000b4f7  pop     r15
0x18000b4f9  pop     r14
0x18000b4fb  pop     r12
0x18000b4fd  pop     rdi
0x18000b4fe  pop     rbp
0x18000b4ff  retn
```
