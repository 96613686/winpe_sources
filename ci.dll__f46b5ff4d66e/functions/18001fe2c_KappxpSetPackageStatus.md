# KappxpSetPackageStatus

- ea: `0x18001fe2c`
- end: `0x18002017c`
- name: `KappxpSetPackageStatus`
- size: `848`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PCWSTR pszSrc@<rcx>, ULONG DataSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800203a0`

## callees

- `0x18000cbe4`
- `0x18001fe2c`
- `0x18002bef0`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18002000f`
- `ntoskrnl!ZwCreateKey` at `0x18002000f`
- `ntoskrnl!ExAllocatePool2` at `0x18001fed6`
- `ntoskrnl!ExAllocatePool2` at `0x18001fed6`
- `ntoskrnl!ZwQueryValueKey` at `0x180020055`
- `ntoskrnl!ZwQueryValueKey` at `0x180020055`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002014d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002014d`
- `ntoskrnl!ZwClose` at `0x180020139`
- `ntoskrnl!ZwClose` at `0x180020139`
- `ntoskrnl!ZwSetValueKey` at `0x1800200bb`
- `ntoskrnl!ZwSetValueKey` at `0x1800200f6`
- `ntoskrnl!ZwSetValueKey` at `0x180020126`
- `ntoskrnl!ZwSetValueKey` at `0x1800200bb`
- `ntoskrnl!ZwSetValueKey` at `0x1800200f6`
- `ntoskrnl!ZwSetValueKey` at `0x180020126`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001ff1f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001ff1f`

## string_xrefs

- `0x18001ff0c`: `TargetNtPath`
- `0x18001ff01`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`

## pseudocode

```c
__int64 __fastcall KappxpSetPackageStatus(NTSTRSAFE_PCWSTR pszSrc, int a2, __int64 a3, void *a4, ULONG DataSize)
{
  wchar_t *Pool2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  __int64 v12; // rcx
  wchar_t *v13; // rax
  NTSTATUS v14; // eax
  int v15; // eax
  void *KeyHandle; // [rsp+40h] [rbp-A1h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-99h] BYREF
  ULONG ResultLength; // [rsp+4Ch] [rbp-95h] BYREF
  int Data; // [rsp+50h] [rbp-91h] BYREF
  __int128 v20; // [rsp+58h] [rbp-89h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-79h] BYREF
  struct _UNICODE_STRING v22; // [rsp+78h] [rbp-69h] BYREF
  struct _UNICODE_STRING v23; // [rsp+88h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-49h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+C8h] [rbp-19h] BYREF
  int v26; // [rsp+CCh] [rbp-15h]
  unsigned int v27; // [rsp+D0h] [rbp-11h]
  int v28; // [rsp+D4h] [rbp-Dh]

  *(_QWORD *)&ValueName.Length = 1835034;
  *(_QWORD *)&v22.Length = 1441812;
  *(_QWORD *)&v23.Length = 1441812;
  KeyHandle = 0;
  ValueName.Buffer = L"PackageStatus";
  Disposition = 0;
  v22.Buffer = L"BinaryName";
  ResultLength = 0;
  v23.Buffer = L"BinaryHash";
  Data = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  Pool2 = (wchar_t *)ExAllocatePool2(256, 522, 1483763777);
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
    PersistedStateLocation = RtlStringCbCatW(Pool2, 0x20Au, L"\\PackageList\\");
    if ( PersistedStateLocation >= 0 )
    {
      PersistedStateLocation = RtlStringCbCatW(Pool2, 0x20Au, pszSrc);
      if ( PersistedStateLocation >= 0 )
      {
        v12 = 0x7FFF;
        v20 = 0;
        v13 = Pool2;
        do
        {
          if ( !*v13 )
            break;
          ++v13;
          --v12;
        }
        while ( v12 );
        PersistedStateLocation = v12 == 0 ? 0xC000000D : 0;
        if ( v12 )
        {
          *((_QWORD *)&v20 + 1) = Pool2;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          LOWORD(v20) = -2 - 2 * v12;
          ObjectAttributes.Attributes = 576;
          WORD1(v20) = -2 * v12;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          PersistedStateLocation = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( PersistedStateLocation >= 0 )
          {
            if ( Disposition == 2 )
            {
              v14 = ZwQueryValueKey(
                      KeyHandle,
                      &ValueName,
                      KeyValuePartialInformation,
                      KeyValueInformation,
                      0x14u,
                      &ResultLength);
              PersistedStateLocation = v14;
              if ( v14 >= 0 )
              {
                if ( v26 == 4 && v27 >= 4 )
                {
                  v15 = v28;
                }
                else
                {
                  v15 = 0;
                  PersistedStateLocation = -1073739509;
                }
                if ( PersistedStateLocation >= 0 )
                {
LABEL_22:
                  Data = v15 | a2;
                  if ( (v15 | a2) != v15 )
                    PersistedStateLocation = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
                }
LABEL_24:
                if ( a4 && PersistedStateLocation >= 0 )
                {
                  PersistedStateLocation = ZwSetValueKey(
                                             KeyHandle,
                                             &v22,
                                             0,
                                             1u,
                                             *(PVOID *)(a3 + 8),
                                             *(unsigned __int16 *)(a3 + 2));
                  if ( PersistedStateLocation >= 0 )
                    PersistedStateLocation = ZwSetValueKey(KeyHandle, &v23, 0, 3u, a4, DataSize);
                }
                ZwClose(KeyHandle);
                goto LABEL_29;
              }
              if ( v14 != -1073741772 )
                goto LABEL_24;
              PersistedStateLocation = 0;
            }
            v15 = 0;
            goto LABEL_22;
          }
        }
      }
    }
  }
