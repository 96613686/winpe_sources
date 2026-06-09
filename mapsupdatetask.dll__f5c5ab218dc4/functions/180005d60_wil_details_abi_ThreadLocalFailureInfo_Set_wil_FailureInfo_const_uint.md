# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005d60`
- end: `0x180005f79`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042e0`

## callees

- `0x180002612`
- `0x18000550c`
- `0x180005d60`
- `0x180007aa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e56`

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
0x180005d60  push    rbx
0x180005d62  push    rbp
0x180005d63  push    rsi
0x180005d64  push    rdi
0x180005d65  push    r12
0x180005d67  push    r13
0x180005d69  push    r14
0x180005d6b  push    r15
0x180005d6d  sub     rsp, 28h
0x180005d71  mov     [rcx+4], r8d
0x180005d75  xor     r13d, r13d
0x180005d78  mov     eax, [rdx+8]
0x180005d7b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005d7f  mov     [rcx+8], eax
0x180005d82  mov     rdi, rcx
0x180005d85  mov     [rcx+10h], r13
0x180005d89  mov     r12, rdx
0x180005d8c  movzx   eax, word ptr [rdx+40h]
0x180005d90  mov     [rcx+18h], ax
0x180005d94  mov     al, [rdx]
0x180005d96  mov     [rcx+1Ah], al
0x180005d99  mov     [rcx+20h], r13
0x180005d9d  mov     rax, [rdx+88h]
0x180005da4  mov     [rcx+28h], rax
0x180005da8  mov     rax, [rdx+90h]
0x180005daf  mov     [rcx+30h], rax
0x180005db3  mov     [rcx+38h], r13
0x180005db7  mov     rcx, [rdx+38h]
0x180005dbb  lea     edx, [rbp+2]
0x180005dbe  test    rcx, rcx
0x180005dc1  jnz     short loc_180005DC8
0x180005dc3  mov     r8d, edx
0x180005dc6  jmp     short loc_180005DD8
0x180005dc8  mov     rax, rbp
0x180005dcb  inc     rax
0x180005dce  cmp     [rcx+rax], r13b
0x180005dd2  jnz     short loc_180005DCB
0x180005dd4  lea     r8, [rax+1]; unsigned __int64
0x180005dd8  mov     rcx, [r12+80h]
0x180005de0  test    rcx, rcx
0x180005de3  jz      short loc_180005DF5
0x180005de5  mov     rax, rbp
0x180005de8  inc     rax
0x180005deb  cmp     [rcx+rax], r13b
0x180005def  jnz     short loc_180005DE8
0x180005df1  lea     rdx, [rax+1]
0x180005df5  mov     rcx, [r12+18h]
0x180005dfa  test    rcx, rcx
0x180005dfd  jnz     short loc_180005E04
0x180005dff  lea     eax, [rcx+2]
0x180005e02  jmp     short loc_180005E19
0x180005e04  mov     rax, rbp
0x180005e07  inc     rax
0x180005e0a  cmp     [rcx+rax*2], r13w
0x180005e0f  jnz     short loc_180005E07
0x180005e11  lea     rax, ds:2[rax*2]
0x180005e19  lea     r14, [rdx+rax]
0x180005e1d  add     r14, r8
0x180005e20  lea     rsi, [rdi+48h]
0x180005e24  cmp     [rdi+40h], r13
0x180005e28  jz      short loc_180005E2F
0x180005e2a  cmp     [rsi], r14
0x180005e2d  jnb     short loc_180005E63
0x180005e2f  mov     rdx, r14; dwBytes
0x180005e32  mov     ecx, 8; dwFlags
0x180005e37  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005e3c  mov     r15, rax
0x180005e3f  test    rax, rax
0x180005e42  jz      short loc_180005E63
0x180005e44  mov     rbx, [rdi+40h]
0x180005e48  call    cs:__imp_GetProcessHeap
0x180005e4e  mov     r8, rbx; lpMem
0x180005e51  xor     edx, edx; dwFlags
0x180005e53  mov     rcx, rax; hHeap
0x180005e56  call    cs:__imp_HeapFree
0x180005e5c  mov     [rdi+40h], r15
0x180005e60  mov     [rsi], r14
0x180005e63  mov     rbx, [rdi+40h]
0x180005e67  test    rbx, rbx
0x180005e6a  jz      loc_180005F68
0x180005e70  mov     rdx, [rsi]; DestinationSize
0x180005e73  lea     rsi, [rdx+rbx]
0x180005e77  cmp     rbx, rsi
0x180005e7a  jz      short loc_180005EBA
0x180005e7c  mov     r8, [r12+38h]; Source
0x180005e81  test    r8, r8
0x180005e84  jz      short loc_180005EBA
0x180005e86  cmp     [r8], r13b
0x180005e89  jz      short loc_180005EBA
0x180005e8b  mov     rax, rbp
0x180005e8e  inc     rax
0x180005e91  cmp     [r8+rax], r13b
0x180005e95  jnz     short loc_180005E8E
0x180005e97  lea     r14, [rax+1]
0x180005e9b  cmp     rdx, r14
0x180005e9e  jnb     short loc_180005EA6
0x180005ea0  mov     [rdi+10h], r13
0x180005ea4  jmp     short loc_180005EC3
0x180005ea6  mov     r9, r14; SourceSize
0x180005ea9  mov     rcx, rbx; Destination
0x180005eac  call    memcpy_s
0x180005eb1  mov     [rdi+10h], rbx
0x180005eb5  add     rbx, r14
0x180005eb8  jmp     short loc_180005EBE
0x180005eba  mov     [rdi+10h], r13
0x180005ebe  cmp     rbx, rsi
0x180005ec1  jz      short loc_180005F0A
0x180005ec3  mov     r8, [r12+80h]; Source
0x180005ecb  test    r8, r8
0x180005ece  jz      short loc_180005F0A
0x180005ed0  cmp     [r8], r13b
0x180005ed3  jz      short loc_180005F0A
0x180005ed5  mov     rax, rbp
0x180005ed8  inc     rax
0x180005edb  cmp     [r8+rax], r13b
0x180005edf  jnz     short loc_180005ED8
0x180005ee1  mov     rdx, rsi
0x180005ee4  lea     r14, [rax+1]
0x180005ee8  sub     rdx, rbx; DestinationSize
0x180005eeb  cmp     rdx, r14
0x180005eee  jnb     short loc_180005EF6
0x180005ef0  mov     [rdi+20h], r13
0x180005ef4  jmp     short loc_180005F13
0x180005ef6  mov     r9, r14; SourceSize
0x180005ef9  mov     rcx, rbx; Destination
0x180005efc  call    memcpy_s
0x180005f01  mov     [rdi+20h], rbx
0x180005f05  add     rbx, r14
0x180005f08  jmp     short loc_180005F0E
0x180005f0a  mov     [rdi+20h], r13
0x180005f0e  cmp     rbx, rsi
0x180005f11  jz      short loc_180005F54
0x180005f13  mov     r8, [r12+18h]; Source
0x180005f18  test    r8, r8
0x180005f1b  jz      short loc_180005F54
0x180005f1d  cmp     [r8], r13w
0x180005f21  jz      short loc_180005F54
0x180005f23  inc     rbp
0x180005f26  cmp     [r8+rbp*2], r13w
0x180005f2b  jnz     short loc_180005F23
0x180005f2d  mov     rdx, rsi
0x180005f30  lea     r14, ds:2[rbp*2]
0x180005f38  sub     rdx, rbx; DestinationSize
0x180005f3b  cmp     rdx, r14
0x180005f3e  jb      short loc_180005F54
0x180005f40  mov     r9, r14; SourceSize
0x180005f43  mov     rcx, rbx; Destination
0x180005f46  call    memcpy_s
0x180005f4b  mov     [rdi+38h], rbx
0x180005f4f  add     rbx, r14
0x180005f52  jmp     short loc_180005F58
0x180005f54  mov     [rdi+38h], r13
0x180005f58  sub     rsi, rbx
0x180005f5b  xor     edx, edx; Val
0x180005f5d  mov     r8, rsi; Size
0x180005f60  mov     rcx, rbx; void *
0x180005f63  call    memset_0
0x180005f68  add     rsp, 28h
0x180005f6c  pop     r15
0x180005f6e  pop     r14
0x180005f70  pop     r13
0x180005f72  pop     r12
0x180005f74  pop     rdi
0x180005f75  pop     rsi
0x180005f76  pop     rbp
0x180005f77  pop     rbx
0x180005f78  retn
```
