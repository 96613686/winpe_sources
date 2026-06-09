# SipCryptProvider::SipCryptProvider(SIP_SUBJECTINFO_ const *)

- ea: `0x1800032e8`
- end: `0x180003342`
- name: `??0SipCryptProvider@@QEAA@PEBUSIP_SUBJECTINFO_@@@Z`
- size: `90`
- prototype: `SipCryptProvider *__fastcall(SipCryptProvider *__hidden this, const struct SIP_SUBJECTINFO_ *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003dd4`
- `0x180003ed8`

## callees

- `0x1800032e8`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x180003328`
- `ADVAPI32!CryptAcquireContextW` at `0x180003328`

## pseudocode

```c
SipCryptProvider *__fastcall SipCryptProvider::SipCryptProvider(
        SipCryptProvider *this,
        const struct SIP_SUBJECTINFO_ *a2)
{
  HCRYPTPROV *v2; // rdi
  HCRYPTPROV hProv; // rax

  v2 = (HCRYPTPROV *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  if ( !a2 || (hProv = a2->hProv) == 0 )
  {
    CryptAcquireContextW((HCRYPTPROV *)this + 1, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000);
    hProv = *v2;
  }
  *(_QWORD *)this = hProv;
  return this;
}

```

## disassembly

```asm
0x1800032e8  mov     [rsp+arg_0], rbx
0x1800032ed  push    rdi
0x1800032ee  sub     rsp, 30h
0x1800032f2  lea     rdi, [rcx+8]
0x1800032f6  mov     rbx, rcx
0x1800032f9  mov     qword ptr [rdi], 0
0x180003300  test    rdx, rdx
0x180003303  jz      short loc_18000330E
0x180003305  mov     rax, [rdx+30h]
0x180003309  test    rax, rax
0x18000330c  jnz     short loc_180003331
0x18000330e  mov     r9d, 1; dwProvType
0x180003314  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x18000331c  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180003323  xor     edx, edx; szContainer
0x180003325  mov     rcx, rdi; phProv
0x180003328  call    cs:__imp_CryptAcquireContextW
0x18000332e  mov     rax, [rdi]
0x180003331  mov     [rbx], rax
0x180003334  mov     rax, rbx
0x180003337  mov     rbx, [rsp+38h+arg_0]
0x18000333c  add     rsp, 30h
0x180003340  pop     rdi
0x180003341  retn
```
