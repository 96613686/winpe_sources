# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140009854`
- end: `0x140009a6d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140006e70`

## callees

- `0x140003168`
- `0x1400083f8`
- `0x140009854`
- `0x14000c160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000993c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000993c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000994a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000994a`

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
0x140009854  push    rbx
0x140009856  push    rbp
0x140009857  push    rsi
0x140009858  push    rdi
0x140009859  push    r12
0x14000985b  push    r13
0x14000985d  push    r14
0x14000985f  push    r15
0x140009861  sub     rsp, 28h
0x140009865  mov     [rcx+4], r8d
0x140009869  xor     r13d, r13d
0x14000986c  mov     eax, [rdx+8]
0x14000986f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140009873  mov     [rcx+8], eax
0x140009876  mov     rdi, rcx
0x140009879  mov     [rcx+10h], r13
0x14000987d  mov     r12, rdx
0x140009880  movzx   eax, word ptr [rdx+40h]
0x140009884  mov     [rcx+18h], ax
0x140009888  mov     al, [rdx]
0x14000988a  mov     [rcx+1Ah], al
0x14000988d  mov     [rcx+20h], r13
0x140009891  mov     rax, [rdx+88h]
0x140009898  mov     [rcx+28h], rax
0x14000989c  mov     rax, [rdx+90h]
0x1400098a3  mov     [rcx+30h], rax
0x1400098a7  mov     [rcx+38h], r13
0x1400098ab  mov     rcx, [rdx+38h]
0x1400098af  lea     edx, [rbp+2]
0x1400098b2  test    rcx, rcx
0x1400098b5  jnz     short loc_1400098BC
0x1400098b7  mov     r8d, edx
0x1400098ba  jmp     short loc_1400098CC
0x1400098bc  mov     rax, rbp
0x1400098bf  inc     rax
0x1400098c2  cmp     [rcx+rax], r13b
0x1400098c6  jnz     short loc_1400098BF
0x1400098c8  lea     r8, [rax+1]; unsigned __int64
0x1400098cc  mov     rcx, [r12+80h]
0x1400098d4  test    rcx, rcx
0x1400098d7  jz      short loc_1400098E9
0x1400098d9  mov     rax, rbp
0x1400098dc  inc     rax
0x1400098df  cmp     [rcx+rax], r13b
0x1400098e3  jnz     short loc_1400098DC
0x1400098e5  lea     rdx, [rax+1]
0x1400098e9  mov     rcx, [r12+18h]
0x1400098ee  test    rcx, rcx
0x1400098f1  jnz     short loc_1400098F8
0x1400098f3  lea     eax, [rcx+2]
0x1400098f6  jmp     short loc_14000990D
0x1400098f8  mov     rax, rbp
0x1400098fb  inc     rax
0x1400098fe  cmp     [rcx+rax*2], r13w
0x140009903  jnz     short loc_1400098FB
0x140009905  lea     rax, ds:2[rax*2]
0x14000990d  lea     r14, [rdx+rax]
0x140009911  add     r14, r8
0x140009914  lea     rsi, [rdi+48h]
0x140009918  cmp     [rdi+40h], r13
0x14000991c  jz      short loc_140009923
0x14000991e  cmp     [rsi], r14
0x140009921  jnb     short loc_140009957
0x140009923  mov     rdx, r14; dwBytes
0x140009926  mov     ecx, 8; dwFlags
0x14000992b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009930  mov     r15, rax
0x140009933  test    rax, rax
0x140009936  jz      short loc_140009957
0x140009938  mov     rbx, [rdi+40h]
0x14000993c  call    cs:__imp_GetProcessHeap
0x140009942  mov     r8, rbx; lpMem
0x140009945  xor     edx, edx; dwFlags
0x140009947  mov     rcx, rax; hHeap
0x14000994a  call    cs:__imp_HeapFree
0x140009950  mov     [rdi+40h], r15
0x140009954  mov     [rsi], r14
0x140009957  mov     rbx, [rdi+40h]
0x14000995b  test    rbx, rbx
0x14000995e  jz      loc_140009A5C
0x140009964  mov     rdx, [rsi]; DestinationSize
0x140009967  lea     rsi, [rdx+rbx]
0x14000996b  cmp     rbx, rsi
0x14000996e  jz      short loc_1400099AE
0x140009970  mov     r8, [r12+38h]; Source
0x140009975  test    r8, r8
0x140009978  jz      short loc_1400099AE
0x14000997a  cmp     [r8], r13b
0x14000997d  jz      short loc_1400099AE
0x14000997f  mov     rax, rbp
0x140009982  inc     rax
0x140009985  cmp     [r8+rax], r13b
0x140009989  jnz     short loc_140009982
0x14000998b  lea     r14, [rax+1]
0x14000998f  cmp     rdx, r14
0x140009992  jnb     short loc_14000999A
0x140009994  mov     [rdi+10h], r13
0x140009998  jmp     short loc_1400099B7
0x14000999a  mov     r9, r14; SourceSize
0x14000999d  mov     rcx, rbx; Destination
0x1400099a0  call    memcpy_s
0x1400099a5  mov     [rdi+10h], rbx
0x1400099a9  add     rbx, r14
0x1400099ac  jmp     short loc_1400099B2
0x1400099ae  mov     [rdi+10h], r13
0x1400099b2  cmp     rbx, rsi
0x1400099b5  jz      short loc_1400099FE
0x1400099b7  mov     r8, [r12+80h]; Source
0x1400099bf  test    r8, r8
0x1400099c2  jz      short loc_1400099FE
0x1400099c4  cmp     [r8], r13b
0x1400099c7  jz      short loc_1400099FE
0x1400099c9  mov     rax, rbp
0x1400099cc  inc     rax
0x1400099cf  cmp     [r8+rax], r13b
0x1400099d3  jnz     short loc_1400099CC
0x1400099d5  mov     rdx, rsi
0x1400099d8  lea     r14, [rax+1]
0x1400099dc  sub     rdx, rbx; DestinationSize
0x1400099df  cmp     rdx, r14
0x1400099e2  jnb     short loc_1400099EA
0x1400099e4  mov     [rdi+20h], r13
0x1400099e8  jmp     short loc_140009A07
0x1400099ea  mov     r9, r14; SourceSize
0x1400099ed  mov     rcx, rbx; Destination
0x1400099f0  call    memcpy_s
0x1400099f5  mov     [rdi+20h], rbx
0x1400099f9  add     rbx, r14
0x1400099fc  jmp     short loc_140009A02
0x1400099fe  mov     [rdi+20h], r13
0x140009a02  cmp     rbx, rsi
0x140009a05  jz      short loc_140009A48
0x140009a07  mov     r8, [r12+18h]; Source
0x140009a0c  test    r8, r8
0x140009a0f  jz      short loc_140009A48
0x140009a11  cmp     [r8], r13w
0x140009a15  jz      short loc_140009A48
0x140009a17  inc     rbp
0x140009a1a  cmp     [r8+rbp*2], r13w
0x140009a1f  jnz     short loc_140009A17
0x140009a21  mov     rdx, rsi
0x140009a24  lea     r14, ds:2[rbp*2]
0x140009a2c  sub     rdx, rbx; DestinationSize
0x140009a2f  cmp     rdx, r14
0x140009a32  jb      short loc_140009A48
0x140009a34  mov     r9, r14; SourceSize
0x140009a37  mov     rcx, rbx; Destination
0x140009a3a  call    memcpy_s
0x140009a3f  mov     [rdi+38h], rbx
0x140009a43  add     rbx, r14
0x140009a46  jmp     short loc_140009A4C
0x140009a48  mov     [rdi+38h], r13
0x140009a4c  sub     rsi, rbx
0x140009a4f  xor     edx, edx; Val
0x140009a51  mov     r8, rsi; Size
0x140009a54  mov     rcx, rbx; void *
0x140009a57  call    memset_0
0x140009a5c  add     rsp, 28h
0x140009a60  pop     r15
0x140009a62  pop     r14
0x140009a64  pop     r13
0x140009a66  pop     r12
0x140009a68  pop     rdi
0x140009a69  pop     rsi
0x140009a6a  pop     rbp
0x140009a6b  pop     rbx
0x140009a6c  retn
```
