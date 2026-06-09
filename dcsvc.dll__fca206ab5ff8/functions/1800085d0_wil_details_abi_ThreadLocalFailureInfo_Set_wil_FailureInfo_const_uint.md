# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800085d0`
- end: `0x1800087e9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800054f0`

## callees

- `0x1800026c8`
- `0x1800068b8`
- `0x1800085d0`
- `0x18000a8b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086c6`

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
0x1800085d0  push    rbx
0x1800085d2  push    rbp
0x1800085d3  push    rsi
0x1800085d4  push    rdi
0x1800085d5  push    r12
0x1800085d7  push    r13
0x1800085d9  push    r14
0x1800085db  push    r15
0x1800085dd  sub     rsp, 28h
0x1800085e1  mov     [rcx+4], r8d
0x1800085e5  xor     r13d, r13d
0x1800085e8  mov     eax, [rdx+8]
0x1800085eb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800085ef  mov     [rcx+8], eax
0x1800085f2  mov     rdi, rcx
0x1800085f5  mov     [rcx+10h], r13
0x1800085f9  mov     r12, rdx
0x1800085fc  movzx   eax, word ptr [rdx+40h]
0x180008600  mov     [rcx+18h], ax
0x180008604  mov     al, [rdx]
0x180008606  mov     [rcx+1Ah], al
0x180008609  mov     [rcx+20h], r13
0x18000860d  mov     rax, [rdx+88h]
0x180008614  mov     [rcx+28h], rax
0x180008618  mov     rax, [rdx+90h]
0x18000861f  mov     [rcx+30h], rax
0x180008623  mov     [rcx+38h], r13
0x180008627  mov     rcx, [rdx+38h]
0x18000862b  lea     edx, [rbp+2]
0x18000862e  test    rcx, rcx
0x180008631  jnz     short loc_180008638
0x180008633  mov     r8d, edx
0x180008636  jmp     short loc_180008648
0x180008638  mov     rax, rbp
0x18000863b  inc     rax
0x18000863e  cmp     [rcx+rax], r13b
0x180008642  jnz     short loc_18000863B
0x180008644  lea     r8, [rax+1]; unsigned __int64
0x180008648  mov     rcx, [r12+80h]
0x180008650  test    rcx, rcx
0x180008653  jz      short loc_180008665
0x180008655  mov     rax, rbp
0x180008658  inc     rax
0x18000865b  cmp     [rcx+rax], r13b
0x18000865f  jnz     short loc_180008658
0x180008661  lea     rdx, [rax+1]
0x180008665  mov     rcx, [r12+18h]
0x18000866a  test    rcx, rcx
0x18000866d  jnz     short loc_180008674
0x18000866f  lea     eax, [rcx+2]
0x180008672  jmp     short loc_180008689
0x180008674  mov     rax, rbp
0x180008677  inc     rax
0x18000867a  cmp     [rcx+rax*2], r13w
0x18000867f  jnz     short loc_180008677
0x180008681  lea     rax, ds:2[rax*2]
0x180008689  lea     r14, [rdx+rax]
0x18000868d  add     r14, r8
0x180008690  lea     rsi, [rdi+48h]
0x180008694  cmp     [rdi+40h], r13
0x180008698  jz      short loc_18000869F
0x18000869a  cmp     [rsi], r14
0x18000869d  jnb     short loc_1800086D3
0x18000869f  mov     rdx, r14; dwBytes
0x1800086a2  mov     ecx, 8; dwFlags
0x1800086a7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800086ac  mov     r15, rax
0x1800086af  test    rax, rax
0x1800086b2  jz      short loc_1800086D3
0x1800086b4  mov     rbx, [rdi+40h]
0x1800086b8  call    cs:__imp_GetProcessHeap
0x1800086be  mov     r8, rbx; lpMem
0x1800086c1  xor     edx, edx; dwFlags
0x1800086c3  mov     rcx, rax; hHeap
0x1800086c6  call    cs:__imp_HeapFree
0x1800086cc  mov     [rdi+40h], r15
0x1800086d0  mov     [rsi], r14
0x1800086d3  mov     rbx, [rdi+40h]
0x1800086d7  test    rbx, rbx
0x1800086da  jz      loc_1800087D8
0x1800086e0  mov     rdx, [rsi]; DestinationSize
0x1800086e3  lea     rsi, [rdx+rbx]
0x1800086e7  cmp     rbx, rsi
0x1800086ea  jz      short loc_18000872A
0x1800086ec  mov     r8, [r12+38h]; Source
0x1800086f1  test    r8, r8
0x1800086f4  jz      short loc_18000872A
0x1800086f6  cmp     [r8], r13b
0x1800086f9  jz      short loc_18000872A
0x1800086fb  mov     rax, rbp
0x1800086fe  inc     rax
0x180008701  cmp     [r8+rax], r13b
0x180008705  jnz     short loc_1800086FE
0x180008707  lea     r14, [rax+1]
0x18000870b  cmp     rdx, r14
0x18000870e  jnb     short loc_180008716
0x180008710  mov     [rdi+10h], r13
0x180008714  jmp     short loc_180008733
0x180008716  mov     r9, r14; SourceSize
0x180008719  mov     rcx, rbx; Destination
0x18000871c  call    memcpy_s
0x180008721  mov     [rdi+10h], rbx
0x180008725  add     rbx, r14
0x180008728  jmp     short loc_18000872E
0x18000872a  mov     [rdi+10h], r13
0x18000872e  cmp     rbx, rsi
0x180008731  jz      short loc_18000877A
0x180008733  mov     r8, [r12+80h]; Source
0x18000873b  test    r8, r8
0x18000873e  jz      short loc_18000877A
0x180008740  cmp     [r8], r13b
0x180008743  jz      short loc_18000877A
0x180008745  mov     rax, rbp
0x180008748  inc     rax
0x18000874b  cmp     [r8+rax], r13b
0x18000874f  jnz     short loc_180008748
0x180008751  mov     rdx, rsi
0x180008754  lea     r14, [rax+1]
0x180008758  sub     rdx, rbx; DestinationSize
0x18000875b  cmp     rdx, r14
0x18000875e  jnb     short loc_180008766
0x180008760  mov     [rdi+20h], r13
0x180008764  jmp     short loc_180008783
0x180008766  mov     r9, r14; SourceSize
0x180008769  mov     rcx, rbx; Destination
0x18000876c  call    memcpy_s
0x180008771  mov     [rdi+20h], rbx
0x180008775  add     rbx, r14
0x180008778  jmp     short loc_18000877E
0x18000877a  mov     [rdi+20h], r13
0x18000877e  cmp     rbx, rsi
0x180008781  jz      short loc_1800087C4
0x180008783  mov     r8, [r12+18h]; Source
0x180008788  test    r8, r8
0x18000878b  jz      short loc_1800087C4
0x18000878d  cmp     [r8], r13w
0x180008791  jz      short loc_1800087C4
0x180008793  inc     rbp
0x180008796  cmp     [r8+rbp*2], r13w
0x18000879b  jnz     short loc_180008793
0x18000879d  mov     rdx, rsi
0x1800087a0  lea     r14, ds:2[rbp*2]
0x1800087a8  sub     rdx, rbx; DestinationSize
0x1800087ab  cmp     rdx, r14
0x1800087ae  jb      short loc_1800087C4
0x1800087b0  mov     r9, r14; SourceSize
0x1800087b3  mov     rcx, rbx; Destination
0x1800087b6  call    memcpy_s
0x1800087bb  mov     [rdi+38h], rbx
0x1800087bf  add     rbx, r14
0x1800087c2  jmp     short loc_1800087C8
0x1800087c4  mov     [rdi+38h], r13
0x1800087c8  sub     rsi, rbx
0x1800087cb  xor     edx, edx; Val
0x1800087cd  mov     r8, rsi; Size
0x1800087d0  mov     rcx, rbx; void *
0x1800087d3  call    memset_0
0x1800087d8  add     rsp, 28h
0x1800087dc  pop     r15
0x1800087de  pop     r14
0x1800087e0  pop     r13
0x1800087e2  pop     r12
0x1800087e4  pop     rdi
0x1800087e5  pop     rsi
0x1800087e6  pop     rbp
0x1800087e7  pop     rbx
0x1800087e8  retn
```
