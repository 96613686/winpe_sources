# SecCheckUserSid

- ea: `0x14002ab0c`
- end: `0x14002abca`
- name: `SecCheckUserSid`
- size: `190`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140023e10`
- `0x14002b3a4`

## callees

- `0x14002ab0c`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x14002ab25`
- `ntoskrnl!RtlValidSid` at `0x14002ab25`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002abab`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002abab`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x14002ab95`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x14002ab95`

## pseudocode

```c
bool __fastcall SecCheckUserSid(char *Sid)
{
  int v4; // [rsp+30h] [rbp+10h]
  __int16 v5; // [rsp+34h] [rbp+14h]

  if ( !Sid || !RtlValidSid(Sid) )
    return 0;
  v4 = *(_DWORD *)(Sid + 2);
  v5 = *((_WORD *)Sid + 3);
  if ( HIBYTE(v5) == 12 )
  {
    if ( (_BYTE)v4 || __PAIR16__(BYTE1(v4), 0) != BYTE2(v4) || HIBYTE(v4) )
      return 0;
    return (_BYTE)v5 == 0;
  }
  else
  {
    if ( HIBYTE(v5) != 5
      || (_BYTE)v4
      || __PAIR16__(BYTE1(v4), 0) != BYTE2(v4)
      || __PAIR16__(HIBYTE(v4), 0) != (unsigned __int8)v5
      || !RtlSubAuthorityCountSid(Sid) )
    {
      return 0;
    }
    return *RtlSubAuthoritySid(Sid, 0) == 21;
  }
}

```

## disassembly

```asm
0x14002ab0c  mov     [rsp-8+arg_8], rbx
0x14002ab11  push    rbp
0x14002ab12  mov     rbp, rsp
0x14002ab15  sub     rsp, 20h
0x14002ab19  mov     rbx, rcx
0x14002ab1c  test    rcx, rcx
0x14002ab1f  jz      loc_14002ABBC
0x14002ab25  call    cs:__imp_RtlValidSid
0x14002ab2c  nop     dword ptr [rax+rax+00h]
0x14002ab31  test    al, al
0x14002ab33  jz      loc_14002ABBC
0x14002ab39  mov     eax, [rbx+2]
0x14002ab3c  mov     [rbp+arg_0], eax
0x14002ab3f  movzx   eax, word ptr [rbx+6]
0x14002ab43  mov     [rbp+arg_4], ax
0x14002ab47  mov     al, byte ptr [rbp+arg_4+1]
0x14002ab4a  cmp     al, 0Ch
0x14002ab4c  jnz     short loc_14002AB70
0x14002ab4e  cmp     byte ptr [rbp+arg_0], 0
0x14002ab52  jnz     short loc_14002ABBC
0x14002ab54  cmp     byte ptr [rbp+arg_0+1], 0
0x14002ab58  jnz     short loc_14002ABBC
0x14002ab5a  cmp     byte ptr [rbp+arg_0+2], 0
0x14002ab5e  jnz     short loc_14002ABBC
0x14002ab60  cmp     byte ptr [rbp+arg_0+3], 0
0x14002ab64  jnz     short loc_14002ABBC
0x14002ab66  cmp     byte ptr [rbp+arg_4], 0
0x14002ab6a  jnz     short loc_14002ABBC
0x14002ab6c  mov     al, 1
0x14002ab6e  jmp     short loc_14002ABBE
0x14002ab70  cmp     al, 5
0x14002ab72  jnz     short loc_14002ABBC
0x14002ab74  cmp     byte ptr [rbp+arg_0], 0
0x14002ab78  jnz     short loc_14002ABBC
0x14002ab7a  cmp     byte ptr [rbp+arg_0+1], 0
0x14002ab7e  jnz     short loc_14002ABBC
0x14002ab80  cmp     byte ptr [rbp+arg_0+2], 0
0x14002ab84  jnz     short loc_14002ABBC
0x14002ab86  cmp     byte ptr [rbp+arg_0+3], 0
0x14002ab8a  jnz     short loc_14002ABBC
0x14002ab8c  cmp     byte ptr [rbp+arg_4], 0
0x14002ab90  jnz     short loc_14002ABBC
0x14002ab92  mov     rcx, rbx; Sid
0x14002ab95  call    cs:__imp_RtlSubAuthorityCountSid
0x14002ab9c  nop     dword ptr [rax+rax+00h]
0x14002aba1  test    rax, rax
0x14002aba4  jz      short loc_14002ABBC
0x14002aba6  xor     edx, edx; SubAuthority
0x14002aba8  mov     rcx, rbx; Sid
0x14002abab  call    cs:__imp_RtlSubAuthoritySid
0x14002abb2  nop     dword ptr [rax+rax+00h]
0x14002abb7  cmp     dword ptr [rax], 15h
0x14002abba  jmp     short loc_14002AB6A
0x14002abbc  xor     al, al
0x14002abbe  mov     rbx, [rsp+20h+arg_8]
0x14002abc3  add     rsp, 20h
0x14002abc7  pop     rbp
0x14002abc8  retn
```
