# MupiLoadUncHardeningConfigurationToList

- ea: `0x140015930`
- end: `0x140015c42`
- name: `MupiLoadUncHardeningConfigurationToList`
- size: `786`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014b70`
- `0x140014ea0`

## callees

- `0x1400013e0`
- `0x1400041b8`
- `0x14000426c`
- `0x140015750`
- `0x140015930`
- `0x140017988`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001596f`
- `ntoskrnl!ExAllocatePool2` at `0x140015beb`
- `ntoskrnl!ExAllocatePool2` at `0x14001596f`
- `ntoskrnl!ExAllocatePool2` at `0x140015beb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c18`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015a9e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015ac1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015a9e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015ac1`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400159b3`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1400159b3`

## pseudocode

```c
__int64 __fastcall MupiLoadUncHardeningConfigurationToList(HANDLE KeyHandle, __int64 a2)
{
  ULONG v4; // esi
  __int64 Pool2; // rdi
  int v6; // ebx
  ULONG v7; // r14d
  NTSTATUS v8; // eax
  __int64 v9; // r8
  _WORD *v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rcx
  USHORT v13; // ax
  __int64 *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // edx
  __int64 v19; // rcx
  int Length; // [rsp+20h] [rbp-49h]
  __int64 Lengtha; // [rsp+20h] [rbp-49h]
  int ResultLength; // [rsp+28h] [rbp-41h]
  __int64 v24; // [rsp+30h] [rbp-39h]
  __int128 v25; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING v26; // [rsp+50h] [rbp-19h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-9h] BYREF
  __int128 v28; // [rsp+70h] [rbp+7h] BYREF
  int v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+84h] [rbp+1Bh]
  __int64 v31; // [rsp+88h] [rbp+1Fh]
  ULONG v32; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v33; // [rsp+E8h] [rbp+7Fh]

  v4 = 1024;
  v33 = 0;
  v32 = 0;
  Pool2 = ExAllocatePool2(258, 1024, 1213560141);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v7 = 0;
  while ( 1 )
  {
    v25 = 0;
    v8 = ZwEnumerateValueKey(KeyHandle, v7, KeyValueFullInformation, (PVOID)Pool2, v4, &v32);
    v6 = v8;
    if ( v8 == -2147483622 )
      break;
    if ( v8 == -2147483643 || v8 == -1073741789 )
    {
      ExFreePoolWithTag((PVOID)Pool2, 0x4855754Du);
      v4 = v32;
      Pool2 = ExAllocatePool2(258, v32, 1213560141);
      if ( !Pool2 )
        return (unsigned int)-1073741670;
    }
    else
    {
      if ( v8 < 0 )
        goto LABEL_35;
      v10 = (_WORD *)(Pool2 + 20);
      ++v7;
      *((_QWORD *)&v25 + 1) = Pool2 + 20;
      v11 = *(unsigned __int16 *)(Pool2 + 16);
      WORD1(v25) = v11;
      LOWORD(v25) = v11;
      if ( (_WORD)v11 )
      {
        v12 = *(unsigned int *)(Pool2 + 4);
        if ( (_DWORD)v12 == 1 || (_DWORD)v12 == 7 )
        {
          if ( (unsigned __int16)v11 >= 4u && *v10 == 92 && *(_WORD *)(Pool2 + 22) == 92 )
          {
            String1 = 0;
            v26 = 0;
            v28 = 0;
            MupiGetPathComponents(&v25, &String1, &v26, 0, &v28);
            if ( RtlEqualUnicodeString(&String1, &MupiUncHardeningWildcard, 1u) )
              String1.Length = 0;
            if ( RtlEqualUnicodeString(&v26, &MupiUncHardeningWildcard, 1u) )
            {
              v13 = 0;
              v26.Length = 0;
            }
            else
            {
              v13 = v26.Length;
            }
            if ( (String1.Length || v13) && !(_WORD)v28 )
            {
              v6 = MupiFindOrCreateUncHardeningConfigurationEntry(a2, &String1, &v26);
              if ( v6 < 0 )
                goto LABEL_35;
              v18 = *(_DWORD *)(Pool2 + 12);
              v19 = Pool2 + *(unsigned int *)(Pool2 + 8);
              *(_QWORD *)&v28 = &v25;
              v31 = v33;
              v30 = 0;
              *((_QWORD *)&v28 + 1) = v19;
              v29 = v18;
              v6 = RfsCskvParse(v19, v18, v16, v17, (__int64)&v28);
              if ( v6 < 0 )
                goto LABEL_35;
            }
            else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
            {
              v14 = UncHardening_UnsupportedUncPath;
              LODWORD(v11) = (unsigned __int16)v25;
              v15 = Pool2 + *(_DWORD *)(Pool2 + 8);
              v24 = Pool2 + *(unsigned int *)(Pool2 + 8);
              ResultLength = *(_DWORD *)(Pool2 + 12) >> 1;
              Lengtha = *((_QWORD *)&v25 + 1);
              goto LABEL_31;
            }
          }
          else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
          {
            v15 = Pool2 + *(_DWORD *)(Pool2 + 8);
            v24 = Pool2 + *(unsigned int *)(Pool2 + 8);
            ResultLength = *(_DWORD *)(Pool2 + 12) >> 1;
            Lengtha = Pool2 + 20;
            v14 = UncHardening_InvalidUncPath;
LABEL_31:
            LOWORD(v11) = (unsigned __int16)v11 >> 1;
            McTemplateK0hzr0qzr2_EtwWriteTransfer(v15, (_DWORD)v14, v9, v11, Lengtha, ResultLength, v24);
          }
        }
        else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
        {
          LOWORD(v11) = (unsigned __int16)v11 >> 1;
          McTemplateK0hzr0hzr2q_EtwWriteTransfer(
            v12,
            (__int64)v10,
            v9,
            v11,
            Length,
            v11,
            Pool2 + 20,
            *(_DWORD *)(Pool2 + 4));
        }
      }
    }
  }
  v6 = 0;
