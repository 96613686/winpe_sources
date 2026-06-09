# CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)

- ea: `0x18003b91c`
- end: `0x18003bbdb`
- name: `?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z`
- size: `703`
- prototype: `__int64 __fastcall(CSourcePluginBufferReader *__hidden this, unsigned int *)`
- caller_count: `9`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180039644`
- `0x18003a2ec`
- `0x18006b720`
- `0x1800a7d2c`
- `0x1800c0568`
- `0x1800c2d10`
- `0x1800d8870`
- `0x180135ae8`
- `0x18015669c`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18003b91c`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b972`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ba0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b972`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ba0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ba5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ba5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003b95e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003b9f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003b95e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003b9f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba87`

## string_xrefs

- `0x18003b943`: `CSourcePluginBufferReader::GetAvailableBufferSize`

## pseudocode

```c
__int64 __fastcall CSourcePluginBufferReader::GetAvailableBufferSize(CSourcePluginBufferReader *this, unsigned int *a2)
{
  wchar_t *v2; // rbx
  wchar_t *v5; // rdi
  DWORD LastError; // esi
  wchar_t *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned int v13; // esi
  wchar_t *v14; // rdi
  DWORD v15; // ebp
  wchar_t *v16; // rax
  int v17; // eax
  int v18; // eax
  CallStackTracing *v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = v2 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v21 = CallStackTracing::s_wpInstance;
      }
      v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v22 )
        v5 = (wchar_t *)v22;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[4 * v9] = "CSourcePluginBufferReader::GetAvailableBufferSize";
      *(_DWORD *)&v5[4 * v9 + 4] = 58;
    }
    ++*((_DWORD *)v5 + 497);
  }
  v10 = *((_QWORD *)this + 57);
  v11 = v10 + *((unsigned int *)this + 116);
  if ( v11 < v10 )
  {
    v13 = -2147024362;
    if ( !v2 )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v2 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v2 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v2);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSourcePluginBufferReader::GetAvailableBufferSize",
          58,
          -2147024362);
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    if ( g_wppLevels )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
        this,
        -2147024362);
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
  }
  else
  {
    v12 = *((_QWORD *)this + 59);
    if ( v12 < v10 || v12 >= v11 )
    {
      v13 = 0;
      *a2 = 0;
    }
    else
    {
      v13 = 0;
      *a2 = v11 - v12;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v14 = v2 + 104;
    v15 = GetLastError();
    v16 = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v16 )
    {
      v14 = v16;
    }
    else if ( !GetLastError() )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
      if ( v24 )
        v14 = (wchar_t *)v24;
    }
    SetLastError(v15);
    v17 = *((_DWORD *)v14 + 497);
    if ( v17 )
    {
      v18 = v17 - 1;
      *((_DWORD *)v14 + 497) = v18;
      if ( !v18 )
      {
        *((_DWORD *)v14 + 497) = 0;
        *((_QWORD *)v14 + 252) = 0;
        *((_DWORD *)v14 + 499) = 0;
        *((GUID *)v14 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v14 + 506) = 0;
        *((_DWORD *)v14 + 496) = GetCurrentThreadId();
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18003b91c  push    rbx
0x18003b91e  push    rbp
0x18003b91f  push    rsi
0x18003b920  push    rdi
0x18003b921  push    r13
0x18003b923  push    r14
0x18003b925  sub     rsp, 38h
0x18003b929  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b930  mov     r14, rdx
0x18003b933  mov     rbp, rcx
0x18003b936  test    rbx, rbx
0x18003b939  jz      loc_18003BAB3
0x18003b93f  cmp     byte ptr [rbx+8], 0
0x18003b943  lea     r13, aCsourcepluginb_5; "CSourcePluginBufferReader::GetAvailable"...
0x18003b94a  jz      short loc_18003B9A2
0x18003b94c  lea     rdi, [rbx+0D0h]
0x18003b953  call    cs:__imp_GetLastError
0x18003b959  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003b95c  mov     esi, eax
0x18003b95e  call    cs:__imp_TlsGetValue
0x18003b964  test    rax, rax
0x18003b967  jz      loc_18003BACE
0x18003b96d  mov     rdi, rax
0x18003b970  mov     ecx, esi; dwErrCode
0x18003b972  call    cs:__imp_SetLastError
0x18003b978  mov     eax, [rdi+7C4h]
0x18003b97e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b985  cmp     eax, [rdi+7C8h]
0x18003b98b  jnb     short loc_18003B99C
0x18003b98d  add     rax, rax
0x18003b990  mov     [rdi+rax*8], r13
0x18003b994  mov     dword ptr [rdi+rax*8+8], 3Ah ; ':'
0x18003b99c  inc     dword ptr [rdi+7C4h]
0x18003b9a2  mov     rdx, [rbp+1C8h]
0x18003b9a9  mov     ecx, [rbp+1D0h]
0x18003b9af  add     rcx, rdx
0x18003b9b2  cmp     rcx, rdx
0x18003b9b5  jb      loc_18003BA79
0x18003b9bb  mov     rax, [rbp+1D8h]
0x18003b9c2  cmp     rax, rdx
0x18003b9c5  jb      loc_18003BAC4
0x18003b9cb  cmp     rax, rcx
0x18003b9ce  jnb     loc_18003BAC4
0x18003b9d4  xor     esi, esi
0x18003b9d6  sub     ecx, eax
0x18003b9d8  mov     [r14], ecx
0x18003b9db  cmp     byte ptr [rbx+8], 0
0x18003b9df  jz      loc_18003BA6A
0x18003b9e5  lea     rdi, [rbx+0D0h]
0x18003b9ec  call    cs:__imp_GetLastError
0x18003b9f2  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003b9f5  mov     ebp, eax
0x18003b9f7  call    cs:__imp_TlsGetValue
0x18003b9fd  test    rax, rax
0x18003ba00  jz      loc_18003BAFF
0x18003ba06  mov     rdi, rax
0x18003ba09  mov     ecx, ebp; dwErrCode
0x18003ba0b  call    cs:__imp_SetLastError
0x18003ba11  mov     eax, [rdi+7C4h]
0x18003ba17  test    eax, eax
0x18003ba19  jz      short loc_18003BA6A
0x18003ba1b  sub     eax, 1
0x18003ba1e  mov     [rdi+7C4h], eax
0x18003ba24  jnz     short loc_18003BA6A
0x18003ba26  mov     dword ptr [rdi+7C4h], 0
0x18003ba30  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003ba37  mov     qword ptr [rdi+7E0h], 0
0x18003ba42  mov     dword ptr [rdi+7CCh], 0
0x18003ba4c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18003ba54  mov     dword ptr [rdi+7E8h], 0
0x18003ba5e  call    cs:__imp_GetCurrentThreadId
0x18003ba64  mov     [rdi+7C0h], eax
0x18003ba6a  mov     eax, esi
0x18003ba6c  add     rsp, 38h
0x18003ba70  pop     r14
0x18003ba72  pop     r13
0x18003ba74  pop     rdi
0x18003ba75  pop     rsi
0x18003ba76  pop     rbp
0x18003ba77  pop     rbx
0x18003ba78  retn
0x18003ba79  mov     esi, 80070216h
0x18003ba7e  test    rbx, rbx
0x18003ba81  jnz     loc_18003BB99
0x18003ba87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ba8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ba94  mov     rcx, rax
0x18003ba97  test    rax, rax
0x18003ba9a  jnz     loc_18003BB79
0x18003baa0  lea     rbx, qword_1801B07E0
0x18003baa7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003baae  jmp     loc_18003BB99
0x18003bab3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003bab8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003babf  jmp     loc_18003B93F
0x18003bac4  xor     esi, esi
0x18003bac6  mov     [r14], esi
0x18003bac9  jmp     loc_18003B9DB
0x18003bace  call    cs:__imp_GetLastError
0x18003bad4  test    eax, eax
0x18003bad6  jnz     loc_18003B970
0x18003badc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bae3  test    rcx, rcx
0x18003bae6  jz      short loc_18003BB30
0x18003bae8  mov     rax, [rcx]
0x18003baeb  mov     rax, [rax]
0x18003baee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baf3  test    rax, rax
0x18003baf6  cmovnz  rdi, rax
0x18003bafa  jmp     loc_18003B970
0x18003baff  call    cs:__imp_GetLastError
0x18003bb05  test    eax, eax
0x18003bb07  jnz     loc_18003BA09
0x18003bb0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb14  test    rcx, rcx
0x18003bb17  jz      short loc_18003BB3E
0x18003bb19  mov     rax, [rcx]
0x18003bb1c  mov     rax, [rax]
0x18003bb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb24  test    rax, rax
0x18003bb27  cmovnz  rdi, rax
0x18003bb2b  jmp     loc_18003BA09
0x18003bb30  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003bb35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb3c  jmp     short loc_18003BAE8
0x18003bb3e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003bb43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb4a  jmp     short loc_18003BB19
0x18003bb4c  mov     rcx, rbx; this
0x18003bb4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bb54  cmp     [rax+7CCh], esi
0x18003bb5a  jz      short loc_18003BB70
0x18003bb5c  mov     r9d, esi; int
0x18003bb5f  mov     r8d, 3Ah ; ':'; int
0x18003bb65  mov     rdx, r13; char *
0x18003bb68  mov     rcx, rax; this
0x18003bb6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bb70  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb77  jmp     short loc_18003BB9F
0x18003bb79  mov     rax, [rax]
0x18003bb7c  mov     edx, 7F0h
0x18003bb81  mov     rax, [rax+8]
0x18003bb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb8a  test    eax, eax
0x18003bb8c  jz      loc_18003BAA0
0x18003bb92  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb99  cmp     byte ptr [rbx+8], 0
0x18003bb9d  jnz     short loc_18003BB4C
0x18003bb9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bba6  jb      loc_18003B9DB
0x18003bbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bbb3  lea     r8, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x18003bbba  mov     edx, 0Ah
0x18003bbbf  mov     [rsp+68h+var_48], esi
0x18003bbc3  mov     r9, rbp
0x18003bbc6  mov     rcx, [rcx+10h]
0x18003bbca  call    WPP_SF_qD
0x18003bbcf  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bbd6  jmp     loc_18003B9DB
```
