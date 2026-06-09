# SIPolicyLoadAuthorizationTokens

- ea: `0x18007be64`
- end: `0x18007c05d`
- name: `SIPolicyLoadAuthorizationTokens`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180057408`

## callees

- `0x180020c38`
- `0x18005b47c`
- `0x18005b644`
- `0x18007bd28`
- `0x18007be64`
- `0x18007c8fc`
- `0x1800a00c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007bfc0`
- `ntoskrnl!ExAllocatePool2` at `0x18007bfc0`

## pseudocode

```c
__int64 __fastcall SIPolicyLoadAuthorizationTokens(int a1, int a2, __int64 a3, int a4)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  void **v8; // rcx
  char v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int AuthorizationTokenFiles; // ebx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 Pool2; // rdi
  unsigned int v17; // esi
  int v18; // ecx
  unsigned int v20; // [rsp+58h] [rbp-19h] BYREF
  _DWORD v21[8]; // [rsp+60h] [rbp-11h] BYREF
  _DWORD v22[4]; // [rsp+80h] [rbp+Fh] BYREF
  __int128 v23; // [rsp+90h] [rbp+1Fh]
  int v24; // [rsp+D8h] [rbp+67h] BYREF
  int v25; // [rsp+E0h] [rbp+6Fh] BYREF

  v25 = a2;
  v24 = a1;
  v20 = 0;
  LOBYTE(v25) = 0;
  v23 = SiPolicyIDEModeBase;
  LOBYTE(v24) = 0;
  v21[0] = -358296965;
  v21[1] = 1115336418;
  v21[2] = -1465402998;
  v21[3] = 1587952196;
  v21[4] = -396471215;
  v21[5] = 1202408593;
  v21[6] = -518863191;
  v21[7] = -1392124565;
  v22[0] = 1498524010;
  v22[1] = 1295900853;
  v22[2] = 1530837135;
  v22[3] = -2079915167;
  while ( 1 )
  {
    v6 = g_SiPolicyTokens;
    if ( g_SiPolicyTokens == (_UNKNOWN *)&g_SiPolicyTokens )
      break;
    v7 = *(_QWORD **)g_SiPolicyTokens;
    if ( *(_UNKNOWN **)(*(_QWORD *)g_SiPolicyTokens + 8LL) != g_SiPolicyTokens
      || (v8 = (void **)*((_QWORD *)g_SiPolicyTokens + 1), *v8 != g_SiPolicyTokens) )
    {
      __fastfail(3u);
    }
    *v8 = v7;
    v7[1] = v8;
    SIPolicyFree(v6[3]);
    SbFreePolicy(v6[2]);
    SIPolicyFree(v6);
  }
  v9 = 0;
  if ( (int)SIPolicyGetTestsigningPolicy(&v25, &v24) >= 0 && ((_BYTE)v25 || (_BYTE)v24) )
    v9 = 1;
  AuthorizationTokenFiles = 0;
  if ( a3 && a4 )
  {
    v13 = SIPolicyPmEnumerateTokens(v11, v10, 0);
    AuthorizationTokenFiles = v13;
    if ( v13 < 0 )
    {
      if ( v13 != -1073741275 )
        return AuthorizationTokenFiles;
    }
    else if ( v20 )
    {
      Pool2 = ExAllocatePool2(256, 24LL * v20, 1769163075);
      if ( Pool2 )
      {
        v17 = v20;
        AuthorizationTokenFiles = SIPolicyPmEnumerateTokens(v15, v14, Pool2);
        if ( (AuthorizationTokenFiles & 0x80000000) == 0 )
          AuthorizationTokenFiles = SIPolicyLoadAuthorizationTokenFiles(
                                      v18,
                                      a3,
                                      a4,
                                      (unsigned int)v21,
                                      (__int64)v22,
                                      (unsigned int)&v20,
                                      Pool2,
                                      v20,
                                      v9);
        SIPolicyPmFreeFileItems(Pool2, v17);
        SIPolicyFree(Pool2);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
      return AuthorizationTokenFiles;
    }
    return 0;
  }
  return AuthorizationTokenFiles;
}

