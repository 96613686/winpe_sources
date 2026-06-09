# KappxpSetPackageStatus

- ea: `0x18001fe6c`
- end: `0x1800201bc`
- name: `KappxpSetPackageStatus`
- size: `848`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PCWSTR pszSrc@<rcx>, ULONG DataSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800203e0`

## callees

- `0x18000cbf4`
- `0x18001fe6c`
- `0x18002c0d0`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18002004f`
- `ntoskrnl!ZwCreateKey` at `0x18002004f`
- `ntoskrnl!ExAllocatePool2` at `0x18001ff16`
- `ntoskrnl!ExAllocatePool2` at `0x18001ff16`
- `ntoskrnl!ZwQueryValueKey` at `0x180020095`
- `ntoskrnl!ZwQueryValueKey` at `0x180020095`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002018d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002018d`
- `ntoskrnl!ZwClose` at `0x180020179`
- `ntoskrnl!ZwClose` at `0x180020179`
- `ntoskrnl!ZwSetValueKey` at `0x1800200fb`
- `ntoskrnl!ZwSetValueKey` at `0x180020136`
- `ntoskrnl!ZwSetValueKey` at `0x180020166`
- `ntoskrnl!ZwSetValueKey` at `0x1800200fb`
- `ntoskrnl!ZwSetValueKey` at `0x180020136`
- `ntoskrnl!ZwSetValueKey` at `0x180020166`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001ff5f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18001ff5f`

## string_xrefs

