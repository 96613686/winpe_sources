# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800068d8`
- end: `0x180006af1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004270`

## callees

- `0x180001ef0`
- `0x1800053f8`
- `0x1800068d8`
- `0x180007de8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c0`

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
0x1800068d8  push    rbx
0x1800068da  push    rbp
0x1800068db  push    rsi
0x1800068dc  push    rdi
0x1800068dd  push    r12
0x1800068df  push    r13
0x1800068e1  push    r14
0x1800068e3  push    r15
0x1800068e5  sub     rsp, 28h
0x1800068e9  mov     [rcx+4], r8d
0x1800068ed  xor     r13d, r13d
0x1800068f0  mov     eax, [rdx+8]
0x1800068f3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800068f7  mov     [rcx+8], eax
0x1800068fa  mov     rdi, rcx
0x1800068fd  mov     [rcx+10h], r13
0x180006901  mov     r12, rdx
0x180006904  movzx   eax, word ptr [rdx+40h]
0x180006908  mov     [rcx+18h], ax
0x18000690c  mov     al, [rdx]
0x18000690e  mov     [rcx+1Ah], al
0x180006911  mov     [rcx+20h], r13
0x180006915  mov     rax, [rdx+88h]
0x18000691c  mov     [rcx+28h], rax
0x180006920  mov     rax, [rdx+90h]
0x180006927  mov     [rcx+30h], rax
0x18000692b  mov     [rcx+38h], r13
0x18000692f  mov     rcx, [rdx+38h]
0x180006933  lea     edx, [rbp+2]
0x180006936  test    rcx, rcx
0x180006939  jnz     short loc_180006940
0x18000693b  mov     r8d, edx
0x18000693e  jmp     short loc_180006950
0x180006940  mov     rax, rbp
0x180006943  inc     rax
0x180006946  cmp     [rcx+rax], r13b
0x18000694a  jnz     short loc_180006943
0x18000694c  lea     r8, [rax+1]; unsigned __int64
0x180006950  mov     rcx, [r12+80h]
0x180006958  test    rcx, rcx
0x18000695b  jz      short loc_18000696D
0x18000695d  mov     rax, rbp
0x180006960  inc     rax
0x180006963  cmp     [rcx+rax], r13b
0x180006967  jnz     short loc_180006960
0x180006969  lea     rdx, [rax+1]
0x18000696d  mov     rcx, [r12+18h]
0x180006972  test    rcx, rcx
0x180006975  jnz     short loc_18000697C
0x180006977  lea     eax, [rcx+2]
0x18000697a  jmp     short loc_180006991
0x18000697c  mov     rax, rbp
0x18000697f  inc     rax
0x180006982  cmp     [rcx+rax*2], r13w
0x180006987  jnz     short loc_18000697F
0x180006989  lea     rax, ds:2[rax*2]
0x180006991  lea     r14, [rdx+rax]
0x180006995  add     r14, r8
0x180006998  lea     rsi, [rdi+48h]
0x18000699c  cmp     [rdi+40h], r13
0x1800069a0  jz      short loc_1800069A7
0x1800069a2  cmp     [rsi], r14
0x1800069a5  jnb     short loc_1800069DB
0x1800069a7  mov     rdx, r14; dwBytes
0x1800069aa  mov     ecx, 8; dwFlags
0x1800069af  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800069b4  mov     r15, rax
0x1800069b7  test    rax, rax
0x1800069ba  jz      short loc_1800069DB
0x1800069bc  mov     rbx, [rdi+40h]
0x1800069c0  call    cs:__imp_GetProcessHeap
0x1800069c6  mov     r8, rbx; lpMem
0x1800069c9  xor     edx, edx; dwFlags
0x1800069cb  mov     rcx, rax; hHeap
0x1800069ce  call    cs:__imp_HeapFree
0x1800069d4  mov     [rdi+40h], r15
0x1800069d8  mov     [rsi], r14
0x1800069db  mov     rbx, [rdi+40h]
0x1800069df  test    rbx, rbx
0x1800069e2  jz      loc_180006AE0
0x1800069e8  mov     rdx, [rsi]; DestinationSize
0x1800069eb  lea     rsi, [rdx+rbx]
0x1800069ef  cmp     rbx, rsi
0x1800069f2  jz      short loc_180006A32
0x1800069f4  mov     r8, [r12+38h]; Source
0x1800069f9  test    r8, r8
0x1800069fc  jz      short loc_180006A32
0x1800069fe  cmp     [r8], r13b
0x180006a01  jz      short loc_180006A32
0x180006a03  mov     rax, rbp
0x180006a06  inc     rax
0x180006a09  cmp     [r8+rax], r13b
0x180006a0d  jnz     short loc_180006A06
0x180006a0f  lea     r14, [rax+1]
0x180006a13  cmp     rdx, r14
0x180006a16  jnb     short loc_180006A1E
0x180006a18  mov     [rdi+10h], r13
0x180006a1c  jmp     short loc_180006A3B
0x180006a1e  mov     r9, r14; SourceSize
0x180006a21  mov     rcx, rbx; Destination
0x180006a24  call    memcpy_s
0x180006a29  mov     [rdi+10h], rbx
0x180006a2d  add     rbx, r14
0x180006a30  jmp     short loc_180006A36
0x180006a32  mov     [rdi+10h], r13
0x180006a36  cmp     rbx, rsi
0x180006a39  jz      short loc_180006A82
0x180006a3b  mov     r8, [r12+80h]; Source
0x180006a43  test    r8, r8
0x180006a46  jz      short loc_180006A82
0x180006a48  cmp     [r8], r13b
0x180006a4b  jz      short loc_180006A82
0x180006a4d  mov     rax, rbp
0x180006a50  inc     rax
0x180006a53  cmp     [r8+rax], r13b
0x180006a57  jnz     short loc_180006A50
0x180006a59  mov     rdx, rsi
0x180006a5c  lea     r14, [rax+1]
0x180006a60  sub     rdx, rbx; DestinationSize
0x180006a63  cmp     rdx, r14
0x180006a66  jnb     short loc_180006A6E
0x180006a68  mov     [rdi+20h], r13
0x180006a6c  jmp     short loc_180006A8B
0x180006a6e  mov     r9, r14; SourceSize
0x180006a71  mov     rcx, rbx; Destination
0x180006a74  call    memcpy_s
0x180006a79  mov     [rdi+20h], rbx
0x180006a7d  add     rbx, r14
0x180006a80  jmp     short loc_180006A86
0x180006a82  mov     [rdi+20h], r13
0x180006a86  cmp     rbx, rsi
0x180006a89  jz      short loc_180006ACC
0x180006a8b  mov     r8, [r12+18h]; Source
0x180006a90  test    r8, r8
0x180006a93  jz      short loc_180006ACC
0x180006a95  cmp     [r8], r13w
0x180006a99  jz      short loc_180006ACC
0x180006a9b  inc     rbp
0x180006a9e  cmp     [r8+rbp*2], r13w
0x180006aa3  jnz     short loc_180006A9B
0x180006aa5  mov     rdx, rsi
0x180006aa8  lea     r14, ds:2[rbp*2]
0x180006ab0  sub     rdx, rbx; DestinationSize
0x180006ab3  cmp     rdx, r14
0x180006ab6  jb      short loc_180006ACC
0x180006ab8  mov     r9, r14; SourceSize
0x180006abb  mov     rcx, rbx; Destination
0x180006abe  call    memcpy_s
0x180006ac3  mov     [rdi+38h], rbx
0x180006ac7  add     rbx, r14
0x180006aca  jmp     short loc_180006AD0
0x180006acc  mov     [rdi+38h], r13
0x180006ad0  sub     rsi, rbx
0x180006ad3  xor     edx, edx; Val
0x180006ad5  mov     r8, rsi; Size
0x180006ad8  mov     rcx, rbx; void *
0x180006adb  call    memset_0
0x180006ae0  add     rsp, 28h
0x180006ae4  pop     r15
0x180006ae6  pop     r14
0x180006ae8  pop     r13
0x180006aea  pop     r12
0x180006aec  pop     rdi
0x180006aed  pop     rsi
0x180006aee  pop     rbp
0x180006aef  pop     rbx
0x180006af0  retn
```
