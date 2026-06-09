# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010c4c`
- end: `0x180010e65`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c7b0`

## callees

- `0x180003940`
- `0x18000e6ac`
- `0x180010c4c`
- `0x1800196f0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180010d34`
- `KERNEL32!GetProcessHeap` at `0x180010d34`
- `KERNEL32!HeapFree` at `0x180010d42`
- `KERNEL32!HeapFree` at `0x180010d42`

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
0x180010c4c  push    rbx
0x180010c4e  push    rbp
0x180010c4f  push    rsi
0x180010c50  push    rdi
0x180010c51  push    r12
0x180010c53  push    r13
0x180010c55  push    r14
0x180010c57  push    r15
0x180010c59  sub     rsp, 28h
0x180010c5d  mov     [rcx+4], r8d
0x180010c61  xor     r13d, r13d
0x180010c64  mov     eax, [rdx+8]
0x180010c67  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180010c6b  mov     [rcx+8], eax
0x180010c6e  mov     rdi, rcx
0x180010c71  mov     [rcx+10h], r13
0x180010c75  mov     r12, rdx
0x180010c78  movzx   eax, word ptr [rdx+40h]
0x180010c7c  mov     [rcx+18h], ax
0x180010c80  mov     al, [rdx]
0x180010c82  mov     [rcx+1Ah], al
0x180010c85  mov     [rcx+20h], r13
0x180010c89  mov     rax, [rdx+88h]
0x180010c90  mov     [rcx+28h], rax
0x180010c94  mov     rax, [rdx+90h]
0x180010c9b  mov     [rcx+30h], rax
0x180010c9f  mov     [rcx+38h], r13
0x180010ca3  mov     rcx, [rdx+38h]
0x180010ca7  lea     edx, [rbp+2]
0x180010caa  test    rcx, rcx
0x180010cad  jnz     short loc_180010CB4
0x180010caf  mov     r8d, edx
0x180010cb2  jmp     short loc_180010CC4
0x180010cb4  mov     rax, rbp
0x180010cb7  inc     rax
0x180010cba  cmp     [rcx+rax], r13b
0x180010cbe  jnz     short loc_180010CB7
0x180010cc0  lea     r8, [rax+1]; unsigned __int64
0x180010cc4  mov     rcx, [r12+80h]
0x180010ccc  test    rcx, rcx
0x180010ccf  jz      short loc_180010CE1
0x180010cd1  mov     rax, rbp
0x180010cd4  inc     rax
0x180010cd7  cmp     [rcx+rax], r13b
0x180010cdb  jnz     short loc_180010CD4
0x180010cdd  lea     rdx, [rax+1]
0x180010ce1  mov     rcx, [r12+18h]
0x180010ce6  test    rcx, rcx
0x180010ce9  jnz     short loc_180010CF0
0x180010ceb  lea     eax, [rcx+2]
0x180010cee  jmp     short loc_180010D05
0x180010cf0  mov     rax, rbp
0x180010cf3  inc     rax
0x180010cf6  cmp     [rcx+rax*2], r13w
0x180010cfb  jnz     short loc_180010CF3
0x180010cfd  lea     rax, ds:2[rax*2]
0x180010d05  lea     r14, [rdx+rax]
0x180010d09  add     r14, r8
0x180010d0c  lea     rsi, [rdi+48h]
0x180010d10  cmp     [rdi+40h], r13
0x180010d14  jz      short loc_180010D1B
0x180010d16  cmp     [rsi], r14
0x180010d19  jnb     short loc_180010D4F
0x180010d1b  mov     rdx, r14; dwBytes
0x180010d1e  mov     ecx, 8; dwFlags
0x180010d23  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010d28  mov     r15, rax
0x180010d2b  test    rax, rax
0x180010d2e  jz      short loc_180010D4F
0x180010d30  mov     rbx, [rdi+40h]
0x180010d34  call    cs:__imp_GetProcessHeap
0x180010d3a  mov     r8, rbx; lpMem
0x180010d3d  xor     edx, edx; dwFlags
0x180010d3f  mov     rcx, rax; hHeap
0x180010d42  call    cs:__imp_HeapFree
0x180010d48  mov     [rdi+40h], r15
0x180010d4c  mov     [rsi], r14
0x180010d4f  mov     rbx, [rdi+40h]
0x180010d53  test    rbx, rbx
0x180010d56  jz      loc_180010E54
0x180010d5c  mov     rdx, [rsi]; DestinationSize
0x180010d5f  lea     rsi, [rdx+rbx]
0x180010d63  cmp     rbx, rsi
0x180010d66  jz      short loc_180010DA6
0x180010d68  mov     r8, [r12+38h]; Source
0x180010d6d  test    r8, r8
0x180010d70  jz      short loc_180010DA6
0x180010d72  cmp     [r8], r13b
0x180010d75  jz      short loc_180010DA6
0x180010d77  mov     rax, rbp
0x180010d7a  inc     rax
0x180010d7d  cmp     [r8+rax], r13b
0x180010d81  jnz     short loc_180010D7A
0x180010d83  lea     r14, [rax+1]
0x180010d87  cmp     rdx, r14
0x180010d8a  jnb     short loc_180010D92
0x180010d8c  mov     [rdi+10h], r13
0x180010d90  jmp     short loc_180010DAF
0x180010d92  mov     r9, r14; SourceSize
0x180010d95  mov     rcx, rbx; Destination
0x180010d98  call    memcpy_s
0x180010d9d  mov     [rdi+10h], rbx
0x180010da1  add     rbx, r14
0x180010da4  jmp     short loc_180010DAA
0x180010da6  mov     [rdi+10h], r13
0x180010daa  cmp     rbx, rsi
0x180010dad  jz      short loc_180010DF6
0x180010daf  mov     r8, [r12+80h]; Source
0x180010db7  test    r8, r8
0x180010dba  jz      short loc_180010DF6
0x180010dbc  cmp     [r8], r13b
0x180010dbf  jz      short loc_180010DF6
0x180010dc1  mov     rax, rbp
0x180010dc4  inc     rax
0x180010dc7  cmp     [r8+rax], r13b
0x180010dcb  jnz     short loc_180010DC4
0x180010dcd  mov     rdx, rsi
0x180010dd0  lea     r14, [rax+1]
0x180010dd4  sub     rdx, rbx; DestinationSize
0x180010dd7  cmp     rdx, r14
0x180010dda  jnb     short loc_180010DE2
0x180010ddc  mov     [rdi+20h], r13
0x180010de0  jmp     short loc_180010DFF
0x180010de2  mov     r9, r14; SourceSize
0x180010de5  mov     rcx, rbx; Destination
0x180010de8  call    memcpy_s
0x180010ded  mov     [rdi+20h], rbx
0x180010df1  add     rbx, r14
0x180010df4  jmp     short loc_180010DFA
0x180010df6  mov     [rdi+20h], r13
0x180010dfa  cmp     rbx, rsi
0x180010dfd  jz      short loc_180010E40
0x180010dff  mov     r8, [r12+18h]; Source
0x180010e04  test    r8, r8
0x180010e07  jz      short loc_180010E40
0x180010e09  cmp     [r8], r13w
0x180010e0d  jz      short loc_180010E40
0x180010e0f  inc     rbp
0x180010e12  cmp     [r8+rbp*2], r13w
0x180010e17  jnz     short loc_180010E0F
0x180010e19  mov     rdx, rsi
0x180010e1c  lea     r14, ds:2[rbp*2]
0x180010e24  sub     rdx, rbx; DestinationSize
0x180010e27  cmp     rdx, r14
0x180010e2a  jb      short loc_180010E40
0x180010e2c  mov     r9, r14; SourceSize
0x180010e2f  mov     rcx, rbx; Destination
0x180010e32  call    memcpy_s
0x180010e37  mov     [rdi+38h], rbx
0x180010e3b  add     rbx, r14
0x180010e3e  jmp     short loc_180010E44
0x180010e40  mov     [rdi+38h], r13
0x180010e44  sub     rsi, rbx
0x180010e47  xor     edx, edx; Val
0x180010e49  mov     r8, rsi; Size
0x180010e4c  mov     rcx, rbx; void *
0x180010e4f  call    memset_0
0x180010e54  add     rsp, 28h
0x180010e58  pop     r15
0x180010e5a  pop     r14
0x180010e5c  pop     r13
0x180010e5e  pop     r12
0x180010e60  pop     rdi
0x180010e61  pop     rsi
0x180010e62  pop     rbp
0x180010e63  pop     rbx
0x180010e64  retn
```
