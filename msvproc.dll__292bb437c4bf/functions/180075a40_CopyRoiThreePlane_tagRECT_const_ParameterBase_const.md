# CopyRoiThreePlane(tagRECT const &,ParameterBase const *)

- ea: `0x180075a40`
- end: `0x180075c44`
- name: `?CopyRoiThreePlane@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180075a40`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180075adb`
- `MFPlat!MFCopyImage` at `0x180075bc9`
- `MFPlat!MFCopyImage` at `0x180075c2b`
- `MFPlat!MFCopyImage` at `0x180075adb`
- `MFPlat!MFCopyImage` at `0x180075bc9`
- `MFPlat!MFCopyImage` at `0x180075c2b`

## pseudocode

```c
__int64 __fastcall CopyRoiThreePlane(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  LONG v3; // r15d
  __int64 v4; // r12
  __int64 v5; // r13
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  DWORD dwLines; // r14d
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rbp
  DWORD dwWidthInBytes; // edi
  int v13; // ecx
  int v14; // r8d
  LONG v15; // r9d
  DWORD v16; // eax
  int v17; // r14d
  int v18; // eax
  int v19; // r15d
  int lSrcStride; // [rsp+30h] [rbp-68h]
  __int64 v22; // [rsp+38h] [rbp-60h]
  __int64 v23; // [rsp+40h] [rbp-58h]
  int v24; // [rsp+A0h] [rbp+8h]
  LONG lDestStride; // [rsp+A8h] [rbp+10h]
  int lDestStridea; // [rsp+A8h] [rbp+10h]
  int v27; // [rsp+B0h] [rbp+18h]
  __int64 v28; // [rsp+B0h] [rbp+18h]
  LONG top; // [rsp+B8h] [rbp+20h]
  __int64 v30; // [rsp+B8h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 6);
  v4 = *((_QWORD *)a2 + 2);
  v5 = *(_QWORD *)a2;
  v6 = *((_DWORD *)a2 + 24);
  v7 = *((_DWORD *)a2 + 26);
  v8 = *((_DWORD *)a2 + 25);
  dwLines = *((_DWORD *)a2 + 28) - v7;
  v27 = v7;
  v10 = (unsigned __int64)(unsigned int)(v6 * v8) >> 3;
  v11 = (unsigned __int64)(unsigned int)(a1->left * v6) >> 3;
  dwWidthInBytes = (unsigned int)(v6 * (*((_DWORD *)a2 + 27) - v8)) >> 3;
  lDestStride = *((_DWORD *)a2 + 2);
  top = a1->top;
  if ( !MFCopyImage(
          (BYTE *)(*(_QWORD *)a2 + v11 + lDestStride * top),
          lDestStride,
          (const BYTE *)(v4 + v10 + v3 * v7),
          v3,
          dwWidthInBytes,
          dwLines) )
  {
    v13 = *((_DWORD *)a2 + 21);
    if ( v13 > 0 )
    {
      v14 = *((_DWORD *)a2 + 22);
      if ( v14 > 0 )
      {
        v15 = lDestStride;
        v16 = dwLines;
        v17 = *((_DWORD *)a2 + 7);
        v24 = v16 / v14;
        lSrcStride = v3 / v13;
        lDestStridea = lDestStride / v13;
        v22 = v3 / v13 * (v27 / v14);
        v18 = v3 * v17;
        v19 = *((_DWORD *)a2 + 3);
        v28 = v18;
        v30 = lDestStridea * (top / v14);
        v23 = v15 * v19;
        if ( !MFCopyImage(
                (BYTE *)(v5 + v30 + v23 + v11),
                lDestStridea,
                (const BYTE *)(v4 + v22 + v10 + v18),
                lSrcStride,
                dwWidthInBytes / v13,
                v24) )
          MFCopyImage(
            (BYTE *)(v5 + v30 + v11 + v23 + lDestStridea * v19),
            lDestStridea,
            (const BYTE *)(v4 + v22 + v10 + v28 + lSrcStride * v17),
            lSrcStride,
            dwWidthInBytes / *((_DWORD *)a2 + 21),
            v24);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180075a40  push    rbx
0x180075a42  push    rbp
0x180075a43  push    rsi
0x180075a44  push    rdi
0x180075a45  push    r12
0x180075a47  push    r13
0x180075a49  push    r14
0x180075a4b  push    r15
0x180075a4d  sub     rsp, 58h
0x180075a51  mov     r10d, [rcx+4]
0x180075a55  mov     rbx, rdx
0x180075a58  mov     r15d, [rdx+18h]
0x180075a5c  mov     r12, [rdx+10h]
0x180075a60  mov     r13, [rdx]
0x180075a63  mov     r8d, [rbx+60h]
0x180075a67  mov     r9d, [rbx+68h]
0x180075a6b  mov     eax, [rbx+64h]
0x180075a6e  mov     edx, [rdx+8]; lDestStride
0x180075a71  mov     edi, [rbx+6Ch]
0x180075a74  mov     r14d, [rbx+70h]
0x180075a78  sub     edi, eax
0x180075a7a  imul    eax, r8d
0x180075a7e  sub     r14d, r9d
0x180075a81  imul    edi, r8d
0x180075a85  imul    r8d, [rcx]
0x180075a89  mov     dword ptr [rsp+98h+arg_10], r9d
0x180075a91  mov     [rsp+98h+dwLines], r14d; dwLines
0x180075a96  mov     esi, eax
0x180075a98  mov     eax, r9d
0x180075a9b  imul    eax, r15d
0x180075a9f  mov     r9d, r15d; lSrcStride
0x180075aa2  mov     ebp, r8d
0x180075aa5  shr     rsi, 3
0x180075aa9  shr     rbp, 3
0x180075aad  shr     edi, 3
0x180075ab0  movsxd  r8, eax
0x180075ab3  mov     eax, r10d
0x180075ab6  imul    eax, edx
0x180075ab9  add     r8, rsi
0x180075abc  add     r8, r12; pSrc
0x180075abf  mov     [rsp+98h+lDestStride], edx
0x180075ac6  mov     dword ptr [rsp+98h+arg_18], r10d
0x180075ace  mov     [rsp+98h+dwWidthInBytes], edi; dwWidthInBytes
0x180075ad2  movsxd  rcx, eax
0x180075ad5  add     rcx, rbp
0x180075ad8  add     rcx, r13; pDest
0x180075adb  call    cs:__imp_MFCopyImage
0x180075ae1  test    eax, eax
0x180075ae3  jnz     loc_180075C31
0x180075ae9  mov     ecx, [rbx+54h]
0x180075aec  test    ecx, ecx
0x180075aee  jle     loc_180075C31
0x180075af4  mov     r8d, [rbx+58h]
0x180075af8  test    r8d, r8d
0x180075afb  jle     loc_180075C31
0x180075b01  mov     r9d, [rsp+98h+lDestStride]
0x180075b09  xor     edx, edx
0x180075b0b  mov     eax, r14d
0x180075b0e  mov     r14d, [rbx+1Ch]
0x180075b12  div     r8d
0x180075b15  mov     [rsp+98h+arg_0], eax
0x180075b1c  mov     eax, r15d
0x180075b1f  cdq
0x180075b20  idiv    ecx
0x180075b22  mov     r10d, eax
0x180075b25  mov     [rsp+98h+lSrcStride], eax
0x180075b29  mov     eax, r9d
0x180075b2c  cdq
0x180075b2d  idiv    ecx
0x180075b2f  mov     r11d, eax
0x180075b32  mov     [rsp+98h+lDestStride], eax
0x180075b39  mov     eax, dword ptr [rsp+98h+arg_10]
0x180075b40  cdq
0x180075b41  idiv    r8d
0x180075b44  imul    eax, r10d
0x180075b48  cdqe
0x180075b4a  mov     [rsp+98h+var_60], rax
0x180075b4f  mov     eax, r14d
0x180075b52  imul    eax, r15d
0x180075b56  mov     r15d, [rbx+0Ch]
0x180075b5a  cdqe
0x180075b5c  mov     [rsp+98h+arg_10], rax
0x180075b64  mov     eax, dword ptr [rsp+98h+arg_18]
0x180075b6b  cdq
0x180075b6c  idiv    r8d
0x180075b6f  mov     r8, [rsp+98h+arg_10]
0x180075b77  xor     edx, edx
0x180075b79  imul    eax, r11d
0x180075b7d  add     r8, rsi
0x180075b80  add     r8, [rsp+98h+var_60]
0x180075b85  add     r8, r12; pSrc
0x180075b88  cdqe
0x180075b8a  mov     [rsp+98h+arg_18], rax
0x180075b92  mov     eax, r15d
0x180075b95  imul    eax, r9d
0x180075b99  movsxd  r9, eax
0x180075b9c  mov     eax, edi
0x180075b9e  div     ecx
0x180075ba0  mov     edx, [rsp+98h+arg_0]
0x180075ba7  lea     rcx, [r9+rbp]
0x180075bab  add     rcx, [rsp+98h+arg_18]
0x180075bb3  mov     [rsp+98h+dwLines], edx; dwLines
0x180075bb7  add     rcx, r13; pDest
0x180075bba  mov     [rsp+98h+var_58], r9
0x180075bbf  mov     edx, r11d; lDestStride
0x180075bc2  mov     r9d, r10d; lSrcStride
0x180075bc5  mov     [rsp+98h+dwWidthInBytes], eax; dwWidthInBytes
0x180075bc9  call    cs:__imp_MFCopyImage
0x180075bcf  test    eax, eax
0x180075bd1  jnz     short loc_180075C31
0x180075bd3  mov     r9d, [rsp+98h+lSrcStride]; lSrcStride
0x180075bd8  xor     edx, edx
0x180075bda  mov     r10d, [rsp+98h+arg_0]
0x180075be2  mov     eax, edi
0x180075be4  div     dword ptr [rbx+54h]
0x180075be7  mov     edx, [rsp+98h+lDestStride]; lDestStride
0x180075bee  imul    r14d, r9d
0x180075bf2  imul    r15d, edx
0x180075bf6  mov     [rsp+98h+dwLines], r10d; dwLines
0x180075bfb  mov     [rsp+98h+dwWidthInBytes], eax; dwWidthInBytes
0x180075bff  movsxd  r8, r14d
0x180075c02  add     r8, [rsp+98h+arg_10]
0x180075c0a  add     r8, rsi
0x180075c0d  movsxd  rcx, r15d
0x180075c10  add     rcx, [rsp+98h+var_58]
0x180075c15  add     r8, [rsp+98h+var_60]
0x180075c1a  add     rcx, rbp
0x180075c1d  add     rcx, [rsp+98h+arg_18]
0x180075c25  add     r8, r12; pSrc
0x180075c28  add     rcx, r13; pDest
0x180075c2b  call    cs:__imp_MFCopyImage
0x180075c31  xor     eax, eax
0x180075c33  add     rsp, 58h
0x180075c37  pop     r15
0x180075c39  pop     r14
0x180075c3b  pop     r13
0x180075c3d  pop     r12
0x180075c3f  pop     rdi
0x180075c40  pop     rsi
0x180075c41  pop     rbp
0x180075c42  pop     rbx
0x180075c43  retn
```
