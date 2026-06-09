# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140012644`
- end: `0x14001285d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000fba0`

## callees

- `0x140003b28`
- `0x140010df8`
- `0x140012644`
- `0x1400143c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001273a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001273a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001272c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001272c`

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
0x140012644  push    rbx
0x140012646  push    rbp
0x140012647  push    rsi
0x140012648  push    rdi
0x140012649  push    r12
0x14001264b  push    r13
0x14001264d  push    r14
0x14001264f  push    r15
0x140012651  sub     rsp, 28h
0x140012655  mov     [rcx+4], r8d
0x140012659  xor     r13d, r13d
0x14001265c  mov     eax, [rdx+8]
0x14001265f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140012663  mov     [rcx+8], eax
0x140012666  mov     rdi, rcx
0x140012669  mov     [rcx+10h], r13
0x14001266d  mov     r12, rdx
0x140012670  movzx   eax, word ptr [rdx+40h]
0x140012674  mov     [rcx+18h], ax
0x140012678  mov     al, [rdx]
0x14001267a  mov     [rcx+1Ah], al
0x14001267d  mov     [rcx+20h], r13
0x140012681  mov     rax, [rdx+88h]
0x140012688  mov     [rcx+28h], rax
0x14001268c  mov     rax, [rdx+90h]
0x140012693  mov     [rcx+30h], rax
0x140012697  mov     [rcx+38h], r13
0x14001269b  mov     rcx, [rdx+38h]
0x14001269f  lea     edx, [rbp+2]
0x1400126a2  test    rcx, rcx
0x1400126a5  jnz     short loc_1400126AC
0x1400126a7  mov     r8d, edx
0x1400126aa  jmp     short loc_1400126BC
0x1400126ac  mov     rax, rbp
0x1400126af  inc     rax
0x1400126b2  cmp     [rcx+rax], r13b
0x1400126b6  jnz     short loc_1400126AF
0x1400126b8  lea     r8, [rax+1]; unsigned __int64
0x1400126bc  mov     rcx, [r12+80h]
0x1400126c4  test    rcx, rcx
0x1400126c7  jz      short loc_1400126D9
0x1400126c9  mov     rax, rbp
0x1400126cc  inc     rax
0x1400126cf  cmp     [rcx+rax], r13b
0x1400126d3  jnz     short loc_1400126CC
0x1400126d5  lea     rdx, [rax+1]
0x1400126d9  mov     rcx, [r12+18h]
0x1400126de  test    rcx, rcx
0x1400126e1  jnz     short loc_1400126E8
0x1400126e3  lea     eax, [rcx+2]
0x1400126e6  jmp     short loc_1400126FD
0x1400126e8  mov     rax, rbp
0x1400126eb  inc     rax
0x1400126ee  cmp     [rcx+rax*2], r13w
0x1400126f3  jnz     short loc_1400126EB
0x1400126f5  lea     rax, ds:2[rax*2]
0x1400126fd  lea     r14, [rdx+rax]
0x140012701  add     r14, r8
0x140012704  lea     rsi, [rdi+48h]
0x140012708  cmp     [rdi+40h], r13
0x14001270c  jz      short loc_140012713
0x14001270e  cmp     [rsi], r14
0x140012711  jnb     short loc_140012747
0x140012713  mov     rdx, r14; dwBytes
0x140012716  mov     ecx, 8; dwFlags
0x14001271b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140012720  mov     r15, rax
0x140012723  test    rax, rax
0x140012726  jz      short loc_140012747
0x140012728  mov     rbx, [rdi+40h]
0x14001272c  call    cs:__imp_GetProcessHeap
0x140012732  mov     r8, rbx; lpMem
0x140012735  xor     edx, edx; dwFlags
0x140012737  mov     rcx, rax; hHeap
0x14001273a  call    cs:__imp_HeapFree
0x140012740  mov     [rdi+40h], r15
0x140012744  mov     [rsi], r14
0x140012747  mov     rbx, [rdi+40h]
0x14001274b  test    rbx, rbx
0x14001274e  jz      loc_14001284C
0x140012754  mov     rdx, [rsi]; DestinationSize
0x140012757  lea     rsi, [rdx+rbx]
0x14001275b  cmp     rbx, rsi
0x14001275e  jz      short loc_14001279E
0x140012760  mov     r8, [r12+38h]; Source
0x140012765  test    r8, r8
0x140012768  jz      short loc_14001279E
0x14001276a  cmp     [r8], r13b
0x14001276d  jz      short loc_14001279E
0x14001276f  mov     rax, rbp
0x140012772  inc     rax
0x140012775  cmp     [r8+rax], r13b
0x140012779  jnz     short loc_140012772
0x14001277b  lea     r14, [rax+1]
0x14001277f  cmp     rdx, r14
0x140012782  jnb     short loc_14001278A
0x140012784  mov     [rdi+10h], r13
0x140012788  jmp     short loc_1400127A7
0x14001278a  mov     r9, r14; SourceSize
0x14001278d  mov     rcx, rbx; Destination
0x140012790  call    memcpy_s
0x140012795  mov     [rdi+10h], rbx
0x140012799  add     rbx, r14
0x14001279c  jmp     short loc_1400127A2
0x14001279e  mov     [rdi+10h], r13
0x1400127a2  cmp     rbx, rsi
0x1400127a5  jz      short loc_1400127EE
0x1400127a7  mov     r8, [r12+80h]; Source
0x1400127af  test    r8, r8
0x1400127b2  jz      short loc_1400127EE
0x1400127b4  cmp     [r8], r13b
0x1400127b7  jz      short loc_1400127EE
0x1400127b9  mov     rax, rbp
0x1400127bc  inc     rax
0x1400127bf  cmp     [r8+rax], r13b
0x1400127c3  jnz     short loc_1400127BC
0x1400127c5  mov     rdx, rsi
0x1400127c8  lea     r14, [rax+1]
0x1400127cc  sub     rdx, rbx; DestinationSize
0x1400127cf  cmp     rdx, r14
0x1400127d2  jnb     short loc_1400127DA
0x1400127d4  mov     [rdi+20h], r13
0x1400127d8  jmp     short loc_1400127F7
0x1400127da  mov     r9, r14; SourceSize
0x1400127dd  mov     rcx, rbx; Destination
0x1400127e0  call    memcpy_s
0x1400127e5  mov     [rdi+20h], rbx
0x1400127e9  add     rbx, r14
0x1400127ec  jmp     short loc_1400127F2
0x1400127ee  mov     [rdi+20h], r13
0x1400127f2  cmp     rbx, rsi
0x1400127f5  jz      short loc_140012838
0x1400127f7  mov     r8, [r12+18h]; Source
0x1400127fc  test    r8, r8
0x1400127ff  jz      short loc_140012838
0x140012801  cmp     [r8], r13w
0x140012805  jz      short loc_140012838
0x140012807  inc     rbp
0x14001280a  cmp     [r8+rbp*2], r13w
0x14001280f  jnz     short loc_140012807
0x140012811  mov     rdx, rsi
0x140012814  lea     r14, ds:2[rbp*2]
0x14001281c  sub     rdx, rbx; DestinationSize
0x14001281f  cmp     rdx, r14
0x140012822  jb      short loc_140012838
0x140012824  mov     r9, r14; SourceSize
0x140012827  mov     rcx, rbx; Destination
0x14001282a  call    memcpy_s
0x14001282f  mov     [rdi+38h], rbx
0x140012833  add     rbx, r14
0x140012836  jmp     short loc_14001283C
0x140012838  mov     [rdi+38h], r13
0x14001283c  sub     rsi, rbx
0x14001283f  xor     edx, edx; Val
0x140012841  mov     r8, rsi; Size
0x140012844  mov     rcx, rbx; void *
0x140012847  call    memset_0
0x14001284c  add     rsp, 28h
0x140012850  pop     r15
0x140012852  pop     r14
0x140012854  pop     r13
0x140012856  pop     r12
0x140012858  pop     rdi
0x140012859  pop     rsi
0x14001285a  pop     rbp
0x14001285b  pop     rbx
0x14001285c  retn
```
