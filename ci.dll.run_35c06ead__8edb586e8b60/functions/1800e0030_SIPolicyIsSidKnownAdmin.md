# SIPolicyIsSidKnownAdmin

- ea: `0x1800e0030`
- end: `0x1800e00ba`
- name: `SIPolicyIsSidKnownAdmin`
- size: `138`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800dff1c`

## callees

- `0x1800e0030`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x1800e005f`
- `ntoskrnl!RtlEqualSid` at `0x1800e005f`

## pseudocode

```c
bool __fastcall SIPolicyIsSidKnownAdmin(PSID Sid1)
{
  unsigned int i; // edi
  bool result; // al

  for ( i = 0; i < 0xD; ++i )
  {
    if ( RtlEqualSid(Sid1, (char *)g_SIPolicyWellKnownSids + 68 * i) )
      return 1;
  }
  result = 0;
  if ( *((_BYTE *)Sid1 + 1) > 1u
    && !*((_BYTE *)Sid1 + 2)
    && !*((_BYTE *)Sid1 + 3)
    && !*((_BYTE *)Sid1 + 4)
    && !*((_BYTE *)Sid1 + 5)
    && !*((_BYTE *)Sid1 + 6)
    && *((_BYTE *)Sid1 + 7) == 5 )
  {
    return *((_DWORD *)Sid1 + 2) == 80;
  }
  return result;
}

```

## disassembly

```asm
0x1800e0030  mov     [rsp+arg_0], rbx
0x1800e0035  mov     [rsp+arg_8], rbp
0x1800e003a  push    rdi
0x1800e003b  sub     rsp, 20h
0x1800e003f  xor     edi, edi
0x1800e0041  mov     rbx, rcx
0x1800e0044  lea     ebp, [rdi+1]
0x1800e0047  cmp     edi, 0Dh
0x1800e004a  jnb     short loc_1800E0078
0x1800e004c  mov     eax, edi
0x1800e004e  mov     rcx, rbx; Sid1
0x1800e0051  imul    rdx, rax, 44h ; 'D'
0x1800e0055  lea     rax, g_SIPolicyWellKnownSids
0x1800e005c  add     rdx, rax; Sid2
0x1800e005f  call    cs:__imp_RtlEqualSid
0x1800e0066  nop     dword ptr [rax+rax+00h]
0x1800e006b  test    al, al
0x1800e006d  jnz     short loc_1800E0073
0x1800e006f  add     edi, ebp
0x1800e0071  jmp     short loc_1800E0047
0x1800e0073  mov     al, bpl
0x1800e0076  jmp     short loc_1800E00A9
0x1800e0078  xor     al, al
0x1800e007a  cmp     [rbx+1], bpl
0x1800e007e  jbe     short loc_1800E00A9
0x1800e0080  cmp     [rbx+2], al
0x1800e0083  jnz     short loc_1800E00A9
0x1800e0085  cmp     [rbx+3], al
0x1800e0088  jnz     short loc_1800E00A9
0x1800e008a  cmp     [rbx+4], al
0x1800e008d  jnz     short loc_1800E00A9
0x1800e008f  cmp     [rbx+5], al
0x1800e0092  jnz     short loc_1800E00A9
0x1800e0094  cmp     [rbx+6], al
0x1800e0097  jnz     short loc_1800E00A9
0x1800e0099  cmp     byte ptr [rbx+7], 5
0x1800e009d  jnz     short loc_1800E00A9
0x1800e009f  cmp     dword ptr [rbx+8], 50h ; 'P'
0x1800e00a3  movzx   eax, al
0x1800e00a6  cmovz   eax, ebp
0x1800e00a9  mov     rbx, [rsp+28h+arg_0]
0x1800e00ae  mov     rbp, [rsp+28h+arg_8]
0x1800e00b3  add     rsp, 20h
0x1800e00b7  pop     rdi
0x1800e00b8  retn
```