- `0x18001ff41`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`
- `0x18001ff4c`: `TargetNtPath`

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
0x18001fe6c  push    rbp
0x18001fe6e  push    rbx
0x18001fe6f  push    rsi
0x18001fe70  push    rdi
0x18001fe71  push    r12
0x18001fe73  push    r13
0x18001fe75  push    r14
0x18001fe77  push    r15
0x18001fe79  lea     rbp, [rsp-17h]
0x18001fe7e  sub     rsp, 0F8h
0x18001fe85  mov     rax, cs:__security_cookie
0x18001fe8c  xor     rax, rsp
0x18001fe8f  mov     [rbp+4Fh+var_50], rax
0x18001fe93  xorps   xmm0, xmm0
0x18001fe96  mov     qword ptr [rbp+4Fh+ValueName.Length], 1C001Ah
0x18001fe9e  xor     eax, eax
0x18001fea0  mov     qword ptr [rbp+4Fh+var_B8.Length], 160014h
0x18001fea8  xor     r12d, r12d
0x18001feab  mov     qword ptr [rbp+4Fh+var_A8.Length], 160014h
0x18001feb3  lea     rax, aPackagestatus; "PackageStatus"
0x18001feba  mov     [rsp+130h+KeyHandle], r12
0x18001febf  mov     [rbp+4Fh+ValueName.Buffer], rax
0x18001fec3  mov     r13, r8
0x18001fec6  lea     rax, aBinaryname; "BinaryName"
0x18001fecd  mov     [rsp+130h+var_E8], r12d
0x18001fed2  mov     [rbp+4Fh+var_B8.Buffer], rax
0x18001fed6  mov     esi, edx
0x18001fed8  lea     rax, aBinaryhash; "BinaryHash"
0x18001fedf  mov     [rsp+130h+ResultLength], r12d
0x18001fee4  mov     r15, rcx
0x18001fee7  mov     [rbp+4Fh+var_A8.Buffer], rax
0x18001feeb  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18001feef  mov     ebx, 20Ah
0x18001fef4  mov     [rsp+130h+Data], r12d
0x18001fef9  mov     r8d, 58707041h
0x18001feff  mov     edx, ebx
0x18001ff01  mov     ecx, 100h
0x18001ff06  mov     r14, r9
0x18001ff09  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18001ff0d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x18001ff11  movups  [rsp+130h+var_D8], xmm0
0x18001ff16  call    cs:__imp_ExAllocatePool2
0x18001ff1d  nop     dword ptr [rax+rax+00h]
0x18001ff22  mov     rdi, rax
0x18001ff25  test    rax, rax
0x18001ff28  jnz     short loc_18001FF34
0x18001ff2a  mov     eax, 0C0000017h
0x18001ff2f  jmp     loc_18002019B
0x18001ff34  lea     rax, [rsp+130h+ResultLength]
0x18001ff39  xor     r9d, r9d
0x18001ff3c  mov     [rsp+130h+Disposition], rax
0x18001ff41  lea     r8, aRegistryMachin_20; "\\Registry\\Machine\\Software\\Microsof"...
0x18001ff48  mov     [rsp+130h+CreateOptions], ebx
0x18001ff4c  lea     rdx, aTargetntpath; "TargetNtPath"
0x18001ff53  lea     rcx, aAppxstatechang; "AppxStateChange"
0x18001ff5a  mov     [rsp+130h+Class], rdi
0x18001ff5f  call    cs:__imp_RtlGetPersistedStateLocation
0x18001ff66  nop     dword ptr [rax+rax+00h]
0x18001ff6b  mov     ebx, eax
0x18001ff6d  test    eax, eax
0x18001ff6f  js      loc_180020185
0x18001ff75  lea     r8, aPackagelist; "\\PackageList\\"
0x18001ff7c  mov     edx, 20Ah; cbDest
0x18001ff81  mov     rcx, rdi; pszDest
0x18001ff84  call    RtlStringCbCatW
0x18001ff89  mov     ebx, eax
0x18001ff8b  test    eax, eax
0x18001ff8d  js      loc_180020185
0x18001ff93  mov     r8, r15; pszSrc
0x18001ff96  mov     edx, 20Ah; cbDest
0x18001ff9b  mov     rcx, rdi; pszDest
0x18001ff9e  call    RtlStringCbCatW
0x18001ffa3  mov     ebx, eax
0x18001ffa5  test    eax, eax
0x18001ffa7  js      loc_180020185
0x18001ffad  xorps   xmm0, xmm0
0x18001ffb0  mov     ecx, 7FFFh
0x18001ffb5  movups  [rsp+130h+var_D8], xmm0
0x18001ffba  mov     rax, rdi
0x18001ffbd  mov     edx, 2
0x18001ffc2  cmp     [rax], r12w
0x18001ffc6  jz      short loc_18001FFD1
0x18001ffc8  add     rax, rdx
0x18001ffcb  sub     rcx, 1
0x18001ffcf  jnz     short loc_18001FFC2
0x18001ffd1  mov     rax, rcx
0x18001ffd4  neg     rax
0x18001ffd7  sbb     ebx, ebx
0x18001ffd9  not     ebx
0x18001ffdb  and     ebx, 0C000000Dh
0x18001ffe1  test    rcx, rcx
0x18001ffe4  jz      loc_180020185
0x18001ffea  add     cx, cx
0x18001ffed  mov     qword ptr [rsp+130h+var_D8+8], rdi
0x18001fff2  mov     eax, 0FFFEh
0x18001fff7  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18001fffe  sub     ax, cx
0x180020001  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180020005  mov     word ptr [rsp+130h+var_D8], ax
0x18002000a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18002000e  add     ax, dx
0x180020011  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x180020018  mov     word ptr [rsp+130h+var_D8+2], ax
0x18002001d  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020022  lea     rax, [rsp+130h+var_D8]
0x180020027  xorps   xmm0, xmm0
0x18002002a  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18002002e  xor     r9d, r9d; TitleIndex
0x180020031  lea     rax, [rsp+130h+var_E8]
0x180020036  mov     edx, 20006h; DesiredAccess
0x18002003b  mov     [rsp+130h+Disposition], rax; Disposition
0x180020040  mov     [rsp+130h+CreateOptions], r12d; CreateOptions
0x180020045  mov     [rsp+130h+Class], r12; Class
0x18002004a  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18002004f  call    cs:__imp_ZwCreateKey
0x180020056  nop     dword ptr [rax+rax+00h]
0x18002005b  mov     ebx, eax
0x18002005d  test    eax, eax
0x18002005f  js      loc_180020185
0x180020065  cmp     [rsp+130h+var_E8], 2
0x18002006a  mov     r15d, 4
0x180020070  jnz     short loc_1800200D0
0x180020072  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020077  lea     rax, [rsp+130h+ResultLength]
0x18002007c  mov     qword ptr [rsp+130h+CreateOptions], rax; ResultLength
0x180020081  lea     r9, [rbp+4Fh+KeyValueInformation]; KeyValueInformation
0x180020085  lea     r8d, [r15-2]; KeyValueInformationClass
0x180020089  mov     dword ptr [rsp+130h+Class], 14h; Length
0x180020091  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x180020095  call    cs:__imp_ZwQueryValueKey
0x18002009c  nop     dword ptr [rax+rax+00h]
0x1800200a1  mov     ebx, eax
0x1800200a3  test    eax, eax
0x1800200a5  js      short loc_1800200C6
0x1800200a7  cmp     [rbp+4Fh+var_64], r15d
0x1800200ab  jnz     short loc_1800200B8
0x1800200ad  cmp     [rbp+4Fh+var_60], r15d
0x1800200b1  jb      short loc_1800200B8
0x1800200b3  mov     eax, [rbp+4Fh+var_5C]
0x1800200b6  jmp     short loc_1800200C0
0x1800200b8  mov     eax, r12d
0x1800200bb  mov     ebx, 0C000090Bh
0x1800200c0  test    ebx, ebx
0x1800200c2  js      short loc_180020109
0x1800200c4  jmp     short loc_1800200D3
0x1800200c6  cmp     eax, 0C0000034h
0x1800200cb  jnz     short loc_180020109
0x1800200cd  mov     ebx, r12d
0x1800200d0  mov     eax, r12d
0x1800200d3  or      esi, eax
0x1800200d5  mov     [rsp+130h+Data], esi
0x1800200d9  cmp     esi, eax
0x1800200db  jz      short loc_180020109
0x1800200dd  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800200e2  lea     rax, [rsp+130h+Data]
0x1800200e7  mov     [rsp+130h+CreateOptions], r15d; DataSize
0x1800200ec  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x1800200f0  mov     r9d, r15d; Type
0x1800200f3  mov     [rsp+130h+Class], rax; Data
0x1800200f8  xor     r8d, r8d; TitleIndex
0x1800200fb  call    cs:__imp_ZwSetValueKey
0x180020102  nop     dword ptr [rax+rax+00h]
0x180020107  mov     ebx, eax
0x180020109  test    r14, r14
0x18002010c  jz      short loc_180020174
0x18002010e  test    ebx, ebx
0x180020110  js      short loc_180020174
0x180020112  movzx   eax, word ptr [r13+2]
0x180020117  lea     rdx, [rbp+4Fh+var_B8]; ValueName
0x18002011b  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020120  mov     r9d, 1; Type
0x180020126  mov     [rsp+130h+CreateOptions], eax; DataSize
0x18002012a  xor     r8d, r8d; TitleIndex
0x18002012d  mov     rax, [r13+8]
0x180020131  mov     [rsp+130h+Class], rax; Data
0x180020136  call    cs:__imp_ZwSetValueKey
0x18002013d  nop     dword ptr [rax+rax+00h]
0x180020142  mov     ebx, eax
0x180020144  test    eax, eax
0x180020146  js      short loc_180020174
0x180020148  mov     eax, [rbp+4Fh+DataSize]
0x18002014b  lea     rdx, [rbp+4Fh+var_A8]; ValueName
0x18002014f  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180020154  mov     r9d, 3; Type
0x18002015a  mov     [rsp+130h+CreateOptions], eax; DataSize
0x18002015e  xor     r8d, r8d; TitleIndex
0x180020161  mov     [rsp+130h+Class], r14; Data
0x180020166  call    cs:__imp_ZwSetValueKey
0x18002016d  nop     dword ptr [rax+rax+00h]
0x180020172  mov     ebx, eax
0x180020174  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x180020179  call    cs:__imp_ZwClose
0x180020180  nop     dword ptr [rax+rax+00h]
0x180020185  mov     edx, 58707041h; Tag
0x18002018a  mov     rcx, rdi; P
0x18002018d  call    cs:__imp_ExFreePoolWithTag
0x180020194  nop     dword ptr [rax+rax+00h]
0x180020199  mov     eax, ebx
0x18002019b  mov     rcx, [rbp+4Fh+var_50]
0x18002019f  xor     rcx, rsp; StackCookie
0x1800201a2  call    __security_check_cookie
0x1800201a7  add     rsp, 0F8h
0x1800201ae  pop     r15
0x1800201b0  pop     r14
0x1800201b2  pop     r13
0x1800201b4  pop     r12
0x1800201b6  pop     rdi
0x1800201b7  pop     rsi
0x1800201b8  pop     rbx
0x1800201b9  pop     rbp
0x1800201ba  retn
```
