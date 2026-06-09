# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005ab4`
- end: `0x140005ccd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004430`

## callees

- `0x140001f0e`
- `0x140005530`
- `0x140005ab4`
- `0x140006f88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005baa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005baa`

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
0x140005ab4  push    rbx
0x140005ab6  push    rbp
0x140005ab7  push    rsi
0x140005ab8  push    rdi
0x140005ab9  push    r12
0x140005abb  push    r13
0x140005abd  push    r14
0x140005abf  push    r15
0x140005ac1  sub     rsp, 28h
0x140005ac5  mov     [rcx+4], r8d
0x140005ac9  xor     r13d, r13d
0x140005acc  mov     eax, [rdx+8]
0x140005acf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140005ad3  mov     [rcx+8], eax
0x140005ad6  mov     rdi, rcx
0x140005ad9  mov     [rcx+10h], r13
0x140005add  mov     r12, rdx
0x140005ae0  movzx   eax, word ptr [rdx+40h]
0x140005ae4  mov     [rcx+18h], ax
0x140005ae8  mov     al, [rdx]
0x140005aea  mov     [rcx+1Ah], al
0x140005aed  mov     [rcx+20h], r13
0x140005af1  mov     rax, [rdx+88h]
0x140005af8  mov     [rcx+28h], rax
0x140005afc  mov     rax, [rdx+90h]
0x140005b03  mov     [rcx+30h], rax
0x140005b07  mov     [rcx+38h], r13
0x140005b0b  mov     rcx, [rdx+38h]
0x140005b0f  lea     edx, [rbp+2]
0x140005b12  test    rcx, rcx
0x140005b15  jnz     short loc_140005B1C
0x140005b17  mov     r8d, edx
0x140005b1a  jmp     short loc_140005B2C
0x140005b1c  mov     rax, rbp
0x140005b1f  inc     rax
0x140005b22  cmp     [rcx+rax], r13b
0x140005b26  jnz     short loc_140005B1F
0x140005b28  lea     r8, [rax+1]; unsigned __int64
0x140005b2c  mov     rcx, [r12+80h]
0x140005b34  test    rcx, rcx
0x140005b37  jz      short loc_140005B49
0x140005b39  mov     rax, rbp
0x140005b3c  inc     rax
0x140005b3f  cmp     [rcx+rax], r13b
0x140005b43  jnz     short loc_140005B3C
0x140005b45  lea     rdx, [rax+1]
0x140005b49  mov     rcx, [r12+18h]
0x140005b4e  test    rcx, rcx
0x140005b51  jnz     short loc_140005B58
0x140005b53  lea     eax, [rcx+2]
0x140005b56  jmp     short loc_140005B6D
0x140005b58  mov     rax, rbp
0x140005b5b  inc     rax
0x140005b5e  cmp     [rcx+rax*2], r13w
0x140005b63  jnz     short loc_140005B5B
0x140005b65  lea     rax, ds:2[rax*2]
0x140005b6d  lea     r14, [rdx+rax]
0x140005b71  add     r14, r8
0x140005b74  lea     rsi, [rdi+48h]
0x140005b78  cmp     [rdi+40h], r13
0x140005b7c  jz      short loc_140005B83
0x140005b7e  cmp     [rsi], r14
0x140005b81  jnb     short loc_140005BB7
0x140005b83  mov     rdx, r14; dwBytes
0x140005b86  mov     ecx, 8; dwFlags
0x140005b8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b90  mov     r15, rax
0x140005b93  test    rax, rax
0x140005b96  jz      short loc_140005BB7
0x140005b98  mov     rbx, [rdi+40h]
0x140005b9c  call    cs:__imp_GetProcessHeap
0x140005ba2  mov     r8, rbx; lpMem
0x140005ba5  xor     edx, edx; dwFlags
0x140005ba7  mov     rcx, rax; hHeap
0x140005baa  call    cs:__imp_HeapFree
0x140005bb0  mov     [rdi+40h], r15
0x140005bb4  mov     [rsi], r14
0x140005bb7  mov     rbx, [rdi+40h]
0x140005bbb  test    rbx, rbx
0x140005bbe  jz      loc_140005CBC
0x140005bc4  mov     rdx, [rsi]; DestinationSize
0x140005bc7  lea     rsi, [rdx+rbx]
0x140005bcb  cmp     rbx, rsi
0x140005bce  jz      short loc_140005C0E
0x140005bd0  mov     r8, [r12+38h]; Source
0x140005bd5  test    r8, r8
0x140005bd8  jz      short loc_140005C0E
0x140005bda  cmp     [r8], r13b
0x140005bdd  jz      short loc_140005C0E
0x140005bdf  mov     rax, rbp
0x140005be2  inc     rax
0x140005be5  cmp     [r8+rax], r13b
0x140005be9  jnz     short loc_140005BE2
0x140005beb  lea     r14, [rax+1]
0x140005bef  cmp     rdx, r14
0x140005bf2  jnb     short loc_140005BFA
0x140005bf4  mov     [rdi+10h], r13
0x140005bf8  jmp     short loc_140005C17
0x140005bfa  mov     r9, r14; SourceSize
0x140005bfd  mov     rcx, rbx; Destination
0x140005c00  call    memcpy_s
0x140005c05  mov     [rdi+10h], rbx
0x140005c09  add     rbx, r14
0x140005c0c  jmp     short loc_140005C12
0x140005c0e  mov     [rdi+10h], r13
0x140005c12  cmp     rbx, rsi
0x140005c15  jz      short loc_140005C5E
0x140005c17  mov     r8, [r12+80h]; Source
0x140005c1f  test    r8, r8
0x140005c22  jz      short loc_140005C5E
0x140005c24  cmp     [r8], r13b
0x140005c27  jz      short loc_140005C5E
0x140005c29  mov     rax, rbp
0x140005c2c  inc     rax
0x140005c2f  cmp     [r8+rax], r13b
0x140005c33  jnz     short loc_140005C2C
0x140005c35  mov     rdx, rsi
0x140005c38  lea     r14, [rax+1]
0x140005c3c  sub     rdx, rbx; DestinationSize
0x140005c3f  cmp     rdx, r14
0x140005c42  jnb     short loc_140005C4A
0x140005c44  mov     [rdi+20h], r13
0x140005c48  jmp     short loc_140005C67
0x140005c4a  mov     r9, r14; SourceSize
0x140005c4d  mov     rcx, rbx; Destination
0x140005c50  call    memcpy_s
0x140005c55  mov     [rdi+20h], rbx
0x140005c59  add     rbx, r14
0x140005c5c  jmp     short loc_140005C62
0x140005c5e  mov     [rdi+20h], r13
0x140005c62  cmp     rbx, rsi
0x140005c65  jz      short loc_140005CA8
0x140005c67  mov     r8, [r12+18h]; Source
0x140005c6c  test    r8, r8
0x140005c6f  jz      short loc_140005CA8
0x140005c71  cmp     [r8], r13w
0x140005c75  jz      short loc_140005CA8
0x140005c77  inc     rbp
0x140005c7a  cmp     [r8+rbp*2], r13w
0x140005c7f  jnz     short loc_140005C77
0x140005c81  mov     rdx, rsi
0x140005c84  lea     r14, ds:2[rbp*2]
0x140005c8c  sub     rdx, rbx; DestinationSize
0x140005c8f  cmp     rdx, r14
0x140005c92  jb      short loc_140005CA8
0x140005c94  mov     r9, r14; SourceSize
0x140005c97  mov     rcx, rbx; Destination
0x140005c9a  call    memcpy_s
0x140005c9f  mov     [rdi+38h], rbx
0x140005ca3  add     rbx, r14
0x140005ca6  jmp     short loc_140005CAC
0x140005ca8  mov     [rdi+38h], r13
0x140005cac  sub     rsi, rbx
0x140005caf  xor     edx, edx; Val
0x140005cb1  mov     r8, rsi; Size
0x140005cb4  mov     rcx, rbx; void *
0x140005cb7  call    memset_0
0x140005cbc  add     rsp, 28h
0x140005cc0  pop     r15
0x140005cc2  pop     r14
0x140005cc4  pop     r13
0x140005cc6  pop     r12
0x140005cc8  pop     rdi
0x140005cc9  pop     rsi
0x140005cca  pop     rbp
0x140005ccb  pop     rbx
0x140005ccc  retn
```
