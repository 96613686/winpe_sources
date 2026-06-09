# CiBuildEaCacheContents

- ea: `0x1800d350c`
- end: `0x1800d3993`
- name: `CiBuildEaCacheContents`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800752bc`
- `0x18008f2f4`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18002c500`
- `0x1800d350c`
- `0x1800d399c`

## import_xrefs

- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d38bf`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d38bf`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800d390e`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800d3903`

## string_xrefs

- `0x1800d3590`: `$Kernel.Purge.ESBCache`
- `0x1800d35a7`: `$Kernel.Purge.CIpCache`

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
        *(_OWORD *)(v10 + 23) = xmmword_1800499F0;
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
0x1800d350c  mov     [rsp+arg_0], rbx
0x1800d3511  push    rbp
0x1800d3512  push    rsi
0x1800d3513  push    rdi
0x1800d3514  push    r12
0x1800d3516  push    r13
0x1800d3518  push    r14
0x1800d351a  push    r15
0x1800d351c  sub     rsp, 0B0h
0x1800d3523  mov     rax, cs:__security_cookie
0x1800d352a  xor     rax, rsp
0x1800d352d  mov     [rsp+0E8h+var_48], rax
0x1800d3535  mov     r12, [rsp+0E8h+arg_20]
0x1800d353d  mov     eax, edx
0x1800d353f  mov     ebp, [rsp+0E8h+arg_28]
0x1800d3546  mov     rdi, r9
0x1800d3549  mov     [rsp+0E8h+var_A4], edx
0x1800d354d  mov     rdx, [rsp+0E8h+arg_30]
0x1800d3555  mov     [rsp+0E8h+var_90], rdx
0x1800d355a  xor     edx, edx
0x1800d355c  mov     qword ptr [rsp+0E8h+var_98], r8
0x1800d3561  mov     ebx, edx
0x1800d3563  mov     [rsp+0E8h+var_A8], dl
0x1800d3567  mov     esi, edx
0x1800d3569  mov     [rsp+0E8h+var_A0], edx
0x1800d356d  mov     r14d, edx
0x1800d3570  test    r12, r12
0x1800d3573  jz      short loc_1800D35E3
0x1800d3575  cmp     ebp, 3Dh ; '='
0x1800d3578  jb      short loc_1800D35E3
0x1800d357a  mov     [r12], rdx
0x1800d357e  add     ebp, 0FFFFFFC3h
0x1800d3581  mov     [r12+8], edx
0x1800d3586  mov     byte ptr [r12+5], 16h
0x1800d358c  test    al, al
0x1800d358e  js      short loc_1800D35A7
0x1800d3590  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x1800d3597  movups  xmmword ptr [r12+8], xmm0
0x1800d359d  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x1800d35a5  jmp     short loc_1800D35BC
0x1800d35a7  movups  xmm0, xmmword ptr cs:aKernelPurgeCip; "$Kernel.Purge.CIpCache"
0x1800d35ae  movups  xmmword ptr [r12+8], xmm0
0x1800d35b4  movsd   xmm1, qword ptr cs:aKernelPurgeCip+0Fh; "IpCache"
0x1800d35bc  lea     rbx, [r12+1Fh]
0x1800d35c1  movsd   qword ptr [r12+17h], xmm1
0x1800d35c8  xorps   xmm0, xmm0
0x1800d35cb  lea     rsi, [rbx+1Eh]
0x1800d35cf  movups  xmmword ptr [rbx], xmm0
0x1800d35d2  movups  xmmword ptr [rbx+0Eh], xmm0
0x1800d35d6  mov     word ptr [rbx+4], 3
0x1800d35dc  mov     byte ptr [rbx+6], 2
0x1800d35e0  mov     [rbx+7], cl
0x1800d35e3  test    al, 1
0x1800d35e5  jz      short loc_1800D360C
0x1800d35e7  test    rdi, rdi
0x1800d35ea  jz      short loc_1800D3601
0x1800d35ec  cmp     [r9], rdx
0x1800d35ef  jnz     short loc_1800D35F7
0x1800d35f1  cmp     [r9+10h], rdx
0x1800d35f5  jz      short loc_1800D3601
0x1800d35f7  mov     eax, 0C000000Dh
0x1800d35fc  jmp     loc_1800D3967
0x1800d3601  mov     r13d, 1
0x1800d3607  jmp     loc_1800D36DA
0x1800d360c  test    al, 2
0x1800d360e  jnz     short loc_1800D361C
0x1800d3610  test    rdi, rdi
0x1800d3613  jz      short loc_1800D35F7
0x1800d3615  cmp     [r9], rdx
0x1800d3618  jnz     short loc_1800D362E
0x1800d361a  jmp     short loc_1800D35F7
0x1800d361c  test    rdi, rdi
0x1800d361f  jz      loc_1800D36D4
0x1800d3625  cmp     [r9], rdx
0x1800d3628  jz      loc_1800D36D4
0x1800d362e  cmp     [r9+10h], rdx
0x1800d3632  jz      loc_1800D36D4
0x1800d3638  mov     r14b, [r9+8]
0x1800d363c  add     r14b, 7
0x1800d3640  test    rbx, rbx
0x1800d3643  jz      short loc_1800D3681
0x1800d3645  movzx   eax, r14b
0x1800d3649  cmp     ebp, eax
0x1800d364b  jnb     short loc_1800D3652
0x1800d364d  mov     rbx, rdx
0x1800d3650  jmp     short loc_1800D3681
0x1800d3652  mov     [rsi], r14b
0x1800d3655  lea     rcx, [rsi+7]; void *
0x1800d3659  mov     byte ptr [rsi+1], 1
0x1800d365d  sub     ebp, eax
0x1800d365f  mov     eax, [r9+0Ch]
0x1800d3663  mov     [rsi+2], eax
0x1800d3666  movzx   eax, byte ptr [r9+8]
0x1800d366b  mov     [rsi+6], al
0x1800d366e  mov     r8d, eax; Size
0x1800d3671  mov     rdx, [r9]; Src
0x1800d3674  call    memmove
0x1800d3679  movzx   eax, byte ptr [rsi]
0x1800d367c  add     rsi, rax
0x1800d367f  xor     edx, edx
0x1800d3681  movzx   r15d, r14b
0x1800d3685  mov     r14b, [rdi+18h]
0x1800d3689  add     r14b, 7
0x1800d368d  test    rbx, rbx
0x1800d3690  jz      short loc_1800D36CC
0x1800d3692  movzx   eax, r14b
0x1800d3696  cmp     ebp, eax
0x1800d3698  jnb     short loc_1800D369F
0x1800d369a  mov     rbx, rdx
0x1800d369d  jmp     short loc_1800D36CC
0x1800d369f  mov     [rsi], r14b
0x1800d36a2  lea     rcx, [rsi+7]; void *
0x1800d36a6  mov     [rsi+1], dl
0x1800d36a9  sub     ebp, eax
0x1800d36ab  mov     eax, [rdi+1Ch]
0x1800d36ae  mov     [rsi+2], eax
0x1800d36b1  movzx   eax, byte ptr [rdi+18h]
0x1800d36b5  mov     [rsi+6], al
0x1800d36b8  mov     r8d, eax; Size
0x1800d36bb  mov     rdx, [rdi+10h]; Src
0x1800d36bf  call    memmove
0x1800d36c4  movzx   eax, byte ptr [rsi]
0x1800d36c7  add     rsi, rax
0x1800d36ca  xor     edx, edx
0x1800d36cc  movzx   r14d, r14b
0x1800d36d0  add     r14w, r15w
0x1800d36d4  mov     r13d, 2
0x1800d36da  mov     r9d, 4
0x1800d36e0  test    rdi, rdi
0x1800d36e3  jz      loc_1800D37D3
0x1800d36e9  lea     r8d, [r9+2]
0x1800d36ed  cmp     [rdi+20h], rdx
0x1800d36f1  jz      short loc_1800D3727
0x1800d36f3  lea     ecx, [r9+0Ah]
0x1800d36f7  test    rbx, rbx
0x1800d36fa  jz      short loc_1800D3723
0x1800d36fc  cmp     ebp, ecx
0x1800d36fe  jnb     short loc_1800D3705
0x1800d3700  mov     rbx, rdx
0x1800d3703  jmp     short loc_1800D3723
0x1800d3705  mov     word ptr [rsi], 60Eh
0x1800d370a  add     ebp, 0FFFFFFF2h
0x1800d370d  mov     rax, [rdi+20h]
0x1800d3711  movsd   xmm0, qword ptr [rax]
0x1800d3715  movsd   qword ptr [rsi+2], xmm0
0x1800d371a  mov     eax, [rax+8]
0x1800d371d  mov     [rsi+0Ah], eax
0x1800d3720  add     rsi, rcx
0x1800d3723  add     r14w, cx
0x1800d3727  cmp     [rdi+28h], dx
0x1800d372b  jz      short loc_1800D3753
0x1800d372d  test    rbx, rbx
0x1800d3730  jz      short loc_1800D374F
0x1800d3732  cmp     ebp, r9d
0x1800d3735  jnb     short loc_1800D373C
0x1800d3737  mov     rbx, rdx
0x1800d373a  jmp     short loc_1800D374F
0x1800d373c  mov     word ptr [rsi], 704h
0x1800d3741  add     ebp, 0FFFFFFFCh
0x1800d3744  movzx   eax, word ptr [rdi+28h]
0x1800d3748  mov     [rsi+2], ax
0x1800d374c  add     rsi, r9
0x1800d374f  add     r14w, r9w
0x1800d3753  cmp     [rdi+2Ch], edx
0x1800d3756  jge     short loc_1800D377C
0x1800d3758  test    rbx, rbx
0x1800d375b  jz      short loc_1800D3778
0x1800d375d  cmp     ebp, r8d
0x1800d3760  jnb     short loc_1800D3767
0x1800d3762  mov     rbx, rdx
0x1800d3765  jmp     short loc_1800D3778
0x1800d3767  mov     word ptr [rsi], 806h
0x1800d376c  add     ebp, 0FFFFFFFAh
0x1800d376f  mov     eax, [rdi+2Ch]
0x1800d3772  mov     [rsi+2], eax
0x1800d3775  add     rsi, r8
0x1800d3778  add     r14w, r8w
0x1800d377c  cmp     [rdi+30h], rdx
0x1800d3780  jz      short loc_1800D37D3
0x1800d3782  mov     r15b, [rdi+38h]
0x1800d3786  add     r15b, 7
0x1800d378a  test    rbx, rbx
0x1800d378d  jz      short loc_1800D37CB
0x1800d378f  movzx   eax, r15b
0x1800d3793  cmp     ebp, eax
0x1800d3795  jnb     short loc_1800D379C
0x1800d3797  mov     rbx, rdx
0x1800d379a  jmp     short loc_1800D37CB
0x1800d379c  mov     [rsi], r15b
0x1800d379f  lea     rcx, [rsi+7]; void *
0x1800d37a3  mov     dword ptr [rsi+2], 800Ch
0x1800d37aa  sub     ebp, eax
0x1800d37ac  mov     byte ptr [rsi+1], 9
0x1800d37b0  movzx   eax, byte ptr [rdi+38h]
0x1800d37b4  mov     [rsi+6], al
0x1800d37b7  mov     r8d, eax; Size
0x1800d37ba  mov     rdx, [rdi+30h]; Src
0x1800d37be  call    memmove
0x1800d37c3  movzx   eax, byte ptr [rsi]
0x1800d37c6  add     rsi, rax
0x1800d37c9  xor     edx, edx
0x1800d37cb  movzx   eax, r15b
0x1800d37cf  add     r14w, ax
0x1800d37d3  mov     r15d, [rsp+0E8h+var_A4]
0x1800d37d8  mov     ecx, r15d
0x1800d37db  and     ecx, 200h
0x1800d37e1  jnz     short loc_1800D3841
0x1800d37e3  mov     eax, cs:g_CiPolicyState
0x1800d37e9  test    al, 2
0x1800d37eb  jnz     short loc_1800D37F1
0x1800d37ed  test    al, 20h
0x1800d37ef  jz      short loc_1800D3841
0x1800d37f1  mov     r8d, 27h ; '''
0x1800d37f7  test    rbx, rbx
0x1800d37fa  jz      short loc_1800D383D
0x1800d37fc  cmp     ebp, r8d
0x1800d37ff  jnb     short loc_1800D3806
0x1800d3801  mov     rbx, rdx
0x1800d3804  jmp     short loc_1800D383D
0x1800d3806  mov     word ptr [rsi], 427h
0x1800d380b  mov     dword ptr [rsi+2], 800Ch
0x1800d3812  mov     byte ptr [rsi+6], 20h ; ' '
0x1800d3816  movups  xmm0, cs:g_SiPolicyHash
0x1800d381d  movups  xmmword ptr [rsi+7], xmm0
0x1800d3821  movups  xmm1, cs:xmmword_1800499F0
0x1800d3828  movups  xmmword ptr [rsi+17h], xmm1
0x1800d382c  test    cs:g_CiPolicyState, 40000h
0x1800d3836  jz      short loc_1800D383D
0x1800d3838  bts     r13d, 0Fh
0x1800d383d  add     r14w, r8w
0x1800d3841  movzx   edi, r14w
0x1800d3845  add     edi, 1Eh
0x1800d3848  test    rbx, rbx
0x1800d384b  jz      loc_1800D394C
0x1800d3851  mov     eax, r15d
0x1800d3854  mov     [rbx+1Ch], r14w
0x1800d3859  and     eax, 400h
0x1800d385e  mov     [rbx], edi
0x1800d3860  or      eax, ecx
0x1800d3862  mov     ebp, 40h ; '@'
0x1800d3867  or      eax, r13d
0x1800d386a  mov     [rbx+18h], eax
0x1800d386d  test    ecx, ecx
0x1800d386f  jnz     loc_1800D38F9
0x1800d3875  mov     rsi, qword ptr [rsp+0E8h+var_98]
0x1800d387a  mov     rax, cs:g_CiBlocklistUpdateTime
0x1800d3881  mov     [rbx+10h], rax
0x1800d3885  test    rsi, rsi
0x1800d3888  jz      short loc_1800D38F9
0x1800d388a  mov     r8d, ebp; Size
0x1800d388d  lea     rcx, [rsp+0E8h+var_88]; void *
0x1800d3892  xor     edx, edx; Val
0x1800d3894  call    memset
0x1800d3899  lea     rax, [rsp+0E8h+var_A0]
0x1800d389e  xor     r9d, r9d
0x1800d38a1  mov     [rsp+0E8h+var_B8], rax
0x1800d38a6  xor     r8d, r8d
0x1800d38a9  lea     rax, [rsp+0E8h+var_88]
0x1800d38ae  mov     [rsp+0E8h+var_C0], ebp
0x1800d38b2  mov     edx, 900F4h
0x1800d38b7  mov     [rsp+0E8h+var_C8], rax
0x1800d38bc  mov     rcx, rsi
0x1800d38bf  call    cs:__imp_FsRtlKernelFsControlFile
0x1800d38c6  nop     dword ptr [rax+rax+00h]
0x1800d38cb  test    eax, eax
0x1800d38cd  js      loc_1800D3967
0x1800d38d3  mov     rax, [rsp+0E8h+var_88]
0x1800d38d8  lea     rdx, [rsp+0E8h+var_A8]
0x1800d38dd  mov     rcx, rsi; int
0x1800d38e0  mov     [rbx+8], rax
0x1800d38e4  call    CipHasPerAppRules
0x1800d38e9  xor     edx, edx
0x1800d38eb  test    eax, eax
0x1800d38ed  js      short loc_1800D3967
0x1800d38ef  cmp     [rsp+0E8h+var_A8], dl
0x1800d38f3  jz      short loc_1800D38F9
0x1800d38f5  or      dword ptr [rbx+18h], 10h
0x1800d38f9  mov     eax, cs:g_CiOptions
0x1800d38ff  test    al, 8
0x1800d3901  jnz     short loc_1800D3926
0x1800d3903  mov     rax, cs:KdDebuggerEnabled
0x1800d390a  cmp     [rax], dl
0x1800d390c  jz      short loc_1800D391A
0x1800d390e  mov     rax, cs:KdDebuggerNotPresent
0x1800d3915  cmp     byte ptr [rax], 1
0x1800d3918  jnz     short loc_1800D3926
0x1800d391a  test    cs:g_CiDeveloperMode, 4000h
0x1800d3924  jz      short loc_1800D392A
0x1800d3926  or      dword ptr [rbx+18h], 20h
0x1800d392a  test    bpl, r15b
0x1800d392d  jz      short loc_1800D3932
0x1800d392f  or      [rbx+18h], ebp
0x1800d3932  test    cs:g_CiDeveloperMode, 8000h
0x1800d393c  jz      short loc_1800D3943
0x1800d393e  bts     dword ptr [rbx+18h], 0Ch
0x1800d3943  movzx   eax, word ptr [rbx]
0x1800d3946  mov     [r12+6], ax
0x1800d394c  mov     rcx, [rsp+0E8h+var_90]
0x1800d3951  lea     eax, [rdi+1Fh]
0x1800d3954  mov     [rcx], eax
  ... truncated ...
```
