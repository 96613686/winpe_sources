# NameCracker::convertSid2Puid(ushort const *,_LARGE_INTEGER &)

- ea: `0x180022438`
- end: `0x180022511`
- name: `?convertSid2Puid@NameCracker@@AEAA_NPEBGAEAT_LARGE_INTEGER@@@Z`
- size: `217`
- prototype: `bool(NameCracker *__hidden this, const unsigned __int16 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800228f8`

## callees

- `0x180022438`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800224f9`
- `KERNEL32!LocalFree` at `0x1800224f9`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002245f`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002245f`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180022498`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180022498`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224a9`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224c2`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224d5`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224e9`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224a9`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224c2`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224d5`
- `ADVAPI32!GetSidSubAuthority` at `0x1800224e9`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18002247a`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18002247a`

## pseudocode

```c
bool __fastcall NameCracker::convertSid2Puid(NameCracker *this, const unsigned __int16 *a2, union _LARGE_INTEGER *a3)
{
  char v3; // bl
  BOOL v5; // eax
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v7; // ecx
  PSID Sid; // [rsp+48h] [rbp+28h] BYREF

  v3 = 0;
  Sid = 0;
  v5 = ConvertStringSidToSidW(a2, &Sid);
  if ( v5 )
  {
    SidIdentifierAuthority = GetSidIdentifierAuthority(Sid);
    v7 = *(_DWORD *)SidIdentifierAuthority->Value;
    if ( !*(_DWORD *)SidIdentifierAuthority->Value )
      v7 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 2560;
    if ( !v7 && *GetSidSubAuthorityCount(Sid) == 3 )
    {
      v3 = 1;
      a3->HighPart = *GetSidSubAuthority(Sid, 0) << 16;
      a3->HighPart |= *((unsigned __int16 *)GetSidSubAuthority(Sid, 1u) + 1);
      a3->LowPart = *GetSidSubAuthority(Sid, 1u) << 16;
      a3->LowPart |= *((unsigned __int16 *)GetSidSubAuthority(Sid, 2u) + 1);
    }
    LocalFree(Sid);
    LOBYTE(v5) = v3;
  }
  return v5;
}

```

## disassembly

```asm
0x180022438  mov     [rsp-8+arg_8], rbx
0x18002243d  mov     [rsp-8+arg_10], rdi
0x180022442  mov     [rsp-8+arg_0], rcx
0x180022447  push    rbp
0x180022448  mov     rbp, rsp
0x18002244b  sub     rsp, 20h
0x18002244f  mov     rcx, rdx; StringSid
0x180022452  xor     ebx, ebx
0x180022454  lea     rdx, [rbp+Sid]; Sid
0x180022458  mov     [rbp+Sid], rbx
0x18002245c  mov     rdi, r8
0x18002245f  call    cs:__imp_ConvertStringSidToSidW
0x180022465  test    eax, eax
0x180022467  jz      loc_180022501
0x18002246d  mov     rcx, [rbp+Sid]; pSid
0x180022471  mov     dword ptr [rbp+arg_0], ebx
0x180022474  mov     word ptr [rbp+arg_0+4], 0A00h
0x18002247a  call    cs:__imp_GetSidIdentifierAuthority
0x180022480  mov     ecx, [rax]
0x180022482  sub     ecx, ebx
0x180022484  jnz     short loc_180022490
0x180022486  movzx   ecx, word ptr [rax+4]
0x18002248a  movzx   eax, word ptr [rbp+arg_0+4]
0x18002248e  sub     ecx, eax
0x180022490  test    ecx, ecx
0x180022492  jnz     short loc_1800224F5
0x180022494  mov     rcx, [rbp+Sid]; pSid
0x180022498  call    cs:__imp_GetSidSubAuthorityCount
0x18002249e  cmp     byte ptr [rax], 3
0x1800224a1  jnz     short loc_1800224F5
0x1800224a3  mov     rcx, [rbp+Sid]; pSid
0x1800224a7  xor     edx, edx; nSubAuthority
0x1800224a9  call    cs:__imp_GetSidSubAuthority
0x1800224af  mov     ebx, 1
0x1800224b4  mov     edx, ebx; nSubAuthority
0x1800224b6  mov     ecx, [rax]
0x1800224b8  shl     ecx, 10h
0x1800224bb  mov     [rdi+4], ecx
0x1800224be  mov     rcx, [rbp+Sid]; pSid
0x1800224c2  call    cs:__imp_GetSidSubAuthority
0x1800224c8  mov     edx, ebx; nSubAuthority
0x1800224ca  movzx   ecx, word ptr [rax+2]
0x1800224ce  or      [rdi+4], ecx
0x1800224d1  mov     rcx, [rbp+Sid]; pSid
0x1800224d5  call    cs:__imp_GetSidSubAuthority
0x1800224db  lea     edx, [rbx+1]; nSubAuthority
0x1800224de  mov     ecx, [rax]
0x1800224e0  shl     ecx, 10h
0x1800224e3  mov     [rdi], ecx
0x1800224e5  mov     rcx, [rbp+Sid]; pSid
0x1800224e9  call    cs:__imp_GetSidSubAuthority
0x1800224ef  movzx   ecx, word ptr [rax+2]
0x1800224f3  or      [rdi], ecx
0x1800224f5  mov     rcx, [rbp+Sid]; hMem
0x1800224f9  call    cs:__imp_LocalFree
0x1800224ff  mov     al, bl
0x180022501  mov     rbx, [rsp+20h+arg_8]
0x180022506  mov     rdi, [rsp+20h+arg_10]
0x18002250b  add     rsp, 20h
0x18002250f  pop     rbp
0x180022510  retn
```
