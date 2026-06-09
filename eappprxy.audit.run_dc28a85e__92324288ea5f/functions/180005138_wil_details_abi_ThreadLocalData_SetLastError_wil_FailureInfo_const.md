# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005138`
- end: `0x1800053c9`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `657`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003630`

## callees

- `0x180002106`
- `0x180002bf8`
- `0x180004904`
- `0x180005138`
- `0x18000b36c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052fe`

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
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
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
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
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
0x180005138  push    rbx
0x18000513a  push    rbp
0x18000513b  push    rsi
0x18000513c  push    rdi
0x18000513d  push    r12
0x18000513f  push    r13
0x180005141  push    r14
0x180005143  push    r15
0x180005145  sub     rsp, 28h
0x180005149  mov     esi, [rcx+10h]
0x18000514c  xor     r12d, r12d
0x18000514f  mov     r15, rdx
0x180005152  mov     rbx, rcx
0x180005155  mov     ebp, 50h ; 'P'
0x18000515a  cmp     [rcx+18h], r12
0x18000515e  jnz     short loc_180005195
0x180005160  test    esi, esi
0x180005162  jz      short loc_180005195
0x180005164  mov     edx, 190h; dwBytes
0x180005169  lea     ecx, [rbp-48h]; dwFlags
0x18000516c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005171  mov     [rbx+18h], rax
0x180005175  test    rax, rax
0x180005178  jz      short loc_180005195
0x18000517a  mov     dword ptr [rbx+20h], 5
0x180005181  lea     rcx, [rax+190h]
0x180005188  jmp     short loc_180005190
0x18000518a  mov     [rax], bp
0x18000518d  add     rax, rbp
0x180005190  cmp     rax, rcx
0x180005193  jnz     short loc_18000518A
0x180005195  mov     rdi, [rbx+18h]
0x180005199  test    rdi, rdi
0x18000519c  jz      loc_1800053B7
0x1800051a2  test    esi, esi
0x1800051a4  jz      short loc_1800051DC
0x1800051a6  movzx   eax, word ptr [rbx+20h]
0x1800051aa  mov     rcx, rdi
0x1800051ad  lea     rdx, [rax+rax*4]
0x1800051b1  shl     rdx, 4
0x1800051b5  add     rdx, rdi
0x1800051b8  cmp     rdi, rdx
0x1800051bb  jz      short loc_1800051DC
0x1800051bd  mov     r8d, [rbx+10h]
0x1800051c1  cmp     [rcx+4], r8d
0x1800051c5  jbe     short loc_1800051D4
0x1800051c7  mov     eax, [r15+8]
0x1800051cb  cmp     [rcx+8], eax
0x1800051ce  jz      loc_1800053B7
0x1800051d4  add     rcx, rbp
0x1800051d7  cmp     rcx, rdx
0x1800051da  jnz     short loc_1800051C1
0x1800051dc  movzx   eax, word ptr [rbx+22h]
0x1800051e0  mov     r8d, 1
0x1800051e6  movzx   ecx, word ptr [rbx+20h]
0x1800051ea  add     eax, r8d
0x1800051ed  xor     edx, edx
0x1800051ef  div     ecx
0x1800051f1  mov     ecx, r8d
0x1800051f4  movzx   eax, dx
0x1800051f7  mov     [rbx+22h], dx
0x1800051fb  lea     rsi, [rax+rax*4]
0x1800051ff  mov     rax, [rbx+8]
0x180005203  shl     rsi, 4
0x180005207  lock xadd [rax], ecx
0x18000520b  add     ecx, r8d
0x18000520e  lea     r13, [rsi+rdi]
0x180005212  mov     [rsi+rdi+4], ecx
0x180005216  lea     rbx, [rdi+20h]
0x18000521a  mov     eax, [r15+8]
0x18000521e  add     rbx, rsi
0x180005221  mov     [rsi+rdi+8], eax
0x180005225  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005229  mov     [r13+10h], r12
0x18000522d  movzx   eax, word ptr [r15+40h]
0x180005232  mov     [rsi+rdi+18h], ax
0x180005237  mov     al, [r15]
0x18000523a  mov     [rsi+rdi+1Ah], al
0x18000523e  mov     [rbx], r12
0x180005241  mov     rax, [r15+88h]
0x180005248  mov     [rsi+rdi+28h], rax
0x18000524d  mov     rax, [r15+90h]
0x180005254  mov     [rsi+rdi+30h], rax
0x180005259  mov     [rsi+rdi+38h], r12
0x18000525e  mov     rcx, [r15+38h]
0x180005262  test    rcx, rcx
0x180005265  jnz     short loc_18000526C
0x180005267  mov     edx, r8d
0x18000526a  jmp     short loc_18000527C
0x18000526c  mov     rax, r14
0x18000526f  inc     rax
0x180005272  cmp     [rcx+rax], r12b
0x180005276  jnz     short loc_18000526F
0x180005278  lea     rdx, [rax+1]
0x18000527c  mov     rcx, [r15+80h]
0x180005283  test    rcx, rcx
0x180005286  jz      short loc_180005298
0x180005288  mov     rax, r14
0x18000528b  inc     rax
0x18000528e  cmp     [rcx+rax], r12b
0x180005292  jnz     short loc_18000528B
0x180005294  lea     r8, [rax+1]; unsigned __int64
0x180005298  mov     rcx, [r15+18h]
0x18000529c  test    rcx, rcx
0x18000529f  jnz     short loc_1800052A6
0x1800052a1  lea     eax, [rcx+2]
0x1800052a4  jmp     short loc_1800052BB
0x1800052a6  mov     rax, r14
0x1800052a9  inc     rax
0x1800052ac  cmp     [rcx+rax*2], r12w
0x1800052b1  jnz     short loc_1800052A9
0x1800052b3  lea     rax, ds:2[rax*2]
0x1800052bb  lea     rbp, [r8+rax]
0x1800052bf  add     rbp, rdx
0x1800052c2  cmp     [rsi+rdi+40h], r12
0x1800052c7  jz      short loc_1800052D0
0x1800052c9  cmp     [rsi+rdi+48h], rbp
0x1800052ce  jnb     short loc_18000531E
0x1800052d0  mov     rdx, rbp; dwBytes
0x1800052d3  mov     ecx, 8; dwFlags
0x1800052d8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800052dd  mov     r12, rax
0x1800052e0  test    rax, rax
0x1800052e3  jz      short loc_18000531B
0x1800052e5  mov     rbx, [rsi+rdi+40h]
0x1800052ea  call    cs:__imp_GetProcessHeap
0x1800052f1  nop     dword ptr [rax+rax+00h]
0x1800052f6  mov     r8, rbx; lpMem
0x1800052f9  xor     edx, edx; dwFlags
0x1800052fb  mov     rcx, rax; hHeap
0x1800052fe  call    cs:__imp_HeapFree
0x180005305  nop     dword ptr [rax+rax+00h]
0x18000530a  lea     rbx, [rdi+20h]
0x18000530e  mov     [rsi+rdi+40h], r12
0x180005313  add     rbx, rsi
0x180005316  mov     [rsi+rdi+48h], rbp
0x18000531b  xor     r12d, r12d
0x18000531e  mov     rcx, [rsi+rdi+40h]
0x180005323  test    rcx, rcx
0x180005326  jz      loc_1800053B7
0x18000532c  mov     rbp, [rsi+rdi+48h]
0x180005331  lea     r9, [r13+10h]
0x180005335  mov     r8, [r15+38h]
0x180005339  add     rbp, rcx
0x18000533c  mov     rdx, rbp
0x18000533f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005344  mov     r8, [r15+80h]
0x18000534b  mov     r9, rbx
0x18000534e  mov     rdx, rbp
0x180005351  mov     rcx, rax
0x180005354  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005359  mov     rbx, rax
0x18000535c  cmp     rax, rbp
0x18000535f  jz      short loc_1800053A2
0x180005361  mov     r8, [r15+18h]; Source
0x180005365  test    r8, r8
0x180005368  jz      short loc_1800053A2
0x18000536a  cmp     [r8], r12w
0x18000536e  jz      short loc_1800053A2
0x180005370  inc     r14
0x180005373  cmp     [r8+r14*2], r12w
0x180005378  jnz     short loc_180005370
0x18000537a  mov     rdx, rbp
0x18000537d  lea     r14, ds:2[r14*2]
0x180005385  sub     rdx, rbx; DestinationSize
0x180005388  cmp     rdx, r14
0x18000538b  jb      short loc_1800053A2
0x18000538d  mov     r9, r14; SourceSize
0x180005390  mov     rcx, rbx; Destination
0x180005393  call    memcpy_s
0x180005398  mov     [rsi+rdi+38h], rbx
0x18000539d  add     rbx, r14
0x1800053a0  jmp     short loc_1800053A7
0x1800053a2  mov     [rsi+rdi+38h], r12
0x1800053a7  sub     rbp, rbx
0x1800053aa  xor     edx, edx; Val
0x1800053ac  mov     r8, rbp; Size
0x1800053af  mov     rcx, rbx; void *
0x1800053b2  call    memset_0
0x1800053b7  add     rsp, 28h
0x1800053bb  pop     r15
0x1800053bd  pop     r14
0x1800053bf  pop     r13
0x1800053c1  pop     r12
0x1800053c3  pop     rdi
0x1800053c4  pop     rsi
0x1800053c5  pop     rbp
0x1800053c6  pop     rbx
0x1800053c7  retn
```
