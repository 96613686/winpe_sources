# DiscpFilterCondition5TupleV6Create

- ea: `0x180015c9c`
- end: `0x18001605a`
- name: `DiscpFilterCondition5TupleV6Create`
- size: `958`
- prototype: `__int64 __fastcall(char, _QWORD *, __int64, _QWORD *, int, __int16, __int16, char, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016780`

## callees

- `0x180001cfe`
- `0x180015c9c`
- `0x180016060`
- `0x18001614c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180015e20`
- `ISCSIUM!DiscpAllocMemory` at `0x180015e20`

## pseudocode

```c
__int64 __fastcall DiscpFilterCondition5TupleV6Create(
        char a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        __int16 a6,
        __int16 a7,
        char a8,
        _QWORD *a9,
        int *a10)
{
  unsigned int v13; // esi
  int v14; // edi
  unsigned int v15; // r13d
  int v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // r14d
  char *v19; // rbx
  __int64 v20; // r8
  int v21; // r14d
  const GUID *v22; // rcx
  const GUID *v23; // rcx
  __int16 v24; // r8
  __int64 v25; // rdx
  GUID v26; // xmm0
  __int16 v27; // r8
  __int64 v28; // rdx
  GUID v29; // xmm0
  char v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v34; // [rsp+20h] [rbp-58h]
  char *v35; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v36; // [rsp+80h] [rbp+8h]
  unsigned int v37; // [rsp+88h] [rbp+10h]
  int v38; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v39; // [rsp+98h] [rbp+20h]

  v38 = 0;
  a5 = 0;
  v13 = 0;
  v14 = 0;
  *a9 = 0;
  *a10 = 0;
  if ( a2 && (*a2 || _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] != a2[1]) )
  {
    v14 = 1;
    v38 = 1;
    v15 = 0;
    v16 = 1;
  }
  else
  {
    v15 = 0xFFFF;
    v16 = 0;
  }
  if ( a4 && (*a4 || _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] != a4[1]) )
  {
    v14 = v16 + 1;
    v36 = v16;
    v38 = ++v16;
  }
  else
  {
    v36 = 0xFFFF;
  }
  if ( a6 )
  {
    v14 = v16 + 1;
    v37 = v16;
    v38 = ++v16;
  }
  else
  {
    v37 = 0xFFFF;
  }
  if ( a7 )
  {
    v14 = v16 + 1;
    v39 = v16;
    v38 = ++v16;
  }
  else
  {
    v39 = 0xFFFF;
  }
  if ( a8 )
  {
    v14 = v16 + 1;
    v34 = v16;
    v38 = ++v16;
  }
  else
  {
    v34 = 0xFFFF;
  }
  if ( (a1 & 1) != 0 || (a1 & 2) != 0 )
  {
    v14 = v16 + 1;
    v17 = v16;
    v38 = v16 + 1;
    v18 = v16 + 1;
    if ( (a1 & 2) != 0 )
      a5 = 1;
  }
  else
  {
    v17 = 0xFFFF;
    v18 = v16;
  }
  if ( v18 )
  {
    v35 = (char *)DiscpAllocMemory(40 * v18);
    v19 = v35;
    if ( !v35 )
    {
      v13 = 8;
LABEL_51:
      DiscpFilterConditionDestroy(&v35, &v38);
      return v13;
    }
    memset_0(v35, 0, 40LL * v18);
    v21 = a5;
    if ( v15 != 0xFFFF )
    {
      v22 = &FWPM_CONDITION_IP_LOCAL_ADDRESS;
      if ( !a5 )
        v22 = &FWPM_CONDITION_IP_REMOTE_ADDRESS;
      v13 = DiscpFilterConditionIpAddressV6Fill(v22, a2, v20, &v35[40 * v15]);
      if ( v13 )
        goto LABEL_51;
    }
    if ( v36 != 0xFFFF )
    {
      v23 = &FWPM_CONDITION_IP_REMOTE_ADDRESS;
      if ( !v21 )
        v23 = &FWPM_CONDITION_IP_LOCAL_ADDRESS;
      v13 = DiscpFilterConditionIpAddressV6Fill(v23, a4, v20, &v35[40 * v36]);
      if ( v13 )
        goto LABEL_51;
    }
    if ( v37 != 0xFFFF )
    {
      v24 = a6;
      v25 = 5LL * v37;
      *(_OWORD *)&v35[8 * v25] = 0;
      *(_OWORD *)&v19[8 * v25 + 16] = 0;
      *(_QWORD *)&v19[8 * v25 + 32] = 0;
      if ( v21 )
        v26 = FWPM_CONDITION_IP_LOCAL_PORT;
      else
        v26 = FWPM_CONDITION_IP_REMOTE_PORT;
      *(GUID *)&v19[40 * v37] = v26;
      *(_DWORD *)&v19[40 * v37 + 16] = v24 == 0 ? 3 : 0;
      *(_WORD *)&v19[40 * v37 + 32] = v24;
      *(_DWORD *)&v19[40 * v37 + 24] = 2;
    }
    if ( v39 != 0xFFFF )
    {
      v27 = a7;
      v28 = 5LL * v39;
      *(_OWORD *)&v19[8 * v28] = 0;
      *(_OWORD *)&v19[8 * v28 + 16] = 0;
      *(_QWORD *)&v19[8 * v28 + 32] = 0;
      if ( v21 )
        v29 = FWPM_CONDITION_IP_REMOTE_PORT;
      else
        v29 = FWPM_CONDITION_IP_LOCAL_PORT;
      *(GUID *)&v19[8 * v28] = v29;
      *(_DWORD *)&v19[8 * v28 + 16] = v27 == 0 ? 3 : 0;
      *(_WORD *)&v19[8 * v28 + 32] = v27;
      *(_DWORD *)&v19[8 * v28 + 24] = 2;
    }
    if ( v34 != 0xFFFF )
    {
      v30 = a8;
      v31 = 5LL * v34;
      *(_OWORD *)&v19[8 * v31 + 16] = 0;
      *(_QWORD *)&v19[8 * v31 + 32] = 0;
      *(GUID *)&v19[8 * v31] = FWPM_CONDITION_IP_PROTOCOL;
      *(_DWORD *)&v19[8 * v31 + 16] = v30 == 0 ? 3 : 0;
      *(_DWORD *)&v19[8 * v31 + 24] = 1;
      v19[8 * v31 + 32] = v30;
    }
    if ( v17 != 0xFFFF )
    {
      v32 = 5LL * v17;
      *(_OWORD *)&v19[8 * v32] = 0;
      *(_OWORD *)&v19[8 * v32 + 16] = 0;
      *(_QWORD *)&v19[8 * v32 + 32] = 0;
      *(_DWORD *)&v19[8 * v32 + 24] = 1;
      v19[8 * v32 + 32] = 1;
      *(GUID *)&v19[8 * v32] = FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE;
    }
    *a9 = v19;
    *a10 = v14;
  }
  return v13;
}

```

