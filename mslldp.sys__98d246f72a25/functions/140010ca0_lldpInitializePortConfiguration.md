# lldpInitializePortConfiguration

- ea: `0x140010ca0`
- end: `0x140010f19`
- name: `lldpInitializePortConfiguration`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140010560`

## callees

- `0x140003cc0`
- `0x140004b00`
- `0x14000561c`
- `0x1400056ac`
- `0x140006630`
- `0x140006670`
- `0x140010ca0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140010e05`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010e05`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140010e38`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010e16`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010e16`

## string_xrefs

- `0x140010d74`: `Mslldp\Parameters\Agents\%s-%u`
- `0x140010dfe`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
unsigned int __fastcall lldpInitializePortConfiguration(__int64 a1)
{
  int v1; // eax
  int v2; // eax
  __int64 v4; // rdi
  __int64 v5; // rsi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  unsigned int result; // eax
  PVOID SystemRoutineAddress; // rax
  int v15; // r8d
  unsigned int v16; // edx
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h]
  wchar_t *v22; // [rsp+70h] [rbp-90h]
  unsigned int *v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h]
  _BYTE v31[208]; // [rsp+D0h] [rbp-30h] BYREF

  v1 = dword_14000B05C;
  *(_DWORD *)(a1 + 248) = dword_14000B05C;
  *(_DWORD *)(a1 + 276) = v1;
  v2 = dword_14000B074;
  *(_DWORD *)(a1 + 252) = dword_14000B074;
  v4 = 0;
  *(_DWORD *)(a1 + 280) = v2;
  v5 = 0;
  v6 = dword_14000B08C;
  *(_DWORD *)(a1 + 256) = dword_14000B08C;
  *(_DWORD *)(a1 + 284) = v6;
  v7 = dword_14000B0A4;
  *(_DWORD *)(a1 + 260) = dword_14000B0A4;
  *(_DWORD *)(a1 + 288) = v7;
  v8 = dword_14000B0BC;
  *(_DWORD *)(a1 + 264) = dword_14000B0BC;
  *(_DWORD *)(a1 + 292) = v8;
  v9 = dword_14000B0D4;
  *(_DWORD *)(a1 + 268) = dword_14000B0D4;
  *(_DWORD *)(a1 + 296) = v9;
  v10 = dword_14000B0EC;
  *(_DWORD *)(a1 + 272) = dword_14000B0EC;
  *(_DWORD *)(a1 + 300) = v10;
  do
  {
    v11 = *(unsigned int *)(a1 + 132);
    v12 = *(_QWORD *)(a1 + 112);
    DestinationString.Buffer = (wchar_t *)v31;
    v22 = (&lldpParameterRules)[v5];
    v23 = &v17;
    v17 = 0;
    *(_QWORD *)&DestinationString.Length = 13369344;
    v20 = 0;
    v21 = 180;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    result = RtlUnicodeStringPrintf(&DestinationString, L"Mslldp\\Parameters\\Agents\\%s-%u", v12, v11);
    if ( result )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        result = WPP_SF_d(
                   WPP_GLOBAL_Control->AttachedDevice,
                   18,
                   WPP_b3a834d394783de5fb279a081dc3c281_Traceguids,
                   result);
    }
    else
    {
      SystemRoutineName = 0;
      DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      result = ((__int64 (__fastcall *)(__int64, _BYTE *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
                 1,
                 v31,
                 &v20,
                 0,
                 0);
      if ( !result )
      {
        v16 = (unsigned int)(&lldpParameterRules)[v5 + 1];
        result = v17;
        if ( v17 <= v16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice, v16, v15, (unsigned int)(&lldpParameterRules)[v5], v17);
            result = v17;
          }
          *(_DWORD *)(a1 + 4 * v4 + 248) = result;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          result = WPP_SF_SDD(
                     WPP_GLOBAL_Control->AttachedDevice,
                     v16,
                     v15,
                     (unsigned int)(&lldpParameterRules)[v5],
                     v17,
                     (char)(&lldpParameterRules)[v5 + 1]);
        }
      }
    }
    ++v4;
    v5 += 3;
  }
  while ( v4 != 7 );
  return result;
}

```