```

## disassembly

```asm
0x18007be64  mov     rax, rsp
0x18007be67  mov     [rax+18h], rbx
0x18007be6b  mov     [rax+20h], rsi
0x18007be6f  mov     [rax+10h], edx
0x18007be72  mov     [rax+8], ecx
0x18007be75  push    rbp
0x18007be76  push    rdi
0x18007be77  push    r12
0x18007be79  push    r14
0x18007be7b  push    r15
0x18007be7d  lea     rbp, [rax-5Fh]
0x18007be81  sub     rsp, 0A0h
0x18007be88  movups  xmm0, cs:SiPolicyIDEModeBase
0x18007be8f  mov     r15d, r9d
0x18007be92  mov     [rbp+57h+var_70], 0
0x18007be99  mov     r12, r8
0x18007be9c  mov     byte ptr [rbp+57h+arg_8], 0
0x18007bea0  movdqu  [rbp+57h+var_38], xmm0
0x18007bea5  mov     byte ptr [rbp+57h+arg_0], 0
0x18007bea9  mov     [rbp+57h+var_68], 0EAA4D27Bh
0x18007beb0  mov     [rbp+57h+var_64], 427AAEE2h
0x18007beb7  mov     [rbp+57h+var_60], 0A8A7B98Ah
0x18007bebe  mov     [rbp+57h+var_5C], 5EA63A44h
0x18007bec5  mov     [rbp+57h+var_58], 0E85E5451h
0x18007becc  mov     [rbp+57h+var_54], 47AB4C91h
0x18007bed3  mov     [rbp+57h+var_50], 0E112C6A9h
0x18007beda  mov     [rbp+57h+var_4C], 0AD05DD6Bh
0x18007bee1  mov     [rbp+57h+var_48], 5951A96Ah
0x18007bee8  mov     [rbp+57h+var_44], 4D3DE0B5h
0x18007beef  mov     [rbp+57h+var_40], 5B3EB88Fh
0x18007bef6  mov     [rbp+57h+var_3C], 84070361h
0x18007befd  mov     rbx, cs:g_SiPolicyTokens
0x18007bf04  lea     rax, g_SiPolicyTokens
0x18007bf0b  cmp     rbx, rax
0x18007bf0e  jz      short loc_18007BF4C
0x18007bf10  mov     rax, [rbx]
0x18007bf13  cmp     [rax+8], rbx
0x18007bf17  jnz     short loc_18007BF45
0x18007bf19  mov     rcx, [rbx+8]
0x18007bf1d  cmp     [rcx], rbx
0x18007bf20  jnz     short loc_18007BF45
0x18007bf22  mov     [rcx], rax
0x18007bf25  mov     [rax+8], rcx
0x18007bf29  mov     rcx, [rbx+18h]
0x18007bf2d  call    SIPolicyFree
0x18007bf32  mov     rcx, [rbx+10h]
0x18007bf36  call    SbFreePolicy
0x18007bf3b  mov     rcx, rbx
0x18007bf3e  call    SIPolicyFree
0x18007bf43  jmp     short loc_18007BEFD
0x18007bf45  mov     ecx, 3
0x18007bf4a  int     29h; Win8: RtlFailFast(ecx)
0x18007bf4c  lea     rdx, [rbp+57h+arg_0]
0x18007bf50  xor     r14b, r14b
0x18007bf53  lea     rcx, [rbp+57h+arg_8]
0x18007bf57  call    SIPolicyGetTestsigningPolicy
0x18007bf5c  test    eax, eax
0x18007bf5e  js      short loc_18007BF6F
0x18007bf60  cmp     byte ptr [rbp+57h+arg_8], r14b
0x18007bf64  jnz     short loc_18007BF6C
0x18007bf66  cmp     byte ptr [rbp+57h+arg_0], r14b
0x18007bf6a  jz      short loc_18007BF6F
0x18007bf6c  mov     r14b, 1
0x18007bf6f  xor     ebx, ebx
0x18007bf71  test    r12, r12
0x18007bf74  jz      loc_18007C03E
0x18007bf7a  test    r15d, r15d
0x18007bf7d  jz      loc_18007C03E
0x18007bf83  lea     rax, [rbp+57h+var_70]
0x18007bf87  xor     r8d, r8d
0x18007bf8a  mov     [rsp+0C0h+var_98], rax
0x18007bf8f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007bf93  call    SIPolicyPmEnumerateTokens
0x18007bf98  mov     ebx, eax
0x18007bf9a  test    eax, eax
0x18007bf9c  js      loc_18007C035
0x18007bfa2  mov     ebx, [rbp+57h+var_70]
0x18007bfa5  test    ebx, ebx
0x18007bfa7  jz      loc_18007C03C
0x18007bfad  lea     rdx, [rbx+rbx*2]
0x18007bfb1  mov     ecx, 100h
0x18007bfb6  shl     rdx, 3
0x18007bfba  mov     r8d, 69734943h
0x18007bfc0  call    cs:__imp_ExAllocatePool2
0x18007bfc7  nop     dword ptr [rax+rax+00h]
0x18007bfcc  mov     rdi, rax
0x18007bfcf  test    rax, rax
0x18007bfd2  jnz     short loc_18007BFDB
0x18007bfd4  mov     ebx, 0C0000017h
0x18007bfd9  jmp     short loc_18007C03E
0x18007bfdb  lea     rax, [rbp+57h+var_70]
0x18007bfdf  mov     r8, rdi
0x18007bfe2  mov     [rsp+0C0h+var_98], rax
0x18007bfe7  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007bfeb  call    SIPolicyPmEnumerateTokens
0x18007bff0  mov     esi, [rbp+57h+var_70]
0x18007bff3  mov     ebx, eax
0x18007bff5  test    eax, eax
0x18007bff7  js      short loc_18007C021
0x18007bff9  mov     [rsp+0C0h+var_80], r14b
0x18007bffe  lea     rax, [rbp+57h+var_48]
0x18007c002  mov     dword ptr [rsp+0C0h+var_88], esi
0x18007c006  lea     r9, [rbp+57h+var_68]
0x18007c00a  mov     qword ptr [rsp+0C0h+var_90], rdi
0x18007c00f  mov     r8d, r15d
0x18007c012  mov     rdx, r12
0x18007c015  mov     [rsp+0C0h+var_A0], rax
0x18007c01a  call    SIPolicyLoadAuthorizationTokenFiles
0x18007c01f  mov     ebx, eax
0x18007c021  mov     edx, esi
0x18007c023  mov     rcx, rdi
0x18007c026  call    SIPolicyPmFreeFileItems
0x18007c02b  mov     rcx, rdi
0x18007c02e  call    SIPolicyFree
0x18007c033  jmp     short loc_18007C03E
0x18007c035  cmp     eax, 0C0000225h
0x18007c03a  jnz     short loc_18007C03E
0x18007c03c  xor     ebx, ebx
0x18007c03e  lea     r11, [rsp+0C0h+var_20]
0x18007c046  mov     eax, ebx
0x18007c048  mov     rbx, [r11+40h]
0x18007c04c  mov     rsi, [r11+48h]
0x18007c050  mov     rsp, r11
0x18007c053  pop     r15
0x18007c055  pop     r14
0x18007c057  pop     r12
0x18007c059  pop     rdi
0x18007c05a  pop     rbp
0x18007c05b  retn
```
