# _CryptBaseInitialize

- ea: `0x180001220`
- end: `0x1800016d7`
- name: `_CryptBaseInitialize`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x180001220`
- `0x1800016e0`

## import_xrefs

- `ntdll!NtClose` at `0x1800016c2`
- `ntdll!NtClose` at `0x1800016c2`
- `api-ms-win-core-xstate-l2-1-0!GetEnabledXStateFeatures` at `0x18000162f`
- `api-ms-win-core-xstate-l2-1-0!GetEnabledXStateFeatures` at `0x18000162f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001232`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001232`

## pseudocode

```c
char __fastcall CryptBaseInitialize(HMODULE a1, int a2)
{
  __int64 v2; // rdx
  const char *v3; // rcx
  int v4; // r9d
  int v10; // r11d
  int v11; // r8d
  signed int v12; // r10d
  int v13; // edi
  int v19; // ecx
  int v20; // edi
  int v26; // ecx
  __int64 v27; // rdi
  int v28; // esi
  int v34; // ecx
  __int64 v35; // rdi
  int v36; // esi
  int v42; // ecx
  __int64 v43; // rdi
  int v44; // esi
  int v50; // ecx
  __int64 v51; // rdi
  int v52; // esi
  int v58; // ecx
  __int64 v59; // rdi
  int v60; // esi
  int v66; // ecx
  __int64 v67; // rdi
  int v68; // esi
  int v74; // ecx
  __int64 v75; // rdi
  int v76; // esi
  int v82; // ecx
  __int64 v83; // rdi
  int v84; // esi
  int v90; // ecx
  char EnabledXStateFeatures; // al
  int v112; // ecx
  void *v115; // r9
  int v116; // [rsp+20h] [rbp-20h]
  int v117; // [rsp+24h] [rbp-1Ch]
  int v118; // [rsp+28h] [rbp-18h]
  int v119; // [rsp+2Ch] [rbp-14h]

  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    if ( !g_hKsecDD )
    {
      if ( (g_SymCryptFlags & 1) != 0 )
      {
LABEL_76:
        EncryptMemoryInitialize(v3, v2);
        return 1;
      }
      v4 = 0;
      _RAX = 0;
      __asm { cpuid }
      v10 = _RAX;
      v116 = _RAX;
      v117 = _RBX;
      v11 = -16352;
      v118 = _RCX;
      v12 = 0;
      v119 = _RDX;
      do
      {
        v13 = LOBYTE(cpuidBitInfo[v12]);
        if ( v13 != v4 )
        {
          _RAX = LOBYTE(cpuidBitInfo[v12]);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v13;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v13 > v10 || (v19 = *(&v116 + BYTE1(cpuidBitInfo[v12])), !_bittest(&v19, BYTE2(cpuidBitInfo[v12]))) )
          v11 |= HIDWORD(cpuidBitInfo[v12]);
        v20 = LOBYTE(cpuidBitInfo[v12 + 1]);
        if ( v20 != v4 )
        {
          _RAX = LOBYTE(cpuidBitInfo[v12 + 1]);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v20;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v20 > v10 || (v26 = *(&v116 + BYTE1(cpuidBitInfo[v12 + 1])), !_bittest(&v26, BYTE2(cpuidBitInfo[v12 + 1]))) )
          v11 |= HIDWORD(cpuidBitInfo[v12 + 1]);
        v27 = 8LL * v12 + 16;
        v28 = *((unsigned __int8 *)cpuidBitInfo + v27);
        if ( v28 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v27);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v28;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v28 > v10
          || (v34 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v27 + 1)),
              !_bittest(&v34, *((unsigned __int8 *)cpuidBitInfo + v27 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v27 + 4);
        }
        v35 = 8LL * v12 + 24;
        v36 = *((unsigned __int8 *)cpuidBitInfo + v35);
        if ( v36 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v35);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v36;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v36 > v10
          || (v42 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v35 + 1)),
              !_bittest(&v42, *((unsigned __int8 *)cpuidBitInfo + v35 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v35 + 4);
        }
        v43 = 8LL * v12 + 32;
        v44 = *((unsigned __int8 *)cpuidBitInfo + v43);
        if ( v44 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v43);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v44;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v44 > v10
          || (v50 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v43 + 1)),
              !_bittest(&v50, *((unsigned __int8 *)cpuidBitInfo + v43 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v43 + 4);
        }
        v51 = 8LL * v12 + 40;
        v52 = *((unsigned __int8 *)cpuidBitInfo + v51);
        if ( v52 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v51);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v52;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v52 > v10
          || (v58 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v51 + 1)),
              !_bittest(&v58, *((unsigned __int8 *)cpuidBitInfo + v51 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v51 + 4);
        }
        v59 = 8LL * v12 + 48;
        v60 = *((unsigned __int8 *)cpuidBitInfo + v59);
        if ( v60 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v59);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v60;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v60 > v10
          || (v66 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v59 + 1)),
              !_bittest(&v66, *((unsigned __int8 *)cpuidBitInfo + v59 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v59 + 4);
        }
        v67 = 8LL * v12 + 56;
        v68 = *((unsigned __int8 *)cpuidBitInfo + v67);
        if ( v68 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v67);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v68;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v68 > v10
          || (v74 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v67 + 1)),
              !_bittest(&v74, *((unsigned __int8 *)cpuidBitInfo + v67 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v67 + 4);
        }
        v75 = 8LL * v12 + 64;
        v76 = *((unsigned __int8 *)cpuidBitInfo + v75);
        if ( v76 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v75);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v76;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v76 > v10
          || (v82 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v75 + 1)),
              !_bittest(&v82, *((unsigned __int8 *)cpuidBitInfo + v75 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v75 + 4);
        }
        v83 = 8LL * v12 + 72;
        v84 = *((unsigned __int8 *)cpuidBitInfo + v83);
        if ( v84 != v4 )
        {
          _RAX = *((unsigned __int8 *)cpuidBitInfo + v83);
          __asm { cpuid }
          v116 = _RAX;
          v4 = v84;
          v117 = _RBX;
          v118 = _RCX;
          v119 = _RDX;
        }
        if ( v84 > v10
          || (v90 = *(&v116 + *((unsigned __int8 *)cpuidBitInfo + v83 + 1)),
              !_bittest(&v90, *((unsigned __int8 *)cpuidBitInfo + v83 + 2))) )
        {
          v11 |= *(_DWORD *)((char *)cpuidBitInfo + v83 + 4);
        }
        v12 += 10;
      }
      while ( (unsigned int)v12 < 0x14 );
      _RAX = 1;
      __asm { cpuid }
      if ( (_RCX & 0x8000000) == 0 )
        goto LABEL_60;
      __asm { xgetbv }
      if ( (_RAX & 6) == 6 )
      {
        if ( (_RAX & 0xE0) == 0xE0 )
        {
LABEL_62:
          if ( (v11 & 4) == 0 )
          {
            _RAX = 0;
            __asm { cpuid }
            if ( (_DWORD)_RBX == 1752462657 && (_DWORD)_RCX == 1145913699 && (_DWORD)_RDX == 1769238117 )
            {
              _RAX = 1;
              __asm { cpuid }
              if ( (((int)_RAX >> 8) & 0xF) != 0xF || (unsigned int)(unsigned __int8)((int)_RAX >> 20) + 15 < 0x15 )
                v11 |= 4u;
            }
          }
          _RAX = 1;
          g_SymCryptCpuFeaturesNotPresent = v11;
          __asm { cpuid }
          g_SymCryptCpuid1 = _RAX;
          dword_1800075C4 = _RBX;
          dword_1800075C8 = _RCX;
          dword_1800075CC = _RDX;
          EnabledXStateFeatures = GetEnabledXStateFeatures();
          v112 = g_SymCryptCpuFeaturesNotPresent;
          if ( (EnabledXStateFeatures & 4) == 0 )
            v112 = g_SymCryptCpuFeaturesNotPresent | 0x10;
          if ( (EnabledXStateFeatures & 0xE0) == 0 )
            v112 |= 0x1000u;
          g_SymCryptCpuFeaturesNotPresent = v112 & 0xFFFFFFDF;
          _InterlockedOr(&g_SymCryptFlags, 1u);
          v3 = "v104.0.0__2026-03-28T02:17:10+00:00_df5eaa1_2026-03-30T17:48:52";
          if ( aV1040020260328[0] )
          {
            while ( *++v3 != 0 )
              ;
          }
          g_SymCryptCpuFeaturesPresentCheck = ~g_SymCryptCpuFeaturesNotPresent;
          goto LABEL_76;
        }
      }
      else
      {
LABEL_60:
        v11 |= 0x10u;
      }
      v11 |= 0x1000u;
      goto LABEL_62;
    }
  }
  else if ( !a2 )
  {
    v115 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hKsecDD, 0);
    if ( v115 )
      NtClose(v115);
  }
  return 1;
}

```

