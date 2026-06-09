# PersistXmlStore::CreatePersistXmlStore(ushort const *,IPersistStore * *)

- ea: `0x180036338`
- end: `0x1800364e8`
- name: `?CreatePersistXmlStore@PersistXmlStore@@SAJPEBGPEAPEAVIPersistStore@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct IPersistStore **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001478c`
- `0x180015500`
- `0x180016110`

## callees

- `0x180006090`
- `0x1800064ae`
- `0x180010c8c`
- `0x180012314`
- `0x180036338`
- `0x1800371c8`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364a5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364a5`

## pseudocode

```c
__int64 __fastcall PersistXmlStore::CreatePersistXmlStore(const unsigned __int16 *Src, struct IPersistStore **a2)
{
  int v3; // r15d
  char *v5; // rdi
  __int64 v6; // r8
  _QWORD *v7; // rsi
  unsigned __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  char *v12; // rbp
  __int64 v13; // rbx
  int Xml; // ebx

  v3 = 0;
  while ( 1 )
  {
    v5 = (char *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v5 )
      break;
    *(_QWORD *)v5 = &PersistXmlStore::`vftable';
    *(_OWORD *)(v5 + 8) = 0;
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 4) = 7;
    *((_WORD *)v5 + 4) = 0;
    *(_OWORD *)(v5 + 40) = 0;
    *((_QWORD *)v5 + 7) = 0;
    *((_QWORD *)v5 + 8) = 7;
    *((_WORD *)v5 + 20) = 0;
    *((_QWORD *)v5 + 9) = 0;
    *((_QWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 11) = 0;
    *((_QWORD *)v5 + 12) = 0;
    *((_QWORD *)v5 + 13) = 0;
    v7 = v5 + 8;
    v8 = -1;
    do
      ++v8;
    while ( Src[v8] );
    if ( v8 > *((_QWORD *)v5 + 4) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v5 + 8,
        v8,
        v6,
        Src);
    }
    else
    {
      if ( *((_QWORD *)v5 + 4) > 7u )
        v7 = (_QWORD *)*v7;
      v9 = 2 * v8;
      *((_QWORD *)v5 + 3) = v8;
      memmove_0(v7, Src, 2 * v8);
      *(_WORD *)((char *)v7 + v9) = 0;
    }
    v11 = -1;
    do
      ++v11;
    while ( Src[v11] );
    if ( v11 > *((_QWORD *)v5 + 8) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v5 + 40,
        v11,
        v10,
        Src);
    }
    else
    {
      if ( *((_QWORD *)v5 + 8) <= 7u )
        v12 = v5 + 40;
      else
        v12 = (char *)*((_QWORD *)v5 + 5);
      v13 = 2 * v11;
      *((_QWORD *)v5 + 7) = v11;
      memmove_0(v12, Src, 2 * v11);
      *(_WORD *)&v12[v13] = 0;
    }
    std::wstring::append(v5 + 40, L".out");
    Xml = PersistXmlStore::ReadXml((PersistXmlStore *)v5);
    if ( Xml >= 0 )
    {
LABEL_21:
      *a2 = (struct IPersistStore *)v5;
      return (unsigned int)Xml;
    }
    if ( v3 == 2 )
    {
      (**(void (__fastcall ***)(void *, __int64))v5)(v5, 1);
      return (unsigned int)Xml;
    }
    (**(void (__fastcall ***)(void *, __int64))v5)(v5, 1);
    v5 = 0;
    Sleep(0x12Cu);
    if ( (unsigned int)++v3 >= 3 )
      goto LABEL_21;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180036338  push    rbx
0x18003633a  push    rbp
0x18003633b  push    rsi
0x18003633c  push    rdi
0x18003633d  push    r12
0x18003633f  push    r13
0x180036341  push    r14
0x180036343  push    r15
0x180036345  sub     rsp, 28h
0x180036349  xor     r13d, r13d
0x18003634c  mov     r12, rdx
0x18003634f  mov     r15d, r13d
0x180036352  mov     r14, rcx
0x180036355  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003635c  mov     ecx, 70h ; 'p'; unsigned __int64
0x180036361  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036366  mov     [rsp+68h+arg_10], rax
0x18003636e  mov     rdi, rax
0x180036371  test    rax, rax
0x180036374  jz      loc_1800364D0
0x18003637a  lea     rax, ??_7PersistXmlStore@@6B@; const PersistXmlStore::`vftable'
0x180036381  xorps   xmm0, xmm0
0x180036384  mov     [rdi], rax
0x180036387  movups  xmmword ptr [rdi+8], xmm0
0x18003638b  mov     [rdi+18h], r13
0x18003638f  mov     qword ptr [rdi+20h], 7
0x180036397  mov     [rdi+8], r13w
0x18003639c  movups  xmmword ptr [rdi+28h], xmm0
0x1800363a0  mov     [rdi+38h], r13
0x1800363a4  mov     qword ptr [rdi+40h], 7
0x1800363ac  mov     [rdi+28h], r13w
0x1800363b1  mov     [rdi+48h], r13
0x1800363b5  mov     [rdi+50h], r13
0x1800363b9  mov     [rdi+58h], r13
0x1800363bd  mov     [rdi+60h], r13
0x1800363c1  mov     [rdi+68h], r13
0x1800363c5  test    rdi, rdi
0x1800363c8  jz      loc_1800364D0
0x1800363ce  lea     rsi, [rdi+8]
0x1800363d2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800363d6  inc     rdx
0x1800363d9  cmp     [r14+rdx*2], r13w
0x1800363de  jnz     short loc_1800363D6
0x1800363e0  cmp     rdx, [rdi+20h]
0x1800363e4  ja      short loc_18003640D
0x1800363e6  cmp     qword ptr [rdi+20h], 7
0x1800363eb  jbe     short loc_1800363F0
0x1800363ed  mov     rsi, [rsi]
0x1800363f0  lea     rbx, [rdx+rdx]
0x1800363f4  mov     [rdi+18h], rdx
0x1800363f8  mov     r8, rbx; Size
0x1800363fb  mov     rdx, r14; Src
0x1800363fe  mov     rcx, rsi; void *
0x180036401  call    memmove_0
0x180036406  mov     [rbx+rsi], r13w
0x18003640b  jmp     short loc_180036418
0x18003640d  mov     r9, r14
0x180036410  mov     rcx, rsi
0x180036413  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036418  lea     rsi, [rdi+28h]
0x18003641c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180036420  inc     rdx
0x180036423  cmp     [r14+rdx*2], r13w
0x180036428  jnz     short loc_180036420
0x18003642a  cmp     rdx, [rsi+18h]
0x18003642e  ja      short loc_18003645C
0x180036430  cmp     qword ptr [rsi+18h], 7
0x180036435  jbe     short loc_18003643C
0x180036437  mov     rbp, [rsi]
0x18003643a  jmp     short loc_18003643F
0x18003643c  mov     rbp, rsi
0x18003643f  lea     rbx, [rdx+rdx]
0x180036443  mov     [rsi+10h], rdx
0x180036447  mov     r8, rbx; Size
0x18003644a  mov     rdx, r14; Src
0x18003644d  mov     rcx, rbp; void *
0x180036450  call    memmove_0
0x180036455  mov     [rbx+rbp], r13w
0x18003645a  jmp     short loc_180036467
0x18003645c  mov     r9, r14
0x18003645f  mov     rcx, rsi
0x180036462  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036467  lea     rdx, aOut; ".out"
0x18003646e  mov     rcx, rsi; Src
0x180036471  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180036476  mov     rcx, rdi; this
0x180036479  call    ?ReadXml@PersistXmlStore@@AEAAJXZ; PersistXmlStore::ReadXml(void)
0x18003647e  mov     ebx, eax
0x180036480  test    eax, eax
0x180036482  jns     short loc_1800364B8
0x180036484  mov     rcx, rdi
0x180036487  cmp     r15d, 2
0x18003648b  jz      short loc_1800364BE
0x18003648d  mov     rdx, [rdi]
0x180036490  mov     rax, [rdx]
0x180036493  mov     edx, 1
0x180036498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003649d  mov     ecx, 12Ch; dwMilliseconds
0x1800364a2  mov     rdi, r13
0x1800364a5  call    cs:__imp_Sleep
0x1800364ab  inc     r15d
0x1800364ae  cmp     r15d, 3
0x1800364b2  jb      loc_180036355
0x1800364b8  mov     [r12], rdi
0x1800364bc  jmp     short loc_1800364D5
0x1800364be  mov     rax, [rdi]
0x1800364c1  mov     edx, 1
0x1800364c6  mov     rax, [rax]
0x1800364c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364ce  jmp     short loc_1800364D5
0x1800364d0  mov     ebx, 8007000Eh
0x1800364d5  mov     eax, ebx
0x1800364d7  add     rsp, 28h
0x1800364db  pop     r15
0x1800364dd  pop     r14
0x1800364df  pop     r13
0x1800364e1  pop     r12
0x1800364e3  pop     rdi
0x1800364e4  pop     rsi
0x1800364e5  pop     rbp
0x1800364e6  pop     rbx
0x1800364e7  retn
```
