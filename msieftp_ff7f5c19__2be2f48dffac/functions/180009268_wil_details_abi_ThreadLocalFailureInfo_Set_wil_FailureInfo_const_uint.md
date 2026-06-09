# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009268`
- end: `0x180009481`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e40`

## callees

- `0x180002b60`
- `0x180007470`
- `0x180009268`
- `0x18000a894`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000935e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000935e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009350`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x180009268  push    rbx
0x18000926a  push    rbp
0x18000926b  push    rsi
0x18000926c  push    rdi
0x18000926d  push    r12
0x18000926f  push    r13
0x180009271  push    r14
0x180009273  push    r15
0x180009275  sub     rsp, 28h
0x180009279  mov     [rcx+4], r8d
0x18000927d  xor     r13d, r13d
0x180009280  mov     eax, [rdx+8]
0x180009283  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009287  mov     [rcx+8], eax
0x18000928a  mov     rdi, rcx
0x18000928d  mov     [rcx+10h], r13
0x180009291  mov     r12, rdx
0x180009294  movzx   eax, word ptr [rdx+40h]
0x180009298  mov     [rcx+18h], ax
0x18000929c  mov     al, [rdx]
0x18000929e  mov     [rcx+1Ah], al
0x1800092a1  mov     [rcx+20h], r13
0x1800092a5  mov     rax, [rdx+88h]
0x1800092ac  mov     [rcx+28h], rax
0x1800092b0  mov     rax, [rdx+90h]
0x1800092b7  mov     [rcx+30h], rax
0x1800092bb  mov     [rcx+38h], r13
0x1800092bf  mov     rcx, [rdx+38h]
0x1800092c3  lea     edx, [rbp+2]
0x1800092c6  test    rcx, rcx
0x1800092c9  jnz     short loc_1800092D0
0x1800092cb  mov     r8d, edx
0x1800092ce  jmp     short loc_1800092E0
0x1800092d0  mov     rax, rbp
0x1800092d3  inc     rax
0x1800092d6  cmp     [rcx+rax], r13b
0x1800092da  jnz     short loc_1800092D3
0x1800092dc  lea     r8, [rax+1]; unsigned __int64
0x1800092e0  mov     rcx, [r12+80h]
0x1800092e8  test    rcx, rcx
0x1800092eb  jz      short loc_1800092FD
0x1800092ed  mov     rax, rbp
0x1800092f0  inc     rax
0x1800092f3  cmp     [rcx+rax], r13b
0x1800092f7  jnz     short loc_1800092F0
0x1800092f9  lea     rdx, [rax+1]
0x1800092fd  mov     rcx, [r12+18h]
0x180009302  test    rcx, rcx
0x180009305  jnz     short loc_18000930C
0x180009307  lea     eax, [rcx+2]
0x18000930a  jmp     short loc_180009321
0x18000930c  mov     rax, rbp
0x18000930f  inc     rax
0x180009312  cmp     [rcx+rax*2], r13w
0x180009317  jnz     short loc_18000930F
0x180009319  lea     rax, ds:2[rax*2]
0x180009321  lea     r14, [rdx+rax]
0x180009325  add     r14, r8
0x180009328  lea     rsi, [rdi+48h]
0x18000932c  cmp     [rdi+40h], r13
0x180009330  jz      short loc_180009337
0x180009332  cmp     [rsi], r14
0x180009335  jnb     short loc_18000936B
0x180009337  mov     rdx, r14; dwBytes
0x18000933a  mov     ecx, 8; dwFlags
0x18000933f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009344  mov     r15, rax
0x180009347  test    rax, rax
0x18000934a  jz      short loc_18000936B
0x18000934c  mov     rbx, [rdi+40h]
0x180009350  call    cs:__imp_GetProcessHeap
0x180009356  mov     r8, rbx; lpMem
0x180009359  xor     edx, edx; dwFlags
0x18000935b  mov     rcx, rax; hHeap
0x18000935e  call    cs:__imp_HeapFree
0x180009364  mov     [rdi+40h], r15
0x180009368  mov     [rsi], r14
0x18000936b  mov     rbx, [rdi+40h]
0x18000936f  test    rbx, rbx
0x180009372  jz      loc_180009470
0x180009378  mov     rdx, [rsi]; DestinationSize
0x18000937b  lea     rsi, [rdx+rbx]
0x18000937f  cmp     rbx, rsi
0x180009382  jz      short loc_1800093C2
0x180009384  mov     r8, [r12+38h]; Source
0x180009389  test    r8, r8
0x18000938c  jz      short loc_1800093C2
0x18000938e  cmp     [r8], r13b
0x180009391  jz      short loc_1800093C2
0x180009393  mov     rax, rbp
0x180009396  inc     rax
0x180009399  cmp     [r8+rax], r13b
0x18000939d  jnz     short loc_180009396
0x18000939f  lea     r14, [rax+1]
0x1800093a3  cmp     rdx, r14
0x1800093a6  jnb     short loc_1800093AE
0x1800093a8  mov     [rdi+10h], r13
0x1800093ac  jmp     short loc_1800093CB
0x1800093ae  mov     r9, r14; SourceSize
0x1800093b1  mov     rcx, rbx; Destination
0x1800093b4  call    memcpy_s
0x1800093b9  mov     [rdi+10h], rbx
0x1800093bd  add     rbx, r14
0x1800093c0  jmp     short loc_1800093C6
0x1800093c2  mov     [rdi+10h], r13
0x1800093c6  cmp     rbx, rsi
0x1800093c9  jz      short loc_180009412
0x1800093cb  mov     r8, [r12+80h]; Source
0x1800093d3  test    r8, r8
0x1800093d6  jz      short loc_180009412
0x1800093d8  cmp     [r8], r13b
0x1800093db  jz      short loc_180009412
0x1800093dd  mov     rax, rbp
0x1800093e0  inc     rax
0x1800093e3  cmp     [r8+rax], r13b
0x1800093e7  jnz     short loc_1800093E0
0x1800093e9  mov     rdx, rsi
0x1800093ec  lea     r14, [rax+1]
0x1800093f0  sub     rdx, rbx; DestinationSize
0x1800093f3  cmp     rdx, r14
0x1800093f6  jnb     short loc_1800093FE
0x1800093f8  mov     [rdi+20h], r13
0x1800093fc  jmp     short loc_18000941B
0x1800093fe  mov     r9, r14; SourceSize
0x180009401  mov     rcx, rbx; Destination
0x180009404  call    memcpy_s
0x180009409  mov     [rdi+20h], rbx
0x18000940d  add     rbx, r14
0x180009410  jmp     short loc_180009416
0x180009412  mov     [rdi+20h], r13
0x180009416  cmp     rbx, rsi
0x180009419  jz      short loc_18000945C
0x18000941b  mov     r8, [r12+18h]; Source
0x180009420  test    r8, r8
0x180009423  jz      short loc_18000945C
0x180009425  cmp     [r8], r13w
0x180009429  jz      short loc_18000945C
0x18000942b  inc     rbp
0x18000942e  cmp     [r8+rbp*2], r13w
0x180009433  jnz     short loc_18000942B
0x180009435  mov     rdx, rsi
0x180009438  lea     r14, ds:2[rbp*2]
0x180009440  sub     rdx, rbx; DestinationSize
0x180009443  cmp     rdx, r14
0x180009446  jb      short loc_18000945C
0x180009448  mov     r9, r14; SourceSize
0x18000944b  mov     rcx, rbx; Destination
0x18000944e  call    memcpy_s
0x180009453  mov     [rdi+38h], rbx
0x180009457  add     rbx, r14
0x18000945a  jmp     short loc_180009460
0x18000945c  mov     [rdi+38h], r13
0x180009460  sub     rsi, rbx
0x180009463  xor     edx, edx; Val
0x180009465  mov     r8, rsi; Size
0x180009468  mov     rcx, rbx; void *
0x18000946b  call    memset_0
0x180009470  add     rsp, 28h
0x180009474  pop     r15
0x180009476  pop     r14
0x180009478  pop     r13
0x18000947a  pop     r12
0x18000947c  pop     rdi
0x18000947d  pop     rsi
0x18000947e  pop     rbp
0x18000947f  pop     rbx
0x180009480  retn
```
