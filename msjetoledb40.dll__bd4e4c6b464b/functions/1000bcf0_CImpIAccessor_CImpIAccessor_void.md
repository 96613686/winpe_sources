# CImpIAccessor::~CImpIAccessor(void)

- ea: `0x1000bcf0`
- end: `0x1000be59`
- name: `??1CImpIAccessor@@QAE@XZ`
- size: `361`
- prototype: `void __thiscall(CImpIAccessor *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10013d50`
- `0x10013f50`
- `0x10027f00`
- `0x10028340`

## callees

- `0x1000bb80`
- `0x1000bcf0`
- `0x1004cea1`

## import_xrefs

- `msvcrt!free` at `0x1000be23`
- `msvcrt!free` at `0x1000be23`
- `KERNEL32!DeleteCriticalSection` at `0x1000be4e`
- `KERNEL32!DeleteCriticalSection` at `0x1000be4e`

## pseudocode

```c
void __usercall CImpIAccessor::~CImpIAccessor(
        struct _RTL_CRITICAL_SECTION *this@<ecx>,
        unsigned int *a2@<edi>,
        unsigned int a3@<esi>)
{
  struct _RTL_CRITICAL_SECTION *v3; // ebx
  ULONG_PTR SpinCount; // ecx
  unsigned int i; // edi
  _DWORD *v6; // esi
  int v7; // ecx
  int v8; // edi
  unsigned int j; // esi
  _DWORD *v10; // ebx
  int v11; // ecx
  unsigned int v12; // esi
  void **v13; // esi
  int v14; // [esp+8h] [ebp-Ch]
  unsigned int v15; // [esp+Ch] [ebp-8h]
  unsigned int v16; // [esp+Ch] [ebp-8h]

  v3 = this;
  SpinCount = this->SpinCount;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpIAccessor::`vftable';
  if ( SpinCount )
  {
    CExtBuffer::GetNextUsedItem((CExtBuffer *)1, a2, a3);
    for ( i = v15; i; v3 = this )
    {
      v6 = (_DWORD *)v3->SpinCount;
      v7 = v6[6];
      if ( i > v7 + 8 * v6[5] - 1
        || (*(_BYTE *)(((i - v7) >> 3) + v6[4]) & *((_BYTE *)&Bitmap::ThisBit + ((i - v7) & 7))) != 0 )
      {
        v8 = 0;
      }
      else
      {
        v8 = *(_DWORD *)(v6[2] + 4 * i);
      }
      if ( *(_DWORD *)(v8 + 20) )
      {
        if ( *(_DWORD *)(v8 + 32) )
          operator delete(*(void **)(v8 + 32));
        for ( j = 0; j < *(_DWORD *)(v8 + 36); ++j )
        {
          if ( *(_DWORD *)(52 * j + v8 + 60) )
            operator delete(*(void **)(52 * j + v8 + 60));
        }
        operator delete((void *)v8);
      }
      v10 = (_DWORD *)v3->SpinCount;
      i = 0;
      v11 = v10[6];
      v12 = v10[3];
      v14 = v11;
      v16 = v11 + 8 * v10[5] - 1;
      if ( v12 <= v16 )
      {
        i = v10[3];
        while ( 1 )
        {
          v12 = i;
          if ( (*(_BYTE *)(((i - v11) >> 3) + v10[4]) & *((_BYTE *)&Bitmap::ThisBit + ((i - v11) & 7))) == 0 )
            break;
          v11 = v14;
          v12 = i + 1;
          i = v12;
          v10[3] = v12;
          if ( v12 > v16 )
          {
            i = 0;
            break;
          }
        }
      }
      v10[3] = v12 + 1;
    }
    v13 = (void **)v3->SpinCount;
    if ( v13 )
    {
      if ( v13[2] )
        _free(v13[2]);
      if ( v13[4] != v13 + 8 )
        operator delete(v13[4]);
      operator delete(v13);
    }
  }
  DeleteCriticalSection(v3 + 1);
}

