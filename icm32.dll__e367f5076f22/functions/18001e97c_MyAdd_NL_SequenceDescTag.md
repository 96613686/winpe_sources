# MyAdd_NL_SequenceDescTag

- ea: `0x18001e97c`
- end: `0x18001edcb`
- name: `MyAdd_NL_SequenceDescTag`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001e1ec`

## callees

- `0x1800042e0`
- `0x18000604c`
- `0x180018abc`
- `0x180018b68`
- `0x18001e97c`
- `0x18003d002`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `ntdll!RtlLogUnexpectedCodepath` at `0x18001edc0`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18001edc0`

## pseudocode

```c
__int64 __fastcall MyAdd_NL_SequenceDescTag(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  const void *v7; // r14
  _OWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rsi
  unsigned int v11; // ebx
  int v12; // edx
  __int128 v13; // xmm6
  __int128 v14; // xmm7
  __int128 v15; // xmm8
  __int128 v16; // xmm9
  __int128 v17; // xmm10
  __int128 v18; // xmm11
  __int64 v19; // r12
  int v20; // eax
  unsigned int v21; // ecx
  void *v22; // rax
  void *v23; // rax
  int v24; // eax
  DWORD pcbElement; // [rsp+38h] [rbp-D0h] BYREF
  int v27; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v28; // [rsp+40h] [rbp-C8h]
  int v29; // [rsp+44h] [rbp-C4h]
  _OWORD v30[4]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v31[26]; // [rsp+88h] [rbp-80h]
  _DWORD *v32; // [rsp+A8h] [rbp-60h] BYREF
  int v33; // [rsp+B0h] [rbp-58h]
  __int64 v34; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp-48h]
  _BYTE v36[48]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v37; // [rsp+F8h] [rbp-10h]
  unsigned int v38; // [rsp+FCh] [rbp-Ch]
  unsigned int v39; // [rsp+100h] [rbp-8h]
  unsigned int v40; // [rsp+104h] [rbp-4h]

  v4 = a3;
  v32 = a4;
  LOWORD(v27) = 0;
  memset_0(v36, 0, 0x80u);
  pcbElement = 0;
  v34 = 0;
  v35 = 0;
  v7 = 0;
  memset_0(v30, 0, 0x5Au);
  *(_QWORD *)a2 = 1902474096;
  v8 = (_OWORD *)(a2 + 12);
  *(_DWORD *)(a2 + 8) = _byteswap_ulong(*(unsigned __int16 *)(a1 + 2));
  v9 = *(unsigned __int16 *)(a1 + 2);
  *(_QWORD *)&v30[0] = 1668506980;
  DWORD2(v30[0]) = 0x1000000;
  v10 = v4 - 20 * v9 - 12;
  if ( v10 >= 180 * v9 )
  {
    v12 = 0;
    v11 = 0;
    v29 = 0;
    if ( (_WORD)v9 )
    {
      v13 = *(_OWORD *)&v31[10];
      v14 = *(_OWORD *)v31;
      v15 = v30[3];
      v16 = v30[2];
      v17 = v30[1];
      v18 = v30[0];
      do
      {
        v19 = v12;
        v11 = CMGetProfileHeader(*(_QWORD *)(a1 + 8LL * v12 + 8), v36);
        if ( v11 )
          goto LABEL_30;
        v28 = 0;
        *(_DWORD *)v8 = ((v37 & 0xFF00 | (v37 << 16)) << 8) | ((HIWORD(v37) | v37 & 0xFF0000) >> 8);
        *((_DWORD *)v8 + 1) = ((v38 & 0xFF00 | (v38 << 16)) << 8) | ((HIWORD(v38) | v38 & 0xFF0000) >> 8);
        *((_DWORD *)v8 + 2) = ((v39 & 0xFF00 | (v39 << 16)) << 8) | ((HIWORD(v39) | v39 & 0xFF0000) >> 8);
        *((_DWORD *)v8 + 3) = ((v40 & 0xFF00 | (v40 << 16)) << 8) | ((HIWORD(v40) | v40 & 0xFF0000) >> 8);
        if ( (unsigned int)CMGetPartialProfileElement(*(HPROFILE *)(a1 + 8 * v19 + 8), 0x74656368u, 0, &pcbElement, 0)
          || pcbElement != 4 )
        {
          v21 = v28;
        }
        else
        {
          v20 = CMGetPartialProfileElement(*(HPROFILE *)(a1 + 8 * v19 + 8), 0x74656368u, 0, &pcbElement, &v34);
          v21 = v11;
          if ( !v20 )
            v21 = v35;
        }
        *((_DWORD *)v8 + 4) = v21;
        v8 = (_OWORD *)((char *)v8 + 20);
        if ( (unsigned int)CMGetPartialProfileElement(*(HPROFILE *)(a1 + 8 * v19 + 8), 0x646D6E64u, 0, &pcbElement, 0) )
        {
          v10 -= 90;
          if ( v10 < 0 )
          {
            HIDWORD(v32) = 1;
            goto LABEL_33;
          }
          *v8 = v18;
          v8[1] = v17;
          v8[2] = v16;
          v8[3] = v15;
          v8[4] = v14;
          *(_OWORD *)((char *)v8 + 74) = v13;
          v8 = (_OWORD *)((char *)v8 + 90);
        }
        else
        {
          v22 = (void *)SmartNewPtr(pcbElement, &v27);
          v11 = (__int16)v27;
          v7 = v22;
          if ( (_WORD)v27 )
            goto LABEL_30;
          if ( !(unsigned int)CMGetPartialProfileElement(
                                *(HPROFILE *)(a1 + 8 * v19 + 8),
                                0x646D6E64u,
                                0,
                                &pcbElement,
                                v22) )
          {
            v10 -= pcbElement;
            if ( v10 < 0 )
              goto LABEL_2;
            memmove_0(v8, v7, (int)pcbElement);
            v8 = (_OWORD *)((char *)v8 + pcbElement);
          }
          v7 = (const void *)DisposeIfPtr(v7);
        }
        if ( (unsigned int)CMGetPartialProfileElement(*(HPROFILE *)(a1 + 8 * v19 + 8), 0x646D6464u, 0, &pcbElement, 0) )
        {
          v10 -= 90;
          if ( v10 < 0 )
          {
            HIDWORD(v32) = 2;
LABEL_33:
            LODWORD(v32) = 49538476;
            v33 = 87;
            RtlLogUnexpectedCodepath(&v32);
            goto LABEL_2;
          }
          *v8 = v18;
          v8[1] = v17;
          v8[2] = v16;
          v8[3] = v15;
          v8[4] = v14;
          *(_OWORD *)((char *)v8 + 74) = v13;
          v8 = (_OWORD *)((char *)v8 + 90);
        }
        else
        {
          v23 = (void *)SmartNewPtr(pcbElement, &v27);
          v11 = (__int16)v27;
          v7 = v23;
          if ( (_WORD)v27 )
            goto LABEL_30;
          if ( !(unsigned int)CMGetPartialProfileElement(
                                *(HPROFILE *)(a1 + 8 * v19 + 8),
                                0x646D6464u,
                                0,
                                &pcbElement,
                                v23) )
          {
            v10 -= pcbElement;
            if ( v10 < 0 )
              goto LABEL_2;
            memmove_0(v8, v7, (int)pcbElement);
            v8 = (_OWORD *)((char *)v8 + pcbElement);
          }
          v7 = (const void *)DisposeIfPtr(v7);
        }
        v24 = *(unsigned __int16 *)(a1 + 2);
        v12 = v29 + 1;
        v29 = v12;
      }
      while ( v12 < v24 );
    }
    *v32 = (_DWORD)v8 - a2;
  }
  else
  {
LABEL_2:
    v11 = 2011;
  }
LABEL_30:
  DisposeIfPtr(v7);
  return v11;
}

```

