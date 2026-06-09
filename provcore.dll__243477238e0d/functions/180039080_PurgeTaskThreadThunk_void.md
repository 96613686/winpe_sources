# PurgeTaskThreadThunk(void *)

- ea: `0x180039080`
- end: `0x1800391fc`
- name: `?PurgeTaskThreadThunk@@YAIPEAX@Z`
- size: `380`
- prototype: `unsigned int __fastcall(void *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012748`
- `0x180012770`
- `0x180037b50`
- `0x180039080`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800390c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800390c4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800390d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180039186`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800390d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180039186`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039141`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039141`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039173`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039173`

## pseudocode

```c
__int64 __fastcall PurgeTaskThreadThunk(IStream *Parameter)
{
  HANDLE CurrentThread; // rsi
  char v3; // di
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  DWORD LastError; // eax
  HRESULT v6; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v7; // rcx
  DWORD v8; // eax
  PurgeTaskThreadThunk::__l8::<lambda_1> f; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x25u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
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
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x26u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids, LastError);
    goto LABEL_9;
  }
LABEL_10:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v4->Control.Logger, 0x27u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
LABEL_13:
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    f.pStream = Parameter;
    v6 = ExecuteAndConvertAnyException__PurgeTaskThreadThunk_::_8_::_lambda_1___(&f);
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
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x28u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids, v8);
LABEL_20:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v7->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v7->Control.Logger, 0x29u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039080  mov     [rsp+arg_0], rbx
0x180039085  push    rbp
0x180039086  push    rsi
0x180039087  push    rdi
0x180039088  push    r14
0x18003908a  push    r15
0x18003908c  sub     rsp, 20h
0x180039090  mov     r14, Parameter
0x180039093  lea     rbp, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003909a  lea     r15, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids
0x1800390a1  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800390a8  cmp     Parameter, rbp
0x1800390ab  jz      short loc_1800390C4
0x1800390ad  test    byte ptr [Parameter+1Ch], 10h
0x1800390b1  jz      short loc_1800390C4
0x1800390b3  mov     edx, 25h ; '%'; id
0x1800390b8  mov     r8, r15; TraceGuid
0x1800390bb  mov     Parameter, [Parameter+10h]; Logger
0x1800390bf  call    WPP_SF_
0x1800390c4  call    cs:__imp_GetCurrentThread
0x1800390ca  mov     rsi, rax
0x1800390cd  mov     edx, 10000h; nPriority
0x1800390d2  mov     Parameter, rax; hThread
0x1800390d5  call    cs:__imp_SetThreadPriority
0x1800390db  test    eax, eax
0x1800390dd  jz      short loc_1800390E4
0x1800390df  mov     dil, 1
0x1800390e2  jmp     short loc_18003911A
0x1800390e4  xor     dil, dil
0x1800390e7  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800390ee  cmp     Parameter, rbp
0x1800390f1  jz      short loc_18003913D
0x1800390f3  test    byte ptr [Parameter+1Ch], 4
0x1800390f7  jz      short loc_180039121
0x1800390f9  call    cs:__imp_GetLastError
0x1800390ff  mov     edx, 26h ; '&'; id
0x180039104  mov     r9d, eax; _a1
0x180039107  mov     r8, r15; TraceGuid
0x18003910a  mov     Parameter, cs:WPP_GLOBAL_Control
0x180039111  mov     Parameter, [Parameter+10h]; Logger
0x180039115  call    WPP_SF_d
0x18003911a  mov     Parameter, cs:WPP_GLOBAL_Control
0x180039121  cmp     Parameter, rbp; __annotation("TMF:",
0x180039124  jz      short loc_18003913D
0x180039126  test    byte ptr [Parameter+1Ch], 10h
0x18003912a  jz      short loc_18003913D
0x18003912c  mov     edx, 27h ; '''; id
0x180039131  mov     r8, r15; TraceGuid
0x180039134  mov     Parameter, [Parameter+10h]; Logger
0x180039138  call    WPP_SF_
0x18003913d  xor     edx, edx; dwCoInit
0x18003913f  xor     ecx, ecx; pvReserved
0x180039141  call    cs:__imp_CoInitializeEx
0x180039147  mov     ebx, eax
0x180039149  test    eax, eax
0x18003914b  js      short loc_180039179
0x18003914d  mov     [rsp+48h+coUninit.m_call], 1
0x180039152  mov     [rsp+48h+f.pStream], r14
0x180039157  lea     Parameter, [rsp+48h+f]; f
0x18003915c  call    ExecuteAndConvertAnyException__PurgeTaskThreadThunk____8____lambda_1___
0x180039161  mov     ebx, eax
0x180039163  mov     rax, [r14]
0x180039166  mov     Parameter, r14
0x180039169  mov     rax, [rax+10h]
0x18003916d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039172  nop
0x180039173  call    cs:__imp_CoUninitialize
0x180039179  test    dil, dil
0x18003917c  jz      short loc_1800391C3
0x18003917e  mov     edx, 20000h; nPriority
0x180039183  mov     Parameter, rsi; hThread
0x180039186  call    cs:__imp_SetThreadPriority
0x18003918c  test    eax, eax
0x18003918e  jnz     short loc_1800391C3
0x180039190  mov     Parameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180039197  cmp     Parameter, rbp
0x18003919a  jz      short loc_1800391E9
0x18003919c  test    byte ptr [Parameter+1Ch], 4
0x1800391a0  jz      short loc_1800391CA
0x1800391a2  call    cs:__imp_GetLastError
0x1800391a8  mov     edx, 28h ; '('; id
0x1800391ad  mov     r9d, eax; _a1
0x1800391b0  mov     r8, r15; TraceGuid
0x1800391b3  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800391ba  mov     Parameter, [Parameter+10h]; Logger
0x1800391be  call    WPP_SF_d
0x1800391c3  mov     Parameter, cs:WPP_GLOBAL_Control
0x1800391ca  cmp     Parameter, rbp; __annotation("TMF:",
0x1800391cd  jz      short loc_1800391E9
0x1800391cf  test    byte ptr [Parameter+1Ch], 10h
0x1800391d3  jz      short loc_1800391E9
0x1800391d5  mov     edx, 29h ; ')'; id
0x1800391da  mov     r9d, ebx; _a1
0x1800391dd  mov     r8, r15; TraceGuid
0x1800391e0  mov     Parameter, [Parameter+10h]; Logger
0x1800391e4  call    WPP_SF_d
0x1800391e9  mov     eax, ebx
0x1800391eb  mov     rbx, [rsp+48h+arg_0]
0x1800391f0  add     rsp, 20h
0x1800391f4  pop     r15
0x1800391f6  pop     r14
0x1800391f8  pop     rdi
0x1800391f9  pop     rsi
0x1800391fa  pop     rbp
0x1800391fb  retn
```
