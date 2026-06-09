# ndisIfLuidAllocatorSubsystemInitialize(void)

- ea: `0x14018e1a4`
- end: `0x14018e40d`
- name: `?ndisIfLuidAllocatorSubsystemInitialize@@YAJXZ`
- size: `617`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14018e618`

## callees

- `0x1400492e0`
- `0x1400493e0`
- `0x1400589d0`
- `0x140061340`
- `0x14008c550`
- `0x1400e62c0`
- `0x14018e1a4`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14018e1db`
- `ntoskrnl!KeInitializeMutex` at `0x14018e1db`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14018e1f4`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14018e1f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018e22c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018e22c`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14018e20a`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14018e20a`
- `ntoskrnl!ExAllocatePool2` at `0x14018e336`
- `ntoskrnl!ExAllocatePool2` at `0x14018e336`

## pseudocode

```c
NTSTATUS ndisIfLuidAllocatorSubsystemInitialize(void)
{
  NTSTATUS result; // eax
  __int64 v1; // rcx
  ULONG v2; // r14d
  unsigned __int16 Length; // r13
  wchar_t *Buffer; // r12
  size_t v5; // rbx
  __int64 Pool2; // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  PVOID v9; // rcx
  int v10; // ebx
  UNICODE_STRING Keyword; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING v12; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING KeyName; // [rsp+60h] [rbp-18h] BYREF
  int Status; // [rsp+B0h] [rbp+38h] BYREF
  PVOID KeyHandle; // [rsp+B8h] [rbp+40h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+C0h] [rbp+48h] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+C8h] [rbp+50h] BYREF

  Status = 0;
  qword_14011C9A8 = (__int64)&qword_14011C9A0;
  qword_14011C9A0 = (__int64)&qword_14011C9A0;
  KeInitializeMutex(&Mutex, 0xFFFFu);
  if ( !RtlCheckRegistryKey(1u, (PWSTR)L"Ndis\\IfTypes")
    || (result = RtlCreateRegistryKey(1u, (PWSTR)L"Ndis\\IfTypes"), result >= 0) )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"Ndis\\IfTypes");
    ConfigurationHandle = 0;
    NdisOpenProtocolConfiguration(&Status, &ConfigurationHandle, &DestinationString);
    if ( Status )
    {
      return NdisConvertNdisStatusToNtStatus((unsigned int)Status);
    }
    else
    {
      KeyHandle = 0;
      NdisOpenConfigurationKeyByIndex(&Status, ConfigurationHandle, 0, &KeyName, &KeyHandle);
      v1 = (unsigned int)Status;
      v2 = 1;
      if ( !Status )
      {
        while ( 1 )
        {
          Keyword.Buffer = (wchar_t *)L"IfType";
          ParameterValue = 0;
          *(_QWORD *)&Keyword.Length = 917516;
          NdisReadConfiguration(&Status, &ParameterValue, KeyHandle, &Keyword, NdisParameterInteger);
          if ( Status )
          {
            NdisCloseConfiguration(KeyHandle);
          }
          else
          {
            Length = ParameterValue->ParameterData.StringData.Length;
            v12.Buffer = (wchar_t *)L"IfUsedNetLuidIndices";
            *(_QWORD *)&v12.Length = 2752552;
            NdisReadConfiguration(&Status, &ParameterValue, KeyHandle, &v12, NdisParameterBinary);
            if ( Status )
            {
              Buffer = 0;
              v5 = 0;
            }
            else
            {
              Buffer = ParameterValue->ParameterData.StringData.Buffer;
              v5 = ParameterValue->ParameterData.StringData.Length;
            }
            Pool2 = ExAllocatePool2(64, (unsigned int)(2 * v5 + 64), 1718174798);
            v7 = Pool2;
            *(_WORD *)(Pool2 + 16) = Length;
            if ( (_DWORD)v5 )
            {
              *(_DWORD *)(Pool2 + 40) = v5;
              *(_QWORD *)(Pool2 + 48) = Pool2 + 64;
              *(_QWORD *)(Pool2 + 56) = Pool2 + v5 + 64;
              memmove((void *)(Pool2 + 64), Buffer, v5);
              memmove(*(void **)(v7 + 56), Buffer, v5);
            }
            v8 = qword_14011C9A0;
            if ( *(__int64 **)(qword_14011C9A0 + 8) != &qword_14011C9A0 )
              __fastfail(3u);
            v9 = KeyHandle;
            *(_QWORD *)v7 = qword_14011C9A0;
            *(_QWORD *)(v7 + 8) = &qword_14011C9A0;
            *(_QWORD *)(v8 + 8) = v7;
            qword_14011C9A0 = v7;
            NdisCloseConfiguration(v9);
          }
          KeyHandle = 0;
          NdisOpenConfigurationKeyByIndex(&Status, ConfigurationHandle, v2, &KeyName, &KeyHandle);
          v1 = (unsigned int)Status;
          if ( Status )
            break;
          ++v2;
        }
      }
      v10 = NdisConvertNdisStatusToNtStatus(v1);
      if ( ConfigurationHandle )
        NdisCloseConfiguration(ConfigurationHandle);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14018e1a4  push    rbp
0x14018e1a6  push    rbx
0x14018e1a7  push    rdi
0x14018e1a8  push    r12
0x14018e1aa  push    r13
0x14018e1ac  push    r14
0x14018e1ae  mov     rbp, rsp
0x14018e1b1  sub     rsp, 78h
0x14018e1b5  lea     r12, qword_14011C9A0
0x14018e1bc  xor     edi, edi
0x14018e1be  mov     edx, 0FFFFh; Level
0x14018e1c3  mov     [rbp+Status], edi
0x14018e1c6  lea     rcx, Mutex; Mutex
0x14018e1cd  mov     cs:qword_14011C9A8, r12
0x14018e1d4  mov     cs:qword_14011C9A0, r12
0x14018e1db  call    cs:__imp_KeInitializeMutex
0x14018e1e2  nop     dword ptr [rax+rax+00h]
0x14018e1e7  lea     rbx, Path; "Ndis\\IfTypes"
0x14018e1ee  mov     rdx, rbx; Path
0x14018e1f1  lea     ecx, [rdi+1]; RelativeTo
0x14018e1f4  call    cs:__imp_RtlCheckRegistryKey
0x14018e1fb  nop     dword ptr [rax+rax+00h]
0x14018e200  test    eax, eax
0x14018e202  jz      short loc_14018E21E
0x14018e204  mov     rdx, rbx; Path
0x14018e207  lea     ecx, [rdi+1]; RelativeTo
0x14018e20a  call    cs:__imp_RtlCreateRegistryKey
0x14018e211  nop     dword ptr [rax+rax+00h]
0x14018e216  test    eax, eax
0x14018e218  js      loc_14018E3FE
0x14018e21e  xorps   xmm0, xmm0
0x14018e221  lea     rcx, [rbp+DestinationString]; DestinationString
0x14018e225  mov     rdx, rbx; SourceString
0x14018e228  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14018e22c  call    cs:__imp_RtlInitUnicodeString
0x14018e233  nop     dword ptr [rax+rax+00h]
0x14018e238  lea     r8, [rbp+DestinationString]
0x14018e23c  mov     [rbp+ConfigurationHandle], rdi
0x14018e240  lea     rdx, [rbp+ConfigurationHandle]
0x14018e244  lea     rcx, [rbp+Status]
0x14018e248  call    NdisOpenProtocolConfiguration
0x14018e24d  mov     ecx, [rbp+Status]
0x14018e250  test    ecx, ecx
0x14018e252  jz      short loc_14018E25E
0x14018e254  call    NdisConvertNdisStatusToNtStatus
0x14018e259  jmp     loc_14018E3FE
0x14018e25e  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14018e262  lea     rax, [rbp+arg_8]
0x14018e266  lea     r9, [rbp+KeyName]; KeyName
0x14018e26a  mov     [rsp+78h+KeyHandle], rax; KeyHandle
0x14018e26f  xor     r8d, r8d; Index
0x14018e272  mov     [rbp+arg_8], rdi
0x14018e276  lea     rcx, [rbp+Status]; Status
0x14018e27a  call    NdisOpenConfigurationKeyByIndex
0x14018e27f  mov     ecx, [rbp+Status]
0x14018e282  mov     r14d, 1
0x14018e288  test    ecx, ecx
0x14018e28a  jnz     loc_14018E3E6
0x14018e290  mov     r8, [rbp+arg_8]; ConfigurationHandle
0x14018e294  lea     rax, aIftype; "IfType"
0x14018e29b  lea     r9, [rbp+Keyword]; Keyword
0x14018e29f  mov     [rbp+Keyword.Buffer], rax
0x14018e2a3  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14018e2a7  mov     [rbp+ParameterValue], rdi
0x14018e2ab  lea     rcx, [rbp+Status]; Status
0x14018e2af  mov     qword ptr [rbp+Keyword.Length], 0E000Ch
0x14018e2b7  mov     dword ptr [rsp+78h+KeyHandle], edi; ParameterType
0x14018e2bb  call    NdisReadConfiguration
0x14018e2c0  cmp     [rbp+Status], edi
0x14018e2c3  jz      short loc_14018E2D3
0x14018e2c5  mov     rcx, [rbp+arg_8]; ConfigurationHandle
0x14018e2c9  call    NdisCloseConfiguration
0x14018e2ce  jmp     loc_14018E3AF
0x14018e2d3  mov     rax, [rbp+ParameterValue]
0x14018e2d7  lea     r9, [rbp+var_38]; Keyword
0x14018e2db  mov     r8, [rbp+arg_8]; ConfigurationHandle
0x14018e2df  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14018e2e3  lea     rcx, [rbp+Status]; Status
0x14018e2e7  mov     dword ptr [rsp+78h+KeyHandle], 4; ParameterType
0x14018e2ef  movzx   r13d, word ptr [rax+8]
0x14018e2f4  lea     rax, aIfusednetluidi; "IfUsedNetLuidIndices"
0x14018e2fb  mov     [rbp+var_38.Buffer], rax
0x14018e2ff  mov     qword ptr [rbp+var_38.Length], 2A0028h
0x14018e307  call    NdisReadConfiguration
0x14018e30c  cmp     [rbp+Status], edi
0x14018e30f  jnz     short loc_14018E31F
0x14018e311  mov     rax, [rbp+ParameterValue]
0x14018e315  mov     r12, [rax+10h]
0x14018e319  movzx   ebx, word ptr [rax+8]
0x14018e31d  jmp     short loc_14018E324
0x14018e31f  mov     r12, rdi
0x14018e322  mov     ebx, edi
0x14018e324  lea     edx, ds:40h[rbx*2]
0x14018e32b  mov     ecx, 40h ; '@'
0x14018e330  mov     r8d, 6669444Eh
0x14018e336  call    cs:__imp_ExAllocatePool2
0x14018e33d  nop     dword ptr [rax+rax+00h]
0x14018e342  mov     rdi, rax
0x14018e345  mov     [rax+10h], r13w
0x14018e34a  test    ebx, ebx
0x14018e34c  jz      short loc_14018E37E
0x14018e34e  lea     rcx, [rax+40h]; void *
0x14018e352  mov     [rax+28h], ebx
0x14018e355  lea     r9, [rbx+40h]
0x14018e359  mov     [rax+30h], rcx
0x14018e35d  add     r9, rax
0x14018e360  mov     r8, rbx; Size
0x14018e363  mov     rdx, r12; Src
0x14018e366  mov     [rax+38h], r9
0x14018e36a  call    memmove
0x14018e36f  mov     rcx, [rdi+38h]; void *
0x14018e373  mov     r8, rbx; Size
0x14018e376  mov     rdx, r12; Src
0x14018e379  call    memmove
0x14018e37e  mov     rax, cs:qword_14011C9A0
0x14018e385  lea     r12, qword_14011C9A0
0x14018e38c  cmp     [rax+8], r12
0x14018e390  jnz     short loc_14018E3DF
0x14018e392  mov     rcx, [rbp+arg_8]; ConfigurationHandle
0x14018e396  mov     [rdi], rax
0x14018e399  mov     [rdi+8], r12
0x14018e39d  mov     [rax+8], rdi
0x14018e3a1  mov     cs:qword_14011C9A0, rdi
0x14018e3a8  call    NdisCloseConfiguration
0x14018e3ad  xor     edi, edi
0x14018e3af  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14018e3b3  lea     rax, [rbp+arg_8]
0x14018e3b7  lea     r9, [rbp+KeyName]; KeyName
0x14018e3bb  mov     [rsp+78h+KeyHandle], rax; KeyHandle
0x14018e3c0  mov     r8d, r14d; Index
0x14018e3c3  mov     [rbp+arg_8], rdi
0x14018e3c7  lea     rcx, [rbp+Status]; Status
0x14018e3cb  call    NdisOpenConfigurationKeyByIndex
0x14018e3d0  mov     ecx, [rbp+Status]
0x14018e3d3  test    ecx, ecx
0x14018e3d5  jnz     short loc_14018E3E6
0x14018e3d7  inc     r14d
0x14018e3da  jmp     loc_14018E290
0x14018e3df  mov     ecx, 3
0x14018e3e4  int     29h; Win8: RtlFailFast(ecx)
0x14018e3e6  call    NdisConvertNdisStatusToNtStatus
0x14018e3eb  mov     ebx, eax
0x14018e3ed  cmp     [rbp+ConfigurationHandle], rdi
0x14018e3f1  jz      short loc_14018E3FC
0x14018e3f3  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x14018e3f7  call    NdisCloseConfiguration
0x14018e3fc  mov     eax, ebx
0x14018e3fe  add     rsp, 78h
0x14018e402  pop     r14
0x14018e404  pop     r13
0x14018e406  pop     r12
0x14018e408  pop     rdi
0x14018e409  pop     rbx
0x14018e40a  pop     rbp
0x14018e40b  retn
```