```

## disassembly

```asm
0x1000bcf0  mov     edi, edi
0x1000bcf2  push    ebp
0x1000bcf3  mov     ebp, esp
0x1000bcf5  sub     esp, 10h
0x1000bcf8  push    ebx
0x1000bcf9  mov     ebx, ecx
0x1000bcfb  mov     [ebp+var_4], ebx
0x1000bcfe  mov     ecx, [ebx+14h]
0x1000bd01  mov     dword ptr [ebx], offset ??_7CImpIAccessor@@6B@; const CImpIAccessor::`vftable'
0x1000bd07  test    ecx, ecx
0x1000bd09  jz      loc_1000BE4A
0x1000bd0f  push    esi; unsigned int
0x1000bd10  push    edi; unsigned int *
0x1000bd11  push    1; this
0x1000bd13  lea     edx, [ebp+var_8]
0x1000bd16  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x1000bd1b  mov     edi, [ebp+var_8]
0x1000bd1e  test    edi, edi
0x1000bd20  jz      loc_1000BE14
0x1000bd26  mov     esi, [ebx+14h]
0x1000bd29  mov     eax, [esi+14h]
0x1000bd2c  mov     ecx, [esi+18h]
0x1000bd2f  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000bd36  add     eax, ecx
0x1000bd38  cmp     edi, eax
0x1000bd3a  ja      short loc_1000BD5E
0x1000bd3c  mov     eax, [esi+10h]
0x1000bd3f  mov     edx, edi
0x1000bd41  sub     edx, ecx
0x1000bd43  mov     ecx, edx
0x1000bd45  and     edx, 7
0x1000bd48  shr     ecx, 3
0x1000bd4b  mov     al, [ecx+eax]
0x1000bd4e  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000bd54  jnz     short loc_1000BD5E
0x1000bd56  mov     eax, [esi+8]
0x1000bd59  mov     edi, [eax+edi*4]
0x1000bd5c  jmp     short loc_1000BD60
0x1000bd5e  xor     edi, edi
0x1000bd60  cmp     dword ptr [edi+14h], 0
0x1000bd64  jbe     short loc_1000BDA3
0x1000bd66  mov     eax, [edi+20h]
0x1000bd69  test    eax, eax
0x1000bd6b  jz      short loc_1000BD76
0x1000bd6d  push    eax; Block
0x1000bd6e  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000bd73  add     esp, 4
0x1000bd76  xor     esi, esi
0x1000bd78  cmp     [edi+24h], esi
0x1000bd7b  jbe     short loc_1000BD9A
0x1000bd7d  nop     dword ptr [eax]
0x1000bd80  imul    eax, esi, 34h ; '4'
0x1000bd83  mov     eax, [eax+edi+3Ch]
0x1000bd87  test    eax, eax
0x1000bd89  jz      short loc_1000BD94
0x1000bd8b  push    eax; Block
0x1000bd8c  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000bd91  add     esp, 4
0x1000bd94  inc     esi
0x1000bd95  cmp     esi, [edi+24h]
0x1000bd98  jb      short loc_1000BD80
0x1000bd9a  push    edi; Block
0x1000bd9b  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000bda0  add     esp, 4
0x1000bda3  mov     ebx, [ebx+14h]
0x1000bda6  xor     edi, edi
0x1000bda8  mov     [ebp+var_10], edi
0x1000bdab  mov     eax, [ebx+14h]
0x1000bdae  mov     ecx, [ebx+18h]
0x1000bdb1  mov     esi, [ebx+0Ch]
0x1000bdb4  mov     [ebp+var_C], ecx
0x1000bdb7  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000bdbe  add     eax, ecx
0x1000bdc0  mov     [ebp+var_8], eax
0x1000bdc3  cmp     esi, eax
0x1000bdc5  ja      short loc_1000BE03
0x1000bdc7  mov     edi, esi
0x1000bdc9  nop     dword ptr [eax+00000000h]
0x1000bdd0  mov     eax, [ebx+10h]
0x1000bdd3  mov     edx, edi
0x1000bdd5  sub     edx, ecx
0x1000bdd7  mov     esi, edi
0x1000bdd9  mov     ecx, edx
0x1000bddb  and     edx, 7
0x1000bdde  shr     ecx, 3
0x1000bde1  mov     al, [ecx+eax]
0x1000bde4  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000bdea  jz      short loc_1000BE01
0x1000bdec  mov     ecx, [ebp+var_C]
0x1000bdef  lea     esi, [edi+1]
0x1000bdf2  mov     edi, esi
0x1000bdf4  mov     [ebx+0Ch], esi
0x1000bdf7  cmp     esi, [ebp+var_8]
0x1000bdfa  jbe     short loc_1000BDD0
0x1000bdfc  mov     edi, [ebp+var_10]
0x1000bdff  jmp     short loc_1000BE03
0x1000be01  mov     edi, esi
0x1000be03  lea     eax, [esi+1]
0x1000be06  mov     [ebx+0Ch], eax
0x1000be09  mov     ebx, [ebp+var_4]
0x1000be0c  test    edi, edi
0x1000be0e  jnz     loc_1000BD26
0x1000be14  mov     esi, [ebx+14h]
0x1000be17  test    esi, esi
0x1000be19  jz      short loc_1000BE48
0x1000be1b  mov     eax, [esi+8]
0x1000be1e  test    eax, eax
0x1000be20  jz      short loc_1000BE2C
0x1000be22  push    eax; Block
0x1000be23  call    ds:__imp__free
0x1000be29  add     esp, 4
0x1000be2c  mov     ecx, [esi+10h]
0x1000be2f  lea     eax, [esi+20h]
0x1000be32  cmp     ecx, eax
0x1000be34  jz      short loc_1000BE3F
0x1000be36  push    ecx; Block
0x1000be37  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000be3c  add     esp, 4
0x1000be3f  push    esi; Block
0x1000be40  call    ??3@YAXPAX@Z; operator delete(void *)
0x1000be45  add     esp, 4
0x1000be48  pop     edi
0x1000be49  pop     esi
0x1000be4a  lea     eax, [ebx+18h]
0x1000be4d  push    eax; lpCriticalSection
0x1000be4e  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000be54  pop     ebx
0x1000be55  mov     esp, ebp
0x1000be57  pop     ebp
0x1000be58  retn
```
