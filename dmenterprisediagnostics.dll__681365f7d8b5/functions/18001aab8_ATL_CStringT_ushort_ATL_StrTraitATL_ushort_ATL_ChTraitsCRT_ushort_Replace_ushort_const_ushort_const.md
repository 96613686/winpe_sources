# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18001aab8`
- end: `0x18001acce`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800195c0`

## callees

- `0x180007d7c`
- `0x180009e24`
- `0x18000c1fc`
- `0x18000c740`
- `0x1800189c4`
- `0x18001aab8`
- `0x18001acd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ab2e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ab55`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001abd6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ac64`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ab2e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ab55`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001abd6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001ac64`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        unsigned __int64 *a1)
{
  unsigned __int64 *v1; // r14
  __int64 result; // rax
  __int64 v3; // rbp
  int v4; // eax
  const wchar_t *v5; // rbx
  int v6; // esi
  int v7; // r12d
  unsigned __int64 v8; // r15
  wchar_t *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r15
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  const wchar_t *v14; // rdi
  unsigned __int64 v15; // rsi
  wchar_t *v16; // r14
  rsize_t v17; // r12
  int v18; // ebx
  errno_t v19; // eax
  unsigned __int64 v20; // [rsp+20h] [rbp-58h]
  unsigned __int64 v21; // [rsp+28h] [rbp-50h]
  int v23; // [rsp+88h] [rbp+10h]
  int v24; // [rsp+90h] [rbp+18h]
  unsigned int v25; // [rsp+98h] [rbp+20h]

  v1 = a1;
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"\\Framework64\\");
  v3 = (int)result;
  if ( (_DWORD)result )
  {
    v4 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(L"\\Framework\\");
    v5 = (const wchar_t *)*v1;
    v6 = 0;
    v7 = v4;
    v24 = v4;
    v23 = 0;
    v8 = *v1 + 2LL * *(int *)(*v1 - 16);
    if ( *v1 < v8 )
    {
      do
      {
        v9 = wcsstr(v5, L"\\Framework64\\");
        if ( v9 )
        {
          v10 = v3;
          do
          {
            v5 = &v9[v10];
            ++v6;
            v9 = wcsstr(&v9[v10], L"\\Framework64\\");
          }
          while ( v9 );
          v23 = v6;
        }
        v5 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v5) + 1);
      }
      while ( (unsigned __int64)v5 < v8 );
      if ( v6 > 0 )
      {
        v11 = *(int *)(*v1 - 16);
        v25 = v11 + v6 * (v7 - v3);
        v12 = v25;
        if ( (int)v25 <= (int)v11 )
          v12 = (unsigned int)v11;
        v13 = ATL::CSimpleStringT<unsigned short,0>::PrepareWrite((__int64)v1, v12);
        v14 = (const wchar_t *)v13;
        v21 = v13 + 2 * v11;
        if ( v13 < v21 )
        {
          v15 = v13;
          do
          {
            v16 = wcsstr(v14, L"\\Framework64\\");
            if ( v16 )
            {
              v17 = v7;
              do
              {
                v14 = &v16[v17];
                v18 = v11 - ((__int64)((__int64)v16 - v15) >> 1) - v3;
                ATL::Checked::memmove_s(
                  (ATL::Checked *)&v16[v17],
                  (void *)(2LL * v18),
                  (unsigned __int64)&v16[v3],
                  (const void *)(2LL * v18),
                  v20);
                v19 = memcpy_s(v16, v17 * 2, L"\\Framework\\", v17 * 2);
                ATL::AtlCrtErrorCheck(v19);
                v16[v18 + v24] = 0;
                LODWORD(v11) = v24 - v3 + v11;
                v16 = wcsstr(&v16[v17], L"\\Framework64\\");
              }
              while ( v16 );
              v7 = v24;
            }
            v14 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v14) + 1);
          }
          while ( (unsigned __int64)v14 < v21 );
          v6 = v23;
          v1 = a1;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v1, v25);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001aab8  mov     [rsp+arg_10], r8
