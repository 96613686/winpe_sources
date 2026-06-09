# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180019784`
- end: `0x1800199ad`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `553`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800194c0`

## callees

- `0x1800096a8`
- `0x180019694`
- `0x180019784`
- `0x1800199b4`
- `0x1800199d4`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800198f7`
- `msvcrt!memmove_s` at `0x1800198f7`
- `msvcrt!memcpy_s` at `0x180019914`
- `msvcrt!memcpy_s` at `0x180019914`
- `msvcrt!wcsstr` at `0x1800197f9`
- `msvcrt!wcsstr` at `0x180019816`
- `msvcrt!wcsstr` at `0x1800198ad`
- `msvcrt!wcsstr` at `0x180019947`
- `msvcrt!wcsstr` at `0x1800197f9`
- `msvcrt!wcsstr` at `0x180019816`
- `msvcrt!wcsstr` at `0x1800198ad`
- `msvcrt!wcsstr` at `0x180019947`

## string_xrefs

- `0x1800197c0`: `__CDATA_XML_CLOSE_SYMBOL__`
- `0x180019907`: `__CDATA_XML_CLOSE_SYMBOL__`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  __int64 *v1; // rsi
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
  int v13; // r8d
  __int64 v14; // r12
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
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"]]>");
  v3 = (int)result;
  if ( (_DWORD)result )
  {
    v4 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"__CDATA_XML_CLOSE_SYMBOL__");
    v5 = (const wchar_t *)*v1;
    v6 = 0;
    v7 = v4;
    v26 = v4;
    v25 = 0;
    v8 = *v1 + 2LL * *(int *)(*v1 - 16);
    if ( *v1 < v8 )
    {
      do
      {
        v9 = wcsstr(v5, L"]]>");
        if ( v9 )
        {
          v10 = v3;
          do
          {
            v5 = &v9[v10];
            ++v6;
            v9 = wcsstr(&v9[v10], L"]]>");
          }
          while ( v9 );
          v25 = v6;
        }
        v5 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v5) + 1);
      }
      while ( (unsigned __int64)v5 < v8 );
      if ( v6 > 0 )
      {
        v11 = *(int *)(*v1 - 16);
        v12 = v11 + v6 * (v7 - v3);
        v27 = v12;
        v13 = v12;
        if ( v12 <= (int)v11 )
          v13 = *(_DWORD *)(*v1 - 16);
        if ( ((*(_DWORD *)(*v1 - 12) - v13) | (1 - *(_DWORD *)(*v1 - 8))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v1, v13);
        v14 = *v1;
        v15 = (const wchar_t *)*v1;
        v23 = *v1 + 2 * v11;
        if ( *v1 < v23 )
        {
          v16 = *v1 + 2 * v11;
          do
          {
            v17 = wcsstr(v15, L"]]>");
            if ( v17 )
            {
              v18 = v17;
              v19 = v26;
              do
              {
                v15 = &v18[v19];
                v20 = v11 - (((__int64)v18 - v14) >> 1) - v3;
                v21 = memmove_s(&v18[v19], 2LL * v20, &v18[v3], 2LL * v20);
                ATL::AtlCrtErrorCheck(v21);
                v22 = memcpy_s(v18, v19 * 2, L"__CDATA_XML_CLOSE_SYMBOL__", v19 * 2);
                ATL::AtlCrtErrorCheck(v22);
                v18[v20 + v26] = 0;
                LODWORD(v11) = v26 - v3 + v11;
                v18 = wcsstr(&v18[v19], L"]]>");
              }
              while ( v18 );
              v16 = v23;
            }
            v15 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v15) + 1);
          }
          while ( (unsigned __int64)v15 < v16 );
          v1 = a1;
          v6 = v25;
          v12 = v27;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v1, (unsigned int)v12);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180019784  mov     [rsp+arg_10], r8
