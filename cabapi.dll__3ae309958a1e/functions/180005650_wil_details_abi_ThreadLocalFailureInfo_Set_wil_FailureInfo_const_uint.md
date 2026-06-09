# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005650`
- end: `0x180005869`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004160`

## callees

- `0x180001fd6`
- `0x18000524c`
- `0x180005650`
- `0x1800078d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005738`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005746`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005746`

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
0x180005650  push    rbx
0x180005652  push    rbp
0x180005653  push    rsi
0x180005654  push    rdi
0x180005655  push    r12
0x180005657  push    r13
0x180005659  push    r14
0x18000565b  push    r15
0x18000565d  sub     rsp, 28h
0x180005661  mov     [rcx+4], r8d
0x180005665  xor     r13d, r13d
0x180005668  mov     eax, [rdx+8]
0x18000566b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000566f  mov     [rcx+8], eax
0x180005672  mov     rdi, rcx
0x180005675  mov     [rcx+10h], r13
0x180005679  mov     r12, rdx
0x18000567c  movzx   eax, word ptr [rdx+40h]
0x180005680  mov     [rcx+18h], ax
0x180005684  mov     al, [rdx]
0x180005686  mov     [rcx+1Ah], al
0x180005689  mov     [rcx+20h], r13
0x18000568d  mov     rax, [rdx+88h]
0x180005694  mov     [rcx+28h], rax
0x180005698  mov     rax, [rdx+90h]
0x18000569f  mov     [rcx+30h], rax
0x1800056a3  mov     [rcx+38h], r13
0x1800056a7  mov     rcx, [rdx+38h]
0x1800056ab  lea     edx, [rbp+2]
0x1800056ae  test    rcx, rcx
0x1800056b1  jnz     short loc_1800056B8
0x1800056b3  mov     r8d, edx
0x1800056b6  jmp     short loc_1800056C8
0x1800056b8  mov     rax, rbp
0x1800056bb  inc     rax
0x1800056be  cmp     [rcx+rax], r13b
0x1800056c2  jnz     short loc_1800056BB
0x1800056c4  lea     r8, [rax+1]; unsigned __int64
0x1800056c8  mov     rcx, [r12+80h]
0x1800056d0  test    rcx, rcx
0x1800056d3  jz      short loc_1800056E5
0x1800056d5  mov     rax, rbp
0x1800056d8  inc     rax
0x1800056db  cmp     [rcx+rax], r13b
0x1800056df  jnz     short loc_1800056D8
0x1800056e1  lea     rdx, [rax+1]
0x1800056e5  mov     rcx, [r12+18h]
0x1800056ea  test    rcx, rcx
0x1800056ed  jnz     short loc_1800056F4
0x1800056ef  lea     eax, [rcx+2]
0x1800056f2  jmp     short loc_180005709
0x1800056f4  mov     rax, rbp
0x1800056f7  inc     rax
0x1800056fa  cmp     [rcx+rax*2], r13w
0x1800056ff  jnz     short loc_1800056F7
0x180005701  lea     rax, ds:2[rax*2]
0x180005709  lea     r14, [rdx+rax]
0x18000570d  add     r14, r8
0x180005710  lea     rsi, [rdi+48h]
0x180005714  cmp     [rdi+40h], r13
0x180005718  jz      short loc_18000571F
0x18000571a  cmp     [rsi], r14
0x18000571d  jnb     short loc_180005753
0x18000571f  mov     rdx, r14; dwBytes
0x180005722  mov     ecx, 8; dwFlags
0x180005727  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000572c  mov     r15, rax
0x18000572f  test    rax, rax
0x180005732  jz      short loc_180005753
0x180005734  mov     rbx, [rdi+40h]
0x180005738  call    cs:__imp_GetProcessHeap
0x18000573e  mov     r8, rbx; lpMem
0x180005741  xor     edx, edx; dwFlags
0x180005743  mov     rcx, rax; hHeap
0x180005746  call    cs:__imp_HeapFree
0x18000574c  mov     [rdi+40h], r15
0x180005750  mov     [rsi], r14
0x180005753  mov     rbx, [rdi+40h]
0x180005757  test    rbx, rbx
0x18000575a  jz      loc_180005858
0x180005760  mov     rdx, [rsi]; DestinationSize
0x180005763  lea     rsi, [rdx+rbx]
0x180005767  cmp     rbx, rsi
0x18000576a  jz      short loc_1800057AA
0x18000576c  mov     r8, [r12+38h]; Source
0x180005771  test    r8, r8
0x180005774  jz      short loc_1800057AA
0x180005776  cmp     [r8], r13b
0x180005779  jz      short loc_1800057AA
0x18000577b  mov     rax, rbp
0x18000577e  inc     rax
0x180005781  cmp     [r8+rax], r13b
0x180005785  jnz     short loc_18000577E
0x180005787  lea     r14, [rax+1]
0x18000578b  cmp     rdx, r14
0x18000578e  jnb     short loc_180005796
0x180005790  mov     [rdi+10h], r13
0x180005794  jmp     short loc_1800057B3
0x180005796  mov     r9, r14; SourceSize
0x180005799  mov     rcx, rbx; Destination
0x18000579c  call    memcpy_s
0x1800057a1  mov     [rdi+10h], rbx
0x1800057a5  add     rbx, r14
0x1800057a8  jmp     short loc_1800057AE
0x1800057aa  mov     [rdi+10h], r13
0x1800057ae  cmp     rbx, rsi
0x1800057b1  jz      short loc_1800057FA
0x1800057b3  mov     r8, [r12+80h]; Source
0x1800057bb  test    r8, r8
0x1800057be  jz      short loc_1800057FA
0x1800057c0  cmp     [r8], r13b
0x1800057c3  jz      short loc_1800057FA
0x1800057c5  mov     rax, rbp
0x1800057c8  inc     rax
0x1800057cb  cmp     [r8+rax], r13b
0x1800057cf  jnz     short loc_1800057C8
0x1800057d1  mov     rdx, rsi
0x1800057d4  lea     r14, [rax+1]
0x1800057d8  sub     rdx, rbx; DestinationSize
0x1800057db  cmp     rdx, r14
0x1800057de  jnb     short loc_1800057E6
0x1800057e0  mov     [rdi+20h], r13
0x1800057e4  jmp     short loc_180005803
0x1800057e6  mov     r9, r14; SourceSize
0x1800057e9  mov     rcx, rbx; Destination
0x1800057ec  call    memcpy_s
0x1800057f1  mov     [rdi+20h], rbx
0x1800057f5  add     rbx, r14
0x1800057f8  jmp     short loc_1800057FE
0x1800057fa  mov     [rdi+20h], r13
0x1800057fe  cmp     rbx, rsi
0x180005801  jz      short loc_180005844
0x180005803  mov     r8, [r12+18h]; Source
0x180005808  test    r8, r8
0x18000580b  jz      short loc_180005844
0x18000580d  cmp     [r8], r13w
0x180005811  jz      short loc_180005844
0x180005813  inc     rbp
0x180005816  cmp     [r8+rbp*2], r13w
0x18000581b  jnz     short loc_180005813
0x18000581d  mov     rdx, rsi
0x180005820  lea     r14, ds:2[rbp*2]
0x180005828  sub     rdx, rbx; DestinationSize
0x18000582b  cmp     rdx, r14
0x18000582e  jb      short loc_180005844
0x180005830  mov     r9, r14; SourceSize
0x180005833  mov     rcx, rbx; Destination
0x180005836  call    memcpy_s
0x18000583b  mov     [rdi+38h], rbx
0x18000583f  add     rbx, r14
0x180005842  jmp     short loc_180005848
0x180005844  mov     [rdi+38h], r13
0x180005848  sub     rsi, rbx
0x18000584b  xor     edx, edx; Val
0x18000584d  mov     r8, rsi; Size
0x180005850  mov     rcx, rbx; void *
0x180005853  call    memset_0
0x180005858  add     rsp, 28h
0x18000585c  pop     r15
0x18000585e  pop     r14
0x180005860  pop     r13
0x180005862  pop     r12
0x180005864  pop     rdi
0x180005865  pop     rsi
0x180005866  pop     rbp
0x180005867  pop     rbx
0x180005868  retn
```
