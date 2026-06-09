# SipProvider::GetHash(SipFile *,SIP_SUBJECTINFO_ const *,uchar *,ulong,ulong *)

- ea: `0x180004220`
- end: `0x1800042e3`
- name: `?GetHash@SipProvider@@QEAAKPEAVSipFile@@PEBUSIP_SUBJECTINFO_@@PEAEKPEAK@Z`
- size: `195`
- prototype: `unsigned int(SipProvider *__hidden this, struct SipFile *, const struct SIP_SUBJECTINFO_ *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800037bc`

## callees

- `0x180001008`
- `0x180003348`
- `0x180003374`
- `0x180003dd4`
- `0x180004108`
- `0x180004220`

## pseudocode

```c
__int64 __fastcall SipProvider::GetHash(
        SipProvider *this,
        struct SipFile *a2,
        const struct SIP_SUBJECTINFO_ *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  CryptHash *v6; // rbx
  unsigned int *v9; // rsi
  unsigned int CryptProviderAndHasher; // eax
  SipProvider *v11; // rcx
  unsigned int Hash; // edi
  SipCryptProvider *v13; // rbx
  unsigned int v15; // [rsp+20h] [rbp-28h]
  void *Block; // [rsp+50h] [rbp+8h] BYREF
  SipCryptProvider *v17; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  Block = 0;
  v17 = 0;
  if ( a2 && a3 && a4 && (v9 = a6) != 0 )
  {
    *a4 = 0;
    *v9 = 0;
    CryptProviderAndHasher = SipProvider::GetCryptProviderAndHasher(this, a3, &v17, (struct CryptHash **)&Block);
    v6 = (CryptHash *)Block;
    Hash = CryptProviderAndHasher;
    if ( !CryptProviderAndHasher )
      Hash = SipProvider::GetHash(v11, a2, (HCRYPTHASH *)Block, a4, v15, v9);
  }
  else
  {
    Hash = 87;
  }
  if ( v6 )
  {
    CryptHash::~CryptHash(v6);
    operator delete(v6);
  }
  v13 = v17;
  if ( v17 )
  {
    SipCryptProvider::~SipCryptProvider(v17);
    operator delete(v13);
  }
  return Hash;
}

```

## disassembly

```asm
0x180004220  mov     r11, rsp
0x180004223  mov     [r11+18h], rbx
0x180004227  mov     [r11+20h], rbp
0x18000422b  mov     [r11+8], rcx
0x18000422f  push    rsi
0x180004230  push    rdi
0x180004231  push    r14
0x180004233  sub     rsp, 30h
0x180004237  xor     ebx, ebx
0x180004239  mov     r14, r9
0x18000423c  mov     [r11+8], rbx
0x180004240  mov     rax, r8
0x180004243  mov     [r11+10h], rbx
0x180004247  mov     rbp, rdx
0x18000424a  test    rdx, rdx
0x18000424d  jz      short loc_18000429A
0x18000424f  test    rax, rax
0x180004252  jz      short loc_18000429A
0x180004254  test    r9, r9
0x180004257  jz      short loc_18000429A
0x180004259  mov     rsi, [rsp+48h+arg_28]
0x18000425e  test    rsi, rsi
0x180004261  jz      short loc_18000429A
0x180004263  mov     [r9], bl
0x180004266  lea     r8, [r11+10h]; struct SipCryptProvider **
0x18000426a  lea     r9, [r11+8]; struct CryptHash **
0x18000426e  mov     [rsi], ebx
0x180004270  mov     rdx, rax; struct SIP_SUBJECTINFO_ *
0x180004273  call    ?GetCryptProviderAndHasher@SipProvider@@AEAAKPEBUSIP_SUBJECTINFO_@@PEAPEAVSipCryptProvider@@PEAPEAVCryptHash@@@Z; SipProvider::GetCryptProviderAndHasher(SIP_SUBJECTINFO_ const *,SipCryptProvider * *,CryptHash * *)
0x180004278  mov     rbx, [rsp+48h+Block]
0x18000427d  mov     edi, eax
0x18000427f  test    eax, eax
0x180004281  jnz     short loc_18000429F
0x180004283  mov     r9, r14; unsigned __int8 *
0x180004286  mov     [rsp+48h+var_20], rsi; unsigned int *
0x18000428b  mov     r8, rbx; struct CryptHash *
0x18000428e  mov     rdx, rbp; struct SipFile *
0x180004291  call    ?GetHash@SipProvider@@QEAAKPEAVSipFile@@PEAVCryptHash@@PEAEKPEAK@Z; SipProvider::GetHash(SipFile *,CryptHash *,uchar *,ulong,ulong *)
0x180004296  mov     edi, eax
0x180004298  jmp     short loc_18000429F
0x18000429a  mov     edi, 57h ; 'W'
0x18000429f  test    rbx, rbx
0x1800042a2  jz      short loc_1800042B4
0x1800042a4  mov     rcx, rbx; this
0x1800042a7  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x1800042ac  mov     rcx, rbx; Block
0x1800042af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042b4  mov     rbx, [rsp+48h+arg_8]
0x1800042b9  test    rbx, rbx
0x1800042bc  jz      short loc_1800042CE
0x1800042be  mov     rcx, rbx; this
0x1800042c1  call    ??1SipCryptProvider@@QEAA@XZ; SipCryptProvider::~SipCryptProvider(void)
0x1800042c6  mov     rcx, rbx; Block
0x1800042c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042ce  mov     rbx, [rsp+48h+arg_10]
0x1800042d3  mov     eax, edi
0x1800042d5  mov     rbp, [rsp+48h+arg_18]
0x1800042da  add     rsp, 30h
0x1800042de  pop     r14
0x1800042e0  pop     rdi
0x1800042e1  pop     rsi
0x1800042e2  retn
```
