# KappxpIncrementPackageStatusVersion

- ea: `0x18001f9e0`
- end: `0x18001fc07`
- name: `KappxpIncrementPackageStatusVersion`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800203a0`

## callees

- `0x18001f9e0`
- `0x18002bef0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001fa47`
- `ntoskrnl!ExAllocatePool2` at `0x18001fa47`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fb61`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fbde`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fbde`
- `ntoskrnl!ZwClose` at `0x18001fbca`
- `ntoskrnl!ZwClose` at `0x18001fbca`
- `ntoskrnl!ZwSetValueKey` at `0x18001fbb1`
- `ntoskrnl!ZwSetValueKey` at `0x18001fbb1`
- `ntoskrnl!ZwOpenKey` at `0x18001fb2b`
- `ntoskrnl!ZwOpenKey` at `0x18001fb2b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001fa8f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001fa8f`

## string_xrefs

- `0x18001fa7c`: `TargetNtPath`
- `0x18001fa71`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`

## pseudocode

```c
__int64 KappxpIncrementPackageStatusVersion()
{
  _WORD *Pool2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  __int64 v3; // rcx
  _WORD *v4; // rax
  NTSTATUS v5; // eax
  int v6; // eax
  ULONG ResultLength; // [rsp+40h] [rbp-49h] BYREF
  int Data; // [rsp+44h] [rbp-45h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  __int128 v10; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp+17h] BYREF
  int v14; // [rsp+A4h] [rbp+1Bh]
  unsigned int v15; // [rsp+A8h] [rbp+1Fh]
  int v16; // [rsp+ACh] [rbp+23h]

  *(_QWORD *)&ValueName.Length = 1966108;
  KeyHandle = 0;
  ValueName.Buffer = L"PackageVersion";
  ResultLength = 0;
  Data = 0;
  memset(&ObjectAttributes, 0, 44);
  v10 = 0;
  Pool2 = (_WORD *)ExAllocatePool2(256, 522, 1483763777);
  if ( !Pool2 )
    return 3221225495LL;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"AppxStateChange",
                             L"TargetNtPath",
                             L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateChange",
                             0,
                             Pool2,
                             522,
                             &ResultLength);
  if ( PersistedStateLocation >= 0 )
  {
    v3 = 0x7FFF;
    v10 = 0;
    v4 = Pool2;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v3;
    }
    while ( v3 );
    PersistedStateLocation = v3 == 0 ? 0xC000000D : 0;
    if ( v3 )
    {
      *((_QWORD *)&v10 + 1) = Pool2;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      LOWORD(v10) = -2 - 2 * v3;
      ObjectAttributes.Attributes = 576;
      WORD1(v10) = -2 * v3;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v10;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      PersistedStateLocation = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
      if ( PersistedStateLocation >= 0 )
      {
        v5 = ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x14u,
               &ResultLength);
        PersistedStateLocation = v5;
        if ( v5 == -1073741772 )
        {
          v6 = 0;
        }
        else
        {
          if ( v5 < 0 )
          {
LABEL_17:
            ZwClose(KeyHandle);
            goto LABEL_18;
          }
          if ( v14 != 4 || v15 < 4 )
          {
            PersistedStateLocation = -1073739509;
            goto LABEL_17;
          }
          v6 = v16;
        }
        Data = v6 + 1;
        PersistedStateLocation = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
        goto LABEL_17;
      }
    }
  }
LABEL_18:
  ExFreePoolWithTag(Pool2, 0x58707041u);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18001f9e0  push    rbp