LABEL_35:
  ExFreePoolWithTag((PVOID)Pool2, 0x4855754Du);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140015930  mov     [rsp-8+arg_0], rbx
0x140015935  push    rbp
0x140015936  push    rsi
0x140015937  push    rdi
0x140015938  push    r12
0x14001593a  push    r13
0x14001593c  push    r14
0x14001593e  push    r15
0x140015940  lea     rbp, [rsp-27h]
0x140015945  sub     rsp, 90h
0x14001594c  mov     r15, rdx
0x14001594f  mov     r12, rcx
0x140015952  xor     r13d, r13d
0x140015955  mov     esi, 400h
0x14001595a  mov     edx, esi
0x14001595c  mov     [rbp+57h+arg_18], r13
0x140015960  mov     r8d, 4855754Dh
0x140015966  mov     [rbp+57h+arg_10], r13d
0x14001596a  mov     ecx, 102h
0x14001596f  call    cs:__imp_ExAllocatePool2
0x140015976  nop     dword ptr [rax+rax+00h]
0x14001597b  mov     rdi, rax
0x14001597e  test    rax, rax
0x140015981  jnz     short loc_14001598D
0x140015983  mov     ebx, 0C000009Ah
0x140015988  jmp     loc_140015C24
0x14001598d  mov     r14d, r13d
0x140015990  lea     rax, [rbp+57h+arg_10]
0x140015994  xorps   xmm0, xmm0
0x140015997  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14001599c  mov     r9, rdi; KeyValueInformation
0x14001599f  mov     r8d, 1; KeyValueInformationClass
0x1400159a5  mov     [rsp+0C0h+Length], esi; Length
0x1400159a9  mov     edx, r14d; Index
0x1400159ac  mov     rcx, r12; KeyHandle
0x1400159af  movups  [rbp+57h+var_80], xmm0
0x1400159b3  call    cs:__imp_ZwEnumerateValueKey
0x1400159ba  nop     dword ptr [rax+rax+00h]
0x1400159bf  mov     ebx, eax
0x1400159c1  cmp     eax, 8000001Ah
0x1400159c6  jz      loc_140015C08
0x1400159cc  cmp     eax, 80000005h
0x1400159d1  jz      loc_140015BC8
0x1400159d7  cmp     eax, 0C0000023h
0x1400159dc  jz      loc_140015BC8
0x1400159e2  test    eax, eax
0x1400159e4  js      loc_140015C0B
0x1400159ea  lea     rdx, [rdi+14h]
0x1400159ee  inc     r14d
0x1400159f1  mov     qword ptr [rbp+57h+var_80+8], rdx
0x1400159f5  movzx   r9d, word ptr [rdi+10h]
0x1400159fa  mov     word ptr [rbp+57h+var_80+2], r9w
0x1400159ff  mov     word ptr [rbp+57h+var_80], r9w
0x140015a04  test    r9w, r9w
0x140015a08  jz      short loc_140015990
0x140015a0a  mov     ecx, [rdi+4]
0x140015a0d  cmp     ecx, 1
0x140015a10  jz      short loc_140015A41
0x140015a12  cmp     ecx, 7
0x140015a15  jz      short loc_140015A41
0x140015a17  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015a1e  jz      loc_140015990
0x140015a24  mov     [rsp+0C0h+var_88], ecx
0x140015a28  shr     r9w, 1
0x140015a2c  mov     [rsp+0C0h+var_90], rdx
0x140015a31  mov     word ptr [rsp+0C0h+ResultLength], r9w
0x140015a37  call    McTemplateK0hzr0hzr2q_EtwWriteTransfer
0x140015a3c  jmp     loc_140015990
0x140015a41  cmp     r9w, 4
0x140015a46  jb      loc_140015B8D
0x140015a4c  cmp     word ptr [rdx], 5Ch ; '\'
0x140015a50  jnz     loc_140015B8D
0x140015a56  cmp     word ptr [rdx+2], 5Ch ; '\'
0x140015a5b  jnz     loc_140015B8D
0x140015a61  xorps   xmm0, xmm0
0x140015a64  lea     rax, [rbp+57h+var_50]
0x140015a68  xorps   xmm1, xmm1
0x140015a6b  mov     qword ptr [rsp+0C0h+Length], rax
0x140015a70  xor     r9d, r9d
0x140015a73  lea     r8, [rbp+57h+var_70]
0x140015a77  lea     rdx, [rbp+57h+String1]
0x140015a7b  lea     rcx, [rbp+57h+var_80]
0x140015a7f  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140015a83  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x140015a87  movups  [rbp+57h+var_50], xmm0
0x140015a8b  call    MupiGetPathComponents
0x140015a90  mov     r8b, 1; CaseInSensitive
0x140015a93  lea     rdx, MupiUncHardeningWildcard; String2
0x140015a9a  lea     rcx, [rbp+57h+String1]; String1
0x140015a9e  call    cs:__imp_RtlEqualUnicodeString
0x140015aa5  nop     dword ptr [rax+rax+00h]
0x140015aaa  test    al, al
0x140015aac  jz      short loc_140015AB3
0x140015aae  mov     [rbp+57h+String1.Length], r13w
0x140015ab3  mov     r8b, 1; CaseInSensitive
0x140015ab6  lea     rdx, MupiUncHardeningWildcard; String2
0x140015abd  lea     rcx, [rbp+57h+var_70]; String1
0x140015ac1  call    cs:__imp_RtlEqualUnicodeString
0x140015ac8  nop     dword ptr [rax+rax+00h]
0x140015acd  test    al, al
0x140015acf  jz      short loc_140015ADA
0x140015ad1  mov     eax, r13d
0x140015ad4  mov     [rbp+57h+var_70.Length], ax
0x140015ad8  jmp     short loc_140015ADE
0x140015ada  movzx   eax, [rbp+57h+var_70.Length]
0x140015ade  cmp     [rbp+57h+String1.Length], r13w
0x140015ae3  jnz     short loc_140015AEA
0x140015ae5  test    ax, ax
0x140015ae8  jz      short loc_140015AF1
0x140015aea  cmp     word ptr [rbp+57h+var_50], r13w
0x140015aef  jz      short loc_140015B2C
0x140015af1  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015af8  jz      loc_140015990
0x140015afe  mov     eax, [rdi+0Ch]
0x140015b01  lea     rdx, UncHardening_UnsupportedUncPath
0x140015b08  mov     ecx, [rdi+8]
0x140015b0b  movzx   r9d, word ptr [rbp+57h+var_80]
0x140015b10  add     rcx, rdi
0x140015b13  shr     eax, 1
0x140015b15  mov     [rsp+0C0h+var_90], rcx
0x140015b1a  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140015b1e  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140015b22  mov     qword ptr [rsp+0C0h+Length], rax
0x140015b27  jmp     loc_140015BBA
0x140015b2c  lea     rax, [rbp+57h+arg_18]
0x140015b30  mov     rcx, r15
0x140015b33  lea     r8, [rbp+57h+var_70]
0x140015b37  mov     qword ptr [rsp+0C0h+Length], rax
0x140015b3c  lea     rdx, [rbp+57h+String1]
0x140015b40  call    MupiFindOrCreateUncHardeningConfigurationEntry
0x140015b45  mov     ebx, eax
0x140015b47  test    eax, eax
0x140015b49  js      loc_140015C0B
0x140015b4f  mov     ecx, [rdi+8]
0x140015b52  lea     rax, [rbp+57h+var_80]
0x140015b56  mov     edx, [rdi+0Ch]
0x140015b59  add     rcx, rdi
0x140015b5c  mov     qword ptr [rbp+57h+var_50], rax
0x140015b60  mov     rax, [rbp+57h+arg_18]
0x140015b64  mov     [rbp+57h+var_38], rax
0x140015b68  lea     rax, [rbp+57h+var_50]
0x140015b6c  mov     qword ptr [rsp+0C0h+Length], rax
0x140015b71  mov     [rbp+57h+var_3C], r13d
0x140015b75  mov     qword ptr [rbp+57h+var_50+8], rcx
0x140015b79  mov     [rbp+57h+var_40], edx
0x140015b7c  call    RfsCskvParse
0x140015b81  mov     ebx, eax
0x140015b83  test    eax, eax
0x140015b85  jns     loc_140015990
0x140015b8b  jmp     short loc_140015C0B
0x140015b8d  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015b94  jz      loc_140015990
0x140015b9a  mov     ecx, [rdi+8]
0x140015b9d  mov     eax, [rdi+0Ch]
0x140015ba0  add     rcx, rdi
0x140015ba3  mov     [rsp+0C0h+var_90], rcx
0x140015ba8  shr     eax, 1
0x140015baa  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140015bae  mov     qword ptr [rsp+0C0h+Length], rdx
0x140015bb3  lea     rdx, UncHardening_InvalidUncPath
0x140015bba  shr     r9w, 1
0x140015bbe  call    McTemplateK0hzr0qzr2_EtwWriteTransfer
0x140015bc3  jmp     loc_140015990
0x140015bc8  mov     ebx, 4855754Dh
0x140015bcd  mov     rcx, rdi; P
0x140015bd0  mov     edx, ebx; Tag
0x140015bd2  call    cs:__imp_ExFreePoolWithTag
0x140015bd9  nop     dword ptr [rax+rax+00h]
0x140015bde  mov     esi, [rbp+57h+arg_10]
0x140015be1  mov     r8d, ebx
0x140015be4  mov     edx, esi
0x140015be6  mov     ecx, 102h
0x140015beb  call    cs:__imp_ExAllocatePool2
0x140015bf2  nop     dword ptr [rax+rax+00h]
0x140015bf7  mov     rdi, rax
0x140015bfa  test    rax, rax
0x140015bfd  jnz     loc_140015990
0x140015c03  jmp     loc_140015983
0x140015c08  mov     ebx, r13d
0x140015c0b  test    rdi, rdi
0x140015c0e  jz      short loc_140015C24
0x140015c10  mov     edx, 4855754Dh; Tag
0x140015c15  mov     rcx, rdi; P
0x140015c18  call    cs:__imp_ExFreePoolWithTag
0x140015c1f  nop     dword ptr [rax+rax+00h]
0x140015c24  mov     eax, ebx
0x140015c26  mov     rbx, [rsp+0C0h+arg_0]
0x140015c2e  add     rsp, 90h
0x140015c35  pop     r15
0x140015c37  pop     r14
0x140015c39  pop     r13
0x140015c3b  pop     r12
0x140015c3d  pop     rdi
0x140015c3e  pop     rsi
0x140015c3f  pop     rbp
0x140015c40  retn
```
