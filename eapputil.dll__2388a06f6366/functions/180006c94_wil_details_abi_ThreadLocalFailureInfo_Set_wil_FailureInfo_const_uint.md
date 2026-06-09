# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006c94`
- end: `0x180006ead`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005330`

## callees

- `0x180002b78`
- `0x1800064cc`
- `0x180006c94`
- `0x180007eac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d8a`

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
0x180006c94  push    rbx
0x180006c96  push    rbp
0x180006c97  push    rsi
0x180006c98  push    rdi
0x180006c99  push    r12
0x180006c9b  push    r13
0x180006c9d  push    r14
0x180006c9f  push    r15
0x180006ca1  sub     rsp, 28h
0x180006ca5  mov     [rcx+4], r8d
0x180006ca9  xor     r13d, r13d
0x180006cac  mov     eax, [rdx+8]
0x180006caf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006cb3  mov     [rcx+8], eax
0x180006cb6  mov     rdi, rcx
0x180006cb9  mov     [rcx+10h], r13
0x180006cbd  mov     r12, rdx
0x180006cc0  movzx   eax, word ptr [rdx+40h]
0x180006cc4  mov     [rcx+18h], ax
0x180006cc8  mov     al, [rdx]
0x180006cca  mov     [rcx+1Ah], al
0x180006ccd  mov     [rcx+20h], r13
0x180006cd1  mov     rax, [rdx+88h]
0x180006cd8  mov     [rcx+28h], rax
0x180006cdc  mov     rax, [rdx+90h]
0x180006ce3  mov     [rcx+30h], rax
0x180006ce7  mov     [rcx+38h], r13
0x180006ceb  mov     rcx, [rdx+38h]
0x180006cef  lea     edx, [rbp+2]
0x180006cf2  test    rcx, rcx
0x180006cf5  jnz     short loc_180006CFC
0x180006cf7  mov     r8d, edx
0x180006cfa  jmp     short loc_180006D0C
0x180006cfc  mov     rax, rbp
0x180006cff  inc     rax
0x180006d02  cmp     [rcx+rax], r13b
0x180006d06  jnz     short loc_180006CFF
0x180006d08  lea     r8, [rax+1]; unsigned __int64
0x180006d0c  mov     rcx, [r12+80h]
0x180006d14  test    rcx, rcx
0x180006d17  jz      short loc_180006D29
0x180006d19  mov     rax, rbp
0x180006d1c  inc     rax
0x180006d1f  cmp     [rcx+rax], r13b
0x180006d23  jnz     short loc_180006D1C
0x180006d25  lea     rdx, [rax+1]
0x180006d29  mov     rcx, [r12+18h]
0x180006d2e  test    rcx, rcx
0x180006d31  jnz     short loc_180006D38
0x180006d33  lea     eax, [rcx+2]
0x180006d36  jmp     short loc_180006D4D
0x180006d38  mov     rax, rbp
0x180006d3b  inc     rax
0x180006d3e  cmp     [rcx+rax*2], r13w
0x180006d43  jnz     short loc_180006D3B
0x180006d45  lea     rax, ds:2[rax*2]
0x180006d4d  lea     r14, [rdx+rax]
0x180006d51  add     r14, r8
0x180006d54  lea     rsi, [rdi+48h]
0x180006d58  cmp     [rdi+40h], r13
0x180006d5c  jz      short loc_180006D63
0x180006d5e  cmp     [rsi], r14
0x180006d61  jnb     short loc_180006D97
0x180006d63  mov     rdx, r14; dwBytes
0x180006d66  mov     ecx, 8; dwFlags
0x180006d6b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006d70  mov     r15, rax
0x180006d73  test    rax, rax
0x180006d76  jz      short loc_180006D97
0x180006d78  mov     rbx, [rdi+40h]
0x180006d7c  call    cs:__imp_GetProcessHeap
0x180006d82  mov     r8, rbx; lpMem
0x180006d85  xor     edx, edx; dwFlags
0x180006d87  mov     rcx, rax; hHeap
0x180006d8a  call    cs:__imp_HeapFree
0x180006d90  mov     [rdi+40h], r15
0x180006d94  mov     [rsi], r14
0x180006d97  mov     rbx, [rdi+40h]
0x180006d9b  test    rbx, rbx
0x180006d9e  jz      loc_180006E9C
0x180006da4  mov     rdx, [rsi]; DestinationSize
0x180006da7  lea     rsi, [rdx+rbx]
0x180006dab  cmp     rbx, rsi
0x180006dae  jz      short loc_180006DEE
0x180006db0  mov     r8, [r12+38h]; Source
0x180006db5  test    r8, r8
0x180006db8  jz      short loc_180006DEE
0x180006dba  cmp     [r8], r13b
0x180006dbd  jz      short loc_180006DEE
0x180006dbf  mov     rax, rbp
0x180006dc2  inc     rax
0x180006dc5  cmp     [r8+rax], r13b
0x180006dc9  jnz     short loc_180006DC2
0x180006dcb  lea     r14, [rax+1]
0x180006dcf  cmp     rdx, r14
0x180006dd2  jnb     short loc_180006DDA
0x180006dd4  mov     [rdi+10h], r13
0x180006dd8  jmp     short loc_180006DF7
0x180006dda  mov     r9, r14; SourceSize
0x180006ddd  mov     rcx, rbx; Destination
0x180006de0  call    memcpy_s
0x180006de5  mov     [rdi+10h], rbx
0x180006de9  add     rbx, r14
0x180006dec  jmp     short loc_180006DF2
0x180006dee  mov     [rdi+10h], r13
0x180006df2  cmp     rbx, rsi
0x180006df5  jz      short loc_180006E3E
0x180006df7  mov     r8, [r12+80h]; Source
0x180006dff  test    r8, r8
0x180006e02  jz      short loc_180006E3E
0x180006e04  cmp     [r8], r13b
0x180006e07  jz      short loc_180006E3E
0x180006e09  mov     rax, rbp
0x180006e0c  inc     rax
0x180006e0f  cmp     [r8+rax], r13b
0x180006e13  jnz     short loc_180006E0C
0x180006e15  mov     rdx, rsi
0x180006e18  lea     r14, [rax+1]
0x180006e1c  sub     rdx, rbx; DestinationSize
0x180006e1f  cmp     rdx, r14
0x180006e22  jnb     short loc_180006E2A
0x180006e24  mov     [rdi+20h], r13
0x180006e28  jmp     short loc_180006E47
0x180006e2a  mov     r9, r14; SourceSize
0x180006e2d  mov     rcx, rbx; Destination
0x180006e30  call    memcpy_s
0x180006e35  mov     [rdi+20h], rbx
0x180006e39  add     rbx, r14
0x180006e3c  jmp     short loc_180006E42
0x180006e3e  mov     [rdi+20h], r13
0x180006e42  cmp     rbx, rsi
0x180006e45  jz      short loc_180006E88
0x180006e47  mov     r8, [r12+18h]; Source
0x180006e4c  test    r8, r8
0x180006e4f  jz      short loc_180006E88
0x180006e51  cmp     [r8], r13w
0x180006e55  jz      short loc_180006E88
0x180006e57  inc     rbp
0x180006e5a  cmp     [r8+rbp*2], r13w
0x180006e5f  jnz     short loc_180006E57
0x180006e61  mov     rdx, rsi
0x180006e64  lea     r14, ds:2[rbp*2]
0x180006e6c  sub     rdx, rbx; DestinationSize
0x180006e6f  cmp     rdx, r14
0x180006e72  jb      short loc_180006E88
0x180006e74  mov     r9, r14; SourceSize
0x180006e77  mov     rcx, rbx; Destination
0x180006e7a  call    memcpy_s
0x180006e7f  mov     [rdi+38h], rbx
0x180006e83  add     rbx, r14
0x180006e86  jmp     short loc_180006E8C
0x180006e88  mov     [rdi+38h], r13
0x180006e8c  sub     rsi, rbx
0x180006e8f  xor     edx, edx; Val
0x180006e91  mov     r8, rsi; Size
0x180006e94  mov     rcx, rbx; void *
0x180006e97  call    memset_0
0x180006e9c  add     rsp, 28h
0x180006ea0  pop     r15
0x180006ea2  pop     r14
0x180006ea4  pop     r13
0x180006ea6  pop     r12
0x180006ea8  pop     rdi
0x180006ea9  pop     rsi
0x180006eaa  pop     rbp
0x180006eab  pop     rbx
0x180006eac  retn
```
