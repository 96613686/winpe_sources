# CiSetPolicyInformation

- ea: `0x18005ec0c`
- end: `0x18005ed01`
- name: `CiSetPolicyInformation`
- size: `245`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18005eac0`

## callees

- `0x1800150ec`
- `0x18002c0d0`
- `0x18002c100`
- `0x18005ec0c`
- `0x180071d98`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ecb5`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ecb5`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ec3c`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ec3c`
- `ntoskrnl!SeExports` at `0x18005ec9d`

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
0x18005ec0c  mov     [rsp+arg_8], rbx
0x18005ec11  mov     [rsp+arg_10], rsi
0x18005ec16  push    rdi
0x18005ec17  sub     rsp, 50h
0x18005ec1b  mov     rax, cs:__security_cookie
0x18005ec22  xor     rax, rsp
0x18005ec25  mov     [rsp+58h+var_10], rax
0x18005ec2a  mov     ebx, edx
0x18005ec2c  mov     rsi, rcx
0x18005ec2f  xorps   xmm0, xmm0
0x18005ec32  movups  [rsp+58h+var_30], xmm0
0x18005ec37  movups  [rsp+58h+var_20], xmm0
0x18005ec3c  call    cs:__imp_ExGetPreviousMode
0x18005ec43  nop     dword ptr [rax+rax+00h]
0x18005ec48  mov     dil, al
0x18005ec4b  mov     r8d, 20h ; ' '; Size
0x18005ec51  cmp     ebx, r8d
0x18005ec54  jnz     loc_18005ECDE
0x18005ec5a  mov     [rsp+58h+var_38], al
0x18005ec5e  test    rsi, rsi
0x18005ec61  jz      short loc_18005ECDE
0x18005ec63  mov     rdx, rsi; Src
0x18005ec66  lea     rcx, [rsp+58h+var_30]; void *
0x18005ec6b  test    al, al
0x18005ec6d  jz      short loc_18005EC76
0x18005ec6f  call    RtlCopyFromUser
0x18005ec74  jmp     short loc_18005EC7C
0x18005ec76  call    RtlCopyVolatileMemory
0x18005ec7b  nop
0x18005ec7c  mov     ebx, dword ptr [rsp+58h+var_30]
0x18005ec80  bt      ebx, 1Ch
0x18005ec84  jb      short loc_18005EC8D
0x18005ec86  mov     eax, 0C00000BBh
0x18005ec8b  jmp     short loc_18005ECE3
0x18005ec8d  bt      ebx, 18h
0x18005ec91  jnb     short loc_18005ECD3
0x18005ec93  test    dil, dil
0x18005ec96  jz      short loc_18005ECD3
0x18005ec98  mov     [rsp+58h+var_38], 0
0x18005ec9d  mov     rax, cs:__imp_SeExports
0x18005eca4  mov     rdx, [rax]
0x18005eca7  lea     r8, [rsp+58h+var_38]
0x18005ecac  mov     rdx, [rdx+108h]
0x18005ecb3  xor     ecx, ecx
0x18005ecb5  call    cs:__imp_RtlCheckTokenMembership
0x18005ecbc  nop     dword ptr [rax+rax+00h]
0x18005ecc1  test    eax, eax
0x18005ecc3  js      short loc_18005ECE3
0x18005ecc5  cmp     [rsp+58h+var_38], 0
0x18005ecca  jnz     short loc_18005ECD3
0x18005eccc  mov     eax, 0C0000022h
0x18005ecd1  jmp     short loc_18005ECE3
0x18005ecd3  mov     ecx, ebx
0x18005ecd5  call    CiUpdatePolicies
0x18005ecda  jmp     short loc_18005ECE3
0x18005ecdc  jmp     short loc_18005ECE3
0x18005ecde  mov     eax, 0C0000004h
0x18005ece3  mov     rcx, [rsp+58h+var_10]
0x18005ece8  xor     rcx, rsp; StackCookie
0x18005eceb  call    __security_check_cookie
0x18005ecf0  mov     rbx, [rsp+58h+arg_8]
0x18005ecf5  mov     rsi, [rsp+58h+arg_10]
0x18005ecfa  add     rsp, 50h
0x18005ecfe  pop     rdi
0x18005ecff  retn
0x1800ea456  push    rbp
0x1800ea458  sub     rsp, 20h
0x1800ea45c  mov     rbp, rdx
0x1800ea45f  xor     eax, eax
0x1800ea461  cmp     [rbp+20h], al
0x1800ea464  setnz   al
0x1800ea467  mov     [rbp+24h], eax
0x1800ea46a  mov     eax, [rbp+24h]
0x1800ea46d  add     rsp, 20h
0x1800ea471  pop     rbp
0x1800ea472  retn
```
