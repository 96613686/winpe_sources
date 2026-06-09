# CiSetPolicyInformation

- ea: `0x18005ec6c`
- end: `0x18005ed61`
- name: `CiSetPolicyInformation`
- size: `245`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18005eb20`

## callees

- `0x18001508c`
- `0x18002bf20`
- `0x18002bf50`
- `0x18005ec6c`
- `0x180071ab8`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ed15`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ed15`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ec9c`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ec9c`
- `ntoskrnl!SeExports` at `0x18005ecfd`

## pseudocode

```c
__int64 __fastcall CiSetPolicyInformation(void *Src, int a2)
{
  KPROCESSOR_MODE PreviousMode; // al
  KPROCESSOR_MODE v5; // di
  unsigned int v6; // ebx
  __int64 result; // rax
  KPROCESSOR_MODE v8[8]; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v9[2]; // [rsp+28h] [rbp-30h] BYREF

  memset(v9, 0, sizeof(v9));
  PreviousMode = ExGetPreviousMode();
  v5 = PreviousMode;
  if ( a2 != 32 )
    return 3221225476LL;
  v8[0] = PreviousMode;
  if ( !Src )
    return 3221225476LL;
  if ( PreviousMode )
    RtlCopyFromUser(v9, Src, 0x20u);
  else
    RtlCopyVolatileMemory(v9, Src, 0x20u);
  v6 = v9[0];
  if ( (v9[0] & 0x10000000) == 0 )
    return 3221225659LL;
  if ( (v9[0] & 0x1000000) == 0 || !v5 )
    return CiUpdatePolicies(v6);
  v8[0] = 0;
  result = RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, v8);
  if ( (int)result < 0 )
    return result;
  if ( !v8[0] )
    return 3221225506LL;
  else
    return CiUpdatePolicies(v6);
}

```

## disassembly

```asm
0x18005ec6c  mov     [rsp+arg_8], rbx
0x18005ec71  mov     [rsp+arg_10], rsi
0x18005ec76  push    rdi
0x18005ec77  sub     rsp, 50h
0x18005ec7b  mov     rax, cs:__security_cookie
0x18005ec82  xor     rax, rsp
0x18005ec85  mov     [rsp+58h+var_10], rax
0x18005ec8a  mov     ebx, edx
0x18005ec8c  mov     rsi, rcx
0x18005ec8f  xorps   xmm0, xmm0
0x18005ec92  movups  [rsp+58h+var_30], xmm0
0x18005ec97  movups  [rsp+58h+var_20], xmm0
0x18005ec9c  call    cs:__imp_ExGetPreviousMode
0x18005eca3  nop     dword ptr [rax+rax+00h]
0x18005eca8  mov     dil, al
0x18005ecab  mov     r8d, 20h ; ' '; Size
0x18005ecb1  cmp     ebx, r8d
0x18005ecb4  jnz     loc_18005ED3E
0x18005ecba  mov     [rsp+58h+var_38], al
0x18005ecbe  test    rsi, rsi
0x18005ecc1  jz      short loc_18005ED3E
0x18005ecc3  mov     rdx, rsi; Src
0x18005ecc6  lea     rcx, [rsp+58h+var_30]; void *
0x18005eccb  test    al, al
0x18005eccd  jz      short loc_18005ECD6
0x18005eccf  call    RtlCopyFromUser
0x18005ecd4  jmp     short loc_18005ECDC
0x18005ecd6  call    RtlCopyVolatileMemory
0x18005ecdb  nop
0x18005ecdc  mov     ebx, dword ptr [rsp+58h+var_30]
0x18005ece0  bt      ebx, 1Ch
0x18005ece4  jb      short loc_18005ECED
0x18005ece6  mov     eax, 0C00000BBh
0x18005eceb  jmp     short loc_18005ED43
0x18005eced  bt      ebx, 18h
0x18005ecf1  jnb     short loc_18005ED33
0x18005ecf3  test    dil, dil
0x18005ecf6  jz      short loc_18005ED33
0x18005ecf8  mov     [rsp+58h+var_38], 0
0x18005ecfd  mov     rax, cs:__imp_SeExports
0x18005ed04  mov     rdx, [rax]
0x18005ed07  lea     r8, [rsp+58h+var_38]
0x18005ed0c  mov     rdx, [rdx+108h]
0x18005ed13  xor     ecx, ecx
0x18005ed15  call    cs:__imp_RtlCheckTokenMembership
0x18005ed1c  nop     dword ptr [rax+rax+00h]
0x18005ed21  test    eax, eax
0x18005ed23  js      short loc_18005ED43
0x18005ed25  cmp     [rsp+58h+var_38], 0
0x18005ed2a  jnz     short loc_18005ED33
0x18005ed2c  mov     eax, 0C0000022h
0x18005ed31  jmp     short loc_18005ED43
0x18005ed33  mov     ecx, ebx
0x18005ed35  call    CiUpdatePolicies
0x18005ed3a  jmp     short loc_18005ED43
0x18005ed3c  jmp     short loc_18005ED43
0x18005ed3e  mov     eax, 0C0000004h
0x18005ed43  mov     rcx, [rsp+58h+var_10]
0x18005ed48  xor     rcx, rsp; StackCookie
0x18005ed4b  call    __security_check_cookie
0x18005ed50  mov     rbx, [rsp+58h+arg_8]
0x18005ed55  mov     rsi, [rsp+58h+arg_10]
0x18005ed5a  add     rsp, 50h
0x18005ed5e  pop     rdi
0x18005ed5f  retn
0x1800e9c16  push    rbp
0x1800e9c18  sub     rsp, 20h
0x1800e9c1c  mov     rbp, rdx
0x1800e9c1f  xor     eax, eax
0x1800e9c21  cmp     [rbp+20h], al
0x1800e9c24  setnz   al
0x1800e9c27  mov     [rbp+24h], eax
0x1800e9c2a  mov     eax, [rbp+24h]
0x1800e9c2d  add     rsp, 20h
0x1800e9c31  pop     rbp
0x1800e9c32  retn
```
