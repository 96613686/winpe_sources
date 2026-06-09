# Microsoft::IoT::ShellExtension::CCBTLauncher::AsyncLaunchCBT(void)

- ea: `0x180010db8`
- end: `0x180010e3f`
- name: `?AsyncLaunchCBT@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ba9c`

## callees

- `0x180003998`
- `0x180008358`
- `0x18000da64`
- `0x18000f3a8`
- `0x180010db8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::AsyncLaunchCBT(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  Microsoft::IoT::Utility::MTAThreadPool *v1; // rbx
  __int64 v2; // rax
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v3; // rdi
  int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v8; // [rsp+30h] [rbp+8h] BYREF
  char v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = (Microsoft::IoT::Utility::MTAThreadPool *)*((_QWORD *)this + 9);
  v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v9, this);
  Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____lambda_645992aee5a6b4af0977e82444ecfa7d___(
    &v8,
    v2);
  v3 = v8;
  if ( v8 )
    v4 = Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(v1, v8);
  else
    v4 = -2147024882;
  if ( v3 )
    (*(void (__fastcall **)(struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v4,
      v6);
  return 0;
}

```

## disassembly

```asm
0x180010db8  mov     [rsp+arg_10], rbx
0x180010dbd  push    rdi; int
0x180010dbe  sub     rsp, 20h
0x180010dc2  mov     rbx, [rcx+48h]
0x180010dc6  mov     rdx, rcx
0x180010dc9  lea     rcx, [rsp+28h+arg_8]
0x180010dce  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180010dd3  mov     rdx, rax
0x180010dd6  lea     rcx, [rsp+28h+arg_0]
0x180010ddb  call    Microsoft__WRL__Details__Make_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_645992aee5a6b4af0977e82444ecfa7d_____lambda_645992aee5a6b4af0977e82444ecfa7d___
0x180010de0  nop
0x180010de1  mov     rdi, [rsp+28h+arg_0]
0x180010de6  test    rdi, rdi
0x180010de9  jnz     short loc_180010DF2
0x180010deb  mov     ebx, 8007000Eh
0x180010df0  jmp     short loc_180010DFF
0x180010df2  mov     rdx, rdi; struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *
0x180010df5  mov     rcx, rbx; this
0x180010df8  call    ?QueueWorkItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJPEAUIMTAThreadPoolWorkCallback@234@@Z; Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *)
0x180010dfd  mov     ebx, eax
0x180010dff  test    rdi, rdi
0x180010e02  jz      short loc_180010E14
0x180010e04  mov     rdx, [rdi]
0x180010e07  mov     rcx, rdi
0x180010e0a  mov     rax, [rdx+10h]
0x180010e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e13  nop
0x180010e14  test    ebx, ebx
0x180010e16  jns     short loc_180010E32
0x180010e18  mov     rcx, [rsp+28h]; this
0x180010e1d  mov     r9d, ebx; char *
0x180010e20  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180010e27  mov     edx, 22Ah; void *
0x180010e2c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180010e32  xor     eax, eax
0x180010e34  mov     rbx, [rsp+28h+arg_10]
0x180010e39  add     rsp, 20h
0x180010e3d  pop     rdi
0x180010e3e  retn
```
