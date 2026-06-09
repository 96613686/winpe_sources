# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006dd4`
- end: `0x140006fed`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400049c0`

## callees

- `0x1400020d0`
- `0x140005838`
- `0x140006dd4`
- `0x140008948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006ebc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006ebc`

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
0x140006dd4  push    rbx
0x140006dd6  push    rbp
0x140006dd7  push    rsi
0x140006dd8  push    rdi
0x140006dd9  push    r12
0x140006ddb  push    r13
0x140006ddd  push    r14
0x140006ddf  push    r15
0x140006de1  sub     rsp, 28h
0x140006de5  mov     [rcx+4], r8d
0x140006de9  xor     r13d, r13d
0x140006dec  mov     eax, [rdx+8]
0x140006def  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140006df3  mov     [rcx+8], eax
0x140006df6  mov     rdi, rcx
0x140006df9  mov     [rcx+10h], r13
0x140006dfd  mov     r12, rdx
0x140006e00  movzx   eax, word ptr [rdx+40h]
0x140006e04  mov     [rcx+18h], ax
0x140006e08  mov     al, [rdx]
0x140006e0a  mov     [rcx+1Ah], al
0x140006e0d  mov     [rcx+20h], r13
0x140006e11  mov     rax, [rdx+88h]
0x140006e18  mov     [rcx+28h], rax
0x140006e1c  mov     rax, [rdx+90h]
0x140006e23  mov     [rcx+30h], rax
0x140006e27  mov     [rcx+38h], r13
0x140006e2b  mov     rcx, [rdx+38h]
0x140006e2f  lea     edx, [rbp+2]
0x140006e32  test    rcx, rcx
0x140006e35  jnz     short loc_140006E3C
0x140006e37  mov     r8d, edx
0x140006e3a  jmp     short loc_140006E4C
0x140006e3c  mov     rax, rbp
0x140006e3f  inc     rax
0x140006e42  cmp     [rcx+rax], r13b
0x140006e46  jnz     short loc_140006E3F
0x140006e48  lea     r8, [rax+1]; unsigned __int64
0x140006e4c  mov     rcx, [r12+80h]
0x140006e54  test    rcx, rcx
0x140006e57  jz      short loc_140006E69
0x140006e59  mov     rax, rbp
0x140006e5c  inc     rax
0x140006e5f  cmp     [rcx+rax], r13b
0x140006e63  jnz     short loc_140006E5C
0x140006e65  lea     rdx, [rax+1]
0x140006e69  mov     rcx, [r12+18h]
0x140006e6e  test    rcx, rcx
0x140006e71  jnz     short loc_140006E78
0x140006e73  lea     eax, [rcx+2]
0x140006e76  jmp     short loc_140006E8D
0x140006e78  mov     rax, rbp
0x140006e7b  inc     rax
0x140006e7e  cmp     [rcx+rax*2], r13w
0x140006e83  jnz     short loc_140006E7B
0x140006e85  lea     rax, ds:2[rax*2]
0x140006e8d  lea     r14, [rdx+rax]
0x140006e91  add     r14, r8
0x140006e94  lea     rsi, [rdi+48h]
0x140006e98  cmp     [rdi+40h], r13
0x140006e9c  jz      short loc_140006EA3
0x140006e9e  cmp     [rsi], r14
0x140006ea1  jnb     short loc_140006ED7
0x140006ea3  mov     rdx, r14; dwBytes
0x140006ea6  mov     ecx, 8; dwFlags
0x140006eab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006eb0  mov     r15, rax
0x140006eb3  test    rax, rax
0x140006eb6  jz      short loc_140006ED7
0x140006eb8  mov     rbx, [rdi+40h]
0x140006ebc  call    cs:__imp_GetProcessHeap
0x140006ec2  mov     r8, rbx; lpMem
0x140006ec5  xor     edx, edx; dwFlags
0x140006ec7  mov     rcx, rax; hHeap
0x140006eca  call    cs:__imp_HeapFree
0x140006ed0  mov     [rdi+40h], r15
0x140006ed4  mov     [rsi], r14
0x140006ed7  mov     rbx, [rdi+40h]
0x140006edb  test    rbx, rbx
0x140006ede  jz      loc_140006FDC
0x140006ee4  mov     rdx, [rsi]; DestinationSize
0x140006ee7  lea     rsi, [rdx+rbx]
0x140006eeb  cmp     rbx, rsi
0x140006eee  jz      short loc_140006F2E
0x140006ef0  mov     r8, [r12+38h]; Source
0x140006ef5  test    r8, r8
0x140006ef8  jz      short loc_140006F2E
0x140006efa  cmp     [r8], r13b
0x140006efd  jz      short loc_140006F2E
0x140006eff  mov     rax, rbp
0x140006f02  inc     rax
0x140006f05  cmp     [r8+rax], r13b
0x140006f09  jnz     short loc_140006F02
0x140006f0b  lea     r14, [rax+1]
0x140006f0f  cmp     rdx, r14
0x140006f12  jnb     short loc_140006F1A
0x140006f14  mov     [rdi+10h], r13
0x140006f18  jmp     short loc_140006F37
0x140006f1a  mov     r9, r14; SourceSize
0x140006f1d  mov     rcx, rbx; Destination
0x140006f20  call    memcpy_s
0x140006f25  mov     [rdi+10h], rbx
0x140006f29  add     rbx, r14
0x140006f2c  jmp     short loc_140006F32
0x140006f2e  mov     [rdi+10h], r13
0x140006f32  cmp     rbx, rsi
0x140006f35  jz      short loc_140006F7E
0x140006f37  mov     r8, [r12+80h]; Source
0x140006f3f  test    r8, r8
0x140006f42  jz      short loc_140006F7E
0x140006f44  cmp     [r8], r13b
0x140006f47  jz      short loc_140006F7E
0x140006f49  mov     rax, rbp
0x140006f4c  inc     rax
0x140006f4f  cmp     [r8+rax], r13b
0x140006f53  jnz     short loc_140006F4C
0x140006f55  mov     rdx, rsi
0x140006f58  lea     r14, [rax+1]
0x140006f5c  sub     rdx, rbx; DestinationSize
0x140006f5f  cmp     rdx, r14
0x140006f62  jnb     short loc_140006F6A
0x140006f64  mov     [rdi+20h], r13
0x140006f68  jmp     short loc_140006F87
0x140006f6a  mov     r9, r14; SourceSize
0x140006f6d  mov     rcx, rbx; Destination
0x140006f70  call    memcpy_s
0x140006f75  mov     [rdi+20h], rbx
0x140006f79  add     rbx, r14
0x140006f7c  jmp     short loc_140006F82
0x140006f7e  mov     [rdi+20h], r13
0x140006f82  cmp     rbx, rsi
0x140006f85  jz      short loc_140006FC8
0x140006f87  mov     r8, [r12+18h]; Source
0x140006f8c  test    r8, r8
0x140006f8f  jz      short loc_140006FC8
0x140006f91  cmp     [r8], r13w
0x140006f95  jz      short loc_140006FC8
0x140006f97  inc     rbp
0x140006f9a  cmp     [r8+rbp*2], r13w
0x140006f9f  jnz     short loc_140006F97
0x140006fa1  mov     rdx, rsi
0x140006fa4  lea     r14, ds:2[rbp*2]
0x140006fac  sub     rdx, rbx; DestinationSize
0x140006faf  cmp     rdx, r14
0x140006fb2  jb      short loc_140006FC8
0x140006fb4  mov     r9, r14; SourceSize
0x140006fb7  mov     rcx, rbx; Destination
0x140006fba  call    memcpy_s
0x140006fbf  mov     [rdi+38h], rbx
0x140006fc3  add     rbx, r14
0x140006fc6  jmp     short loc_140006FCC
0x140006fc8  mov     [rdi+38h], r13
0x140006fcc  sub     rsi, rbx
0x140006fcf  xor     edx, edx; Val
0x140006fd1  mov     r8, rsi; Size
0x140006fd4  mov     rcx, rbx; void *
0x140006fd7  call    memset_0
0x140006fdc  add     rsp, 28h
0x140006fe0  pop     r15
0x140006fe2  pop     r14
0x140006fe4  pop     r13
0x140006fe6  pop     r12
0x140006fe8  pop     rdi
0x140006fe9  pop     rsi
0x140006fea  pop     rbp
0x140006feb  pop     rbx
0x140006fec  retn
```
