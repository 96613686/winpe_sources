# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006960`
- end: `0x180006b79`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800040c0`

## callees

- `0x1800020c4`
- `0x18000529c`
- `0x180006960`
- `0x180007d88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a48`

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
0x180006960  push    rbx
0x180006962  push    rbp
0x180006963  push    rsi
0x180006964  push    rdi
0x180006965  push    r12
0x180006967  push    r13
0x180006969  push    r14
0x18000696b  push    r15
0x18000696d  sub     rsp, 28h
0x180006971  mov     [rcx+4], r8d
0x180006975  xor     r13d, r13d
0x180006978  mov     eax, [rdx+8]
0x18000697b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000697f  mov     [rcx+8], eax
0x180006982  mov     rdi, rcx
0x180006985  mov     [rcx+10h], r13
0x180006989  mov     r12, rdx
0x18000698c  movzx   eax, word ptr [rdx+40h]
0x180006990  mov     [rcx+18h], ax
0x180006994  mov     al, [rdx]
0x180006996  mov     [rcx+1Ah], al
0x180006999  mov     [rcx+20h], r13
0x18000699d  mov     rax, [rdx+88h]
0x1800069a4  mov     [rcx+28h], rax
0x1800069a8  mov     rax, [rdx+90h]
0x1800069af  mov     [rcx+30h], rax
0x1800069b3  mov     [rcx+38h], r13
0x1800069b7  mov     rcx, [rdx+38h]
0x1800069bb  lea     edx, [rbp+2]
0x1800069be  test    rcx, rcx
0x1800069c1  jnz     short loc_1800069C8
0x1800069c3  mov     r8d, edx
0x1800069c6  jmp     short loc_1800069D8
0x1800069c8  mov     rax, rbp
0x1800069cb  inc     rax
0x1800069ce  cmp     [rcx+rax], r13b
0x1800069d2  jnz     short loc_1800069CB
0x1800069d4  lea     r8, [rax+1]; unsigned __int64
0x1800069d8  mov     rcx, [r12+80h]
0x1800069e0  test    rcx, rcx
0x1800069e3  jz      short loc_1800069F5
0x1800069e5  mov     rax, rbp
0x1800069e8  inc     rax
0x1800069eb  cmp     [rcx+rax], r13b
0x1800069ef  jnz     short loc_1800069E8
0x1800069f1  lea     rdx, [rax+1]
0x1800069f5  mov     rcx, [r12+18h]
0x1800069fa  test    rcx, rcx
0x1800069fd  jnz     short loc_180006A04
0x1800069ff  lea     eax, [rcx+2]
0x180006a02  jmp     short loc_180006A19
0x180006a04  mov     rax, rbp
0x180006a07  inc     rax
0x180006a0a  cmp     [rcx+rax*2], r13w
0x180006a0f  jnz     short loc_180006A07
0x180006a11  lea     rax, ds:2[rax*2]
0x180006a19  lea     r14, [rdx+rax]
0x180006a1d  add     r14, r8
0x180006a20  lea     rsi, [rdi+48h]
0x180006a24  cmp     [rdi+40h], r13
0x180006a28  jz      short loc_180006A2F
0x180006a2a  cmp     [rsi], r14
0x180006a2d  jnb     short loc_180006A63
0x180006a2f  mov     rdx, r14; dwBytes
0x180006a32  mov     ecx, 8; dwFlags
0x180006a37  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a3c  mov     r15, rax
0x180006a3f  test    rax, rax
0x180006a42  jz      short loc_180006A63
0x180006a44  mov     rbx, [rdi+40h]
0x180006a48  call    cs:__imp_GetProcessHeap
0x180006a4e  mov     r8, rbx; lpMem
0x180006a51  xor     edx, edx; dwFlags
0x180006a53  mov     rcx, rax; hHeap
0x180006a56  call    cs:__imp_HeapFree
0x180006a5c  mov     [rdi+40h], r15
0x180006a60  mov     [rsi], r14
0x180006a63  mov     rbx, [rdi+40h]
0x180006a67  test    rbx, rbx
0x180006a6a  jz      loc_180006B68
0x180006a70  mov     rdx, [rsi]; DestinationSize
0x180006a73  lea     rsi, [rdx+rbx]
0x180006a77  cmp     rbx, rsi
0x180006a7a  jz      short loc_180006ABA
0x180006a7c  mov     r8, [r12+38h]; Source
0x180006a81  test    r8, r8
0x180006a84  jz      short loc_180006ABA
0x180006a86  cmp     [r8], r13b
0x180006a89  jz      short loc_180006ABA
0x180006a8b  mov     rax, rbp
0x180006a8e  inc     rax
0x180006a91  cmp     [r8+rax], r13b
0x180006a95  jnz     short loc_180006A8E
0x180006a97  lea     r14, [rax+1]
0x180006a9b  cmp     rdx, r14
0x180006a9e  jnb     short loc_180006AA6
0x180006aa0  mov     [rdi+10h], r13
0x180006aa4  jmp     short loc_180006AC3
0x180006aa6  mov     r9, r14; SourceSize
0x180006aa9  mov     rcx, rbx; Destination
0x180006aac  call    memcpy_s
0x180006ab1  mov     [rdi+10h], rbx
0x180006ab5  add     rbx, r14
0x180006ab8  jmp     short loc_180006ABE
0x180006aba  mov     [rdi+10h], r13
0x180006abe  cmp     rbx, rsi
0x180006ac1  jz      short loc_180006B0A
0x180006ac3  mov     r8, [r12+80h]; Source
0x180006acb  test    r8, r8
0x180006ace  jz      short loc_180006B0A
0x180006ad0  cmp     [r8], r13b
0x180006ad3  jz      short loc_180006B0A
0x180006ad5  mov     rax, rbp
0x180006ad8  inc     rax
0x180006adb  cmp     [r8+rax], r13b
0x180006adf  jnz     short loc_180006AD8
0x180006ae1  mov     rdx, rsi
0x180006ae4  lea     r14, [rax+1]
0x180006ae8  sub     rdx, rbx; DestinationSize
0x180006aeb  cmp     rdx, r14
0x180006aee  jnb     short loc_180006AF6
0x180006af0  mov     [rdi+20h], r13
0x180006af4  jmp     short loc_180006B13
0x180006af6  mov     r9, r14; SourceSize
0x180006af9  mov     rcx, rbx; Destination
0x180006afc  call    memcpy_s
0x180006b01  mov     [rdi+20h], rbx
0x180006b05  add     rbx, r14
0x180006b08  jmp     short loc_180006B0E
0x180006b0a  mov     [rdi+20h], r13
0x180006b0e  cmp     rbx, rsi
0x180006b11  jz      short loc_180006B54
0x180006b13  mov     r8, [r12+18h]; Source
0x180006b18  test    r8, r8
0x180006b1b  jz      short loc_180006B54
0x180006b1d  cmp     [r8], r13w
0x180006b21  jz      short loc_180006B54
0x180006b23  inc     rbp
0x180006b26  cmp     [r8+rbp*2], r13w
0x180006b2b  jnz     short loc_180006B23
0x180006b2d  mov     rdx, rsi
0x180006b30  lea     r14, ds:2[rbp*2]
0x180006b38  sub     rdx, rbx; DestinationSize
0x180006b3b  cmp     rdx, r14
0x180006b3e  jb      short loc_180006B54
0x180006b40  mov     r9, r14; SourceSize
0x180006b43  mov     rcx, rbx; Destination
0x180006b46  call    memcpy_s
0x180006b4b  mov     [rdi+38h], rbx
0x180006b4f  add     rbx, r14
0x180006b52  jmp     short loc_180006B58
0x180006b54  mov     [rdi+38h], r13
0x180006b58  sub     rsi, rbx
0x180006b5b  xor     edx, edx; Val
0x180006b5d  mov     r8, rsi; Size
0x180006b60  mov     rcx, rbx; void *
0x180006b63  call    memset_0
0x180006b68  add     rsp, 28h
0x180006b6c  pop     r15
0x180006b6e  pop     r14
0x180006b70  pop     r13
0x180006b72  pop     r12
0x180006b74  pop     rdi
0x180006b75  pop     rsi
0x180006b76  pop     rbp
0x180006b77  pop     rbx
0x180006b78  retn
```
