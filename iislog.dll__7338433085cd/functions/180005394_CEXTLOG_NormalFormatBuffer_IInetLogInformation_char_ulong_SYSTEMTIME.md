# CEXTLOG::NormalFormatBuffer(IInetLogInformation *,char *,ulong *,_SYSTEMTIME *)

- ea: `0x180005394`
- end: `0x180005b2c`
- name: `?NormalFormatBuffer@CEXTLOG@@IEAAHPEAVIInetLogInformation@@PEADPEAKPEAU_SYSTEMTIME@@@Z`
- size: `1944`
- prototype: `__int64 __fastcall(CEXTLOG *__hidden this, struct IInetLogInformation *, char *, unsigned int *, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004160`

## callees

- `0x1800022a8`
- `0x180003fcc`
- `0x180005394`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x1800053fd`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x1800053fd`
- `KERNEL32!SetLastError` at `0x180005afd`
- `KERNEL32!SetLastError` at `0x180005afd`

## pseudocode

```c
__int64 __fastcall CEXTLOG::NormalFormatBuffer(
        CEXTLOG *this,
        struct IInetLogInformation *a2,
        char *a3,
        unsigned int *a4,
        struct _SYSTEMTIME *a5)
{
  __int64 v5; // r13
  bool v7; // zf
  struct _SYSTEMTIME *v9; // rdx
  unsigned int v10; // r12d
  char *v11; // rsi
  unsigned int FormattedDateTime; // r14d
  __int64 v14; // rsi
  char *v15; // rax
  char *v16; // rax
  char *v17; // rax
  char *v18; // rax
  char *v19; // rax
  unsigned int v20; // eax
  char *v21; // rax
  char *v22; // rax
  size_t v23; // rdx
  char *v24; // r10
  char v25; // cl
  char *v26; // rax
  size_t v27; // rdx
  char *v28; // r10
  char v29; // cl
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  char *v35; // rax
  char *v36; // rax
  char *v37; // r10
  char *v38; // rdi
  unsigned int v39; // r8d
  size_t v40; // rdx
  char *v41; // rcx
  char i; // al
  unsigned int v43; // r9d
  char *v44; // r8
  char *v45; // r10
  size_t v46; // rdx
  unsigned int v47; // r9d
  char *v48; // r8
  char *v49; // r10
  size_t v50; // rdx
  unsigned int v51; // edx
  char v52; // al
  char *v53; // rcx
  char v54; // al
  char v55; // al
  __int64 result; // rax
  unsigned int v57; // [rsp+30h] [rbp-51h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-4Dh] BYREF
  char *v59; // [rsp+40h] [rbp-41h]
  char Buffer[32]; // [rsp+48h] [rbp-39h] BYREF
  char Src[32]; // [rsp+68h] [rbp-19h] BYREF

  v59 = a3;
  Size[0] = 0;
  v5 = -1;
  *a3 = 0;
  v7 = (*((_BYTE *)this + 1576) & 3) == 0;
  v9 = a5;
  v10 = 1;
  v11 = a3;
  v57 = 0;
  *(_QWORD *)&Size[1] = a3;
  if ( !v7 )
  {
    FormattedDateTime = CACHED_DATETIME_FORMATS::GetFormattedDateTime((CEXTLOG *)((char *)this + 1584), a5, Src);
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
    if ( (*((_BYTE *)this + 1576) & 1) != 0 )
      CopyFieldToBuffer(Src, (unsigned int)v14, (char **)&Size[1], &v57, *a4);
    if ( (*((_BYTE *)this + 1576) & 2) != 0 )
      CopyFieldToBuffer(
        &Src[(unsigned int)v14 + 1],
        FormattedDateTime - (unsigned int)v14 - 1,
        (char **)&Size[1],
        &v57,
        *a4);
    v11 = v59;
  }
  if ( (*((_BYTE *)this + 1576) & 4) != 0 )
  {
    v15 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v15, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_BYTE *)this + 1576) & 8) != 0 )
  {
    v16 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 48LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v16, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_BYTE *)this + 1576) & 0x10) != 0 )
  {
    v17 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v17, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_BYTE *)this + 1576) & 0x20) != 0 )
  {
    v18 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 32LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v18, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_BYTE *)this + 1576) & 0x40) != 0 )
  {
    v19 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 56LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v19, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x8000) != 0 )
  {
    v20 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 136LL))(
            a2,
            v9);
    Size[0] = FastDwToA(Buffer, v20);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( *((char *)this + 1576) < 0 )
  {
    v21 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 64LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v21, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x100) != 0 )
  {
    v22 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 72LL))(
                    a2,
                    0,
                    Size);
    v23 = Size[0];
    v24 = v22;
    if ( Size[0] > 0x1000u || Size[0] + v57 > 0x2800 )
    {
      v23 = 3;
      v24 = szDotDot;
      Size[0] = 3;
    }
    else if ( v22 )
    {
      v25 = *v22;
      if ( *v22 )
      {
        do
        {
          if ( v25 == 32 || v25 == 9 )
            *v22 = 43;
          v25 = *++v22;
        }
        while ( *v22 );
        v23 = Size[0];
      }
    }
    CopyFieldToBuffer(v24, v23, (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x200) != 0 )
  {
    v26 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 80LL))(
                    a2,
                    0,
                    Size);
    v27 = Size[0];
    v28 = v26;
    if ( Size[0] > 0x1000u || Size[0] + v57 > 0x2800 )
    {
      v27 = 3;
      v28 = szDotDot;
      Size[0] = 3;
    }
    else if ( v26 )
    {
      v29 = *v26;
      if ( *v26 )
      {
        do
        {
          if ( v29 == 32 || v29 == 9 )
            *v26 = 43;
          v29 = *++v26;
        }
        while ( *v26 );
        v27 = Size[0];
      }
    }
    CopyFieldToBuffer(v28, v27, (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x400) != 0 )
  {
    v30 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            v9);
    Size[0] = FastDwToA(Buffer, v30);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x800) != 0 )
  {
    v31 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 120LL))(
            a2,
            v9);
    Size[0] = FastDwToA(Buffer, v31);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x1000) != 0 )
  {
    v32 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 104LL))(
            a2,
            v9);
    Size[0] = FastDwToA(Buffer, v32);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x2000) != 0 )
  {
    v33 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 112LL))(
            a2,
            v9);
    Size[0] = FastDwToA(Buffer, v33);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x4000) != 0 )
  {
    v34 = (*(__int64 (__fastcall **)(struct IInetLogInformation *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 96LL))(a2, v9);
    Size[0] = FastDwToA(Buffer, v34);
    CopyFieldToBuffer(Buffer, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x80000) != 0 )
  {
    v35 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 144LL))(
                    a2,
                    0,
                    Size);
    CopyFieldToBuffer(v35, Size[0], (char **)&Size[1], &v57, *a4);
  }
  if ( (*((_DWORD *)this + 394) & 0x170000) != 0 )
  {
    v36 = (char *)(*(__int64 (__fastcall **)(struct IInetLogInformation *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    0,
                    Size);
    v37 = v36;
    v38 = v36;
    if ( (*((_DWORD *)this + 394) & 0x100000) != 0 && v36 )
    {
      v39 = *a4;
      v40 = -1;
      do
        ++v40;
      while ( v36[v40] );
      v38 = &v36[(unsigned int)v40 + 1];
      if ( (unsigned int)v40 > 0x1000 || (unsigned int)v40 + v57 > 0x2800 )
      {
        v37 = szDotDot;
        v40 = 3;
      }
      else
      {
        v41 = v36;
        for ( i = *v36; i; i = *v41 )
        {
          if ( i == 32 || i == 9 )
            *v41 = 43;
          ++v41;
        }
      }
      CopyFieldToBuffer(v37, v40, (char **)&Size[1], &v57, v39);
    }
    if ( (*((_DWORD *)this + 394) & 0x10000) != 0 && v38 )
    {
      v43 = *a4;
      v44 = v38;
      v45 = v38;
      v46 = -1;
      do
        ++v46;
      while ( v38[v46] );
      v38 += (unsigned int)v46 + 1;
      if ( (unsigned int)v46 <= 0x1000 && (unsigned int)v46 + v57 <= 0x2800 )
      {
        while ( 1 )
        {
          v54 = *v44;
          if ( !*v44 )
            break;
          if ( v54 == 32 || v54 == 9 )
            *v44 = 43;
          ++v44;
        }
      }
      else
      {
        v45 = szDotDot;
        v46 = 3;
      }
      CopyFieldToBuffer(v45, v46, (char **)&Size[1], &v57, v43);
    }
    if ( (*((_DWORD *)this + 394) & 0x20000) != 0 && v38 )
    {
      v47 = *a4;
      v48 = v38;
      v49 = v38;
      v50 = -1;
      do
        ++v50;
      while ( v38[v50] );
      v38 += (unsigned int)v50 + 1;
      if ( (unsigned int)v50 <= 0x1000 && (unsigned int)v50 + v57 <= 0x2800 )
      {
        while ( 1 )
        {
          v55 = *v48;
          if ( !*v48 )
            break;
          if ( v55 == 32 || v55 == 9 )
            *v48 = 43;
          ++v48;
        }
      }
      else
      {
        v49 = szDotDot;
        v50 = 3;
      }
      CopyFieldToBuffer(v49, v50, (char **)&Size[1], &v57, v47);
    }
    if ( (*((_DWORD *)this + 394) & 0x40000) != 0 && v38 )
    {
      v51 = *a4;
      do
        ++v5;
      while ( v38[v5] );
      if ( (unsigned int)v5 > 0x1000 || (unsigned int)v5 + v57 > 0x2800 )
      {
        v38 = szDotDot;
        LODWORD(v5) = 3;
      }
      else
      {
        v52 = *v38;
        if ( *v38 )
        {
          v53 = v38;
          do
          {
            if ( v52 == 32 || v52 == 9 )
              *v53 = 43;
            v52 = *++v53;
          }
          while ( *v53 );
        }
      }
      CopyFieldToBuffer(v38, (unsigned int)v5, (char **)&Size[1], &v57, v51);
    }
  }
  if ( *v11 )
  {
    --*(_QWORD *)&Size[1];
    --v57;
  }
  v57 += 2;
  if ( v57 > *a4 )
  {
    v10 = 0;
    SetLastError(0x7Au);
  }
  else
  {
    **(_WORD **)&Size[1] = 2573;
  }
  result = v10;
  *a4 = v57;
  return result;
}

```

