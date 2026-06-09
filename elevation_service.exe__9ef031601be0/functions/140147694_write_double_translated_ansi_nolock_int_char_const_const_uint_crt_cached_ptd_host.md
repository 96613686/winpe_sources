# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x140147694`
- end: `0x140147b27`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(__int64, int, _BYTE *, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x140147244`

## callees

- `0x14012fc90`
- `0x140132a90`
- `0x140142b84`
- `0x140147694`
- `0x140148a30`
- `0x1401577ec`
- `0x140161030`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x140147713`
- `KERNEL32!GetConsoleOutputCP` at `0x140147713`
- `KERNEL32!GetLastError` at `0x140147af5`
- `KERNEL32!GetLastError` at `0x140147af5`
- `KERNEL32!WriteFile` at `0x1401479f0`
- `KERNEL32!WriteFile` at `0x140147a36`
- `KERNEL32!WriteFile` at `0x1401479f0`
- `KERNEL32!WriteFile` at `0x140147a36`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(
        __int64 a1,
        int a2,
        _BYTE *a3,
        int a4,
        __crt_cached_ptd_host *a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  __crt_cached_ptd_host *v12; // r10
  int v13; // ecx
  __int64 v14; // r11
  int v15; // edx
  int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // r8
  signed __int64 v22; // r9
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r9
  int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  _BYTE *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r10
  __int16 v41[2]; // [rsp+48h] [rbp-71h] BYREF
  int v42; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-61h]
  __crt_cached_ptd_host *v45; // [rsp+60h] [rbp-59h]
  __int64 v46; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v48; // [rsp+74h] [rbp-45h]
  _BYTE *v49; // [rsp+78h] [rbp-41h]
  __int64 v50; // [rsp+80h] [rbp-39h]
  __int64 v51; // [rsp+88h] [rbp-31h] BYREF
  _BYTE *v52; // [rsp+90h] [rbp-29h] BYREF
  _BYTE *v53; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v55; // [rsp+A8h] [rbp-11h]
  __int64 v56; // [rsp+B0h] [rbp-9h]
  _BYTE v57[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v58[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v56 = -2;
  v5 = a3;
  v49 = a3;
  v6 = a2;
  v45 = a5;
  v8 = (__int64)a2 >> 6;
  v50 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(qword_14038C5D0[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v44 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = a5;
  if ( !*((_BYTE *)a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(v45);
    v12 = v45;
  }
  v13 = *(_DWORD *)(*((_QWORD *)v12 + 3) + 12LL);
  v48 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v49 < v10 )
  {
    v14 = v6 >> 6;
    v55 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v41[0]) = *v5;
      v42 = 0;
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(qword_14038C5D0[v14] + 8 * v9 + 62);
        do
        {
          if ( !*v19 )
            break;
          ++v17;
          ++v18;
          ++v19;
        }
        while ( v18 < 5 );
        if ( v18 <= 0 )
        {
          v26 = *((char *)qword_14037A370 + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_14038C5D0[v39] + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v46 = 0;
          v53 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( sub_140148A30((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)qword_14037A370 + *(unsigned __int8 *)(qword_14038C5D0[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v46) = v20 - v17;
          v21 = v44 - (_QWORD)v5;
          v22 = v20 - v17;
          if ( v22 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + 8 * v9 + qword_14038C5D0[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_14038C5D0[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memcpy(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_14038C5D0[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_140148A30((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_14038C5D0[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v58[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v58[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = v58;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**((_QWORD **)v12 + 3) + 2 * v33) >= 0 )
        {
          v31 = 1;
          v32 = v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal(&v42, v32, v31, v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v44 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(qword_14038C5D0[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(&v42, v5, 2, v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v42, v16, (unsigned int)Buffer, 5, 0, 0);
      v35 = v34;
      if ( !v34 )
        return a1;
      NumberOfBytesWritten = 0;
      v36 = hFile;
      if ( !WriteFile(hFile, Buffer, v34, &NumberOfBytesWritten, 0) )
      {
LABEL_48:
        *(_DWORD *)a1 = GetLastError();
        return a1;
      }
      v15 = (_DWORD)v5 + *(_DWORD *)(a1 + 8) - (_DWORD)v49;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v41[0]) == 10 )
      {
        v41[0] = 13;
        if ( !WriteFile(v36, v41, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v44 )
        return a1;
      v12 = v45;
      v14 = v55;
      v13 = v48;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140147694  mov     rax, rsp
0x140147697  push    rbp
0x140147698  push    rsi
0x140147699  push    rdi
0x14014769a  push    r12
0x14014769c  push    r13
0x14014769e  push    r14
0x1401476a0  push    r15
0x1401476a2  lea     rbp, [rax-57h]
0x1401476a6  sub     rsp, 0D0h
0x1401476ad  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x1401476b5  mov     [rax+8], rbx
0x1401476b9  mov     rax, cs:__security_cookie
0x1401476c0  xor     rax, rsp
0x1401476c3  mov     [rbp+4Fh+var_38], rax
0x1401476c7  mov     rsi, r8
0x1401476ca  mov     [rbp+4Fh+var_90], r8
0x1401476ce  movsxd  r14, edx
0x1401476d1  mov     rbx, rcx
0x1401476d4  mov     rax, [rbp+4Fh+arg_20]
0x1401476d8  mov     [rbp+4Fh+var_A8], rax
0x1401476dc  mov     rax, r14
0x1401476df  mov     r13, r14
0x1401476e2  sar     r13, 6
0x1401476e6  mov     [rbp+4Fh+var_88], r13
0x1401476ea  lea     rcx, __ImageBase
0x1401476f1  and     eax, 3Fh
0x1401476f4  lea     r15, [rax+rax*8]
0x1401476f8  mov     rax, rva qword_14038C5D0[rcx+r13*8]
0x140147700  mov     rax, [rax+r15*8+28h]
0x140147705  mov     [rbp+4Fh+hFile], rax
0x140147709  mov     r12d, r9d
0x14014770c  add     r12, r8
0x14014770f  mov     [rbp+4Fh+var_B0], r12
0x140147713  call    cs:GetConsoleOutputCP
0x140147719  mov     [rbp+4Fh+var_98], eax
0x14014771c  xor     edi, edi
0x14014771e  mov     r10, [rbp+4Fh+var_A8]
0x140147722  cmp     [r10+28h], dil
0x140147726  jnz     short loc_140147734
0x140147728  mov     rcx, r10; this
0x14014772b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140147730  mov     r10, [rbp+4Fh+var_A8]
0x140147734  mov     rcx, [r10+18h]
0x140147738  mov     ecx, [rcx+0Ch]
0x14014773b  mov     [rbp+4Fh+var_94], ecx
0x14014773e  xor     eax, eax
0x140147740  mov     [rbx], rax
0x140147743  mov     [rbx+8], eax
0x140147746  cmp     [rbp+4Fh+var_90], r12
0x14014774a  jnb     loc_140147AFD
0x140147750  mov     r11, r14
0x140147753  sar     r11, 6
0x140147757  mov     [rbp+4Fh+var_60], r11
0x14014775b  mov     edx, edi
0x14014775d  mov     al, [rsi]
0x14014775f  mov     byte ptr [rbp+4Fh+var_C0], al
0x140147762  mov     [rbp+4Fh+var_BC], edi
0x140147765  mov     r12d, 1
0x14014776b  cmp     ecx, 0FDE9h
0x140147771  jnz     loc_140147904
0x140147777  mov     edx, edi
0x140147779  mov     r14, rdi
0x14014777c  lea     r12, __ImageBase
0x140147783  lea     rcx, ds:3Eh[r15*8]
0x14014778b  add     rcx, rva qword_14038C5D0[r12+r11*8]
0x140147793  cmp     [rcx], dil
0x140147796  jz      short loc_1401477A6
0x140147798  inc     edx
0x14014779a  inc     r14
0x14014779d  inc     rcx
0x1401477a0  cmp     r14, 5
0x1401477a4  jl      short loc_140147793
0x1401477a6  test    r14, r14
0x1401477a9  jle     loc_14014789A
0x1401477af  mov     rax, rva qword_14038C5D0[r12+r13*8]
0x1401477b7  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x1401477bd  movsx   r12d, byte ptr [rcx+r12+37A370h]
0x1401477c6  inc     r12d
0x1401477c9  mov     eax, r12d
0x1401477cc  sub     eax, edx
0x1401477ce  mov     dword ptr [rbp+4Fh+var_A0], eax
0x1401477d1  mov     r8, [rbp+4Fh+var_B0]
0x1401477d5  sub     r8, rsi
0x1401477d8  movsxd  r9, eax
0x1401477db  cmp     r9, r8
0x1401477de  jg      loc_140147A71
0x1401477e4  mov     rcx, rdi
0x1401477e7  lea     r8, __ImageBase
0x1401477ee  lea     rdx, ds:3Eh[r15*8]
0x1401477f6  add     rdx, rva qword_14038C5D0[r8+r11*8]
0x1401477fe  mov     al, [rdx]
0x140147800  mov     [rbp+rcx+4Fh+var_50], al
0x140147804  inc     rcx
0x140147807  inc     rdx
0x14014780a  cmp     rcx, r14
0x14014780d  jl      short loc_1401477FE
0x14014780f  test    r9, r9
0x140147812  jle     short loc_140147831
0x140147814  lea     rcx, [rbp+4Fh+var_50]
0x140147818  add     rcx, r14; Dst
0x14014781b  mov     r8, r9; MaxCount
0x14014781e  mov     rdx, rsi; Src
0x140147821  call    memcpy
0x140147826  mov     r10, [rbp+4Fh+var_A8]
0x14014782a  lea     r8, __ImageBase
0x140147831  mov     rdx, rdi
0x140147834  lea     rcx, [rdx+r15*8]
0x140147838  mov     rax, rva qword_14038C5D0[r8+r13*8]
0x140147840  mov     [rcx+rax+3Eh], dil
0x140147845  inc     rdx
0x140147848  cmp     rdx, r14
0x14014784b  jl      short loc_140147834
0x14014784d  mov     [rbp+4Fh+var_80], rdi
0x140147851  lea     rax, [rbp+4Fh+var_50]
0x140147855  mov     [rbp+4Fh+var_78], rax
0x140147859  mov     eax, edi
0x14014785b  cmp     r12d, 4
0x14014785f  setz    al
0x140147862  inc     eax
0x140147864  mov     r12d, eax
0x140147867  mov     r8d, eax
0x14014786a  mov     [rsp+100h+lpOverlapped], r10
0x14014786f  lea     r9, [rbp+4Fh+var_80]
0x140147873  lea     rdx, [rbp+4Fh+var_78]
0x140147877  lea     rcx, [rbp+4Fh+var_BC]
0x14014787b  call    sub_140148A30
0x140147880  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140147884  jz      loc_140147AFD
0x14014788a  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x14014788d  dec     eax
0x14014788f  movsxd  rcx, eax
0x140147892  add     rsi, rcx
0x140147895  jmp     loc_14014799C
0x14014789a  movzx   eax, byte ptr [rsi]
0x14014789d  movsx   r13, byte ptr [rax+r12+37A370h]
0x1401478a6  lea     ecx, [r13+1]
0x1401478aa  mov     r9, [rbp+4Fh+var_B0]
0x1401478ae  sub     r9, rsi
0x1401478b1  movsxd  rax, ecx
0x1401478b4  cmp     rax, r9
0x1401478b7  jg      loc_140147AA7
0x1401478bd  mov     [rbp+4Fh+var_A0], rdi
0x1401478c1  mov     [rbp+4Fh+var_70], rsi
0x1401478c5  mov     eax, edi
0x1401478c7  cmp     ecx, 4
0x1401478ca  setz    al
0x1401478cd  inc     eax
0x1401478cf  mov     r14d, eax
0x1401478d2  mov     r8d, eax
0x1401478d5  mov     [rsp+100h+lpOverlapped], r10
0x1401478da  lea     r9, [rbp+4Fh+var_A0]
0x1401478de  lea     rdx, [rbp+4Fh+var_70]
0x1401478e2  lea     rcx, [rbp+4Fh+var_BC]
0x1401478e6  call    sub_140148A30
0x1401478eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401478ef  jz      loc_140147AFD
0x1401478f5  add     rsi, r13
0x1401478f8  mov     r12d, r14d
0x1401478fb  mov     r13, [rbp+4Fh+var_88]
0x1401478ff  jmp     loc_14014799C
0x140147904  lea     r11, __ImageBase
0x14014790b  mov     r8, rva qword_14038C5D0[r11+r13*8]
0x140147913  mov     cl, [r8+r15*8+3Dh]
0x140147918  test    cl, 4
0x14014791b  jz      short loc_14014793E
0x14014791d  mov     al, [r8+r15*8+3Eh]
0x140147922  mov     [rbp+4Fh+var_48], al
0x140147925  mov     al, [rsi]
0x140147927  mov     [rbp+4Fh+var_47], al
0x14014792a  and     cl, 0FBh
0x14014792d  mov     [r8+r15*8+3Dh], cl
0x140147932  mov     r8d, 2
0x140147938  lea     rdx, [rbp+4Fh+var_48]
0x14014793c  jmp     short loc_140147987
0x14014793e  movzx   r9d, byte ptr [rsi]
0x140147942  mov     rax, [r10+18h]
0x140147946  mov     rcx, [rax]
0x140147949  cmp     [rcx+r9*2], di
0x14014794e  jge     short loc_140147981
0x140147950  lea     r14, [rsi+1]
0x140147954  cmp     r14, [rbp+4Fh+var_B0]
0x140147958  jnb     loc_140147ADA
0x14014795e  mov     r9, r10
0x140147961  mov     r8d, 2
0x140147967  mov     rdx, rsi
0x14014796a  lea     rcx, [rbp+4Fh+var_BC]
0x14014796e  call    _mbtowc_internal
0x140147973  cmp     eax, 0FFFFFFFFh
0x140147976  jz      loc_140147AFD
0x14014797c  mov     rsi, r14
0x14014797f  jmp     short loc_14014799C
0x140147981  mov     r8, r12
0x140147984  mov     rdx, rsi
0x140147987  mov     r9, r10
0x14014798a  lea     rcx, [rbp+4Fh+var_BC]
0x14014798e  call    _mbtowc_internal
0x140147993  cmp     eax, 0FFFFFFFFh
0x140147996  jz      loc_140147AFD
0x14014799c  inc     rsi
0x14014799f  mov     [rsp+38h], rdi
0x1401479a4  mov     [rsp+100h+var_D0], rdi
0x1401479a9  mov     dword ptr [rsp+100h+var_D8], 5
0x1401479b1  lea     rax, [rbp+4Fh+Buffer]
0x1401479b5  mov     [rsp+100h+lpOverlapped], rax
0x1401479ba  mov     r9d, r12d
0x1401479bd  lea     r8, [rbp+4Fh+var_BC]
0x1401479c1  xor     edx, edx
0x1401479c3  mov     ecx, [rbp+4Fh+var_98]
0x1401479c6  call    __acrt_WideCharToMultiByte
0x1401479cb  mov     r14d, eax
0x1401479ce  test    eax, eax
0x1401479d0  jz      loc_140147AFD
0x1401479d6  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x1401479d9  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1401479de  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1401479e2  mov     r8d, eax; nNumberOfBytesToWrite
0x1401479e5  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x1401479e9  mov     r12, [rbp+4Fh+hFile]
0x1401479ed  mov     rcx, r12; hFile
0x1401479f0  call    cs:WriteFile
0x1401479f6  test    eax, eax
0x1401479f8  jz      loc_140147AF5
0x1401479fe  mov     edx, [rbx+8]
0x140147a01  sub     edx, dword ptr [rbp+4Fh+var_90]
0x140147a04  add     edx, esi
0x140147a06  mov     [rbx+4], edx
0x140147a09  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x140147a0d  jb      loc_140147AFD
0x140147a13  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x140147a17  jnz     short loc_140147A57
0x140147a19  mov     eax, 0Dh
0x140147a1e  mov     [rbp+4Fh+var_C0], ax
0x140147a22  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140147a27  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140147a2b  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x140147a2f  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x140147a33  mov     rcx, r12; hFile
0x140147a36  call    cs:WriteFile
0x140147a3c  test    eax, eax
0x140147a3e  jz      loc_140147AF5
0x140147a44  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x140147a48  jb      loc_140147AFD
0x140147a4e  inc     dword ptr [rbx+8]
0x140147a51  inc     dword ptr [rbx+4]
0x140147a54  mov     edx, [rbx+4]
0x140147a57  cmp     rsi, [rbp+4Fh+var_B0]
0x140147a5b  jnb     loc_140147AFD
0x140147a61  mov     r10, [rbp+4Fh+var_A8]
0x140147a65  mov     r11, [rbp+4Fh+var_60]
0x140147a69  mov     ecx, [rbp+4Fh+var_94]
0x140147a6c  jmp     loc_14014775D
0x140147a71  test    r8, r8
0x140147a74  jle     short loc_140147AA1
0x140147a76  sub     rsi, r14
0x140147a79  lea     r9, __ImageBase
0x140147a80  lea     rdx, [r14+r15*8]
0x140147a84  mov     rcx, rva qword_14038C5D0[r9+r13*8]
0x140147a8c  mov     al, [rsi+r14]
0x140147a90  mov     [rdx+rcx+3Eh], al
0x140147a94  inc     edi
0x140147a96  inc     r14
0x140147a99  movsxd  rax, edi
0x140147a9c  cmp     rax, r8
0x140147a9f  jl      short loc_140147A80
0x140147aa1  add     [rbx+4], r8d
0x140147aa5  jmp     short loc_140147AFD
0x140147aa7  test    r9, r9
0x140147aaa  jle     short loc_140147AD4
0x140147aac  mov     r8, rdi
0x140147aaf  mov     r10, [rbp+4Fh+var_88]
0x140147ab3  lea     rdx, [r8+r15*8]
0x140147ab7  mov     rcx, rva qword_14038C5D0[r12+r10*8]
0x140147abf  mov     al, [r8+rsi]
0x140147ac3  mov     [rdx+rcx+3Eh], al
0x140147ac7  inc     edi
0x140147ac9  inc     r8
0x140147acc  movsxd  rax, edi
0x140147acf  cmp     rax, r9
0x140147ad2  jl      short loc_140147AB3
0x140147ad4  add     [rbx+4], r9d
0x140147ad8  jmp     short loc_140147AFD
0x140147ada  mov     [r8+r15*8+3Eh], r9b
0x140147adf  mov     rax, rva qword_14038C5D0[r11+r13*8]
0x140147ae7  or      byte ptr [rax+r15*8+3Dh], 4
0x140147aed  lea     eax, [rdx+1]
0x140147af0  mov     [rbx+4], eax
0x140147af3  jmp     short loc_140147AFD
0x140147af5  call    cs:__imp_GetLastError
0x140147afb  mov     [rbx], eax
0x140147afd  mov     rax, rbx
0x140147b00  mov     rcx, [rbp+4Fh+var_38]
0x140147b04  xor     rcx, rsp; StackCookie
0x140147b07  call    __security_check_cookie
0x140147b0c  mov     rbx, [rsp+100h+arg_0]
0x140147b14  add     rsp, 0D0h
0x140147b1b  pop     r15
0x140147b1d  pop     r14
0x140147b1f  pop     r13
0x140147b21  pop     r12
  ... truncated ...
```
