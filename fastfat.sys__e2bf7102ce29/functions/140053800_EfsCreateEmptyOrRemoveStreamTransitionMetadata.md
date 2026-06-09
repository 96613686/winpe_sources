# EfsCreateEmptyOrRemoveStreamTransitionMetadata

- ea: `0x140053800`
- end: `0x1400538d6`
- name: `EfsCreateEmptyOrRemoveStreamTransitionMetadata`
- size: `214`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140053c18`
- `0x140054480`

## callees

- `0x140050ae0`
- `0x140053800`
- `0x1400558c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400538a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400538bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400538a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400538bc`

## pseudocode

```c
__int64 __fastcall EfsCreateEmptyOrRemoveStreamTransitionMetadata(
        void *Src,
        size_t Size,
        char a3,
        char a4,
        _QWORD *a5,
        _DWORD *a6)
{
  unsigned int v7; // esi
  int StreamTransitionMetadata; // edi
  void *v10; // rbx
  PVOID P[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int128 v14; // [rsp+50h] [rbp-10h]

  v7 = Size;
  *(_OWORD *)P = 0;
  v13 = 0;
  v14 = 0;
  if ( a3 )
  {
    StreamTransitionMetadata = EfspCreateStreamTransitionMetadata(
                                 0,
                                 Size,
                                 (__int64 *)&P[1],
                                 (__int64 *)&v13,
                                 (unsigned int *)&v13 + 2);
    if ( StreamTransitionMetadata < 0 )
      goto LABEL_7;
    if ( a4 )
      *((_DWORD *)P[1] + 3) |= 1u;
  }
  StreamTransitionMetadata = EfsSetEfsStreamInfo(Src, v7, 48);
  if ( StreamTransitionMetadata >= 0 )
  {
    v10 = 0;
    *a5 = v14;
    *a6 = DWORD2(v14);
    goto LABEL_8;
  }
LABEL_7:
  v10 = (void *)v14;
LABEL_8:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)StreamTransitionMetadata;
}

```

## disassembly

```asm
0x140053800  push    rbp
0x140053802  push    rbx
0x140053803  push    rsi
0x140053804  push    rdi
0x140053805  push    r14
0x140053807  mov     rbp, rsp
0x14005380a  sub     rsp, 60h
0x14005380e  xorps   xmm0, xmm0
0x140053811  mov     bl, r9b
0x140053814  mov     esi, edx
0x140053816  mov     r14, rcx
0x140053819  movups  xmmword ptr [rbp+P], xmm0
0x14005381d  movups  [rbp+var_20], xmm0
0x140053821  movups  [rbp+var_10], xmm0
0x140053825  test    r8b, r8b
0x140053828  jz      short loc_140053856
0x14005382a  lea     rax, [rbp+var_20+8]
0x14005382e  xor     ecx, ecx
0x140053830  lea     r9, [rbp+var_20]
0x140053834  mov     qword ptr [rsp+60h+var_40], rax
0x140053839  lea     r8, [rbp+P+8]
0x14005383d  call    EfspCreateStreamTransitionMetadata
0x140053842  mov     edi, eax
0x140053844  test    eax, eax
0x140053846  js      short loc_140053897
0x140053848  test    bl, bl
0x14005384a  jz      short loc_14005385D
0x14005384c  mov     rax, [rbp+P+8]
0x140053850  or      dword ptr [rax+0Ch], 1
0x140053854  jmp     short loc_14005385D
0x140053856  mov     dword ptr [rbp+P], 3
0x14005385d  lea     r9, [rbp+P]
0x140053861  mov     [rsp+60h+var_40], 30h ; '0'; int
0x140053869  mov     r8d, 0Ah
0x14005386f  mov     edx, esi; Size
0x140053871  mov     rcx, r14; Src
0x140053874  call    EfsSetEfsStreamInfo
0x140053879  mov     edi, eax
0x14005387b  test    eax, eax
0x14005387d  js      short loc_140053897
0x14005387f  mov     rcx, [rbp+arg_20]
0x140053883  xor     ebx, ebx
0x140053885  mov     rax, qword ptr [rbp+var_10]
0x140053889  mov     [rcx], rax
0x14005388c  mov     rcx, [rbp+arg_28]
0x140053890  mov     eax, dword ptr [rbp+var_10+8]
0x140053893  mov     [rcx], eax
0x140053895  jmp     short loc_14005389B
0x140053897  mov     rbx, qword ptr [rbp+var_10]
0x14005389b  mov     rcx, [rbp+P+8]; P
0x14005389f  test    rcx, rcx
0x1400538a2  jz      short loc_1400538B2
0x1400538a4  xor     edx, edx; Tag
0x1400538a6  call    cs:__imp_ExFreePoolWithTag
0x1400538ad  nop     dword ptr [rax+rax+00h]
0x1400538b2  test    rbx, rbx
0x1400538b5  jz      short loc_1400538C8
0x1400538b7  xor     edx, edx; Tag
0x1400538b9  mov     rcx, rbx; P
0x1400538bc  call    cs:__imp_ExFreePoolWithTag
0x1400538c3  nop     dword ptr [rax+rax+00h]
0x1400538c8  mov     eax, edi
0x1400538ca  add     rsp, 60h
0x1400538ce  pop     r14
0x1400538d0  pop     rdi
0x1400538d1  pop     rsi
0x1400538d2  pop     rbx
0x1400538d3  pop     rbp
0x1400538d4  retn
```
