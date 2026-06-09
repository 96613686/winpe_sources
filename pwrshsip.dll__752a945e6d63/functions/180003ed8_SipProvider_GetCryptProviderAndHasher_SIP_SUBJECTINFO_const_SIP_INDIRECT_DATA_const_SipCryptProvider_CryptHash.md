# SipProvider::GetCryptProviderAndHasher(SIP_SUBJECTINFO_ const *,SIP_INDIRECT_DATA_ const *,SipCryptProvider * *,CryptHash * *)

- ea: `0x180003ed8`
- end: `0x180003fdb`
- name: `?GetCryptProviderAndHasher@SipProvider@@AEAAKPEBUSIP_SUBJECTINFO_@@PEBUSIP_INDIRECT_DATA_@@PEAPEAVSipCryptProvider@@PEAPEAVCryptHash@@@Z`
- size: `259`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, const struct SIP_INDIRECT_DATA_ *, struct SipCryptProvider **, struct CryptHash **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800050b0`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800032e8`
- `0x180003348`
- `0x180003374`
- `0x180003ba0`
- `0x180003d50`
- `0x180003ed8`

## pseudocode

```c
__int64 __fastcall SipProvider::GetCryptProviderAndHasher(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        const struct SIP_INDIRECT_DATA_ *a3,
        struct SipCryptProvider **a4,
        struct CryptHash **a5)
{
  CryptHash *v5; // rdi
  struct CryptHash **v9; // r14
  SipCryptProvider *v10; // rax
  SipCryptProvider *v11; // rcx
  const struct SipCryptProvider *v12; // rsi
  unsigned int AlgId; // ebx
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF
  int v16; // [rsp+44h] [rbp+Ch]
  struct CryptHash *v17; // [rsp+48h] [rbp+10h] BYREF

  v16 = HIDWORD(this);
  v5 = 0;
  v15 = 0;
  v17 = 0;
  if ( !a2 )
    return 87;
  if ( !a3 )
    return 87;
  if ( !a4 )
    return 87;
  v9 = a5;
  if ( !a5 )
    return 87;
  *a4 = 0;
  *v9 = 0;
  v10 = (SipCryptProvider *)operator new(0x10u);
  if ( !v10 )
    return 8;
  v12 = SipCryptProvider::SipCryptProvider(v10, a2);
  if ( !v12 )
    return 8;
  AlgId = SipCryptProvider::GetAlgId(v11, a3->DigestAlgorithm.pszObjId, &v15);
  if ( !AlgId )
  {
    AlgId = SipProvider::GetCryptHasher(v12, v15, &v17);
    if ( !AlgId )
    {
      *v9 = v17;
      *a4 = v12;
      return AlgId;
    }
    v5 = v17;
  }
  SipCryptProvider::~SipCryptProvider(v12);
  operator delete(v12);
  if ( v5 )
  {
    CryptHash::~CryptHash(v5);
    operator delete(v5);
  }
  return AlgId;
}

```

## disassembly

```asm
0x180003ed8  mov     rax, rsp
0x180003edb  mov     [rax+18h], rbx
0x180003edf  mov     [rax+20h], rsi
0x180003ee3  mov     [rax+8], rcx
0x180003ee7  push    rdi
0x180003ee8  push    r14
0x180003eea  push    r15
0x180003eec  sub     rsp, 20h
0x180003ef0  xor     edi, edi
0x180003ef2  mov     dword ptr [rax+8], 0
0x180003ef9  mov     [rax+10h], rdi
0x180003efd  mov     r15, r9
0x180003f00  mov     rbx, r8
0x180003f03  mov     rsi, rdx
0x180003f06  test    rdx, rdx
0x180003f09  jz      loc_180003FC0
0x180003f0f  test    rbx, rbx
0x180003f12  jz      loc_180003FC0
0x180003f18  test    r9, r9
0x180003f1b  jz      loc_180003FC0
0x180003f21  mov     r14, [rsp+38h+arg_20]
0x180003f26  test    r14, r14
0x180003f29  jz      loc_180003FC0
0x180003f2f  lea     ecx, [rdi+10h]; Size
0x180003f32  mov     [r9], rdi
0x180003f35  mov     [r14], rdi
0x180003f38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f3d  test    rax, rax
0x180003f40  jz      short loc_180003FB9
0x180003f42  mov     rdx, rsi; struct SIP_SUBJECTINFO_ *
0x180003f45  mov     rcx, rax; this
0x180003f48  call    ??0SipCryptProvider@@QEAA@PEBUSIP_SUBJECTINFO_@@@Z; SipCryptProvider::SipCryptProvider(SIP_SUBJECTINFO_ const *)
0x180003f4d  mov     rsi, rax
0x180003f50  test    rax, rax
0x180003f53  jz      short loc_180003FB9
0x180003f55  mov     rdx, [rbx+18h]; char *
0x180003f59  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x180003f5e  call    ?GetAlgId@SipCryptProvider@@QEAAKPEBDPEAK@Z; SipCryptProvider::GetAlgId(char const *,ulong *)
0x180003f63  mov     ebx, eax
0x180003f65  test    eax, eax
0x180003f67  jnz     short loc_180003F92
0x180003f69  mov     edx, [rsp+38h+arg_0]; unsigned int
0x180003f6d  lea     r8, [rsp+38h+arg_8]; struct CryptHash **
0x180003f72  mov     rcx, rsi; struct SipCryptProvider *
0x180003f75  call    ?GetCryptHasher@SipProvider@@CAKPEBVSipCryptProvider@@KPEAPEAVCryptHash@@@Z; SipProvider::GetCryptHasher(SipCryptProvider const *,ulong,CryptHash * *)
0x180003f7a  mov     ebx, eax
0x180003f7c  test    eax, eax
0x180003f7e  jnz     short loc_180003F8D
0x180003f80  mov     rcx, [rsp+38h+arg_8]
0x180003f85  mov     [r14], rcx
0x180003f88  mov     [r15], rsi
0x180003f8b  jmp     short loc_180003FC5
0x180003f8d  mov     rdi, [rsp+38h+arg_8]
0x180003f92  mov     rcx, rsi; this
0x180003f95  call    ??1SipCryptProvider@@QEAA@XZ; SipCryptProvider::~SipCryptProvider(void)
0x180003f9a  mov     rcx, rsi; Block
0x180003f9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003fa2  test    rdi, rdi
0x180003fa5  jz      short loc_180003FC5
0x180003fa7  mov     rcx, rdi; this
0x180003faa  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x180003faf  mov     rcx, rdi; Block
0x180003fb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003fb7  jmp     short loc_180003FC5
0x180003fb9  mov     ebx, 8
0x180003fbe  jmp     short loc_180003FC5
0x180003fc0  mov     ebx, 57h ; 'W'
0x180003fc5  mov     rsi, [rsp+38h+arg_18]
0x180003fca  mov     eax, ebx
0x180003fcc  mov     rbx, [rsp+38h+arg_10]
0x180003fd1  add     rsp, 20h
0x180003fd5  pop     r15
0x180003fd7  pop     r14
0x180003fd9  pop     rdi
0x180003fda  retn
```
