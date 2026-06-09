# winrt::Windows::Foundation::AsyncActionCompletedHandler::AsyncActionCompletedHandler(_lambda_dc4921c5914f1dac0ac69065375e73ef_)

- ea: `0x180016054`
- end: `0x1800160ea`
- name: `??$?0V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@AsyncActionCompletedHandler@Foundation@Windows@winrt@@QEAA@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@Z`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001711c`

## callees

- `0x180001640`
- `0x180002158`
- `0x1800065f0`
- `0x180016054`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Foundation::AsyncActionCompletedHandler::AsyncActionCompletedHandler(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rax
  char *v6; // [rsp+28h] [rbp-20h]

  v6 = (char *)operator new(0x28u);
  *((_DWORD *)v6 + 2) = 1;
  v4 = *(_QWORD *)a2;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)v6 + 2) = v4;
  *(_OWORD *)(v6 + 24) = *(_OWORD *)(a2 + 8);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v6 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable';
  *a1 = v6;
  if ( *(_QWORD *)a2 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)a2);
  return a1;
}

```

## disassembly

```asm
0x180016054  mov     [rsp+arg_10], rbx
0x180016059  push    rdi
0x18001605a  sub     rsp, 40h
0x18001605e  mov     rax, cs:__security_cookie
0x180016065  xor     rax, rsp
0x180016068  mov     [rsp+48h+var_18], rax
0x18001606d  mov     rbx, rdx
0x180016070  mov     rdi, rcx
0x180016073  mov     [rsp+48h+var_28], rcx
0x180016078  mov     [rsp+48h+var_20], rdx
0x18001607d  mov     ecx, 28h ; '('; Size
0x180016082  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016087  mov     rdx, rax
0x18001608a  mov     [rsp+48h+var_20], rax
0x18001608f  mov     dword ptr [rax+8], 1
0x180016096  mov     rax, [rbx]
0x180016099  mov     qword ptr [rbx], 0
0x1800160a0  mov     [rdx+10h], rax
0x1800160a4  movups  xmm0, xmmword ptr [rbx+8]
0x1800160a8  movdqu  xmmword ptr [rdx+18h], xmm0
0x1800160ad  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800160b4  lea     rax, ??_7?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable'
0x1800160bb  mov     [rdx], rax
0x1800160be  mov     [rdi], rdx
0x1800160c1  cmp     qword ptr [rbx], 0
0x1800160c5  jz      short loc_1800160CF
0x1800160c7  mov     rcx, rbx
0x1800160ca  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800160cf  mov     rax, rdi
0x1800160d2  mov     rcx, [rsp+48h+var_18]
0x1800160d7  xor     rcx, rsp; StackCookie
0x1800160da  call    __security_check_cookie
0x1800160df  mov     rbx, [rsp+48h+arg_10]
0x1800160e4  add     rsp, 40h
0x1800160e8  pop     rdi
0x1800160e9  retn
```
