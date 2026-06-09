# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005a70`
- end: `0x180005c8c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004390`

## callees

- `0x1800051fc`
- `0x180005a70`
- `0x18001200e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005bbc`
- `msvcrt!memcpy_s` at `0x180005c0d`
- `msvcrt!memcpy_s` at `0x180005c58`
- `msvcrt!memcpy_s` at `0x180005bbc`
- `msvcrt!memcpy_s` at `0x180005c0d`
- `msvcrt!memcpy_s` at `0x180005c58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b66`

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
0x180005a70  push    rbx
0x180005a72  push    rbp
0x180005a73  push    rsi
0x180005a74  push    rdi
0x180005a75  push    r12
0x180005a77  push    r13
0x180005a79  push    r14
0x180005a7b  push    r15
0x180005a7d  sub     rsp, 28h
0x180005a81  mov     [rcx+4], r8d
0x180005a85  xor     r13d, r13d
0x180005a88  mov     eax, [rdx+8]
0x180005a8b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005a8f  mov     [rcx+8], eax
0x180005a92  mov     rdi, rcx
0x180005a95  mov     [rcx+10h], r13
0x180005a99  mov     r12, rdx
0x180005a9c  movzx   eax, word ptr [rdx+40h]
0x180005aa0  mov     [rcx+18h], ax
0x180005aa4  mov     al, [rdx]
0x180005aa6  mov     [rcx+1Ah], al
0x180005aa9  mov     [rcx+20h], r13
0x180005aad  mov     rax, [rdx+88h]
0x180005ab4  mov     [rcx+28h], rax
0x180005ab8  mov     rax, [rdx+90h]
0x180005abf  mov     [rcx+30h], rax
0x180005ac3  mov     [rcx+38h], r13
0x180005ac7  mov     rcx, [rdx+38h]
0x180005acb  lea     edx, [rbp+2]
0x180005ace  test    rcx, rcx
0x180005ad1  jnz     short loc_180005AD8
0x180005ad3  mov     r8d, edx
0x180005ad6  jmp     short loc_180005AE8
0x180005ad8  mov     rax, rbp
0x180005adb  inc     rax
0x180005ade  cmp     [rcx+rax], r13b
0x180005ae2  jnz     short loc_180005ADB
0x180005ae4  lea     r8, [rax+1]; unsigned __int64
0x180005ae8  mov     rcx, [r12+80h]
0x180005af0  test    rcx, rcx
0x180005af3  jz      short loc_180005B05
0x180005af5  mov     rax, rbp
0x180005af8  inc     rax
0x180005afb  cmp     [rcx+rax], r13b
0x180005aff  jnz     short loc_180005AF8
0x180005b01  lea     rdx, [rax+1]
0x180005b05  mov     rcx, [r12+18h]
0x180005b0a  test    rcx, rcx
0x180005b0d  jnz     short loc_180005B14
0x180005b0f  lea     eax, [rcx+2]
0x180005b12  jmp     short loc_180005B29
0x180005b14  mov     rax, rbp
0x180005b17  inc     rax
0x180005b1a  cmp     [rcx+rax*2], r13w
0x180005b1f  jnz     short loc_180005B17
0x180005b21  lea     rax, ds:2[rax*2]
0x180005b29  lea     r14, [rdx+rax]
0x180005b2d  add     r14, r8
0x180005b30  lea     rsi, [rdi+48h]
0x180005b34  cmp     [rdi+40h], r13
0x180005b38  jz      short loc_180005B3F
0x180005b3a  cmp     [rsi], r14
0x180005b3d  jnb     short loc_180005B73
0x180005b3f  mov     rdx, r14; dwBytes
0x180005b42  mov     ecx, 8; dwFlags
0x180005b47  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005b4c  mov     r15, rax
0x180005b4f  test    rax, rax
0x180005b52  jz      short loc_180005B73
0x180005b54  mov     rbx, [rdi+40h]
0x180005b58  call    cs:__imp_GetProcessHeap
0x180005b5e  mov     r8, rbx; lpMem
0x180005b61  xor     edx, edx; dwFlags
0x180005b63  mov     rcx, rax; hHeap
0x180005b66  call    cs:__imp_HeapFree
0x180005b6c  mov     [rdi+40h], r15
0x180005b70  mov     [rsi], r14
0x180005b73  mov     rbx, [rdi+40h]
0x180005b77  test    rbx, rbx
0x180005b7a  jz      loc_180005C7B
0x180005b80  mov     rdx, [rsi]; DestinationSize
0x180005b83  lea     rsi, [rdx+rbx]
0x180005b87  cmp     rbx, rsi
0x180005b8a  jz      short loc_180005BCB
0x180005b8c  mov     r8, [r12+38h]; Source
0x180005b91  test    r8, r8
0x180005b94  jz      short loc_180005BCB
0x180005b96  cmp     [r8], r13b
0x180005b99  jz      short loc_180005BCB
0x180005b9b  mov     rax, rbp
0x180005b9e  inc     rax
0x180005ba1  cmp     [r8+rax], r13b
0x180005ba5  jnz     short loc_180005B9E
0x180005ba7  lea     r14, [rax+1]
0x180005bab  cmp     rdx, r14
0x180005bae  jnb     short loc_180005BB6
0x180005bb0  mov     [rdi+10h], r13
0x180005bb4  jmp     short loc_180005BD4
0x180005bb6  mov     r9, r14; SourceSize
0x180005bb9  mov     rcx, rbx; Destination
0x180005bbc  call    cs:__imp_memcpy_s
0x180005bc2  mov     [rdi+10h], rbx
0x180005bc6  add     rbx, r14
0x180005bc9  jmp     short loc_180005BCF
0x180005bcb  mov     [rdi+10h], r13
0x180005bcf  cmp     rbx, rsi
0x180005bd2  jz      short loc_180005C1C
0x180005bd4  mov     r8, [r12+80h]; Source
0x180005bdc  test    r8, r8
0x180005bdf  jz      short loc_180005C1C
0x180005be1  cmp     [r8], r13b
0x180005be4  jz      short loc_180005C1C
0x180005be6  mov     rax, rbp
0x180005be9  inc     rax
0x180005bec  cmp     [r8+rax], r13b
0x180005bf0  jnz     short loc_180005BE9
0x180005bf2  mov     rdx, rsi
0x180005bf5  lea     r14, [rax+1]
0x180005bf9  sub     rdx, rbx; DestinationSize
0x180005bfc  cmp     rdx, r14
0x180005bff  jnb     short loc_180005C07
0x180005c01  mov     [rdi+20h], r13
0x180005c05  jmp     short loc_180005C25
0x180005c07  mov     r9, r14; SourceSize
0x180005c0a  mov     rcx, rbx; Destination
0x180005c0d  call    cs:__imp_memcpy_s
0x180005c13  mov     [rdi+20h], rbx
0x180005c17  add     rbx, r14
0x180005c1a  jmp     short loc_180005C20
0x180005c1c  mov     [rdi+20h], r13
0x180005c20  cmp     rbx, rsi
0x180005c23  jz      short loc_180005C67
0x180005c25  mov     r8, [r12+18h]; Source
0x180005c2a  test    r8, r8
0x180005c2d  jz      short loc_180005C67
0x180005c2f  cmp     [r8], r13w
0x180005c33  jz      short loc_180005C67
0x180005c35  inc     rbp
0x180005c38  cmp     [r8+rbp*2], r13w
0x180005c3d  jnz     short loc_180005C35
0x180005c3f  mov     rdx, rsi
0x180005c42  lea     r14, ds:2[rbp*2]
0x180005c4a  sub     rdx, rbx; DestinationSize
0x180005c4d  cmp     rdx, r14
0x180005c50  jb      short loc_180005C67
0x180005c52  mov     r9, r14; SourceSize
0x180005c55  mov     rcx, rbx; Destination
0x180005c58  call    cs:__imp_memcpy_s
0x180005c5e  mov     [rdi+38h], rbx
0x180005c62  add     rbx, r14
0x180005c65  jmp     short loc_180005C6B
0x180005c67  mov     [rdi+38h], r13
0x180005c6b  sub     rsi, rbx
0x180005c6e  xor     edx, edx; Val
0x180005c70  mov     r8, rsi; Size
0x180005c73  mov     rcx, rbx; void *
0x180005c76  call    memset_0
0x180005c7b  add     rsp, 28h
0x180005c7f  pop     r15
0x180005c81  pop     r14
0x180005c83  pop     r13
0x180005c85  pop     r12
0x180005c87  pop     rdi
0x180005c88  pop     rsi
0x180005c89  pop     rbp
0x180005c8a  pop     rbx
0x180005c8b  retn
```
