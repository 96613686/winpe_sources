# SipProvider::GetHashSize(SIP_SUBJECTINFO_ const *,ulong *)

- ea: `0x1800042ec`
- end: `0x1800043c8`
- name: `?GetHashSize@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEAK@Z`
- size: `220`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800037bc`

## callees

- `0x180001008`
- `0x180003348`
- `0x180003374`
- `0x180003dd4`
- `0x18000409c`
- `0x1800042ec`
- `0x1800054ae`
- `0x1800054f0`

## pseudocode

```c
__int64 __fastcall SipProvider::GetHashSize(SipProvider *this, const struct SIP_SUBJECTINFO_ *a2, unsigned int *a3)
{
  CryptHash *v3; // rbx
  unsigned int CryptProviderAndHasher; // edi
  void *v6; // rsi
  CryptHash *v8; // [rsp+20h] [rbp-68h] BYREF
  void *Block; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int8 v10[64]; // [rsp+30h] [rbp-58h] BYREF

  v3 = 0;
  v8 = 0;
  Block = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    CryptProviderAndHasher = SipProvider::GetCryptProviderAndHasher(this, a2, (struct SipCryptProvider **)&Block, &v8);
    if ( CryptProviderAndHasher )
    {
      v3 = v8;
    }
    else
    {
      memset_0(v10, 0, sizeof(v10));
      v3 = v8;
      CryptProviderAndHasher = CryptHash::GetHash(v8, v10, 0x40u, a3);
    }
  }
  else
  {
    CryptProviderAndHasher = 87;
  }
  v6 = Block;
  if ( Block )
  {
    SipCryptProvider::~SipCryptProvider((SipCryptProvider *)Block);
    operator delete(v6);
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
0x1800042ec  mov     r11, rsp
0x1800042ef  mov     [r11+8], rbx
0x1800042f3  mov     [r11+20h], rsi
0x1800042f7  push    rdi
0x1800042f8  sub     rsp, 80h
0x1800042ff  mov     rax, cs:__security_cookie
0x180004306  xor     rax, rsp
0x180004309  mov     [rsp+88h+var_18], rax
0x18000430e  xor     ebx, ebx
0x180004310  mov     rsi, r8
0x180004313  mov     [r11-68h], rbx
0x180004317  mov     [r11-60h], rbx
0x18000431b  test    rdx, rdx
0x18000431e  jz      short loc_180004370
0x180004320  test    r8, r8
0x180004323  jz      short loc_180004370
0x180004325  mov     [r8], ebx
0x180004328  lea     r9, [r11-68h]; struct CryptHash **
0x18000432c  lea     r8, [r11-60h]; struct SipCryptProvider **
0x180004330  call    ?GetCryptProviderAndHasher@SipProvider@@AEAAKPEBUSIP_SUBJECTINFO_@@PEAPEAVSipCryptProvider@@PEAPEAVCryptHash@@@Z; SipProvider::GetCryptProviderAndHasher(SIP_SUBJECTINFO_ const *,SipCryptProvider * *,CryptHash * *)
0x180004335  mov     edi, eax
0x180004337  test    eax, eax
0x180004339  jnz     short loc_180004369
0x18000433b  lea     ebx, [rax+40h]
0x18000433e  xor     edx, edx; Val
0x180004340  mov     r8d, ebx; Size
0x180004343  lea     rcx, [rsp+88h+var_58]; void *
0x180004348  call    memset_0
0x18000434d  mov     r8d, ebx; unsigned int
0x180004350  lea     rdx, [rsp+88h+var_58]; unsigned __int8 *
0x180004355  mov     rbx, [rsp+88h+var_68]
0x18000435a  mov     r9, rsi; unsigned int *
0x18000435d  mov     rcx, rbx; this
0x180004360  call    ?GetHash@CryptHash@@QEAAKPEAEKPEAK@Z; CryptHash::GetHash(uchar *,ulong,ulong *)
0x180004365  mov     edi, eax
0x180004367  jmp     short loc_180004375
0x180004369  mov     rbx, [rsp+88h+var_68]
0x18000436e  jmp     short loc_180004375
0x180004370  mov     edi, 57h ; 'W'
0x180004375  mov     rsi, [rsp+88h+Block]
0x18000437a  test    rsi, rsi
0x18000437d  jz      short loc_18000438F
0x18000437f  mov     rcx, rsi; this
0x180004382  call    ??1SipCryptProvider@@QEAA@XZ; SipCryptProvider::~SipCryptProvider(void)
0x180004387  mov     rcx, rsi; Block
0x18000438a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000438f  test    rbx, rbx
0x180004392  jz      short loc_1800043A4
0x180004394  mov     rcx, rbx; this
0x180004397  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x18000439c  mov     rcx, rbx; Block
0x18000439f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043a4  mov     eax, edi
0x1800043a6  mov     rcx, [rsp+88h+var_18]
0x1800043ab  xor     rcx, rsp; StackCookie
0x1800043ae  call    __security_check_cookie
0x1800043b3  lea     r11, [rsp+88h+var_8]
0x1800043bb  mov     rbx, [r11+10h]
0x1800043bf  mov     rsi, [r11+28h]
0x1800043c3  mov     rsp, r11
0x1800043c6  pop     rdi
0x1800043c7  retn
```
