# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006814`
- end: `0x180006a2d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004980`

## callees

- `0x180002158`
- `0x1800062a4`
- `0x180006814`
- `0x180009d44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000690a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000690a`

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
0x180006814  push    rbx
0x180006816  push    rbp
0x180006817  push    rsi
0x180006818  push    rdi
0x180006819  push    r12
0x18000681b  push    r13
0x18000681d  push    r14
0x18000681f  push    r15
0x180006821  sub     rsp, 28h
0x180006825  mov     [rcx+4], r8d
0x180006829  xor     r13d, r13d
0x18000682c  mov     eax, [rdx+8]
0x18000682f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006833  mov     [rcx+8], eax
0x180006836  mov     rdi, rcx
0x180006839  mov     [rcx+10h], r13
0x18000683d  mov     r12, rdx
0x180006840  movzx   eax, word ptr [rdx+40h]
0x180006844  mov     [rcx+18h], ax
0x180006848  mov     al, [rdx]
0x18000684a  mov     [rcx+1Ah], al
0x18000684d  mov     [rcx+20h], r13
0x180006851  mov     rax, [rdx+88h]
0x180006858  mov     [rcx+28h], rax
0x18000685c  mov     rax, [rdx+90h]
0x180006863  mov     [rcx+30h], rax
0x180006867  mov     [rcx+38h], r13
0x18000686b  mov     rcx, [rdx+38h]
0x18000686f  lea     edx, [rbp+2]
0x180006872  test    rcx, rcx
0x180006875  jnz     short loc_18000687C
0x180006877  mov     r8d, edx
0x18000687a  jmp     short loc_18000688C
0x18000687c  mov     rax, rbp
0x18000687f  inc     rax
0x180006882  cmp     [rcx+rax], r13b
0x180006886  jnz     short loc_18000687F
0x180006888  lea     r8, [rax+1]; unsigned __int64
0x18000688c  mov     rcx, [r12+80h]
0x180006894  test    rcx, rcx
0x180006897  jz      short loc_1800068A9
0x180006899  mov     rax, rbp
0x18000689c  inc     rax
0x18000689f  cmp     [rcx+rax], r13b
0x1800068a3  jnz     short loc_18000689C
0x1800068a5  lea     rdx, [rax+1]
0x1800068a9  mov     rcx, [r12+18h]
0x1800068ae  test    rcx, rcx
0x1800068b1  jnz     short loc_1800068B8
0x1800068b3  lea     eax, [rcx+2]
0x1800068b6  jmp     short loc_1800068CD
0x1800068b8  mov     rax, rbp
0x1800068bb  inc     rax
0x1800068be  cmp     [rcx+rax*2], r13w
0x1800068c3  jnz     short loc_1800068BB
0x1800068c5  lea     rax, ds:2[rax*2]
0x1800068cd  lea     r14, [rdx+rax]
0x1800068d1  add     r14, r8
0x1800068d4  lea     rsi, [rdi+48h]
0x1800068d8  cmp     [rdi+40h], r13
0x1800068dc  jz      short loc_1800068E3
0x1800068de  cmp     [rsi], r14
0x1800068e1  jnb     short loc_180006917
0x1800068e3  mov     rdx, r14; dwBytes
0x1800068e6  mov     ecx, 8; dwFlags
0x1800068eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068f0  mov     r15, rax
0x1800068f3  test    rax, rax
0x1800068f6  jz      short loc_180006917
0x1800068f8  mov     rbx, [rdi+40h]
0x1800068fc  call    cs:__imp_GetProcessHeap
0x180006902  mov     r8, rbx; lpMem
0x180006905  xor     edx, edx; dwFlags
0x180006907  mov     rcx, rax; hHeap
0x18000690a  call    cs:__imp_HeapFree
0x180006910  mov     [rdi+40h], r15
0x180006914  mov     [rsi], r14
0x180006917  mov     rbx, [rdi+40h]
0x18000691b  test    rbx, rbx
0x18000691e  jz      loc_180006A1C
0x180006924  mov     rdx, [rsi]; DestinationSize
0x180006927  lea     rsi, [rdx+rbx]
0x18000692b  cmp     rbx, rsi
0x18000692e  jz      short loc_18000696E
0x180006930  mov     r8, [r12+38h]; Source
0x180006935  test    r8, r8
0x180006938  jz      short loc_18000696E
0x18000693a  cmp     [r8], r13b
0x18000693d  jz      short loc_18000696E
0x18000693f  mov     rax, rbp
0x180006942  inc     rax
0x180006945  cmp     [r8+rax], r13b
0x180006949  jnz     short loc_180006942
0x18000694b  lea     r14, [rax+1]
0x18000694f  cmp     rdx, r14
0x180006952  jnb     short loc_18000695A
0x180006954  mov     [rdi+10h], r13
0x180006958  jmp     short loc_180006977
0x18000695a  mov     r9, r14; SourceSize
0x18000695d  mov     rcx, rbx; Destination
0x180006960  call    memcpy_s
0x180006965  mov     [rdi+10h], rbx
0x180006969  add     rbx, r14
0x18000696c  jmp     short loc_180006972
0x18000696e  mov     [rdi+10h], r13
0x180006972  cmp     rbx, rsi
0x180006975  jz      short loc_1800069BE
0x180006977  mov     r8, [r12+80h]; Source
0x18000697f  test    r8, r8
0x180006982  jz      short loc_1800069BE
0x180006984  cmp     [r8], r13b
0x180006987  jz      short loc_1800069BE
0x180006989  mov     rax, rbp
0x18000698c  inc     rax
0x18000698f  cmp     [r8+rax], r13b
0x180006993  jnz     short loc_18000698C
0x180006995  mov     rdx, rsi
0x180006998  lea     r14, [rax+1]
0x18000699c  sub     rdx, rbx; DestinationSize
0x18000699f  cmp     rdx, r14
0x1800069a2  jnb     short loc_1800069AA
0x1800069a4  mov     [rdi+20h], r13
0x1800069a8  jmp     short loc_1800069C7
0x1800069aa  mov     r9, r14; SourceSize
0x1800069ad  mov     rcx, rbx; Destination
0x1800069b0  call    memcpy_s
0x1800069b5  mov     [rdi+20h], rbx
0x1800069b9  add     rbx, r14
0x1800069bc  jmp     short loc_1800069C2
0x1800069be  mov     [rdi+20h], r13
0x1800069c2  cmp     rbx, rsi
0x1800069c5  jz      short loc_180006A08
0x1800069c7  mov     r8, [r12+18h]; Source
0x1800069cc  test    r8, r8
0x1800069cf  jz      short loc_180006A08
0x1800069d1  cmp     [r8], r13w
0x1800069d5  jz      short loc_180006A08
0x1800069d7  inc     rbp
0x1800069da  cmp     [r8+rbp*2], r13w
0x1800069df  jnz     short loc_1800069D7
0x1800069e1  mov     rdx, rsi
0x1800069e4  lea     r14, ds:2[rbp*2]
0x1800069ec  sub     rdx, rbx; DestinationSize
0x1800069ef  cmp     rdx, r14
0x1800069f2  jb      short loc_180006A08
0x1800069f4  mov     r9, r14; SourceSize
0x1800069f7  mov     rcx, rbx; Destination
0x1800069fa  call    memcpy_s
0x1800069ff  mov     [rdi+38h], rbx
0x180006a03  add     rbx, r14
0x180006a06  jmp     short loc_180006A0C
0x180006a08  mov     [rdi+38h], r13
0x180006a0c  sub     rsi, rbx
0x180006a0f  xor     edx, edx; Val
0x180006a11  mov     r8, rsi; Size
0x180006a14  mov     rcx, rbx; void *
0x180006a17  call    memset_0
0x180006a1c  add     rsp, 28h
0x180006a20  pop     r15
0x180006a22  pop     r14
0x180006a24  pop     r13
0x180006a26  pop     r12
0x180006a28  pop     rdi
0x180006a29  pop     rsi
0x180006a2a  pop     rbp
0x180006a2b  pop     rbx
0x180006a2c  retn
```
