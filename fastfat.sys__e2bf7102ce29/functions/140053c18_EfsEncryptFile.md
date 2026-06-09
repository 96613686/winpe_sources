# EfsEncryptFile

- ea: `0x140053c18`
- end: `0x140053f19`
- name: `EfsEncryptFile`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14005521c`

## callees

- `0x1400034f0`
- `0x14000363c`
- `0x1400040e4`
- `0x140004264`
- `0x140004554`
- `0x14004d720`
- `0x14004e560`
- `0x14004e610`
- `0x14004ea30`
- `0x140050ae0`
- `0x140053800`
- `0x140053c18`
- `0x140055a18`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140053ca9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140053ca9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053c91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006057d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053c91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006057d`

## pseudocode

```c
__int64 __fastcall EfsEncryptFile(__int64 a1, char a2, __int64 a3, _WORD *a4, _BYTE *a5, _DWORD *a6, __int64 *a7)
{
  void *v9; // rdi
  PNPAGED_LOOKASIDE_LIST *KeyBlobBuffer; // rsi
  int Attribute; // ebx
  __int64 v12; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  _DWORD *v16; // r12
  __int64 v17; // r14
  __int64 v18; // [rsp+40h] [rbp-58h] BYREF
  _WORD *v19; // [rsp+48h] [rbp-50h] BYREF
  void *Src; // [rsp+50h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-40h] BYREF
  __int64 v22; // [rsp+60h] [rbp-38h]
  __int64 v23; // [rsp+68h] [rbp-30h]
  size_t Size; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+18h]
  _WORD *v26; // [rsp+B8h] [rbp+20h]

  v26 = a4;
  v25 = a3;
  v19 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v22 = 0;
  v9 = 0;
  v21 = 0;
  LODWORD(v18) = 0;
  KeyBlobBuffer = 0;
  v23 = 0;
  if ( (a2 & 2) != 0 )
  {
    Attribute = -1073741811;
    v12 = 2062;
LABEL_3:
    EfspTraceLogAssert(a1, 6, v12, (unsigned int)Attribute);
    goto LABEL_4;
  }
  Attribute = EfspGetEfsStreamForWrite(*(_QWORD *)(a1 + 16), **(unsigned int **)(a1 + 16), &Src, &Size);
  if ( Attribute >= 0 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x8000000) != 0 )
    {
      Attribute = EfsCreateEmptyOrRemoveStreamTransitionMetadata(Src, (unsigned int)Size, (__int64)&v21, (__int64)&v18);
      v9 = (void *)v21;
      if ( Attribute < 0 )
        goto LABEL_4;
      Src = (void *)v21;
      LODWORD(Size) = v18;
      BYTE4(v22) = 1;
      *a5 = 1;
    }
    LODWORD(v22) = 1;
    Attribute = EfsSetEfsStreamInfo(Src, (unsigned int)Size, 8);
    if ( Attribute >= 0 )
    {
      Attribute = NtOfsCreateAttributeEx(a4, v25, &DestinationString, 256, 1, 1, (__int64 *)&v19);
      HIDWORD(v18) = Attribute;
      if ( Attribute >= 0 )
      {
        NtOfsSetLength((__int64)a4, (__int64)v19, (unsigned int)Size);
        NtOfsPutData(a4, (__int64)v19, v15, Size, Src);
        if ( !v19 || (v14 = 1795, (unsigned __int16)(*v19 - 1795) > 2u) )
          NtOfsFlushAttribute(v14, v19);
      }
      if ( v19 )
        NtOfsCloseAttribute((__int64)a4, (__int64)v19);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0);
        v9 = 0;
      }
      if ( Attribute < 0 )
      {
        EfspTraceLogAssert(v14, 6, 2198, (unsigned int)Attribute);
        return (unsigned int)Attribute;
      }
      if ( (*(_DWORD *)(a1 + 8) & 0x8000000) != 0 )
      {
        KeyBlobBuffer = (PNPAGED_LOOKASIDE_LIST *)GetKeyBlobBufferEx(
                                                    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 4LL),
                                                    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
        if ( KeyBlobBuffer )
        {
          v16 = a6;
          LODWORD(Size) = *a6;
          if ( !(unsigned __int8)SetKeyTable(KeyBlobBuffer, &Size, *(_QWORD *)(a1 + 24)) )
          {
            Attribute = -1073741790;
            v12 = 2222;
            goto LABEL_3;
          }
          v17 = AllocateAndSetContextDataBlock(KeyBlobBuffer);
          v23 = v17;
          if ( v17 )
          {
            *v16 = Size;
            *a7 = v17;
            v23 = 0;
            KeyBlobBuffer = 0;
            goto LABEL_4;
          }
        }
        Attribute = -1073741670;
      }
    }
  }
LABEL_4:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( KeyBlobBuffer )
    ExFreeToNPagedLookasideList(KeyBlobBuffer[9], KeyBlobBuffer);
  return (unsigned int)Attribute;
}

```

