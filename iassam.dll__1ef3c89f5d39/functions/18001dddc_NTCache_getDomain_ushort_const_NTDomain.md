# NTCache::getDomain(ushort const *,NTDomain * *)

- ea: `0x18001dddc`
- end: `0x18001df36`
- name: `?getDomain@NTCache@@QEAAKPEBGPEAPEAVNTDomain@@@Z`
- size: `346`
- prototype: `unsigned int(NTCache *__hidden this, const unsigned __int16 *, struct NTDomain **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001d04c`
- `0x18001df3c`

## callees

- `0x1800033bc`
- `0x18001dd28`
- `0x18001dddc`
- `0x18001dfe0`
- `0x18001e030`
- `0x18001f708`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001df1b`
- `KERNEL32!LeaveCriticalSection` at `0x18001df1b`
- `KERNEL32!EnterCriticalSection` at `0x18001de21`
- `KERNEL32!EnterCriticalSection` at `0x18001de21`
- `KERNEL32!TryEnterCriticalSection` at `0x18001de01`
- `KERNEL32!TryEnterCriticalSection` at `0x18001de01`
- `KERNEL32!SwitchToThread` at `0x18001de12`
- `KERNEL32!SwitchToThread` at `0x18001de12`

## pseudocode

```c
__int64 __fastcall NTCache::getDomain(NTCache *this, const unsigned __int16 *a2, struct NTDomain **a3)
{
  struct NTDomain **v3; // rbx
  int v5; // edi
  _QWORD *i; // rcx
  char *v7; // rax
  char *v8; // r9
  int v9; // r8d
  int v10; // edx
  volatile signed __int32 *v11; // rax
  NTCache *v12; // rcx
  NTCache *v13; // rax
  _QWORD *bucket; // rdi
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  NTCache *v18; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v19; // [rsp+48h] [rbp+10h] BYREF
  struct NTDomain **v20; // [rsp+50h] [rbp+18h]

  v20 = a3;
  v19 = a2;
  v18 = this;
  v3 = a3;
  v5 = 0;
  while ( !TryEnterCriticalSection(&CriticalSection) )
  {
    if ( ++v5 >= 100 )
    {
      EnterCriticalSection(&CriticalSection);
      break;
    }
    SwitchToThread();
  }
  for ( i = *(_QWORD **)hash_table<unsigned short const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::get_bucket(
                          &qword_1800402C8,
                          &v19); i; i = (_QWORD *)*i )
  {
    v7 = (char *)(i[1] + 48LL);
    if ( *(_QWORD *)(i[1] + 72LL) >= 8u )
      v7 = *(char **)v7;
    v8 = (char *)((char *)a2 - v7);
    do
    {
      v9 = *(unsigned __int16 *)&v8[(_QWORD)v7];
      v10 = *(unsigned __int16 *)v7 - v9;
      if ( v10 )
        break;
      v7 += 2;
    }
    while ( v9 );
    if ( !v10 )
    {
      v11 = (volatile signed __int32 *)i[1];
      *v3 = (struct NTDomain *)v11;
      _InterlockedIncrement(v11 + 10);
      goto LABEL_25;
    }
  }
  *v3 = NTDomain::createInstance(a2);
  NTCache::evict(v12);
  try
  {
    if ( qword_1800402D8 >= (unsigned __int64)qword_1800402C8 )
      hash_table<unsigned short const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::grow(&qword_1800402C8);
    v13 = (struct NTDomain *)((char *)*v3 + 48);
    if ( *((_QWORD *)*v3 + 9) >= 8u )
      v13 = *(NTCache **)v13;
    v18 = v13;
    bucket = (_QWORD *)hash_table<unsigned short const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::get_bucket(
                         &qword_1800402C8,
                         &v18);
    v15 = operator new(0x10u);
    v16 = v15;
    if ( v15 )
      v15[1] = *v3;
    else
      v16 = 0;
    *v16 = *bucket;
    *bucket = v16;
    ++qword_1800402D8;
    _InterlockedIncrement((volatile signed __int32 *)*v3 + 10);
  }
  catch ( ... )
  {
    v3 = v20;
  }
LABEL_25:
  LeaveCriticalSection(&CriticalSection);
  return *v3 == 0 ? 8 : 0;
}

