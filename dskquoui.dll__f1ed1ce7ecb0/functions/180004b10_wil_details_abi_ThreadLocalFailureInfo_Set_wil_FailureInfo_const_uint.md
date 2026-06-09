# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004b10`
- end: `0x180004d29`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003760`

## callees

- `0x1800022b4`
- `0x1800047a8`
- `0x180004b10`
- `0x180005b18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c06`

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
0x180004b10  push    rbx
0x180004b12  push    rbp
0x180004b13  push    rsi
0x180004b14  push    rdi
0x180004b15  push    r12
0x180004b17  push    r13
0x180004b19  push    r14
0x180004b1b  push    r15
0x180004b1d  sub     rsp, 28h
0x180004b21  mov     [rcx+4], r8d
0x180004b25  xor     r13d, r13d
0x180004b28  mov     eax, [rdx+8]
0x180004b2b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004b2f  mov     [rcx+8], eax
0x180004b32  mov     rdi, rcx
0x180004b35  mov     [rcx+10h], r13
0x180004b39  mov     r12, rdx
0x180004b3c  movzx   eax, word ptr [rdx+40h]
0x180004b40  mov     [rcx+18h], ax
0x180004b44  mov     al, [rdx]
0x180004b46  mov     [rcx+1Ah], al
0x180004b49  mov     [rcx+20h], r13
0x180004b4d  mov     rax, [rdx+88h]
0x180004b54  mov     [rcx+28h], rax
0x180004b58  mov     rax, [rdx+90h]
0x180004b5f  mov     [rcx+30h], rax
0x180004b63  mov     [rcx+38h], r13
0x180004b67  mov     rcx, [rdx+38h]
0x180004b6b  lea     edx, [rbp+2]
0x180004b6e  test    rcx, rcx
0x180004b71  jnz     short loc_180004B78
0x180004b73  mov     r8d, edx
0x180004b76  jmp     short loc_180004B88
0x180004b78  mov     rax, rbp
0x180004b7b  inc     rax
0x180004b7e  cmp     [rcx+rax], r13b
0x180004b82  jnz     short loc_180004B7B
0x180004b84  lea     r8, [rax+1]; unsigned __int64
0x180004b88  mov     rcx, [r12+80h]
0x180004b90  test    rcx, rcx
0x180004b93  jz      short loc_180004BA5
0x180004b95  mov     rax, rbp
0x180004b98  inc     rax
0x180004b9b  cmp     [rcx+rax], r13b
0x180004b9f  jnz     short loc_180004B98
0x180004ba1  lea     rdx, [rax+1]
0x180004ba5  mov     rcx, [r12+18h]
0x180004baa  test    rcx, rcx
0x180004bad  jnz     short loc_180004BB4
0x180004baf  lea     eax, [rcx+2]
0x180004bb2  jmp     short loc_180004BC9
0x180004bb4  mov     rax, rbp
0x180004bb7  inc     rax
0x180004bba  cmp     [rcx+rax*2], r13w
0x180004bbf  jnz     short loc_180004BB7
0x180004bc1  lea     rax, ds:2[rax*2]
0x180004bc9  lea     r14, [rdx+rax]
0x180004bcd  add     r14, r8
0x180004bd0  lea     rsi, [rdi+48h]
0x180004bd4  cmp     [rdi+40h], r13
0x180004bd8  jz      short loc_180004BDF
0x180004bda  cmp     [rsi], r14
0x180004bdd  jnb     short loc_180004C13
0x180004bdf  mov     rdx, r14; dwBytes
0x180004be2  mov     ecx, 8; dwFlags
0x180004be7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004bec  mov     r15, rax
0x180004bef  test    rax, rax
0x180004bf2  jz      short loc_180004C13
0x180004bf4  mov     rbx, [rdi+40h]
0x180004bf8  call    cs:__imp_GetProcessHeap
0x180004bfe  mov     r8, rbx; lpMem
0x180004c01  xor     edx, edx; dwFlags
0x180004c03  mov     rcx, rax; hHeap
0x180004c06  call    cs:__imp_HeapFree
0x180004c0c  mov     [rdi+40h], r15
0x180004c10  mov     [rsi], r14
0x180004c13  mov     rbx, [rdi+40h]
0x180004c17  test    rbx, rbx
0x180004c1a  jz      loc_180004D18
0x180004c20  mov     rdx, [rsi]; DestinationSize
0x180004c23  lea     rsi, [rdx+rbx]
0x180004c27  cmp     rbx, rsi
0x180004c2a  jz      short loc_180004C6A
0x180004c2c  mov     r8, [r12+38h]; Source
0x180004c31  test    r8, r8
0x180004c34  jz      short loc_180004C6A
0x180004c36  cmp     [r8], r13b
0x180004c39  jz      short loc_180004C6A
0x180004c3b  mov     rax, rbp
0x180004c3e  inc     rax
0x180004c41  cmp     [r8+rax], r13b
0x180004c45  jnz     short loc_180004C3E
0x180004c47  lea     r14, [rax+1]
0x180004c4b  cmp     rdx, r14
0x180004c4e  jnb     short loc_180004C56
0x180004c50  mov     [rdi+10h], r13
0x180004c54  jmp     short loc_180004C73
0x180004c56  mov     r9, r14; SourceSize
0x180004c59  mov     rcx, rbx; Destination
0x180004c5c  call    memcpy_s
0x180004c61  mov     [rdi+10h], rbx
0x180004c65  add     rbx, r14
0x180004c68  jmp     short loc_180004C6E
0x180004c6a  mov     [rdi+10h], r13
0x180004c6e  cmp     rbx, rsi
0x180004c71  jz      short loc_180004CBA
0x180004c73  mov     r8, [r12+80h]; Source
0x180004c7b  test    r8, r8
0x180004c7e  jz      short loc_180004CBA
0x180004c80  cmp     [r8], r13b
0x180004c83  jz      short loc_180004CBA
0x180004c85  mov     rax, rbp
0x180004c88  inc     rax
0x180004c8b  cmp     [r8+rax], r13b
0x180004c8f  jnz     short loc_180004C88
0x180004c91  mov     rdx, rsi
0x180004c94  lea     r14, [rax+1]
0x180004c98  sub     rdx, rbx; DestinationSize
0x180004c9b  cmp     rdx, r14
0x180004c9e  jnb     short loc_180004CA6
0x180004ca0  mov     [rdi+20h], r13
0x180004ca4  jmp     short loc_180004CC3
0x180004ca6  mov     r9, r14; SourceSize
0x180004ca9  mov     rcx, rbx; Destination
0x180004cac  call    memcpy_s
0x180004cb1  mov     [rdi+20h], rbx
0x180004cb5  add     rbx, r14
0x180004cb8  jmp     short loc_180004CBE
0x180004cba  mov     [rdi+20h], r13
0x180004cbe  cmp     rbx, rsi
0x180004cc1  jz      short loc_180004D04
0x180004cc3  mov     r8, [r12+18h]; Source
0x180004cc8  test    r8, r8
0x180004ccb  jz      short loc_180004D04
0x180004ccd  cmp     [r8], r13w
0x180004cd1  jz      short loc_180004D04
0x180004cd3  inc     rbp
0x180004cd6  cmp     [r8+rbp*2], r13w
0x180004cdb  jnz     short loc_180004CD3
0x180004cdd  mov     rdx, rsi
0x180004ce0  lea     r14, ds:2[rbp*2]
0x180004ce8  sub     rdx, rbx; DestinationSize
0x180004ceb  cmp     rdx, r14
0x180004cee  jb      short loc_180004D04
0x180004cf0  mov     r9, r14; SourceSize
0x180004cf3  mov     rcx, rbx; Destination
0x180004cf6  call    memcpy_s
0x180004cfb  mov     [rdi+38h], rbx
0x180004cff  add     rbx, r14
0x180004d02  jmp     short loc_180004D08
0x180004d04  mov     [rdi+38h], r13
0x180004d08  sub     rsi, rbx
0x180004d0b  xor     edx, edx; Val
0x180004d0d  mov     r8, rsi; Size
0x180004d10  mov     rcx, rbx; void *
0x180004d13  call    memset_0
0x180004d18  add     rsp, 28h
0x180004d1c  pop     r15
0x180004d1e  pop     r14
0x180004d20  pop     r13
0x180004d22  pop     r12
0x180004d24  pop     rdi
0x180004d25  pop     rsi
0x180004d26  pop     rbp
0x180004d27  pop     rbx
0x180004d28  retn
```
