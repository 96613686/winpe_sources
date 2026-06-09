# CscSec_TestTokenMembership(void *,ulong)

- ea: `0x180080ad4`
- end: `0x180080b80`
- name: `?CscSec_TestTokenMembership@@YAJPEAXK@Z`
- size: `172`
- prototype: `__int64 __fastcall(void *, WINBOOL)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004a15c`
- `0x180065850`
- `0x180069d90`

## callees

- `0x18002f10c`
- `0x180080ad4`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x180080b38`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180080b38`
- `ADVAPI32!CheckTokenMembership` at `0x180080b52`
- `ADVAPI32!CheckTokenMembership` at `0x180080b52`
- `ADVAPI32!FreeSid` at `0x180080b65`
- `ADVAPI32!FreeSid` at `0x180080b65`

## pseudocode

```c
__int64 __fastcall CscSec_TestTokenMembership(void *a1, WINBOOL a2)
{
  PSID SidToCheck; // [rsp+70h] [rbp+8h] BYREF
  WINBOOL IsMember; // [rsp+78h] [rbp+10h] BYREF

  IsMember = a2;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( !IsMember )
    return ResultFromLastError();
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    IsMember = 0;
  FreeSid(SidToCheck);
  return IsMember == 0;
}

```

## disassembly

```asm
0x180080ad4  mov     rax, rsp
0x180080ad7  mov     [rax+10h], edx
0x180080ada  mov     [rax+8], rcx
0x180080ade  sub     rsp, 68h
0x180080ae2  mov     qword ptr [rax+8], 0
0x180080aea  lea     rax, [rax+8]
0x180080aee  mov     [rsp+68h+pSid], rax; pSid
0x180080af3  lea     rcx, pIdentifierAuthority; pIdentifierAuthority
0x180080afa  mov     [rsp+68h+nSubAuthority7], 0; nSubAuthority7
0x180080b02  mov     r9d, 220h; nSubAuthority1
0x180080b08  mov     [rsp+68h+nSubAuthority6], 0; nSubAuthority6
0x180080b10  mov     r8d, 20h ; ' '; nSubAuthority0
0x180080b16  mov     [rsp+68h+nSubAuthority5], 0; nSubAuthority5
0x180080b1e  mov     dl, 2; nSubAuthorityCount
0x180080b20  mov     [rsp+68h+nSubAuthority4], 0; nSubAuthority4
0x180080b28  mov     [rsp+68h+nSubAuthority3], 0; nSubAuthority3
0x180080b30  mov     [rsp+68h+nSubAuthority2], 0; nSubAuthority2
0x180080b38  call    cs:__imp_AllocateAndInitializeSid
0x180080b3e  mov     [rsp+68h+IsMember], eax
0x180080b42  test    eax, eax
0x180080b44  jz      short loc_180080B76
0x180080b46  mov     rdx, [rsp+68h+SidToCheck]; SidToCheck
0x180080b4b  lea     r8, [rsp+68h+IsMember]; IsMember
0x180080b50  xor     ecx, ecx; TokenHandle
0x180080b52  call    cs:__imp_CheckTokenMembership
0x180080b58  test    eax, eax
0x180080b5a  jnz     short loc_180080B60
0x180080b5c  mov     [rsp+68h+IsMember], eax
0x180080b60  mov     rcx, [rsp+68h+SidToCheck]; pSid
0x180080b65  call    cs:__imp_FreeSid
0x180080b6b  xor     eax, eax
0x180080b6d  cmp     [rsp+68h+IsMember], eax
0x180080b71  setz    al
0x180080b74  jmp     short loc_180080B7B
0x180080b76  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180080b7b  add     rsp, 68h
0x180080b7f  retn
```
