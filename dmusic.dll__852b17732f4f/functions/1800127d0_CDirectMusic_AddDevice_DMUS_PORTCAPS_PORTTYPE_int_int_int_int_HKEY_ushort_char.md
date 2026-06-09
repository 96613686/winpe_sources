# CDirectMusic::AddDevice(_DMUS_PORTCAPS &,PORTTYPE,int,int,int,int,HKEY__ *,ushort *,char *)

- ea: `0x1800127d0`
- end: `0x180012dca`
- name: `?AddDevice@CDirectMusic@@QEAAJAEAU_DMUS_PORTCAPS@@W4PORTTYPE@@HHHHPEAUHKEY__@@PEAGPEAD@Z`
- size: `1530`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180012dd0`
- `0x180012e60`
- `0x18001e528`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800016d0`
- `0x1800021a8`
- `0x18000818c`
- `0x18000a56c`
- `0x1800127d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800128a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001291f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012cd7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001291f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012cd7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180012a47`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180012a47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012aa9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012aa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180012a85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180012af1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180012a85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180012af1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012b01`
- `RPCRT4!UuidCreate` at `0x180012abc`
- `RPCRT4!UuidCreate` at `0x180012b14`
- `RPCRT4!UuidCreate` at `0x180012abc`
- `RPCRT4!UuidCreate` at `0x180012b14`

## pseudocode

```c
__int64 __fastcall CDirectMusic::AddDevice(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        HKEY hKey,
        _WORD *a9,
        _BYTE *a10)
{
  int v10; // ebx
  _BYTE *v11; // r13
  _QWORD *v12; // rcx
  __int64 v16; // rax
  __int64 v17; // rsi
  _DWORD *v18; // rcx
  bool v19; // zf
  __int64 v20; // rax
  char *v22; // rax
  __int64 v23; // rdx
  _OWORD *v24; // rcx
  _OWORD *v25; // rax
  __int64 v26; // r8
  __int128 v27; // xmm1
  __int64 v28; // rax
  _BOOL8 v29; // rbx
  const unsigned __int16 *v30; // r8
  BYTE *lpData; // rax
  int v32; // ebx
  __int64 v33; // rdi
  _WORD *v34; // rdx
  __int64 v35; // rcx
  _WORD *v36; // rax
  _WORD *v37; // rdx
  void *v38; // rbx
  unsigned __int64 v39; // rdx
  void *v40; // rcx
  __int64 v41; // rax
  unsigned __int8 *v42; // rdx
  __int64 v43; // r9
  int v44; // ecx
  int v45; // r8d
  _DWORD *v46; // rax
  __int64 v47; // rbx
  unsigned __int64 v48; // rbx
  void *v49; // rax
  _BYTE *v50; // r8
  _BYTE *v51; // rax
  unsigned __int64 v52; // rdx
  void *v53; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v54; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v55; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+54h] [rbp-ACh]
  WCHAR SubKey[136]; // [rsp+60h] [rbp-A0h] BYREF

  v10 = 0;
  v11 = a10;
  v12 = (_QWORD *)(a1 + 32);
  v58 = a4;
  v53 = 0;
  phkResult = 0;
  v16 = *v12;
  v55 = 0;
  Type = 0;
  v54 = v12;
  v17 = (*(__int64 (__fastcall **)(_QWORD *))(v16 + 40))(v12);
  if ( v17 )
  {
    while ( 1 )
    {
      if ( v10 )
      {
LABEL_19:
        *((_DWORD *)v53 + 2) = a4;
        *((_DWORD *)v53 + 3) = a5;
        *((_DWORD *)v53 + 1) = 1;
        *((_DWORD *)v53 + 5) = a7;
        return 0;
      }
      v18 = *(_DWORD **)(v17 + 16);
      v53 = v18;
      if ( *v18 == a3 && v18[14] == *(_DWORD *)(a2 + 24) )
      {
        if ( !a3 )
        {
          v20 = *(_QWORD *)(a2 + 8) - *((_QWORD *)v18 + 5);
          if ( !v20 )
            v20 = *(_QWORD *)(a2 + 16) - *((_QWORD *)v18 + 6);
          if ( !v20 )
            v10 = 1;
          goto LABEL_17;
        }
        if ( a3 == 1 )
        {
          v19 = (unsigned int)_o__wcsicmp(a2 + 52, v18 + 21, 0, 1) == 0;
LABEL_10:
          if ( v19 )
            v10 = 1;
          goto LABEL_17;
        }
        if ( (unsigned int)(a3 - 2) <= 1 && *(_QWORD *)(a2 + 8) == *((_QWORD *)v18 + 5) )
        {
          v19 = *(_QWORD *)(a2 + 16) == *((_QWORD *)v18 + 6);
          goto LABEL_10;
        }
      }
LABEL_17:
      v17 = *(_QWORD *)(v17 + 8);
      if ( !v17 )
      {
        if ( !v10 )
          break;
        goto LABEL_19;
      }
    }
  }
  v22 = (char *)malloc(0x378u);
  v53 = v22;
  if ( !v22 )
    return 2147942414LL;
  *((_QWORD *)v22 + 44) = 0;
  *((_QWORD *)v22 + 43) = &CList<IDirectMusicPort *>::`vftable';
  *((_QWORD *)v22 + 45) = 0;
  *((_DWORD *)v22 + 92) = 0;
  v53 = v22;
  memset_0(v22 + 376, 0, 0x200u);
  v23 = 2;
  v24 = (char *)v53 + 32;
  v25 = (_OWORD *)a2;
  v26 = 128;
  do
  {
    *v24 = *v25;
    v24[1] = v25[1];
    v24[2] = v25[2];
    v24[3] = v25[3];
    v24[4] = v25[4];
    v24[5] = v25[5];
    v24[6] = v25[6];
    v27 = v25[7];
    v25 += 8;
    v24[7] = v27;
    v24 += 8;
    --v23;
  }
  while ( v23 );
  *v24 = *v25;
  v24[1] = v25[1];
  v24[2] = v25[2];
  *((_DWORD *)v24 + 12) = *((_DWORD *)v25 + 12);
  v28 = *(_QWORD *)(a2 + 8);
  if ( !v28 )
    v28 = *(_QWORD *)(a2 + 16);
  v29 = v28 != 0;
  if ( hKey )
  {
    v30 = L"%s\\In";
    if ( *(_DWORD *)(a2 + 24) )
      v30 = L"%s\\Out";
    StringCchPrintfW(SubKey, 0x88u, v30, a2 + 52);
    if ( !RegCreateKeyW(hKey, SubKey, &phkResult) )
    {
      lpData = (BYTE *)v53 + 40;
      v55 = 16;
      if ( v29 )
      {
        RegSetValueExA(phkResult, "DMPortGUID", 0, 3u, lpData, 0x10u);
      }
      else
      {
        if ( RegQueryValueExA(phkResult, "DMPortGUID", 0, &Type, lpData, &v55) )
        {
          if ( UuidCreate((UUID *)((char *)v53 + 40)) < 0 )
          {
            LODWORD(v29) = 0;
            goto LABEL_36;
          }
          RegSetValueExA(phkResult, "DMPortGUID", 0, 3u, (const BYTE *)v53 + 40, 0x10u);
        }
        LODWORD(v29) = 1;
      }
LABEL_36:
      RegCloseKey(phkResult);
    }
  }
  if ( v29 || UuidCreate((UUID *)((char *)v53 + 40)) >= 0 )
  {
    v32 = 0;
    v33 = 2147483646;
    v34 = a9;
    *(_DWORD *)v53 = a3;
    *((_DWORD *)v53 + 1) = 1;
    *((_DWORD *)v53 + 2) = a4;
    *((_DWORD *)v53 + 3) = a5;
    *((_DWORD *)v53 + 4) = a6;
    *((_DWORD *)v53 + 5) = a7;
    *((_DWORD *)v53 + 85) = 0;
    if ( a9 )
    {
      v35 = 2147483646;
      v36 = (char *)v53 + 376;
      v26 = 256;
      do
      {
        if ( !v35 )
          break;
        if ( !*v34 )
          break;
        *v36++ = *v34++;
        --v35;
        --v26;
      }
      while ( v26 );
      v37 = v36 - 1;
      if ( v26 )
        v37 = v36;
      *v37 = 0;
    }
    if ( (*(__int64 (__fastcall **)(_QWORD *, void **, __int64))(*v54 + 8LL))(v54, &v53, v26) )
    {
      if ( !a3 || a3 == 3 )
      {
        *((_DWORD *)v53 + 85) = 1;
        v54 = 0;
        v41 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v53 + 43) + 40LL))((char *)v53 + 344);
        if ( v41 )
        {
          while ( !v32 )
          {
            v54 = *(_QWORD **)(v41 + 16);
            v42 = (unsigned __int8 *)v54[2];
            v43 = a10 - v42;
            do
            {
              v44 = v42[v43];
              v45 = *v42 - v44;
              if ( v45 )
                break;
              ++v42;
            }
            while ( v44 );
            v41 = *(_QWORD *)(v41 + 8);
            if ( !v45 )
              v32 = 1;
            if ( !v41 )
            {
              if ( v32 )
                return 0;
              goto LABEL_64;
            }
          }
        }
        else
        {
LABEL_64:
          v46 = malloc(0x20u);
          v54 = v46;
          if ( !v46 )
            return 2147942414LL;
          v47 = -1;
          *v46 = v58;
          *((_DWORD *)v54 + 1) = a5;
          *((_DWORD *)v54 + 2) = a6;
          *((_DWORD *)v54 + 6) = a7;
          do
            ++v47;
          while ( a10[v47] );
          v48 = v47 + 1;
          v49 = operator new[](v48);
          v54[2] = v49;
          v40 = v54;
          v50 = (_BYTE *)v54[2];
          if ( !v50 )
          {
            v39 = 32;
            goto LABEL_50;
          }
          if ( v48 )
          {
            if ( v48 <= 0x7FFFFFFF )
            {
              do
              {
                if ( !v33 )
                  break;
                if ( !*v11 )
                  break;
                *v50++ = *v11++;
                --v33;
                --v48;
              }
              while ( v48 );
              v51 = v50 - 1;
              if ( v48 )
                v51 = v50;
              *v51 = 0;
            }
            else
            {
              *v50 = 0;
            }
          }
          if ( !(*(__int64 (__fastcall **)(char *, _QWORD **))(*((_QWORD *)v53 + 43) + 8LL))((char *)v53 + 344, &v54) )
          {
            operator delete((void *)v54[2], v52);
            v40 = v54;
            v39 = 32;
            goto LABEL_50;
          }
        }
      }
      return 0;
    }
  }
  v38 = v53;
  if ( v53 )
  {
    CList<tagPORTDEST *>::~CList<tagPORTDEST *>((char *)v53 + 344);
    v39 = 888;
    v40 = v38;
LABEL_50:
    operator delete(v40, v39);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800127d0  mov     [rsp-8+arg_10], rbx
0x1800127d5  push    rbp
0x1800127d6  push    rsi
0x1800127d7  push    rdi
0x1800127d8  push    r12
0x1800127da  push    r13
0x1800127dc  push    r14
0x1800127de  push    r15
0x1800127e0  lea     rbp, [rsp-80h]
0x1800127e5  sub     rsp, 180h
0x1800127ec  mov     rax, cs:__security_cookie
0x1800127f3  xor     rax, rsp
0x1800127f6  mov     [rbp+0B0h+var_40], rax
0x1800127fa  mov     r15, [rbp+0B0h+hKey]
0x180012801  xor     ebx, ebx
0x180012803  mov     r13, [rbp+0B0h+arg_48]
0x18001280a  add     rcx, 20h ; ' '
0x18001280e  mov     r12d, r9d
0x180012811  mov     [rsp+1B0h+var_15C], r9d
0x180012816  mov     r14d, r8d
0x180012819  mov     [rsp+1B0h+var_180], rbx
0x18001281e  mov     rdi, rdx
0x180012821  mov     [rsp+1B0h+phkResult], rbx
0x180012826  mov     rax, [rcx]
0x180012829  mov     [rsp+1B0h+var_170], ebx
0x18001282d  mov     [rsp+1B0h+Type], ebx
0x180012831  mov     [rsp+1B0h+var_178], rcx
0x180012836  mov     rax, [rax+28h]
0x18001283a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001283f  xor     r8d, r8d
0x180012842  lea     r9d, [rbx+1]
0x180012846  mov     rsi, rax
0x180012849  test    rax, rax
0x18001284c  jz      loc_180012918
0x180012852  test    ebx, ebx
0x180012854  jnz     loc_1800128E3
0x18001285a  mov     rcx, [rsi+10h]
0x18001285e  mov     [rsp+1B0h+var_180], rcx
0x180012863  cmp     [rcx], r14d
0x180012866  jnz     short loc_1800128D2
0x180012868  mov     eax, [rdi+18h]
0x18001286b  cmp     [rcx+38h], eax
0x18001286e  jnz     short loc_1800128D2
0x180012870  mov     edx, r14d
0x180012873  test    r14d, r14d
0x180012876  jz      short loc_1800128B9
0x180012878  sub     edx, 1
0x18001287b  jz      short loc_1800128A0
0x18001287d  sub     edx, 1
0x180012880  jz      short loc_180012887
0x180012882  cmp     edx, 1
0x180012885  jnz     short loc_1800128D2
0x180012887  mov     rax, [rdi+8]
0x18001288b  cmp     rax, [rcx+28h]
0x18001288f  jnz     short loc_1800128D2
0x180012891  mov     rax, [rdi+10h]
0x180012895  cmp     rax, [rcx+30h]
0x180012899  jnz     short loc_1800128D2
0x18001289b  mov     ebx, r9d
0x18001289e  jmp     short loc_1800128D2
0x1800128a0  lea     rdx, [rcx+54h]
0x1800128a4  lea     rcx, [rdi+34h]
0x1800128a8  call    cs:__imp__o__wcsicmp
0x1800128ae  xor     r8d, r8d
0x1800128b1  test    eax, eax
0x1800128b3  lea     r9d, [r8+1]
0x1800128b7  jmp     short loc_180012899
0x1800128b9  mov     rax, [rdi+8]
0x1800128bd  sub     rax, [rcx+28h]
0x1800128c1  jnz     short loc_1800128CB
0x1800128c3  mov     rax, [rdi+10h]
0x1800128c7  sub     rax, [rcx+30h]
0x1800128cb  test    rax, rax
0x1800128ce  cmovz   ebx, r9d
0x1800128d2  mov     rsi, [rsi+8]
0x1800128d6  test    rsi, rsi
0x1800128d9  jnz     loc_180012852
0x1800128df  test    ebx, ebx
0x1800128e1  jz      short loc_18001291A
0x1800128e3  mov     rax, [rsp+1B0h+var_180]
0x1800128e8  mov     ecx, [rbp+0B0h+arg_20]
0x1800128ee  mov     [rax+8], r12d
0x1800128f2  mov     rax, [rsp+1B0h+var_180]
0x1800128f7  mov     [rax+0Ch], ecx
0x1800128fa  mov     rax, [rsp+1B0h+var_180]
0x1800128ff  mov     ecx, [rbp+0B0h+arg_30]
0x180012905  mov     [rax+4], r9d
0x180012909  mov     rax, [rsp+1B0h+var_180]
0x18001290e  mov     [rax+14h], ecx
0x180012911  xor     eax, eax
0x180012913  jmp     loc_180012C15
0x180012918  xor     esi, esi
0x18001291a  mov     ecx, 378h; Size
0x18001291f  call    cs:__imp_malloc
0x180012925  mov     [rsp+1B0h+var_180], rax
0x18001292a  test    rax, rax
0x18001292d  jz      loc_180012C10
0x180012933  lea     rcx, ??_7?$CList@PEAUIDirectMusicPort@@@@6B@; const CList<IDirectMusicPort *>::`vftable'
0x18001293a  mov     [rax+160h], rsi
0x180012941  mov     [rax+158h], rcx
0x180012948  xor     edx, edx; Val
0x18001294a  mov     [rax+168h], rsi
0x180012951  lea     rcx, [rax+178h]; void *
0x180012958  mov     [rax+170h], esi
0x18001295e  mov     r8d, 200h; Size
0x180012964  mov     [rsp+1B0h+var_180], rax
0x180012969  call    memset_0
0x18001296e  mov     rcx, [rsp+1B0h+var_180]
0x180012973  mov     edx, 2
0x180012978  add     rcx, 20h ; ' '
0x18001297c  mov     rax, rdi
0x18001297f  lea     r8d, [rdx+7Eh]
0x180012983  movups  xmm0, xmmword ptr [rax]
0x180012986  movups  xmmword ptr [rcx], xmm0
0x180012989  movups  xmm1, xmmword ptr [rax+10h]
0x18001298d  movups  xmmword ptr [rcx+10h], xmm1
0x180012991  movups  xmm0, xmmword ptr [rax+20h]
0x180012995  movups  xmmword ptr [rcx+20h], xmm0
0x180012999  movups  xmm1, xmmword ptr [rax+30h]
0x18001299d  movups  xmmword ptr [rcx+30h], xmm1
0x1800129a1  movups  xmm0, xmmword ptr [rax+40h]
0x1800129a5  movups  xmmword ptr [rcx+40h], xmm0
0x1800129a9  movups  xmm1, xmmword ptr [rax+50h]
0x1800129ad  movups  xmmword ptr [rcx+50h], xmm1
0x1800129b1  movups  xmm0, xmmword ptr [rax+60h]
0x1800129b5  movups  xmmword ptr [rcx+60h], xmm0
0x1800129b9  movups  xmm1, xmmword ptr [rax+70h]
0x1800129bd  add     rax, r8
0x1800129c0  movups  xmmword ptr [rcx+70h], xmm1
0x1800129c4  add     rcx, r8
0x1800129c7  sub     rdx, 1
0x1800129cb  jnz     short loc_180012983
0x1800129cd  movups  xmm0, xmmword ptr [rax]
0x1800129d0  movups  xmmword ptr [rcx], xmm0
0x1800129d3  movups  xmm1, xmmword ptr [rax+10h]
0x1800129d7  movups  xmmword ptr [rcx+10h], xmm1
0x1800129db  movups  xmm0, xmmword ptr [rax+20h]
0x1800129df  movups  xmmword ptr [rcx+20h], xmm0
0x1800129e3  mov     eax, [rax+30h]
0x1800129e6  mov     [rcx+30h], eax
0x1800129e9  mov     rax, [rdi+8]
0x1800129ed  sub     rax, cs:qword_1800257A0
0x1800129f4  jnz     short loc_180012A01
0x1800129f6  mov     rax, [rdi+10h]
0x1800129fa  sub     rax, cs:qword_1800257A8
0x180012a01  test    rax, rax
0x180012a04  mov     ebx, esi
0x180012a06  setnz   bl
0x180012a09  test    r15, r15
0x180012a0c  jz      loc_180012B07
0x180012a12  cmp     [rdi+18h], esi
0x180012a15  lea     rax, aSOut; "%s\\Out"
0x180012a1c  lea     r8, aSIn; "%s\\In"
0x180012a23  mov     edx, 88h; unsigned __int64
0x180012a28  cmovnz  r8, rax; unsigned __int16 *
0x180012a2c  lea     r9, [rdi+34h]
0x180012a30  lea     rcx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x180012a35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012a3a  lea     r8, [rsp+1B0h+phkResult]; phkResult
0x180012a3f  mov     rcx, r15; hKey
0x180012a42  lea     rdx, [rsp+1B0h+SubKey]; lpSubKey
0x180012a47  call    cs:__imp_RegCreateKeyW
0x180012a4d  test    eax, eax
0x180012a4f  jnz     loc_180012B07
0x180012a55  lea     edi, [rax+10h]
0x180012a58  mov     rax, [rsp+1B0h+var_180]
0x180012a5d  add     rax, 28h ; '('
0x180012a61  mov     [rsp+1B0h+var_170], edi
0x180012a65  lea     rdx, ValueName; "DMPortGUID"
0x180012a6c  test    ebx, ebx
0x180012a6e  jz      short loc_180012A8D
0x180012a70  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x180012a75  lea     r9d, [rdi-0Dh]; dwType
0x180012a79  mov     [rsp+1B0h+cbData], edi; cbData
0x180012a7d  xor     r8d, r8d; Reserved
0x180012a80  mov     [rsp+1B0h+lpData], rax; lpData
0x180012a85  call    cs:__imp_RegSetValueExA
0x180012a8b  jmp     short loc_180012AFC
0x180012a8d  lea     rcx, [rsp+1B0h+var_170]
0x180012a92  xor     r8d, r8d; lpReserved
0x180012a95  mov     qword ptr [rsp+1B0h+cbData], rcx; lpcbData
0x180012a9a  lea     r9, [rsp+1B0h+Type]; lpType
0x180012a9f  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x180012aa4  mov     [rsp+1B0h+lpData], rax; lpData
0x180012aa9  call    cs:__imp_RegQueryValueExA
0x180012aaf  test    eax, eax
0x180012ab1  jz      short loc_180012AF7
0x180012ab3  mov     rcx, [rsp+1B0h+var_180]
0x180012ab8  add     rcx, 28h ; '('; Uuid
0x180012abc  call    cs:__imp_UuidCreate
0x180012ac2  test    eax, eax
0x180012ac4  js      loc_180012C3C
0x180012aca  mov     rax, [rsp+1B0h+var_180]
0x180012acf  lea     rdx, ValueName; "DMPortGUID"
0x180012ad6  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x180012adb  add     rax, 28h ; '('
0x180012adf  mov     [rsp+1B0h+cbData], edi; cbData
0x180012ae3  mov     r9d, 3; dwType
0x180012ae9  xor     r8d, r8d; Reserved
0x180012aec  mov     [rsp+1B0h+lpData], rax; lpData
0x180012af1  call    cs:__imp_RegSetValueExA
0x180012af7  mov     ebx, 1
0x180012afc  mov     rcx, [rsp+1B0h+phkResult]; hKey
0x180012b01  call    cs:__imp_RegCloseKey
0x180012b07  test    ebx, ebx
0x180012b09  jnz     short loc_180012B22
0x180012b0b  mov     rcx, [rsp+1B0h+var_180]
0x180012b10  add     rcx, 28h ; '('; Uuid
0x180012b14  call    cs:__imp_UuidCreate
0x180012b1a  test    eax, eax
0x180012b1c  js      loc_180012BED
0x180012b22  mov     rax, [rsp+1B0h+var_180]
0x180012b27  xor     ebx, ebx
0x180012b29  mov     esi, [rbp+0B0h+arg_20]
0x180012b2f  mov     r10d, 1
0x180012b35  mov     r15d, [rbp+0B0h+arg_28]
0x180012b3c  mov     edi, 7FFFFFFEh
0x180012b41  mov     rdx, [rbp+0B0h+arg_40]
0x180012b48  mov     [rax], r14d
0x180012b4b  mov     rax, [rsp+1B0h+var_180]
0x180012b50  mov     [rax+4], r10d
0x180012b54  mov     rax, [rsp+1B0h+var_180]
0x180012b59  mov     [rax+8], r12d
0x180012b5d  mov     rax, [rsp+1B0h+var_180]
0x180012b62  mov     r12d, [rbp+0B0h+arg_30]
0x180012b69  mov     [rax+0Ch], esi
0x180012b6c  mov     rax, [rsp+1B0h+var_180]
0x180012b71  mov     [rax+10h], r15d
0x180012b75  mov     rax, [rsp+1B0h+var_180]
0x180012b7a  mov     [rax+14h], r12d
0x180012b7e  mov     rax, [rsp+1B0h+var_180]
0x180012b83  mov     [rax+154h], ebx
0x180012b89  test    rdx, rdx
0x180012b8c  jz      short loc_180012BD2
0x180012b8e  mov     rax, [rsp+1B0h+var_180]
0x180012b93  mov     ecx, edi
0x180012b95  add     rax, 178h
0x180012b9b  mov     r8d, 100h
0x180012ba1  test    rcx, rcx
0x180012ba4  jz      short loc_180012BC4
0x180012ba6  movzx   r9d, word ptr [rdx]
0x180012baa  test    r9w, r9w
0x180012bae  jz      short loc_180012BC4
0x180012bb0  mov     [rax], r9w
0x180012bb4  add     rdx, 2
0x180012bb8  add     rax, 2
0x180012bbc  sub     rcx, r10
0x180012bbf  sub     r8, r10
0x180012bc2  jnz     short loc_180012BA1
0x180012bc4  test    r8, r8
0x180012bc7  lea     rdx, [rax-2]
0x180012bcb  cmovnz  rdx, rax
0x180012bcf  mov     [rdx], bx
0x180012bd2  mov     rcx, [rsp+1B0h+var_178]
0x180012bd7  lea     rdx, [rsp+1B0h+var_180]
0x180012bdc  mov     rax, [rcx]
0x180012bdf  mov     rax, [rax+8]
0x180012be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012be8  test    rax, rax
0x180012beb  jnz     short loc_180012C43
0x180012bed  mov     rbx, [rsp+1B0h+var_180]
0x180012bf2  test    rbx, rbx
0x180012bf5  jz      short loc_180012C10
0x180012bf7  lea     rcx, [rbx+158h]
0x180012bfe  call    ??1?$CList@PEAUtagPORTDEST@@@@UEAA@XZ; CList<tagPORTDEST *>::~CList<tagPORTDEST *>(void)
0x180012c03  mov     edx, 378h; unsigned __int64
0x180012c08  mov     rcx, rbx; void *
0x180012c0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c10  mov     eax, 8007000Eh
0x180012c15  mov     rcx, [rbp+0B0h+var_40]
0x180012c19  xor     rcx, rsp; StackCookie
0x180012c1c  call    __security_check_cookie
0x180012c21  mov     rbx, [rsp+1B0h+arg_10]
0x180012c29  add     rsp, 180h
0x180012c30  pop     r15
0x180012c32  pop     r14
0x180012c34  pop     r13
0x180012c36  pop     r12
0x180012c38  pop     rdi
0x180012c39  pop     rsi
0x180012c3a  pop     rbp
0x180012c3b  retn
0x180012c3c  mov     ebx, esi
0x180012c3e  jmp     loc_180012AFC
0x180012c43  test    r14d, r14d
0x180012c46  jz      short loc_180012C52
0x180012c48  cmp     r14d, 3
0x180012c4c  jnz     loc_180012911
0x180012c52  mov     rax, [rsp+1B0h+var_180]
0x180012c57  xor     r14d, r14d
0x180012c5a  mov     dword ptr [rax+154h], 1
0x180012c64  mov     rcx, [rsp+1B0h+var_180]
0x180012c69  add     rcx, 158h
0x180012c70  mov     [rsp+1B0h+var_178], r14
0x180012c75  mov     rax, [rcx]
0x180012c78  mov     rax, [rax+28h]
0x180012c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c81  test    rax, rax
0x180012c84  jz      short loc_180012CD2
0x180012c86  lea     r10d, [r14+1]
  ... truncated ...
```
