# UserIsAdministrator(IDiskQuotaUser *)

- ea: `0x18001ad0c`
- end: `0x18001adc9`
- name: `?UserIsAdministrator@@YAHPEAUIDiskQuotaUser@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct IDiskQuotaUser *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c8c4`
- `0x1800170dc`
- `0x1800177fc`
- `0x180017b7c`

## callees

- `0x180001510`
- `0x18001ad0c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001ad9d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001ad9d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ad70`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ad70`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ada9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ada9`

## pseudocode

```c
__int64 __fastcall UserIsAdministrator(struct IDiskQuotaUser *a1)
{
  unsigned int v2; // ebx
  PSID pSid2; // [rsp+60h] [rbp-39h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-31h] BYREF
  _BYTE pSid1[80]; // [rsp+70h] [rbp-29h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v2 = 0;
  pSid2 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    if ( ((int (__fastcall *)(struct IDiskQuotaUser *, _BYTE *, __int64))a1->lpVtbl->GetQuotaLimit)(a1, pSid1, 68) >= 0 )
      v2 = EqualSid(pSid1, pSid2);
    FreeSid(pSid2);
  }
  return v2;
}

```

## disassembly

```asm
0x18001ad0c  push    rbp
0x18001ad0e  push    rbx
0x18001ad0f  push    rsi
0x18001ad10  push    rdi
0x18001ad11  lea     rbp, [rsp-3Fh]
0x18001ad16  sub     rsp, 0D8h
0x18001ad1d  mov     rax, cs:__security_cookie
0x18001ad24  xor     rax, rsp
0x18001ad27  mov     [rbp+57h+var_30], rax
0x18001ad2b  xor     esi, esi
0x18001ad2d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001ad33  lea     rax, [rbp+57h+pSid2]
0x18001ad37  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18001ad3a  mov     [rsp+0F0h+pSid], rax; pSid
0x18001ad3f  mov     rdi, rcx
0x18001ad42  mov     [rsp+0F0h+nSubAuthority7], esi; nSubAuthority7
0x18001ad46  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001ad4a  mov     [rsp+0F0h+nSubAuthority6], esi; nSubAuthority6
0x18001ad4e  lea     r8d, [rsi+20h]; nSubAuthority0
0x18001ad52  mov     [rsp+0F0h+nSubAuthority5], esi; nSubAuthority5
0x18001ad56  mov     r9d, 220h; nSubAuthority1
0x18001ad5c  mov     [rsp+0F0h+nSubAuthority4], esi; nSubAuthority4
0x18001ad60  mov     dl, 2; nSubAuthorityCount
0x18001ad62  mov     [rsp+0F0h+nSubAuthority3], esi; nSubAuthority3
0x18001ad66  mov     ebx, esi
0x18001ad68  mov     [rsp+0F0h+nSubAuthority2], esi; nSubAuthority2
0x18001ad6c  mov     [rbp+57h+pSid2], rsi
0x18001ad70  call    cs:__imp_AllocateAndInitializeSid
0x18001ad76  test    eax, eax
0x18001ad78  jz      short loc_18001ADAF
0x18001ad7a  mov     rax, [rdi]
0x18001ad7d  lea     r8d, [rsi+44h]
0x18001ad81  lea     rdx, [rbp+57h+pSid1]
0x18001ad85  mov     rcx, rdi
0x18001ad88  mov     rax, [rax+30h]
0x18001ad8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad91  test    eax, eax
0x18001ad93  js      short loc_18001ADA5
0x18001ad95  mov     rdx, [rbp+57h+pSid2]; pSid2
0x18001ad99  lea     rcx, [rbp+57h+pSid1]; pSid1
0x18001ad9d  call    cs:__imp_EqualSid
0x18001ada3  mov     ebx, eax
0x18001ada5  mov     rcx, [rbp+57h+pSid2]; pSid
0x18001ada9  call    cs:__imp_FreeSid
0x18001adaf  mov     eax, ebx
0x18001adb1  mov     rcx, [rbp+57h+var_30]
0x18001adb5  xor     rcx, rsp; StackCookie
0x18001adb8  call    __security_check_cookie
0x18001adbd  add     rsp, 0D8h
0x18001adc4  pop     rdi
0x18001adc5  pop     rsi
0x18001adc6  pop     rbx
0x18001adc7  pop     rbp
0x18001adc8  retn
```
