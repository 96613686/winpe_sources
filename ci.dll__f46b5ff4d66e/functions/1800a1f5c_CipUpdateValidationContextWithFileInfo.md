# CipUpdateValidationContextWithFileInfo

- ea: `0x1800a1f5c`
- end: `0x1800a21f0`
- name: `CipUpdateValidationContextWithFileInfo`
- size: `660`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000eda0`
- `0x18008bdc0`
- `0x180097d10`

## callees

- `0x180074f70`
- `0x1800a1f5c`
- `0x1800a21f8`
- `0x1800a2c10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a211a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2132`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a214a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a211a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a2132`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a214a`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a20a9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a216f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a2199`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a21c3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a20a9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a216f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a2199`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a21c3`

## pseudocode

```c
__int64 __fastcall CipUpdateValidationContextWithFileInfo(__int64 a1, __int64 a2, void *a3, unsigned int a4, char a5)
{
  bool v5; // zf
  int updated; // ecx
  __int64 v12; // rax
  int v13; // [rsp+30h] [rbp-21h]
  UNICODE_STRING StringIn; // [rsp+50h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+Fh] BYREF
  UNICODE_STRING v16; // [rsp+70h] [rbp+1Fh] BYREF
  UNICODE_STRING v17; // [rsp+80h] [rbp+2Fh] BYREF
  __int64 v18; // [rsp+B0h] [rbp+5Fh] BYREF

  v5 = *(_QWORD *)(a1 + 816) == 0;
  v18 = 0;
  StringIn = 0;
  DestinationString = 0;
  v16 = 0;
  v17 = 0;
  if ( !v5 || (*(_DWORD *)(a1 + 2360) & 4) != 0 )
    return 0;
  if ( (g_CiPolicyState & 0x400000) != 0 && *(_DWORD *)(a1 + 3416) == 1 )
    CiHotpatchGetHotpatchSequenceFromImage();
  if ( !a2 )
    goto LABEL_9;
  if ( *(_DWORD *)(a1 + 2336) == 1 )
    *(_QWORD *)(a1 + 984) = a2;
  updated = CiUpdateValidationContextWithFilePath(a1);
  if ( updated >= 0 )
  {
LABEL_9:
    updated = SIPolicyGetOriginalFilenameAndVersionFromImageBase(
                a3,
                a4,
                a5,
                &StringIn,
                &v18,
                &v17,
                v13,
                &DestinationString,
                &v16);
    if ( (unsigned int)(updated + 1073741687) <= 2 || updated == -1073741793 || updated == -1073741308 )
    {
      updated = -1073741275;
    }
    else if ( updated >= 0 )
    {
      goto LABEL_13;
    }
    if ( !StringIn.Buffer )
      goto LABEL_28;
    if ( updated == -1073741275 )
    {
LABEL_13:
      if ( StringIn.Buffer )
      {
LABEL_14:
        if ( !DestinationString.Buffer )
          RtlInitUnicodeString(&DestinationString, &word_1800489C0);
        if ( !v16.Buffer )
          RtlInitUnicodeString(&v16, &word_1800489C0);
        if ( !v17.Buffer )
          RtlInitUnicodeString(&v17, &word_1800489C0);
        updated = RtlDuplicateUnicodeString(0, &StringIn, (PUNICODE_STRING)(a1 + 744));
        if ( updated >= 0 )
        {
          *(_DWORD *)(a1 + 2360) |= 4u;
          updated = RtlDuplicateUnicodeString(0, &DestinationString, (PUNICODE_STRING)(a1 + 760));
          if ( updated >= 0 )
          {
            *(_DWORD *)(a1 + 2360) |= 8u;
            updated = RtlDuplicateUnicodeString(0, &v16, (PUNICODE_STRING)(a1 + 776));
            if ( updated >= 0 )
            {
              *(_DWORD *)(a1 + 2360) |= 0x10u;
              updated = RtlDuplicateUnicodeString(0, &v17, (PUNICODE_STRING)(a1 + 792));
              if ( updated >= 0 )
              {
                v12 = v18;
                *(_DWORD *)(a1 + 2360) |= 0x20u;
                *(_QWORD *)(a1 + 840) = v12;
              }
            }
          }
        }
        return (unsigned int)updated;
      }
LABEL_28:
      RtlInitUnicodeString(&StringIn, &word_1800489C0);
      goto LABEL_14;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800a1f5c  mov     [rsp-8+arg_8], rbx
0x1800a1f61  mov     [rsp-8+arg_10], rsi
0x1800a1f66  push    rbp
0x1800a1f67  push    rdi
0x1800a1f68  push    r14
0x1800a1f6a  lea     rbp, [rsp-3Fh]
0x1800a1f6f  sub     rsp, 90h
0x1800a1f76  cmp     qword ptr [rcx+330h], 0
0x1800a1f7e  xorps   xmm0, xmm0
0x1800a1f81  xorps   xmm1, xmm1
0x1800a1f84  mov     [rbp+4Fh+arg_0], 0
0x1800a1f8c  movups  xmmword ptr [rbp+4Fh+StringIn.Length], xmm0
0x1800a1f90  mov     esi, r9d
0x1800a1f93  mov     r14, r8
0x1800a1f96  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x1800a1f9a  mov     rdi, rdx
0x1800a1f9d  mov     rbx, rcx
0x1800a1fa0  movups  xmmword ptr [rbp+4Fh+var_30.Length], xmm0
0x1800a1fa4  movups  xmmword ptr [rbp+4Fh+var_20.Length], xmm1
0x1800a1fa8  jz      short loc_1800A1FC5
0x1800a1faa  xor     eax, eax
0x1800a1fac  lea     r11, [rsp+0A0h+var_10]
0x1800a1fb4  mov     rbx, [r11+28h]
0x1800a1fb8  mov     rsi, [r11+30h]
0x1800a1fbc  mov     rsp, r11
0x1800a1fbf  pop     r14
0x1800a1fc1  pop     rdi
0x1800a1fc2  pop     rbp
0x1800a1fc3  retn
0x1800a1fc5  mov     eax, [rcx+938h]
0x1800a1fcb  test    al, 4
0x1800a1fcd  jnz     short loc_1800A1FAA
0x1800a1fcf  test    cs:g_CiPolicyState, 400000h
0x1800a1fd9  jnz     loc_1800A20C6
0x1800a1fdf  test    rdi, rdi
0x1800a1fe2  jz      short loc_1800A2003
0x1800a1fe4  cmp     dword ptr [rbx+920h], 1
0x1800a1feb  jz      loc_1800A20DD
0x1800a1ff1  mov     rcx, rbx
0x1800a1ff4  call    CiUpdateValidationContextWithFilePath
0x1800a1ff9  mov     ecx, eax
0x1800a1ffb  test    eax, eax
0x1800a1ffd  js      loc_1800A20BF
0x1800a2003  mov     r8b, [rbp+4Fh+arg_20]
0x1800a2007  lea     rax, [rbp+4Fh+var_30]
0x1800a200b  mov     [rsp+0A0h+var_60], rax; __int64
0x1800a2010  lea     r9, [rbp+4Fh+StringIn]
0x1800a2014  lea     rax, [rbp+4Fh+DestinationString]
0x1800a2018  mov     edx, esi; Size
0x1800a201a  mov     [rsp+0A0h+var_68], rax; __int64
0x1800a201f  mov     rcx, r14; BaseAddress
0x1800a2022  lea     rax, [rbp+4Fh+var_20]
0x1800a2026  mov     [rsp+0A0h+var_78], rax; __int64
0x1800a202b  lea     rax, [rbp+4Fh+arg_0]
0x1800a202f  mov     [rsp+0A0h+var_80], rax; __int64
0x1800a2034  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a2039  mov     rdx, [rbp+4Fh+StringIn.Buffer]
0x1800a203d  lea     rdi, word_1800489C0
0x1800a2044  mov     ecx, eax
0x1800a2046  mov     r8d, 0C0000225h
0x1800a204c  add     eax, 3FFFFF77h
0x1800a2051  cmp     eax, 2
0x1800a2054  jbe     loc_1800A20E9
0x1800a205a  cmp     ecx, 0C000001Fh
0x1800a2060  jz      loc_1800A20E9
0x1800a2066  cmp     ecx, 0C0000204h
0x1800a206c  jz      short loc_1800A20E9
0x1800a206e  test    ecx, ecx
0x1800a2070  js      short loc_1800A20EC
0x1800a2072  test    rdx, rdx
0x1800a2075  jz      loc_1800A20FB
0x1800a207b  cmp     [rbp+4Fh+DestinationString.Buffer], 0
0x1800a2080  jz      loc_1800A2113
0x1800a2086  cmp     [rbp+4Fh+var_30.Buffer], 0
0x1800a208b  jz      loc_1800A212B
0x1800a2091  cmp     [rbp+4Fh+var_20.Buffer], 0
0x1800a2096  jz      loc_1800A2143
0x1800a209c  lea     r8, [rbx+2E8h]; StringOut
0x1800a20a3  xor     ecx, ecx; Flags
0x1800a20a5  lea     rdx, [rbp+4Fh+StringIn]; StringIn
0x1800a20a9  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a20b0  nop     dword ptr [rax+rax+00h]
0x1800a20b5  mov     ecx, eax
0x1800a20b7  test    eax, eax
0x1800a20b9  jns     loc_1800A215B
0x1800a20bf  mov     eax, ecx
0x1800a20c1  jmp     loc_1800A1FAC
0x1800a20c6  cmp     dword ptr [rcx+0D58h], 1
0x1800a20cd  jnz     loc_1800A1FDF
0x1800a20d3  call    CiHotpatchGetHotpatchSequenceFromImage
0x1800a20d8  jmp     loc_1800A1FDF
0x1800a20dd  mov     [rbx+3D8h], rdi
0x1800a20e4  jmp     loc_1800A1FF1
0x1800a20e9  mov     ecx, r8d
0x1800a20ec  test    rdx, rdx
0x1800a20ef  jz      short loc_1800A20FB
0x1800a20f1  cmp     ecx, r8d
0x1800a20f4  jnz     short loc_1800A20BF
0x1800a20f6  jmp     loc_1800A2072
0x1800a20fb  mov     rdx, rdi; SourceString
0x1800a20fe  lea     rcx, [rbp+4Fh+StringIn]; DestinationString
0x1800a2102  call    cs:__imp_RtlInitUnicodeString
0x1800a2109  nop     dword ptr [rax+rax+00h]
0x1800a210e  jmp     loc_1800A207B
0x1800a2113  mov     rdx, rdi; SourceString
0x1800a2116  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800a211a  call    cs:__imp_RtlInitUnicodeString
0x1800a2121  nop     dword ptr [rax+rax+00h]
0x1800a2126  jmp     loc_1800A2086
0x1800a212b  mov     rdx, rdi; SourceString
0x1800a212e  lea     rcx, [rbp+4Fh+var_30]; DestinationString
0x1800a2132  call    cs:__imp_RtlInitUnicodeString
0x1800a2139  nop     dword ptr [rax+rax+00h]
0x1800a213e  jmp     loc_1800A2091
0x1800a2143  mov     rdx, rdi; SourceString
0x1800a2146  lea     rcx, [rbp+4Fh+var_20]; DestinationString
0x1800a214a  call    cs:__imp_RtlInitUnicodeString
0x1800a2151  nop     dword ptr [rax+rax+00h]
0x1800a2156  jmp     loc_1800A209C
0x1800a215b  or      dword ptr [rbx+938h], 4
0x1800a2162  lea     r8, [rbx+2F8h]; StringOut
0x1800a2169  lea     rdx, [rbp+4Fh+DestinationString]; StringIn
0x1800a216d  xor     ecx, ecx; Flags
0x1800a216f  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a2176  nop     dword ptr [rax+rax+00h]
0x1800a217b  mov     ecx, eax
0x1800a217d  test    eax, eax
0x1800a217f  js      loc_1800A20BF
0x1800a2185  or      dword ptr [rbx+938h], 8
0x1800a218c  lea     r8, [rbx+308h]; StringOut
0x1800a2193  lea     rdx, [rbp+4Fh+var_30]; StringIn
0x1800a2197  xor     ecx, ecx; Flags
0x1800a2199  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a21a0  nop     dword ptr [rax+rax+00h]
0x1800a21a5  mov     ecx, eax
0x1800a21a7  test    eax, eax
0x1800a21a9  js      loc_1800A20BF
0x1800a21af  or      dword ptr [rbx+938h], 10h
0x1800a21b6  lea     r8, [rbx+318h]; StringOut
0x1800a21bd  lea     rdx, [rbp+4Fh+var_20]; StringIn
0x1800a21c1  xor     ecx, ecx; Flags
0x1800a21c3  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a21ca  nop     dword ptr [rax+rax+00h]
0x1800a21cf  mov     ecx, eax
0x1800a21d1  test    eax, eax
0x1800a21d3  js      loc_1800A20BF
0x1800a21d9  mov     rax, [rbp+4Fh+arg_0]
0x1800a21dd  or      dword ptr [rbx+938h], 20h
0x1800a21e4  mov     [rbx+348h], rax
0x1800a21eb  jmp     loc_1800A20BF
```
