# PDB1::OpenTSPdb(wchar_t const *,wchar_t const *,char const *,_GUID const &,ulong,int,long *,wchar_t *,unsigned __int64,PDB * *)

- ea: `0x1800334b0`
- end: `0x180033c35`
- name: `?OpenTSPdb@PDB1@@SAHPEB_W0PEBDAEBU_GUID@@KHPEAJPEA_W_KPEAPEAUPDB@@@Z`
- size: `1925`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const char *, const struct _GUID *, unsigned int, int, int *, wchar_t *, unsigned __int64, struct PDB **)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180060e20`

## callees

- `0x180021340`
- `0x18002641c`
- `0x180026980`
- `0x18002723e`
- `0x180029ad0`
- `0x180029c40`
- `0x1800334b0`
- `0x180033ce0`
- `0x180168f90`
- `0x1801693d5`
- `0x18016944c`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180033835`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18003392a`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180033835`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18003392a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180033702`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800337da`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180033a49`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180033702`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800337da`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180033a49`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18003360c`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18003360c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800335f9`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800335f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800338f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800338f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180033648`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800336be`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003371d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800337fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800338d5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180033ace`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180033648`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800336be`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003371d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800337fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800338d5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180033ace`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PDB1::OpenTSPdb(
        const wchar_t *a1,
        const wchar_t *a2,
        char *a3,
        struct _GUID *a4,
        unsigned int a5,
        int a6,
        int *a7,
        wchar_t *a8,
        unsigned __int64 a9,
        struct PDB **a10)
{
  __int64 v11; // rdi
  int v12; // esi
  char *v13; // r14
  size_t v14; // rbx
  rsize_t v15; // r14
  unsigned __int64 v16; // rdx
  char *v17; // rbx
  __int64 v18; // rax
  PSGSI1::EnumPubsByAddr *v19; // rbx
  PSGSI1::EnumPubsByAddr *v20; // rcx
  wchar_t *v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  unsigned int v25; // r14d
  __int64 v26; // r9
  unsigned int *v27; // r14
  const char *v28; // rdx
  const wchar_t *v29; // rbx
  int v30; // eax
  __int64 v31; // rcx
  wchar_t v32; // ax
  wchar_t i; // ax
  PSGSI1::EnumPubsByAddr *v34; // rbx
  PSGSI1::EnumPubsByAddr *v35; // rcx
  PSGSI1::EnumPubsByAddr *v36; // rbx
  PSGSI1::EnumPubsByAddr *v37; // rcx
  PSGSI1::EnumPubsByAddr *v38; // rbx
  PSGSI1::EnumPubsByAddr *v39; // rcx
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v41; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h]
  const wchar_t *v43; // [rsp+68h] [rbp-98h]
  int *v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  void **v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  PSGSI1::EnumPubsByAddr *v48; // [rsp+90h] [rbp-70h]
  _BYTE v49[16]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Drive[4]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Str[264]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Filename[256]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Dir[256]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t Ext[256]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v55[512]; // [rsp+8C0h] [rbp+7C0h] BYREF
  wchar_t Buffer[256]; // [rsp+AC0h] [rbp+9C0h] BYREF
  wchar_t v57[256]; // [rsp+CC0h] [rbp+BC0h] BYREF
  wchar_t FullPath[776]; // [rsp+EC0h] [rbp+DC0h] BYREF
  wchar_t v59[1024]; // [rsp+14D0h] [rbp+13D0h] BYREF

  v45 = -2;
  v41 = a4;
  v43 = a2;
  lpFileName = a1;
  v44 = a7;
  LODWORD(v11) = 0;
  v12 = 0;
  v40 = 0;
  v13 = strchr_0(a3, 88);
  *(_QWORD *)Drive = v13;
  *a10 = 0;
  v46 = &SafeStackAllocator<16>::`vftable';
  v48 = 0;
  v47 = 0;
  if ( strchr_0(a3, 84) )
  {
    v17 = a3;
    goto LABEL_22;
  }
  v14 = strlen_0(a3);
  v15 = v14 + strlen_0("T") + 1;
  if ( v15 <= 0xFFFFFFFFFFFFFFF0uLL )
  {
    if ( *v46 == SafeStackAllocator<16>::AllocBytes )
    {
      if ( v15 >= 0xFFFFFFFFFFFFFFF0uLL )
      {
        v17 = 0;
        goto LABEL_11;
      }
      v16 = (v15 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( 16 - v47 >= v16 )
      {
        v17 = &v49[v47];
        v47 += v16;
        goto LABEL_11;
      }
      v18 = SafeStackAllocator<528>::AllocInHeap(&v46);
    }
    else
    {
      v18 = ((__int64 (__fastcall *)(void ***, rsize_t))*v46)(&v46, v15);
    }
    v17 = (char *)v18;
LABEL_11:
    if ( v17 )
    {
      strcpy_s(v17, v15, a3);
      _o_strcat_s(v17, v15, "T");
      v13 = *(char **)Drive;
LABEL_22:
      if ( v43 && !v13 )
      {
        _o_wcsncpy_s(FullPath, 776, lpFileName, -1);
        _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
        _o_wcsncpy_s(Str, 260, v43, -1);
        CCanonFile::SzCanonFilename(Str);
        v22 = wcsrchr_0(Str, 0x5Cu);
        v23 = -1;
        do
          ++v23;
        while ( Str[v23] );
        if ( !v22 || v23 != ((char *)v22 - (char *)Str + 2) >> 1 )
        {
          if ( v23 == 259 )
          {
            Str[258] = 92;
            v24 = 518;
          }
          else
          {
            Str[v23] = 92;
            v24 = 2 * v23 + 2;
            if ( v24 >= 0x208 )
              _report_rangecheckfailure(v24, Str);
          }
          *(wchar_t *)((char *)Str + v24) = 0;
        }
        _wsplitpath_s(Str, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
        _o_wcsncpy_s(v55, 256, Filename, -1);
        v25 = 2;
        _o__wmakepath_s(FullPath, 776, Drive, Dir, Filename, Ext);
        PDB1::OpenValidate4(FullPath, v17, v41, 0, a5, &v40, v59, 0x400u, a10);
        if ( *a10 )
        {
LABEL_71:
          v46 = &SafeStackAllocator<16>::`vftable';
          v38 = v48;
          while ( v38 )
          {
            v39 = v38;
            v38 = *(PSGSI1::EnumPubsByAddr **)v38;
            PSGSI1::EnumPubsByAddr::release(v39);
          }
          return 1;
        }
        while ( 1 )
        {
          v12 = v40;
          if ( v40 != 5 )
            break;
          v26 = v25++;
          swprintf_s(Buffer, 0x100u, L".%u", v26);
          _o_wcsncpy_s(Filename, 256, v55, -1);
          _o_wcsncat_s(Filename, 256, Buffer, -1);
          _o__wmakepath_s(FullPath, 776, Drive, Dir, Filename, Ext);
          PDB1::OpenValidate4(FullPath, v17, v41, 0, a5, &v40, v59, 0x400u, a10);
          if ( *a10 )
          {
            v12 = v40;
            break;
          }
        }
      }
      if ( !*a10 )
      {
        v27 = (unsigned int *)v44;
        v28 = v17;
        v29 = lpFileName;
        PDB1::OpenValidate4(lpFileName, v28, v41, 0, a5, v44, a8, 0x400u, a10);
        if ( !*a10 )
        {
          if ( v43 )
          {
            v30 = *((_DWORD *)&PDB1::c_mpEcEcBest + v12);
            if ( !_bittest(&v30, *v27) )
            {
              if ( a6 && v12 == 4 )
              {
                _wsplitpath_s(v29, 0, 0, 0, 0, Dir, 0x100u, v57, 0x100u);
                v31 = 0;
                while ( 1 )
                {
                  v32 = v57[v31++];
                  if ( v32 != aTmp[v31 - 1] )
                    break;
                  if ( v31 == 5 )
                  {
                    for ( i = Dir[0]; i; i = Dir[v11] )
                    {
                      switch ( (int)v11 )
                      {
                        case 0:
                          if ( i != 108 )
                            goto LABEL_48;
                          break;
                        case 1:
                          if ( i != 110 )
                            goto LABEL_48;
                          break;
                        case 2:
                          if ( i != 107 )
                            goto LABEL_48;
                          break;
                        case 3:
                          if ( i != 123 )
                            goto LABEL_48;
                          break;
                        case 12:
                        case 17:
                        case 22:
                        case 27:
                          if ( i != 45 )
                            goto LABEL_48;
                          break;
                        case 40:
                          if ( i != 125 )
                            goto LABEL_48;
                          break;
                        default:
                          if ( (unsigned __int16)(i - 48) > 9u
                            && (unsigned __int16)(i - 65) > 5u
                            && (unsigned __int16)(i - 97) > 5u )
                          {
                            goto LABEL_48;
                          }
                          break;
                      }
                      v11 = (unsigned int)(v11 + 1);
                    }
                    if ( (_DWORD)v11 != 41 )
                      break;
                    v46 = &SafeStackAllocator<16>::`vftable';
                    v36 = v48;
                    if ( !v48 )
                      return 0;
                    do
                    {
                      v37 = v36;
                      v36 = *(PSGSI1::EnumPubsByAddr **)v36;
                      PSGSI1::EnumPubsByAddr::release(v37);
                    }
                    while ( v36 );
                    return 0;
                  }
                }
              }
LABEL_48:
              *v27 = v12;
              if ( a8 )
                _o_wcsncpy_s(a8, 1024, v59, -1);
            }
          }
          v46 = &SafeStackAllocator<16>::`vftable';
          v34 = v48;
          while ( v34 )
          {
            v35 = v34;
            v34 = *(PSGSI1::EnumPubsByAddr **)v34;
            PSGSI1::EnumPubsByAddr::release(v35);
          }
          return 0;
        }
      }
      goto LABEL_71;
    }
  }
  if ( v44 )
    *v44 = 2;
  if ( a8 && a9 )
    _o_wcsncpy_s(a8, a9, lpFileName, -1);
  v46 = &SafeStackAllocator<16>::`vftable';
  v19 = v48;
  if ( !v48 )
    return 0;
  do
  {
    v20 = v19;
    v19 = *(PSGSI1::EnumPubsByAddr **)v19;
    PSGSI1::EnumPubsByAddr::release(v20);
  }
  while ( v19 );
  return 0;
}

```

## disassembly

```asm
0x1800334b0  push    rbp
0x1800334b2  push    rbx
0x1800334b3  push    rsi
0x1800334b4  push    rdi
0x1800334b5  push    r12
0x1800334b7  push    r13
0x1800334b9  push    r14
0x1800334bb  push    r15
0x1800334bd  lea     rbp, [rsp-1BE8h]
0x1800334c5  mov     eax, 1CE8h
0x1800334ca  call    _alloca_probe
0x1800334cf  sub     rsp, rax
0x1800334d2  mov     [rsp+1D20h+var_1CA8], 0FFFFFFFFFFFFFFFEh
0x1800334db  mov     rax, cs:__security_cookie
0x1800334e2  xor     rax, rsp
0x1800334e5  mov     [rbp+1C20h+var_50], rax
0x1800334ec  mov     [rsp+1D20h+var_1CC8], r9
0x1800334f1  mov     r15, r8
0x1800334f4  mov     [rsp+1D20h+var_1CB8], rdx
0x1800334f9  mov     [rsp+1D20h+lpFileName], rcx
0x1800334fe  mov     rax, [rbp+1C20h+arg_30]
0x180033505  mov     [rsp+1D20h+var_1CB0], rax
0x18003350a  mov     r13, [rbp+1C20h+arg_38]
0x180033511  mov     r12, [rbp+1C20h+arg_48]
0x180033518  xor     edi, edi
0x18003351a  mov     esi, edi
0x18003351c  mov     [rsp+1D20h+var_1CD0], edi
0x180033520  mov     edx, 58h ; 'X'; Val
0x180033525  mov     rcx, r8; Str
0x180033528  call    strchr_0
0x18003352d  mov     r14, rax
0x180033530  mov     qword ptr [rbp+1C20h+Drive], rax
0x180033534  mov     [r12], rdi
0x180033538  lea     rax, ??_7?$SafeStackAllocator@$0BA@@@6B@; const SafeStackAllocator<16>::`vftable'
0x18003353f  mov     [rbp+1C20h+var_1CA0], rax
0x180033543  mov     [rbp+1C20h+var_1C90], rdi
0x180033547  mov     [rbp+1C20h+var_1C98], rdi
0x18003354b  mov     edx, 54h ; 'T'; Val
0x180033550  mov     rcx, r15; Str
0x180033553  call    strchr_0
0x180033558  test    rax, rax
0x18003355b  jnz     loc_180033687
0x180033561  mov     rcx, r15; Str
0x180033564  call    strlen_0
0x180033569  mov     rbx, rax
0x18003356c  lea     rcx, Str; "T"
0x180033573  call    strlen_0
0x180033578  lea     r14, [rax+1]
0x18003357c  add     r14, rbx
0x18003357f  cmp     r14, 0FFFFFFFFFFFFFFF0h
0x180033583  ja      loc_180033618
0x180033589  mov     rax, [rbp+1C20h+var_1CA0]
0x18003358d  mov     rax, [rax]
0x180033590  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0BA@@@UEAAPEAX_K@Z; SafeStackAllocator<16>::AllocBytes(unsigned __int64)
0x180033597  cmp     rax, rcx
0x18003359a  jnz     short loc_1800335DB
0x18003359c  cmp     r14, 0FFFFFFFFFFFFFFF0h
0x1800335a0  jnb     short loc_1800335D6
0x1800335a2  lea     rdx, [r14+7]
0x1800335a6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800335aa  mov     eax, 10h
0x1800335af  mov     rcx, [rbp+1C20h+var_1C98]
0x1800335b3  sub     rax, rcx
0x1800335b6  cmp     rax, rdx
0x1800335b9  jb      short loc_1800335CB
0x1800335bb  lea     rbx, [rbp+1C20h+var_1C88]
0x1800335bf  add     rbx, rcx
0x1800335c2  add     rcx, rdx
0x1800335c5  mov     [rbp+1C20h+var_1C98], rcx
0x1800335c9  jmp     short loc_1800335EB
0x1800335cb  lea     rcx, [rbp+1C20h+var_1CA0]
0x1800335cf  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x1800335d4  jmp     short loc_1800335E8
0x1800335d6  mov     rbx, rdi
0x1800335d9  jmp     short loc_1800335EB
0x1800335db  mov     rdx, r14
0x1800335de  lea     rcx, [rbp+1C20h+var_1CA0]
0x1800335e2  call    cs:__guard_dispatch_icall_fptr
0x1800335e8  mov     rbx, rax
0x1800335eb  test    rbx, rbx
0x1800335ee  jz      short loc_180033618
0x1800335f0  mov     r8, r15; Source
0x1800335f3  mov     rdx, r14; SizeInBytes
0x1800335f6  mov     rcx, rbx; Destination
0x1800335f9  call    cs:__imp_strcpy_s
0x1800335ff  lea     r8, Str; "T"
0x180033606  mov     rdx, r14
0x180033609  mov     rcx, rbx
0x18003360c  call    cs:__imp__o_strcat_s
0x180033612  mov     r14, qword ptr [rbp+1C20h+Drive]
0x180033616  jmp     short loc_18003368A
0x180033618  mov     rax, [rsp+1D20h+var_1CB0]
0x18003361d  test    rax, rax
0x180033620  jz      short loc_180033628
0x180033622  mov     dword ptr [rax], 2
0x180033628  test    r13, r13
0x18003362b  jz      short loc_18003364F
0x18003362d  mov     rdx, [rbp+1C20h+arg_40]
0x180033634  test    rdx, rdx
0x180033637  jz      short loc_18003364F
0x180033639  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180033640  mov     r8, [rsp+1D20h+lpFileName]
0x180033645  mov     rcx, r13
0x180033648  call    cs:__imp__o_wcsncpy_s
0x18003364e  nop
0x18003364f  lea     rax, ??_7?$SafeStackAllocator@$0BA@@@6B@; const SafeStackAllocator<16>::`vftable'
0x180033656  mov     [rbp+1C20h+var_1CA0], rax
0x18003365a  mov     rbx, [rbp+1C20h+var_1C90]
0x18003365e  test    rbx, rbx
0x180033661  jz      loc_180033B00
0x180033667  nop     word ptr [rax+rax+00000000h]
0x180033670  mov     rcx, rbx; this
0x180033673  mov     rbx, [rbx]
0x180033676  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18003367b  test    rbx, rbx
0x18003367e  jnz     short loc_180033670
0x180033680  xor     eax, eax
0x180033682  jmp     loc_180033BC5
0x180033687  mov     rbx, r15
0x18003368a  mov     r15d, [rbp+1C20h+arg_20]
0x180033691  cmp     [rsp+1D20h+var_1CB8], 0
0x180033697  jz      loc_18003397F
0x18003369d  test    r14, r14
0x1800336a0  jnz     loc_18003397F
0x1800336a6  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800336ad  mov     r8, [rsp+1D20h+lpFileName]
0x1800336b2  mov     edx, 308h
0x1800336b7  lea     rcx, [rbp+1C20h+FullPath]
0x1800336be  call    cs:__imp__o_wcsncpy_s
0x1800336c4  mov     [rsp+1D20h+ExtCount], 100h; ExtCount
0x1800336cd  lea     rax, [rbp+1C20h+var_1660]
0x1800336d4  mov     [rsp+1D20h+Ext], rax; Ext
0x1800336d9  mov     [rsp+1D20h+FilenameCount], 100h; FilenameCount
0x1800336e2  lea     rax, [rbp+1C20h+var_1A60]
0x1800336e9  mov     [rsp+1D20h+Filename], rax; Filename
0x1800336ee  mov     [rsp+1D20h+DirCount], rdi; DirCount
0x1800336f3  xor     r9d, r9d; Dir
0x1800336f6  xor     r8d, r8d; DriveCount
0x1800336f9  xor     edx, edx; Drive
0x1800336fb  lea     rcx, [rbp+1C20h+FullPath]; FullPath
0x180033702  call    cs:__imp__wsplitpath_s
0x180033708  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003370f  mov     r8, [rsp+1D20h+var_1CB8]
0x180033714  mov     edx, 104h
0x180033719  lea     rcx, [rbp+1C20h+Str]
0x18003371d  call    cs:__imp__o_wcsncpy_s
0x180033723  lea     rcx, [rbp+1C20h+Str]; lpSrcStr
0x180033727  call    ?SzCanonFilename@CCanonFile@@SAPEA_WPEA_W@Z; CCanonFile::SzCanonFilename(wchar_t *)
0x18003372c  mov     esi, 5Ch ; '\'
0x180033731  mov     edx, esi; Ch
0x180033733  lea     rcx, [rbp+1C20h+Str]; Str
0x180033737  call    wcsrchr_0
0x18003373c  lea     rdx, [rbp+1C20h+Str]
0x180033740  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033747  nop     word ptr [rax+rax+00000000h]
0x180033750  inc     rcx
0x180033753  cmp     word ptr [rdx+rcx*2], 0
0x180033758  jnz     short loc_180033750
0x18003375a  test    rax, rax
0x18003375d  jz      short loc_180033772
0x18003375f  lea     rdx, [rbp+1C20h+Str]
0x180033763  sub     rax, rdx
0x180033766  add     rax, 2
0x18003376a  sar     rax, 1
0x18003376d  cmp     rcx, rax
0x180033770  jz      short loc_1800337A8
0x180033772  cmp     rcx, 103h
0x180033779  jnz     short loc_180033789
0x18003377b  mov     [rbp+1C20h+var_1A6C], si
0x180033782  mov     ecx, 206h
0x180033787  jmp     short loc_1800337A3
0x180033789  mov     [rbp+rcx*2+1C20h+Str], si
0x18003378e  lea     rcx, ds:2[rcx*2]
0x180033796  cmp     rcx, 208h
0x18003379d  jnb     loc_180033BE8
0x1800337a3  mov     [rbp+rcx+1C20h+Str], di
0x1800337a8  mov     [rsp+1D20h+ExtCount], rdi; ExtCount
0x1800337ad  mov     [rsp+1D20h+Ext], rdi; Ext
0x1800337b2  mov     [rsp+1D20h+FilenameCount], rdi; FilenameCount
0x1800337b7  mov     [rsp+1D20h+Filename], rdi; Filename
0x1800337bc  mov     [rsp+1D20h+DirCount], 100h; DirCount
0x1800337c5  lea     r9, [rbp+1C20h+Dir]; Dir
0x1800337cc  mov     r8d, 3; DriveCount
0x1800337d2  lea     rdx, [rbp+1C20h+Drive]; Drive
0x1800337d6  lea     rcx, [rbp+1C20h+Str]; FullPath
0x1800337da  call    cs:__imp__wsplitpath_s
0x1800337e0  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800337e7  lea     r8, [rbp+1C20h+var_1A60]
0x1800337ee  mov     edx, 100h
0x1800337f3  lea     rcx, [rbp+1C20h+var_1460]
0x1800337fa  call    cs:__imp__o_wcsncpy_s
0x180033800  mov     r14d, 2
0x180033806  lea     rax, [rbp+1C20h+var_1660]
0x18003380d  mov     [rsp+1D20h+Filename], rax
0x180033812  lea     rax, [rbp+1C20h+var_1A60]
0x180033819  mov     [rsp+1D20h+DirCount], rax
0x18003381e  lea     r9, [rbp+1C20h+Dir]
0x180033825  lea     r8, [rbp+1C20h+Drive]
0x180033829  mov     edx, 308h
0x18003382e  lea     rcx, [rbp+1C20h+FullPath]
0x180033835  call    cs:__imp__o__wmakepath_s
0x18003383b  mov     [rsp+1D20h+ExtCount], r12; struct PDB **
0x180033840  mov     [rsp+1D20h+Ext], 400h; unsigned __int64
0x180033849  lea     rax, [rbp+1C20h+var_850]
0x180033850  mov     [rsp+1D20h+FilenameCount], rax; wchar_t *
0x180033855  lea     rax, [rsp+1D20h+var_1CD0]
0x18003385a  mov     [rsp+1D20h+Filename], rax; int *
0x18003385f  mov     dword ptr [rsp+1D20h+DirCount], r15d; unsigned int
0x180033864  xor     r9d, r9d; unsigned int
0x180033867  mov     r8, [rsp+1D20h+var_1CC8]; struct _GUID *
0x18003386c  mov     rdx, rbx; char *
0x18003386f  lea     rcx, [rbp+1C20h+FullPath]; lpFileName
0x180033876  call    ?OpenValidate4@PDB1@@SAHPEB_WPEBDPEBU_GUID@@KKPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenValidate4(wchar_t const *,char const *,_GUID const *,ulong,ulong,long *,wchar_t *,unsigned __int64,PDB * *)
0x18003387b  cmp     qword ptr [r12], 0
0x180033880  jnz     loc_180033B94
0x180033886  nop     word ptr [rax+rax+00000000h]
0x180033890  mov     esi, [rsp+1D20h+var_1CD0]
0x180033894  cmp     esi, 5
0x180033897  jnz     loc_18003397F
0x18003389d  mov     r9d, r14d
0x1800338a0  inc     r14d
0x1800338a3  lea     r8, aU; ".%u"
0x1800338aa  mov     edx, 100h; BufferCount
0x1800338af  lea     rcx, [rbp+1C20h+Buffer]; Buffer
0x1800338b6  call    swprintf_s
0x1800338bb  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800338c2  lea     r8, [rbp+1C20h+var_1460]
0x1800338c9  mov     edx, 100h
0x1800338ce  lea     rcx, [rbp+1C20h+var_1A60]
0x1800338d5  call    cs:__imp__o_wcsncpy_s
0x1800338db  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800338e2  lea     r8, [rbp+1C20h+Buffer]
0x1800338e9  mov     edx, 100h
0x1800338ee  lea     rcx, [rbp+1C20h+var_1A60]
0x1800338f5  call    cs:__imp__o_wcsncat_s
0x1800338fb  lea     rax, [rbp+1C20h+var_1660]
0x180033902  mov     [rsp+1D20h+Filename], rax
0x180033907  lea     rax, [rbp+1C20h+var_1A60]
0x18003390e  mov     [rsp+1D20h+DirCount], rax
0x180033913  lea     r9, [rbp+1C20h+Dir]
0x18003391a  lea     r8, [rbp+1C20h+Drive]
0x18003391e  mov     edx, 308h
0x180033923  lea     rcx, [rbp+1C20h+FullPath]
0x18003392a  call    cs:__imp__o__wmakepath_s
0x180033930  mov     [rsp+1D20h+ExtCount], r12; struct PDB **
0x180033935  mov     [rsp+1D20h+Ext], 400h; unsigned __int64
0x18003393e  lea     rax, [rbp+1C20h+var_850]
0x180033945  mov     [rsp+1D20h+FilenameCount], rax; wchar_t *
0x18003394a  lea     rax, [rsp+1D20h+var_1CD0]
0x18003394f  mov     [rsp+1D20h+Filename], rax; int *
0x180033954  mov     dword ptr [rsp+1D20h+DirCount], r15d; unsigned int
0x180033959  xor     r9d, r9d; unsigned int
0x18003395c  mov     r8, [rsp+1D20h+var_1CC8]; struct _GUID *
0x180033961  mov     rdx, rbx; char *
0x180033964  lea     rcx, [rbp+1C20h+FullPath]; lpFileName
0x18003396b  call    ?OpenValidate4@PDB1@@SAHPEB_WPEBDPEBU_GUID@@KKPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenValidate4(wchar_t const *,char const *,_GUID const *,ulong,ulong,long *,wchar_t *,unsigned __int64,PDB * *)
0x180033970  cmp     qword ptr [r12], 0
0x180033975  jz      loc_180033890
0x18003397b  mov     esi, [rsp+1D20h+var_1CD0]
0x18003397f  cmp     qword ptr [r12], 0
0x180033984  jnz     loc_180033B94
0x18003398a  mov     [rsp+1D20h+ExtCount], r12; struct PDB **
0x18003398f  mov     [rsp+1D20h+Ext], 400h; unsigned __int64
0x180033998  mov     [rsp+1D20h+FilenameCount], r13; wchar_t *
0x18003399d  mov     r14, [rsp+1D20h+var_1CB0]
0x1800339a2  mov     [rsp+1D20h+Filename], r14; int *
0x1800339a7  mov     dword ptr [rsp+1D20h+DirCount], r15d; unsigned int
0x1800339ac  xor     r9d, r9d; unsigned int
0x1800339af  mov     r8, [rsp+1D20h+var_1CC8]; struct _GUID *
0x1800339b4  mov     rdx, rbx; char *
0x1800339b7  mov     rbx, [rsp+1D20h+lpFileName]
0x1800339bc  mov     rcx, rbx; lpFileName
0x1800339bf  call    ?OpenValidate4@PDB1@@SAHPEB_WPEBDPEBU_GUID@@KKPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenValidate4(wchar_t const *,char const *,_GUID const *,ulong,ulong,long *,wchar_t *,unsigned __int64,PDB * *)
0x1800339c4  cmp     qword ptr [r12], 0
0x1800339c9  jnz     loc_180033B94
0x1800339cf  cmp     [rsp+1D20h+var_1CB8], 0
0x1800339d5  jz      loc_180033AD5
0x1800339db  movsxd  rax, esi
0x1800339de  lea     r15, __ImageBase
0x1800339e5  mov     ecx, [r14]
0x1800339e8  mov     eax, ds:rva ?c_mpEcEcBest@PDB1@@0QBHB[r15+rax*4]; int const near * const PDB1::c_mpEcEcBest ...
0x1800339f0  bt      eax, ecx
0x1800339f3  jb      loc_180033AD5
0x1800339f9  cmp     [rbp+1C20h+arg_28], 0
0x180033a00  jz      loc_180033AB0
0x180033a06  cmp     esi, 4
0x180033a09  jnz     loc_180033AB0
0x180033a0f  mov     [rsp+1D20h+ExtCount], 100h; ExtCount
0x180033a18  lea     rax, [rbp+1C20h+var_1060]
0x180033a1f  mov     [rsp+1D20h+Ext], rax; Ext
0x180033a24  mov     [rsp+1D20h+FilenameCount], 100h; FilenameCount
0x180033a2d  lea     rax, [rbp+1C20h+Dir]
0x180033a34  mov     [rsp+1D20h+Filename], rax; Filename
0x180033a39  mov     [rsp+1D20h+DirCount], rdi; DirCount
0x180033a3e  xor     r9d, r9d; Dir
0x180033a41  xor     r8d, r8d; DriveCount
0x180033a44  xor     edx, edx; Drive
0x180033a46  mov     rcx, rbx; FullPath
0x180033a49  call    cs:__imp__wsplitpath_s
0x180033a4f  mov     rcx, rdi
  ... truncated ...
```
