# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18001a038`
- end: `0x18001a235`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `509`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180018bac`

## callees

- `0x180007a20`
- `0x180009948`
- `0x18000bc80`
- `0x18000c16c`
- `0x180017f7c`
- `0x18001a038`
- `0x18001a23c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a0ae`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a0cf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a14a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a1d2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a0ae`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a0cf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a14a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001a1d2`

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
0x18001a038  mov     [rsp+arg_10], r8
0x18001a03d  mov     [rsp+arg_8], rdx
0x18001a042  mov     [rsp+arg_0], rcx
0x18001a047  push    rbx
0x18001a048  push    rbp
0x18001a049  push    rsi
0x18001a04a  push    rdi
0x18001a04b  push    r12
0x18001a04d  push    r13
0x18001a04f  push    r14
0x18001a051  push    r15
0x18001a053  sub     rsp, 38h
0x18001a057  mov     r14, rcx
0x18001a05a  lea     rcx, aFramework64; "\\Framework64\\"
0x18001a061  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001a066  movsxd  rbp, eax
0x18001a069  test    eax, eax
0x18001a06b  jz      loc_18001A224
0x18001a071  lea     rcx, aFramework; "\\Framework\\"
0x18001a078  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001a07d  mov     rbx, [r14]
0x18001a080  xor     esi, esi
0x18001a082  mov     r12d, eax
0x18001a085  mov     dword ptr [rsp+78h+arg_10], eax
0x18001a08c  mov     dword ptr [rsp+78h+arg_8], esi
0x18001a093  movsxd  rcx, dword ptr [rbx-10h]
0x18001a097  lea     r15, [rbx+rcx*2]
0x18001a09b  cmp     rbx, r15
0x18001a09e  jnb     loc_18001A222
0x18001a0a4  lea     rdx, aFramework64; "\\Framework64\\"
0x18001a0ab  mov     rcx, rbx; Str
0x18001a0ae  call    cs:__imp_wcsstr
0x18001a0b4  test    rax, rax
0x18001a0b7  jz      short loc_18001A0E1
0x18001a0b9  mov     rdi, rbp
0x18001a0bc  add     rdi, rdi
0x18001a0bf  lea     rbx, [rdi+rax]
0x18001a0c3  inc     esi
0x18001a0c5  mov     rcx, rbx; Str
0x18001a0c8  lea     rdx, aFramework64; "\\Framework64\\"
0x18001a0cf  call    cs:__imp_wcsstr
0x18001a0d5  test    rax, rax
0x18001a0d8  jnz     short loc_18001A0BF
0x18001a0da  mov     dword ptr [rsp+78h+arg_8], esi
0x18001a0e1  mov     rcx, rbx
0x18001a0e4  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001a0e9  inc     eax
0x18001a0eb  cdqe
0x18001a0ed  lea     rbx, [rbx+rax*2]
0x18001a0f1  cmp     rbx, r15
0x18001a0f4  jb      short loc_18001A0A4
0x18001a0f6  test    esi, esi
0x18001a0f8  jle     loc_18001A222
0x18001a0fe  mov     rax, [r14]
0x18001a101  mov     rcx, r14
0x18001a104  movsxd  r15, dword ptr [rax-10h]
0x18001a108  mov     eax, r12d
0x18001a10b  sub     eax, ebp
0x18001a10d  imul    eax, esi
0x18001a110  add     eax, r15d
0x18001a113  cmp     eax, r15d
0x18001a116  mov     [rsp+78h+arg_18], eax
0x18001a11d  mov     edx, eax
0x18001a11f  cmovle  edx, r15d
0x18001a123  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18001a128  mov     rdi, rax
0x18001a12b  lea     rcx, [rax+r15*2]
0x18001a12f  mov     [rsp+78h+var_50], rcx
0x18001a134  cmp     rax, rcx
0x18001a137  jnb     loc_18001A213
0x18001a13d  mov     rsi, rax
0x18001a140  lea     rdx, aFramework64; "\\Framework64\\"
0x18001a147  mov     rcx, rdi; Str
0x18001a14a  call    cs:__imp_wcsstr
0x18001a150  mov     r14, rax
0x18001a153  test    rax, rax
0x18001a156  jz      loc_18001A1E8
0x18001a15c  mov     r13, rbp
0x18001a15f  movsxd  r12, r12d
0x18001a162  add     r13, r13
0x18001a165  add     r12, r12
0x18001a168  mov     rcx, r14
0x18001a16b  lea     rdi, [r12+r14]
0x18001a16f  sub     rcx, rsi
0x18001a172  lea     r8, [r14+r13]; unsigned __int64
0x18001a176  sar     rcx, 1
0x18001a179  mov     ebx, r15d
0x18001a17c  sub     ebx, ecx
0x18001a17e  mov     rcx, rdi; this
0x18001a181  sub     ebx, ebp
0x18001a183  movsxd  rdx, ebx
0x18001a186  add     rdx, rdx; void *
0x18001a189  mov     r9, rdx; void *
0x18001a18c  call    ?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001a191  mov     r9, r12; SourceSize
0x18001a194  lea     r8, aFramework; "\\Framework\\"
0x18001a19b  mov     rdx, r12; DestinationSize
0x18001a19e  mov     rcx, r14; Destination
0x18001a1a1  call    memcpy_s
0x18001a1a6  mov     ecx, eax; int
0x18001a1a8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001a1ad  mov     edx, dword ptr [rsp+78h+arg_10]
0x18001a1b4  lea     eax, [rbx+rdx]
0x18001a1b7  movsxd  rcx, eax
0x18001a1ba  xor     eax, eax
0x18001a1bc  mov     [r14+rcx*2], ax
0x18001a1c1  mov     eax, edx
0x18001a1c3  sub     eax, ebp
0x18001a1c5  lea     rdx, aFramework64; "\\Framework64\\"
0x18001a1cc  mov     rcx, rdi; Str
0x18001a1cf  add     r15d, eax
0x18001a1d2  call    cs:__imp_wcsstr
0x18001a1d8  mov     r14, rax
0x18001a1db  test    rax, rax
0x18001a1de  jnz     short loc_18001A168
0x18001a1e0  mov     r12d, dword ptr [rsp+78h+arg_10]
0x18001a1e8  mov     rcx, rdi
0x18001a1eb  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18001a1f0  inc     eax
0x18001a1f2  movsxd  rcx, eax
0x18001a1f5  lea     rdi, [rdi+rcx*2]
0x18001a1f9  cmp     rdi, [rsp+78h+var_50]
0x18001a1fe  jb      loc_18001A140
0x18001a204  mov     esi, dword ptr [rsp+78h+arg_8]
0x18001a20b  mov     r14, [rsp+78h+arg_0]
0x18001a213  mov     edx, [rsp+78h+arg_18]
0x18001a21a  mov     rcx, r14
0x18001a21d  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001a222  mov     eax, esi
0x18001a224  add     rsp, 38h
0x18001a228  pop     r15
0x18001a22a  pop     r14
0x18001a22c  pop     r13
0x18001a22e  pop     r12
0x18001a230  pop     rdi
0x18001a231  pop     rsi
0x18001a232  pop     rbp
0x18001a233  pop     rbx
0x18001a234  retn
```
