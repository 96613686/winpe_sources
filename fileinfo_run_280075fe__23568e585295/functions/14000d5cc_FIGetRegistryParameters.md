# FIGetRegistryParameters

- ea: `0x14000d5cc`
- end: `0x14000d8c6`
- name: `FIGetRegistryParameters`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018078`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x14000d504`
- `0x14000d5cc`
- `0x140014940`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d89b`
- `ntoskrnl!ZwClose` at `0x14000d89b`
- `ntoskrnl!ZwOpenKey` at `0x14000d68a`
- `ntoskrnl!ZwOpenKey` at `0x14000d68a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d64b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d64b`

## string_xrefs

- `0x14000d603`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters`
- `0x14000d789`: `FIDbgStream2ndAttempt`
- `0x14000d7a9`: `FIDbgVolume2ndAttempt`

## pseudocode

```c
__int64 __fastcall FIGetRegistryParameters(_DWORD *a1)
{
  _DWORD *v1; // rdi
  NTSTATUS v2; // ebx
  int v4; // [rsp+20h] [rbp-89h]
  int v5; // [rsp+20h] [rbp-89h]
  int v6; // [rsp+20h] [rbp-89h]
  int v7; // [rsp+20h] [rbp-89h]
  int v8; // [rsp+20h] [rbp-89h]
  int v9; // [rsp+20h] [rbp-89h]
  int v10; // [rsp+20h] [rbp-89h]
  int v11; // [rsp+20h] [rbp-89h]
  int v12; // [rsp+20h] [rbp-89h]
  int v13; // [rsp+20h] [rbp-89h]
  int v14; // [rsp+20h] [rbp-89h]
  void *KeyHandle; // [rsp+40h] [rbp-69h] BYREF
  int v16; // [rsp+48h] [rbp-61h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-29h] BYREF
  _BYTE KeyValueInformation[56]; // [rsp+90h] [rbp-19h] BYREF

  v1 = a1 + 2;
  KeyHandle = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  DestinationString = 0;
  *a1 = 0;
  a1[1] = 30000;
  a1[2] = 180000;
  dword_1400099E8 = 100;
  dword_1400099DC = 100;
  dword_1400099CC = 0;
  Count = 0x7FFFFFFF;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\PrefetchParameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    FIGetParameter(KeyHandle, v4, KeyValueInformation);
    FIGetParameter(KeyHandle, v5, KeyValueInformation);
    FIGetParameter(KeyHandle, v6, KeyValueInformation);
    FIGetParameter(KeyHandle, v7, KeyValueInformation);
    FIGetParameter(KeyHandle, v8, KeyValueInformation);
    FIGetParameter(KeyHandle, v9, KeyValueInformation);
    FIGetParameter(KeyHandle, v10, KeyValueInformation);
    FIGetParameter(KeyHandle, v11, KeyValueInformation);
    FIGetParameter(KeyHandle, v12, KeyValueInformation);
    v16 = 0;
    FIGetParameter(KeyHandle, v13, KeyValueInformation);
    if ( v16 )
      FIFileInfoStateChange(1, 3);
    v16 = 0;
    FIGetParameter(KeyHandle, v14, KeyValueInformation);
    if ( v16 == 1 )
    {
      FILockExclusiveAcquire(&qword_140009A78);
      if ( (dword_140009A74 & 1) == 0 )
      {
        dword_140009A70 = 1;
        dword_140009A74 |= 1u;
      }
      FILockExclusiveRelease(&qword_140009A78);
    }
    if ( *v1 < 0xAu )
      *v1 = 10;
    if ( (unsigned int)dword_1400099E4 > 0x64 )
      dword_1400099E4 = 100;
    if ( (unsigned int)dword_1400099D8 > 0x64 )
      dword_1400099D8 = 100;
    if ( (unsigned int)dword_1400099F4 > 0x64 )
      dword_1400099F4 = 100;
    if ( (unsigned int)dword_1400099F0 > 0x64 )
      dword_1400099F0 = 100;
    v2 = 0;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000d5cc  push    rbp
0x14000d5ce  push    rbx
0x14000d5cf  push    rsi
0x14000d5d0  push    rdi
0x14000d5d1  push    r14
0x14000d5d3  push    r15
0x14000d5d5  lea     rbp, [rsp-2Fh]
0x14000d5da  sub     rsp, 0D8h
0x14000d5e1  mov     rax, cs:__security_cookie
0x14000d5e8  xor     rax, rsp
0x14000d5eb  mov     [rbp+57h+var_38], rax
0x14000d5ef  xor     eax, eax
0x14000d5f1  lea     rdi, [rcx+8]
0x14000d5f5  xorps   xmm0, xmm0
0x14000d5f8  mov     [rbp+57h+KeyHandle], rax
0x14000d5fc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000d600  mov     rsi, rcx
0x14000d603  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d60a  lea     r15d, [rax+64h]
0x14000d60e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000d612  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000d616  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000d61a  mov     [rcx], eax
0x14000d61c  mov     dword ptr [rcx+4], 7530h
0x14000d623  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000d627  mov     dword ptr [rdi], 2BF20h
0x14000d62d  mov     cs:dword_1400099E8, r15d
0x14000d634  mov     cs:dword_1400099DC, r15d
0x14000d63b  mov     cs:dword_1400099CC, eax
0x14000d641  mov     cs:Count, 7FFFFFFFh
0x14000d64b  call    cs:__imp_RtlInitUnicodeString
0x14000d652  nop     dword ptr [rax+rax+00h]
0x14000d657  lea     rax, [rbp+57h+DestinationString]
0x14000d65b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d662  xorps   xmm0, xmm0
0x14000d665  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d669  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d66d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000d675  mov     edx, 0F003Fh; DesiredAccess
0x14000d67a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d681  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d685  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d68a  call    cs:__imp_ZwOpenKey
0x14000d691  nop     dword ptr [rax+rax+00h]
0x14000d696  mov     ebx, eax
0x14000d698  test    eax, eax
0x14000d69a  js      loc_14000D892
0x14000d6a0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d6a4  lea     rax, [rbp+57h+var_70]
0x14000d6a8  mov     r9, rsi
0x14000d6ab  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d6b0  lea     rdx, aBasetime; "BaseTime"
0x14000d6b7  call    FIGetParameter
0x14000d6bc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d6c0  lea     rax, [rbp+57h+var_70]
0x14000d6c4  lea     r9, [rsi+4]
0x14000d6c8  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d6cd  lea     rdx, aFiprefetchdela; "FIPrefetchDelayMs"
0x14000d6d4  call    FIGetParameter
0x14000d6d9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d6dd  lea     rax, [rbp+57h+var_70]
0x14000d6e1  mov     r9, rdi
0x14000d6e4  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d6e9  lea     rdx, aFifsopmaxblock; "FIFSOpMaxBlockTimeMs"
0x14000d6f0  call    FIGetParameter
0x14000d6f5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d6f9  lea     rax, [rbp+57h+var_70]
0x14000d6fd  lea     r9, dword_1400099CC
0x14000d704  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d709  lea     rdx, aFiblockdbgbrea; "FIBlockDbgBreak"
0x14000d710  call    FIGetParameter
0x14000d715  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d719  lea     rax, [rbp+57h+var_70]
0x14000d71d  lea     r9, Count
0x14000d724  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d729  lea     rdx, aFimaxquerywork; "FIMaxQueryWorkers"
0x14000d730  call    FIGetParameter
0x14000d735  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d739  lea     rax, [rbp+57h+var_70]
0x14000d73d  lea     r9, dword_1400099E4
0x14000d744  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d749  lea     rdx, aFidbgstreamfai; "FIDbgStreamFailurePercent"
0x14000d750  call    FIGetParameter
0x14000d755  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d759  lea     rax, [rbp+57h+var_70]
0x14000d75d  lea     r9, dword_1400099D8
0x14000d764  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d769  lea     rdx, aFidbgvolumefai; "FIDbgVolumeFailurePercent"
0x14000d770  call    FIGetParameter
0x14000d775  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d779  lea     rax, [rbp+57h+var_70]
0x14000d77d  lea     r9, dword_1400099F4
0x14000d784  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d789  lea     rdx, aFidbgstream2nd; "FIDbgStream2ndAttempt"
0x14000d790  call    FIGetParameter
0x14000d795  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d799  lea     rax, [rbp+57h+var_70]
0x14000d79d  lea     r9, dword_1400099F0
0x14000d7a4  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d7a9  lea     rdx, aFidbgvolume2nd; "FIDbgVolume2ndAttempt"
0x14000d7b0  call    FIGetParameter
0x14000d7b5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d7b9  lea     rax, [rbp+57h+var_70]
0x14000d7bd  lea     r9, [rbp+57h+var_B8]
0x14000d7c1  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d7c6  lea     rdx, aFiforcednametr; "FIForcedNameTracking"
0x14000d7cd  mov     [rbp+57h+var_B8], 0
0x14000d7d4  call    FIGetParameter
0x14000d7d9  cmp     [rbp+57h+var_B8], 0
0x14000d7dd  lea     ebx, [r15-63h]
0x14000d7e1  jz      short loc_14000D7ED
0x14000d7e3  lea     edx, [rbx+2]
0x14000d7e6  mov     ecx, ebx
0x14000d7e8  call    FIFileInfoStateChange
0x14000d7ed  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d7f1  lea     rax, [rbp+57h+var_70]
0x14000d7f5  lea     r9, [rbp+57h+var_B8]
0x14000d7f9  mov     [rsp+100h+KeyValueInformation], rax; KeyValueInformation
0x14000d7fe  lea     rdx, aSftracingstate; "SfTracingState"
0x14000d805  mov     [rbp+57h+var_B8], 0
0x14000d80c  call    FIGetParameter
0x14000d811  cmp     [rbp+57h+var_B8], ebx
0x14000d814  jnz     short loc_14000D845
0x14000d816  lea     rsi, qword_140009A78
0x14000d81d  mov     rcx, rsi
0x14000d820  call    FILockExclusiveAcquire
0x14000d825  mov     eax, cs:dword_140009A74
0x14000d82b  mov     rcx, rsi
0x14000d82e  test    bl, al
0x14000d830  jnz     short loc_14000D840
0x14000d832  or      eax, ebx
0x14000d834  mov     cs:dword_140009A70, ebx
0x14000d83a  mov     cs:dword_140009A74, eax
0x14000d840  call    FILockExclusiveRelease
0x14000d845  cmp     dword ptr [rdi], 0Ah
0x14000d848  jnb     short loc_14000D850
0x14000d84a  mov     dword ptr [rdi], 0Ah
0x14000d850  cmp     cs:dword_1400099E4, r15d
0x14000d857  jbe     short loc_14000D860
0x14000d859  mov     cs:dword_1400099E4, r15d
0x14000d860  cmp     cs:dword_1400099D8, r15d
0x14000d867  jbe     short loc_14000D870
0x14000d869  mov     cs:dword_1400099D8, r15d
0x14000d870  cmp     cs:dword_1400099F4, r15d
0x14000d877  jbe     short loc_14000D880
0x14000d879  mov     cs:dword_1400099F4, r15d
0x14000d880  cmp     cs:dword_1400099F0, r15d
0x14000d887  jbe     short loc_14000D890
0x14000d889  mov     cs:dword_1400099F0, r15d
0x14000d890  xor     ebx, ebx
0x14000d892  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d896  test    rcx, rcx
0x14000d899  jz      short loc_14000D8A7
0x14000d89b  call    cs:__imp_ZwClose
0x14000d8a2  nop     dword ptr [rax+rax+00h]
0x14000d8a7  mov     eax, ebx
0x14000d8a9  mov     rcx, [rbp+57h+var_38]
0x14000d8ad  xor     rcx, rsp; StackCookie
0x14000d8b0  call    __security_check_cookie
0x14000d8b5  add     rsp, 0D8h
0x14000d8bc  pop     r15
0x14000d8be  pop     r14
0x14000d8c0  pop     rdi
0x14000d8c1  pop     rsi
0x14000d8c2  pop     rbx
0x14000d8c3  pop     rbp
0x14000d8c4  retn
```
