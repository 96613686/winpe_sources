# RegistryKeyWatcher::ResetNotify(void)

- ea: `0x180037b64`
- end: `0x180037d78`
- name: `?ResetNotify@RegistryKeyWatcher@@AEAAJXZ`
- size: `532`
- prototype: `__int64 __fastcall(RegistryKeyWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f36c`
- `0x18007549c`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000ec20`
- `0x180037b64`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d53`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180037b9f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180037b9f`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x180037cc7`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x180037cc7`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x180037c39`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x180037c39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037bba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037bba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ce3`

## string_xrefs

- `0x180037d40`: `RegistryKeyWatcher::ResetNotify`

## pseudocode

```c
__int64 __fastcall RegistryKeyWatcher::ResetNotify(RegistryKeyWatcher *this)
{
  HKEY v2; // rcx
  HRESULT v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // r8d
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  IRtwqAsyncResult *asyncResult; // [rsp+40h] [rbp+8h] BYREF

  asyncResult = 0;
  v2 = (HKEY)*((_QWORD *)this + 8);
  if ( v2 )
  {
    if ( RegNotifyChangeKeyValue(v2, 0, 0x10000004u, *((HANDLE *)this + 10), 1) )
    {
      v4 = (__int64 *)CallStackTracing::s_wpInstance;
      v3 = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v5;
        if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
        {
          v4 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( !*((_BYTE *)v4 + 8) )
        goto LABEL_31;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147467259 )
        goto LABEL_31;
      v7 = 262;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
      v3 = RtwqCreateAsyncResult(0, (IRtwqAsyncCallback *)((char *)this + 40), 0, &asyncResult);
      if ( v3 >= 0 )
      {
        v3 = RtwqPutWaitingWorkItem(*((HANDLE *)this + 10), 0, asyncResult, (RTWQWORKITEM_KEY *)this + 7);
        if ( v3 >= 0 )
          goto LABEL_32;
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v11;
          if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
          {
            v10 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( !*((_BYTE *)v10 + 8)
          || (ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10),
              *((_DWORD *)ThreadRelativeContext + 499) == v3) )
        {
LABEL_31:
          RegCloseKey(*((HKEY *)this + 8));
          *((_QWORD *)this + 8) = 0;
          goto LABEL_32;
        }
        v7 = 269;
      }
      else
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v9;
          if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
          {
            v8 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v8 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( !*((_BYTE *)v8 + 8) )
          goto LABEL_31;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == v3 )
          goto LABEL_31;
        v7 = 266;
      }
    }
    CallStackContext::TraceFailure(ThreadRelativeContext, "RegistryKeyWatcher::ResetNotify", v7, v3);
    goto LABEL_31;
  }
  v3 = 1;
