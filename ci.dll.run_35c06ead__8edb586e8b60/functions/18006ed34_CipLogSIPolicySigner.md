# CipLogSIPolicySigner

- ea: `0x18006ed34`
- end: `0x18006ef8f`
- name: `CipLogSIPolicySigner`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006d84c`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18006e940`
- `0x18006ed34`
- `0x18007da80`
- `0x18009be98`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006ef5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006ef5e`
- `ntoskrnl!EtwEventEnabled` at `0x18006eda9`
- `ntoskrnl!EtwEventEnabled` at `0x18006eda9`
- `ntoskrnl!EtwWrite` at `0x18006ef43`
- `ntoskrnl!EtwWrite` at `0x18006ef43`

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
0x18006ed34  push    rbp
0x18006ed36  push    rbx
0x18006ed37  push    rsi
0x18006ed38  push    rdi
0x18006ed39  lea     rbp, [rsp-58h]
0x18006ed3e  sub     rsp, 158h
0x18006ed45  mov     rax, cs:__security_cookie
0x18006ed4c  xor     rax, rsp
0x18006ed4f  mov     [rbp+70h+var_30], rax
0x18006ed53  xorps   xmm0, xmm0
0x18006ed56  mov     rdi, rcx
0x18006ed59  xor     eax, eax
0x18006ed5b  lea     rcx, [rbp+70h+var_F0]; void *
0x18006ed5f  xor     esi, esi
0x18006ed61  mov     [rsp+170h+var_F8], rax
0x18006ed66  xor     edx, edx; Val
0x18006ed68  mov     [rsp+170h+P], rsi
0x18006ed6d  mov     r8d, 0C0h; Size
0x18006ed73  mov     [rsp+170h+var_138], esi
0x18006ed77  movups  [rsp+170h+var_128], xmm0
0x18006ed7c  movups  [rsp+170h+var_118], xmm0
0x18006ed81  movups  [rsp+170h+var_108], xmm0
0x18006ed86  call    memset
0x18006ed8b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ed92  lea     rdx, CiPolicySigner; EventDescriptor
0x18006ed99  mov     [rsp+170h+var_13C], si
0x18006ed9e  mov     ebx, esi
0x18006eda0  mov     [rsp+170h+var_140], si
0x18006eda5  mov     [rsp+170h+var_134], esi
0x18006eda9  call    cs:__imp_EtwEventEnabled
0x18006edb0  nop     dword ptr [rax+rax+00h]
0x18006edb5  test    al, al
0x18006edb7  jz      loc_18006EF6A
0x18006edbd  lea     rdx, [rsp+170h+var_128]
0x18006edc2  mov     rcx, rdi
0x18006edc5  call    SIPolicyGetPolicySigner
0x18006edca  test    eax, eax
0x18006edcc  jns     short loc_18006EDDB
0x18006edce  cmp     eax, 0C0E90004h
0x18006edd3  cmovnz  ebx, eax
0x18006edd6  jmp     loc_18006EF6A
0x18006eddb  cmp     dword ptr [rdi+28h], 6
0x18006eddf  mov     r9d, dword ptr [rsp+170h+var_108]
0x18006ede4  sbb     rax, rax
0x18006ede7  mov     qword ptr [rbp+70h+var_F0.Size], 10h
0x18006edef  and     rax, 0FFFFFFFFFFFFFD50h
0x18006edf5  mov     [rbp+70h+var_98], 4
0x18006edfd  add     rax, 2C0h
0x18006ee03  mov     [rbp+70h+var_78], 4
0x18006ee0b  add     rax, rdi
0x18006ee0e  mov     [rbp+70h+var_F0.Ptr], rax
0x18006ee12  lea     rax, [rsp+170h+var_134]
0x18006ee17  mov     [rbp+70h+var_A0], rax
0x18006ee1b  lea     rax, [rsp+170h+var_134]
0x18006ee20  mov     [rbp+70h+var_80], rax
0x18006ee24  test    r9d, r9d
0x18006ee27  jz      short loc_18006EE6E
0x18006ee29  mov     rdx, qword ptr [rsp+170h+var_118+8]
0x18006ee2e  lea     rax, [rdx+4]
0x18006ee32  mov     [rbp+70h+var_A0], rax
0x18006ee36  lea     r8, [rdx+10h]
0x18006ee3a  mov     ecx, [rax]
0x18006ee3c  lea     r10, [rdx+20h]
0x18006ee40  mov     rax, [rdx+8]
0x18006ee44  mov     [rbp+70h+var_90], rax
0x18006ee48  mov     [rbp+70h+var_88], ecx
0x18006ee4b  mov     [rbp+70h+var_84], esi
0x18006ee4e  cmp     r9d, 1
0x18006ee52  jbe     short loc_18006EE78
0x18006ee54  lea     rax, [rdx+34h]
0x18006ee58  mov     [rbp+70h+var_80], rax
0x18006ee5c  mov     ecx, [rax]
0x18006ee5e  mov     rax, [rdx+38h]
0x18006ee62  mov     [rbp+70h+var_70], rax
0x18006ee66  mov     [rbp+70h+var_68], ecx
0x18006ee69  mov     [rbp+70h+var_64], esi
0x18006ee6c  jmp     short loc_18006EE78
0x18006ee6e  lea     r8, g_CiUnknown
0x18006ee75  mov     r10, r8
0x18006ee78  movzx   eax, word ptr [r8]
0x18006ee7c  lea     r9, [rsp+170h+P]
0x18006ee81  mov     edx, dword ptr [rsp+170h+var_118]
0x18006ee85  shr     ax, 1
0x18006ee88  mov     [rsp+170h+var_140], ax
0x18006ee8d  lea     rax, [rsp+170h+var_140]
0x18006ee92  mov     [rbp+70h+var_E0], rax
0x18006ee96  mov     [rbp+70h+var_D8], 2
0x18006ee9e  movzx   ecx, word ptr [r8]
0x18006eea2  mov     rax, [r8+8]
0x18006eea6  lea     r8, [rsp+170h+var_138]
0x18006eeab  mov     [rbp+70h+var_D0], rax
0x18006eeaf  mov     [rbp+70h+var_C8], ecx
0x18006eeb2  mov     [rbp+70h+var_C4], esi
0x18006eeb5  movzx   eax, word ptr [r10]
0x18006eeb9  shr     ax, 1
0x18006eebc  mov     [rsp+170h+var_13C], ax
0x18006eec1  lea     rax, [rsp+170h+var_13C]
0x18006eec6  mov     [rbp+70h+var_C0], rax
0x18006eeca  mov     [rbp+70h+var_B8], 2
0x18006eed2  movzx   ecx, word ptr [r10]
0x18006eed6  mov     rax, [r10+8]
0x18006eeda  mov     [rbp+70h+var_A8], ecx
0x18006eedd  mov     rcx, qword ptr [rsp+170h+var_128+8]
0x18006eee2  mov     [rbp+70h+var_B0], rax
0x18006eee6  mov     [rbp+70h+var_A4], esi
0x18006eee9  call    CipCollectEKUsIntoArray
0x18006eeee  mov     rdi, [rsp+170h+P]
0x18006eef3  lea     rax, [rsp+170h+var_138]
0x18006eef8  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006eeff  lea     rdx, CiPolicySigner; EventDescriptor
0x18006ef06  mov     [rbp+70h+var_60], rax
0x18006ef0a  mov     r9d, 0Ch; UserDataCount
0x18006ef10  mov     eax, [rsp+170h+var_138]
0x18006ef14  xor     r8d, r8d; ActivityId
0x18006ef17  mov     [rbp+70h+var_48], eax
0x18006ef1a  lea     rax, [rsp+170h+var_108+4]
0x18006ef1f  mov     [rbp+70h+var_40], rax
0x18006ef23  lea     rax, [rbp+70h+var_F0]
0x18006ef27  mov     [rsp+170h+UserData], rax; UserData
0x18006ef2c  mov     [rbp+70h+var_58], 4
0x18006ef34  mov     [rbp+70h+var_50], rdi
0x18006ef38  mov     [rbp+70h+var_44], esi
0x18006ef3b  mov     [rbp+70h+var_38], 4
0x18006ef43  call    cs:__imp_EtwWrite
0x18006ef4a  nop     dword ptr [rax+rax+00h]
0x18006ef4f  mov     ebx, eax
0x18006ef51  test    rdi, rdi
0x18006ef54  jz      short loc_18006EF6A
0x18006ef56  mov     edx, 63734943h; Tag
0x18006ef5b  mov     rcx, rdi; P
0x18006ef5e  call    cs:__imp_ExFreePoolWithTag
0x18006ef65  nop     dword ptr [rax+rax+00h]
0x18006ef6a  lea     rcx, [rsp+170h+var_128]
0x18006ef6f  call    SIPolicyFreeSIChainInfo
0x18006ef74  mov     eax, ebx
0x18006ef76  mov     rcx, [rbp+70h+var_30]
0x18006ef7a  xor     rcx, rsp; StackCookie
0x18006ef7d  call    __security_check_cookie
0x18006ef82  add     rsp, 158h
0x18006ef89  pop     rdi
0x18006ef8a  pop     rsi
0x18006ef8b  pop     rbx
0x18006ef8c  pop     rbp
0x18006ef8d  retn
```
