# SipProvider::GetCryptProviderAndHasher(SIP_SUBJECTINFO_ const *,SipCryptProvider * *,CryptHash * *)

- ea: `0x180003dd4`
- end: `0x180003ecf`
- name: `?GetCryptProviderAndHasher@SipProvider@@AEAAKPEBUSIP_SUBJECTINFO_@@PEAPEAVSipCryptProvider@@PEAPEAVCryptHash@@@Z`
- size: `251`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, struct SipCryptProvider **, struct CryptHash **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180004220`
- `0x1800042ec`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800032e8`
- `0x180003348`
- `0x180003374`
- `0x180003ba0`
- `0x180003d50`
- `0x180003dd4`

## pseudocode

```c
__int64 __fastcall SipProvider::GetCryptProviderAndHasher(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        struct SipCryptProvider **a3,
        struct CryptHash **a4)
{
  CryptHash *v4; // rsi
  unsigned int AlgId; // ebx
  SipCryptProvider *v9; // rax
  SipCryptProvider *v10; // rcx
  const struct SipCryptProvider *v11; // rdi
  unsigned int v13; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+44h] [rbp+Ch]
  struct CryptHash *v15; // [rsp+50h] [rbp+18h] BYREF

  v14 = HIDWORD(this);
  v4 = 0;
  v13 = 0;
  v15 = 0;
  if ( a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    if ( !a2 )
      return 87;
    v9 = (SipCryptProvider *)operator new(0x10u);
    if ( !v9 )
      return 8;
    v11 = SipCryptProvider::SipCryptProvider(v9, a2);
    if ( !v11 )
      return 8;
    AlgId = SipCryptProvider::GetAlgId(v10, a2->DigestAlgorithm.pszObjId, &v13);
    if ( !AlgId )
    {
      AlgId = SipProvider::GetCryptHasher(v11, v13, &v15);
      if ( !AlgId )
      {
        *a4 = v15;
        *a3 = v11;
        return AlgId;
      }
      v4 = v15;
    }
    SipCryptProvider::~SipCryptProvider(v11);
    operator delete(v11);
  }
  else
  {
    AlgId = 87;
  }
  if ( v4 )
  {
    CryptHash::~CryptHash(v4);
    operator delete(v4);
  }
  return AlgId;
}

```

## disassembly

```asm
0x180003dd4  mov     rax, rsp
0x180003dd7  mov     [rax+10h], rbx
0x180003ddb  mov     [rax+20h], rsi
0x180003ddf  mov     [rax+8], rcx
0x180003de3  push    rdi
0x180003de4  push    r14
0x180003de6  push    r15
0x180003de8  sub     rsp, 20h
0x180003dec  xor     esi, esi
0x180003dee  mov     dword ptr [rax+8], 0
0x180003df5  mov     [rax+18h], rsi
0x180003df9  mov     r14, r9
0x180003dfc  mov     r15, r8
0x180003dff  mov     rbx, rdx
0x180003e02  test    r8, r8
0x180003e05  jz      loc_180003E9F
0x180003e0b  test    r9, r9
0x180003e0e  jz      loc_180003E9F
0x180003e14  mov     [r8], rsi
0x180003e17  mov     [r9], rsi
0x180003e1a  test    rdx, rdx
0x180003e1d  jnz     short loc_180003E27
0x180003e1f  lea     ebx, [rdx+57h]
0x180003e22  jmp     loc_180003EB9
0x180003e27  mov     ecx, 10h; Size
0x180003e2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e31  test    rax, rax
0x180003e34  jz      short loc_180003E98
0x180003e36  mov     rdx, rbx; struct SIP_SUBJECTINFO_ *
0x180003e39  mov     rcx, rax; this
0x180003e3c  call    ??0SipCryptProvider@@QEAA@PEBUSIP_SUBJECTINFO_@@@Z; SipCryptProvider::SipCryptProvider(SIP_SUBJECTINFO_ const *)
0x180003e41  mov     rdi, rax
0x180003e44  test    rax, rax
0x180003e47  jz      short loc_180003E98
0x180003e49  mov     rdx, [rbx+38h]; char *
0x180003e4d  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x180003e52  call    ?GetAlgId@SipCryptProvider@@QEAAKPEBDPEAK@Z; SipCryptProvider::GetAlgId(char const *,ulong *)
0x180003e57  mov     ebx, eax
0x180003e59  test    eax, eax
0x180003e5b  jnz     short loc_180003E86
0x180003e5d  mov     edx, [rsp+38h+arg_0]; unsigned int
0x180003e61  lea     r8, [rsp+38h+arg_10]; struct CryptHash **
0x180003e66  mov     rcx, rdi; struct SipCryptProvider *
0x180003e69  call    ?GetCryptHasher@SipProvider@@CAKPEBVSipCryptProvider@@KPEAPEAVCryptHash@@@Z; SipProvider::GetCryptHasher(SipCryptProvider const *,ulong,CryptHash * *)
0x180003e6e  mov     ebx, eax
0x180003e70  test    eax, eax
0x180003e72  jnz     short loc_180003E81
0x180003e74  mov     rax, [rsp+38h+arg_10]
0x180003e79  mov     [r14], rax
0x180003e7c  mov     [r15], rdi
0x180003e7f  jmp     short loc_180003EB9
0x180003e81  mov     rsi, [rsp+38h+arg_10]
0x180003e86  mov     rcx, rdi; this
0x180003e89  call    ??1SipCryptProvider@@QEAA@XZ; SipCryptProvider::~SipCryptProvider(void)
0x180003e8e  mov     rcx, rdi; Block
0x180003e91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003e96  jmp     short loc_180003EA4
0x180003e98  mov     ebx, 8
0x180003e9d  jmp     short loc_180003EB9
0x180003e9f  mov     ebx, 57h ; 'W'
0x180003ea4  test    rsi, rsi
0x180003ea7  jz      short loc_180003EB9
0x180003ea9  mov     rcx, rsi; this
0x180003eac  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x180003eb1  mov     rcx, rsi; Block
0x180003eb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003eb9  mov     rsi, [rsp+38h+arg_18]
0x180003ebe  mov     eax, ebx
0x180003ec0  mov     rbx, [rsp+38h+arg_8]
0x180003ec5  add     rsp, 20h
0x180003ec9  pop     r15
0x180003ecb  pop     r14
0x180003ecd  pop     rdi
0x180003ece  retn
```
