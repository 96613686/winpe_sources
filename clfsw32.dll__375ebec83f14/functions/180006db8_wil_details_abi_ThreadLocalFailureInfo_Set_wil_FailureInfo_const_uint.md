# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006db8`
- end: `0x180006ff3`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `571`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046d0`

## callees

- `0x180005910`
- `0x180006db8`
- `0x180014dce`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006f10`
- `msvcrt!memcpy_s` at `0x180006f67`
- `msvcrt!memcpy_s` at `0x180006fb8`
- `msvcrt!memcpy_s` at `0x180006f10`
- `msvcrt!memcpy_s` at `0x180006f67`
- `msvcrt!memcpy_s` at `0x180006fb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006eb4`

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
0x180006db8  push    rbx
0x180006dba  push    rbp
0x180006dbb  push    rsi
0x180006dbc  push    rdi
0x180006dbd  push    r12
0x180006dbf  push    r13
0x180006dc1  push    r14
0x180006dc3  push    r15
0x180006dc5  sub     rsp, 28h
0x180006dc9  mov     [rcx+4], r8d
0x180006dcd  xor     r13d, r13d
0x180006dd0  mov     eax, [rdx+8]
0x180006dd3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006dd7  mov     [rcx+8], eax
0x180006dda  mov     rdi, rcx
0x180006ddd  mov     [rcx+10h], r13
0x180006de1  mov     r12, rdx
0x180006de4  movzx   eax, word ptr [rdx+40h]
0x180006de8  mov     [rcx+18h], ax
0x180006dec  mov     al, [rdx]
0x180006dee  mov     [rcx+1Ah], al
0x180006df1  mov     [rcx+20h], r13
0x180006df5  mov     rax, [rdx+88h]
0x180006dfc  mov     [rcx+28h], rax
0x180006e00  mov     rax, [rdx+90h]
0x180006e07  mov     [rcx+30h], rax
0x180006e0b  mov     [rcx+38h], r13
0x180006e0f  mov     rcx, [rdx+38h]
0x180006e13  lea     edx, [rbp+2]
0x180006e16  test    rcx, rcx
0x180006e19  jnz     short loc_180006E20
0x180006e1b  mov     r8d, edx
0x180006e1e  jmp     short loc_180006E30
0x180006e20  mov     rax, rbp
0x180006e23  inc     rax
0x180006e26  cmp     [rcx+rax], r13b
0x180006e2a  jnz     short loc_180006E23
0x180006e2c  lea     r8, [rax+1]; unsigned __int64
0x180006e30  mov     rcx, [r12+80h]
0x180006e38  test    rcx, rcx
0x180006e3b  jz      short loc_180006E4D
0x180006e3d  mov     rax, rbp
0x180006e40  inc     rax
0x180006e43  cmp     [rcx+rax], r13b
0x180006e47  jnz     short loc_180006E40
0x180006e49  lea     rdx, [rax+1]
0x180006e4d  mov     rcx, [r12+18h]
0x180006e52  test    rcx, rcx
0x180006e55  jnz     short loc_180006E5C
0x180006e57  lea     eax, [rcx+2]
0x180006e5a  jmp     short loc_180006E71
0x180006e5c  mov     rax, rbp
0x180006e5f  inc     rax
0x180006e62  cmp     [rcx+rax*2], r13w
0x180006e67  jnz     short loc_180006E5F
0x180006e69  lea     rax, ds:2[rax*2]
0x180006e71  lea     r14, [rdx+rax]
0x180006e75  add     r14, r8
0x180006e78  lea     rsi, [rdi+48h]
0x180006e7c  cmp     [rdi+40h], r13
0x180006e80  jz      short loc_180006E87
0x180006e82  cmp     [rsi], r14
0x180006e85  jnb     short loc_180006EC7
0x180006e87  mov     rdx, r14; dwBytes
0x180006e8a  mov     ecx, 8; dwFlags
0x180006e8f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006e94  mov     r15, rax
0x180006e97  test    rax, rax
0x180006e9a  jz      short loc_180006EC7
0x180006e9c  mov     rbx, [rdi+40h]
0x180006ea0  call    cs:__imp_GetProcessHeap
0x180006ea7  nop     dword ptr [rax+rax+00h]
0x180006eac  mov     r8, rbx; lpMem
0x180006eaf  xor     edx, edx; dwFlags
0x180006eb1  mov     rcx, rax; hHeap
0x180006eb4  call    cs:__imp_HeapFree
0x180006ebb  nop     dword ptr [rax+rax+00h]
0x180006ec0  mov     [rdi+40h], r15
0x180006ec4  mov     [rsi], r14
0x180006ec7  mov     rbx, [rdi+40h]
0x180006ecb  test    rbx, rbx
0x180006ece  jz      loc_180006FE1
0x180006ed4  mov     rdx, [rsi]; DestinationSize
0x180006ed7  lea     rsi, [rdx+rbx]
0x180006edb  cmp     rbx, rsi
0x180006ede  jz      short loc_180006F25
0x180006ee0  mov     r8, [r12+38h]; Source
0x180006ee5  test    r8, r8
0x180006ee8  jz      short loc_180006F25
0x180006eea  cmp     [r8], r13b
0x180006eed  jz      short loc_180006F25
0x180006eef  mov     rax, rbp
0x180006ef2  inc     rax
0x180006ef5  cmp     [r8+rax], r13b
0x180006ef9  jnz     short loc_180006EF2
0x180006efb  lea     r14, [rax+1]
0x180006eff  cmp     rdx, r14
0x180006f02  jnb     short loc_180006F0A
0x180006f04  mov     [rdi+10h], r13
0x180006f08  jmp     short loc_180006F2E
0x180006f0a  mov     r9, r14; SourceSize
0x180006f0d  mov     rcx, rbx; Destination
0x180006f10  call    cs:__imp_memcpy_s
0x180006f17  nop     dword ptr [rax+rax+00h]
0x180006f1c  mov     [rdi+10h], rbx
0x180006f20  add     rbx, r14
0x180006f23  jmp     short loc_180006F29
0x180006f25  mov     [rdi+10h], r13
0x180006f29  cmp     rbx, rsi
0x180006f2c  jz      short loc_180006F7C
0x180006f2e  mov     r8, [r12+80h]; Source
0x180006f36  test    r8, r8
0x180006f39  jz      short loc_180006F7C
0x180006f3b  cmp     [r8], r13b
0x180006f3e  jz      short loc_180006F7C
0x180006f40  mov     rax, rbp
0x180006f43  inc     rax
0x180006f46  cmp     [r8+rax], r13b
0x180006f4a  jnz     short loc_180006F43
0x180006f4c  mov     rdx, rsi
0x180006f4f  lea     r14, [rax+1]
0x180006f53  sub     rdx, rbx; DestinationSize
0x180006f56  cmp     rdx, r14
0x180006f59  jnb     short loc_180006F61
0x180006f5b  mov     [rdi+20h], r13
0x180006f5f  jmp     short loc_180006F85
0x180006f61  mov     r9, r14; SourceSize
0x180006f64  mov     rcx, rbx; Destination
0x180006f67  call    cs:__imp_memcpy_s
0x180006f6e  nop     dword ptr [rax+rax+00h]
0x180006f73  mov     [rdi+20h], rbx
0x180006f77  add     rbx, r14
0x180006f7a  jmp     short loc_180006F80
0x180006f7c  mov     [rdi+20h], r13
0x180006f80  cmp     rbx, rsi
0x180006f83  jz      short loc_180006FCD
0x180006f85  mov     r8, [r12+18h]; Source
0x180006f8a  test    r8, r8
0x180006f8d  jz      short loc_180006FCD
0x180006f8f  cmp     [r8], r13w
0x180006f93  jz      short loc_180006FCD
0x180006f95  inc     rbp
0x180006f98  cmp     [r8+rbp*2], r13w
0x180006f9d  jnz     short loc_180006F95
0x180006f9f  mov     rdx, rsi
0x180006fa2  lea     r14, ds:2[rbp*2]
0x180006faa  sub     rdx, rbx; DestinationSize
0x180006fad  cmp     rdx, r14
0x180006fb0  jb      short loc_180006FCD
0x180006fb2  mov     r9, r14; SourceSize
0x180006fb5  mov     rcx, rbx; Destination
0x180006fb8  call    cs:__imp_memcpy_s
0x180006fbf  nop     dword ptr [rax+rax+00h]
0x180006fc4  mov     [rdi+38h], rbx
0x180006fc8  add     rbx, r14
0x180006fcb  jmp     short loc_180006FD1
0x180006fcd  mov     [rdi+38h], r13
0x180006fd1  sub     rsi, rbx
0x180006fd4  xor     edx, edx; Val
0x180006fd6  mov     r8, rsi; Size
0x180006fd9  mov     rcx, rbx; void *
0x180006fdc  call    memset_0
0x180006fe1  add     rsp, 28h
0x180006fe5  pop     r15
0x180006fe7  pop     r14
0x180006fe9  pop     r13
0x180006feb  pop     r12
0x180006fed  pop     rdi
0x180006fee  pop     rsi
0x180006fef  pop     rbp
0x180006ff0  pop     rbx
0x180006ff1  retn
```
