# EdppIsProcessLocalSystem

- ea: `0x140053360`
- end: `0x140053410`
- name: `EdppIsProcessLocalSystem`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400510ac`

## callees

- `0x140053360`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400533f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400533f6`
- `ntoskrnl!SeExports` at `0x1400533bc`
- `ntoskrnl!SeQueryInformationToken` at `0x140053399`
- `ntoskrnl!SeQueryInformationToken` at `0x140053399`
- `ntoskrnl!RtlEqualSid` at `0x1400533d0`
- `ntoskrnl!RtlEqualSid` at `0x1400533d0`

## pseudocode

```c
__int64 __fastcall EdppIsProcessLocalSystem(__int64 a1, _BYTE *a2)
{
  PVOID v4; // rcx
  void *v5; // rcx
  NTSTATUS v6; // ebx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  TokenInformation = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v5 = *(void **)a1;
    if ( !*(_QWORD *)a1 )
      v5 = *(void **)(a1 + 16);
    v6 = SeQueryInformationToken(v5, TokenUser, &TokenInformation);
    if ( v6 >= 0 )
    {
      if ( !TokenInformation )
        return (unsigned int)-1073741670;
      if ( RtlEqualSid(SeExports->SeLocalSystemSid, *(PSID *)TokenInformation) )
        *a2 = 1;
    }
    v4 = TokenInformation;
  }
  else
  {
    v6 = -1073741811;
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140053360  mov     [rsp+arg_8], rbx
0x140053365  push    rdi
0x140053366  sub     rsp, 20h
0x14005336a  mov     rax, rcx
0x14005336d  mov     rdi, rdx
0x140053370  xor     ecx, ecx; P
0x140053372  mov     [rsp+28h+TokenInformation], rcx
0x140053377  test    rax, rax
0x14005337a  jz      short loc_1400533EA
0x14005337c  test    rdx, rdx
0x14005337f  jz      short loc_1400533EA
0x140053381  mov     [rdx], cl
0x140053383  mov     rcx, [rax]
0x140053386  test    rcx, rcx
0x140053389  jnz     short loc_14005338F
0x14005338b  mov     rcx, [rax+10h]; Token
0x14005338f  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x140053394  mov     edx, 1; TokenInformationClass
0x140053399  call    cs:__imp_SeQueryInformationToken
0x1400533a0  nop     dword ptr [rax+rax+00h]
0x1400533a5  mov     ebx, eax
0x1400533a7  test    eax, eax
0x1400533a9  js      short loc_1400533E3
0x1400533ab  mov     rdx, [rsp+28h+TokenInformation]
0x1400533b0  test    rdx, rdx
0x1400533b3  jnz     short loc_1400533BC
0x1400533b5  mov     ebx, 0C000009Ah
0x1400533ba  jmp     short loc_140053402
0x1400533bc  mov     rax, cs:__imp_SeExports
0x1400533c3  mov     rdx, [rdx]; Sid2
0x1400533c6  mov     rcx, [rax]
0x1400533c9  mov     rcx, [rcx+108h]; Sid1
0x1400533d0  call    cs:__imp_RtlEqualSid
0x1400533d7  nop     dword ptr [rax+rax+00h]
0x1400533dc  test    al, al
0x1400533de  jz      short loc_1400533E3
0x1400533e0  mov     byte ptr [rdi], 1
0x1400533e3  mov     rcx, [rsp+28h+TokenInformation]
0x1400533e8  jmp     short loc_1400533EF
0x1400533ea  mov     ebx, 0C000000Dh
0x1400533ef  test    rcx, rcx
0x1400533f2  jz      short loc_140053402
0x1400533f4  xor     edx, edx; Tag
0x1400533f6  call    cs:__imp_ExFreePoolWithTag
0x1400533fd  nop     dword ptr [rax+rax+00h]
0x140053402  mov     eax, ebx
0x140053404  mov     rbx, [rsp+28h+arg_8]
0x140053409  add     rsp, 20h
0x14005340d  pop     rdi
0x14005340e  retn
```
