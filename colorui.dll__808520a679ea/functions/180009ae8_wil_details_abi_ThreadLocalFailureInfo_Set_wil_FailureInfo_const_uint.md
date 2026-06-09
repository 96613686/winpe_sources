# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009ae8`
- end: `0x180009d04`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a20`

## callees

- `0x1800075e4`
- `0x180009ae8`
- `0x1800184ce`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009c34`
- `msvcrt!memcpy_s` at `0x180009c85`
- `msvcrt!memcpy_s` at `0x180009cd0`
- `msvcrt!memcpy_s` at `0x180009c34`
- `msvcrt!memcpy_s` at `0x180009c85`
- `msvcrt!memcpy_s` at `0x180009cd0`
- `KERNEL32!GetProcessHeap` at `0x180009bd0`
- `KERNEL32!GetProcessHeap` at `0x180009bd0`
- `KERNEL32!HeapFree` at `0x180009bde`
- `KERNEL32!HeapFree` at `0x180009bde`

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
0x180009ae8  push    rbx
0x180009aea  push    rbp
0x180009aeb  push    rsi
0x180009aec  push    rdi
0x180009aed  push    r12
0x180009aef  push    r13
0x180009af1  push    r14
0x180009af3  push    r15
0x180009af5  sub     rsp, 28h
0x180009af9  mov     [rcx+4], r8d
0x180009afd  xor     r13d, r13d
0x180009b00  mov     eax, [rdx+8]
0x180009b03  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180009b07  mov     [rcx+8], eax
0x180009b0a  mov     rdi, rcx
0x180009b0d  mov     [rcx+10h], r13
0x180009b11  mov     r12, rdx
0x180009b14  movzx   eax, word ptr [rdx+40h]
0x180009b18  mov     [rcx+18h], ax
0x180009b1c  mov     al, [rdx]
0x180009b1e  mov     [rcx+1Ah], al
0x180009b21  mov     [rcx+20h], r13
0x180009b25  mov     rax, [rdx+88h]
0x180009b2c  mov     [rcx+28h], rax
0x180009b30  mov     rax, [rdx+90h]
0x180009b37  mov     [rcx+30h], rax
0x180009b3b  mov     [rcx+38h], r13
0x180009b3f  mov     rcx, [rdx+38h]
0x180009b43  lea     edx, [rbp+2]
0x180009b46  test    rcx, rcx
0x180009b49  jnz     short loc_180009B50
0x180009b4b  mov     r8d, edx
0x180009b4e  jmp     short loc_180009B60
0x180009b50  mov     rax, rbp
0x180009b53  inc     rax
0x180009b56  cmp     [rcx+rax], r13b
0x180009b5a  jnz     short loc_180009B53
0x180009b5c  lea     r8, [rax+1]; unsigned __int64
0x180009b60  mov     rcx, [r12+80h]
0x180009b68  test    rcx, rcx
0x180009b6b  jz      short loc_180009B7D
0x180009b6d  mov     rax, rbp
0x180009b70  inc     rax
0x180009b73  cmp     [rcx+rax], r13b
0x180009b77  jnz     short loc_180009B70
0x180009b79  lea     rdx, [rax+1]
0x180009b7d  mov     rcx, [r12+18h]
0x180009b82  test    rcx, rcx
0x180009b85  jnz     short loc_180009B8C
0x180009b87  lea     eax, [rcx+2]
0x180009b8a  jmp     short loc_180009BA1
0x180009b8c  mov     rax, rbp
0x180009b8f  inc     rax
0x180009b92  cmp     [rcx+rax*2], r13w
0x180009b97  jnz     short loc_180009B8F
0x180009b99  lea     rax, ds:2[rax*2]
0x180009ba1  lea     r14, [rdx+rax]
0x180009ba5  add     r14, r8
0x180009ba8  lea     rsi, [rdi+48h]
0x180009bac  cmp     [rdi+40h], r13
0x180009bb0  jz      short loc_180009BB7
0x180009bb2  cmp     [rsi], r14
0x180009bb5  jnb     short loc_180009BEB
0x180009bb7  mov     rdx, r14; dwBytes
0x180009bba  mov     ecx, 8; dwFlags
0x180009bbf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009bc4  mov     r15, rax
0x180009bc7  test    rax, rax
0x180009bca  jz      short loc_180009BEB
0x180009bcc  mov     rbx, [rdi+40h]
0x180009bd0  call    cs:__imp_GetProcessHeap
0x180009bd6  mov     r8, rbx; lpMem
0x180009bd9  xor     edx, edx; dwFlags
0x180009bdb  mov     rcx, rax; hHeap
0x180009bde  call    cs:__imp_HeapFree
0x180009be4  mov     [rdi+40h], r15
0x180009be8  mov     [rsi], r14
0x180009beb  mov     rbx, [rdi+40h]
0x180009bef  test    rbx, rbx
0x180009bf2  jz      loc_180009CF3
0x180009bf8  mov     rdx, [rsi]; DestinationSize
0x180009bfb  lea     rsi, [rdx+rbx]
0x180009bff  cmp     rbx, rsi
0x180009c02  jz      short loc_180009C43
0x180009c04  mov     r8, [r12+38h]; Source
0x180009c09  test    r8, r8
0x180009c0c  jz      short loc_180009C43
0x180009c0e  cmp     [r8], r13b
0x180009c11  jz      short loc_180009C43
0x180009c13  mov     rax, rbp
0x180009c16  inc     rax
0x180009c19  cmp     [r8+rax], r13b
0x180009c1d  jnz     short loc_180009C16
0x180009c1f  lea     r14, [rax+1]
0x180009c23  cmp     rdx, r14
0x180009c26  jnb     short loc_180009C2E
0x180009c28  mov     [rdi+10h], r13
0x180009c2c  jmp     short loc_180009C4C
0x180009c2e  mov     r9, r14; SourceSize
0x180009c31  mov     rcx, rbx; Destination
0x180009c34  call    cs:__imp_memcpy_s
0x180009c3a  mov     [rdi+10h], rbx
0x180009c3e  add     rbx, r14
0x180009c41  jmp     short loc_180009C47
0x180009c43  mov     [rdi+10h], r13
0x180009c47  cmp     rbx, rsi
0x180009c4a  jz      short loc_180009C94
0x180009c4c  mov     r8, [r12+80h]; Source
0x180009c54  test    r8, r8
0x180009c57  jz      short loc_180009C94
0x180009c59  cmp     [r8], r13b
0x180009c5c  jz      short loc_180009C94
0x180009c5e  mov     rax, rbp
0x180009c61  inc     rax
0x180009c64  cmp     [r8+rax], r13b
0x180009c68  jnz     short loc_180009C61
0x180009c6a  mov     rdx, rsi
0x180009c6d  lea     r14, [rax+1]
0x180009c71  sub     rdx, rbx; DestinationSize
0x180009c74  cmp     rdx, r14
0x180009c77  jnb     short loc_180009C7F
0x180009c79  mov     [rdi+20h], r13
0x180009c7d  jmp     short loc_180009C9D
0x180009c7f  mov     r9, r14; SourceSize
0x180009c82  mov     rcx, rbx; Destination
0x180009c85  call    cs:__imp_memcpy_s
0x180009c8b  mov     [rdi+20h], rbx
0x180009c8f  add     rbx, r14
0x180009c92  jmp     short loc_180009C98
0x180009c94  mov     [rdi+20h], r13
0x180009c98  cmp     rbx, rsi
0x180009c9b  jz      short loc_180009CDF
0x180009c9d  mov     r8, [r12+18h]; Source
0x180009ca2  test    r8, r8
0x180009ca5  jz      short loc_180009CDF
0x180009ca7  cmp     [r8], r13w
0x180009cab  jz      short loc_180009CDF
0x180009cad  inc     rbp
0x180009cb0  cmp     [r8+rbp*2], r13w
0x180009cb5  jnz     short loc_180009CAD
0x180009cb7  mov     rdx, rsi
0x180009cba  lea     r14, ds:2[rbp*2]
0x180009cc2  sub     rdx, rbx; DestinationSize
0x180009cc5  cmp     rdx, r14
0x180009cc8  jb      short loc_180009CDF
0x180009cca  mov     r9, r14; SourceSize
0x180009ccd  mov     rcx, rbx; Destination
0x180009cd0  call    cs:__imp_memcpy_s
0x180009cd6  mov     [rdi+38h], rbx
0x180009cda  add     rbx, r14
0x180009cdd  jmp     short loc_180009CE3
0x180009cdf  mov     [rdi+38h], r13
0x180009ce3  sub     rsi, rbx
0x180009ce6  xor     edx, edx; Val
0x180009ce8  mov     r8, rsi; Size
0x180009ceb  mov     rcx, rbx; void *
0x180009cee  call    memset_0
0x180009cf3  add     rsp, 28h
0x180009cf7  pop     r15
0x180009cf9  pop     r14
0x180009cfb  pop     r13
0x180009cfd  pop     r12
0x180009cff  pop     rdi
0x180009d00  pop     rsi
0x180009d01  pop     rbp
0x180009d02  pop     rbx
0x180009d03  retn
```
