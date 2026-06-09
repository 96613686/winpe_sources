# TREE_HASH_TABLE::InsertRecord(void *)

- ea: `0x180004d50`
- end: `0x180005459`
- name: `?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z`
- size: `1801`
- prototype: `__int64 __fastcall(TREE_HASH_TABLE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x180003b80`
- `0x180003fb0`
- `0x180004c30`
- `0x180004d50`
- `0x180005aa0`
- `0x1800142d0`
- `0x18002e516`
- `0x18002e52e`
- `0x18002e560`
- `0x18002f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004f40`
- `msvcrt!_wcsicmp` at `0x180004f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000524a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000524a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ff9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ff9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005108`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050f4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000533e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000533e`
- `bcrypt!BCryptCreateHash` at `0x18000536e`
- `bcrypt!BCryptCreateHash` at `0x18000536e`
- `bcrypt!BCryptFinishHash` at `0x1800053b4`
- `bcrypt!BCryptFinishHash` at `0x1800053b4`
- `bcrypt!BCryptHashData` at `0x18000538f`
- `bcrypt!BCryptHashData` at `0x18000538f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800053cf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800053cf`
- `bcrypt!BCryptDestroyHash` at `0x1800053e5`
- `bcrypt!BCryptDestroyHash` at `0x1800053e5`

## pseudocode

```c
__int64 __fastcall TREE_HASH_TABLE::InsertRecord(TREE_HASH_TABLE *this, void *a2)
{
  __int64 (*v2)(void); // rax
  const void *v4; // rbx
  wchar_t *p_String2; // r12
  _DWORD *j; // rdi
  char v7; // r13
  __int64 v8; // rax
  bool v9; // zf
  __int64 v10; // rsi
  __int64 v11; // rsi
  int v12; // r10d
  int v13; // r14d
  wchar_t *v14; // rcx
  __int64 i; // r9
  wchar_t v16; // ax
  wchar_t v17; // ax
  int v18; // ebx
  wchar_t *v19; // rcx
  unsigned int v20; // esi
  const wchar_t *v21; // rcx
  signed __int64 v22; // r8
  int v23; // edx
  int v24; // eax
  __int64 v25; // rsi
  unsigned int k; // r10d
  signed __int32 v27; // edx
  HANDLE v28; // rax
  __int64 v30; // rbx
  void *v31; // r9
  HANDLE ProcessHeap; // rax
  wchar_t *v33; // rax
  wchar_t *v34; // rdx
  wchar_t *v35; // rcx
  __int64 v36; // r8
  __int128 v37; // xmm0
  UCHAR *v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rdi
  int v42; // ecx
  signed int LastError; // eax
  wchar_t v44; // cx
  wchar_t *v45; // rdx
  signed int v46; // eax
  ULONG v47; // edi
  unsigned __int64 v48; // rdx
  unsigned int v49; // r8d
  NTSTATUS v50; // r14d
  int v51; // [rsp+48h] [rbp-C0h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A8h]
  __int64 v55; // [rsp+70h] [rbp-98h]
  __int64 v56; // [rsp+78h] [rbp-90h]
  void *v57; // [rsp+80h] [rbp-88h]
  _BYTE v58[32]; // [rsp+88h] [rbp-80h] BYREF
  UCHAR *v59; // [rsp+A8h] [rbp-60h]
  int v60; // [rsp+B0h] [rbp-58h]
  __int16 v61; // [rsp+B4h] [rbp-54h]
  int v62; // [rsp+B8h] [rbp-50h]
  UCHAR pbOutput[16]; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v64; // [rsp+D0h] [rbp-38h]
  wchar_t String2; // [rsp+E8h] [rbp-20h] BYREF
  char v66[510]; // [rsp+EAh] [rbp-1Eh] BYREF
  UCHAR pbInput[2]; // [rsp+2E8h] [rbp+1E0h] BYREF
  char v68[526]; // [rsp+2EAh] [rbp+1E2h] BYREF

  v2 = *(__int64 (**)(void))(*(_QWORD *)this + 16LL);
  v57 = a2;
  v55 = v2();
  v4 = (const void *)v55;
  memset_0(v66, 0, sizeof(v66));
  p_String2 = &String2;
  String2 = 0;
  j = 0;
  LODWORD(phAlgorithm) = 0;
  v7 = 0;
  phHash = 0;
  CReaderWriterLock3::ReadLock((TREE_HASH_TABLE *)((char *)this + 32));
  if ( !v55 )
  {
LABEL_89:
    v13 = -2147024809;
    goto LABEL_28;
  }
  v8 = -1;
  do
    v9 = *(_WORD *)(v55 + 2 * v8++ + 2) == 0;
  while ( !v9 );
  v10 = (unsigned int)(2 * v8);
  if ( (unsigned __int64)(v10 + 2) > 0x200 )
  {
    v12 = 0;
    v54 = 0;
    if ( (unsigned __int64)(v10 + 128) > 0xFFFFFFFF )
    {
      v13 = -2147024362;
      goto LABEL_6;
    }
    if ( (unsigned int)(v10 + 128) > 0x200 )
    {
      ProcessHeap = GetProcessHeap();
      v33 = (wchar_t *)HeapAlloc(ProcessHeap, 0, (unsigned int)(v10 + 128));
      v34 = v33;
      if ( !v33 )
      {
        SetLastError(8u);
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        v12 = v54;
        goto LABEL_6;
      }
      v35 = &String2;
      v36 = 4;
      do
      {
        v33 += 64;
        v37 = *(_OWORD *)v35;
        v35 += 64;
        *((_OWORD *)v33 - 8) = v37;
        *((_OWORD *)v33 - 7) = *((_OWORD *)v35 - 7);
        *((_OWORD *)v33 - 6) = *((_OWORD *)v35 - 6);
        *((_OWORD *)v33 - 5) = *((_OWORD *)v35 - 5);
        *((_OWORD *)v33 - 4) = *((_OWORD *)v35 - 4);
        *((_OWORD *)v33 - 3) = *((_OWORD *)v35 - 3);
        *((_OWORD *)v33 - 2) = *((_OWORD *)v35 - 2);
        *((_OWORD *)v33 - 1) = *((_OWORD *)v35 - 1);
        --v36;
      }
      while ( v36 );
      v4 = (const void *)v55;
      p_String2 = v34;
      v7 = 1;
    }
  }
  memcpy_0(p_String2, v4, (unsigned int)v10);
  v11 = (unsigned int)v10 >> 1;
  v12 = v11;
  v13 = 0;
  v54 = (unsigned int)v11;
  p_String2[v11] = 0;
LABEL_6:
  if ( v13 < 0 )
    goto LABEL_28;
  v14 = p_String2;
  for ( i = (unsigned int)(v12 - 1); ; i = (unsigned int)(i - 1) )
  {
    v51 = i;
    if ( !(_DWORD)i )
      break;
    v16 = v14[i];
    v56 = 2 * i;
    if ( v16 != 47 && v16 != 92 )
      continue;
    v14[i] = 0;
    if ( !p_String2 )
      goto LABEL_89;
    v13 = 0;
    if ( *((_DWORD *)this + 6) )
    {
      if ( *((_DWORD *)this + 7) )
      {
        memset_0(v68, 0, 0x206u);
        v60 = 520;
        v38 = pbInput;
        *(_WORD *)pbInput = 0;
        v39 = -1;
        v59 = pbInput;
        v61 = 256;
        v62 = 0;
        do
          v9 = p_String2[++v39] == 0;
        while ( !v9 );
        v40 = (unsigned int)(2 * v39);
        if ( (unsigned __int64)(v40 + 2) > 0x208 )
        {
          if ( (unsigned __int64)(v40 + 128) > 0xFFFFFFFF )
          {
            v13 = -2147024362;
            goto LABEL_86;
          }
          if ( BUFFER::Resize((BUFFER *)v58, v40 + 128) )
          {
            v38 = v59;
            goto LABEL_54;
          }
          v46 = GetLastError();
          v13 = v46;
          if ( v46 > 0 )
            v13 = (unsigned __int16)v46 | 0x80070000;
          if ( v13 < 0 )
            goto LABEL_86;
          v42 = v62;
          v38 = v59;
        }
        else
        {
LABEL_54:
          memcpy_0(v38, p_String2, (unsigned int)v40);
          v41 = (unsigned int)v40 >> 1;
          v42 = v41;
          v62 = v41;
          *(_WORD *)&v38[2 * v41] = 0;
        }
        phAlgorithm = 0;
        phHash = 0;
        *(_OWORD *)pbOutput = 0;
        v64 = 0;
        if ( !v38 || (v47 = 2 * v42) == 0 )
        {
          v13 = -805306355;
LABEL_86:
          BUFFER::~BUFFER((BUFFER *)v58);
          goto LABEL_28;
        }
        v50 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
        if ( v50 >= 0 )
        {
          v50 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
          if ( v50 >= 0 )
          {
            v50 = BCryptHashData(phHash, v38, v47, 0);
            if ( v50 >= 0 )
              v50 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          }
        }
        if ( phAlgorithm )
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        if ( phHash )
          BCryptDestroyHash(phHash);
        v13 = v50 | 0x10000000;
        if ( v13 < 0 )
          goto LABEL_86;
        v18 = HashBlob(pbOutput, v48, v49);
        BUFFER::~BUFFER((BUFFER *)v58);
        goto LABEL_16;
      }
      v17 = *p_String2;
      v18 = 0;
      if ( *p_String2 )
      {
        v19 = p_String2;
        do
        {
          ++v19;
          v18 = v17 + 101 * v18;
          v17 = *v19;
        }
        while ( *v19 );
      }
    }
    else
    {
      v44 = *p_String2;
      v18 = 0;
      if ( *p_String2 )
      {
        v45 = p_String2;
        do
        {
          ++v45;
          v18 = (v44 & 0xFFDF) + 101 * v18;
          v44 = *v45;
        }
        while ( *v45 );
      }
    }
LABEL_16:
    v20 = (69069 * v18 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v18 + 12345) >> 16);
    LODWORD(phAlgorithm) = v20;
    for ( j = *(_DWORD **)(*((_QWORD *)this + 1)
                         + 8
                         * (((69069 * v18 + 1) & 0xFFFF0000
                           | (unsigned __int64)((unsigned int)(1103515245 * v18 + 12345) >> 16))
                          % *((unsigned int *)this + 4))); j; j = *(_DWORD **)j )
    {
      if ( j[12] == v20 )
      {
        v21 = (const wchar_t *)*((_QWORD *)j + 5);
        if ( *((_DWORD *)this + 6) )
        {
          v22 = (char *)p_String2 - (char *)v21;
          do
          {
            v23 = *(const wchar_t *)((char *)v21 + v22);
            v24 = *v21 - v23;
            if ( v24 )
              break;
            ++v21;
          }
          while ( v23 );
          if ( !v24 )
          {
LABEL_26:
            v25 = v55;
            LODWORD(i) = v51;
            phHash = j;
            p_String2[(unsigned __int64)v56 / 2] = *(_WORD *)(v56 + v55);
            v14 = p_String2;
            goto LABEL_27;
          }
        }
        else if ( !_wcsicmp(v21, p_String2) )
        {
          goto LABEL_26;
        }
      }
      else if ( j[12] > v20 )
      {
        break;
      }
    }
    LODWORD(i) = v51;
    j = 0;
    phHash = 0;
    v14 = p_String2;
  }
  v25 = v55;
