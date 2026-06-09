# ndisIfLuidAllocatorSubsystemInitialize(void)

- ea: `0x1401941b4`
- end: `0x14019441d`
- name: `?ndisIfLuidAllocatorSubsystemInitialize@@YAJXZ`
- size: `617`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140194628`

## callees

- `0x14004dc60`
- `0x14004dd60`
- `0x14005d540`
- `0x1400663c0`
- `0x140090f90`
- `0x1400eb4c0`
- `0x1401941b4`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1401941eb`
- `ntoskrnl!KeInitializeMutex` at `0x1401941eb`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140194204`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140194204`
- `ntoskrnl!RtlInitUnicodeString` at `0x14019423c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14019423c`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14019421a`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14019421a`
- `ntoskrnl!ExAllocatePool2` at `0x140194346`
- `ntoskrnl!ExAllocatePool2` at `0x140194346`

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
  qword_1401229A8 = (__int64)&qword_1401229A0;
  qword_1401229A0 = (__int64)&qword_1401229A0;
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
            v8 = qword_1401229A0;
            if ( *(__int64 **)(qword_1401229A0 + 8) != &qword_1401229A0 )
              __fastfail(3u);
            v9 = KeyHandle;
            *(_QWORD *)v7 = qword_1401229A0;
            *(_QWORD *)(v7 + 8) = &qword_1401229A0;
            *(_QWORD *)(v8 + 8) = v7;
            qword_1401229A0 = v7;
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
0x1401941b4  push    rbp
0x1401941b6  push    rbx
0x1401941b7  push    rdi
0x1401941b8  push    r12
0x1401941ba  push    r13
0x1401941bc  push    r14
0x1401941be  mov     rbp, rsp
0x1401941c1  sub     rsp, 78h
0x1401941c5  lea     r12, qword_1401229A0
0x1401941cc  xor     edi, edi
0x1401941ce  mov     edx, 0FFFFh; Level
0x1401941d3  mov     [rbp+Status], edi
0x1401941d6  lea     rcx, Mutex; Mutex
0x1401941dd  mov     cs:qword_1401229A8, r12
0x1401941e4  mov     cs:qword_1401229A0, r12
0x1401941eb  call    cs:__imp_KeInitializeMutex
0x1401941f2  nop     dword ptr [rax+rax+00h]
0x1401941f7  lea     rbx, Path; "Ndis\\IfTypes"
0x1401941fe  mov     rdx, rbx; Path
0x140194201  lea     ecx, [rdi+1]; RelativeTo
0x140194204  call    cs:__imp_RtlCheckRegistryKey
0x14019420b  nop     dword ptr [rax+rax+00h]
0x140194210  test    eax, eax
0x140194212  jz      short loc_14019422E
0x140194214  mov     rdx, rbx; Path
0x140194217  lea     ecx, [rdi+1]; RelativeTo
0x14019421a  call    cs:__imp_RtlCreateRegistryKey
0x140194221  nop     dword ptr [rax+rax+00h]
0x140194226  test    eax, eax
0x140194228  js      loc_14019440E
0x14019422e  xorps   xmm0, xmm0
0x140194231  lea     rcx, [rbp+DestinationString]; DestinationString
0x140194235  mov     rdx, rbx; SourceString
0x140194238  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14019423c  call    cs:__imp_RtlInitUnicodeString
0x140194243  nop     dword ptr [rax+rax+00h]
0x140194248  lea     r8, [rbp+DestinationString]
0x14019424c  mov     [rbp+ConfigurationHandle], rdi
0x140194250  lea     rdx, [rbp+ConfigurationHandle]
0x140194254  lea     rcx, [rbp+Status]
0x140194258  call    NdisOpenProtocolConfiguration
0x14019425d  mov     ecx, [rbp+Status]
0x140194260  test    ecx, ecx
0x140194262  jz      short loc_14019426E
0x140194264  call    NdisConvertNdisStatusToNtStatus
0x140194269  jmp     loc_14019440E
0x14019426e  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140194272  lea     rax, [rbp+arg_8]
0x140194276  lea     r9, [rbp+KeyName]; KeyName
0x14019427a  mov     [rsp+78h+KeyHandle], rax; KeyHandle
0x14019427f  xor     r8d, r8d; Index
0x140194282  mov     [rbp+arg_8], rdi
0x140194286  lea     rcx, [rbp+Status]; Status
0x14019428a  call    NdisOpenConfigurationKeyByIndex
0x14019428f  mov     ecx, [rbp+Status]
0x140194292  mov     r14d, 1
0x140194298  test    ecx, ecx
0x14019429a  jnz     loc_1401943F6
0x1401942a0  mov     r8, [rbp+arg_8]; ConfigurationHandle
0x1401942a4  lea     rax, aIftype; "IfType"
0x1401942ab  lea     r9, [rbp+Keyword]; Keyword
0x1401942af  mov     [rbp+Keyword.Buffer], rax
0x1401942b3  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x1401942b7  mov     [rbp+ParameterValue], rdi
0x1401942bb  lea     rcx, [rbp+Status]; Status
0x1401942bf  mov     qword ptr [rbp+Keyword.Length], 0E000Ch
0x1401942c7  mov     dword ptr [rsp+78h+KeyHandle], edi; ParameterType
0x1401942cb  call    NdisReadConfiguration
0x1401942d0  cmp     [rbp+Status], edi
0x1401942d3  jz      short loc_1401942E3
0x1401942d5  mov     rcx, [rbp+arg_8]; ConfigurationHandle
0x1401942d9  call    NdisCloseConfiguration
0x1401942de  jmp     loc_1401943BF
0x1401942e3  mov     rax, [rbp+ParameterValue]
0x1401942e7  lea     r9, [rbp+var_38]; Keyword
0x1401942eb  mov     r8, [rbp+arg_8]; ConfigurationHandle
0x1401942ef  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x1401942f3  lea     rcx, [rbp+Status]; Status
0x1401942f7  mov     dword ptr [rsp+78h+KeyHandle], 4; ParameterType
0x1401942ff  movzx   r13d, word ptr [rax+8]
0x140194304  lea     rax, aIfusednetluidi; "IfUsedNetLuidIndices"
0x14019430b  mov     [rbp+var_38.Buffer], rax
0x14019430f  mov     qword ptr [rbp+var_38.Length], 2A0028h
0x140194317  call    NdisReadConfiguration
0x14019431c  cmp     [rbp+Status], edi
0x14019431f  jnz     short loc_14019432F
0x140194321  mov     rax, [rbp+ParameterValue]
0x140194325  mov     r12, [rax+10h]
0x140194329  movzx   ebx, word ptr [rax+8]
0x14019432d  jmp     short loc_140194334
0x14019432f  mov     r12, rdi
0x140194332  mov     ebx, edi
0x140194334  lea     edx, ds:40h[rbx*2]
0x14019433b  mov     ecx, 40h ; '@'
0x140194340  mov     r8d, 6669444Eh
0x140194346  call    cs:__imp_ExAllocatePool2
0x14019434d  nop     dword ptr [rax+rax+00h]
0x140194352  mov     rdi, rax
0x140194355  mov     [rax+10h], r13w
0x14019435a  test    ebx, ebx
0x14019435c  jz      short loc_14019438E
0x14019435e  lea     rcx, [rax+40h]; void *
0x140194362  mov     [rax+28h], ebx
0x140194365  lea     r9, [rbx+40h]
0x140194369  mov     [rax+30h], rcx
0x14019436d  add     r9, rax
0x140194370  mov     r8, rbx; Size
0x140194373  mov     rdx, r12; Src
0x140194376  mov     [rax+38h], r9
0x14019437a  call    memmove
0x14019437f  mov     rcx, [rdi+38h]; void *
0x140194383  mov     r8, rbx; Size
0x140194386  mov     rdx, r12; Src
0x140194389  call    memmove
0x14019438e  mov     rax, cs:qword_1401229A0
0x140194395  lea     r12, qword_1401229A0
0x14019439c  cmp     [rax+8], r12
0x1401943a0  jnz     short loc_1401943EF
0x1401943a2  mov     rcx, [rbp+arg_8]; ConfigurationHandle
0x1401943a6  mov     [rdi], rax
0x1401943a9  mov     [rdi+8], r12
0x1401943ad  mov     [rax+8], rdi
0x1401943b1  mov     cs:qword_1401229A0, rdi
0x1401943b8  call    NdisCloseConfiguration
0x1401943bd  xor     edi, edi
0x1401943bf  mov     rdx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1401943c3  lea     rax, [rbp+arg_8]
0x1401943c7  lea     r9, [rbp+KeyName]; KeyName
0x1401943cb  mov     [rsp+78h+KeyHandle], rax; KeyHandle
0x1401943d0  mov     r8d, r14d; Index
0x1401943d3  mov     [rbp+arg_8], rdi
0x1401943d7  lea     rcx, [rbp+Status]; Status
0x1401943db  call    NdisOpenConfigurationKeyByIndex
0x1401943e0  mov     ecx, [rbp+Status]
0x1401943e3  test    ecx, ecx
0x1401943e5  jnz     short loc_1401943F6
0x1401943e7  inc     r14d
0x1401943ea  jmp     loc_1401942A0
0x1401943ef  mov     ecx, 3
0x1401943f4  int     29h; Win8: RtlFailFast(ecx)
0x1401943f6  call    NdisConvertNdisStatusToNtStatus
0x1401943fb  mov     ebx, eax
0x1401943fd  cmp     [rbp+ConfigurationHandle], rdi
0x140194401  jz      short loc_14019440C
0x140194403  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x140194407  call    NdisCloseConfiguration
0x14019440c  mov     eax, ebx
0x14019440e  add     rsp, 78h
0x140194412  pop     r14
0x140194414  pop     r13
0x140194416  pop     r12
0x140194418  pop     rdi
0x140194419  pop     rbx
0x14019441a  pop     rbp
0x14019441b  retn
```
