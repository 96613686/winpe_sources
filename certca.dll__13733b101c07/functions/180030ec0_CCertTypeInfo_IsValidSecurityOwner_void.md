# CCertTypeInfo::IsValidSecurityOwner(void)

- ea: `0x180030ec0`
- end: `0x180031033`
- name: `?IsValidSecurityOwner@CCertTypeInfo@@QEAAHXZ`
- size: `371`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e710`
- `0x180030224`

## callees

- `0x180008400`
- `0x180012450`
- `0x18002ffbc`
- `0x180030ec0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031023`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180030fc0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180030fc0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180030f42`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180030f42`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030ef2`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180030ef2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180030ff6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180031008`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180030ff6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180031008`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180030f86`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180030f86`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::IsValidSecurityOwner(CCertTypeInfo *this)
{
  void *v2; // rcx
  unsigned int v3; // esi
  int RootDomEntitySid; // eax
  unsigned int v5; // ecx
  int v6; // edx
  PSID pSid2; // [rsp+20h] [rbp-20h] BYREF
  PSID pOwner; // [rsp+28h] [rbp-18h] BYREF
  PSID pGroup; // [rsp+30h] [rbp-10h] BYREF
  WORD pControl; // [rsp+60h] [rbp+20h] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp+28h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+70h] [rbp+30h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+78h] [rbp+38h] BYREF

  v2 = (void *)*((_QWORD *)this + 17);
  v3 = 0;
  pControl = 0;
  dwRevision = 0;
  pOwner = 0;
  pGroup = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  pSid2 = 0;
  if ( !IsValidSecurityDescriptor(v2) )
  {
    CSPrintErrorLineFile(0x1E630328u, -2147023558);
    return v3;
  }
  RootDomEntitySid = GetRootDomEntitySid(&pSid2, 519);
  if ( RootDomEntitySid )
  {
    v5 = 510133032;
LABEL_5:
    v6 = RootDomEntitySid;
    goto LABEL_6;
  }
  if ( !GetSecurityDescriptorControl(*((PSECURITY_DESCRIPTOR *)this + 17), &pControl, &dwRevision) )
  {
    RootDomEntitySid = myHLastError();
    v5 = 510526248;
    goto LABEL_5;
  }
  if ( (pControl & 0x8000u) == 0 )
  {
    v6 = -2147023558;
    v5 = 510919464;
    goto LABEL_6;
  }
  if ( !GetSecurityDescriptorOwner(*((PSECURITY_DESCRIPTOR *)this + 17), &pOwner, &bOwnerDefaulted) )
  {
    RootDomEntitySid = myHLastError();
    v5 = 511378216;
    goto LABEL_5;
  }
  if ( !pOwner )
  {
    v6 = -2147023558;
    v5 = 511771432;
    goto LABEL_6;
  }
  if ( !GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 17), &pGroup, &bGroupDefaulted) )
  {
    RootDomEntitySid = myHLastError();
    v5 = 512164648;
    goto LABEL_5;
  }
  if ( pGroup )
  {
    if ( EqualSid(pOwner, pSid2) )
      v3 = EqualSid(pGroup, pSid2);
    goto LABEL_21;
  }
  v6 = -2147023558;
  v5 = 512557864;
LABEL_6:
  CSPrintErrorLineFile(v5, v6);
LABEL_21:
  if ( pSid2 )
    LocalFree(pSid2);
  return v3;
}

