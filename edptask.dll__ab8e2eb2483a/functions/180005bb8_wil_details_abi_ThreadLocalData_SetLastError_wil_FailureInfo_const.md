# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005bb8`
- end: `0x180005e3d`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800044d0`

## callees

- `0x1800038ac`
- `0x180005468`
- `0x180005bb8`
- `0x1800133e2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005e07`
- `msvcrt!memcpy_s` at `0x180005e07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d6a`

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
0x180005bb8  push    rbx
0x180005bba  push    rbp
0x180005bbb  push    rsi
0x180005bbc  push    rdi
0x180005bbd  push    r12
0x180005bbf  push    r13
0x180005bc1  push    r14
0x180005bc3  push    r15
0x180005bc5  sub     rsp, 28h
0x180005bc9  mov     esi, [rcx+10h]
0x180005bcc  xor     r12d, r12d
0x180005bcf  mov     r15, rdx
0x180005bd2  mov     rbx, rcx
0x180005bd5  mov     ebp, 50h ; 'P'
0x180005bda  cmp     [rcx+18h], r12
0x180005bde  jnz     short loc_180005C15
0x180005be0  test    esi, esi
0x180005be2  jz      short loc_180005C15
0x180005be4  mov     edx, 190h; dwBytes
0x180005be9  lea     ecx, [rbp-48h]; dwFlags
0x180005bec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005bf1  mov     [rbx+18h], rax
0x180005bf5  test    rax, rax
0x180005bf8  jz      short loc_180005C15
0x180005bfa  mov     dword ptr [rbx+20h], 5
0x180005c01  lea     rcx, [rax+190h]
0x180005c08  jmp     short loc_180005C10
0x180005c0a  mov     [rax], bp
0x180005c0d  add     rax, rbp
0x180005c10  cmp     rax, rcx
0x180005c13  jnz     short loc_180005C0A
0x180005c15  mov     rdi, [rbx+18h]
0x180005c19  test    rdi, rdi
0x180005c1c  jz      loc_180005E2C
0x180005c22  test    esi, esi
0x180005c24  jz      short loc_180005C5C
0x180005c26  movzx   eax, word ptr [rbx+20h]
0x180005c2a  mov     rcx, rdi
0x180005c2d  lea     rdx, [rax+rax*4]
0x180005c31  shl     rdx, 4
0x180005c35  add     rdx, rdi
0x180005c38  cmp     rdi, rdx
0x180005c3b  jz      short loc_180005C5C
0x180005c3d  mov     r8d, [rbx+10h]
0x180005c41  cmp     [rcx+4], r8d
0x180005c45  jbe     short loc_180005C54
0x180005c47  mov     eax, [r15+8]
0x180005c4b  cmp     [rcx+8], eax
0x180005c4e  jz      loc_180005E2C
0x180005c54  add     rcx, rbp
0x180005c57  cmp     rcx, rdx
0x180005c5a  jnz     short loc_180005C41
0x180005c5c  movzx   eax, word ptr [rbx+22h]
0x180005c60  mov     r8d, 1
0x180005c66  movzx   ecx, word ptr [rbx+20h]
0x180005c6a  add     eax, r8d
0x180005c6d  xor     edx, edx
0x180005c6f  div     ecx
0x180005c71  mov     ecx, r8d
0x180005c74  movzx   eax, dx
0x180005c77  mov     [rbx+22h], dx
0x180005c7b  lea     rsi, [rax+rax*4]
0x180005c7f  mov     rax, [rbx+8]
0x180005c83  shl     rsi, 4
0x180005c87  lock xadd [rax], ecx
0x180005c8b  add     ecx, r8d
0x180005c8e  lea     r13, [rsi+rdi]
0x180005c92  mov     [rsi+rdi+4], ecx
0x180005c96  lea     rbx, [rdi+20h]
0x180005c9a  mov     eax, [r15+8]
0x180005c9e  add     rbx, rsi
0x180005ca1  mov     [rsi+rdi+8], eax
0x180005ca5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005ca9  mov     [r13+10h], r12
0x180005cad  movzx   eax, word ptr [r15+40h]
0x180005cb2  mov     [rsi+rdi+18h], ax
0x180005cb7  mov     al, [r15]
0x180005cba  mov     [rsi+rdi+1Ah], al
0x180005cbe  mov     [rbx], r12
0x180005cc1  mov     rax, [r15+88h]
0x180005cc8  mov     [rsi+rdi+28h], rax
0x180005ccd  mov     rax, [r15+90h]
0x180005cd4  mov     [rsi+rdi+30h], rax
0x180005cd9  mov     [rsi+rdi+38h], r12
0x180005cde  mov     rcx, [r15+38h]
0x180005ce2  test    rcx, rcx
0x180005ce5  jnz     short loc_180005CEC
0x180005ce7  mov     edx, r8d
0x180005cea  jmp     short loc_180005CFC
0x180005cec  mov     rax, r14
0x180005cef  inc     rax
0x180005cf2  cmp     [rcx+rax], r12b
0x180005cf6  jnz     short loc_180005CEF
0x180005cf8  lea     rdx, [rax+1]
0x180005cfc  mov     rcx, [r15+80h]
0x180005d03  test    rcx, rcx
0x180005d06  jz      short loc_180005D18
0x180005d08  mov     rax, r14
0x180005d0b  inc     rax
0x180005d0e  cmp     [rcx+rax], r12b
0x180005d12  jnz     short loc_180005D0B
0x180005d14  lea     r8, [rax+1]; unsigned __int64
0x180005d18  mov     rcx, [r15+18h]
0x180005d1c  test    rcx, rcx
0x180005d1f  jnz     short loc_180005D26
0x180005d21  lea     eax, [rcx+2]
0x180005d24  jmp     short loc_180005D3B
0x180005d26  mov     rax, r14
0x180005d29  inc     rax
0x180005d2c  cmp     [rcx+rax*2], r12w
0x180005d31  jnz     short loc_180005D29
0x180005d33  lea     rax, ds:2[rax*2]
0x180005d3b  lea     rbp, [r8+rax]
0x180005d3f  add     rbp, rdx
0x180005d42  cmp     [rsi+rdi+40h], r12
0x180005d47  jz      short loc_180005D50
0x180005d49  cmp     [rsi+rdi+48h], rbp
0x180005d4e  jnb     short loc_180005D92
0x180005d50  mov     rdx, rbp; dwBytes
0x180005d53  mov     ecx, 8; dwFlags
0x180005d58  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005d5d  mov     r12, rax
0x180005d60  test    rax, rax
0x180005d63  jz      short loc_180005D8F
0x180005d65  mov     rbx, [rsi+rdi+40h]
0x180005d6a  call    cs:__imp_GetProcessHeap
0x180005d70  mov     r8, rbx; lpMem
0x180005d73  xor     edx, edx; dwFlags
0x180005d75  mov     rcx, rax; hHeap
0x180005d78  call    cs:__imp_HeapFree
0x180005d7e  lea     rbx, [rdi+20h]
0x180005d82  mov     [rsi+rdi+40h], r12
0x180005d87  add     rbx, rsi
0x180005d8a  mov     [rsi+rdi+48h], rbp
0x180005d8f  xor     r12d, r12d
0x180005d92  mov     rcx, [rsi+rdi+40h]
0x180005d97  test    rcx, rcx
0x180005d9a  jz      loc_180005E2C
0x180005da0  mov     rbp, [rsi+rdi+48h]
0x180005da5  lea     r9, [r13+10h]
0x180005da9  mov     r8, [r15+38h]
0x180005dad  add     rbp, rcx
0x180005db0  mov     rdx, rbp
0x180005db3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005db8  mov     r8, [r15+80h]
0x180005dbf  mov     r9, rbx
0x180005dc2  mov     rdx, rbp
0x180005dc5  mov     rcx, rax
0x180005dc8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005dcd  mov     rbx, rax
0x180005dd0  cmp     rax, rbp
0x180005dd3  jz      short loc_180005E17
0x180005dd5  mov     r8, [r15+18h]; Source
0x180005dd9  test    r8, r8
0x180005ddc  jz      short loc_180005E17
0x180005dde  cmp     [r8], r12w
0x180005de2  jz      short loc_180005E17
0x180005de4  inc     r14
0x180005de7  cmp     [r8+r14*2], r12w
0x180005dec  jnz     short loc_180005DE4
0x180005dee  mov     rdx, rbp
0x180005df1  lea     r14, ds:2[r14*2]
0x180005df9  sub     rdx, rbx; DestinationSize
0x180005dfc  cmp     rdx, r14
0x180005dff  jb      short loc_180005E17
0x180005e01  mov     r9, r14; SourceSize
0x180005e04  mov     rcx, rbx; Destination
0x180005e07  call    cs:__imp_memcpy_s
0x180005e0d  mov     [rsi+rdi+38h], rbx
0x180005e12  add     rbx, r14
0x180005e15  jmp     short loc_180005E1C
0x180005e17  mov     [rsi+rdi+38h], r12
0x180005e1c  sub     rbp, rbx
0x180005e1f  xor     edx, edx; Val
0x180005e21  mov     r8, rbp; Size
0x180005e24  mov     rcx, rbx; void *
0x180005e27  call    memset_0
0x180005e2c  add     rsp, 28h
0x180005e30  pop     r15
0x180005e32  pop     r14
0x180005e34  pop     r13
0x180005e36  pop     r12
0x180005e38  pop     rdi
0x180005e39  pop     rsi
0x180005e3a  pop     rbp
0x180005e3b  pop     rbx
0x180005e3c  retn
```
