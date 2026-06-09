# InstallOIDFunctionAddress(HINSTANCE__ *,ulong,_FUNC_SET *,ulong,_CRYPT_OID_FUNC_ENTRY const * const,ulong)

- ea: `0x180027f90`
- end: `0x1800286d1`
- name: `?InstallOIDFunctionAddress@@YAHPEAUHINSTANCE__@@KPEAU_FUNC_SET@@KQEBU_CRYPT_OID_FUNC_ENTRY@@K@Z`
- size: `1857`
- prototype: `__int64 __fastcall(HINSTANCE hModule, unsigned int, struct _FUNC_SET *, unsigned int, const struct _CRYPT_OID_FUNC_ENTRY *const, signed int)`
- caller_count: `8`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180027d20`
- `0x180029624`
- `0x1800296c0`
- `0x18002b170`
- `0x18002b5c8`
- `0x1800545d0`
- `0x180089f30`
- `0x18008dc10`

## callees

- `0x180027f90`
- `0x180028834`
- `0x180046e10`
- `0x180086e4c`
- `0x1800bec20`
- `0x1800bf63c`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002869e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800286ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002869e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800286ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028267`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028267`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800285be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800285be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800285e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800285e6`

## pseudocode

```c
__int64 __fastcall InstallOIDFunctionAddress(
        HINSTANCE hModule,
        unsigned int a2,
        struct _FUNC_SET *a3,
        unsigned int a4,
        const struct _CRYPT_OID_FUNC_ENTRY *const a5,
        signed int a6)
{
  HMODULE v7; // r14
  int v9; // ebp
  __int64 *v10; // r8
  LPCSTR v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // r15d
  unsigned int v14; // ebx
  unsigned int v15; // edx
  unsigned int v16; // ebx
  const struct _CRYPT_OID_FUNC_ENTRY *v17; // rsi
  LPCSTR pszOID; // rdi
  LPCSTR v19; // rbp
  __int16 *v20; // rdi
  HMODULE Library; // rax
  __int16 *v22; // rcx
  unsigned int v23; // r15d
  __int64 *v24; // r14
  __int16 *v25; // rsi
  __int64 v26; // rdx
  const struct _CRYPT_OID_FUNC_ENTRY *v27; // r15
  LPCSTR v28; // rcx
  unsigned int i; // ecx
  __int64 v30; // rax
  __int64 *v31; // rax
  __int64 v32; // rax
  unsigned int v33; // r14d
  __int16 *v34; // rax
  __int64 *v35; // rdi
  __int64 v36; // rax
  __int16 *v37; // r8
  unsigned int v39; // edi
  __int64 v40; // rdx
  __int64 *v41; // r14
  __int16 *v42; // r15
  const struct _CRYPT_OID_FUNC_ENTRY *v43; // rbp
  LPCSTR v44; // rcx
  unsigned int j; // ecx
  __int64 v46; // rax
  unsigned int v47; // r15d
  __int16 *v48; // rbx
  const struct _CRYPT_OID_FUNC_ENTRY *v49; // rsi
  LPCSTR v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rax
  unsigned int v53; // ecx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  unsigned int v59; // [rsp+20h] [rbp-2E8h]
  unsigned int v60; // [rsp+20h] [rbp-2E8h]
  int v61; // [rsp+24h] [rbp-2E4h]
  unsigned int v62; // [rsp+28h] [rbp-2E0h]
  __int64 *v63; // [rsp+30h] [rbp-2D8h]
  __int64 *v65; // [rsp+48h] [rbp-2C0h]
  LPCSTR v66; // [rsp+50h] [rbp-2B8h]
  _BYTE v68[16]; // [rsp+60h] [rbp-2A8h] BYREF
  __int64 *v69; // [rsp+70h] [rbp-298h]
  __int64 *v70; // [rsp+78h] [rbp-290h]
  __int16 *v71; // [rsp+80h] [rbp-288h]
  __int16 *v72; // [rsp+88h] [rbp-280h]
  WCHAR Filename[264]; // [rsp+B0h] [rbp-258h] BYREF

  v7 = hModule;
  memset_0(v68, 0, 0x50u);
  v9 = -1;
  v10 = v69;
  v11 = 0;
  v12 = (unsigned __int16)a2;
  v13 = 0;
  v14 = HIWORD(a2);
  v15 = (unsigned int)a6 >> 31;
  v61 = -1;
  v59 = 0;
  if ( !v12 )
    v12 = v14;
  v66 = 0;
  v62 = v12;
  v16 = 0;
  v63 = v70;
  v65 = v69;
  while ( v16 < a4 )
  {
    v17 = &a5[v16];
    pszOID = v17->pszOID;
    if ( v17->pszOID <= (LPCSTR)0xFFFF )
    {
      if ( v9 >= 0 )
      {
        if ( pszOID == v11 + 1 )
          goto LABEL_28;
        v23 = v13 - v9 + 1;
        v60 = v23;
        if ( v23 > 0xFFFF )
          goto LABEL_85;
        if ( (_BYTE)v15
          && (++dword_18015D5CC, dword_18015D5C4 += v23, (unsigned int)dword_18015D5D0 < 0x37)
          && dword_18015D5C8 + v23 <= 0xEA )
        {
          v24 = &qword_180159500[6 * (unsigned int)dword_18015D5D0++];
          v25 = &_ImageBase[4 * dword_18015D5C8 + 708520];
          v26 = v23 + dword_18015D5C8;
          dword_18015D5C8 += v23;
        }
        else
        {
          v58 = PkiZeroAlloc(8 * v23 + 48);
          v24 = (__int64 *)v58;
          if ( !v58 )
            goto LABEL_86;
          v25 = (__int16 *)(v58 + 48);
        }
        *((_DWORD *)v24 + 1) = v62;
        *(_DWORD *)v24 = 1;
        v24[1] = 0;
        v27 = &a5[v9];
        v28 = v27->pszOID;
        v24[2] = (__int64)v27->pszOID;
        v24[3] = (__int64)&v28[v60 - 1];
        v24[4] = DuplicateLibrary(hModule, v26, v10);
        v24[5] = (__int64)v25;
        for ( i = 0; i < v60; *((_QWORD *)v25 - 1) = v27[v30].pvFuncAddr )
        {
          v25 += 4;
          v30 = i++;
        }
        if ( v63 )
        {
          v63[1] = (__int64)v24;
        }
        else
        {
          v65 = v24;
          v69 = v24;
        }
        v31 = v24;
        v7 = hModule;
        v63 = v31;
        v70 = v31;
      }
      v61 = v16;
LABEL_28:
      v9 = v61;
      v13 = v16;
      LOBYTE(v15) = a6 < 0;
      v11 = pszOID;
      v59 = v16++;
      v66 = pszOID;
    }
    else
    {
      if ( v9 >= 0 )
      {
        v39 = v13 - v9 + 1;
        if ( v39 > 0xFFFF )
          goto LABEL_85;
        if ( (_BYTE)v15
          && (++dword_18015D5CC, dword_18015D5C4 += v39, (unsigned int)dword_18015D5D0 < 0x37)
          && v39 + dword_18015D5C8 <= 0xEA )
        {
          v40 = (unsigned int)(dword_18015D5D0 + 1);
          v41 = &qword_180159500[6 * (unsigned int)dword_18015D5D0++];
          v42 = &_ImageBase[4 * dword_18015D5C8 + 708520];
          dword_18015D5C8 += v39;
        }
        else
        {
          v56 = PkiZeroAlloc(8 * v39 + 48);
          v41 = (__int64 *)v56;
          if ( !v56 )
            goto LABEL_86;
          v42 = (__int16 *)(v56 + 48);
        }
        *((_DWORD *)v41 + 1) = v62;
        *(_DWORD *)v41 = 1;
        v41[1] = 0;
        v43 = &a5[v9];
        v44 = v43->pszOID;
        v41[2] = (__int64)v43->pszOID;
        v41[3] = (__int64)&v44[v39 - 1];
        v41[4] = DuplicateLibrary(hModule, v40, v10);
        v41[5] = (__int64)v42;
        for ( j = 0; j < v39; *((_QWORD *)v42 - 1) = v43[v46].pvFuncAddr )
        {
          v42 += 4;
          v46 = j++;
        }
        if ( v63 )
        {
          v63[1] = (__int64)v41;
        }
        else
        {
          v65 = v41;
          v69 = v41;
        }
        v13 = v59;
        LOBYTE(v15) = a6 < 0;
        v63 = v41;
        v70 = v41;
        v7 = hModule;
        v61 = -1;
      }
      if ( (_BYTE)v15 && (++dword_18015D5BC, (unsigned int)dword_18015D5C0 < 0xEE) )
      {
        v19 = v17->pszOID;
        v20 = &_ImageBase[20 * dword_18015D5C0++ + 709456];
      }
      else
      {
        if ( v17->pszOID )
        {
          v32 = -1;
          do
            ++v32;
          while ( v17->pszOID[v32] );
        }
        else
        {
          LODWORD(v32) = 0;
        }
        v33 = v32 + 1;
        v34 = (__int16 *)LocalAlloc(0x40u, (unsigned int)(v32 + 41));
        v20 = v34;
        if ( !v34 )
        {
          SetLastError(0x8007000E);
          goto LABEL_86;
        }
        v19 = (LPCSTR)(v34 + 20);
        memcpy_0(v34 + 20, v17->pszOID, v33);
        v7 = hModule;
      }
      *((_DWORD *)v20 + 1) = v62;
      *(_DWORD *)v20 = 2;
      *((_QWORD *)v20 + 1) = 0;
      *((_QWORD *)v20 + 2) = v19;
      if ( v7 )
      {
        if ( !GetModuleFileNameW(v7, Filename, 0x104u)
          || (Filename[260] = 0, (Library = LoadLibraryExW(Filename, 0, 0x11u)) == 0) )
        {
          Library = 0;
        }
      }
      else
      {
        Library = 0;
      }
      v22 = v72;
      *((_QWORD *)v20 + 3) = Library;
      *((_QWORD *)v20 + 4) = v17->pvFuncAddr;
      if ( v22 )
        *((_QWORD *)v22 + 1) = v20;
      else
        v71 = v20;
      v9 = v61;
      ++v16;
      v11 = v66;
      LOBYTE(v15) = a6 < 0;
      v72 = v20;
    }
  }
  if ( v9 < 0 )
  {
    v35 = v63;
    goto LABEL_36;
  }
  v47 = v13 - v9 + 1;
  if ( v47 > 0xFFFF )
  {
LABEL_85:
    SetLastError(0x216u);
    goto LABEL_86;
  }
  if ( (_BYTE)v15 )
  {
    ++dword_18015D5CC;
    dword_18015D5C4 += v47;
    if ( (unsigned int)dword_18015D5D0 < 0x37 && v47 + dword_18015D5C8 <= 0xEA )
    {
      v35 = &qword_180159500[6 * (unsigned int)dword_18015D5D0++];
      v48 = &_ImageBase[4 * dword_18015D5C8 + 708520];
      dword_18015D5C8 += v47;
LABEL_57:
      *((_DWORD *)v35 + 1) = v62;
      *(_DWORD *)v35 = 1;
      v35[1] = 0;
      v49 = &a5[v9];
      v50 = v49->pszOID;
      v35[2] = (__int64)v49->pszOID;
      v51 = (__int64)&v50[v47 - 1];
      v35[3] = v51;
      v52 = DuplicateLibrary(v7, v51, v10);
      v53 = 0;
      v35[4] = v52;
      for ( v35[5] = (__int64)v48; v53 < v47; *((_QWORD *)v48 - 1) = v49[v54].pvFuncAddr )
      {
        v48 += 4;
        v54 = v53++;
      }
      if ( v63 )
        v63[1] = (__int64)v35;
      else
        v65 = v35;
LABEL_36:
      EnterCriticalSection(&CriticalSection);
      if ( v65 )
      {
        v36 = *((_QWORD *)a3 + 2);
        if ( !v36 )
        {
          *((_QWORD *)a3 + 2) = v65;
          goto LABEL_39;
        }
        if ( (a6 & 1) != 0 )
        {
          v35[1] = v36;
          *((_QWORD *)a3 + 2) = v65;
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)a3 + 3) + 8LL) = v65;
LABEL_39:
          *((_QWORD *)a3 + 3) = v35;
        }
      }
      v37 = v71;
      if ( v71 )
      {
        v55 = *((_QWORD *)a3 + 4);
        if ( v55 )
        {
          if ( (a6 & 1) != 0 )
          {
            *((_QWORD *)v72 + 1) = v55;
            *((_QWORD *)a3 + 4) = v37;
            goto LABEL_41;
          }
          *(_QWORD *)(*((_QWORD *)a3 + 5) + 8LL) = v71;
        }
        else
        {
          *((_QWORD *)a3 + 4) = v71;
        }
        *((_QWORD *)a3 + 5) = v72;
      }
LABEL_41:
      LeaveCriticalSection(&CriticalSection);
      return 1;
    }
  }
  v57 = PkiZeroAlloc(8 * v47 + 48);
  v35 = (__int64 *)v57;
  if ( v57 )
  {
    v48 = (__int16 *)(v57 + 48);
    goto LABEL_57;
  }
LABEL_86:
  FreeFuncSetConstAndStrElements((struct _FUNC_SET *)v68);
  return 0;
}

```

