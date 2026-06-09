# DfsRemoveWellKnownSidsAcl

- ea: `0x140059cf0`
- end: `0x140059e1c`
- name: `DfsRemoveWellKnownSidsAcl`
- size: `300`
- prototype: `__int64 __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400599e0`

## callees

- `0x140059cf0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x140059d86`
- `ntdll!RtlSubAuthorityCountSid` at `0x140059d86`
- `ntdll!RtlIdentifierAuthoritySid` at `0x140059d9a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x140059d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059df2`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140059dd0`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x140059dd0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140059d31`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140059d31`

## pseudocode

```c
DWORD __fastcall DfsRemoveWellKnownSidsAcl(PACL pAcl)
{
  int v1; // ebx
  WORD v3; // si
  unsigned __int8 v4; // al
  char *v5; // rdi
  PSID_IDENTIFIER_AUTHORITY v6; // rax
  int v7; // ecx
  LPVOID pAce; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  pAce = 0;
  v3 = 0;
  while ( v3 < pAcl->AceCount )
  {
    if ( !GetAce(pAcl, v3, &pAce) )
      return GetLastError();
    v4 = *(_BYTE *)pAce;
    if ( *(_BYTE *)pAce == 4 )
    {
      v5 = (char *)pAce + 12;
LABEL_10:
      if ( *RtlSubAuthorityCountSid(v5) <= 2u )
      {
        v6 = RtlIdentifierAuthoritySid(v5);
        v7 = *(_DWORD *)v6->Value - CreatorSidAuthority;
        if ( *(_DWORD *)v6->Value == CreatorSidAuthority )
          v7 = *(unsigned __int16 *)&v6->Value[4] - (unsigned __int16)word_140070AA4;
        if ( v7 )
          goto LABEL_15;
      }
      ++v3;
    }
    else
    {
      if ( v4 <= 3u )
      {
        v5 = (char *)pAce + 8;
        goto LABEL_10;
      }
      if ( (unsigned __int8)(v4 - 5) <= 3u )
      {
        v5 = (char *)pAce + 16 * (*((_DWORD *)pAce + 2) & 1LL) + 8 * (*((_DWORD *)pAce + 2) & 2) + 12;
        goto LABEL_10;
      }
LABEL_15:
      if ( !DeleteAce(pAcl, v3) )
        return GetLastError();
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140059cf0  mov     rax, rsp
0x140059cf3  mov     [rax+10h], rbx
0x140059cf7  mov     [rax+18h], rbp
0x140059cfb  mov     [rax+20h], rsi
0x140059cff  push    rdi
0x140059d00  push    r14
0x140059d02  push    r15
0x140059d04  sub     rsp, 20h
0x140059d08  xor     ebx, ebx
0x140059d0a  mov     rbp, rcx
0x140059d0d  mov     [rax+8], rbx
0x140059d11  movzx   esi, bx
0x140059d14  lea     r15d, [rbx+1]
0x140059d18  cmp     si, [rbp+4]
0x140059d1c  jnb     loc_140059E00
0x140059d22  movzx   r14d, si
0x140059d26  lea     r8, [rsp+38h+pAce]; pAce
0x140059d2b  mov     edx, r14d; dwAceIndex
0x140059d2e  mov     rcx, rbp; pAcl
0x140059d31  call    cs:__imp_GetAce
0x140059d38  nop     dword ptr [rax+rax+00h]
0x140059d3d  test    eax, eax
0x140059d3f  jz      loc_140059DF2
0x140059d45  mov     rdx, [rsp+38h+pAce]
0x140059d4a  mov     al, [rdx]
0x140059d4c  cmp     al, 4
0x140059d4e  jnz     short loc_140059D56
0x140059d50  lea     rdi, [rdx+0Ch]
0x140059d54  jmp     short loc_140059D83
0x140059d56  cmp     al, 3
0x140059d58  ja      short loc_140059D60
0x140059d5a  lea     rdi, [rdx+8]
0x140059d5e  jmp     short loc_140059D83
0x140059d60  sub     al, 5
0x140059d62  cmp     al, 3
0x140059d64  ja      short loc_140059DCA
0x140059d66  mov     ecx, [rdx+8]
0x140059d69  mov     eax, ecx
0x140059d6b  and     rax, r15
0x140059d6e  and     ecx, 2
0x140059d71  shl     rax, 4
0x140059d75  add     rax, rdx
0x140059d78  lea     rdi, ds:0Ch[rcx*8]
0x140059d80  add     rdi, rax
0x140059d83  mov     rcx, rdi; Sid
0x140059d86  call    cs:__imp_RtlSubAuthorityCountSid
0x140059d8d  nop     dword ptr [rax+rax+00h]
0x140059d92  cmp     byte ptr [rax], 2
0x140059d95  ja      short loc_140059DC1
0x140059d97  mov     rcx, rdi; Sid
0x140059d9a  call    cs:__imp_RtlIdentifierAuthoritySid
0x140059da1  nop     dword ptr [rax+rax+00h]
0x140059da6  mov     ecx, [rax]
0x140059da8  sub     ecx, cs:CreatorSidAuthority
0x140059dae  jnz     short loc_140059DBD
0x140059db0  movzx   ecx, word ptr [rax+4]
0x140059db4  movzx   eax, cs:word_140070AA4
0x140059dbb  sub     ecx, eax
0x140059dbd  test    ecx, ecx
0x140059dbf  jnz     short loc_140059DCA
0x140059dc1  add     si, r15w
0x140059dc5  jmp     loc_140059D18
0x140059dca  mov     edx, r14d; dwAceIndex
0x140059dcd  mov     rcx, rbp; pAcl
0x140059dd0  call    cs:__imp_DeleteAce
0x140059dd7  nop     dword ptr [rax+rax+00h]
0x140059ddc  test    eax, eax
0x140059dde  jnz     loc_140059D18
0x140059de4  call    cs:__imp_GetLastError
0x140059deb  nop     dword ptr [rax+rax+00h]
0x140059df0  jmp     short loc_140059E02
0x140059df2  call    cs:__imp_GetLastError
0x140059df9  nop     dword ptr [rax+rax+00h]
0x140059dfe  mov     ebx, eax
0x140059e00  mov     eax, ebx
0x140059e02  mov     rbx, [rsp+38h+arg_8]
0x140059e07  mov     rbp, [rsp+38h+arg_10]
0x140059e0c  mov     rsi, [rsp+38h+arg_18]
0x140059e11  add     rsp, 20h
0x140059e15  pop     r15
0x140059e17  pop     r14
0x140059e19  pop     rdi
0x140059e1a  retn
```
