# RefreshTaskThreadThunk(void *)

- ea: `0x180037120`
- end: `0x18003729c`
- name: `?RefreshTaskThreadThunk@@YAIPEAX@Z`
- size: `380`
- prototype: `unsigned int __fastcall(void *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012748`
- `0x180012770`
- `0x180036524`
- `0x180037120`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037164`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037164`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037175`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037226`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037175`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180037226`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800371e1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800371e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180037213`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180037213`

## pseudocode

```c
__int64 __fastcall RefreshTaskThreadThunk(IStream *Parameter)
{
  HANDLE CurrentThread; // rsi
  char v3; // di
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  DWORD LastError; // eax
  HRESULT v6; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v7; // rcx
  DWORD v8; // eax
  RefreshTaskThreadThunk::__l8::<lambda_1> f; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
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
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, LastError);
    goto LABEL_9;
  }
LABEL_10:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v4->Control.Logger, 0x1Eu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
LABEL_13:
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    f.pStream = Parameter;
    v6 = ExecuteAndConvertAnyException__RefreshTaskThreadThunk_::_8_::_lambda_1___(&f);
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
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Fu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, v8);
LABEL_20:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v7->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v7->Control.Logger, 0x20u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037120  mov     [rsp+arg_0], rbx
0x180037125  push    rbp
0x180037126  push    rsi
0x180037127  push    rdi
0x180037128  push    r14
0x18003712a  push    r15
0x18003712c  sub     rsp, 20h
0x180037130  mov     r14, Parameter
0x180037133  lea     rbp, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003713a  lea     r15, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids
0x180037141  mov     Parameter, cs:WPP_GLOBAL_Control
0x180037148  cmp     Parameter, rbp
0x18003714b  jz      short loc_180037164
0x18003714d  test    byte ptr [Parameter+1Ch], 10h
0x180037151  jz      short loc_180037164
0x180037153  mov     edx, 1Ch; id
0x180037158  mov     r8, r15; TraceGuid
0x18003715b  mov     Parameter, [Parameter+10h]; Logger
0x18003715f  call    WPP_SF_
0x180037164  call    cs:__imp_GetCurrentThread
0x18003716a  mov     rsi, rax
0x18003716d  mov     edx, 10000h; nPriority
0x180037172  mov     Parameter, rax; hThread
0x180037175  call    cs:__imp_SetThreadPriority
0x18003717b  test    eax, eax
0x18003717d  jz      short loc_180037184
0x18003717f  mov     dil, 1
0x180037182  jmp     short loc_1800371BA
0x180037184  xor     dil, dil
0x180037187  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003718e  cmp     Parameter, rbp
0x180037191  jz      short loc_1800371DD
0x180037193  test    byte ptr [Parameter+1Ch], 4
0x180037197  jz      short loc_1800371C1
0x180037199  call    cs:__imp_GetLastError
0x18003719f  mov     edx, 1Dh; id
0x1800371a4  mov     r9d, eax; _a1
0x1800371a7  mov     r8, r15; TraceGuid
0x1800371aa  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800371b1  mov     Parameter, [Parameter+10h]; Logger
0x1800371b5  call    WPP_SF_d
0x1800371ba  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800371c1  cmp     Parameter, rbp; __annotation("TMF:",
0x1800371c4  jz      short loc_1800371DD
0x1800371c6  test    byte ptr [Parameter+1Ch], 10h
0x1800371ca  jz      short loc_1800371DD
0x1800371cc  mov     edx, 1Eh; id
0x1800371d1  mov     r8, r15; TraceGuid
0x1800371d4  mov     Parameter, [Parameter+10h]; Logger
0x1800371d8  call    WPP_SF_
0x1800371dd  xor     edx, edx; dwCoInit
0x1800371df  xor     ecx, ecx; pvReserved
0x1800371e1  call    cs:__imp_CoInitializeEx
0x1800371e7  mov     ebx, eax
0x1800371e9  test    eax, eax
0x1800371eb  js      short loc_180037219
0x1800371ed  mov     [rsp+48h+coUninit.m_call], 1
0x1800371f2  mov     [rsp+48h+f.pStream], r14
0x1800371f7  lea     Parameter, [rsp+48h+f]; f
0x1800371fc  call    ExecuteAndConvertAnyException__RefreshTaskThreadThunk____8____lambda_1___
0x180037201  mov     ebx, eax
0x180037203  mov     rax, [r14]
0x180037206  mov     Parameter, r14
0x180037209  mov     rax, [rax+10h]
0x18003720d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037212  nop
0x180037213  call    cs:__imp_CoUninitialize
0x180037219  test    dil, dil
0x18003721c  jz      short loc_180037263
0x18003721e  mov     edx, 20000h; nPriority
0x180037223  mov     Parameter, rsi; hThread
0x180037226  call    cs:__imp_SetThreadPriority
0x18003722c  test    eax, eax
0x18003722e  jnz     short loc_180037263
0x180037230  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180037237  cmp     Parameter, rbp
0x18003723a  jz      short loc_180037289
0x18003723c  test    byte ptr [Parameter+1Ch], 4
0x180037240  jz      short loc_18003726A
0x180037242  call    cs:__imp_GetLastError
0x180037248  mov     edx, 1Fh; id
0x18003724d  mov     r9d, eax; _a1
0x180037250  mov     r8, r15; TraceGuid
0x180037253  mov     Parameter, cs:WPP_GLOBAL_Control
0x18003725a  mov     Parameter, [Parameter+10h]; Logger
0x18003725e  call    WPP_SF_d
0x180037263  mov     Parameter, cs:WPP_GLOBAL_Control
0x18003726a  cmp     Parameter, rbp; __annotation("TMF:",
0x18003726d  jz      short loc_180037289
0x18003726f  test    byte ptr [Parameter+1Ch], 10h
0x180037273  jz      short loc_180037289
0x180037275  mov     edx, 20h ; ' '; id
0x18003727a  mov     r9d, ebx; _a1
0x18003727d  mov     r8, r15; TraceGuid
0x180037280  mov     Parameter, [Parameter+10h]; Logger
0x180037284  call    WPP_SF_d
0x180037289  mov     eax, ebx
0x18003728b  mov     rbx, [rsp+48h+arg_0]
0x180037290  add     rsp, 20h
0x180037294  pop     r15
0x180037296  pop     r14
0x180037298  pop     rdi
0x180037299  pop     rsi
0x18003729a  pop     rbp
0x18003729b  retn
```
