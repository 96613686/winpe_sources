# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a4e8`
- end: `0x18000a701`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006fd0`

## callees

- `0x1800021f4`
- `0x180008b94`
- `0x18000a4e8`
- `0x180010558`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5de`

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
0x18000a4e8  push    rbx
0x18000a4ea  push    rbp
0x18000a4eb  push    rsi
0x18000a4ec  push    rdi
0x18000a4ed  push    r12
0x18000a4ef  push    r13
0x18000a4f1  push    r14
0x18000a4f3  push    r15
0x18000a4f5  sub     rsp, 28h
0x18000a4f9  mov     [rcx+4], r8d
0x18000a4fd  xor     r13d, r13d
0x18000a500  mov     eax, [rdx+8]
0x18000a503  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a507  mov     [rcx+8], eax
0x18000a50a  mov     rdi, rcx
0x18000a50d  mov     [rcx+10h], r13
0x18000a511  mov     r12, rdx
0x18000a514  movzx   eax, word ptr [rdx+40h]
0x18000a518  mov     [rcx+18h], ax
0x18000a51c  mov     al, [rdx]
0x18000a51e  mov     [rcx+1Ah], al
0x18000a521  mov     [rcx+20h], r13
0x18000a525  mov     rax, [rdx+88h]
0x18000a52c  mov     [rcx+28h], rax
0x18000a530  mov     rax, [rdx+90h]
0x18000a537  mov     [rcx+30h], rax
0x18000a53b  mov     [rcx+38h], r13
0x18000a53f  mov     rcx, [rdx+38h]
0x18000a543  lea     edx, [rbp+2]
0x18000a546  test    rcx, rcx
0x18000a549  jnz     short loc_18000A550
0x18000a54b  mov     r8d, edx
0x18000a54e  jmp     short loc_18000A560
0x18000a550  mov     rax, rbp
0x18000a553  inc     rax
0x18000a556  cmp     [rcx+rax], r13b
0x18000a55a  jnz     short loc_18000A553
0x18000a55c  lea     r8, [rax+1]; unsigned __int64
0x18000a560  mov     rcx, [r12+80h]
0x18000a568  test    rcx, rcx
0x18000a56b  jz      short loc_18000A57D
0x18000a56d  mov     rax, rbp
0x18000a570  inc     rax
0x18000a573  cmp     [rcx+rax], r13b
0x18000a577  jnz     short loc_18000A570
0x18000a579  lea     rdx, [rax+1]
0x18000a57d  mov     rcx, [r12+18h]
0x18000a582  test    rcx, rcx
0x18000a585  jnz     short loc_18000A58C
0x18000a587  lea     eax, [rcx+2]
0x18000a58a  jmp     short loc_18000A5A1
0x18000a58c  mov     rax, rbp
0x18000a58f  inc     rax
0x18000a592  cmp     [rcx+rax*2], r13w
0x18000a597  jnz     short loc_18000A58F
0x18000a599  lea     rax, ds:2[rax*2]
0x18000a5a1  lea     r14, [rdx+rax]
0x18000a5a5  add     r14, r8
0x18000a5a8  lea     rsi, [rdi+48h]
0x18000a5ac  cmp     [rdi+40h], r13
0x18000a5b0  jz      short loc_18000A5B7
0x18000a5b2  cmp     [rsi], r14
0x18000a5b5  jnb     short loc_18000A5EB
0x18000a5b7  mov     rdx, r14; dwBytes
0x18000a5ba  mov     ecx, 8; dwFlags
0x18000a5bf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a5c4  mov     r15, rax
0x18000a5c7  test    rax, rax
0x18000a5ca  jz      short loc_18000A5EB
0x18000a5cc  mov     rbx, [rdi+40h]
0x18000a5d0  call    cs:__imp_GetProcessHeap
0x18000a5d6  mov     r8, rbx; lpMem
0x18000a5d9  xor     edx, edx; dwFlags
0x18000a5db  mov     rcx, rax; hHeap
0x18000a5de  call    cs:__imp_HeapFree
0x18000a5e4  mov     [rdi+40h], r15
0x18000a5e8  mov     [rsi], r14
0x18000a5eb  mov     rbx, [rdi+40h]
0x18000a5ef  test    rbx, rbx
0x18000a5f2  jz      loc_18000A6F0
0x18000a5f8  mov     rdx, [rsi]; DestinationSize
0x18000a5fb  lea     rsi, [rdx+rbx]
0x18000a5ff  cmp     rbx, rsi
0x18000a602  jz      short loc_18000A642
0x18000a604  mov     r8, [r12+38h]; Source
0x18000a609  test    r8, r8
0x18000a60c  jz      short loc_18000A642
0x18000a60e  cmp     [r8], r13b
0x18000a611  jz      short loc_18000A642
0x18000a613  mov     rax, rbp
0x18000a616  inc     rax
0x18000a619  cmp     [r8+rax], r13b
0x18000a61d  jnz     short loc_18000A616
0x18000a61f  lea     r14, [rax+1]
0x18000a623  cmp     rdx, r14
0x18000a626  jnb     short loc_18000A62E
0x18000a628  mov     [rdi+10h], r13
0x18000a62c  jmp     short loc_18000A64B
0x18000a62e  mov     r9, r14; SourceSize
0x18000a631  mov     rcx, rbx; Destination
0x18000a634  call    memcpy_s
0x18000a639  mov     [rdi+10h], rbx
0x18000a63d  add     rbx, r14
0x18000a640  jmp     short loc_18000A646
0x18000a642  mov     [rdi+10h], r13
0x18000a646  cmp     rbx, rsi
0x18000a649  jz      short loc_18000A692
0x18000a64b  mov     r8, [r12+80h]; Source
0x18000a653  test    r8, r8
0x18000a656  jz      short loc_18000A692
0x18000a658  cmp     [r8], r13b
0x18000a65b  jz      short loc_18000A692
0x18000a65d  mov     rax, rbp
0x18000a660  inc     rax
0x18000a663  cmp     [r8+rax], r13b
0x18000a667  jnz     short loc_18000A660
0x18000a669  mov     rdx, rsi
0x18000a66c  lea     r14, [rax+1]
0x18000a670  sub     rdx, rbx; DestinationSize
0x18000a673  cmp     rdx, r14
0x18000a676  jnb     short loc_18000A67E
0x18000a678  mov     [rdi+20h], r13
0x18000a67c  jmp     short loc_18000A69B
0x18000a67e  mov     r9, r14; SourceSize
0x18000a681  mov     rcx, rbx; Destination
0x18000a684  call    memcpy_s
0x18000a689  mov     [rdi+20h], rbx
0x18000a68d  add     rbx, r14
0x18000a690  jmp     short loc_18000A696
0x18000a692  mov     [rdi+20h], r13
0x18000a696  cmp     rbx, rsi
0x18000a699  jz      short loc_18000A6DC
0x18000a69b  mov     r8, [r12+18h]; Source
0x18000a6a0  test    r8, r8
0x18000a6a3  jz      short loc_18000A6DC
0x18000a6a5  cmp     [r8], r13w
0x18000a6a9  jz      short loc_18000A6DC
0x18000a6ab  inc     rbp
0x18000a6ae  cmp     [r8+rbp*2], r13w
0x18000a6b3  jnz     short loc_18000A6AB
0x18000a6b5  mov     rdx, rsi
0x18000a6b8  lea     r14, ds:2[rbp*2]
0x18000a6c0  sub     rdx, rbx; DestinationSize
0x18000a6c3  cmp     rdx, r14
0x18000a6c6  jb      short loc_18000A6DC
0x18000a6c8  mov     r9, r14; SourceSize
0x18000a6cb  mov     rcx, rbx; Destination
0x18000a6ce  call    memcpy_s
0x18000a6d3  mov     [rdi+38h], rbx
0x18000a6d7  add     rbx, r14
0x18000a6da  jmp     short loc_18000A6E0
0x18000a6dc  mov     [rdi+38h], r13
0x18000a6e0  sub     rsi, rbx
0x18000a6e3  xor     edx, edx; Val
0x18000a6e5  mov     r8, rsi; Size
0x18000a6e8  mov     rcx, rbx; void *
0x18000a6eb  call    memset_0
0x18000a6f0  add     rsp, 28h
0x18000a6f4  pop     r15
0x18000a6f6  pop     r14
0x18000a6f8  pop     r13
0x18000a6fa  pop     r12
0x18000a6fc  pop     rdi
0x18000a6fd  pop     rsi
0x18000a6fe  pop     rbp
0x18000a6ff  pop     rbx
0x18000a700  retn
```
