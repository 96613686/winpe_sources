# Helper::FilterSpecFromMultiSz(ushort const *,wistd::unique_ptr<_COMDLG_FILTERSPEC [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &,uint *)

- ea: `0x180013ef8`
- end: `0x180014027`
- name: `?FilterSpecFromMultiSz@Helper@@YAJPEBGAEAV?$unique_ptr@$$BY0A@U_COMDLG_FILTERSPEC@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@PEAI@Z`
- size: `303`
- prototype: `__int64 __fastcall(_WORD *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014b78`

## callees

- `0x1800099f8`
- `0x180013ef8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180013fa2`
- `KERNEL32!LocalFree` at `0x180013fa2`
- `KERNEL32!LocalAlloc` at `0x180013f71`
- `KERNEL32!LocalAlloc` at `0x180013f71`

## pseudocode

```c
__int64 __fastcall Helper::FilterSpecFromMultiSz(_WORD *a1, void **a2, unsigned int *a3)
{
  _WORD *v5; // rbx
  unsigned int v6; // edi
  _WORD *v7; // rax
  __int64 v8; // rcx
  _WORD *v9; // rdx
  __int64 v10; // rax
  _WORD *v11; // rdx
  SIZE_T v12; // rsi
  char *v13; // rax
  char *i; // rcx
  void *v15; // rcx
  unsigned int j; // ecx
  __int64 v17; // rax
  _WORD *v18; // r8
  __int64 v19; // rax
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  v5 = a1;
  v6 = 0;
  if ( !a1 )
    goto LABEL_21;
  v7 = a1;
  if ( !*a1 )
    goto LABEL_21;
  do
  {
    ++v6;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = v7 + 1;
    v10 = -1;
    v11 = &v9[v8];
    do
      ++v10;
    while ( v11[v10] );
    v7 = &v11[v10 + 1];
  }
  while ( *v7 );
  if ( !v6 )
    goto LABEL_21;
  v12 = 16LL * v6;
  v13 = (char *)LocalAlloc(0, v12);
  if ( v13 )
  {
    for ( i = v13; i != &v13[v12]; i += 16 )
      *(_OWORD *)i = 0;
  }
  v15 = *a2;
  *a2 = v13;
  if ( v15 )
    LocalFree(v15);
  if ( *a2 )
  {
    for ( j = 0; j < v6; ++j )
    {
      *((_QWORD *)*a2 + 2 * j) = v5;
      v17 = -1;
      do
        ++v17;
      while ( v5[v17] );
      v18 = &v5[v17 + 1];
      *((_QWORD *)*a2 + 2 * j + 1) = v18;
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
      v5 = &v18[v19 + 1];
    }
LABEL_21:
    *a3 = v6;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E5,
    (unsigned int)"clientcore\\windows\\core\\ntgdi\\icm\\colorui\\ui\\helper.cpp",
    (const char *)0x8007000ELL,
    v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180013ef8  push    rbx
0x180013efa  push    rbp
0x180013efb  push    rsi
0x180013efc  push    rdi
0x180013efd  push    r12
0x180013eff  push    r14
0x180013f01  push    r15; int
0x180013f03  sub     rsp, 20h
0x180013f07  xor     ebp, ebp
0x180013f09  mov     r15, r8
0x180013f0c  mov     [r8], ebp
0x180013f0f  mov     r14, rdx
0x180013f12  mov     rbx, rcx
0x180013f15  mov     edi, ebp
0x180013f17  test    rcx, rcx
0x180013f1a  jz      loc_180013FF1
0x180013f20  mov     rax, rcx
0x180013f23  cmp     [rcx], bp
0x180013f26  jz      loc_180013FF1
0x180013f2c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180013f30  inc     edi
0x180013f32  mov     rcx, r12
0x180013f35  inc     rcx
0x180013f38  cmp     [rax+rcx*2], bp
0x180013f3c  jnz     short loc_180013F35
0x180013f3e  lea     rdx, [rax+2]
0x180013f42  mov     rax, r12
0x180013f45  lea     rdx, [rdx+rcx*2]
0x180013f49  inc     rax
0x180013f4c  cmp     [rdx+rax*2], bp
0x180013f50  jnz     short loc_180013F49
0x180013f52  inc     rax
0x180013f55  lea     rax, [rdx+rax*2]
0x180013f59  cmp     [rax], bp
0x180013f5c  jnz     short loc_180013F30
0x180013f5e  test    edi, edi
0x180013f60  jz      loc_180013FF1
0x180013f66  mov     esi, edi
0x180013f68  xor     ecx, ecx; uFlags
0x180013f6a  shl     rsi, 4
0x180013f6e  mov     rdx, rsi; uBytes
0x180013f71  call    cs:__imp_LocalAlloc
0x180013f77  test    rax, rax
0x180013f7a  jz      short loc_180013F97
0x180013f7c  lea     rdx, [rsi+rax]
0x180013f80  mov     rcx, rax
0x180013f83  cmp     rax, rdx
0x180013f86  jz      short loc_180013F97
0x180013f88  xorps   xmm0, xmm0
0x180013f8b  movups  xmmword ptr [rcx], xmm0
0x180013f8e  add     rcx, 10h
0x180013f92  cmp     rcx, rdx
0x180013f95  jnz     short loc_180013F88
0x180013f97  mov     rcx, [r14]; hMem
0x180013f9a  mov     [r14], rax
0x180013f9d  test    rcx, rcx
0x180013fa0  jz      short loc_180013FA8
0x180013fa2  call    cs:__imp_LocalFree
0x180013fa8  cmp     [r14], rbp
0x180013fab  jz      short loc_180014005
0x180013fad  mov     ecx, ebp
0x180013faf  mov     rax, [r14]
0x180013fb2  mov     edx, ecx
0x180013fb4  add     rdx, rdx
0x180013fb7  mov     [rax+rdx*8], rbx
0x180013fbb  mov     rax, r12
0x180013fbe  inc     rax
0x180013fc1  cmp     [rbx+rax*2], bp
0x180013fc5  jnz     short loc_180013FBE
0x180013fc7  inc     rax
0x180013fca  lea     r8, [rbx+rax*2]
0x180013fce  mov     rax, [r14]
0x180013fd1  mov     [rax+rdx*8+8], r8
0x180013fd6  mov     rax, r12
0x180013fd9  inc     rax
0x180013fdc  cmp     [r8+rax*2], bp
0x180013fe1  jnz     short loc_180013FD9
0x180013fe3  inc     ecx
0x180013fe5  lea     rbx, [rax+1]
0x180013fe9  lea     rbx, [r8+rbx*2]
0x180013fed  cmp     ecx, edi
0x180013fef  jb      short loc_180013FAF
0x180013ff1  mov     [r15], edi
0x180013ff4  xor     eax, eax
0x180013ff6  add     rsp, 20h
0x180013ffa  pop     r15
0x180013ffc  pop     r14
0x180013ffe  pop     r12
0x180014000  pop     rdi
0x180014001  pop     rsi
0x180014002  pop     rbp
0x180014003  pop     rbx
0x180014004  retn
0x180014005  mov     rcx, [rsp+58h]; this
0x18001400a  lea     r8, aClientcoreWind; "clientcore\\windows\\core\\ntgdi\\icm\\"...
0x180014011  mov     ebx, 8007000Eh
0x180014016  mov     edx, 1E5h; void *
0x18001401b  mov     r9d, ebx; char *
0x18001401e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014023  mov     eax, ebx
0x180014025  jmp     short loc_180013FF6
```
