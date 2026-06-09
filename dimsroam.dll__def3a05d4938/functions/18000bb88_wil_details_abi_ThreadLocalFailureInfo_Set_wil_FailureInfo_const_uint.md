# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000bb88`
- end: `0x18000bda4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009690`

## callees

- `0x18000a7f8`
- `0x18000bb88`
- `0x18000d89e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bcd4`
- `msvcrt!memcpy_s` at `0x18000bd25`
- `msvcrt!memcpy_s` at `0x18000bd70`
- `msvcrt!memcpy_s` at `0x18000bcd4`
- `msvcrt!memcpy_s` at `0x18000bd25`
- `msvcrt!memcpy_s` at `0x18000bd70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc70`

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
0x18000bb88  push    rbx
0x18000bb8a  push    rbp
0x18000bb8b  push    rsi
0x18000bb8c  push    rdi
0x18000bb8d  push    r12
0x18000bb8f  push    r13
0x18000bb91  push    r14
0x18000bb93  push    r15
0x18000bb95  sub     rsp, 28h
0x18000bb99  mov     [rcx+4], r8d
0x18000bb9d  xor     r13d, r13d
0x18000bba0  mov     eax, [rdx+8]
0x18000bba3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000bba7  mov     [rcx+8], eax
0x18000bbaa  mov     rdi, rcx
0x18000bbad  mov     [rcx+10h], r13
0x18000bbb1  mov     r12, rdx
0x18000bbb4  movzx   eax, word ptr [rdx+40h]
0x18000bbb8  mov     [rcx+18h], ax
0x18000bbbc  mov     al, [rdx]
0x18000bbbe  mov     [rcx+1Ah], al
0x18000bbc1  mov     [rcx+20h], r13
0x18000bbc5  mov     rax, [rdx+88h]
0x18000bbcc  mov     [rcx+28h], rax
0x18000bbd0  mov     rax, [rdx+90h]
0x18000bbd7  mov     [rcx+30h], rax
0x18000bbdb  mov     [rcx+38h], r13
0x18000bbdf  mov     rcx, [rdx+38h]
0x18000bbe3  lea     edx, [rbp+2]
0x18000bbe6  test    rcx, rcx
0x18000bbe9  jnz     short loc_18000BBF0
0x18000bbeb  mov     r8d, edx
0x18000bbee  jmp     short loc_18000BC00
0x18000bbf0  mov     rax, rbp
0x18000bbf3  inc     rax
0x18000bbf6  cmp     [rcx+rax], r13b
0x18000bbfa  jnz     short loc_18000BBF3
0x18000bbfc  lea     r8, [rax+1]; unsigned __int64
0x18000bc00  mov     rcx, [r12+80h]
0x18000bc08  test    rcx, rcx
0x18000bc0b  jz      short loc_18000BC1D
0x18000bc0d  mov     rax, rbp
0x18000bc10  inc     rax
0x18000bc13  cmp     [rcx+rax], r13b
0x18000bc17  jnz     short loc_18000BC10
0x18000bc19  lea     rdx, [rax+1]
0x18000bc1d  mov     rcx, [r12+18h]
0x18000bc22  test    rcx, rcx
0x18000bc25  jnz     short loc_18000BC2C
0x18000bc27  lea     eax, [rcx+2]
0x18000bc2a  jmp     short loc_18000BC41
0x18000bc2c  mov     rax, rbp
0x18000bc2f  inc     rax
0x18000bc32  cmp     [rcx+rax*2], r13w
0x18000bc37  jnz     short loc_18000BC2F
0x18000bc39  lea     rax, ds:2[rax*2]
0x18000bc41  lea     r14, [rdx+rax]
0x18000bc45  add     r14, r8
0x18000bc48  lea     rsi, [rdi+48h]
0x18000bc4c  cmp     [rdi+40h], r13
0x18000bc50  jz      short loc_18000BC57
0x18000bc52  cmp     [rsi], r14
0x18000bc55  jnb     short loc_18000BC8B
0x18000bc57  mov     rdx, r14; dwBytes
0x18000bc5a  mov     ecx, 8; dwFlags
0x18000bc5f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bc64  mov     r15, rax
0x18000bc67  test    rax, rax
0x18000bc6a  jz      short loc_18000BC8B
0x18000bc6c  mov     rbx, [rdi+40h]
0x18000bc70  call    cs:__imp_GetProcessHeap
0x18000bc76  mov     r8, rbx; lpMem
0x18000bc79  xor     edx, edx; dwFlags
0x18000bc7b  mov     rcx, rax; hHeap
0x18000bc7e  call    cs:__imp_HeapFree
0x18000bc84  mov     [rdi+40h], r15
0x18000bc88  mov     [rsi], r14
0x18000bc8b  mov     rbx, [rdi+40h]
0x18000bc8f  test    rbx, rbx
0x18000bc92  jz      loc_18000BD93
0x18000bc98  mov     rdx, [rsi]; DestinationSize
0x18000bc9b  lea     rsi, [rdx+rbx]
0x18000bc9f  cmp     rbx, rsi
0x18000bca2  jz      short loc_18000BCE3
0x18000bca4  mov     r8, [r12+38h]; Source
0x18000bca9  test    r8, r8
0x18000bcac  jz      short loc_18000BCE3
0x18000bcae  cmp     [r8], r13b
0x18000bcb1  jz      short loc_18000BCE3
0x18000bcb3  mov     rax, rbp
0x18000bcb6  inc     rax
0x18000bcb9  cmp     [r8+rax], r13b
0x18000bcbd  jnz     short loc_18000BCB6
0x18000bcbf  lea     r14, [rax+1]
0x18000bcc3  cmp     rdx, r14
0x18000bcc6  jnb     short loc_18000BCCE
0x18000bcc8  mov     [rdi+10h], r13
0x18000bccc  jmp     short loc_18000BCEC
0x18000bcce  mov     r9, r14; SourceSize
0x18000bcd1  mov     rcx, rbx; Destination
0x18000bcd4  call    cs:__imp_memcpy_s
0x18000bcda  mov     [rdi+10h], rbx
0x18000bcde  add     rbx, r14
0x18000bce1  jmp     short loc_18000BCE7
0x18000bce3  mov     [rdi+10h], r13
0x18000bce7  cmp     rbx, rsi
0x18000bcea  jz      short loc_18000BD34
0x18000bcec  mov     r8, [r12+80h]; Source
0x18000bcf4  test    r8, r8
0x18000bcf7  jz      short loc_18000BD34
0x18000bcf9  cmp     [r8], r13b
0x18000bcfc  jz      short loc_18000BD34
0x18000bcfe  mov     rax, rbp
0x18000bd01  inc     rax
0x18000bd04  cmp     [r8+rax], r13b
0x18000bd08  jnz     short loc_18000BD01
0x18000bd0a  mov     rdx, rsi
0x18000bd0d  lea     r14, [rax+1]
0x18000bd11  sub     rdx, rbx; DestinationSize
0x18000bd14  cmp     rdx, r14
0x18000bd17  jnb     short loc_18000BD1F
0x18000bd19  mov     [rdi+20h], r13
0x18000bd1d  jmp     short loc_18000BD3D
0x18000bd1f  mov     r9, r14; SourceSize
0x18000bd22  mov     rcx, rbx; Destination
0x18000bd25  call    cs:__imp_memcpy_s
0x18000bd2b  mov     [rdi+20h], rbx
0x18000bd2f  add     rbx, r14
0x18000bd32  jmp     short loc_18000BD38
0x18000bd34  mov     [rdi+20h], r13
0x18000bd38  cmp     rbx, rsi
0x18000bd3b  jz      short loc_18000BD7F
0x18000bd3d  mov     r8, [r12+18h]; Source
0x18000bd42  test    r8, r8
0x18000bd45  jz      short loc_18000BD7F
0x18000bd47  cmp     [r8], r13w
0x18000bd4b  jz      short loc_18000BD7F
0x18000bd4d  inc     rbp
0x18000bd50  cmp     [r8+rbp*2], r13w
0x18000bd55  jnz     short loc_18000BD4D
0x18000bd57  mov     rdx, rsi
0x18000bd5a  lea     r14, ds:2[rbp*2]
0x18000bd62  sub     rdx, rbx; DestinationSize
0x18000bd65  cmp     rdx, r14
0x18000bd68  jb      short loc_18000BD7F
0x18000bd6a  mov     r9, r14; SourceSize
0x18000bd6d  mov     rcx, rbx; Destination
0x18000bd70  call    cs:__imp_memcpy_s
0x18000bd76  mov     [rdi+38h], rbx
0x18000bd7a  add     rbx, r14
0x18000bd7d  jmp     short loc_18000BD83
0x18000bd7f  mov     [rdi+38h], r13
0x18000bd83  sub     rsi, rbx
0x18000bd86  xor     edx, edx; Val
0x18000bd88  mov     r8, rsi; Size
0x18000bd8b  mov     rcx, rbx; void *
0x18000bd8e  call    memset_0
0x18000bd93  add     rsp, 28h
0x18000bd97  pop     r15
0x18000bd99  pop     r14
0x18000bd9b  pop     r13
0x18000bd9d  pop     r12
0x18000bd9f  pop     rdi
0x18000bda0  pop     rsi
0x18000bda1  pop     rbp
0x18000bda2  pop     rbx
0x18000bda3  retn
```
