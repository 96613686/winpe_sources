# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18000eed8`
- end: `0x18000f1c7`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `751`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd58`
- `0x18001dd0c`
- `0x18001de8c`

## callees

- `0x180005688`
- `0x18000ebb4`
- `0x18000eed8`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000ef6a`
- `msvcrt!wcsstr` at `0x18000ef8b`
- `msvcrt!wcsstr` at `0x18000f03b`
- `msvcrt!wcsstr` at `0x18000f123`
- `msvcrt!wcsstr` at `0x18000ef6a`
- `msvcrt!wcsstr` at `0x18000ef8b`
- `msvcrt!wcsstr` at `0x18000f03b`
- `msvcrt!wcsstr` at `0x18000f123`
- `msvcrt!memmove_s` at `0x18000f092`
- `msvcrt!memmove_s` at `0x18000f092`
- `msvcrt!memcpy_s` at `0x18000f0d3`
- `msvcrt!memcpy_s` at `0x18000f0d3`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1,
        const wchar_t *a2,
        _WORD *a3)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  const wchar_t *v6; // rbx
  unsigned int v7; // esi
  unsigned __int64 v8; // r12
  int v9; // r15d
  wchar_t *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // r12
  int v14; // ebx
  int v15; // edx
  const wchar_t *v16; // rsi
  wchar_t *v17; // rbp
  __int64 v18; // rcx
  __int64 v19; // r8
  errno_t v20; // eax
  errno_t v21; // eax
  wchar_t *v22; // rax
  __int64 v23; // rax
  __int64 v25; // [rsp+28h] [rbp-60h]
  unsigned __int64 v26; // [rsp+38h] [rbp-50h]
  int v28; // [rsp+98h] [rbp+10h]
  unsigned __int64 v30; // [rsp+A8h] [rbp+20h]
  int v31; // [rsp+A8h] [rbp+20h]

  if ( !a2 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( !(_DWORD)v4 )
    return 0;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  v6 = (const wchar_t *)*a1;
  v7 = 0;
  v28 = 0;
  v8 = *a1 + 2LL * *(int *)(*a1 - 16);
  v30 = v8;
  if ( *a1 < v8 )
  {
    v9 = 0;
    do
    {
      v10 = wcsstr(v6, a2);
      if ( v10 )
      {
        v11 = (int)v4;
        do
        {
          v6 = &v10[v11];
          ++v9;
          v10 = wcsstr(&v10[v11], a2);
        }
        while ( v10 );
        v8 = v30;
        v28 = v9;
      }
      if ( v6 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v6[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v6 += (int)v12 + 1;
    }
    while ( (unsigned __int64)v6 < v8 );
    v7 = v28;
    if ( v28 > 0 )
    {
      v13 = *(int *)(*a1 - 16);
      v14 = v13 + v28 * (v5 - v4);
      v15 = v14;
      if ( v14 <= (int)v13 )
        v15 = *(_DWORD *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - v15) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v15);
      v25 = *a1;
      v16 = (const wchar_t *)*a1;
      v26 = *a1 + 2 * v13;
      if ( *a1 < v26 )
      {
        do
        {
          v17 = wcsstr(v16, a2);
          if ( v17 )
          {
            v18 = (int)v5;
            v19 = (int)v4;
            do
            {
              v16 = &v17[v18];
              v31 = v13 - (((__int64)v17 - v25) >> 1) - v4;
              v20 = memmove_s(&v17[v18], 2LL * v31, &v17[v19], 2LL * v31);
              if ( v20 )
              {
                if ( v20 == 12 )
                  goto LABEL_54;
                if ( v20 == 22 || v20 == 34 )
                  goto LABEL_52;
                if ( v20 != 80 )
                  goto LABEL_53;
              }
              v21 = memcpy_s(v17, 2LL * (int)v5, a3, 2LL * (int)v5);
              if ( v21 )
              {
                if ( v21 == 12 )
LABEL_54:
                  ATL::AtlThrowImpl(-2147024882);
                if ( v21 == 22 || v21 == 34 )
                  goto LABEL_52;
                if ( v21 != 80 )
LABEL_53:
                  ATL::AtlThrowImpl(-2147467259);
              }
              v17[(int)v5 + v31] = 0;
              LODWORD(v13) = v5 - v4 + v13;
              v22 = wcsstr(v16, a2);
              v18 = (int)v5;
              v17 = v22;
              v19 = (int)v4;
            }
            while ( v22 );
          }
          if ( v16 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v16[v23] );
          }
          else
          {
            LODWORD(v23) = 0;
          }
          v16 += (int)v23 + 1;
        }
        while ( (unsigned __int64)v16 < v26 );
      }
      if ( v14 < 0 || v14 > *(_DWORD *)(*a1 - 12) )
LABEL_52:
        ATL::AtlThrowImpl(-2147024809);
      v7 = v28;
      *(_DWORD *)(*a1 - 16) = v14;
      *(_WORD *)(*a1 + 2LL * v14) = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000eed8  mov     [rsp+Source], r8
0x18000eedd  mov     [rsp+arg_0], rcx
0x18000eee2  push    rbx
0x18000eee3  push    rbp
0x18000eee4  push    rsi
0x18000eee5  push    rdi
0x18000eee6  push    r12
0x18000eee8  push    r13
0x18000eeea  push    r14
0x18000eeec  push    r15
0x18000eeee  sub     rsp, 48h
0x18000eef2  mov     r15, rcx
0x18000eef5  mov     rax, r8
0x18000eef8  xor     ecx, ecx
0x18000eefa  mov     r13, rdx
0x18000eefd  test    rdx, rdx
0x18000ef00  jz      loc_18000F193
0x18000ef06  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ef0a  mov     rdi, rdx
0x18000ef0d  inc     rdi
0x18000ef10  cmp     [r13+rdi*2+0], cx
0x18000ef16  jnz     short loc_18000EF0D
0x18000ef18  test    edi, edi
0x18000ef1a  jz      loc_18000F193
0x18000ef20  test    rax, rax
0x18000ef23  jz      short loc_18000EF34
0x18000ef25  mov     r14, rdx
0x18000ef28  inc     r14
0x18000ef2b  cmp     [r8+r14*2], cx
0x18000ef30  jnz     short loc_18000EF28
0x18000ef32  jmp     short loc_18000EF37
0x18000ef34  mov     r14d, ecx
0x18000ef37  mov     rbx, [r15]
0x18000ef3a  mov     esi, ecx
0x18000ef3c  mov     [rsp+88h+arg_8], ecx
0x18000ef43  movsxd  rax, dword ptr [rbx-10h]
0x18000ef47  lea     r12, [rbx+rax*2]
0x18000ef4b  mov     [rsp+88h+arg_18], r12
0x18000ef53  cmp     rbx, r12
0x18000ef56  jnb     loc_18000F18F
0x18000ef5c  mov     ebp, 1
0x18000ef61  mov     r15d, ecx
0x18000ef64  mov     rdx, r13; SubStr
0x18000ef67  mov     rcx, rbx; Str
0x18000ef6a  call    cs:__imp_wcsstr
0x18000ef70  xor     r8d, r8d
0x18000ef73  test    rax, rax
0x18000ef76  jz      short loc_18000EFA9
0x18000ef78  movsxd  rsi, edi
0x18000ef7b  add     rsi, rsi
0x18000ef7e  lea     rbx, [rsi+rax]
0x18000ef82  mov     rdx, r13; SubStr
0x18000ef85  mov     rcx, rbx; Str
0x18000ef88  add     r15d, ebp
0x18000ef8b  call    cs:__imp_wcsstr
0x18000ef91  test    rax, rax
0x18000ef94  jnz     short loc_18000EF7E
0x18000ef96  mov     r12, [rsp+88h+arg_18]
0x18000ef9e  xor     r8d, r8d
0x18000efa1  mov     [rsp+88h+arg_8], r15d
0x18000efa9  test    rbx, rbx
0x18000efac  jz      short loc_18000EFBE
0x18000efae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efb2  inc     rax
0x18000efb5  cmp     [rbx+rax*2], r8w
0x18000efba  jnz     short loc_18000EFB2
0x18000efbc  jmp     short loc_18000EFC1
0x18000efbe  mov     eax, r8d
0x18000efc1  inc     eax
0x18000efc3  movsxd  rcx, eax
0x18000efc6  lea     rbx, [rbx+rcx*2]
0x18000efca  cmp     rbx, r12
0x18000efcd  jb      short loc_18000EF64
0x18000efcf  mov     esi, [rsp+88h+arg_8]
0x18000efd6  mov     r15, [rsp+88h+arg_0]
0x18000efde  test    esi, esi
0x18000efe0  jle     loc_18000F18F
0x18000efe6  mov     rcx, [r15]
0x18000efe9  mov     ebx, r14d
0x18000efec  sub     ebx, edi
0x18000efee  imul    ebx, esi
0x18000eff1  movsxd  r12, dword ptr [rcx-10h]
0x18000eff5  mov     eax, [rcx-0Ch]
0x18000eff8  add     ebx, r12d
0x18000effb  cmp     ebx, r12d
0x18000effe  mov     edx, ebx
0x18000f000  cmovle  edx, r12d
0x18000f004  sub     ebp, [rcx-8]
0x18000f007  sub     eax, edx
0x18000f009  or      ebp, eax
0x18000f00b  jge     short loc_18000F018
0x18000f00d  mov     rcx, r15
0x18000f010  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000f015  xor     r8d, r8d
0x18000f018  mov     rcx, [r15]
0x18000f01b  mov     [rsp+88h+var_60], rcx
0x18000f020  mov     rsi, rcx
0x18000f023  lea     rax, [rcx+r12*2]
0x18000f027  mov     [rsp+88h+var_50], rax
0x18000f02c  cmp     rcx, rax
0x18000f02f  jnb     loc_18000F16E
0x18000f035  mov     rdx, r13; SubStr
0x18000f038  mov     rcx, rsi; Str
0x18000f03b  call    cs:__imp_wcsstr
0x18000f041  xor     r8d, r8d
0x18000f044  mov     rbp, rax
0x18000f047  test    rax, rax
0x18000f04a  jz      loc_18000F142
0x18000f050  movsxd  rcx, r14d
0x18000f053  add     rcx, rcx
0x18000f056  movsxd  r8, edi
0x18000f059  add     r8, r8
0x18000f05c  mov     [rsp+88h+SourceSize], rcx
0x18000f061  mov     [rsp+88h+var_58], r8
0x18000f066  mov     edx, r12d
0x18000f069  lea     rsi, [rcx+rbp]
0x18000f06d  mov     rax, rbp
0x18000f070  add     r8, rbp; Source
0x18000f073  sub     rax, [rsp+88h+var_60]
0x18000f078  mov     rcx, rsi; Destination
0x18000f07b  sar     rax, 1
0x18000f07e  sub     edx, eax
0x18000f080  sub     edx, edi
0x18000f082  mov     dword ptr [rsp+88h+arg_18], edx
0x18000f089  movsxd  rdx, edx
0x18000f08c  add     rdx, rdx; DestinationSize
0x18000f08f  mov     r9, rdx; SourceSize
0x18000f092  call    cs:__imp_memmove_s
0x18000f098  test    eax, eax
0x18000f09a  jz      short loc_18000F0C0
0x18000f09c  cmp     eax, 0Ch
0x18000f09f  jz      loc_18000F1BC
0x18000f0a5  cmp     eax, 16h
0x18000f0a8  jz      loc_18000F1A6
0x18000f0ae  cmp     eax, 22h ; '"'
0x18000f0b1  jz      loc_18000F1A6
0x18000f0b7  cmp     eax, 50h ; 'P'
0x18000f0ba  jnz     loc_18000F1B1
0x18000f0c0  mov     rdx, [rsp+88h+SourceSize]; DestinationSize
0x18000f0c5  mov     rcx, rbp; Destination
0x18000f0c8  mov     r8, [rsp+88h+Source]; Source
0x18000f0d0  mov     r9, rdx; SourceSize
0x18000f0d3  call    cs:__imp_memcpy_s
0x18000f0d9  test    eax, eax
0x18000f0db  jz      short loc_18000F101
0x18000f0dd  cmp     eax, 0Ch
0x18000f0e0  jz      loc_18000F1BC
0x18000f0e6  cmp     eax, 16h
0x18000f0e9  jz      loc_18000F1A6
0x18000f0ef  cmp     eax, 22h ; '"'
0x18000f0f2  jz      loc_18000F1A6
0x18000f0f8  cmp     eax, 50h ; 'P'
0x18000f0fb  jnz     loc_18000F1B1
0x18000f101  mov     eax, dword ptr [rsp+88h+arg_18]
0x18000f108  mov     rdx, r13; SubStr
0x18000f10b  add     eax, r14d
0x18000f10e  movsxd  rcx, eax
0x18000f111  xor     eax, eax
0x18000f113  mov     [rbp+rcx*2+0], ax
0x18000f118  mov     eax, r14d
0x18000f11b  sub     eax, edi
0x18000f11d  mov     rcx, rsi; Str
0x18000f120  add     r12d, eax
0x18000f123  call    cs:__imp_wcsstr
0x18000f129  mov     rcx, [rsp+88h+SourceSize]
0x18000f12e  mov     rbp, rax
0x18000f131  mov     r8, [rsp+88h+var_58]
0x18000f136  test    rax, rax
0x18000f139  jnz     loc_18000F066
0x18000f13f  xor     r8d, r8d
0x18000f142  test    rsi, rsi
0x18000f145  jz      short loc_18000F157
0x18000f147  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f14b  inc     rax
0x18000f14e  cmp     [rsi+rax*2], r8w
0x18000f153  jnz     short loc_18000F14B
0x18000f155  jmp     short loc_18000F15A
0x18000f157  mov     eax, r8d
0x18000f15a  inc     eax
0x18000f15c  movsxd  rcx, eax
0x18000f15f  lea     rsi, [rsi+rcx*2]
0x18000f163  cmp     rsi, [rsp+88h+var_50]
0x18000f168  jb      loc_18000F035
0x18000f16e  test    ebx, ebx
0x18000f170  js      short loc_18000F1A6
0x18000f172  mov     rax, [r15]
0x18000f175  cmp     ebx, [rax-0Ch]
0x18000f178  jg      short loc_18000F1A6
0x18000f17a  mov     esi, [rsp+88h+arg_8]
0x18000f181  mov     [rax-10h], ebx
0x18000f184  mov     rcx, [r15]
0x18000f187  movsxd  rdx, ebx
0x18000f18a  mov     [rcx+rdx*2], r8w
0x18000f18f  mov     eax, esi
0x18000f191  jmp     short loc_18000F195
0x18000f193  xor     eax, eax
0x18000f195  add     rsp, 48h
0x18000f199  pop     r15
0x18000f19b  pop     r14
0x18000f19d  pop     r13
0x18000f19f  pop     r12
0x18000f1a1  pop     rdi
0x18000f1a2  pop     rsi
0x18000f1a3  pop     rbp
0x18000f1a4  pop     rbx
0x18000f1a5  retn
0x18000f1a6  mov     ecx, 80070057h; int
0x18000f1ab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f1b1  mov     ecx, 80004005h; int
0x18000f1b6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f1bc  mov     ecx, 8007000Eh; int
0x18000f1c1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