LABEL_32:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&asyncResult);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180037b64  mov     [rsp+arg_8], rbx
0x180037b69  push    rdi
0x180037b6a  sub     rsp, 30h
0x180037b6e  mov     rdi, rcx
0x180037b71  mov     [rsp+38h+asyncResult], 0
0x180037b7a  mov     rcx, [rcx+40h]; hKey
0x180037b7e  test    rcx, rcx
0x180037b81  jnz     short loc_180037B8B
0x180037b83  lea     ebx, [rcx+1]
0x180037b86  jmp     loc_180037D61
0x180037b8b  mov     r9, [rdi+50h]; hEvent
0x180037b8f  xor     edx, edx; bWatchSubtree
0x180037b91  mov     r8d, 10000004h; dwNotifyFilter
0x180037b97  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180037b9f  call    cs:__imp_RegNotifyChangeKeyValue
0x180037ba5  test    eax, eax
0x180037ba7  jz      short loc_180037C21
0x180037ba9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037bb0  mov     ebx, 80004005h
0x180037bb5  test    rcx, rcx
0x180037bb8  jnz     short loc_180037BFB
0x180037bba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037bc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037bc7  mov     rcx, rax
0x180037bca  test    rax, rax
0x180037bcd  jz      short loc_180037BED
0x180037bcf  mov     rax, [rax]
0x180037bd2  mov     edx, 7F0h
0x180037bd7  mov     rax, [rax+8]
0x180037bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037be0  test    eax, eax
0x180037be2  jz      short loc_180037BED
0x180037be4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037beb  jmp     short loc_180037BFB
0x180037bed  lea     rcx, qword_180153440; this
0x180037bf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037bfb  cmp     byte ptr [rcx+8], 0
0x180037bff  jz      loc_180037D4F
0x180037c05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037c0a  cmp     [rax+7CCh], ebx
0x180037c10  jz      loc_180037D4F
0x180037c16  mov     r8d, 106h
0x180037c1c  jmp     loc_180037D3D
0x180037c21  lea     rcx, [rsp+38h+asyncResult]
0x180037c26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037c2b  lea     rdx, [rdi+28h]; callback
0x180037c2f  xor     r8d, r8d; appState
0x180037c32  lea     r9, [rsp+38h+asyncResult]; asyncResult
0x180037c37  xor     ecx, ecx; appObject
0x180037c39  call    cs:__imp_RtwqCreateAsyncResult
0x180037c3f  mov     ebx, eax
0x180037c41  test    eax, eax
0x180037c43  jns     short loc_180037CB8
0x180037c45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c4c  test    rcx, rcx
0x180037c4f  jnz     short loc_180037C92
0x180037c51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037c57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c5e  mov     rcx, rax
0x180037c61  test    rax, rax
0x180037c64  jz      short loc_180037C84
0x180037c66  mov     rax, [rax]
0x180037c69  mov     edx, 7F0h
0x180037c6e  mov     rax, [rax+8]
0x180037c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c77  test    eax, eax
0x180037c79  jz      short loc_180037C84
0x180037c7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c82  jmp     short loc_180037C92
0x180037c84  lea     rcx, qword_180153440; this
0x180037c8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c92  cmp     byte ptr [rcx+8], 0
0x180037c96  jz      loc_180037D4F
0x180037c9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037ca1  cmp     [rax+7CCh], ebx
0x180037ca7  jz      loc_180037D4F
0x180037cad  mov     r8d, 10Ah
0x180037cb3  jmp     loc_180037D3D
0x180037cb8  mov     r8, [rsp+38h+asyncResult]; result
0x180037cbd  lea     r9, [rdi+38h]; key
0x180037cc1  mov     rcx, [rdi+50h]; hEvent
0x180037cc5  xor     edx, edx; lPriority
0x180037cc7  call    cs:__imp_RtwqPutWaitingWorkItem
0x180037ccd  mov     ebx, eax
0x180037ccf  test    eax, eax
0x180037cd1  jns     loc_180037D61
0x180037cd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037cde  test    rcx, rcx
0x180037ce1  jnz     short loc_180037D24
0x180037ce3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037ce9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037cf0  mov     rcx, rax
0x180037cf3  test    rax, rax
0x180037cf6  jz      short loc_180037D16
0x180037cf8  mov     rax, [rax]
0x180037cfb  mov     edx, 7F0h
0x180037d00  mov     rax, [rax+8]
0x180037d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d09  test    eax, eax
0x180037d0b  jz      short loc_180037D16
0x180037d0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037d14  jmp     short loc_180037D24
0x180037d16  lea     rcx, qword_180153440; this
0x180037d1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037d24  cmp     byte ptr [rcx+8], 0
0x180037d28  jz      short loc_180037D4F
0x180037d2a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037d2f  cmp     [rax+7CCh], ebx
0x180037d35  jz      short loc_180037D4F
0x180037d37  mov     r8d, 10Dh; int
0x180037d3d  mov     r9d, ebx; int
0x180037d40  lea     rdx, aRegistrykeywat; "RegistryKeyWatcher::ResetNotify"
0x180037d47  mov     rcx, rax; this
0x180037d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037d4f  mov     rcx, [rdi+40h]; hKey
0x180037d53  call    cs:__imp_RegCloseKey
0x180037d59  mov     qword ptr [rdi+40h], 0
0x180037d61  lea     rcx, [rsp+38h+asyncResult]
0x180037d66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037d6b  mov     eax, ebx
0x180037d6d  mov     rbx, [rsp+38h+arg_8]
0x180037d72  add     rsp, 30h
0x180037d76  pop     rdi
0x180037d77  retn
```
