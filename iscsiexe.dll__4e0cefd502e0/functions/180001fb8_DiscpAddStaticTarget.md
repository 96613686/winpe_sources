# DiscpAddStaticTarget

- ea: `0x180001fb8`
- end: `0x18000246b`
- name: `DiscpAddStaticTarget`
- size: `1203`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, char, char, __int64, _BYTE *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004850`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180001fb8`
- `0x180002474`
- `0x1800025ac`
- `0x180003198`
- `0x18000325c`
- `0x180005d2c`
- `0x1800064f8`
- `0x1800076dc`
- `0x18000a488`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180002334`
- `ISCSIUM!DiscpAllocMemory` at `0x18000239e`
- `ISCSIUM!DiscpAllocMemory` at `0x180002334`
- `ISCSIUM!DiscpAllocMemory` at `0x18000239e`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800023eb`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800023eb`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800022c3`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800022c3`
- `ISCSIUM!DiscpFreeMemory` at `0x1800023f6`
- `ISCSIUM!DiscpFreeMemory` at `0x180002406`
- `ISCSIUM!DiscpFreeMemory` at `0x180002439`
- `ISCSIUM!DiscpFreeMemory` at `0x1800023f6`
- `ISCSIUM!DiscpFreeMemory` at `0x180002406`
- `ISCSIUM!DiscpFreeMemory` at `0x180002439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000241e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000241e`

## string_xrefs

- `0x180002095`: `Manually Configured:`

## pseudocode

```c
__int64 __fastcall DiscpAddStaticTarget(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        _BYTE *a6,
        unsigned int a7,
        int *a8)
{
  __int64 v8; // r14
  int *v9; // rdi
  _BYTE *v10; // rbx
  int *v12; // rsi
  unsigned int v14; // r15d
  unsigned int TargetByDiscoveryMechanism; // ebx
  _QWORD *v16; // rax
  char *v17; // rcx
  __int128 *v18; // rax
  __int64 v19; // rdx
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 *v28; // rax
  char *v29; // rcx
  __int64 v30; // rdx
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  int *v39; // rax
  __int64 v40; // rdx
  _BYTE *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // r14
  __int64 v44; // rax
  unsigned int v45; // ebx
  wchar_t *v46; // rax
  wchar_t *v47; // rsi
  int v49; // [rsp+30h] [rbp-D0h]
  unsigned int v52; // [rsp+64h] [rbp-9Ch] BYREF
  int v53; // [rsp+68h] [rbp-98h] BYREF
  int v54; // [rsp+6Ch] [rbp-94h] BYREF
  int v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  int *v57; // [rsp+78h] [rbp-88h] BYREF
  int v58; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v59; // [rsp+88h] [rbp-78h]
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h]
  _BYTE v63[64]; // [rsp+B0h] [rbp-50h] BYREF
  int v64; // [rsp+F0h] [rbp-10h] BYREF
  char v65; // [rsp+F4h] [rbp-Ch] BYREF
  int v66; // [rsp+500h] [rbp+400h] BYREF
  char v67; // [rsp+504h] [rbp+404h]
  char v68; // [rsp+508h] [rbp+408h] BYREF

  LODWORD(v8) = a5;
  v9 = 0;
  v10 = a6;
  v12 = a8;
  v62 = a5;
  v59 = a6;
  hKey = 0;
  v56 = 0;
  v55 = 0;
  v58 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v61 = 0;
  memset_0(&v66, 0, 0x40Cu);
  memset_0(&v64, 0, 0x408u);
  memset_0(v63, 0, sizeof(v63));
  v14 = a7;
  v57 = 0;
  if ( (a7 & 4) == 0 )
  {
    if ( !DiscpRestrictNewStaticTargets )
      goto LABEL_14;
    return (unsigned int)-268500891;
  }
  if ( DiscpRestrictConfigureTargets )
    return (unsigned int)-268500891;
  TargetByDiscoveryMechanism = DiscpFindTargetByDiscoveryMechanism(pszSrc, L"Manually Configured:", &v57);
  if ( TargetByDiscoveryMechanism )
    return TargetByDiscoveryMechanism;
  v9 = v57;
  if ( !a2 )
    a2 = *((_QWORD *)v57 + 7);
  if ( !a5 )
  {
    v8 = *((_QWORD *)v57 + 11);
    v62 = v8;
  }
  DiscpMergeLoginOptions((unsigned int)v63, (_DWORD)v59, 0, *((_QWORD *)v57 + 12), 0);
  v10 = v63;
  v59 = v63;
  if ( !a8 )
  {
    v16 = (_QWORD *)*((_QWORD *)v9 + 10);
    if ( v16 )
    {
      v17 = &v65;
      v18 = (__int128 *)(*v16 + 8LL);
      v64 = 1;
      v19 = 8;
      do
      {
        v20 = *v18;
        v21 = v18[1];
        v18 += 8;
        *(_OWORD *)v17 = v20;
        v22 = *(v18 - 6);
        *((_OWORD *)v17 + 1) = v21;
        v23 = *(v18 - 5);
        *((_OWORD *)v17 + 2) = v22;
        v24 = *(v18 - 4);
        *((_OWORD *)v17 + 3) = v23;
        v25 = *(v18 - 3);
        *((_OWORD *)v17 + 4) = v24;
        v26 = *(v18 - 2);
        *((_OWORD *)v17 + 5) = v25;
        v27 = *(v18 - 1);
        *((_OWORD *)v17 + 6) = v26;
        *((_OWORD *)v17 + 7) = v27;
        v17 += 128;
        --v19;
      }
      while ( v19 );
      v12 = &v64;
      *(_WORD *)v17 = *(_WORD *)v18;
    }
  }
  v14 = (v9[26] | a7) & 0xFFFFFFFB;
