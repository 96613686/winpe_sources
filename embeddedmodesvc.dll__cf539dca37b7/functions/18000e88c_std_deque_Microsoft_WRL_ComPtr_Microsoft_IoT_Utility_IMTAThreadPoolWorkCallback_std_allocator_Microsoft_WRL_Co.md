# std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>::_Growmap(unsigned __int64)

- ea: `0x18000e88c`
- end: `0x18000e9d5`
- name: `?_Growmap@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAX_K@Z`
- size: `329`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cb74`

## callees

- `0x1800035a0`
- `0x180009ebc`
- `0x180009f7c`
- `0x18000a1e0`
- `0x18000e88c`
- `0x18000ea1c`
- `0x18001876c`

## pseudocode

```c
void __fastcall std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Growmap(
        _QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t size_of; // rax
  _QWORD *v6; // r14
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  _QWORD *v17; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3] >> 1;
  size_of = std::_Get_size_of_n<8>(v2);
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = 8 * v4;
  v8 = (char *)&v6[v4];
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v7;
  memmove_0(v8, (const void *)(a1[1] + v7), v12);
  v13 = (const void *)a1[1];
  v14 = &v8[v12];
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v7 - 8 * v11);
    v16 = (char *)v6 + v7 - 8 * v11;
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v7], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = (char *)v6;
  }
  memset_0(v16, 0, v15);
  v17 = (_QWORD *)a1[1];
  if ( v17 )
    std::_Deallocate<16>(v17, 8LL * a1[2]);
  a1[2] += v11;
  a1[1] = v6;
}

```

## disassembly

```asm
0x18000e88c  push    rbx
0x18000e88e  push    rbp
0x18000e88f  push    rsi
0x18000e890  push    rdi
0x18000e891  push    r12
0x18000e893  push    r14
0x18000e895  push    r15
0x18000e897  sub     rsp, 20h
0x18000e89b  mov     rbp, rcx
0x18000e89e  mov     esi, 1
0x18000e8a3  mov     rcx, [rcx+10h]
0x18000e8a7  test    rcx, rcx
0x18000e8aa  cmovnz  rsi, rcx
0x18000e8ae  mov     rax, rsi
0x18000e8b1  sub     rax, rcx
0x18000e8b4  cmp     rax, 1
0x18000e8b8  jb      short loc_18000E8C0
0x18000e8ba  cmp     rsi, 8
0x18000e8be  jnb     short loc_18000E8DB
0x18000e8c0  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000e8ca  sub     rax, rsi
0x18000e8cd  cmp     rax, rsi
0x18000e8d0  jb      loc_18000E9CF
0x18000e8d6  add     rsi, rsi
0x18000e8d9  jmp     short loc_18000E8AE
0x18000e8db  mov     rdi, [rbp+18h]
0x18000e8df  mov     rcx, rsi
0x18000e8e2  shr     rdi, 1
0x18000e8e5  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000e8ea  mov     rcx, rax
0x18000e8ed  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e8f2  mov     r14, rax
0x18000e8f5  lea     r15, ds:0[rdi*8]
0x18000e8fd  lea     r12, [r15+rax]
0x18000e901  mov     rax, rsi
0x18000e904  shr     rax, 1
0x18000e907  jmp     short loc_18000E90C
0x18000e909  add     rsi, rsi
0x18000e90c  cmp     rsi, rax
0x18000e90f  jbe     short loc_18000E909
0x18000e911  mov     rcx, [rbp+8]
0x18000e915  mov     rax, [rbp+10h]
0x18000e919  sub     rsi, rax
0x18000e91c  shl     rax, 3
0x18000e920  lea     rdx, [rcx+r15]; Src
0x18000e924  sub     rax, rdx
0x18000e927  lea     rbx, [rax+rcx]
0x18000e92b  mov     rcx, r12; void *
0x18000e92e  mov     r8, rbx; Size
0x18000e931  call    memmove_0
0x18000e936  mov     rdx, [rbp+8]; Src
0x18000e93a  add     rbx, r12
0x18000e93d  mov     rcx, rbx; void *
0x18000e940  cmp     rdi, rsi
0x18000e943  ja      short loc_18000E96A
0x18000e945  mov     r8, r15; Size
0x18000e948  call    memmove_0
0x18000e94d  mov     r8, rsi
0x18000e950  lea     rcx, [rbx+r15]; void *
0x18000e954  sub     r8, rdi
0x18000e957  xor     edx, edx; Val
0x18000e959  shl     r8, 3; Size
0x18000e95d  call    memset_0
0x18000e962  mov     r8, r15
0x18000e965  mov     rcx, r14
0x18000e968  jmp     short loc_18000E99B
0x18000e96a  lea     rdi, ds:0[rsi*8]
0x18000e972  mov     r8, rdi; Size
0x18000e975  call    memmove_0
0x18000e97a  mov     rax, [rbp+8]
0x18000e97e  mov     rcx, r14; void *
0x18000e981  lea     rdx, [rdi+rax]; Src
0x18000e985  sub     rax, rdx
0x18000e988  lea     rbx, [rax+r15]
0x18000e98c  mov     r8, rbx; Size
0x18000e98f  call    memmove_0
0x18000e994  lea     rcx, [rbx+r14]; void *
0x18000e998  mov     r8, rdi; Size
0x18000e99b  xor     edx, edx; Val
0x18000e99d  call    memset_0
0x18000e9a2  mov     rcx, [rbp+8]
0x18000e9a6  test    rcx, rcx
0x18000e9a9  jz      short loc_18000E9B8
0x18000e9ab  mov     rdx, [rbp+10h]
0x18000e9af  shl     rdx, 3
0x18000e9b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e9b8  add     [rbp+10h], rsi
0x18000e9bc  mov     [rbp+8], r14
0x18000e9c0  add     rsp, 20h
0x18000e9c4  pop     r15
0x18000e9c6  pop     r14
0x18000e9c8  pop     r12
0x18000e9ca  pop     rdi
0x18000e9cb  pop     rsi
0x18000e9cc  pop     rbp
0x18000e9cd  pop     rbx
0x18000e9ce  retn
0x18000e9cf  call    ?_Xlen@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@CAXXZ; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Xlen(void)
```
