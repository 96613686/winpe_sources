# HsmiCompressBuffer

- ea: `0x14004a3f0`
- end: `0x14004a636`
- name: `HsmiCompressBuffer`
- size: `582`
- prototype: `__int64 __fastcall(UCHAR *, ULONG, UCHAR *, ULONG, ULONG *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004a63c`

## callees

- `0x140003c50`
- `0x14004a3f0`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004a45d`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004a45d`
- `ntoskrnl!RtlCompressBuffer` at `0x14004a525`
- `ntoskrnl!RtlCompressBuffer` at `0x14004a525`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a582`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a582`
- `ntoskrnl!ExAllocatePool2` at `0x14004a4a7`
- `ntoskrnl!ExAllocatePool2` at `0x14004a4a7`

## pseudocode

```c
__int64 __fastcall HsmiCompressBuffer(UCHAR *a1, ULONG a2, UCHAR *a3, ULONG a4, ULONG *a5, _BYTE *a6, _BYTE *a7)
{
  NTSTATUS CompressionWorkSpaceSize; // edi
  ULONG v8; // r15d
  ULONG v9; // ebx
  __int64 i; // rsi
  void *WorkSpace; // rbp
  unsigned int v15; // esi
  __int64 v16; // rbx
  char v17; // dl
  char v18; // cl
  ULONG CompressFragmentWorkSpaceSize[18]; // [rsp+40h] [rbp-48h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+98h] [rbp+10h] BYREF
  ULONG FinalCompressedSize; // [rsp+A8h] [rbp+20h] BYREF

  CompressionWorkSpaceSize = 0;
  v8 = a4 + 1;
  v9 = 0;
  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize[0] = 0;
  FinalCompressedSize = 0;
  if ( a2 < a4 + 1 )
    v8 = a2;
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    if ( *((_DWORD *)SupportedCompressionTypes + 3 * i + 1) <= a2
      && *((_DWORD *)&SupportedCompressionTypes[1] + 3 * i) >= a2 )
    {
      CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                   *((_WORD *)SupportedCompressionTypes + 6 * i),
                                   &CompressBufferWorkSpaceSize,
                                   CompressFragmentWorkSpaceSize);
      HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
      if ( CompressionWorkSpaceSize < 0 )
        return (unsigned int)CompressionWorkSpaceSize;
      if ( CompressBufferWorkSpaceSize > v9 )
        v9 = CompressBufferWorkSpaceSize;
    }
  }
  WorkSpace = 0;
  if ( v9 && (WorkSpace = (void *)ExAllocatePool2(256, v9, 1917875016)) == 0 )
  {
    CompressionWorkSpaceSize = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
  }
  else
  {
    v15 = 3;
    v16 = 0;
    do
    {
      if ( *((_DWORD *)SupportedCompressionTypes + 3 * v16 + 1) <= a2
        && *((_DWORD *)&SupportedCompressionTypes[1] + 3 * v16) >= a2 )
      {
        CompressionWorkSpaceSize = RtlCompressBuffer(
                                     *((_WORD *)SupportedCompressionTypes + 6 * v16),
                                     a1,
                                     a2,
                                     a3,
                                     a4,
                                     512 << (*((_BYTE *)SupportedCompressionTypes + 12 * v16 + 2) & 7),
                                     &FinalCompressedSize,
                                     WorkSpace);
        HsmDbgBreakOnStatus(CompressionWorkSpaceSize);
        if ( CompressionWorkSpaceSize >= 0 && FinalCompressedSize < v8 )
        {
          v8 = FinalCompressedSize;
          v15 = v16;
        }
        else if ( (_DWORD)v16 == 2 )
        {
          LODWORD(v16) = v15 - 1;
          if ( v15 >= 2 )
            LODWORD(v16) = 2;
        }
        else if ( (_DWORD)v16 == v15 )
        {
          break;
        }
      }
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < 3 );
    if ( WorkSpace )
      ExFreePoolWithTag(WorkSpace, 0x72507348u);
    if ( CompressionWorkSpaceSize >= 0 )
    {
      if ( v15 >= 3 )
      {
        *a5 = 0;
        *a6 = 0;
        *a7 = 0;
      }
      else
      {
        v17 = *((_BYTE *)SupportedCompressionTypes + 12 * v15);
        v18 = *((_BYTE *)SupportedCompressionTypes + 12 * v15 + 1) & 0x1F
            | (16 * *((_BYTE *)SupportedCompressionTypes + 12 * v15 + 2));
        *a5 = v8;
        *a6 = v17;
        *a7 = v18;
      }
    }
  }
  return (unsigned int)CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14004a3f0  mov     rax, rsp
0x14004a3f3  mov     [rax+18h], rbx
0x14004a3f7  mov     [rax+8], rcx
0x14004a3fb  push    rbp
0x14004a3fc  push    rsi
0x14004a3fd  push    rdi
0x14004a3fe  push    r12
0x14004a400  push    r13
0x14004a402  push    r14
0x14004a404  push    r15
0x14004a406  sub     rsp, 50h
0x14004a40a  xor     edi, edi
0x14004a40c  lea     r15d, [r9+1]
0x14004a410  xor     ebx, ebx
0x14004a412  mov     [rax+10h], edi
0x14004a415  cmp     edx, r15d
0x14004a418  mov     [rax-48h], edi
0x14004a41b  mov     r13d, r9d
0x14004a41e  mov     [rax+20h], ebx
0x14004a421  cmovb   r15d, edx
0x14004a425  lea     r11, SupportedCompressionTypes
0x14004a42c  xor     esi, esi
0x14004a42e  mov     r12, r8
0x14004a431  mov     r14d, edx
0x14004a434  cmp     esi, 3
0x14004a437  jnb     short loc_14004A494
0x14004a439  lea     rcx, [rsi+rsi*2]
0x14004a43d  cmp     [r11+rcx*4+4], r14d
0x14004a442  ja      short loc_14004A490
0x14004a444  cmp     [r11+rcx*4+8], r14d
0x14004a449  jb      short loc_14004A490
0x14004a44b  movzx   ecx, word ptr [r11+rcx*4]; CompressionFormatAndEngine
0x14004a450  lea     r8, [rsp+88h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004a455  lea     rdx, [rsp+88h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004a45d  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004a464  nop     dword ptr [rax+rax+00h]
0x14004a469  mov     ecx, eax
0x14004a46b  mov     edi, eax
0x14004a46d  call    HsmDbgBreakOnStatus
0x14004a472  test    edi, edi
0x14004a474  js      loc_14004A5D8
0x14004a47a  cmp     [rsp+88h+CompressBufferWorkSpaceSize], ebx
0x14004a481  lea     r11, SupportedCompressionTypes
0x14004a488  cmova   ebx, [rsp+88h+CompressBufferWorkSpaceSize]
0x14004a490  inc     esi
0x14004a492  jmp     short loc_14004A434
0x14004a494  xor     ebp, ebp
0x14004a496  test    ebx, ebx
0x14004a498  jz      short loc_14004A4C6
0x14004a49a  mov     edx, ebx
0x14004a49c  mov     ecx, 100h
0x14004a4a1  mov     r8d, 72507348h
0x14004a4a7  call    cs:__imp_ExAllocatePool2
0x14004a4ae  nop     dword ptr [rax+rax+00h]
0x14004a4b3  mov     rbp, rax
0x14004a4b6  test    rax, rax
0x14004a4b9  jz      loc_14004A5F3
0x14004a4bf  lea     r11, SupportedCompressionTypes
0x14004a4c6  mov     esi, 3
0x14004a4cb  xor     ebx, ebx
0x14004a4cd  lea     r10, [rbx+rbx*2]
0x14004a4d1  cmp     [r11+r10*4+4], r14d
0x14004a4d6  ja      loc_14004A56A
0x14004a4dc  cmp     [r11+r10*4+8], r14d
0x14004a4e1  jb      loc_14004A56A
0x14004a4e7  movzx   ecx, byte ptr [r11+r10*4+2]
0x14004a4ed  mov     eax, 200h
0x14004a4f2  mov     rdx, [rsp+88h+UncompressedBuffer]; UncompressedBuffer
0x14004a4fa  and     ecx, 7
0x14004a4fd  shl     eax, cl
0x14004a4ff  mov     r9, r12; CompressedBuffer
0x14004a502  lea     rcx, [rsp+88h+arg_18]
0x14004a50a  mov     [rsp+88h+WorkSpace], rbp; WorkSpace
0x14004a50f  mov     [rsp+88h+FinalCompressedSize], rcx; FinalCompressedSize
0x14004a514  mov     r8d, r14d; UncompressedBufferSize
0x14004a517  movzx   ecx, word ptr [r11+r10*4]; CompressionFormatAndEngine
0x14004a51c  mov     [rsp+88h+UncompressedChunkSize], eax; UncompressedChunkSize
0x14004a520  mov     [rsp+88h+CompressedBufferSize], r13d; CompressedBufferSize
0x14004a525  call    cs:__imp_RtlCompressBuffer
0x14004a52c  nop     dword ptr [rax+rax+00h]
0x14004a531  mov     ecx, eax
0x14004a533  mov     edi, eax
0x14004a535  call    HsmDbgBreakOnStatus
0x14004a53a  test    edi, edi
0x14004a53c  js      short loc_14004A54C
0x14004a53e  cmp     [rsp+88h+arg_18], r15d
0x14004a546  jb      loc_14004A601
0x14004a54c  mov     ecx, 2
0x14004a551  cmp     ebx, ecx
0x14004a553  jz      short loc_14004A55B
0x14004a555  cmp     ebx, esi
0x14004a557  jnz     short loc_14004A563
0x14004a559  jmp     short loc_14004A575
0x14004a55b  cmp     esi, ecx
0x14004a55d  lea     ebx, [rsi-1]
0x14004a560  cmovnb  ebx, ecx
0x14004a563  lea     r11, SupportedCompressionTypes
0x14004a56a  inc     ebx
0x14004a56c  cmp     ebx, 3
0x14004a56f  jb      loc_14004A4CD
0x14004a575  test    rbp, rbp
0x14004a578  jz      short loc_14004A58E
0x14004a57a  mov     edx, 72507348h; Tag
0x14004a57f  mov     rcx, rbp; P
0x14004a582  call    cs:__imp_ExFreePoolWithTag
0x14004a589  nop     dword ptr [rax+rax+00h]
0x14004a58e  test    edi, edi
0x14004a590  js      short loc_14004A5D8
0x14004a592  cmp     esi, 3
0x14004a595  jnb     short loc_14004A610
0x14004a597  lea     r8, SupportedCompressionTypes
0x14004a59e  mov     eax, esi
0x14004a5a0  lea     rax, [rax+rax*2]
0x14004a5a4  mov     cl, [r8+rax*4+2]
0x14004a5a9  mov     dl, [r8+rax*4]
0x14004a5ad  mov     al, [r8+rax*4+1]
0x14004a5b2  and     al, 1Fh
0x14004a5b4  shl     cl, 4
0x14004a5b7  or      cl, al
0x14004a5b9  mov     rax, [rsp+88h+arg_20]
0x14004a5c1  mov     [rax], r15d
0x14004a5c4  mov     rax, [rsp+88h+arg_28]
0x14004a5cc  mov     [rax], dl
0x14004a5ce  mov     rax, [rsp+88h+arg_30]
0x14004a5d6  mov     [rax], cl
0x14004a5d8  mov     rbx, [rsp+88h+arg_10]
0x14004a5e0  mov     eax, edi
0x14004a5e2  add     rsp, 50h
0x14004a5e6  pop     r15
0x14004a5e8  pop     r14
0x14004a5ea  pop     r13
0x14004a5ec  pop     r12
0x14004a5ee  pop     rdi
0x14004a5ef  pop     rsi
0x14004a5f0  pop     rbp
0x14004a5f1  retn
0x14004a5f3  mov     edi, 0C000009Ah
0x14004a5f8  mov     ecx, edi
0x14004a5fa  call    HsmDbgBreakOnStatus
0x14004a5ff  jmp     short loc_14004A5D8
0x14004a601  mov     r15d, [rsp+88h+arg_18]
0x14004a609  mov     esi, ebx
0x14004a60b  jmp     loc_14004A563
0x14004a610  mov     rax, [rsp+88h+arg_20]
0x14004a618  mov     dword ptr [rax], 0
0x14004a61e  mov     rax, [rsp+88h+arg_28]
0x14004a626  mov     byte ptr [rax], 0
0x14004a629  mov     rax, [rsp+88h+arg_30]
0x14004a631  mov     byte ptr [rax], 0
0x14004a634  jmp     short loc_14004A5D8
```
