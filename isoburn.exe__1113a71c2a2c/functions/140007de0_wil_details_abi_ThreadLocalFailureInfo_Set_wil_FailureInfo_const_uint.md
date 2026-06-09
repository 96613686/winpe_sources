# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140007de0`
- end: `0x140007ff9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004dd0`

## callees

- `0x140002bc6`
- `0x14000756c`
- `0x140007de0`
- `0x14000a570`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140007ec8`
- `KERNEL32!GetProcessHeap` at `0x140007ec8`
- `KERNEL32!HeapFree` at `0x140007ed6`
- `KERNEL32!HeapFree` at `0x140007ed6`

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
0x140007de0  push    rbx
0x140007de2  push    rbp
0x140007de3  push    rsi
0x140007de4  push    rdi
0x140007de5  push    r12
0x140007de7  push    r13
0x140007de9  push    r14
0x140007deb  push    r15
0x140007ded  sub     rsp, 28h
0x140007df1  mov     [rcx+4], r8d
0x140007df5  xor     r13d, r13d
0x140007df8  mov     eax, [rdx+8]
0x140007dfb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140007dff  mov     [rcx+8], eax
0x140007e02  mov     rdi, rcx
0x140007e05  mov     [rcx+10h], r13
0x140007e09  mov     r12, rdx
0x140007e0c  movzx   eax, word ptr [rdx+40h]
0x140007e10  mov     [rcx+18h], ax
0x140007e14  mov     al, [rdx]
0x140007e16  mov     [rcx+1Ah], al
0x140007e19  mov     [rcx+20h], r13
0x140007e1d  mov     rax, [rdx+88h]
0x140007e24  mov     [rcx+28h], rax
0x140007e28  mov     rax, [rdx+90h]
0x140007e2f  mov     [rcx+30h], rax
0x140007e33  mov     [rcx+38h], r13
0x140007e37  mov     rcx, [rdx+38h]
0x140007e3b  lea     edx, [rbp+2]
0x140007e3e  test    rcx, rcx
0x140007e41  jnz     short loc_140007E48
0x140007e43  mov     r8d, edx
0x140007e46  jmp     short loc_140007E58
0x140007e48  mov     rax, rbp
0x140007e4b  inc     rax
0x140007e4e  cmp     [rcx+rax], r13b
0x140007e52  jnz     short loc_140007E4B
0x140007e54  lea     r8, [rax+1]; unsigned __int64
0x140007e58  mov     rcx, [r12+80h]
0x140007e60  test    rcx, rcx
0x140007e63  jz      short loc_140007E75
0x140007e65  mov     rax, rbp
0x140007e68  inc     rax
0x140007e6b  cmp     [rcx+rax], r13b
0x140007e6f  jnz     short loc_140007E68
0x140007e71  lea     rdx, [rax+1]
0x140007e75  mov     rcx, [r12+18h]
0x140007e7a  test    rcx, rcx
0x140007e7d  jnz     short loc_140007E84
0x140007e7f  lea     eax, [rcx+2]
0x140007e82  jmp     short loc_140007E99
0x140007e84  mov     rax, rbp
0x140007e87  inc     rax
0x140007e8a  cmp     [rcx+rax*2], r13w
0x140007e8f  jnz     short loc_140007E87
0x140007e91  lea     rax, ds:2[rax*2]
0x140007e99  lea     r14, [rdx+rax]
0x140007e9d  add     r14, r8
0x140007ea0  lea     rsi, [rdi+48h]
0x140007ea4  cmp     [rdi+40h], r13
0x140007ea8  jz      short loc_140007EAF
0x140007eaa  cmp     [rsi], r14
0x140007ead  jnb     short loc_140007EE3
0x140007eaf  mov     rdx, r14; dwBytes
0x140007eb2  mov     ecx, 8; dwFlags
0x140007eb7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007ebc  mov     r15, rax
0x140007ebf  test    rax, rax
0x140007ec2  jz      short loc_140007EE3
0x140007ec4  mov     rbx, [rdi+40h]
0x140007ec8  call    cs:__imp_GetProcessHeap
0x140007ece  mov     r8, rbx; lpMem
0x140007ed1  xor     edx, edx; dwFlags
0x140007ed3  mov     rcx, rax; hHeap
0x140007ed6  call    cs:__imp_HeapFree
0x140007edc  mov     [rdi+40h], r15
0x140007ee0  mov     [rsi], r14
0x140007ee3  mov     rbx, [rdi+40h]
0x140007ee7  test    rbx, rbx
0x140007eea  jz      loc_140007FE8
0x140007ef0  mov     rdx, [rsi]; DestinationSize
0x140007ef3  lea     rsi, [rdx+rbx]
0x140007ef7  cmp     rbx, rsi
0x140007efa  jz      short loc_140007F3A
0x140007efc  mov     r8, [r12+38h]; Source
0x140007f01  test    r8, r8
0x140007f04  jz      short loc_140007F3A
0x140007f06  cmp     [r8], r13b
0x140007f09  jz      short loc_140007F3A
0x140007f0b  mov     rax, rbp
0x140007f0e  inc     rax
0x140007f11  cmp     [r8+rax], r13b
0x140007f15  jnz     short loc_140007F0E
0x140007f17  lea     r14, [rax+1]
0x140007f1b  cmp     rdx, r14
0x140007f1e  jnb     short loc_140007F26
0x140007f20  mov     [rdi+10h], r13
0x140007f24  jmp     short loc_140007F43
0x140007f26  mov     r9, r14; SourceSize
0x140007f29  mov     rcx, rbx; Destination
0x140007f2c  call    memcpy_s
0x140007f31  mov     [rdi+10h], rbx
0x140007f35  add     rbx, r14
0x140007f38  jmp     short loc_140007F3E
0x140007f3a  mov     [rdi+10h], r13
0x140007f3e  cmp     rbx, rsi
0x140007f41  jz      short loc_140007F8A
0x140007f43  mov     r8, [r12+80h]; Source
0x140007f4b  test    r8, r8
0x140007f4e  jz      short loc_140007F8A
0x140007f50  cmp     [r8], r13b
0x140007f53  jz      short loc_140007F8A
0x140007f55  mov     rax, rbp
0x140007f58  inc     rax
0x140007f5b  cmp     [r8+rax], r13b
0x140007f5f  jnz     short loc_140007F58
0x140007f61  mov     rdx, rsi
0x140007f64  lea     r14, [rax+1]
0x140007f68  sub     rdx, rbx; DestinationSize
0x140007f6b  cmp     rdx, r14
0x140007f6e  jnb     short loc_140007F76
0x140007f70  mov     [rdi+20h], r13
0x140007f74  jmp     short loc_140007F93
0x140007f76  mov     r9, r14; SourceSize
0x140007f79  mov     rcx, rbx; Destination
0x140007f7c  call    memcpy_s
0x140007f81  mov     [rdi+20h], rbx
0x140007f85  add     rbx, r14
0x140007f88  jmp     short loc_140007F8E
0x140007f8a  mov     [rdi+20h], r13
0x140007f8e  cmp     rbx, rsi
0x140007f91  jz      short loc_140007FD4
0x140007f93  mov     r8, [r12+18h]; Source
0x140007f98  test    r8, r8
0x140007f9b  jz      short loc_140007FD4
0x140007f9d  cmp     [r8], r13w
0x140007fa1  jz      short loc_140007FD4
0x140007fa3  inc     rbp
0x140007fa6  cmp     [r8+rbp*2], r13w
0x140007fab  jnz     short loc_140007FA3
0x140007fad  mov     rdx, rsi
0x140007fb0  lea     r14, ds:2[rbp*2]
0x140007fb8  sub     rdx, rbx; DestinationSize
0x140007fbb  cmp     rdx, r14
0x140007fbe  jb      short loc_140007FD4
0x140007fc0  mov     r9, r14; SourceSize
0x140007fc3  mov     rcx, rbx; Destination
0x140007fc6  call    memcpy_s
0x140007fcb  mov     [rdi+38h], rbx
0x140007fcf  add     rbx, r14
0x140007fd2  jmp     short loc_140007FD8
0x140007fd4  mov     [rdi+38h], r13
0x140007fd8  sub     rsi, rbx
0x140007fdb  xor     edx, edx; Val
0x140007fdd  mov     r8, rsi; Size
0x140007fe0  mov     rcx, rbx; void *
0x140007fe3  call    memset_0
0x140007fe8  add     rsp, 28h
0x140007fec  pop     r15
0x140007fee  pop     r14
0x140007ff0  pop     r13
0x140007ff2  pop     r12
0x140007ff4  pop     rdi
0x140007ff5  pop     rsi
0x140007ff6  pop     rbp
0x140007ff7  pop     rbx
0x140007ff8  retn
```