LABEL_29:
  ExFreePoolWithTag(Pool2, 0x58707041u);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18001fe2c  push    rbp
0x18001fe2e  push    rbx
0x18001fe2f  push    rsi
0x18001fe30  push    rdi
0x18001fe31  push    r12
0x18001fe33  push    r13
0x18001fe35  push    r14
0x18001fe37  push    r15
0x18001fe39  lea     rbp, [rsp-17h]
0x18001fe3e  sub     rsp, 0F8h
0x18001fe45  mov     rax, cs:__security_cookie
0x18001fe4c  xor     rax, rsp
0x18001fe4f  mov     [rbp+4Fh+var_50], rax
0x18001fe53  xorps   xmm0, xmm0
0x18001fe56  mov     qword ptr [rbp+4Fh+ValueName.Length], 1C001Ah
0x18001fe5e  xor     eax, eax
0x18001fe60  mov     qword ptr [rbp+4Fh+var_B8.Length], 160014h
0x18001fe68  xor     r12d, r12d
0x18001fe6b  mov     qword ptr [rbp+4Fh+var_A8.Length], 160014h
0x18001fe73  lea     rax, aPackagestatus; "PackageStatus"
0x18001fe7a  mov     [rsp+130h+KeyHandle], r12
0x18001fe7f  mov     [rbp+4Fh+ValueName.Buffer], rax
0x18001fe83  mov     r13, r8
0x18001fe86  lea     rax, aBinaryname; "BinaryName"
0x18001fe8d  mov     [rsp+130h+var_E8], r12d
0x18001fe92  mov     [rbp+4Fh+var_B8.Buffer], rax
0x18001fe96  mov     esi, edx
0x18001fe98  lea     rax, aBinaryhash; "BinaryHash"
0x18001fe9f  mov     [rsp+130h+ResultLength], r12d
0x18001fea4  mov     r15, rcx
0x18001fea7  mov     [rbp+4Fh+var_A8.Buffer], rax
0x18001feab  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18001feaf  mov     ebx, 20Ah
0x18001feb4  mov     [rsp+130h+Data], r12d
0x18001feb9  mov     r8d, 58707041h
0x18001febf  mov     edx, ebx
0x18001fec1  mov     ecx, 100h
0x18001fec6  mov     r14, r9
0x18001fec9  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18001fecd  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18001fed1  movups  [rsp+130h+var_D8], xmm0
0x18001fed6  call    cs:__imp_ExAllocatePool2
0x18001fedd  nop     dword ptr [rax+rax+00h]
0x18001fee2  mov     rdi, rax
0x18001fee5  test    rax, rax
0x18001fee8  jnz     short loc_18001FEF4
0x18001feea  mov     eax, 0C0000017h
0x18001feef  jmp     loc_18002015B
0x18001fef4  lea     rax, [rsp+130h+ResultLength]
0x18001fef9  xor     r9d, r9d
0x18001fefc  mov     [rsp+130h+Disposition], rax
0x18001ff01  lea     r8, aRegistryMachin_21; "\\Registry\\Machine\\Software\\Microsof"...
0x18001ff08  mov     [rsp+130h+CreateOptions], ebx
0x18001ff0c  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001ff13  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001ff1a  mov     [rsp+130h+Class], rdi
0x18001ff1f  call    cs:__imp_RtlGetPersistedStateLocation
0x18001ff26  nop     dword ptr [rax+rax+00h]
0x18001ff2b  mov     ebx, eax
0x18001ff2d  test    eax, eax
0x18001ff2f  js      loc_180020145
0x18001ff35  lea     r8, aPackagelist; "\\PackageList\\"
0x18001ff3c  mov     edx, 20Ah; cbDest
0x18001ff41  mov     rcx, rdi; pszDest
0x18001ff44  call    RtlStringCbCatW
0x18001ff49  mov     ebx, eax
0x18001ff4b  test    eax, eax
0x18001ff4d  js      loc_180020145
0x18001ff53  mov     r8, r15; pszSrc
0x18001ff56  mov     edx, 20Ah; cbDest
0x18001ff5b  mov     rcx, rdi; pszDest
0x18001ff5e  call    RtlStringCbCatW
0x18001ff63  mov     ebx, eax
0x18001ff65  test    eax, eax
0x18001ff67  js      loc_180020145
0x18001ff6d  xorps   xmm0, xmm0
0x18001ff70  mov     ecx, 7FFFh
0x18001ff75  movups  [rsp+130h+var_D8], xmm0
0x18001ff7a  mov     rax, rdi
0x18001ff7d  mov     edx, 2
0x18001ff82  cmp     [rax], r12w
0x18001ff86  jz      short loc_18001FF91
0x18001ff88  add     rax, rdx
0x18001ff8b  sub     rcx, 1
0x18001ff8f  jnz     short loc_18001FF82
0x18001ff91  mov     rax, rcx
0x18001ff94  neg     rax
0x18001ff97  sbb     ebx, ebx
0x18001ff99  not     ebx
0x18001ff9b  and     ebx, 0C000000Dh
0x18001ffa1  test    rcx, rcx
0x18001ffa4  jz      loc_180020145
0x18001ffaa  add     cx, cx
0x18001ffad  mov     qword ptr [rsp+130h+var_D8+8], rdi
0x18001ffb2  mov     eax, 0FFFEh
0x18001ffb7  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18001ffbe  sub     ax, cx
0x18001ffc1  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18001ffc5  mov     word ptr [rsp+130h+var_D8], ax
0x18001ffca  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18001ffce  add     ax, dx
0x18001ffd1  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x18001ffd8  mov     word ptr [rsp+130h+var_D8+2], ax
0x18001ffdd  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x18001ffe2  lea     rax, [rsp+130h+var_D8]
0x18001ffe7  xorps   xmm0, xmm0
0x18001ffea  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18001ffee  xor     r9d, r9d; TitleIndex
0x18001fff1  lea     rax, [rsp+130h+var_E8]
0x18001fff6  mov     edx, 20006h; DesiredAccess
0x18001fffb  mov     [rsp+130h+Disposition], rax; Disposition
0x180020000  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x180020005  mov     [rsp+130h+Class], r12; Class
0x18002000a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18002000f  call    cs:__imp_ZwCreateKey
0x180020016  nop     dword ptr [rax+rax+00h]
0x18002001b  mov     ebx, eax
0x18002001d  test    eax, eax
0x18002001f  js      loc_180020145
0x180020025  cmp     [rsp+130h+var_E8], 2
0x18002002a  mov     r15d, 4
0x180020030  jnz     short loc_180020090
0x180020032  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020037  lea     rax, [rsp+130h+ResultLength]
0x18002003c  mov     qword ptr [rsp+130h+CreateOptions], rax; ResultLength
0x180020041  lea     r9, [rbp+4Fh+KeyValueInformation]; KeyValueInformation
0x180020045  lea     r8d, [r15-2]; KeyValueInformationClass
0x180020049  mov     dword ptr [rsp+130h+Class], 14h; Length
0x180020051  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x180020055  call    cs:__imp_ZwQueryValueKey
0x18002005c  nop     dword ptr [rax+rax+00h]
0x180020061  mov     ebx, eax
0x180020063  test    eax, eax
0x180020065  js      short loc_180020086
0x180020067  cmp     [rbp+4Fh+var_64], r15d
0x18002006b  jnz     short loc_180020078
0x18002006d  cmp     [rbp+4Fh+var_60], r15d
0x180020071  jb      short loc_180020078
0x180020073  mov     eax, [rbp+4Fh+var_5C]
0x180020076  jmp     short loc_180020080
0x180020078  mov     eax, r12d
0x18002007b  mov     ebx, 0C000090Bh
0x180020080  test    ebx, ebx
0x180020082  js      short loc_1800200C9
0x180020084  jmp     short loc_180020093
0x180020086  cmp     eax, 0C0000034h
0x18002008b  jnz     short loc_1800200C9
0x18002008d  mov     ebx, r12d
0x180020090  mov     eax, r12d
0x180020093  or      esi, eax
0x180020095  mov     [rsp+130h+Data], esi
0x180020099  cmp     esi, eax
0x18002009b  jz      short loc_1800200C9
0x18002009d  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800200a2  lea     rax, [rsp+130h+Data]
0x1800200a7  mov     [rsp+130h+CreateOptions], r15d; DataSize
0x1800200ac  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x1800200b0  mov     r9d, r15d; Type
0x1800200b3  mov     [rsp+130h+Class], rax; Data
0x1800200b8  xor     r8d, r8d; TitleIndex
0x1800200bb  call    cs:__imp_ZwSetValueKey
0x1800200c2  nop     dword ptr [rax+rax+00h]
0x1800200c7  mov     ebx, eax
0x1800200c9  test    r14, r14
0x1800200cc  jz      short loc_180020134
0x1800200ce  test    ebx, ebx
0x1800200d0  js      short loc_180020134
0x1800200d2  movzx   eax, word ptr [r13+2]
0x1800200d7  lea     rdx, [rbp+4Fh+var_B8]; ValueName
0x1800200db  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800200e0  mov     r9d, 1; Type
0x1800200e6  mov     [rsp+130h+CreateOptions], eax; DataSize
0x1800200ea  xor     r8d, r8d; TitleIndex
0x1800200ed  mov     rax, [r13+8]
0x1800200f1  mov     [rsp+130h+Class], rax; Data
0x1800200f6  call    cs:__imp_ZwSetValueKey
0x1800200fd  nop     dword ptr [rax+rax+00h]
0x180020102  mov     ebx, eax
0x180020104  test    eax, eax
0x180020106  js      short loc_180020134
0x180020108  mov     eax, [rbp+4Fh+DataSize]
0x18002010b  lea     rdx, [rbp+4Fh+var_A8]; ValueName
0x18002010f  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020114  mov     r9d, 3; Type
0x18002011a  mov     [rsp+130h+CreateOptions], eax; DataSize
0x18002011e  xor     r8d, r8d; TitleIndex
0x180020121  mov     [rsp+130h+Class], r14; Data
0x180020126  call    cs:__imp_ZwSetValueKey
0x18002012d  nop     dword ptr [rax+rax+00h]
0x180020132  mov     ebx, eax
0x180020134  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x180020139  call    cs:__imp_ZwClose
0x180020140  nop     dword ptr [rax+rax+00h]
0x180020145  mov     edx, 58707041h; Tag
0x18002014a  mov     rcx, rdi; P
0x18002014d  call    cs:__imp_ExFreePoolWithTag
0x180020154  nop     dword ptr [rax+rax+00h]
0x180020159  mov     eax, ebx
0x18002015b  mov     rcx, [rbp+4Fh+var_50]
0x18002015f  xor     rcx, rsp; StackCookie
0x180020162  call    __security_check_cookie
0x180020167  add     rsp, 0F8h
0x18002016e  pop     r15
0x180020170  pop     r14
0x180020172  pop     r13
0x180020174  pop     r12
0x180020176  pop     rdi
0x180020177  pop     rsi
0x180020178  pop     rbx
0x180020179  pop     rbp
0x18002017a  retn
```
