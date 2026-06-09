# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140004a04`
- end: `0x140004c1d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003530`

## callees

- `0x140001e56`
- `0x140004624`
- `0x140004a04`
- `0x140005b68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004aec`

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
0x140004a04  push    rbx
0x140004a06  push    rbp
0x140004a07  push    rsi
0x140004a08  push    rdi
0x140004a09  push    r12
0x140004a0b  push    r13
0x140004a0d  push    r14
0x140004a0f  push    r15
0x140004a11  sub     rsp, 28h
0x140004a15  mov     [rcx+4], r8d
0x140004a19  xor     r13d, r13d
0x140004a1c  mov     eax, [rdx+8]
0x140004a1f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140004a23  mov     [rcx+8], eax
0x140004a26  mov     rdi, rcx
0x140004a29  mov     [rcx+10h], r13
0x140004a2d  mov     r12, rdx
0x140004a30  movzx   eax, word ptr [rdx+40h]
0x140004a34  mov     [rcx+18h], ax
0x140004a38  mov     al, [rdx]
0x140004a3a  mov     [rcx+1Ah], al
0x140004a3d  mov     [rcx+20h], r13
0x140004a41  mov     rax, [rdx+88h]
0x140004a48  mov     [rcx+28h], rax
0x140004a4c  mov     rax, [rdx+90h]
0x140004a53  mov     [rcx+30h], rax
0x140004a57  mov     [rcx+38h], r13
0x140004a5b  mov     rcx, [rdx+38h]
0x140004a5f  lea     edx, [rbp+2]
0x140004a62  test    rcx, rcx
0x140004a65  jnz     short loc_140004A6C
0x140004a67  mov     r8d, edx
0x140004a6a  jmp     short loc_140004A7C
0x140004a6c  mov     rax, rbp
0x140004a6f  inc     rax
0x140004a72  cmp     [rcx+rax], r13b
0x140004a76  jnz     short loc_140004A6F
0x140004a78  lea     r8, [rax+1]; unsigned __int64
0x140004a7c  mov     rcx, [r12+80h]
0x140004a84  test    rcx, rcx
0x140004a87  jz      short loc_140004A99
0x140004a89  mov     rax, rbp
0x140004a8c  inc     rax
0x140004a8f  cmp     [rcx+rax], r13b
0x140004a93  jnz     short loc_140004A8C
0x140004a95  lea     rdx, [rax+1]
0x140004a99  mov     rcx, [r12+18h]
0x140004a9e  test    rcx, rcx
0x140004aa1  jnz     short loc_140004AA8
0x140004aa3  lea     eax, [rcx+2]
0x140004aa6  jmp     short loc_140004ABD
0x140004aa8  mov     rax, rbp
0x140004aab  inc     rax
0x140004aae  cmp     [rcx+rax*2], r13w
0x140004ab3  jnz     short loc_140004AAB
0x140004ab5  lea     rax, ds:2[rax*2]
0x140004abd  lea     r14, [rdx+rax]
0x140004ac1  add     r14, r8
0x140004ac4  lea     rsi, [rdi+48h]
0x140004ac8  cmp     [rdi+40h], r13
0x140004acc  jz      short loc_140004AD3
0x140004ace  cmp     [rsi], r14
0x140004ad1  jnb     short loc_140004B07
0x140004ad3  mov     rdx, r14; dwBytes
0x140004ad6  mov     ecx, 8; dwFlags
0x140004adb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004ae0  mov     r15, rax
0x140004ae3  test    rax, rax
0x140004ae6  jz      short loc_140004B07
0x140004ae8  mov     rbx, [rdi+40h]
0x140004aec  call    cs:__imp_GetProcessHeap
0x140004af2  mov     r8, rbx; lpMem
0x140004af5  xor     edx, edx; dwFlags
0x140004af7  mov     rcx, rax; hHeap
0x140004afa  call    cs:__imp_HeapFree
0x140004b00  mov     [rdi+40h], r15
0x140004b04  mov     [rsi], r14
0x140004b07  mov     rbx, [rdi+40h]
0x140004b0b  test    rbx, rbx
0x140004b0e  jz      loc_140004C0C
0x140004b14  mov     rdx, [rsi]; DestinationSize
0x140004b17  lea     rsi, [rdx+rbx]
0x140004b1b  cmp     rbx, rsi
0x140004b1e  jz      short loc_140004B5E
0x140004b20  mov     r8, [r12+38h]; Source
0x140004b25  test    r8, r8
0x140004b28  jz      short loc_140004B5E
0x140004b2a  cmp     [r8], r13b
0x140004b2d  jz      short loc_140004B5E
0x140004b2f  mov     rax, rbp
0x140004b32  inc     rax
0x140004b35  cmp     [r8+rax], r13b
0x140004b39  jnz     short loc_140004B32
0x140004b3b  lea     r14, [rax+1]
0x140004b3f  cmp     rdx, r14
0x140004b42  jnb     short loc_140004B4A
0x140004b44  mov     [rdi+10h], r13
0x140004b48  jmp     short loc_140004B67
0x140004b4a  mov     r9, r14; SourceSize
0x140004b4d  mov     rcx, rbx; Destination
0x140004b50  call    memcpy_s
0x140004b55  mov     [rdi+10h], rbx
0x140004b59  add     rbx, r14
0x140004b5c  jmp     short loc_140004B62
0x140004b5e  mov     [rdi+10h], r13
0x140004b62  cmp     rbx, rsi
0x140004b65  jz      short loc_140004BAE
0x140004b67  mov     r8, [r12+80h]; Source
0x140004b6f  test    r8, r8
0x140004b72  jz      short loc_140004BAE
0x140004b74  cmp     [r8], r13b
0x140004b77  jz      short loc_140004BAE
0x140004b79  mov     rax, rbp
0x140004b7c  inc     rax
0x140004b7f  cmp     [r8+rax], r13b
0x140004b83  jnz     short loc_140004B7C
0x140004b85  mov     rdx, rsi
0x140004b88  lea     r14, [rax+1]
0x140004b8c  sub     rdx, rbx; DestinationSize
0x140004b8f  cmp     rdx, r14
0x140004b92  jnb     short loc_140004B9A
0x140004b94  mov     [rdi+20h], r13
0x140004b98  jmp     short loc_140004BB7
0x140004b9a  mov     r9, r14; SourceSize
0x140004b9d  mov     rcx, rbx; Destination
0x140004ba0  call    memcpy_s
0x140004ba5  mov     [rdi+20h], rbx
0x140004ba9  add     rbx, r14
0x140004bac  jmp     short loc_140004BB2
0x140004bae  mov     [rdi+20h], r13
0x140004bb2  cmp     rbx, rsi
0x140004bb5  jz      short loc_140004BF8
0x140004bb7  mov     r8, [r12+18h]; Source
0x140004bbc  test    r8, r8
0x140004bbf  jz      short loc_140004BF8
0x140004bc1  cmp     [r8], r13w
0x140004bc5  jz      short loc_140004BF8
0x140004bc7  inc     rbp
0x140004bca  cmp     [r8+rbp*2], r13w
0x140004bcf  jnz     short loc_140004BC7
0x140004bd1  mov     rdx, rsi
0x140004bd4  lea     r14, ds:2[rbp*2]
0x140004bdc  sub     rdx, rbx; DestinationSize
0x140004bdf  cmp     rdx, r14
0x140004be2  jb      short loc_140004BF8
0x140004be4  mov     r9, r14; SourceSize
0x140004be7  mov     rcx, rbx; Destination
0x140004bea  call    memcpy_s
0x140004bef  mov     [rdi+38h], rbx
0x140004bf3  add     rbx, r14
0x140004bf6  jmp     short loc_140004BFC
0x140004bf8  mov     [rdi+38h], r13
0x140004bfc  sub     rsi, rbx
0x140004bff  xor     edx, edx; Val
0x140004c01  mov     r8, rsi; Size
0x140004c04  mov     rcx, rbx; void *
0x140004c07  call    memset_0
0x140004c0c  add     rsp, 28h
0x140004c10  pop     r15
0x140004c12  pop     r14
0x140004c14  pop     r13
0x140004c16  pop     r12
0x140004c18  pop     rdi
0x140004c19  pop     rsi
0x140004c1a  pop     rbp
0x140004c1b  pop     rbx
0x140004c1c  retn
```
