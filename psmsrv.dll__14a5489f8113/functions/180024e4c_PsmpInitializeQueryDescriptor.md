# PsmpInitializeQueryDescriptor

- ea: `0x180024e4c`
- end: `0x180024fd1`
- name: `PsmpInitializeQueryDescriptor`
- size: `389`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025078`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x180024e4c`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180024ed9`
- `ntdll!NtOpenKey` at `0x180024ed9`
- `ntdll!NtClose` at `0x180024fa8`
- `ntdll!NtClose` at `0x180024fa8`
- `ntdll!RtlLengthSid` at `0x180024f66`
- `ntdll!RtlLengthSid` at `0x180024f66`
- `ntdll!NtQueryValueKey` at `0x180024f09`
- `ntdll!NtQueryValueKey` at `0x180024f09`
- `ntdll!RtlValidSid` at `0x180024f59`
- `ntdll!RtlValidSid` at `0x180024f59`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180024f2c`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180024f2c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180024f81`
- `ntdll!RtlAddAccessAllowedAce` at `0x180024f81`

## pseudocode

```c
__int64 PsmpInitializeQueryDescriptor()
{
  NTSTATUS DaclSecurityDescriptor; // ebx
  char *i; // rdi
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+31h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-55h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  PACL Dacl; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-41h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v10; // [rsp+88h] [rbp-1h]
  char Sid; // [rsp+8Ch] [rbp+3h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"tv";
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  Dacl = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  KeyHandle = 0;
  memset_0(KeyValueInformation, 0, 0x50u);
  DaclSecurityDescriptor = NtOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( DaclSecurityDescriptor >= 0 )
  {
    DaclSecurityDescriptor = NtQueryValueKey(
                               KeyHandle,
                               &stru_18003F0F0,
                               KeyValuePartialInformation,
                               KeyValueInformation,
                               0x50u,
                               &ResultLength);
    if ( DaclSecurityDescriptor >= 0 )
    {
      DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(PsmpQueryDescriptor, &DaclPresent, &Dacl, DaclDefaulted);
      if ( DaclSecurityDescriptor >= 0 )
      {
        if ( DaclPresent )
        {
          for ( i = &Sid; i <= (char *)&ObjectAttributes.SecurityDescriptor + v10 + 4; i += 32 )
          {
            if ( !RtlValidSid(i) )
            {
              DaclSecurityDescriptor = -1073741704;
              break;
            }
            if ( RtlLengthSid(i) != 32 )
            {
              DaclSecurityDescriptor = -1073741271;
              break;
            }
            DaclSecurityDescriptor = RtlAddAccessAllowedAce(Dacl, 2u, 0x80000000, i);
            if ( DaclSecurityDescriptor < 0 )
              break;
          }
        }
        else
        {
          DaclSecurityDescriptor = -1073741703;
        }
      }
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x180024e4c  mov     [rsp-8+arg_0], rbx
0x180024e51  mov     [rsp-8+arg_8], rdi
0x180024e56  push    rbp
0x180024e57  lea     rbp, [rsp-57h]
0x180024e5c  sub     rsp, 0E0h
0x180024e63  mov     rax, cs:__security_cookie
0x180024e6a  xor     rax, rsp
0x180024e6d  mov     [rbp+57h+var_10], rax
0x180024e71  lea     rax, aTv; "tv"
0x180024e78  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180024e80  xorps   xmm0, xmm0
0x180024e83  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180024e8b  mov     edi, 50h ; 'P'
0x180024e90  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180024e94  mov     r8d, edi; Size
0x180024e97  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180024e9f  xor     edx, edx; Val
0x180024ea1  mov     [rbp+57h+var_AC], 0
0x180024ea8  lea     rcx, [rbp+57h+KeyValueInformation]; void *
0x180024eac  mov     [rbp+57h+Dacl], 0
0x180024eb4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024eb9  mov     [rbp+57h+DaclPresent], 0
0x180024ebd  mov     [rbp+57h+DaclDefaulted], 0
0x180024ec1  mov     [rbp+57h+KeyHandle], 0
0x180024ec9  call    memset_0
0x180024ece  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180024ed2  lea     edx, [rdi-4Fh]; DesiredAccess
0x180024ed5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180024ed9  call    cs:__imp_NtOpenKey
0x180024edf  mov     ebx, eax
0x180024ee1  test    eax, eax
0x180024ee3  js      loc_180024F9F
0x180024ee9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180024eed  lea     rax, [rbp+57h+var_AC]
0x180024ef1  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180024ef6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180024efa  lea     r8d, [rdi-4Eh]; KeyValueInformationClass
0x180024efe  mov     [rsp+0E0h+Length], edi; Length
0x180024f02  lea     rdx, stru_18003F0F0; ValueName
0x180024f09  call    cs:__imp_NtQueryValueKey
0x180024f0f  mov     ebx, eax
0x180024f11  test    eax, eax
0x180024f13  js      loc_180024F9F
0x180024f19  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x180024f1d  lea     r8, [rbp+57h+Dacl]; Dacl
0x180024f21  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x180024f25  lea     rcx, PsmpQueryDescriptor; SecurityDescriptor
0x180024f2c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180024f32  mov     ebx, eax
0x180024f34  test    eax, eax
0x180024f36  js      short loc_180024F9F
0x180024f38  cmp     [rbp+57h+DaclPresent], 0
0x180024f3c  jnz     short loc_180024F45
0x180024f3e  mov     ebx, 0C0000079h
0x180024f43  jmp     short loc_180024F9F
0x180024f45  lea     rdi, [rbp+57h+Sid]
0x180024f49  mov     eax, [rbp+57h+var_58]
0x180024f4c  lea     rcx, [rbp+rax+57h+ObjectAttributes.SecurityDescriptor+4]
0x180024f51  cmp     rdi, rcx
0x180024f54  ja      short loc_180024F9F
0x180024f56  mov     rcx, rdi; Sid
0x180024f59  call    cs:__imp_RtlValidSid
0x180024f5f  test    al, al
0x180024f61  jz      short loc_180024F9A
0x180024f63  mov     rcx, rdi; Sid
0x180024f66  call    cs:__imp_RtlLengthSid
0x180024f6c  cmp     eax, 20h ; ' '
0x180024f6f  jnz     short loc_180024F93
0x180024f71  mov     rcx, [rbp+57h+Dacl]; Acl
0x180024f75  lea     edx, [rax-1Eh]; Revision
0x180024f78  mov     r9, rdi; Sid
0x180024f7b  mov     r8d, 80000000h; AccessMask
0x180024f81  call    cs:__imp_RtlAddAccessAllowedAce
0x180024f87  mov     ebx, eax
0x180024f89  test    eax, eax
0x180024f8b  js      short loc_180024F9F
0x180024f8d  add     rdi, 20h ; ' '
0x180024f91  jmp     short loc_180024F49
0x180024f93  mov     ebx, 0C0000229h
0x180024f98  jmp     short loc_180024F9F
0x180024f9a  mov     ebx, 0C0000078h
0x180024f9f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180024fa3  test    rcx, rcx
0x180024fa6  jz      short loc_180024FAE
0x180024fa8  call    cs:__imp_NtClose
0x180024fae  mov     eax, ebx
0x180024fb0  mov     rcx, [rbp+57h+var_10]
0x180024fb4  xor     rcx, rsp; StackCookie
0x180024fb7  call    __security_check_cookie
0x180024fbc  lea     r11, [rsp+0E0h+var_s0]
0x180024fc4  mov     rbx, [r11+10h]
0x180024fc8  mov     rdi, [r11+18h]
0x180024fcc  mov     rsp, r11
0x180024fcf  pop     rbp
0x180024fd0  retn
```
