# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008c84`
- end: `0x180008e9d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006170`

## callees

- `0x180003320`
- `0x1800073c8`
- `0x180008c84`
- `0x18000ac08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d7a`

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
0x180008c84  push    rbx
0x180008c86  push    rbp
0x180008c87  push    rsi
0x180008c88  push    rdi
0x180008c89  push    r12
0x180008c8b  push    r13
0x180008c8d  push    r14
0x180008c8f  push    r15
0x180008c91  sub     rsp, 28h
0x180008c95  mov     [rcx+4], r8d
0x180008c99  xor     r13d, r13d
0x180008c9c  mov     eax, [rdx+8]
0x180008c9f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008ca3  mov     [rcx+8], eax
0x180008ca6  mov     rdi, rcx
0x180008ca9  mov     [rcx+10h], r13
0x180008cad  mov     r12, rdx
0x180008cb0  movzx   eax, word ptr [rdx+40h]
0x180008cb4  mov     [rcx+18h], ax
0x180008cb8  mov     al, [rdx]
0x180008cba  mov     [rcx+1Ah], al
0x180008cbd  mov     [rcx+20h], r13
0x180008cc1  mov     rax, [rdx+88h]
0x180008cc8  mov     [rcx+28h], rax
0x180008ccc  mov     rax, [rdx+90h]
0x180008cd3  mov     [rcx+30h], rax
0x180008cd7  mov     [rcx+38h], r13
0x180008cdb  mov     rcx, [rdx+38h]
0x180008cdf  lea     edx, [rbp+2]
0x180008ce2  test    rcx, rcx
0x180008ce5  jnz     short loc_180008CEC
0x180008ce7  mov     r8d, edx
0x180008cea  jmp     short loc_180008CFC
0x180008cec  mov     rax, rbp
0x180008cef  inc     rax
0x180008cf2  cmp     [rcx+rax], r13b
0x180008cf6  jnz     short loc_180008CEF
0x180008cf8  lea     r8, [rax+1]; unsigned __int64
0x180008cfc  mov     rcx, [r12+80h]
0x180008d04  test    rcx, rcx
0x180008d07  jz      short loc_180008D19
0x180008d09  mov     rax, rbp
0x180008d0c  inc     rax
0x180008d0f  cmp     [rcx+rax], r13b
0x180008d13  jnz     short loc_180008D0C
0x180008d15  lea     rdx, [rax+1]
0x180008d19  mov     rcx, [r12+18h]
0x180008d1e  test    rcx, rcx
0x180008d21  jnz     short loc_180008D28
0x180008d23  lea     eax, [rcx+2]
0x180008d26  jmp     short loc_180008D3D
0x180008d28  mov     rax, rbp
0x180008d2b  inc     rax
0x180008d2e  cmp     [rcx+rax*2], r13w
0x180008d33  jnz     short loc_180008D2B
0x180008d35  lea     rax, ds:2[rax*2]
0x180008d3d  lea     r14, [rdx+rax]
0x180008d41  add     r14, r8
0x180008d44  lea     rsi, [rdi+48h]
0x180008d48  cmp     [rdi+40h], r13
0x180008d4c  jz      short loc_180008D53
0x180008d4e  cmp     [rsi], r14
0x180008d51  jnb     short loc_180008D87
0x180008d53  mov     rdx, r14; dwBytes
0x180008d56  mov     ecx, 8; dwFlags
0x180008d5b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008d60  mov     r15, rax
0x180008d63  test    rax, rax
0x180008d66  jz      short loc_180008D87
0x180008d68  mov     rbx, [rdi+40h]
0x180008d6c  call    cs:__imp_GetProcessHeap
0x180008d72  mov     r8, rbx; lpMem
0x180008d75  xor     edx, edx; dwFlags
0x180008d77  mov     rcx, rax; hHeap
0x180008d7a  call    cs:__imp_HeapFree
0x180008d80  mov     [rdi+40h], r15
0x180008d84  mov     [rsi], r14
0x180008d87  mov     rbx, [rdi+40h]
0x180008d8b  test    rbx, rbx
0x180008d8e  jz      loc_180008E8C
0x180008d94  mov     rdx, [rsi]; DestinationSize
0x180008d97  lea     rsi, [rdx+rbx]
0x180008d9b  cmp     rbx, rsi
0x180008d9e  jz      short loc_180008DDE
0x180008da0  mov     r8, [r12+38h]; Source
0x180008da5  test    r8, r8
0x180008da8  jz      short loc_180008DDE
0x180008daa  cmp     [r8], r13b
0x180008dad  jz      short loc_180008DDE
0x180008daf  mov     rax, rbp
0x180008db2  inc     rax
0x180008db5  cmp     [r8+rax], r13b
0x180008db9  jnz     short loc_180008DB2
0x180008dbb  lea     r14, [rax+1]
0x180008dbf  cmp     rdx, r14
0x180008dc2  jnb     short loc_180008DCA
0x180008dc4  mov     [rdi+10h], r13
0x180008dc8  jmp     short loc_180008DE7
0x180008dca  mov     r9, r14; SourceSize
0x180008dcd  mov     rcx, rbx; Destination
0x180008dd0  call    memcpy_s
0x180008dd5  mov     [rdi+10h], rbx
0x180008dd9  add     rbx, r14
0x180008ddc  jmp     short loc_180008DE2
0x180008dde  mov     [rdi+10h], r13
0x180008de2  cmp     rbx, rsi
0x180008de5  jz      short loc_180008E2E
0x180008de7  mov     r8, [r12+80h]; Source
0x180008def  test    r8, r8
0x180008df2  jz      short loc_180008E2E
0x180008df4  cmp     [r8], r13b
0x180008df7  jz      short loc_180008E2E
0x180008df9  mov     rax, rbp
0x180008dfc  inc     rax
0x180008dff  cmp     [r8+rax], r13b
0x180008e03  jnz     short loc_180008DFC
0x180008e05  mov     rdx, rsi
0x180008e08  lea     r14, [rax+1]
0x180008e0c  sub     rdx, rbx; DestinationSize
0x180008e0f  cmp     rdx, r14
0x180008e12  jnb     short loc_180008E1A
0x180008e14  mov     [rdi+20h], r13
0x180008e18  jmp     short loc_180008E37
0x180008e1a  mov     r9, r14; SourceSize
0x180008e1d  mov     rcx, rbx; Destination
0x180008e20  call    memcpy_s
0x180008e25  mov     [rdi+20h], rbx
0x180008e29  add     rbx, r14
0x180008e2c  jmp     short loc_180008E32
0x180008e2e  mov     [rdi+20h], r13
0x180008e32  cmp     rbx, rsi
0x180008e35  jz      short loc_180008E78
0x180008e37  mov     r8, [r12+18h]; Source
0x180008e3c  test    r8, r8
0x180008e3f  jz      short loc_180008E78
0x180008e41  cmp     [r8], r13w
0x180008e45  jz      short loc_180008E78
0x180008e47  inc     rbp
0x180008e4a  cmp     [r8+rbp*2], r13w
0x180008e4f  jnz     short loc_180008E47
0x180008e51  mov     rdx, rsi
0x180008e54  lea     r14, ds:2[rbp*2]
0x180008e5c  sub     rdx, rbx; DestinationSize
0x180008e5f  cmp     rdx, r14
0x180008e62  jb      short loc_180008E78
0x180008e64  mov     r9, r14; SourceSize
0x180008e67  mov     rcx, rbx; Destination
0x180008e6a  call    memcpy_s
0x180008e6f  mov     [rdi+38h], rbx
0x180008e73  add     rbx, r14
0x180008e76  jmp     short loc_180008E7C
0x180008e78  mov     [rdi+38h], r13
0x180008e7c  sub     rsi, rbx
0x180008e7f  xor     edx, edx; Val
0x180008e81  mov     r8, rsi; Size
0x180008e84  mov     rcx, rbx; void *
0x180008e87  call    memset_0
0x180008e8c  add     rsp, 28h
0x180008e90  pop     r15
0x180008e92  pop     r14
0x180008e94  pop     r13
0x180008e96  pop     r12
0x180008e98  pop     rdi
0x180008e99  pop     rsi
0x180008e9a  pop     rbp
0x180008e9b  pop     rbx
0x180008e9c  retn
```
