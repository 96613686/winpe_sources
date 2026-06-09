# Compress

- ea: `0x1800064e8`
- end: `0x180006758`
- name: `Compress`
- size: `624`
- prototype: `HRESULT __stdcall(PVOID context, const BYTE *input_buffer, LONG input_buffer_size, PBYTE output_buffer, LONG output_buffer_size, PLONG input_used, PLONG output_used, INT compression_level)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180001dd8`
- `0x180002920`
- `0x180003458`
- `0x1800064e8`
- `0x180006760`
- `0x18000689c`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066ad`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800065a1`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800065a1`

## pseudocode

```c
HRESULT __stdcall Compress(
        PVOID context,
        const BYTE *input_buffer,
        LONG input_buffer_size,
        PBYTE output_buffer,
        LONG output_buffer_size,
        PLONG input_used,
        PLONG output_used,
        INT compression_level)
{
  __int64 v8; // rsi
  __int64 v10; // rbp
  HRESULT result; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r15d
  int v16; // ecx
  double v17; // xmm7_8
  double v18; // xmm0_8
  void (__fastcall *v19)(_QWORD, _QWORD, _QWORD); // rax
  _OWORD *v20; // r14
  __int64 v21; // rdx
  unsigned int (__fastcall *v22)(__int64, __int64, _QWORD); // r8
  unsigned int v23; // r9d
  unsigned int v24; // ecx
  int v25; // eax
  int v26; // r12d
  __int64 v27; // rdx
  void (__fastcall *v28)(_QWORD, __int64, _QWORD); // rax
  unsigned int v29; // eax
  _DWORD *v30; // rax
  _DWORD *v31; // rax

  v8 = *((_QWORD *)input_buffer + 1);
  v10 = *((_QWORD *)input_buffer + 3);
  result = CompressQuery(context, v10, v8);
  if ( !result )
  {
    if ( *((_DWORD *)context + 7) )
    {
      v15 = 0;
    }
    else
    {
      result = CompressQuery(v13, v10, v14);
      if ( result )
        return result;
      v15 = 1;
      *((_DWORD *)context + 7) = 1;
      result = CompressFrameBegin(v10, v8, (char *)context + 56, (char *)context + 64);
      if ( result )
        return result;
    }
    if ( *((_DWORD *)input_buffer + 16) == -1 )
      v16 = 2500;
    else
      v16 = 10000 - *((_DWORD *)input_buffer + 16);
    v17 = (double)v16 / 10000.0 * ((double)v16 / 10000.0) * ((double)v16 / 10000.0) * ((double)v16 / 10000.0);
    v18 = (double)MulDiv(v16, 100, *((_DWORD *)context + 6));
    v19 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))*((_QWORD *)context + 5);
    if ( v19 )
      v19(*((_QWORD *)context + 6), 0, 0);
    v20 = LocalAlloc(0x40u, 0xC0u);
    if ( v20 )
    {
      v21 = *((_QWORD *)context + 6);
      v22 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD))*((_QWORD *)context + 5);
      v23 = (int)(v17 * 32768.0);
      v24 = (int)(v18 / 10000.0 * (v18 / 10000.0) * (v18 / 10000.0) * (v18 / 10000.0) * 32768.0);
      if ( *(_WORD *)(v8 + 14) == 8 )
        v25 = CompressFrame8(
                *((_QWORD *)input_buffer + 3),
                *((_QWORD *)input_buffer + 4),
                *((_WORD **)input_buffer + 2),
                v23,
                v24,
                *((_QWORD *)input_buffer + 9),
                *((_QWORD *)input_buffer + 10),
                v22,
                v21,
                v20,
                *((_QWORD *)context + 7),
                (__int64)context + 64);
      else
        v25 = CompressFrame16(
                *((_QWORD *)input_buffer + 3),
                *((_QWORD *)input_buffer + 4),
                *((_WORD **)input_buffer + 2),
                v23,
                v24,
                *((_QWORD *)input_buffer + 9),
                *((_QWORD *)input_buffer + 10),
                v22,
                v21,
                v20);
      v26 = v25;
      LocalFree(v20);
      v28 = (void (__fastcall *)(_QWORD, __int64, _QWORD))*((_QWORD *)context + 5);
      if ( v28 )
        v28(*((_QWORD *)context + 6), 2, 0);
      if ( v26 == -1 )
      {
        return -100;
      }
      else
      {
        *(_DWORD *)(v8 + 4) = *(_DWORD *)(v10 + 4) & 0xFFFFFFFC;
        v29 = *(_DWORD *)(v10 + 8) & 0xFFFFFFFC;
        *(_DWORD *)(v8 + 16) = 1296126531;
        *(_DWORD *)(v8 + 8) = v29;
        *(_DWORD *)(v8 + 20) = v26;
        v30 = (_DWORD *)*((_QWORD *)input_buffer + 5);
        if ( v30 )
          *v30 = 25444;
        v31 = (_DWORD *)*((_QWORD *)input_buffer + 6);
        if ( v31 )
        {
          *v31 = 2;
          if ( !*((_QWORD *)input_buffer + 9) || !numberOfSkips )
            **((_DWORD **)input_buffer + 6) |= 0x10u;
        }
        if ( v15 )
          CompressEnd(context, v27);
        return 0;
      }
    }
    else
    {
      return -3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800064e8  push    rbx
0x1800064ea  push    rbp
0x1800064eb  push    rsi
0x1800064ec  push    rdi
0x1800064ed  push    r12
0x1800064ef  push    r14
0x1800064f1  push    r15
0x1800064f3  sub     rsp, 80h
0x1800064fa  mov     rsi, [rdx+8]
0x1800064fe  mov     rbx, rdx
0x180006501  mov     rbp, [rdx+18h]
0x180006505  mov     r8, rsi
0x180006508  mov     rdx, rbp
0x18000650b  movaps  [rsp+0B8h+var_48], xmm6
0x180006510  movaps  [rsp+0B8h+var_58], xmm7
0x180006515  mov     rdi, rcx
0x180006518  call    CompressQuery
0x18000651d  test    eax, eax
0x18000651f  jnz     loc_18000673C
0x180006525  cmp     [rdi+1Ch], eax
0x180006528  jz      short loc_18000652F
0x18000652a  xor     r15d, r15d
0x18000652d  jmp     short loc_180006562
0x18000652f  mov     rdx, rbp
0x180006532  call    CompressQuery
0x180006537  test    eax, eax
0x180006539  jnz     loc_18000673C
0x18000653f  lea     r15d, [rax+1]
0x180006543  mov     rdx, rsi
0x180006546  lea     r9, [rdi+40h]
0x18000654a  mov     [rdi+1Ch], r15d
0x18000654e  lea     r8, [rdi+38h]
0x180006552  mov     rcx, rbp
0x180006555  call    CompressFrameBegin
0x18000655a  test    eax, eax
0x18000655c  jnz     loc_18000673C
0x180006562  cmp     dword ptr [rbx+40h], 0FFFFFFFFh
0x180006566  jnz     short loc_18000656F
0x180006568  mov     ecx, 9C4h
0x18000656d  jmp     short loc_180006577
0x18000656f  mov     ecx, 2710h
0x180006574  sub     ecx, [rbx+40h]; nNumber
0x180006577  mov     r8d, [rdi+18h]; nDenominator
0x18000657b  xorps   xmm0, xmm0
0x18000657e  mov     eax, ecx
0x180006580  mov     edx, 64h ; 'd'; nNumerator
0x180006585  cvtsi2sd xmm0, rax
0x18000658a  divsd   xmm0, cs:__real@40c3880000000000
0x180006592  movaps  xmm7, xmm0
0x180006595  mulsd   xmm7, xmm0
0x180006599  mulsd   xmm7, xmm0
0x18000659d  mulsd   xmm7, xmm0
0x1800065a1  call    cs:__imp_MulDiv
0x1800065a7  xorps   xmm0, xmm0
0x1800065aa  mov     eax, eax
0x1800065ac  cvtsi2sd xmm0, rax
0x1800065b1  mov     rax, [rdi+28h]
0x1800065b5  divsd   xmm0, cs:__real@40c3880000000000
0x1800065bd  movaps  xmm6, xmm0
0x1800065c0  mulsd   xmm6, xmm0
0x1800065c4  mulsd   xmm6, xmm0
0x1800065c8  mulsd   xmm6, xmm0
0x1800065cc  test    rax, rax
0x1800065cf  jz      short loc_1800065DF
0x1800065d1  mov     rcx, [rdi+30h]
0x1800065d5  xor     r8d, r8d
0x1800065d8  xor     edx, edx
0x1800065da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065df  mov     edx, 0C0h; uBytes
0x1800065e4  lea     ecx, [rdx-80h]; uFlags
0x1800065e7  call    cs:__imp_LocalAlloc
0x1800065ed  mov     r14, rax
0x1800065f0  test    rax, rax
0x1800065f3  jnz     short loc_1800065FE
0x1800065f5  lea     eax, [r14-3]
0x1800065f9  jmp     loc_18000673C
0x1800065fe  cmp     word ptr [rsi+0Eh], 8
0x180006603  mulsd   xmm7, cs:__real@40e0000000000000
0x18000660b  mov     rdx, [rdi+30h]
0x18000660f  mulsd   xmm6, cs:__real@40e0000000000000
0x180006617  mov     r8, [rdi+28h]
0x18000661b  cvttsd2si r9, xmm7
0x180006620  cvttsd2si rcx, xmm6
0x180006625  jnz     short loc_180006671
0x180006627  lea     rax, [rdi+40h]
0x18000662b  mov     [rsp+0B8h+var_60], rax
0x180006630  mov     rax, [rdi+38h]
0x180006634  mov     [rsp+0B8h+var_68], rax
0x180006639  mov     rax, [rbx+50h]
0x18000663d  mov     [rsp+0B8h+var_70], r14
0x180006642  mov     [rsp+0B8h+var_78], rdx
0x180006647  mov     rdx, [rbx+20h]
0x18000664b  mov     [rsp+0B8h+var_80], r8
0x180006650  mov     r8, [rbx+10h]
0x180006654  mov     [rsp+0B8h+var_88], rax
0x180006659  mov     rax, [rbx+48h]
0x18000665d  mov     [rsp+0B8h+var_90], rax
0x180006662  mov     [rsp+0B8h+var_98], ecx
0x180006666  mov     rcx, [rbx+18h]
0x18000666a  call    CompressFrame8
0x18000666f  jmp     short loc_1800066A7
0x180006671  mov     rax, [rbx+50h]
0x180006675  mov     [rsp+0B8h+var_70], r14
0x18000667a  mov     [rsp+0B8h+var_78], rdx
0x18000667f  mov     rdx, [rbx+20h]
0x180006683  mov     [rsp+0B8h+var_80], r8
0x180006688  mov     r8, [rbx+10h]
0x18000668c  mov     [rsp+0B8h+var_88], rax
0x180006691  mov     rax, [rbx+48h]
0x180006695  mov     [rsp+0B8h+var_90], rax
0x18000669a  mov     [rsp+0B8h+var_98], ecx
0x18000669e  mov     rcx, [rbx+18h]
0x1800066a2  call    CompressFrame16
0x1800066a7  mov     rcx, r14; hMem
0x1800066aa  mov     r12d, eax
0x1800066ad  call    cs:__imp_LocalFree
0x1800066b3  mov     rax, [rdi+28h]
0x1800066b7  mov     r14d, 2
0x1800066bd  test    rax, rax
0x1800066c0  jz      short loc_1800066D1
0x1800066c2  mov     rcx, [rdi+30h]
0x1800066c6  xor     r8d, r8d
0x1800066c9  mov     edx, r14d
0x1800066cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d1  cmp     r12d, 0FFFFFFFFh
0x1800066d5  jnz     short loc_1800066DE
0x1800066d7  lea     eax, [r12-63h]
0x1800066dc  jmp     short loc_18000673C
0x1800066de  mov     eax, [rbp+4]
0x1800066e1  and     eax, 0FFFFFFFCh
0x1800066e4  mov     [rsi+4], eax
0x1800066e7  mov     eax, [rbp+8]
0x1800066ea  and     eax, 0FFFFFFFCh
0x1800066ed  mov     dword ptr [rsi+10h], 4D415243h
0x1800066f4  mov     [rsi+8], eax
0x1800066f7  mov     [rsi+14h], r12d
0x1800066fb  mov     rax, [rbx+28h]
0x1800066ff  test    rax, rax
0x180006702  jz      short loc_18000670A
0x180006704  mov     dword ptr [rax], 6364h
0x18000670a  mov     rax, [rbx+30h]
0x18000670e  test    rax, rax
0x180006711  jz      short loc_18000672D
0x180006713  mov     [rax], r14d
0x180006716  cmp     qword ptr [rbx+48h], 0
0x18000671b  jz      short loc_180006726
0x18000671d  cmp     cs:numberOfSkips, 0
0x180006724  jnz     short loc_18000672D
0x180006726  mov     rax, [rbx+30h]
0x18000672a  or      dword ptr [rax], 10h
0x18000672d  test    r15d, r15d
0x180006730  jz      short loc_18000673A
0x180006732  mov     rcx, rdi
0x180006735  call    CompressEnd
0x18000673a  xor     eax, eax
0x18000673c  movaps  xmm6, [rsp+0B8h+var_48]
0x180006741  movaps  xmm7, [rsp+0B8h+var_58]
0x180006746  add     rsp, 80h
0x18000674d  pop     r15
0x18000674f  pop     r14
0x180006751  pop     r12
0x180006753  pop     rdi
0x180006754  pop     rsi
0x180006755  pop     rbp
0x180006756  pop     rbx
0x180006757  retn
```
