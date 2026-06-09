# ToastHelper::OnMediumDisconnected(void)

- ea: `0x18002d2dc`
- end: `0x18002d3ef`
- name: `?OnMediumDisconnected@ToastHelper@@QEAAJXZ`
- size: `275`
- prototype: `__int64 __fastcall(ToastHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019d94`

## callees

- `0x18000c230`
- `0x18001bd4c`
- `0x1800289b8`
- `0x18002d2dc`
- `0x18002da30`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002d376`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002d376`

## pseudocode

```c
__int64 __fastcall ToastHelper::OnMediumDisconnected(ToastHelper *this)
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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 40, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
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
      (void *)0x1AE,
      (int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)(unsigned int)v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 41, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d2dc  mov     [rsp+arg_10], rbx
0x18002d2e1  mov     [rsp+arg_18], rbp
0x18002d2e6  push    rdi
0x18002d2e7  sub     rsp, 30h
0x18002d2eb  mov     rbx, rcx
0x18002d2ee  lea     rbp, WPP_GLOBAL_Control
0x18002d2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2fc  cmp     rcx, rbp
0x18002d2ff  jz      short loc_18002D322
0x18002d301  cmp     byte ptr [rcx+19h], 4
0x18002d305  jb      short loc_18002D322
0x18002d307  test    byte ptr [rcx+1Ch], 1
0x18002d30b  jz      short loc_18002D322
0x18002d30d  mov     edx, 28h ; '('
0x18002d312  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d319  mov     rcx, [rcx+10h]
0x18002d31d  call    WPP_SF_
0x18002d322  mov     [rsp+38h+arg_8], rbx
0x18002d327  mov     ebx, [rbx+20h]
0x18002d32a  nop
0x18002d32b  lea     rdx, [rsp+38h+arg_8]
0x18002d330  lea     rcx, [rsp+38h+arg_0]
0x18002d335  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_a6be452d3d4248434c801bc34cf78214_____lambda_a6be452d3d4248434c801bc34cf78214___
0x18002d33a  mov     rdi, [rax]
0x18002d33d  mov     qword ptr [rax], 0
0x18002d344  mov     rcx, [rsp+38h+arg_0]
0x18002d349  test    rcx, rcx
0x18002d34c  jz      short loc_18002D35C
0x18002d34e  mov     [rsp+38h+arg_0], 0
0x18002d357  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002d35c  mov     [rsp+38h+var_10], 0
0x18002d365  mov     qword ptr [rsp+38h+var_18], rdi; int
0x18002d36a  xor     r9d, r9d
0x18002d36d  mov     r8d, ebx
0x18002d370  lea     edx, [r9+2]
0x18002d374  xor     ecx, ecx
0x18002d376  call    cs:__imp_SHTaskPoolQueueTask
0x18002d37c  mov     ebx, eax
0x18002d37e  test    rdi, rdi
0x18002d381  jz      short loc_18002D393
0x18002d383  mov     rdx, [rdi]
0x18002d386  mov     rcx, rdi
0x18002d389  mov     rax, [rdx+10h]
0x18002d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d392  nop
0x18002d393  test    ebx, ebx
0x18002d395  jns     short loc_18002D3B0
0x18002d397  mov     rcx, [rsp+38h]; this
0x18002d39c  mov     r9d, ebx; char *
0x18002d39f  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002d3a6  mov     edx, 1AEh; void *
0x18002d3ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3b7  cmp     rcx, rbp
0x18002d3ba  jz      short loc_18002D3DD
0x18002d3bc  cmp     byte ptr [rcx+19h], 4
0x18002d3c0  jb      short loc_18002D3DD
0x18002d3c2  test    byte ptr [rcx+1Ch], 1
0x18002d3c6  jz      short loc_18002D3DD
0x18002d3c8  mov     edx, 29h ; ')'
0x18002d3cd  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002d3d4  mov     rcx, [rcx+10h]
0x18002d3d8  call    WPP_SF_
0x18002d3dd  xor     eax, eax
0x18002d3df  mov     rbx, [rsp+38h+arg_10]
0x18002d3e4  mov     rbp, [rsp+38h+arg_18]
0x18002d3e9  add     rsp, 30h
0x18002d3ed  pop     rdi
0x18002d3ee  retn
```
