# OneXSetEapUserData

- ea: `0x180017540`
- end: `0x18001782e`
- name: `OneXSetEapUserData`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ce44`

## callees

- `0x180014870`
- `0x180014e20`
- `0x180017540`
- `0x18001f1fc`
- `0x18002f705`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017782`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180017778`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180017778`
- `MobileNetworking!FreeMemory` at `0x1800177dd`
- `MobileNetworking!FreeMemory` at `0x180017820`
- `MobileNetworking!FreeMemory` at `0x1800177dd`
- `MobileNetworking!FreeMemory` at `0x180017820`

## pseudocode

```c
__int64 __fastcall OneXSetEapUserData(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        unsigned int a4,
        void *Src,
        _OWORD *a6,
        unsigned int *a7)
{
  unsigned int *v8; // rsi
  __int64 v9; // rdi
  size_t v11; // r14
  DWORD v12; // eax
  DWORD AlignedSize; // ebp
  DWORD v14; // r13d
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // ecx
  _OWORD *v18; // r12
  char *v19; // rdx
  int v20; // r9d
  __int64 v21; // r10
  unsigned int v22; // eax
  char *v23; // r10
  __int128 v24; // xmm0
  unsigned int *v25; // rdx
  int v26; // r9d
  __int64 v27; // r10
  __int64 v28; // rax
  void *v29; // rdx
  __int64 v30; // r10
  __int64 v31; // rcx
  unsigned int *v32; // rdx
  void *v33; // r11
  __int64 v35; // [rsp+60h] [rbp+8h] BYREF
  __int64 v36; // [rsp+68h] [rbp+10h] BYREF

  v8 = a7;
  v9 = 0;
  v11 = a4;
  v35 = 0;
  v36 = 0;
  if ( !a7 )
  {
    AlignedSize = 87;
    goto LABEL_38;
  }
  if ( a2 )
  {
    v9 = a2;
LABEL_6:
    v14 = 0;
    v35 = 0;
    v15 = 64;
    if ( Src && (_DWORD)v11 )
    {
      if ( (unsigned int)v11 >= 0xFFFFFFEC )
        goto LABEL_36;
      if ( (int)v11 + 27 < (unsigned int)(v11 + 20) )
      {
        AlignedSize = 534;
        goto LABEL_38;
      }
      v16 = (v11 + 27) & 0xFFFFFFF8;
      v17 = v16 + 64;
      if ( v16 >= 0xFFFFFFC0 )
      {
        AlignedSize = 534;
        goto LABEL_38;
      }
      v14 = *(_DWORD *)(v9 + 20);
      if ( v14 + 7 < v14 )
      {
        AlignedSize = 534;
        goto LABEL_38;
      }
      v15 = v17 + ((v14 + 7) & 0xFFFFFFF8);
      if ( v15 < v17 )
        goto LABEL_36;
      v35 = v9 + *(unsigned int *)(v9 + 24);
    }
    v18 = a6;
    if ( !a6 )
    {
      *v8 = v15;
      AlignedSize = 234;
      goto LABEL_38;
    }
    if ( *v8 < v15 )
    {
      *v8 = v15;
      AlignedSize = 122;
      goto LABEL_38;
    }
    v19 = (char *)a6 + 12;
    *a6 = *(_OWORD *)v9;
    v18[1] = *(_OWORD *)(v9 + 16);
    v18[2] = *(_OWORD *)(v9 + 32);
    v18[3] = *(_OWORD *)(v9 + 48);
    *((_DWORD *)v18 + 1) = v15;
    AlignedSize = GetAlignedSize(32, v19);
    if ( AlignedSize )
      goto LABEL_38;
    v22 = *((_DWORD *)v18 + 3);
    if ( v22 + v20 >= v22 )
    {
      v23 = (char *)v18 + v21;
      *((_DWORD *)v18 + 3) = v22 + v20;
      if ( Src && (_DWORD)v11 )
      {
        v24 = *a3;
        *(_DWORD *)v23 |= 1u;
        *(_OWORD *)(v23 + 4) = v24;
        AlignedSize = GetAlignedSize(32, v23 + 28);
        if ( AlignedSize )
          goto LABEL_38;
        v28 = *v25;
        v29 = Src;
        *(_DWORD *)(v27 + 24) = v26;
        *(_DWORD *)(v28 + v27 + 16) = v11;
        *(_OWORD *)(v28 + v27) = v24;
        memcpy_0((void *)(v28 + v27 + 20), v29, v11);
      }
      else
      {
        *(_DWORD *)v23 &= ~1u;
        AlignedSize = GetAlignedSize(32, v23 + 28);
        if ( AlignedSize )
          goto LABEL_38;
        *(_DWORD *)(v30 + 24) = 0;
        *(_OWORD *)(v30 + 4) = 0;
      }
      v31 = *((unsigned int *)v18 + 3);
      *((_DWORD *)v18 + 6) = *((_DWORD *)v18 + 4);
      AlignedSize = IncrementDwordByAlignedSize(v31);
      if ( !AlignedSize )
      {
        if ( v14 )
        {
          if ( CopySid(v14, (char *)v18 + *v32, v33) || (AlignedSize = GetLastError()) == 0 )
          {
            *((_DWORD *)v18 + 2) |= 1u;
            *((_DWORD *)v18 + 5) = v14;
          }
        }
        else
        {
          *((_DWORD *)v18 + 2) &= ~1u;
          *((_DWORD *)v18 + 5) = 0;
        }
      }
LABEL_38:
      if ( a2 )
        goto LABEL_40;
      goto LABEL_39;
    }
    *((_DWORD *)v18 + 3) = -1;
LABEL_36:
    AlignedSize = 534;
    goto LABEL_38;
  }
  v12 = OneXCreateDefaultUserProfile(&v35);
  v9 = v35;
  AlignedSize = v12;
  if ( !v12 )
    goto LABEL_6;
LABEL_39:
  v35 = v9;
  FreeMemory(&v35, "OneXFreeUserProfile", 84);
LABEL_40:
  if ( v36 )
    FreeMemory(&v36, "OneXSetEapUserData", 766);
  return AlignedSize;
}

```

