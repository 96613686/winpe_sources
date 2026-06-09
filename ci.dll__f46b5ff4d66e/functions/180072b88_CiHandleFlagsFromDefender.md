# CiHandleFlagsFromDefender

- ea: `0x180072b88`
- end: `0x180072d81`
- name: `CiHandleFlagsFromDefender`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007281c`

## callees

- `0x180059ed0`
- `0x180064c24`
- `0x180072720`
- `0x180072b88`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180072c50`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180072c50`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072d1b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072d1b`

## string_xrefs

- `0x180072c24`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180072cd5`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180072cfb`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
void __fastcall CiHandleFlagsFromDefender(__int64 a1, char a2, _BYTE *a3, _DWORD *a4, _BYTE *a5)
{
  _BYTE *v5; // r14
  int RegistryValue; // eax
  unsigned int v11; // r15d
  __int64 v12; // rax
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 ValueData; // [rsp+48h] [rbp-18h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+38h] BYREF
  int v17; // [rsp+A0h] [rbp+40h] BYREF

  v5 = a5;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  ValueData = 0;
  v13 = 0;
  *a3 = 0;
  if ( (a2 & 4) != 0 && _InterlockedCompareExchange(&g_ReceivedSignalFromDefender, 1, 2) == 2 )
  {
    *a4 = 1;
    *a3 = 1;
    *v5 = 1;
  }
  if ( (a2 & 2) != 0 )
  {
    RegistryValue = CipGetRegistryValue(
                      0,
                      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                      (__int64)L"VerifiedAndReputableIgnoreAutoOptOut",
                      0,
                      (__int64)&v16,
                      4,
                      (__int64)&v17);
    v11 = v16;
    if ( RegistryValue < 0 )
      v11 = 0;
    if ( v11 )
      goto LABEL_16;
    KeQuerySystemTimePrecise(&v13);
    if ( (int)CiGetOOBECompleteTime(&v15) < 0 )
    {
      if ( (int)CipGetRegistryValue(
                  0,
                  L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                  (__int64)L"OOBESafetyTimer",
                  1,
                  (__int64)&ValueData,
                  8,
                  (__int64)&v17) < 0 )
      {
        ValueData = v13;
        RtlWriteRegistryValue(
          0,
          L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
          L"OOBESafetyTimer",
          3u,
          &ValueData,
          8u);
        goto LABEL_16;
      }
      if ( v13 <= ValueData )
      {
LABEL_12:
        if ( _InterlockedExchange(&g_ReceivedSignalFromDefender, 0) )
        {
          *a4 = 0;
          *a3 = 1;
          *v5 = 0;
        }
        goto LABEL_17;
      }
      v12 = v13 - ValueData;
    }
    else
    {
      if ( v13 <= v15 )
        goto LABEL_12;
      v12 = v13 - v15;
    }
    if ( v12 >= 864000000000LL )
      goto LABEL_12;
LABEL_16:
    CiInstrumentDefenderTriggeredNWSwitchOffIgnored(v11, v15, ValueData);
  }
LABEL_17:
  if ( (a2 & 8) != 0 )
    *(_BYTE *)(a1 + 2092) = 1;
}

