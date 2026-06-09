# CiHandleFlagsFromDefender

- ea: `0x180074118`
- end: `0x180074311`
- name: `CiHandleFlagsFromDefender`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073dac`

## callees

- `0x18005ab10`
- `0x180065688`
- `0x180073cb0`
- `0x180074118`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800741e0`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800741e0`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800742ab`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800742ab`

## string_xrefs

- `0x1800741b4`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074265`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x18007428b`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180074118  mov     [rsp-28h+arg_0], rbx
0x18007411d  mov     [rsp-28h+arg_18], rsi
0x180074122  push    rbp
0x180074123  push    rdi
0x180074124  push    r13
0x180074126  push    r14
0x180074128  push    r15
0x18007412a  mov     rbp, rsp
0x18007412d  sub     rsp, 60h
0x180074131  mov     r14, [rbp+arg_20]
0x180074135  mov     r13, rcx
0x180074138  mov     [rbp+arg_8], 0
0x18007413f  mov     ecx, 1
0x180074144  mov     [rbp+arg_10], 0
0x18007414b  mov     rsi, r9
0x18007414e  mov     [rbp+var_10], 0
0x180074156  mov     rbx, r8
0x180074159  mov     [rbp+var_18], 0
0x180074161  mov     rdi, rdx
0x180074164  mov     [rbp+var_20], 0
0x18007416c  mov     byte ptr [r8], 0
0x180074170  test    dl, 4
0x180074173  jz      short loc_18007418B
0x180074175  lea     eax, [rcx+1]
0x180074178  lock cmpxchg cs:g_ReceivedSignalFromDefender, ecx
0x180074180  jnz     short loc_18007418B
0x180074182  mov     [r9], ecx
0x180074185  mov     [r8], cl
0x180074188  mov     [r14], cl
0x18007418b  test    dil, 2
0x18007418f  jz      loc_1800742D0
0x180074195  lea     rax, [rbp+arg_10]
0x180074199  xor     r9d, r9d
0x18007419c  mov     [rsp+60h+var_30], rax
0x1800741a1  lea     r8, aVerifiedandrep_4; "VerifiedAndReputableIgnoreAutoOptOut"
0x1800741a8  lea     rax, [rbp+arg_8]
0x1800741ac  mov     [rsp+60h+ValueLength], 4
0x1800741b4  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800741bb  mov     [rsp+60h+ValueData], rax
0x1800741c0  xor     ecx, ecx
0x1800741c2  call    CipGetRegistryValue
0x1800741c7  mov     r15d, [rbp+arg_8]
0x1800741cb  xor     ecx, ecx
0x1800741cd  test    eax, eax
0x1800741cf  cmovs   r15d, ecx
0x1800741d3  test    r15d, r15d
0x1800741d6  jnz     loc_1800742B7
0x1800741dc  lea     rcx, [rbp+var_20]
0x1800741e0  call    cs:__imp_KeQuerySystemTimePrecise
0x1800741e7  nop     dword ptr [rax+rax+00h]
0x1800741ec  lea     rcx, [rbp+var_10]
0x1800741f0  call    CiGetOOBECompleteTime
0x1800741f5  test    eax, eax
0x1800741f7  js      short loc_180074243
0x1800741f9  mov     r9, [rbp+var_20]
0x1800741fd  cmp     r9, [rbp+var_10]
0x180074201  jle     short loc_18007421D
0x180074203  mov     rax, r9
0x180074206  sub     rax, [rbp+var_10]
0x18007420a  mov     rcx, 0C92A69C000h
0x180074214  cmp     rax, rcx
0x180074217  jl      loc_1800742BB
0x18007421d  xor     eax, eax
0x18007421f  mov     ecx, 1
0x180074224  xchg    eax, cs:g_ReceivedSignalFromDefender
0x18007422a  test    eax, eax
0x18007422c  jz      loc_1800742D0
0x180074232  mov     dword ptr [rsi], 0
0x180074238  mov     [rbx], cl
0x18007423a  mov     byte ptr [r14], 0
0x18007423e  jmp     loc_1800742D0
0x180074243  lea     rax, [rbp+arg_10]
0x180074247  mov     r9d, 1
0x18007424d  mov     [rsp+60h+var_30], rax
0x180074252  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180074259  lea     rax, [rbp+var_18]
0x18007425d  mov     [rsp+60h+ValueLength], 8
0x180074265  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007426c  mov     [rsp+60h+ValueData], rax
0x180074271  xor     ecx, ecx
0x180074273  call    CipGetRegistryValue
0x180074278  test    eax, eax
0x18007427a  jns     short loc_1800742F7
0x18007427c  mov     rax, [rbp+var_20]
0x180074280  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180074287  mov     [rbp+var_18], rax
0x18007428b  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074292  lea     rax, [rbp+var_18]
0x180074296  mov     [rsp+60h+ValueLength], 8; ValueLength
0x18007429e  mov     r9d, 3; ValueType
0x1800742a4  mov     [rsp+60h+ValueData], rax; ValueData
0x1800742a9  xor     ecx, ecx; RelativeTo
0x1800742ab  call    cs:__imp_RtlWriteRegistryValue
0x1800742b2  nop     dword ptr [rax+rax+00h]
0x1800742b7  mov     r9, [rbp+var_20]
0x1800742bb  mov     r8, [rbp+var_18]
0x1800742bf  mov     ecx, r15d
0x1800742c2  mov     rdx, [rbp+var_10]
0x1800742c6  call    CiInstrumentDefenderTriggeredNWSwitchOffIgnored
0x1800742cb  mov     ecx, 1
0x1800742d0  test    dil, 8
0x1800742d4  jz      short loc_1800742DD
0x1800742d6  mov     [r13+82Ch], cl
0x1800742dd  lea     r11, [rsp+60h+var_s0]
0x1800742e2  mov     rbx, [r11+30h]
0x1800742e6  mov     rsi, [r11+48h]
0x1800742ea  mov     rsp, r11
0x1800742ed  pop     r15
0x1800742ef  pop     r14
0x1800742f1  pop     r13
0x1800742f3  pop     rdi
0x1800742f4  pop     rbp
0x1800742f5  retn
0x1800742f7  mov     r9, [rbp+var_20]
0x1800742fb  cmp     r9, [rbp+var_18]
0x1800742ff  jle     loc_18007421D
0x180074305  mov     rax, r9
0x180074308  sub     rax, [rbp+var_18]
0x18007430c  jmp     loc_18007420A
```
