# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000bba4`
- end: `0x18000bdbd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008fb0`

## callees

- `0x1800043a8`
- `0x18000a2b8`
- `0x18000bba4`
- `0x18000e298`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc8c`

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
0x18000bba4  push    rbx
0x18000bba6  push    rbp
0x18000bba7  push    rsi
0x18000bba8  push    rdi
0x18000bba9  push    r12
0x18000bbab  push    r13
0x18000bbad  push    r14
0x18000bbaf  push    r15
0x18000bbb1  sub     rsp, 28h
0x18000bbb5  mov     [rcx+4], r8d
0x18000bbb9  xor     r13d, r13d
0x18000bbbc  mov     eax, [rdx+8]
0x18000bbbf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000bbc3  mov     [rcx+8], eax
0x18000bbc6  mov     rdi, rcx
0x18000bbc9  mov     [rcx+10h], r13
0x18000bbcd  mov     r12, rdx
0x18000bbd0  movzx   eax, word ptr [rdx+40h]
0x18000bbd4  mov     [rcx+18h], ax
0x18000bbd8  mov     al, [rdx]
0x18000bbda  mov     [rcx+1Ah], al
0x18000bbdd  mov     [rcx+20h], r13
0x18000bbe1  mov     rax, [rdx+88h]
0x18000bbe8  mov     [rcx+28h], rax
0x18000bbec  mov     rax, [rdx+90h]
0x18000bbf3  mov     [rcx+30h], rax
0x18000bbf7  mov     [rcx+38h], r13
0x18000bbfb  mov     rcx, [rdx+38h]
0x18000bbff  lea     edx, [rbp+2]
0x18000bc02  test    rcx, rcx
0x18000bc05  jnz     short loc_18000BC0C
0x18000bc07  mov     r8d, edx
0x18000bc0a  jmp     short loc_18000BC1C
0x18000bc0c  mov     rax, rbp
0x18000bc0f  inc     rax
0x18000bc12  cmp     [rcx+rax], r13b
0x18000bc16  jnz     short loc_18000BC0F
0x18000bc18  lea     r8, [rax+1]; unsigned __int64
0x18000bc1c  mov     rcx, [r12+80h]
0x18000bc24  test    rcx, rcx
0x18000bc27  jz      short loc_18000BC39
0x18000bc29  mov     rax, rbp
0x18000bc2c  inc     rax
0x18000bc2f  cmp     [rcx+rax], r13b
0x18000bc33  jnz     short loc_18000BC2C
0x18000bc35  lea     rdx, [rax+1]
0x18000bc39  mov     rcx, [r12+18h]
0x18000bc3e  test    rcx, rcx
0x18000bc41  jnz     short loc_18000BC48
0x18000bc43  lea     eax, [rcx+2]
0x18000bc46  jmp     short loc_18000BC5D
0x18000bc48  mov     rax, rbp
0x18000bc4b  inc     rax
0x18000bc4e  cmp     [rcx+rax*2], r13w
0x18000bc53  jnz     short loc_18000BC4B
0x18000bc55  lea     rax, ds:2[rax*2]
0x18000bc5d  lea     r14, [rdx+rax]
0x18000bc61  add     r14, r8
0x18000bc64  lea     rsi, [rdi+48h]
0x18000bc68  cmp     [rdi+40h], r13
0x18000bc6c  jz      short loc_18000BC73
0x18000bc6e  cmp     [rsi], r14
0x18000bc71  jnb     short loc_18000BCA7
0x18000bc73  mov     rdx, r14; dwBytes
0x18000bc76  mov     ecx, 8; dwFlags
0x18000bc7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bc80  mov     r15, rax
0x18000bc83  test    rax, rax
0x18000bc86  jz      short loc_18000BCA7
0x18000bc88  mov     rbx, [rdi+40h]
0x18000bc8c  call    cs:__imp_GetProcessHeap
0x18000bc92  mov     r8, rbx; lpMem
0x18000bc95  xor     edx, edx; dwFlags
0x18000bc97  mov     rcx, rax; hHeap
0x18000bc9a  call    cs:__imp_HeapFree
0x18000bca0  mov     [rdi+40h], r15
0x18000bca4  mov     [rsi], r14
0x18000bca7  mov     rbx, [rdi+40h]
0x18000bcab  test    rbx, rbx
0x18000bcae  jz      loc_18000BDAC
0x18000bcb4  mov     rdx, [rsi]; DestinationSize
0x18000bcb7  lea     rsi, [rdx+rbx]
0x18000bcbb  cmp     rbx, rsi
0x18000bcbe  jz      short loc_18000BCFE
0x18000bcc0  mov     r8, [r12+38h]; Source
0x18000bcc5  test    r8, r8
0x18000bcc8  jz      short loc_18000BCFE
0x18000bcca  cmp     [r8], r13b
0x18000bccd  jz      short loc_18000BCFE
0x18000bccf  mov     rax, rbp
0x18000bcd2  inc     rax
0x18000bcd5  cmp     [r8+rax], r13b
0x18000bcd9  jnz     short loc_18000BCD2
0x18000bcdb  lea     r14, [rax+1]
0x18000bcdf  cmp     rdx, r14
0x18000bce2  jnb     short loc_18000BCEA
0x18000bce4  mov     [rdi+10h], r13
0x18000bce8  jmp     short loc_18000BD07
0x18000bcea  mov     r9, r14; SourceSize
0x18000bced  mov     rcx, rbx; Destination
0x18000bcf0  call    memcpy_s
0x18000bcf5  mov     [rdi+10h], rbx
0x18000bcf9  add     rbx, r14
0x18000bcfc  jmp     short loc_18000BD02
0x18000bcfe  mov     [rdi+10h], r13
0x18000bd02  cmp     rbx, rsi
0x18000bd05  jz      short loc_18000BD4E
0x18000bd07  mov     r8, [r12+80h]; Source
0x18000bd0f  test    r8, r8
0x18000bd12  jz      short loc_18000BD4E
0x18000bd14  cmp     [r8], r13b
0x18000bd17  jz      short loc_18000BD4E
0x18000bd19  mov     rax, rbp
0x18000bd1c  inc     rax
0x18000bd1f  cmp     [r8+rax], r13b
0x18000bd23  jnz     short loc_18000BD1C
0x18000bd25  mov     rdx, rsi
0x18000bd28  lea     r14, [rax+1]
0x18000bd2c  sub     rdx, rbx; DestinationSize
0x18000bd2f  cmp     rdx, r14
0x18000bd32  jnb     short loc_18000BD3A
0x18000bd34  mov     [rdi+20h], r13
0x18000bd38  jmp     short loc_18000BD57
0x18000bd3a  mov     r9, r14; SourceSize
0x18000bd3d  mov     rcx, rbx; Destination
0x18000bd40  call    memcpy_s
0x18000bd45  mov     [rdi+20h], rbx
0x18000bd49  add     rbx, r14
0x18000bd4c  jmp     short loc_18000BD52
0x18000bd4e  mov     [rdi+20h], r13
0x18000bd52  cmp     rbx, rsi
0x18000bd55  jz      short loc_18000BD98
0x18000bd57  mov     r8, [r12+18h]; Source
0x18000bd5c  test    r8, r8
0x18000bd5f  jz      short loc_18000BD98
0x18000bd61  cmp     [r8], r13w
0x18000bd65  jz      short loc_18000BD98
0x18000bd67  inc     rbp
0x18000bd6a  cmp     [r8+rbp*2], r13w
0x18000bd6f  jnz     short loc_18000BD67
0x18000bd71  mov     rdx, rsi
0x18000bd74  lea     r14, ds:2[rbp*2]
0x18000bd7c  sub     rdx, rbx; DestinationSize
0x18000bd7f  cmp     rdx, r14
0x18000bd82  jb      short loc_18000BD98
0x18000bd84  mov     r9, r14; SourceSize
0x18000bd87  mov     rcx, rbx; Destination
0x18000bd8a  call    memcpy_s
0x18000bd8f  mov     [rdi+38h], rbx
0x18000bd93  add     rbx, r14
0x18000bd96  jmp     short loc_18000BD9C
0x18000bd98  mov     [rdi+38h], r13
0x18000bd9c  sub     rsi, rbx
0x18000bd9f  xor     edx, edx; Val
0x18000bda1  mov     r8, rsi; Size
0x18000bda4  mov     rcx, rbx; void *
0x18000bda7  call    memset_0
0x18000bdac  add     rsp, 28h
0x18000bdb0  pop     r15
0x18000bdb2  pop     r14
0x18000bdb4  pop     r13
0x18000bdb6  pop     r12
0x18000bdb8  pop     rdi
0x18000bdb9  pop     rsi
0x18000bdba  pop     rbp
0x18000bdbb  pop     rbx
0x18000bdbc  retn
```
