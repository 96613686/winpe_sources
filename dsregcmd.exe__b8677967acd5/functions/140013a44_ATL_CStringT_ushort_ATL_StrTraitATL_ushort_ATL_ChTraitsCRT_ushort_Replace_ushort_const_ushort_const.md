# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x140013a44`
- end: `0x140013bf8`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140013c00`

## callees

- `0x14000274e`
- `0x140005c58`
- `0x1400060c4`
- `0x140013a44`
- `0x140014038`
- `0x14002c40c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140013bdc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140013bdc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013a8b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013b04`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013b73`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013a8b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013b04`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140013b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  int v1; // ebp
  const wchar_t *v2; // rbx
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r15
  const wchar_t *v8; // rbx
  unsigned __int64 v9; // r13
  __int64 v10; // rcx
  wchar_t *v11; // rsi
  int v12; // r13d
  size_t v13; // r8
  __int64 v14; // rax
  unsigned __int64 v16; // [rsp+20h] [rbp-48h]

  v1 = 0;
  v2 = (const wchar_t *)*a1;
  v3 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( *a1 < v3 )
  {
    do
    {
      while ( 1 )
      {
        v4 = wcsstr(v2, L"+");
        if ( !v4 )
          break;
        ++v1;
        v2 = v4 + 1;
      }
      if ( v2 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v2[v5] );
      }
      else
      {
        LODWORD(v5) = 0;
      }
      v2 += (int)v5 + 1;
    }
    while ( (unsigned __int64)v2 < v3 );
    if ( v1 > 0 )
    {
      v6 = *(int *)(*a1 - 16);
      if ( (int)((*(_DWORD *)(*a1 - 12) - v6) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v6);
      v7 = *a1;
      v8 = (const wchar_t *)*a1;
      v9 = *a1 + 2 * v6;
      if ( *a1 >= v9 )
        goto LABEL_27;
      while ( 1 )
      {
        v11 = wcsstr(v8, L"+");
        if ( !v11 )
          goto LABEL_21;
        do
        {
          v12 = v6 - (((__int64)v11 - v7) >> 1);
          v8 = v11 + 1;
          v13 = 2LL * (v12 - 1);
          if ( v13 )
          {
            if ( v11 == (wchar_t *)-2LL )
            {
              *(_DWORD *)_o__errno(v10, 0, v13) = 22;
              invalid_parameter_noinfo();
              goto LABEL_32;
            }
            memmove_0(v11 + 1, v11 + 1, v13);
          }
          ATL::Checked::memcpy_s((ATL::Checked *)v11, (void *)2, (unsigned __int64)L" ", (const void *)2, v16);
          v11[v12] = 0;
          v11 = wcsstr(v11 + 1, L"+");
        }
        while ( v11 );
        v9 = v7 + 2 * v6;
LABEL_21:
        if ( v8 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v8[v14] );
        }
        else
        {
          LODWORD(v14) = 0;
        }
        v8 += (int)v14 + 1;
        if ( (unsigned __int64)v8 >= v9 )
        {
LABEL_27:
          if ( (int)v6 >= 0 && (int)v6 <= *(_DWORD *)(*a1 - 12) )
          {
            *(_DWORD *)(*a1 - 16) = v6;
            *(_WORD *)(*a1 + 2 * v6) = 0;
            return (unsigned int)v1;
          }
LABEL_32:
          ATL::AtlThrowImpl(0x80070057);
        }
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140013a44  mov     [rsp+arg_0], rcx
0x140013a49  push    rbx
0x140013a4a  push    rbp
0x140013a4b  push    rsi
0x140013a4c  push    rdi
0x140013a4d  push    r12
0x140013a4f  push    r13
0x140013a51  push    r14
0x140013a53  push    r15
0x140013a55  sub     rsp, 28h
0x140013a59  xor     eax, eax
0x140013a5b  mov     ebp, eax
0x140013a5d  mov     rbx, [rcx]
0x140013a60  movsxd  rax, dword ptr [rbx-10h]
0x140013a64  lea     rdi, [rbx+rax*2]
0x140013a68  cmp     rbx, rdi
0x140013a6b  jnb     loc_140013BC9
0x140013a71  mov     esi, 1
0x140013a76  xor     r14d, r14d
0x140013a79  jmp     short loc_140013A81
0x140013a7b  add     ebp, esi
0x140013a7d  lea     rbx, [rax+2]
0x140013a81  lea     rdx, asc_140034DC8; "+"
0x140013a88  mov     rcx, rbx; Str
0x140013a8b  call    cs:__imp_wcsstr
0x140013a91  nop
0x140013a92  test    rax, rax
0x140013a95  jnz     short loc_140013A7B
0x140013a97  test    rbx, rbx
0x140013a9a  jz      short loc_140013AAC
0x140013a9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013aa0  inc     rax
0x140013aa3  cmp     [rbx+rax*2], r14w
0x140013aa8  jnz     short loc_140013AA0
0x140013aaa  jmp     short loc_140013AAF
0x140013aac  mov     eax, r14d
0x140013aaf  inc     eax
0x140013ab1  movsxd  rcx, eax
0x140013ab4  lea     rbx, [rbx+rcx*2]
0x140013ab8  cmp     rbx, rdi
0x140013abb  jb      short loc_140013A79
0x140013abd  test    ebp, ebp
0x140013abf  mov     r14, [rsp+68h+arg_0]
0x140013ac4  jle     loc_140013BC9
0x140013aca  mov     rax, [r14]
0x140013acd  movsxd  rdi, dword ptr [rax-10h]
0x140013ad1  sub     esi, [rax-8]
0x140013ad4  mov     eax, [rax-0Ch]
0x140013ad7  sub     eax, edi
0x140013ad9  or      esi, eax
0x140013adb  jge     short loc_140013AE7
0x140013add  mov     edx, edi
0x140013adf  mov     rcx, r14
0x140013ae2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140013ae7  mov     r15, [r14]
0x140013aea  mov     rbx, r15
0x140013aed  lea     r13, [r15+rdi*2]
0x140013af1  cmp     r15, r13
0x140013af4  jnb     loc_140013BB1
0x140013afa  lea     rdx, asc_140034DC8; "+"
0x140013b01  mov     rcx, rbx; Str
0x140013b04  call    cs:__imp_wcsstr
0x140013b0a  mov     rsi, rax
0x140013b0d  xor     edx, edx
0x140013b0f  test    rax, rax
0x140013b12  jz      short loc_140013B87
0x140013b14  mov     rax, rsi
0x140013b17  sub     rax, r15
0x140013b1a  sar     rax, 1
0x140013b1d  mov     r13d, edi
0x140013b20  sub     r13d, eax
0x140013b23  lea     rbx, [rsi+2]
0x140013b27  lea     eax, [r13-1]
0x140013b2b  movsxd  r8, eax
0x140013b2e  add     r8, r8; Size
0x140013b31  jz      short loc_140013B47
0x140013b33  test    rbx, rbx
0x140013b36  jz      loc_140013BDC
0x140013b3c  mov     rdx, rbx; Src
0x140013b3f  mov     rcx, rbx; void *
0x140013b42  call    memmove_0
0x140013b47  mov     eax, 2
0x140013b4c  mov     r9d, eax; void *
0x140013b4f  lea     r8, asc_140034DD0; " "
0x140013b56  mov     edx, eax; void *
0x140013b58  mov     rcx, rsi; this
0x140013b5b  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x140013b60  movsxd  rcx, r13d
0x140013b63  xor     eax, eax
0x140013b65  mov     [rsi+rcx*2], ax
0x140013b69  lea     rdx, asc_140034DC8; "+"
0x140013b70  mov     rcx, rbx; Str
0x140013b73  call    cs:__imp_wcsstr
0x140013b79  mov     rsi, rax
0x140013b7c  xor     edx, edx
0x140013b7e  test    rax, rax
0x140013b81  jnz     short loc_140013B14
0x140013b83  lea     r13, [r15+rdi*2]
0x140013b87  test    rbx, rbx
0x140013b8a  jz      short loc_140013B9B
0x140013b8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013b90  inc     rax
0x140013b93  cmp     [rbx+rax*2], dx
0x140013b97  jnz     short loc_140013B90
0x140013b99  jmp     short loc_140013B9D
0x140013b9b  mov     eax, edx
0x140013b9d  inc     eax
0x140013b9f  movsxd  rcx, eax
0x140013ba2  lea     rbx, [rbx+rcx*2]
0x140013ba6  cmp     rbx, r13
0x140013ba9  jb      loc_140013AFA
0x140013baf  jmp     short loc_140013BB3
0x140013bb1  xor     edx, edx
0x140013bb3  test    edi, edi
0x140013bb5  js      short loc_140013BED
0x140013bb7  mov     rax, [r14]
0x140013bba  cmp     edi, [rax-0Ch]
0x140013bbd  jg      short loc_140013BED
0x140013bbf  mov     [rax-10h], edi
0x140013bc2  mov     rcx, [r14]
0x140013bc5  mov     [rcx+rdi*2], dx
0x140013bc9  mov     eax, ebp
0x140013bcb  add     rsp, 28h
0x140013bcf  pop     r15
0x140013bd1  pop     r14
0x140013bd3  pop     r13
0x140013bd5  pop     r12
0x140013bd7  pop     rdi
0x140013bd8  pop     rsi
0x140013bd9  pop     rbp
0x140013bda  pop     rbx
0x140013bdb  retn
0x140013bdc  call    cs:__imp__o__errno
0x140013be2  mov     dword ptr [rax], 16h
0x140013be8  call    _invalid_parameter_noinfo
0x140013bed  mov     ecx, 80070057h; unsigned int
0x140013bf2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
