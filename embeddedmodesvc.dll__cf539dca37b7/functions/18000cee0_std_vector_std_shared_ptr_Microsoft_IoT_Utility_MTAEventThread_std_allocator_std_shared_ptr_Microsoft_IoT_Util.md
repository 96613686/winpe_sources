# std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> &&)

- ea: `0x18000cee0`
- end: `0x18000d031`
- name: `??$_Emplace_reallocate@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@1@QEAV21@$$QEAV21@@Z`
- size: `337`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d82c`
- `0x18000da64`

## callees

- `0x180009ebc`
- `0x180009f7c`
- `0x18000a020`
- `0x18000a20c`
- `0x18000c6b8`
- `0x18000cee0`
- `0x18000d0ec`
- `0x18000d580`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rsi
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  size_t size_of; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // r14
  _QWORD *v15; // rbp
  _QWORD *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD v21[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v22; // [rsp+38h] [rbp-60h]
  _QWORD *v23; // [rsp+40h] [rbp-58h]

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Xlength();
  v8 = a2 - *a1;
  v9 = v5 + 1;
  v10 = (a1[2] - *a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v9 )
      v3 = v9;
  }
  size_of = std::_Get_size_of_n<16>(v3);
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v21[0] = a1;
  v21[2] = v3;
  v14 = (_QWORD *)((char *)v13 + (v8 & 0xFFFFFFFFFFFFFFF0uLL));
  v15 = v13;
  v22 = v14;
  v16 = v13;
  *v14 = 0;
  v14[1] = 0;
  *v14 = *a3;
  v14[1] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v17 = a1[1];
  v18 = *a1;
  v23 = v14 + 2;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>>>(
      v18,
      a2,
      v13);
    v17 = a1[1];
    v16 = v14 + 2;
    v18 = a2;
    v22 = v15;
  }
  std::_Uninitialized_move<std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>>>(
    v18,
    v17,
    v16);
  v19 = *a1;
  v21[1] = 0;
  if ( v19 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(v19, a1[1]);
    std::_Deallocate<16>((_QWORD *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  *a1 = (__int64)v15;
  a1[1] = (__int64)&v15[2 * v9];
  a1[2] = (__int64)&v15[2 * v3];
  std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Reallocation_guard::~_Reallocation_guard(v21);
  return v14;
}

```

## disassembly

```asm
0x18000cee0  push    rbx
0x18000cee2  push    rbp
0x18000cee3  push    rsi
0x18000cee4  push    rdi
0x18000cee5  push    r12
0x18000cee7  push    r13
0x18000cee9  push    r14
0x18000ceeb  push    r15
0x18000ceed  sub     rsp, 58h
0x18000cef1  mov     rsi, [rcx+8]
0x18000cef5  mov     rbx, 0FFFFFFFFFFFFFFFh
0x18000ceff  sub     rsi, [rcx]
0x18000cf02  mov     r12, r8
0x18000cf05  sar     rsi, 4
0x18000cf09  mov     r15, rdx
0x18000cf0c  mov     rdi, rcx
0x18000cf0f  cmp     rsi, rbx
0x18000cf12  jz      loc_18000D02B
0x18000cf18  mov     r14, rdx
0x18000cf1b  mov     rax, rbx
0x18000cf1e  sub     r14, [rcx]
0x18000cf21  mov     rcx, [rcx+10h]
0x18000cf25  inc     rsi
0x18000cf28  sub     rcx, [rdi]
0x18000cf2b  sar     rcx, 4
0x18000cf2f  mov     rdx, rcx
0x18000cf32  shr     rdx, 1
0x18000cf35  sub     rax, rdx
0x18000cf38  cmp     rcx, rax
0x18000cf3b  ja      short loc_18000CF48
0x18000cf3d  lea     rbx, [rdx+rcx]
0x18000cf41  cmp     rbx, rsi
0x18000cf44  cmovb   rbx, rsi
0x18000cf48  mov     rcx, rbx
0x18000cf4b  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18000cf50  mov     rcx, rax
0x18000cf53  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000cf58  xor     edx, edx
0x18000cf5a  mov     [rsp+98h+var_78], rdi
0x18000cf5f  and     r14, 0FFFFFFFFFFFFFFF0h
0x18000cf63  mov     [rsp+98h+var_68], rbx
0x18000cf68  add     r14, rax
0x18000cf6b  mov     rbp, rax
0x18000cf6e  mov     [rsp+98h+var_60], r14
0x18000cf73  mov     r8, rbp
0x18000cf76  mov     [r14], rdx
0x18000cf79  lea     r13, [r14+10h]
0x18000cf7d  mov     [r14+8], rdx
0x18000cf81  mov     rcx, [r12]
0x18000cf85  mov     [r14], rcx
0x18000cf88  mov     rax, [r12+8]
0x18000cf8d  mov     [r14+8], rax
0x18000cf91  mov     [r12], rdx
0x18000cf95  mov     [r12+8], rdx
0x18000cf9a  mov     rdx, [rdi+8]
0x18000cf9e  mov     rcx, [rdi]
0x18000cfa1  mov     [rsp+98h+var_58], r13
0x18000cfa6  cmp     r15, rdx
0x18000cfa9  jz      short loc_18000CFC2
0x18000cfab  mov     rdx, r15
0x18000cfae  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@@2@@std@@YAPEAV?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>> &)
0x18000cfb3  mov     rdx, [rdi+8]
0x18000cfb7  mov     r8, r13
0x18000cfba  mov     rcx, r15
0x18000cfbd  mov     [rsp+98h+var_60], rbp
0x18000cfc2  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@@2@@std@@YAPEAV?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAThread> *,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAThread>> &)
0x18000cfc7  mov     rcx, [rdi]
0x18000cfca  mov     [rsp+98h+var_70], 0
0x18000cfd3  test    rcx, rcx
0x18000cfd6  jz      short loc_18000CFF4
0x18000cfd8  mov     rdx, [rdi+8]
0x18000cfdc  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)
0x18000cfe1  mov     rdx, [rdi+10h]
0x18000cfe5  sub     rdx, [rdi]
0x18000cfe8  mov     rcx, [rdi]
0x18000cfeb  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000cfef  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cff4  mov     [rdi], rbp
0x18000cff7  lea     rcx, [rsp+98h+var_78]
0x18000cffc  shl     rsi, 4
0x18000d000  shl     rbx, 4
0x18000d004  add     rsi, rbp
0x18000d007  add     rbx, rbp
0x18000d00a  mov     [rdi+8], rsi
0x18000d00e  mov     [rdi+10h], rbx
0x18000d012  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000d017  mov     rax, r14
0x18000d01a  add     rsp, 58h
0x18000d01e  pop     r15
0x18000d020  pop     r14
0x18000d022  pop     r13
0x18000d024  pop     r12
0x18000d026  pop     rdi
0x18000d027  pop     rsi
0x18000d028  pop     rbp
0x18000d029  pop     rbx
0x18000d02a  retn
0x18000d02b  call    ?_Xlength@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Xlength(void)
```
