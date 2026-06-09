# NOTIFICATION_CONTEXT::GenerateCachedModuleList(CACHED_MODULE_LIST *)

- ea: `0x1800128b0`
- end: `0x180012b17`
- name: `?GenerateCachedModuleList@NOTIFICATION_CONTEXT@@SAJPEAUCACHED_MODULE_LIST@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(struct CACHED_MODULE_LIST *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bfe0`
- `0x18001c6fc`

## callees

- `0x1800128b0`
- `0x18003439a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012930`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012985`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800129ea`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012ab0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012930`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012985`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800129ea`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180012ab0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012902`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800129bd`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800129da`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012a87`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012aa0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012902`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800129bd`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800129da`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012a87`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180012aa0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800128c9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800129c9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180012a93`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800128c9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800129c9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180012a93`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_CONTEXT::GenerateCachedModuleList(struct CACHED_MODULE_LIST *a1)
{
  BUFFER *v1; // rbx
  __int64 result; // rax
  __int64 v4; // rbp
  char *v5; // rsi
  unsigned int v6; // r14d
  unsigned int v7; // r13d
  char *Ptr; // rdx
  unsigned int i; // r15d
  __int64 v10; // r12
  unsigned int v11; // eax
  __int64 j; // rsi
  _QWORD *v13; // rax
  __int64 v14; // rdx
  unsigned int Size; // eax
  unsigned int k; // r9d
  unsigned int *v17; // rax
  __int64 v18; // rax
  bool v19; // zf
  char *v20; // rdx
  unsigned int v21; // eax
  char *v22; // rax
  char *v23; // r8
  int v24; // ecx
  int v25; // [rsp+60h] [rbp+8h]
  unsigned int v26; // [rsp+68h] [rbp+10h]
  char *v27; // [rsp+70h] [rbp+18h]

  v1 = (struct CACHED_MODULE_LIST *)((char *)a1 + 128);
  if ( !BUFFER::Resize((struct CACHED_MODULE_LIST *)((char *)a1 + 128), 0x400u) )
    return 2147942408LL;
  v4 = 0;
  v5 = (char *)a1 + 184;
  v6 = BUFFER::QuerySize(v1) >> 2;
  memset_0((char *)a1 + 184, 0, 0x100u);
  v26 = *((_DWORD *)a1 + 12);
  v25 = 1;
  v7 = 0;
  Ptr = (char *)BUFFER::QueryPtr(v1);
  v27 = Ptr;
LABEL_4:
  if ( v7 < 0x20 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
        v25 *= 2;
        ++v7;
        goto LABEL_4;
      }
      v10 = 0;
      *(_DWORD *)&v5[8 * v7 + 4 * i] = v4;
      v11 = v26;
      while ( (unsigned int)v10 < 5 )
      {
        for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
        {
          v13 = BUFFER::QueryPtr(a1);
          v14 = 112;
          if ( i )
            v14 = 132;
          if ( (v25 & *(_DWORD *)(v13[j] + v14 + 4 * v10)) != 0 )
          {
            *(_DWORD *)&v27[4 * v4] = j;
            v4 = (unsigned int)(v4 + 1);
            if ( (_DWORD)v4 == v6 )
            {
              Size = BUFFER::QuerySize(v1);
              if ( !BUFFER::Resize(v1, 2 * Size) )
                return 2147942408LL;
              v6 = BUFFER::QuerySize(v1) >> 2;
              v27 = (char *)BUFFER::QueryPtr(v1);
            }
          }
          v11 = v26;
        }
        v10 = (unsigned int)(v10 + 1);
      }
      Ptr = v27;
      *(_DWORD *)&v27[4 * v4] = -1;
      v4 = (unsigned int)(v4 + 1);
      if ( (_DWORD)v4 == v6 )
      {
        v21 = BUFFER::QuerySize(v1);
        if ( !BUFFER::Resize(v1, 2 * v21) )
          return 2147942408LL;
        v6 = BUFFER::QuerySize(v1) >> 2;
        Ptr = (char *)BUFFER::QueryPtr(v1);
        v27 = Ptr;
      }
      v5 = (char *)a1 + 184;
    }
  }
  for ( k = 0; k < 2; ++k )
  {
    v17 = (unsigned int *)(v5 + 232);
    if ( k )
      v17 = (unsigned int *)(v5 + 236);
    v18 = *v17;
    v19 = *(_DWORD *)&Ptr[4 * v18] == -1;
    v20 = &Ptr[4 * v18];
    if ( !v19 )
    {
      v22 = v20;
      do
      {
        v23 = v22;
        v22 += 4;
      }
      while ( *(_DWORD *)v22 != -1 );
      for ( ; v20 < v23; v23 -= 4 )
      {
        v24 = *(_DWORD *)v20;
        *(_DWORD *)v20 = *(_DWORD *)v23;
        v20 += 4;
        *(_DWORD *)v23 = v24;
      }
    }
    Ptr = v27;
  }
  *((_DWORD *)a1 + 45) = v4;
  result = 0;
  *((_DWORD *)a1 + 44) = 1;
  return result;
}

```

