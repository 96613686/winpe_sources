# CXMLReader::LoadMaps(void)

- ea: `0x180027164`
- end: `0x18002731b`
- name: `?LoadMaps@CXMLReader@@AEAAJXZ`
- size: `439`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800257ec`

## callees

- `0x180027164`
- `0x180029528`
- `0x1800295ac`
- `0x180029e94`

## pseudocode

```c
int __fastcall CXMLReader::LoadMaps(CXMLReader *this)
{
  CCollectionList *v1; // rsi
  int result; // eax
  unsigned int v4; // edi
  struct tagDICTENTRY near **v5; // rbx
  unsigned __int16 *v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // edi
  struct tagDICTENTRY near **v9; // rbx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // edi
  struct tagDICTENTRY near **v13; // rbx
  unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edi
  struct tagDICTENTRY near **v17; // rbx
  unsigned __int16 *v18; // rdx
  __int64 v19; // r8

  v1 = (CXMLReader *)((char *)this + 208);
  result = CCollectionList::Reserve((CXMLReader *)((char *)this + 208), 0x1Au);
  if ( result >= 0 )
  {
    v4 = 0;
    v5 = &rgdictColumnAttribs;
    while ( v4 < 0x1A )
    {
      v6 = (unsigned __int16 *)*v5;
      if ( *v5 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
      }
      else
      {
        LODWORD(v7) = 0;
      }
      result = CCollectionList::AppendDup(v1, v6, v7, (unsigned __int64)v5[1]);
      if ( result < 0 )
        return result;
      ++v4;
      v5 += 2;
    }
    result = CCollectionList::Reserve((CXMLReader *)((char *)this + 256), 0xFu);
    if ( result >= 0 )
    {
      v8 = 0;
      v9 = &rgdictRowsetAttribs;
      while ( v8 < 0xF )
      {
        v10 = (unsigned __int16 *)*v9;
        if ( *v9 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
        }
        else
        {
          LODWORD(v11) = 0;
        }
        result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 256), v10, v11, (unsigned __int64)v9[1]);
        if ( result < 0 )
          return result;
        ++v8;
        v9 += 2;
      }
      result = CCollectionList::Reserve((CXMLReader *)((char *)this + 352), 0xAu);
      if ( result >= 0 )
      {
        v12 = 0;
        v13 = &rgdictFlags;
        while ( v12 < 0xA )
        {
          v14 = (unsigned __int16 *)*v13;
          if ( *v13 )
          {
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
          }
          else
          {
            LODWORD(v15) = 0;
          }
          result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 352), v14, v15, (unsigned __int64)v13[1]);
          if ( result < 0 )
            return result;
          ++v12;
          v13 += 2;
        }
        result = CCollectionList::Reserve((CXMLReader *)((char *)this + 304), 0x1Fu);
        if ( result >= 0 )
        {
          v16 = 0;
          v17 = &rgdictTypes;
          while ( v16 < 0x1F )
          {
            v18 = (unsigned __int16 *)*v17;
            if ( *v17 )
            {
              v19 = -1;
              do
                ++v19;
              while ( v18[v19] );
            }
            else
            {
              LODWORD(v19) = 0;
            }
            result = CCollectionList::AppendDup((CXMLReader *)((char *)this + 304), v18, v19, (unsigned __int64)v17[1]);
            if ( result < 0 )
              return result;
            ++v16;
            v17 += 2;
          }
          return CCollectionList::Append((CXMLReader *)((char *)this + 160), L"xml", 3u, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027164  push    rbx
0x180027166  push    rbp
0x180027167  push    rsi
0x180027168  push    rdi
0x180027169  push    r14
0x18002716b  push    r15
0x18002716d  sub     rsp, 28h
0x180027171  lea     rsi, [rcx+0D0h]
0x180027178  mov     rbp, rcx
0x18002717b  mov     rcx, rsi; this
0x18002717e  mov     edx, 1Ah; unsigned int
0x180027183  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180027188  xor     r14d, r14d
0x18002718b  test    eax, eax
0x18002718d  js      loc_18002730D
0x180027193  mov     edi, r14d
0x180027196  lea     rbx, ?rgdictColumnAttribs@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictColumnAttribs
0x18002719d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800271a1  cmp     edi, 1Ah
0x1800271a4  jnb     short loc_1800271DC
0x1800271a6  mov     rdx, [rbx]; unsigned __int16 *
0x1800271a9  test    rdx, rdx
0x1800271ac  jz      short loc_1800271BD
0x1800271ae  mov     r8, r15
0x1800271b1  inc     r8
0x1800271b4  cmp     [rdx+r8*2], r14w
0x1800271b9  jnz     short loc_1800271B1
0x1800271bb  jmp     short loc_1800271C0
0x1800271bd  mov     r8, r14; unsigned int
0x1800271c0  mov     r9, [rbx+8]; unsigned __int64
0x1800271c4  mov     rcx, rsi; this
0x1800271c7  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x1800271cc  test    eax, eax
0x1800271ce  js      loc_18002730D
0x1800271d4  inc     edi
0x1800271d6  add     rbx, 10h
0x1800271da  jmp     short loc_1800271A1
0x1800271dc  lea     rsi, [rbp+100h]
0x1800271e3  mov     edx, 0Fh; unsigned int
0x1800271e8  mov     rcx, rsi; this
0x1800271eb  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800271f0  test    eax, eax
0x1800271f2  js      loc_18002730D
0x1800271f8  mov     edi, r14d
0x1800271fb  lea     rbx, ?rgdictRowsetAttribs@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictRowsetAttribs
0x180027202  cmp     edi, 0Fh
0x180027205  jnb     short loc_18002723D
0x180027207  mov     rdx, [rbx]; unsigned __int16 *
0x18002720a  test    rdx, rdx
0x18002720d  jz      short loc_18002721E
0x18002720f  mov     r8, r15
0x180027212  inc     r8
0x180027215  cmp     [rdx+r8*2], r14w
0x18002721a  jnz     short loc_180027212
0x18002721c  jmp     short loc_180027221
0x18002721e  mov     r8, r14; unsigned int
0x180027221  mov     r9, [rbx+8]; unsigned __int64
0x180027225  mov     rcx, rsi; this
0x180027228  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x18002722d  test    eax, eax
0x18002722f  js      loc_18002730D
0x180027235  inc     edi
0x180027237  add     rbx, 10h
0x18002723b  jmp     short loc_180027202
0x18002723d  lea     rsi, [rbp+160h]
0x180027244  mov     edx, 0Ah; unsigned int
0x180027249  mov     rcx, rsi; this
0x18002724c  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x180027251  test    eax, eax
0x180027253  js      loc_18002730D
0x180027259  mov     edi, r14d
0x18002725c  lea     rbx, ?rgdictFlags@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictFlags
0x180027263  cmp     edi, 0Ah
0x180027266  jnb     short loc_18002729A
0x180027268  mov     rdx, [rbx]; unsigned __int16 *
0x18002726b  test    rdx, rdx
0x18002726e  jz      short loc_18002727F
0x180027270  mov     r8, r15
0x180027273  inc     r8
0x180027276  cmp     [rdx+r8*2], r14w
0x18002727b  jnz     short loc_180027273
0x18002727d  jmp     short loc_180027282
0x18002727f  mov     r8, r14; unsigned int
0x180027282  mov     r9, [rbx+8]; unsigned __int64
0x180027286  mov     rcx, rsi; this
0x180027289  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x18002728e  test    eax, eax
0x180027290  js      short loc_18002730D
0x180027292  inc     edi
0x180027294  add     rbx, 10h
0x180027298  jmp     short loc_180027263
0x18002729a  lea     rsi, [rbp+130h]
0x1800272a1  mov     edx, 1Fh; unsigned int
0x1800272a6  mov     rcx, rsi; this
0x1800272a9  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x1800272ae  test    eax, eax
0x1800272b0  js      short loc_18002730D
0x1800272b2  mov     edi, r14d
0x1800272b5  lea     rbx, ?rgdictTypes@@3PAUtagDICTENTRY@@A; tagDICTENTRY near * rgdictTypes
0x1800272bc  cmp     edi, 1Fh
0x1800272bf  jnb     short loc_1800272F3
0x1800272c1  mov     rdx, [rbx]; unsigned __int16 *
0x1800272c4  test    rdx, rdx
0x1800272c7  jz      short loc_1800272D8
0x1800272c9  mov     r8, r15
0x1800272cc  inc     r8
0x1800272cf  cmp     [rdx+r8*2], r14w
0x1800272d4  jnz     short loc_1800272CC
0x1800272d6  jmp     short loc_1800272DB
0x1800272d8  mov     r8, r14; unsigned int
0x1800272db  mov     r9, [rbx+8]; unsigned __int64
0x1800272df  mov     rcx, rsi; this
0x1800272e2  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x1800272e7  test    eax, eax
0x1800272e9  js      short loc_18002730D
0x1800272eb  inc     edi
0x1800272ed  add     rbx, 10h
0x1800272f1  jmp     short loc_1800272BC
0x1800272f3  xor     r9d, r9d; unsigned __int64
0x1800272f6  lea     rcx, [rbp+0A0h]; this
0x1800272fd  lea     rdx, aXml; "xml"
0x180027304  lea     r8d, [r9+3]; unsigned int
0x180027308  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x18002730d  add     rsp, 28h
0x180027311  pop     r15
0x180027313  pop     r14
0x180027315  pop     rdi
0x180027316  pop     rsi
0x180027317  pop     rbp
0x180027318  pop     rbx
0x180027319  retn
```
