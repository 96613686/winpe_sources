# CipValidateSigningPolicyForScenario

- ea: `0x18007194c`
- end: `0x180071a82`
- name: `CipValidateSigningPolicyForScenario`
- size: `310`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005bc50`
- `0x180070778`
- `0x180073510`

## callees

- `0x18006fb48`
- `0x18007194c`
- `0x1800a82b4`

## import_xrefs

- `ntoskrnl!SeQuerySecureBootPlatformManifest` at `0x180071a0b`
- `ntoskrnl!SeQuerySecureBootPlatformManifest` at `0x180071a0b`

## pseudocode

```c
__int64 __fastcall CipValidateSigningPolicyForScenario(int a1, __int64 a2, __int64 a3, char a4, char a5, _DWORD *a6)
{
  int v7; // r13d
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // edi
  __int64 v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rsi
  int SecureBootPlatformManifest; // eax
  __int64 v17; // [rsp+20h] [rbp-48h]
  char v19; // [rsp+88h] [rbp+20h]

  v19 = a4;
  v7 = a3;
  v8 = a1;
  v9 = -1073740760;
  v10 = 0;
LABEL_2:
  if ( v10 > v7 )
    return v9;
  v11 = v8;
  v12 = 0;
  v13 = v10 + 12LL * v8;
  v17 = v13;
  while ( 1 )
  {
    if ( (unsigned int)v12 >= g_CiScenarios[v13 + 8] )
    {
      v8 = a1;
      ++v10;
      goto LABEL_2;
    }
    v14 = *(unsigned int *)(*(_QWORD *)&g_CiScenarios[12 * v11 + 2 + 2 * v10] + 4 * v12);
    if ( (unsigned int)v14 >= g_CiSignersCount )
      return 3225616387LL;
    LOBYTE(a3) = a4;
    if ( !(unsigned __int8)CipValidateChainAgainstSigner(a2, g_CiSigners + 40 * v14, a3) )
      goto LABEL_14;
    if ( a5 || !CipRequirePlatformManifestForSigner(v14) )
      break;
    if ( a2 )
    {
      SecureBootPlatformManifest = SeQuerySecureBootPlatformManifest(a2 + 72, 32);
      v9 = SecureBootPlatformManifest;
      if ( SecureBootPlatformManifest >= 0 )
        break;
      if ( SecureBootPlatformManifest == -1073741275 )
        v9 = -1058340861;
    }
    else
    {
      v9 = -1058340861;
    }
LABEL_14:
    v13 = v17;
    a4 = v19;
    v12 = (unsigned int)(v12 + 1);
  }
  if ( a6 )
    *a6 = v14;
  return 0;
}

```

## disassembly

```asm
0x18007194c  mov     [rsp+arg_8], rbx
0x180071951  mov     [rsp+arg_18], r9b
0x180071956  mov     [rsp+arg_0], ecx
0x18007195a  push    rbp
0x18007195b  push    rsi
0x18007195c  push    rdi
0x18007195d  push    r12
0x18007195f  push    r13
0x180071961  push    r14
0x180071963  push    r15
0x180071965  sub     rsp, 30h
0x180071969  mov     r15, rdx
0x18007196c  mov     r13d, r8d
0x18007196f  lea     rdx, g_CiScenarios
0x180071976  mov     eax, ecx
0x180071978  mov     ebx, 0C0000428h
0x18007197d  xor     edi, edi
0x18007197f  cmp     edi, r13d
0x180071982  jg      loc_180071A6A
0x180071988  movsxd  r14, eax
0x18007198b  xor     ebp, ebp
0x18007198d  movsxd  r12, edi
0x180071990  lea     rax, [r14+r14*2]
0x180071994  lea     rax, [r12+rax*4]
0x180071998  mov     [rsp+68h+var_48], rax
0x18007199d  cmp     ebp, [rdx+rax*4+20h]
0x1800719a1  jnb     loc_180071A45
0x1800719a7  lea     rax, [r14+r14*2]
0x1800719ab  lea     rax, [r12+rax*2]
0x1800719af  mov     rax, [rdx+rax*8+8]
0x1800719b4  mov     esi, [rax+rbp*4]
0x1800719b7  cmp     esi, cs:g_CiSignersCount
0x1800719bd  jnb     loc_180071A63
0x1800719c3  mov     rax, cs:g_CiSigners
0x1800719ca  lea     rcx, [rsi+rsi*4]
0x1800719ce  mov     r8b, r9b
0x1800719d1  lea     rdx, [rax+rcx*8]
0x1800719d5  mov     rcx, r15
0x1800719d8  call    CipValidateChainAgainstSigner
0x1800719dd  test    al, al
0x1800719df  jz      short loc_180071A2A
0x1800719e1  cmp     [rsp+68h+arg_20], 0
0x1800719e9  jnz     short loc_180071A50
0x1800719eb  mov     ecx, esi
0x1800719ed  call    CipRequirePlatformManifestForSigner
0x1800719f2  test    al, al
0x1800719f4  jz      short loc_180071A50
0x1800719f6  test    r15, r15
0x1800719f9  jnz     short loc_180071A02
0x1800719fb  mov     ebx, 0C0EB0003h
0x180071a00  jmp     short loc_180071A2A
0x180071a02  lea     rcx, [r15+48h]
0x180071a06  mov     edx, 20h ; ' '
0x180071a0b  call    cs:__imp_SeQuerySecureBootPlatformManifest
0x180071a12  nop     dword ptr [rax+rax+00h]
0x180071a17  mov     ebx, eax
0x180071a19  test    eax, eax
0x180071a1b  jns     short loc_180071A50
0x180071a1d  cmp     eax, 0C0000225h
0x180071a22  mov     eax, 0C0EB0003h
0x180071a27  cmovz   ebx, eax
0x180071a2a  mov     rax, [rsp+68h+var_48]
0x180071a2f  lea     rdx, g_CiScenarios
0x180071a36  mov     r9b, [rsp+68h+arg_18]
0x180071a3e  inc     ebp
0x180071a40  jmp     loc_18007199D
0x180071a45  mov     eax, [rsp+68h+arg_0]
0x180071a49  inc     edi
0x180071a4b  jmp     loc_18007197F
0x180071a50  mov     rax, [rsp+68h+arg_28]
0x180071a58  test    rax, rax
0x180071a5b  jz      short loc_180071A5F
0x180071a5d  mov     [rax], esi
0x180071a5f  xor     eax, eax
0x180071a61  jmp     short loc_180071A6C
0x180071a63  mov     eax, 0C0430003h
0x180071a68  jmp     short loc_180071A6C
0x180071a6a  mov     eax, ebx
0x180071a6c  mov     rbx, [rsp+68h+arg_8]
0x180071a71  add     rsp, 30h
0x180071a75  pop     r15
0x180071a77  pop     r14
0x180071a79  pop     r13
0x180071a7b  pop     r12
0x180071a7d  pop     rdi
0x180071a7e  pop     rsi
0x180071a7f  pop     rbp
0x180071a80  retn
```
