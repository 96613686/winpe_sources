# CipLogSIPolicySigner

- ea: `0x18006dc80`
- end: `0x18006dedb`
- name: `CipLogSIPolicySigner`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006c798`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006d88c`
- `0x18006dc80`
- `0x18007babc`
- `0x1800a09e4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006deaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006deaa`
- `ntoskrnl!EtwEventEnabled` at `0x18006dcf5`
- `ntoskrnl!EtwEventEnabled` at `0x18006dcf5`
- `ntoskrnl!EtwWrite` at `0x18006de8f`
- `ntoskrnl!EtwWrite` at `0x18006de8f`

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
0x18006dc80  push    rbp
0x18006dc82  push    rbx
0x18006dc83  push    rsi
0x18006dc84  push    rdi
0x18006dc85  lea     rbp, [rsp-58h]
0x18006dc8a  sub     rsp, 158h
0x18006dc91  mov     rax, cs:__security_cookie
0x18006dc98  xor     rax, rsp
0x18006dc9b  mov     [rbp+70h+var_30], rax
0x18006dc9f  xorps   xmm0, xmm0
0x18006dca2  mov     rdi, rcx
0x18006dca5  xor     eax, eax
0x18006dca7  lea     rcx, [rbp+70h+var_F0]; void *
0x18006dcab  xor     esi, esi
0x18006dcad  mov     [rsp+170h+var_F8], rax
0x18006dcb2  xor     edx, edx; Val
0x18006dcb4  mov     [rsp+170h+P], rsi
0x18006dcb9  mov     r8d, 0C0h; Size
0x18006dcbf  mov     [rsp+170h+var_138], esi
0x18006dcc3  movups  [rsp+170h+var_128], xmm0
0x18006dcc8  movups  [rsp+170h+var_118], xmm0
0x18006dccd  movups  [rsp+170h+var_108], xmm0
0x18006dcd2  call    memset
0x18006dcd7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006dcde  lea     rdx, CiPolicySigner; EventDescriptor
0x18006dce5  mov     [rsp+170h+var_13C], si
0x18006dcea  mov     ebx, esi
0x18006dcec  mov     [rsp+170h+var_140], si
0x18006dcf1  mov     [rsp+170h+var_134], esi
0x18006dcf5  call    cs:__imp_EtwEventEnabled
0x18006dcfc  nop     dword ptr [rax+rax+00h]
0x18006dd01  test    al, al
0x18006dd03  jz      loc_18006DEB6
0x18006dd09  lea     rdx, [rsp+170h+var_128]
0x18006dd0e  mov     rcx, rdi
0x18006dd11  call    SIPolicyGetPolicySigner
0x18006dd16  test    eax, eax
0x18006dd18  jns     short loc_18006DD27
0x18006dd1a  cmp     eax, 0C0E90004h
0x18006dd1f  cmovnz  ebx, eax
0x18006dd22  jmp     loc_18006DEB6
0x18006dd27  cmp     dword ptr [rdi+28h], 6
0x18006dd2b  mov     r9d, dword ptr [rsp+170h+var_108]
0x18006dd30  sbb     rax, rax
0x18006dd33  mov     qword ptr [rbp+70h+var_F0.Size], 10h
0x18006dd3b  and     rax, 0FFFFFFFFFFFFFD50h
0x18006dd41  mov     [rbp+70h+var_98], 4
0x18006dd49  add     rax, 2C0h
0x18006dd4f  mov     [rbp+70h+var_78], 4
0x18006dd57  add     rax, rdi
0x18006dd5a  mov     [rbp+70h+var_F0.Ptr], rax
0x18006dd5e  lea     rax, [rsp+170h+var_134]
0x18006dd63  mov     [rbp+70h+var_A0], rax
0x18006dd67  lea     rax, [rsp+170h+var_134]
0x18006dd6c  mov     [rbp+70h+var_80], rax
0x18006dd70  test    r9d, r9d
0x18006dd73  jz      short loc_18006DDBA
0x18006dd75  mov     rdx, qword ptr [rsp+170h+var_118+8]
0x18006dd7a  lea     rax, [rdx+4]
0x18006dd7e  mov     [rbp+70h+var_A0], rax
0x18006dd82  lea     r8, [rdx+10h]
0x18006dd86  mov     ecx, [rax]
0x18006dd88  lea     r10, [rdx+20h]
0x18006dd8c  mov     rax, [rdx+8]
0x18006dd90  mov     [rbp+70h+var_90], rax
0x18006dd94  mov     [rbp+70h+var_88], ecx
0x18006dd97  mov     [rbp+70h+var_84], esi
0x18006dd9a  cmp     r9d, 1
0x18006dd9e  jbe     short loc_18006DDC4
0x18006dda0  lea     rax, [rdx+34h]
0x18006dda4  mov     [rbp+70h+var_80], rax
0x18006dda8  mov     ecx, [rax]
0x18006ddaa  mov     rax, [rdx+38h]
0x18006ddae  mov     [rbp+70h+var_70], rax
0x18006ddb2  mov     [rbp+70h+var_68], ecx
0x18006ddb5  mov     [rbp+70h+var_64], esi
0x18006ddb8  jmp     short loc_18006DDC4
0x18006ddba  lea     r8, g_CiUnknown
0x18006ddc1  mov     r10, r8
0x18006ddc4  movzx   eax, word ptr [r8]
0x18006ddc8  lea     r9, [rsp+170h+P]
0x18006ddcd  mov     edx, dword ptr [rsp+170h+var_118]
0x18006ddd1  shr     ax, 1
0x18006ddd4  mov     [rsp+170h+var_140], ax
0x18006ddd9  lea     rax, [rsp+170h+var_140]
0x18006ddde  mov     [rbp+70h+var_E0], rax
0x18006dde2  mov     [rbp+70h+var_D8], 2
0x18006ddea  movzx   ecx, word ptr [r8]
0x18006ddee  mov     rax, [r8+8]
0x18006ddf2  lea     r8, [rsp+170h+var_138]
0x18006ddf7  mov     [rbp+70h+var_D0], rax
0x18006ddfb  mov     [rbp+70h+var_C8], ecx
0x18006ddfe  mov     [rbp+70h+var_C4], esi
0x18006de01  movzx   eax, word ptr [r10]
0x18006de05  shr     ax, 1
0x18006de08  mov     [rsp+170h+var_13C], ax
0x18006de0d  lea     rax, [rsp+170h+var_13C]
0x18006de12  mov     [rbp+70h+var_C0], rax
0x18006de16  mov     [rbp+70h+var_B8], 2
0x18006de1e  movzx   ecx, word ptr [r10]
0x18006de22  mov     rax, [r10+8]
0x18006de26  mov     [rbp+70h+var_A8], ecx
0x18006de29  mov     rcx, qword ptr [rsp+170h+var_128+8]
0x18006de2e  mov     [rbp+70h+var_B0], rax
0x18006de32  mov     [rbp+70h+var_A4], esi
0x18006de35  call    CipCollectEKUsIntoArray
0x18006de3a  mov     rdi, [rsp+170h+P]
0x18006de3f  lea     rax, [rsp+170h+var_138]
0x18006de44  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006de4b  lea     rdx, CiPolicySigner; EventDescriptor
0x18006de52  mov     [rbp+70h+var_60], rax
0x18006de56  mov     r9d, 0Ch; UserDataCount
0x18006de5c  mov     eax, [rsp+170h+var_138]
0x18006de60  xor     r8d, r8d; ActivityId
0x18006de63  mov     [rbp+70h+var_48], eax
0x18006de66  lea     rax, [rsp+170h+var_108+4]
0x18006de6b  mov     [rbp+70h+var_40], rax
0x18006de6f  lea     rax, [rbp+70h+var_F0]
0x18006de73  mov     [rsp+170h+UserData], rax; UserData
0x18006de78  mov     [rbp+70h+var_58], 4
0x18006de80  mov     [rbp+70h+var_50], rdi
0x18006de84  mov     [rbp+70h+var_44], esi
0x18006de87  mov     [rbp+70h+var_38], 4
0x18006de8f  call    cs:__imp_EtwWrite
0x18006de96  nop     dword ptr [rax+rax+00h]
0x18006de9b  mov     ebx, eax
0x18006de9d  test    rdi, rdi
0x18006dea0  jz      short loc_18006DEB6
0x18006dea2  mov     edx, 63734943h; Tag
0x18006dea7  mov     rcx, rdi; P
0x18006deaa  call    cs:__imp_ExFreePoolWithTag
0x18006deb1  nop     dword ptr [rax+rax+00h]
0x18006deb6  lea     rcx, [rsp+170h+var_128]
0x18006debb  call    SIPolicyFreeSIChainInfo
0x18006dec0  mov     eax, ebx
0x18006dec2  mov     rcx, [rbp+70h+var_30]
0x18006dec6  xor     rcx, rsp; StackCookie
0x18006dec9  call    __security_check_cookie
0x18006dece  add     rsp, 158h
0x18006ded5  pop     rdi
0x18006ded6  pop     rsi
0x18006ded7  pop     rbx
0x18006ded8  pop     rbp
0x18006ded9  retn
```
