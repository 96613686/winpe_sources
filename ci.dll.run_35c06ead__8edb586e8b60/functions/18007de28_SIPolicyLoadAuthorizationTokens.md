# SIPolicyLoadAuthorizationTokens

- ea: `0x18007de28`
- end: `0x18007e021`
- name: `SIPolicyLoadAuthorizationTokens`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180058048`

## callees

- `0x180020c78`
- `0x18005c0bc`
- `0x18005c284`
- `0x18007dcec`
- `0x18007de28`
- `0x18007e8c0`
- `0x180091e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007df84`
- `ntoskrnl!ExAllocatePool2` at `0x18007df84`

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
0x18007de28  mov     rax, rsp
0x18007de2b  mov     [rax+18h], rbx
0x18007de2f  mov     [rax+20h], rsi
0x18007de33  mov     [rax+10h], edx
0x18007de36  mov     [rax+8], ecx
0x18007de39  push    rbp
0x18007de3a  push    rdi
0x18007de3b  push    r12
0x18007de3d  push    r14
0x18007de3f  push    r15
0x18007de41  lea     rbp, [rax-5Fh]
0x18007de45  sub     rsp, 0A0h
0x18007de4c  movups  xmm0, cs:SiPolicyIDEModeBase
0x18007de53  mov     r15d, r9d
0x18007de56  mov     [rbp+57h+var_70], 0
0x18007de5d  mov     r12, r8
0x18007de60  mov     byte ptr [rbp+57h+arg_8], 0
0x18007de64  movdqu  [rbp+57h+var_38], xmm0
0x18007de69  mov     byte ptr [rbp+57h+arg_0], 0
0x18007de6d  mov     [rbp+57h+var_68], 0EAA4D27Bh
0x18007de74  mov     [rbp+57h+var_64], 427AAEE2h
0x18007de7b  mov     [rbp+57h+var_60], 0A8A7B98Ah
0x18007de82  mov     [rbp+57h+var_5C], 5EA63A44h
0x18007de89  mov     [rbp+57h+var_58], 0E85E5451h
0x18007de90  mov     [rbp+57h+var_54], 47AB4C91h
0x18007de97  mov     [rbp+57h+var_50], 0E112C6A9h
0x18007de9e  mov     [rbp+57h+var_4C], 0AD05DD6Bh
0x18007dea5  mov     [rbp+57h+var_48], 5951A96Ah
0x18007deac  mov     [rbp+57h+var_44], 4D3DE0B5h
0x18007deb3  mov     [rbp+57h+var_40], 5B3EB88Fh
0x18007deba  mov     [rbp+57h+var_3C], 84070361h
0x18007dec1  mov     rbx, cs:g_SiPolicyTokens
0x18007dec8  lea     rax, g_SiPolicyTokens
0x18007decf  cmp     rbx, rax
0x18007ded2  jz      short loc_18007DF10
0x18007ded4  mov     rax, [rbx]
0x18007ded7  cmp     [rax+8], rbx
0x18007dedb  jnz     short loc_18007DF09
0x18007dedd  mov     rcx, [rbx+8]
0x18007dee1  cmp     [rcx], rbx
0x18007dee4  jnz     short loc_18007DF09
0x18007dee6  mov     [rcx], rax
0x18007dee9  mov     [rax+8], rcx
0x18007deed  mov     rcx, [rbx+18h]
0x18007def1  call    SIPolicyFree
0x18007def6  mov     rcx, [rbx+10h]
0x18007defa  call    SbFreePolicy
0x18007deff  mov     rcx, rbx
0x18007df02  call    SIPolicyFree
0x18007df07  jmp     short loc_18007DEC1
0x18007df09  mov     ecx, 3
0x18007df0e  int     29h; Win8: RtlFailFast(ecx)
0x18007df10  lea     rdx, [rbp+57h+arg_0]
0x18007df14  xor     r14b, r14b
0x18007df17  lea     rcx, [rbp+57h+arg_8]
0x18007df1b  call    SIPolicyGetTestsigningPolicy
0x18007df20  test    eax, eax
0x18007df22  js      short loc_18007DF33
0x18007df24  cmp     byte ptr [rbp+57h+arg_8], r14b
0x18007df28  jnz     short loc_18007DF30
0x18007df2a  cmp     byte ptr [rbp+57h+arg_0], r14b
0x18007df2e  jz      short loc_18007DF33
0x18007df30  mov     r14b, 1
0x18007df33  xor     ebx, ebx
0x18007df35  test    r12, r12
0x18007df38  jz      loc_18007E002
0x18007df3e  test    r15d, r15d
0x18007df41  jz      loc_18007E002
0x18007df47  lea     rax, [rbp+57h+var_70]
0x18007df4b  xor     r8d, r8d
0x18007df4e  mov     [rsp+0C0h+var_98], rax
0x18007df53  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007df57  call    SIPolicyPmEnumerateTokens
0x18007df5c  mov     ebx, eax
0x18007df5e  test    eax, eax
0x18007df60  js      loc_18007DFF9
0x18007df66  mov     ebx, [rbp+57h+var_70]
0x18007df69  test    ebx, ebx
0x18007df6b  jz      loc_18007E000
0x18007df71  lea     rdx, [rbx+rbx*2]
0x18007df75  mov     ecx, 100h
0x18007df7a  shl     rdx, 3
0x18007df7e  mov     r8d, 69734943h
0x18007df84  call    cs:__imp_ExAllocatePool2
0x18007df8b  nop     dword ptr [rax+rax+00h]
0x18007df90  mov     rdi, rax
0x18007df93  test    rax, rax
0x18007df96  jnz     short loc_18007DF9F
0x18007df98  mov     ebx, 0C0000017h
0x18007df9d  jmp     short loc_18007E002
0x18007df9f  lea     rax, [rbp+57h+var_70]
0x18007dfa3  mov     r8, rdi
0x18007dfa6  mov     [rsp+0C0h+var_98], rax
0x18007dfab  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007dfaf  call    SIPolicyPmEnumerateTokens
0x18007dfb4  mov     esi, [rbp+57h+var_70]
0x18007dfb7  mov     ebx, eax
0x18007dfb9  test    eax, eax
0x18007dfbb  js      short loc_18007DFE5
0x18007dfbd  mov     [rsp+0C0h+var_80], r14b
0x18007dfc2  lea     rax, [rbp+57h+var_48]
0x18007dfc6  mov     dword ptr [rsp+0C0h+var_88], esi
0x18007dfca  lea     r9, [rbp+57h+var_68]
0x18007dfce  mov     qword ptr [rsp+0C0h+var_90], rdi
0x18007dfd3  mov     r8d, r15d
0x18007dfd6  mov     rdx, r12
0x18007dfd9  mov     [rsp+0C0h+var_A0], rax
0x18007dfde  call    SIPolicyLoadAuthorizationTokenFiles
0x18007dfe3  mov     ebx, eax
0x18007dfe5  mov     edx, esi
0x18007dfe7  mov     rcx, rdi
0x18007dfea  call    SIPolicyPmFreeFileItems
0x18007dfef  mov     rcx, rdi
0x18007dff2  call    SIPolicyFree
0x18007dff7  jmp     short loc_18007E002
0x18007dff9  cmp     eax, 0C0000225h
0x18007dffe  jnz     short loc_18007E002
0x18007e000  xor     ebx, ebx
0x18007e002  lea     r11, [rsp+0C0h+var_20]
0x18007e00a  mov     eax, ebx
0x18007e00c  mov     rbx, [r11+40h]
0x18007e010  mov     rsi, [r11+48h]
0x18007e014  mov     rsp, r11
0x18007e017  pop     r15
0x18007e019  pop     r14
0x18007e01b  pop     r12
0x18007e01d  pop     rdi
0x18007e01e  pop     rbp
0x18007e01f  retn
```