LABEL_14:
  if ( !a4 )
  {
    TargetByDiscoveryMechanism = 0;
    goto LABEL_28;
  }
  if ( v12 )
  {
    if ( *v12 != 1 )
    {
      TargetByDiscoveryMechanism = 87;
      goto LABEL_41;
    }
    v67 = 0;
    v28 = (__int128 *)(v12 + 1);
    v29 = &v68;
    v66 = 1;
    v30 = 8;
    do
    {
      v31 = *v28;
      v32 = v28[1];
      v28 += 8;
      *(_OWORD *)v29 = v31;
      v33 = *(v28 - 6);
      *((_OWORD *)v29 + 1) = v32;
      v34 = *(v28 - 5);
      *((_OWORD *)v29 + 2) = v33;
      v35 = *(v28 - 4);
      *((_OWORD *)v29 + 3) = v34;
      v36 = *(v28 - 3);
      *((_OWORD *)v29 + 4) = v35;
      v37 = *(v28 - 2);
      *((_OWORD *)v29 + 5) = v36;
      v38 = *(v28 - 1);
      *((_OWORD *)v29 + 6) = v37;
      *((_OWORD *)v29 + 7) = v38;
      v29 += 128;
      --v30;
    }
    while ( v30 );
    *(_WORD *)v29 = *(_WORD *)v28;
    v39 = &v66;
  }
  else
  {
    v39 = 0;
  }
  v57 = v39;
  TargetByDiscoveryMechanism = DiscpCreateTarget(
                                 (_DWORD)pszSrc,
                                 a2,
                                 0,
                                 v8,
                                 (__int64)v10,
                                 v14,
                                 v12 != 0,
                                 (__int64)&v57,
                                 2,
                                 2,
                                 (__int64)&v61);
  if ( !TargetByDiscoveryMechanism )
  {
    LOBYTE(v40) = 1;
    TargetByDiscoveryMechanism = DiscpInsertTarget(v61, v40);
    if ( !TargetByDiscoveryMechanism )
    {
LABEL_28:
      if ( a3 )
      {
        TargetByDiscoveryMechanism = DiscpOpenRegistryKey(
                                       &hKey,
                                       L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Static Targets",
                                       131103);
        if ( !TargetByDiscoveryMechanism )
        {
          v41 = v59;
          if ( (int)DiscpComputeStaticTargetSize(
                      (_DWORD)pszSrc,
                      a2,
                      v8,
                      (_DWORD)v59,
                      (__int64)v12,
                      (__int64)&v56,
                      (__int64)&v55,
                      (__int64)&v54,
                      (__int64)&v53,
                      (__int64)&v58,
                      (__int64)&v52) < 0 )
          {
            TargetByDiscoveryMechanism = 87;
          }
          else
          {
            v42 = DiscpAllocMemory(v52);
            v43 = v42;
            if ( v42 )
            {
              DiscpBuildStaticTarget(v42, pszSrc, a2, v62, v41, v14, v12, v56, v55, v54, v53);
              v44 = -1;
              do
                ++v44;
              while ( pszSrc[v44] );
              v45 = v44 + 2;
              v46 = (wchar_t *)DiscpAllocMemory((unsigned int)(2 * (v44 + 2)));
              v47 = v46;
              if ( v46 )
              {
                StringCchCopyW(v46, v45, L"*");
                StringCchCatW(v47, v45, pszSrc);
                LOBYTE(v49) = 1;
                TargetByDiscoveryMechanism = DiscpSetRegistryValue(hKey, 0, v47, 3, v43, v52, v49);
                DiscpFreeMemory(v47);
              }
              else
              {
                TargetByDiscoveryMechanism = 8;
              }
              DiscpFreeMemory(v43);
            }
            else
            {
              TargetByDiscoveryMechanism = 8;
            }
          }
          RegCloseKey(hKey);
        }
      }
    }
  }
