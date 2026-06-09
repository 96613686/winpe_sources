# CCacheReaderBufferList::UnlockBuffer(ulong)

- ea: `0x18003fb20`
- end: `0x18003fe40`
- name: `?UnlockBuffer@CCacheReaderBufferList@@QEAAJK@Z`
- size: `800`
- prototype: `__int64 __fastcall(CCacheReaderBufferList *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180009ab4`
- `0x18003eb70`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18003fb20`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fb97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fc9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fc9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fb83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc44`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fb83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fcbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fd6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fcbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fd6e`

## string_xrefs

- `0x18003fb5a`: `CCacheReaderBufferList::UnlockBuffer`

## pseudocode

```c
__int64 __fastcall CCacheReaderBufferList::UnlockBuffer(__int64 **this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // r14d
  CallStackTracing *v6; // rbx
  char *v7; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // ebp
  __int64 *v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  CallStackTracing *v20; // rbx
  GUID *v21; // rdi
  DWORD v22; // esi
  GUID *v23; // rax
  int v24; // eax
  int v25; // eax
  CallStackTracing *v27; // rax
  CallStackTracing *v28; // rcx
  __int64 v29; // rax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v34; // rdx

  v5 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2, a3, a4);
    CallStackTracing::s_wpInstance = v27;
    if ( !v27 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  v6 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v7 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v6 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v28 = CallStackTracing::s_wpInstance;
      }
      v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v28)(v28);
      if ( v29 )
        v7 = (char *)v29;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CCacheReaderBufferList::UnlockBuffer";
      *(_DWORD *)&v7[8 * v11 + 8] = 867;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( v5 > *((_DWORD *)this + 116) )
  {
    v12 = -1072875829;
    if ( g_wppLevels )
    {
      v34 = 56;
LABEL_47:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v12);
    }
  }
  else
  {
    v12 = 0;
    v13 = this[54];
    v14 = 0;
    while ( v13 )
    {
      v15 = *v13;
      v13 = (__int64 *)v13[1];
      v14 += *(_DWORD *)(v15 + 32);
      if ( v5 + *((_DWORD *)this + 114) < v14 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 16) + 32LL))(*(_QWORD *)(v15 + 16));
        if ( v12 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v16, v18, v19);
            CallStackTracing::s_wpInstance = v32;
            if ( !v32
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CCacheReaderBufferList::UnlockBuffer", 893, v12);
          }
          if ( g_wppLevels )
          {
            v34 = 57;
            goto LABEL_47;
          }
        }
        break;
      }
    }
  }
  v20 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v21 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v22 = GetLastError();
    v23 = (GUID *)TlsGetValue(*((_DWORD *)v20 + 3));
    if ( v23 )
    {
      v21 = v23;
    }
    else if ( !GetLastError() )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v30 = CallStackTracing::s_wpInstance;
      }
      v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v30)(v30);
      if ( v31 )
        v21 = (GUID *)v31;
    }
    SetLastError(v22);
    v24 = *(_DWORD *)&v21[124].Data2;
    if ( v24 )
    {
      v25 = v24 - 1;
      *(_DWORD *)&v21[124].Data2 = v25;
      if ( !v25 )
      {
        *(_DWORD *)&v21[124].Data2 = 0;
        *(_QWORD *)&v21[126].Data1 = 0;
        *(_DWORD *)&v21[124].Data4[4] = 0;
        v21[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v21[126].Data4 = 0;
        v21[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003fb20  push    rbx
0x18003fb22  push    rsi
0x18003fb23  push    r15
0x18003fb25  sub     rsp, 40h
0x18003fb29  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fb31  mov     rsi, rcx
0x18003fb34  mov     [rsp+58h+arg_10], r12
0x18003fb39  mov     [rsp+58h+var_20], r13
0x18003fb3e  lea     r13, qword_1801B07E0
0x18003fb45  mov     [rsp+58h+var_28], r14
0x18003fb4a  mov     r14d, edx
0x18003fb4d  jz      loc_18003FCBE
0x18003fb53  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fb5a  lea     r12, aCcachereaderbu_0; "CCacheReaderBufferList::UnlockBuffer"
0x18003fb61  mov     [rsp+58h+arg_0], rbp
0x18003fb66  mov     [rsp+58h+arg_8], rdi
0x18003fb6b  cmp     byte ptr [rbx+8], 0
0x18003fb6f  jz      short loc_18003FBC0
0x18003fb71  lea     rdi, [rbx+0D0h]
0x18003fb78  call    cs:__imp_GetLastError
0x18003fb7e  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003fb81  mov     ebp, eax
0x18003fb83  call    cs:__imp_TlsGetValue
0x18003fb89  test    rax, rax
0x18003fb8c  jz      loc_18003FCE3
0x18003fb92  mov     rdi, rax
0x18003fb95  mov     ecx, ebp; dwErrCode
0x18003fb97  call    cs:__imp_SetLastError
0x18003fb9d  mov     eax, [rdi+7C4h]
0x18003fba3  cmp     eax, [rdi+7C8h]
0x18003fba9  jnb     short loc_18003FBBA
0x18003fbab  add     rax, rax
0x18003fbae  mov     [rdi+rax*8], r12
0x18003fbb2  mov     dword ptr [rdi+rax*8+8], 363h
0x18003fbba  inc     dword ptr [rdi+7C4h]
0x18003fbc0  xor     r15d, r15d
0x18003fbc3  cmp     r14d, [rsi+1D0h]
0x18003fbca  ja      loc_18003FDD0
0x18003fbd0  mov     r9d, [rsi+1C8h]
0x18003fbd7  mov     ebp, r15d
0x18003fbda  mov     rcx, [rsi+1B0h]
0x18003fbe1  add     r9d, r14d
0x18003fbe4  mov     edx, r15d
0x18003fbe7  test    rcx, rcx
0x18003fbea  jz      short loc_18003FC16
0x18003fbec  mov     r8, [rcx]
0x18003fbef  mov     rcx, [rcx+8]
0x18003fbf3  add     edx, [r8+20h]
0x18003fbf7  cmp     r9d, edx
0x18003fbfa  jnb     short loc_18003FBE7
0x18003fbfc  mov     rcx, [r8+10h]
0x18003fc00  mov     rax, [rcx]
0x18003fc03  mov     rax, [rax+20h]
0x18003fc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc0c  mov     ebp, eax
0x18003fc0e  test    eax, eax
0x18003fc10  js      loc_18003FD61
0x18003fc16  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc1d  mov     r14, [rsp+58h+var_28]
0x18003fc22  mov     r13, [rsp+58h+var_20]
0x18003fc27  mov     r12, [rsp+58h+arg_10]
0x18003fc2c  cmp     [rbx+8], r15b
0x18003fc30  jz      short loc_18003FCA9
0x18003fc32  lea     rdi, [rbx+0D0h]
0x18003fc39  call    cs:__imp_GetLastError
0x18003fc3f  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003fc42  mov     esi, eax
0x18003fc44  call    cs:__imp_TlsGetValue
0x18003fc4a  test    rax, rax
0x18003fc4d  jz      loc_18003FD14
0x18003fc53  mov     rdi, rax
0x18003fc56  mov     ecx, esi; dwErrCode
0x18003fc58  call    cs:__imp_SetLastError
0x18003fc5e  mov     eax, [rdi+7C4h]
0x18003fc64  test    eax, eax
0x18003fc66  jz      short loc_18003FCA9
0x18003fc68  sub     eax, 1
0x18003fc6b  mov     [rdi+7C4h], eax
0x18003fc71  jnz     short loc_18003FCA9
0x18003fc73  mov     [rdi+7C4h], r15d
0x18003fc7a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003fc81  mov     [rdi+7E0h], r15
0x18003fc88  mov     [rdi+7CCh], r15d
0x18003fc8f  movups  xmmword ptr [rdi+7D0h], xmm0
0x18003fc96  mov     [rdi+7E8h], r15d
0x18003fc9d  call    cs:__imp_GetCurrentThreadId
0x18003fca3  mov     [rdi+7C0h], eax
0x18003fca9  mov     rdi, [rsp+58h+arg_8]
0x18003fcae  mov     eax, ebp
0x18003fcb0  mov     rbp, [rsp+58h+arg_0]
0x18003fcb5  add     rsp, 40h
0x18003fcb9  pop     r15
0x18003fcbb  pop     rsi
0x18003fcbc  pop     rbx
0x18003fcbd  retn
0x18003fcbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fcc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fccb  mov     rcx, rax
0x18003fcce  test    rax, rax
0x18003fcd1  jnz     loc_18003FDB2
0x18003fcd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fcde  jmp     loc_18003FB53
0x18003fce3  call    cs:__imp_GetLastError
0x18003fce9  test    eax, eax
0x18003fceb  jnz     loc_18003FB95
0x18003fcf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fcf8  test    rcx, rcx
0x18003fcfb  jz      short loc_18003FD45
0x18003fcfd  mov     rax, [rcx]
0x18003fd00  mov     rax, [rax]
0x18003fd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd08  test    rax, rax
0x18003fd0b  cmovnz  rdi, rax
0x18003fd0f  jmp     loc_18003FB95
0x18003fd14  call    cs:__imp_GetLastError
0x18003fd1a  test    eax, eax
0x18003fd1c  jnz     loc_18003FC56
0x18003fd22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd29  test    rcx, rcx
0x18003fd2c  jz      short loc_18003FD53
0x18003fd2e  mov     rax, [rcx]
0x18003fd31  mov     rax, [rax]
0x18003fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd39  test    rax, rax
0x18003fd3c  cmovnz  rdi, rax
0x18003fd40  jmp     loc_18003FC56
0x18003fd45  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003fd4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd51  jmp     short loc_18003FCFD
0x18003fd53  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003fd58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd5f  jmp     short loc_18003FD2E
0x18003fd61  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd68  jnz     loc_18003FDFE
0x18003fd6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fd74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd7b  mov     rcx, rax
0x18003fd7e  test    rax, rax
0x18003fd81  jnz     short loc_18003FDE9
0x18003fd83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd8a  jmp     short loc_18003FDFE
0x18003fd8c  mov     rcx, rbx; this
0x18003fd8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003fd94  cmp     [rax+7CCh], ebp
0x18003fd9a  jz      short loc_18003FE0B
0x18003fd9c  mov     r9d, ebp; int
0x18003fd9f  mov     r8d, 37Dh; int
0x18003fda5  mov     rdx, r12; char *
0x18003fda8  mov     rcx, rax; this
0x18003fdab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003fdb0  jmp     short loc_18003FE0B
0x18003fdb2  mov     rax, [rax]
0x18003fdb5  mov     edx, 7F0h
0x18003fdba  mov     rax, [rax+8]
0x18003fdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdc3  test    eax, eax
0x18003fdc5  jnz     loc_18003FB53
0x18003fdcb  jmp     loc_18003FCD7
0x18003fdd0  mov     ebp, 0C00D36CBh
0x18003fdd5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fddc  jb      loc_18003FC16
0x18003fde2  mov     edx, 38h ; '8'
0x18003fde7  jmp     short loc_18003FE1D
0x18003fde9  mov     rax, [rax]
0x18003fdec  mov     edx, 7F0h
0x18003fdf1  mov     rax, [rax+8]
0x18003fdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdfa  test    eax, eax
0x18003fdfc  jz      short loc_18003FD83
0x18003fdfe  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe05  cmp     [rbx+8], r15b
0x18003fe09  jnz     short loc_18003FD8C
0x18003fe0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003fe12  jb      loc_18003FC16
0x18003fe18  mov     edx, 39h ; '9'
0x18003fe1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe24  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x18003fe2b  mov     r9, rsi
0x18003fe2e  mov     [rsp+58h+var_38], ebp
0x18003fe32  mov     rcx, [rcx+10h]
0x18003fe36  call    WPP_SF_qD
0x18003fe3b  jmp     loc_18003FC16
```
