# PersistXmlStore::ReadXml(void)

- ea: `0x1800371c8`
- end: `0x18003746b`
- name: `?ReadXml@PersistXmlStore@@AEAAJXZ`
- size: `675`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180036338`

## callees

- `0x180006090`
- `0x18001974c`
- `0x180035c24`
- `0x180035f9c`
- `0x180036a74`
- `0x180036dc0`
- `0x1800371c8`
- `0x180037e8c`
- `0x18003b010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180037258`
- `XmlLite!CreateXmlReader` at `0x180037258`
- `DMCmnUtils!InvStrCmpW` at `0x18003737f`
- `DMCmnUtils!InvStrCmpW` at `0x18003737f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistXmlStore::ReadXml(PersistXmlStore *this)
{
  PersistObject *v2; // rsi
  char *v3; // r14
  const unsigned __int16 *v4; // rcx
  struct IStream *FileStream; // r15
  HRESULT AttributeAsDword; // edi
  void *v7; // rax
  unsigned int v8; // r14d
  PersistObject *v9; // rax
  PersistObject **v10; // rdx
  int v12; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+10h] BYREF
  void *ppvObject; // [rsp+70h] [rbp+18h] BYREF
  const unsigned __int16 *v15; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  v2 = 0;
  v15 = 0;
  ppvObject = 0;
  v3 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) <= 7u )
    v4 = (const unsigned __int16 *)((char *)this + 8);
  else
    v4 = *(const unsigned __int16 **)v3;
  FileStream = CreateFileStream(v4, 0);
  if ( FileStream )
    goto LABEL_10;
  AttributeAsDword = PersistXmlStore::InitializePersistXml(this);
  if ( AttributeAsDword < 0 )
    goto LABEL_15;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  FileStream = CreateFileStream((const unsigned __int16 *)v3, 0);
  if ( FileStream )
  {
LABEL_10:
    AttributeAsDword = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    if ( AttributeAsDword >= 0 )
    {
      AttributeAsDword = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      if ( AttributeAsDword >= 0 )
      {
        AttributeAsDword = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(
                             ppvObject,
                             FileStream);
        if ( AttributeAsDword >= 0 )
        {
          v7 = ppvObject;
          ppvObject = 0;
          *((_QWORD *)this + 10) = v7;
        }
      }
    }
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)FileStream + 16LL))(FileStream);
  }
  else
  {
    AttributeAsDword = -2147024882;
  }
LABEL_15:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( AttributeAsDword >= 0 )
  {
    AttributeAsDword = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 10) + 48LL))(
                         *((_QWORD *)this + 10),
                         &v12);
    if ( AttributeAsDword >= 0 )
    {
      v8 = 0;
      AttributeAsDword = PersistXmlStore::GetAttributeAsDword(this, L"count", &v13);
      if ( AttributeAsDword >= 0 )
      {
        while ( !(*(unsigned int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 10) + 48LL))(
                   *((_QWORD *)this + 10),
                   &v12)
             && v8 < v13 )
        {
          if ( v12 == 1 )
          {
            AttributeAsDword = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD))(**((_QWORD **)this + 10) + 112LL))(
                                 *((_QWORD *)this + 10),
                                 &v15,
                                 0);
            if ( AttributeAsDword < 0 )
              break;
            if ( !InvStrCmpW(v15, L"item")
              && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 160LL))(*((_QWORD *)this + 10)) )
            {
              AttributeAsDword = PersistXmlStore::GetAttributeAsDword(this, L"count", (unsigned int *)&ppvObject);
              if ( AttributeAsDword < 0 )
                break;
              v9 = (PersistObject *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v9 )
                v2 = PersistObject::PersistObject(v9);
              else
                v2 = 0;
              ppvObject = v2;
              if ( !v2 )
              {
                AttributeAsDword = -2147024882;
                break;
              }
              ++v8;
              AttributeAsDword = PersistXmlStore::CreateItemFromElement(this, v2);
              if ( AttributeAsDword < 0 )
                break;
              if ( __eh34_try(-1, 0) )
              {
                __eh34_scope_strut(0);
                v10 = (PersistObject **)*((_QWORD *)this + 12);
                if ( v10 == *((PersistObject ***)this + 13) )
                {
                  std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(
                    (char *)this + 88,
                    v10,
                    &ppvObject);
                }
                else
                {
                  *v10 = v2;
                  *((_QWORD *)this + 12) += 8LL;
                }
                v2 = 0;
                ppvObject = 0;
              }
              if ( __eh34_catch(0) )
              {
                if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                {
                  v13 = -2147024882;
                  AttributeAsDword = -2147024882;
                  v2 = (PersistObject *)ppvObject;
                  __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18003743B);
                  break;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v2 )
    (**(void (__fastcall ***)(PersistObject *, __int64))v2)(v2, 1);
  return (unsigned int)AttributeAsDword;
}

