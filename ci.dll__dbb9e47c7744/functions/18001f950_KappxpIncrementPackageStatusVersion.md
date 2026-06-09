# KappxpIncrementPackageStatusVersion

- ea: `0x18001f950`
- end: `0x18001fb77`
- name: `KappxpIncrementPackageStatusVersion`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020310`

## callees

- `0x18001f950`
- `0x18002bf20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001f9b7`
- `ntoskrnl!ExAllocatePool2` at `0x18001f9b7`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fad1`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fb4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fb4e`
- `ntoskrnl!ZwClose` at `0x18001fb3a`
- `ntoskrnl!ZwClose` at `0x18001fb3a`
- `ntoskrnl!ZwSetValueKey` at `0x18001fb21`
- `ntoskrnl!ZwSetValueKey` at `0x18001fb21`
- `ntoskrnl!ZwOpenKey` at `0x18001fa9b`
- `ntoskrnl!ZwOpenKey` at `0x18001fa9b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001f9ff`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001f9ff`

## string_xrefs

- `0x18001f9e1`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x18001f9ec`: `TargetNtPath`

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
0x18001f950  push    rbp
0x18001f952  push    rbx
0x18001f953  push    rsi
0x18001f954  push    rdi
0x18001f955  push    r14
0x18001f957  lea     rbp, [rsp-37h]
0x18001f95c  sub     rsp, 0C0h
0x18001f963  mov     rax, cs:__security_cookie
0x18001f96a  xor     rax, rsp
0x18001f96d  mov     [rbp+57h+var_28], rax
0x18001f971  xorps   xmm0, xmm0
0x18001f974  mov     qword ptr [rbp+57h+ValueName.Length], 1E001Ch
0x18001f97c  xor     esi, esi
0x18001f97e  xor     eax, eax
0x18001f980  lea     rax, aPackageversion; "PackageVersion"
0x18001f987  mov     [rbp+57h+KeyHandle], rsi
0x18001f98b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001f98f  mov     ebx, 20Ah
0x18001f994  mov     [rbp+57h+ValueName.Buffer], rax
0x18001f998  mov     r8d, 58707041h
0x18001f99e  mov     [rbp+57h+var_A0], esi
0x18001f9a1  mov     edx, ebx
0x18001f9a3  mov     [rbp+57h+Data], esi
0x18001f9a6  mov     ecx, 100h
0x18001f9ab  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001f9af  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001f9b3  movups  [rbp+57h+var_90], xmm0
0x18001f9b7  call    cs:__imp_ExAllocatePool2
0x18001f9be  nop     dword ptr [rax+rax+00h]
0x18001f9c3  mov     rdi, rax
0x18001f9c6  test    rax, rax
0x18001f9c9  jnz     short loc_18001F9D5
0x18001f9cb  mov     eax, 0C0000017h
0x18001f9d0  jmp     loc_18001FB5C
0x18001f9d5  lea     rax, [rbp+57h+var_A0]
0x18001f9d9  xor     r9d, r9d
0x18001f9dc  mov     [rsp+0E0h+var_B0], rax
0x18001f9e1  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x18001f9e8  mov     dword ptr [rsp+0E0h+ResultLength], ebx
0x18001f9ec  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001f9f3  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001f9fa  mov     qword ptr [rsp+0E0h+Length], rdi
0x18001f9ff  call    cs:__imp_RtlGetPersistedStateLocation
0x18001fa06  nop     dword ptr [rax+rax+00h]
0x18001fa0b  mov     ebx, eax
0x18001fa0d  test    eax, eax
0x18001fa0f  js      loc_18001FB46
0x18001fa15  xorps   xmm0, xmm0
0x18001fa18  mov     ecx, 7FFFh
0x18001fa1d  movups  [rbp+57h+var_90], xmm0
0x18001fa21  mov     rax, rdi
0x18001fa24  mov     r14d, 2
0x18001fa2a  cmp     [rax], si
0x18001fa2d  jz      short loc_18001FA38
0x18001fa2f  add     rax, r14
0x18001fa32  sub     rcx, 1
0x18001fa36  jnz     short loc_18001FA2A
0x18001fa38  mov     rax, rcx
0x18001fa3b  neg     rax
0x18001fa3e  sbb     ebx, ebx
0x18001fa40  not     ebx
0x18001fa42  and     ebx, 0C000000Dh
0x18001fa48  test    rcx, rcx
0x18001fa4b  jz      loc_18001FB46
0x18001fa51  add     cx, cx
0x18001fa54  mov     qword ptr [rbp+57h+var_90+8], rdi
0x18001fa58  mov     eax, 0FFFEh
0x18001fa5d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001fa64  sub     ax, cx
0x18001fa67  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18001fa6b  mov     word ptr [rbp+57h+var_90], ax
0x18001fa6f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001fa73  add     ax, r14w
0x18001fa77  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18001fa7e  mov     word ptr [rbp+57h+var_90+2], ax
0x18001fa82  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fa86  lea     rax, [rbp+57h+var_90]
0x18001fa8a  xorps   xmm0, xmm0
0x18001fa8d  mov     edx, 2001Fh; DesiredAccess
0x18001fa92  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001fa96  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001fa9b  call    cs:__imp_ZwOpenKey
0x18001faa2  nop     dword ptr [rax+rax+00h]
0x18001faa7  mov     ebx, eax
0x18001faa9  test    eax, eax
0x18001faab  js      loc_18001FB46
0x18001fab1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fab5  lea     rax, [rbp+57h+var_A0]
0x18001fab9  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18001fabe  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001fac2  mov     r8d, r14d; KeyValueInformationClass
0x18001fac5  mov     [rsp+0E0h+Length], 14h; Length
0x18001facd  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fad1  call    cs:__imp_ZwQueryValueKey
0x18001fad8  nop     dword ptr [rax+rax+00h]
0x18001fadd  mov     ebx, eax
0x18001fadf  mov     r9d, 4; Type
0x18001fae5  cmp     eax, 0C0000034h
0x18001faea  jnz     short loc_18001FAF0
0x18001faec  mov     eax, esi
0x18001faee  jmp     short loc_18001FB03
0x18001faf0  test    eax, eax
0x18001faf2  js      short loc_18001FB36
0x18001faf4  cmp     [rbp+57h+var_3C], r9d
0x18001faf8  jnz     short loc_18001FB31
0x18001fafa  cmp     [rbp+57h+var_38], r9d
0x18001fafe  jb      short loc_18001FB31
0x18001fb00  mov     eax, [rbp+57h+var_34]
0x18001fb03  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb07  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fb0b  inc     eax
0x18001fb0d  mov     dword ptr [rsp+0E0h+ResultLength], r9d; DataSize
0x18001fb12  mov     [rbp+57h+Data], eax
0x18001fb15  xor     r8d, r8d; TitleIndex
0x18001fb18  lea     rax, [rbp+57h+Data]
0x18001fb1c  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x18001fb21  call    cs:__imp_ZwSetValueKey
0x18001fb28  nop     dword ptr [rax+rax+00h]
0x18001fb2d  mov     ebx, eax
0x18001fb2f  jmp     short loc_18001FB36
0x18001fb31  mov     ebx, 0C000090Bh
0x18001fb36  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001fb3a  call    cs:__imp_ZwClose
0x18001fb41  nop     dword ptr [rax+rax+00h]
0x18001fb46  mov     edx, 58707041h; Tag
0x18001fb4b  mov     rcx, rdi; P
0x18001fb4e  call    cs:__imp_ExFreePoolWithTag
0x18001fb55  nop     dword ptr [rax+rax+00h]
0x18001fb5a  mov     eax, ebx
0x18001fb5c  mov     rcx, [rbp+57h+var_28]
0x18001fb60  xor     rcx, rsp; StackCookie
0x18001fb63  call    __security_check_cookie
0x18001fb68  add     rsp, 0C0h
0x18001fb6f  pop     r14
0x18001fb71  pop     rdi
0x18001fb72  pop     rsi
0x18001fb73  pop     rbx
0x18001fb74  pop     rbp
0x18001fb75  retn
```
