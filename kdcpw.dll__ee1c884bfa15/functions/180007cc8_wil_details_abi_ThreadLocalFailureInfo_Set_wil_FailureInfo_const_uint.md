# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007cc8`
- end: `0x180007ee1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ce0`

## callees

- `0x180001f88`
- `0x1800061a8`
- `0x180007cc8`
- `0x1800094bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007db0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007db0`

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
0x180007cc8  push    rbx
0x180007cca  push    rbp
0x180007ccb  push    rsi
0x180007ccc  push    rdi
0x180007ccd  push    r12
0x180007ccf  push    r13
0x180007cd1  push    r14
0x180007cd3  push    r15
0x180007cd5  sub     rsp, 28h
0x180007cd9  mov     [rcx+4], r8d
0x180007cdd  xor     r13d, r13d
0x180007ce0  mov     eax, [rdx+8]
0x180007ce3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007ce7  mov     [rcx+8], eax
0x180007cea  mov     rdi, rcx
0x180007ced  mov     [rcx+10h], r13
0x180007cf1  mov     r12, rdx
0x180007cf4  movzx   eax, word ptr [rdx+40h]
0x180007cf8  mov     [rcx+18h], ax
0x180007cfc  mov     al, [rdx]
0x180007cfe  mov     [rcx+1Ah], al
0x180007d01  mov     [rcx+20h], r13
0x180007d05  mov     rax, [rdx+88h]
0x180007d0c  mov     [rcx+28h], rax
0x180007d10  mov     rax, [rdx+90h]
0x180007d17  mov     [rcx+30h], rax
0x180007d1b  mov     [rcx+38h], r13
0x180007d1f  mov     rcx, [rdx+38h]
0x180007d23  lea     edx, [rbp+2]
0x180007d26  test    rcx, rcx
0x180007d29  jnz     short loc_180007D30
0x180007d2b  mov     r8d, edx
0x180007d2e  jmp     short loc_180007D40
0x180007d30  mov     rax, rbp
0x180007d33  inc     rax
0x180007d36  cmp     [rcx+rax], r13b
0x180007d3a  jnz     short loc_180007D33
0x180007d3c  lea     r8, [rax+1]; unsigned __int64
0x180007d40  mov     rcx, [r12+80h]
0x180007d48  test    rcx, rcx
0x180007d4b  jz      short loc_180007D5D
0x180007d4d  mov     rax, rbp
0x180007d50  inc     rax
0x180007d53  cmp     [rcx+rax], r13b
0x180007d57  jnz     short loc_180007D50
0x180007d59  lea     rdx, [rax+1]
0x180007d5d  mov     rcx, [r12+18h]
0x180007d62  test    rcx, rcx
0x180007d65  jnz     short loc_180007D6C
0x180007d67  lea     eax, [rcx+2]
0x180007d6a  jmp     short loc_180007D81
0x180007d6c  mov     rax, rbp
0x180007d6f  inc     rax
0x180007d72  cmp     [rcx+rax*2], r13w
0x180007d77  jnz     short loc_180007D6F
0x180007d79  lea     rax, ds:2[rax*2]
0x180007d81  lea     r14, [rdx+rax]
0x180007d85  add     r14, r8
0x180007d88  lea     rsi, [rdi+48h]
0x180007d8c  cmp     [rdi+40h], r13
0x180007d90  jz      short loc_180007D97
0x180007d92  cmp     [rsi], r14
0x180007d95  jnb     short loc_180007DCB
0x180007d97  mov     rdx, r14; dwBytes
0x180007d9a  mov     ecx, 8; dwFlags
0x180007d9f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007da4  mov     r15, rax
0x180007da7  test    rax, rax
0x180007daa  jz      short loc_180007DCB
0x180007dac  mov     rbx, [rdi+40h]
0x180007db0  call    cs:__imp_GetProcessHeap
0x180007db6  mov     r8, rbx; lpMem
0x180007db9  xor     edx, edx; dwFlags
0x180007dbb  mov     rcx, rax; hHeap
0x180007dbe  call    cs:__imp_HeapFree
0x180007dc4  mov     [rdi+40h], r15
0x180007dc8  mov     [rsi], r14
0x180007dcb  mov     rbx, [rdi+40h]
0x180007dcf  test    rbx, rbx
0x180007dd2  jz      loc_180007ED0
0x180007dd8  mov     rdx, [rsi]; DestinationSize
0x180007ddb  lea     rsi, [rdx+rbx]
0x180007ddf  cmp     rbx, rsi
0x180007de2  jz      short loc_180007E22
0x180007de4  mov     r8, [r12+38h]; Source
0x180007de9  test    r8, r8
0x180007dec  jz      short loc_180007E22
0x180007dee  cmp     [r8], r13b
0x180007df1  jz      short loc_180007E22
0x180007df3  mov     rax, rbp
0x180007df6  inc     rax
0x180007df9  cmp     [r8+rax], r13b
0x180007dfd  jnz     short loc_180007DF6
0x180007dff  lea     r14, [rax+1]
0x180007e03  cmp     rdx, r14
0x180007e06  jnb     short loc_180007E0E
0x180007e08  mov     [rdi+10h], r13
0x180007e0c  jmp     short loc_180007E2B
0x180007e0e  mov     r9, r14; SourceSize
0x180007e11  mov     rcx, rbx; Destination
0x180007e14  call    memcpy_s
0x180007e19  mov     [rdi+10h], rbx
0x180007e1d  add     rbx, r14
0x180007e20  jmp     short loc_180007E26
0x180007e22  mov     [rdi+10h], r13
0x180007e26  cmp     rbx, rsi
0x180007e29  jz      short loc_180007E72
0x180007e2b  mov     r8, [r12+80h]; Source
0x180007e33  test    r8, r8
0x180007e36  jz      short loc_180007E72
0x180007e38  cmp     [r8], r13b
0x180007e3b  jz      short loc_180007E72
0x180007e3d  mov     rax, rbp
0x180007e40  inc     rax
0x180007e43  cmp     [r8+rax], r13b
0x180007e47  jnz     short loc_180007E40
0x180007e49  mov     rdx, rsi
0x180007e4c  lea     r14, [rax+1]
0x180007e50  sub     rdx, rbx; DestinationSize
0x180007e53  cmp     rdx, r14
0x180007e56  jnb     short loc_180007E5E
0x180007e58  mov     [rdi+20h], r13
0x180007e5c  jmp     short loc_180007E7B
0x180007e5e  mov     r9, r14; SourceSize
0x180007e61  mov     rcx, rbx; Destination
0x180007e64  call    memcpy_s
0x180007e69  mov     [rdi+20h], rbx
0x180007e6d  add     rbx, r14
0x180007e70  jmp     short loc_180007E76
0x180007e72  mov     [rdi+20h], r13
0x180007e76  cmp     rbx, rsi
0x180007e79  jz      short loc_180007EBC
0x180007e7b  mov     r8, [r12+18h]; Source
0x180007e80  test    r8, r8
0x180007e83  jz      short loc_180007EBC
0x180007e85  cmp     [r8], r13w
0x180007e89  jz      short loc_180007EBC
0x180007e8b  inc     rbp
0x180007e8e  cmp     [r8+rbp*2], r13w
0x180007e93  jnz     short loc_180007E8B
0x180007e95  mov     rdx, rsi
0x180007e98  lea     r14, ds:2[rbp*2]
0x180007ea0  sub     rdx, rbx; DestinationSize
0x180007ea3  cmp     rdx, r14
0x180007ea6  jb      short loc_180007EBC
0x180007ea8  mov     r9, r14; SourceSize
0x180007eab  mov     rcx, rbx; Destination
0x180007eae  call    memcpy_s
0x180007eb3  mov     [rdi+38h], rbx
0x180007eb7  add     rbx, r14
0x180007eba  jmp     short loc_180007EC0
0x180007ebc  mov     [rdi+38h], r13
0x180007ec0  sub     rsi, rbx
0x180007ec3  xor     edx, edx; Val
0x180007ec5  mov     r8, rsi; Size
0x180007ec8  mov     rcx, rbx; void *
0x180007ecb  call    memset_0
0x180007ed0  add     rsp, 28h
0x180007ed4  pop     r15
0x180007ed6  pop     r14
0x180007ed8  pop     r13
0x180007eda  pop     r12
0x180007edc  pop     rdi
0x180007edd  pop     rsi
0x180007ede  pop     rbp
0x180007edf  pop     rbx
0x180007ee0  retn
```
