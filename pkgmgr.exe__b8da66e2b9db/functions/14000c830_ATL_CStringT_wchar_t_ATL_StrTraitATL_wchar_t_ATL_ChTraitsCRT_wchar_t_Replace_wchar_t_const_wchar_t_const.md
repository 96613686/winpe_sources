# ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Replace(wchar_t const *,wchar_t const *)

- ea: `0x14000c830`
- end: `0x14000ca57`
- name: `?Replace@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHPEB_W0@Z`
- size: `551`
- prototype: `__int64 __fastcall(const wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000baa4`

## callees

- `0x1400066d8`
- `0x14000ba38`
- `0x14000c318`
- `0x14000c830`
- `0x14000cb78`
- `0x14000cb98`
- `0x14000d6d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c8a5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c8c2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c959`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c9f1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c8a5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c8c2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c959`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000c9f1`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Replace(
        const wchar_t **a1)
{
  const wchar_t **v1; // rsi
  __int64 result; // rax
  __int64 v3; // r14
  int v4; // eax
  const wchar_t *v5; // rbx
  int v6; // ebp
  int v7; // r12d
  unsigned __int64 v8; // r15
  wchar_t *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r15
  int v12; // r13d
  unsigned int v13; // r8d
  const wchar_t *v14; // r12
  const wchar_t *v15; // rdi
  unsigned __int64 v16; // rbp
  wchar_t *v17; // rax
  wchar_t *v18; // rbp
  rsize_t v19; // r13
  int v20; // ebx
  errno_t v21; // eax
  errno_t v22; // eax
  unsigned __int64 v23; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+88h] [rbp+10h]
  int v26; // [rsp+90h] [rbp+18h]
  int v27; // [rsp+98h] [rbp+20h]

  v1 = a1;
  result = ATL::ChTraitsCRT<wchar_t>::SafeStringLen(L"\\\"");
  v3 = (int)result;
  if ( (_DWORD)result )
  {
    v4 = ATL::ChTraitsCRT<wchar_t>::SafeStringLen(L"\\\\\"");
    v5 = *v1;
    v6 = 0;
    v7 = v4;
    v26 = v4;
    v25 = 0;
    v8 = (unsigned __int64)&(*v1)[*((int *)*v1 - 4)];
    if ( (unsigned __int64)*v1 < v8 )
    {
      do
      {
        v9 = wcsstr(v5, L"\\\"");
        if ( v9 )
        {
          v10 = v3;
          do
          {
            v5 = &v9[v10];
            ++v6;
            v9 = wcsstr(&v9[v10], L"\\\"");
          }
          while ( v9 );
          v25 = v6;
        }
        v5 += (int)(ATL::ChTraitsCRT<wchar_t>::SafeStringLen(v5) + 1);
      }
      while ( (unsigned __int64)v5 < v8 );
      if ( v6 > 0 )
      {
        v11 = *((int *)*v1 - 4);
        v12 = v11 + v6 * (v7 - v3);
        v27 = v12;
        v13 = v12;
        if ( v12 <= (int)v11 )
          v13 = *((_DWORD *)*v1 - 4);
        if ( (((*((_DWORD *)*v1 - 3) - v13) | (1 - *((_DWORD *)*v1 - 2))) & 0x80000000) != 0 )
          ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v1, v13);
        v14 = *v1;
        v15 = *v1;
        v23 = (unsigned __int64)&(*v1)[v11];
        if ( (unsigned __int64)*v1 < v23 )
        {
          v16 = (unsigned __int64)&(*v1)[v11];
          do
          {
            v17 = wcsstr(v15, L"\\\"");
            if ( v17 )
            {
              v18 = v17;
              v19 = v26;
              do
              {
                v15 = &v18[v19];
                v20 = v11 - (v18 - v14) - v3;
                v21 = memmove_s(&v18[v19], 2LL * v20, &v18[v3], 2LL * v20);
                ATL::AtlCrtErrorCheck(v21);
                v22 = memcpy_s(v18, v19 * 2, L"\\\\\"", v19 * 2);
                ATL::AtlCrtErrorCheck(v22);
                v18[v20 + v26] = 0;
                LODWORD(v11) = v26 - v3 + v11;
                v18 = wcsstr(&v18[v19], L"\\\"");
              }
              while ( v18 );
              v16 = v23;
            }
            v15 += (int)(ATL::ChTraitsCRT<wchar_t>::SafeStringLen(v15) + 1);
          }
          while ( (unsigned __int64)v15 < v16 );
          v1 = a1;
          v6 = v25;
          v12 = v27;
        }
        ATL::CSimpleStringT<wchar_t,0>::SetLength(v1, (unsigned int)v12);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000c830  mov     [rsp+arg_10], r8
0x14000c835  mov     [rsp+arg_8], rdx
0x14000c83a  mov     [rsp+arg_0], rcx
0x14000c83f  push    rbx
0x14000c840  push    rbp
0x14000c841  push    rsi
0x14000c842  push    rdi
0x14000c843  push    r12
0x14000c845  push    r13
0x14000c847  push    r14
0x14000c849  push    r15
0x14000c84b  sub     rsp, 38h
0x14000c84f  lea     r13, SubStr; "\\\""
0x14000c856  mov     rsi, rcx
0x14000c859  mov     rcx, r13
0x14000c85c  call    ?SafeStringLen@?$ChTraitsCRT@_W@ATL@@SAHPEB_W@Z; ATL::ChTraitsCRT<wchar_t>::SafeStringLen(wchar_t const *)
0x14000c861  movsxd  r14, eax
0x14000c864  test    eax, eax
0x14000c866  jz      loc_14000CA46
0x14000c86c  lea     rcx, asc_14002E8F0; "\\\\\""
0x14000c873  call    ?SafeStringLen@?$ChTraitsCRT@_W@ATL@@SAHPEB_W@Z; ATL::ChTraitsCRT<wchar_t>::SafeStringLen(wchar_t const *)
0x14000c878  mov     rbx, [rsi]
0x14000c87b  xor     ebp, ebp
0x14000c87d  mov     r12d, eax
0x14000c880  mov     dword ptr [rsp+78h+arg_10], eax
0x14000c887  mov     dword ptr [rsp+78h+arg_8], ebp
0x14000c88e  movsxd  rcx, dword ptr [rbx-10h]
0x14000c892  lea     r15, [rbx+rcx*2]
0x14000c896  cmp     rbx, r15
0x14000c899  jnb     loc_14000CA44
0x14000c89f  mov     rdx, r13; SubStr
0x14000c8a2  mov     rcx, rbx; Str
0x14000c8a5  call    cs:__imp_wcsstr
0x14000c8ab  test    rax, rax
0x14000c8ae  jz      short loc_14000C8D4
0x14000c8b0  mov     rdi, r14
0x14000c8b3  add     rdi, rdi
0x14000c8b6  lea     rbx, [rdi+rax]
0x14000c8ba  mov     rdx, r13; SubStr
0x14000c8bd  mov     rcx, rbx; Str
0x14000c8c0  inc     ebp
0x14000c8c2  call    cs:__imp_wcsstr
0x14000c8c8  test    rax, rax
0x14000c8cb  jnz     short loc_14000C8B6
0x14000c8cd  mov     dword ptr [rsp+78h+arg_8], ebp
0x14000c8d4  mov     rcx, rbx
0x14000c8d7  call    ?SafeStringLen@?$ChTraitsCRT@_W@ATL@@SAHPEB_W@Z; ATL::ChTraitsCRT<wchar_t>::SafeStringLen(wchar_t const *)
0x14000c8dc  inc     eax
0x14000c8de  cdqe
0x14000c8e0  lea     rbx, [rbx+rax*2]
0x14000c8e4  cmp     rbx, r15
0x14000c8e7  jb      short loc_14000C89F
0x14000c8e9  test    ebp, ebp
0x14000c8eb  jle     loc_14000CA44
0x14000c8f1  mov     rdx, [rsi]
0x14000c8f4  mov     r13d, r12d
0x14000c8f7  sub     r13d, r14d
0x14000c8fa  mov     ecx, 1
0x14000c8ff  imul    r13d, ebp
0x14000c903  movsxd  r15, dword ptr [rdx-10h]
0x14000c907  mov     eax, [rdx-0Ch]
0x14000c90a  add     r13d, r15d
0x14000c90d  cmp     r13d, r15d
0x14000c910  mov     [rsp+78h+arg_18], r13d
0x14000c918  mov     r8d, r13d
0x14000c91b  cmovle  r8d, r15d
0x14000c91f  sub     ecx, [rdx-8]
0x14000c922  sub     eax, r8d
0x14000c925  or      ecx, eax
0x14000c927  jge     short loc_14000C934
0x14000c929  mov     edx, r8d
0x14000c92c  mov     rcx, rsi
0x14000c92f  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x14000c934  mov     r12, [rsi]
0x14000c937  mov     rdi, r12
0x14000c93a  lea     rax, [r12+r15*2]
0x14000c93e  mov     [rsp+78h+var_58], rax
0x14000c943  cmp     r12, rax
0x14000c946  jnb     loc_14000CA39
0x14000c94c  mov     rbp, rax
0x14000c94f  lea     rdx, SubStr; "\\\""
0x14000c956  mov     rcx, rdi; Str
0x14000c959  call    cs:__imp_wcsstr
0x14000c95f  test    rax, rax
0x14000c962  jz      loc_14000CA08
0x14000c968  movsxd  r13, dword ptr [rsp+78h+arg_10]
0x14000c970  mov     rsi, r14
0x14000c973  add     rsi, rsi
0x14000c976  mov     rbp, rax
0x14000c979  add     r13, r13
0x14000c97c  mov     rcx, rbp
0x14000c97f  lea     r8, [rsi+rbp]; Source
0x14000c983  sub     rcx, r12
0x14000c986  mov     ebx, r15d
0x14000c989  sar     rcx, 1
0x14000c98c  mov     rdi, rbp
0x14000c98f  sub     ebx, ecx
0x14000c991  add     rdi, r13
0x14000c994  sub     ebx, r14d
0x14000c997  mov     rcx, rdi; Destination
0x14000c99a  movsxd  rdx, ebx
0x14000c99d  add     rdx, rdx; DestinationSize
0x14000c9a0  mov     r9, rdx; SourceSize
0x14000c9a3  call    memmove_s
0x14000c9a8  mov     ecx, eax; int
0x14000c9aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000c9af  mov     r9, r13; SourceSize
0x14000c9b2  lea     r8, asc_14002E8F0; "\\\\\""
0x14000c9b9  mov     rdx, r13; DestinationSize
0x14000c9bc  mov     rcx, rbp; Destination
0x14000c9bf  call    memcpy_s
0x14000c9c4  mov     ecx, eax; int
0x14000c9c6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000c9cb  mov     edx, dword ptr [rsp+78h+arg_10]
0x14000c9d2  lea     eax, [rbx+rdx]
0x14000c9d5  movsxd  rcx, eax
0x14000c9d8  xor     eax, eax
0x14000c9da  mov     [rbp+rcx*2+0], ax
0x14000c9df  mov     eax, edx
0x14000c9e1  sub     eax, r14d
0x14000c9e4  lea     rdx, SubStr; "\\\""
0x14000c9eb  mov     rcx, rdi; Str
0x14000c9ee  add     r15d, eax
0x14000c9f1  call    cs:__imp_wcsstr
0x14000c9f7  mov     rbp, rax
0x14000c9fa  test    rax, rax
0x14000c9fd  jnz     loc_14000C97C
0x14000ca03  mov     rbp, [rsp+78h+var_58]
0x14000ca08  mov     rcx, rdi
0x14000ca0b  call    ?SafeStringLen@?$ChTraitsCRT@_W@ATL@@SAHPEB_W@Z; ATL::ChTraitsCRT<wchar_t>::SafeStringLen(wchar_t const *)
0x14000ca10  inc     eax
0x14000ca12  movsxd  rcx, eax
0x14000ca15  lea     rdi, [rdi+rcx*2]
0x14000ca19  cmp     rdi, rbp
0x14000ca1c  jb      loc_14000C94F
0x14000ca22  mov     rsi, [rsp+78h+arg_0]
0x14000ca2a  mov     ebp, dword ptr [rsp+78h+arg_8]
0x14000ca31  mov     r13d, [rsp+78h+arg_18]
0x14000ca39  mov     edx, r13d
0x14000ca3c  mov     rcx, rsi
0x14000ca3f  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x14000ca44  mov     eax, ebp
0x14000ca46  add     rsp, 38h
0x14000ca4a  pop     r15
0x14000ca4c  pop     r14
0x14000ca4e  pop     r13
0x14000ca50  pop     r12
0x14000ca52  pop     rdi
0x14000ca53  pop     rsi
0x14000ca54  pop     rbp
0x14000ca55  pop     rbx
0x14000ca56  retn
```
