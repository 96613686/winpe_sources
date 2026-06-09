# LdrpInitializeProcessHeap

- ea: `0x180086838`
- end: `0x180086b98`
- name: `LdrpInitializeProcessHeap`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180050718`

## callees

- `0x18001eb80`
- `0x180086838`
- `0x180086bd4`
- `0x180087eb8`
- `0x1801610f0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180086a64`: `Cannot open partition.`

## pseudocode

```c
__int64 __fastcall LdrpInitializeProcessHeap(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  char *v15; // r9
  int *v16; // rax
  __int64 Heap; // rax
  __int64 v18; // rbx
  int v19; // edi
  int v21; // edi
  unsigned int v22; // eax
  char v23; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[48]; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+80h] [rbp-80h] BYREF
  int v27; // [rsp+84h] [rbp-7Ch]
  int v28; // [rsp+8Ch] [rbp-74h]
  int v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[20]; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v33; // [rsp+E8h] [rbp-18h]
  __int64 v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  __int64 v36; // [rsp+100h] [rbp+0h]

  v24 = 0;
  memset(v25, 0, 44);
  memset_thunk_772440563353939046(&v26, 0, 0x50u);
  memset_thunk_772440563353939046(v32, 0, 0x5Cu);
  v31 = 96;
  v8 = 2;
  if ( !a1 )
    goto LABEL_19;
  if ( *(_DWORD *)a1 >= 0x4Cu )
  {
    v9 = *(_DWORD *)(a1 + 72);
    if ( v9 )
    {
      v22 = v9 & 0xFFFF0FFF;
      if ( v22 )
        v8 = v22;
    }
    goto LABEL_4;
  }
  if ( *(_DWORD *)a1 >= 0x20u )
  {
LABEL_4:
    v10 = v33;
    if ( *(_QWORD *)(a1 + 24) )
      v10 = *(_QWORD *)(a1 + 24);
    v33 = v10;
  }
  if ( *(_DWORD *)a1 >= 0x28u )
  {
    v11 = v34;
    if ( *(_QWORD *)(a1 + 32) )
      v11 = *(_QWORD *)(a1 + 32);
    v34 = v11;
  }
  if ( *(_DWORD *)a1 >= 0x38u )
  {
    v12 = v35;
    if ( *(_QWORD *)(a1 + 48) )
      v12 = *(_QWORD *)(a1 + 48);
    v35 = v12;
  }
  if ( *(_DWORD *)a1 >= 0x40u )
  {
    v13 = v36;
    if ( *(_QWORD *)(a1 + 56) )
      v13 = *(_QWORD *)(a1 + 56);
    v36 = v13;
  }
LABEL_19:
  if ( a2 )
  {
    v14 = *(_QWORD *)(a2 + 112);
    v15 = *(char **)(a2 + 120);
  }
  else
  {
    v15 = 0;
    v14 = 0;
  }
  if ( qword_1801CA9C8
    || (*(_OWORD *)LdrpHeapPartitionName = *(_OWORD *)(a3 + 1056),
        _mm_srli_si128(*(__m128i *)LdrpHeapPartitionName, 8).m128i_u64[0]) )
  {
    *(_DWORD *)v25 = 48;
    *(_QWORD *)&v25[16] = LdrpHeapPartitionName;
    *(_QWORD *)&v25[8] = 0;
    *(_DWORD *)&v25[24] = 0;
    *(_OWORD *)&v25[32] = 0;
    v19 = NtOpenPartition(&v24, 2031619, v25, v15);
    if ( v19 < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        9487,
        (int)"LdrpInitializeProcessHeap",
        0,
        "Cannot open partition.",
        v23);
      return (unsigned int)v19;
    }
    if ( *(_DWORD *)(a3 + 1088) )
    {
      v21 = *(_DWORD *)(a3 + 1088) & 0x1C;
      if ( !v21 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          9502,
          (int)"LdrpInitializeProcessHeap",
          0,
          "Invalid partition heap page types.",
          v23);
        return (unsigned int)-1073741811;
      }
    }
    else
    {
      v21 = 8;
    }
    v8 = 258;
    memset_thunk_772440563353939046(&v26, 0, 0x50u);
    v14 = 0;
    v30 = v24;
    v15 = 0;
    v27 = 2;
    v28 = v21;
  }
  else
  {
    if ( (RtlpHpHeapFeatures & 1) == 0 )
    {
      v16 = &v31;
      goto LABEL_26;
    }
    v8 = 258;
    v27 = 2;
    v28 = 1;
  }
  v16 = &v26;
  v29 = -1;
  v26 = 5242883;