## disassembly

```asm
0x180015c9c  mov     rax, rsp
0x180015c9f  mov     [rax+18h], r8b
0x180015ca3  push    rbx
0x180015ca4  push    rbp
0x180015ca5  push    rsi
0x180015ca6  push    rdi
0x180015ca7  push    r12
0x180015ca9  push    r13
0x180015cab  push    r14
0x180015cad  push    r15
0x180015caf  sub     rsp, 38h
0x180015cb3  xor     r8d, r8d
0x180015cb6  mov     rbp, rdx
0x180015cb9  mov     [rax+18h], r8d
0x180015cbd  mov     r12, r9
0x180015cc0  mov     rax, [rsp+78h+arg_40]
0x180015cc8  mov     edx, ecx
0x180015cca  mov     [rsp+78h+arg_20], r8d
0x180015cd2  mov     esi, r8d
0x180015cd5  lea     r10d, [r8+1]
0x180015cd9  mov     edi, r8d
0x180015cdc  xorps   xmm0, xmm0
0x180015cdf  mov     r9d, 0FFFFh
0x180015ce5  mov     [rax], r8
0x180015ce8  mov     rax, [rsp+78h+arg_48]
0x180015cf0  mov     [rax], r8d
0x180015cf3  test    rbp, rbp
0x180015cf6  jz      short loc_180015D26
0x180015cf8  movq    rax, xmm0
0x180015cfd  cmp     rax, [rbp+0]
0x180015d01  jnz     short loc_180015D13
0x180015d03  psrldq  xmm0, 8
0x180015d08  movq    rax, xmm0
0x180015d0d  cmp     rax, [rbp+8]
0x180015d11  jz      short loc_180015D26
0x180015d13  mov     edi, r10d
0x180015d16  mov     [rsp+78h+arg_10], r10d
0x180015d1e  mov     r13d, r8d
0x180015d21  mov     ecx, r10d
0x180015d24  jmp     short loc_180015D2C
0x180015d26  mov     r13d, r9d
0x180015d29  mov     ecx, r8d
0x180015d2c  xorps   xmm0, xmm0
0x180015d2f  test    r12, r12
0x180015d32  jz      short loc_180015D65
0x180015d34  movq    rax, xmm0
0x180015d39  cmp     rax, [r12]
0x180015d3d  jnz     short loc_180015D50
0x180015d3f  psrldq  xmm0, 8
0x180015d44  movq    rax, xmm0
0x180015d49  cmp     rax, [r12+8]
0x180015d4e  jz      short loc_180015D65
0x180015d50  lea     edi, [rcx+1]
0x180015d53  mov     [rsp+78h+arg_0], ecx
0x180015d5a  mov     [rsp+78h+arg_10], edi
0x180015d61  mov     ecx, edi
0x180015d63  jmp     short loc_180015D6D
0x180015d65  mov     [rsp+78h+arg_0], r9d
0x180015d6d  cmp     [rsp+78h+arg_28], r8w
0x180015d76  jz      short loc_180015D8D
0x180015d78  lea     edi, [rcx+1]
0x180015d7b  mov     [rsp+78h+arg_8], ecx
0x180015d82  mov     [rsp+78h+arg_10], edi
0x180015d89  mov     ecx, edi
0x180015d8b  jmp     short loc_180015D95
0x180015d8d  mov     [rsp+78h+arg_8], r9d
0x180015d95  cmp     [rsp+78h+arg_30], r8w
0x180015d9e  jz      short loc_180015DB5
0x180015da0  lea     edi, [rcx+1]
0x180015da3  mov     [rsp+78h+arg_18], ecx
0x180015daa  mov     [rsp+78h+arg_10], edi
0x180015db1  mov     ecx, edi
0x180015db3  jmp     short loc_180015DBD
0x180015db5  mov     [rsp+78h+arg_18], r9d
0x180015dbd  cmp     [rsp+78h+arg_38], r8b
0x180015dc5  jz      short loc_180015DD9
0x180015dc7  lea     edi, [rcx+1]
0x180015dca  mov     [rsp+78h+var_58], ecx
0x180015dce  mov     [rsp+78h+arg_10], edi
0x180015dd5  mov     ecx, edi
0x180015dd7  jmp     short loc_180015DDE
0x180015dd9  mov     [rsp+78h+var_58], r9d
0x180015dde  mov     eax, edx
0x180015de0  and     eax, 2
0x180015de3  test    r10b, dl
0x180015de6  jnz     short loc_180015DF4
0x180015de8  test    eax, eax
0x180015dea  jnz     short loc_180015DF4
0x180015dec  mov     r15d, r9d
0x180015def  mov     r14d, ecx
0x180015df2  jmp     short loc_180015E10
0x180015df4  lea     edi, [rcx+1]
0x180015df7  mov     r15d, ecx
0x180015dfa  mov     [rsp+78h+arg_10], edi
0x180015e01  mov     r14d, edi
0x180015e04  test    eax, eax
0x180015e06  jz      short loc_180015E10
0x180015e08  mov     [rsp+78h+arg_20], r10d
0x180015e10  test    r14d, r14d
0x180015e13  jz      loc_180016047
0x180015e19  lea     ecx, [r14+r14*4]
0x180015e1d  shl     ecx, 3
0x180015e20  call    cs:__imp_DiscpAllocMemory
0x180015e26  mov     [rsp+78h+var_50], rax
0x180015e2b  mov     rbx, rax
0x180015e2e  test    rax, rax
0x180015e31  jnz     short loc_180015E3B
0x180015e33  lea     esi, [rax+8]
0x180015e36  jmp     loc_180016035
0x180015e3b  mov     eax, r14d
0x180015e3e  xor     edx, edx; Val
0x180015e40  mov     rcx, rbx; void *
0x180015e43  lea     r8, [rax+rax*4]
0x180015e47  shl     r8, 3; Size
0x180015e4b  call    memset_0
0x180015e50  mov     r14d, [rsp+78h+arg_20]
0x180015e58  cmp     r13d, 0FFFFh
0x180015e5f  jz      short loc_180015E91
0x180015e61  mov     eax, r13d
0x180015e64  mov     rdx, rbp
0x180015e67  lea     rcx, [rax+rax*4]
0x180015e6b  lea     r9, [rbx+rcx*8]
0x180015e6f  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180015e76  test    r14d, r14d
0x180015e79  jnz     short loc_180015E82
0x180015e7b  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180015e82  call    DiscpFilterConditionIpAddressV6Fill
0x180015e87  mov     esi, eax
0x180015e89  test    eax, eax
0x180015e8b  jnz     loc_180016035
0x180015e91  mov     eax, [rsp+78h+arg_0]
0x180015e98  mov     ebp, 0FFFFh
0x180015e9d  cmp     eax, ebp
0x180015e9f  jz      short loc_180015ECE
0x180015ea1  lea     rdx, [rax+rax*4]
0x180015ea5  lea     r9, [rbx+rdx*8]
0x180015ea9  mov     rdx, r12
0x180015eac  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180015eb3  test    r14d, r14d
0x180015eb6  jnz     short loc_180015EBF
0x180015eb8  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180015ebf  call    DiscpFilterConditionIpAddressV6Fill
0x180015ec4  mov     esi, eax
0x180015ec6  test    eax, eax
0x180015ec8  jnz     loc_180016035
0x180015ece  mov     eax, [rsp+78h+arg_8]
0x180015ed5  cmp     eax, ebp
0x180015ed7  jz      short loc_180015F33
0x180015ed9  movzx   r8d, [rsp+78h+arg_28]
0x180015ee2  lea     rdx, [rax+rax*4]
0x180015ee6  xor     eax, eax
0x180015ee8  xorps   xmm0, xmm0
0x180015eeb  movups  xmmword ptr [rbx+rdx*8], xmm0
0x180015eef  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015ef4  mov     [rbx+rdx*8+20h], rax
0x180015ef9  movzx   eax, r8w
0x180015efd  test    r14d, r14d
0x180015f00  jz      short loc_180015F0B
0x180015f02  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180015f09  jmp     short loc_180015F12
0x180015f0b  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180015f12  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015f17  neg     ax
0x180015f1a  sbb     ecx, ecx
0x180015f1c  not     ecx
0x180015f1e  and     ecx, 3
0x180015f21  mov     [rbx+rdx*8+10h], ecx
0x180015f25  mov     [rbx+rdx*8+20h], r8w
0x180015f2b  mov     dword ptr [rbx+rdx*8+18h], 2
0x180015f33  mov     eax, [rsp+78h+arg_18]
0x180015f3a  cmp     eax, ebp
0x180015f3c  jz      short loc_180015F98
0x180015f3e  movzx   r8d, [rsp+78h+arg_30]
0x180015f47  lea     rdx, [rax+rax*4]
0x180015f4b  xor     eax, eax
0x180015f4d  xorps   xmm0, xmm0
0x180015f50  movups  xmmword ptr [rbx+rdx*8], xmm0
0x180015f54  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015f59  mov     [rbx+rdx*8+20h], rax
0x180015f5e  movzx   eax, r8w
0x180015f62  test    r14d, r14d
0x180015f65  jz      short loc_180015F70
0x180015f67  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180015f6e  jmp     short loc_180015F77
0x180015f70  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180015f77  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015f7c  neg     ax
0x180015f7f  sbb     ecx, ecx
0x180015f81  not     ecx
0x180015f83  and     ecx, 3
0x180015f86  mov     [rbx+rdx*8+10h], ecx
0x180015f8a  mov     [rbx+rdx*8+20h], r8w
0x180015f90  mov     dword ptr [rbx+rdx*8+18h], 2
0x180015f98  mov     eax, [rsp+78h+var_58]
0x180015f9c  cmp     eax, ebp
0x180015f9e  jz      short loc_180015FE4
0x180015fa0  mov     r8b, [rsp+78h+arg_38]
0x180015fa8  lea     rdx, [rax+rax*4]
0x180015fac  xor     eax, eax
0x180015fae  xorps   xmm0, xmm0
0x180015fb1  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015fb6  mov     [rbx+rdx*8+20h], rax
0x180015fbb  mov     al, r8b
0x180015fbe  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x180015fc5  neg     al
0x180015fc7  sbb     ecx, ecx
0x180015fc9  not     ecx
0x180015fcb  and     ecx, 3
0x180015fce  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015fd3  mov     [rbx+rdx*8+10h], ecx
0x180015fd7  mov     dword ptr [rbx+rdx*8+18h], 1
0x180015fdf  mov     [rbx+rdx*8+20h], r8b
0x180015fe4  cmp     r15d, ebp
0x180015fe7  jz      short loc_18001601C
0x180015fe9  xorps   xmm0, xmm0
0x180015fec  mov     eax, r15d
0x180015fef  lea     rcx, [rax+rax*4]
0x180015ff3  xor     eax, eax
0x180015ff5  movups  xmmword ptr [rbx+rcx*8], xmm0
0x180015ff9  movups  xmmword ptr [rbx+rcx*8+10h], xmm0
0x180015ffe  mov     [rbx+rcx*8+20h], rax
0x180016003  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE.Data1
0x18001600a  mov     dword ptr [rbx+rcx*8+18h], 1
0x180016012  mov     byte ptr [rbx+rcx*8+20h], 1
0x180016017  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x18001601c  mov     rax, [rsp+78h+arg_40]
0x180016024  mov     [rax], rbx
0x180016027  mov     rax, [rsp+78h+arg_48]
0x18001602f  mov     [rax], edi
0x180016031  test    esi, esi
0x180016033  jz      short loc_180016047
0x180016035  lea     rdx, [rsp+78h+arg_10]
0x18001603d  lea     rcx, [rsp+78h+var_50]
0x180016042  call    DiscpFilterConditionDestroy
0x180016047  mov     eax, esi
0x180016049  add     rsp, 38h
0x18001604d  pop     r15
0x18001604f  pop     r14
0x180016051  pop     r13
0x180016053  pop     r12
0x180016055  pop     rdi
0x180016056  pop     rsi
0x180016057  pop     rbp
0x180016058  pop     rbx
0x180016059  retn
```