```

## disassembly

```asm
0x18001dddc  mov     [rsp+arg_10], r8
0x18001dde1  mov     [rsp+arg_8], rdx
0x18001dde6  mov     [rsp+arg_0], rcx
0x18001ddeb  push    rbx
0x18001ddec  push    rsi
0x18001dded  push    rdi
0x18001ddee  sub     rsp, 20h
0x18001ddf2  mov     rbx, r8
0x18001ddf5  mov     rsi, rdx
0x18001ddf8  xor     edi, edi
0x18001ddfa  lea     rcx, CriticalSection; lpCriticalSection
0x18001de01  call    cs:__imp_TryEnterCriticalSection
0x18001de07  test    eax, eax
0x18001de09  jnz     short loc_18001DE27
0x18001de0b  inc     edi
0x18001de0d  cmp     edi, 64h ; 'd'
0x18001de10  jge     short loc_18001DE1A
0x18001de12  call    cs:__imp_SwitchToThread
0x18001de18  jmp     short loc_18001DDFA
0x18001de1a  lea     rcx, CriticalSection; lpCriticalSection
0x18001de21  call    cs:__imp_EnterCriticalSection
0x18001de27  lea     rdx, [rsp+38h+arg_8]
0x18001de2c  lea     rdi, qword_1800402C8
0x18001de33  mov     rcx, rdi
0x18001de36  call    ?get_bucket@?$hash_table@PEBGUHasher@NTCache@@PEAVNTDomain@@UExtractor@2@UKeyMatch@2@@@IEBAAEAUSList@1@AEBQEBG@Z; hash_table<ushort const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::get_bucket(ushort const * const &)
0x18001de3b  mov     rcx, [rax]
0x18001de3e  test    rcx, rcx
0x18001de41  jz      short loc_18001DE8A
0x18001de43  mov     rax, [rcx+8]
0x18001de47  add     rax, 30h ; '0'
0x18001de4b  cmp     qword ptr [rax+18h], 8
0x18001de50  jb      short loc_18001DE55
0x18001de52  mov     rax, [rax]
0x18001de55  mov     r9, rsi
0x18001de58  sub     r9, rax
0x18001de5b  movzx   edx, word ptr [rax]
0x18001de5e  movzx   r8d, word ptr [rax+r9]
0x18001de63  sub     edx, r8d
0x18001de66  jnz     short loc_18001DE71
0x18001de68  add     rax, 2
0x18001de6c  test    r8d, r8d
0x18001de6f  jnz     short loc_18001DE5B
0x18001de71  test    edx, edx
0x18001de73  jz      short loc_18001DE7A
0x18001de75  mov     rcx, [rcx]
0x18001de78  jmp     short loc_18001DE3E
0x18001de7a  mov     rax, [rcx+8]
0x18001de7e  mov     [rbx], rax
0x18001de81  lock inc dword ptr [rax+28h]
0x18001de85  jmp     loc_18001DF14
0x18001de8a  mov     rcx, rsi; unsigned __int16 *
0x18001de8d  call    ?createInstance@NTDomain@@SAPEAV1@PEBG@Z; NTDomain::createInstance(ushort const *)
0x18001de92  mov     [rbx], rax
0x18001de95  call    ?evict@NTCache@@IEAAXXZ; NTCache::evict(void)
0x18001de9a  nop
0x18001de9b  mov     rax, cs:qword_1800402C8
0x18001dea2  cmp     cs:qword_1800402D8, rax
0x18001dea9  jb      short loc_18001DEB3
0x18001deab  mov     rcx, rdi
0x18001deae  call    ?grow@?$hash_table@PEBGUHasher@NTCache@@PEAVNTDomain@@UExtractor@2@UKeyMatch@2@@@IEAAXXZ; hash_table<ushort const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::grow(void)
0x18001deb3  mov     rax, [rbx]
0x18001deb6  add     rax, 30h ; '0'
0x18001deba  cmp     qword ptr [rax+18h], 8
0x18001debf  jb      short loc_18001DEC4
0x18001dec1  mov     rax, [rax]
0x18001dec4  mov     [rsp+38h+arg_0], rax
0x18001dec9  lea     rdx, [rsp+38h+arg_0]
0x18001dece  mov     rcx, rdi
0x18001ded1  call    ?get_bucket@?$hash_table@PEBGUHasher@NTCache@@PEAVNTDomain@@UExtractor@2@UKeyMatch@2@@@IEBAAEAUSList@1@AEBQEBG@Z; hash_table<ushort const *,NTCache::Hasher,NTDomain *,NTCache::Extractor,NTCache::KeyMatch>::get_bucket(ushort const * const &)
0x18001ded6  mov     rdi, rax
0x18001ded9  mov     ecx, 10h; Size
0x18001dede  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dee3  mov     rdx, rax
0x18001dee6  test    rax, rax
0x18001dee9  jz      short loc_18001DEF4
0x18001deeb  mov     rcx, [rbx]
0x18001deee  mov     [rax+8], rcx
0x18001def2  jmp     short loc_18001DEF6
0x18001def4  xor     edx, edx
0x18001def6  mov     rax, [rdi]
0x18001def9  mov     [rdx], rax
0x18001defc  mov     [rdi], rdx
0x18001deff  inc     cs:qword_1800402D8
0x18001df06  mov     rax, [rbx]
0x18001df09  lock inc dword ptr [rax+28h]
0x18001df0d  jmp     short loc_18001DF14
0x18001df0f  mov     rbx, [rsp+38h+arg_10]
0x18001df14  lea     rcx, CriticalSection; lpCriticalSection
0x18001df1b  call    cs:__imp_LeaveCriticalSection
0x18001df21  mov     rax, [rbx]
0x18001df24  neg     rax
0x18001df27  sbb     eax, eax
0x18001df29  not     eax
0x18001df2b  and     eax, 8
0x18001df2e  add     rsp, 20h
0x18001df32  pop     rdi
0x18001df33  pop     rsi
0x18001df34  pop     rbx
0x18001df35  retn
```
