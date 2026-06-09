# CMFD3D12Buffer::WaitForFree(void)

- ea: `0x18005fa5c`
- end: `0x18005fc4a`
- name: `?WaitForFree@CMFD3D12Buffer@@IEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(CMFD3D12Buffer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180058fc0`
- `0x18005f340`

## callees

- `0x18005fa5c`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005fa76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005fa76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005fc29`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005fc29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fadb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fbb2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fadb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fbb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fc37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fc37`

## pseudocode

```c
__int64 __fastcall CMFD3D12Buffer::WaitForFree(CMFD3D12Buffer *this)
{
  signed int v2; // ebx
  HANDLE EventW; // rbp
  signed int LastError; // eax
  CallStackTracing *v5; // rdi
  CallStackContext *v6; // rsi
  DWORD v7; // ebp
  CallStackContext *v8; // rax
  CallStackTracing *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  CallStackTracing *v12; // rdi
  CallStackContext *v13; // rsi
  DWORD v14; // r14d
  CallStackContext *Value; // rax
  CallStackTracing *v16; // rcx
  __int64 v17; // rax

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
    goto LABEL_17;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_17:
    v11 = *((_QWORD *)this + 87);
    if ( v11 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v11 + 24LL))(v11, EventW);
      if ( v2 >= 0 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
      }
      else
      {
        v12 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v13 = (CallStackTracing *)((char *)v12 + 208);
          v14 = GetLastError();
          Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v12 + 3));
          if ( Value )
          {
            v13 = Value;
          }
          else if ( !GetLastError() )
          {
            v16 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v16 = (CallStackTracing *)&qword_18009CF60;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
            }
            v17 = (**(__int64 (__fastcall ***)(CallStackTracing *))v16)(v16);
            if ( v17 )
              v13 = (CallStackContext *)v17;
          }
          SetLastError(v14);
          if ( *((_DWORD *)v13 + 499) != v2 )
            CallStackContext::TraceFailure(v13, "CMFD3D12Buffer::WaitForFree", 675, v2);
        }
      }
    }
    if ( EventW )
      CloseHandle(EventW);
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v6 = (CallStackTracing *)((char *)v5 + 208);
      v7 = GetLastError();
      v8 = (CallStackContext *)TlsGetValue(*((_DWORD *)v5 + 3));
      if ( v8 )
      {
        v6 = v8;
      }
      else if ( !GetLastError() )
      {
        v9 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v9 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v10 = (**(__int64 (__fastcall ***)(CallStackTracing *))v9)(v9);
        if ( v10 )
          v6 = (CallStackContext *)v10;
      }
      SetLastError(v7);
      if ( *((_DWORD *)v6 + 499) != v2 )
        CallStackContext::TraceFailure(v6, "CMFD3D12Buffer::WaitForFree", 670, v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005fa5c  push    rbx
0x18005fa5e  push    rbp
0x18005fa5f  push    rsi
0x18005fa60  push    rdi
0x18005fa61  push    r14
0x18005fa63  sub     rsp, 20h
0x18005fa67  mov     rdi, rcx
0x18005fa6a  xor     r9d, r9d; lpName
0x18005fa6d  xor     ecx, ecx; lpEventAttributes
0x18005fa6f  xor     r8d, r8d; bInitialState
0x18005fa72  xor     edx, edx; bManualReset
0x18005fa74  xor     ebx, ebx
0x18005fa76  call    cs:__imp_CreateEventW
0x18005fa7c  mov     rbp, rax
0x18005fa7f  test    rax, rax
0x18005fa82  jnz     loc_18005FB52
0x18005fa88  call    cs:__imp_GetLastError
0x18005fa8e  mov     ebx, eax
0x18005fa90  test    eax, eax
0x18005fa92  jle     short loc_18005FA9D
0x18005fa94  movzx   ebx, ax
0x18005fa97  or      ebx, 80070000h
0x18005fa9d  test    ebx, ebx
0x18005fa9f  jns     loc_18005FB52
0x18005faa5  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005faac  test    rdi, rdi
0x18005faaf  jnz     short loc_18005FABF
0x18005fab1  lea     rdi, qword_18009CF60
0x18005fab8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fabf  cmp     byte ptr [rdi+8], 0
0x18005fac3  jz      loc_18005FC3D
0x18005fac9  lea     rsi, [rdi+0D0h]
0x18005fad0  call    cs:__imp_GetLastError
0x18005fad6  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18005fad9  mov     ebp, eax
0x18005fadb  call    cs:__imp_TlsGetValue
0x18005fae1  test    rax, rax
0x18005fae4  jz      short loc_18005FAEB
0x18005fae6  mov     rsi, rax
0x18005fae9  jmp     short loc_18005FB21
0x18005faeb  call    cs:__imp_GetLastError
0x18005faf1  test    eax, eax
0x18005faf3  jnz     short loc_18005FB21
0x18005faf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fafc  test    rcx, rcx
0x18005faff  jnz     short loc_18005FB0F
0x18005fb01  lea     rcx, qword_18009CF60
0x18005fb08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fb0f  mov     rax, [rcx]
0x18005fb12  mov     rax, [rax]
0x18005fb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb1a  test    rax, rax
0x18005fb1d  cmovnz  rsi, rax
0x18005fb21  mov     ecx, ebp; dwErrCode
0x18005fb23  call    cs:__imp_SetLastError
0x18005fb29  cmp     [rsi+7CCh], ebx
0x18005fb2f  jz      loc_18005FC3D
0x18005fb35  mov     r9d, ebx; int
0x18005fb38  lea     rdx, aCmfd3d12buffer_0; "CMFD3D12Buffer::WaitForFree"
0x18005fb3f  mov     r8d, 29Eh; int
0x18005fb45  mov     rcx, rsi; this
0x18005fb48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005fb4d  jmp     loc_18005FC3D
0x18005fb52  mov     rcx, [rdi+2B8h]
0x18005fb59  test    rcx, rcx
0x18005fb5c  jz      loc_18005FC2F
0x18005fb62  mov     rax, [rcx]
0x18005fb65  mov     rdx, rbp
0x18005fb68  mov     rax, [rax+18h]
0x18005fb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb71  mov     ebx, eax
0x18005fb73  test    eax, eax
0x18005fb75  jns     loc_18005FC23
0x18005fb7b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fb82  test    rdi, rdi
0x18005fb85  jnz     short loc_18005FB95
0x18005fb87  lea     rdi, qword_18009CF60
0x18005fb8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fb95  cmp     byte ptr [rdi+8], 0
0x18005fb99  jz      loc_18005FC2F
0x18005fb9f  lea     rsi, [rdi+0D0h]
0x18005fba6  call    cs:__imp_GetLastError
0x18005fbac  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18005fbaf  mov     r14d, eax
0x18005fbb2  call    cs:__imp_TlsGetValue
0x18005fbb8  test    rax, rax
0x18005fbbb  jz      short loc_18005FBC2
0x18005fbbd  mov     rsi, rax
0x18005fbc0  jmp     short loc_18005FBF8
0x18005fbc2  call    cs:__imp_GetLastError
0x18005fbc8  test    eax, eax
0x18005fbca  jnz     short loc_18005FBF8
0x18005fbcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fbd3  test    rcx, rcx
0x18005fbd6  jnz     short loc_18005FBE6
0x18005fbd8  lea     rcx, qword_18009CF60
0x18005fbdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005fbe6  mov     rax, [rcx]
0x18005fbe9  mov     rax, [rax]
0x18005fbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fbf1  test    rax, rax
0x18005fbf4  cmovnz  rsi, rax
0x18005fbf8  mov     ecx, r14d; dwErrCode
0x18005fbfb  call    cs:__imp_SetLastError
0x18005fc01  cmp     [rsi+7CCh], ebx
0x18005fc07  jz      short loc_18005FC2F
0x18005fc09  mov     r9d, ebx; int
0x18005fc0c  lea     rdx, aCmfd3d12buffer_0; "CMFD3D12Buffer::WaitForFree"
0x18005fc13  mov     r8d, 2A3h; int
0x18005fc19  mov     rcx, rsi; this
0x18005fc1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005fc21  jmp     short loc_18005FC2F
0x18005fc23  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005fc26  mov     rcx, rbp; hHandle
0x18005fc29  call    cs:__imp_WaitForSingleObject
0x18005fc2f  test    rbp, rbp
0x18005fc32  jz      short loc_18005FC3D
0x18005fc34  mov     rcx, rbp; hObject
0x18005fc37  call    cs:__imp_CloseHandle
0x18005fc3d  mov     eax, ebx
0x18005fc3f  add     rsp, 20h
0x18005fc43  pop     r14
0x18005fc45  pop     rdi
0x18005fc46  pop     rsi
0x18005fc47  pop     rbp
0x18005fc48  pop     rbx
0x18005fc49  retn
```
