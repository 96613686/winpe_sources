# ActivationTaskThreadThunk(void *)

- ea: `0x180018290`
- end: `0x18001840c`
- name: `?ActivationTaskThreadThunk@@YAIPEAX@Z`
- size: `380`
- prototype: `unsigned int __fastcall(void *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012748`
- `0x180012770`
- `0x180017558`
- `0x180018290`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800182d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800182d4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800182e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180018396`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800182e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180018396`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018351`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018351`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018383`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018383`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ActivationTaskThreadThunk(IStream *Parameter)
{
  HANDLE CurrentThread; // rsi
  char v3; // di
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  DWORD LastError; // eax
  HRESULT v6; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v7; // rcx
  DWORD v8; // eax
  ActivationTaskThreadThunk::__l8::<lambda_1> f; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x29u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
  }
  CurrentThread = GetCurrentThread();
  if ( SetThreadPriority(CurrentThread, 0x10000) )
  {
    v3 = 1;
LABEL_9:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v3 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    goto LABEL_13;
  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Au, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, LastError);
    goto LABEL_9;
  }
LABEL_10:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v4->Control.Logger, 0x2Bu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
LABEL_13:
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    f.pStream = Parameter;
    v6 = ExecuteAndConvertAnyException__ActivationTaskThreadThunk_::_8_::_lambda_1___(&f);
    Parameter->Release(Parameter);
    CoUninitialize();
  }
  if ( !v3 || SetThreadPriority(CurrentThread, 0x20000) )
    goto LABEL_20;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    return (unsigned int)v6;
  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    v8 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Cu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v8);
LABEL_20:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v7->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v7->Control.Logger, 0x2Du, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018290  mov     [rsp+arg_0], rbx
0x180018295  push    rbp
0x180018296  push    rsi
0x180018297  push    rdi
0x180018298  push    r14
0x18001829a  push    r15
0x18001829c  sub     rsp, 20h
0x1800182a0  mov     r14, Parameter
0x1800182a3  lea     rbp, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800182aa  lea     r15, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids
0x1800182b1  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800182b8  cmp     Parameter, rbp
0x1800182bb  jz      short loc_1800182D4
0x1800182bd  test    byte ptr [Parameter+1Ch], 10h
0x1800182c1  jz      short loc_1800182D4
0x1800182c3  mov     edx, 29h ; ')'; id
0x1800182c8  mov     r8, r15; TraceGuid
0x1800182cb  mov     Parameter, [Parameter+10h]; Logger
0x1800182cf  call    WPP_SF_
0x1800182d4  call    cs:__imp_GetCurrentThread
0x1800182da  mov     rsi, rax
0x1800182dd  mov     edx, 10000h; nPriority
0x1800182e2  mov     Parameter, rax; hThread
0x1800182e5  call    cs:__imp_SetThreadPriority
0x1800182eb  test    eax, eax
0x1800182ed  jz      short loc_1800182F4
0x1800182ef  mov     dil, 1
0x1800182f2  jmp     short loc_18001832A
0x1800182f4  xor     dil, dil
0x1800182f7  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800182fe  cmp     Parameter, rbp
0x180018301  jz      short loc_18001834D
0x180018303  test    byte ptr [Parameter+1Ch], 4
0x180018307  jz      short loc_180018331
0x180018309  call    cs:__imp_GetLastError
0x18001830f  mov     edx, 2Ah ; '*'; id
0x180018314  mov     r9d, eax; _a1
0x180018317  mov     r8, r15; TraceGuid
0x18001831a  mov     Parameter, cs:WPP_GLOBAL_Control
0x180018321  mov     Parameter, [Parameter+10h]; Logger
0x180018325  call    WPP_SF_d
0x18001832a  mov     Parameter, cs:WPP_GLOBAL_Control
0x180018331  cmp     Parameter, rbp; __annotation("TMF:",
0x180018334  jz      short loc_18001834D
0x180018336  test    byte ptr [Parameter+1Ch], 10h
0x18001833a  jz      short loc_18001834D
0x18001833c  mov     edx, 2Bh ; '+'; id
0x180018341  mov     r8, r15; TraceGuid
0x180018344  mov     Parameter, [Parameter+10h]; Logger
0x180018348  call    WPP_SF_
0x18001834d  xor     edx, edx; dwCoInit
0x18001834f  xor     ecx, ecx; pvReserved
0x180018351  call    cs:__imp_CoInitializeEx
0x180018357  mov     ebx, eax
0x180018359  test    eax, eax
0x18001835b  js      short loc_180018389
0x18001835d  mov     [rsp+48h+coUninit.m_call], 1
0x180018362  mov     [rsp+48h+f.pStream], r14
0x180018367  lea     Parameter, [rsp+48h+f]; f
0x18001836c  call    ExecuteAndConvertAnyException__ActivationTaskThreadThunk____8____lambda_1___
0x180018371  mov     ebx, eax
0x180018373  mov     rax, [r14]
0x180018376  mov     Parameter, r14
0x180018379  mov     rax, [rax+10h]
0x18001837d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018382  nop
0x180018383  call    cs:__imp_CoUninitialize
0x180018389  test    dil, dil
0x18001838c  jz      short loc_1800183D3
0x18001838e  mov     edx, 20000h; nPriority
0x180018393  mov     Parameter, rsi; hThread
0x180018396  call    cs:__imp_SetThreadPriority
0x18001839c  test    eax, eax
0x18001839e  jnz     short loc_1800183D3
0x1800183a0  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800183a7  cmp     Parameter, rbp
0x1800183aa  jz      short loc_1800183F9
0x1800183ac  test    byte ptr [Parameter+1Ch], 4
0x1800183b0  jz      short loc_1800183DA
0x1800183b2  call    cs:__imp_GetLastError
0x1800183b8  mov     edx, 2Ch ; ','; id
0x1800183bd  mov     r9d, eax; _a1
0x1800183c0  mov     r8, r15; TraceGuid
0x1800183c3  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800183ca  mov     Parameter, [Parameter+10h]; Logger
0x1800183ce  call    WPP_SF_d
0x1800183d3  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800183da  cmp     Parameter, rbp; __annotation("TMF:",
0x1800183dd  jz      short loc_1800183F9
0x1800183df  test    byte ptr [Parameter+1Ch], 10h
0x1800183e3  jz      short loc_1800183F9
0x1800183e5  mov     edx, 2Dh ; '-'; id
0x1800183ea  mov     r9d, ebx; _a1
0x1800183ed  mov     r8, r15; TraceGuid
0x1800183f0  mov     Parameter, [Parameter+10h]; Logger
0x1800183f4  call    WPP_SF_d
0x1800183f9  mov     eax, ebx
0x1800183fb  mov     rbx, [rsp+48h+arg_0]
0x180018400  add     rsp, 20h
0x180018404  pop     r15
0x180018406  pop     r14
0x180018408  pop     rdi
0x180018409  pop     rsi
0x18001840a  pop     rbp
0x18001840b  retn
```
