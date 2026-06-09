# sub_1401BDEFE

- ea: `0x1401bdefe`
- end: `0x1401bdf4d`
- name: `sub_1401BDEFE`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401bdea2`

## callees

- `0x1400f8e50`
- `0x14011fa70`
- `0x1401bdefe`
- `0x1401bdf50`

## import_xrefs

- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1401b98e5`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1401b98e5`
- `ADVAPI32!FreeSid` at `0x1401b9921`
- `ADVAPI32!FreeSid` at `0x1401b9921`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1401b9907`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1401b9907`

## pseudocode

```c
__int64 __fastcall sub_1401BDEFE()
{
  PSID v0; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int v2; // esi
  __int64 v4; // [rsp+0h] [rbp-48h] BYREF
  PSID pSid[4]; // [rsp+28h] [rbp-20h] BYREF

  LOBYTE(v2) = 1;
  if ( !(unsigned __int8)sub_1400F8E50() && (unsigned __int8)sub_1401BDF50() )
    goto LABEL_5;
  while ( _security_cookie != ((unsigned __int64)&v4 ^ (unsigned __int64)pSid[1]) )
  {
LABEL_5:
    pSid[0] = 0;
    LOBYTE(v2) = 1;
    if ( (int)DeriveAppContainerSidFromAppContainerName("w", pSid) >= 0 )
    {
      v0 = pSid[0];
      if ( pSid[0] )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
        if ( SidSubAuthorityCount && *SidSubAuthorityCount == 8 )
          v2 = 0;
        else
          LOBYTE(v2) = 1;
        FreeSid(v0);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1401bdefe  push    rsi
0x1401bdeff  push    rdi
0x1401bdf00  sub     rsp, 38h
0x1401bdf04  mov     rax, cs:__security_cookie
0x1401bdf0b  xor     rax, rsp
0x1401bdf0e  mov     [rsp+48h+var_18], rax
0x1401bdf13  mov     sil, 1
0x1401bdf16  call    sub_1400F8E50
0x1401bdf1b  test    al, al
0x1401bdf1d  jnz     short loc_1401BDF2C
0x1401bdf1f  call    sub_1401BDF50
0x1401bdf24  test    al, al
0x1401bdf26  jnz     loc_1401B98D2
0x1401bdf2c  mov     rax, [rsp+48h+var_18]
0x1401bdf31  xor     rax, rsp
0x1401bdf34  mov     rcx, cs:__security_cookie
0x1401bdf3b  cmp     rcx, rax
0x1401bdf3e  jnz     loc_1401B98C5
0x1401bdf44  mov     eax, esi
0x1401bdf46  add     rsp, 38h
0x1401bdf4a  pop     rdi
0x1401bdf4b  pop     rsi
0x1401bdf4c  retn
0x1401b98c5  mov     rcx, [rsp+48h+var_18]
0x1401b98ca  xor     rcx, rsp; StackCookie
0x1401b98cd  call    __security_check_cookie
0x1401b98d2  lea     rdx, [rsp+48h+pSid]
0x1401b98d7  mov     qword ptr [rdx], 0
0x1401b98de  lea     rcx, aW_3; "w"
0x1401b98e5  call    cs:DeriveAppContainerSidFromAppContainerName
0x1401b98eb  mov     sil, 1
0x1401b98ee  test    eax, eax
0x1401b98f0  js      loc_1401BDF2C
0x1401b98f6  mov     rdi, [rsp+48h+pSid]
0x1401b98fb  test    rdi, rdi
0x1401b98fe  jz      loc_1401BDF2C
0x1401b9904  mov     rcx, rdi; pSid
0x1401b9907  call    cs:GetSidSubAuthorityCount
0x1401b990d  test    rax, rax
0x1401b9910  jz      short loc_1401B991B
0x1401b9912  cmp     byte ptr [rax], 8
0x1401b9915  jnz     short loc_1401B991B
0x1401b9917  xor     esi, esi
0x1401b9919  jmp     short loc_1401B991E
0x1401b991b  mov     sil, 1
0x1401b991e  mov     rcx, rdi; pSid
0x1401b9921  call    cs:FreeSid
0x1401b9927  jmp     loc_1401BDF2C
```