0x180019789  mov     [rsp+arg_8], rdx
0x18001978e  mov     [rsp+arg_0], rcx
0x180019793  push    rbx
0x180019794  push    rbp
0x180019795  push    rsi
0x180019796  push    rdi
0x180019797  push    r12
0x180019799  push    r13
0x18001979b  push    r14
0x18001979d  push    r15
0x18001979f  sub     rsp, 38h
0x1800197a3  lea     r13, SubStr; "]]>"
0x1800197aa  mov     rsi, rcx
0x1800197ad  mov     rcx, r13
0x1800197b0  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800197b5  movsxd  r14, eax
0x1800197b8  test    eax, eax
0x1800197ba  jz      loc_18001999C
0x1800197c0  lea     rcx, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x1800197c7  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800197cc  mov     rbx, [rsi]
0x1800197cf  xor     ebp, ebp
0x1800197d1  mov     r12d, eax
0x1800197d4  mov     dword ptr [rsp+78h+arg_10], eax
0x1800197db  mov     dword ptr [rsp+78h+arg_8], ebp
0x1800197e2  movsxd  rcx, dword ptr [rbx-10h]
0x1800197e6  lea     r15, [rbx+rcx*2]
0x1800197ea  cmp     rbx, r15
0x1800197ed  jnb     loc_18001999A
0x1800197f3  mov     rdx, r13; SubStr
0x1800197f6  mov     rcx, rbx; Str
0x1800197f9  call    cs:__imp_wcsstr
0x1800197ff  test    rax, rax
0x180019802  jz      short loc_180019828
0x180019804  mov     rdi, r14
0x180019807  add     rdi, rdi
0x18001980a  lea     rbx, [rdi+rax]
0x18001980e  mov     rdx, r13; SubStr
0x180019811  mov     rcx, rbx; Str
0x180019814  inc     ebp
0x180019816  call    cs:__imp_wcsstr
0x18001981c  test    rax, rax
0x18001981f  jnz     short loc_18001980A
0x180019821  mov     dword ptr [rsp+78h+arg_8], ebp
0x180019828  mov     rcx, rbx
0x18001982b  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180019830  inc     eax
0x180019832  cdqe
0x180019834  lea     rbx, [rbx+rax*2]
0x180019838  cmp     rbx, r15
0x18001983b  jb      short loc_1800197F3
0x18001983d  test    ebp, ebp
0x18001983f  jle     loc_18001999A
0x180019845  mov     rdx, [rsi]
0x180019848  mov     r13d, r12d
0x18001984b  sub     r13d, r14d
0x18001984e  mov     ecx, 1
0x180019853  imul    r13d, ebp
0x180019857  movsxd  r15, dword ptr [rdx-10h]
0x18001985b  mov     eax, [rdx-0Ch]
0x18001985e  add     r13d, r15d
0x180019861  cmp     r13d, r15d
0x180019864  mov     [rsp+78h+arg_18], r13d
0x18001986c  mov     r8d, r13d
0x18001986f  cmovle  r8d, r15d
0x180019873  sub     ecx, [rdx-8]
0x180019876  sub     eax, r8d
0x180019879  or      ecx, eax
0x18001987b  jge     short loc_180019888
0x18001987d  mov     edx, r8d
0x180019880  mov     rcx, rsi
0x180019883  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180019888  mov     r12, [rsi]
0x18001988b  mov     rdi, r12
0x18001988e  lea     rax, [r12+r15*2]
0x180019892  mov     [rsp+78h+var_58], rax
0x180019897  cmp     r12, rax
0x18001989a  jnb     loc_18001998F
0x1800198a0  mov     rbp, rax
0x1800198a3  lea     rdx, SubStr; "]]>"
0x1800198aa  mov     rcx, rdi; Str
0x1800198ad  call    cs:__imp_wcsstr
0x1800198b3  test    rax, rax
0x1800198b6  jz      loc_18001995E
0x1800198bc  movsxd  r13, dword ptr [rsp+78h+arg_10]
0x1800198c4  mov     rsi, r14
0x1800198c7  add     rsi, rsi
0x1800198ca  mov     rbp, rax
0x1800198cd  add     r13, r13
0x1800198d0  mov     rcx, rbp
0x1800198d3  lea     r8, [rsi+rbp]; Source
0x1800198d7  sub     rcx, r12
0x1800198da  mov     ebx, r15d
0x1800198dd  sar     rcx, 1
0x1800198e0  mov     rdi, rbp
0x1800198e3  sub     ebx, ecx
0x1800198e5  add     rdi, r13
0x1800198e8  sub     ebx, r14d
0x1800198eb  mov     rcx, rdi; Destination
0x1800198ee  movsxd  rdx, ebx
0x1800198f1  add     rdx, rdx; DestinationSize
0x1800198f4  mov     r9, rdx; SourceSize
0x1800198f7  call    cs:__imp_memmove_s
0x1800198fd  mov     ecx, eax; int
0x1800198ff  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019904  mov     r9, r13; SourceSize
0x180019907  lea     r8, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x18001990e  mov     rdx, r13; DestinationSize
0x180019911  mov     rcx, rbp; Destination
0x180019914  call    cs:__imp_memcpy_s
0x18001991a  mov     ecx, eax; int
0x18001991c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019921  mov     edx, dword ptr [rsp+78h+arg_10]
0x180019928  lea     eax, [rbx+rdx]
0x18001992b  movsxd  rcx, eax
0x18001992e  xor     eax, eax
0x180019930  mov     [rbp+rcx*2+0], ax
0x180019935  mov     eax, edx
0x180019937  sub     eax, r14d
0x18001993a  lea     rdx, SubStr; "]]>"
0x180019941  mov     rcx, rdi; Str
0x180019944  add     r15d, eax
0x180019947  call    cs:__imp_wcsstr
0x18001994d  mov     rbp, rax
0x180019950  test    rax, rax
0x180019953  jnz     loc_1800198D0
0x180019959  mov     rbp, [rsp+78h+var_58]
0x18001995e  mov     rcx, rdi
0x180019961  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180019966  inc     eax
0x180019968  movsxd  rcx, eax
0x18001996b  lea     rdi, [rdi+rcx*2]
0x18001996f  cmp     rdi, rbp
0x180019972  jb      loc_1800198A3
0x180019978  mov     rsi, [rsp+78h+arg_0]
0x180019980  mov     ebp, dword ptr [rsp+78h+arg_8]
0x180019987  mov     r13d, [rsp+78h+arg_18]
0x18001998f  mov     edx, r13d
0x180019992  mov     rcx, rsi
0x180019995  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001999a  mov     eax, ebp
0x18001999c  add     rsp, 38h
0x1800199a0  pop     r15
0x1800199a2  pop     r14
0x1800199a4  pop     r13
0x1800199a6  pop     r12
0x1800199a8  pop     rdi
0x1800199a9  pop     rsi
0x1800199aa  pop     rbp
0x1800199ab  pop     rbx
0x1800199ac  retn
```
