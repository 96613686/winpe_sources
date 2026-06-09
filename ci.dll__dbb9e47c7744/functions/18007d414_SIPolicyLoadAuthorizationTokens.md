# SIPolicyLoadAuthorizationTokens

- ea: `0x18007d414`
- end: `0x18007d60d`
- name: `SIPolicyLoadAuthorizationTokens`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180058120`

## callees

- `0x180020ba8`
- `0x18005c18c`
- `0x18005c354`
- `0x18007d2d8`
- `0x18007d414`
- `0x18007deac`
- `0x1800a16f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18007d570`
- `ntoskrnl!ExAllocatePool2` at `0x18007d570`

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
0x18007d414  mov     rax, rsp
0x18007d417  mov     [rax+18h], rbx
0x18007d41b  mov     [rax+20h], rsi
0x18007d41f  mov     [rax+10h], edx
0x18007d422  mov     [rax+8], ecx
0x18007d425  push    rbp
0x18007d426  push    rdi
0x18007d427  push    r12
0x18007d429  push    r14
0x18007d42b  push    r15
0x18007d42d  lea     rbp, [rax-5Fh]
0x18007d431  sub     rsp, 0A0h
0x18007d438  movups  xmm0, cs:SiPolicyIDEModeBase
0x18007d43f  mov     r15d, r9d
0x18007d442  mov     [rbp+57h+var_70], 0
0x18007d449  mov     r12, r8
0x18007d44c  mov     byte ptr [rbp+57h+arg_8], 0
0x18007d450  movdqu  [rbp+57h+var_38], xmm0
0x18007d455  mov     byte ptr [rbp+57h+arg_0], 0
0x18007d459  mov     [rbp+57h+var_68], 0EAA4D27Bh
0x18007d460  mov     [rbp+57h+var_64], 427AAEE2h
0x18007d467  mov     [rbp+57h+var_60], 0A8A7B98Ah
0x18007d46e  mov     [rbp+57h+var_5C], 5EA63A44h
0x18007d475  mov     [rbp+57h+var_58], 0E85E5451h
0x18007d47c  mov     [rbp+57h+var_54], 47AB4C91h
0x18007d483  mov     [rbp+57h+var_50], 0E112C6A9h
0x18007d48a  mov     [rbp+57h+var_4C], 0AD05DD6Bh
0x18007d491  mov     [rbp+57h+var_48], 5951A96Ah
0x18007d498  mov     [rbp+57h+var_44], 4D3DE0B5h
0x18007d49f  mov     [rbp+57h+var_40], 5B3EB88Fh
0x18007d4a6  mov     [rbp+57h+var_3C], 84070361h
0x18007d4ad  mov     rbx, cs:g_SiPolicyTokens
0x18007d4b4  lea     rax, g_SiPolicyTokens
0x18007d4bb  cmp     rbx, rax
0x18007d4be  jz      short loc_18007D4FC
0x18007d4c0  mov     rax, [rbx]
0x18007d4c3  cmp     [rax+8], rbx
0x18007d4c7  jnz     short loc_18007D4F5
0x18007d4c9  mov     rcx, [rbx+8]
0x18007d4cd  cmp     [rcx], rbx
0x18007d4d0  jnz     short loc_18007D4F5
0x18007d4d2  mov     [rcx], rax
0x18007d4d5  mov     [rax+8], rcx
0x18007d4d9  mov     rcx, [rbx+18h]
0x18007d4dd  call    SIPolicyFree
0x18007d4e2  mov     rcx, [rbx+10h]
0x18007d4e6  call    SbFreePolicy
0x18007d4eb  mov     rcx, rbx
0x18007d4ee  call    SIPolicyFree
0x18007d4f3  jmp     short loc_18007D4AD
0x18007d4f5  mov     ecx, 3
0x18007d4fa  int     29h; Win8: RtlFailFast(ecx)
0x18007d4fc  lea     rdx, [rbp+57h+arg_0]
0x18007d500  xor     r14b, r14b
0x18007d503  lea     rcx, [rbp+57h+arg_8]
0x18007d507  call    SIPolicyGetTestsigningPolicy
0x18007d50c  test    eax, eax
0x18007d50e  js      short loc_18007D51F
0x18007d510  cmp     byte ptr [rbp+57h+arg_8], r14b
0x18007d514  jnz     short loc_18007D51C
0x18007d516  cmp     byte ptr [rbp+57h+arg_0], r14b
0x18007d51a  jz      short loc_18007D51F
0x18007d51c  mov     r14b, 1
0x18007d51f  xor     ebx, ebx
0x18007d521  test    r12, r12
0x18007d524  jz      loc_18007D5EE
0x18007d52a  test    r15d, r15d
0x18007d52d  jz      loc_18007D5EE
0x18007d533  lea     rax, [rbp+57h+var_70]
0x18007d537  xor     r8d, r8d
0x18007d53a  mov     [rsp+0C0h+var_98], rax
0x18007d53f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007d543  call    SIPolicyPmEnumerateTokens
0x18007d548  mov     ebx, eax
0x18007d54a  test    eax, eax
0x18007d54c  js      loc_18007D5E5
0x18007d552  mov     ebx, [rbp+57h+var_70]
0x18007d555  test    ebx, ebx
0x18007d557  jz      loc_18007D5EC
0x18007d55d  lea     rdx, [rbx+rbx*2]
0x18007d561  mov     ecx, 100h
0x18007d566  shl     rdx, 3
0x18007d56a  mov     r8d, 69734943h
0x18007d570  call    cs:__imp_ExAllocatePool2
0x18007d577  nop     dword ptr [rax+rax+00h]
0x18007d57c  mov     rdi, rax
0x18007d57f  test    rax, rax
0x18007d582  jnz     short loc_18007D58B
0x18007d584  mov     ebx, 0C0000017h
0x18007d589  jmp     short loc_18007D5EE
0x18007d58b  lea     rax, [rbp+57h+var_70]
0x18007d58f  mov     r8, rdi
0x18007d592  mov     [rsp+0C0h+var_98], rax
0x18007d597  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18007d59b  call    SIPolicyPmEnumerateTokens
0x18007d5a0  mov     esi, [rbp+57h+var_70]
0x18007d5a3  mov     ebx, eax
0x18007d5a5  test    eax, eax
0x18007d5a7  js      short loc_18007D5D1
0x18007d5a9  mov     [rsp+0C0h+var_80], r14b
0x18007d5ae  lea     rax, [rbp+57h+var_48]
0x18007d5b2  mov     dword ptr [rsp+0C0h+var_88], esi
0x18007d5b6  lea     r9, [rbp+57h+var_68]
0x18007d5ba  mov     qword ptr [rsp+0C0h+var_90], rdi
0x18007d5bf  mov     r8d, r15d
0x18007d5c2  mov     rdx, r12
0x18007d5c5  mov     [rsp+0C0h+var_A0], rax
0x18007d5ca  call    SIPolicyLoadAuthorizationTokenFiles
0x18007d5cf  mov     ebx, eax
0x18007d5d1  mov     edx, esi
0x18007d5d3  mov     rcx, rdi
0x18007d5d6  call    SIPolicyPmFreeFileItems
0x18007d5db  mov     rcx, rdi
0x18007d5de  call    SIPolicyFree
0x18007d5e3  jmp     short loc_18007D5EE
0x18007d5e5  cmp     eax, 0C0000225h
0x18007d5ea  jnz     short loc_18007D5EE
0x18007d5ec  xor     ebx, ebx
0x18007d5ee  lea     r11, [rsp+0C0h+var_20]
0x18007d5f6  mov     eax, ebx
0x18007d5f8  mov     rbx, [r11+40h]
0x18007d5fc  mov     rsi, [r11+48h]
0x18007d600  mov     rsp, r11
0x18007d603  pop     r15
0x18007d605  pop     r14
0x18007d607  pop     r12
0x18007d609  pop     rdi
0x18007d60a  pop     rbp
0x18007d60b  retn
```
