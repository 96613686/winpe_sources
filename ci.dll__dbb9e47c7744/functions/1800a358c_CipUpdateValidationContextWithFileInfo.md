# CipUpdateValidationContextWithFileInfo

- ea: `0x1800a358c`
- end: `0x1800a3820`
- name: `CipUpdateValidationContextWithFileInfo`
- size: `660`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000eda0`
- `0x18008d3f0`
- `0x180099340`

## callees

- `0x18007652c`
- `0x1800a358c`
- `0x1800a3828`
- `0x1800a4240`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3732`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a374a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3762`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a377a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3732`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a374a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3762`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a377a`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a36d9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a379f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a37c9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a37f3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a36d9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a379f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a37c9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a37f3`

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
          RtlInitUnicodeString(&DestinationString, &word_1800499AC);
        if ( !v16.Buffer )
          RtlInitUnicodeString(&v16, &word_1800499AC);
        if ( !v17.Buffer )
          RtlInitUnicodeString(&v17, &word_1800499AC);
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
      RtlInitUnicodeString(&StringIn, &word_1800499AC);
      goto LABEL_14;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800a358c  mov     [rsp-8+arg_8], rbx
0x1800a3591  mov     [rsp-8+arg_10], rsi
0x1800a3596  push    rbp
0x1800a3597  push    rdi
0x1800a3598  push    r14
0x1800a359a  lea     rbp, [rsp-3Fh]
0x1800a359f  sub     rsp, 90h
0x1800a35a6  cmp     qword ptr [rcx+330h], 0
0x1800a35ae  xorps   xmm0, xmm0
0x1800a35b1  xorps   xmm1, xmm1
0x1800a35b4  mov     [rbp+4Fh+arg_0], 0
0x1800a35bc  movups  xmmword ptr [rbp+4Fh+StringIn.Length], xmm0
0x1800a35c0  mov     esi, r9d
0x1800a35c3  mov     r14, r8
0x1800a35c6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x1800a35ca  mov     rdi, rdx
0x1800a35cd  mov     rbx, rcx
0x1800a35d0  movups  xmmword ptr [rbp+4Fh+var_30.Length], xmm0
0x1800a35d4  movups  xmmword ptr [rbp+4Fh+var_20.Length], xmm1
0x1800a35d8  jz      short loc_1800A35F5
0x1800a35da  xor     eax, eax
0x1800a35dc  lea     r11, [rsp+0A0h+var_10]
0x1800a35e4  mov     rbx, [r11+28h]
0x1800a35e8  mov     rsi, [r11+30h]
0x1800a35ec  mov     rsp, r11
0x1800a35ef  pop     r14
0x1800a35f1  pop     rdi
0x1800a35f2  pop     rbp
0x1800a35f3  retn
0x1800a35f5  mov     eax, [rcx+938h]
0x1800a35fb  test    al, 4
0x1800a35fd  jnz     short loc_1800A35DA
0x1800a35ff  test    cs:g_CiPolicyState, 400000h
0x1800a3609  jnz     loc_1800A36F6
0x1800a360f  test    rdi, rdi
0x1800a3612  jz      short loc_1800A3633
0x1800a3614  cmp     dword ptr [rbx+920h], 1
0x1800a361b  jz      loc_1800A370D
0x1800a3621  mov     rcx, rbx
0x1800a3624  call    CiUpdateValidationContextWithFilePath
0x1800a3629  mov     ecx, eax
0x1800a362b  test    eax, eax
0x1800a362d  js      loc_1800A36EF
0x1800a3633  mov     r8b, [rbp+4Fh+arg_20]
0x1800a3637  lea     rax, [rbp+4Fh+var_30]
0x1800a363b  mov     [rsp+0A0h+var_60], rax; __int64
0x1800a3640  lea     r9, [rbp+4Fh+StringIn]
0x1800a3644  lea     rax, [rbp+4Fh+DestinationString]
0x1800a3648  mov     edx, esi; Size
0x1800a364a  mov     [rsp+0A0h+var_68], rax; __int64
0x1800a364f  mov     rcx, r14; BaseAddress
0x1800a3652  lea     rax, [rbp+4Fh+var_20]
0x1800a3656  mov     [rsp+0A0h+var_78], rax; __int64
0x1800a365b  lea     rax, [rbp+4Fh+arg_0]
0x1800a365f  mov     [rsp+0A0h+var_80], rax; __int64
0x1800a3664  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x1800a3669  mov     rdx, [rbp+4Fh+StringIn.Buffer]
0x1800a366d  lea     rdi, word_1800499AC
0x1800a3674  mov     ecx, eax
0x1800a3676  mov     r8d, 0C0000225h
0x1800a367c  add     eax, 3FFFFF77h
0x1800a3681  cmp     eax, 2
0x1800a3684  jbe     loc_1800A3719
0x1800a368a  cmp     ecx, 0C000001Fh
0x1800a3690  jz      loc_1800A3719
0x1800a3696  cmp     ecx, 0C0000204h
0x1800a369c  jz      short loc_1800A3719
0x1800a369e  test    ecx, ecx
0x1800a36a0  js      short loc_1800A371C
0x1800a36a2  test    rdx, rdx
0x1800a36a5  jz      loc_1800A372B
0x1800a36ab  cmp     [rbp+4Fh+DestinationString.Buffer], 0
0x1800a36b0  jz      loc_1800A3743
0x1800a36b6  cmp     [rbp+4Fh+var_30.Buffer], 0
0x1800a36bb  jz      loc_1800A375B
0x1800a36c1  cmp     [rbp+4Fh+var_20.Buffer], 0
0x1800a36c6  jz      loc_1800A3773
0x1800a36cc  lea     r8, [rbx+2E8h]; StringOut
0x1800a36d3  xor     ecx, ecx; Flags
0x1800a36d5  lea     rdx, [rbp+4Fh+StringIn]; StringIn
0x1800a36d9  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a36e0  nop     dword ptr [rax+rax+00h]
0x1800a36e5  mov     ecx, eax
0x1800a36e7  test    eax, eax
0x1800a36e9  jns     loc_1800A378B
0x1800a36ef  mov     eax, ecx
0x1800a36f1  jmp     loc_1800A35DC
0x1800a36f6  cmp     dword ptr [rcx+0D58h], 1
0x1800a36fd  jnz     loc_1800A360F
0x1800a3703  call    CiHotpatchGetHotpatchSequenceFromImage
0x1800a3708  jmp     loc_1800A360F
0x1800a370d  mov     [rbx+3D8h], rdi
0x1800a3714  jmp     loc_1800A3621
0x1800a3719  mov     ecx, r8d
0x1800a371c  test    rdx, rdx
0x1800a371f  jz      short loc_1800A372B
0x1800a3721  cmp     ecx, r8d
0x1800a3724  jnz     short loc_1800A36EF
0x1800a3726  jmp     loc_1800A36A2
0x1800a372b  mov     rdx, rdi; SourceString
0x1800a372e  lea     rcx, [rbp+4Fh+StringIn]; DestinationString
0x1800a3732  call    cs:__imp_RtlInitUnicodeString
0x1800a3739  nop     dword ptr [rax+rax+00h]
0x1800a373e  jmp     loc_1800A36AB
0x1800a3743  mov     rdx, rdi; SourceString
0x1800a3746  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800a374a  call    cs:__imp_RtlInitUnicodeString
0x1800a3751  nop     dword ptr [rax+rax+00h]
0x1800a3756  jmp     loc_1800A36B6
0x1800a375b  mov     rdx, rdi; SourceString
0x1800a375e  lea     rcx, [rbp+4Fh+var_30]; DestinationString
0x1800a3762  call    cs:__imp_RtlInitUnicodeString
0x1800a3769  nop     dword ptr [rax+rax+00h]
0x1800a376e  jmp     loc_1800A36C1
0x1800a3773  mov     rdx, rdi; SourceString
0x1800a3776  lea     rcx, [rbp+4Fh+var_20]; DestinationString
0x1800a377a  call    cs:__imp_RtlInitUnicodeString
0x1800a3781  nop     dword ptr [rax+rax+00h]
0x1800a3786  jmp     loc_1800A36CC
0x1800a378b  or      dword ptr [rbx+938h], 4
0x1800a3792  lea     r8, [rbx+2F8h]; StringOut
0x1800a3799  lea     rdx, [rbp+4Fh+DestinationString]; StringIn
0x1800a379d  xor     ecx, ecx; Flags
0x1800a379f  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a37a6  nop     dword ptr [rax+rax+00h]
0x1800a37ab  mov     ecx, eax
0x1800a37ad  test    eax, eax
0x1800a37af  js      loc_1800A36EF
0x1800a37b5  or      dword ptr [rbx+938h], 8
0x1800a37bc  lea     r8, [rbx+308h]; StringOut
0x1800a37c3  lea     rdx, [rbp+4Fh+var_30]; StringIn
0x1800a37c7  xor     ecx, ecx; Flags
0x1800a37c9  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a37d0  nop     dword ptr [rax+rax+00h]
0x1800a37d5  mov     ecx, eax
0x1800a37d7  test    eax, eax
0x1800a37d9  js      loc_1800A36EF
0x1800a37df  or      dword ptr [rbx+938h], 10h
0x1800a37e6  lea     r8, [rbx+318h]; StringOut
0x1800a37ed  lea     rdx, [rbp+4Fh+var_20]; StringIn
0x1800a37f1  xor     ecx, ecx; Flags
0x1800a37f3  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a37fa  nop     dword ptr [rax+rax+00h]
0x1800a37ff  mov     ecx, eax
0x1800a3801  test    eax, eax
0x1800a3803  js      loc_1800A36EF
0x1800a3809  mov     rax, [rbp+4Fh+arg_0]
0x1800a380d  or      dword ptr [rbx+938h], 20h
0x1800a3814  mov     [rbx+348h], rax
0x1800a381b  jmp     loc_1800A36EF
```
