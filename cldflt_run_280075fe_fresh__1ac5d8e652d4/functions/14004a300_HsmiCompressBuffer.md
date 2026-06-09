# HsmiCompressBuffer

- ea: `0x14004a300`
- end: `0x14004a546`
- name: `HsmiCompressBuffer`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004a54c`

## callees

- `0x140003c50`
- `0x14004a300`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004a36d`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14004a36d`
- `ntoskrnl!RtlCompressBuffer` at `0x14004a435`
- `ntoskrnl!RtlCompressBuffer` at `0x14004a435`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a492`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a492`
- `ntoskrnl!ExAllocatePool2` at `0x14004a3b7`
- `ntoskrnl!ExAllocatePool2` at `0x14004a3b7`

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
      HsmDbgBreakOnStatus((unsigned int)CompressionWorkSpaceSize);
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
    HsmDbgBreakOnStatus(3221225626LL);
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
        HsmDbgBreakOnStatus((unsigned int)CompressionWorkSpaceSize);
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
0x14004a300  mov     rax, rsp
0x14004a303  mov     [rax+18h], rbx
0x14004a307  mov     [rax+8], rcx
0x14004a30b  push    rbp
0x14004a30c  push    rsi
0x14004a30d  push    rdi
0x14004a30e  push    r12
0x14004a310  push    r13
0x14004a312  push    r14
0x14004a314  push    r15
0x14004a316  sub     rsp, 50h
0x14004a31a  xor     edi, edi
0x14004a31c  lea     r15d, [r9+1]
0x14004a320  xor     ebx, ebx
0x14004a322  mov     [rax+10h], edi
0x14004a325  cmp     edx, r15d
0x14004a328  mov     [rax-48h], edi
0x14004a32b  mov     r13d, r9d
0x14004a32e  mov     [rax+20h], ebx
0x14004a331  cmovb   r15d, edx
0x14004a335  lea     r11, SupportedCompressionTypes
0x14004a33c  xor     esi, esi
0x14004a33e  mov     r12, r8
0x14004a341  mov     r14d, edx
0x14004a344  cmp     esi, 3
0x14004a347  jnb     short loc_14004A3A4
0x14004a349  lea     rcx, [rsi+rsi*2]
0x14004a34d  cmp     [r11+rcx*4+4], r14d
0x14004a352  ja      short loc_14004A3A0
0x14004a354  cmp     [r11+rcx*4+8], r14d
0x14004a359  jb      short loc_14004A3A0
0x14004a35b  movzx   ecx, word ptr [r11+rcx*4]; CompressionFormatAndEngine
0x14004a360  lea     r8, [rsp+88h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14004a365  lea     rdx, [rsp+88h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14004a36d  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14004a374  nop     dword ptr [rax+rax+00h]
0x14004a379  mov     ecx, eax
0x14004a37b  mov     edi, eax
0x14004a37d  call    HsmDbgBreakOnStatus
0x14004a382  test    edi, edi
0x14004a384  js      loc_14004A4E8
0x14004a38a  cmp     [rsp+88h+CompressBufferWorkSpaceSize], ebx
0x14004a391  lea     r11, SupportedCompressionTypes
0x14004a398  cmova   ebx, [rsp+88h+CompressBufferWorkSpaceSize]
0x14004a3a0  inc     esi
0x14004a3a2  jmp     short loc_14004A344
0x14004a3a4  xor     ebp, ebp
0x14004a3a6  test    ebx, ebx
0x14004a3a8  jz      short loc_14004A3D6
0x14004a3aa  mov     edx, ebx
0x14004a3ac  mov     ecx, 100h
0x14004a3b1  mov     r8d, 72507348h
0x14004a3b7  call    cs:__imp_ExAllocatePool2
0x14004a3be  nop     dword ptr [rax+rax+00h]
0x14004a3c3  mov     rbp, rax
0x14004a3c6  test    rax, rax
0x14004a3c9  jz      loc_14004A503
0x14004a3cf  lea     r11, SupportedCompressionTypes
0x14004a3d6  mov     esi, 3
0x14004a3db  xor     ebx, ebx
0x14004a3dd  lea     r10, [rbx+rbx*2]
0x14004a3e1  cmp     [r11+r10*4+4], r14d
0x14004a3e6  ja      loc_14004A47A
0x14004a3ec  cmp     [r11+r10*4+8], r14d
0x14004a3f1  jb      loc_14004A47A
0x14004a3f7  movzx   ecx, byte ptr [r11+r10*4+2]
0x14004a3fd  mov     eax, 200h
0x14004a402  mov     rdx, [rsp+88h+UncompressedBuffer]; UncompressedBuffer
0x14004a40a  and     ecx, 7
0x14004a40d  shl     eax, cl
0x14004a40f  mov     r9, r12; CompressedBuffer
0x14004a412  lea     rcx, [rsp+88h+arg_18]
0x14004a41a  mov     [rsp+88h+WorkSpace], rbp; WorkSpace
0x14004a41f  mov     [rsp+88h+FinalCompressedSize], rcx; FinalCompressedSize
0x14004a424  mov     r8d, r14d; UncompressedBufferSize
0x14004a427  movzx   ecx, word ptr [r11+r10*4]; CompressionFormatAndEngine
0x14004a42c  mov     [rsp+88h+UncompressedChunkSize], eax; UncompressedChunkSize
0x14004a430  mov     [rsp+88h+CompressedBufferSize], r13d; CompressedBufferSize
0x14004a435  call    cs:__imp_RtlCompressBuffer
0x14004a43c  nop     dword ptr [rax+rax+00h]
0x14004a441  mov     ecx, eax
0x14004a443  mov     edi, eax
0x14004a445  call    HsmDbgBreakOnStatus
0x14004a44a  test    edi, edi
0x14004a44c  js      short loc_14004A45C
0x14004a44e  cmp     [rsp+88h+arg_18], r15d
0x14004a456  jb      loc_14004A511
0x14004a45c  mov     ecx, 2
0x14004a461  cmp     ebx, ecx
0x14004a463  jz      short loc_14004A46B
0x14004a465  cmp     ebx, esi
0x14004a467  jnz     short loc_14004A473
0x14004a469  jmp     short loc_14004A485
0x14004a46b  cmp     esi, ecx
0x14004a46d  lea     ebx, [rsi-1]
0x14004a470  cmovnb  ebx, ecx
0x14004a473  lea     r11, SupportedCompressionTypes
0x14004a47a  inc     ebx
0x14004a47c  cmp     ebx, 3
0x14004a47f  jb      loc_14004A3DD
0x14004a485  test    rbp, rbp
0x14004a488  jz      short loc_14004A49E
0x14004a48a  mov     edx, 72507348h; Tag
0x14004a48f  mov     rcx, rbp; P
0x14004a492  call    cs:__imp_ExFreePoolWithTag
0x14004a499  nop     dword ptr [rax+rax+00h]
0x14004a49e  test    edi, edi
0x14004a4a0  js      short loc_14004A4E8
0x14004a4a2  cmp     esi, 3
0x14004a4a5  jnb     short loc_14004A520
0x14004a4a7  lea     r8, SupportedCompressionTypes
0x14004a4ae  mov     eax, esi
0x14004a4b0  lea     rax, [rax+rax*2]
0x14004a4b4  mov     cl, [r8+rax*4+2]
0x14004a4b9  mov     dl, [r8+rax*4]
0x14004a4bd  mov     al, [r8+rax*4+1]
0x14004a4c2  and     al, 1Fh
0x14004a4c4  shl     cl, 4
0x14004a4c7  or      cl, al
0x14004a4c9  mov     rax, [rsp+88h+arg_20]
0x14004a4d1  mov     [rax], r15d
0x14004a4d4  mov     rax, [rsp+88h+arg_28]
0x14004a4dc  mov     [rax], dl
0x14004a4de  mov     rax, [rsp+88h+arg_30]
0x14004a4e6  mov     [rax], cl
0x14004a4e8  mov     rbx, [rsp+88h+arg_10]
0x14004a4f0  mov     eax, edi
0x14004a4f2  add     rsp, 50h
0x14004a4f6  pop     r15
0x14004a4f8  pop     r14
0x14004a4fa  pop     r13
0x14004a4fc  pop     r12
0x14004a4fe  pop     rdi
0x14004a4ff  pop     rsi
0x14004a500  pop     rbp
0x14004a501  retn
0x14004a503  mov     edi, 0C000009Ah
0x14004a508  mov     ecx, edi
0x14004a50a  call    HsmDbgBreakOnStatus
0x14004a50f  jmp     short loc_14004A4E8
0x14004a511  mov     r15d, [rsp+88h+arg_18]
0x14004a519  mov     esi, ebx
0x14004a51b  jmp     loc_14004A473
0x14004a520  mov     rax, [rsp+88h+arg_20]
0x14004a528  mov     dword ptr [rax], 0
0x14004a52e  mov     rax, [rsp+88h+arg_28]
0x14004a536  mov     byte ptr [rax], 0
0x14004a539  mov     rax, [rsp+88h+arg_30]
0x14004a541  mov     byte ptr [rax], 0
0x14004a544  jmp     short loc_14004A4E8
```
