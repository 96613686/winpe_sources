# IopSymlinkQueryEnabledClasses

- ea: `0x140af17f8`
- end: `0x140af1982`
- name: `IopSymlinkQueryEnabledClasses`
- size: `394`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1407592c0`

## callees

- `0x1403f2d50`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dab70`
- `0x140af17f8`

## string_xrefs

- `0x140af188e`: `SymlinkLocalToLocalEvaluation`
- `0x140af18a4`: `SymlinkLocalToRemoteEvaluation`
- `0x140af18b8`: `SymlinkRemoteToRemoteEvaluation`
- `0x140af18cf`: `SymlinkRemoteToLocalEvaluation`

## pseudocode

```c
__int64 __fastcall IopSymlinkQueryEnabledClasses(PCWSTR SourceString)
{
  NTSTATUS v1; // esi
  __int32 v2; // ebx
  unsigned __int16 v3; // di
  ULONG ResultLength; // [rsp+30h] [rbp-99h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-89h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  UNICODE_STRING v9; // [rsp+80h] [rbp-49h] BYREF
  _DWORD v10[2]; // [rsp+90h] [rbp-39h]
  UNICODE_STRING v11; // [rsp+98h] [rbp-31h] BYREF
  int v12; // [rsp+A8h] [rbp-21h]
  UNICODE_STRING v13; // [rsp+B0h] [rbp-19h] BYREF
  int v14; // [rsp+C0h] [rbp-9h]
  UNICODE_STRING v15; // [rsp+C8h] [rbp-1h] BYREF
  int v16; // [rsp+D8h] [rbp+Fh]
  _BYTE KeyValueInformation[12]; // [rsp+E0h] [rbp+17h] BYREF
  int v18; // [rsp+ECh] [rbp+23h]

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    v2 = 0;
    RtlInitUnicodeString(&v9, L"SymlinkLocalToLocalEvaluation");
    v10[0] = 1;
    RtlInitUnicodeString(&v11, L"SymlinkLocalToRemoteEvaluation");
    v12 = 2;
    RtlInitUnicodeString(&v13, L"SymlinkRemoteToRemoteEvaluation");
    v14 = 8;
    RtlInitUnicodeString(&v15, L"SymlinkRemoteToLocalEvaluation");
    v3 = 0;
    v16 = 4;
    while ( v3 < 4u )
    {
      v1 = ZwQueryValueKey(
             KeyHandle,
             (UNICODE_STRING *)((char *)&v9 + 24 * v3),
             KeyValuePartialInformation,
             KeyValueInformation,
             0x14u,
             &ResultLength);
      if ( v1 < 0 )
        goto LABEL_9;
      if ( v18 )
        v2 += v10[6 * v3];
      ++v3;
    }
    _InterlockedExchange(&IopSymlinkEnabledTypes, v2);
  }
LABEL_9:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140af17f8  mov     [rsp-8+arg_8], rbx
0x140af17fd  mov     [rsp-8+arg_10], rsi
0x140af1802  push    rbp
0x140af1803  push    rdi
0x140af1804  push    r12
0x140af1806  push    r13
0x140af1808  push    r14
0x140af180a  lea     rbp, [rsp-37h]
0x140af180f  sub     rsp, 100h
0x140af1816  mov     rax, cs:__security_cookie
0x140af181d  xor     rax, rsp
0x140af1820  mov     [rbp+57h+var_28], rax
0x140af1824  xorps   xmm0, xmm0
0x140af1827  mov     [rsp+120h+KeyHandle], 0
0x140af1830  mov     rdx, rcx; SourceString
0x140af1833  mov     [rsp+120h+var_F0], 0
0x140af183b  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x140af1840  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x140af1845  call    RtlInitUnicodeString
0x140af184a  xor     eax, eax
0x140af184c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140af1854  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140af1858  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140af185c  lea     rax, [rsp+120h+DestinationString]
0x140af1861  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140af1869  xorps   xmm0, xmm0
0x140af186c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140af1870  mov     edx, 20019h; DesiredAccess
0x140af1875  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140af187a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140af187f  call    ZwOpenKey
0x140af1884  mov     esi, eax
0x140af1886  test    eax, eax
0x140af1888  js      loc_140AF1948
0x140af188e  lea     rdx, aSymlinklocalto; "SymlinkLocalToLocalEvaluation"
0x140af1895  xor     ebx, ebx
0x140af1897  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x140af189b  call    RtlInitUnicodeString
0x140af18a0  lea     r12d, [rbx+1]
0x140af18a4  lea     rdx, aSymlinklocalto_0; "SymlinkLocalToRemoteEvaluation"
0x140af18ab  mov     [rbp+57h+var_90], r12d
0x140af18af  lea     rcx, [rbp+57h+var_88]; DestinationString
0x140af18b3  call    RtlInitUnicodeString
0x140af18b8  lea     rdx, aSymlinkremotet; "SymlinkRemoteToRemoteEvaluation"
0x140af18bf  mov     [rbp+57h+var_78], 2
0x140af18c6  lea     rcx, [rbp+57h+var_70]; DestinationString
0x140af18ca  call    RtlInitUnicodeString
0x140af18cf  lea     rdx, aSymlinkremotet_0; "SymlinkRemoteToLocalEvaluation"
0x140af18d6  mov     [rbp+57h+var_60], 8
0x140af18dd  lea     rcx, [rbp+57h+var_58]; DestinationString
0x140af18e1  call    RtlInitUnicodeString
0x140af18e6  lea     r13d, [rbx+4]
0x140af18ea  xor     edi, edi
0x140af18ec  mov     [rbp+57h+var_48], r13d
0x140af18f0  cmp     di, r13w
0x140af18f4  jnb     short loc_140AF1942
0x140af18f6  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140af18fb  lea     rdx, [rbp+57h+var_A0]
0x140af18ff  movzx   eax, di
0x140af1902  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140af1906  mov     r8d, 2; KeyValueInformationClass
0x140af190c  lea     r14, [rax+rax*2]
0x140af1910  lea     rax, [rsp+120h+var_F0]
0x140af1915  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140af191a  lea     rdx, [rdx+r14*8]; ValueName
0x140af191e  mov     [rsp+120h+Length], 14h; Length
0x140af1926  call    ZwQueryValueKey
0x140af192b  mov     esi, eax
0x140af192d  test    eax, eax
0x140af192f  js      short loc_140AF1948
0x140af1931  cmp     [rbp+57h+var_34], 0
0x140af1935  jz      short loc_140AF193C
0x140af1937  add     ebx, [rbp+r14*8+57h+var_90]
0x140af193c  add     di, r12w
0x140af1940  jmp     short loc_140AF18F0
0x140af1942  xchg    ebx, cs:IopSymlinkEnabledTypes
0x140af1948  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140af194d  test    rcx, rcx
0x140af1950  jz      short loc_140AF1957
0x140af1952  call    ZwClose
0x140af1957  mov     eax, esi
0x140af1959  mov     rcx, [rbp+57h+var_28]
0x140af195d  xor     rcx, rsp; StackCookie
0x140af1960  call    __security_check_cookie
0x140af1965  lea     r11, [rsp+120h+var_20]
0x140af196d  mov     rbx, [r11+38h]
0x140af1971  mov     rsi, [r11+40h]
0x140af1975  mov     rsp, r11
0x140af1978  pop     r14
0x140af197a  pop     r13
0x140af197c  pop     r12
0x140af197e  pop     rdi
0x140af197f  pop     rbp
0x140af1980  retn
```
