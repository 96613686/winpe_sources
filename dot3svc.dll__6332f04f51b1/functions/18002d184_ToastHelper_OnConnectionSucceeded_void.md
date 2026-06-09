# ToastHelper::OnConnectionSucceeded(void)

- ea: `0x18002d184`
- end: `0x18002d297`
- name: `?OnConnectionSucceeded@ToastHelper@@QEAAJXZ`
- size: `275`
- prototype: `__int64 __fastcall(ToastHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023ce0`

## callees

- `0x18000c230`
- `0x18001bd4c`
- `0x1800289b8`
- `0x18002d184`
- `0x18002da30`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002d21e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002d21e`

## pseudocode

```c
__int64 __fastcall ToastHelper::OnConnectionSucceeded(ToastHelper *this)
{
  unsigned int v2; // ebx
  __int64 *v3; // rax
  __int64 v4; // rdi
  int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  ToastHelper *v9; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 34, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
  }
  v9 = this;
  v2 = *((_DWORD *)this + 8);
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_a6be452d3d4248434c801bc34cf78214_____lambda_a6be452d3d4248434c801bc34cf78214___(
                    &v8,
                    &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v8 )
  {
    v8 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v5 = SHTaskPoolQueueTask(0, 2, v2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x193,
      (int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)(unsigned int)v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d184  mov     [rsp+arg_10], rbx
0x18002d189  mov     [rsp+arg_18], rbp
0x18002d18e  push    rdi
0x18002d18f  sub     rsp, 30h
0x18002d193  mov     rbx, rcx
0x18002d196  lea     rbp, WPP_GLOBAL_Control
0x18002d19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1a4  cmp     rcx, rbp
0x18002d1a7  jz      short loc_18002D1CA
0x18002d1a9  cmp     byte ptr [rcx+19h], 4
0x18002d1ad  jb      short loc_18002D1CA
0x18002d1af  test    byte ptr [rcx+1Ch], 1
0x18002d1b3  jz      short loc_18002D1CA
0x18002d1b5  mov     edx, 22h ; '"'
0x18002d1ba  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d1c1  mov     rcx, [rcx+10h]
0x18002d1c5  call    WPP_SF_
0x18002d1ca  mov     [rsp+38h+arg_8], rbx
0x18002d1cf  mov     ebx, [rbx+20h]
0x18002d1d2  nop
0x18002d1d3  lea     rdx, [rsp+38h+arg_8]
0x18002d1d8  lea     rcx, [rsp+38h+arg_0]
0x18002d1dd  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_a6be452d3d4248434c801bc34cf78214_____lambda_a6be452d3d4248434c801bc34cf78214___
0x18002d1e2  mov     rdi, [rax]
0x18002d1e5  mov     qword ptr [rax], 0
0x18002d1ec  mov     rcx, [rsp+38h+arg_0]
0x18002d1f1  test    rcx, rcx
0x18002d1f4  jz      short loc_18002D204
0x18002d1f6  mov     [rsp+38h+arg_0], 0
0x18002d1ff  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002d204  mov     [rsp+38h+var_10], 0
0x18002d20d  mov     qword ptr [rsp+38h+var_18], rdi; int
0x18002d212  xor     r9d, r9d
0x18002d215  mov     r8d, ebx
0x18002d218  lea     edx, [r9+2]
0x18002d21c  xor     ecx, ecx
0x18002d21e  call    cs:__imp_SHTaskPoolQueueTask
0x18002d224  mov     ebx, eax
0x18002d226  test    rdi, rdi
0x18002d229  jz      short loc_18002D23B
0x18002d22b  mov     rdx, [rdi]
0x18002d22e  mov     rcx, rdi
0x18002d231  mov     rax, [rdx+10h]
0x18002d235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d23a  nop
0x18002d23b  test    ebx, ebx
0x18002d23d  jns     short loc_18002D258
0x18002d23f  mov     rcx, [rsp+38h]; this
0x18002d244  mov     r9d, ebx; char *
0x18002d247  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d24e  mov     edx, 193h; void *
0x18002d253  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d258  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d25f  cmp     rcx, rbp
0x18002d262  jz      short loc_18002D285
0x18002d264  cmp     byte ptr [rcx+19h], 4
0x18002d268  jb      short loc_18002D285
0x18002d26a  test    byte ptr [rcx+1Ch], 1
0x18002d26e  jz      short loc_18002D285
0x18002d270  mov     edx, 23h ; '#'
0x18002d275  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d27c  mov     rcx, [rcx+10h]
0x18002d280  call    WPP_SF_
0x18002d285  xor     eax, eax
0x18002d287  mov     rbx, [rsp+38h+arg_10]
0x18002d28c  mov     rbp, [rsp+38h+arg_18]
0x18002d291  add     rsp, 30h
0x18002d295  pop     rdi
0x18002d296  retn
```
