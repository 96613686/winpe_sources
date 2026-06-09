# NOTIFICATION_CONTEXT::GenerateCachedModuleList(CACHED_MODULE_LIST *)

- ea: `0x180013850`
- end: `0x180013b00`
- name: `?GenerateCachedModuleList@NOTIFICATION_CONTEXT@@SAJPEAUCACHED_MODULE_LIST@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(struct CACHED_MODULE_LIST *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cf40`
- `0x18001e020`

## callees

- `0x180013850`
- `0x18003773a`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800138dd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013938`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800139b5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013a93`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800138dd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013938`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800139b5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013a93`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800138a9`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013976`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001399f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013a58`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013a7d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800138a9`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013976`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001399f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013a58`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180013a7d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013869`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013988`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013a6a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013869`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013988`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180013a6a`

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
0x180013850  push    rbx
0x180013852  push    rdi
0x180013853  sub     rsp, 48h
0x180013857  lea     rbx, [rcx+80h]
0x18001385e  mov     rdi, rcx
0x180013861  mov     rcx, rbx
0x180013864  mov     edx, 400h
0x180013869  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180013870  nop     dword ptr [rax+rax+00h]
0x180013875  test    al, al
0x180013877  jnz     short loc_180013886
0x180013879  mov     eax, 80070008h
0x18001387e  add     rsp, 48h
0x180013882  pop     rdi
0x180013883  pop     rbx
0x180013884  retn
0x180013886  mov     [rsp+58h+arg_18], rbp
0x18001388b  mov     rcx, rbx
0x18001388e  mov     [rsp+58h+var_18], rsi
0x180013893  xor     ebp, ebp
0x180013895  mov     [rsp+58h+var_20], r12
0x18001389a  mov     [rsp+58h+var_28], r13
0x18001389f  mov     [rsp+58h+var_30], r14
0x1800138a4  mov     [rsp+58h+var_38], r15
0x1800138a9  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800138b0  nop     dword ptr [rax+rax+00h]
0x1800138b5  lea     rsi, [rdi+0B8h]
0x1800138bc  xor     edx, edx; Val
0x1800138be  mov     r14d, eax
0x1800138c1  mov     r8d, 100h; Size
0x1800138c7  mov     rcx, rsi; void *
0x1800138ca  shr     r14d, 2
0x1800138ce  call    memset_0
0x1800138d3  mov     eax, [rdi+30h]
0x1800138d6  mov     rcx, rbx
0x1800138d9  mov     [rsp+58h+arg_8], eax
0x1800138dd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800138e4  nop     dword ptr [rax+rax+00h]
0x1800138e9  mov     [rsp+58h+arg_0], 1
0x1800138f1  xor     r13d, r13d
0x1800138f4  mov     rdx, rax
0x1800138f7  mov     [rsp+58h+arg_10], rax
0x1800138fc  cmp     r13d, 20h ; ' '
0x180013900  jnb     loc_1800139D1
0x180013906  xor     r15d, r15d
0x180013909  cmp     r15d, 2
0x18001390d  jnb     loc_180013AB6
0x180013913  lea     eax, [r15+r13*2]
0x180013917  xor     r12d, r12d
0x18001391a  mov     [rsi+rax*4], ebp
0x18001391d  mov     eax, [rsp+58h+arg_8]
0x180013921  cmp     r12d, 5
0x180013925  jnb     loc_180013A42
0x18001392b  xor     esi, esi
0x18001392d  cmp     esi, eax
0x18001392f  jnb     loc_180013A3A
0x180013935  mov     rcx, rdi
0x180013938  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001393f  nop     dword ptr [rax+rax+00h]
0x180013944  mov     ecx, [rsp+58h+arg_0]
0x180013948  test    r15d, r15d
0x18001394b  mov     edx, 70h ; 'p'
0x180013950  mov     r8d, 84h
0x180013956  cmovnz  edx, r8d
0x18001395a  add     rdx, [rax+rsi*8]
0x18001395e  test    [rdx+r12*4], ecx
0x180013962  jz      short loc_1800139C6
0x180013964  mov     rcx, [rsp+58h+arg_10]
0x180013969  mov     [rcx+rbp*4], esi
0x18001396c  inc     ebp
0x18001396e  cmp     ebp, r14d
0x180013971  jnz     short loc_1800139C6
0x180013973  mov     rcx, rbx
0x180013976  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001397d  nop     dword ptr [rax+rax+00h]
0x180013982  mov     rcx, rbx
0x180013985  lea     edx, [rax+rax]
0x180013988  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001398f  nop     dword ptr [rax+rax+00h]
0x180013994  test    al, al
0x180013996  jz      loc_180013AF6
0x18001399c  mov     rcx, rbx
0x18001399f  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800139a6  nop     dword ptr [rax+rax+00h]
0x1800139ab  mov     r14d, eax
0x1800139ae  shr     r14d, 2
0x1800139b2  mov     rcx, rbx
0x1800139b5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800139bc  nop     dword ptr [rax+rax+00h]
0x1800139c1  mov     [rsp+58h+arg_10], rax
0x1800139c6  mov     eax, [rsp+58h+arg_8]
0x1800139ca  inc     esi
0x1800139cc  jmp     loc_18001392D
0x1800139d1  xor     r9d, r9d
0x1800139d4  lea     rax, [rsi+0E8h]
0x1800139db  test    r9d, r9d
0x1800139de  jz      short loc_1800139E7
0x1800139e0  lea     rax, [rsi+0ECh]
0x1800139e7  mov     eax, [rax]
0x1800139e9  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x1800139ed  lea     rdx, [rdx+rax*4]
0x1800139f1  jnz     loc_180013AC2
0x1800139f7  mov     rdx, [rsp+58h+arg_10]
0x1800139fc  inc     r9d
0x1800139ff  cmp     r9d, 2
0x180013a03  jb      short loc_1800139D4
0x180013a05  mov     [rdi+0B4h], ebp
0x180013a0b  xor     eax, eax
0x180013a0d  mov     dword ptr [rdi+0B0h], 1
0x180013a17  mov     r14, [rsp+58h+var_30]
0x180013a1c  mov     r13, [rsp+58h+var_28]
0x180013a21  mov     r12, [rsp+58h+var_20]
0x180013a26  mov     rsi, [rsp+58h+var_18]
0x180013a2b  mov     rbp, [rsp+58h+arg_18]
0x180013a30  mov     r15, [rsp+58h+var_38]
0x180013a35  jmp     loc_18001387E
0x180013a3a  inc     r12d
0x180013a3d  jmp     loc_180013921
0x180013a42  mov     rdx, [rsp+58h+arg_10]
0x180013a47  mov     dword ptr [rdx+rbp*4], 0FFFFFFFFh
0x180013a4e  inc     ebp
0x180013a50  cmp     ebp, r14d
0x180013a53  jnz     short loc_180013AA7
0x180013a55  mov     rcx, rbx
0x180013a58  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180013a5f  nop     dword ptr [rax+rax+00h]
0x180013a64  mov     rcx, rbx
0x180013a67  lea     edx, [rax+rax]
0x180013a6a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180013a71  nop     dword ptr [rax+rax+00h]
0x180013a76  test    al, al
0x180013a78  jz      short loc_180013AF6
0x180013a7a  mov     rcx, rbx
0x180013a7d  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180013a84  nop     dword ptr [rax+rax+00h]
0x180013a89  mov     r14d, eax
0x180013a8c  shr     r14d, 2
0x180013a90  mov     rcx, rbx
0x180013a93  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013a9a  nop     dword ptr [rax+rax+00h]
0x180013a9f  mov     rdx, rax
0x180013aa2  mov     [rsp+58h+arg_10], rax
0x180013aa7  inc     r15d
0x180013aaa  lea     rsi, [rdi+0B8h]
0x180013ab1  jmp     loc_180013909
0x180013ab6  shl     [rsp+58h+arg_0], 1
0x180013aba  inc     r13d
0x180013abd  jmp     loc_1800138FC
0x180013ac2  mov     rax, rdx
0x180013ac5  mov     r8, rax
0x180013ac8  add     rax, 4
0x180013acc  cmp     dword ptr [rax], 0FFFFFFFFh
0x180013acf  jnz     short loc_180013AC5
0x180013ad1  cmp     rdx, r8
0x180013ad4  jnb     loc_1800139F7
0x180013ada  mov     ecx, [rdx]
0x180013adc  mov     eax, [r8]
0x180013adf  mov     [rdx], eax
0x180013ae1  add     rdx, 4
0x180013ae5  mov     [r8], ecx
0x180013ae8  sub     r8, 4
0x180013aec  cmp     rdx, r8
0x180013aef  jb      short loc_180013ADA
0x180013af1  jmp     loc_1800139F7
0x180013af6  mov     eax, 80070008h
0x180013afb  jmp     loc_180013A17
```