## disassembly

```asm
0x140053c18  mov     rax, rsp
0x140053c1b  mov     [rax+8], rbx
0x140053c1f  mov     [rax+20h], r9
0x140053c23  mov     [rax+18h], r8
0x140053c27  push    rsi
0x140053c28  push    rdi
0x140053c29  push    r12
0x140053c2b  push    r14
0x140053c2d  push    r15
0x140053c2f  sub     rsp, 70h
0x140053c33  mov     r12, r9
0x140053c36  mov     r15, rcx
0x140053c39  mov     qword ptr [rax-50h], 0
0x140053c41  mov     qword ptr [rax-48h], 0
0x140053c49  mov     dword ptr [rax+10h], 0
0x140053c50  mov     qword ptr [rax-38h], 0
0x140053c58  xor     edi, edi
0x140053c5a  mov     [rax-40h], rdi
0x140053c5e  mov     [rax-58h], edi
0x140053c61  xor     esi, esi
0x140053c63  xor     r14d, r14d
0x140053c66  mov     [rax-30h], r14
0x140053c6a  test    dl, 2
0x140053c6d  jz      short loc_140053CDC
0x140053c6f  mov     ebx, 0C000000Dh
0x140053c74  mov     r8d, 80Eh
0x140053c7a  mov     edx, 6
0x140053c7f  mov     r9d, ebx
0x140053c82  call    EfspTraceLogAssert
0x140053c87  test    rdi, rdi
0x140053c8a  jz      short loc_140053C9D
0x140053c8c  xor     edx, edx; Tag
0x140053c8e  mov     rcx, rdi; P
0x140053c91  call    cs:__imp_ExFreePoolWithTag
0x140053c98  nop     dword ptr [rax+rax+00h]
0x140053c9d  test    rsi, rsi
0x140053ca0  jz      short loc_140053CB5
0x140053ca2  mov     rdx, rsi; Entry
0x140053ca5  mov     rcx, [rsi+48h]; Lookaside
0x140053ca9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140053cb0  nop     dword ptr [rax+rax+00h]
0x140053cb5  test    r14, r14
0x140053cb8  jz      short loc_140053CC4
0x140053cba  lea     rcx, [rsp+98h+var_30]
0x140053cbf  call    FreeContextDataBlock
0x140053cc4  mov     eax, ebx
0x140053cc6  mov     rbx, [rsp+98h+arg_0]
0x140053cce  add     rsp, 70h
0x140053cd2  pop     r15
0x140053cd4  pop     r14
0x140053cd6  pop     r12
0x140053cd8  pop     rdi
0x140053cd9  pop     rsi
0x140053cda  retn
0x140053cdc  mov     rcx, [rcx+10h]
0x140053ce0  lea     r9, [rsp+98h+Size]
0x140053ce8  lea     r8, [rsp+98h+Src]
0x140053ced  mov     edx, [rcx]
0x140053cef  call    EfspGetEfsStreamForWrite
0x140053cf4  mov     ebx, eax
0x140053cf6  test    eax, eax
0x140053cf8  js      short loc_140053C87
0x140053cfa  test    dword ptr [r15+8], 8000000h
0x140053d02  jz      short loc_140053D5E
0x140053d04  lea     rax, [rsp+98h+var_58]
0x140053d09  mov     [rsp+98h+var_70], rax; __int64
0x140053d0e  lea     rax, [rsp+98h+var_40]
0x140053d13  mov     [rsp+98h+var_78], rax; __int64
0x140053d18  mov     r9b, 1
0x140053d1b  mov     r8b, r9b
0x140053d1e  mov     edx, dword ptr [rsp+98h+Size]; Size
0x140053d25  mov     rcx, [rsp+98h+Src]; Src
0x140053d2a  call    EfsCreateEmptyOrRemoveStreamTransitionMetadata
0x140053d2f  mov     ebx, eax
0x140053d31  mov     rdi, [rsp+98h+var_40]
0x140053d36  test    eax, eax
0x140053d38  js      loc_140053C87
0x140053d3e  mov     [rsp+98h+Src], rdi
0x140053d43  mov     eax, dword ptr [rsp+98h+var_58]
0x140053d47  mov     dword ptr [rsp+98h+Size], eax
0x140053d4e  mov     [rsp+98h+var_34], 1
0x140053d53  mov     rax, [rsp+98h+arg_20]
0x140053d5b  mov     byte ptr [rax], 1
0x140053d5e  mov     [rsp+98h+var_38], 1
0x140053d66  mov     dword ptr [rsp+98h+var_78], 8; int
0x140053d6e  lea     r9, [rsp+98h+var_38]
0x140053d73  mov     r8d, 0Bh
0x140053d79  mov     edx, dword ptr [rsp+98h+Size]; Size
0x140053d80  mov     rcx, [rsp+98h+Src]; Src
0x140053d85  call    EfsSetEfsStreamInfo
0x140053d8a  mov     ebx, eax
0x140053d8c  test    eax, eax
0x140053d8e  js      loc_140053C87
0x140053d94  lea     rax, [rsp+98h+var_50]
0x140053d99  mov     [rsp+98h+var_68], rax
0x140053d9e  mov     dword ptr [rsp+98h+var_70], 1
0x140053da6  mov     dword ptr [rsp+98h+var_78], 1
0x140053dae  mov     r9d, 100h
0x140053db4  lea     r8, DestinationString
0x140053dbb  mov     rdx, [rsp+98h+arg_10]
0x140053dc3  mov     rcx, r12
0x140053dc6  call    NtOfsCreateAttributeEx
0x140053dcb  mov     ebx, eax
0x140053dcd  mov     dword ptr [rsp+98h+var_58+4], eax
0x140053dd1  test    eax, eax
0x140053dd3  js      short loc_140053E2F
0x140053dd5  mov     r8d, dword ptr [rsp+98h+Size]
0x140053ddd  mov     rdx, [rsp+98h+var_50]
0x140053de2  mov     rcx, r12
0x140053de5  call    NtOfsSetLength
0x140053dea  mov     rax, [rsp+98h+Src]
0x140053def  mov     [rsp+98h+var_78], rax
0x140053df4  mov     r9d, dword ptr [rsp+98h+Size]
0x140053dfc  mov     rdx, [rsp+98h+var_50]
0x140053e01  mov     rcx, r12
0x140053e04  call    NtOfsPutData
0x140053e09  mov     rdx, [rsp+98h+var_50]
0x140053e0e  test    rdx, rdx
0x140053e11  jz      short loc_140053E24
0x140053e13  movzx   eax, word ptr [rdx]
0x140053e16  mov     ecx, 703h
0x140053e1b  sub     ax, cx
0x140053e1e  cmp     ax, 2
0x140053e22  jbe     short loc_140053E2F
0x140053e24  mov     rdx, [rsp+98h+var_50]
0x140053e29  call    NtOfsFlushAttribute
0x140053e2e  nop
0x140053e2f  mov     rdx, [rsp+98h+var_50]
0x140053e34  test    rdx, rdx
0x140053e37  jz      short loc_140053E41
0x140053e39  mov     rcx, r12
0x140053e3c  call    NtOfsCloseAttribute
0x140053e41  test    rdi, rdi
0x140053e44  jz      short loc_140053E59
0x140053e46  xor     edx, edx; Tag
0x140053e48  mov     rcx, rdi; P
0x140053e4b  call    cs:__imp_ExFreePoolWithTag
0x140053e52  nop     dword ptr [rax+rax+00h]
0x140053e57  xor     edi, edi
0x140053e59  test    ebx, ebx
0x140053e5b  jns     short loc_140053E75
0x140053e5d  mov     r9d, ebx
0x140053e60  mov     edx, 6
0x140053e65  mov     r8d, 896h
0x140053e6b  call    EfspTraceLogAssert
0x140053e70  jmp     loc_140053CC4
0x140053e75  test    dword ptr [r15+8], 8000000h
0x140053e7d  jz      loc_140053C87
0x140053e83  mov     rcx, [r15+18h]
0x140053e87  mov     edx, [rcx+8]
0x140053e8a  mov     ecx, [rcx+4]
0x140053e8d  call    GetKeyBlobBufferEx
0x140053e92  mov     rsi, rax
0x140053e95  test    rax, rax
0x140053e98  jnz     short loc_140053EA4
0x140053e9a  mov     ebx, 0C000009Ah
0x140053e9f  jmp     loc_140053C87
0x140053ea4  mov     r12, [rsp+98h+arg_28]
0x140053eac  mov     eax, [r12]
0x140053eb0  mov     dword ptr [rsp+98h+Size], eax
0x140053eb7  mov     r8, [r15+18h]
0x140053ebb  lea     rdx, [rsp+98h+Size]
0x140053ec3  mov     rcx, rsi
0x140053ec6  call    SetKeyTable
0x140053ecb  test    al, al
0x140053ecd  jnz     short loc_140053EDF
0x140053ecf  mov     ebx, 0C0000022h
0x140053ed4  mov     r8d, 8AEh
0x140053eda  jmp     loc_140053C7A
0x140053edf  mov     rcx, rsi
0x140053ee2  call    AllocateAndSetContextDataBlock
0x140053ee7  mov     r14, rax
0x140053eea  mov     [rsp+98h+var_30], rax
0x140053eef  test    rax, rax
0x140053ef2  jz      short loc_140053E9A
0x140053ef4  mov     eax, dword ptr [rsp+98h+Size]
0x140053efb  mov     [r12], eax
0x140053eff  mov     rax, [rsp+98h+arg_30]
0x140053f07  mov     [rax], r14
0x140053f0a  xor     r14d, r14d
0x140053f0d  mov     [rsp+98h+var_30], r14
0x140053f12  xor     esi, esi
0x140053f14  jmp     loc_140053C87
0x140060553  push    rbp
0x140060555  sub     rsp, 40h
0x140060559  mov     rbp, rdx
0x14006055c  mov     rdx, [rbp+48h]
0x140060560  test    rdx, rdx
0x140060563  jz      short loc_140060572
0x140060565  mov     rcx, [rbp+0B8h]
0x14006056c  call    NtOfsCloseAttribute
0x140060571  nop
0x140060572  mov     rcx, [rbp+58h]; P
0x140060576  test    rcx, rcx
0x140060579  jz      short loc_14006058A
0x14006057b  xor     edx, edx; Tag
0x14006057d  call    cs:__imp_ExFreePoolWithTag
0x140060584  nop     dword ptr [rax+rax+00h]
0x140060589  nop
0x14006058a  add     rsp, 40h
0x14006058e  pop     rbp
0x14006058f  retn
```
