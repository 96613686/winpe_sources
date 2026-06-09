# CiBuildEaCacheContents

- ea: `0x1800d34fc`
- end: `0x1800d3983`
- name: `CiBuildEaCacheContents`
- size: `1159`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180074fdc`
- `0x18009e068`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18002c380`
- `0x1800d34fc`
- `0x1800d398c`

## import_xrefs

- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d38af`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1800d38af`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800d38fe`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800d38f3`

## string_xrefs

- `0x1800d3580`: `$Kernel.Purge.ESBCache`
- `0x1800d3597`: `$Kernel.Purge.CIpCache`

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
        *(_OWORD *)(v10 + 23) = xmmword_1800499E8;
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
0x1800d34fc  mov     [rsp+arg_0], rbx
0x1800d3501  push    rbp
0x1800d3502  push    rsi
0x1800d3503  push    rdi
0x1800d3504  push    r12
0x1800d3506  push    r13
0x1800d3508  push    r14
0x1800d350a  push    r15
0x1800d350c  sub     rsp, 0B0h
0x1800d3513  mov     rax, cs:__security_cookie
0x1800d351a  xor     rax, rsp
0x1800d351d  mov     [rsp+0E8h+var_48], rax
0x1800d3525  mov     r12, [rsp+0E8h+arg_20]
0x1800d352d  mov     eax, edx
0x1800d352f  mov     ebp, [rsp+0E8h+arg_28]
0x1800d3536  mov     rdi, r9
0x1800d3539  mov     [rsp+0E8h+var_A4], edx
0x1800d353d  mov     rdx, [rsp+0E8h+arg_30]
0x1800d3545  mov     [rsp+0E8h+var_90], rdx
0x1800d354a  xor     edx, edx
0x1800d354c  mov     qword ptr [rsp+0E8h+var_98], r8
0x1800d3551  mov     ebx, edx
0x1800d3553  mov     [rsp+0E8h+var_A8], dl
0x1800d3557  mov     esi, edx
0x1800d3559  mov     [rsp+0E8h+var_A0], edx
0x1800d355d  mov     r14d, edx
0x1800d3560  test    r12, r12
0x1800d3563  jz      short loc_1800D35D3
0x1800d3565  cmp     ebp, 3Dh ; '='
0x1800d3568  jb      short loc_1800D35D3
0x1800d356a  mov     [r12], rdx
0x1800d356e  add     ebp, 0FFFFFFC3h
0x1800d3571  mov     [r12+8], edx
0x1800d3576  mov     byte ptr [r12+5], 16h
0x1800d357c  test    al, al
0x1800d357e  js      short loc_1800D3597
0x1800d3580  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x1800d3587  movups  xmmword ptr [r12+8], xmm0
0x1800d358d  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x1800d3595  jmp     short loc_1800D35AC
0x1800d3597  movups  xmm0, xmmword ptr cs:aKernelPurgeCip; "$Kernel.Purge.CIpCache"
0x1800d359e  movups  xmmword ptr [r12+8], xmm0
0x1800d35a4  movsd   xmm1, qword ptr cs:aKernelPurgeCip+0Fh; "IpCache"
0x1800d35ac  lea     rbx, [r12+1Fh]
0x1800d35b1  movsd   qword ptr [r12+17h], xmm1
0x1800d35b8  xorps   xmm0, xmm0
0x1800d35bb  lea     rsi, [rbx+1Eh]
0x1800d35bf  movups  xmmword ptr [rbx], xmm0
0x1800d35c2  movups  xmmword ptr [rbx+0Eh], xmm0
0x1800d35c6  mov     word ptr [rbx+4], 3
0x1800d35cc  mov     byte ptr [rbx+6], 2
0x1800d35d0  mov     [rbx+7], cl
0x1800d35d3  test    al, 1
0x1800d35d5  jz      short loc_1800D35FC
0x1800d35d7  test    rdi, rdi
0x1800d35da  jz      short loc_1800D35F1
0x1800d35dc  cmp     [r9], rdx
0x1800d35df  jnz     short loc_1800D35E7
0x1800d35e1  cmp     [r9+10h], rdx
0x1800d35e5  jz      short loc_1800D35F1
0x1800d35e7  mov     eax, 0C000000Dh
0x1800d35ec  jmp     loc_1800D3957
0x1800d35f1  mov     r13d, 1
0x1800d35f7  jmp     loc_1800D36CA
0x1800d35fc  test    al, 2
0x1800d35fe  jnz     short loc_1800D360C
0x1800d3600  test    rdi, rdi
0x1800d3603  jz      short loc_1800D35E7
0x1800d3605  cmp     [r9], rdx
0x1800d3608  jnz     short loc_1800D361E
0x1800d360a  jmp     short loc_1800D35E7
0x1800d360c  test    rdi, rdi
0x1800d360f  jz      loc_1800D36C4
0x1800d3615  cmp     [r9], rdx
0x1800d3618  jz      loc_1800D36C4
0x1800d361e  cmp     [r9+10h], rdx
0x1800d3622  jz      loc_1800D36C4
0x1800d3628  mov     r14b, [r9+8]
0x1800d362c  add     r14b, 7
0x1800d3630  test    rbx, rbx
0x1800d3633  jz      short loc_1800D3671
0x1800d3635  movzx   eax, r14b
0x1800d3639  cmp     ebp, eax
0x1800d363b  jnb     short loc_1800D3642
0x1800d363d  mov     rbx, rdx
0x1800d3640  jmp     short loc_1800D3671
0x1800d3642  mov     [rsi], r14b
0x1800d3645  lea     rcx, [rsi+7]; void *
0x1800d3649  mov     byte ptr [rsi+1], 1
0x1800d364d  sub     ebp, eax
0x1800d364f  mov     eax, [r9+0Ch]
0x1800d3653  mov     [rsi+2], eax
0x1800d3656  movzx   eax, byte ptr [r9+8]
0x1800d365b  mov     [rsi+6], al
0x1800d365e  mov     r8d, eax; Size
0x1800d3661  mov     rdx, [r9]; Src
0x1800d3664  call    memmove
0x1800d3669  movzx   eax, byte ptr [rsi]
0x1800d366c  add     rsi, rax
0x1800d366f  xor     edx, edx
0x1800d3671  movzx   r15d, r14b
0x1800d3675  mov     r14b, [rdi+18h]
0x1800d3679  add     r14b, 7
0x1800d367d  test    rbx, rbx
0x1800d3680  jz      short loc_1800D36BC
0x1800d3682  movzx   eax, r14b
0x1800d3686  cmp     ebp, eax
0x1800d3688  jnb     short loc_1800D368F
0x1800d368a  mov     rbx, rdx
0x1800d368d  jmp     short loc_1800D36BC
0x1800d368f  mov     [rsi], r14b
0x1800d3692  lea     rcx, [rsi+7]; void *
0x1800d3696  mov     [rsi+1], dl
0x1800d3699  sub     ebp, eax
0x1800d369b  mov     eax, [rdi+1Ch]
0x1800d369e  mov     [rsi+2], eax
0x1800d36a1  movzx   eax, byte ptr [rdi+18h]
0x1800d36a5  mov     [rsi+6], al
0x1800d36a8  mov     r8d, eax; Size
0x1800d36ab  mov     rdx, [rdi+10h]; Src
0x1800d36af  call    memmove
0x1800d36b4  movzx   eax, byte ptr [rsi]
0x1800d36b7  add     rsi, rax
0x1800d36ba  xor     edx, edx
0x1800d36bc  movzx   r14d, r14b
0x1800d36c0  add     r14w, r15w
0x1800d36c4  mov     r13d, 2
0x1800d36ca  mov     r9d, 4
0x1800d36d0  test    rdi, rdi
0x1800d36d3  jz      loc_1800D37C3
0x1800d36d9  lea     r8d, [r9+2]
0x1800d36dd  cmp     [rdi+20h], rdx
0x1800d36e1  jz      short loc_1800D3717
0x1800d36e3  lea     ecx, [r9+0Ah]
0x1800d36e7  test    rbx, rbx
0x1800d36ea  jz      short loc_1800D3713
0x1800d36ec  cmp     ebp, ecx
0x1800d36ee  jnb     short loc_1800D36F5
0x1800d36f0  mov     rbx, rdx
0x1800d36f3  jmp     short loc_1800D3713
0x1800d36f5  mov     word ptr [rsi], 60Eh
0x1800d36fa  add     ebp, 0FFFFFFF2h
0x1800d36fd  mov     rax, [rdi+20h]
0x1800d3701  movsd   xmm0, qword ptr [rax]
0x1800d3705  movsd   qword ptr [rsi+2], xmm0
0x1800d370a  mov     eax, [rax+8]
0x1800d370d  mov     [rsi+0Ah], eax
0x1800d3710  add     rsi, rcx
0x1800d3713  add     r14w, cx
0x1800d3717  cmp     [rdi+28h], dx
0x1800d371b  jz      short loc_1800D3743
0x1800d371d  test    rbx, rbx
0x1800d3720  jz      short loc_1800D373F
0x1800d3722  cmp     ebp, r9d
0x1800d3725  jnb     short loc_1800D372C
0x1800d3727  mov     rbx, rdx
0x1800d372a  jmp     short loc_1800D373F
0x1800d372c  mov     word ptr [rsi], 704h
0x1800d3731  add     ebp, 0FFFFFFFCh
0x1800d3734  movzx   eax, word ptr [rdi+28h]
0x1800d3738  mov     [rsi+2], ax
0x1800d373c  add     rsi, r9
0x1800d373f  add     r14w, r9w
0x1800d3743  cmp     [rdi+2Ch], edx
0x1800d3746  jge     short loc_1800D376C
0x1800d3748  test    rbx, rbx
0x1800d374b  jz      short loc_1800D3768
0x1800d374d  cmp     ebp, r8d
0x1800d3750  jnb     short loc_1800D3757
0x1800d3752  mov     rbx, rdx
0x1800d3755  jmp     short loc_1800D3768
0x1800d3757  mov     word ptr [rsi], 806h
0x1800d375c  add     ebp, 0FFFFFFFAh
0x1800d375f  mov     eax, [rdi+2Ch]
0x1800d3762  mov     [rsi+2], eax
0x1800d3765  add     rsi, r8
0x1800d3768  add     r14w, r8w
0x1800d376c  cmp     [rdi+30h], rdx
0x1800d3770  jz      short loc_1800D37C3
0x1800d3772  mov     r15b, [rdi+38h]
0x1800d3776  add     r15b, 7
0x1800d377a  test    rbx, rbx
0x1800d377d  jz      short loc_1800D37BB
0x1800d377f  movzx   eax, r15b
0x1800d3783  cmp     ebp, eax
0x1800d3785  jnb     short loc_1800D378C
0x1800d3787  mov     rbx, rdx
0x1800d378a  jmp     short loc_1800D37BB
0x1800d378c  mov     [rsi], r15b
0x1800d378f  lea     rcx, [rsi+7]; void *
0x1800d3793  mov     dword ptr [rsi+2], 800Ch
0x1800d379a  sub     ebp, eax
0x1800d379c  mov     byte ptr [rsi+1], 9
0x1800d37a0  movzx   eax, byte ptr [rdi+38h]
0x1800d37a4  mov     [rsi+6], al
0x1800d37a7  mov     r8d, eax; Size
0x1800d37aa  mov     rdx, [rdi+30h]; Src
0x1800d37ae  call    memmove
0x1800d37b3  movzx   eax, byte ptr [rsi]
0x1800d37b6  add     rsi, rax
0x1800d37b9  xor     edx, edx
0x1800d37bb  movzx   eax, r15b
0x1800d37bf  add     r14w, ax
0x1800d37c3  mov     r15d, [rsp+0E8h+var_A4]
0x1800d37c8  mov     ecx, r15d
0x1800d37cb  and     ecx, 200h
0x1800d37d1  jnz     short loc_1800D3831
0x1800d37d3  mov     eax, cs:g_CiPolicyState
0x1800d37d9  test    al, 2
0x1800d37db  jnz     short loc_1800D37E1
0x1800d37dd  test    al, 20h
0x1800d37df  jz      short loc_1800D3831
0x1800d37e1  mov     r8d, 27h ; '''
0x1800d37e7  test    rbx, rbx
0x1800d37ea  jz      short loc_1800D382D
0x1800d37ec  cmp     ebp, r8d
0x1800d37ef  jnb     short loc_1800D37F6
0x1800d37f1  mov     rbx, rdx
0x1800d37f4  jmp     short loc_1800D382D
0x1800d37f6  mov     word ptr [rsi], 427h
0x1800d37fb  mov     dword ptr [rsi+2], 800Ch
0x1800d3802  mov     byte ptr [rsi+6], 20h ; ' '
0x1800d3806  movups  xmm0, cs:g_SiPolicyHash
0x1800d380d  movups  xmmword ptr [rsi+7], xmm0
0x1800d3811  movups  xmm1, cs:xmmword_1800499E8
0x1800d3818  movups  xmmword ptr [rsi+17h], xmm1
0x1800d381c  test    cs:g_CiPolicyState, 40000h
0x1800d3826  jz      short loc_1800D382D
0x1800d3828  bts     r13d, 0Fh
0x1800d382d  add     r14w, r8w
0x1800d3831  movzx   edi, r14w
0x1800d3835  add     edi, 1Eh
0x1800d3838  test    rbx, rbx
0x1800d383b  jz      loc_1800D393C
0x1800d3841  mov     eax, r15d
0x1800d3844  mov     [rbx+1Ch], r14w
0x1800d3849  and     eax, 400h
0x1800d384e  mov     [rbx], edi
0x1800d3850  or      eax, ecx
0x1800d3852  mov     ebp, 40h ; '@'
0x1800d3857  or      eax, r13d
0x1800d385a  mov     [rbx+18h], eax
0x1800d385d  test    ecx, ecx
0x1800d385f  jnz     loc_1800D38E9
0x1800d3865  mov     rsi, qword ptr [rsp+0E8h+var_98]
0x1800d386a  mov     rax, cs:g_CiBlocklistUpdateTime
0x1800d3871  mov     [rbx+10h], rax
0x1800d3875  test    rsi, rsi
0x1800d3878  jz      short loc_1800D38E9
0x1800d387a  mov     r8d, ebp; Size
0x1800d387d  lea     rcx, [rsp+0E8h+var_88]; void *
0x1800d3882  xor     edx, edx; Val
0x1800d3884  call    memset
0x1800d3889  lea     rax, [rsp+0E8h+var_A0]
0x1800d388e  xor     r9d, r9d
0x1800d3891  mov     [rsp+0E8h+var_B8], rax
0x1800d3896  xor     r8d, r8d
0x1800d3899  lea     rax, [rsp+0E8h+var_88]
0x1800d389e  mov     [rsp+0E8h+var_C0], ebp
0x1800d38a2  mov     edx, 900F4h
0x1800d38a7  mov     [rsp+0E8h+var_C8], rax
0x1800d38ac  mov     rcx, rsi
0x1800d38af  call    cs:__imp_FsRtlKernelFsControlFile
0x1800d38b6  nop     dword ptr [rax+rax+00h]
0x1800d38bb  test    eax, eax
0x1800d38bd  js      loc_1800D3957
0x1800d38c3  mov     rax, [rsp+0E8h+var_88]
0x1800d38c8  lea     rdx, [rsp+0E8h+var_A8]
0x1800d38cd  mov     rcx, rsi; int
0x1800d38d0  mov     [rbx+8], rax
0x1800d38d4  call    CipHasPerAppRules
0x1800d38d9  xor     edx, edx
0x1800d38db  test    eax, eax
0x1800d38dd  js      short loc_1800D3957
0x1800d38df  cmp     [rsp+0E8h+var_A8], dl
0x1800d38e3  jz      short loc_1800D38E9
0x1800d38e5  or      dword ptr [rbx+18h], 10h
0x1800d38e9  mov     eax, cs:g_CiOptions
0x1800d38ef  test    al, 8
0x1800d38f1  jnz     short loc_1800D3916
0x1800d38f3  mov     rax, cs:KdDebuggerEnabled
0x1800d38fa  cmp     [rax], dl
0x1800d38fc  jz      short loc_1800D390A
0x1800d38fe  mov     rax, cs:KdDebuggerNotPresent
0x1800d3905  cmp     byte ptr [rax], 1
0x1800d3908  jnz     short loc_1800D3916
0x1800d390a  test    cs:g_CiDeveloperMode, 4000h
0x1800d3914  jz      short loc_1800D391A
0x1800d3916  or      dword ptr [rbx+18h], 20h
0x1800d391a  test    bpl, r15b
0x1800d391d  jz      short loc_1800D3922
0x1800d391f  or      [rbx+18h], ebp
0x1800d3922  test    cs:g_CiDeveloperMode, 8000h
0x1800d392c  jz      short loc_1800D3933
0x1800d392e  bts     dword ptr [rbx+18h], 0Ch
0x1800d3933  movzx   eax, word ptr [rbx]
0x1800d3936  mov     [r12+6], ax
0x1800d393c  mov     rcx, [rsp+0E8h+var_90]
0x1800d3941  lea     eax, [rdi+1Fh]
0x1800d3944  mov     [rcx], eax
  ... truncated ...
```
