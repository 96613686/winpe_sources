# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009dbc`
- end: `0x18000a041`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800083f0`

## callees

- `0x1800037dc`
- `0x180009238`
- `0x180009dbc`
- `0x18004371a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a00b`
- `msvcrt!memcpy_s` at `0x18000a00b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f7c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  char *v27; // rcx
  char *v28; // rbp
  char *v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(char **)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = &v27[*(_QWORD *)(v12 + v7 + 72)];
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_BYTE **)a2 + 7), (_QWORD *)(v12 + v7 + 16));
        v30 = wil::details::WriteResultString<char const *>(v29, v28, *((_BYTE **)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x180009dbc  push    rbx
0x180009dbe  push    rbp
0x180009dbf  push    rsi
0x180009dc0  push    rdi
0x180009dc1  push    r12
0x180009dc3  push    r13
0x180009dc5  push    r14
0x180009dc7  push    r15
0x180009dc9  sub     rsp, 28h
0x180009dcd  mov     esi, [rcx+10h]
0x180009dd0  xor     r12d, r12d
0x180009dd3  mov     r15, rdx
0x180009dd6  mov     rbx, rcx
0x180009dd9  mov     ebp, 50h ; 'P'
0x180009dde  cmp     [rcx+18h], r12
0x180009de2  jnz     short loc_180009E19
0x180009de4  test    esi, esi
0x180009de6  jz      short loc_180009E19
0x180009de8  mov     edx, 190h; dwBytes
0x180009ded  lea     ecx, [rbp-48h]; dwFlags
0x180009df0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009df5  mov     [rbx+18h], rax
0x180009df9  test    rax, rax
0x180009dfc  jz      short loc_180009E19
0x180009dfe  mov     dword ptr [rbx+20h], 5
0x180009e05  lea     rcx, [rax+190h]
0x180009e0c  jmp     short loc_180009E14
0x180009e0e  mov     [rax], bp
0x180009e11  add     rax, rbp
0x180009e14  cmp     rax, rcx
0x180009e17  jnz     short loc_180009E0E
0x180009e19  mov     rdi, [rbx+18h]
0x180009e1d  test    rdi, rdi
0x180009e20  jz      loc_18000A030
0x180009e26  test    esi, esi
0x180009e28  jz      short loc_180009E60
0x180009e2a  movzx   eax, word ptr [rbx+20h]
0x180009e2e  mov     rcx, rdi
0x180009e31  lea     rdx, [rax+rax*4]
0x180009e35  shl     rdx, 4
0x180009e39  add     rdx, rdi
0x180009e3c  cmp     rdi, rdx
0x180009e3f  jz      short loc_180009E60
0x180009e41  mov     r8d, [rbx+10h]
0x180009e45  cmp     [rcx+4], r8d
0x180009e49  jbe     short loc_180009E58
0x180009e4b  mov     eax, [r15+8]
0x180009e4f  cmp     [rcx+8], eax
0x180009e52  jz      loc_18000A030
0x180009e58  add     rcx, rbp
0x180009e5b  cmp     rcx, rdx
0x180009e5e  jnz     short loc_180009E45
0x180009e60  movzx   eax, word ptr [rbx+22h]
0x180009e64  mov     r8d, 1
0x180009e6a  movzx   ecx, word ptr [rbx+20h]
0x180009e6e  add     eax, r8d
0x180009e71  xor     edx, edx
0x180009e73  div     ecx
0x180009e75  mov     ecx, r8d
0x180009e78  movzx   eax, dx
0x180009e7b  mov     [rbx+22h], dx
0x180009e7f  lea     rsi, [rax+rax*4]
0x180009e83  mov     rax, [rbx+8]
0x180009e87  shl     rsi, 4
0x180009e8b  lock xadd [rax], ecx
0x180009e8f  add     ecx, r8d
0x180009e92  lea     r13, [rsi+rdi]
0x180009e96  mov     [rsi+rdi+4], ecx
0x180009e9a  lea     rbx, [rdi+20h]
0x180009e9e  mov     eax, [r15+8]
0x180009ea2  add     rbx, rsi
0x180009ea5  mov     [rsi+rdi+8], eax
0x180009ea9  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009ead  mov     [r13+10h], r12
0x180009eb1  movzx   eax, word ptr [r15+40h]
0x180009eb6  mov     [rsi+rdi+18h], ax
0x180009ebb  mov     al, [r15]
0x180009ebe  mov     [rsi+rdi+1Ah], al
0x180009ec2  mov     [rbx], r12
0x180009ec5  mov     rax, [r15+88h]
0x180009ecc  mov     [rsi+rdi+28h], rax
0x180009ed1  mov     rax, [r15+90h]
0x180009ed8  mov     [rsi+rdi+30h], rax
0x180009edd  mov     [rsi+rdi+38h], r12
0x180009ee2  mov     rcx, [r15+38h]
0x180009ee6  test    rcx, rcx
0x180009ee9  jnz     short loc_180009EF0
0x180009eeb  mov     edx, r8d
0x180009eee  jmp     short loc_180009F00
0x180009ef0  mov     rax, r14
0x180009ef3  inc     rax
0x180009ef6  cmp     [rcx+rax], r12b
0x180009efa  jnz     short loc_180009EF3
0x180009efc  lea     rdx, [rax+1]
0x180009f00  mov     rcx, [r15+80h]
0x180009f07  test    rcx, rcx
0x180009f0a  jz      short loc_180009F1C
0x180009f0c  mov     rax, r14
0x180009f0f  inc     rax
0x180009f12  cmp     [rcx+rax], r12b
0x180009f16  jnz     short loc_180009F0F
0x180009f18  lea     r8, [rax+1]; unsigned __int64
0x180009f1c  mov     rcx, [r15+18h]
0x180009f20  test    rcx, rcx
0x180009f23  jnz     short loc_180009F2A
0x180009f25  lea     eax, [rcx+2]
0x180009f28  jmp     short loc_180009F3F
0x180009f2a  mov     rax, r14
0x180009f2d  inc     rax
0x180009f30  cmp     [rcx+rax*2], r12w
0x180009f35  jnz     short loc_180009F2D
0x180009f37  lea     rax, ds:2[rax*2]
0x180009f3f  lea     rbp, [r8+rax]
0x180009f43  add     rbp, rdx
0x180009f46  cmp     [rsi+rdi+40h], r12
0x180009f4b  jz      short loc_180009F54
0x180009f4d  cmp     [rsi+rdi+48h], rbp
0x180009f52  jnb     short loc_180009F96
0x180009f54  mov     rdx, rbp; dwBytes
0x180009f57  mov     ecx, 8; dwFlags
0x180009f5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009f61  mov     r12, rax
0x180009f64  test    rax, rax
0x180009f67  jz      short loc_180009F93
0x180009f69  mov     rbx, [rsi+rdi+40h]
0x180009f6e  call    cs:__imp_GetProcessHeap
0x180009f74  mov     r8, rbx; lpMem
0x180009f77  xor     edx, edx; dwFlags
0x180009f79  mov     rcx, rax; hHeap
0x180009f7c  call    cs:__imp_HeapFree
0x180009f82  lea     rbx, [rdi+20h]
0x180009f86  mov     [rsi+rdi+40h], r12
0x180009f8b  add     rbx, rsi
0x180009f8e  mov     [rsi+rdi+48h], rbp
0x180009f93  xor     r12d, r12d
0x180009f96  mov     rcx, [rsi+rdi+40h]
0x180009f9b  test    rcx, rcx
0x180009f9e  jz      loc_18000A030
0x180009fa4  mov     rbp, [rsi+rdi+48h]
0x180009fa9  lea     r9, [r13+10h]
0x180009fad  mov     r8, [r15+38h]
0x180009fb1  add     rbp, rcx
0x180009fb4  mov     rdx, rbp
0x180009fb7  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009fbc  mov     r8, [r15+80h]
0x180009fc3  mov     r9, rbx
0x180009fc6  mov     rdx, rbp
0x180009fc9  mov     rcx, rax
0x180009fcc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009fd1  mov     rbx, rax
0x180009fd4  cmp     rax, rbp
0x180009fd7  jz      short loc_18000A01B
0x180009fd9  mov     r8, [r15+18h]; Source
0x180009fdd  test    r8, r8
0x180009fe0  jz      short loc_18000A01B
0x180009fe2  cmp     [r8], r12w
0x180009fe6  jz      short loc_18000A01B
0x180009fe8  inc     r14
0x180009feb  cmp     [r8+r14*2], r12w
0x180009ff0  jnz     short loc_180009FE8
0x180009ff2  mov     rdx, rbp
0x180009ff5  lea     r14, ds:2[r14*2]
0x180009ffd  sub     rdx, rbx; DestinationSize
0x18000a000  cmp     rdx, r14
0x18000a003  jb      short loc_18000A01B
0x18000a005  mov     r9, r14; SourceSize
0x18000a008  mov     rcx, rbx; Destination
0x18000a00b  call    cs:__imp_memcpy_s
0x18000a011  mov     [rsi+rdi+38h], rbx
0x18000a016  add     rbx, r14
0x18000a019  jmp     short loc_18000A020
0x18000a01b  mov     [rsi+rdi+38h], r12
0x18000a020  sub     rbp, rbx
0x18000a023  xor     edx, edx; Val
0x18000a025  mov     r8, rbp; Size
0x18000a028  mov     rcx, rbx; void *
0x18000a02b  call    memset_0
0x18000a030  add     rsp, 28h
0x18000a034  pop     r15
0x18000a036  pop     r14
0x18000a038  pop     r13
0x18000a03a  pop     r12
0x18000a03c  pop     rdi
0x18000a03d  pop     rsi
0x18000a03e  pop     rbp
0x18000a03f  pop     rbx
0x18000a040  retn
```
