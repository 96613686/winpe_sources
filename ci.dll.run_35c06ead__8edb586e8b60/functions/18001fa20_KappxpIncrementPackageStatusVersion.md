# KappxpIncrementPackageStatusVersion

- ea: `0x18001fa20`
- end: `0x18001fc47`
- name: `KappxpIncrementPackageStatusVersion`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800203e0`

## callees

- `0x18001fa20`
- `0x18002c0d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001fa87`
- `ntoskrnl!ExAllocatePool2` at `0x18001fa87`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fba1`
- `ntoskrnl!ZwQueryValueKey` at `0x18001fba1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fc1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001fc1e`
- `ntoskrnl!ZwClose` at `0x18001fc0a`
- `ntoskrnl!ZwClose` at `0x18001fc0a`
- `ntoskrnl!ZwSetValueKey` at `0x18001fbf1`
- `ntoskrnl!ZwSetValueKey` at `0x18001fbf1`
- `ntoskrnl!ZwOpenKey` at `0x18001fb6b`
- `ntoskrnl!ZwOpenKey` at `0x18001fb6b`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001facf`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001facf`

## string_xrefs

- `0x18001fab1`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x18001fabc`: `TargetNtPath`

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
0x18001fa20  push    rbp
0x18001fa22  push    rbx
0x18001fa23  push    rsi
0x18001fa24  push    rdi
0x18001fa25  push    r14
0x18001fa27  lea     rbp, [rsp-37h]
0x18001fa2c  sub     rsp, 0C0h
0x18001fa33  mov     rax, cs:__security_cookie
0x18001fa3a  xor     rax, rsp
0x18001fa3d  mov     [rbp+57h+var_28], rax
0x18001fa41  xorps   xmm0, xmm0
0x18001fa44  mov     qword ptr [rbp+57h+ValueName.Length], 1E001Ch
0x18001fa4c  xor     esi, esi
0x18001fa4e  xor     eax, eax
0x18001fa50  lea     rax, aPackageversion; "PackageVersion"
0x18001fa57  mov     [rbp+57h+KeyHandle], rsi
0x18001fa5b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001fa5f  mov     ebx, 20Ah
0x18001fa64  mov     [rbp+57h+ValueName.Buffer], rax
0x18001fa68  mov     r8d, 58707041h
0x18001fa6e  mov     [rbp+57h+var_A0], esi
0x18001fa71  mov     edx, ebx
0x18001fa73  mov     [rbp+57h+Data], esi
0x18001fa76  mov     ecx, 100h
0x18001fa7b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001fa7f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001fa83  movups  [rbp+57h+var_90], xmm0
0x18001fa87  call    cs:__imp_ExAllocatePool2
0x18001fa8e  nop     dword ptr [rax+rax+00h]
0x18001fa93  mov     rdi, rax
0x18001fa96  test    rax, rax
0x18001fa99  jnz     short loc_18001FAA5
0x18001fa9b  mov     eax, 0C0000017h
0x18001faa0  jmp     loc_18001FC2C
0x18001faa5  lea     rax, [rbp+57h+var_A0]
0x18001faa9  xor     r9d, r9d
0x18001faac  mov     [rsp+0E0h+var_B0], rax
0x18001fab1  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x18001fab8  mov     dword ptr [rsp+0E0h+ResultLength], ebx
0x18001fabc  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001fac3  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001faca  mov     qword ptr [rsp+0E0h+Length], rdi
0x18001facf  call    cs:__imp_RtlGetPersistedStateLocation
0x18001fad6  nop     dword ptr [rax+rax+00h]
0x18001fadb  mov     ebx, eax
0x18001fadd  test    eax, eax
0x18001fadf  js      loc_18001FC16
0x18001fae5  xorps   xmm0, xmm0
0x18001fae8  mov     ecx, 7FFFh
0x18001faed  movups  [rbp+57h+var_90], xmm0
0x18001faf1  mov     rax, rdi
0x18001faf4  mov     r14d, 2
0x18001fafa  cmp     [rax], si
0x18001fafd  jz      short loc_18001FB08
0x18001faff  add     rax, r14
0x18001fb02  sub     rcx, 1
0x18001fb06  jnz     short loc_18001FAFA
0x18001fb08  mov     rax, rcx
0x18001fb0b  neg     rax
0x18001fb0e  sbb     ebx, ebx
0x18001fb10  not     ebx
0x18001fb12  and     ebx, 0C000000Dh
0x18001fb18  test    rcx, rcx
0x18001fb1b  jz      loc_18001FC16
0x18001fb21  add     cx, cx
0x18001fb24  mov     qword ptr [rbp+57h+var_90+8], rdi
0x18001fb28  mov     eax, 0FFFEh
0x18001fb2d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001fb34  sub     ax, cx
0x18001fb37  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18001fb3b  mov     word ptr [rbp+57h+var_90], ax
0x18001fb3f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001fb43  add     ax, r14w
0x18001fb47  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18001fb4e  mov     word ptr [rbp+57h+var_90+2], ax
0x18001fb52  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb56  lea     rax, [rbp+57h+var_90]
0x18001fb5a  xorps   xmm0, xmm0
0x18001fb5d  mov     edx, 2001Fh; DesiredAccess
0x18001fb62  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001fb66  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001fb6b  call    cs:__imp_ZwOpenKey
0x18001fb72  nop     dword ptr [rax+rax+00h]
0x18001fb77  mov     ebx, eax
0x18001fb79  test    eax, eax
0x18001fb7b  js      loc_18001FC16
0x18001fb81  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fb85  lea     rax, [rbp+57h+var_A0]
0x18001fb89  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18001fb8e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001fb92  mov     r8d, r14d; KeyValueInformationClass
0x18001fb95  mov     [rsp+0E0h+Length], 14h; Length
0x18001fb9d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fba1  call    cs:__imp_ZwQueryValueKey
0x18001fba8  nop     dword ptr [rax+rax+00h]
0x18001fbad  mov     ebx, eax
0x18001fbaf  mov     r9d, 4; Type
0x18001fbb5  cmp     eax, 0C0000034h
0x18001fbba  jnz     short loc_18001FBC0
0x18001fbbc  mov     eax, esi
0x18001fbbe  jmp     short loc_18001FBD3
0x18001fbc0  test    eax, eax
0x18001fbc2  js      short loc_18001FC06
0x18001fbc4  cmp     [rbp+57h+var_3C], r9d
0x18001fbc8  jnz     short loc_18001FC01
0x18001fbca  cmp     [rbp+57h+var_38], r9d
0x18001fbce  jb      short loc_18001FC01
0x18001fbd0  mov     eax, [rbp+57h+var_34]
0x18001fbd3  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001fbd7  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001fbdb  inc     eax
0x18001fbdd  mov     dword ptr [rsp+0E0h+ResultLength], r9d; DataSize
0x18001fbe2  mov     [rbp+57h+Data], eax
0x18001fbe5  xor     r8d, r8d; TitleIndex
0x18001fbe8  lea     rax, [rbp+57h+Data]
0x18001fbec  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x18001fbf1  call    cs:__imp_ZwSetValueKey
0x18001fbf8  nop     dword ptr [rax+rax+00h]
0x18001fbfd  mov     ebx, eax
0x18001fbff  jmp     short loc_18001FC06
0x18001fc01  mov     ebx, 0C000090Bh
0x18001fc06  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001fc0a  call    cs:__imp_ZwClose
0x18001fc11  nop     dword ptr [rax+rax+00h]
0x18001fc16  mov     edx, 58707041h; Tag
0x18001fc1b  mov     rcx, rdi; P
0x18001fc1e  call    cs:__imp_ExFreePoolWithTag
0x18001fc25  nop     dword ptr [rax+rax+00h]
0x18001fc2a  mov     eax, ebx
0x18001fc2c  mov     rcx, [rbp+57h+var_28]
0x18001fc30  xor     rcx, rsp; StackCookie
0x18001fc33  call    __security_check_cookie
0x18001fc38  add     rsp, 0C0h
0x18001fc3f  pop     r14
0x18001fc41  pop     rdi
0x18001fc42  pop     rsi
0x18001fc43  pop     rbx
0x18001fc44  pop     rbp
0x18001fc45  retn
```
