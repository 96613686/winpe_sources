# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a940`
- end: `0x18000ab59`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006310`

## callees

- `0x180002be8`
- `0x180007e78`
- `0x18000a940`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa28`

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
0x18000a940  push    rbx
0x18000a942  push    rbp
0x18000a943  push    rsi
0x18000a944  push    rdi
0x18000a945  push    r12
0x18000a947  push    r13
0x18000a949  push    r14
0x18000a94b  push    r15
0x18000a94d  sub     rsp, 28h
0x18000a951  mov     [rcx+4], r8d
0x18000a955  xor     r13d, r13d
0x18000a958  mov     eax, [rdx+8]
0x18000a95b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a95f  mov     [rcx+8], eax
0x18000a962  mov     rdi, rcx
0x18000a965  mov     [rcx+10h], r13
0x18000a969  mov     r12, rdx
0x18000a96c  movzx   eax, word ptr [rdx+40h]
0x18000a970  mov     [rcx+18h], ax
0x18000a974  mov     al, [rdx]
0x18000a976  mov     [rcx+1Ah], al
0x18000a979  mov     [rcx+20h], r13
0x18000a97d  mov     rax, [rdx+88h]
0x18000a984  mov     [rcx+28h], rax
0x18000a988  mov     rax, [rdx+90h]
0x18000a98f  mov     [rcx+30h], rax
0x18000a993  mov     [rcx+38h], r13
0x18000a997  mov     rcx, [rdx+38h]
0x18000a99b  lea     edx, [rbp+2]
0x18000a99e  test    rcx, rcx
0x18000a9a1  jnz     short loc_18000A9A8
0x18000a9a3  mov     r8d, edx
0x18000a9a6  jmp     short loc_18000A9B8
0x18000a9a8  mov     rax, rbp
0x18000a9ab  inc     rax
0x18000a9ae  cmp     [rcx+rax], r13b
0x18000a9b2  jnz     short loc_18000A9AB
0x18000a9b4  lea     r8, [rax+1]; unsigned __int64
0x18000a9b8  mov     rcx, [r12+80h]
0x18000a9c0  test    rcx, rcx
0x18000a9c3  jz      short loc_18000A9D5
0x18000a9c5  mov     rax, rbp
0x18000a9c8  inc     rax
0x18000a9cb  cmp     [rcx+rax], r13b
0x18000a9cf  jnz     short loc_18000A9C8
0x18000a9d1  lea     rdx, [rax+1]
0x18000a9d5  mov     rcx, [r12+18h]
0x18000a9da  test    rcx, rcx
0x18000a9dd  jnz     short loc_18000A9E4
0x18000a9df  lea     eax, [rcx+2]
0x18000a9e2  jmp     short loc_18000A9F9
0x18000a9e4  mov     rax, rbp
0x18000a9e7  inc     rax
0x18000a9ea  cmp     [rcx+rax*2], r13w
0x18000a9ef  jnz     short loc_18000A9E7
0x18000a9f1  lea     rax, ds:2[rax*2]
0x18000a9f9  lea     r14, [rdx+rax]
0x18000a9fd  add     r14, r8
0x18000aa00  lea     rsi, [rdi+48h]
0x18000aa04  cmp     [rdi+40h], r13
0x18000aa08  jz      short loc_18000AA0F
0x18000aa0a  cmp     [rsi], r14
0x18000aa0d  jnb     short loc_18000AA43
0x18000aa0f  mov     rdx, r14; dwBytes
0x18000aa12  mov     ecx, 8; dwFlags
0x18000aa17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aa1c  mov     r15, rax
0x18000aa1f  test    rax, rax
0x18000aa22  jz      short loc_18000AA43
0x18000aa24  mov     rbx, [rdi+40h]
0x18000aa28  call    cs:__imp_GetProcessHeap
0x18000aa2e  mov     r8, rbx; lpMem
0x18000aa31  xor     edx, edx; dwFlags
0x18000aa33  mov     rcx, rax; hHeap
0x18000aa36  call    cs:__imp_HeapFree
0x18000aa3c  mov     [rdi+40h], r15
0x18000aa40  mov     [rsi], r14
0x18000aa43  mov     rbx, [rdi+40h]
0x18000aa47  test    rbx, rbx
0x18000aa4a  jz      loc_18000AB48
0x18000aa50  mov     rdx, [rsi]; DestinationSize
0x18000aa53  lea     rsi, [rdx+rbx]
0x18000aa57  cmp     rbx, rsi
0x18000aa5a  jz      short loc_18000AA9A
0x18000aa5c  mov     r8, [r12+38h]; Source
0x18000aa61  test    r8, r8
0x18000aa64  jz      short loc_18000AA9A
0x18000aa66  cmp     [r8], r13b
0x18000aa69  jz      short loc_18000AA9A
0x18000aa6b  mov     rax, rbp
0x18000aa6e  inc     rax
0x18000aa71  cmp     [r8+rax], r13b
0x18000aa75  jnz     short loc_18000AA6E
0x18000aa77  lea     r14, [rax+1]
0x18000aa7b  cmp     rdx, r14
0x18000aa7e  jnb     short loc_18000AA86
0x18000aa80  mov     [rdi+10h], r13
0x18000aa84  jmp     short loc_18000AAA3
0x18000aa86  mov     r9, r14; SourceSize
0x18000aa89  mov     rcx, rbx; Destination
0x18000aa8c  call    memcpy_s
0x18000aa91  mov     [rdi+10h], rbx
0x18000aa95  add     rbx, r14
0x18000aa98  jmp     short loc_18000AA9E
0x18000aa9a  mov     [rdi+10h], r13
0x18000aa9e  cmp     rbx, rsi
0x18000aaa1  jz      short loc_18000AAEA
0x18000aaa3  mov     r8, [r12+80h]; Source
0x18000aaab  test    r8, r8
0x18000aaae  jz      short loc_18000AAEA
0x18000aab0  cmp     [r8], r13b
0x18000aab3  jz      short loc_18000AAEA
0x18000aab5  mov     rax, rbp
0x18000aab8  inc     rax
0x18000aabb  cmp     [r8+rax], r13b
0x18000aabf  jnz     short loc_18000AAB8
0x18000aac1  mov     rdx, rsi
0x18000aac4  lea     r14, [rax+1]
0x18000aac8  sub     rdx, rbx; DestinationSize
0x18000aacb  cmp     rdx, r14
0x18000aace  jnb     short loc_18000AAD6
0x18000aad0  mov     [rdi+20h], r13
0x18000aad4  jmp     short loc_18000AAF3
0x18000aad6  mov     r9, r14; SourceSize
0x18000aad9  mov     rcx, rbx; Destination
0x18000aadc  call    memcpy_s
0x18000aae1  mov     [rdi+20h], rbx
0x18000aae5  add     rbx, r14
0x18000aae8  jmp     short loc_18000AAEE
0x18000aaea  mov     [rdi+20h], r13
0x18000aaee  cmp     rbx, rsi
0x18000aaf1  jz      short loc_18000AB34
0x18000aaf3  mov     r8, [r12+18h]; Source
0x18000aaf8  test    r8, r8
0x18000aafb  jz      short loc_18000AB34
0x18000aafd  cmp     [r8], r13w
0x18000ab01  jz      short loc_18000AB34
0x18000ab03  inc     rbp
0x18000ab06  cmp     [r8+rbp*2], r13w
0x18000ab0b  jnz     short loc_18000AB03
0x18000ab0d  mov     rdx, rsi
0x18000ab10  lea     r14, ds:2[rbp*2]
0x18000ab18  sub     rdx, rbx; DestinationSize
0x18000ab1b  cmp     rdx, r14
0x18000ab1e  jb      short loc_18000AB34
0x18000ab20  mov     r9, r14; SourceSize
0x18000ab23  mov     rcx, rbx; Destination
0x18000ab26  call    memcpy_s
0x18000ab2b  mov     [rdi+38h], rbx
0x18000ab2f  add     rbx, r14
0x18000ab32  jmp     short loc_18000AB38
0x18000ab34  mov     [rdi+38h], r13
0x18000ab38  sub     rsi, rbx
0x18000ab3b  xor     edx, edx; Val
0x18000ab3d  mov     r8, rsi; Size
0x18000ab40  mov     rcx, rbx; void *
0x18000ab43  call    memset_0
0x18000ab48  add     rsp, 28h
0x18000ab4c  pop     r15
0x18000ab4e  pop     r14
0x18000ab50  pop     r13
0x18000ab52  pop     r12
0x18000ab54  pop     rdi
0x18000ab55  pop     rsi
0x18000ab56  pop     rbp
0x18000ab57  pop     rbx
0x18000ab58  retn
```
