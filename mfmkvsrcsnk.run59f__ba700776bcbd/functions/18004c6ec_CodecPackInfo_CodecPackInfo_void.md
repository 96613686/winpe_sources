# CodecPackInfo::~CodecPackInfo(void)

- ea: `0x18004c6ec`
- end: `0x18004c84a`
- name: `??1CodecPackInfo@@QEAA@XZ`
- size: `350`
- prototype: `void __fastcall(CodecPackInfo *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004cdb4`
- `0x1800b2d28`

## callees

- `0x18004c584`
- `0x18004c5ac`
- `0x18004c6ec`
- `0x18004c910`
- `0x18004d7dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c7f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c7f5`

## pseudocode

```c
void __fastcall CodecPackInfo::~CodecPackInfo(CodecPackInfo *this)
{
  char *v2; // rsi
  unsigned int v3; // edi
  unsigned int i; // ebx
  char *j; // rdx
  unsigned int v6; // ecx
  HSTRING v7; // rcx
  unsigned int v8; // r14d
  unsigned int k; // edi
  char *m; // rdx
  unsigned int v11; // ecx
  HSTRING v12; // rcx

  v2 = (char *)this + 856;
  v3 = *((_DWORD *)this + 264);
  for ( i = 0; i < v3; ++i )
  {
    if ( i < *((_DWORD *)v2 + 50) )
    {
      for ( j = v2; j; j = (char *)*((_QWORD *)j + 24) )
      {
        v6 = *((_DWORD *)j + 2);
        if ( i >= v6 && i < v6 + 20 )
        {
          if ( ((unsigned __int8)j[((unsigned __int64)(i - v6) >> 3) + 24]
              & CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks[((_BYTE)i - (_BYTE)v6) & 7]) != 0 )
          {
            v7 = *(HSTRING *)&j[8 * (i - v6) + 32];
            goto LABEL_12;
          }
          break;
        }
      }
      if ( (v2[12] & 1) == 0 )
        continue;
      v7 = (HSTRING)*((_QWORD *)v2 + 2);
LABEL_12:
      WindowsDeleteString(v7);
    }
  }
  CTSparseBlock<unsigned long,HSTRING__ *,20,0>::FreeList(v2);
  *((_DWORD *)v2 + 50) = 0;
  v8 = *((_DWORD *)this + 316);
  for ( k = 0; k < v8; ++k )
  {
    if ( k < *((_DWORD *)this + 316) )
    {
      for ( m = (char *)this + 1064; m; m = (char *)*((_QWORD *)m + 24) )
      {
        v11 = *((_DWORD *)m + 2);
        if ( k >= v11 && k < v11 + 20 )
        {
          if ( ((unsigned __int8)m[((unsigned __int64)(k - v11) >> 3) + 24]
              & CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks[((_BYTE)k - (_BYTE)v11) & 7]) != 0 )
          {
            v12 = *(HSTRING *)&m[8 * (k - v11) + 32];
            goto LABEL_25;
          }
          break;
        }
      }
      if ( (*((_BYTE *)this + 1076) & 1) == 0 )
        continue;
      v12 = (HSTRING)*((_QWORD *)this + 135);
LABEL_25:
      WindowsDeleteString(v12);
    }
  }
  CTSparseBlock<unsigned long,HSTRING__ *,20,0>::FreeList((char *)this + 1064);
  *((_DWORD *)this + 316) = 0;
  CTSparseBlock<unsigned long,IMFMetadata *,20,0>::~CTSparseBlock<unsigned long,IMFMetadata *,20,0>((char *)this + 1064);
  CTSparseBlock<unsigned long,IMFMetadata *,20,0>::~CTSparseBlock<unsigned long,IMFMetadata *,20,0>(v2);
  CTSparseBlock<unsigned long,_GUID,20,0>::~CTSparseBlock<unsigned long,_GUID,20,0>((char *)this + 480);
  InprocMFTExtensionInfo::~InprocMFTExtensionInfo(this);
}

```

## disassembly

