# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000ca04`
- end: `0x14000cc1d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008e70`

## callees

- `0x140002d4c`
- `0x14000a910`
- `0x14000ca04`
- `0x140010f78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000caec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000caec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cafa`

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
0x14000ca04  push    rbx
0x14000ca06  push    rbp
0x14000ca07  push    rsi
0x14000ca08  push    rdi
0x14000ca09  push    r12
0x14000ca0b  push    r13
0x14000ca0d  push    r14
0x14000ca0f  push    r15
0x14000ca11  sub     rsp, 28h
0x14000ca15  mov     [rcx+4], r8d
0x14000ca19  xor     r13d, r13d
0x14000ca1c  mov     eax, [rdx+8]
0x14000ca1f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000ca23  mov     [rcx+8], eax
0x14000ca26  mov     rdi, rcx
0x14000ca29  mov     [rcx+10h], r13
0x14000ca2d  mov     r12, rdx
0x14000ca30  movzx   eax, word ptr [rdx+40h]
0x14000ca34  mov     [rcx+18h], ax
0x14000ca38  mov     al, [rdx]
0x14000ca3a  mov     [rcx+1Ah], al
0x14000ca3d  mov     [rcx+20h], r13
0x14000ca41  mov     rax, [rdx+88h]
0x14000ca48  mov     [rcx+28h], rax
0x14000ca4c  mov     rax, [rdx+90h]
0x14000ca53  mov     [rcx+30h], rax
0x14000ca57  mov     [rcx+38h], r13
0x14000ca5b  mov     rcx, [rdx+38h]
0x14000ca5f  lea     edx, [rbp+2]
0x14000ca62  test    rcx, rcx
0x14000ca65  jnz     short loc_14000CA6C
0x14000ca67  mov     r8d, edx
0x14000ca6a  jmp     short loc_14000CA7C
0x14000ca6c  mov     rax, rbp
0x14000ca6f  inc     rax
0x14000ca72  cmp     [rcx+rax], r13b
0x14000ca76  jnz     short loc_14000CA6F
0x14000ca78  lea     r8, [rax+1]; unsigned __int64
0x14000ca7c  mov     rcx, [r12+80h]
0x14000ca84  test    rcx, rcx
0x14000ca87  jz      short loc_14000CA99
0x14000ca89  mov     rax, rbp
0x14000ca8c  inc     rax
0x14000ca8f  cmp     [rcx+rax], r13b
0x14000ca93  jnz     short loc_14000CA8C
0x14000ca95  lea     rdx, [rax+1]
0x14000ca99  mov     rcx, [r12+18h]
0x14000ca9e  test    rcx, rcx
0x14000caa1  jnz     short loc_14000CAA8
0x14000caa3  lea     eax, [rcx+2]
0x14000caa6  jmp     short loc_14000CABD
0x14000caa8  mov     rax, rbp
0x14000caab  inc     rax
0x14000caae  cmp     [rcx+rax*2], r13w
0x14000cab3  jnz     short loc_14000CAAB
0x14000cab5  lea     rax, ds:2[rax*2]
0x14000cabd  lea     r14, [rdx+rax]
0x14000cac1  add     r14, r8
0x14000cac4  lea     rsi, [rdi+48h]
0x14000cac8  cmp     [rdi+40h], r13
0x14000cacc  jz      short loc_14000CAD3
0x14000cace  cmp     [rsi], r14
0x14000cad1  jnb     short loc_14000CB07
0x14000cad3  mov     rdx, r14; dwBytes
0x14000cad6  mov     ecx, 8; dwFlags
0x14000cadb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000cae0  mov     r15, rax
0x14000cae3  test    rax, rax
0x14000cae6  jz      short loc_14000CB07
0x14000cae8  mov     rbx, [rdi+40h]
0x14000caec  call    cs:__imp_GetProcessHeap
0x14000caf2  mov     r8, rbx; lpMem
0x14000caf5  xor     edx, edx; dwFlags
0x14000caf7  mov     rcx, rax; hHeap
0x14000cafa  call    cs:__imp_HeapFree
0x14000cb00  mov     [rdi+40h], r15
0x14000cb04  mov     [rsi], r14
0x14000cb07  mov     rbx, [rdi+40h]
0x14000cb0b  test    rbx, rbx
0x14000cb0e  jz      loc_14000CC0C
0x14000cb14  mov     rdx, [rsi]; DestinationSize
0x14000cb17  lea     rsi, [rdx+rbx]
0x14000cb1b  cmp     rbx, rsi
0x14000cb1e  jz      short loc_14000CB5E
0x14000cb20  mov     r8, [r12+38h]; Source
0x14000cb25  test    r8, r8
0x14000cb28  jz      short loc_14000CB5E
0x14000cb2a  cmp     [r8], r13b
0x14000cb2d  jz      short loc_14000CB5E
0x14000cb2f  mov     rax, rbp
0x14000cb32  inc     rax
0x14000cb35  cmp     [r8+rax], r13b
0x14000cb39  jnz     short loc_14000CB32
0x14000cb3b  lea     r14, [rax+1]
0x14000cb3f  cmp     rdx, r14
0x14000cb42  jnb     short loc_14000CB4A
0x14000cb44  mov     [rdi+10h], r13
0x14000cb48  jmp     short loc_14000CB67
0x14000cb4a  mov     r9, r14; SourceSize
0x14000cb4d  mov     rcx, rbx; Destination
0x14000cb50  call    memcpy_s
0x14000cb55  mov     [rdi+10h], rbx
0x14000cb59  add     rbx, r14
0x14000cb5c  jmp     short loc_14000CB62
0x14000cb5e  mov     [rdi+10h], r13
0x14000cb62  cmp     rbx, rsi
0x14000cb65  jz      short loc_14000CBAE
0x14000cb67  mov     r8, [r12+80h]; Source
0x14000cb6f  test    r8, r8
0x14000cb72  jz      short loc_14000CBAE
0x14000cb74  cmp     [r8], r13b
0x14000cb77  jz      short loc_14000CBAE
0x14000cb79  mov     rax, rbp
0x14000cb7c  inc     rax
0x14000cb7f  cmp     [r8+rax], r13b
0x14000cb83  jnz     short loc_14000CB7C
0x14000cb85  mov     rdx, rsi
0x14000cb88  lea     r14, [rax+1]
0x14000cb8c  sub     rdx, rbx; DestinationSize
0x14000cb8f  cmp     rdx, r14
0x14000cb92  jnb     short loc_14000CB9A
0x14000cb94  mov     [rdi+20h], r13
0x14000cb98  jmp     short loc_14000CBB7
0x14000cb9a  mov     r9, r14; SourceSize
0x14000cb9d  mov     rcx, rbx; Destination
0x14000cba0  call    memcpy_s
0x14000cba5  mov     [rdi+20h], rbx
0x14000cba9  add     rbx, r14
0x14000cbac  jmp     short loc_14000CBB2
0x14000cbae  mov     [rdi+20h], r13
0x14000cbb2  cmp     rbx, rsi
0x14000cbb5  jz      short loc_14000CBF8
0x14000cbb7  mov     r8, [r12+18h]; Source
0x14000cbbc  test    r8, r8
0x14000cbbf  jz      short loc_14000CBF8
0x14000cbc1  cmp     [r8], r13w
0x14000cbc5  jz      short loc_14000CBF8
0x14000cbc7  inc     rbp
0x14000cbca  cmp     [r8+rbp*2], r13w
0x14000cbcf  jnz     short loc_14000CBC7
0x14000cbd1  mov     rdx, rsi
0x14000cbd4  lea     r14, ds:2[rbp*2]
0x14000cbdc  sub     rdx, rbx; DestinationSize
0x14000cbdf  cmp     rdx, r14
0x14000cbe2  jb      short loc_14000CBF8
0x14000cbe4  mov     r9, r14; SourceSize
0x14000cbe7  mov     rcx, rbx; Destination
0x14000cbea  call    memcpy_s
0x14000cbef  mov     [rdi+38h], rbx
0x14000cbf3  add     rbx, r14
0x14000cbf6  jmp     short loc_14000CBFC
0x14000cbf8  mov     [rdi+38h], r13
0x14000cbfc  sub     rsi, rbx
0x14000cbff  xor     edx, edx; Val
0x14000cc01  mov     r8, rsi; Size
0x14000cc04  mov     rcx, rbx; void *
0x14000cc07  call    memset_0
0x14000cc0c  add     rsp, 28h
0x14000cc10  pop     r15
0x14000cc12  pop     r14
0x14000cc14  pop     r13
0x14000cc16  pop     r12
0x14000cc18  pop     rdi
0x14000cc19  pop     rsi
0x14000cc1a  pop     rbp
0x14000cc1b  pop     rbx
0x14000cc1c  retn
```
