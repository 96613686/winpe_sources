# CipLogSIPolicySigner

- ea: `0x18006ea54`
- end: `0x18006ecaf`
- name: `CipLogSIPolicySigner`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006d56c`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18006e660`
- `0x18006ea54`
- `0x18007d06c`
- `0x1800a2014`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006ec7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006ec7e`
- `ntoskrnl!EtwEventEnabled` at `0x18006eac9`
- `ntoskrnl!EtwEventEnabled` at `0x18006eac9`
- `ntoskrnl!EtwWrite` at `0x18006ec63`
- `ntoskrnl!EtwWrite` at `0x18006ec63`

## pseudocode

```c
__int64 __fastcall CipLogSIPolicySigner(__int64 a1)
{
  unsigned int v2; // ebx
  int PolicySigner; // eax
  __int64 v4; // rax
  char *v5; // r8
  ULONG v6; // ecx
  char *v7; // r10
  ULONG v8; // ecx
  ULONG v9; // ecx
  ULONGLONG v10; // rax
  PVOID v11; // rdi
  __int16 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+3Ch] [rbp-C4h] BYREF
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  struct _EVENT_DATA_DESCRIPTOR UserData[12]; // [rsp+80h] [rbp-80h] BYREF

  v21 = 0;
  P = 0;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset(UserData, 0, sizeof(UserData));
  v14 = 0;
  v2 = 0;
  v13 = 0;
  v16 = 0;
  if ( EtwEventEnabled(g_EtwEventHandle, &CiPolicySigner) )
  {
    PolicySigner = SIPolicyGetPolicySigner(a1, &v18);
    if ( PolicySigner >= 0 )
    {
      v4 = -(__int64)(*(_DWORD *)(a1 + 40) < 6u);
      *(_QWORD *)&UserData[0].Size = 16;
      *(_QWORD *)&UserData[5].Size = 4;
      *(_QWORD *)&UserData[7].Size = 4;
      UserData[0].Ptr = a1 + (v4 & 0xFFFFFFFFFFFFFD50uLL) + 704;
      UserData[5].Ptr = (ULONGLONG)&v16;
      UserData[7].Ptr = (ULONGLONG)&v16;
      if ( (_DWORD)v20 )
      {
        UserData[5].Ptr = *((_QWORD *)&v19 + 1) + 4LL;
        v5 = (char *)(*((_QWORD *)&v19 + 1) + 16LL);
        v6 = *(_DWORD *)(*((_QWORD *)&v19 + 1) + 4LL);
        v7 = (char *)(*((_QWORD *)&v19 + 1) + 32LL);
        UserData[6].Ptr = *(_QWORD *)(*((_QWORD *)&v19 + 1) + 8LL);
        UserData[6].Size = v6;
        UserData[6].Reserved = 0;
        if ( (unsigned int)v20 > 1 )
        {
          UserData[7].Ptr = *((_QWORD *)&v19 + 1) + 52LL;
          v8 = *(_DWORD *)(*((_QWORD *)&v19 + 1) + 52LL);
          UserData[8].Ptr = *(_QWORD *)(*((_QWORD *)&v19 + 1) + 56LL);
          UserData[8].Size = v8;
          UserData[8].Reserved = 0;
        }
      }
      else
      {
        v5 = g_CiUnknown;
        v7 = g_CiUnknown;
      }
      v13 = *(_WORD *)v5 >> 1;
      UserData[1].Ptr = (ULONGLONG)&v13;
      *(_QWORD *)&UserData[1].Size = 2;
      v9 = *(unsigned __int16 *)v5;
      UserData[2].Ptr = *((_QWORD *)v5 + 1);
      UserData[2].Size = v9;
      UserData[2].Reserved = 0;
      v14 = *(_WORD *)v7 >> 1;
      UserData[3].Ptr = (ULONGLONG)&v14;
      *(_QWORD *)&UserData[3].Size = 2;
      v10 = *((_QWORD *)v7 + 1);
      UserData[4].Size = *(unsigned __int16 *)v7;
      UserData[4].Ptr = v10;
      UserData[4].Reserved = 0;
      CipCollectEKUsIntoArray(*((_QWORD *)&v18 + 1), (unsigned int)v19, &v15, &P);
      v11 = P;
      UserData[9].Ptr = (ULONGLONG)&v15;
      UserData[10].Size = v15;
      UserData[11].Ptr = (ULONGLONG)&v20 + 4;
      *(_QWORD *)&UserData[9].Size = 4;
      UserData[10].Ptr = (ULONGLONG)P;
      UserData[10].Reserved = 0;
      *(_QWORD *)&UserData[11].Size = 4;
      v2 = EtwWrite(g_EtwEventHandle, &CiPolicySigner, 0, 0xCu, UserData);
      if ( v11 )
        ExFreePoolWithTag(v11, 0x63734943u);
    }
    else if ( PolicySigner != -1058471932 )
    {
      v2 = PolicySigner;
    }
  }
  SIPolicyFreeSIChainInfo(&v18);
  return v2;
}

