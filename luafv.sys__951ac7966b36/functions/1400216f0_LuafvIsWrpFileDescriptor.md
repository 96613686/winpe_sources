# LuafvIsWrpFileDescriptor

- ea: `0x1400216f0`
- end: `0x14002175d`
- name: `LuafvIsWrpFileDescriptor`
- size: `109`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001730`

## callees

- `0x1400216f0`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140021731`
- `ntoskrnl!RtlEqualSid` at `0x140021731`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140021710`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140021710`

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
0x1400216f0  push    rbx
0x1400216f2  sub     rsp, 20h
0x1400216f6  lea     r8, [rsp+28h+OwnerDefaulted]; OwnerDefaulted
0x1400216fb  mov     [rsp+28h+Owner], 0
0x140021704  lea     rdx, [rsp+28h+Owner]; Owner
0x140021709  mov     [rsp+28h+OwnerDefaulted], 0
0x14002170e  xor     bl, bl
0x140021710  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140021717  nop     dword ptr [rax+rax+00h]
0x14002171c  test    eax, eax
0x14002171e  js      short loc_140021754
0x140021720  mov     rdx, [rsp+28h+Owner]; Sid2
0x140021725  test    rdx, rdx
0x140021728  jz      short loc_140021759
0x14002172a  mov     rcx, cs:Sid1; Sid1
0x140021731  call    cs:__imp_RtlEqualSid
0x140021738  nop     dword ptr [rax+rax+00h]
0x14002173d  movzx   ecx, bl
0x140021740  mov     edx, 1
0x140021745  test    al, al
0x140021747  cmovnz  ecx, edx
0x14002174a  movzx   eax, cl
0x14002174d  add     rsp, 20h
0x140021751  pop     rbx
0x140021752  retn
0x140021754  movzx   eax, bl
0x140021757  jmp     short loc_14002174D
0x140021759  xor     al, al
0x14002175b  jmp     short loc_14002174D
```