```asm
0x18004c6ec  push    rbx
0x18004c6ee  push    rbp
0x18004c6ef  push    rsi
0x18004c6f0  push    rdi
0x18004c6f1  push    r14
0x18004c6f3  push    r15
0x18004c6f5  sub     rsp, 28h
0x18004c6f9  mov     rbp, rcx
0x18004c6fc  lea     rsi, [rcx+358h]
0x18004c703  mov     edi, [rsi+0C8h]
0x18004c709  xor     ebx, ebx
0x18004c70b  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_tagpropertykey,20,0>::s_bSingleBitMasks
0x18004c712  test    edi, edi
0x18004c714  jz      short loc_18004C77B
0x18004c716  cmp     ebx, [rsi+0C8h]
0x18004c71c  jnb     short loc_18004C775
0x18004c71e  mov     rdx, rsi
0x18004c721  test    rdx, rdx
0x18004c724  jz      short loc_18004C75F
0x18004c726  mov     ecx, [rdx+8]
0x18004c729  cmp     ebx, ecx
0x18004c72b  jb      short loc_18004C734
0x18004c72d  lea     eax, [rcx+14h]
0x18004c730  cmp     ebx, eax
0x18004c732  jb      short loc_18004C73D
0x18004c734  mov     rdx, [rdx+0C0h]
0x18004c73b  jmp     short loc_18004C721
0x18004c73d  mov     eax, ebx
0x18004c73f  sub     eax, ecx
0x18004c741  mov     r8d, eax
0x18004c744  shr     rax, 3
0x18004c748  mov     ecx, r8d
0x18004c74b  and     ecx, 7
0x18004c74e  mov     al, [rax+rdx+18h]
0x18004c752  test    [rcx+r15], al
0x18004c756  jz      short loc_18004C75F
0x18004c758  mov     rcx, [rdx+r8*8+20h]
0x18004c75d  jmp     short loc_18004C769
0x18004c75f  test    byte ptr [rsi+0Ch], 1
0x18004c763  jz      short loc_18004C775
0x18004c765  mov     rcx, [rsi+10h]; string
0x18004c769  call    cs:__imp_WindowsDeleteString
0x18004c770  nop     dword ptr [rax+rax+00h]
0x18004c775  inc     ebx
0x18004c777  cmp     ebx, edi
0x18004c779  jb      short loc_18004C716
0x18004c77b  mov     rcx, rsi
0x18004c77e  call    ?FreeList@?$CTSparseBlock@KPEAUHSTRING__@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,HSTRING__ *,20,0>::FreeList(int)
0x18004c783  mov     dword ptr [rsi+0C8h], 0
0x18004c78d  lea     rbx, [rbp+428h]
0x18004c794  mov     r14d, [rbx+0C8h]
0x18004c79b  xor     edi, edi
0x18004c79d  test    r14d, r14d
0x18004c7a0  jz      short loc_18004C808
0x18004c7a2  cmp     edi, [rbx+0C8h]
0x18004c7a8  jnb     short loc_18004C801
0x18004c7aa  mov     rdx, rbx
0x18004c7ad  test    rdx, rdx
0x18004c7b0  jz      short loc_18004C7EB
0x18004c7b2  mov     ecx, [rdx+8]
0x18004c7b5  cmp     edi, ecx
0x18004c7b7  jb      short loc_18004C7C0
0x18004c7b9  lea     eax, [rcx+14h]
0x18004c7bc  cmp     edi, eax
0x18004c7be  jb      short loc_18004C7C9
0x18004c7c0  mov     rdx, [rdx+0C0h]
0x18004c7c7  jmp     short loc_18004C7AD
0x18004c7c9  mov     eax, edi
0x18004c7cb  sub     eax, ecx
0x18004c7cd  mov     r8d, eax
0x18004c7d0  shr     rax, 3
0x18004c7d4  mov     ecx, r8d
0x18004c7d7  and     ecx, 7
0x18004c7da  mov     al, [rax+rdx+18h]
0x18004c7de  test    [rcx+r15], al
0x18004c7e2  jz      short loc_18004C7EB
0x18004c7e4  mov     rcx, [rdx+r8*8+20h]
0x18004c7e9  jmp     short loc_18004C7F5
0x18004c7eb  test    byte ptr [rbx+0Ch], 1
0x18004c7ef  jz      short loc_18004C801
0x18004c7f1  mov     rcx, [rbx+10h]; string
0x18004c7f5  call    cs:__imp_WindowsDeleteString
0x18004c7fc  nop     dword ptr [rax+rax+00h]
0x18004c801  inc     edi
0x18004c803  cmp     edi, r14d
0x18004c806  jb      short loc_18004C7A2
0x18004c808  mov     rcx, rbx
0x18004c80b  call    ?FreeList@?$CTSparseBlock@KPEAUHSTRING__@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,HSTRING__ *,20,0>::FreeList(int)
0x18004c810  mov     dword ptr [rbx+0C8h], 0
0x18004c81a  mov     rcx, rbx
0x18004c81d  call    ??1?$CTSparseBlock@KPEAUIMFMetadata@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,IMFMetadata *,20,0>::~CTSparseBlock<ulong,IMFMetadata *,20,0>(void)
0x18004c822  mov     rcx, rsi
0x18004c825  call    ??1?$CTSparseBlock@KPEAUIMFMetadata@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,IMFMetadata *,20,0>::~CTSparseBlock<ulong,IMFMetadata *,20,0>(void)
0x18004c82a  lea     rcx, [rbp+1E0h]
0x18004c831  call    ??1?$CTSparseBlock@KU_GUID@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,_GUID,20,0>::~CTSparseBlock<ulong,_GUID,20,0>(void)
0x18004c836  mov     rcx, rbp; this
0x18004c839  add     rsp, 28h
0x18004c83d  pop     r15
0x18004c83f  pop     r14
0x18004c841  pop     rdi
0x18004c842  pop     rsi
0x18004c843  pop     rbp
0x18004c844  pop     rbx
0x18004c845  jmp     ??1InprocMFTExtensionInfo@@QEAA@XZ; InprocMFTExtensionInfo::~InprocMFTExtensionInfo(void)
```