## disassembly

```asm
0x140010ca0  push    rbp
0x140010ca2  push    rbx
0x140010ca3  push    rsi
0x140010ca4  push    rdi
0x140010ca5  push    r12
0x140010ca7  push    r13
0x140010ca9  push    r14
0x140010cab  push    r15
0x140010cad  lea     rbp, [rsp-0B8h]
0x140010cb5  sub     rsp, 1B8h
0x140010cbc  mov     rax, cs:__security_cookie
0x140010cc3  xor     rax, rsp
0x140010cc6  mov     [rbp+0F0h+var_50], rax
0x140010ccd  mov     eax, cs:dword_14000B05C
0x140010cd3  lea     r15, lldpParameterRules
0x140010cda  mov     [rcx+0F8h], eax
0x140010ce0  lea     r13, WPP_GLOBAL_Control
0x140010ce7  mov     [rcx+114h], eax
0x140010ced  xor     r14d, r14d
0x140010cf0  mov     eax, cs:dword_14000B074
0x140010cf6  mov     rbx, rcx
0x140010cf9  mov     [rcx+0FCh], eax
0x140010cff  mov     edi, r14d
0x140010d02  mov     [rcx+118h], eax
0x140010d08  mov     esi, r14d
0x140010d0b  mov     eax, cs:dword_14000B08C
0x140010d11  mov     [rcx+100h], eax
0x140010d17  mov     [rcx+11Ch], eax
0x140010d1d  mov     eax, cs:dword_14000B0A4
0x140010d23  mov     [rcx+104h], eax
0x140010d29  mov     [rcx+120h], eax
0x140010d2f  mov     eax, cs:dword_14000B0BC
0x140010d35  mov     [rcx+108h], eax
0x140010d3b  mov     [rcx+124h], eax
0x140010d41  mov     eax, cs:dword_14000B0D4
0x140010d47  mov     [rcx+10Ch], eax
0x140010d4d  mov     [rcx+128h], eax
0x140010d53  mov     eax, cs:dword_14000B0EC
0x140010d59  mov     [rcx+110h], eax
0x140010d5f  mov     [rcx+12Ch], eax
0x140010d65  mov     r9d, [rbx+84h]
0x140010d6c  lea     rax, [rbp+0F0h+var_120]
0x140010d70  mov     r8, [rbx+70h]
0x140010d74  lea     rdx, aMslldpParamete_0; "Mslldp\\Parameters\\Agents\\%s-%u"
0x140010d7b  xorps   xmm0, xmm0
0x140010d7e  mov     [rsp+1F0h+DestinationString.Buffer], rax
0x140010d83  mov     rax, [rsi+r15]
0x140010d87  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x140010d8c  mov     [rsp+1F0h+var_180], rax
0x140010d91  lea     rax, [rsp+1F0h+var_1C0]
0x140010d96  mov     [rsp+1F0h+var_178], rax
0x140010d9b  mov     [rsp+1F0h+var_1C0], r14d
0x140010da0  mov     qword ptr [rsp+1F0h+DestinationString.Length], 0CC0000h
0x140010da9  mov     [rsp+1F0h+var_190], r14
0x140010dae  mov     [rsp+1F0h+var_188], 0B4h
0x140010db6  mov     [rbp+0F0h+var_170], r14d
0x140010dba  mov     [rbp+0F0h+var_168], r14
0x140010dbe  mov     [rbp+0F0h+var_160], r14d
0x140010dc2  mov     [rbp+0F0h+var_158], r14
0x140010dc6  movups  [rbp+0F0h+var_150], xmm0
0x140010dca  movups  [rbp+0F0h+var_140], xmm0
0x140010dce  movups  [rbp+0F0h+var_130], xmm0
0x140010dd2  call    RtlUnicodeStringPrintf
0x140010dd7  test    eax, eax
0x140010dd9  jnz     loc_140010E81
0x140010ddf  mov     rax, [rsp+1F0h+DestinationString.Buffer]
0x140010de4  lea     rcx, [rsp+1F0h+SystemRoutineName]; DestinationString
0x140010de9  movzx   edx, [rsp+1F0h+DestinationString.Length]
0x140010dee  xorps   xmm0, xmm0
0x140010df1  shr     rdx, 1
0x140010df4  movups  xmmword ptr [rsp+1F0h+SystemRoutineName.Length], xmm0
0x140010df9  mov     [rax+rdx*2], r14w
0x140010dfe  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140010e05  call    cs:__imp_RtlInitUnicodeString
0x140010e0c  nop     dword ptr [rax+rax+00h]
0x140010e11  lea     rcx, [rsp+1F0h+SystemRoutineName]; SystemRoutineName
0x140010e16  call    cs:__imp_MmGetSystemRoutineAddress
0x140010e1d  nop     dword ptr [rax+rax+00h]
0x140010e22  lea     r8, [rsp+1F0h+var_190]
0x140010e27  mov     [rsp+1F0h+var_1D0], r14
0x140010e2c  test    rax, rax
0x140010e2f  lea     rdx, [rbp+0F0h+var_120]
0x140010e33  mov     ecx, 1
0x140010e38  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140010e40  xor     r9d, r9d
0x140010e43  call    _guard_dispatch_icall
0x140010e48  test    eax, eax
0x140010e4a  jz      short loc_140010EAD
0x140010e4c  inc     rdi
0x140010e4f  add     rsi, 18h
0x140010e53  cmp     rdi, 7
0x140010e57  jnz     loc_140010D65
0x140010e5d  mov     rcx, [rbp+0F0h+var_50]
0x140010e64  xor     rcx, rsp; StackCookie
0x140010e67  call    __security_check_cookie
0x140010e6c  add     rsp, 1B8h
0x140010e73  pop     r15
0x140010e75  pop     r14
0x140010e77  pop     r13
0x140010e79  pop     r12
0x140010e7b  pop     rdi
0x140010e7c  pop     rsi
0x140010e7d  pop     rbx
0x140010e7e  pop     rbp
0x140010e7f  retn
0x140010e81  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e88  cmp     rcx, r13
0x140010e8b  jz      short loc_140010E4C
0x140010e8d  cmp     byte ptr [rcx+29h], 2
0x140010e91  jb      short loc_140010E4C
0x140010e93  mov     rcx, [rcx+18h]
0x140010e97  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x140010e9e  mov     edx, 12h
0x140010ea3  mov     r9d, eax
0x140010ea6  call    WPP_SF_d
0x140010eab  jmp     short loc_140010E4C
0x140010ead  mov     edx, [rsi+r15+10h]
0x140010eb2  mov     eax, [rsp+1F0h+var_1C0]
0x140010eb6  cmp     eax, edx
0x140010eb8  jbe     short loc_140010EE6
0x140010eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ec1  cmp     rcx, r13
0x140010ec4  jz      short loc_140010E4C
0x140010ec6  cmp     byte ptr [rcx+29h], 3
0x140010eca  jb      short loc_140010E4C
0x140010ecc  mov     r9, [rsi+r15]
0x140010ed0  mov     rcx, [rcx+18h]
0x140010ed4  mov     [rsp+1F0h+var_1C8], edx
0x140010ed8  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140010edc  call    WPP_SF_SDD
0x140010ee1  jmp     loc_140010E4C
0x140010ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140010eed  cmp     rcx, r13
0x140010ef0  jz      short loc_140010F0D
0x140010ef2  cmp     byte ptr [rcx+29h], 4
0x140010ef6  jb      short loc_140010F0D
0x140010ef8  mov     r9, [rsi+r15]
0x140010efc  mov     rcx, [rcx+18h]
0x140010f00  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140010f04  call    WPP_SF_SD
0x140010f09  mov     eax, [rsp+1F0h+var_1C0]
0x140010f0d  mov     [rbx+rdi*4+0F8h], eax
0x140010f14  jmp     loc_140010E4C
```
