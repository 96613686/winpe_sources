# MupiLoadUncHardeningConfigurationToList

- ea: `0x140015980`
- end: `0x140015c92`
- name: `MupiLoadUncHardeningConfigurationToList`
- size: `786`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014bc0`
- `0x140014ef0`

## callees

- `0x1400013e0`
- `0x1400041b8`
- `0x14000426c`
- `0x1400157a0`
- `0x140015980`
- `0x1400179d8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400159bf`
- `ntoskrnl!ExAllocatePool2` at `0x140015c3b`
- `ntoskrnl!ExAllocatePool2` at `0x1400159bf`
- `ntoskrnl!ExAllocatePool2` at `0x140015c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c68`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015aee`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015b11`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015aee`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015b11`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140015a03`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140015a03`

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
  __int64 v13; // r9
  USHORT v14; // ax
  __int64 *v15; // rdx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // edx
  WCHAR *v20; // rcx
  int Length; // [rsp+20h] [rbp-49h]
  __int64 Lengtha; // [rsp+20h] [rbp-49h]
  int ResultLength; // [rsp+28h] [rbp-41h]
  __int64 v25; // [rsp+30h] [rbp-39h]
  __int128 v26; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING v27; // [rsp+50h] [rbp-19h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING v29; // [rsp+70h] [rbp+7h] BYREF
  int v30; // [rsp+80h] [rbp+17h]
  int v31; // [rsp+84h] [rbp+1Bh]
  const UNICODE_STRING *v32; // [rsp+88h] [rbp+1Fh]
  ULONG v33; // [rsp+E0h] [rbp+77h] BYREF
  const UNICODE_STRING *v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = 1024;
  v34 = 0;
  v33 = 0;
  Pool2 = ExAllocatePool2(258, 1024, 1213560141);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v7 = 0;
  while ( 1 )
  {
    v26 = 0;
    v8 = ZwEnumerateValueKey(KeyHandle, v7, KeyValueFullInformation, (PVOID)Pool2, v4, &v33);
    v6 = v8;
    if ( v8 == -2147483622 )
      break;
    if ( v8 == -2147483643 || v8 == -1073741789 )
    {
      ExFreePoolWithTag((PVOID)Pool2, 0x4855754Du);
      v4 = v33;
      Pool2 = ExAllocatePool2(258, v33, 1213560141);
      if ( !Pool2 )
        return (unsigned int)-1073741670;
    }
    else
    {
      if ( v8 < 0 )
        goto LABEL_35;
      v10 = (_WORD *)(Pool2 + 20);
      ++v7;
      *((_QWORD *)&v26 + 1) = Pool2 + 20;
      v11 = *(unsigned __int16 *)(Pool2 + 16);
      WORD1(v26) = v11;
      LOWORD(v26) = v11;
      if ( (_WORD)v11 )
      {
        v12 = *(unsigned int *)(Pool2 + 4);
        if ( (_DWORD)v12 == 1 || (_DWORD)v12 == 7 )
        {
          if ( (unsigned __int16)v11 >= 4u && *v10 == 92 && *(_WORD *)(Pool2 + 22) == 92 )
          {
            String1 = 0;
            v27 = 0;
            v29 = 0;
            MupiGetPathComponents((__int64)&v26, &String1, &v27, 0, &v29);
            if ( RtlEqualUnicodeString(&String1, &MupiUncHardeningWildcard, 1u) )
              String1.Length = 0;
            if ( RtlEqualUnicodeString(&v27, &MupiUncHardeningWildcard, 1u) )
            {
              v14 = 0;
              v27.Length = 0;
            }
            else
            {
              v14 = v27.Length;
            }
            if ( (String1.Length || v14) && !v29.Length )
            {
              v6 = MupiFindOrCreateUncHardeningConfigurationEntry(a2, &String1, &v27, v13, &v34);
              if ( v6 < 0 )
                goto LABEL_35;
              v19 = *(_DWORD *)(Pool2 + 12);
              v20 = (WCHAR *)(Pool2 + *(unsigned int *)(Pool2 + 8));
              *(_QWORD *)&v29.Length = &v26;
              v32 = v34;
              v31 = 0;
              v29.Buffer = v20;
              v30 = v19;
              v6 = RfsCskvParse((_DWORD)v20, v19, v17, v18, (__int64)&v29);
              if ( v6 < 0 )
                goto LABEL_35;
            }
            else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
            {
              v15 = UncHardening_UnsupportedUncPath;
              LODWORD(v11) = (unsigned __int16)v26;
              v16 = Pool2 + *(_DWORD *)(Pool2 + 8);
              v25 = Pool2 + *(unsigned int *)(Pool2 + 8);
              ResultLength = *(_DWORD *)(Pool2 + 12) >> 1;
              Lengtha = *((_QWORD *)&v26 + 1);
              goto LABEL_31;
            }
          }
          else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
          {
            v16 = Pool2 + *(_DWORD *)(Pool2 + 8);
            v25 = Pool2 + *(unsigned int *)(Pool2 + 8);
            ResultLength = *(_DWORD *)(Pool2 + 12) >> 1;
            Lengtha = Pool2 + 20;
            v15 = UncHardening_InvalidUncPath;
LABEL_31:
            LOWORD(v11) = (unsigned __int16)v11 >> 1;
            McTemplateK0hzr0qzr2_EtwWriteTransfer(v16, (_DWORD)v15, v9, v11, Lengtha, ResultLength, v25);
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
0x140015980  mov     [rsp-8+arg_0], rbx
0x140015985  push    rbp
0x140015986  push    rsi
0x140015987  push    rdi
0x140015988  push    r12
0x14001598a  push    r13
0x14001598c  push    r14
0x14001598e  push    r15
0x140015990  lea     rbp, [rsp-27h]
0x140015995  sub     rsp, 90h
0x14001599c  mov     r15, rdx
0x14001599f  mov     r12, rcx
0x1400159a2  xor     r13d, r13d
0x1400159a5  mov     esi, 400h
0x1400159aa  mov     edx, esi
0x1400159ac  mov     [rbp+57h+arg_18], r13
0x1400159b0  mov     r8d, 4855754Dh
0x1400159b6  mov     [rbp+57h+arg_10], r13d
0x1400159ba  mov     ecx, 102h
0x1400159bf  call    cs:__imp_ExAllocatePool2
0x1400159c6  nop     dword ptr [rax+rax+00h]
0x1400159cb  mov     rdi, rax
0x1400159ce  test    rax, rax
0x1400159d1  jnz     short loc_1400159DD
0x1400159d3  mov     ebx, 0C000009Ah
0x1400159d8  jmp     loc_140015C74
0x1400159dd  mov     r14d, r13d
0x1400159e0  lea     rax, [rbp+57h+arg_10]
0x1400159e4  xorps   xmm0, xmm0
0x1400159e7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400159ec  mov     r9, rdi; KeyValueInformation
0x1400159ef  mov     r8d, 1; KeyValueInformationClass
0x1400159f5  mov     [rsp+0C0h+Length], esi; Length
0x1400159f9  mov     edx, r14d; Index
0x1400159fc  mov     rcx, r12; KeyHandle
0x1400159ff  movups  [rbp+57h+var_80], xmm0
0x140015a03  call    cs:__imp_ZwEnumerateValueKey
0x140015a0a  nop     dword ptr [rax+rax+00h]
0x140015a0f  mov     ebx, eax
0x140015a11  cmp     eax, 8000001Ah
0x140015a16  jz      loc_140015C58
0x140015a1c  cmp     eax, 80000005h
0x140015a21  jz      loc_140015C18
0x140015a27  cmp     eax, 0C0000023h
0x140015a2c  jz      loc_140015C18
0x140015a32  test    eax, eax
0x140015a34  js      loc_140015C5B
0x140015a3a  lea     rdx, [rdi+14h]
0x140015a3e  inc     r14d
0x140015a41  mov     qword ptr [rbp+57h+var_80+8], rdx
0x140015a45  movzx   r9d, word ptr [rdi+10h]
0x140015a4a  mov     word ptr [rbp+57h+var_80+2], r9w
0x140015a4f  mov     word ptr [rbp+57h+var_80], r9w
0x140015a54  test    r9w, r9w
0x140015a58  jz      short loc_1400159E0
0x140015a5a  mov     ecx, [rdi+4]
0x140015a5d  cmp     ecx, 1
0x140015a60  jz      short loc_140015A91
0x140015a62  cmp     ecx, 7
0x140015a65  jz      short loc_140015A91
0x140015a67  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015a6e  jz      loc_1400159E0
0x140015a74  mov     [rsp+0C0h+var_88], ecx
0x140015a78  shr     r9w, 1
0x140015a7c  mov     [rsp+0C0h+var_90], rdx
0x140015a81  mov     word ptr [rsp+0C0h+ResultLength], r9w
0x140015a87  call    McTemplateK0hzr0hzr2q_EtwWriteTransfer
0x140015a8c  jmp     loc_1400159E0
0x140015a91  cmp     r9w, 4
0x140015a96  jb      loc_140015BDD
0x140015a9c  cmp     word ptr [rdx], 5Ch ; '\'
0x140015aa0  jnz     loc_140015BDD
0x140015aa6  cmp     word ptr [rdx+2], 5Ch ; '\'
0x140015aab  jnz     loc_140015BDD
0x140015ab1  xorps   xmm0, xmm0
0x140015ab4  lea     rax, [rbp+57h+var_50]
0x140015ab8  xorps   xmm1, xmm1
0x140015abb  mov     qword ptr [rsp+0C0h+Length], rax
0x140015ac0  xor     r9d, r9d
0x140015ac3  lea     r8, [rbp+57h+var_70]
0x140015ac7  lea     rdx, [rbp+57h+String1]
0x140015acb  lea     rcx, [rbp+57h+var_80]
0x140015acf  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140015ad3  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x140015ad7  movups  [rbp+57h+var_50], xmm0
0x140015adb  call    MupiGetPathComponents
0x140015ae0  mov     r8b, 1; CaseInSensitive
0x140015ae3  lea     rdx, MupiUncHardeningWildcard; String2
0x140015aea  lea     rcx, [rbp+57h+String1]; String1
0x140015aee  call    cs:__imp_RtlEqualUnicodeString
0x140015af5  nop     dword ptr [rax+rax+00h]
0x140015afa  test    al, al
0x140015afc  jz      short loc_140015B03
0x140015afe  mov     [rbp+57h+String1.Length], r13w
0x140015b03  mov     r8b, 1; CaseInSensitive
0x140015b06  lea     rdx, MupiUncHardeningWildcard; String2
0x140015b0d  lea     rcx, [rbp+57h+var_70]; String1
0x140015b11  call    cs:__imp_RtlEqualUnicodeString
0x140015b18  nop     dword ptr [rax+rax+00h]
0x140015b1d  test    al, al
0x140015b1f  jz      short loc_140015B2A
0x140015b21  mov     eax, r13d
0x140015b24  mov     [rbp+57h+var_70.Length], ax
0x140015b28  jmp     short loc_140015B2E
0x140015b2a  movzx   eax, [rbp+57h+var_70.Length]
0x140015b2e  cmp     [rbp+57h+String1.Length], r13w
0x140015b33  jnz     short loc_140015B3A
0x140015b35  test    ax, ax
0x140015b38  jz      short loc_140015B41
0x140015b3a  cmp     word ptr [rbp+57h+var_50], r13w
0x140015b3f  jz      short loc_140015B7C
0x140015b41  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015b48  jz      loc_1400159E0
0x140015b4e  mov     eax, [rdi+0Ch]
0x140015b51  lea     rdx, UncHardening_UnsupportedUncPath
0x140015b58  mov     ecx, [rdi+8]
0x140015b5b  movzx   r9d, word ptr [rbp+57h+var_80]
0x140015b60  add     rcx, rdi
0x140015b63  shr     eax, 1
0x140015b65  mov     [rsp+0C0h+var_90], rcx
0x140015b6a  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140015b6e  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140015b72  mov     qword ptr [rsp+0C0h+Length], rax
0x140015b77  jmp     loc_140015C0A
0x140015b7c  lea     rax, [rbp+57h+arg_18]
0x140015b80  mov     rcx, r15
0x140015b83  lea     r8, [rbp+57h+var_70]
0x140015b87  mov     qword ptr [rsp+0C0h+Length], rax
0x140015b8c  lea     rdx, [rbp+57h+String1]
0x140015b90  call    MupiFindOrCreateUncHardeningConfigurationEntry
0x140015b95  mov     ebx, eax
0x140015b97  test    eax, eax
0x140015b99  js      loc_140015C5B
0x140015b9f  mov     ecx, [rdi+8]
0x140015ba2  lea     rax, [rbp+57h+var_80]
0x140015ba6  mov     edx, [rdi+0Ch]
0x140015ba9  add     rcx, rdi
0x140015bac  mov     qword ptr [rbp+57h+var_50], rax
0x140015bb0  mov     rax, [rbp+57h+arg_18]
0x140015bb4  mov     [rbp+57h+var_38], rax
0x140015bb8  lea     rax, [rbp+57h+var_50]
0x140015bbc  mov     qword ptr [rsp+0C0h+Length], rax
0x140015bc1  mov     [rbp+57h+var_3C], r13d
0x140015bc5  mov     qword ptr [rbp+57h+var_50+8], rcx
0x140015bc9  mov     [rbp+57h+var_40], edx
0x140015bcc  call    RfsCskvParse
0x140015bd1  mov     ebx, eax
0x140015bd3  test    eax, eax
0x140015bd5  jns     loc_1400159E0
0x140015bdb  jmp     short loc_140015C5B
0x140015bdd  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140015be4  jz      loc_1400159E0
0x140015bea  mov     ecx, [rdi+8]
0x140015bed  mov     eax, [rdi+0Ch]
0x140015bf0  add     rcx, rdi
0x140015bf3  mov     [rsp+0C0h+var_90], rcx
0x140015bf8  shr     eax, 1
0x140015bfa  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x140015bfe  mov     qword ptr [rsp+0C0h+Length], rdx
0x140015c03  lea     rdx, UncHardening_InvalidUncPath
0x140015c0a  shr     r9w, 1
0x140015c0e  call    McTemplateK0hzr0qzr2_EtwWriteTransfer
0x140015c13  jmp     loc_1400159E0
0x140015c18  mov     ebx, 4855754Dh
0x140015c1d  mov     rcx, rdi; P
0x140015c20  mov     edx, ebx; Tag
0x140015c22  call    cs:__imp_ExFreePoolWithTag
0x140015c29  nop     dword ptr [rax+rax+00h]
0x140015c2e  mov     esi, [rbp+57h+arg_10]
0x140015c31  mov     r8d, ebx
0x140015c34  mov     edx, esi
0x140015c36  mov     ecx, 102h
0x140015c3b  call    cs:__imp_ExAllocatePool2
0x140015c42  nop     dword ptr [rax+rax+00h]
0x140015c47  mov     rdi, rax
0x140015c4a  test    rax, rax
0x140015c4d  jnz     loc_1400159E0
0x140015c53  jmp     loc_1400159D3
0x140015c58  mov     ebx, r13d
0x140015c5b  test    rdi, rdi
0x140015c5e  jz      short loc_140015C74
0x140015c60  mov     edx, 4855754Dh; Tag
0x140015c65  mov     rcx, rdi; P
0x140015c68  call    cs:__imp_ExFreePoolWithTag
0x140015c6f  nop     dword ptr [rax+rax+00h]
0x140015c74  mov     eax, ebx
0x140015c76  mov     rbx, [rsp+0C0h+arg_0]
0x140015c7e  add     rsp, 90h
0x140015c85  pop     r15
0x140015c87  pop     r14
0x140015c89  pop     r13
0x140015c8b  pop     r12
0x140015c8d  pop     rdi
0x140015c8e  pop     rsi
0x140015c8f  pop     rbp
0x140015c90  retn
```
