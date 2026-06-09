# container::RegistryProvider::BuildTightlyPackgedStringBuffer(unsigned __int64,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> *,unsigned __int64 *)

- ea: `0x180028d8c`
- end: `0x180028eac`
- name: `?BuildTightlyPackgedStringBuffer@RegistryProvider@container@@YAX_KAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@4@PEA_K@Z`
- size: `288`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180029bc0`
- `0x18002a78c`

## callees

- `0x180002ee4`
- `0x180002f1c`
- `0x180003614`
- `0x18000b4bc`
- `0x180028d8c`

## string_xrefs

- `0x180028e85`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x180028e97`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
void __fastcall container::RegistryProvider::BuildTightlyPackgedStringBuffer(
        unsigned __int64 a1,
        const void ***a2,
        void **a3,
        unsigned __int64 *a4)
{
  const void **v4; // r10
  unsigned __int64 i; // rdi
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  bool v14; // cf
  __int64 v15; // rax
  void *v16; // rax
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  const void **v19; // rbp
  char *v20; // rsi
  const void **j; // rbx
  __int64 v22; // rdi
  const void *v23; // rdx
  int v24; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *a2;
  for ( i = a1; v4 != a2[1]; v4 += 4 )
  {
    v10 = 2LL * (_QWORD)v4[2];
    if ( is_mul_ok((unsigned __int64)v4[2], 2u) )
    {
      v11 = 0;
    }
    else
    {
      v10 = -1;
      v11 = 3221225621LL;
    }
    if ( (int)v11 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)v11,
        v24);
    v12 = i + v10;
    v13 = i;
    v14 = i + v10 < i;
    v15 = -1;
    if ( !v14 )
      v15 = v12;
    i = v15;
    if ( v12 < v13 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v12 < v13 ? (const char *)0xC0000095LL : 0,
        v24);
  }
  v16 = operator new[](i);
  v18 = *a3;
  *a3 = v16;
  if ( v18 )
    operator delete(v18, v17);
  *a4 = i;
  v19 = a2[1];
  v20 = (char *)*a3 + a1;
  for ( j = *a2; j != v19; j += 4 )
  {
    v22 = 2LL * (_QWORD)j[2];
    if ( (unsigned __int64)j[3] <= 7 )
      v23 = j;
    else
      v23 = *j;
    memcpy_0(v20, v23, 2LL * (_QWORD)j[2]);
    v20 += v22;
  }
}

```

## disassembly

```asm
0x180028d8c  push    rbx
0x180028d8e  push    rbp
0x180028d8f  push    rsi
0x180028d90  push    rdi
0x180028d91  push    r14
0x180028d93  push    r15
0x180028d95  sub     rsp, 28h
0x180028d99  mov     r10, [rdx]
0x180028d9c  mov     r15, r9
0x180028d9f  mov     rsi, r8
0x180028da2  mov     rbx, rdx
0x180028da5  mov     r14, rcx
0x180028da8  mov     rdi, rcx
0x180028dab  cmp     r10, [rdx+8]
0x180028daf  jz      short loc_180028E20
0x180028db1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028db5  mov     r11d, 0C0000095h
0x180028dbb  mov     eax, 2
0x180028dc0  mov     [rsp+58h+arg_0], 0
0x180028dc9  mul     qword ptr [r10+10h]
0x180028dcd  test    rdx, rdx
0x180028dd0  jnz     short loc_180028DD7
0x180028dd2  xor     r9d, r9d
0x180028dd5  jmp     short loc_180028DDD
0x180028dd7  mov     rax, r8
0x180028dda  mov     r9d, r11d; char *
0x180028ddd  mov     rcx, [rsp+58h]; this
0x180028de2  test    r9d, r9d
0x180028de5  js      loc_180028E85
0x180028deb  lea     rcx, [rdi+rax]
0x180028def  mov     rdx, rdi
0x180028df2  cmp     rcx, rdi
0x180028df5  mov     rax, r8
0x180028df8  cmovnb  rax, rcx
0x180028dfc  cmp     rcx, rdx
0x180028dff  mov     rdi, rax
0x180028e02  mov     rax, [rsp+58h]
0x180028e07  sbb     r9d, r9d
0x180028e0a  and     r9d, r11d; char *
0x180028e0d  cmp     rcx, rdx
0x180028e10  jb      loc_180028E97
0x180028e16  add     r10, 20h ; ' '
0x180028e1a  cmp     r10, [rbx+8]
0x180028e1e  jnz     short loc_180028DBB
0x180028e20  mov     rcx, rdi; unsigned __int64
0x180028e23  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028e28  mov     rcx, [rsi]; void *
0x180028e2b  mov     [rsi], rax
0x180028e2e  test    rcx, rcx
0x180028e31  jz      short loc_180028E38
0x180028e33  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028e38  mov     [r15], rdi
0x180028e3b  mov     rsi, [rsi]
0x180028e3e  mov     rbp, [rbx+8]
0x180028e42  add     rsi, r14
0x180028e45  mov     rbx, [rbx]
0x180028e48  jmp     short loc_180028E72
0x180028e4a  mov     rdi, [rbx+10h]
0x180028e4e  add     rdi, rdi
0x180028e51  cmp     qword ptr [rbx+18h], 7
0x180028e56  jbe     short loc_180028E5D
0x180028e58  mov     rdx, [rbx]
0x180028e5b  jmp     short loc_180028E60
0x180028e5d  mov     rdx, rbx; Src
0x180028e60  mov     r8, rdi; Size
0x180028e63  mov     rcx, rsi; void *
0x180028e66  call    memcpy_0
0x180028e6b  add     rsi, rdi
0x180028e6e  add     rbx, 20h ; ' '
0x180028e72  cmp     rbx, rbp
0x180028e75  jnz     short loc_180028E4A
0x180028e77  add     rsp, 28h
0x180028e7b  pop     r15
0x180028e7d  pop     r14
0x180028e7f  pop     rdi
0x180028e80  pop     rsi
0x180028e81  pop     rbp
0x180028e82  pop     rbx
0x180028e83  retn
0x180028e85  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180028e8c  mov     edx, 67h ; 'g'; void *
0x180028e91  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180028e97  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180028e9e  mov     edx, 6Ah ; 'j'; void *
0x180028ea3  mov     rcx, rax; this
0x180028ea6  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