```

## disassembly

```asm
0x180072b88  mov     [rsp-28h+arg_0], rbx
0x180072b8d  mov     [rsp-28h+arg_18], rsi
0x180072b92  push    rbp
0x180072b93  push    rdi
0x180072b94  push    r13
0x180072b96  push    r14
0x180072b98  push    r15
0x180072b9a  mov     rbp, rsp
0x180072b9d  sub     rsp, 60h
0x180072ba1  mov     r14, [rbp+arg_20]
0x180072ba5  mov     r13, rcx
0x180072ba8  mov     [rbp+arg_8], 0
0x180072baf  mov     ecx, 1
0x180072bb4  mov     [rbp+arg_10], 0
0x180072bbb  mov     rsi, r9
0x180072bbe  mov     [rbp+var_10], 0
0x180072bc6  mov     rbx, r8
0x180072bc9  mov     [rbp+var_18], 0
0x180072bd1  mov     rdi, rdx
0x180072bd4  mov     [rbp+var_20], 0
0x180072bdc  mov     byte ptr [r8], 0
0x180072be0  test    dl, 4
0x180072be3  jz      short loc_180072BFB
0x180072be5  lea     eax, [rcx+1]
0x180072be8  lock cmpxchg cs:g_ReceivedSignalFromDefender, ecx
0x180072bf0  jnz     short loc_180072BFB
0x180072bf2  mov     [r9], ecx
0x180072bf5  mov     [r8], cl
0x180072bf8  mov     [r14], cl
0x180072bfb  test    dil, 2
0x180072bff  jz      loc_180072D40
0x180072c05  lea     rax, [rbp+arg_10]
0x180072c09  xor     r9d, r9d
0x180072c0c  mov     [rsp+60h+var_30], rax
0x180072c11  lea     r8, aVerifiedandrep_4; "VerifiedAndReputableIgnoreAutoOptOut"
0x180072c18  lea     rax, [rbp+arg_8]
0x180072c1c  mov     [rsp+60h+ValueLength], 4
0x180072c24  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072c2b  mov     [rsp+60h+ValueData], rax
0x180072c30  xor     ecx, ecx
0x180072c32  call    CipGetRegistryValue
0x180072c37  mov     r15d, [rbp+arg_8]
0x180072c3b  xor     ecx, ecx
0x180072c3d  test    eax, eax
0x180072c3f  cmovs   r15d, ecx
0x180072c43  test    r15d, r15d
0x180072c46  jnz     loc_180072D27
0x180072c4c  lea     rcx, [rbp+var_20]
0x180072c50  call    cs:__imp_KeQuerySystemTimePrecise
0x180072c57  nop     dword ptr [rax+rax+00h]
0x180072c5c  lea     rcx, [rbp+var_10]
0x180072c60  call    CiGetOOBECompleteTime
0x180072c65  test    eax, eax
0x180072c67  js      short loc_180072CB3
0x180072c69  mov     r9, [rbp+var_20]
0x180072c6d  cmp     r9, [rbp+var_10]
0x180072c71  jle     short loc_180072C8D
0x180072c73  mov     rax, r9
0x180072c76  sub     rax, [rbp+var_10]
0x180072c7a  mov     rcx, 0C92A69C000h
0x180072c84  cmp     rax, rcx
0x180072c87  jl      loc_180072D2B
0x180072c8d  xor     eax, eax
0x180072c8f  mov     ecx, 1
0x180072c94  xchg    eax, cs:g_ReceivedSignalFromDefender
0x180072c9a  test    eax, eax
0x180072c9c  jz      loc_180072D40
0x180072ca2  mov     dword ptr [rsi], 0
0x180072ca8  mov     [rbx], cl
0x180072caa  mov     byte ptr [r14], 0
0x180072cae  jmp     loc_180072D40
0x180072cb3  lea     rax, [rbp+arg_10]
0x180072cb7  mov     r9d, 1
0x180072cbd  mov     [rsp+60h+var_30], rax
0x180072cc2  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180072cc9  lea     rax, [rbp+var_18]
0x180072ccd  mov     [rsp+60h+ValueLength], 8
0x180072cd5  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072cdc  mov     [rsp+60h+ValueData], rax
0x180072ce1  xor     ecx, ecx
0x180072ce3  call    CipGetRegistryValue
0x180072ce8  test    eax, eax
0x180072cea  jns     short loc_180072D67
0x180072cec  mov     rax, [rbp+var_20]
0x180072cf0  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180072cf7  mov     [rbp+var_18], rax
0x180072cfb  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072d02  lea     rax, [rbp+var_18]
0x180072d06  mov     [rsp+60h+ValueLength], 8; ValueLength
0x180072d0e  mov     r9d, 3; ValueType
0x180072d14  mov     [rsp+60h+ValueData], rax; ValueData
0x180072d19  xor     ecx, ecx; RelativeTo
0x180072d1b  call    cs:__imp_RtlWriteRegistryValue
0x180072d22  nop     dword ptr [rax+rax+00h]
0x180072d27  mov     r9, [rbp+var_20]
0x180072d2b  mov     r8, [rbp+var_18]
0x180072d2f  mov     ecx, r15d
0x180072d32  mov     rdx, [rbp+var_10]
0x180072d36  call    CiInstrumentDefenderTriggeredNWSwitchOffIgnored
0x180072d3b  mov     ecx, 1
0x180072d40  test    dil, 8
0x180072d44  jz      short loc_180072D4D
0x180072d46  mov     [r13+82Ch], cl
0x180072d4d  lea     r11, [rsp+60h+var_s0]
0x180072d52  mov     rbx, [r11+30h]
0x180072d56  mov     rsi, [r11+48h]
0x180072d5a  mov     rsp, r11
0x180072d5d  pop     r15
0x180072d5f  pop     r14
0x180072d61  pop     r13
0x180072d63  pop     rdi
0x180072d64  pop     rbp
0x180072d65  retn
0x180072d67  mov     r9, [rbp+var_20]
0x180072d6b  cmp     r9, [rbp+var_18]
0x180072d6f  jle     loc_180072C8D
0x180072d75  mov     rax, r9
0x180072d78  sub     rax, [rbp+var_18]
0x180072d7c  jmp     loc_180072C7A
```
