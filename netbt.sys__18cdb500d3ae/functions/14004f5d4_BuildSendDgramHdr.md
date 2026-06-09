# BuildSendDgramHdr

- ea: `0x14004f5d4`
- end: `0x14004f815`
- name: `BuildSendDgramHdr`
- size: `577`
- prototype: `__int64 __usercall@<rax>(ULONG DestinationBufferSize@<ecx>, size_t Size, PMDL SourceMdlChain, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004f224`

## callees

- `0x140001ca0`
- `0x140006bf0`
- `0x14000b2f0`
- `0x14000be64`
- `0x14001b738`
- `0x140031140`
- `0x14004f5d4`

## import_xrefs

- `TDI!TdiCopyMdlToBuffer` at `0x14004f75f`
- `TDI!TdiCopyMdlToBuffer` at `0x14004f75f`

## pseudocode

```c
__int64 __fastcall BuildSendDgramHdr(
        ULONG DestinationBufferSize,
        __int64 a2,
        __int64 a3,
        const void *a4,
        size_t Size,
        PMDL SourceMdlChain,
        PVOID *a7,
        _QWORD *a8)
{
  int v11; // r13d
  __int64 v12; // r14
  ULONG v13; // eax
  __int64 result; // rax
  ULONG v15; // edi
  _BYTE *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r12
  char *v19; // r14
  char *v20; // rbp
  __int64 v21; // rcx
  ULONG BytesCopied; // [rsp+30h] [rbp-58h] BYREF
  PVOID P; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v24[9]; // [rsp+40h] [rbp-48h] BYREF

  v24[0] = 0;
  P = 0;
  BytesCopied = 0;
  v11 = 2 * (unsigned __int16)word_1400395DC + 80;
  v12 = (2 * (unsigned __int16)word_1400395DC + 83) & 0xFFFFFFFC;
  v13 = v12 + Size;
  if ( (int)v12 + (int)Size < (unsigned int)v12 )
    return 3221225621LL;
  v15 = v13 + DestinationBufferSize;
  if ( v13 + DestinationBufferSize < v13 )
    return 3221225621LL;
  CTECountedAllocMem(&P, v15);
  v16 = P;
  if ( P )
  {
    *a7 = P;
    v16[1] = ((unsigned __int16)word_140039626 >> 11) | 2;
    *((_WORD *)v16 + 1) = __ROR2__(GetTransactId(), 8);
    *((_WORD *)v16 + 4) = __ROR2__(*(_WORD *)(a2 + 876), 8);
    if ( *(_DWORD *)(a2 + 340) == 1 )
      *((_DWORD *)v16 + 1) = 0;
    else
      *((_DWORD *)v16 + 1) = _byteswap_ulong(*(_DWORD *)(a2 + 488));
    *((_WORD *)v16 + 5) = __ROR2__(DestinationBufferSize + 2 * (word_1400395DC + 33), 8);
    *((_WORD *)v16 + 6) = 0;
    v17 = ConvertToHalfAscii(v16 + 14, a3, Str2, (unsigned __int16)word_1400395DC);
    ConvertToHalfAscii(v17, a4, Str2, (unsigned __int16)word_1400395DC);
    v18 = (unsigned int)v12;
    v19 = &v16[v12];
    memmove(v19, a4, (unsigned int)Size);
    if ( DestinationBufferSize )
    {
      v20 = &v16[v18 + (unsigned int)Size];
      if ( TdiCopyMdlToBuffer(SourceMdlChain, 0, v20, 0, DestinationBufferSize, &BytesCopied) < 0
        || BytesCopied != DestinationBufferSize )
      {
        CTECountedFreeMem(v16);
        return 3221225473LL;
      }
    }
    else
    {
      v20 = 0;
    }
    if ( (int)GetTracker(v24, 4) >= 0 )
    {
      v21 = v24[0];
      *(_QWORD *)(v24[0] + 80LL) = v20;
      *(_DWORD *)(v21 + 72) = DestinationBufferSize;
      *(_QWORD *)(v21 + 64) = v16;
      *(_DWORD *)(v21 + 56) = v11;
      *(_QWORD *)(v21 + 24) = 0;
      *(_QWORD *)(v21 + 40) = v19;
      *(_QWORD *)(v21 + 312) = 0;
      *(_QWORD *)(v21 + 48) = 0;
      *(_DWORD *)(v21 + 212) = Size;
      *(_QWORD *)(v21 + 96) = 0;
      *a8 = v21;
      result = 0;
      *(_DWORD *)(v21 + 136) = v15;
      return result;
    }
    CTECountedFreeMem(v16);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004f5d4  mov     r11, rsp
0x14004f5d7  mov     [r11+8], rbx
0x14004f5db  mov     [r11+20h], r9
0x14004f5df  mov     [r11+18h], r8
0x14004f5e3  push    rbp
0x14004f5e4  push    rsi
0x14004f5e5  push    rdi
0x14004f5e6  push    r12
0x14004f5e8  push    r13
0x14004f5ea  push    r14
0x14004f5ec  push    r15
0x14004f5ee  sub     rsp, 50h
0x14004f5f2  mov     r15d, dword ptr [rsp+88h+Size]
0x14004f5fa  xor     eax, eax
0x14004f5fc  mov     [r11-48h], rax
0x14004f600  mov     r12, r9
0x14004f603  mov     [r11-50h], rax
0x14004f607  mov     rbp, rdx
0x14004f60a  mov     [rsp+88h+var_58], eax
0x14004f60e  mov     esi, ecx
0x14004f610  movzx   eax, cs:word_1400395DC
0x14004f617  lea     r13d, ds:50h[rax*2]
0x14004f61f  lea     r14d, [r13+3]
0x14004f623  and     r14d, 0FFFFFFFCh
0x14004f627  lea     eax, [r14+r15]
0x14004f62b  cmp     eax, r14d
0x14004f62e  jnb     short loc_14004F64E
0x14004f630  mov     eax, 0C0000095h
0x14004f635  mov     rbx, [rsp+88h+arg_0]
0x14004f63d  add     rsp, 50h
0x14004f641  pop     r15
0x14004f643  pop     r14
0x14004f645  pop     r13
0x14004f647  pop     r12
0x14004f649  pop     rdi
0x14004f64a  pop     rsi
0x14004f64b  pop     rbp
0x14004f64c  retn
0x14004f64e  lea     edi, [rax+rcx]
0x14004f651  cmp     edi, eax
0x14004f653  jb      short loc_14004F630
0x14004f655  mov     edx, edi
0x14004f657  lea     rcx, [rsp+88h+P]
0x14004f65c  call    CTECountedAllocMem
0x14004f661  mov     rbx, [rsp+88h+P]
0x14004f666  test    rbx, rbx
0x14004f669  jz      loc_14004F804
0x14004f66f  mov     rax, [rsp+88h+arg_30]
0x14004f677  mov     [rax], rbx
0x14004f67a  movzx   eax, cs:word_140039626
0x14004f681  shr     ax, 0Bh
0x14004f685  or      al, 2
0x14004f687  mov     [rbx+1], al
0x14004f68a  call    GetTransactId
0x14004f68f  ror     ax, 8
0x14004f693  mov     [rbx+2], ax
0x14004f697  movzx   eax, word ptr [rbp+36Ch]
0x14004f69e  ror     ax, 8
0x14004f6a2  mov     [rbx+8], ax
0x14004f6a6  cmp     dword ptr [rbp+154h], 1
0x14004f6ad  jz      loc_14004F7EB
0x14004f6b3  mov     eax, [rbp+1E8h]
0x14004f6b9  bswap   eax
0x14004f6bb  mov     [rbx+4], eax
0x14004f6be  movzx   eax, cs:word_1400395DC
0x14004f6c5  lea     rcx, [rbx+0Eh]
0x14004f6c9  mov     rdx, [rsp+88h+arg_10]
0x14004f6d1  add     ax, 21h ; '!'
0x14004f6d5  add     ax, ax
0x14004f6d8  add     ax, si
0x14004f6db  ror     ax, 8
0x14004f6df  mov     [rbx+0Ah], ax
0x14004f6e3  xor     eax, eax
0x14004f6e5  mov     [rbx+0Ch], ax
0x14004f6e9  movzx   r9d, cs:word_1400395DC
0x14004f6f1  mov     r8, cs:Str2
0x14004f6f8  call    ConvertToHalfAscii
0x14004f6fd  movzx   r9d, cs:word_1400395DC
0x14004f705  mov     rdx, r12
0x14004f708  mov     r8, cs:Str2
0x14004f70f  mov     rcx, rax
0x14004f712  call    ConvertToHalfAscii
0x14004f717  mov     rdx, [rsp+88h+Src]; Src
0x14004f71f  mov     r8, r15; Size
0x14004f722  mov     r12d, r14d
0x14004f725  mov     rbp, r15
0x14004f728  add     r14, rbx
0x14004f72b  mov     rcx, r14; void *
0x14004f72e  call    memmove
0x14004f733  test    esi, esi
0x14004f735  jz      loc_14004F80E
0x14004f73b  mov     rcx, [rsp+88h+SourceMdlChain]; SourceMdlChain
0x14004f743  lea     rax, [rsp+88h+var_58]
0x14004f748  mov     [rsp+88h+BytesCopied], rax; BytesCopied
0x14004f74d  add     rbp, r12
0x14004f750  add     rbp, rbx
0x14004f753  mov     [rsp+88h+DestinationBufferSize], esi; DestinationBufferSize
0x14004f757  mov     r8, rbp; DestinationBuffer
0x14004f75a  xor     r9d, r9d; DestinationOffset
0x14004f75d  xor     edx, edx; SourceOffset
0x14004f75f  call    cs:__imp_TdiCopyMdlToBuffer
0x14004f766  nop     dword ptr [rax+rax+00h]
0x14004f76b  test    eax, eax
0x14004f76d  js      short loc_14004F7D4
0x14004f76f  cmp     [rsp+88h+var_58], esi
0x14004f773  jnz     short loc_14004F7D4
0x14004f775  mov     edx, 4
0x14004f77a  lea     rcx, [rsp+88h+var_48]
0x14004f77f  call    GetTracker
0x14004f784  xor     edx, edx
0x14004f786  test    eax, eax
0x14004f788  js      short loc_14004F7F7
0x14004f78a  mov     rcx, [rsp+88h+var_48]
0x14004f78f  mov     rax, [rsp+88h+arg_38]
0x14004f797  mov     [rcx+50h], rbp
0x14004f79b  mov     [rcx+48h], esi
0x14004f79e  mov     [rcx+40h], rbx
0x14004f7a2  mov     [rcx+38h], r13d
0x14004f7a6  mov     [rcx+18h], rdx
0x14004f7aa  mov     [rcx+28h], r14
0x14004f7ae  mov     [rcx+138h], rdx
0x14004f7b5  mov     [rcx+30h], rdx
0x14004f7b9  mov     [rcx+0D4h], r15d
0x14004f7c0  mov     [rcx+60h], rdx
0x14004f7c4  mov     [rax], rcx
0x14004f7c7  mov     eax, edx
0x14004f7c9  mov     [rcx+88h], edi
0x14004f7cf  jmp     loc_14004F635
0x14004f7d4  xor     r8d, r8d
0x14004f7d7  mov     edx, edi
0x14004f7d9  mov     rcx, rbx; P
0x14004f7dc  call    CTECountedFreeMem
0x14004f7e1  mov     eax, 0C0000001h
0x14004f7e6  jmp     loc_14004F635
0x14004f7eb  mov     dword ptr [rbx+4], 0
0x14004f7f2  jmp     loc_14004F6BE
0x14004f7f7  xor     r8d, r8d
0x14004f7fa  mov     edx, edi
0x14004f7fc  mov     rcx, rbx; P
0x14004f7ff  call    CTECountedFreeMem
0x14004f804  mov     eax, 0C000009Ah
0x14004f809  jmp     loc_14004F635
0x14004f80e  xor     ebp, ebp
0x14004f810  jmp     loc_14004F775
```
