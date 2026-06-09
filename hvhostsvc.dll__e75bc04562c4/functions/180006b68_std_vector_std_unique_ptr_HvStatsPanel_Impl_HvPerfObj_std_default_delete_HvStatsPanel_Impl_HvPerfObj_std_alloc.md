# std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>::_Emplace_reallocate<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> &&)

- ea: `0x180006b68`
- end: `0x180006cf7`
- name: `??$_Emplace_reallocate@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `399`
- prototype: `_QWORD *__fastcall(__int64 *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001a80`

## callees

- `0x1800018c0`
- `0x180002bd0`
- `0x180006af0`
- `0x180006b30`
- `0x180006b68`
- `0x180006d00`
- `0x180007210`
- `0x18000802c`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Emplace_reallocate<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>(
        __int64 *a1,
        void *a2,
        __int64 *a3)
{
  __int64 v3; // r14
  __int64 v6; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // r12
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rsi
  _QWORD *v13; // rbx
  void *v14; // rax
  _QWORD *v15; // r8
  _QWORD *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  _QWORD v22[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-60h]
  _QWORD *v24; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = (a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Xlength();
  v8 = (a1[2] - v3) >> 3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_20;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_20;
  v12 = 8 * v11;
  if ( !(8 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(8 * v11);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_20:
    std::_Throw_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v22[2] = v11;
  v22[0] = a1;
  v15 = v13;
  v16 = &v13[((__int64)a2 - v3) >> 3];
  v17 = *a3;
  *a3 = 0;
  *v16 = v17;
  v18 = a1[1];
  v19 = *a1;
  v24 = v16 + 1;
  v23 = v16;
  if ( a2 != (void *)v18 )
  {
    std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(
      v19,
      a2,
      v13);
    v18 = a1[1];
    v15 = v16 + 1;
    v19 = (__int64)a2;
    v23 = v13;
  }
  std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(
    v19,
    v18,
    v15);
  v20 = *a1;
  v22[1] = 0;
  if ( v20 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(v20, a1[1]);
    std::_Deallocate<16>((void *)*a1, (struct std::nothrow_t *)((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL));
  }
  *a1 = (__int64)v13;
  a1[1] = (__int64)&v13[v10];
  a1[2] = (__int64)&v13[v12 / 8];
  std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Reallocation_guard::~_Reallocation_guard(v22);
  return v16;
}

```

## disassembly

```asm
0x180006b68  push    rbx
0x180006b6a  push    rbp
0x180006b6b  push    rsi
0x180006b6c  push    rdi
0x180006b6d  push    r12
0x180006b6f  push    r13
0x180006b71  push    r14
0x180006b73  push    r15
0x180006b75  sub     rsp, 58h
0x180006b79  mov     r14, [rcx]
0x180006b7c  mov     r13, r8
0x180006b7f  mov     r9, [rcx+8]
0x180006b83  mov     r8, 1FFFFFFFFFFFFFFFh
0x180006b8d  sub     r9, r14
0x180006b90  mov     r15, rdx
0x180006b93  sar     r9, 3
0x180006b97  mov     rdi, rcx
0x180006b9a  cmp     r9, r8
0x180006b9d  jz      loc_180006CEB
0x180006ba3  mov     rcx, [rcx+10h]
0x180006ba7  mov     rax, r8
0x180006baa  sub     rcx, r14
0x180006bad  sar     rcx, 3
0x180006bb1  mov     rdx, rcx
0x180006bb4  shr     rdx, 1
0x180006bb7  sub     rax, rdx
0x180006bba  cmp     rcx, rax
0x180006bbd  ja      loc_180006CF1
0x180006bc3  lea     r12, [r9+1]
0x180006bc7  lea     rax, [rcx+rdx]
0x180006bcb  mov     rbp, r12
0x180006bce  cmp     rax, r12
0x180006bd1  cmovnb  rbp, rax
0x180006bd5  cmp     rbp, r8
0x180006bd8  ja      loc_180006CF1
0x180006bde  lea     rsi, ds:0[rbp*8]
0x180006be6  test    rsi, rsi
0x180006be9  jnz     short loc_180006BEF
0x180006beb  xor     ebx, ebx
0x180006bed  jmp     short loc_180006C2D
0x180006bef  cmp     rsi, 1000h
0x180006bf6  jb      short loc_180006C22
0x180006bf8  lea     rcx, [rsi+27h]; Size
0x180006bfc  cmp     rcx, rsi
0x180006bff  jbe     loc_180006CF1
0x180006c05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c0a  test    rax, rax
0x180006c0d  jnz     short loc_180006C14
0x180006c0f  lea     ecx, [rax+5]
0x180006c12  int     29h; Win8: RtlFailFast(ecx)
0x180006c14  lea     rbx, [rax+27h]
0x180006c18  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180006c1c  mov     [rbx-8], rax
0x180006c20  jmp     short loc_180006C2D
0x180006c22  mov     rcx, rsi; Size
0x180006c25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c2a  mov     rbx, rax
0x180006c2d  mov     rcx, r15
0x180006c30  mov     [rsp+98h+var_68], rbp
0x180006c35  sub     rcx, r14
0x180006c38  mov     [rsp+98h+var_78], rdi
0x180006c3d  sar     rcx, 3
0x180006c41  mov     r8, rbx
0x180006c44  lea     r14, [rbx+rcx*8]
0x180006c48  mov     rcx, [r13+0]
0x180006c4c  mov     qword ptr [r13+0], 0
0x180006c54  lea     rbp, [r14+8]
0x180006c58  mov     [r14], rcx
0x180006c5b  mov     rdx, [rdi+8]
0x180006c5f  mov     rcx, [rdi]
0x180006c62  mov     [rsp+98h+var_58], rbp
0x180006c67  mov     [rsp+98h+var_60], r14
0x180006c6c  cmp     r15, rdx
0x180006c6f  jz      short loc_180006C88
0x180006c71  mov     rdx, r15
0x180006c74  call    ??$_Uninitialized_move@PEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x180006c79  mov     rdx, [rdi+8]
0x180006c7d  mov     r8, rbp
0x180006c80  mov     rcx, r15
0x180006c83  mov     [rsp+98h+var_60], rbx
0x180006c88  call    ??$_Uninitialized_move@PEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x180006c8d  mov     rcx, [rdi]
0x180006c90  mov     [rsp+98h+var_70], 0
0x180006c99  test    rcx, rcx
0x180006c9c  jz      short loc_180006CBA
0x180006c9e  mov     rdx, [rdi+8]
0x180006ca2  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x180006ca7  mov     rdx, [rdi+10h]
0x180006cab  sub     rdx, [rdi]
0x180006cae  mov     rcx, [rdi]
0x180006cb1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180006cb5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006cba  mov     [rdi], rbx
0x180006cbd  lea     rcx, [rbx+r12*8]
0x180006cc1  mov     [rdi+8], rcx
0x180006cc5  lea     rcx, [rsi+rbx]
0x180006cc9  mov     [rdi+10h], rcx
0x180006ccd  lea     rcx, [rsp+98h+var_78]
0x180006cd2  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180006cd7  mov     rax, r14
0x180006cda  add     rsp, 58h
0x180006cde  pop     r15
0x180006ce0  pop     r14
0x180006ce2  pop     r13
0x180006ce4  pop     r12
0x180006ce6  pop     rdi
0x180006ce7  pop     rsi
0x180006ce8  pop     rbp
0x180006ce9  pop     rbx
0x180006cea  retn
0x180006ceb  call    ?_Xlength@?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Xlength(void)
0x180006cf1  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
