# SIPolicyIsSidKnownAdmin

- ea: `0x1800e0020`
- end: `0x1800e00aa`
- name: `SIPolicyIsSidKnownAdmin`
- size: `138`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800dff0c`

## callees

- `0x1800e0020`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x1800e004f`
- `ntoskrnl!RtlEqualSid` at `0x1800e004f`

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
0x1800e0020  mov     [rsp+arg_0], rbx
0x1800e0025  mov     [rsp+arg_8], rbp
0x1800e002a  push    rdi
0x1800e002b  sub     rsp, 20h
0x1800e002f  xor     edi, edi
0x1800e0031  mov     rbx, rcx
0x1800e0034  lea     ebp, [rdi+1]
0x1800e0037  cmp     edi, 0Dh
0x1800e003a  jnb     short loc_1800E0068
0x1800e003c  mov     eax, edi
0x1800e003e  mov     rcx, rbx; Sid1
0x1800e0041  imul    rdx, rax, 44h ; 'D'
0x1800e0045  lea     rax, g_SIPolicyWellKnownSids
0x1800e004c  add     rdx, rax; Sid2
0x1800e004f  call    cs:__imp_RtlEqualSid
0x1800e0056  nop     dword ptr [rax+rax+00h]
0x1800e005b  test    al, al
0x1800e005d  jnz     short loc_1800E0063
0x1800e005f  add     edi, ebp
0x1800e0061  jmp     short loc_1800E0037
0x1800e0063  mov     al, bpl
0x1800e0066  jmp     short loc_1800E0099
0x1800e0068  xor     al, al
0x1800e006a  cmp     [rbx+1], bpl
0x1800e006e  jbe     short loc_1800E0099
0x1800e0070  cmp     [rbx+2], al
0x1800e0073  jnz     short loc_1800E0099
0x1800e0075  cmp     [rbx+3], al
0x1800e0078  jnz     short loc_1800E0099
0x1800e007a  cmp     [rbx+4], al
0x1800e007d  jnz     short loc_1800E0099
0x1800e007f  cmp     [rbx+5], al
0x1800e0082  jnz     short loc_1800E0099
0x1800e0084  cmp     [rbx+6], al
0x1800e0087  jnz     short loc_1800E0099
0x1800e0089  cmp     byte ptr [rbx+7], 5
0x1800e008d  jnz     short loc_1800E0099
0x1800e008f  cmp     dword ptr [rbx+8], 50h ; 'P'
0x1800e0093  movzx   eax, al
0x1800e0096  cmovz   eax, ebp
0x1800e0099  mov     rbx, [rsp+28h+arg_0]
0x1800e009e  mov     rbp, [rsp+28h+arg_8]
0x1800e00a3  add     rsp, 20h
0x1800e00a7  pop     rdi
0x1800e00a8  retn
```
