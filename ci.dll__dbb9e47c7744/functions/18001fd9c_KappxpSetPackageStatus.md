# KappxpSetPackageStatus

- ea: `0x18001fd9c`
- end: `0x1800200ec`
- name: `KappxpSetPackageStatus`
- size: `848`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PCWSTR pszSrc@<rcx>, ULONG DataSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020310`

## callees

- `0x18000cbe4`
- `0x18001fd9c`
- `0x18002bf20`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18001ff7f`
- `ntoskrnl!ZwCreateKey` at `0x18001ff7f`
- `ntoskrnl!ExAllocatePool2` at `0x18001fe46`
- `ntoskrnl!ExAllocatePool2` at `0x18001fe46`
- `ntoskrnl!ZwQueryValueKey` at `0x18001ffc5`
- `ntoskrnl!ZwQueryValueKey` at `0x18001ffc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800200bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800200bd`
- `ntoskrnl!ZwClose` at `0x1800200a9`
- `ntoskrnl!ZwClose` at `0x1800200a9`
- `ntoskrnl!ZwSetValueKey` at `0x18002002b`
- `ntoskrnl!ZwSetValueKey` at `0x180020066`
- `ntoskrnl!ZwSetValueKey` at `0x180020096`
- `ntoskrnl!ZwSetValueKey` at `0x18002002b`
- `ntoskrnl!ZwSetValueKey` at `0x180020066`
- `ntoskrnl!ZwSetValueKey` at `0x180020096`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001fe8f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001fe8f`

## string_xrefs

- `0x18001fe71`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x18001fe7c`: `TargetNtPath`

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
0x18001fd9c  push    rbp
0x18001fd9e  push    rbx
0x18001fd9f  push    rsi
0x18001fda0  push    rdi
0x18001fda1  push    r12
0x18001fda3  push    r13
0x18001fda5  push    r14
0x18001fda7  push    r15
0x18001fda9  lea     rbp, [rsp-17h]
0x18001fdae  sub     rsp, 0F8h
0x18001fdb5  mov     rax, cs:__security_cookie
0x18001fdbc  xor     rax, rsp
0x18001fdbf  mov     [rbp+4Fh+var_50], rax
0x18001fdc3  xorps   xmm0, xmm0
0x18001fdc6  mov     qword ptr [rbp+4Fh+ValueName.Length], 1C001Ah
0x18001fdce  xor     eax, eax
0x18001fdd0  mov     qword ptr [rbp+4Fh+var_B8.Length], 160014h
0x18001fdd8  xor     r12d, r12d
0x18001fddb  mov     qword ptr [rbp+4Fh+var_A8.Length], 160014h
0x18001fde3  lea     rax, aPackagestatus; "PackageStatus"
0x18001fdea  mov     [rsp+130h+KeyHandle], r12
0x18001fdef  mov     [rbp+4Fh+ValueName.Buffer], rax
0x18001fdf3  mov     r13, r8
0x18001fdf6  lea     rax, aBinaryname; "BinaryName"
0x18001fdfd  mov     [rsp+130h+var_E8], r12d
0x18001fe02  mov     [rbp+4Fh+var_B8.Buffer], rax
0x18001fe06  mov     esi, edx
0x18001fe08  lea     rax, aBinaryhash; "BinaryHash"
0x18001fe0f  mov     [rsp+130h+ResultLength], r12d
0x18001fe14  mov     r15, rcx
0x18001fe17  mov     [rbp+4Fh+var_A8.Buffer], rax
0x18001fe1b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18001fe1f  mov     ebx, 20Ah
0x18001fe24  mov     [rsp+130h+Data], r12d
0x18001fe29  mov     r8d, 58707041h
0x18001fe2f  mov     edx, ebx
0x18001fe31  mov     ecx, 100h
0x18001fe36  mov     r14, r9
0x18001fe39  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18001fe3d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18001fe41  movups  [rsp+130h+var_D8], xmm0
0x18001fe46  call    cs:__imp_ExAllocatePool2
0x18001fe4d  nop     dword ptr [rax+rax+00h]
0x18001fe52  mov     rdi, rax
0x18001fe55  test    rax, rax
0x18001fe58  jnz     short loc_18001FE64
0x18001fe5a  mov     eax, 0C0000017h
0x18001fe5f  jmp     loc_1800200CB
0x18001fe64  lea     rax, [rsp+130h+ResultLength]
0x18001fe69  xor     r9d, r9d
0x18001fe6c  mov     [rsp+130h+Disposition], rax
0x18001fe71  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x18001fe78  mov     [rsp+130h+CreateOptions], ebx
0x18001fe7c  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001fe83  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001fe8a  mov     [rsp+130h+Class], rdi
0x18001fe8f  call    cs:__imp_RtlGetPersistedStateLocation
0x18001fe96  nop     dword ptr [rax+rax+00h]
0x18001fe9b  mov     ebx, eax
0x18001fe9d  test    eax, eax
0x18001fe9f  js      loc_1800200B5
0x18001fea5  lea     r8, aPackagelist; "\\PackageList\\"
0x18001feac  mov     edx, 20Ah; cbDest
0x18001feb1  mov     rcx, rdi; pszDest
0x18001feb4  call    RtlStringCbCatW
0x18001feb9  mov     ebx, eax
0x18001febb  test    eax, eax
0x18001febd  js      loc_1800200B5
0x18001fec3  mov     r8, r15; pszSrc
0x18001fec6  mov     edx, 20Ah; cbDest
0x18001fecb  mov     rcx, rdi; pszDest
0x18001fece  call    RtlStringCbCatW
0x18001fed3  mov     ebx, eax
0x18001fed5  test    eax, eax
0x18001fed7  js      loc_1800200B5
0x18001fedd  xorps   xmm0, xmm0
0x18001fee0  mov     ecx, 7FFFh
0x18001fee5  movups  [rsp+130h+var_D8], xmm0
0x18001feea  mov     rax, rdi
0x18001feed  mov     edx, 2
0x18001fef2  cmp     [rax], r12w
0x18001fef6  jz      short loc_18001FF01
0x18001fef8  add     rax, rdx
0x18001fefb  sub     rcx, 1
0x18001feff  jnz     short loc_18001FEF2
0x18001ff01  mov     rax, rcx
0x18001ff04  neg     rax
0x18001ff07  sbb     ebx, ebx
0x18001ff09  not     ebx
0x18001ff0b  and     ebx, 0C000000Dh
0x18001ff11  test    rcx, rcx
0x18001ff14  jz      loc_1800200B5
0x18001ff1a  add     cx, cx
0x18001ff1d  mov     qword ptr [rsp+130h+var_D8+8], rdi
0x18001ff22  mov     eax, 0FFFEh
0x18001ff27  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18001ff2e  sub     ax, cx
0x18001ff31  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18001ff35  mov     word ptr [rsp+130h+var_D8], ax
0x18001ff3a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18001ff3e  add     ax, dx
0x18001ff41  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x18001ff48  mov     word ptr [rsp+130h+var_D8+2], ax
0x18001ff4d  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x18001ff52  lea     rax, [rsp+130h+var_D8]
0x18001ff57  xorps   xmm0, xmm0
0x18001ff5a  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18001ff5e  xor     r9d, r9d; TitleIndex
0x18001ff61  lea     rax, [rsp+130h+var_E8]
0x18001ff66  mov     edx, 20006h; DesiredAccess
0x18001ff6b  mov     [rsp+130h+Disposition], rax; Disposition
0x18001ff70  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x18001ff75  mov     [rsp+130h+Class], r12; Class
0x18001ff7a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ff7f  call    cs:__imp_ZwCreateKey
0x18001ff86  nop     dword ptr [rax+rax+00h]
0x18001ff8b  mov     ebx, eax
0x18001ff8d  test    eax, eax
0x18001ff8f  js      loc_1800200B5
0x18001ff95  cmp     [rsp+130h+var_E8], 2
0x18001ff9a  mov     r15d, 4
0x18001ffa0  jnz     short loc_180020000
0x18001ffa2  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x18001ffa7  lea     rax, [rsp+130h+ResultLength]
0x18001ffac  mov     qword ptr [rsp+130h+CreateOptions], rax; ResultLength
0x18001ffb1  lea     r9, [rbp+4Fh+KeyValueInformation]; KeyValueInformation
0x18001ffb5  lea     r8d, [r15-2]; KeyValueInformationClass
0x18001ffb9  mov     dword ptr [rsp+130h+Class], 14h; Length
0x18001ffc1  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x18001ffc5  call    cs:__imp_ZwQueryValueKey
0x18001ffcc  nop     dword ptr [rax+rax+00h]
0x18001ffd1  mov     ebx, eax
0x18001ffd3  test    eax, eax
0x18001ffd5  js      short loc_18001FFF6
0x18001ffd7  cmp     [rbp+4Fh+var_64], r15d
0x18001ffdb  jnz     short loc_18001FFE8
0x18001ffdd  cmp     [rbp+4Fh+var_60], r15d
0x18001ffe1  jb      short loc_18001FFE8
0x18001ffe3  mov     eax, [rbp+4Fh+var_5C]
0x18001ffe6  jmp     short loc_18001FFF0
0x18001ffe8  mov     eax, r12d
0x18001ffeb  mov     ebx, 0C000090Bh
0x18001fff0  test    ebx, ebx
0x18001fff2  js      short loc_180020039
0x18001fff4  jmp     short loc_180020003
0x18001fff6  cmp     eax, 0C0000034h
0x18001fffb  jnz     short loc_180020039
0x18001fffd  mov     ebx, r12d
0x180020000  mov     eax, r12d
0x180020003  or      esi, eax
0x180020005  mov     [rsp+130h+Data], esi
0x180020009  cmp     esi, eax
0x18002000b  jz      short loc_180020039
0x18002000d  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020012  lea     rax, [rsp+130h+Data]
0x180020017  mov     [rsp+130h+CreateOptions], r15d; DataSize
0x18002001c  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x180020020  mov     r9d, r15d; Type
0x180020023  mov     [rsp+130h+Class], rax; Data
0x180020028  xor     r8d, r8d; TitleIndex
0x18002002b  call    cs:__imp_ZwSetValueKey
0x180020032  nop     dword ptr [rax+rax+00h]
0x180020037  mov     ebx, eax
0x180020039  test    r14, r14
0x18002003c  jz      short loc_1800200A4
0x18002003e  test    ebx, ebx
0x180020040  js      short loc_1800200A4
0x180020042  movzx   eax, word ptr [r13+2]
0x180020047  lea     rdx, [rbp+4Fh+var_B8]; ValueName
0x18002004b  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020050  mov     r9d, 1; Type
0x180020056  mov     [rsp+130h+CreateOptions], eax; DataSize
0x18002005a  xor     r8d, r8d; TitleIndex
0x18002005d  mov     rax, [r13+8]
0x180020061  mov     [rsp+130h+Class], rax; Data
0x180020066  call    cs:__imp_ZwSetValueKey
0x18002006d  nop     dword ptr [rax+rax+00h]
0x180020072  mov     ebx, eax
0x180020074  test    eax, eax
0x180020076  js      short loc_1800200A4
0x180020078  mov     eax, [rbp+4Fh+DataSize]
0x18002007b  lea     rdx, [rbp+4Fh+var_A8]; ValueName
0x18002007f  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020084  mov     r9d, 3; Type
0x18002008a  mov     [rsp+130h+CreateOptions], eax; DataSize
0x18002008e  xor     r8d, r8d; TitleIndex
0x180020091  mov     [rsp+130h+Class], r14; Data
0x180020096  call    cs:__imp_ZwSetValueKey
0x18002009d  nop     dword ptr [rax+rax+00h]
0x1800200a2  mov     ebx, eax
0x1800200a4  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x1800200a9  call    cs:__imp_ZwClose
0x1800200b0  nop     dword ptr [rax+rax+00h]
0x1800200b5  mov     edx, 58707041h; Tag
0x1800200ba  mov     rcx, rdi; P
0x1800200bd  call    cs:__imp_ExFreePoolWithTag
0x1800200c4  nop     dword ptr [rax+rax+00h]
0x1800200c9  mov     eax, ebx
0x1800200cb  mov     rcx, [rbp+4Fh+var_50]
0x1800200cf  xor     rcx, rsp; StackCookie
0x1800200d2  call    __security_check_cookie
0x1800200d7  add     rsp, 0F8h
0x1800200de  pop     r15
0x1800200e0  pop     r14
0x1800200e2  pop     r13
0x1800200e4  pop     r12
0x1800200e6  pop     rdi
0x1800200e7  pop     rsi
0x1800200e8  pop     rbx
0x1800200e9  pop     rbp
0x1800200ea  retn
```
