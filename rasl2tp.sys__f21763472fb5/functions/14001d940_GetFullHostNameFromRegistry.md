# GetFullHostNameFromRegistry

- ea: `0x14001d940`
- end: `0x14001dbbf`
- name: `GetFullHostNameFromRegistry`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001e3c0`

## callees

- `0x140001440`
- `0x140001b70`
- `0x140004900`
- `0x14001d940`
- `0x14001dc40`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001da2d`
- `ntoskrnl!ZwQueryValueKey` at `0x14001daa1`
- `ntoskrnl!ZwQueryValueKey` at `0x14001da2d`
- `ntoskrnl!ZwQueryValueKey` at `0x14001daa1`
- `ntoskrnl!ZwClose` at `0x14001db51`
- `ntoskrnl!ZwClose` at `0x14001db51`
- `ntoskrnl!ZwOpenKey` at `0x14001d9c8`
- `ntoskrnl!ZwOpenKey` at `0x14001d9c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d98d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da04`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da78`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d98d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da04`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001da78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db96`

## string_xrefs

- `0x14001d95c`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 GetFullHostNameFromRegistry()
{
  _WORD *v0; // r14
  _DWORD *v1; // rsi
  __int64 v2; // r15
  _DWORD *v3; // rdi
  NTSTATUS v4; // ebx
  _WORD *v5; // rax
  _WORD *v6; // rbx
  int v7; // eax
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+38h] BYREF

  ResultLength = 0;
  KeyHandle = 0;
  v0 = 0;
  memset(&ObjectAttributes, 0, 44);
  v1 = 0;
  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) )
  {
    v3 = 0;
  }
  else
  {
    v3 = (_DWORD *)ALLOC_NONPAGED(512, 1767125580);
    if ( v3 )
    {
      RtlInitUnicodeString(&DestinationString, L"Hostname");
      if ( !ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v3, 0x200u, &ResultLength)
        && v3[1] == 1
        && v3[2] >= 4u )
      {
        v1 = (_DWORD *)ALLOC_NONPAGED(512, 1767125580);
        if ( v1 )
        {
          RtlInitUnicodeString(&DestinationString, L"Domain");
          v4 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v1, 0x200u, &ResultLength);
        }
        else
        {
          v4 = -1073741801;
        }
        v5 = (_WORD *)ALLOC_NONPAGED(1024, 1767125580);
        v0 = v5;
        if ( v5 )
        {
          memmove(v5, v3 + 3, (unsigned int)v3[2]);
          v0[(v3[2] >> 1) - 1] = 0;
          if ( !v4 && v1[1] == 1 && v1[2] >= 4u && *((_WORD *)v1 + 6) )
          {
            v6 = &v0[(v3[2] >> 1) - 1];
            *v6 = 46;
            memmove(v6 + 1, v1 + 3, (unsigned int)v1[2]);
            v6[(v1[2] >> 1) - 1 + 1] = 0;
          }
          v7 = StrLenW(v0);
          v2 = StrDupUnicodeToAscii(v0, (unsigned int)(2 * v7));
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v3 )
    ExFreePoolWithTag(v3 - 4, 0);
  if ( v1 )
    ExFreePoolWithTag(v1 - 4, 0);
  if ( v0 )
    ExFreePoolWithTag(v0 - 8, 0);
  return v2;
}

```

## disassembly