0x18001aabd  mov     [rsp+arg_8], rdx
0x18001aac2  mov     [rsp+arg_0], rcx
0x18001aac7  push    rbx
0x18001aac8  push    rbp
0x18001aac9  push    rsi
0x18001aaca  push    rdi
0x18001aacb  push    r12
0x18001aacd  push    r13
0x18001aacf  push    r14
0x18001aad1  push    r15
0x18001aad3  sub     rsp, 38h
0x18001aad7  mov     r14, rcx
0x18001aada  lea     rcx, aFramework64; "\\Framework64\\"
0x18001aae1  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001aae6  movsxd  rbp, eax
0x18001aae9  test    eax, eax
0x18001aaeb  jz      loc_18001ACBC
0x18001aaf1  lea     rcx, aFramework; "\\Framework\\"
0x18001aaf8  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001aafd  mov     rbx, [r14]
0x18001ab00  xor     esi, esi
0x18001ab02  mov     r12d, eax
0x18001ab05  mov     dword ptr [rsp+78h+arg_10], eax
0x18001ab0c  mov     dword ptr [rsp+78h+arg_8], esi
0x18001ab13  movsxd  rcx, dword ptr [rbx-10h]
0x18001ab17  lea     r15, [rbx+rcx*2]
0x18001ab1b  cmp     rbx, r15
0x18001ab1e  jnb     loc_18001ACBA
0x18001ab24  lea     rdx, aFramework64; "\\Framework64\\"
0x18001ab2b  mov     rcx, rbx; Str
0x18001ab2e  call    cs:__imp_wcsstr
0x18001ab35  nop     dword ptr [rax+rax+00h]
0x18001ab3a  test    rax, rax
0x18001ab3d  jz      short loc_18001AB6D
0x18001ab3f  mov     rdi, rbp
0x18001ab42  add     rdi, rdi
0x18001ab45  lea     rbx, [rdi+rax]
0x18001ab49  inc     esi
0x18001ab4b  mov     rcx, rbx; Str
0x18001ab4e  lea     rdx, aFramework64; "\\Framework64\\"
0x18001ab55  call    cs:__imp_wcsstr
0x18001ab5c  nop     dword ptr [rax+rax+00h]
0x18001ab61  test    rax, rax
0x18001ab64  jnz     short loc_18001AB45
0x18001ab66  mov     dword ptr [rsp+78h+arg_8], esi
0x18001ab6d  mov     rcx, rbx
0x18001ab70  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001ab75  inc     eax
0x18001ab77  cdqe
0x18001ab79  lea     rbx, [rbx+rax*2]
0x18001ab7d  cmp     rbx, r15
0x18001ab80  jb      short loc_18001AB24
0x18001ab82  test    esi, esi
0x18001ab84  jle     loc_18001ACBA
0x18001ab8a  mov     rax, [r14]
0x18001ab8d  mov     rcx, r14
0x18001ab90  movsxd  r15, dword ptr [rax-10h]
0x18001ab94  mov     eax, r12d
0x18001ab97  sub     eax, ebp
0x18001ab99  imul    eax, esi
0x18001ab9c  add     eax, r15d
0x18001ab9f  cmp     eax, r15d
0x18001aba2  mov     [rsp+78h+arg_18], eax
0x18001aba9  mov     edx, eax
0x18001abab  cmovle  edx, r15d
0x18001abaf  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18001abb4  mov     rdi, rax
0x18001abb7  lea     rcx, [rax+r15*2]
0x18001abbb  mov     [rsp+78h+var_50], rcx
0x18001abc0  cmp     rax, rcx
0x18001abc3  jnb     loc_18001ACAB
0x18001abc9  mov     rsi, rax
0x18001abcc  lea     rdx, aFramework64; "\\Framework64\\"
0x18001abd3  mov     rcx, rdi; Str
0x18001abd6  call    cs:__imp_wcsstr
0x18001abdd  nop     dword ptr [rax+rax+00h]
0x18001abe2  mov     r14, rax
0x18001abe5  test    rax, rax
0x18001abe8  jz      loc_18001AC80
0x18001abee  mov     r13, rbp
0x18001abf1  movsxd  r12, r12d
0x18001abf4  add     r13, r13
0x18001abf7  add     r12, r12
0x18001abfa  mov     rcx, r14
0x18001abfd  lea     rdi, [r12+r14]
0x18001ac01  sub     rcx, rsi
0x18001ac04  lea     r8, [r14+r13]; unsigned __int64
0x18001ac08  sar     rcx, 1
0x18001ac0b  mov     ebx, r15d
0x18001ac0e  sub     ebx, ecx
0x18001ac10  mov     rcx, rdi; this
0x18001ac13  sub     ebx, ebp
0x18001ac15  movsxd  rdx, ebx
0x18001ac18  add     rdx, rdx; void *
0x18001ac1b  mov     r9, rdx; void *
0x18001ac1e  call    ?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001ac23  mov     r9, r12; SourceSize
0x18001ac26  lea     r8, aFramework; "\\Framework\\"
0x18001ac2d  mov     rdx, r12; DestinationSize
0x18001ac30  mov     rcx, r14; Destination
0x18001ac33  call    memcpy_s
0x18001ac38  mov     ecx, eax; int
0x18001ac3a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001ac3f  mov     edx, dword ptr [rsp+78h+arg_10]
0x18001ac46  lea     eax, [rbx+rdx]
0x18001ac49  movsxd  rcx, eax
0x18001ac4c  xor     eax, eax
0x18001ac4e  mov     [r14+rcx*2], ax
0x18001ac53  mov     eax, edx
0x18001ac55  sub     eax, ebp
0x18001ac57  lea     rdx, aFramework64; "\\Framework64\\"
0x18001ac5e  mov     rcx, rdi; Str
0x18001ac61  add     r15d, eax
0x18001ac64  call    cs:__imp_wcsstr
0x18001ac6b  nop     dword ptr [rax+rax+00h]
0x18001ac70  mov     r14, rax
0x18001ac73  test    rax, rax
0x18001ac76  jnz     short loc_18001ABFA
0x18001ac78  mov     r12d, dword ptr [rsp+78h+arg_10]
0x18001ac80  mov     rcx, rdi
0x18001ac83  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001ac88  inc     eax
0x18001ac8a  movsxd  rcx, eax
0x18001ac8d  lea     rdi, [rdi+rcx*2]
0x18001ac91  cmp     rdi, [rsp+78h+var_50]
0x18001ac96  jb      loc_18001ABCC
0x18001ac9c  mov     esi, dword ptr [rsp+78h+arg_8]
0x18001aca3  mov     r14, [rsp+78h+arg_0]
0x18001acab  mov     edx, [rsp+78h+arg_18]
0x18001acb2  mov     rcx, r14
0x18001acb5  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001acba  mov     eax, esi
0x18001acbc  add     rsp, 38h
0x18001acc0  pop     r15
0x18001acc2  pop     r14
0x18001acc4  pop     r13
0x18001acc6  pop     r12
0x18001acc8  pop     rdi
0x18001acc9  pop     rsi
0x18001acca  pop     rbp
0x18001accb  pop     rbx
0x18001accc  retn
```