## disassembly

```asm
0x180001220  push    rbp
0x180001222  mov     rbp, rsp
0x180001225  sub     rsp, 40h
0x180001229  cmp     edx, 1
0x18000122c  jnz     loc_1800016AC
0x180001232  call    cs:__imp_DisableThreadLibraryCalls
0x180001239  nop     dword ptr [rax+rax+00h]
0x18000123e  cmp     cs:g_hKsecDD, 0
0x180001246  jnz     loc_1800016CE
0x18000124c  test    byte ptr cs:g_SymCryptFlags, 1
0x180001253  jnz     loc_18000169E
0x180001259  mov     [rsp+40h+arg_0], rbx
0x18000125e  xor     r9d, r9d
0x180001261  xor     eax, eax
0x180001263  mov     [rsp+40h+arg_10], rsi
0x180001268  xor     ecx, ecx
0x18000126a  mov     [rsp+40h+var_8], rdi
0x18000126f  cpuid
0x180001271  mov     [rsp+40h+var_10], r14
0x180001276  mov     r11d, eax
0x180001279  mov     [rbp+var_20], eax
0x18000127c  lea     r14, cpuidBitInfo
0x180001283  mov     [rbp+var_1C], ebx
0x180001286  mov     r8d, 0FFFFC020h
0x18000128c  mov     [rbp+var_18], ecx
0x18000128f  mov     r10d, r9d
0x180001292  mov     [rbp+var_14], edx
0x180001295  nop     word ptr [rax+rax+00000000h]
0x1800012a0  movsxd  rsi, r10d
0x1800012a3  movzx   edi, byte ptr [r14+rsi*8]
0x1800012a8  cmp     edi, r9d
0x1800012ab  jz      short loc_1800012C2
0x1800012ad  mov     eax, edi
0x1800012af  xor     ecx, ecx
0x1800012b1  cpuid
0x1800012b3  mov     [rbp+var_20], eax
0x1800012b6  mov     r9d, edi
0x1800012b9  mov     [rbp+var_1C], ebx
0x1800012bc  mov     [rbp+var_18], ecx
0x1800012bf  mov     [rbp+var_14], edx
0x1800012c2  cmp     edi, r11d
0x1800012c5  jg      short loc_1800012DC
0x1800012c7  movzx   eax, byte ptr [r14+rsi*8+1]
0x1800012cd  movzx   edx, byte ptr [r14+rsi*8+2]
0x1800012d3  mov     ecx, [rbp+rax*4+var_20]
0x1800012d7  bt      ecx, edx
0x1800012da  jb      short loc_1800012E1
0x1800012dc  or      r8d, [r14+rsi*8+4]
0x1800012e1  movzx   edi, byte ptr [r14+rsi*8+8]
0x1800012e7  cmp     edi, r9d
0x1800012ea  jz      short loc_180001301
0x1800012ec  mov     eax, edi
0x1800012ee  xor     ecx, ecx
0x1800012f0  cpuid
0x1800012f2  mov     [rbp+var_20], eax
0x1800012f5  mov     r9d, edi
0x1800012f8  mov     [rbp+var_1C], ebx
0x1800012fb  mov     [rbp+var_18], ecx
0x1800012fe  mov     [rbp+var_14], edx
0x180001301  cmp     edi, r11d
0x180001304  jg      short loc_18000131B
0x180001306  movzx   eax, byte ptr [r14+rsi*8+9]
0x18000130c  movzx   edx, byte ptr [r14+rsi*8+0Ah]
0x180001312  mov     ecx, [rbp+rax*4+var_20]
0x180001316  bt      ecx, edx
0x180001319  jb      short loc_180001320
0x18000131b  or      r8d, [r14+rsi*8+0Ch]
0x180001320  movsxd  rax, r10d
0x180001323  lea     rdi, ds:10h[rax*8]
0x18000132b  movzx   esi, byte ptr [rdi+r14]
0x180001330  cmp     esi, r9d
0x180001333  jz      short loc_18000134A
0x180001335  mov     eax, esi
0x180001337  xor     ecx, ecx
0x180001339  cpuid
0x18000133b  mov     [rbp+var_20], eax
0x18000133e  mov     r9d, esi
0x180001341  mov     [rbp+var_1C], ebx
0x180001344  mov     [rbp+var_18], ecx
0x180001347  mov     [rbp+var_14], edx
0x18000134a  cmp     esi, r11d
0x18000134d  jg      short loc_180001364
0x18000134f  movzx   eax, byte ptr [rdi+r14+1]
0x180001355  movzx   edx, byte ptr [rdi+r14+2]
0x18000135b  mov     ecx, [rbp+rax*4+var_20]
0x18000135f  bt      ecx, edx
0x180001362  jb      short loc_180001369
0x180001364  or      r8d, [rdi+r14+4]
0x180001369  movsxd  rax, r10d
0x18000136c  lea     rdi, ds:18h[rax*8]
0x180001374  movzx   esi, byte ptr [rdi+r14]
0x180001379  cmp     esi, r9d
0x18000137c  jz      short loc_180001393
0x18000137e  mov     eax, esi
0x180001380  xor     ecx, ecx
0x180001382  cpuid
0x180001384  mov     [rbp+var_20], eax
0x180001387  mov     r9d, esi
0x18000138a  mov     [rbp+var_1C], ebx
0x18000138d  mov     [rbp+var_18], ecx
0x180001390  mov     [rbp+var_14], edx
0x180001393  cmp     esi, r11d
0x180001396  jg      short loc_1800013AD
0x180001398  movzx   eax, byte ptr [rdi+r14+1]
0x18000139e  movzx   edx, byte ptr [rdi+r14+2]
0x1800013a4  mov     ecx, [rbp+rax*4+var_20]
0x1800013a8  bt      ecx, edx
0x1800013ab  jb      short loc_1800013B2
0x1800013ad  or      r8d, [rdi+r14+4]
0x1800013b2  movsxd  rax, r10d
0x1800013b5  lea     rdi, ds:20h[rax*8]
0x1800013bd  movzx   esi, byte ptr [rdi+r14]
0x1800013c2  cmp     esi, r9d
0x1800013c5  jz      short loc_1800013DC
0x1800013c7  mov     eax, esi
0x1800013c9  xor     ecx, ecx
0x1800013cb  cpuid
0x1800013cd  mov     [rbp+var_20], eax
0x1800013d0  mov     r9d, esi
0x1800013d3  mov     [rbp+var_1C], ebx
0x1800013d6  mov     [rbp+var_18], ecx
0x1800013d9  mov     [rbp+var_14], edx
0x1800013dc  cmp     esi, r11d
0x1800013df  jg      short loc_1800013F6
0x1800013e1  movzx   eax, byte ptr [rdi+r14+1]
0x1800013e7  movzx   edx, byte ptr [rdi+r14+2]
0x1800013ed  mov     ecx, [rbp+rax*4+var_20]
0x1800013f1  bt      ecx, edx
0x1800013f4  jb      short loc_1800013FB
0x1800013f6  or      r8d, [rdi+r14+4]
0x1800013fb  movsxd  rax, r10d
0x1800013fe  lea     rdi, ds:28h[rax*8]
0x180001406  movzx   esi, byte ptr [rdi+r14]
0x18000140b  cmp     esi, r9d
0x18000140e  jz      short loc_180001425
0x180001410  mov     eax, esi
0x180001412  xor     ecx, ecx
0x180001414  cpuid
0x180001416  mov     [rbp+var_20], eax
0x180001419  mov     r9d, esi
0x18000141c  mov     [rbp+var_1C], ebx
0x18000141f  mov     [rbp+var_18], ecx
0x180001422  mov     [rbp+var_14], edx
0x180001425  cmp     esi, r11d
0x180001428  jg      short loc_18000143F
0x18000142a  movzx   eax, byte ptr [rdi+r14+1]
0x180001430  movzx   edx, byte ptr [rdi+r14+2]
0x180001436  mov     ecx, [rbp+rax*4+var_20]
0x18000143a  bt      ecx, edx
0x18000143d  jb      short loc_180001444
0x18000143f  or      r8d, [rdi+r14+4]
0x180001444  movsxd  rax, r10d
0x180001447  lea     rdi, ds:30h[rax*8]
0x18000144f  movzx   esi, byte ptr [rdi+r14]
0x180001454  cmp     esi, r9d
0x180001457  jz      short loc_18000146E
0x180001459  mov     eax, esi
0x18000145b  xor     ecx, ecx
0x18000145d  cpuid
0x18000145f  mov     [rbp+var_20], eax
0x180001462  mov     r9d, esi
0x180001465  mov     [rbp+var_1C], ebx
0x180001468  mov     [rbp+var_18], ecx
0x18000146b  mov     [rbp+var_14], edx
0x18000146e  cmp     esi, r11d
0x180001471  jg      short loc_180001488
0x180001473  movzx   eax, byte ptr [rdi+r14+1]
0x180001479  movzx   edx, byte ptr [rdi+r14+2]
0x18000147f  mov     ecx, [rbp+rax*4+var_20]
0x180001483  bt      ecx, edx
0x180001486  jb      short loc_18000148D
0x180001488  or      r8d, [rdi+r14+4]
0x18000148d  movsxd  rax, r10d
0x180001490  lea     rdi, ds:38h[rax*8]
0x180001498  movzx   esi, byte ptr [rdi+r14]
0x18000149d  cmp     esi, r9d
0x1800014a0  jz      short loc_1800014B7
0x1800014a2  mov     eax, esi
0x1800014a4  xor     ecx, ecx
0x1800014a6  cpuid
0x1800014a8  mov     [rbp+var_20], eax
0x1800014ab  mov     r9d, esi
0x1800014ae  mov     [rbp+var_1C], ebx
0x1800014b1  mov     [rbp+var_18], ecx
0x1800014b4  mov     [rbp+var_14], edx
0x1800014b7  cmp     esi, r11d
0x1800014ba  jg      short loc_1800014D1
0x1800014bc  movzx   eax, byte ptr [rdi+r14+1]
0x1800014c2  movzx   edx, byte ptr [rdi+r14+2]
0x1800014c8  mov     ecx, [rbp+rax*4+var_20]
0x1800014cc  bt      ecx, edx
0x1800014cf  jb      short loc_1800014D6
0x1800014d1  or      r8d, [rdi+r14+4]
0x1800014d6  movsxd  rax, r10d
0x1800014d9  lea     rdi, ds:40h[rax*8]
0x1800014e1  movzx   esi, byte ptr [rdi+r14]
0x1800014e6  cmp     esi, r9d
0x1800014e9  jz      short loc_180001500
0x1800014eb  mov     eax, esi
0x1800014ed  xor     ecx, ecx
0x1800014ef  cpuid
0x1800014f1  mov     [rbp+var_20], eax
0x1800014f4  mov     r9d, esi
0x1800014f7  mov     [rbp+var_1C], ebx
0x1800014fa  mov     [rbp+var_18], ecx
0x1800014fd  mov     [rbp+var_14], edx
0x180001500  cmp     esi, r11d
0x180001503  jg      short loc_18000151A
0x180001505  movzx   eax, byte ptr [rdi+r14+1]
0x18000150b  movzx   edx, byte ptr [rdi+r14+2]
0x180001511  mov     ecx, [rbp+rax*4+var_20]
0x180001515  bt      ecx, edx
0x180001518  jb      short loc_18000151F
0x18000151a  or      r8d, [rdi+r14+4]
0x18000151f  movsxd  rax, r10d
0x180001522  lea     rdi, ds:48h[rax*8]
0x18000152a  movzx   esi, byte ptr [rdi+r14]
0x18000152f  cmp     esi, r9d
0x180001532  jz      short loc_180001549
0x180001534  mov     eax, esi
0x180001536  xor     ecx, ecx
0x180001538  cpuid
0x18000153a  mov     [rbp+var_20], eax
0x18000153d  mov     r9d, esi
0x180001540  mov     [rbp+var_1C], ebx
0x180001543  mov     [rbp+var_18], ecx
0x180001546  mov     [rbp+var_14], edx
0x180001549  cmp     esi, r11d
0x18000154c  jg      short loc_180001563
0x18000154e  movzx   eax, byte ptr [rdi+r14+1]
0x180001554  movzx   edx, byte ptr [rdi+r14+2]
0x18000155a  mov     ecx, [rbp+rax*4+var_20]
0x18000155e  bt      ecx, edx
0x180001561  jb      short loc_180001568
0x180001563  or      r8d, [rdi+r14+4]
0x180001568  add     r10d, 0Ah
0x18000156c  cmp     r10d, 14h
0x180001570  jb      loc_1800012A0
0x180001576  mov     r14, [rsp+40h+var_10]
0x18000157b  xor     ecx, ecx
0x18000157d  mov     rdi, [rsp+40h+var_8]
0x180001582  mov     eax, 1
0x180001587  mov     rsi, [rsp+40h+arg_10]
0x18000158c  cpuid
0x18000158e  bt      ecx, 1Bh
0x180001592  jnb     short loc_1800015B3
0x180001594  xor     ecx, ecx
0x180001596  xgetbv
0x180001599  shl     rdx, 20h
0x18000159d  or      rdx, rax
0x1800015a0  movzx   eax, dl
0x1800015a3  and     al, 6
0x1800015a5  cmp     al, 6
0x1800015a7  jnz     short loc_1800015B3
0x1800015a9  and     dl, 0E0h
0x1800015ac  cmp     dl, 0E0h
0x1800015af  jnz     short loc_1800015B7
0x1800015b1  jmp     short loc_1800015BC
0x1800015b3  or      r8d, 10h
0x1800015b7  bts     r8d, 0Ch
0x1800015bc  test    r8b, 4
0x1800015c0  jnz     short loc_180001607
0x1800015c2  xor     eax, eax
0x1800015c4  xor     ecx, ecx
0x1800015c6  cpuid
0x1800015c8  cmp     ebx, 68747541h
0x1800015ce  jnz     short loc_180001607
0x1800015d0  cmp     ecx, 444D4163h
0x1800015d6  jnz     short loc_180001607
0x1800015d8  cmp     edx, 69746E65h
0x1800015de  jnz     short loc_180001607
0x1800015e0  xor     ecx, ecx
0x1800015e2  mov     eax, 1
0x1800015e7  cpuid
0x1800015e9  mov     edx, eax
0x1800015eb  sar     edx, 8
0x1800015ee  and     edx, 0Fh
0x1800015f1  cmp     edx, 0Fh
0x1800015f4  jb      short loc_180001603
0x1800015f6  sar     eax, 14h
0x1800015f9  movzx   ecx, al
0x1800015fc  add     ecx, edx
0x1800015fe  cmp     ecx, 15h
0x180001601  jnb     short loc_180001607
0x180001603  or      r8d, 4
0x180001607  mov     eax, 1
0x18000160c  mov     cs:g_SymCryptCpuFeaturesNotPresent, r8d
0x180001613  xor     ecx, ecx
0x180001615  cpuid
0x180001617  mov     cs:g_SymCryptCpuid1, eax
0x18000161d  mov     cs:dword_1800075C4, ebx
0x180001623  mov     cs:dword_1800075C8, ecx
0x180001629  mov     cs:dword_1800075CC, edx
0x18000162f  call    cs:__imp_GetEnabledXStateFeatures
0x180001636  nop     dword ptr [rax+rax+00h]
0x18000163b  mov     rbx, [rsp+40h+arg_0]
0x180001640  mov     ecx, cs:g_SymCryptCpuFeaturesNotPresent
0x180001646  test    al, 4
0x180001648  jnz     short loc_18000164D
0x18000164a  or      ecx, 10h
  ... truncated ...
```