```

## disassembly

```asm
0x1800371c8  mov     rax, rsp
0x1800371cb  push    rsi
0x1800371cc  push    rdi
0x1800371cd  push    r13
0x1800371cf  push    r14
0x1800371d1  push    r15
0x1800371d3  sub     rsp, 30h
0x1800371d7  mov     r13, rcx
0x1800371da  mov     dword ptr [rax+10h], 0
0x1800371e1  mov     dword ptr [rax+8], 0
0x1800371e8  xor     esi, esi
0x1800371ea  mov     [rax+20h], rsi
0x1800371ee  mov     [rax+18h], rsi
0x1800371f2  lea     r14, [rcx+8]
0x1800371f6  cmp     qword ptr [r14+18h], 7
0x1800371fb  jbe     short loc_180037202
0x1800371fd  mov     rcx, [r14]
0x180037200  jmp     short loc_180037205
0x180037202  mov     rcx, r14; unsigned __int16 *
0x180037205  xor     edx, edx; bool
0x180037207  call    ?CreateFileStream@@YAPEAUIStream@@PEBG_N@Z; CreateFileStream(ushort const *,bool)
0x18003720c  mov     r15, rax
0x18003720f  test    rax, rax
0x180037212  jnz     short loc_180037249
0x180037214  mov     rcx, r13; this
0x180037217  call    ?InitializePersistXml@PersistXmlStore@@AEAAJXZ; PersistXmlStore::InitializePersistXml(void)
0x18003721c  mov     edi, eax
0x18003721e  test    eax, eax
0x180037220  js      loc_1800372C3
0x180037226  cmp     qword ptr [r14+18h], 7
0x18003722b  jbe     short loc_180037230
0x18003722d  mov     r14, [r14]
0x180037230  xor     edx, edx; bool
0x180037232  mov     rcx, r14; unsigned __int16 *
0x180037235  call    ?CreateFileStream@@YAPEAUIStream@@PEBG_N@Z; CreateFileStream(ushort const *,bool)
0x18003723a  mov     r15, rax
0x18003723d  test    rax, rax
0x180037240  jnz     short loc_180037249
0x180037242  mov     edi, 8007000Eh
0x180037247  jmp     short loc_1800372C3
0x180037249  xor     r8d, r8d; pMalloc
0x18003724c  lea     rdx, [rsp+58h+ppvObject]; ppvObject
0x180037251  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180037258  call    cs:__imp_CreateXmlReader
0x18003725e  mov     edi, eax
0x180037260  test    eax, eax
0x180037262  js      short loc_1800372B3
0x180037264  mov     rcx, [rsp+58h+ppvObject]
0x180037269  mov     rax, [rcx]
0x18003726c  xor     r8d, r8d
0x18003726f  lea     edx, [r8+4]
0x180037273  mov     rax, [rax+28h]
0x180037277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003727c  mov     edi, eax
0x18003727e  test    eax, eax
0x180037280  js      short loc_1800372AE
0x180037282  mov     rcx, [rsp+58h+ppvObject]
0x180037287  mov     rax, [rcx]
0x18003728a  mov     rdx, r15
0x18003728d  mov     rax, [rax+18h]
0x180037291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037296  mov     edi, eax
0x180037298  test    eax, eax
0x18003729a  js      short loc_1800372AE
0x18003729c  mov     rax, [rsp+58h+ppvObject]
0x1800372a1  mov     [rsp+58h+ppvObject], 0
0x1800372aa  mov     [r13+50h], rax
0x1800372ae  test    r15, r15
0x1800372b1  jz      short loc_1800372C3
0x1800372b3  mov     rax, [r15]
0x1800372b6  mov     rcx, r15
0x1800372b9  mov     rax, [rax+10h]
0x1800372bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372c2  nop
0x1800372c3  mov     rcx, [rsp+58h+ppvObject]
0x1800372c8  test    rcx, rcx
0x1800372cb  jz      short loc_1800372DA
0x1800372cd  mov     rax, [rcx]
0x1800372d0  mov     rax, [rax+10h]
0x1800372d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372d9  nop
0x1800372da  test    edi, edi
0x1800372dc  js      loc_180037444
0x1800372e2  mov     rcx, [r13+50h]
0x1800372e6  mov     rax, [rcx]
0x1800372e9  lea     rdx, [rsp+58h+arg_0]
0x1800372ee  mov     rax, [rax+30h]
0x1800372f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372f7  mov     edi, eax
0x1800372f9  test    eax, eax
0x1800372fb  js      loc_180037444
0x180037301  xor     r14d, r14d
0x180037304  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x180037309  lea     rdx, aCount; "count"
0x180037310  mov     rcx, r13; this
0x180037313  call    ?GetAttributeAsDword@PersistXmlStore@@AEAAJPEBGPEAK@Z; PersistXmlStore::GetAttributeAsDword(ushort const *,ulong *)
0x180037318  mov     edi, eax
0x18003731a  test    eax, eax
0x18003731c  js      loc_180037444
0x180037322  mov     rcx, [r13+50h]
0x180037326  mov     rax, [rcx]
0x180037329  lea     rdx, [rsp+58h+arg_0]
0x18003732e  mov     rax, [rax+30h]
0x180037332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037337  test    eax, eax
0x180037339  jnz     loc_180037444
0x18003733f  cmp     r14d, [rsp+58h+arg_8]
0x180037344  jnb     loc_180037444
0x18003734a  cmp     [rsp+58h+arg_0], 1
0x18003734f  jnz     short loc_180037322
0x180037351  mov     rcx, [r13+50h]
0x180037355  mov     rax, [rcx]
0x180037358  xor     r8d, r8d
0x18003735b  lea     rdx, [rsp+58h+arg_18]
0x180037360  mov     rax, [rax+70h]
0x180037364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037369  mov     edi, eax
0x18003736b  test    eax, eax
0x18003736d  js      loc_180037444
0x180037373  lea     rdx, aItem; "item"
0x18003737a  mov     rcx, [rsp+58h+arg_18]
0x18003737f  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180037385  test    eax, eax
0x180037387  jnz     short loc_180037322
0x180037389  mov     rcx, [r13+50h]
0x18003738d  mov     rax, [rcx]
0x180037390  mov     rax, [rax+0A0h]
0x180037397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003739c  test    eax, eax
0x18003739e  jnz     short loc_180037322
0x1800373a0  lea     r8, [rsp+58h+ppvObject]; unsigned int *
0x1800373a5  lea     rdx, aCount; "count"
0x1800373ac  mov     rcx, r13; this
0x1800373af  call    ?GetAttributeAsDword@PersistXmlStore@@AEAAJPEBGPEAK@Z; PersistXmlStore::GetAttributeAsDword(ushort const *,ulong *)
0x1800373b4  mov     edi, eax
0x1800373b6  test    eax, eax
0x1800373b8  js      loc_180037444
0x1800373be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800373c5  mov     ecx, 60h ; '`'; unsigned __int64
0x1800373ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800373cf  mov     [rsp+58h+var_38], rax
0x1800373d4  test    rax, rax
0x1800373d7  jz      short loc_1800373E6
0x1800373d9  mov     rcx, rax; this
0x1800373dc  call    ??0PersistObject@@QEAA@XZ; PersistObject::PersistObject(void)
0x1800373e1  mov     rsi, rax
0x1800373e4  jmp     short loc_1800373E8
0x1800373e6  xor     esi, esi
0x1800373e8  mov     [rsp+58h+ppvObject], rsi
0x1800373ed  test    rsi, rsi
0x1800373f0  jnz     short loc_1800373F9
0x1800373f2  mov     edi, 8007000Eh
0x1800373f7  jmp     short loc_180037444
0x1800373f9  inc     r14d
0x1800373fc  mov     rdx, rsi; struct PersistObject *
0x1800373ff  mov     rcx, r13; this
0x180037402  call    ?CreateItemFromElement@PersistXmlStore@@AEAAJPEAVPersistObject@@@Z; PersistXmlStore::CreateItemFromElement(PersistObject *)
0x180037407  mov     edi, eax
0x180037409  test    eax, eax
0x18003740b  js      short loc_180037444
0x18003740d  lea     rcx, [r13+58h]
0x180037411  mov     rdx, [rcx+8]
0x180037415  cmp     rdx, [rcx+10h]
0x180037419  jz      short loc_180037425
0x18003741b  mov     [rdx], rsi
0x18003741e  add     qword ptr [rcx+8], 8
0x180037423  jmp     short loc_18003742F
0x180037425  lea     r8, [rsp+58h+ppvObject]
0x18003742a  call    ??$_Emplace_reallocate@AEBQEAVPersistObject@@@?$vector@PEAVPersistObject@@V?$allocator@PEAVPersistObject@@@std@@@std@@AEAAPEAPEAVPersistObject@@QEAPEAV2@AEBQEAV2@@Z; std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(PersistObject * * const,PersistObject * const &)
0x18003742f  xor     esi, esi
0x180037431  mov     [rsp+58h+ppvObject], rsi
0x180037436  jmp     loc_180037322
0x18003743b  mov     edi, [rsp+58h+arg_8]
0x18003743f  mov     rsi, [rsp+58h+ppvObject]
0x180037444  test    rsi, rsi
0x180037447  jz      short loc_18003745C
0x180037449  mov     rax, [rsi]
0x18003744c  mov     edx, 1
0x180037451  mov     rcx, rsi
0x180037454  mov     rax, [rax]
0x180037457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003745c  mov     eax, edi
0x18003745e  add     rsp, 30h
0x180037462  pop     r15
0x180037464  pop     r14
0x180037466  pop     r13
0x180037468  pop     rdi
0x180037469  pop     rsi
0x18003746a  retn
```