LABEL_27:
  for ( k = v54; (unsigned int)i <= k; v51 = i )
  {
    v30 = (unsigned int)i;
    if ( !v14[v30] )
    {
      v13 = TREE_HASH_TABLE::CalcHash(this, p_String2, (unsigned int *)&phAlgorithm);
      if ( v13 < 0 )
        break;
      v31 = v57;
      if ( v51 != (_DWORD)v54 )
        v31 = 0;
      v13 = TREE_HASH_TABLE::AddNodeInternal(
              this,
              p_String2,
              (unsigned int)phAlgorithm,
              v31,
              (struct TREE_HASH_NODE *)j,
              (struct TREE_HASH_NODE **)&phHash);
      if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147024713 )
        break;
      v14 = p_String2;
      j = phHash;
      LODWORD(i) = v51;
      k = v54;
      p_String2[v30] = *(_WORD *)(v30 * 2 + v25);
    }
    LODWORD(i) = i + 1;
  }
LABEL_28:
  while ( 1 )
  {
    v27 = *((_DWORD *)this + 8);
    if ( v27 == _InterlockedCompareExchange((volatile signed __int32 *)this + 8, v27 - 1, v27) )
      break;
    _mm_pause();
  }
  if ( v13 >= 0 )
    TREE_HASH_TABLE::RehashTableIfNeeded(this);
  if ( v7 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, p_String2);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180004d50  mov     r11, rsp
