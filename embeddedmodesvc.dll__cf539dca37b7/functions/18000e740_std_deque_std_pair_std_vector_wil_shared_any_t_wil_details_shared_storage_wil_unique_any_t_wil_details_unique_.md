# std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,std::allocator<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>,std::allocator<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,std::allocator<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>>::_Growmap(unsigned __int64)

- ea: `0x18000e740`
- end: `0x18000e886`
- name: `?_Growmap@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@AEAAX_K@Z`
- size: `326`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d82c`

## callees

- `0x1800035a0`
- `0x180009ebc`
- `0x180009f7c`
- `0x18000a1e0`
- `0x18000e740`
- `0x18000ea1c`
- `0x18001876c`

## pseudocode

```c
void __fastcall std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Growmap(
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
    if ( 0x7FFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
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
0x18000e740  push    rbx
0x18000e742  push    rbp
0x18000e743  push    rsi
0x18000e744  push    rdi
0x18000e745  push    r12
0x18000e747  push    r14
0x18000e749  push    r15
0x18000e74b  sub     rsp, 20h
0x18000e74f  mov     rbp, rcx
0x18000e752  mov     esi, 1
0x18000e757  mov     rcx, [rcx+10h]
0x18000e75b  test    rcx, rcx
0x18000e75e  cmovnz  rsi, rcx
0x18000e762  mov     rax, rsi
0x18000e765  sub     rax, rcx
0x18000e768  cmp     rax, 1
0x18000e76c  jb      short loc_18000E774
0x18000e76e  cmp     rsi, 8
0x18000e772  jnb     short loc_18000E78F
0x18000e774  mov     rax, 7FFFFFFFFFFFFFFh
0x18000e77e  sub     rax, rsi
0x18000e781  cmp     rax, rsi
0x18000e784  jb      loc_18000E880
0x18000e78a  add     rsi, rsi
0x18000e78d  jmp     short loc_18000E762
0x18000e78f  mov     rdi, [rbp+18h]
0x18000e793  mov     rcx, rsi
0x18000e796  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000e79b  mov     rcx, rax
0x18000e79e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e7a3  mov     r14, rax
0x18000e7a6  lea     r15, ds:0[rdi*8]
0x18000e7ae  lea     r12, [r15+rax]
0x18000e7b2  mov     rax, rsi
0x18000e7b5  shr     rax, 1
0x18000e7b8  jmp     short loc_18000E7BD
0x18000e7ba  add     rsi, rsi
0x18000e7bd  cmp     rsi, rax
0x18000e7c0  jbe     short loc_18000E7BA
0x18000e7c2  mov     rcx, [rbp+8]
0x18000e7c6  mov     rax, [rbp+10h]
0x18000e7ca  sub     rsi, rax
0x18000e7cd  shl     rax, 3
0x18000e7d1  lea     rdx, [rcx+r15]; Src
0x18000e7d5  sub     rax, rdx
0x18000e7d8  lea     rbx, [rax+rcx]
0x18000e7dc  mov     rcx, r12; void *
0x18000e7df  mov     r8, rbx; Size
0x18000e7e2  call    memmove_0
0x18000e7e7  mov     rdx, [rbp+8]; Src
0x18000e7eb  add     rbx, r12
0x18000e7ee  mov     rcx, rbx; void *
0x18000e7f1  cmp     rdi, rsi
0x18000e7f4  ja      short loc_18000E81B
0x18000e7f6  mov     r8, r15; Size
0x18000e7f9  call    memmove_0
0x18000e7fe  mov     r8, rsi
0x18000e801  lea     rcx, [rbx+r15]; void *
0x18000e805  sub     r8, rdi
0x18000e808  xor     edx, edx; Val
0x18000e80a  shl     r8, 3; Size
0x18000e80e  call    memset_0
0x18000e813  mov     r8, r15
0x18000e816  mov     rcx, r14
0x18000e819  jmp     short loc_18000E84C
0x18000e81b  lea     rdi, ds:0[rsi*8]
0x18000e823  mov     r8, rdi; Size
0x18000e826  call    memmove_0
0x18000e82b  mov     rax, [rbp+8]
0x18000e82f  mov     rcx, r14; void *
0x18000e832  lea     rdx, [rdi+rax]; Src
0x18000e836  sub     rax, rdx
0x18000e839  lea     rbx, [rax+r15]
0x18000e83d  mov     r8, rbx; Size
0x18000e840  call    memmove_0
0x18000e845  lea     rcx, [rbx+r14]; void *
0x18000e849  mov     r8, rdi; Size
0x18000e84c  xor     edx, edx; Val
0x18000e84e  call    memset_0
0x18000e853  mov     rcx, [rbp+8]
0x18000e857  test    rcx, rcx
0x18000e85a  jz      short loc_18000E869
0x18000e85c  mov     rdx, [rbp+10h]
0x18000e860  shl     rdx, 3
0x18000e864  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e869  add     [rbp+10h], rsi
0x18000e86d  mov     [rbp+8], r14
0x18000e871  add     rsp, 20h
0x18000e875  pop     r15
0x18000e877  pop     r14
0x18000e879  pop     r12
0x18000e87b  pop     rdi
0x18000e87c  pop     rsi
0x18000e87d  pop     rbp
0x18000e87e  pop     rbx
0x18000e87f  retn
0x18000e880  call    ?_Xlen@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@CAXXZ; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Xlen(void)
```