LABEL_26:
  if ( UseWOW64 || *(_WORD *)(a2 + 24) == 267 )
  {
    v14 = 0;
    v15 = 0;
  }
  else if ( *(_WORD *)(a2 + 72) <= 3u && *(_WORD *)(a2 + 74) < 0x33u )
  {
    v8 |= 0x10000u;
  }
  Heap = RtlpCreateHeap(v8, 0, v14, v15, 0, (__int64)v16, 0);
  v18 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *a4 = Heap;
  if ( *(_DWORD *)(Heap + 16) != -571548178 )
    return 0;
  if ( (*(_DWORD *)(Heap + 20) & 0x400000) == 0 )
    NT_ASSERT("Heap->GlobalFlags & 0x00400000");
  v19 = RtlpHpLfhContextEnable(Heap + 960, &qword_1801CA1E8);
  if ( v19 >= 0 )
  {
    _InterlockedAnd((volatile signed __int32 *)(v18 + 20), 0xFFBFFFFF);
    return 0;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180086838  push    rbp
0x18008683a  push    rbx
0x18008683b  push    rsi
0x18008683c  push    rdi
0x18008683d  push    r13
0x18008683f  push    r14
0x180086841  push    r15
0x180086843  lea     rbp, [rsp-40h]
0x180086848  sub     rsp, 140h
0x18008684f  mov     rax, cs:__security_cookie
0x180086856  xor     rax, rsp
0x180086859  mov     [rbp+70h+var_40], rax
0x18008685d  xorps   xmm0, xmm0
0x180086860  mov     [rsp+170h+var_130], 0
0x180086869  xor     eax, eax
0x18008686b  mov     r14, r8
0x18008686e  mov     rsi, rdx
0x180086871  mov     rdi, rcx
0x180086874  movups  [rsp+170h+var_118], xmm0
0x180086879  xor     edx, edx; Val
0x18008687b  lea     rcx, [rbp+70h+var_F0]; void *
0x18008687f  lea     r8d, [rax+50h]; Size
0x180086883  mov     r15, r9
0x180086886  movups  [rsp+170h+var_128], xmm0
0x18008688b  movups  [rsp+170h+var_118+0Ch], xmm0
0x180086890  call    memset$thunk$772440563353939046
0x180086895  xor     edx, edx; Val
0x180086897  lea     rcx, [rbp+70h+var_9C]; void *
0x18008689b  lea     r8d, [rdx+5Ch]; Size
0x18008689f  call    memset$thunk$772440563353939046
0x1800868a4  mov     [rbp+70h+var_A0], 60h ; '`'
0x1800868ab  mov     ecx, 2
0x1800868b0  mov     ebx, ecx
0x1800868b2  test    rdi, rdi
0x1800868b5  jz      short loc_180086922
0x1800868b7  cmp     dword ptr [rdi], 4Ch ; 'L'
0x1800868ba  jb      loc_180086AC7
0x1800868c0  mov     eax, [rdi+48h]
0x1800868c3  test    eax, eax
0x1800868c5  jnz     loc_180086B21
0x1800868cb  mov     rax, [rbp+70h+var_88]
0x1800868cf  cmp     qword ptr [rdi+18h], 0
0x1800868d4  cmovnz  rax, [rdi+18h]
0x1800868d9  mov     [rbp+70h+var_88], rax
0x1800868dd  cmp     dword ptr [rdi], 28h ; '('
0x1800868e0  jb      short loc_1800868F4
0x1800868e2  mov     rax, [rbp+70h+var_80]
0x1800868e6  cmp     qword ptr [rdi+20h], 0
0x1800868eb  cmovnz  rax, [rdi+20h]
0x1800868f0  mov     [rbp+70h+var_80], rax
0x1800868f4  cmp     dword ptr [rdi], 38h ; '8'
0x1800868f7  jb      short loc_18008690B
0x1800868f9  mov     rax, [rbp+70h+var_78]
0x1800868fd  cmp     qword ptr [rdi+30h], 0
0x180086902  cmovnz  rax, [rdi+30h]
0x180086907  mov     [rbp+70h+var_78], rax
0x18008690b  cmp     dword ptr [rdi], 40h ; '@'
0x18008690e  jb      short loc_180086922
0x180086910  mov     rax, [rbp+70h+var_70]
0x180086914  cmp     qword ptr [rdi+38h], 0
0x180086919  cmovnz  rax, [rdi+38h]
0x18008691e  mov     [rbp+70h+var_70], rax
0x180086922  test    rsi, rsi
0x180086925  jz      loc_180086B84
0x18008692b  mov     r8, [rsi+70h]
0x18008692f  mov     r9, [rsi+78h]
0x180086933  cmp     cs:qword_1801CA9C8, 0
0x18008693b  mov     r13d, 3
0x180086941  jnz     loc_180086A1C
0x180086947  movups  xmm0, xmmword ptr [r14+420h]
0x18008694f  movups  xmmword ptr cs:LdrpHeapPartitionName, xmm0
0x180086956  psrldq  xmm0, 8
0x18008695b  movq    rax, xmm0
0x180086960  test    rax, rax
0x180086963  jnz     loc_180086A1C
0x180086969  test    cs:RtlpHpHeapFeatures, 1
0x180086970  jz      loc_180086B8F
0x180086976  mov     ebx, 102h
0x18008697b  mov     [rbp+70h+var_EC], ecx
0x18008697e  mov     [rbp+70h+var_E4], 1
0x180086985  lea     rax, [rbp+70h+var_F0]
0x180086989  mov     [rbp+70h+var_E0], 0FFFFFFFFh
0x180086990  mov     [rbp+70h+var_F0], 500003h
0x180086997  cmp     cs:UseWOW64, 0
0x18008699e  jnz     short loc_180086A14
0x1800869a0  mov     ecx, 10Bh
0x1800869a5  cmp     [rsi+18h], cx
0x1800869a9  jz      short loc_180086A14
0x1800869ab  cmp     [rsi+48h], r13w
0x1800869b0  jbe     loc_180086B69
0x1800869b6  mov     [rsp+170h+var_140], 0
0x1800869be  xor     edx, edx
0x1800869c0  mov     [rsp+170h+var_148], rax
0x1800869c5  mov     ecx, ebx
0x1800869c7  mov     [rsp+170h+Format], 0
0x1800869d0  call    RtlpCreateHeap
0x1800869d5  mov     rbx, rax
0x1800869d8  test    rax, rax
0x1800869db  jz      loc_180086AD5
0x1800869e1  mov     [r15], rax
0x1800869e4  cmp     dword ptr [rax+10h], 0DDEEDDEEh
0x1800869eb  jz      loc_180086A90
0x1800869f1  xor     edi, edi
0x1800869f3  mov     eax, edi
0x1800869f5  mov     rcx, [rbp+70h+var_40]
0x1800869f9  xor     rcx, rsp; StackCookie
0x1800869fc  call    __security_check_cookie
0x180086a01  add     rsp, 140h
0x180086a08  pop     r15
0x180086a0a  pop     r14
0x180086a0c  pop     r13
0x180086a0e  pop     rdi
0x180086a0f  pop     rsi
0x180086a10  pop     rbx
0x180086a11  pop     rbp
0x180086a12  retn
0x180086a14  xor     r8d, r8d
0x180086a17  xor     r9d, r9d
0x180086a1a  jmp     short loc_1800869B6
0x180086a1c  lea     rax, LdrpHeapPartitionName
0x180086a23  mov     dword ptr [rsp+170h+var_128], 30h ; '0'
0x180086a2b  xorps   xmm0, xmm0
0x180086a2e  mov     qword ptr [rsp+170h+var_118], rax
0x180086a33  lea     r8, [rsp+170h+var_128]
0x180086a38  mov     qword ptr [rsp+170h+var_128+8], 0
0x180086a41  mov     edx, 1F0003h
0x180086a46  mov     dword ptr [rsp+170h+var_118+8], 0
0x180086a4e  lea     rcx, [rsp+170h+var_130]
0x180086a53  movdqu  [rsp+170h+var_108], xmm0
0x180086a59  call    NtOpenPartition
0x180086a5e  mov     edi, eax
0x180086a60  test    eax, eax
0x180086a62  jns     short loc_180086ADF
0x180086a64  lea     rax, aCannotOpenPart; "Cannot open partition."
0x180086a6b  xor     r9d, r9d; int
0x180086a6e  lea     r8, aLdrpinitialize_8; "LdrpInitializeProcessHeap"
0x180086a75  mov     [rsp+170h+Format], rax; Format
0x180086a7a  mov     edx, 250Fh; int
0x180086a7f  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x180086a86  call    LdrpLogInternal
0x180086a8b  jmp     loc_1800869F3
0x180086a90  test    dword ptr [rax+14h], 400000h
0x180086a97  jz      loc_180086B7D
0x180086a9d  lea     rcx, [rax+3C0h]
0x180086aa4  lea     rdx, qword_1801CA1E8
0x180086aab  call    RtlpHpLfhContextEnable
0x180086ab0  mov     edi, eax
0x180086ab2  test    eax, eax
0x180086ab4  js      loc_1800869F3
0x180086aba  lock and dword ptr [rbx+14h], 0FFBFFFFFh
0x180086ac2  jmp     loc_1800869F1
0x180086ac7  cmp     dword ptr [rdi], 20h ; ' '
0x180086aca  jnb     loc_1800868CB
0x180086ad0  jmp     loc_1800868DD
0x180086ad5  mov     edi, 0C0000017h
0x180086ada  jmp     loc_1800869F3
0x180086adf  mov     edi, [r14+440h]
0x180086ae6  test    edi, edi
0x180086ae8  jnz     short loc_180086B33
0x180086aea  mov     edi, 8
0x180086aef  xor     edx, edx; Val
0x180086af1  lea     rcx, [rbp+70h+var_F0]; void *
0x180086af5  mov     ebx, 102h
0x180086afa  lea     r8d, [rdx+50h]; Size
0x180086afe  call    memset$thunk$772440563353939046
0x180086b03  mov     rax, [rsp+170h+var_130]
0x180086b08  xor     r8d, r8d
0x180086b0b  mov     [rbp+70h+var_D8], rax
0x180086b0f  xor     r9d, r9d
0x180086b12  mov     [rbp+70h+var_EC], 2
0x180086b19  mov     [rbp+70h+var_E4], edi
0x180086b1c  jmp     loc_180086985
0x180086b21  and     eax, 0FFFF0FFFh
0x180086b26  jz      loc_1800868CB
0x180086b2c  mov     ebx, eax
0x180086b2e  jmp     loc_1800868CB
0x180086b33  and     edi, 1Ch
0x180086b36  jnz     short loc_180086AEF
0x180086b38  lea     rax, aInvalidPartiti; "Invalid partition heap page types."
0x180086b3f  xor     r9d, r9d; int
0x180086b42  lea     r8, aLdrpinitialize_8; "LdrpInitializeProcessHeap"
0x180086b49  mov     [rsp+170h+Format], rax; Format
0x180086b4e  mov     edx, 251Eh; int
0x180086b53  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x180086b5a  call    LdrpLogInternal
0x180086b5f  mov     edi, 0C000000Dh
0x180086b64  jmp     loc_1800869F3
0x180086b69  cmp     word ptr [rsi+4Ah], 33h ; '3'
0x180086b6e  jnb     loc_1800869B6
0x180086b74  bts     ebx, 10h
0x180086b78  jmp     loc_1800869B6
0x180086b7d  int     2Ch; NT_ASSERT("Heap->GlobalFlags & 0x00400000")
0x180086b7f  jmp     loc_180086A9D
0x180086b84  xor     r9d, r9d
0x180086b87  xor     r8d, r8d
0x180086b8a  jmp     loc_180086933
0x180086b8f  lea     rax, [rbp+70h+var_A0]
0x180086b93  jmp     loc_180086997
```