## disassembly

```asm
0x180027f90  mov     [rsp+arg_8], rbx
0x180027f95  push    rbp
0x180027f96  push    rsi
0x180027f97  push    rdi
0x180027f98  push    r12
0x180027f9a  push    r13
0x180027f9c  push    r14
0x180027f9e  push    r15
0x180027fa0  sub     rsp, 2D0h
0x180027fa7  mov     rax, cs:__security_cookie
0x180027fae  xor     rax, rsp
0x180027fb1  mov     [rsp+308h+var_48], rax
0x180027fb9  mov     r13, [rsp+308h+arg_20]
0x180027fc1  mov     ebx, edx
0x180027fc3  mov     [rsp+308h+var_2B0], r8
0x180027fc8  mov     r14, rcx
0x180027fcb  mov     [rsp+308h+var_2C8], rcx
0x180027fd0  xor     edx, edx; Val
0x180027fd2  mov     r8d, 50h ; 'P'; Size
0x180027fd8  lea     rcx, [rsp+308h+var_2A8]; void *
0x180027fdd  mov     r12d, r9d
0x180027fe0  call    memset_0
0x180027fe5  mov     edx, [rsp+308h+arg_28]
0x180027fec  xor     r9d, r9d
0x180027fef  mov     rdi, [rsp+308h+var_290]
0x180027ff4  mov     ebp, 0FFFFFFFFh
0x180027ff9  mov     r8, [rsp+308h+var_298]
0x180027ffe  mov     ecx, r9d
0x180028001  movzx   eax, bx
0x180028004  mov     r15d, r9d
0x180028007  shr     ebx, 10h
0x18002800a  shr     edx, 1Fh
0x18002800d  test    eax, eax
0x18002800f  mov     [rsp+308h+var_2E4], ebp
0x180028013  mov     [rsp+308h+var_2E8], r9d
0x180028018  cmovz   eax, ebx
0x18002801b  mov     [rsp+308h+var_2B8], rcx
0x180028020  mov     [rsp+308h+var_2E0], eax
0x180028024  mov     ebx, r9d
0x180028027  mov     [rsp+308h+var_2D0], edx
0x18002802b  mov     [rsp+308h+var_2D8], rdi
0x180028030  mov     [rsp+308h+var_2C0], r8
0x180028035  lea     r10, __ImageBase
0x18002803c  lea     r11, qword_180159500
0x180028043  cmp     ebx, r12d
0x180028046  jnb     loc_180028298
0x18002804c  mov     esi, ebx
0x18002804e  shl     rsi, 4
0x180028052  add     rsi, r13
0x180028055  mov     rdi, [rsi]
0x180028058  cmp     rdi, 0FFFFh
0x18002805f  jbe     loc_180028102
0x180028065  test    ebp, ebp
0x180028067  jns     loc_180028324
0x18002806d  test    dl, dl
0x18002806f  jz      loc_18002823E
0x180028075  inc     cs:dword_18015D5BC
0x18002807b  mov     eax, cs:dword_18015D5C0
0x180028081  cmp     eax, 0EEh
0x180028086  jnb     loc_18002823E
0x18002808c  mov     rbp, [rsi]
0x18002808f  lea     rcx, [rax+rax*4]
0x180028093  lea     rdi, ds:15A6A0h[rcx*8]
0x18002809b  add     rdi, r10
0x18002809e  inc     cs:dword_18015D5C0
0x1800280a4  mov     eax, [rsp+308h+var_2E0]
0x1800280a8  mov     [rdi+4], eax
0x1800280ab  mov     dword ptr [rdi], 2
0x1800280b1  mov     [rdi+8], r9
0x1800280b5  mov     [rdi+10h], rbp
0x1800280b9  test    r14, r14
0x1800280bc  jnz     loc_1800285AD
0x1800280c2  mov     rax, r14
0x1800280c5  mov     rcx, [rsp+308h+var_280]
0x1800280cd  mov     [rdi+18h], rax
0x1800280d1  mov     rax, [rsi+8]
0x1800280d5  mov     [rdi+20h], rax
0x1800280d9  test    rcx, rcx
0x1800280dc  jz      loc_18002852C
0x1800280e2  mov     [rcx+8], rdi
0x1800280e6  mov     ebp, [rsp+308h+var_2E4]
0x1800280ea  inc     ebx
0x1800280ec  mov     rcx, [rsp+308h+var_2B8]
0x1800280f1  mov     edx, [rsp+308h+var_2D0]
0x1800280f5  mov     [rsp+308h+var_280], rdi
0x1800280fd  jmp     loc_180028035
0x180028102  test    ebp, ebp
0x180028104  js      loc_18002821C
0x18002810a  lea     rax, [rcx+1]
0x18002810e  cmp     rdi, rax
0x180028111  jz      loc_180028220
0x180028117  sub     r15d, ebp
0x18002811a  inc     r15d
0x18002811d  mov     [rsp+308h+var_2E8], r15d
0x180028122  cmp     r15d, 0FFFFh
0x180028129  ja      loc_1800286A6
0x18002812f  test    dl, dl
0x180028131  jz      loc_180028622
0x180028137  inc     cs:dword_18015D5CC
0x18002813d  add     cs:dword_18015D5C4, r15d
0x180028144  mov     ecx, cs:dword_18015D5D0
0x18002814a  cmp     ecx, 37h ; '7'
0x18002814d  jnb     loc_180028622
0x180028153  mov     edx, cs:dword_18015D5C8
0x180028159  lea     eax, [rdx+r15]
0x18002815d  cmp     eax, 0EAh
0x180028162  ja      loc_180028622
0x180028168  lea     r14, [rcx+rcx*2]
0x18002816c  inc     ecx
0x18002816e  shl     r14, 4
0x180028172  lea     rsi, ds:159F50h[rdx*8]
0x18002817a  add     r14, r11
0x18002817d  mov     cs:dword_18015D5D0, ecx
0x180028183  add     rsi, r10
0x180028186  add     edx, r15d
0x180028189  mov     cs:dword_18015D5C8, edx
0x18002818f  mov     eax, [rsp+308h+var_2E0]
0x180028193  mov     [r14+4], eax
0x180028197  movsxd  r15, ebp
0x18002819a  mov     ebp, [rsp+308h+var_2E8]
0x18002819e  mov     dword ptr [r14], 1
0x1800281a5  mov     [r14+8], r9
0x1800281a9  shl     r15, 4
0x1800281ad  lea     rax, [rbp-1]
0x1800281b1  add     r15, r13
0x1800281b4  mov     rcx, [r15]
0x1800281b7  mov     [r14+10h], rcx
0x1800281bb  add     rcx, rax
0x1800281be  mov     [r14+18h], rcx
0x1800281c2  mov     rcx, [rsp+308h+var_2C8]
0x1800281c7  call    DuplicateLibrary
0x1800281cc  xor     r9d, r9d
0x1800281cf  mov     [r14+20h], rax
0x1800281d3  mov     [r14+28h], rsi
0x1800281d7  mov     ecx, r9d
0x1800281da  test    ebp, ebp
0x1800281dc  jz      short loc_1800281F8
0x1800281de  xchg    ax, ax
0x1800281e0  mov     eax, ecx
0x1800281e2  lea     rsi, [rsi+8]
0x1800281e6  add     rax, rax
0x1800281e9  inc     ecx
0x1800281eb  mov     rax, [r15+rax*8+8]
0x1800281f0  mov     [rsi-8], rax
0x1800281f4  cmp     ecx, ebp
0x1800281f6  jb      short loc_1800281E0
0x1800281f8  mov     rax, [rsp+308h+var_2D8]
0x1800281fd  test    rax, rax
0x180028200  jz      loc_18002859B
0x180028206  mov     [rax+8], r14
0x18002820a  mov     rax, r14
0x18002820d  mov     r14, [rsp+308h+var_2C8]
0x180028212  mov     [rsp+308h+var_2D8], rax
0x180028217  mov     [rsp+308h+var_290], rax
0x18002821c  mov     [rsp+308h+var_2E4], ebx
0x180028220  mov     ebp, [rsp+308h+var_2E4]
0x180028224  mov     r15d, ebx
0x180028227  mov     edx, [rsp+308h+var_2D0]
0x18002822b  mov     rcx, rdi
0x18002822e  mov     [rsp+308h+var_2E8], ebx
0x180028232  inc     ebx
0x180028234  mov     [rsp+308h+var_2B8], rdi
0x180028239  jmp     loc_180028035
0x18002823e  mov     rcx, [rsi]
0x180028241  test    rcx, rcx
0x180028244  jz      loc_180028686
0x18002824a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028251  inc     rax
0x180028254  cmp     byte ptr [rcx+rax], 0
0x180028258  jnz     short loc_180028251
0x18002825a  lea     r14d, [rax+1]
0x18002825e  mov     ecx, 40h ; '@'; uFlags
0x180028263  lea     edx, [r14+28h]; uBytes
0x180028267  call    cs:__imp_LocalAlloc
0x18002826d  mov     rdi, rax
0x180028270  test    rax, rax
0x180028273  jz      loc_180028699
0x180028279  mov     rdx, [rsi]; Src
0x18002827c  lea     rbp, [rax+28h]
0x180028280  mov     rcx, rbp; void *
0x180028283  mov     r8d, r14d; Size
0x180028286  call    memcpy_0
0x18002828b  mov     r14, [rsp+308h+var_2C8]
0x180028290  xor     r9d, r9d
0x180028293  jmp     loc_1800280A4
0x180028298  test    ebp, ebp
0x18002829a  jns     loc_180028446
0x1800282a0  mov     rdi, [rsp+308h+var_2D8]
0x1800282a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800282ac  call    cs:__imp_EnterCriticalSection
0x1800282b2  mov     rcx, [rsp+308h+var_2C0]
0x1800282b7  mov     rsi, [rsp+308h+var_2B0]
0x1800282bc  test    rcx, rcx
0x1800282bf  jz      short loc_1800282D6
0x1800282c1  mov     rax, [rsi+10h]
0x1800282c5  test    rax, rax
0x1800282c8  jnz     loc_180028643
0x1800282ce  mov     [rsi+10h], rcx
0x1800282d2  mov     [rsi+18h], rdi
0x1800282d6  mov     r8, [rsp+308h+var_288]
0x1800282de  test    r8, r8
0x1800282e1  jnz     loc_18002854B
0x1800282e7  lea     rcx, CriticalSection; lpCriticalSection
0x1800282ee  call    cs:__imp_LeaveCriticalSection
0x1800282f4  mov     eax, 1
0x1800282f9  mov     rcx, [rsp+308h+var_48]
0x180028301  xor     rcx, rsp; StackCookie
0x180028304  call    __security_check_cookie
0x180028309  mov     rbx, [rsp+308h+arg_8]
0x180028311  add     rsp, 2D0h
0x180028318  pop     r15
0x18002831a  pop     r14
0x18002831c  pop     r13
0x18002831e  pop     r12
0x180028320  pop     rdi
0x180028321  pop     rsi
0x180028322  pop     rbp
0x180028323  retn
0x180028324  mov     edi, r15d
0x180028327  sub     edi, ebp
0x180028329  inc     edi
0x18002832b  cmp     edi, 0FFFFh
0x180028331  ja      loc_1800286A6
0x180028337  test    dl, dl
0x180028339  jz      loc_180028577
0x18002833f  inc     cs:dword_18015D5CC
0x180028345  add     cs:dword_18015D5C4, edi
0x18002834b  mov     edx, cs:dword_18015D5D0
0x180028351  cmp     edx, 37h ; '7'
0x180028354  jnb     loc_180028577
0x18002835a  mov     ecx, cs:dword_18015D5C8
0x180028360  lea     eax, [rdi+rcx]
0x180028363  cmp     eax, 0EAh
0x180028368  ja      loc_180028577
0x18002836e  lea     r14, [rdx+rdx*2]
0x180028372  inc     edx
0x180028374  shl     r14, 4
0x180028378  lea     r15, ds:159F50h[rcx*8]
0x180028380  add     r14, r11
0x180028383  mov     cs:dword_18015D5D0, edx
0x180028389  add     r15, r10
0x18002838c  add     ecx, edi
0x18002838e  mov     cs:dword_18015D5C8, ecx
0x180028394  mov     eax, [rsp+308h+var_2E0]
0x180028398  mov     [r14+4], eax
0x18002839c  movsxd  rbp, ebp
0x18002839f  mov     dword ptr [r14], 1
0x1800283a6  mov     [r14+8], r9
0x1800283aa  shl     rbp, 4
0x1800283ae  add     rbp, r13
0x1800283b1  mov     eax, edi
0x1800283b3  dec     rax
0x1800283b6  mov     rcx, [rbp+0]
0x1800283ba  mov     [r14+10h], rcx
0x1800283be  add     rcx, rax
0x1800283c1  mov     [r14+18h], rcx
0x1800283c5  mov     rcx, [rsp+308h+var_2C8]
0x1800283ca  call    DuplicateLibrary
0x1800283cf  xor     r9d, r9d
0x1800283d2  mov     [r14+20h], rax
0x1800283d6  mov     [r14+28h], r15
0x1800283da  mov     ecx, r9d
0x1800283dd  test    edi, edi
0x1800283df  jz      short loc_180028408
0x1800283e1  nop     dword ptr [rax+00h]
0x1800283e5  nop     word ptr [rax+rax+00000000h]
0x1800283f0  mov     eax, ecx
0x1800283f2  lea     r15, [r15+8]
0x1800283f6  add     rax, rax
0x1800283f9  inc     ecx
0x1800283fb  mov     rax, [rbp+rax*8+8]
0x180028400  mov     [r15-8], rax
0x180028404  cmp     ecx, edi
0x180028406  jb      short loc_1800283F0
0x180028408  mov     rax, [rsp+308h+var_2D8]
0x18002840d  test    rax, rax
0x180028410  jz      loc_180028539
0x180028416  mov     [rax+8], r14
0x18002841a  mov     r15d, [rsp+308h+var_2E8]
0x18002841f  lea     r10, __ImageBase
0x180028426  mov     edx, [rsp+308h+var_2D0]
0x18002842a  mov     [rsp+308h+var_2D8], r14
0x18002842f  mov     [rsp+308h+var_290], r14
0x180028434  mov     r14, [rsp+308h+var_2C8]
0x180028439  mov     [rsp+308h+var_2E4], 0FFFFFFFFh
0x180028441  jmp     loc_18002806D
0x180028446  sub     r15d, ebp
0x180028449  inc     r15d
0x18002844c  cmp     r15d, 0FFFFh
0x180028453  ja      loc_1800286A6
0x180028459  test    dl, dl
0x18002845b  jz      loc_1800285FD
0x180028461  inc     cs:dword_18015D5CC
0x180028467  add     cs:dword_18015D5C4, r15d
0x18002846e  mov     ecx, cs:dword_18015D5D0
0x180028474  cmp     ecx, 37h ; '7'
0x180028477  jnb     loc_1800285FD
0x18002847d  mov     edx, cs:dword_18015D5C8
0x180028483  lea     eax, [r15+rdx]
0x180028487  cmp     eax, 0EAh
  ... truncated ...
```
