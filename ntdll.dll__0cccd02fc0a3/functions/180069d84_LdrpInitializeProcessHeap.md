# LdrpInitializeProcessHeap

- ea: `0x180069d84`
- end: `0x18006a0e4`
- name: `LdrpInitializeProcessHeap`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x180069d84`
- `0x18006a124`
- `0x18006b408`
- `0x1801608e0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x180069fb0`: `Cannot open partition.`

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
  if ( qword_1801CA9A8
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
        9631,
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
          9646,
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
  v19 = RtlpHpLfhContextEnable(Heap + 960, &qword_1801CA1F8);
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
0x180069d84  push    rbp
0x180069d86  push    rbx
0x180069d87  push    rsi
0x180069d88  push    rdi
0x180069d89  push    r13
0x180069d8b  push    r14
0x180069d8d  push    r15
0x180069d8f  lea     rbp, [rsp-40h]
0x180069d94  sub     rsp, 140h
0x180069d9b  mov     rax, cs:__security_cookie
0x180069da2  xor     rax, rsp
0x180069da5  mov     [rbp+70h+var_40], rax
0x180069da9  xorps   xmm0, xmm0
0x180069dac  mov     [rsp+170h+var_130], 0
0x180069db5  xor     eax, eax
0x180069db7  mov     r14, r8
0x180069dba  mov     rsi, rdx
0x180069dbd  mov     rdi, rcx
0x180069dc0  movups  [rsp+170h+var_118], xmm0
0x180069dc5  xor     edx, edx; Val
0x180069dc7  lea     rcx, [rbp+70h+var_F0]; void *
0x180069dcb  lea     r8d, [rax+50h]; Size
0x180069dcf  mov     r15, r9
0x180069dd2  movups  [rsp+170h+var_128], xmm0
0x180069dd7  movups  [rsp+170h+var_118+0Ch], xmm0
0x180069ddc  call    memset$thunk$772440563353939046
0x180069de1  xor     edx, edx; Val
0x180069de3  lea     rcx, [rbp+70h+var_9C]; void *
0x180069de7  lea     r8d, [rdx+5Ch]; Size
0x180069deb  call    memset$thunk$772440563353939046
0x180069df0  mov     [rbp+70h+var_A0], 60h ; '`'
0x180069df7  mov     ecx, 2
0x180069dfc  mov     ebx, ecx
0x180069dfe  test    rdi, rdi
0x180069e01  jz      short loc_180069E6E
0x180069e03  cmp     dword ptr [rdi], 4Ch ; 'L'
0x180069e06  jb      loc_18006A013
0x180069e0c  mov     eax, [rdi+48h]
0x180069e0f  test    eax, eax
0x180069e11  jnz     loc_18006A06D
0x180069e17  mov     rax, [rbp+70h+var_88]
0x180069e1b  cmp     qword ptr [rdi+18h], 0
0x180069e20  cmovnz  rax, [rdi+18h]
0x180069e25  mov     [rbp+70h+var_88], rax
0x180069e29  cmp     dword ptr [rdi], 28h ; '('
0x180069e2c  jb      short loc_180069E40
0x180069e2e  mov     rax, [rbp+70h+var_80]
0x180069e32  cmp     qword ptr [rdi+20h], 0
0x180069e37  cmovnz  rax, [rdi+20h]
0x180069e3c  mov     [rbp+70h+var_80], rax
0x180069e40  cmp     dword ptr [rdi], 38h ; '8'
0x180069e43  jb      short loc_180069E57
0x180069e45  mov     rax, [rbp+70h+var_78]
0x180069e49  cmp     qword ptr [rdi+30h], 0
0x180069e4e  cmovnz  rax, [rdi+30h]
0x180069e53  mov     [rbp+70h+var_78], rax
0x180069e57  cmp     dword ptr [rdi], 40h ; '@'
0x180069e5a  jb      short loc_180069E6E
0x180069e5c  mov     rax, [rbp+70h+var_70]
0x180069e60  cmp     qword ptr [rdi+38h], 0
0x180069e65  cmovnz  rax, [rdi+38h]
0x180069e6a  mov     [rbp+70h+var_70], rax
0x180069e6e  test    rsi, rsi
0x180069e71  jz      loc_18006A0D0
0x180069e77  mov     r8, [rsi+70h]
0x180069e7b  mov     r9, [rsi+78h]
0x180069e7f  cmp     cs:qword_1801CA9A8, 0
0x180069e87  mov     r13d, 3
0x180069e8d  jnz     loc_180069F68
0x180069e93  movups  xmm0, xmmword ptr [r14+420h]
0x180069e9b  movups  xmmword ptr cs:LdrpHeapPartitionName, xmm0
0x180069ea2  psrldq  xmm0, 8
0x180069ea7  movq    rax, xmm0
0x180069eac  test    rax, rax
0x180069eaf  jnz     loc_180069F68
0x180069eb5  test    cs:RtlpHpHeapFeatures, 1
0x180069ebc  jz      loc_18006A0DB
0x180069ec2  mov     ebx, 102h
0x180069ec7  mov     [rbp+70h+var_EC], ecx
0x180069eca  mov     [rbp+70h+var_E4], 1
0x180069ed1  lea     rax, [rbp+70h+var_F0]
0x180069ed5  mov     [rbp+70h+var_E0], 0FFFFFFFFh
0x180069edc  mov     [rbp+70h+var_F0], 500003h
0x180069ee3  cmp     cs:UseWOW64, 0
0x180069eea  jnz     short loc_180069F60
0x180069eec  mov     ecx, 10Bh
0x180069ef1  cmp     [rsi+18h], cx
0x180069ef5  jz      short loc_180069F60
0x180069ef7  cmp     [rsi+48h], r13w
0x180069efc  jbe     loc_18006A0B5
0x180069f02  mov     [rsp+170h+var_140], 0
0x180069f0a  xor     edx, edx
0x180069f0c  mov     [rsp+170h+var_148], rax
0x180069f11  mov     ecx, ebx
0x180069f13  mov     [rsp+170h+Format], 0
0x180069f1c  call    RtlpCreateHeap
0x180069f21  mov     rbx, rax
0x180069f24  test    rax, rax
0x180069f27  jz      loc_18006A021
0x180069f2d  mov     [r15], rax
0x180069f30  cmp     dword ptr [rax+10h], 0DDEEDDEEh
0x180069f37  jz      loc_180069FDC
0x180069f3d  xor     edi, edi
0x180069f3f  mov     eax, edi
0x180069f41  mov     rcx, [rbp+70h+var_40]
0x180069f45  xor     rcx, rsp; StackCookie
0x180069f48  call    __security_check_cookie
0x180069f4d  add     rsp, 140h
0x180069f54  pop     r15
0x180069f56  pop     r14
0x180069f58  pop     r13
0x180069f5a  pop     rdi
0x180069f5b  pop     rsi
0x180069f5c  pop     rbx
0x180069f5d  pop     rbp
0x180069f5e  retn
0x180069f60  xor     r8d, r8d
0x180069f63  xor     r9d, r9d
0x180069f66  jmp     short loc_180069F02
0x180069f68  lea     rax, LdrpHeapPartitionName
0x180069f6f  mov     dword ptr [rsp+170h+var_128], 30h ; '0'
0x180069f77  xorps   xmm0, xmm0
0x180069f7a  mov     qword ptr [rsp+170h+var_118], rax
0x180069f7f  lea     r8, [rsp+170h+var_128]
0x180069f84  mov     qword ptr [rsp+170h+var_128+8], 0
0x180069f8d  mov     edx, 1F0003h
0x180069f92  mov     dword ptr [rsp+170h+var_118+8], 0
0x180069f9a  lea     rcx, [rsp+170h+var_130]
0x180069f9f  movdqu  [rsp+170h+var_108], xmm0
0x180069fa5  call    NtOpenPartition
0x180069faa  mov     edi, eax
0x180069fac  test    eax, eax
0x180069fae  jns     short loc_18006A02B
0x180069fb0  lea     rax, aCannotOpenPart; "Cannot open partition."
0x180069fb7  xor     r9d, r9d; int
0x180069fba  lea     r8, aLdrpinitialize_8; "LdrpInitializeProcessHeap"
0x180069fc1  mov     [rsp+170h+Format], rax; Format
0x180069fc6  mov     edx, 259Fh; int
0x180069fcb  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x180069fd2  call    LdrpLogInternal
0x180069fd7  jmp     loc_180069F3F
0x180069fdc  test    dword ptr [rax+14h], 400000h
0x180069fe3  jz      loc_18006A0C9
0x180069fe9  lea     rcx, [rax+3C0h]
0x180069ff0  lea     rdx, qword_1801CA1F8
0x180069ff7  call    RtlpHpLfhContextEnable
0x180069ffc  mov     edi, eax
0x180069ffe  test    eax, eax
0x18006a000  js      loc_180069F3F
0x18006a006  lock and dword ptr [rbx+14h], 0FFBFFFFFh
0x18006a00e  jmp     loc_180069F3D
0x18006a013  cmp     dword ptr [rdi], 20h ; ' '
0x18006a016  jnb     loc_180069E17
0x18006a01c  jmp     loc_180069E29
0x18006a021  mov     edi, 0C0000017h
0x18006a026  jmp     loc_180069F3F
0x18006a02b  mov     edi, [r14+440h]
0x18006a032  test    edi, edi
0x18006a034  jnz     short loc_18006A07F
0x18006a036  mov     edi, 8
0x18006a03b  xor     edx, edx; Val
0x18006a03d  lea     rcx, [rbp+70h+var_F0]; void *
0x18006a041  mov     ebx, 102h
0x18006a046  lea     r8d, [rdx+50h]; Size
0x18006a04a  call    memset$thunk$772440563353939046
0x18006a04f  mov     rax, [rsp+170h+var_130]
0x18006a054  xor     r8d, r8d
0x18006a057  mov     [rbp+70h+var_D8], rax
0x18006a05b  xor     r9d, r9d
0x18006a05e  mov     [rbp+70h+var_EC], 2
0x18006a065  mov     [rbp+70h+var_E4], edi
0x18006a068  jmp     loc_180069ED1
0x18006a06d  and     eax, 0FFFF0FFFh
0x18006a072  jz      loc_180069E17
0x18006a078  mov     ebx, eax
0x18006a07a  jmp     loc_180069E17
0x18006a07f  and     edi, 1Ch
0x18006a082  jnz     short loc_18006A03B
0x18006a084  lea     rax, aInvalidPartiti; "Invalid partition heap page types."
0x18006a08b  xor     r9d, r9d; int
0x18006a08e  lea     r8, aLdrpinitialize_8; "LdrpInitializeProcessHeap"
0x18006a095  mov     [rsp+170h+Format], rax; Format
0x18006a09a  mov     edx, 25AEh; int
0x18006a09f  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x18006a0a6  call    LdrpLogInternal
0x18006a0ab  mov     edi, 0C000000Dh
0x18006a0b0  jmp     loc_180069F3F
0x18006a0b5  cmp     word ptr [rsi+4Ah], 33h ; '3'
0x18006a0ba  jnb     loc_180069F02
0x18006a0c0  bts     ebx, 10h
0x18006a0c4  jmp     loc_180069F02
0x18006a0c9  int     2Ch; NT_ASSERT("Heap->GlobalFlags & 0x00400000")
0x18006a0cb  jmp     loc_180069FE9
0x18006a0d0  xor     r9d, r9d
0x18006a0d3  xor     r8d, r8d
0x18006a0d6  jmp     loc_180069E7F
0x18006a0db  lea     rax, [rbp+70h+var_A0]
0x18006a0df  jmp     loc_180069EE3
```
