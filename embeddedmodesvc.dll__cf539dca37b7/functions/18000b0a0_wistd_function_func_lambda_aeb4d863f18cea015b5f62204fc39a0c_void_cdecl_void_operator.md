# wistd::__function::__func__lambda_aeb4d863f18cea015b5f62204fc39a0c__void___cdecl(void)_::operator()

- ea: `0x18000b0a0`
- end: `0x18000b125`
- name: `wistd::__function::__func__lambda_aeb4d863f18cea015b5f62204fc39a0c__void___cdecl(void)_::operator()`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003998`
- `0x180008378`
- `0x180009a90`
- `0x18000b0a0`
- `0x18000da64`
- `0x18001b010`

## string_xrefs

- `0x18000b109`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wistd::__function::__func__lambda_aeb4d863f18cea015b5f62204fc39a0c__void___cdecl_void__::operator()(
        __int64 a1)
{
  __int64 v1; // rdx
  Microsoft::IoT::Utility::MTAThreadPool *v2; // rbx
  _QWORD *v3; // rax
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v4; // rdi
  int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  v2 = *(Microsoft::IoT::Utility::MTAThreadPool **)(v1 + 72);
  v3 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v8, v1);
  Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_1bb57df98d7ba98072f104d9e64aece0_____lambda_1bb57df98d7ba98072f104d9e64aece0___(
    &v7,
    v3);
  v4 = v7;
  if ( v7 )
    v5 = Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(v2, v7);
  else
    v5 = -2147024882;
  if ( v4 )
    (*(void (__fastcall **)(struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
      (const char *)(unsigned int)v5);
}

```

## disassembly

```asm
0x18000b0a0  mov     [rsp+arg_10], rbx
0x18000b0a5  push    rdi; int
0x18000b0a6  sub     rsp, 20h
0x18000b0aa  mov     rdx, [rcx+8]
0x18000b0ae  mov     rbx, [rdx+48h]
0x18000b0b2  lea     rcx, [rsp+28h+arg_8]
0x18000b0b7  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000b0bc  mov     rdx, rax
0x18000b0bf  lea     rcx, [rsp+28h+arg_0]
0x18000b0c4  call    Microsoft__WRL__Details__Make_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_1bb57df98d7ba98072f104d9e64aece0_____lambda_1bb57df98d7ba98072f104d9e64aece0___
0x18000b0c9  nop
0x18000b0ca  mov     rdi, [rsp+28h+arg_0]
0x18000b0cf  test    rdi, rdi
0x18000b0d2  jnz     short loc_18000B0DB
0x18000b0d4  mov     ebx, 8007000Eh
0x18000b0d9  jmp     short loc_18000B0E8
0x18000b0db  mov     rdx, rdi; struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *
0x18000b0de  mov     rcx, rbx; this
0x18000b0e1  call    ?QueueWorkItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJPEAUIMTAThreadPoolWorkCallback@234@@Z; Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *)
0x18000b0e6  mov     ebx, eax
0x18000b0e8  test    rdi, rdi
0x18000b0eb  jz      short loc_18000B0FD
0x18000b0ed  mov     rdx, [rdi]
0x18000b0f0  mov     rcx, rdi
0x18000b0f3  mov     rax, [rdx+10h]
0x18000b0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fc  nop
0x18000b0fd  test    ebx, ebx
0x18000b0ff  jns     short loc_18000B11A
0x18000b101  mov     rcx, [rsp+28h]; this
0x18000b106  mov     r9d, ebx; char *
0x18000b109  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b110  mov     edx, 61h ; 'a'; void *
0x18000b115  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b11a  mov     rbx, [rsp+28h+arg_10]
0x18000b11f  add     rsp, 20h
0x18000b123  pop     rdi
0x18000b124  retn
```