0x18001f9e2  push    rbx
0x18001f9e3  push    rsi
0x18001f9e4  push    rdi
0x18001f9e5  push    r14
0x18001f9e7  lea     rbp, [rsp-37h]
0x18001f9ec  sub     rsp, 0C0h
0x18001f9f3  mov     rax, cs:__security_cookie
0x18001f9fa  xor     rax, rsp
0x18001f9fd  mov     [rbp+57h+var_28], rax
0x18001fa01  xorps   xmm0, xmm0
0x18001fa04  mov     qword ptr [rbp+57h+ValueName.Length], 1E001Ch
0x18001fa0c  xor     esi, esi
0x18001fa0e  xor     eax, eax
0x18001fa10  lea     rax, aPackageversion; "PackageVersion"
0x18001fa17  mov     [rbp+57h+KeyHandle], rsi
0x18001fa1b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001fa1f  mov     ebx, 20Ah
0x18001fa24  mov     [rbp+57h+ValueName.Buffer], rax
0x18001fa28  mov     r8d, 58707041h
0x18001fa2e  mov     [rbp+57h+var_A0], esi
0x18001fa31  mov     edx, ebx
0x18001fa33  mov     [rbp+57h+Data], esi
0x18001fa36  mov     ecx, 100h
0x18001fa3b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001fa3f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001fa43  movups  [rbp+57h+var_90], xmm0
0x18001fa47  call    cs:__imp_ExAllocatePool2
0x18001fa4e  nop     dword ptr [rax+rax+00h]
0x18001fa53  mov     rdi, rax
0x18001fa56  test    rax, rax
0x18001fa59  jnz     short loc_18001FA65
0x18001fa5b  mov     eax, 0C0000017h
0x18001fa60  jmp     loc_18001FBEC
0x18001fa65  lea     rax, [rbp+57h+var_A0]
0x18001fa69  xor     r9d, r9d
0x18001fa6c  mov     [rsp+0E0h+var_B0], rax
0x18001fa71  lea     r8, aRegistryMachin_21; "\\Registry\\Machine\\Software\\Microsof"...
0x18001fa78  mov     dword ptr [rsp+0E0h+ResultLength], ebx
0x18001fa7c  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001fa83  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001fa8a  mov     qword ptr [rsp+0E0h+Length], rdi
0x18001fa8f  call    cs:__imp_RtlGetPersistedStateLocation
0x18001fa96  nop     dword ptr [rax+rax+00h]
0x18001fa9b  mov     ebx, eax
0x18001fa9d  test    eax, eax
0x18001fa9f  js      loc_18001FBD6
0x18001faa5  xorps   xmm0, xmm0
0x18001faa8  mov     ecx, 7FFFh
0x18001faad  movups  [rbp+57h+var_90], xmm0
0x18001fab1  mov     rax, rdi
0x18001fab4  mov     r14d, 2
0x18001faba  cmp     [rax], si
0x18001fabd  jz      short loc_18001FAC8
0x18001fabf  add     rax, r14
0x18001fac2  sub     rcx, 1
0x18001fac6  jnz     short loc_18001FABA
0x18001fac8  mov     rax, rcx
0x18001facb  neg     rax
0x18001face  sbb     ebx, ebx
0x18001fad0  not     ebx
0x18001fad2  and     ebx, 0C000000Dh
0x18001fad8  test    rcx, rcx
0x18001fadb  jz      loc_18001FBD6
0x18001fae1  add     cx, cx
0x18001fae4  mov     qword ptr [rbp+57h+var_90+8], rdi
0x18001fae8  mov     eax, 0FFFEh
0x18001faed  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001faf4  sub     ax, cx
0x18001faf7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18001fafb  mov     word ptr [rbp+57h+var_90], ax
0x18001faff  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001fb03  add     ax, r14w
0x18001fb07  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18001fb0e  mov     word ptr [rbp+57h+var_90+2], ax
0x18001fb12  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb16  lea     rax, [rbp+57h+var_90]
0x18001fb1a  xorps   xmm0, xmm0
0x18001fb1d  mov     edx, 2001Fh; DesiredAccess
0x18001fb22  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001fb26  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001fb2b  call    cs:__imp_ZwOpenKey
0x18001fb32  nop     dword ptr [rax+rax+00h]
0x18001fb37  mov     ebx, eax
0x18001fb39  test    eax, eax
0x18001fb3b  js      loc_18001FBD6
0x18001fb41  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb45  lea     rax, [rbp+57h+var_A0]
0x18001fb49  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18001fb4e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001fb52  mov     r8d, r14d; KeyValueInformationClass
0x18001fb55  mov     [rsp+0E0h+Length], 14h; Length
0x18001fb5d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fb61  call    cs:__imp_ZwQueryValueKey
0x18001fb68  nop     dword ptr [rax+rax+00h]
0x18001fb6d  mov     ebx, eax
0x18001fb6f  mov     r9d, 4; Type
0x18001fb75  cmp     eax, 0C0000034h
0x18001fb7a  jnz     short loc_18001FB80
0x18001fb7c  mov     eax, esi
0x18001fb7e  jmp     short loc_18001FB93
0x18001fb80  test    eax, eax
0x18001fb82  js      short loc_18001FBC6
0x18001fb84  cmp     [rbp+57h+var_3C], r9d
0x18001fb88  jnz     short loc_18001FBC1
0x18001fb8a  cmp     [rbp+57h+var_38], r9d
0x18001fb8e  jb      short loc_18001FBC1
0x18001fb90  mov     eax, [rbp+57h+var_34]
0x18001fb93  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb97  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fb9b  inc     eax
0x18001fb9d  mov     dword ptr [rsp+0E0h+ResultLength], r9d; DataSize
0x18001fba2  mov     [rbp+57h+Data], eax
0x18001fba5  xor     r8d, r8d; TitleIndex
0x18001fba8  lea     rax, [rbp+57h+Data]
0x18001fbac  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x18001fbb1  call    cs:__imp_ZwSetValueKey
0x18001fbb8  nop     dword ptr [rax+rax+00h]
0x18001fbbd  mov     ebx, eax
0x18001fbbf  jmp     short loc_18001FBC6
0x18001fbc1  mov     ebx, 0C000090Bh
0x18001fbc6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001fbca  call    cs:__imp_ZwClose
0x18001fbd1  nop     dword ptr [rax+rax+00h]
0x18001fbd6  mov     edx, 58707041h; Tag
0x18001fbdb  mov     rcx, rdi; P
0x18001fbde  call    cs:__imp_ExFreePoolWithTag
0x18001fbe5  nop     dword ptr [rax+rax+00h]
0x18001fbea  mov     eax, ebx
0x18001fbec  mov     rcx, [rbp+57h+var_28]
0x18001fbf0  xor     rcx, rsp; StackCookie
0x18001fbf3  call    __security_check_cookie
0x18001fbf8  add     rsp, 0C0h
0x18001fbff  pop     r14
0x18001fc01  pop     rdi
0x18001fc02  pop     rsi
0x18001fc03  pop     rbx
0x18001fc04  pop     rbp
0x18001fc05  retn
```
