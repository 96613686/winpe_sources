# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18002c0c0`
- end: `0x18002c2d4`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002bc60`
- `0x18002bd7c`

## callees

- `0x180005bcc`
- `0x180006c44`
- `0x180006dc0`
- `0x18002c0c0`
- `0x18002c2dc`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002c129`
- `msvcrt!wcsstr` at `0x18002c146`
- `msvcrt!wcsstr` at `0x18002c1d2`
- `msvcrt!wcsstr` at `0x18002c272`
- `msvcrt!wcsstr` at `0x18002c129`
- `msvcrt!wcsstr` at `0x18002c146`
- `msvcrt!wcsstr` at `0x18002c1d2`
- `msvcrt!wcsstr` at `0x18002c272`
- `msvcrt!memcpy_s` at `0x18002c23c`
- `msvcrt!memcpy_s` at `0x18002c23c`
- `msvcrt!memmove_s` at `0x18002c21c`
- `msvcrt!memmove_s` at `0x18002c21c`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1,
        const wchar_t *a2,
        const void *a3)
{
  const wchar_t **v3; // rsi
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // r14
  int v8; // eax
  const wchar_t *v9; // rbx
  int v10; // ebp
  int v11; // r13d
  unsigned __int64 v12; // r12
  wchar_t *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // r12
  int v16; // edx
  const wchar_t *v17; // r13
  const wchar_t *v18; // rdi
  wchar_t *v19; // rax
  rsize_t v20; // rsi
  int v21; // ebx
  errno_t v22; // eax
  errno_t v23; // eax
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+24h] [rbp-54h]
  wchar_t *Destination; // [rsp+28h] [rbp-50h]
  unsigned __int64 v27; // [rsp+30h] [rbp-48h]
  int v30; // [rsp+98h] [rbp+20h]

  v3 = a1;
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(a2);
  v7 = (int)result;
  if ( (_DWORD)result )
  {
    v8 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v6);
    v9 = *v3;
    v10 = 0;
    v11 = v8;
    v30 = v8;
    v24 = 0;
    v12 = (unsigned __int64)&(*v3)[*((int *)*v3 - 4)];
    if ( (unsigned __int64)*v3 < v12 )
    {
      do
      {
        v13 = wcsstr(v9, a2);
        if ( v13 )
        {
          v14 = v7;
          do
          {
            v9 = &v13[v14];
            ++v10;
            v13 = wcsstr(&v13[v14], a2);
          }
          while ( v13 );
          v24 = v10;
        }
        v9 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v9) + 1);
      }
      while ( (unsigned __int64)v9 < v12 );
      if ( v10 > 0 )
      {
        v15 = *((int *)*v3 - 4);
        v25 = v15 + v10 * (v11 - v7);
        v16 = v25;
        if ( v25 <= (int)v15 )
          v16 = *((_DWORD *)*v3 - 4);
        if ( ((*((_DWORD *)*v3 - 3) - v16) | (1 - *((_DWORD *)*v3 - 2))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v3);
        v17 = *v3;
        v18 = *v3;
        v27 = (unsigned __int64)&(*v3)[v15];
        if ( (unsigned __int64)*v3 < v27 )
        {
          do
          {
            v19 = wcsstr(v18, a2);
            Destination = v19;
            if ( v19 )
            {
              v20 = v30;
              do
              {
                v18 = &v19[v20];
                v21 = v15 - (v19 - v17) - v7;
                v22 = memmove_s(&v19[v20], 2LL * v21, &v19[v7], 2LL * v21);
                ATL::AtlCrtErrorCheck(v22);
                v23 = memcpy_s(Destination, v20 * 2, a3, v20 * 2);
                ATL::AtlCrtErrorCheck(v23);
                Destination[v21 + v30] = 0;
                LODWORD(v15) = v30 - v7 + v15;
                v19 = wcsstr(v18, a2);
                Destination = v19;
              }
              while ( v19 );
            }
            v18 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v18) + 1);
          }
          while ( (unsigned __int64)v18 < v27 );
          v3 = a1;
          v10 = v24;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v3, (unsigned int)v25);
      }
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18002c0c0  mov     [rsp+arg_8], rbx
0x18002c0c5  mov     [rsp+Source], r8
0x18002c0ca  mov     [rsp+arg_0], rcx
0x18002c0cf  push    rbp
0x18002c0d0  push    rsi
0x18002c0d1  push    rdi
0x18002c0d2  push    r12
0x18002c0d4  push    r13
0x18002c0d6  push    r14
0x18002c0d8  push    r15
0x18002c0da  sub     rsp, 40h
0x18002c0de  mov     rsi, rcx
0x18002c0e1  mov     r15, rdx
0x18002c0e4  mov     rcx, rdx
0x18002c0e7  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18002c0ec  movsxd  r14, eax
0x18002c0ef  test    eax, eax
0x18002c0f1  jz      loc_18002C2BC
0x18002c0f7  mov     rcx, r8
0x18002c0fa  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18002c0ff  mov     rbx, [rsi]
0x18002c102  xor     ebp, ebp
0x18002c104  mov     r13d, eax
0x18002c107  mov     [rsp+78h+arg_18], eax
0x18002c10e  mov     [rsp+78h+var_58], ebp
0x18002c112  movsxd  rcx, dword ptr [rbx-10h]
0x18002c116  lea     r12, [rbx+rcx*2]
0x18002c11a  cmp     rbx, r12
0x18002c11d  jnb     loc_18002C2BA
0x18002c123  mov     rdx, r15; SubStr
0x18002c126  mov     rcx, rbx; Str
0x18002c129  call    cs:__imp_wcsstr
0x18002c12f  test    rax, rax
0x18002c132  jz      short loc_18002C155
0x18002c134  mov     rdi, r14
0x18002c137  add     rdi, rdi
0x18002c13a  lea     rbx, [rdi+rax]
0x18002c13e  mov     rdx, r15; SubStr
0x18002c141  mov     rcx, rbx; Str
0x18002c144  inc     ebp
0x18002c146  call    cs:__imp_wcsstr
0x18002c14c  test    rax, rax
0x18002c14f  jnz     short loc_18002C13A
0x18002c151  mov     [rsp+78h+var_58], ebp
0x18002c155  mov     rcx, rbx
0x18002c158  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18002c15d  inc     eax
0x18002c15f  cdqe
0x18002c161  lea     rbx, [rbx+rax*2]
0x18002c165  cmp     rbx, r12
0x18002c168  jb      short loc_18002C123
0x18002c16a  test    ebp, ebp
0x18002c16c  jle     loc_18002C2BA
0x18002c172  mov     r8, [rsi]
0x18002c175  mov     eax, r13d
0x18002c178  sub     eax, r14d
0x18002c17b  mov     ecx, 1
0x18002c180  imul    eax, ebp
0x18002c183  movsxd  r12, dword ptr [r8-10h]
0x18002c187  add     eax, r12d
0x18002c18a  cmp     eax, r12d
0x18002c18d  mov     [rsp+78h+var_54], eax
0x18002c191  mov     edx, eax
0x18002c193  mov     eax, [r8-0Ch]
0x18002c197  cmovle  edx, r12d
0x18002c19b  sub     ecx, [r8-8]
0x18002c19f  sub     eax, edx
0x18002c1a1  or      ecx, eax
0x18002c1a3  jge     short loc_18002C1AD
0x18002c1a5  mov     rcx, rsi
0x18002c1a8  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002c1ad  mov     r13, [rsi]
0x18002c1b0  lea     rax, ds:0[r12*2]
0x18002c1b8  add     rax, r13
0x18002c1bb  mov     rdi, r13
0x18002c1be  mov     [rsp+78h+var_48], rax
0x18002c1c3  cmp     r13, rax
0x18002c1c6  jnb     loc_18002C2AE
0x18002c1cc  mov     rdx, r15; SubStr
0x18002c1cf  mov     rcx, rdi; Str
0x18002c1d2  call    cs:__imp_wcsstr
0x18002c1d8  mov     [rsp+78h+Destination], rax
0x18002c1dd  test    rax, rax
0x18002c1e0  jz      loc_18002C286
0x18002c1e6  movsxd  rsi, [rsp+78h+arg_18]
0x18002c1ee  mov     rbp, r14
0x18002c1f1  add     rbp, rbp
0x18002c1f4  add     rsi, rsi
0x18002c1f7  mov     rcx, rax
0x18002c1fa  lea     rdi, [rsi+rax]
0x18002c1fe  sub     rcx, r13
0x18002c201  lea     r8, [rax+rbp]; Source
0x18002c205  sar     rcx, 1
0x18002c208  mov     ebx, r12d
0x18002c20b  sub     ebx, ecx
0x18002c20d  mov     rcx, rdi; Destination
0x18002c210  sub     ebx, r14d
0x18002c213  movsxd  rdx, ebx
0x18002c216  add     rdx, rdx; DestinationSize
0x18002c219  mov     r9, rdx; SourceSize
0x18002c21c  call    cs:__imp_memmove_s
0x18002c222  mov     ecx, eax; int
0x18002c224  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002c229  mov     r8, [rsp+78h+Source]; Source
0x18002c231  mov     r9, rsi; SourceSize
0x18002c234  mov     rcx, [rsp+78h+Destination]; Destination
0x18002c239  mov     rdx, rsi; DestinationSize
0x18002c23c  call    cs:__imp_memcpy_s
0x18002c242  mov     ecx, eax; int
0x18002c244  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002c249  mov     r8d, [rsp+78h+arg_18]
0x18002c251  mov     rdx, [rsp+78h+Destination]
0x18002c256  lea     eax, [rbx+r8]
0x18002c25a  movsxd  rcx, eax
0x18002c25d  xor     eax, eax
0x18002c25f  mov     [rdx+rcx*2], ax
0x18002c263  mov     eax, r8d
0x18002c266  sub     eax, r14d
0x18002c269  mov     rdx, r15; SubStr
0x18002c26c  mov     rcx, rdi; Str
0x18002c26f  add     r12d, eax
0x18002c272  call    cs:__imp_wcsstr
0x18002c278  mov     [rsp+78h+Destination], rax
0x18002c27d  test    rax, rax
0x18002c280  jnz     loc_18002C1F7
0x18002c286  mov     rcx, rdi
0x18002c289  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18002c28e  inc     eax
0x18002c290  movsxd  rcx, eax
0x18002c293  lea     rdi, [rdi+rcx*2]
0x18002c297  cmp     rdi, [rsp+78h+var_48]
0x18002c29c  jb      loc_18002C1CC
0x18002c2a2  mov     rsi, [rsp+78h+arg_0]
0x18002c2aa  mov     ebp, [rsp+78h+var_58]
0x18002c2ae  mov     edx, [rsp+78h+var_54]
0x18002c2b2  mov     rcx, rsi
0x18002c2b5  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18002c2ba  mov     eax, ebp
0x18002c2bc  mov     rbx, [rsp+78h+arg_8]
0x18002c2c4  add     rsp, 40h
0x18002c2c8  pop     r15
0x18002c2ca  pop     r14
0x18002c2cc  pop     r13
0x18002c2ce  pop     r12
0x18002c2d0  pop     rdi
0x18002c2d1  pop     rsi
0x18002c2d2  pop     rbp
0x18002c2d3  retn
```
