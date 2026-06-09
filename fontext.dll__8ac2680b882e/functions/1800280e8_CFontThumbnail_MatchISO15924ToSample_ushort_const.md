# CFontThumbnail::_MatchISO15924ToSample(ushort const *)

- ea: `0x1800280e8`
- end: `0x18002818f`
- name: `?_MatchISO15924ToSample@CFontThumbnail@@AEAAHPEBG@Z`
- size: `167`
- prototype: `int(CFontThumbnail *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800278dc`
- `0x180027b60`

## callees

- `0x1800280e8`

## import_xrefs

- `msvcrt!bsearch_s` at `0x18002814a`
- `msvcrt!bsearch_s` at `0x18002814a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028119`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028119`

## pseudocode

```c
__int64 __fastcall CFontThumbnail::_MatchISO15924ToSample(CFontThumbnail *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  _BYTE *v4; // rax
  __int64 v5; // rax

  v2 = -1;
  if ( *a2 )
  {
    if ( CompareStringOrdinal(a2, -1, L"LATN", -1, 1) != 2 )
    {
      v4 = bsearch_s(a2, &_pszSampleIds, 0x44u, 8u, (_CoreCrtSecureSearchSortCompareFunction)CompareISO15924Tags, 0);
      if ( v4 )
      {
        v5 = (v4 - (_BYTE *)&_pszSampleIds) >> 3;
        if ( (unsigned __int64)(v5 + 0x80000000LL) <= 0xFFFFFFFF && (unsigned int)v5 < 0x44 )
          return *((unsigned __int8 *)&_bSampleIds + (int)v5);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800280e8  push    rbx
0x1800280ea  push    rbp
0x1800280eb  push    rsi
0x1800280ec  push    rdi
0x1800280ed  sub     rsp, 38h
0x1800280f1  or      ebx, 0FFFFFFFFh
0x1800280f4  xor     esi, esi
0x1800280f6  mov     rdi, rdx
0x1800280f9  cmp     [rdx], si
0x1800280fc  jz      loc_180028184
0x180028102  mov     r9d, ebx; cchCount2
0x180028105  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18002810d  lea     r8, aLatn; "LATN"
0x180028114  mov     edx, ebx; cchCount1
0x180028116  mov     rcx, rdi; lpString1
0x180028119  call    cs:__imp_CompareStringOrdinal
0x18002811f  cmp     eax, 2
0x180028122  jz      short loc_180028184
0x180028124  lea     rax, ?CompareISO15924Tags@@YAHPEAXPEBGPEAPEBG@Z; CompareISO15924Tags(void *,ushort const *,ushort const * *)
0x18002812b  mov     [rsp+58h+Context], rsi; Context
0x180028130  lea     rbp, ?_pszSampleIds@@3PAPEAGA; ushort * near * _pszSampleIds
0x180028137  mov     qword ptr [rsp+58h+bIgnoreCase], rax; CompareFunction
0x18002813c  mov     rdx, rbp; Base
0x18002813f  lea     r9d, [rbx+9]; SizeOfElements
0x180028143  lea     r8d, [rbx+45h]; NumOfElements
0x180028147  mov     rcx, rdi; Key
0x18002814a  call    cs:__imp_bsearch_s
0x180028150  test    rax, rax
0x180028153  jz      short loc_180028184
0x180028155  sub     rax, rbp
0x180028158  mov     ecx, 80000000h
0x18002815d  sar     rax, 3
0x180028161  mov     edx, 0FFFFFFFFh
0x180028166  add     rcx, rax
0x180028169  cmp     rcx, rdx
0x18002816c  ja      short loc_180028184
0x18002816e  test    eax, eax
0x180028170  js      short loc_180028184
0x180028172  cmp     eax, 44h ; 'D'
0x180028175  jnb     short loc_180028184
0x180028177  cdqe
0x180028179  lea     rcx, ?_bSampleIds@@3PAEA; uchar near * _bSampleIds
0x180028180  movzx   ebx, byte ptr [rax+rcx]
0x180028184  mov     eax, ebx
0x180028186  add     rsp, 38h
0x18002818a  pop     rdi
0x18002818b  pop     rsi
0x18002818c  pop     rbp
0x18002818d  pop     rbx
0x18002818e  retn
```
