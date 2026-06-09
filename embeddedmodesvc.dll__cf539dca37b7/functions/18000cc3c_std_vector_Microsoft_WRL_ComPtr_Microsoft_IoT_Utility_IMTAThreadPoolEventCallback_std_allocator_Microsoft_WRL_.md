# std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &)

- ea: `0x18000cc3c`
- end: `0x18000cd76`
- name: `??$_Emplace_reallocate@AEBV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV234@AEBV234@@Z`
- size: `314`
- prototype: `_QWORD *__fastcall(__int64 **, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de50`

## callees

- `0x180009ebc`
- `0x180009f7c`
- `0x18000a1e0`
- `0x18000c6b8`
- `0x18000cb28`
- `0x18000cc3c`
- `0x18000d064`
- `0x18000d508`
- `0x18000d7c8`

## pseudocode

```c
_QWORD *__fastcall std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // r15
  __int64 *v18; // rdx
  _QWORD *v19; // r8
  __int64 *v20; // rcx
  __int64 *v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = a1[1] - *a1;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Xlength();
  v8 = v5 + 1;
  v9 = (char *)a2 - (char *)*a1;
  v10 = a1[2] - *a1;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  v23[0] = a1;
  v23[2] = v3;
  v17 = &v14[v11];
  *v17 = v15;
  v25 = v17 + 1;
  Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(v17);
  v18 = a1[1];
  v19 = v16;
  v20 = *a1;
  v24 = v17;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
      v20,
      a2,
      v16);
    v18 = a1[1];
    v19 = v17 + 1;
    v20 = a2;
    v24 = v16;
  }
  std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
    v20,
    v18,
    v19);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
      v21,
      a1[1]);
    std::_Deallocate<16>(*a1, ((char *)a1[2] - (char *)*a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = &v16[v8];
  a1[2] = &v16[v3];
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v17;
}

```

## disassembly

```asm
0x18000cc3c  push    rbx
0x18000cc3e  push    rbp
0x18000cc3f  push    rsi
0x18000cc40  push    rdi
0x18000cc41  push    r12
0x18000cc43  push    r13
0x18000cc45  push    r14
0x18000cc47  push    r15
0x18000cc49  sub     rsp, 58h
0x18000cc4d  mov     rax, [rcx+8]
0x18000cc51  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18000cc5b  sub     rax, [rcx]
0x18000cc5e  mov     r13, r8
0x18000cc61  sar     rax, 3
0x18000cc65  mov     rbp, rdx
0x18000cc68  mov     rbx, rcx
0x18000cc6b  cmp     rax, rdi
0x18000cc6e  jz      loc_18000CD70
0x18000cc74  mov     r15, rdx
0x18000cc77  lea     r14, [rax+1]
0x18000cc7b  sub     r15, [rcx]
0x18000cc7e  mov     rax, rdi
0x18000cc81  mov     rcx, [rcx+10h]
0x18000cc85  sub     rcx, [rbx]
0x18000cc88  sar     rcx, 3
0x18000cc8c  mov     rdx, rcx
0x18000cc8f  sar     r15, 3
0x18000cc93  shr     rdx, 1
0x18000cc96  sub     rax, rdx
0x18000cc99  cmp     rcx, rax
0x18000cc9c  ja      short loc_18000CCA9
0x18000cc9e  lea     rdi, [rdx+rcx]
0x18000cca2  cmp     rdi, r14
0x18000cca5  cmovb   rdi, r14
0x18000cca9  mov     rcx, rdi
0x18000ccac  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000ccb1  mov     rcx, rax
0x18000ccb4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000ccb9  mov     rcx, [r13+0]
0x18000ccbd  mov     rsi, rax
0x18000ccc0  mov     [rsp+98h+var_78], rbx
0x18000ccc5  mov     [rsp+98h+var_68], rdi
0x18000ccca  lea     r15, [rax+r15*8]
0x18000ccce  mov     [r15], rcx
0x18000ccd1  lea     r12, [r15+8]
0x18000ccd5  mov     rcx, r15
0x18000ccd8  mov     [rsp+98h+var_58], r12
0x18000ccdd  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000cce2  mov     rdx, [rbx+8]
0x18000cce6  mov     r8, rsi
0x18000cce9  mov     rcx, [rbx]
0x18000ccec  mov     [rsp+98h+var_60], r15
0x18000ccf1  cmp     rbp, rdx
0x18000ccf4  jz      short loc_18000CD0D
0x18000ccf6  mov     rdx, rbp
0x18000ccf9  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>> &)
0x18000ccfe  mov     rdx, [rbx+8]
0x18000cd02  mov     r8, r12
0x18000cd05  mov     rcx, rbp
0x18000cd08  mov     [rsp+98h+var_60], rsi
0x18000cd0d  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>> &)
0x18000cd12  mov     rcx, [rbx]
0x18000cd15  mov     [rsp+98h+var_70], 0
0x18000cd1e  test    rcx, rcx
0x18000cd21  jz      short loc_18000CD3F
0x18000cd23  mov     rdx, [rbx+8]
0x18000cd27  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>> &)
0x18000cd2c  mov     rdx, [rbx+10h]
0x18000cd30  sub     rdx, [rbx]
0x18000cd33  mov     rcx, [rbx]
0x18000cd36  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000cd3a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cd3f  mov     [rbx], rsi
0x18000cd42  lea     rcx, [rsi+r14*8]
0x18000cd46  mov     [rbx+8], rcx
0x18000cd4a  lea     rcx, [rsi+rdi*8]
0x18000cd4e  mov     [rbx+10h], rcx
0x18000cd52  lea     rcx, [rsp+98h+var_78]
0x18000cd57  call    ??1_Reallocation_guard@?$vector@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000cd5c  mov     rax, r15
0x18000cd5f  add     rsp, 58h
0x18000cd63  pop     r15
0x18000cd65  pop     r14
0x18000cd67  pop     r13
0x18000cd69  pop     r12
0x18000cd6b  pop     rdi
0x18000cd6c  pop     rsi
0x18000cd6d  pop     rbp
0x18000cd6e  pop     rbx
0x18000cd6f  retn
0x18000cd70  call    ?_Xlength@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Xlength(void)
```