## disassembly

```asm
0x180005394  push    rbp
0x180005396  push    rbx
0x180005397  push    rsi
0x180005398  push    rdi
0x180005399  push    r12
0x18000539b  push    r13
0x18000539d  push    r14
0x18000539f  push    r15
0x1800053a1  lea     rbp, [rsp-17h]
0x1800053a6  sub     rsp, 98h
0x1800053ad  mov     rax, cs:__security_cookie
0x1800053b4  xor     rax, rsp
0x1800053b7  mov     [rbp+4Fh+var_48], rax
0x1800053bb  xor     r14d, r14d
0x1800053be  mov     [rbp+4Fh+var_90], r8
0x1800053c2  mov     dword ptr [rbp+4Fh+Size], r14d
0x1800053c6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800053ca  mov     [r8], r14b
0x1800053cd  mov     rdi, rdx
0x1800053d0  test    byte ptr [rcx+628h], 3
0x1800053d7  mov     r15, r9
0x1800053da  mov     rdx, [rbp+4Fh+arg_20]
0x1800053de  lea     r12d, [r14+1]
0x1800053e2  mov     rsi, r8
0x1800053e5  mov     [rbp+4Fh+var_A0], r14d
0x1800053e9  mov     rbx, rcx
0x1800053ec  mov     qword ptr [rbp+4Fh+Size+4], r8
0x1800053f0  jz      short loc_18000546F
0x1800053f2  add     rcx, 630h
0x1800053f9  lea     r8, [rbp+4Fh+Src]
0x1800053fd  call    cs:__imp_?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedDateTime(_SYSTEMTIME const *,char *)
0x180005403  mov     r14d, eax
0x180005406  mov     rsi, r13
0x180005409  lea     rax, [rbp+4Fh+Src]
0x18000540d  inc     rsi
0x180005410  cmp     byte ptr [rax+rsi], 0
0x180005414  jnz     short loc_18000540D
0x180005416  test    [rbx+628h], r12b
0x18000541d  jz      short loc_180005439
0x18000541f  mov     eax, [r15]
0x180005422  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x180005426  lea     r8, [rbp+4Fh+Size+4]; char **
0x18000542a  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x18000542e  mov     edx, esi; Size
0x180005430  lea     rcx, [rbp+4Fh+Src]; Src
0x180005434  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005439  test    byte ptr [rbx+628h], 2
0x180005440  jz      short loc_180005468
0x180005442  mov     eax, esi
0x180005444  lea     rcx, [rbp+4Fh+var_67]
0x180005448  sub     r14d, esi
0x18000544b  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18000544f  sub     r14d, r12d
0x180005452  lea     r8, [rbp+4Fh+Size+4]; char **
0x180005456  add     rcx, rax; Src
0x180005459  mov     edx, r14d; Size
0x18000545c  mov     eax, [r15]
0x18000545f  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005463  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005468  mov     rsi, [rbp+4Fh+var_90]
0x18000546c  xor     r14d, r14d
0x18000546f  test    byte ptr [rbx+628h], 4
0x180005476  jz      short loc_1800054A7
0x180005478  mov     rax, [rdi]
0x18000547b  lea     r8, [rbp+4Fh+Size]
0x18000547f  xor     edx, edx
0x180005481  mov     rcx, rdi
0x180005484  mov     rax, [rax+28h]
0x180005488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000548d  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x180005490  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x180005494  mov     rcx, rax; Src
0x180005497  lea     r8, [rbp+4Fh+Size+4]; char **
0x18000549b  mov     eax, [r15]
0x18000549e  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x1800054a2  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x1800054a7  test    byte ptr [rbx+628h], 8
0x1800054ae  jz      short loc_1800054DF
0x1800054b0  mov     rax, [rdi]
0x1800054b3  lea     r8, [rbp+4Fh+Size]
0x1800054b7  xor     edx, edx
0x1800054b9  mov     rcx, rdi
0x1800054bc  mov     rax, [rax+30h]
0x1800054c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c5  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x1800054c8  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x1800054cc  mov     rcx, rax; Src
0x1800054cf  lea     r8, [rbp+4Fh+Size+4]; char **
0x1800054d3  mov     eax, [r15]
0x1800054d6  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x1800054da  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x1800054df  test    byte ptr [rbx+628h], 10h
0x1800054e6  jz      short loc_180005517
0x1800054e8  mov     rax, [rdi]
0x1800054eb  lea     r8, [rbp+4Fh+Size]
0x1800054ef  xor     edx, edx
0x1800054f1  mov     rcx, rdi
0x1800054f4  mov     rax, [rax+18h]
0x1800054f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fd  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x180005500  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x180005504  mov     rcx, rax; Src
0x180005507  lea     r8, [rbp+4Fh+Size+4]; char **
0x18000550b  mov     eax, [r15]
0x18000550e  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005512  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005517  test    byte ptr [rbx+628h], 20h
0x18000551e  jz      short loc_18000554F
0x180005520  mov     rax, [rdi]
0x180005523  lea     r8, [rbp+4Fh+Size]
0x180005527  xor     edx, edx
0x180005529  mov     rcx, rdi
0x18000552c  mov     rax, [rax+20h]
0x180005530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005535  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x180005538  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18000553c  mov     rcx, rax; Src
0x18000553f  lea     r8, [rbp+4Fh+Size+4]; char **
0x180005543  mov     eax, [r15]
0x180005546  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x18000554a  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x18000554f  test    byte ptr [rbx+628h], 40h
0x180005556  jz      short loc_180005587
0x180005558  mov     rax, [rdi]
0x18000555b  lea     r8, [rbp+4Fh+Size]
0x18000555f  xor     edx, edx
0x180005561  mov     rcx, rdi
0x180005564  mov     rax, [rax+38h]
0x180005568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556d  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x180005570  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x180005574  mov     rcx, rax; Src
0x180005577  lea     r8, [rbp+4Fh+Size+4]; char **
0x18000557b  mov     eax, [r15]
0x18000557e  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005582  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005587  test    dword ptr [rbx+628h], 8000h
0x180005591  jz      short loc_1800055CD
0x180005593  mov     rax, [rdi]
0x180005596  mov     rcx, rdi
0x180005599  mov     rax, [rax+88h]
0x1800055a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a5  mov     edx, eax; Value
0x1800055a7  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x1800055ab  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x1800055b0  mov     edx, eax; Size
0x1800055b2  mov     dword ptr [rbp+4Fh+Size], eax
0x1800055b5  mov     eax, [r15]
0x1800055b8  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x1800055bc  lea     r8, [rbp+4Fh+Size+4]; char **
0x1800055c0  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x1800055c4  lea     rcx, [rbp+4Fh+Buffer]; Src
0x1800055c8  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x1800055cd  test    byte ptr [rbx+628h], 80h
0x1800055d4  jz      short loc_180005605
0x1800055d6  mov     rax, [rdi]
0x1800055d9  lea     r8, [rbp+4Fh+Size]
0x1800055dd  xor     edx, edx
0x1800055df  mov     rcx, rdi
0x1800055e2  mov     rax, [rax+40h]
0x1800055e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055eb  mov     edx, dword ptr [rbp+4Fh+Size]; Size
0x1800055ee  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x1800055f2  mov     rcx, rax; Src
0x1800055f5  lea     r8, [rbp+4Fh+Size+4]; char **
0x1800055f9  mov     eax, [r15]
0x1800055fc  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005600  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005605  test    dword ptr [rbx+628h], 100h
0x18000560f  jz      short loc_18000568D
0x180005611  mov     rax, [rdi]
0x180005614  lea     r8, [rbp+4Fh+Size]
0x180005618  xor     edx, edx
0x18000561a  mov     rcx, rdi
0x18000561d  mov     rax, [rax+48h]
0x180005621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005626  mov     edx, dword ptr [rbp+4Fh+Size]
0x180005629  mov     r10, rax
0x18000562c  cmp     edx, 1000h
0x180005632  ja      short loc_180005667
0x180005634  mov     ecx, [rbp+4Fh+var_A0]
0x180005637  add     ecx, edx
0x180005639  cmp     ecx, 2800h
0x18000563f  ja      short loc_180005667
0x180005641  test    rax, rax
0x180005644  jz      short loc_180005676
0x180005646  mov     cl, [rax]
0x180005648  test    cl, cl
0x18000564a  jz      short loc_180005676
0x18000564c  cmp     cl, 20h ; ' '
0x18000564f  jz      short loc_180005656
0x180005651  cmp     cl, 9
0x180005654  jnz     short loc_180005659
0x180005656  mov     byte ptr [rax], 2Bh ; '+'
0x180005659  add     rax, r12
0x18000565c  mov     cl, [rax]
0x18000565e  test    cl, cl
0x180005660  jnz     short loc_18000564C
0x180005662  mov     edx, dword ptr [rbp+4Fh+Size]
0x180005665  jmp     short loc_180005676
0x180005667  mov     edx, 3; Size
0x18000566c  lea     r10, ?szDotDot@@3PADA; char near * szDotDot
0x180005673  mov     dword ptr [rbp+4Fh+Size], edx
0x180005676  mov     eax, [r15]
0x180005679  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18000567d  lea     r8, [rbp+4Fh+Size+4]; char **
0x180005681  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005685  mov     rcx, r10; Src
0x180005688  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x18000568d  test    dword ptr [rbx+628h], 200h
0x180005697  jz      short loc_180005715
0x180005699  mov     rax, [rdi]
0x18000569c  lea     r8, [rbp+4Fh+Size]
0x1800056a0  xor     edx, edx
0x1800056a2  mov     rcx, rdi
0x1800056a5  mov     rax, [rax+50h]
0x1800056a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ae  mov     edx, dword ptr [rbp+4Fh+Size]
0x1800056b1  mov     r10, rax
0x1800056b4  cmp     edx, 1000h
0x1800056ba  ja      short loc_1800056EF
0x1800056bc  mov     ecx, [rbp+4Fh+var_A0]
0x1800056bf  add     ecx, edx
0x1800056c1  cmp     ecx, 2800h
0x1800056c7  ja      short loc_1800056EF
0x1800056c9  test    rax, rax
0x1800056cc  jz      short loc_1800056FE
0x1800056ce  mov     cl, [rax]
0x1800056d0  test    cl, cl
0x1800056d2  jz      short loc_1800056FE
0x1800056d4  cmp     cl, 20h ; ' '
0x1800056d7  jz      short loc_1800056DE
0x1800056d9  cmp     cl, 9
0x1800056dc  jnz     short loc_1800056E1
0x1800056de  mov     byte ptr [rax], 2Bh ; '+'
0x1800056e1  add     rax, r12
0x1800056e4  mov     cl, [rax]
0x1800056e6  test    cl, cl
0x1800056e8  jnz     short loc_1800056D4
0x1800056ea  mov     edx, dword ptr [rbp+4Fh+Size]
0x1800056ed  jmp     short loc_1800056FE
0x1800056ef  mov     edx, 3; Size
0x1800056f4  lea     r10, ?szDotDot@@3PADA; char near * szDotDot
0x1800056fb  mov     dword ptr [rbp+4Fh+Size], edx
0x1800056fe  mov     eax, [r15]
0x180005701  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x180005705  lea     r8, [rbp+4Fh+Size+4]; char **
0x180005709  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x18000570d  mov     rcx, r10; Src
0x180005710  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x180005715  test    dword ptr [rbx+628h], 400h
0x18000571f  jz      short loc_18000575B
0x180005721  mov     rax, [rdi]
0x180005724  mov     rcx, rdi
0x180005727  mov     rax, [rax+80h]
0x18000572e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005733  mov     edx, eax; Value
0x180005735  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x180005739  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000573e  mov     edx, eax; Size
0x180005740  mov     dword ptr [rbp+4Fh+Size], eax
0x180005743  mov     eax, [r15]
0x180005746  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18000574a  lea     r8, [rbp+4Fh+Size+4]; char **
0x18000574e  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005752  lea     rcx, [rbp+4Fh+Buffer]; Src
0x180005756  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x18000575b  test    dword ptr [rbx+628h], 800h
0x180005765  jz      short loc_18000579E
0x180005767  mov     rax, [rdi]
0x18000576a  mov     rcx, rdi
0x18000576d  mov     rax, [rax+78h]
0x180005771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005776  mov     edx, eax; Value
0x180005778  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x18000577c  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x180005781  mov     edx, eax; Size
0x180005783  mov     dword ptr [rbp+4Fh+Size], eax
0x180005786  mov     eax, [r15]
0x180005789  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x18000578d  lea     r8, [rbp+4Fh+Size+4]; char **
0x180005791  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x180005795  lea     rcx, [rbp+4Fh+Buffer]; Src
0x180005799  call    ?CopyFieldToBuffer@@YAHPEADKPEAPEADPEAKK@Z; CopyFieldToBuffer(char *,ulong,char * *,ulong *,ulong)
0x18000579e  test    dword ptr [rbx+628h], 1000h
0x1800057a8  jz      short loc_1800057E1
0x1800057aa  mov     rax, [rdi]
0x1800057ad  mov     rcx, rdi
0x1800057b0  mov     rax, [rax+68h]
0x1800057b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b9  mov     edx, eax; Value
0x1800057bb  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x1800057bf  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x1800057c4  mov     edx, eax; Size
0x1800057c6  mov     dword ptr [rbp+4Fh+Size], eax
0x1800057c9  mov     eax, [r15]
0x1800057cc  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x1800057d0  lea     r8, [rbp+4Fh+Size+4]; char **
0x1800057d4  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x1800057d8  lea     rcx, [rbp+4Fh+Buffer]; Src
  ... truncated ...
```