## disassembly

```asm
0x180017540  mov     rax, rsp
0x180017543  mov     [rax+8], rcx
0x180017547  push    rbp
0x180017548  sub     rsp, 50h
0x18001754c  mov     [rax+18h], rbx
0x180017550  mov     rbx, rdx
0x180017553  mov     [rax-10h], rsi
0x180017557  mov     rsi, [rsp+58h+arg_30]
0x18001755f  mov     [rax-18h], rdi
0x180017563  xor     edi, edi
0x180017565  mov     [rax-20h], r12
0x180017569  mov     [rax-28h], r13
0x18001756d  mov     [rax-30h], r14
0x180017571  mov     [rax-38h], r15
0x180017575  mov     r15, r8
0x180017578  mov     r14d, r9d
0x18001757b  mov     [rax+8], rdi
0x18001757f  mov     [rax+10h], rdi
0x180017583  test    rsi, rsi
0x180017586  jz      loc_1800177BC
0x18001758c  test    rdx, rdx
0x18001758f  jnz     short loc_1800175AB
0x180017591  lea     rcx, [rax+8]
0x180017595  call    OneXCreateDefaultUserProfile
0x18001759a  mov     rdi, [rsp+58h+arg_0]
0x18001759f  mov     ebp, eax
0x1800175a1  test    eax, eax
0x1800175a3  jnz     loc_1800177C6
0x1800175a9  jmp     short loc_1800175AE
0x1800175ab  mov     rdi, rbx
0x1800175ae  xor     r11d, r11d
0x1800175b1  xor     r9d, r9d
0x1800175b4  xor     r13d, r13d
0x1800175b7  mov     [rsp+58h+arg_0], r11
0x1800175bc  mov     eax, 40h ; '@'
0x1800175c1  cmp     [rsp+58h+Src], r9
0x1800175c9  jz      short loc_180017636
0x1800175cb  test    r14d, r14d
0x1800175ce  jz      short loc_180017636
0x1800175d0  lea     r9d, [r14+14h]
0x1800175d4  cmp     r9d, 14h
0x1800175d8  jb      loc_1800177B5
0x1800175de  lea     eax, [r9+7]
0x1800175e2  cmp     eax, r9d
0x1800175e5  jnb     short loc_1800175F1
0x1800175e7  mov     ebp, 216h
0x1800175ec  jmp     loc_1800177C1
0x1800175f1  and     eax, 0FFFFFFF8h
0x1800175f4  lea     ecx, [rax+40h]
0x1800175f7  cmp     ecx, 40h ; '@'
0x1800175fa  jnb     short loc_180017606
0x1800175fc  mov     ebp, 216h
0x180017601  jmp     loc_1800177C1
0x180017606  mov     r13d, [rdi+14h]
0x18001760a  lea     eax, [r13+7]
0x18001760e  cmp     eax, r13d
0x180017611  jnb     short loc_18001761D
0x180017613  mov     ebp, 216h
0x180017618  jmp     loc_1800177C1
0x18001761d  and     eax, 0FFFFFFF8h
0x180017620  add     eax, ecx
0x180017622  cmp     eax, ecx
0x180017624  jb      loc_1800177B5
0x18001762a  mov     r11d, [rdi+18h]
0x18001762e  add     r11, rdi
0x180017631  mov     [rsp+58h+arg_0], r11
0x180017636  mov     r12, [rsp+58h+arg_28]
0x18001763e  test    r12, r12
0x180017641  jnz     short loc_18001764F
0x180017643  mov     [rsi], eax
0x180017645  mov     ebp, 0EAh
0x18001764a  jmp     loc_1800177C1
0x18001764f  cmp     [rsi], eax
0x180017651  jnb     short loc_18001765F
0x180017653  mov     [rsi], eax
0x180017655  mov     ebp, 7Ah ; 'z'
0x18001765a  jmp     loc_1800177C1
0x18001765f  movups  xmm0, xmmword ptr [rdi]
0x180017662  lea     rdx, [r12+0Ch]
0x180017667  mov     ecx, 20h ; ' '
0x18001766c  movups  xmmword ptr [r12], xmm0
0x180017671  movups  xmm1, xmmword ptr [rdi+10h]
0x180017675  movups  xmmword ptr [r12+10h], xmm1
0x18001767b  movups  xmm0, xmmword ptr [rdi+20h]
0x18001767f  movups  xmmword ptr [r12+20h], xmm0
0x180017685  movups  xmm1, xmmword ptr [rdi+30h]
0x180017689  movups  xmmword ptr [r12+30h], xmm1
0x18001768f  mov     r10d, [r12+10h]
0x180017694  mov     [r12+4], eax
0x180017699  call    GetAlignedSize
0x18001769e  mov     ebp, eax
0x1800176a0  test    eax, eax
0x1800176a2  jnz     loc_1800177C1
0x1800176a8  mov     eax, [r12+0Ch]
0x1800176ad  lea     ecx, [rax+r9]
0x1800176b1  cmp     ecx, eax
0x1800176b3  jb      loc_1800177AC
0x1800176b9  add     r10, r12
0x1800176bc  mov     [r12+0Ch], ecx
0x1800176c1  cmp     [rsp+58h+Src], 0
0x1800176ca  jz      short loc_180017724
0x1800176cc  test    r14d, r14d
0x1800176cf  jz      short loc_180017724
0x1800176d1  movaps  xmm0, xmmword ptr [r15]
0x1800176d5  lea     rdx, [r10+1Ch]
0x1800176d9  or      dword ptr [r10], 1
0x1800176dd  mov     ecx, 20h ; ' '
0x1800176e2  movups  xmmword ptr [r10+4], xmm0
0x1800176e7  call    GetAlignedSize
0x1800176ec  mov     ebp, eax
0x1800176ee  test    eax, eax
0x1800176f0  jnz     loc_1800177C1
0x1800176f6  mov     eax, [rdx]
0x1800176f8  lea     rcx, [r10+14h]
0x1800176fc  mov     rdx, [rsp+58h+Src]; Src
0x180017704  mov     r8, r14; Size
0x180017707  mov     [r10+18h], r9d
0x18001770b  add     rcx, rax; void *
0x18001770e  mov     [rax+r10+10h], r14d
0x180017713  movups  xmmword ptr [rax+r10], xmm0
0x180017718  call    memcpy_0
0x18001771d  mov     r11, [rsp+58h+arg_0]
0x180017722  jmp     short loc_18001774C
0x180017724  and     dword ptr [r10], 0FFFFFFFEh
0x180017728  lea     rdx, [r10+1Ch]
0x18001772c  mov     ecx, 20h ; ' '
0x180017731  call    GetAlignedSize
0x180017736  mov     ebp, eax
0x180017738  test    eax, eax
0x18001773a  jnz     loc_1800177C1
0x180017740  xorps   xmm0, xmm0
0x180017743  mov     [r10+18h], eax
0x180017747  movups  xmmword ptr [r10+4], xmm0
0x18001774c  mov     eax, [r12+10h]
0x180017751  lea     rdx, [r12+18h]
0x180017756  mov     ecx, [r12+0Ch]
0x18001775b  mov     [rdx], eax
0x18001775d  call    IncrementDwordByAlignedSize
0x180017762  mov     ebp, eax
0x180017764  test    eax, eax
0x180017766  jnz     short loc_1800177C1
0x180017768  test    r13d, r13d
0x18001776b  jz      short loc_18001779B
0x18001776d  mov     edx, [rdx]
0x18001776f  mov     r8, r11; pSourceSid
0x180017772  add     rdx, r12; pDestinationSid
0x180017775  mov     ecx, r13d; nDestinationSidLength
0x180017778  call    cs:__imp_CopySid
0x18001777e  test    eax, eax
0x180017780  jnz     short loc_18001778E
0x180017782  call    cs:__imp_GetLastError
0x180017788  mov     ebp, eax
0x18001778a  test    eax, eax
0x18001778c  jnz     short loc_1800177C1
0x18001778e  or      dword ptr [r12+8], 1
0x180017794  mov     [r12+14h], r13d
0x180017799  jmp     short loc_1800177C1
0x18001779b  and     dword ptr [r12+8], 0FFFFFFFEh
0x1800177a1  mov     dword ptr [r12+14h], 0
0x1800177aa  jmp     short loc_1800177C1
0x1800177ac  mov     dword ptr [r12+0Ch], 0FFFFFFFFh
0x1800177b5  mov     ebp, 216h
0x1800177ba  jmp     short loc_1800177C1
0x1800177bc  mov     ebp, 57h ; 'W'
0x1800177c1  test    rbx, rbx
0x1800177c4  jnz     short loc_1800177E3
0x1800177c6  mov     r8d, 54h ; 'T'
0x1800177cc  mov     [rsp+58h+arg_0], rdi
0x1800177d1  lea     rdx, aOnexfreeuserpr; "OneXFreeUserProfile"
0x1800177d8  lea     rcx, [rsp+58h+arg_0]
0x1800177dd  call    cs:__imp_FreeMemory
0x1800177e3  cmp     [rsp+58h+arg_8], 0
0x1800177e9  mov     r15, [rsp+58h+var_38]
0x1800177ee  mov     r14, [rsp+58h+var_30]
0x1800177f3  mov     r13, [rsp+58h+var_28]
0x1800177f8  mov     r12, [rsp+58h+var_20]
0x1800177fd  mov     rdi, [rsp+58h+var_18]
0x180017802  mov     rsi, [rsp+58h+var_10]
0x180017807  mov     rbx, [rsp+58h+arg_10]
0x18001780c  jz      short loc_180017826
0x18001780e  mov     r8d, 2FEh
0x180017814  lea     rdx, aOnexseteapuser; "OneXSetEapUserData"
0x18001781b  lea     rcx, [rsp+58h+arg_8]
0x180017820  call    cs:__imp_FreeMemory
0x180017826  mov     eax, ebp
0x180017828  add     rsp, 50h
0x18001782c  pop     rbp
0x18001782d  retn
```
