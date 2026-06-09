# CCacheReaderBufferList::GetLockedBufferPointer(ulong,MFBUFFER::CBuffer &)

- ea: `0x18003fbd0`
- end: `0x18003ffd4`
- name: `?GetLockedBufferPointer@CCacheReaderBufferList@@QEAAJKAEAVCBuffer@MFBUFFER@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(CCacheReaderBufferList *__hidden this, unsigned int, struct MFBUFFER::CBuffer *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180021fb0`
- `0x180040700`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18003fbd0`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fda9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fda9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fdf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fdf4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc42`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd8f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fc42`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fd8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fe1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fedc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fe1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003fedc`

## string_xrefs

- `0x18003fc10`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18003fc6e`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18003ff26`: `CCacheReaderBufferList::GetLockedBufferPointer`

## pseudocode

```c
__int64 __fastcall CCacheReaderBufferList::GetLockedBufferPointer(
        __int64 **this,
        __int64 a2,
        struct MFBUFFER::CBuffer *a3)
{
  unsigned int v5; // r14d
  int v6; // r15d
  CallStackTracing *v7; // rbx
  char *v8; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 *v14; // rcx
  unsigned int v15; // ebp
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r10
  unsigned __int64 v24; // rax
  unsigned int v25; // r9d
  unsigned __int64 v26; // r10
  unsigned __int64 v27; // rax
  CallStackTracing *v28; // rbx
  GUID *v29; // rdi
  DWORD v30; // esi
  GUID *v31; // rax
  int v32; // eax
  int v33; // eax
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v42; // rdx
  __int64 v43; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v44; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v6 = -1072875829;
  if ( !CallStackTracing::s_wpInstance )
  {
    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v35;
    if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
  v7 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v8 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
    if ( Value )
    {
      v8 = Value;
    }
    else if ( !GetLastError() )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      v37 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
      if ( v37 )
        v8 = (char *)v37;
    }
    SetLastError(LastError);
    v11 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v11 < *((_DWORD *)v8 + 498) )
    {
      v12 = 2 * v11;
      *(_QWORD *)&v8[8 * v12] = "CCacheReaderBufferList::GetLockedBufferPointer";
      *(_DWORD *)&v8[8 * v12 + 8] = 814;
    }
    ++*((_DWORD *)v8 + 497);
  }
  if ( v5 >= *((_DWORD *)this + 116) )
  {
    if ( g_wppLevels )
    {
      v42 = 53;
LABEL_50:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v6);
    }
  }
  else
  {
    v13 = 0;
    v14 = this[54];
    v15 = v5 + *((_DWORD *)this + 114);
    while ( v14 )
    {
      v16 = *v14;
      v14 = (__int64 *)v14[1];
      v13 += *(_DWORD *)(v16 + 32);
      if ( v15 < v13 )
      {
        v17 = *(_QWORD *)(v16 + 16);
        v44 = 0;
        v43 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v17 + 24LL))(
               v17,
               &v43,
               0,
               &v44);
        if ( v6 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
            CallStackTracing::s_wpInstance = v40;
            if ( !v40
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CCacheReaderBufferList::GetLockedBufferPointer",
                843,
                v6);
          }
          if ( g_wppLevels )
          {
            v42 = 54;
            goto LABEL_50;
          }
        }
        else
        {
          v20 = v44;
          v21 = v43;
          v22 = v44;
          *(_QWORD *)a3 = v44;
          v23 = (unsigned int)v20;
          *((_QWORD *)a3 + 1) = v21;
          v24 = v15 - v13 + *(_DWORD *)(v16 + 32);
          if ( v24 <= v20 )
            v22 = (unsigned int)v24;
          v25 = v20 - (v15 - v13 + *(_DWORD *)(v16 + 32));
          v26 = v23 - v22;
          *(_QWORD *)a3 = v26;
          *((_QWORD *)a3 + 1) = v22 + v21;
          v27 = *((_DWORD *)this + 116) - v5;
          if ( (unsigned int)v27 >= v25 )
            v27 = v25;
          if ( v27 <= v26 )
            v26 = v27;
          *(_QWORD *)a3 = v26;
        }
        break;
      }
    }
  }
  v28 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v29 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v30 = GetLastError();
    v31 = (GUID *)TlsGetValue(*((_DWORD *)v28 + 3));
    if ( v31 )
    {
      v29 = v31;
    }
    else if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v29 = (GUID *)v39;
    }
    SetLastError(v30);
    v32 = *(_DWORD *)&v29[124].Data2;
    if ( v32 )
    {
      v33 = v32 - 1;
      *(_DWORD *)&v29[124].Data2 = v33;
      if ( !v33 )
      {
        *(_DWORD *)&v29[124].Data2 = 0;
        *(_QWORD *)&v29[126].Data1 = 0;
        *(_DWORD *)&v29[124].Data4[4] = 0;
        v29[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v29[126].Data4 = 0;
        v29[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003fbd0  push    rbx
0x18003fbd2  push    rsi
0x18003fbd3  push    r13
0x18003fbd5  push    r15
0x18003fbd7  sub     rsp, 48h
0x18003fbdb  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fbe3  lea     rbx, qword_1801B97E0
0x18003fbea  mov     [rsp+68h+var_30], r12
0x18003fbef  mov     rsi, rcx
0x18003fbf2  mov     [rsp+68h+var_38], r14
0x18003fbf7  mov     r12, r8
0x18003fbfa  mov     r14d, edx
0x18003fbfd  mov     r15d, 0C00D36CBh
0x18003fc03  jz      loc_18003FE1A
0x18003fc09  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fc10  lea     rcx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003fc17  mov     [rsp+68h+arg_10], rbp
0x18003fc1f  mov     [rsp+68h+var_28], rdi
0x18003fc24  cmp     byte ptr [rbx+8], 0
0x18003fc28  jz      short loc_18003FC92
0x18003fc2a  lea     rdi, [rbx+0D0h]
0x18003fc31  call    cs:__imp_GetLastError
0x18003fc38  nop     dword ptr [rax+rax+00h]
0x18003fc3d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003fc40  mov     ebp, eax
0x18003fc42  call    cs:__imp_TlsGetValue
0x18003fc49  nop     dword ptr [rax+rax+00h]
0x18003fc4e  test    rax, rax
0x18003fc51  jz      loc_18003FE45
0x18003fc57  mov     rdi, rax
0x18003fc5a  mov     ecx, ebp; dwErrCode
0x18003fc5c  call    cs:__imp_SetLastError
0x18003fc63  nop     dword ptr [rax+rax+00h]
0x18003fc68  mov     eax, [rdi+7C4h]
0x18003fc6e  lea     rcx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003fc75  cmp     eax, [rdi+7C8h]
0x18003fc7b  jnb     short loc_18003FC8C
0x18003fc7d  add     rax, rax
0x18003fc80  mov     [rdi+rax*8], rcx
0x18003fc84  mov     dword ptr [rdi+rax*8+8], 32Eh
0x18003fc8c  inc     dword ptr [rdi+7C4h]
0x18003fc92  xor     r13d, r13d
0x18003fc95  cmp     r14d, [rsi+1D0h]
0x18003fc9c  jnb     loc_18003FF5E
0x18003fca2  mov     ebp, [rsi+1C8h]
0x18003fca8  mov     ebx, r13d
0x18003fcab  mov     rcx, [rsi+1B0h]
0x18003fcb2  add     ebp, r14d
0x18003fcb5  test    rcx, rcx
0x18003fcb8  jz      loc_18003FD54
0x18003fcbe  mov     rdi, [rcx]
0x18003fcc1  mov     rcx, [rcx+8]
0x18003fcc5  add     ebx, [rdi+20h]
0x18003fcc8  cmp     ebp, ebx
0x18003fcca  jnb     short loc_18003FCB5
0x18003fccc  mov     rcx, [rdi+10h]
0x18003fcd0  lea     r9, [rsp+68h+arg_8]
0x18003fcd5  mov     [rsp+68h+arg_8], r13d
0x18003fcda  lea     rdx, [rsp+68h+arg_0]
0x18003fcdf  mov     [rsp+68h+arg_0], r13
0x18003fce4  xor     r8d, r8d
0x18003fce7  mov     rax, [rcx]
0x18003fcea  mov     rax, [rax+18h]
0x18003fcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcf3  mov     r15d, eax
0x18003fcf6  test    eax, eax
0x18003fcf8  js      loc_18003FECF
0x18003fcfe  mov     r9d, [rsp+68h+arg_8]
0x18003fd03  sub     ebp, ebx
0x18003fd05  mov     r8, [rsp+68h+arg_0]
0x18003fd0a  mov     ecx, r9d
0x18003fd0d  mov     [r12], r9
0x18003fd11  mov     r10d, r9d
0x18003fd14  mov     [r12+8], r8
0x18003fd19  mov     edx, [rdi+20h]
0x18003fd1c  add     edx, ebp
0x18003fd1e  mov     eax, edx
0x18003fd20  cmp     rax, r9
0x18003fd23  cmovbe  ecx, eax
0x18003fd26  sub     r9d, edx
0x18003fd29  sub     r10, rcx
0x18003fd2c  mov     [r12], r10
0x18003fd30  lea     rax, [rcx+r8]
0x18003fd34  mov     [r12+8], rax
0x18003fd39  mov     eax, [rsi+1D0h]
0x18003fd3f  sub     eax, r14d
0x18003fd42  cmp     eax, r9d
0x18003fd45  cmovnb  eax, r9d
0x18003fd49  cmp     rax, r10
0x18003fd4c  cmovbe  r10, rax
0x18003fd50  mov     [r12], r10
0x18003fd54  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fd5b  mov     r14, [rsp+68h+var_38]
0x18003fd60  mov     r12, [rsp+68h+var_30]
0x18003fd65  mov     rbp, [rsp+68h+arg_10]
0x18003fd6d  cmp     [rbx+8], r13b
0x18003fd71  jz      loc_18003FE06
0x18003fd77  lea     rdi, [rbx+0D0h]
0x18003fd7e  call    cs:__imp_GetLastError
0x18003fd85  nop     dword ptr [rax+rax+00h]
0x18003fd8a  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003fd8d  mov     esi, eax
0x18003fd8f  call    cs:__imp_TlsGetValue
0x18003fd96  nop     dword ptr [rax+rax+00h]
0x18003fd9b  test    rax, rax
0x18003fd9e  jz      loc_18003FE7C
0x18003fda4  mov     rdi, rax
0x18003fda7  mov     ecx, esi; dwErrCode
0x18003fda9  call    cs:__imp_SetLastError
0x18003fdb0  nop     dword ptr [rax+rax+00h]
0x18003fdb5  mov     eax, [rdi+7C4h]
0x18003fdbb  test    eax, eax
0x18003fdbd  jz      short loc_18003FE06
0x18003fdbf  sub     eax, 1
0x18003fdc2  mov     [rdi+7C4h], eax
0x18003fdc8  jnz     short loc_18003FE06
0x18003fdca  mov     [rdi+7C4h], r13d
0x18003fdd1  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003fdd8  mov     [rdi+7E0h], r13
0x18003fddf  mov     [rdi+7CCh], r13d
0x18003fde6  movups  xmmword ptr [rdi+7D0h], xmm0
0x18003fded  mov     [rdi+7E8h], r13d
0x18003fdf4  call    cs:__imp_GetCurrentThreadId
0x18003fdfb  nop     dword ptr [rax+rax+00h]
0x18003fe00  mov     [rdi+7C0h], eax
0x18003fe06  mov     rdi, [rsp+68h+var_28]
0x18003fe0b  mov     eax, r15d
0x18003fe0e  add     rsp, 48h
0x18003fe12  pop     r15
0x18003fe14  pop     r13
0x18003fe16  pop     rsi
0x18003fe17  pop     rbx
0x18003fe18  retn
0x18003fe1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fe21  nop     dword ptr [rax+rax+00h]
0x18003fe26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe2d  mov     rcx, rax
0x18003fe30  test    rax, rax
0x18003fe33  jnz     loc_18003FF40
0x18003fe39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe40  jmp     loc_18003FC09
0x18003fe45  call    cs:__imp_GetLastError
0x18003fe4c  nop     dword ptr [rax+rax+00h]
0x18003fe51  test    eax, eax
0x18003fe53  jnz     loc_18003FC5A
0x18003fe59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe60  test    rcx, rcx
0x18003fe63  jz      short loc_18003FEB3
0x18003fe65  mov     rax, [rcx]
0x18003fe68  mov     rax, [rax]
0x18003fe6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe70  test    rax, rax
0x18003fe73  cmovnz  rdi, rax
0x18003fe77  jmp     loc_18003FC5A
0x18003fe7c  call    cs:__imp_GetLastError
0x18003fe83  nop     dword ptr [rax+rax+00h]
0x18003fe88  test    eax, eax
0x18003fe8a  jnz     loc_18003FDA7
0x18003fe90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fe97  test    rcx, rcx
0x18003fe9a  jz      short loc_18003FEC1
0x18003fe9c  mov     rax, [rcx]
0x18003fe9f  mov     rax, [rax]
0x18003fea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fea7  test    rax, rax
0x18003feaa  cmovnz  rdi, rax
0x18003feae  jmp     loc_18003FDA7
0x18003feb3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003feb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003febf  jmp     short loc_18003FE65
0x18003fec1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003fec6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fecd  jmp     short loc_18003FE9C
0x18003fecf  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18003fed6  jnz     loc_18003FFB4
0x18003fedc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003fee3  nop     dword ptr [rax+rax+00h]
0x18003fee8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003feef  mov     rcx, rax
0x18003fef2  test    rax, rax
0x18003fef5  jnz     loc_18003FF9B
0x18003fefb  lea     rax, qword_1801B97E0
0x18003ff02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ff09  jmp     loc_18003FFB4
0x18003ff0e  mov     rcx, rbx; this
0x18003ff11  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ff16  cmp     [rax+7CCh], r15d
0x18003ff1d  jz      loc_18003FFC5
0x18003ff23  mov     r9d, r15d; int
0x18003ff26  lea     rdx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003ff2d  mov     r8d, 34Bh; int
0x18003ff33  mov     rcx, rax; this
0x18003ff36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ff3b  jmp     loc_18003FFC5
0x18003ff40  mov     rax, [rax]
0x18003ff43  mov     edx, 7F0h
0x18003ff48  mov     rax, [rax+8]
0x18003ff4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff51  test    eax, eax
0x18003ff53  jnz     loc_18003FC09
0x18003ff59  jmp     loc_18003FE39
0x18003ff5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ff65  jb      loc_18003FD54
0x18003ff6b  mov     edx, 35h ; '5'
0x18003ff70  jmp     short loc_18003FF77
0x18003ff72  mov     edx, 36h ; '6'
0x18003ff77  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff7e  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x18003ff85  mov     r9, rsi
0x18003ff88  mov     [rsp+68h+var_48], r15d
0x18003ff8d  mov     rcx, [rcx+10h]
0x18003ff91  call    WPP_SF_qD
0x18003ff96  jmp     loc_18003FD54
0x18003ff9b  mov     rax, [rax]
0x18003ff9e  mov     edx, 7F0h
0x18003ffa3  mov     rax, [rax+8]
0x18003ffa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffac  test    eax, eax
0x18003ffae  jz      loc_18003FEFB
0x18003ffb4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ffbb  cmp     [rbx+8], r13b
0x18003ffbf  jnz     loc_18003FF0E
0x18003ffc5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ffcc  jb      loc_18003FD54
0x18003ffd2  jmp     short loc_18003FF72
```
