# CiBuildEaCacheContents

- ea: `0x1800d203c`
- end: `0x1800d24c3`
- name: `CiBuildEaCacheContents`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180073d2c`
- `0x18009ca38`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18002c340`
- `0x1800d203c`
- `0x1800d24cc`

## import_xrefs

- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d23ef`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d23ef`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800d243e`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800d2433`

## string_xrefs

- `0x1800d20c0`: `$Kernel.Purge.ESBCache`
- `0x1800d20d7`: `$Kernel.Purge.CIpCache`

## pseudocode

```c
__int64 __fastcall CiBuildEaCacheContents(
        char a1,
        __int16 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned int v7; // ebp
  __int64 v9; // rbx
  unsigned __int8 *v10; // rsi
  unsigned __int16 v11; // r14
  __int64 v12; // xmm1_8
  __int64 result; // rax
  int v14; // r13d
  unsigned __int8 v15; // r14
  unsigned int v16; // eax
  __int16 v17; // r15
  unsigned __int8 v18; // r14
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned __int8 v21; // r15
  unsigned int v22; // eax
  __int64 v23; // rsi
  int v25; // [rsp+48h] [rbp-A0h] BYREF
  int v26[2]; // [rsp+50h] [rbp-98h]
  _DWORD *v27; // [rsp+58h] [rbp-90h]
  _QWORD v28[8]; // [rsp+60h] [rbp-88h] BYREF

  v7 = a6;
  v27 = a7;
  *(_QWORD *)v26 = a3;
  v9 = 0;
  v10 = 0;
  v25 = 0;
  v11 = 0;
  if ( a5 && a6 >= 0x3D )
  {
    *(_QWORD *)a5 = 0;
    v7 = a6 - 61;
    *(_DWORD *)(a5 + 8) = 0;
    *(_BYTE *)(a5 + 5) = 22;
    if ( (a2 & 0x80u) != 0 )
    {
      *(_OWORD *)(a5 + 8) = *(_OWORD *)"$Kernel.Purge.CIpCache";
      v12 = *(_QWORD *)"IpCache";
    }
    else
    {
      *(_OWORD *)(a5 + 8) = *(_OWORD *)"$Kernel.Purge.ESBCache";
      v12 = *(_QWORD *)"SBCache";
    }
    v9 = a5 + 31;
    *(_QWORD *)(a5 + 23) = v12;
    v10 = (unsigned __int8 *)(a5 + 61);
    *(_OWORD *)(a5 + 31) = 0;
    *(_OWORD *)(a5 + 45) = 0;
    *(_WORD *)(a5 + 35) = 3;
    *(_BYTE *)(a5 + 37) = 2;
    *(_BYTE *)(a5 + 38) = a1;
  }
  if ( (a2 & 1) == 0 )
  {
    if ( (a2 & 2) != 0 )
    {
      if ( !a4 || !*(_QWORD *)a4 )
      {
LABEL_29:
        v14 = 2;
        goto LABEL_30;
      }
    }
    else if ( !a4 || !*(_QWORD *)a4 )
    {
      return 3221225485LL;
    }
    if ( *(_QWORD *)(a4 + 16) )
    {
      v15 = *(_BYTE *)(a4 + 8) + 7;
      if ( v9 )
      {
        if ( v7 >= v15 )
        {
          *v10 = v15;
          v10[1] = 1;
          v7 -= v15;
          *(_DWORD *)(v10 + 2) = *(_DWORD *)(a4 + 12);
          v16 = *(unsigned __int8 *)(a4 + 8);
          v10[6] = v16;
          memmove(v10 + 7, *(const void **)a4, v16);
          v10 += *v10;
        }
        else
        {
          v9 = 0;
        }
      }
      v17 = v15;
      v18 = *(_BYTE *)(a4 + 24) + 7;
      if ( v9 )
      {
        if ( v7 >= v18 )
        {
          *v10 = v18;
          v10[1] = 0;
          v7 -= v18;
          *(_DWORD *)(v10 + 2) = *(_DWORD *)(a4 + 28);
          v19 = *(unsigned __int8 *)(a4 + 24);
          v10[6] = v19;
          memmove(v10 + 7, *(const void **)(a4 + 16), v19);
          v10 += *v10;
        }
        else
        {
          v9 = 0;
        }
      }
      v11 = v17 + v18;
    }
    goto LABEL_29;
  }
  if ( a4 && (*(_QWORD *)a4 || *(_QWORD *)(a4 + 16)) )
    return 3221225485LL;
  v14 = 1;
LABEL_30:
  if ( a4 )
  {
    if ( *(_QWORD *)(a4 + 32) )
    {
      if ( v9 )
      {
        if ( v7 >= 0xE )
        {
          *(_WORD *)v10 = 1550;
          v7 -= 14;
          v20 = *(_QWORD *)(a4 + 32);
          *(_QWORD *)(v10 + 2) = *(_QWORD *)v20;
          *(_DWORD *)(v10 + 10) = *(_DWORD *)(v20 + 8);
          v10 += 14;
        }
        else
        {
          v9 = 0;
        }
      }
      v11 += 14;
    }
    if ( *(_WORD *)(a4 + 40) )
    {
      if ( v9 )
      {
        if ( v7 >= 4 )
        {
          *(_WORD *)v10 = 1796;
          v7 -= 4;
          *((_WORD *)v10 + 1) = *(_WORD *)(a4 + 40);
          v10 += 4;
        }
        else
        {
          v9 = 0;
        }
      }
      v11 += 4;
    }
    if ( *(int *)(a4 + 44) < 0 )
    {
      if ( v9 )
      {
        if ( v7 >= 6 )
        {
          *(_WORD *)v10 = 2054;
          v7 -= 6;
          *(_DWORD *)(v10 + 2) = *(_DWORD *)(a4 + 44);
          v10 += 6;
        }
        else
        {
          v9 = 0;
        }
      }
      v11 += 6;
    }
    if ( *(_QWORD *)(a4 + 48) )
    {
      v21 = *(_BYTE *)(a4 + 56) + 7;
      if ( v9 )
      {
        if ( v7 >= v21 )
        {
          *v10 = v21;
          *(_DWORD *)(v10 + 2) = 32780;
          v7 -= v21;
          v10[1] = 9;
          v22 = *(unsigned __int8 *)(a4 + 56);
          v10[6] = v22;
          memmove(v10 + 7, *(const void **)(a4 + 48), v22);
          v10 += *v10;
        }
        else
        {
          v9 = 0;
        }
      }
      v11 += v21;
    }
  }
  if ( (a2 & 0x200) == 0 && ((g_CiPolicyState & 2) != 0 || (g_CiPolicyState & 0x20) != 0) )
  {
    if ( v9 )
    {
      if ( v7 >= 0x27 )
      {
        *(_WORD *)v10 = 1063;
        *(_DWORD *)(v10 + 2) = 32780;
        v10[6] = 32;
        *(_OWORD *)(v10 + 7) = g_SiPolicyHash;
        *(_OWORD *)(v10 + 23) = xmmword_180048A08;
        if ( (g_CiPolicyState & 0x40000) != 0 )
          v14 |= 0x8000u;
      }
      else
      {
        v9 = 0;
      }
    }
    v11 += 39;
  }
  if ( v9 )
  {
    *(_WORD *)(v9 + 28) = v11;
    *(_DWORD *)v9 = v11 + 30;
    *(_DWORD *)(v9 + 24) = v14 | a2 & 0x200 | a2 & 0x400;
    if ( (a2 & 0x200) == 0 )
    {
      v23 = *(_QWORD *)v26;
      *(_QWORD *)(v9 + 16) = g_CiBlocklistUpdateTime;
      if ( v23 )
      {
        memset(v28, 0, sizeof(v28));
        result = FsRtlKernelFsControlFile(v23, 590068, 0, 0, v28, 64, &v25);
        if ( (int)result < 0 )
          return result;
        *(_QWORD *)(v9 + 8) = v28[0];
        result = CipHasPerAppRules(v23);
        if ( (int)result < 0 )
          return result;
      }
    }
    if ( (g_CiOptions & 8) != 0
      || (_BYTE)KdDebuggerEnabled && (_BYTE)KdDebuggerNotPresent != 1
      || (g_CiDeveloperMode & 0x4000) != 0 )
    {
      *(_DWORD *)(v9 + 24) |= 0x20u;
    }
    if ( (a2 & 0x40) != 0 )
      *(_DWORD *)(v9 + 24) |= 0x40u;
    if ( (g_CiDeveloperMode & 0x8000) != 0 )
      *(_DWORD *)(v9 + 24) |= 0x1000u;
    *(_WORD *)(a5 + 6) = *(_WORD *)v9;
  }
  *v27 = v11 + 61;
  if ( !a5 )
    return 0;
  result = 3221225507LL;
  if ( v9 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800d203c  mov     [rsp+arg_0], rbx
0x1800d2041  push    rbp
0x1800d2042  push    rsi
0x1800d2043  push    rdi
0x1800d2044  push    r12
0x1800d2046  push    r13
0x1800d2048  push    r14
0x1800d204a  push    r15
0x1800d204c  sub     rsp, 0B0h
0x1800d2053  mov     rax, cs:__security_cookie
0x1800d205a  xor     rax, rsp
0x1800d205d  mov     [rsp+0E8h+var_48], rax
0x1800d2065  mov     r12, [rsp+0E8h+arg_20]
0x1800d206d  mov     eax, edx
0x1800d206f  mov     ebp, [rsp+0E8h+arg_28]
0x1800d2076  mov     rdi, r9
0x1800d2079  mov     [rsp+0E8h+var_A4], edx
0x1800d207d  mov     rdx, [rsp+0E8h+arg_30]
0x1800d2085  mov     [rsp+0E8h+var_90], rdx
0x1800d208a  xor     edx, edx
0x1800d208c  mov     qword ptr [rsp+0E8h+var_98], r8
0x1800d2091  mov     ebx, edx
0x1800d2093  mov     [rsp+0E8h+var_A8], dl
0x1800d2097  mov     esi, edx
0x1800d2099  mov     [rsp+0E8h+var_A0], edx
0x1800d209d  mov     r14d, edx
0x1800d20a0  test    r12, r12
0x1800d20a3  jz      short loc_1800D2113
0x1800d20a5  cmp     ebp, 3Dh ; '='
0x1800d20a8  jb      short loc_1800D2113
0x1800d20aa  mov     [r12], rdx
0x1800d20ae  add     ebp, 0FFFFFFC3h
0x1800d20b1  mov     [r12+8], edx
0x1800d20b6  mov     byte ptr [r12+5], 16h
0x1800d20bc  test    al, al
0x1800d20be  js      short loc_1800D20D7
0x1800d20c0  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x1800d20c7  movups  xmmword ptr [r12+8], xmm0
0x1800d20cd  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x1800d20d5  jmp     short loc_1800D20EC
0x1800d20d7  movups  xmm0, xmmword ptr cs:aKernelPurgeCip; "$Kernel.Purge.CIpCache"
0x1800d20de  movups  xmmword ptr [r12+8], xmm0
0x1800d20e4  movsd   xmm1, qword ptr cs:aKernelPurgeCip+0Fh; "IpCache"
0x1800d20ec  lea     rbx, [r12+1Fh]
0x1800d20f1  movsd   qword ptr [r12+17h], xmm1
0x1800d20f8  xorps   xmm0, xmm0
0x1800d20fb  lea     rsi, [rbx+1Eh]
0x1800d20ff  movups  xmmword ptr [rbx], xmm0
0x1800d2102  movups  xmmword ptr [rbx+0Eh], xmm0
0x1800d2106  mov     word ptr [rbx+4], 3
0x1800d210c  mov     byte ptr [rbx+6], 2
0x1800d2110  mov     [rbx+7], cl
0x1800d2113  test    al, 1
0x1800d2115  jz      short loc_1800D213C
0x1800d2117  test    rdi, rdi
0x1800d211a  jz      short loc_1800D2131
0x1800d211c  cmp     [r9], rdx
0x1800d211f  jnz     short loc_1800D2127
0x1800d2121  cmp     [r9+10h], rdx
0x1800d2125  jz      short loc_1800D2131
0x1800d2127  mov     eax, 0C000000Dh
0x1800d212c  jmp     loc_1800D2497
0x1800d2131  mov     r13d, 1
0x1800d2137  jmp     loc_1800D220A
0x1800d213c  test    al, 2
0x1800d213e  jnz     short loc_1800D214C
0x1800d2140  test    rdi, rdi
0x1800d2143  jz      short loc_1800D2127
0x1800d2145  cmp     [r9], rdx
0x1800d2148  jnz     short loc_1800D215E
0x1800d214a  jmp     short loc_1800D2127
0x1800d214c  test    rdi, rdi
0x1800d214f  jz      loc_1800D2204
0x1800d2155  cmp     [r9], rdx
0x1800d2158  jz      loc_1800D2204
0x1800d215e  cmp     [r9+10h], rdx
0x1800d2162  jz      loc_1800D2204
0x1800d2168  mov     r14b, [r9+8]
0x1800d216c  add     r14b, 7
0x1800d2170  test    rbx, rbx
0x1800d2173  jz      short loc_1800D21B1
0x1800d2175  movzx   eax, r14b
0x1800d2179  cmp     ebp, eax
0x1800d217b  jnb     short loc_1800D2182
0x1800d217d  mov     rbx, rdx
0x1800d2180  jmp     short loc_1800D21B1
0x1800d2182  mov     [rsi], r14b
0x1800d2185  lea     rcx, [rsi+7]; void *
0x1800d2189  mov     byte ptr [rsi+1], 1
0x1800d218d  sub     ebp, eax
0x1800d218f  mov     eax, [r9+0Ch]
0x1800d2193  mov     [rsi+2], eax
0x1800d2196  movzx   eax, byte ptr [r9+8]
0x1800d219b  mov     [rsi+6], al
0x1800d219e  mov     r8d, eax; Size
0x1800d21a1  mov     rdx, [r9]; Src
0x1800d21a4  call    memmove
0x1800d21a9  movzx   eax, byte ptr [rsi]
0x1800d21ac  add     rsi, rax
0x1800d21af  xor     edx, edx
0x1800d21b1  movzx   r15d, r14b
0x1800d21b5  mov     r14b, [rdi+18h]
0x1800d21b9  add     r14b, 7
0x1800d21bd  test    rbx, rbx
0x1800d21c0  jz      short loc_1800D21FC
0x1800d21c2  movzx   eax, r14b
0x1800d21c6  cmp     ebp, eax
0x1800d21c8  jnb     short loc_1800D21CF
0x1800d21ca  mov     rbx, rdx
0x1800d21cd  jmp     short loc_1800D21FC
0x1800d21cf  mov     [rsi], r14b
0x1800d21d2  lea     rcx, [rsi+7]; void *
0x1800d21d6  mov     [rsi+1], dl
0x1800d21d9  sub     ebp, eax
0x1800d21db  mov     eax, [rdi+1Ch]
0x1800d21de  mov     [rsi+2], eax
0x1800d21e1  movzx   eax, byte ptr [rdi+18h]
0x1800d21e5  mov     [rsi+6], al
0x1800d21e8  mov     r8d, eax; Size
0x1800d21eb  mov     rdx, [rdi+10h]; Src
0x1800d21ef  call    memmove
0x1800d21f4  movzx   eax, byte ptr [rsi]
0x1800d21f7  add     rsi, rax
0x1800d21fa  xor     edx, edx
0x1800d21fc  movzx   r14d, r14b
0x1800d2200  add     r14w, r15w
0x1800d2204  mov     r13d, 2
0x1800d220a  mov     r9d, 4
0x1800d2210  test    rdi, rdi
0x1800d2213  jz      loc_1800D2303
0x1800d2219  lea     r8d, [r9+2]
0x1800d221d  cmp     [rdi+20h], rdx
0x1800d2221  jz      short loc_1800D2257
0x1800d2223  lea     ecx, [r9+0Ah]
0x1800d2227  test    rbx, rbx
0x1800d222a  jz      short loc_1800D2253
0x1800d222c  cmp     ebp, ecx
0x1800d222e  jnb     short loc_1800D2235
0x1800d2230  mov     rbx, rdx
0x1800d2233  jmp     short loc_1800D2253
0x1800d2235  mov     word ptr [rsi], 60Eh
0x1800d223a  add     ebp, 0FFFFFFF2h
0x1800d223d  mov     rax, [rdi+20h]
0x1800d2241  movsd   xmm0, qword ptr [rax]
0x1800d2245  movsd   qword ptr [rsi+2], xmm0
0x1800d224a  mov     eax, [rax+8]
0x1800d224d  mov     [rsi+0Ah], eax
0x1800d2250  add     rsi, rcx
0x1800d2253  add     r14w, cx
0x1800d2257  cmp     [rdi+28h], dx
0x1800d225b  jz      short loc_1800D2283
0x1800d225d  test    rbx, rbx
0x1800d2260  jz      short loc_1800D227F
0x1800d2262  cmp     ebp, r9d
0x1800d2265  jnb     short loc_1800D226C
0x1800d2267  mov     rbx, rdx
0x1800d226a  jmp     short loc_1800D227F
0x1800d226c  mov     word ptr [rsi], 704h
0x1800d2271  add     ebp, 0FFFFFFFCh
0x1800d2274  movzx   eax, word ptr [rdi+28h]
0x1800d2278  mov     [rsi+2], ax
0x1800d227c  add     rsi, r9
0x1800d227f  add     r14w, r9w
0x1800d2283  cmp     [rdi+2Ch], edx
0x1800d2286  jge     short loc_1800D22AC
0x1800d2288  test    rbx, rbx
0x1800d228b  jz      short loc_1800D22A8
0x1800d228d  cmp     ebp, r8d
0x1800d2290  jnb     short loc_1800D2297
0x1800d2292  mov     rbx, rdx
0x1800d2295  jmp     short loc_1800D22A8
0x1800d2297  mov     word ptr [rsi], 806h
0x1800d229c  add     ebp, 0FFFFFFFAh
0x1800d229f  mov     eax, [rdi+2Ch]
0x1800d22a2  mov     [rsi+2], eax
0x1800d22a5  add     rsi, r8
0x1800d22a8  add     r14w, r8w
0x1800d22ac  cmp     [rdi+30h], rdx
0x1800d22b0  jz      short loc_1800D2303
0x1800d22b2  mov     r15b, [rdi+38h]
0x1800d22b6  add     r15b, 7
0x1800d22ba  test    rbx, rbx
0x1800d22bd  jz      short loc_1800D22FB
0x1800d22bf  movzx   eax, r15b
0x1800d22c3  cmp     ebp, eax
0x1800d22c5  jnb     short loc_1800D22CC
0x1800d22c7  mov     rbx, rdx
0x1800d22ca  jmp     short loc_1800D22FB
0x1800d22cc  mov     [rsi], r15b
0x1800d22cf  lea     rcx, [rsi+7]; void *
0x1800d22d3  mov     dword ptr [rsi+2], 800Ch
0x1800d22da  sub     ebp, eax
0x1800d22dc  mov     byte ptr [rsi+1], 9
0x1800d22e0  movzx   eax, byte ptr [rdi+38h]
0x1800d22e4  mov     [rsi+6], al
0x1800d22e7  mov     r8d, eax; Size
0x1800d22ea  mov     rdx, [rdi+30h]; Src
0x1800d22ee  call    memmove
0x1800d22f3  movzx   eax, byte ptr [rsi]
0x1800d22f6  add     rsi, rax
0x1800d22f9  xor     edx, edx
0x1800d22fb  movzx   eax, r15b
0x1800d22ff  add     r14w, ax
0x1800d2303  mov     r15d, [rsp+0E8h+var_A4]
0x1800d2308  mov     ecx, r15d
0x1800d230b  and     ecx, 200h
0x1800d2311  jnz     short loc_1800D2371
0x1800d2313  mov     eax, cs:g_CiPolicyState
0x1800d2319  test    al, 2
0x1800d231b  jnz     short loc_1800D2321
0x1800d231d  test    al, 20h
0x1800d231f  jz      short loc_1800D2371
0x1800d2321  mov     r8d, 27h ; '''
0x1800d2327  test    rbx, rbx
0x1800d232a  jz      short loc_1800D236D
0x1800d232c  cmp     ebp, r8d
0x1800d232f  jnb     short loc_1800D2336
0x1800d2331  mov     rbx, rdx
0x1800d2334  jmp     short loc_1800D236D
0x1800d2336  mov     word ptr [rsi], 427h
0x1800d233b  mov     dword ptr [rsi+2], 800Ch
0x1800d2342  mov     byte ptr [rsi+6], 20h ; ' '
0x1800d2346  movups  xmm0, cs:g_SiPolicyHash
0x1800d234d  movups  xmmword ptr [rsi+7], xmm0
0x1800d2351  movups  xmm1, cs:xmmword_180048A08
0x1800d2358  movups  xmmword ptr [rsi+17h], xmm1
0x1800d235c  test    cs:g_CiPolicyState, 40000h
0x1800d2366  jz      short loc_1800D236D
0x1800d2368  bts     r13d, 0Fh
0x1800d236d  add     r14w, r8w
0x1800d2371  movzx   edi, r14w
0x1800d2375  add     edi, 1Eh
0x1800d2378  test    rbx, rbx
0x1800d237b  jz      loc_1800D247C
0x1800d2381  mov     eax, r15d
0x1800d2384  mov     [rbx+1Ch], r14w
0x1800d2389  and     eax, 400h
0x1800d238e  mov     [rbx], edi
0x1800d2390  or      eax, ecx
0x1800d2392  mov     ebp, 40h ; '@'
0x1800d2397  or      eax, r13d
0x1800d239a  mov     [rbx+18h], eax
0x1800d239d  test    ecx, ecx
0x1800d239f  jnz     loc_1800D2429
0x1800d23a5  mov     rsi, qword ptr [rsp+0E8h+var_98]
0x1800d23aa  mov     rax, cs:g_CiBlocklistUpdateTime
0x1800d23b1  mov     [rbx+10h], rax
0x1800d23b5  test    rsi, rsi
0x1800d23b8  jz      short loc_1800D2429
0x1800d23ba  mov     r8d, ebp; Size
0x1800d23bd  lea     rcx, [rsp+0E8h+var_88]; void *
0x1800d23c2  xor     edx, edx; Val
0x1800d23c4  call    memset
0x1800d23c9  lea     rax, [rsp+0E8h+var_A0]
0x1800d23ce  xor     r9d, r9d
0x1800d23d1  mov     [rsp+0E8h+var_B8], rax
0x1800d23d6  xor     r8d, r8d
0x1800d23d9  lea     rax, [rsp+0E8h+var_88]
0x1800d23de  mov     [rsp+0E8h+var_C0], ebp
0x1800d23e2  mov     edx, 900F4h
0x1800d23e7  mov     [rsp+0E8h+var_C8], rax
0x1800d23ec  mov     rcx, rsi
0x1800d23ef  call    cs:__imp_FsRtlKernelFsControlFile
0x1800d23f6  nop     dword ptr [rax+rax+00h]
0x1800d23fb  test    eax, eax
0x1800d23fd  js      loc_1800D2497
0x1800d2403  mov     rax, [rsp+0E8h+var_88]
0x1800d2408  lea     rdx, [rsp+0E8h+var_A8]
0x1800d240d  mov     rcx, rsi; int
0x1800d2410  mov     [rbx+8], rax
0x1800d2414  call    CipHasPerAppRules
0x1800d2419  xor     edx, edx
0x1800d241b  test    eax, eax
0x1800d241d  js      short loc_1800D2497
0x1800d241f  cmp     [rsp+0E8h+var_A8], dl
0x1800d2423  jz      short loc_1800D2429
0x1800d2425  or      dword ptr [rbx+18h], 10h
0x1800d2429  mov     eax, cs:g_CiOptions
0x1800d242f  test    al, 8
0x1800d2431  jnz     short loc_1800D2456
0x1800d2433  mov     rax, cs:KdDebuggerEnabled
0x1800d243a  cmp     [rax], dl
0x1800d243c  jz      short loc_1800D244A
0x1800d243e  mov     rax, cs:KdDebuggerNotPresent
0x1800d2445  cmp     byte ptr [rax], 1
0x1800d2448  jnz     short loc_1800D2456
0x1800d244a  test    cs:g_CiDeveloperMode, 4000h
0x1800d2454  jz      short loc_1800D245A
0x1800d2456  or      dword ptr [rbx+18h], 20h
0x1800d245a  test    bpl, r15b
0x1800d245d  jz      short loc_1800D2462
0x1800d245f  or      [rbx+18h], ebp
0x1800d2462  test    cs:g_CiDeveloperMode, 8000h
0x1800d246c  jz      short loc_1800D2473
0x1800d246e  bts     dword ptr [rbx+18h], 0Ch
0x1800d2473  movzx   eax, word ptr [rbx]
0x1800d2476  mov     [r12+6], ax
0x1800d247c  mov     rcx, [rsp+0E8h+var_90]
0x1800d2481  lea     eax, [rdi+1Fh]
0x1800d2484  mov     [rcx], eax
  ... truncated ...
```
