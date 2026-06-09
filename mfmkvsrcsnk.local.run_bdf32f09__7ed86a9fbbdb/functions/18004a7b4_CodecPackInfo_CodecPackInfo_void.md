# CodecPackInfo::~CodecPackInfo(void)

- ea: `0x18004a7b4`
- end: `0x18004a906`
- name: `??1CodecPackInfo@@QEAA@XZ`
- size: `338`
- prototype: `void __fastcall(CodecPackInfo *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004ae44`
- `0x1800adff5`

## callees

- `0x18004a64c`
- `0x18004a674`
- `0x18004a7b4`
- `0x18004a9a8`
- `0x18004b838`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a8b7`

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
              & *((_BYTE *)&CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks
                + (((_BYTE)i - (_BYTE)v6) & 7))) != 0 )
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
              & *((_BYTE *)&CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks
                + (((_BYTE)k - (_BYTE)v11) & 7))) != 0 )
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
0x18004a7b4  push    rbx
0x18004a7b6  push    rbp
0x18004a7b7  push    rsi
0x18004a7b8  push    rdi
0x18004a7b9  push    r14
0x18004a7bb  push    r15
0x18004a7bd  sub     rsp, 28h
0x18004a7c1  mov     rbp, rcx
0x18004a7c4  lea     rsi, [rcx+358h]
0x18004a7cb  mov     edi, [rsi+0C8h]
0x18004a7d1  xor     ebx, ebx
0x18004a7d3  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_tagpropertykey,20,0>::s_bSingleBitMasks
0x18004a7da  test    edi, edi
0x18004a7dc  jz      short loc_18004A83D
0x18004a7de  cmp     ebx, [rsi+0C8h]
0x18004a7e4  jnb     short loc_18004A837
0x18004a7e6  mov     rdx, rsi
0x18004a7e9  test    rdx, rdx
0x18004a7ec  jz      short loc_18004A827
0x18004a7ee  mov     ecx, [rdx+8]
0x18004a7f1  cmp     ebx, ecx
0x18004a7f3  jb      short loc_18004A7FC
0x18004a7f5  lea     eax, [rcx+14h]
0x18004a7f8  cmp     ebx, eax
0x18004a7fa  jb      short loc_18004A805
0x18004a7fc  mov     rdx, [rdx+0C0h]
0x18004a803  jmp     short loc_18004A7E9
0x18004a805  mov     eax, ebx
0x18004a807  sub     eax, ecx
0x18004a809  mov     r8d, eax
0x18004a80c  shr     rax, 3
0x18004a810  mov     ecx, r8d
0x18004a813  and     ecx, 7
0x18004a816  mov     al, [rax+rdx+18h]
0x18004a81a  test    [rcx+r15], al
0x18004a81e  jz      short loc_18004A827
0x18004a820  mov     rcx, [rdx+r8*8+20h]
0x18004a825  jmp     short loc_18004A831
0x18004a827  test    byte ptr [rsi+0Ch], 1
0x18004a82b  jz      short loc_18004A837
0x18004a82d  mov     rcx, [rsi+10h]; string
0x18004a831  call    cs:__imp_WindowsDeleteString
0x18004a837  inc     ebx
0x18004a839  cmp     ebx, edi
0x18004a83b  jb      short loc_18004A7DE
0x18004a83d  mov     rcx, rsi
0x18004a840  call    ?FreeList@?$CTSparseBlock@KPEAUHSTRING__@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,HSTRING__ *,20,0>::FreeList(int)
0x18004a845  mov     dword ptr [rsi+0C8h], 0
0x18004a84f  lea     rbx, [rbp+428h]
0x18004a856  mov     r14d, [rbx+0C8h]
0x18004a85d  xor     edi, edi
0x18004a85f  test    r14d, r14d
0x18004a862  jz      short loc_18004A8C4
0x18004a864  cmp     edi, [rbx+0C8h]
0x18004a86a  jnb     short loc_18004A8BD
0x18004a86c  mov     rdx, rbx
0x18004a86f  test    rdx, rdx
0x18004a872  jz      short loc_18004A8AD
0x18004a874  mov     ecx, [rdx+8]
0x18004a877  cmp     edi, ecx
0x18004a879  jb      short loc_18004A882
0x18004a87b  lea     eax, [rcx+14h]
0x18004a87e  cmp     edi, eax
0x18004a880  jb      short loc_18004A88B
0x18004a882  mov     rdx, [rdx+0C0h]
0x18004a889  jmp     short loc_18004A86F
0x18004a88b  mov     eax, edi
0x18004a88d  sub     eax, ecx
0x18004a88f  mov     r8d, eax
0x18004a892  shr     rax, 3
0x18004a896  mov     ecx, r8d
0x18004a899  and     ecx, 7
0x18004a89c  mov     al, [rax+rdx+18h]
0x18004a8a0  test    [rcx+r15], al
0x18004a8a4  jz      short loc_18004A8AD
0x18004a8a6  mov     rcx, [rdx+r8*8+20h]
0x18004a8ab  jmp     short loc_18004A8B7
0x18004a8ad  test    byte ptr [rbx+0Ch], 1
0x18004a8b1  jz      short loc_18004A8BD
0x18004a8b3  mov     rcx, [rbx+10h]; string
0x18004a8b7  call    cs:__imp_WindowsDeleteString
0x18004a8bd  inc     edi
0x18004a8bf  cmp     edi, r14d
0x18004a8c2  jb      short loc_18004A864
0x18004a8c4  mov     rcx, rbx
0x18004a8c7  call    ?FreeList@?$CTSparseBlock@KPEAUHSTRING__@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,HSTRING__ *,20,0>::FreeList(int)
0x18004a8cc  mov     dword ptr [rbx+0C8h], 0
0x18004a8d6  mov     rcx, rbx
0x18004a8d9  call    ??1?$CTSparseBlock@KPEAUIMFMetadata@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,IMFMetadata *,20,0>::~CTSparseBlock<ulong,IMFMetadata *,20,0>(void)
0x18004a8de  mov     rcx, rsi
0x18004a8e1  call    ??1?$CTSparseBlock@KPEAUIMFMetadata@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,IMFMetadata *,20,0>::~CTSparseBlock<ulong,IMFMetadata *,20,0>(void)
0x18004a8e6  lea     rcx, [rbp+1E0h]
0x18004a8ed  call    ??1?$CTSparseBlock@KU_GUID@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,_GUID,20,0>::~CTSparseBlock<ulong,_GUID,20,0>(void)
0x18004a8f2  mov     rcx, rbp; this
0x18004a8f5  add     rsp, 28h
0x18004a8f9  pop     r15
0x18004a8fb  pop     r14
0x18004a8fd  pop     rdi
0x18004a8fe  pop     rsi
0x18004a8ff  pop     rbp
0x18004a900  pop     rbx
0x18004a901  jmp     ??1InprocMFTExtensionInfo@@QEAA@XZ; InprocMFTExtensionInfo::~InprocMFTExtensionInfo(void)
```