## disassembly

```asm
0x18001e97c  mov     rax, rsp
0x18001e97f  mov     [rax+18h], rbx
0x18001e983  push    rbp
0x18001e984  push    rsi
0x18001e985  push    rdi
0x18001e986  push    r12
0x18001e988  push    r13
0x18001e98a  push    r14
0x18001e98c  push    r15
0x18001e98e  lea     rbp, [rax-0E8h]
0x18001e995  sub     rsp, 1B0h
0x18001e99c  movaps  xmmword ptr [rax-48h], xmm6
0x18001e9a0  movaps  xmmword ptr [rax-58h], xmm7
0x18001e9a4  movaps  xmmword ptr [rax-68h], xmm8
0x18001e9a9  movaps  xmmword ptr [rax-78h], xmm9
0x18001e9ae  movaps  xmmword ptr [rax-88h], xmm10
0x18001e9b6  movaps  xmmword ptr [rax-98h], xmm11
0x18001e9be  mov     rax, cs:__security_cookie
0x18001e9c5  xor     rax, rsp
0x18001e9c8  mov     [rbp+0E0h+var_A0], rax
0x18001e9cc  movsxd  rsi, r8d
0x18001e9cf  mov     r13, rdx
0x18001e9d2  mov     r15, rcx
0x18001e9d5  mov     [rbp+0E0h+var_140], r9
0x18001e9d9  xor     r12d, r12d
0x18001e9dc  lea     rcx, [rbp+0E0h+var_120]; void *
0x18001e9e0  xor     edx, edx; Val
0x18001e9e2  mov     word ptr [rsp+1E0h+var_1AC], r12w
0x18001e9e8  mov     r8d, 80h; Size
0x18001e9ee  call    memset_0
0x18001e9f3  xor     eax, eax
0x18001e9f5  mov     [rsp+1E0h+pcbElement], r12d
0x18001e9fa  xor     edx, edx; Val
0x18001e9fc  mov     [rbp+0E0h+var_130], rax
0x18001ea00  lea     r8d, [r12+5Ah]; Size
0x18001ea05  mov     [rbp+0E0h+var_128], eax
0x18001ea08  lea     rcx, [rsp+1E0h+var_1A8+8]; void *
0x18001ea0d  mov     r14d, r12d
0x18001ea10  call    memset_0
0x18001ea15  mov     qword ptr [r13+0], 71657370h
0x18001ea1d  lea     rdi, [r13+0Ch]
0x18001ea21  movzx   eax, word ptr [r15+2]
0x18001ea26  bswap   eax
0x18001ea28  mov     [r13+8], eax
0x18001ea2c  movzx   ecx, word ptr [r15+2]
0x18001ea31  mov     qword ptr [rsp+1E0h+var_1A8+8], 63736564h
0x18001ea3a  mov     dword ptr [rsp+1E0h+var_198], 1000000h
0x18001ea42  lea     rax, [rcx+rcx*4]
0x18001ea46  shl     rax, 2
0x18001ea4a  sub     rsi, rax
0x18001ea4d  sub     rsi, rdi
0x18001ea50  imul    rax, rcx, 0B4h
0x18001ea57  add     rsi, r13
0x18001ea5a  cmp     rsi, rax
0x18001ea5d  jge     short loc_18001EA69
0x18001ea5f  mov     ebx, 7DBh
0x18001ea64  jmp     loc_18001ED4F
0x18001ea69  mov     edx, r12d
0x18001ea6c  mov     ebx, r12d
0x18001ea6f  mov     dword ptr [rsp+1E0h+var_1A8+4], edx
0x18001ea73  cmp     r12w, cx
0x18001ea77  jnb     loc_18001ED46
0x18001ea7d  movups  xmm6, [rbp+0E0h+var_156]
0x18001ea81  movaps  xmm7, xmmword ptr [rbp-80h]
0x18001ea85  movaps  xmm8, [rsp+1E0h+var_178+8]
0x18001ea8b  movaps  xmm9, [rsp+1E0h+var_188+8]
0x18001ea91  movaps  xmm10, [rsp+1E0h+var_198+8]
0x18001ea97  movaps  xmm11, [rsp+1E0h+var_1A8+8]
0x18001ea9d  movsxd  r12, edx
0x18001eaa0  lea     rdx, [rbp+0E0h+var_120]
0x18001eaa4  mov     rcx, [r15+r12*8+8]
0x18001eaa9  call    CMGetProfileHeader
0x18001eaae  mov     ebx, eax
0x18001eab0  test    eax, eax
0x18001eab2  jnz     loc_18001ED4F
0x18001eab8  mov     ecx, [rbp+0E0h+var_F0]
0x18001eabb  mov     r8d, 0FF0000h
0x18001eac1  mov     edx, ecx
0x18001eac3  mov     dword ptr [rsp+1E0h+var_1A8], ebx
0x18001eac7  and     edx, r8d
0x18001eaca  mov     [rsp+1E0h+var_1C0], 0; PVOID
0x18001ead3  mov     eax, ecx
0x18001ead5  mov     r9d, 0FF00h
0x18001eadb  shr     eax, 10h
0x18001eade  or      edx, eax
0x18001eae0  mov     eax, ecx
0x18001eae2  shl     eax, 10h
0x18001eae5  and     ecx, r9d
0x18001eae8  or      eax, ecx
0x18001eaea  shr     edx, 8
0x18001eaed  shl     eax, 8
0x18001eaf0  or      edx, eax
0x18001eaf2  mov     [rdi], edx
0x18001eaf4  mov     ecx, [rbp+0E0h+var_EC]
0x18001eaf7  mov     edx, ecx
0x18001eaf9  and     edx, r8d
0x18001eafc  mov     eax, ecx
0x18001eafe  shr     eax, 10h
0x18001eb01  or      edx, eax
0x18001eb03  mov     eax, ecx
0x18001eb05  shl     eax, 10h
0x18001eb08  and     ecx, r9d
0x18001eb0b  or      eax, ecx
0x18001eb0d  shr     edx, 8
0x18001eb10  shl     eax, 8
0x18001eb13  or      edx, eax
0x18001eb15  mov     [rdi+4], edx
0x18001eb18  mov     ecx, [rbp+0E0h+var_E8]
0x18001eb1b  mov     edx, ecx
0x18001eb1d  and     edx, r8d
0x18001eb20  mov     eax, ecx
0x18001eb22  shr     eax, 10h
0x18001eb25  or      edx, eax
0x18001eb27  mov     eax, ecx
0x18001eb29  shl     eax, 10h
0x18001eb2c  and     ecx, r9d
0x18001eb2f  or      eax, ecx
0x18001eb31  shr     edx, 8
0x18001eb34  shl     eax, 8
0x18001eb37  or      edx, eax
0x18001eb39  mov     [rdi+8], edx
0x18001eb3c  mov     ecx, [rbp+0E0h+var_E4]
0x18001eb3f  mov     edx, ecx
0x18001eb41  and     edx, r8d
0x18001eb44  mov     eax, ecx
0x18001eb46  shr     eax, 10h
0x18001eb49  xor     r8d, r8d; dwOffset
0x18001eb4c  or      edx, eax
0x18001eb4e  mov     eax, ecx
0x18001eb50  and     ecx, r9d
0x18001eb53  shl     eax, 10h
0x18001eb56  or      eax, ecx
0x18001eb58  shr     edx, 8
0x18001eb5b  shl     eax, 8
0x18001eb5e  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001eb63  or      edx, eax
0x18001eb65  mov     [rdi+0Ch], edx
0x18001eb68  mov     edx, 74656368h; tag
0x18001eb6d  mov     rcx, [r15+r12*8+8]; hProfile
0x18001eb72  call    CMGetPartialProfileElement
0x18001eb77  test    eax, eax
0x18001eb79  jnz     short loc_18001EBAC
0x18001eb7b  cmp     [rsp+1E0h+pcbElement], 4
0x18001eb80  jnz     short loc_18001EBAC
0x18001eb82  mov     rcx, [r15+r12*8+8]; hProfile
0x18001eb87  lea     rax, [rbp+0E0h+var_130]
0x18001eb8b  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001eb90  mov     [rsp+1E0h+var_1C0], rax; PVOID
0x18001eb95  xor     r8d, r8d; dwOffset
0x18001eb98  mov     edx, 74656368h; tag
0x18001eb9d  call    CMGetPartialProfileElement
0x18001eba2  test    eax, eax
0x18001eba4  mov     ecx, ebx
0x18001eba6  cmovz   ecx, [rbp+0E0h+var_128]
0x18001ebaa  jmp     short loc_18001EBB0
0x18001ebac  mov     ecx, dword ptr [rsp+1E0h+var_1A8]
0x18001ebb0  mov     [rdi+10h], ecx
0x18001ebb3  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001ebb8  mov     rcx, [r15+r12*8+8]; hProfile
0x18001ebbd  xor     r8d, r8d; dwOffset
0x18001ebc0  mov     edx, 646D6E64h; tag
0x18001ebc5  mov     [rsp+1E0h+var_1C0], 0; PVOID
0x18001ebce  add     rdi, 14h
0x18001ebd2  call    CMGetPartialProfileElement
0x18001ebd7  test    eax, eax
0x18001ebd9  jnz     short loc_18001EC4A
0x18001ebdb  mov     ecx, [rsp+1E0h+pcbElement]
0x18001ebdf  lea     rdx, [rsp+1E0h+var_1AC]
0x18001ebe4  call    SmartNewPtr
0x18001ebe9  movsx   ebx, word ptr [rsp+1E0h+var_1AC]
0x18001ebee  mov     r14, rax
0x18001ebf1  test    ebx, ebx
0x18001ebf3  jnz     loc_18001ED4F
0x18001ebf9  mov     rcx, [r15+r12*8+8]; hProfile
0x18001ebfe  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001ec03  xor     r8d, r8d; dwOffset
0x18001ec06  mov     [rsp+1E0h+var_1C0], rax; PVOID
0x18001ec0b  mov     edx, 646D6E64h; tag
0x18001ec10  call    CMGetPartialProfileElement
0x18001ec15  test    eax, eax
0x18001ec17  jnz     short loc_18001EC3D
0x18001ec19  mov     eax, [rsp+1E0h+pcbElement]
0x18001ec1d  sub     rsi, rax
0x18001ec20  js      loc_18001EA5F
0x18001ec26  movsxd  r8, [rsp+1E0h+pcbElement]; Size
0x18001ec2b  mov     rdx, r14; Src
0x18001ec2e  mov     rcx, rdi; void *
0x18001ec31  call    memmove_0
0x18001ec36  mov     eax, [rsp+1E0h+pcbElement]
0x18001ec3a  add     rdi, rax
0x18001ec3d  mov     rcx, r14
0x18001ec40  call    DisposeIfPtr
0x18001ec45  mov     r14, rax
0x18001ec48  jmp     short loc_18001EC73
0x18001ec4a  add     rsi, 0FFFFFFFFFFFFFFA6h
0x18001ec4e  js      loc_18001EDA7
0x18001ec54  movups  xmmword ptr [rdi], xmm11
0x18001ec58  movups  xmmword ptr [rdi+10h], xmm10
0x18001ec5d  movups  xmmword ptr [rdi+20h], xmm9
0x18001ec62  movups  xmmword ptr [rdi+30h], xmm8
0x18001ec67  movups  xmmword ptr [rdi+40h], xmm7
0x18001ec6b  movups  xmmword ptr [rdi+4Ah], xmm6
0x18001ec6f  add     rdi, 5Ah ; 'Z'
0x18001ec73  mov     rcx, [r15+r12*8+8]; hProfile
0x18001ec78  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001ec7d  xor     r8d, r8d; dwOffset
0x18001ec80  mov     [rsp+1E0h+var_1C0], 0; PVOID
0x18001ec89  mov     edx, 646D6464h; tag
0x18001ec8e  call    CMGetPartialProfileElement
0x18001ec93  test    eax, eax
0x18001ec95  jnz     short loc_18001ED06
0x18001ec97  mov     ecx, [rsp+1E0h+pcbElement]
0x18001ec9b  lea     rdx, [rsp+1E0h+var_1AC]
0x18001eca0  call    SmartNewPtr
0x18001eca5  movsx   ebx, word ptr [rsp+1E0h+var_1AC]
0x18001ecaa  mov     r14, rax
0x18001ecad  test    ebx, ebx
0x18001ecaf  jnz     loc_18001ED4F
0x18001ecb5  mov     rcx, [r15+r12*8+8]; hProfile
0x18001ecba  lea     r9, [rsp+1E0h+pcbElement]; pcbElement
0x18001ecbf  xor     r8d, r8d; dwOffset
0x18001ecc2  mov     [rsp+1E0h+var_1C0], rax; PVOID
0x18001ecc7  mov     edx, 646D6464h; tag
0x18001eccc  call    CMGetPartialProfileElement
0x18001ecd1  test    eax, eax
0x18001ecd3  jnz     short loc_18001ECF9
0x18001ecd5  mov     eax, [rsp+1E0h+pcbElement]
0x18001ecd9  sub     rsi, rax
0x18001ecdc  js      loc_18001EA5F
0x18001ece2  movsxd  r8, [rsp+1E0h+pcbElement]; Size
0x18001ece7  mov     rdx, r14; Src
0x18001ecea  mov     rcx, rdi; void *
0x18001eced  call    memmove_0
0x18001ecf2  mov     eax, [rsp+1E0h+pcbElement]
0x18001ecf6  add     rdi, rax
0x18001ecf9  mov     rcx, r14
0x18001ecfc  call    DisposeIfPtr
0x18001ed01  mov     r14, rax
0x18001ed04  jmp     short loc_18001ED2F
0x18001ed06  add     rsi, 0FFFFFFFFFFFFFFA6h
0x18001ed0a  js      loc_18001ED9E
0x18001ed10  movups  xmmword ptr [rdi], xmm11
0x18001ed14  movups  xmmword ptr [rdi+10h], xmm10
0x18001ed19  movups  xmmword ptr [rdi+20h], xmm9
0x18001ed1e  movups  xmmword ptr [rdi+30h], xmm8
0x18001ed23  movups  xmmword ptr [rdi+40h], xmm7
0x18001ed27  movups  xmmword ptr [rdi+4Ah], xmm6
0x18001ed2b  add     rdi, 5Ah ; 'Z'
0x18001ed2f  mov     edx, dword ptr [rsp+1E0h+var_1A8+4]
0x18001ed33  movzx   eax, word ptr [r15+2]
0x18001ed38  inc     edx
0x18001ed3a  mov     dword ptr [rsp+1E0h+var_1A8+4], edx
0x18001ed3e  cmp     edx, eax
0x18001ed40  jl      loc_18001EA9D
0x18001ed46  mov     rax, [rbp+0E0h+var_140]
0x18001ed4a  sub     edi, r13d
0x18001ed4d  mov     [rax], edi
0x18001ed4f  mov     rcx, r14
0x18001ed52  call    DisposeIfPtr
0x18001ed57  mov     eax, ebx
0x18001ed59  mov     rcx, [rbp+0E0h+var_A0]
0x18001ed5d  xor     rcx, rsp; StackCookie
0x18001ed60  call    __security_check_cookie
0x18001ed65  lea     r11, [rsp+1E0h+var_30]
0x18001ed6d  mov     rbx, [r11+50h]
0x18001ed71  movaps  xmm6, xmmword ptr [r11-10h]
0x18001ed76  movaps  xmm7, xmmword ptr [r11-20h]
0x18001ed7b  movaps  xmm8, xmmword ptr [r11-30h]
0x18001ed80  movaps  xmm9, xmmword ptr [r11-40h]
0x18001ed85  movaps  xmm10, xmmword ptr [r11-50h]
0x18001ed8a  movaps  xmm11, xmmword ptr [r11-60h]
0x18001ed8f  mov     rsp, r11
0x18001ed92  pop     r15
0x18001ed94  pop     r14
0x18001ed96  pop     r13
0x18001ed98  pop     r12
0x18001ed9a  pop     rdi
0x18001ed9b  pop     rsi
0x18001ed9c  pop     rbp
0x18001ed9d  retn
0x18001ed9e  mov     dword ptr [rbp+0E0h+var_140+4], 2
0x18001eda5  jmp     short loc_18001EDAE
0x18001eda7  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x18001edae  lea     rcx, [rbp+0E0h+var_140]
0x18001edb2  mov     dword ptr [rbp+0E0h+var_140], 2F3E5ACh
0x18001edb9  mov     [rbp+0E0h+var_138], 57h ; 'W'
0x18001edc0  call    cs:__imp_RtlLogUnexpectedCodepath
0x18001edc6  jmp     loc_18001EA5F
```
