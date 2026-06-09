# Concurrency::streams::streambuf<char>::close(int,std::exception_ptr)

- ea: `0x1800c0e80`
- end: `0x1800c0fb8`
- name: `?close@?$streambuf@D@streams@Concurrency@@UEAA?AV?$task@X@pplx@@HVexception_ptr@std@@@Z`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180061c50`
- `0x1800636dc`
- `0x1800a3454`
- `0x1800a68e0`
- `0x1800a8c18`
- `0x1800c0e80`
- `0x1800c17e8`
- `0x180101010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c0f98`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c0f98`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c0ede`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c0ede`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Concurrency::streams::streambuf<char>::close(__int64 a1, _QWORD *a2, unsigned int a3, void *a4)
{
  __int64 base; // rax
  __int64 v8; // r8
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, _BYTE *, _QWORD, __int128 *); // rbx
  _QWORD *v11; // rcx
  char v12; // bl
  __int64 v13; // rax
  char v14; // bl
  __int128 v16; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v18[16]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v19[16]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v20[120]; // [rsp+78h] [rbp-21h] BYREF

  base = Concurrency::streams::streambuf<char>::get_base();
  std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v17, base, v8);
  v9 = v17[0];
  if ( v17[0] )
  {
    v10 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int128 *))(*(_QWORD *)v17[0] + 80LL);
    v16 = 0;
    __ExceptionPtrCopy(&v16, a4);
    v11 = (_QWORD *)v10(v9, v19, a3, &v16);
    v12 = 1;
  }
  else
  {
    v13 = pplx::task_options::task_options((pplx::task_options *)v20);
    v11 = (_QWORD *)pplx::task_from_result<void>(v18, v13);
    v12 = 6;
  }
  *a2 = 0;
  a2[1] = 0;
  *a2 = *v11;
  a2[1] = v11[1];
  *v11 = 0;
  v11[1] = 0;
  v14 = v12 | 8;
  if ( (v14 & 4) != 0 )
  {
    v14 &= ~4u;
    std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v18);
  }
  if ( (v14 & 2) != 0 )
  {
    v14 &= ~2u;
    pplx::task_options::~task_options((pplx::task_options *)v20);
  }
  if ( (v14 & 1) != 0 )
    std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v19);
  std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v17);
  __ExceptionPtrDestroy(a4);
  return a2;
}

```

## disassembly

```asm
0x1800c0e80  mov     [rsp-8+arg_0], rbx
0x1800c0e85  mov     [rsp-8+arg_18], r9
0x1800c0e8a  push    rbp
0x1800c0e8b  push    rsi
0x1800c0e8c  push    rdi
0x1800c0e8d  push    r14
0x1800c0e8f  push    r15
0x1800c0e91  lea     rbp, [rsp-37h]
0x1800c0e96  sub     rsp, 0D0h
0x1800c0e9d  mov     rsi, r9
0x1800c0ea0  mov     r15d, r8d
0x1800c0ea3  mov     rdi, rdx
0x1800c0ea6  mov     [rbp+57h+var_C0], 0
0x1800c0ead  call    ?get_base@?$streambuf@D@streams@Concurrency@@QEBAAEBV?$shared_ptr@V?$basic_streambuf@D@details@streams@Concurrency@@@std@@XZ; Concurrency::streams::streambuf<char>::get_base(void)
0x1800c0eb2  mov     rdx, rax
0x1800c0eb5  lea     rcx, [rbp+57h+var_A8]
0x1800c0eb9  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800c0ebe  nop
0x1800c0ebf  mov     r14, [rbp+57h+var_A8]
0x1800c0ec3  test    r14, r14
0x1800c0ec6  jz      short loc_1800C0F04
0x1800c0ec8  mov     rax, [r14]
0x1800c0ecb  mov     rbx, [rax+50h]
0x1800c0ecf  xorps   xmm0, xmm0
0x1800c0ed2  movdqu  [rbp+57h+var_B8], xmm0
0x1800c0ed7  mov     rdx, rsi
0x1800c0eda  lea     rcx, [rbp+57h+var_B8]
0x1800c0ede  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c0ee4  lea     r9, [rbp+57h+var_B8]
0x1800c0ee8  mov     r8d, r15d
0x1800c0eeb  lea     rdx, [rbp+57h+var_88]
0x1800c0eef  mov     rcx, r14
0x1800c0ef2  mov     rax, rbx
0x1800c0ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0efa  mov     rcx, rax
0x1800c0efd  mov     ebx, 1
0x1800c0f02  jmp     short loc_1800C0F29
0x1800c0f04  lea     rcx, [rbp+57h+var_78]; this
0x1800c0f08  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x1800c0f0d  nop
0x1800c0f0e  mov     [rbp+57h+var_C0], 2
0x1800c0f15  mov     rdx, rax
0x1800c0f18  lea     rcx, [rbp+57h+var_98]
0x1800c0f1c  call    ??$task_from_result@X@pplx@@YA?AV?$task@X@0@AEBVtask_options@0@@Z; pplx::task_from_result<void>(pplx::task_options const &)
0x1800c0f21  mov     rcx, rax
0x1800c0f24  mov     ebx, 6
0x1800c0f29  mov     qword ptr [rdi], 0
0x1800c0f30  mov     qword ptr [rdi+8], 0
0x1800c0f38  mov     rax, [rcx]
0x1800c0f3b  mov     [rdi], rax
0x1800c0f3e  mov     rax, [rcx+8]
0x1800c0f42  mov     [rdi+8], rax
0x1800c0f46  mov     qword ptr [rcx], 0
0x1800c0f4d  mov     qword ptr [rcx+8], 0
0x1800c0f55  or      ebx, 8
0x1800c0f58  test    bl, 4
0x1800c0f5b  jz      short loc_1800C0F6A
0x1800c0f5d  and     ebx, 0FFFFFFFBh
0x1800c0f60  lea     rcx, [rbp+57h+var_98]
0x1800c0f64  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800c0f69  nop
0x1800c0f6a  test    bl, 2
0x1800c0f6d  jz      short loc_1800C0F7C
0x1800c0f6f  and     ebx, 0FFFFFFFDh
0x1800c0f72  lea     rcx, [rbp+57h+var_78]; this
0x1800c0f76  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x1800c0f7b  nop
0x1800c0f7c  test    bl, 1
0x1800c0f7f  jz      short loc_1800C0F8B
0x1800c0f81  lea     rcx, [rbp+57h+var_88]
0x1800c0f85  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800c0f8a  nop
0x1800c0f8b  lea     rcx, [rbp+57h+var_A8]
0x1800c0f8f  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800c0f94  nop
0x1800c0f95  mov     rcx, rsi
0x1800c0f98  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c0f9e  mov     rax, rdi
0x1800c0fa1  mov     rbx, [rsp+0F0h+arg_0]
0x1800c0fa9  add     rsp, 0D0h
0x1800c0fb0  pop     r15
0x1800c0fb2  pop     r14
0x1800c0fb4  pop     rdi
0x1800c0fb5  pop     rsi
0x1800c0fb6  pop     rbp
0x1800c0fb7  retn
```
