# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004ea0`
- end: `0x1800050b9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050c0`

## callees

- `0x180001962`
- `0x180004b28`
- `0x180004ea0`
- `0x180005728`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f96`

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
0x180004ea0  push    rbx
0x180004ea2  push    rbp
0x180004ea3  push    rsi
0x180004ea4  push    rdi
0x180004ea5  push    r12
0x180004ea7  push    r13
0x180004ea9  push    r14
0x180004eab  push    r15
0x180004ead  sub     rsp, 28h
0x180004eb1  mov     [rcx+4], r8d
0x180004eb5  xor     r13d, r13d
0x180004eb8  mov     eax, [rdx+8]
0x180004ebb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004ebf  mov     [rcx+8], eax
0x180004ec2  mov     rdi, rcx
0x180004ec5  mov     [rcx+10h], r13
0x180004ec9  mov     r12, rdx
0x180004ecc  movzx   eax, word ptr [rdx+40h]
0x180004ed0  mov     [rcx+18h], ax
0x180004ed4  mov     al, [rdx]
0x180004ed6  mov     [rcx+1Ah], al
0x180004ed9  mov     [rcx+20h], r13
0x180004edd  mov     rax, [rdx+88h]
0x180004ee4  mov     [rcx+28h], rax
0x180004ee8  mov     rax, [rdx+90h]
0x180004eef  mov     [rcx+30h], rax
0x180004ef3  mov     [rcx+38h], r13
0x180004ef7  mov     rcx, [rdx+38h]
0x180004efb  lea     edx, [rbp+2]
0x180004efe  test    rcx, rcx
0x180004f01  jnz     short loc_180004F08
0x180004f03  mov     r8d, edx
0x180004f06  jmp     short loc_180004F18
0x180004f08  mov     rax, rbp
0x180004f0b  inc     rax
0x180004f0e  cmp     [rcx+rax], r13b
0x180004f12  jnz     short loc_180004F0B
0x180004f14  lea     r8, [rax+1]; unsigned __int64
0x180004f18  mov     rcx, [r12+80h]
0x180004f20  test    rcx, rcx
0x180004f23  jz      short loc_180004F35
0x180004f25  mov     rax, rbp
0x180004f28  inc     rax
0x180004f2b  cmp     [rcx+rax], r13b
0x180004f2f  jnz     short loc_180004F28
0x180004f31  lea     rdx, [rax+1]
0x180004f35  mov     rcx, [r12+18h]
0x180004f3a  test    rcx, rcx
0x180004f3d  jnz     short loc_180004F44
0x180004f3f  lea     eax, [rcx+2]
0x180004f42  jmp     short loc_180004F59
0x180004f44  mov     rax, rbp
0x180004f47  inc     rax
0x180004f4a  cmp     [rcx+rax*2], r13w
0x180004f4f  jnz     short loc_180004F47
0x180004f51  lea     rax, ds:2[rax*2]
0x180004f59  lea     r14, [rdx+rax]
0x180004f5d  add     r14, r8
0x180004f60  lea     rsi, [rdi+48h]
0x180004f64  cmp     [rdi+40h], r13
0x180004f68  jz      short loc_180004F6F
0x180004f6a  cmp     [rsi], r14
0x180004f6d  jnb     short loc_180004FA3
0x180004f6f  mov     rdx, r14; dwBytes
0x180004f72  mov     ecx, 8; dwFlags
0x180004f77  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f7c  mov     r15, rax
0x180004f7f  test    rax, rax
0x180004f82  jz      short loc_180004FA3
0x180004f84  mov     rbx, [rdi+40h]
0x180004f88  call    cs:__imp_GetProcessHeap
0x180004f8e  mov     r8, rbx; lpMem
0x180004f91  xor     edx, edx; dwFlags
0x180004f93  mov     rcx, rax; hHeap
0x180004f96  call    cs:__imp_HeapFree
0x180004f9c  mov     [rdi+40h], r15
0x180004fa0  mov     [rsi], r14
0x180004fa3  mov     rbx, [rdi+40h]
0x180004fa7  test    rbx, rbx
0x180004faa  jz      loc_1800050A8
0x180004fb0  mov     rdx, [rsi]; DestinationSize
0x180004fb3  lea     rsi, [rdx+rbx]
0x180004fb7  cmp     rbx, rsi
0x180004fba  jz      short loc_180004FFA
0x180004fbc  mov     r8, [r12+38h]; Source
0x180004fc1  test    r8, r8
0x180004fc4  jz      short loc_180004FFA
0x180004fc6  cmp     [r8], r13b
0x180004fc9  jz      short loc_180004FFA
0x180004fcb  mov     rax, rbp
0x180004fce  inc     rax
0x180004fd1  cmp     [r8+rax], r13b
0x180004fd5  jnz     short loc_180004FCE
0x180004fd7  lea     r14, [rax+1]
0x180004fdb  cmp     rdx, r14
0x180004fde  jnb     short loc_180004FE6
0x180004fe0  mov     [rdi+10h], r13
0x180004fe4  jmp     short loc_180005003
0x180004fe6  mov     r9, r14; SourceSize
0x180004fe9  mov     rcx, rbx; Destination
0x180004fec  call    memcpy_s
0x180004ff1  mov     [rdi+10h], rbx
0x180004ff5  add     rbx, r14
0x180004ff8  jmp     short loc_180004FFE
0x180004ffa  mov     [rdi+10h], r13
0x180004ffe  cmp     rbx, rsi
0x180005001  jz      short loc_18000504A
0x180005003  mov     r8, [r12+80h]; Source
0x18000500b  test    r8, r8
0x18000500e  jz      short loc_18000504A
0x180005010  cmp     [r8], r13b
0x180005013  jz      short loc_18000504A
0x180005015  mov     rax, rbp
0x180005018  inc     rax
0x18000501b  cmp     [r8+rax], r13b
0x18000501f  jnz     short loc_180005018
0x180005021  mov     rdx, rsi
0x180005024  lea     r14, [rax+1]
0x180005028  sub     rdx, rbx; DestinationSize
0x18000502b  cmp     rdx, r14
0x18000502e  jnb     short loc_180005036
0x180005030  mov     [rdi+20h], r13
0x180005034  jmp     short loc_180005053
0x180005036  mov     r9, r14; SourceSize
0x180005039  mov     rcx, rbx; Destination
0x18000503c  call    memcpy_s
0x180005041  mov     [rdi+20h], rbx
0x180005045  add     rbx, r14
0x180005048  jmp     short loc_18000504E
0x18000504a  mov     [rdi+20h], r13
0x18000504e  cmp     rbx, rsi
0x180005051  jz      short loc_180005094
0x180005053  mov     r8, [r12+18h]; Source
0x180005058  test    r8, r8
0x18000505b  jz      short loc_180005094
0x18000505d  cmp     [r8], r13w
0x180005061  jz      short loc_180005094
0x180005063  inc     rbp
0x180005066  cmp     [r8+rbp*2], r13w
0x18000506b  jnz     short loc_180005063
0x18000506d  mov     rdx, rsi
0x180005070  lea     r14, ds:2[rbp*2]
0x180005078  sub     rdx, rbx; DestinationSize
0x18000507b  cmp     rdx, r14
0x18000507e  jb      short loc_180005094
0x180005080  mov     r9, r14; SourceSize
0x180005083  mov     rcx, rbx; Destination
0x180005086  call    memcpy_s
0x18000508b  mov     [rdi+38h], rbx
0x18000508f  add     rbx, r14
0x180005092  jmp     short loc_180005098
0x180005094  mov     [rdi+38h], r13
0x180005098  sub     rsi, rbx
0x18000509b  xor     edx, edx; Val
0x18000509d  mov     r8, rsi; Size
0x1800050a0  mov     rcx, rbx; void *
0x1800050a3  call    memset_0
0x1800050a8  add     rsp, 28h
0x1800050ac  pop     r15
0x1800050ae  pop     r14
0x1800050b0  pop     r13
0x1800050b2  pop     r12
0x1800050b4  pop     rdi
0x1800050b5  pop     rsi
0x1800050b6  pop     rbp
0x1800050b7  pop     rbx
0x1800050b8  retn
```