LABEL_41:
  if ( v9 && _InterlockedExchangeAdd(v9 + 8, 0xFFFFFFFF) == 1 )
    DiscpFreeMemory(v9);
  return TargetByDiscoveryMechanism;
}

```

## disassembly

```asm
0x180001fb8  mov     [rsp-8+arg_10], rbx
0x180001fbd  push    rbp
0x180001fbe  push    rsi
0x180001fbf  push    rdi
0x180001fc0  push    r12
0x180001fc2  push    r13
0x180001fc4  push    r14
0x180001fc6  push    r15
0x180001fc8  lea     rbp, [rsp-820h]
0x180001fd0  sub     rsp, 920h
0x180001fd7  mov     rax, cs:__security_cookie
0x180001fde  xor     rax, rsp
0x180001fe1  mov     [rbp+850h+var_40], rax
0x180001fe8  mov     r14, [rbp+850h+arg_20]
0x180001fef  xor     edi, edi
0x180001ff1  mov     rbx, [rbp+850h+arg_28]
0x180001ff8  mov     r13, rdx
0x180001ffb  mov     rsi, [rbp+850h+arg_38]
0x180002002  mov     r12, rcx
0x180002005  mov     [rsp+950h+var_8EF], r8b
0x18000200a  lea     rcx, [rbp+850h+var_450]; void *
0x180002011  xor     edx, edx; Val
0x180002013  mov     [rbp+850h+var_8B0], r14
0x180002017  mov     r8d, 40Ch; Size
0x18000201d  mov     [rbp+850h+var_8C8], rbx
0x180002021  mov     [rbp+850h+hKey], rdi
0x180002025  mov     [rsp+950h+var_8DC], edi
0x180002029  mov     [rsp+950h+var_8E0], edi
0x18000202d  mov     [rbp+850h+var_8D0], edi
0x180002030  mov     [rsp+950h+var_8EC], edi
0x180002034  mov     [rsp+950h+var_8E8], edi
0x180002038  mov     [rsp+950h+var_8E4], edi
0x18000203c  mov     [rbp+850h+var_8B8], rdi
0x180002040  mov     [rsp+950h+var_8F0], r9b
0x180002045  call    memset_0
0x18000204a  xor     edx, edx; Val
0x18000204c  lea     rcx, [rbp+850h+var_860]; void *
0x180002050  mov     r8d, 408h; Size
0x180002056  call    memset_0
0x18000205b  xor     edx, edx; Val
0x18000205d  lea     r8d, [rdi+40h]; Size
0x180002061  lea     rcx, [rbp+850h+var_8A0]; void *
0x180002065  call    memset_0
0x18000206a  mov     r15d, [rbp+850h+arg_30]
0x180002071  mov     [rsp+950h+var_8D8], rdi
0x180002076  test    r15b, 4
0x18000207a  jz      loc_180002212
0x180002080  cmp     cs:DiscpRestrictConfigureTargets, dil
0x180002087  jnz     loc_180002220
0x18000208d  lea     r8, [rsp+950h+var_8D8]
0x180002092  mov     rcx, r12
0x180002095  lea     rdx, aManuallyConfig; "Manually Configured:"
0x18000209c  call    DiscpFindTargetByDiscoveryMechanism
0x1800020a1  mov     ebx, eax
0x1800020a3  xor     eax, eax
0x1800020a5  test    ebx, ebx
0x1800020a7  jnz     loc_18000243F
0x1800020ad  mov     rdi, [rsp+950h+var_8D8]
0x1800020b2  test    r13, r13
0x1800020b5  jnz     short loc_1800020BB
0x1800020b7  mov     r13, [rdi+38h]
0x1800020bb  test    r14, r14
0x1800020be  jnz     short loc_1800020C8
0x1800020c0  mov     r14, [rdi+58h]
0x1800020c4  mov     [rbp+850h+var_8B0], r14
0x1800020c8  mov     r9, [rdi+60h]
0x1800020cc  lea     rcx, [rbp+850h+var_8A0]
0x1800020d0  mov     rdx, [rbp+850h+var_8C8]
0x1800020d4  xor     r8d, r8d
0x1800020d7  mov     byte ptr [rsp+950h+var_930], al
0x1800020db  call    DiscpMergeLoginOptions
0x1800020e0  xor     ecx, ecx
0x1800020e2  lea     rbx, [rbp+850h+var_8A0]
0x1800020e6  mov     [rbp+850h+var_8C8], rbx
0x1800020ea  test    rsi, rsi
0x1800020ed  jnz     short loc_18000216B
0x1800020ef  mov     rax, [rdi+50h]
0x1800020f3  test    rax, rax
0x1800020f6  jz      short loc_18000216B
0x1800020f8  mov     rax, [rax]
0x1800020fb  lea     rcx, [rbp+850h+var_85C]
0x1800020ff  add     rax, 8
0x180002103  mov     [rbp+850h+var_860], 1
0x18000210a  lea     edx, [rsi+8]
0x18000210d  movups  xmm0, xmmword ptr [rax]
0x180002110  movups  xmm1, xmmword ptr [rax+10h]
0x180002114  lea     rax, [rax+80h]
0x18000211b  movups  xmmword ptr [rcx], xmm0
0x18000211e  movups  xmm0, xmmword ptr [rax-60h]
0x180002122  movups  xmmword ptr [rcx+10h], xmm1
0x180002126  movups  xmm1, xmmword ptr [rax-50h]
0x18000212a  movups  xmmword ptr [rcx+20h], xmm0
0x18000212e  movups  xmm0, xmmword ptr [rax-40h]
0x180002132  movups  xmmword ptr [rcx+30h], xmm1
0x180002136  movups  xmm1, xmmword ptr [rax-30h]
0x18000213a  movups  xmmword ptr [rcx+40h], xmm0
0x18000213e  movups  xmm0, xmmword ptr [rax-20h]
0x180002142  movups  xmmword ptr [rcx+50h], xmm1
0x180002146  movups  xmm1, xmmword ptr [rax-10h]
0x18000214a  movups  xmmword ptr [rcx+60h], xmm0
0x18000214e  movups  xmmword ptr [rcx+70h], xmm1
0x180002152  lea     rcx, [rcx+80h]
0x180002159  sub     rdx, 1
0x18000215d  jnz     short loc_18000210D
0x18000215f  movzx   eax, word ptr [rax]
0x180002162  lea     rsi, [rbp+850h+var_860]
0x180002166  mov     [rcx], ax
0x180002169  xor     ecx, ecx
0x18000216b  or      r15d, [rdi+68h]
0x18000216f  and     r15d, 0FFFFFFFBh
0x180002173  cmp     [rsp+950h+var_8F0], cl
0x180002177  jz      loc_1800022A6
0x18000217d  test    rsi, rsi
0x180002180  jz      loc_180002234
0x180002186  cmp     dword ptr [rsi], 1
0x180002189  jnz     loc_18000222A
0x18000218f  mov     [rbp+850h+var_44C], cl
0x180002195  lea     rax, [rsi+4]
0x180002199  lea     rcx, [rbp+850h+var_448]
0x1800021a0  mov     [rbp+850h+var_450], 1
0x1800021aa  mov     edx, 8
0x1800021af  movups  xmm0, xmmword ptr [rax]
0x1800021b2  movups  xmm1, xmmword ptr [rax+10h]
0x1800021b6  lea     rax, [rax+80h]
0x1800021bd  movups  xmmword ptr [rcx], xmm0
0x1800021c0  movups  xmm0, xmmword ptr [rax-60h]
0x1800021c4  movups  xmmword ptr [rcx+10h], xmm1
0x1800021c8  movups  xmm1, xmmword ptr [rax-50h]
0x1800021cc  movups  xmmword ptr [rcx+20h], xmm0
0x1800021d0  movups  xmm0, xmmword ptr [rax-40h]
0x1800021d4  movups  xmmword ptr [rcx+30h], xmm1
0x1800021d8  movups  xmm1, xmmword ptr [rax-30h]
0x1800021dc  movups  xmmword ptr [rcx+40h], xmm0
0x1800021e0  movups  xmm0, xmmword ptr [rax-20h]
0x1800021e4  movups  xmmword ptr [rcx+50h], xmm1
0x1800021e8  movups  xmm1, xmmword ptr [rax-10h]
0x1800021ec  movups  xmmword ptr [rcx+60h], xmm0
0x1800021f0  movups  xmmword ptr [rcx+70h], xmm1
0x1800021f4  lea     rcx, [rcx+80h]
0x1800021fb  sub     rdx, 1
0x1800021ff  jnz     short loc_1800021AF
0x180002201  movzx   eax, word ptr [rax]
0x180002204  mov     [rcx], ax
0x180002207  lea     rax, [rbp+850h+var_450]
0x18000220e  xor     ecx, ecx
0x180002210  jmp     short loc_180002237
0x180002212  xor     ecx, ecx
0x180002214  cmp     cs:DiscpRestrictNewStaticTargets, cl
0x18000221a  jz      loc_180002173
0x180002220  mov     ebx, 0EFFF0065h
0x180002225  jmp     loc_18000243F
0x18000222a  mov     ebx, 57h ; 'W'
0x18000222f  jmp     loc_180002424
0x180002234  mov     rax, rcx
0x180002237  mov     [rsp+950h+var_8D8], rax
0x18000223c  test    rsi, rsi
0x18000223f  mov     eax, ecx
0x180002241  mov     r9, r14
0x180002244  lea     rcx, [rbp+850h+var_8B8]
0x180002248  setnz   al
0x18000224b  mov     [rsp+950h+var_900], rcx
0x180002250  xor     r8d, r8d
0x180002253  mov     ecx, 2
0x180002258  mov     rdx, r13
0x18000225b  mov     dword ptr [rsp+950h+var_908], ecx
0x18000225f  mov     dword ptr [rsp+950h+var_910], ecx
0x180002263  lea     rcx, [rsp+950h+var_8D8]
0x180002268  mov     [rsp+950h+var_918], rcx
0x18000226d  mov     rcx, r12
0x180002270  mov     dword ptr [rsp+950h+var_920], eax
0x180002274  mov     dword ptr [rsp+950h+var_928], r15d
0x180002279  mov     [rsp+950h+var_930], rbx
0x18000227e  call    DiscpCreateTarget
0x180002283  mov     ebx, eax
0x180002285  test    eax, eax
0x180002287  jnz     loc_180002424
0x18000228d  mov     rcx, [rbp+850h+var_8B8]
0x180002291  mov     dl, 1
0x180002293  call    DiscpInsertTarget
0x180002298  xor     ecx, ecx
0x18000229a  mov     ebx, eax
0x18000229c  test    eax, eax
0x18000229e  jnz     loc_180002424
0x1800022a4  jmp     short loc_1800022A8
0x1800022a6  mov     ebx, ecx
0x1800022a8  cmp     [rsp+950h+var_8EF], cl
0x1800022ac  jz      loc_180002424
0x1800022b2  mov     r8d, 2001Fh
0x1800022b8  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800022bf  lea     rcx, [rbp+850h+hKey]
0x1800022c3  call    cs:__imp_DiscpOpenRegistryKey
0x1800022c9  mov     ebx, eax
0x1800022cb  test    eax, eax
0x1800022cd  jnz     loc_180002424
0x1800022d3  mov     rbx, [rbp+850h+var_8C8]
0x1800022d7  lea     rax, [rsp+950h+var_8EC]
0x1800022dc  mov     [rsp+950h+var_900], rax
0x1800022e1  mov     r9, rbx
0x1800022e4  lea     rax, [rbp+850h+var_8D0]
0x1800022e8  mov     r8, r14
0x1800022eb  mov     [rsp+950h+var_908], rax
0x1800022f0  mov     rdx, r13
0x1800022f3  lea     rax, [rsp+950h+var_8E8]
0x1800022f8  mov     rcx, r12
0x1800022fb  mov     [rsp+950h+var_910], rax
0x180002300  lea     rax, [rsp+950h+var_8E4]
0x180002305  mov     [rsp+950h+var_918], rax
0x18000230a  lea     rax, [rsp+950h+var_8E0]
0x18000230f  mov     [rsp+950h+var_920], rax
0x180002314  lea     rax, [rsp+950h+var_8DC]
0x180002319  mov     [rsp+950h+var_928], rax
0x18000231e  mov     [rsp+950h+var_930], rsi
0x180002323  call    DiscpComputeStaticTargetSize
0x180002328  test    eax, eax
0x18000232a  js      loc_180002415
0x180002330  mov     ecx, [rsp+950h+var_8EC]
0x180002334  call    cs:__imp_DiscpAllocMemory
0x18000233a  mov     r14, rax
0x18000233d  test    rax, rax
0x180002340  jz      loc_18000240E
0x180002346  mov     ecx, [rsp+950h+var_8E8]
0x18000234a  mov     r8, r13
0x18000234d  mov     r9, [rbp+850h+var_8B0]
0x180002351  mov     rdx, r12
0x180002354  mov     dword ptr [rsp+950h+var_900], ecx
0x180002358  mov     ecx, [rsp+950h+var_8E4]
0x18000235c  mov     dword ptr [rsp+950h+var_908], ecx
0x180002360  mov     ecx, [rsp+950h+var_8E0]
0x180002364  mov     dword ptr [rsp+950h+var_910], ecx
0x180002368  mov     ecx, [rsp+950h+var_8DC]
0x18000236c  mov     dword ptr [rsp+950h+var_918], ecx
0x180002370  mov     rcx, rax
0x180002373  mov     [rsp+950h+var_920], rsi
0x180002378  mov     dword ptr [rsp+950h+var_928], r15d
0x18000237d  mov     [rsp+950h+var_930], rbx
0x180002382  call    DiscpBuildStaticTarget
0x180002387  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000238b  xor     r15d, r15d
0x18000238e  inc     rax
0x180002391  cmp     [r12+rax*2], r15w
0x180002396  jnz     short loc_18000238E
0x180002398  lea     ebx, [rax+2]
0x18000239b  lea     ecx, [rbx+rbx]
0x18000239e  call    cs:__imp_DiscpAllocMemory
0x1800023a4  mov     rsi, rax
0x1800023a7  test    rax, rax
0x1800023aa  jz      short loc_1800023FE
0x1800023ac  lea     r8, pszSrc; "*"
0x1800023b3  mov     edx, ebx; cchDest
0x1800023b5  mov     rcx, rax; pszDest
0x1800023b8  call    StringCchCopyW
0x1800023bd  mov     r8, r12; pszSrc
0x1800023c0  mov     edx, ebx; cchDest
0x1800023c2  mov     rcx, rsi; pszDest
0x1800023c5  call    StringCchCatW
0x1800023ca  mov     ecx, [rsp+950h+var_8EC]
0x1800023ce  mov     r9d, 3
0x1800023d4  mov     byte ptr [rsp+950h+var_920], 1
0x1800023d9  mov     r8, rsi
0x1800023dc  mov     dword ptr [rsp+950h+var_928], ecx
0x1800023e0  xor     edx, edx
0x1800023e2  mov     rcx, [rbp+850h+hKey]
0x1800023e6  mov     [rsp+950h+var_930], r14
0x1800023eb  call    cs:__imp_DiscpSetRegistryValue
0x1800023f1  mov     rcx, rsi
0x1800023f4  mov     ebx, eax
0x1800023f6  call    cs:__imp_DiscpFreeMemory
0x1800023fc  jmp     short loc_180002403
0x1800023fe  mov     ebx, 8
0x180002403  mov     rcx, r14
0x180002406  call    cs:__imp_DiscpFreeMemory
0x18000240c  jmp     short loc_18000241A
0x18000240e  mov     ebx, 8
0x180002413  jmp     short loc_18000241A
0x180002415  mov     ebx, 57h ; 'W'
0x18000241a  mov     rcx, [rbp+850h+hKey]; hKey
0x18000241e  call    cs:__imp_RegCloseKey
0x180002424  test    rdi, rdi
0x180002427  jz      short loc_18000243F
0x180002429  or      eax, 0FFFFFFFFh
0x18000242c  lock xadd [rdi+20h], eax
0x180002431  cmp     eax, 1
0x180002434  jnz     short loc_18000243F
0x180002436  mov     rcx, rdi
0x180002439  call    cs:__imp_DiscpFreeMemory
0x18000243f  mov     eax, ebx
0x180002441  mov     rcx, [rbp+850h+var_40]
0x180002448  xor     rcx, rsp; StackCookie
0x18000244b  call    __security_check_cookie
0x180002450  mov     rbx, [rsp+950h+arg_10]
0x180002458  add     rsp, 920h
0x18000245f  pop     r15
0x180002461  pop     r14
0x180002463  pop     r13
0x180002465  pop     r12
0x180002467  pop     rdi
0x180002468  pop     rsi
0x180002469  pop     rbp
0x18000246a  retn
```
