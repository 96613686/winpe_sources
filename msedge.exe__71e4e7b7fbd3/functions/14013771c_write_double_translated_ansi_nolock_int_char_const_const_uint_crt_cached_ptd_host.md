# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x14013771c`
- end: `0x140137baf`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: `struct _anonymous_namespace_::write_result __high(int, const char *const, unsigned int, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1401372cc`

## callees

- `0x14011fa70`
- `0x140122310`
- `0x140132ef8`
- `0x14013771c`
- `0x140138e8c`
- `0x140148214`
- `0x140152630`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x14013779b`
- `KERNEL32!GetConsoleOutputCP` at `0x14013779b`
- `KERNEL32!GetLastError` at `0x140137b7d`
- `KERNEL32!GetLastError` at `0x140137b7d`
- `KERNEL32!WriteFile` at `0x140137a78`
- `KERNEL32!WriteFile` at `0x140137abe`
- `KERNEL32!WriteFile` at `0x140137a78`
- `KERNEL32!WriteFile` at `0x140137abe`

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
  hFile = *(HANDLE *)(qword_14042C950[v8] + 72LL * (a2 & 0x3F) + 40);
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
        v19 = (_BYTE *)(qword_14042C950[v14] + 8 * v9 + 62);
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
          v26 = *((char *)qword_140419370 + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_14042C950[v39] + 62) = v5[v38];
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
          if ( sub_140138E8C((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)qword_140419370 + *(unsigned __int8 *)(qword_14042C950[v8] + 8 * v9 + 62)) + 1;
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
                *(_BYTE *)(v18 + 8 * v9 + qword_14042C950[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_14042C950[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memcpy(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_14042C950[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_140138E8C((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_14042C950[v8];
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
          *(_BYTE *)(qword_14042C950[v8] + 8 * v9 + 61) |= 4u;
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
0x14013771c  mov     rax, rsp
0x14013771f  push    rbp
0x140137720  push    rsi
0x140137721  push    rdi
0x140137722  push    r12
0x140137724  push    r13
0x140137726  push    r14
0x140137728  push    r15
0x14013772a  lea     rbp, [rax-57h]
0x14013772e  sub     rsp, 0D0h
0x140137735  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x14013773d  mov     [rax+8], rbx
0x140137741  mov     rax, cs:__security_cookie
0x140137748  xor     rax, rsp
0x14013774b  mov     [rbp+4Fh+var_38], rax
0x14013774f  mov     rsi, r8
0x140137752  mov     [rbp+4Fh+var_90], r8
0x140137756  movsxd  r14, edx
0x140137759  mov     rbx, rcx
0x14013775c  mov     rax, [rbp+4Fh+arg_20]
0x140137760  mov     [rbp+4Fh+var_A8], rax
0x140137764  mov     rax, r14
0x140137767  mov     r13, r14
0x14013776a  sar     r13, 6
0x14013776e  mov     [rbp+4Fh+var_88], r13
0x140137772  lea     rcx, __ImageBase
0x140137779  and     eax, 3Fh
0x14013777c  lea     r15, [rax+rax*8]
0x140137780  mov     rax, rva qword_14042C950[rcx+r13*8]
0x140137788  mov     rax, [rax+r15*8+28h]
0x14013778d  mov     [rbp+4Fh+hFile], rax
0x140137791  mov     r12d, r9d
0x140137794  add     r12, r8
0x140137797  mov     [rbp+4Fh+var_B0], r12
0x14013779b  call    cs:GetConsoleOutputCP
0x1401377a1  mov     [rbp+4Fh+var_98], eax
0x1401377a4  xor     edi, edi
0x1401377a6  mov     r10, [rbp+4Fh+var_A8]
0x1401377aa  cmp     [r10+28h], dil
0x1401377ae  jnz     short loc_1401377BC
0x1401377b0  mov     rcx, r10; this
0x1401377b3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1401377b8  mov     r10, [rbp+4Fh+var_A8]
0x1401377bc  mov     rcx, [r10+18h]
0x1401377c0  mov     ecx, [rcx+0Ch]
0x1401377c3  mov     [rbp+4Fh+var_94], ecx
0x1401377c6  xor     eax, eax
0x1401377c8  mov     [rbx], rax
0x1401377cb  mov     [rbx+8], eax
0x1401377ce  cmp     [rbp+4Fh+var_90], r12
0x1401377d2  jnb     loc_140137B85
0x1401377d8  mov     r11, r14
0x1401377db  sar     r11, 6
0x1401377df  mov     [rbp+4Fh+var_60], r11
0x1401377e3  mov     edx, edi
0x1401377e5  mov     al, [rsi]
0x1401377e7  mov     byte ptr [rbp+4Fh+var_C0], al
0x1401377ea  mov     [rbp+4Fh+var_BC], edi
0x1401377ed  mov     r12d, 1
0x1401377f3  cmp     ecx, 0FDE9h
0x1401377f9  jnz     loc_14013798C
0x1401377ff  mov     edx, edi
0x140137801  mov     r14, rdi
0x140137804  lea     r12, __ImageBase
0x14013780b  lea     rcx, ds:3Eh[r15*8]
0x140137813  add     rcx, rva qword_14042C950[r12+r11*8]
0x14013781b  cmp     [rcx], dil
0x14013781e  jz      short loc_14013782E
0x140137820  inc     edx
0x140137822  inc     r14
0x140137825  inc     rcx
0x140137828  cmp     r14, 5
0x14013782c  jl      short loc_14013781B
0x14013782e  test    r14, r14
0x140137831  jle     loc_140137922
0x140137837  mov     rax, rva qword_14042C950[r12+r13*8]
0x14013783f  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x140137845  movsx   r12d, byte ptr [rcx+r12+419370h]
0x14013784e  inc     r12d
0x140137851  mov     eax, r12d
0x140137854  sub     eax, edx
0x140137856  mov     dword ptr [rbp+4Fh+var_A0], eax
0x140137859  mov     r8, [rbp+4Fh+var_B0]
0x14013785d  sub     r8, rsi
0x140137860  movsxd  r9, eax
0x140137863  cmp     r9, r8
0x140137866  jg      loc_140137AF9
0x14013786c  mov     rcx, rdi
0x14013786f  lea     r8, __ImageBase
0x140137876  lea     rdx, ds:3Eh[r15*8]
0x14013787e  add     rdx, rva qword_14042C950[r8+r11*8]
0x140137886  mov     al, [rdx]
0x140137888  mov     [rbp+rcx+4Fh+var_50], al
0x14013788c  inc     rcx
0x14013788f  inc     rdx
0x140137892  cmp     rcx, r14
0x140137895  jl      short loc_140137886
0x140137897  test    r9, r9
0x14013789a  jle     short loc_1401378B9
0x14013789c  lea     rcx, [rbp+4Fh+var_50]
0x1401378a0  add     rcx, r14; Dst
0x1401378a3  mov     r8, r9; MaxCount
0x1401378a6  mov     rdx, rsi; Src
0x1401378a9  call    memcpy
0x1401378ae  mov     r10, [rbp+4Fh+var_A8]
0x1401378b2  lea     r8, __ImageBase
0x1401378b9  mov     rdx, rdi
0x1401378bc  lea     rcx, [rdx+r15*8]
0x1401378c0  mov     rax, rva qword_14042C950[r8+r13*8]
0x1401378c8  mov     [rcx+rax+3Eh], dil
0x1401378cd  inc     rdx
0x1401378d0  cmp     rdx, r14
0x1401378d3  jl      short loc_1401378BC
0x1401378d5  mov     [rbp+4Fh+var_80], rdi
0x1401378d9  lea     rax, [rbp+4Fh+var_50]
0x1401378dd  mov     [rbp+4Fh+var_78], rax
0x1401378e1  mov     eax, edi
0x1401378e3  cmp     r12d, 4
0x1401378e7  setz    al
0x1401378ea  inc     eax
0x1401378ec  mov     r12d, eax
0x1401378ef  mov     r8d, eax
0x1401378f2  mov     [rsp+100h+lpOverlapped], r10
0x1401378f7  lea     r9, [rbp+4Fh+var_80]
0x1401378fb  lea     rdx, [rbp+4Fh+var_78]
0x1401378ff  lea     rcx, [rbp+4Fh+var_BC]
0x140137903  call    sub_140138E8C
0x140137908  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14013790c  jz      loc_140137B85
0x140137912  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x140137915  dec     eax
0x140137917  movsxd  rcx, eax
0x14013791a  add     rsi, rcx
0x14013791d  jmp     loc_140137A24
0x140137922  movzx   eax, byte ptr [rsi]
0x140137925  movsx   r13, byte ptr [rax+r12+419370h]
0x14013792e  lea     ecx, [r13+1]
0x140137932  mov     r9, [rbp+4Fh+var_B0]
0x140137936  sub     r9, rsi
0x140137939  movsxd  rax, ecx
0x14013793c  cmp     rax, r9
0x14013793f  jg      loc_140137B2F
0x140137945  mov     [rbp+4Fh+var_A0], rdi
0x140137949  mov     [rbp+4Fh+var_70], rsi
0x14013794d  mov     eax, edi
0x14013794f  cmp     ecx, 4
0x140137952  setz    al
0x140137955  inc     eax
0x140137957  mov     r14d, eax
0x14013795a  mov     r8d, eax
0x14013795d  mov     [rsp+100h+lpOverlapped], r10
0x140137962  lea     r9, [rbp+4Fh+var_A0]
0x140137966  lea     rdx, [rbp+4Fh+var_70]
0x14013796a  lea     rcx, [rbp+4Fh+var_BC]
0x14013796e  call    sub_140138E8C
0x140137973  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140137977  jz      loc_140137B85
0x14013797d  add     rsi, r13
0x140137980  mov     r12d, r14d
0x140137983  mov     r13, [rbp+4Fh+var_88]
0x140137987  jmp     loc_140137A24
0x14013798c  lea     r11, __ImageBase
0x140137993  mov     r8, rva qword_14042C950[r11+r13*8]
0x14013799b  mov     cl, [r8+r15*8+3Dh]
0x1401379a0  test    cl, 4
0x1401379a3  jz      short loc_1401379C6
0x1401379a5  mov     al, [r8+r15*8+3Eh]
0x1401379aa  mov     [rbp+4Fh+var_48], al
0x1401379ad  mov     al, [rsi]
0x1401379af  mov     [rbp+4Fh+var_47], al
0x1401379b2  and     cl, 0FBh
0x1401379b5  mov     [r8+r15*8+3Dh], cl
0x1401379ba  mov     r8d, 2
0x1401379c0  lea     rdx, [rbp+4Fh+var_48]
0x1401379c4  jmp     short loc_140137A0F
0x1401379c6  movzx   r9d, byte ptr [rsi]
0x1401379ca  mov     rax, [r10+18h]
0x1401379ce  mov     rcx, [rax]
0x1401379d1  cmp     [rcx+r9*2], di
0x1401379d6  jge     short loc_140137A09
0x1401379d8  lea     r14, [rsi+1]
0x1401379dc  cmp     r14, [rbp+4Fh+var_B0]
0x1401379e0  jnb     loc_140137B62
0x1401379e6  mov     r9, r10
0x1401379e9  mov     r8d, 2
0x1401379ef  mov     rdx, rsi
0x1401379f2  lea     rcx, [rbp+4Fh+var_BC]
0x1401379f6  call    _mbtowc_internal
0x1401379fb  cmp     eax, 0FFFFFFFFh
0x1401379fe  jz      loc_140137B85
0x140137a04  mov     rsi, r14
0x140137a07  jmp     short loc_140137A24
0x140137a09  mov     r8, r12
0x140137a0c  mov     rdx, rsi
0x140137a0f  mov     r9, r10
0x140137a12  lea     rcx, [rbp+4Fh+var_BC]
0x140137a16  call    _mbtowc_internal
0x140137a1b  cmp     eax, 0FFFFFFFFh
0x140137a1e  jz      loc_140137B85
0x140137a24  inc     rsi
0x140137a27  mov     [rsp+38h], rdi
0x140137a2c  mov     [rsp+100h+var_D0], rdi
0x140137a31  mov     dword ptr [rsp+100h+var_D8], 5
0x140137a39  lea     rax, [rbp+4Fh+Buffer]
0x140137a3d  mov     [rsp+100h+lpOverlapped], rax
0x140137a42  mov     r9d, r12d
0x140137a45  lea     r8, [rbp+4Fh+var_BC]
0x140137a49  xor     edx, edx
0x140137a4b  mov     ecx, [rbp+4Fh+var_98]
0x140137a4e  call    __acrt_WideCharToMultiByte
0x140137a53  mov     r14d, eax
0x140137a56  test    eax, eax
0x140137a58  jz      loc_140137B85
0x140137a5e  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x140137a61  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140137a66  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140137a6a  mov     r8d, eax; nNumberOfBytesToWrite
0x140137a6d  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x140137a71  mov     r12, [rbp+4Fh+hFile]
0x140137a75  mov     rcx, r12; hFile
0x140137a78  call    cs:WriteFile
0x140137a7e  test    eax, eax
0x140137a80  jz      loc_140137B7D
0x140137a86  mov     edx, [rbx+8]
0x140137a89  sub     edx, dword ptr [rbp+4Fh+var_90]
0x140137a8c  add     edx, esi
0x140137a8e  mov     [rbx+4], edx
0x140137a91  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x140137a95  jb      loc_140137B85
0x140137a9b  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x140137a9f  jnz     short loc_140137ADF
0x140137aa1  mov     eax, 0Dh
0x140137aa6  mov     [rbp+4Fh+var_C0], ax
0x140137aaa  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140137aaf  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140137ab3  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x140137ab7  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x140137abb  mov     rcx, r12; hFile
0x140137abe  call    cs:WriteFile
0x140137ac4  test    eax, eax
0x140137ac6  jz      loc_140137B7D
0x140137acc  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x140137ad0  jb      loc_140137B85
0x140137ad6  inc     dword ptr [rbx+8]
0x140137ad9  inc     dword ptr [rbx+4]
0x140137adc  mov     edx, [rbx+4]
0x140137adf  cmp     rsi, [rbp+4Fh+var_B0]
0x140137ae3  jnb     loc_140137B85
0x140137ae9  mov     r10, [rbp+4Fh+var_A8]
0x140137aed  mov     r11, [rbp+4Fh+var_60]
0x140137af1  mov     ecx, [rbp+4Fh+var_94]
0x140137af4  jmp     loc_1401377E5
0x140137af9  test    r8, r8
0x140137afc  jle     short loc_140137B29
0x140137afe  sub     rsi, r14
0x140137b01  lea     r9, __ImageBase
0x140137b08  lea     rdx, [r14+r15*8]
0x140137b0c  mov     rcx, rva qword_14042C950[r9+r13*8]
0x140137b14  mov     al, [rsi+r14]
0x140137b18  mov     [rdx+rcx+3Eh], al
0x140137b1c  inc     edi
0x140137b1e  inc     r14
0x140137b21  movsxd  rax, edi
0x140137b24  cmp     rax, r8
0x140137b27  jl      short loc_140137B08
0x140137b29  add     [rbx+4], r8d
0x140137b2d  jmp     short loc_140137B85
0x140137b2f  test    r9, r9
0x140137b32  jle     short loc_140137B5C
0x140137b34  mov     r8, rdi
0x140137b37  mov     r10, [rbp+4Fh+var_88]
0x140137b3b  lea     rdx, [r8+r15*8]
0x140137b3f  mov     rcx, rva qword_14042C950[r12+r10*8]
0x140137b47  mov     al, [r8+rsi]
0x140137b4b  mov     [rdx+rcx+3Eh], al
0x140137b4f  inc     edi
0x140137b51  inc     r8
0x140137b54  movsxd  rax, edi
0x140137b57  cmp     rax, r9
0x140137b5a  jl      short loc_140137B3B
0x140137b5c  add     [rbx+4], r9d
0x140137b60  jmp     short loc_140137B85
0x140137b62  mov     [r8+r15*8+3Eh], r9b
0x140137b67  mov     rax, rva qword_14042C950[r11+r13*8]
0x140137b6f  or      byte ptr [rax+r15*8+3Dh], 4
0x140137b75  lea     eax, [rdx+1]
0x140137b78  mov     [rbx+4], eax
0x140137b7b  jmp     short loc_140137B85
0x140137b7d  call    cs:__imp_GetLastError
0x140137b83  mov     [rbx], eax
0x140137b85  mov     rax, rbx
0x140137b88  mov     rcx, [rbp+4Fh+var_38]
0x140137b8c  xor     rcx, rsp; StackCookie
0x140137b8f  call    __security_check_cookie
0x140137b94  mov     rbx, [rsp+100h+arg_0]
0x140137b9c  add     rsp, 0D0h
0x140137ba3  pop     r15
0x140137ba5  pop     r14
0x140137ba7  pop     r13
0x140137ba9  pop     r12
  ... truncated ...
```
