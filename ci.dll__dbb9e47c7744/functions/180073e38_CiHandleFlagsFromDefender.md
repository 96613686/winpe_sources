# CiHandleFlagsFromDefender

- ea: `0x180073e38`
- end: `0x180074031`
- name: `CiHandleFlagsFromDefender`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073acc`

## callees

- `0x18005abe8`
- `0x180065518`
- `0x1800739d0`
- `0x180073e38`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180073f00`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180073f00`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073fcb`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073fcb`

## string_xrefs

- `0x180073ed4`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180073f85`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180073fab`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180073e38  mov     [rsp-28h+arg_0], rbx
0x180073e3d  mov     [rsp-28h+arg_18], rsi
0x180073e42  push    rbp
0x180073e43  push    rdi
0x180073e44  push    r13
0x180073e46  push    r14
0x180073e48  push    r15
0x180073e4a  mov     rbp, rsp
0x180073e4d  sub     rsp, 60h
0x180073e51  mov     r14, [rbp+arg_20]
0x180073e55  mov     r13, rcx
0x180073e58  mov     [rbp+arg_8], 0
0x180073e5f  mov     ecx, 1
0x180073e64  mov     [rbp+arg_10], 0
0x180073e6b  mov     rsi, r9
0x180073e6e  mov     [rbp+var_10], 0
0x180073e76  mov     rbx, r8
0x180073e79  mov     [rbp+var_18], 0
0x180073e81  mov     rdi, rdx
0x180073e84  mov     [rbp+var_20], 0
0x180073e8c  mov     byte ptr [r8], 0
0x180073e90  test    dl, 4
0x180073e93  jz      short loc_180073EAB
0x180073e95  lea     eax, [rcx+1]
0x180073e98  lock cmpxchg cs:g_ReceivedSignalFromDefender, ecx
0x180073ea0  jnz     short loc_180073EAB
0x180073ea2  mov     [r9], ecx
0x180073ea5  mov     [r8], cl
0x180073ea8  mov     [r14], cl
0x180073eab  test    dil, 2
0x180073eaf  jz      loc_180073FF0
0x180073eb5  lea     rax, [rbp+arg_10]
0x180073eb9  xor     r9d, r9d
0x180073ebc  mov     [rsp+60h+var_30], rax
0x180073ec1  lea     r8, aVerifiedandrep_4; "VerifiedAndReputableIgnoreAutoOptOut"
0x180073ec8  lea     rax, [rbp+arg_8]
0x180073ecc  mov     [rsp+60h+ValueLength], 4
0x180073ed4  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180073edb  mov     [rsp+60h+ValueData], rax
0x180073ee0  xor     ecx, ecx
0x180073ee2  call    CipGetRegistryValue
0x180073ee7  mov     r15d, [rbp+arg_8]
0x180073eeb  xor     ecx, ecx
0x180073eed  test    eax, eax
0x180073eef  cmovs   r15d, ecx
0x180073ef3  test    r15d, r15d
0x180073ef6  jnz     loc_180073FD7
0x180073efc  lea     rcx, [rbp+var_20]
0x180073f00  call    cs:__imp_KeQuerySystemTimePrecise
0x180073f07  nop     dword ptr [rax+rax+00h]
0x180073f0c  lea     rcx, [rbp+var_10]
0x180073f10  call    CiGetOOBECompleteTime
0x180073f15  test    eax, eax
0x180073f17  js      short loc_180073F63
0x180073f19  mov     r9, [rbp+var_20]
0x180073f1d  cmp     r9, [rbp+var_10]
0x180073f21  jle     short loc_180073F3D
0x180073f23  mov     rax, r9
0x180073f26  sub     rax, [rbp+var_10]
0x180073f2a  mov     rcx, 0C92A69C000h
0x180073f34  cmp     rax, rcx
0x180073f37  jl      loc_180073FDB
0x180073f3d  xor     eax, eax
0x180073f3f  mov     ecx, 1
0x180073f44  xchg    eax, cs:g_ReceivedSignalFromDefender
0x180073f4a  test    eax, eax
0x180073f4c  jz      loc_180073FF0
0x180073f52  mov     dword ptr [rsi], 0
0x180073f58  mov     [rbx], cl
0x180073f5a  mov     byte ptr [r14], 0
0x180073f5e  jmp     loc_180073FF0
0x180073f63  lea     rax, [rbp+arg_10]
0x180073f67  mov     r9d, 1
0x180073f6d  mov     [rsp+60h+var_30], rax
0x180073f72  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180073f79  lea     rax, [rbp+var_18]
0x180073f7d  mov     [rsp+60h+ValueLength], 8
0x180073f85  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180073f8c  mov     [rsp+60h+ValueData], rax
0x180073f91  xor     ecx, ecx
0x180073f93  call    CipGetRegistryValue
0x180073f98  test    eax, eax
0x180073f9a  jns     short loc_180074017
0x180073f9c  mov     rax, [rbp+var_20]
0x180073fa0  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180073fa7  mov     [rbp+var_18], rax
0x180073fab  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180073fb2  lea     rax, [rbp+var_18]
0x180073fb6  mov     [rsp+60h+ValueLength], 8; ValueLength
0x180073fbe  mov     r9d, 3; ValueType
0x180073fc4  mov     [rsp+60h+ValueData], rax; ValueData
0x180073fc9  xor     ecx, ecx; RelativeTo
0x180073fcb  call    cs:__imp_RtlWriteRegistryValue
0x180073fd2  nop     dword ptr [rax+rax+00h]
0x180073fd7  mov     r9, [rbp+var_20]
0x180073fdb  mov     r8, [rbp+var_18]
0x180073fdf  mov     ecx, r15d
0x180073fe2  mov     rdx, [rbp+var_10]
0x180073fe6  call    CiInstrumentDefenderTriggeredNWSwitchOffIgnored
0x180073feb  mov     ecx, 1
0x180073ff0  test    dil, 8
0x180073ff4  jz      short loc_180073FFD
0x180073ff6  mov     [r13+82Ch], cl
0x180073ffd  lea     r11, [rsp+60h+var_s0]
0x180074002  mov     rbx, [r11+30h]
0x180074006  mov     rsi, [r11+48h]
0x18007400a  mov     rsp, r11
0x18007400d  pop     r15
0x18007400f  pop     r14
0x180074011  pop     r13
0x180074013  pop     rdi
0x180074014  pop     rbp
0x180074015  retn
0x180074017  mov     r9, [rbp+var_20]
0x18007401b  cmp     r9, [rbp+var_18]
0x18007401f  jle     loc_180073F3D
0x180074025  mov     rax, r9
0x180074028  sub     rax, [rbp+var_18]
0x18007402c  jmp     loc_180073F2A
```
