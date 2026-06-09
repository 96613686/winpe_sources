# CiSetPolicyInformation

- ea: `0x18005e56c`
- end: `0x18005e615`
- name: `CiSetPolicyInformation`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18005e420`

## callees

- `0x18005e56c`
- `0x180070808`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005e5e2`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005e5e2`
- `ntoskrnl!ExGetPreviousMode` at `0x18005e5b5`
- `ntoskrnl!ExGetPreviousMode` at `0x18005e5b5`
- `ntoskrnl!SeExports` at `0x18005e5ca`

## pseudocode

```c
__int64 __fastcall CiSetPolicyInformation(unsigned int *a1, int a2)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  char v4; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 != 32 || !a1 )
    return 3221225476LL;
  v2 = *a1;
  if ( (*a1 & 0x10000000) == 0 )
    return 3221225659LL;
  if ( (v2 & 0x1000000) == 0 || !ExGetPreviousMode() )
    return CiUpdatePolicies(v2);
  v4 = 0;
  result = RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, &v4);
  if ( (int)result < 0 )
    return result;
  if ( !v4 )
    return 3221225506LL;
  else
    return CiUpdatePolicies(v2);
}

```

## disassembly

```asm
0x18005e56c  push    rbx
0x18005e56e  sub     rsp, 30h
0x18005e572  cmp     edx, 20h ; ' '
0x18005e575  jnz     loc_18005E609
0x18005e57b  mov     [rsp+38h+var_18], 0
0x18005e583  xor     eax, eax
0x18005e585  test    rcx, rcx
0x18005e588  jz      short loc_18005E609
0x18005e58a  mov     ebx, [rcx]
0x18005e58c  mov     [rsp+38h+var_18], ebx
0x18005e590  bt      ebx, 1Ch
0x18005e594  jb      short loc_18005E5A1
0x18005e596  mov     eax, 0C00000BBh
0x18005e59b  mov     [rsp+38h+var_14], eax
0x18005e59f  jmp     short loc_18005E60E
0x18005e5a1  jmp     short loc_18005E5AB
0x18005e5a3  mov     [rsp+38h+var_14], eax
0x18005e5a7  mov     ebx, [rsp+38h+var_18]
0x18005e5ab  test    eax, eax
0x18005e5ad  js      short loc_18005E60E
0x18005e5af  bt      ebx, 18h
0x18005e5b3  jnb     short loc_18005E600
0x18005e5b5  call    cs:__imp_ExGetPreviousMode
0x18005e5bc  nop     dword ptr [rax+rax+00h]
0x18005e5c1  test    al, al
0x18005e5c3  jz      short loc_18005E600
0x18005e5c5  mov     [rsp+38h+arg_8], 0
0x18005e5ca  mov     rax, cs:__imp_SeExports
0x18005e5d1  mov     rdx, [rax]
0x18005e5d4  lea     r8, [rsp+38h+arg_8]
0x18005e5d9  mov     rdx, [rdx+108h]
0x18005e5e0  xor     ecx, ecx
0x18005e5e2  call    cs:__imp_RtlCheckTokenMembership
0x18005e5e9  nop     dword ptr [rax+rax+00h]
0x18005e5ee  test    eax, eax
0x18005e5f0  js      short loc_18005E60E
0x18005e5f2  cmp     [rsp+38h+arg_8], 0
0x18005e5f7  jnz     short loc_18005E600
0x18005e5f9  mov     eax, 0C0000022h
0x18005e5fe  jmp     short loc_18005E60E
0x18005e600  mov     ecx, ebx
0x18005e602  call    CiUpdatePolicies
0x18005e607  jmp     short loc_18005E60E
0x18005e609  mov     eax, 0C0000004h
0x18005e60e  add     rsp, 30h
0x18005e612  pop     rbx
0x18005e613  retn
0x1800e8459  push    rbp
0x1800e845b  sub     rsp, 20h
0x1800e845f  mov     rbp, rdx
0x1800e8462  call    cs:__imp_ExSystemExceptionFilter
0x1800e8469  nop     dword ptr [rax+rax+00h]
0x1800e846e  nop
0x1800e846f  add     rsp, 20h
0x1800e8473  pop     rbp
0x1800e8474  retn
```