```

## disassembly

```asm
0x180030ec0  push    rbp
0x180030ec2  push    rsi
0x180030ec3  push    rdi
0x180030ec4  mov     rbp, rsp
0x180030ec7  sub     rsp, 40h
0x180030ecb  xor     eax, eax
0x180030ecd  mov     rdi, rcx
0x180030ed0  mov     rcx, [rcx+88h]; pSecurityDescriptor
0x180030ed7  xor     esi, esi
0x180030ed9  mov     [rbp+pControl], ax
0x180030edd  mov     [rbp+dwRevision], eax
0x180030ee0  mov     [rbp+pOwner], rax
0x180030ee4  mov     [rbp+pGroup], rax
0x180030ee8  mov     [rbp+bOwnerDefaulted], eax
0x180030eeb  mov     [rbp+bGroupDefaulted], eax
0x180030eee  mov     [rbp+pSid2], rax
0x180030ef2  call    cs:__imp_IsValidSecurityDescriptor
0x180030ef8  test    eax, eax
0x180030efa  jnz     short loc_180030F10
0x180030efc  mov     edx, 8007053Ah; int
0x180030f01  mov     ecx, 1E630328h; unsigned int
0x180030f06  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030f0b  jmp     loc_180031029
0x180030f10  mov     edx, 207h
0x180030f15  lea     rcx, [rbp+pSid2]
0x180030f19  call    GetRootDomEntitySid
0x180030f1e  test    eax, eax
0x180030f20  jz      short loc_180030F33
0x180030f22  mov     ecx, 1E680328h; unsigned int
0x180030f27  mov     edx, eax; int
0x180030f29  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030f2e  jmp     loc_180031018
0x180030f33  mov     rcx, [rdi+88h]; pSecurityDescriptor
0x180030f3a  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180030f3e  lea     rdx, [rbp+pControl]; pControl
0x180030f42  call    cs:__imp_GetSecurityDescriptorControl
0x180030f48  test    eax, eax
0x180030f4a  jnz     short loc_180030F58
0x180030f4c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180030f51  mov     ecx, 1E6E0328h
0x180030f56  jmp     short loc_180030F27
0x180030f58  movzx   ecx, [rbp+pControl]
0x180030f5c  mov     eax, 8000h
0x180030f61  and     cx, ax
0x180030f64  xor     eax, eax
0x180030f66  cmp     ax, cx
0x180030f69  jnz     short loc_180030F77
0x180030f6b  mov     edx, 8007053Ah
0x180030f70  mov     ecx, 1E740328h
0x180030f75  jmp     short loc_180030F29
0x180030f77  mov     rcx, [rdi+88h]; pSecurityDescriptor
0x180030f7e  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180030f82  lea     rdx, [rbp+pOwner]; pOwner
0x180030f86  call    cs:__imp_GetSecurityDescriptorOwner
0x180030f8c  test    eax, eax
0x180030f8e  jnz     short loc_180030F9C
0x180030f90  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180030f95  mov     ecx, 1E7B0328h
0x180030f9a  jmp     short loc_180030F27
0x180030f9c  cmp     [rbp+pOwner], rsi
0x180030fa0  jnz     short loc_180030FB1
0x180030fa2  mov     edx, 8007053Ah
0x180030fa7  mov     ecx, 1E810328h
0x180030fac  jmp     loc_180030F29
0x180030fb1  mov     rcx, [rdi+88h]; pSecurityDescriptor
0x180030fb8  lea     r8, [rbp+bGroupDefaulted]; lpbGroupDefaulted
0x180030fbc  lea     rdx, [rbp+pGroup]; pGroup
0x180030fc0  call    cs:__imp_GetSecurityDescriptorGroup
0x180030fc6  test    eax, eax
0x180030fc8  jnz     short loc_180030FD9
0x180030fca  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180030fcf  mov     ecx, 1E870328h
0x180030fd4  jmp     loc_180030F27
0x180030fd9  cmp     [rbp+pGroup], rsi
0x180030fdd  jnz     short loc_180030FEE
0x180030fdf  mov     edx, 8007053Ah
0x180030fe4  mov     ecx, 1E8D0328h
0x180030fe9  jmp     loc_180030F29
0x180030fee  mov     rdx, [rbp+pSid2]; pSid2
0x180030ff2  mov     rcx, [rbp+pOwner]; pSid1
0x180030ff6  call    cs:__imp_EqualSid
0x180030ffc  test    eax, eax
0x180030ffe  jz      short loc_180031018
0x180031000  mov     rdx, [rbp+pSid2]; pSid2
0x180031004  mov     rcx, [rbp+pGroup]; pSid1
0x180031008  call    cs:__imp_EqualSid
0x18003100e  test    eax, eax
0x180031010  mov     ecx, 1
0x180031015  cmovnz  esi, ecx
0x180031018  cmp     [rbp+pSid2], 0
0x18003101d  jz      short loc_180031029
0x18003101f  mov     rcx, [rbp+pSid2]; hMem
0x180031023  call    cs:__imp_LocalFree
0x180031029  mov     eax, esi
0x18003102b  add     rsp, 40h
0x18003102f  pop     rdi
0x180031030  pop     rsi
0x180031031  pop     rbp
0x180031032  retn
```
