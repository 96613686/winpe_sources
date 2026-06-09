# LuafvIsWrpFileDescriptor

- ea: `0x1400216a0`
- end: `0x14002170d`
- name: `LuafvIsWrpFileDescriptor`
- size: `109`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001730`

## callees

- `0x1400216a0`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x1400216e1`
- `ntoskrnl!RtlEqualSid` at `0x1400216e1`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400216c0`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400216c0`

## pseudocode

```c
bool __fastcall LuafvIsWrpFileDescriptor(void *a1)
{
  unsigned __int8 OwnerDefaulted; // [rsp+38h] [rbp+10h] BYREF
  PSID Owner; // [rsp+40h] [rbp+18h] BYREF

  Owner = 0;
  OwnerDefaulted = 0;
  if ( RtlGetOwnerSecurityDescriptor(a1, &Owner, &OwnerDefaulted) < 0 )
    return 0;
  if ( Owner )
    return RtlEqualSid(Sid1, Owner) != 0;
  return 0;
}

```

## disassembly

```asm
0x1400216a0  push    rbx
0x1400216a2  sub     rsp, 20h
0x1400216a6  lea     r8, [rsp+28h+OwnerDefaulted]; OwnerDefaulted
0x1400216ab  mov     [rsp+28h+Owner], 0
0x1400216b4  lea     rdx, [rsp+28h+Owner]; Owner
0x1400216b9  mov     [rsp+28h+OwnerDefaulted], 0
0x1400216be  xor     bl, bl
0x1400216c0  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400216c7  nop     dword ptr [rax+rax+00h]
0x1400216cc  test    eax, eax
0x1400216ce  js      short loc_140021704
0x1400216d0  mov     rdx, [rsp+28h+Owner]; Sid2
0x1400216d5  test    rdx, rdx
0x1400216d8  jz      short loc_140021709
0x1400216da  mov     rcx, cs:Sid1; Sid1
0x1400216e1  call    cs:__imp_RtlEqualSid
0x1400216e8  nop     dword ptr [rax+rax+00h]
0x1400216ed  movzx   ecx, bl
0x1400216f0  mov     edx, 1
0x1400216f5  test    al, al
0x1400216f7  cmovnz  ecx, edx
0x1400216fa  movzx   eax, cl
0x1400216fd  add     rsp, 20h
0x140021701  pop     rbx
0x140021702  retn
0x140021704  movzx   eax, bl
0x140021707  jmp     short loc_1400216FD
0x140021709  xor     al, al
0x14002170b  jmp     short loc_1400216FD
```
