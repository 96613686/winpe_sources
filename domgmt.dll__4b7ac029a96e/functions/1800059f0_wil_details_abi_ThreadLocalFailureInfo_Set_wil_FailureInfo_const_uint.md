# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800059f0`
- end: `0x180005c09`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800044a0`

## callees

- `0x18000296c`
- `0x1800054f8`
- `0x1800059f0`
- `0x1800069d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ad8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ae6`

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
0x1800059f0  push    rbx
0x1800059f2  push    rbp
0x1800059f3  push    rsi
0x1800059f4  push    rdi
0x1800059f5  push    r12
0x1800059f7  push    r13
0x1800059f9  push    r14
0x1800059fb  push    r15
0x1800059fd  sub     rsp, 28h
0x180005a01  mov     [rcx+4], r8d
0x180005a05  xor     r13d, r13d
0x180005a08  mov     eax, [rdx+8]
0x180005a0b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005a0f  mov     [rcx+8], eax
0x180005a12  mov     rdi, rcx
0x180005a15  mov     [rcx+10h], r13
0x180005a19  mov     r12, rdx
0x180005a1c  movzx   eax, word ptr [rdx+40h]
0x180005a20  mov     [rcx+18h], ax
0x180005a24  mov     al, [rdx]
0x180005a26  mov     [rcx+1Ah], al
0x180005a29  mov     [rcx+20h], r13
0x180005a2d  mov     rax, [rdx+88h]
0x180005a34  mov     [rcx+28h], rax
0x180005a38  mov     rax, [rdx+90h]
0x180005a3f  mov     [rcx+30h], rax
0x180005a43  mov     [rcx+38h], r13
0x180005a47  mov     rcx, [rdx+38h]
0x180005a4b  lea     edx, [rbp+2]
0x180005a4e  test    rcx, rcx
0x180005a51  jnz     short loc_180005A58
0x180005a53  mov     r8d, edx
0x180005a56  jmp     short loc_180005A68
0x180005a58  mov     rax, rbp
0x180005a5b  inc     rax
0x180005a5e  cmp     [rcx+rax], r13b
0x180005a62  jnz     short loc_180005A5B
0x180005a64  lea     r8, [rax+1]; unsigned __int64
0x180005a68  mov     rcx, [r12+80h]
0x180005a70  test    rcx, rcx
0x180005a73  jz      short loc_180005A85
0x180005a75  mov     rax, rbp
0x180005a78  inc     rax
0x180005a7b  cmp     [rcx+rax], r13b
0x180005a7f  jnz     short loc_180005A78
0x180005a81  lea     rdx, [rax+1]
0x180005a85  mov     rcx, [r12+18h]
0x180005a8a  test    rcx, rcx
0x180005a8d  jnz     short loc_180005A94
0x180005a8f  lea     eax, [rcx+2]
0x180005a92  jmp     short loc_180005AA9
0x180005a94  mov     rax, rbp
0x180005a97  inc     rax
0x180005a9a  cmp     [rcx+rax*2], r13w
0x180005a9f  jnz     short loc_180005A97
0x180005aa1  lea     rax, ds:2[rax*2]
0x180005aa9  lea     r14, [rdx+rax]
0x180005aad  add     r14, r8
0x180005ab0  lea     rsi, [rdi+48h]
0x180005ab4  cmp     [rdi+40h], r13
0x180005ab8  jz      short loc_180005ABF
0x180005aba  cmp     [rsi], r14
0x180005abd  jnb     short loc_180005AF3
0x180005abf  mov     rdx, r14; dwBytes
0x180005ac2  mov     ecx, 8; dwFlags
0x180005ac7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005acc  mov     r15, rax
0x180005acf  test    rax, rax
0x180005ad2  jz      short loc_180005AF3
0x180005ad4  mov     rbx, [rdi+40h]
0x180005ad8  call    cs:__imp_GetProcessHeap
0x180005ade  mov     r8, rbx; lpMem
0x180005ae1  xor     edx, edx; dwFlags
0x180005ae3  mov     rcx, rax; hHeap
0x180005ae6  call    cs:__imp_HeapFree
0x180005aec  mov     [rdi+40h], r15
0x180005af0  mov     [rsi], r14
0x180005af3  mov     rbx, [rdi+40h]
0x180005af7  test    rbx, rbx
0x180005afa  jz      loc_180005BF8
0x180005b00  mov     rdx, [rsi]; DestinationSize
0x180005b03  lea     rsi, [rdx+rbx]
0x180005b07  cmp     rbx, rsi
0x180005b0a  jz      short loc_180005B4A
0x180005b0c  mov     r8, [r12+38h]; Source
0x180005b11  test    r8, r8
0x180005b14  jz      short loc_180005B4A
0x180005b16  cmp     [r8], r13b
0x180005b19  jz      short loc_180005B4A
0x180005b1b  mov     rax, rbp
0x180005b1e  inc     rax
0x180005b21  cmp     [r8+rax], r13b
0x180005b25  jnz     short loc_180005B1E
0x180005b27  lea     r14, [rax+1]
0x180005b2b  cmp     rdx, r14
0x180005b2e  jnb     short loc_180005B36
0x180005b30  mov     [rdi+10h], r13
0x180005b34  jmp     short loc_180005B53
0x180005b36  mov     r9, r14; SourceSize
0x180005b39  mov     rcx, rbx; Destination
0x180005b3c  call    memcpy_s
0x180005b41  mov     [rdi+10h], rbx
0x180005b45  add     rbx, r14
0x180005b48  jmp     short loc_180005B4E
0x180005b4a  mov     [rdi+10h], r13
0x180005b4e  cmp     rbx, rsi
0x180005b51  jz      short loc_180005B9A
0x180005b53  mov     r8, [r12+80h]; Source
0x180005b5b  test    r8, r8
0x180005b5e  jz      short loc_180005B9A
0x180005b60  cmp     [r8], r13b
0x180005b63  jz      short loc_180005B9A
0x180005b65  mov     rax, rbp
0x180005b68  inc     rax
0x180005b6b  cmp     [r8+rax], r13b
0x180005b6f  jnz     short loc_180005B68
0x180005b71  mov     rdx, rsi
0x180005b74  lea     r14, [rax+1]
0x180005b78  sub     rdx, rbx; DestinationSize
0x180005b7b  cmp     rdx, r14
0x180005b7e  jnb     short loc_180005B86
0x180005b80  mov     [rdi+20h], r13
0x180005b84  jmp     short loc_180005BA3
0x180005b86  mov     r9, r14; SourceSize
0x180005b89  mov     rcx, rbx; Destination
0x180005b8c  call    memcpy_s
0x180005b91  mov     [rdi+20h], rbx
0x180005b95  add     rbx, r14
0x180005b98  jmp     short loc_180005B9E
0x180005b9a  mov     [rdi+20h], r13
0x180005b9e  cmp     rbx, rsi
0x180005ba1  jz      short loc_180005BE4
0x180005ba3  mov     r8, [r12+18h]; Source
0x180005ba8  test    r8, r8
0x180005bab  jz      short loc_180005BE4
0x180005bad  cmp     [r8], r13w
0x180005bb1  jz      short loc_180005BE4
0x180005bb3  inc     rbp
0x180005bb6  cmp     [r8+rbp*2], r13w
0x180005bbb  jnz     short loc_180005BB3
0x180005bbd  mov     rdx, rsi
0x180005bc0  lea     r14, ds:2[rbp*2]
0x180005bc8  sub     rdx, rbx; DestinationSize
0x180005bcb  cmp     rdx, r14
0x180005bce  jb      short loc_180005BE4
0x180005bd0  mov     r9, r14; SourceSize
0x180005bd3  mov     rcx, rbx; Destination
0x180005bd6  call    memcpy_s
0x180005bdb  mov     [rdi+38h], rbx
0x180005bdf  add     rbx, r14
0x180005be2  jmp     short loc_180005BE8
0x180005be4  mov     [rdi+38h], r13
0x180005be8  sub     rsi, rbx
0x180005beb  xor     edx, edx; Val
0x180005bed  mov     r8, rsi; Size
0x180005bf0  mov     rcx, rbx; void *
0x180005bf3  call    memset_0
0x180005bf8  add     rsp, 28h
0x180005bfc  pop     r15
0x180005bfe  pop     r14
0x180005c00  pop     r13
0x180005c02  pop     r12
0x180005c04  pop     rdi
0x180005c05  pop     rsi
0x180005c06  pop     rbp
0x180005c07  pop     rbx
0x180005c08  retn
```
