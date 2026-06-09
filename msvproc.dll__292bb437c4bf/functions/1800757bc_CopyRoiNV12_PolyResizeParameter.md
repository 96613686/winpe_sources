# CopyRoiNV12(PolyResizeParameter *)

- ea: `0x1800757bc`
- end: `0x1800758e8`
- name: `?CopyRoiNV12@@YAXPEAUPolyResizeParameter@@@Z`
- size: `300`
- prototype: `void __fastcall(struct PolyResizeParameter *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025cf0`

## callees

- `0x1800757bc`
- `0x1800cfecc`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18007587a`
- `MFPlat!MFCopyImage` at `0x1800758d1`
- `MFPlat!MFCopyImage` at `0x18007587a`
- `MFPlat!MFCopyImage` at `0x1800758d1`

## pseudocode

```c
void __fastcall CopyRoiNV12(struct PolyResizeParameter *a1)
{
  const void *v1; // r9
  BYTE *v2; // r10
  LONG v3; // r12d
  DWORD dwWidthInBytes; // r15d
  int v5; // edx
  LONG v6; // r14d
  DWORD dwLines; // ebp
  int v8; // r13d
  int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rdi
  int v12; // [rsp+80h] [rbp+8h]
  int v13; // [rsp+88h] [rbp+10h]
  __int64 v14; // [rsp+90h] [rbp+18h]
  BYTE *v15; // [rsp+98h] [rbp+20h]

  v1 = *(const void **)a1;
  v2 = (BYTE *)*((_QWORD *)a1 + 1);
  v3 = *((_DWORD *)a1 + 9);
  dwWidthInBytes = *((_DWORD *)a1 + 6);
  v5 = *((_DWORD *)a1 + 11);
  v6 = *((_DWORD *)a1 + 15);
  dwLines = *((_DWORD *)a1 + 7);
  v8 = *((_DWORD *)a1 + 5);
  v9 = *((_DWORD *)a1 + 14);
  v14 = *(_QWORD *)a1;
  v15 = v2;
  v13 = v5;
  v12 = *((_DWORD *)a1 + 8);
  if ( dwWidthInBytes == v3 && dwWidthInBytes == v6 && !v8 && !v5 && v9 == dwLines && *((_DWORD *)a1 + 8) == dwLines )
  {
    memcpy_0(v2, v1, (unsigned __int64)(unsigned int)(3 * v6 * v9) >> 1);
  }
  else
  {
    v10 = *((int *)a1 + 4);
    v11 = *((int *)a1 + 10);
    MFCopyImage(&v2[v11 + v6 * v5], v6, (const BYTE *)v1 + v10 + v3 * v8, v3, dwWidthInBytes, dwLines);
    MFCopyImage(
      &v15[v11 + (unsigned int)(v6 * (v9 + v13 / 2))],
      v6,
      (const BYTE *)(v14 + v10 + (unsigned int)(v3 * (v12 + v8 / 2))),
      v3,
      dwWidthInBytes,
      dwLines >> 1);
  }
}

```

## disassembly

```asm
0x1800757bc  push    rbx
0x1800757be  push    rbp
0x1800757bf  push    rsi
0x1800757c0  push    rdi
0x1800757c1  push    r12
0x1800757c3  push    r13
0x1800757c5  push    r14
0x1800757c7  push    r15
0x1800757c9  sub     rsp, 38h
0x1800757cd  mov     r9, [rcx]
0x1800757d0  mov     r10, [rcx+8]
0x1800757d4  mov     r12d, [rcx+24h]
0x1800757d8  mov     r15d, [rcx+18h]
0x1800757dc  mov     edx, [rcx+2Ch]
0x1800757df  mov     eax, [rcx+20h]
0x1800757e2  mov     r14d, [rcx+3Ch]
0x1800757e6  mov     ebp, [rcx+1Ch]
0x1800757e9  mov     r13d, [rcx+14h]
0x1800757ed  mov     esi, [rcx+38h]
0x1800757f0  mov     [rsp+78h+arg_10], r9
0x1800757f8  mov     [rsp+78h+arg_18], r10
0x180075800  mov     [rsp+78h+arg_8], edx
0x180075807  mov     [rsp+78h+arg_0], eax
0x18007580e  cmp     r15d, r12d
0x180075811  jnz     short loc_180075844
0x180075813  cmp     r15d, r14d
0x180075816  jnz     short loc_180075844
0x180075818  test    r13d, r13d
0x18007581b  jnz     short loc_180075844
0x18007581d  test    edx, edx
0x18007581f  jnz     short loc_180075844
0x180075821  cmp     esi, ebp
0x180075823  jnz     short loc_180075844
0x180075825  cmp     eax, ebp
0x180075827  jnz     short loc_180075844
0x180075829  imul    esi, r14d
0x18007582d  mov     rdx, r9; Src
0x180075830  mov     rcx, r10; void *
0x180075833  lea     r8d, [rsi+rsi*2]
0x180075837  shr     r8, 1; Size
0x18007583a  call    memcpy_0
0x18007583f  jmp     loc_1800758D7
0x180075844  movsxd  rbx, dword ptr [rcx+10h]
0x180075848  mov     eax, r13d
0x18007584b  movsxd  rdi, dword ptr [rcx+28h]
0x18007584f  mov     ecx, edx
0x180075851  imul    ecx, r14d
0x180075855  mov     edx, r14d; lDestStride
0x180075858  imul    eax, r12d
0x18007585c  mov     [rsp+78h+dwLines], ebp; dwLines
0x180075860  mov     [rsp+78h+dwWidthInBytes], r15d; dwWidthInBytes
0x180075865  movsxd  rcx, ecx
0x180075868  movsxd  r8, eax
0x18007586b  add     rcx, rdi
0x18007586e  add     r8, rbx
0x180075871  add     rcx, r10; pDest
0x180075874  add     r8, r9; pSrc
0x180075877  mov     r9d, r12d; lSrcStride
0x18007587a  call    cs:__imp_MFCopyImage
0x180075880  mov     ecx, 2
0x180075885  shr     ebp, 1
0x180075887  mov     eax, r13d
0x18007588a  mov     [rsp+78h+dwLines], ebp; dwLines
0x18007588e  cdq
0x18007588f  mov     [rsp+78h+dwWidthInBytes], r15d; dwWidthInBytes
0x180075894  idiv    ecx
0x180075896  mov     r9d, r12d; lSrcStride
0x180075899  add     eax, [rsp+78h+arg_0]
0x1800758a0  imul    eax, r12d
0x1800758a4  mov     r8d, eax
0x1800758a7  mov     eax, [rsp+78h+arg_8]
0x1800758ae  add     r8, rbx
0x1800758b1  add     r8, [rsp+78h+arg_10]; pSrc
0x1800758b9  cdq
0x1800758ba  idiv    ecx
0x1800758bc  mov     edx, r14d; lDestStride
0x1800758bf  lea     ecx, [rsi+rax]
0x1800758c2  imul    ecx, r14d
0x1800758c6  add     rcx, rdi
0x1800758c9  add     rcx, [rsp+78h+arg_18]; pDest
0x1800758d1  call    cs:__imp_MFCopyImage
0x1800758d7  add     rsp, 38h
0x1800758db  pop     r15
0x1800758dd  pop     r14
0x1800758df  pop     r13
0x1800758e1  pop     r12
0x1800758e3  pop     rdi
0x1800758e4  pop     rsi
0x1800758e5  pop     rbp
0x1800758e6  pop     rbx
0x1800758e7  retn
```
