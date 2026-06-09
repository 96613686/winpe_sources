# SipProvider::VerifySignature(SIP_SUBJECTINFO_ const *,SIP_INDIRECT_DATA_ const *)

- ea: `0x1800050b0`
- end: `0x180005218`
- name: `?VerifySignature@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEBUSIP_INDIRECT_DATA_@@@Z`
- size: `360`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, const struct SIP_INDIRECT_DATA_ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180004d40`

## callees

- `0x180001008`
- `0x180003348`
- `0x180003374`
- `0x180003ed8`
- `0x180004108`
- `0x180004834`
- `0x1800050b0`
- `0x180005496`
- `0x1800054f0`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SipProvider::VerifySignature(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        const struct SIP_INDIRECT_DATA_ *a3)
{
  CryptHash *v3; // rdi
  SipFile *v6; // rax
  struct SipFile *v7; // r14
  unsigned int CryptProviderAndHasher; // ebx
  SipProvider *v9; // rcx
  SipProvider *v10; // rcx
  void *v11; // rsi
  unsigned int v13; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  struct CryptHash *v15; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 Buf1[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  Block = 0;
  v15 = 0;
  if ( a2 && a3 )
  {
    v6 = (SipFile *)(*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 8LL))(this);
    v7 = v6;
    if ( !v6 )
      return 8;
    CryptProviderAndHasher = SipFile::Open(v6, a2, 0);
    if ( !CryptProviderAndHasher )
    {
      CryptProviderAndHasher = SipProvider::GetCryptProviderAndHasher(
                                 v9,
                                 a2,
                                 a3,
                                 (struct SipCryptProvider **)&Block,
                                 &v15);
      if ( CryptProviderAndHasher )
      {
        v3 = v15;
      }
      else
      {
        LODWORD(Size) = 0;
        v3 = v15;
        CryptProviderAndHasher = SipProvider::GetHash(v10, v7, v15, Buf1, v13, (unsigned int *)&Size);
        if ( !CryptProviderAndHasher
          && ((_DWORD)Size != a3->Digest.cbData || memcmp_0(Buf1, a3->Digest.pbData, (unsigned int)Size)) )
        {
          CryptProviderAndHasher = -2146869232;
        }
      }
    }
    (**(void (__fastcall ***)(struct SipFile *, __int64))v7)(v7, 1);
  }
  else
  {
    CryptProviderAndHasher = 87;
  }
  v11 = Block;
  if ( Block )
  {
    SipCryptProvider::~SipCryptProvider((SipCryptProvider *)Block);
    operator delete(v11);
  }
  if ( v3 )
  {
    CryptHash::~CryptHash(v3);
    operator delete(v3);
  }
  return CryptProviderAndHasher;
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp-8+arg_18], rbx
0x1800050b5  push    rbp
0x1800050b6  push    rsi
0x1800050b7  push    rdi
0x1800050b8  push    r14
0x1800050ba  push    r15
0x1800050bc  lea     rbp, [rsp-360h]
0x1800050c4  sub     rsp, 460h
0x1800050cb  mov     rax, cs:__security_cookie
0x1800050d2  xor     rax, rsp
0x1800050d5  mov     [rbp+380h+var_30], rax
0x1800050dc  xor     edi, edi
0x1800050de  mov     [rsp+480h+Block], 0
0x1800050e7  mov     [rsp+480h+var_448], rdi
0x1800050ec  mov     rsi, r8
0x1800050ef  mov     r15, rdx
0x1800050f2  test    rdx, rdx
0x1800050f5  jz      loc_1800051BC
0x1800050fb  test    r8, r8
0x1800050fe  jz      loc_1800051BC
0x180005104  mov     rax, [rcx]
0x180005107  mov     rax, [rax+8]
0x18000510b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005110  mov     r14, rax
0x180005113  test    rax, rax
0x180005116  jnz     short loc_180005120
0x180005118  lea     ebx, [rdi+8]
0x18000511b  jmp     loc_1800051F0
0x180005120  xor     r8d, r8d; bool
0x180005123  mov     rdx, r15; struct SIP_SUBJECTINFO_ *
0x180005126  mov     rcx, r14; this
0x180005129  call    ?Open@SipFile@@QEAAKPEBUSIP_SUBJECTINFO_@@_N@Z; SipFile::Open(SIP_SUBJECTINFO_ const *,bool)
0x18000512e  mov     ebx, eax
0x180005130  test    eax, eax
0x180005132  jnz     short loc_1800051A7
0x180005134  lea     rax, [rsp+480h+var_448]
0x180005139  mov     r8, rsi; struct SIP_INDIRECT_DATA_ *
0x18000513c  lea     r9, [rsp+480h+Block]; struct SipCryptProvider **
0x180005141  mov     [rsp+480h+var_460], rax; unsigned int
0x180005146  mov     rdx, r15; struct SIP_SUBJECTINFO_ *
0x180005149  call    ?GetCryptProviderAndHasher@SipProvider@@AEAAKPEBUSIP_SUBJECTINFO_@@PEBUSIP_INDIRECT_DATA_@@PEAPEAVSipCryptProvider@@PEAPEAVCryptHash@@@Z; SipProvider::GetCryptProviderAndHasher(SIP_SUBJECTINFO_ const *,SIP_INDIRECT_DATA_ const *,SipCryptProvider * *,CryptHash * *)
0x18000514e  mov     ebx, eax
0x180005150  test    eax, eax
0x180005152  jnz     short loc_1800051A2
0x180005154  mov     dword ptr [rsp+480h+Size], edi
0x180005158  lea     rax, [rsp+480h+Size]
0x18000515d  mov     rdi, [rsp+480h+var_448]
0x180005162  lea     r9, [rsp+480h+Buf1]; unsigned __int8 *
0x180005167  mov     r8, rdi; struct CryptHash *
0x18000516a  mov     [rsp+480h+var_458], rax; unsigned int *
0x18000516f  mov     rdx, r14; struct SipFile *
0x180005172  call    ?GetHash@SipProvider@@QEAAKPEAVSipFile@@PEAVCryptHash@@PEAEKPEAK@Z; SipProvider::GetHash(SipFile *,CryptHash *,uchar *,ulong,ulong *)
0x180005177  mov     ebx, eax
0x180005179  test    eax, eax
0x18000517b  jnz     short loc_1800051A7
0x18000517d  mov     eax, dword ptr [rsp+480h+Size]
0x180005181  cmp     eax, [rsi+30h]
0x180005184  jnz     short loc_18000519B
0x180005186  mov     rdx, [rsi+38h]; Buf2
0x18000518a  lea     rcx, [rsp+480h+Buf1]; Buf1
0x18000518f  mov     r8d, eax; Size
0x180005192  call    memcmp_0
0x180005197  test    eax, eax
0x180005199  jz      short loc_1800051A7
0x18000519b  mov     ebx, 80096010h
0x1800051a0  jmp     short loc_1800051A7
0x1800051a2  mov     rdi, [rsp+480h+var_448]
0x1800051a7  mov     rax, [r14]
0x1800051aa  mov     edx, 1
0x1800051af  mov     rcx, r14
0x1800051b2  mov     rax, [rax]
0x1800051b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ba  jmp     short loc_1800051C1
0x1800051bc  mov     ebx, 57h ; 'W'
0x1800051c1  mov     rsi, [rsp+480h+Block]
0x1800051c6  test    rsi, rsi
0x1800051c9  jz      short loc_1800051DB
0x1800051cb  mov     rcx, rsi; this
0x1800051ce  call    ??1SipCryptProvider@@QEAA@XZ; SipCryptProvider::~SipCryptProvider(void)
0x1800051d3  mov     rcx, rsi; Block
0x1800051d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051db  test    rdi, rdi
0x1800051de  jz      short loc_1800051F0
0x1800051e0  mov     rcx, rdi; this
0x1800051e3  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x1800051e8  mov     rcx, rdi; Block
0x1800051eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051f0  mov     eax, ebx
0x1800051f2  mov     rcx, [rbp+380h+var_30]
0x1800051f9  xor     rcx, rsp; StackCookie
0x1800051fc  call    __security_check_cookie
0x180005201  mov     rbx, [rsp+480h+arg_18]
0x180005209  add     rsp, 460h
0x180005210  pop     r15
0x180005212  pop     r14
0x180005214  pop     rdi
0x180005215  pop     rsi
0x180005216  pop     rbp
0x180005217  retn
```
