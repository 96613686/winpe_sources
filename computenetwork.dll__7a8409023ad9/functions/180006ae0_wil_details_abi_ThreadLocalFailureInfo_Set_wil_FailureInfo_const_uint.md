# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006ae0`
- end: `0x180006cf9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004bf0`

## callees

- `0x180002062`
- `0x180006588`
- `0x180006ae0`
- `0x180009d40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bc8`

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
0x180006ae0  push    rbx
0x180006ae2  push    rbp
0x180006ae3  push    rsi
0x180006ae4  push    rdi
0x180006ae5  push    r12
0x180006ae7  push    r13
0x180006ae9  push    r14
0x180006aeb  push    r15
0x180006aed  sub     rsp, 28h
0x180006af1  mov     [rcx+4], r8d
0x180006af5  xor     r13d, r13d
0x180006af8  mov     eax, [rdx+8]
0x180006afb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006aff  mov     [rcx+8], eax
0x180006b02  mov     rdi, rcx
0x180006b05  mov     [rcx+10h], r13
0x180006b09  mov     r12, rdx
0x180006b0c  movzx   eax, word ptr [rdx+40h]
0x180006b10  mov     [rcx+18h], ax
0x180006b14  mov     al, [rdx]
0x180006b16  mov     [rcx+1Ah], al
0x180006b19  mov     [rcx+20h], r13
0x180006b1d  mov     rax, [rdx+88h]
0x180006b24  mov     [rcx+28h], rax
0x180006b28  mov     rax, [rdx+90h]
0x180006b2f  mov     [rcx+30h], rax
0x180006b33  mov     [rcx+38h], r13
0x180006b37  mov     rcx, [rdx+38h]
0x180006b3b  lea     edx, [rbp+2]
0x180006b3e  test    rcx, rcx
0x180006b41  jnz     short loc_180006B48
0x180006b43  mov     r8d, edx
0x180006b46  jmp     short loc_180006B58
0x180006b48  mov     rax, rbp
0x180006b4b  inc     rax
0x180006b4e  cmp     [rcx+rax], r13b
0x180006b52  jnz     short loc_180006B4B
0x180006b54  lea     r8, [rax+1]; unsigned __int64
0x180006b58  mov     rcx, [r12+80h]
0x180006b60  test    rcx, rcx
0x180006b63  jz      short loc_180006B75
0x180006b65  mov     rax, rbp
0x180006b68  inc     rax
0x180006b6b  cmp     [rcx+rax], r13b
0x180006b6f  jnz     short loc_180006B68
0x180006b71  lea     rdx, [rax+1]
0x180006b75  mov     rcx, [r12+18h]
0x180006b7a  test    rcx, rcx
0x180006b7d  jnz     short loc_180006B84
0x180006b7f  lea     eax, [rcx+2]
0x180006b82  jmp     short loc_180006B99
0x180006b84  mov     rax, rbp
0x180006b87  inc     rax
0x180006b8a  cmp     [rcx+rax*2], r13w
0x180006b8f  jnz     short loc_180006B87
0x180006b91  lea     rax, ds:2[rax*2]
0x180006b99  lea     r14, [rdx+rax]
0x180006b9d  add     r14, r8
0x180006ba0  lea     rsi, [rdi+48h]
0x180006ba4  cmp     [rdi+40h], r13
0x180006ba8  jz      short loc_180006BAF
0x180006baa  cmp     [rsi], r14
0x180006bad  jnb     short loc_180006BE3
0x180006baf  mov     rdx, r14; dwBytes
0x180006bb2  mov     ecx, 8; dwFlags
0x180006bb7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006bbc  mov     r15, rax
0x180006bbf  test    rax, rax
0x180006bc2  jz      short loc_180006BE3
0x180006bc4  mov     rbx, [rdi+40h]
0x180006bc8  call    cs:__imp_GetProcessHeap
0x180006bce  mov     r8, rbx; lpMem
0x180006bd1  xor     edx, edx; dwFlags
0x180006bd3  mov     rcx, rax; hHeap
0x180006bd6  call    cs:__imp_HeapFree
0x180006bdc  mov     [rdi+40h], r15
0x180006be0  mov     [rsi], r14
0x180006be3  mov     rbx, [rdi+40h]
0x180006be7  test    rbx, rbx
0x180006bea  jz      loc_180006CE8
0x180006bf0  mov     rdx, [rsi]; DestinationSize
0x180006bf3  lea     rsi, [rdx+rbx]
0x180006bf7  cmp     rbx, rsi
0x180006bfa  jz      short loc_180006C3A
0x180006bfc  mov     r8, [r12+38h]; Source
0x180006c01  test    r8, r8
0x180006c04  jz      short loc_180006C3A
0x180006c06  cmp     [r8], r13b
0x180006c09  jz      short loc_180006C3A
0x180006c0b  mov     rax, rbp
0x180006c0e  inc     rax
0x180006c11  cmp     [r8+rax], r13b
0x180006c15  jnz     short loc_180006C0E
0x180006c17  lea     r14, [rax+1]
0x180006c1b  cmp     rdx, r14
0x180006c1e  jnb     short loc_180006C26
0x180006c20  mov     [rdi+10h], r13
0x180006c24  jmp     short loc_180006C43
0x180006c26  mov     r9, r14; SourceSize
0x180006c29  mov     rcx, rbx; Destination
0x180006c2c  call    memcpy_s
0x180006c31  mov     [rdi+10h], rbx
0x180006c35  add     rbx, r14
0x180006c38  jmp     short loc_180006C3E
0x180006c3a  mov     [rdi+10h], r13
0x180006c3e  cmp     rbx, rsi
0x180006c41  jz      short loc_180006C8A
0x180006c43  mov     r8, [r12+80h]; Source
0x180006c4b  test    r8, r8
0x180006c4e  jz      short loc_180006C8A
0x180006c50  cmp     [r8], r13b
0x180006c53  jz      short loc_180006C8A
0x180006c55  mov     rax, rbp
0x180006c58  inc     rax
0x180006c5b  cmp     [r8+rax], r13b
0x180006c5f  jnz     short loc_180006C58
0x180006c61  mov     rdx, rsi
0x180006c64  lea     r14, [rax+1]
0x180006c68  sub     rdx, rbx; DestinationSize
0x180006c6b  cmp     rdx, r14
0x180006c6e  jnb     short loc_180006C76
0x180006c70  mov     [rdi+20h], r13
0x180006c74  jmp     short loc_180006C93
0x180006c76  mov     r9, r14; SourceSize
0x180006c79  mov     rcx, rbx; Destination
0x180006c7c  call    memcpy_s
0x180006c81  mov     [rdi+20h], rbx
0x180006c85  add     rbx, r14
0x180006c88  jmp     short loc_180006C8E
0x180006c8a  mov     [rdi+20h], r13
0x180006c8e  cmp     rbx, rsi
0x180006c91  jz      short loc_180006CD4
0x180006c93  mov     r8, [r12+18h]; Source
0x180006c98  test    r8, r8
0x180006c9b  jz      short loc_180006CD4
0x180006c9d  cmp     [r8], r13w
0x180006ca1  jz      short loc_180006CD4
0x180006ca3  inc     rbp
0x180006ca6  cmp     [r8+rbp*2], r13w
0x180006cab  jnz     short loc_180006CA3
0x180006cad  mov     rdx, rsi
0x180006cb0  lea     r14, ds:2[rbp*2]
0x180006cb8  sub     rdx, rbx; DestinationSize
0x180006cbb  cmp     rdx, r14
0x180006cbe  jb      short loc_180006CD4
0x180006cc0  mov     r9, r14; SourceSize
0x180006cc3  mov     rcx, rbx; Destination
0x180006cc6  call    memcpy_s
0x180006ccb  mov     [rdi+38h], rbx
0x180006ccf  add     rbx, r14
0x180006cd2  jmp     short loc_180006CD8
0x180006cd4  mov     [rdi+38h], r13
0x180006cd8  sub     rsi, rbx
0x180006cdb  xor     edx, edx; Val
0x180006cdd  mov     r8, rsi; Size
0x180006ce0  mov     rcx, rbx; void *
0x180006ce3  call    memset_0
0x180006ce8  add     rsp, 28h
0x180006cec  pop     r15
0x180006cee  pop     r14
0x180006cf0  pop     r13
0x180006cf2  pop     r12
0x180006cf4  pop     rdi
0x180006cf5  pop     rsi
0x180006cf6  pop     rbp
0x180006cf7  pop     rbx
0x180006cf8  retn
```