0x180004d53  push    rbp
0x180004d54  push    r12
0x180004d56  push    r14
0x180004d58  lea     rbp, [r11-438h]
0x180004d5f  sub     rsp, 520h
0x180004d66  mov     rax, cs:__security_cookie
0x180004d6d  xor     rax, rsp
0x180004d70  mov     [rbp+430h+var_40], rax
0x180004d77  mov     rax, [rcx]
0x180004d7a  mov     [r11+18h], rbx
0x180004d7e  mov     [r11-20h], rsi
0x180004d82  mov     [r11-28h], rdi
0x180004d86  mov     rax, [rax+10h]
0x180004d8a  mov     [r11-30h], r13
0x180004d8e  mov     [r11-38h], r15
0x180004d92  mov     r15, rcx
0x180004d95  mov     [rsp+530h+var_4B8], rdx
0x180004d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9f  xor     edx, edx; Val
0x180004da1  mov     [rsp+530h+var_4C8], rax
0x180004da6  mov     r8d, 1FEh; Size
0x180004dac  lea     rcx, [rbp+430h+var_44E]; void *
0x180004db0  mov     rbx, rax
0x180004db3  call    memset_0
0x180004db8  xor     ecx, ecx
0x180004dba  lea     r12, [rbp+430h+String2]
0x180004dbe  mov     [rbp+430h+String2], cx
0x180004dc2  xor     edi, edi
0x180004dc4  mov     dword ptr [rsp+530h+phAlgorithm], ecx
0x180004dc8  xor     r13b, r13b
0x180004dcb  lea     rcx, [r15+20h]; this
0x180004dcf  mov     [rsp+530h+phHash], rdi
0x180004dd4  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180004dd9  test    rbx, rbx
0x180004ddc  jz      loc_18000543B
0x180004de2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004de9  nop     dword ptr [rax+00000000h]
0x180004df0  cmp     [rbx+rax*2+2], di
0x180004df5  lea     rax, [rax+1]
0x180004df9  jnz     short loc_180004DF0
0x180004dfb  lea     esi, [rax+rax]
0x180004dfe  mov     ecx, 0FFFFFFFFh
0x180004e03  lea     rax, [rsi+2]
0x180004e07  mov     r14d, esi
0x180004e0a  cmp     rax, 200h
0x180004e10  ja      loc_1800050CF
0x180004e16  mov     r8, r14; Size
0x180004e19  mov     rdx, rbx; Src
0x180004e1c  mov     rcx, r12; void *
0x180004e1f  call    memcpy_0
0x180004e24  shr     esi, 1
0x180004e26  xor     eax, eax
0x180004e28  mov     r10d, esi
0x180004e2b  xor     r14d, r14d
0x180004e2e  mov     [rsp+530h+var_4D8], r10
0x180004e33  mov     [r12+rsi*2], ax
0x180004e38  test    r14d, r14d
0x180004e3b  js      loc_180004F7E
0x180004e41  mov     rcx, r12
0x180004e44  lea     r9d, [r10-1]
0x180004e48  mov     dword ptr [rsp+530h+var_4F0], r9d
0x180004e4d  test    r9d, r9d
0x180004e50  jz      loc_18000544F
0x180004e56  lea     r10, [r9+r9]
0x180004e5a  movzx   eax, word ptr [rcx+r10]
0x180004e5f  mov     [rsp+530h+var_4C0], r10
0x180004e64  cmp     ax, 2Fh ; '/'
0x180004e68  jnz     loc_180005211
0x180004e6e  xor     eax, eax
0x180004e70  mov     [rcx+r10], ax
0x180004e75  test    r12, r12
0x180004e78  jz      loc_18000543B
0x180004e7e  xor     r14d, r14d
0x180004e81  cmp     [r15+18h], eax
0x180004e85  jz      loc_18000527E
0x180004e8b  cmp     [r15+1Ch], eax
0x180004e8f  jnz     loc_18000518D
0x180004e95  movzx   eax, word ptr [r12]
0x180004e9a  xor     ebx, ebx
0x180004e9c  test    ax, ax
0x180004e9f  jz      short loc_180004EC4
0x180004ea1  mov     rcx, r12
0x180004ea4  nop     dword ptr [rax+00h]
0x180004ea8  nop     dword ptr [rax+rax+00000000h]
0x180004eb0  imul    ebx, 65h ; 'e'
0x180004eb3  lea     rcx, [rcx+2]
0x180004eb7  movzx   eax, ax
0x180004eba  add     ebx, eax
0x180004ebc  movzx   eax, word ptr [rcx]
0x180004ebf  test    ax, ax
0x180004ec2  jnz     short loc_180004EB0
0x180004ec4  imul    eax, ebx, 10DCDh
0x180004eca  xor     edx, edx
0x180004ecc  imul    esi, ebx, 41C64E6Dh
0x180004ed2  inc     eax
0x180004ed4  and     eax, 0FFFF0000h
0x180004ed9  add     esi, 3039h
0x180004edf  shr     esi, 10h
0x180004ee2  or      esi, eax
0x180004ee4  mov     eax, esi
0x180004ee6  mov     dword ptr [rsp+530h+phAlgorithm], esi
0x180004eea  div     dword ptr [r15+10h]
0x180004eee  mov     rax, [r15+8]
0x180004ef2  mov     rdi, [rax+rdx*8]
0x180004ef6  test    rdi, rdi
0x180004ef9  jz      loc_180004FAF
0x180004eff  cmp     [rdi+30h], esi
0x180004f02  jnz     loc_180004FAD
0x180004f08  cmp     dword ptr [r15+18h], 0
0x180004f0d  mov     rcx, [rdi+28h]; String1
0x180004f11  jz      short loc_180004F3D
0x180004f13  mov     r8, r12
0x180004f16  sub     r8, rcx
0x180004f19  nop     dword ptr [rax+00000000h]
0x180004f20  movzx   eax, word ptr [rcx]
0x180004f23  movzx   edx, word ptr [rcx+r8]
0x180004f28  sub     eax, edx
0x180004f2a  jnz     short loc_180004F34
0x180004f2c  add     rcx, 2
0x180004f30  test    edx, edx
0x180004f32  jnz     short loc_180004F20
0x180004f34  test    eax, eax
0x180004f36  jz      short loc_180004F50
0x180004f38  mov     rdi, [rdi]
0x180004f3b  jmp     short loc_180004EF6
0x180004f3d  mov     rdx, r12; String2
0x180004f40  call    cs:__imp__wcsicmp
0x180004f47  nop     dword ptr [rax+rax+00h]
0x180004f4c  test    eax, eax
0x180004f4e  jnz     short loc_180004F38
0x180004f50  mov     rcx, [rsp+530h+var_4C0]
0x180004f55  mov     rsi, [rsp+530h+var_4C8]
0x180004f5a  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x180004f5f  mov     [rsp+530h+phHash], rdi
0x180004f64  movzx   eax, word ptr [rcx+rsi]
0x180004f68  mov     [r12+rcx], ax
0x180004f6d  mov     rcx, r12
0x180004f70  mov     r10, [rsp+530h+var_4D8]
0x180004f75  cmp     r9d, r10d
0x180004f78  jbe     loc_180005030
0x180004f7e  mov     rdi, [rsp+530h+var_20]
0x180004f86  mov     rsi, [rsp+518h]
0x180004f8e  mov     rbx, [rsp+530h+arg_10]
0x180004f96  mov     edx, [r15+20h]
0x180004f9a  mov     eax, edx
0x180004f9c  lea     ecx, [rdx-1]
0x180004f9f  lock cmpxchg [r15+20h], ecx
0x180004fa5  cmp     edx, eax
0x180004fa7  jz      short loc_180004FC3
0x180004fa9  pause
0x180004fab  jmp     short loc_180004F96
0x180004fad  jbe     short loc_180004F38
0x180004faf  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x180004fb4  xor     edi, edi
0x180004fb6  mov     [rsp+530h+phHash], rdi
0x180004fbb  mov     rcx, r12
0x180004fbe  jmp     loc_18000521B
0x180004fc3  test    r14d, r14d
0x180004fc6  js      short loc_180004FD0
0x180004fc8  mov     rcx, r15; this
0x180004fcb  call    ?RehashTableIfNeeded@TREE_HASH_TABLE@@AEAAXXZ; TREE_HASH_TABLE::RehashTableIfNeeded(void)
0x180004fd0  mov     r15, [rsp+530h+var_30]
0x180004fd8  test    r13b, r13b
0x180004fdb  mov     r13, [rsp+530h+var_28]
0x180004fe3  jz      short loc_180005005
0x180004fe5  call    cs:__imp_GetProcessHeap
0x180004fec  nop     dword ptr [rax+rax+00h]
0x180004ff1  mov     r8, r12; lpMem
0x180004ff4  xor     edx, edx; dwFlags
0x180004ff6  mov     rcx, rax; hHeap
0x180004ff9  call    cs:__imp_HeapFree
0x180005000  nop     dword ptr [rax+rax+00h]
0x180005005  mov     eax, r14d
0x180005008  mov     rcx, [rbp+430h+var_40]
0x18000500f  xor     rcx, rsp; StackCookie
0x180005012  call    __security_check_cookie
0x180005017  add     rsp, 520h
0x18000501e  pop     r14
0x180005020  pop     r12
0x180005022  pop     rbp
0x180005023  retn
0x180005030  mov     eax, r9d
0x180005033  lea     rbx, [rax+rax]
0x180005037  cmp     word ptr [rbx+rcx], 0
0x18000503c  jnz     short loc_1800050B9
0x18000503e  lea     r8, [rsp+530h+phAlgorithm]; unsigned int *
0x180005043  mov     rdx, r12; unsigned __int16 *
0x180005046  mov     rcx, r15; this
0x180005049  call    ?CalcHash@TREE_HASH_TABLE@@QEAAJPEBGPEAK@Z; TREE_HASH_TABLE::CalcHash(ushort const *,ulong *)
0x18000504e  mov     r14d, eax
0x180005051  test    eax, eax
0x180005053  js      loc_180004F7E
0x180005059  mov     rcx, [rsp+530h+var_4D8]
0x18000505e  xor     eax, eax
0x180005060  cmp     dword ptr [rsp+530h+var_4F0], ecx
0x180005064  mov     rdx, r12; unsigned __int16 *
0x180005067  mov     r9, [rsp+530h+var_4B8]
0x18000506c  mov     rcx, r15; this
0x18000506f  mov     r8d, dword ptr [rsp+530h+phAlgorithm]; unsigned int
0x180005074  cmovnz  r9, rax; void *
0x180005078  lea     rax, [rsp+530h+phHash]
0x18000507d  mov     qword ptr [rsp+530h+cbSecret], rax; struct TREE_HASH_NODE **
0x180005082  mov     [rsp+530h+pbSecret], rdi; struct TREE_HASH_NODE *
0x180005087  call    ?AddNodeInternal@TREE_HASH_TABLE@@AEAAJPEBGKPEAXPEAUTREE_HASH_NODE@@PEAPEAU2@@Z; TREE_HASH_TABLE::AddNodeInternal(ushort const *,ulong,void *,TREE_HASH_NODE *,TREE_HASH_NODE * *)
0x18000508c  mov     edx, 80000000h
0x180005091  mov     r14d, eax
0x180005094  add     eax, edx
0x180005096  test    edx, eax
0x180005098  jz      loc_180005228
0x18000509e  movzx   eax, word ptr [rbx+rsi]
0x1800050a2  mov     rcx, r12
0x1800050a5  mov     rdi, [rsp+530h+phHash]
0x1800050aa  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x1800050af  mov     r10, [rsp+530h+var_4D8]
0x1800050b4  mov     [rbx+r12], ax
0x1800050b9  inc     r9d
0x1800050bc  mov     dword ptr [rsp+530h+var_4F0], r9d
0x1800050c1  cmp     r9d, r10d
0x1800050c4  jbe     loc_180005030
0x1800050ca  jmp     loc_180004F7E
0x1800050cf  xor     r10d, r10d
0x1800050d2  lea     rax, [rsi+80h]
0x1800050d9  mov     [rsp+530h+var_4D8], r10
0x1800050de  cmp     rax, rcx
0x1800050e1  ja      loc_18000523A
0x1800050e7  cmp     eax, 200h
0x1800050ec  jbe     loc_180004E16
0x1800050f2  mov     ebx, eax
0x1800050f4  call    cs:__imp_GetProcessHeap
0x1800050fb  nop     dword ptr [rax+rax+00h]
0x180005100  mov     r8d, ebx; dwBytes
0x180005103  xor     edx, edx; dwFlags
0x180005105  mov     rcx, rax; hHeap
0x180005108  call    cs:__imp_HeapAlloc
0x18000510f  nop     dword ptr [rax+rax+00h]
0x180005114  mov     rdx, rax
0x180005117  test    rax, rax
0x18000511a  jz      loc_180005245
0x180005120  lea     rcx, [rbp+430h+String2]
0x180005124  mov     r8d, 4
0x18000512a  lea     rax, [rax+80h]
0x180005131  movups  xmm0, xmmword ptr [rcx]
0x180005134  lea     rcx, [rcx+80h]
0x18000513b  movups  xmmword ptr [rax-80h], xmm0
0x18000513f  movups  xmm1, xmmword ptr [rcx-70h]
0x180005143  movups  xmmword ptr [rax-70h], xmm1
0x180005147  movups  xmm0, xmmword ptr [rcx-60h]
0x18000514b  movups  xmmword ptr [rax-60h], xmm0
0x18000514f  movups  xmm1, xmmword ptr [rcx-50h]
0x180005153  movups  xmmword ptr [rax-50h], xmm1
0x180005157  movups  xmm0, xmmword ptr [rcx-40h]
0x18000515b  movups  xmmword ptr [rax-40h], xmm0
0x18000515f  movups  xmm1, xmmword ptr [rcx-30h]
0x180005163  movups  xmmword ptr [rax-30h], xmm1
0x180005167  movups  xmm0, xmmword ptr [rcx-20h]
0x18000516b  movups  xmmword ptr [rax-20h], xmm0
0x18000516f  movups  xmm1, xmmword ptr [rcx-10h]
0x180005173  movups  xmmword ptr [rax-10h], xmm1
0x180005177  sub     r8, 1
0x18000517b  jnz     short loc_18000512A
0x18000517d  mov     rbx, [rsp+530h+var_4C8]
0x180005182  mov     r12, rdx
0x180005185  mov     r13b, 1
0x180005188  jmp     loc_180004E16
0x18000518d  xor     edx, edx; Val
0x18000518f  lea     rcx, [rbp+430h+var_24E]; void *
0x180005196  mov     r8d, 206h; Size
0x18000519c  call    memset_0
0x1800051a1  xor     eax, eax
0x1800051a3  mov     [rbp+430h+var_488], 208h
0x1800051aa  lea     rbx, [rbp+430h+pbInput]
0x1800051b1  mov     word ptr [rbp+430h+pbInput], ax
0x1800051b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800051bf  mov     [rbp+430h+var_490], rbx
0x1800051c3  mov     [rbp+430h+var_484], 100h
0x1800051c9  mov     [rbp+430h+var_480], r14d
0x1800051cd  nop     dword ptr [rax]
0x1800051d0  cmp     [r12+rax*2+2], r14w
0x1800051d6  lea     rax, [rax+1]
0x1800051da  jnz     short loc_1800051D0
0x1800051dc  lea     edi, [rax+rax]
0x1800051df  lea     rax, [rdi+2]
0x1800051e3  mov     esi, edi
0x1800051e5  cmp     rax, 208h
0x1800051eb  ja      loc_1800052AD
0x1800051f1  mov     r8, rsi; Size
0x1800051f4  mov     rdx, r12; Src
0x1800051f7  mov     rcx, rbx; void *
0x1800051fa  call    memcpy_0
0x1800051ff  shr     edi, 1
0x180005201  mov     ecx, edi
0x180005203  xor     esi, esi
0x180005205  mov     [rbp+430h+var_480], ecx
0x180005208  mov     [rbx+rdi*2], si
0x18000520c  jmp     loc_180005303
0x180005211  cmp     ax, 5Ch ; '\'
0x180005215  jz      loc_180004E6E
0x18000521b  mov     eax, 0FFFFFFFFh
0x180005220  add     r9d, eax
  ... truncated ...
```