## disassembly

```asm
0x1800128b0  push    rbx
0x1800128b2  push    rdi
0x1800128b3  sub     rsp, 48h
0x1800128b7  lea     rbx, [rcx+80h]
0x1800128be  mov     rdi, rcx
0x1800128c1  mov     rcx, rbx
0x1800128c4  mov     edx, 400h
0x1800128c9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800128cf  test    al, al
0x1800128d1  jnz     short loc_1800128DF
0x1800128d3  mov     eax, 80070008h
0x1800128d8  add     rsp, 48h
0x1800128dc  pop     rdi
0x1800128dd  pop     rbx
0x1800128de  retn
0x1800128df  mov     [rsp+58h+arg_18], rbp
0x1800128e4  mov     rcx, rbx
0x1800128e7  mov     [rsp+58h+var_18], rsi
0x1800128ec  xor     ebp, ebp
0x1800128ee  mov     [rsp+58h+var_20], r12
0x1800128f3  mov     [rsp+58h+var_28], r13
0x1800128f8  mov     [rsp+58h+var_30], r14
0x1800128fd  mov     [rsp+58h+var_38], r15
0x180012902  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180012908  lea     rsi, [rdi+0B8h]
0x18001290f  xor     edx, edx; Val
0x180012911  mov     r14d, eax
0x180012914  mov     r8d, 100h; Size
0x18001291a  mov     rcx, rsi; void *
0x18001291d  shr     r14d, 2
0x180012921  call    memset_0
0x180012926  mov     eax, [rdi+30h]
0x180012929  mov     rcx, rbx
0x18001292c  mov     [rsp+58h+arg_8], eax
0x180012930  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180012936  mov     [rsp+58h+arg_0], 1
0x18001293e  xor     r13d, r13d
0x180012941  mov     rdx, rax
0x180012944  mov     [rsp+58h+arg_10], rax
0x180012949  cmp     r13d, 20h ; ' '
0x18001294d  jnb     loc_180012A00
0x180012953  xor     r15d, r15d
0x180012956  cmp     r15d, 2
0x18001295a  jnb     loc_180012ACD
0x180012960  lea     eax, [r15+r13*2]
0x180012964  xor     r12d, r12d
0x180012967  mov     [rsi+rax*4], ebp
0x18001296a  mov     eax, [rsp+58h+arg_8]
0x18001296e  cmp     r12d, 5
0x180012972  jnb     loc_180012A71
0x180012978  xor     esi, esi
0x18001297a  cmp     esi, eax
0x18001297c  jnb     loc_180012A69
0x180012982  mov     rcx, rdi
0x180012985  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001298b  mov     ecx, [rsp+58h+arg_0]
0x18001298f  test    r15d, r15d
0x180012992  mov     edx, 70h ; 'p'
0x180012997  mov     r8d, 84h
0x18001299d  cmovnz  edx, r8d
0x1800129a1  add     rdx, [rax+rsi*8]
0x1800129a5  test    [rdx+r12*4], ecx
0x1800129a9  jz      short loc_1800129F5
0x1800129ab  mov     rcx, [rsp+58h+arg_10]
0x1800129b0  mov     [rcx+rbp*4], esi
0x1800129b3  inc     ebp
0x1800129b5  cmp     ebp, r14d
0x1800129b8  jnz     short loc_1800129F5
0x1800129ba  mov     rcx, rbx
0x1800129bd  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800129c3  mov     rcx, rbx
0x1800129c6  lea     edx, [rax+rax]
0x1800129c9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800129cf  test    al, al
0x1800129d1  jz      loc_180012B0D
0x1800129d7  mov     rcx, rbx
0x1800129da  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800129e0  mov     r14d, eax
0x1800129e3  shr     r14d, 2
0x1800129e7  mov     rcx, rbx
0x1800129ea  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800129f0  mov     [rsp+58h+arg_10], rax
0x1800129f5  mov     eax, [rsp+58h+arg_8]
0x1800129f9  inc     esi
0x1800129fb  jmp     loc_18001297A
0x180012a00  xor     r9d, r9d
0x180012a03  lea     rax, [rsi+0E8h]
0x180012a0a  test    r9d, r9d
0x180012a0d  jz      short loc_180012A16
0x180012a0f  lea     rax, [rsi+0ECh]
0x180012a16  mov     eax, [rax]
0x180012a18  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180012a1c  lea     rdx, [rdx+rax*4]
0x180012a20  jnz     loc_180012AD9
0x180012a26  mov     rdx, [rsp+58h+arg_10]
0x180012a2b  inc     r9d
0x180012a2e  cmp     r9d, 2
0x180012a32  jb      short loc_180012A03
0x180012a34  mov     [rdi+0B4h], ebp
0x180012a3a  xor     eax, eax
0x180012a3c  mov     dword ptr [rdi+0B0h], 1
0x180012a46  mov     r14, [rsp+58h+var_30]
0x180012a4b  mov     r13, [rsp+58h+var_28]
0x180012a50  mov     r12, [rsp+58h+var_20]
0x180012a55  mov     rsi, [rsp+58h+var_18]
0x180012a5a  mov     rbp, [rsp+58h+arg_18]
0x180012a5f  mov     r15, [rsp+58h+var_38]
0x180012a64  jmp     loc_1800128D8
0x180012a69  inc     r12d
0x180012a6c  jmp     loc_18001296E
0x180012a71  mov     rdx, [rsp+58h+arg_10]
0x180012a76  mov     dword ptr [rdx+rbp*4], 0FFFFFFFFh
0x180012a7d  inc     ebp
0x180012a7f  cmp     ebp, r14d
0x180012a82  jnz     short loc_180012ABE
0x180012a84  mov     rcx, rbx
0x180012a87  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180012a8d  mov     rcx, rbx
0x180012a90  lea     edx, [rax+rax]
0x180012a93  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180012a99  test    al, al
0x180012a9b  jz      short loc_180012B0D
0x180012a9d  mov     rcx, rbx
0x180012aa0  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180012aa6  mov     r14d, eax
0x180012aa9  shr     r14d, 2
0x180012aad  mov     rcx, rbx
0x180012ab0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180012ab6  mov     rdx, rax
0x180012ab9  mov     [rsp+58h+arg_10], rax
0x180012abe  inc     r15d
0x180012ac1  lea     rsi, [rdi+0B8h]
0x180012ac8  jmp     loc_180012956
0x180012acd  shl     [rsp+58h+arg_0], 1
0x180012ad1  inc     r13d
0x180012ad4  jmp     loc_180012949
0x180012ad9  mov     rax, rdx
0x180012adc  mov     r8, rax
0x180012adf  add     rax, 4
0x180012ae3  cmp     dword ptr [rax], 0FFFFFFFFh
0x180012ae6  jnz     short loc_180012ADC
0x180012ae8  cmp     rdx, r8
0x180012aeb  jnb     loc_180012A26
0x180012af1  mov     ecx, [rdx]
0x180012af3  mov     eax, [r8]
0x180012af6  mov     [rdx], eax
0x180012af8  add     rdx, 4
0x180012afc  mov     [r8], ecx
0x180012aff  sub     r8, 4
0x180012b03  cmp     rdx, r8
0x180012b06  jb      short loc_180012AF1
0x180012b08  jmp     loc_180012A26
0x180012b0d  mov     eax, 80070008h
0x180012b12  jmp     loc_180012A46
```
