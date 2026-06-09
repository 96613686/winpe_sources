# TREE_HASH_TABLE::InsertRecord(void *)

- ea: `0x180004250`
- end: `0x1800048fe`
- name: `?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z`
- size: `1710`
- prototype: `__int64 __fastcall(TREE_HASH_TABLE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002470`
- `0x180002b60`
- `0x180003190`
- `0x180003550`
- `0x180004150`
- `0x180004250`
- `0x180004f40`
- `0x180013870`
- `0x18002c476`
- `0x18002c48e`
- `0x18002c4c0`
- `0x18002d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004440`
- `msvcrt!_wcsicmp` at `0x180004440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000471d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000471d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045d6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180004807`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180004807`
- `bcrypt!BCryptCreateHash` at `0x180004831`
- `bcrypt!BCryptCreateHash` at `0x180004831`
- `bcrypt!BCryptFinishHash` at `0x18000486b`
- `bcrypt!BCryptFinishHash` at `0x18000486b`
- `bcrypt!BCryptHashData` at `0x18000484c`
- `bcrypt!BCryptHashData` at `0x18000484c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180004880`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180004880`
- `bcrypt!BCryptDestroyHash` at `0x180004890`
- `bcrypt!BCryptDestroyHash` at `0x180004890`

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
0x180004250  mov     r11, rsp
0x180004253  push    rbp
0x180004254  push    r12
0x180004256  push    r14
0x180004258  lea     rbp, [r11-438h]
0x18000425f  sub     rsp, 520h
0x180004266  mov     rax, cs:__security_cookie
0x18000426d  xor     rax, rsp
0x180004270  mov     [rbp+430h+var_40], rax
0x180004277  mov     rax, [rcx]
0x18000427a  mov     [r11+18h], rbx
0x18000427e  mov     [r11-20h], rsi
0x180004282  mov     [r11-28h], rdi
0x180004286  mov     rax, [rax+10h]
0x18000428a  mov     [r11-30h], r13
0x18000428e  mov     [r11-38h], r15
0x180004292  mov     r15, rcx
0x180004295  mov     [rsp+530h+var_4B8], rdx
0x18000429a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429f  xor     edx, edx; Val
0x1800042a1  mov     [rsp+530h+var_4C8], rax
0x1800042a6  mov     r8d, 1FEh; Size
0x1800042ac  lea     rcx, [rbp+430h+var_44E]; void *
0x1800042b0  mov     rbx, rax
0x1800042b3  call    memset_0
0x1800042b8  xor     ecx, ecx
0x1800042ba  lea     r12, [rbp+430h+String2]
0x1800042be  mov     [rbp+430h+String2], cx
0x1800042c2  xor     edi, edi
0x1800042c4  mov     dword ptr [rsp+530h+phAlgorithm], ecx
0x1800042c8  xor     r13b, r13b
0x1800042cb  lea     rcx, [r15+20h]; this
0x1800042cf  mov     [rsp+530h+phHash], rdi
0x1800042d4  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800042d9  test    rbx, rbx
0x1800042dc  jz      loc_1800048E0
0x1800042e2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800042e9  nop     dword ptr [rax+00000000h]
0x1800042f0  cmp     [rbx+rax*2+2], di
0x1800042f5  lea     rax, [rax+1]
0x1800042f9  jnz     short loc_1800042F0
0x1800042fb  lea     esi, [rax+rax]
0x1800042fe  mov     ecx, 0FFFFFFFFh
0x180004303  lea     rax, [rsi+2]
0x180004307  mov     r14d, esi
0x18000430a  cmp     rax, 200h
0x180004310  ja      loc_1800045B1
0x180004316  mov     r8, r14; Size
0x180004319  mov     rdx, rbx; Src
0x18000431c  mov     rcx, r12; void *
0x18000431f  call    memcpy_0
0x180004324  shr     esi, 1
0x180004326  xor     eax, eax
0x180004328  mov     r10d, esi
0x18000432b  xor     r14d, r14d
0x18000432e  mov     [rsp+530h+var_4D8], r10
0x180004333  mov     [r12+rsi*2], ax
0x180004338  test    r14d, r14d
0x18000433b  js      loc_180004478
0x180004341  mov     rcx, r12
0x180004344  lea     r9d, [r10-1]
0x180004348  mov     dword ptr [rsp+530h+var_4F0], r9d
0x18000434d  test    r9d, r9d
0x180004350  jz      loc_1800048F4
0x180004356  lea     r10, [r9+r9]
0x18000435a  movzx   eax, word ptr [rcx+r10]
0x18000435f  mov     [rsp+530h+var_4C0], r10
0x180004364  cmp     ax, 2Fh ; '/'
0x180004368  jnz     loc_1800046E4
0x18000436e  xor     eax, eax
0x180004370  mov     [rcx+r10], ax
0x180004375  test    r12, r12
0x180004378  jz      loc_1800048E0
0x18000437e  xor     r14d, r14d
0x180004381  cmp     [r15+18h], eax
0x180004385  jz      loc_180004745
0x18000438b  cmp     [r15+1Ch], eax
0x18000438f  jnz     loc_180004663
0x180004395  movzx   eax, word ptr [r12]
0x18000439a  xor     ebx, ebx
0x18000439c  test    ax, ax
0x18000439f  jz      short loc_1800043C4
0x1800043a1  mov     rcx, r12
0x1800043a4  nop     dword ptr [rax+00h]
0x1800043a8  nop     dword ptr [rax+rax+00000000h]
0x1800043b0  imul    ebx, 65h ; 'e'
0x1800043b3  lea     rcx, [rcx+2]
0x1800043b7  movzx   eax, ax
0x1800043ba  add     ebx, eax
0x1800043bc  movzx   eax, word ptr [rcx]
0x1800043bf  test    ax, ax
0x1800043c2  jnz     short loc_1800043B0
0x1800043c4  imul    eax, ebx, 10DCDh
0x1800043ca  xor     edx, edx
0x1800043cc  imul    esi, ebx, 41C64E6Dh
0x1800043d2  inc     eax
0x1800043d4  and     eax, 0FFFF0000h
0x1800043d9  add     esi, 3039h
0x1800043df  shr     esi, 10h
0x1800043e2  or      esi, eax
0x1800043e4  mov     eax, esi
0x1800043e6  mov     dword ptr [rsp+530h+phAlgorithm], esi
0x1800043ea  div     dword ptr [r15+10h]
0x1800043ee  mov     rax, [r15+8]
0x1800043f2  mov     rdi, [rax+rdx*8]
0x1800043f6  test    rdi, rdi
0x1800043f9  jz      loc_1800044A9
0x1800043ff  cmp     [rdi+30h], esi
0x180004402  jnz     loc_1800044A7
0x180004408  cmp     dword ptr [r15+18h], 0
0x18000440d  mov     rcx, [rdi+28h]; String1
0x180004411  jz      short loc_18000443D
0x180004413  mov     r8, r12
0x180004416  sub     r8, rcx
0x180004419  nop     dword ptr [rax+00000000h]
0x180004420  movzx   eax, word ptr [rcx]
0x180004423  movzx   edx, word ptr [rcx+r8]
0x180004428  sub     eax, edx
0x18000442a  jnz     short loc_180004434
0x18000442c  add     rcx, 2
0x180004430  test    edx, edx
0x180004432  jnz     short loc_180004420
0x180004434  test    eax, eax
0x180004436  jz      short loc_18000444A
0x180004438  mov     rdi, [rdi]
0x18000443b  jmp     short loc_1800043F6
0x18000443d  mov     rdx, r12; String2
0x180004440  call    cs:__imp__wcsicmp
0x180004446  test    eax, eax
0x180004448  jnz     short loc_180004438
0x18000444a  mov     rcx, [rsp+530h+var_4C0]
0x18000444f  mov     rsi, [rsp+530h+var_4C8]
0x180004454  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x180004459  mov     [rsp+530h+phHash], rdi
0x18000445e  movzx   eax, word ptr [rcx+rsi]
0x180004462  mov     [r12+rcx], ax
0x180004467  mov     rcx, r12
0x18000446a  mov     r10, [rsp+530h+var_4D8]
0x18000446f  cmp     r9d, r10d
0x180004472  jbe     loc_180004512
0x180004478  mov     rdi, [rsp+530h+var_20]
0x180004480  mov     rsi, [rsp+518h]
0x180004488  mov     rbx, [rsp+530h+arg_10]
0x180004490  mov     edx, [r15+20h]
0x180004494  mov     eax, edx
0x180004496  lea     ecx, [rdx-1]
0x180004499  lock cmpxchg [r15+20h], ecx
0x18000449f  cmp     edx, eax
0x1800044a1  jz      short loc_1800044BD
0x1800044a3  pause
0x1800044a5  jmp     short loc_180004490
0x1800044a7  jbe     short loc_180004438
0x1800044a9  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x1800044ae  xor     edi, edi
0x1800044b0  mov     [rsp+530h+phHash], rdi
0x1800044b5  mov     rcx, r12
0x1800044b8  jmp     loc_1800046EE
0x1800044bd  test    r14d, r14d
0x1800044c0  js      short loc_1800044CA
0x1800044c2  mov     rcx, r15; this
0x1800044c5  call    ?RehashTableIfNeeded@TREE_HASH_TABLE@@AEAAXXZ; TREE_HASH_TABLE::RehashTableIfNeeded(void)
0x1800044ca  mov     r15, [rsp+530h+var_30]
0x1800044d2  test    r13b, r13b
0x1800044d5  mov     r13, [rsp+530h+var_28]
0x1800044dd  jz      short loc_1800044F3
0x1800044df  call    cs:__imp_GetProcessHeap
0x1800044e5  mov     r8, r12; lpMem
0x1800044e8  xor     edx, edx; dwFlags
0x1800044ea  mov     rcx, rax; hHeap
0x1800044ed  call    cs:__imp_HeapFree
0x1800044f3  mov     eax, r14d
0x1800044f6  mov     rcx, [rbp+430h+var_40]
0x1800044fd  xor     rcx, rsp; StackCookie
0x180004500  call    __security_check_cookie
0x180004505  add     rsp, 520h
0x18000450c  pop     r14
0x18000450e  pop     r12
0x180004510  pop     rbp
0x180004511  retn
0x180004512  mov     eax, r9d
0x180004515  lea     rbx, [rax+rax]
0x180004519  cmp     word ptr [rbx+rcx], 0
0x18000451e  jnz     short loc_18000459B
0x180004520  lea     r8, [rsp+530h+phAlgorithm]; unsigned int *
0x180004525  mov     rdx, r12; unsigned __int16 *
0x180004528  mov     rcx, r15; this
0x18000452b  call    ?CalcHash@TREE_HASH_TABLE@@QEAAJPEBGPEAK@Z; TREE_HASH_TABLE::CalcHash(ushort const *,ulong *)
0x180004530  mov     r14d, eax
0x180004533  test    eax, eax
0x180004535  js      loc_180004478
0x18000453b  mov     rcx, [rsp+530h+var_4D8]
0x180004540  xor     eax, eax
0x180004542  cmp     dword ptr [rsp+530h+var_4F0], ecx
0x180004546  mov     rdx, r12; unsigned __int16 *
0x180004549  mov     r9, [rsp+530h+var_4B8]
0x18000454e  mov     rcx, r15; this
0x180004551  mov     r8d, dword ptr [rsp+530h+phAlgorithm]; unsigned int
0x180004556  cmovnz  r9, rax; void *
0x18000455a  lea     rax, [rsp+530h+phHash]
0x18000455f  mov     qword ptr [rsp+530h+cbSecret], rax; struct TREE_HASH_NODE **
0x180004564  mov     [rsp+530h+pbSecret], rdi; struct TREE_HASH_NODE *
0x180004569  call    ?AddNodeInternal@TREE_HASH_TABLE@@AEAAJPEBGKPEAXPEAUTREE_HASH_NODE@@PEAPEAU2@@Z; TREE_HASH_TABLE::AddNodeInternal(ushort const *,ulong,void *,TREE_HASH_NODE *,TREE_HASH_NODE * *)
0x18000456e  mov     edx, 80000000h
0x180004573  mov     r14d, eax
0x180004576  add     eax, edx
0x180004578  test    edx, eax
0x18000457a  jz      loc_1800046FB
0x180004580  movzx   eax, word ptr [rbx+rsi]
0x180004584  mov     rcx, r12
0x180004587  mov     rdi, [rsp+530h+phHash]
0x18000458c  mov     r9d, dword ptr [rsp+530h+var_4F0]
0x180004591  mov     r10, [rsp+530h+var_4D8]
0x180004596  mov     [rbx+r12], ax
0x18000459b  inc     r9d
0x18000459e  mov     dword ptr [rsp+530h+var_4F0], r9d
0x1800045a3  cmp     r9d, r10d
0x1800045a6  jbe     loc_180004512
0x1800045ac  jmp     loc_180004478
0x1800045b1  xor     r10d, r10d
0x1800045b4  lea     rax, [rsi+80h]
0x1800045bb  mov     [rsp+530h+var_4D8], r10
0x1800045c0  cmp     rax, rcx
0x1800045c3  ja      loc_18000470D
0x1800045c9  cmp     eax, 200h
0x1800045ce  jbe     loc_180004316
0x1800045d4  mov     ebx, eax
0x1800045d6  call    cs:__imp_GetProcessHeap
0x1800045dc  mov     r8d, ebx; dwBytes
0x1800045df  xor     edx, edx; dwFlags
0x1800045e1  mov     rcx, rax; hHeap
0x1800045e4  call    cs:__imp_HeapAlloc
0x1800045ea  mov     rdx, rax
0x1800045ed  test    rax, rax
0x1800045f0  jz      loc_180004718
0x1800045f6  lea     rcx, [rbp+430h+String2]
0x1800045fa  mov     r8d, 4
0x180004600  lea     rax, [rax+80h]
0x180004607  movups  xmm0, xmmword ptr [rcx]
0x18000460a  lea     rcx, [rcx+80h]
0x180004611  movups  xmmword ptr [rax-80h], xmm0
0x180004615  movups  xmm1, xmmword ptr [rcx-70h]
0x180004619  movups  xmmword ptr [rax-70h], xmm1
0x18000461d  movups  xmm0, xmmword ptr [rcx-60h]
0x180004621  movups  xmmword ptr [rax-60h], xmm0
0x180004625  movups  xmm1, xmmword ptr [rcx-50h]
0x180004629  movups  xmmword ptr [rax-50h], xmm1
0x18000462d  movups  xmm0, xmmword ptr [rcx-40h]
0x180004631  movups  xmmword ptr [rax-40h], xmm0
0x180004635  movups  xmm1, xmmword ptr [rcx-30h]
0x180004639  movups  xmmword ptr [rax-30h], xmm1
0x18000463d  movups  xmm0, xmmword ptr [rcx-20h]
0x180004641  movups  xmmword ptr [rax-20h], xmm0
0x180004645  movups  xmm1, xmmword ptr [rcx-10h]
0x180004649  movups  xmmword ptr [rax-10h], xmm1
0x18000464d  sub     r8, 1
0x180004651  jnz     short loc_180004600
0x180004653  mov     rbx, [rsp+530h+var_4C8]
0x180004658  mov     r12, rdx
0x18000465b  mov     r13b, 1
0x18000465e  jmp     loc_180004316
0x180004663  xor     edx, edx; Val
0x180004665  lea     rcx, [rbp+430h+var_24E]; void *
0x18000466c  mov     r8d, 206h; Size
0x180004672  call    memset_0
0x180004677  xor     eax, eax
0x180004679  mov     [rbp+430h+var_488], 208h
0x180004680  lea     rbx, [rbp+430h+pbInput]
0x180004687  mov     word ptr [rbp+430h+pbInput], ax
0x18000468e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004695  mov     [rbp+430h+var_490], rbx
0x180004699  mov     [rbp+430h+var_484], 100h
0x18000469f  mov     [rbp+430h+var_480], r14d
0x1800046a3  cmp     [r12+rax*2+2], r14w
0x1800046a9  lea     rax, [rax+1]
0x1800046ad  jnz     short loc_1800046A3
0x1800046af  lea     edi, [rax+rax]
0x1800046b2  lea     rax, [rdi+2]
0x1800046b6  mov     esi, edi
0x1800046b8  cmp     rax, 208h
0x1800046be  ja      loc_18000477C
0x1800046c4  mov     r8, rsi; Size
0x1800046c7  mov     rdx, r12; Src
0x1800046ca  mov     rcx, rbx; void *
0x1800046cd  call    memcpy_0
0x1800046d2  shr     edi, 1
0x1800046d4  mov     ecx, edi
0x1800046d6  xor     esi, esi
0x1800046d8  mov     [rbp+430h+var_480], ecx
0x1800046db  mov     [rbx+rdi*2], si
0x1800046df  jmp     loc_1800047CC
0x1800046e4  cmp     ax, 5Ch ; '\'
0x1800046e8  jz      loc_18000436E
0x1800046ee  mov     eax, 0FFFFFFFFh
0x1800046f3  add     r9d, eax
0x1800046f6  jmp     loc_180004348
0x1800046fb  cmp     r14d, 800700B7h
0x180004702  jz      loc_180004580
0x180004708  jmp     loc_180004478
0x18000470d  mov     r14d, 80070216h
0x180004713  jmp     loc_180004338
  ... truncated ...
```
