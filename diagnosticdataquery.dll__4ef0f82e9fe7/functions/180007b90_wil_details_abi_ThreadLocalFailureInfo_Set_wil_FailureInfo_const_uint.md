# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007b90`
- end: `0x180007da9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800067b0`

## callees

- `0x180007828`
- `0x180007b90`
- `0x180008b78`
- `0x18000b8b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c86`

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
                memset(v20, 0, v22 - v20);
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
0x180007b90  push    rbx
0x180007b92  push    rbp
0x180007b93  push    rsi
0x180007b94  push    rdi
0x180007b95  push    r12
0x180007b97  push    r13
0x180007b99  push    r14
0x180007b9b  push    r15
0x180007b9d  sub     rsp, 28h
0x180007ba1  mov     [rcx+4], r8d
0x180007ba5  xor     r13d, r13d
0x180007ba8  mov     eax, [rdx+8]
0x180007bab  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007baf  mov     [rcx+8], eax
0x180007bb2  mov     rdi, rcx
0x180007bb5  mov     [rcx+10h], r13
0x180007bb9  mov     r12, rdx
0x180007bbc  movzx   eax, word ptr [rdx+40h]
0x180007bc0  mov     [rcx+18h], ax
0x180007bc4  mov     al, [rdx]
0x180007bc6  mov     [rcx+1Ah], al
0x180007bc9  mov     [rcx+20h], r13
0x180007bcd  mov     rax, [rdx+88h]
0x180007bd4  mov     [rcx+28h], rax
0x180007bd8  mov     rax, [rdx+90h]
0x180007bdf  mov     [rcx+30h], rax
0x180007be3  mov     [rcx+38h], r13
0x180007be7  mov     rcx, [rdx+38h]
0x180007beb  lea     edx, [rbp+2]
0x180007bee  test    rcx, rcx
0x180007bf1  jnz     short loc_180007BF8
0x180007bf3  mov     r8d, edx
0x180007bf6  jmp     short loc_180007C08
0x180007bf8  mov     rax, rbp
0x180007bfb  inc     rax
0x180007bfe  cmp     [rcx+rax], r13b
0x180007c02  jnz     short loc_180007BFB
0x180007c04  lea     r8, [rax+1]; unsigned __int64
0x180007c08  mov     rcx, [r12+80h]
0x180007c10  test    rcx, rcx
0x180007c13  jz      short loc_180007C25
0x180007c15  mov     rax, rbp
0x180007c18  inc     rax
0x180007c1b  cmp     [rcx+rax], r13b
0x180007c1f  jnz     short loc_180007C18
0x180007c21  lea     rdx, [rax+1]
0x180007c25  mov     rcx, [r12+18h]
0x180007c2a  test    rcx, rcx
0x180007c2d  jnz     short loc_180007C34
0x180007c2f  lea     eax, [rcx+2]
0x180007c32  jmp     short loc_180007C49
0x180007c34  mov     rax, rbp
0x180007c37  inc     rax
0x180007c3a  cmp     [rcx+rax*2], r13w
0x180007c3f  jnz     short loc_180007C37
0x180007c41  lea     rax, ds:2[rax*2]
0x180007c49  lea     r14, [rdx+rax]
0x180007c4d  add     r14, r8
0x180007c50  lea     rsi, [rdi+48h]
0x180007c54  cmp     [rdi+40h], r13
0x180007c58  jz      short loc_180007C5F
0x180007c5a  cmp     [rsi], r14
0x180007c5d  jnb     short loc_180007C93
0x180007c5f  mov     rdx, r14; dwBytes
0x180007c62  mov     ecx, 8; dwFlags
0x180007c67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007c6c  mov     r15, rax
0x180007c6f  test    rax, rax
0x180007c72  jz      short loc_180007C93
0x180007c74  mov     rbx, [rdi+40h]
0x180007c78  call    cs:__imp_GetProcessHeap
0x180007c7e  mov     r8, rbx; lpMem
0x180007c81  xor     edx, edx; dwFlags
0x180007c83  mov     rcx, rax; hHeap
0x180007c86  call    cs:__imp_HeapFree
0x180007c8c  mov     [rdi+40h], r15
0x180007c90  mov     [rsi], r14
0x180007c93  mov     rbx, [rdi+40h]
0x180007c97  test    rbx, rbx
0x180007c9a  jz      loc_180007D98
0x180007ca0  mov     rdx, [rsi]; DestinationSize
0x180007ca3  lea     rsi, [rdx+rbx]
0x180007ca7  cmp     rbx, rsi
0x180007caa  jz      short loc_180007CEA
0x180007cac  mov     r8, [r12+38h]; Source
0x180007cb1  test    r8, r8
0x180007cb4  jz      short loc_180007CEA
0x180007cb6  cmp     [r8], r13b
0x180007cb9  jz      short loc_180007CEA
0x180007cbb  mov     rax, rbp
0x180007cbe  inc     rax
0x180007cc1  cmp     [r8+rax], r13b
0x180007cc5  jnz     short loc_180007CBE
0x180007cc7  lea     r14, [rax+1]
0x180007ccb  cmp     rdx, r14
0x180007cce  jnb     short loc_180007CD6
0x180007cd0  mov     [rdi+10h], r13
0x180007cd4  jmp     short loc_180007CF3
0x180007cd6  mov     r9, r14; SourceSize
0x180007cd9  mov     rcx, rbx; Destination
0x180007cdc  call    memcpy_s
0x180007ce1  mov     [rdi+10h], rbx
0x180007ce5  add     rbx, r14
0x180007ce8  jmp     short loc_180007CEE
0x180007cea  mov     [rdi+10h], r13
0x180007cee  cmp     rbx, rsi
0x180007cf1  jz      short loc_180007D3A
0x180007cf3  mov     r8, [r12+80h]; Source
0x180007cfb  test    r8, r8
0x180007cfe  jz      short loc_180007D3A
0x180007d00  cmp     [r8], r13b
0x180007d03  jz      short loc_180007D3A
0x180007d05  mov     rax, rbp
0x180007d08  inc     rax
0x180007d0b  cmp     [r8+rax], r13b
0x180007d0f  jnz     short loc_180007D08
0x180007d11  mov     rdx, rsi
0x180007d14  lea     r14, [rax+1]
0x180007d18  sub     rdx, rbx; DestinationSize
0x180007d1b  cmp     rdx, r14
0x180007d1e  jnb     short loc_180007D26
0x180007d20  mov     [rdi+20h], r13
0x180007d24  jmp     short loc_180007D43
0x180007d26  mov     r9, r14; SourceSize
0x180007d29  mov     rcx, rbx; Destination
0x180007d2c  call    memcpy_s
0x180007d31  mov     [rdi+20h], rbx
0x180007d35  add     rbx, r14
0x180007d38  jmp     short loc_180007D3E
0x180007d3a  mov     [rdi+20h], r13
0x180007d3e  cmp     rbx, rsi
0x180007d41  jz      short loc_180007D84
0x180007d43  mov     r8, [r12+18h]; Source
0x180007d48  test    r8, r8
0x180007d4b  jz      short loc_180007D84
0x180007d4d  cmp     [r8], r13w
0x180007d51  jz      short loc_180007D84
0x180007d53  inc     rbp
0x180007d56  cmp     [r8+rbp*2], r13w
0x180007d5b  jnz     short loc_180007D53
0x180007d5d  mov     rdx, rsi
0x180007d60  lea     r14, ds:2[rbp*2]
0x180007d68  sub     rdx, rbx; DestinationSize
0x180007d6b  cmp     rdx, r14
0x180007d6e  jb      short loc_180007D84
0x180007d70  mov     r9, r14; SourceSize
0x180007d73  mov     rcx, rbx; Destination
0x180007d76  call    memcpy_s
0x180007d7b  mov     [rdi+38h], rbx
0x180007d7f  add     rbx, r14
0x180007d82  jmp     short loc_180007D88
0x180007d84  mov     [rdi+38h], r13
0x180007d88  sub     rsi, rbx
0x180007d8b  xor     edx, edx; Val
0x180007d8d  mov     r8, rsi; Size
0x180007d90  mov     rcx, rbx; void *
0x180007d93  call    memset
0x180007d98  add     rsp, 28h
0x180007d9c  pop     r15
0x180007d9e  pop     r14
0x180007da0  pop     r13
0x180007da2  pop     r12
0x180007da4  pop     rdi
0x180007da5  pop     rsi
0x180007da6  pop     rbp
0x180007da7  pop     rbx
0x180007da8  retn
```