```asm
0x14001d940  mov     [rsp-28h+arg_10], rbx
0x14001d945  mov     [rsp-28h+arg_18], rsi
0x14001d94a  push    rbp
0x14001d94b  push    rdi
0x14001d94c  push    r12
0x14001d94e  push    r14
0x14001d950  push    r15
0x14001d952  mov     rbp, rsp
0x14001d955  sub     rsp, 70h
0x14001d959  xorps   xmm0, xmm0
0x14001d95c  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001d963  xor     r12d, r12d
0x14001d966  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001d96a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001d96e  xor     eax, eax
0x14001d970  mov     [rbp+arg_0], r12d
0x14001d974  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001d978  mov     [rbp+KeyHandle], r12
0x14001d97c  mov     r14d, r12d
0x14001d97f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001d983  mov     esi, r12d
0x14001d986  mov     r15d, r12d
0x14001d989  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001d98d  call    cs:__imp_RtlInitUnicodeString
0x14001d994  nop     dword ptr [rax+rax+00h]
0x14001d999  lea     rax, [rbp+DestinationString]
0x14001d99d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001d9a4  xorps   xmm0, xmm0
0x14001d9a7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001d9ab  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001d9af  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x14001d9b3  lea     edx, [r12+1]; DesiredAccess
0x14001d9b8  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14001d9bf  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001d9c3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d9c8  call    cs:__imp_ZwOpenKey
0x14001d9cf  nop     dword ptr [rax+rax+00h]
0x14001d9d4  test    eax, eax
0x14001d9d6  jnz     loc_14001DB45
0x14001d9dc  mov     ebx, 200h
0x14001d9e1  mov     edx, 6954324Ch
0x14001d9e6  mov     ecx, ebx
0x14001d9e8  call    ALLOC_NONPAGED
0x14001d9ed  mov     rdi, rax
0x14001d9f0  test    rax, rax
0x14001d9f3  jz      loc_14001DB48
0x14001d9f9  lea     rdx, aHostname; "Hostname"
0x14001da00  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001da04  call    cs:__imp_RtlInitUnicodeString
0x14001da0b  nop     dword ptr [rax+rax+00h]
0x14001da10  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001da14  lea     rax, [rbp+arg_0]
0x14001da18  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14001da1d  lea     r8d, [r12+2]; KeyValueInformationClass
0x14001da22  mov     r9, rdi; KeyValueInformation
0x14001da25  mov     [rsp+70h+Length], ebx; Length
0x14001da29  lea     rdx, [rbp+DestinationString]; ValueName
0x14001da2d  call    cs:__imp_ZwQueryValueKey
0x14001da34  nop     dword ptr [rax+rax+00h]
0x14001da39  test    eax, eax
0x14001da3b  jnz     loc_14001DB48
0x14001da41  cmp     dword ptr [rdi+4], 1
0x14001da45  jnz     loc_14001DB48
0x14001da4b  cmp     dword ptr [rdi+8], 4
0x14001da4f  jb      loc_14001DB48
0x14001da55  mov     r14d, 6954324Ch
0x14001da5b  mov     ecx, ebx
0x14001da5d  mov     edx, r14d
0x14001da60  call    ALLOC_NONPAGED
0x14001da65  mov     rsi, rax
0x14001da68  test    rax, rax
0x14001da6b  jz      short loc_14001DAB1
0x14001da6d  lea     rdx, aDomain; "Domain"
0x14001da74  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001da78  call    cs:__imp_RtlInitUnicodeString
0x14001da7f  nop     dword ptr [rax+rax+00h]
0x14001da84  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001da88  lea     rax, [rbp+arg_0]
0x14001da8c  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14001da91  lea     r8d, [r12+2]; KeyValueInformationClass
0x14001da96  mov     r9, rsi; KeyValueInformation
0x14001da99  mov     [rsp+70h+Length], ebx; Length
0x14001da9d  lea     rdx, [rbp+DestinationString]; ValueName
0x14001daa1  call    cs:__imp_ZwQueryValueKey
0x14001daa8  nop     dword ptr [rax+rax+00h]
0x14001daad  mov     ebx, eax
0x14001daaf  jmp     short loc_14001DAB6
0x14001dab1  mov     ebx, 0C0000017h
0x14001dab6  mov     edx, r14d
0x14001dab9  mov     ecx, 400h
0x14001dabe  call    ALLOC_NONPAGED
0x14001dac3  mov     r14, rax
0x14001dac6  test    rax, rax
0x14001dac9  jz      short loc_14001DB48
0x14001dacb  mov     r8d, [rdi+8]; Size
0x14001dacf  lea     rdx, [rdi+0Ch]; Src
0x14001dad3  mov     rcx, rax; void *
0x14001dad6  call    memmove
0x14001dadb  mov     ecx, [rdi+8]
0x14001dade  shr     ecx, 1
0x14001dae0  dec     ecx
0x14001dae2  mov     [r14+rcx*2], r12w
0x14001dae7  test    ebx, ebx
0x14001dae9  jnz     short loc_14001DB2D
0x14001daeb  cmp     dword ptr [rsi+4], 1
0x14001daef  jnz     short loc_14001DB2D
0x14001daf1  cmp     dword ptr [rsi+8], 4
0x14001daf5  jb      short loc_14001DB2D
0x14001daf7  lea     rdx, [rsi+0Ch]; Src
0x14001dafb  cmp     [rdx], r12w
0x14001daff  jz      short loc_14001DB2D
0x14001db01  mov     eax, [rdi+8]
0x14001db04  shr     eax, 1
0x14001db06  dec     eax
0x14001db08  lea     rbx, [r14+rax*2]
0x14001db0c  mov     word ptr [r14+rax*2], 2Eh ; '.'
0x14001db13  mov     r8d, [rsi+8]; Size
0x14001db17  lea     rcx, [rbx+2]; void *
0x14001db1b  call    memmove
0x14001db20  mov     eax, [rsi+8]
0x14001db23  shr     eax, 1
0x14001db25  dec     eax
0x14001db27  mov     [rbx+rax*2+2], r12w
0x14001db2d  mov     rcx, r14
0x14001db30  call    StrLenW
0x14001db35  mov     rcx, r14
0x14001db38  lea     edx, [rax+rax]
0x14001db3b  call    StrDupUnicodeToAscii
0x14001db40  mov     r15, rax
0x14001db43  jmp     short loc_14001DB48
0x14001db45  mov     rdi, r12
0x14001db48  mov     rcx, [rbp+KeyHandle]; Handle
0x14001db4c  test    rcx, rcx
0x14001db4f  jz      short loc_14001DB5D
0x14001db51  call    cs:__imp_ZwClose
0x14001db58  nop     dword ptr [rax+rax+00h]
0x14001db5d  test    rdi, rdi
0x14001db60  jz      short loc_14001DB74
0x14001db62  lea     rcx, [rdi-10h]; P
0x14001db66  xor     edx, edx; Tag
0x14001db68  call    cs:__imp_ExFreePoolWithTag
0x14001db6f  nop     dword ptr [rax+rax+00h]
0x14001db74  test    rsi, rsi
0x14001db77  jz      short loc_14001DB8B
0x14001db79  lea     rcx, [rsi-10h]; P
0x14001db7d  xor     edx, edx; Tag
0x14001db7f  call    cs:__imp_ExFreePoolWithTag
0x14001db86  nop     dword ptr [rax+rax+00h]
0x14001db8b  test    r14, r14
0x14001db8e  jz      short loc_14001DBA2
0x14001db90  lea     rcx, [r14-10h]; P
0x14001db94  xor     edx, edx; Tag
0x14001db96  call    cs:__imp_ExFreePoolWithTag
0x14001db9d  nop     dword ptr [rax+rax+00h]
0x14001dba2  lea     r11, [rsp+70h+var_s0]
0x14001dba7  mov     rax, r15
0x14001dbaa  mov     rbx, [r11+40h]
0x14001dbae  mov     rsi, [r11+48h]
0x14001dbb2  mov     rsp, r11
0x14001dbb5  pop     r15
0x14001dbb7  pop     r14
0x14001dbb9  pop     r12
0x14001dbbb  pop     rdi
0x14001dbbc  pop     rbp
0x14001dbbd  retn
```
