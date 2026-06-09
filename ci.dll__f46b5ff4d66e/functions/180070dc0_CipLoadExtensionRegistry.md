# CipLoadExtensionRegistry

- ea: `0x180070dc0`
- end: `0x18007110e`
- name: `CipLoadExtensionRegistry`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800709ec`

## callees

- `0x18001e0ac`
- `0x18001e0f8`
- `0x180070dc0`
- `0x180071114`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180070f3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180070f3e`
- `ntoskrnl!ExAllocatePool2` at `0x180070e73`
- `ntoskrnl!ExAllocatePool2` at `0x180071009`
- `ntoskrnl!ExAllocatePool2` at `0x180070e73`
- `ntoskrnl!ExAllocatePool2` at `0x180071009`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070ea0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070f9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070ea0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070f9e`
- `ntoskrnl!ZwClose` at `0x180070ecc`
- `ntoskrnl!ZwClose` at `0x180070ecc`
- `ntoskrnl!ZwOpenKey` at `0x180070f79`
- `ntoskrnl!ZwOpenKey` at `0x180070f79`
- `ntoskrnl!ZwEnumerateKey` at `0x180070fd1`
- `ntoskrnl!ZwEnumerateKey` at `0x18007103e`
- `ntoskrnl!ZwEnumerateKey` at `0x180070fd1`
- `ntoskrnl!ZwEnumerateKey` at `0x18007103e`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180070e43`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180070f15`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180070e43`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180070f15`

## string_xrefs

- `0x180070deb`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`
- `0x180070ef9`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`

## pseudocode

```c
__int64 __fastcall CipLoadExtensionRegistry(__int64 a1)
{
  ULONG *v1; // rdi
  int PersistedStateLocation; // eax
  NTSTATUS v4; // ebx
  WCHAR *Pool2; // rsi
  ULONG i; // r14d
  NTSTATUS v8; // eax
  ULONG *v9; // rax
  __int64 *v10; // rax
  __int64 *v11; // rcx
  __int64 **v12; // rcx
  __int64 *v13; // [rsp+48h] [rbp-41h] BYREF
  __int64 **v14; // [rsp+50h] [rbp-39h]
  USHORT pusResult[8]; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  ULONG ResultLength; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+100h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+108h] [rbp+7Fh] BYREF

  v19 = 0;
  Handle = 0;
  ResultLength = 0;
  v14 = &v13;
  v1 = 0;
  v13 = (__int64 *)&v13;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)pusResult = 0;
  DestinationString = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIExtPolicy",
                             0,
                             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\ExtensionPolicy",
                             0,
                             0,
                             0,
                             &v19);
  v4 = PersistedStateLocation;
  if ( PersistedStateLocation >= 0 || (Pool2 = 0, PersistedStateLocation == -2147483643) )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, v19, 1668499779);
    if ( Pool2 )
    {
      v4 = RtlGetPersistedStateLocation(
             L"CIExtPolicy",
             0,
             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\ExtensionPolicy",
             0,
             Pool2,
             v19,
             &v19);
      if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483643 )
      {
        RtlInitUnicodeString(&DestinationString, Pool2);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( v1 )
            {
              ExFreePoolWithTag(v1, 0x63734943u);
              v1 = 0;
            }
            ResultLength = 0;
            v8 = ZwEnumerateKey(Handle, i, KeyBasicInformation, v1, 0, &ResultLength);
            if ( v8 == -2147483622 )
              break;
            if ( v8 == -2147483643 || v8 == -1073741789 || v8 >= 0 )
            {
              v9 = (ULONG *)ExAllocatePool2(256, ResultLength, 1668499779);
              v1 = v9;
              if ( !v9 )
                goto LABEL_4;
              if ( ZwEnumerateKey(Handle, i, KeyBasicInformation, v9, ResultLength, &ResultLength) >= 0 )
              {
                v4 = RtlULongToUShort(v1[3], pusResult);
                if ( v4 < 0 )
                  goto LABEL_5;
                *(_QWORD *)&pusResult[4] = v1 + 4;
                pusResult[1] = pusResult[0];
                if ( (int)CipLoadOneExtensionConfig(&DestinationString, (PCUNICODE_STRING)pusResult) >= 0 )
                {
                  if ( *v14 != (__int64 *)&v13 )
LABEL_36:
                    __fastfail(3u);
                  MEMORY[0] = &v13;
                  MEMORY[8] = v14;
                  *v14 = 0;
                  v14 = 0;
                }
              }
            }
          }
          v4 = 0;
          while ( 1 )
          {
            v10 = v13;
            if ( v13 == (__int64 *)&v13 )
              break;
            if ( (__int64 **)v13[1] != &v13 )
              goto LABEL_36;
            v11 = (__int64 *)*v13;
            if ( *(__int64 **)(*v13 + 8) != v13 )
              goto LABEL_36;
            v13 = (__int64 *)*v13;
            v11[1] = (__int64)&v13;
            v12 = *(__int64 ***)(a1 + 8);
            if ( *v12 != (__int64 *)a1 )
              goto LABEL_36;
            *v10 = a1;
            v10[1] = (__int64)v12;
            *v12 = v10;
            *(_QWORD *)(a1 + 8) = v10;
          }
        }
        else
        {
          v4 = 0;
        }
      }
    }
    else
    {
LABEL_4:
      v4 = -1073741801;
    }
  }