```

## disassembly

```asm
0x18006ea54  push    rbp
0x18006ea56  push    rbx
0x18006ea57  push    rsi
0x18006ea58  push    rdi
0x18006ea59  lea     rbp, [rsp-58h]
0x18006ea5e  sub     rsp, 158h
0x18006ea65  mov     rax, cs:__security_cookie
0x18006ea6c  xor     rax, rsp
0x18006ea6f  mov     [rbp+70h+var_30], rax
0x18006ea73  xorps   xmm0, xmm0
0x18006ea76  mov     rdi, rcx
0x18006ea79  xor     eax, eax
0x18006ea7b  lea     rcx, [rbp+70h+var_F0]; void *
0x18006ea7f  xor     esi, esi
0x18006ea81  mov     [rsp+170h+var_F8], rax
0x18006ea86  xor     edx, edx; Val
0x18006ea88  mov     [rsp+170h+P], rsi
0x18006ea8d  mov     r8d, 0C0h; Size
0x18006ea93  mov     [rsp+170h+var_138], esi
0x18006ea97  movups  [rsp+170h+var_128], xmm0
0x18006ea9c  movups  [rsp+170h+var_118], xmm0
0x18006eaa1  movups  [rsp+170h+var_108], xmm0
0x18006eaa6  call    memset
0x18006eaab  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006eab2  lea     rdx, CiPolicySigner; EventDescriptor
0x18006eab9  mov     [rsp+170h+var_13C], si
0x18006eabe  mov     ebx, esi
0x18006eac0  mov     [rsp+170h+var_140], si
0x18006eac5  mov     [rsp+170h+var_134], esi
0x18006eac9  call    cs:__imp_EtwEventEnabled
0x18006ead0  nop     dword ptr [rax+rax+00h]
0x18006ead5  test    al, al
0x18006ead7  jz      loc_18006EC8A
0x18006eadd  lea     rdx, [rsp+170h+var_128]
0x18006eae2  mov     rcx, rdi
0x18006eae5  call    SIPolicyGetPolicySigner
0x18006eaea  test    eax, eax
0x18006eaec  jns     short loc_18006EAFB
0x18006eaee  cmp     eax, 0C0E90004h
0x18006eaf3  cmovnz  ebx, eax
0x18006eaf6  jmp     loc_18006EC8A
0x18006eafb  cmp     dword ptr [rdi+28h], 6
0x18006eaff  mov     r9d, dword ptr [rsp+170h+var_108]
0x18006eb04  sbb     rax, rax
0x18006eb07  mov     qword ptr [rbp+70h+var_F0.Size], 10h
0x18006eb0f  and     rax, 0FFFFFFFFFFFFFD50h
0x18006eb15  mov     [rbp+70h+var_98], 4
0x18006eb1d  add     rax, 2C0h
0x18006eb23  mov     [rbp+70h+var_78], 4
0x18006eb2b  add     rax, rdi
0x18006eb2e  mov     [rbp+70h+var_F0.Ptr], rax
0x18006eb32  lea     rax, [rsp+170h+var_134]
0x18006eb37  mov     [rbp+70h+var_A0], rax
0x18006eb3b  lea     rax, [rsp+170h+var_134]
0x18006eb40  mov     [rbp+70h+var_80], rax
0x18006eb44  test    r9d, r9d
0x18006eb47  jz      short loc_18006EB8E
0x18006eb49  mov     rdx, qword ptr [rsp+170h+var_118+8]
0x18006eb4e  lea     rax, [rdx+4]
0x18006eb52  mov     [rbp+70h+var_A0], rax
0x18006eb56  lea     r8, [rdx+10h]
0x18006eb5a  mov     ecx, [rax]
0x18006eb5c  lea     r10, [rdx+20h]
0x18006eb60  mov     rax, [rdx+8]
0x18006eb64  mov     [rbp+70h+var_90], rax
0x18006eb68  mov     [rbp+70h+var_88], ecx
0x18006eb6b  mov     [rbp+70h+var_84], esi
0x18006eb6e  cmp     r9d, 1
0x18006eb72  jbe     short loc_18006EB98
0x18006eb74  lea     rax, [rdx+34h]
0x18006eb78  mov     [rbp+70h+var_80], rax
0x18006eb7c  mov     ecx, [rax]
0x18006eb7e  mov     rax, [rdx+38h]
0x18006eb82  mov     [rbp+70h+var_70], rax
0x18006eb86  mov     [rbp+70h+var_68], ecx
0x18006eb89  mov     [rbp+70h+var_64], esi
0x18006eb8c  jmp     short loc_18006EB98
0x18006eb8e  lea     r8, g_CiUnknown
0x18006eb95  mov     r10, r8
0x18006eb98  movzx   eax, word ptr [r8]
0x18006eb9c  lea     r9, [rsp+170h+P]
0x18006eba1  mov     edx, dword ptr [rsp+170h+var_118]
0x18006eba5  shr     ax, 1
0x18006eba8  mov     [rsp+170h+var_140], ax
0x18006ebad  lea     rax, [rsp+170h+var_140]
0x18006ebb2  mov     [rbp+70h+var_E0], rax
0x18006ebb6  mov     [rbp+70h+var_D8], 2
0x18006ebbe  movzx   ecx, word ptr [r8]
0x18006ebc2  mov     rax, [r8+8]
0x18006ebc6  lea     r8, [rsp+170h+var_138]
0x18006ebcb  mov     [rbp+70h+var_D0], rax
0x18006ebcf  mov     [rbp+70h+var_C8], ecx
0x18006ebd2  mov     [rbp+70h+var_C4], esi
0x18006ebd5  movzx   eax, word ptr [r10]
0x18006ebd9  shr     ax, 1
0x18006ebdc  mov     [rsp+170h+var_13C], ax
0x18006ebe1  lea     rax, [rsp+170h+var_13C]
0x18006ebe6  mov     [rbp+70h+var_C0], rax
0x18006ebea  mov     [rbp+70h+var_B8], 2
0x18006ebf2  movzx   ecx, word ptr [r10]
0x18006ebf6  mov     rax, [r10+8]
0x18006ebfa  mov     [rbp+70h+var_A8], ecx
0x18006ebfd  mov     rcx, qword ptr [rsp+170h+var_128+8]
0x18006ec02  mov     [rbp+70h+var_B0], rax
0x18006ec06  mov     [rbp+70h+var_A4], esi
0x18006ec09  call    CipCollectEKUsIntoArray
0x18006ec0e  mov     rdi, [rsp+170h+P]
0x18006ec13  lea     rax, [rsp+170h+var_138]
0x18006ec18  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ec1f  lea     rdx, CiPolicySigner; EventDescriptor
0x18006ec26  mov     [rbp+70h+var_60], rax
0x18006ec2a  mov     r9d, 0Ch; UserDataCount
0x18006ec30  mov     eax, [rsp+170h+var_138]
0x18006ec34  xor     r8d, r8d; ActivityId
0x18006ec37  mov     [rbp+70h+var_48], eax
0x18006ec3a  lea     rax, [rsp+170h+var_108+4]
0x18006ec3f  mov     [rbp+70h+var_40], rax
0x18006ec43  lea     rax, [rbp+70h+var_F0]
0x18006ec47  mov     [rsp+170h+UserData], rax; UserData
0x18006ec4c  mov     [rbp+70h+var_58], 4
0x18006ec54  mov     [rbp+70h+var_50], rdi
0x18006ec58  mov     [rbp+70h+var_44], esi
0x18006ec5b  mov     [rbp+70h+var_38], 4
0x18006ec63  call    cs:__imp_EtwWrite
0x18006ec6a  nop     dword ptr [rax+rax+00h]
0x18006ec6f  mov     ebx, eax
0x18006ec71  test    rdi, rdi
0x18006ec74  jz      short loc_18006EC8A
0x18006ec76  mov     edx, 63734943h; Tag
0x18006ec7b  mov     rcx, rdi; P
0x18006ec7e  call    cs:__imp_ExFreePoolWithTag
0x18006ec85  nop     dword ptr [rax+rax+00h]
0x18006ec8a  lea     rcx, [rsp+170h+var_128]
0x18006ec8f  call    SIPolicyFreeSIChainInfo
0x18006ec94  mov     eax, ebx
0x18006ec96  mov     rcx, [rbp+70h+var_30]
0x18006ec9a  xor     rcx, rsp; StackCookie
0x18006ec9d  call    __security_check_cookie
0x18006eca2  add     rsp, 158h
0x18006eca9  pop     rdi
0x18006ecaa  pop     rsi
0x18006ecab  pop     rbx
0x18006ecac  pop     rbp
0x18006ecad  retn
```