LABEL_5:
  CipFreeExtRegistryList(&v13);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x63734943u);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180070dc0  push    rbp
0x180070dc2  push    rbx
0x180070dc3  push    rsi
0x180070dc4  push    rdi
0x180070dc5  push    r13
0x180070dc7  push    r14
0x180070dc9  push    r15
0x180070dcb  lea     rbp, [rsp-27h]
0x180070dd0  sub     rsp, 0B0h
0x180070dd7  xor     eax, eax
0x180070dd9  mov     [rbp+57h+arg_10], 0
0x180070de0  xorps   xmm0, xmm0
0x180070de3  mov     [rbp+57h+Handle], rax
0x180070de7  mov     [rbp+57h+var_A0], rax
0x180070deb  lea     r8, aRegistryMachin_15; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x180070df2  lea     rax, [rbp+57h+var_98]
0x180070df6  mov     [rbp+57h+arg_8], 0
0x180070dfd  mov     [rbp+57h+var_90], rax
0x180070e01  xor     edi, edi
0x180070e03  lea     rax, [rbp+57h+var_98]
0x180070e07  mov     r15, rcx
0x180070e0a  mov     [rbp+57h+var_98], rax
0x180070e0e  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x180070e15  lea     rax, [rbp+57h+arg_10]
0x180070e19  xorps   xmm1, xmm1
0x180070e1c  mov     [rsp+0E0h+var_B0], rax
0x180070e21  xor     r9d, r9d
0x180070e24  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180070e28  mov     dword ptr [rsp+0E0h+ResultLength], edi
0x180070e2c  xor     edx, edx
0x180070e2e  mov     qword ptr [rsp+0E0h+Length], rdi
0x180070e33  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180070e37  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180070e3b  movups  xmmword ptr [rbp+57h+pusResult], xmm0
0x180070e3f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180070e43  call    cs:__imp_RtlGetPersistedStateLocation
0x180070e4a  nop     dword ptr [rax+rax+00h]
0x180070e4f  mov     r13d, 63734943h
0x180070e55  mov     r14d, 80000005h
0x180070e5b  mov     ebx, eax
0x180070e5d  test    eax, eax
0x180070e5f  jns     short loc_180070E68
0x180070e61  xor     esi, esi
0x180070e63  cmp     eax, r14d
0x180070e66  jnz     short loc_180070E8C
0x180070e68  mov     edx, [rbp+57h+arg_10]
0x180070e6b  mov     r8d, r13d
0x180070e6e  mov     ecx, 100h
0x180070e73  call    cs:__imp_ExAllocatePool2
0x180070e7a  nop     dword ptr [rax+rax+00h]
0x180070e7f  mov     rsi, rax
0x180070e82  test    rax, rax
0x180070e85  jnz     short loc_180070EED
0x180070e87  mov     ebx, 0C0000017h
0x180070e8c  lea     rcx, [rbp+57h+var_98]
0x180070e90  call    CipFreeExtRegistryList
0x180070e95  test    rsi, rsi
0x180070e98  jz      short loc_180070EAC
0x180070e9a  mov     edx, r13d; Tag
0x180070e9d  mov     rcx, rsi; P
0x180070ea0  call    cs:__imp_ExFreePoolWithTag
0x180070ea7  nop     dword ptr [rax+rax+00h]
0x180070eac  test    rdi, rdi
0x180070eaf  jz      short loc_180070EC3
0x180070eb1  mov     edx, r13d; Tag
0x180070eb4  mov     rcx, rdi; P
0x180070eb7  call    cs:__imp_ExFreePoolWithTag
0x180070ebe  nop     dword ptr [rax+rax+00h]
0x180070ec3  mov     rcx, [rbp+57h+Handle]; Handle
0x180070ec7  test    rcx, rcx
0x180070eca  jz      short loc_180070ED8
0x180070ecc  call    cs:__imp_ZwClose
0x180070ed3  nop     dword ptr [rax+rax+00h]
0x180070ed8  mov     eax, ebx
0x180070eda  add     rsp, 0B0h
0x180070ee1  pop     r15
0x180070ee3  pop     r14
0x180070ee5  pop     r13
0x180070ee7  pop     rdi
0x180070ee8  pop     rsi
0x180070ee9  pop     rbx
0x180070eea  pop     rbp
0x180070eeb  retn
0x180070eed  mov     eax, [rbp+57h+arg_10]
0x180070ef0  lea     rdx, [rbp+57h+arg_10]
0x180070ef4  mov     [rsp+0E0h+var_B0], rdx
0x180070ef9  lea     r8, aRegistryMachin_15; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x180070f00  mov     dword ptr [rsp+0E0h+ResultLength], eax
0x180070f04  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x180070f0b  xor     edx, edx
0x180070f0d  mov     qword ptr [rsp+0E0h+Length], rsi
0x180070f12  xor     r9d, r9d
0x180070f15  call    cs:__imp_RtlGetPersistedStateLocation
0x180070f1c  nop     dword ptr [rax+rax+00h]
0x180070f21  mov     ecx, 80000000h
0x180070f26  mov     ebx, eax
0x180070f28  add     eax, ecx
0x180070f2a  test    ecx, eax
0x180070f2c  jnz     short loc_180070F37
0x180070f2e  cmp     ebx, r14d
0x180070f31  jnz     loc_180070E8C
0x180070f37  mov     rdx, rsi; SourceString
0x180070f3a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180070f3e  call    cs:__imp_RtlInitUnicodeString
0x180070f45  nop     dword ptr [rax+rax+00h]
0x180070f4a  lea     rax, [rbp+57h+DestinationString]
0x180070f4e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180070f55  xorps   xmm0, xmm0
0x180070f58  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180070f5c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180070f60  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180070f64  mov     edx, 20019h; DesiredAccess
0x180070f69  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180070f70  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180070f74  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180070f79  call    cs:__imp_ZwOpenKey
0x180070f80  nop     dword ptr [rax+rax+00h]
0x180070f85  test    eax, eax
0x180070f87  jns     short loc_180070F90
0x180070f89  xor     ebx, ebx
0x180070f8b  jmp     loc_180070E8C
0x180070f90  xor     r14d, r14d
0x180070f93  test    rdi, rdi
0x180070f96  jz      short loc_180070FAC
0x180070f98  mov     edx, r13d; Tag
0x180070f9b  mov     rcx, rdi; P
0x180070f9e  call    cs:__imp_ExFreePoolWithTag
0x180070fa5  nop     dword ptr [rax+rax+00h]
0x180070faa  xor     edi, edi
0x180070fac  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180070fb0  lea     rax, [rbp+57h+arg_8]
0x180070fb4  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180070fb9  mov     r9, rdi; KeyInformation
0x180070fbc  xor     r8d, r8d; KeyInformationClass
0x180070fbf  mov     [rsp+0E0h+Length], 0; Length
0x180070fc7  mov     edx, r14d; Index
0x180070fca  mov     [rbp+57h+arg_8], 0
0x180070fd1  call    cs:__imp_ZwEnumerateKey
0x180070fd8  nop     dword ptr [rax+rax+00h]
0x180070fdd  cmp     eax, 8000001Ah
0x180070fe2  jz      loc_1800710BC
0x180070fe8  cmp     eax, 80000005h
0x180070fed  jz      short loc_180070FFE
0x180070fef  cmp     eax, 0C0000023h
0x180070ff4  jz      short loc_180070FFE
0x180070ff6  test    eax, eax
0x180070ff8  js      loc_1800710B4
0x180070ffe  mov     edx, [rbp+57h+arg_8]
0x180071001  mov     r8d, r13d
0x180071004  mov     ecx, 100h
0x180071009  call    cs:__imp_ExAllocatePool2
0x180071010  nop     dword ptr [rax+rax+00h]
0x180071015  mov     rdi, rax
0x180071018  test    rax, rax
0x18007101b  jz      loc_180070E87
0x180071021  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180071025  lea     rax, [rbp+57h+arg_8]
0x180071029  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18007102e  mov     r9, rdi; KeyInformation
0x180071031  mov     eax, [rbp+57h+arg_8]
0x180071034  xor     r8d, r8d; KeyInformationClass
0x180071037  mov     edx, r14d; Index
0x18007103a  mov     [rsp+0E0h+Length], eax; Length
0x18007103e  call    cs:__imp_ZwEnumerateKey
0x180071045  nop     dword ptr [rax+rax+00h]
0x18007104a  test    eax, eax
0x18007104c  js      short loc_1800710B4
0x18007104e  mov     ecx, [rdi+0Ch]; ulOperand
0x180071051  lea     rdx, [rbp+57h+pusResult]; pusResult
0x180071055  call    RtlULongToUShort
0x18007105a  mov     ebx, eax
0x18007105c  test    eax, eax
0x18007105e  js      loc_180070E8C
0x180071064  lea     rax, [rdi+10h]
0x180071068  mov     qword ptr [rbp+57h+pusResult+8], rax
0x18007106c  lea     r8, [rbp+57h+var_A0]
0x180071070  movzx   eax, [rbp+57h+pusResult]
0x180071074  lea     rdx, [rbp+57h+pusResult]; Source
0x180071078  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x18007107c  mov     [rbp+57h+pusResult+2], ax
0x180071080  call    CipLoadOneExtensionConfig
0x180071085  test    eax, eax
0x180071087  js      short loc_1800710B4
0x180071089  mov     rcx, [rbp+57h+var_90]
0x18007108d  lea     rax, [rbp+57h+var_98]
0x180071091  cmp     [rcx], rax
0x180071094  jnz     short loc_180071107
0x180071096  mov     rax, [rbp+57h+var_A0]
0x18007109a  lea     rdx, [rbp+57h+var_98]
0x18007109e  mov     [rbp+57h+var_A0], 0
0x1800710a6  mov     [rax], rdx
0x1800710a9  mov     [rax+8], rcx
0x1800710ad  mov     [rcx], rax
0x1800710b0  mov     [rbp+57h+var_90], rax
0x1800710b4  inc     r14d
0x1800710b7  jmp     loc_180070F93
0x1800710bc  xor     ebx, ebx
0x1800710be  mov     rax, [rbp+57h+var_98]
0x1800710c2  lea     rcx, [rbp+57h+var_98]
0x1800710c6  cmp     rax, rcx
0x1800710c9  jz      loc_180070E8C
0x1800710cf  lea     rcx, [rbp+57h+var_98]
0x1800710d3  cmp     [rax+8], rcx
0x1800710d7  jnz     short loc_180071107
0x1800710d9  mov     rcx, [rax]
0x1800710dc  cmp     [rcx+8], rax
0x1800710e0  jnz     short loc_180071107
0x1800710e2  mov     [rbp+57h+var_98], rcx
0x1800710e6  lea     rdx, [rbp+57h+var_98]
0x1800710ea  mov     [rcx+8], rdx
0x1800710ee  mov     rcx, [r15+8]
0x1800710f2  cmp     [rcx], r15
0x1800710f5  jnz     short loc_180071107
0x1800710f7  mov     [rax], r15
0x1800710fa  mov     [rax+8], rcx
0x1800710fe  mov     [rcx], rax
0x180071101  mov     [r15+8], rax
0x180071105  jmp     short loc_1800710BE
0x180071107  mov     ecx, 3
0x18007110c  int     29h; Win8: RtlFailFast(ecx)
```
