# CAVIidx1Index::FindNextIndexEntry(ulong,ulong,ulong *,int)

- ea: `0x180019d24`
- end: `0x18001a478`
- name: `?FindNextIndexEntry@CAVIidx1Index@@AEBAHKKPEAKH@Z`
- size: `1876`
- prototype: `__int64 __fastcall(CAVIidx1Index *__hidden this, unsigned int, unsigned int, unsigned int *, int)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18004ae78`
- `0x180109ad0`
- `0x18013de3c`
- `0x1801465a4`

## callees

- `0x180005cf4`
- `0x180019d24`
- `0x18001a480`
- `0x18001c6c0`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019dcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019dcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fdc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019db2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019f75`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019db2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019f75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a10c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a188`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a1c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a10c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a188`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a1c9`

## pseudocode

```c
__int64 __fastcall CAVIidx1Index::FindNextIndexEntry(
        CAVIidx1Index *this,
        const char *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5)
{
  CAVIidx1Index *v6; // r13
  int v7; // ebp
  unsigned int v8; // esi
  CallStackTracing *v9; // rbx
  char *v10; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // r14d
  int v19; // eax
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // edi
  int v25; // eax
  int v26; // eax
  CallStackTracing *v27; // rbx
  GUID *v28; // rdi
  DWORD v29; // esi
  GUID *v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 result; // rax
  int v34; // eax
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  CallStackTracing *v37; // rcx
  __int64 v38; // rax
  CallStackTracing *v39; // rax
  CallStackTracing *v40; // rax
  CallStackTracing *v41; // rax
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  int v48; // [rsp+78h] [rbp+10h]

  v48 = (int)a2;
  v6 = this;
  v7 = 0;
  while ( a3 < *((_DWORD *)v6 + 2) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)v6 + 16LL * a3 + 4) & 1) != 0 )
      goto LABEL_49;
    v8 = *(_DWORD *)(*(_QWORD *)v6 + 16LL * a3);
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    v9 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v10 = (char *)CallStackTracing::s_wpInstance + 208;
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v9 + 3));
      if ( Value )
      {
        v10 = Value;
      }
      else if ( !GetLastError() )
      {
        v35 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v35 = CallStackTracing::s_wpInstance;
        }
        v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
        if ( v36 )
          v10 = (char *)v36;
      }
      SetLastError(LastError);
      v13 = *((unsigned int *)v10 + 497);
      v7 = 0;
      if ( (unsigned int)v13 < *((_DWORD *)v10 + 498) )
      {
        v14 = 2 * v13;
        *(_QWORD *)&v10[8 * v14] = "GetStreamNumberFromDataChunkID";
        *(_DWORD *)&v10[8 * v14 + 8] = 43;
      }
      ++*((_DWORD *)v10 + 497);
    }
    v15 = -1;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      this = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v16 = *((unsigned int *)this + 497);
      if ( (unsigned int)v16 < *((_DWORD *)this + 498) )
      {
        v17 = 2 * v16;
        *((_QWORD *)this + v17) = "ConvertASCIIHexDigitToNumber";
        *((_DWORD *)this + 2 * v17 + 2) = 227;
      }
      ++*((_DWORD *)this + 497);
    }
    v18 = 0;
    if ( (unsigned __int8)(v8 - 48) > 9u )
    {
      if ( (unsigned __int8)(v8 - 65) > 0x19u )
      {
        if ( (unsigned __int8)(v8 - 97) > 0x19u )
        {
          v18 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
            CallStackTracing::s_wpInstance = v39;
            this = v39;
            if ( !v39
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "ConvertASCIIHexDigitToNumber", 243, -2147024809);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_ee4aee6488f63d001f8aa593f5c1c919_Traceguids,
              0,
              -2147024809);
        }
        else
        {
          v7 = (unsigned __int8)v8 - 87;
        }
      }
      else
      {
        v7 = (unsigned __int8)v8 - 55;
      }
    }
    else
    {
      v7 = (unsigned __int8)v8 - 48;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      this = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v19 = *((_DWORD *)this + 497);
      if ( v19 )
      {
        v20 = v19 - 1;
        *((_DWORD *)this + 497) = v20;
        if ( !v20 )
          CallStackContext::ClearState(this);
      }
    }
    if ( v18 < 0 )
    {
      v7 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
        CallStackTracing::s_wpInstance = v40;
        this = v40;
        if ( !v40 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v44 + 499) != v18 )
          CallStackContext::TraceFailure(v44, "GetStreamNumberFromDataChunkID", 61, v18);
      }
      if ( g_wppLevels )
      {
        v47 = 11;
LABEL_96:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v47, WPP_ee4aee6488f63d001f8aa593f5c1c919_Traceguids, 0, v18);
      }
    }
    else
    {
      v21 = v8 >> 8;
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        this = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        v22 = *((unsigned int *)this + 497);
        if ( (unsigned int)v22 < *((_DWORD *)this + 498) )
        {
          v23 = 2 * v22;
          a2 = "ConvertASCIIHexDigitToNumber";
          *((_QWORD *)this + v23) = "ConvertASCIIHexDigitToNumber";
          *((_DWORD *)this + 2 * v23 + 2) = 227;
        }
        ++*((_DWORD *)this + 497);
      }
      v18 = 0;
      if ( (unsigned __int8)(v21 - 48) > 9u )
      {
        if ( (unsigned __int8)(v21 - 65) > 0x19u )
        {
          if ( (unsigned __int8)(v21 - 97) > 0x19u )
          {
            v24 = 0;
            v18 = -2147024809;
            if ( !CallStackTracing::s_wpInstance )
            {
              v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
              CallStackTracing::s_wpInstance = v41;
              this = v41;
              if ( !v41
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v45 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v45 + 499) != -2147024809 )
                CallStackContext::TraceFailure(v45, "ConvertASCIIHexDigitToNumber", 243, -2147024809);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                WPP_ee4aee6488f63d001f8aa593f5c1c919_Traceguids,
                0,
                -2147024809);
          }
          else
          {
            v24 = (unsigned __int8)v21 - 87;
          }
        }
        else
        {
          v24 = (unsigned __int8)v21 - 55;
        }
      }
      else
      {
        v24 = (unsigned __int8)v21 - 48;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        this = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        v25 = *((_DWORD *)this + 497);
        if ( v25 )
        {
          v26 = v25 - 1;
          *((_DWORD *)this + 497) = v26;
          if ( !v26 )
            CallStackContext::ClearState(this);
        }
      }
      if ( v18 >= 0 )
      {
        v15 = v24 + 15 * v7;
        v7 = 0;
        goto LABEL_39;
      }
      v7 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
        CallStackTracing::s_wpInstance = v42;
        this = v42;
        if ( !v42 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v46 + 499) != v18 )
          CallStackContext::TraceFailure(v46, "GetStreamNumberFromDataChunkID", 62, v18);
      }
      if ( g_wppLevels )
      {
        v47 = 12;
        goto LABEL_96;
      }
    }
LABEL_39:
    v27 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v28 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
      v29 = GetLastError();
      v30 = (GUID *)TlsGetValue(*((_DWORD *)v27 + 3));
      if ( v30 )
      {
        v28 = v30;
      }
      else if ( !GetLastError() )
      {
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v37 = CallStackTracing::s_wpInstance;
        }
        v38 = (**(__int64 (__fastcall ***)(CallStackTracing *))v37)(v37);
        if ( v38 )
          v28 = (GUID *)v38;
      }
      SetLastError(v29);
      v31 = *(_DWORD *)&v28[124].Data2;
      if ( v31 )
      {
        v32 = v31 - 1;
        *(_DWORD *)&v28[124].Data2 = v32;
        if ( !v32 )
        {
          *(_DWORD *)&v28[124].Data2 = 0;
          *(_QWORD *)&v28[126].Data1 = 0;
          *(_DWORD *)&v28[124].Data4[4] = 0;
          v28[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v28[126].Data4 = 0;
          v28[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    if ( v18 >= 0 && v48 == v15 )
    {
      result = 1;
      *a4 = a3;
      return result;
    }
LABEL_49:
    v34 = a3++ - 1;
    if ( !a5 )
      a3 = v34;
  }
  return 0;
}

```

## disassembly

```asm
0x180019d24  mov     [rsp+arg_0], rbx
0x180019d29  mov     [rsp+arg_18], r9
0x180019d2e  mov     [rsp+arg_8], edx
0x180019d32  push    rbp
0x180019d33  push    rsi
0x180019d34  push    rdi
0x180019d35  push    r12
0x180019d37  push    r13
0x180019d39  push    r14
0x180019d3b  push    r15
0x180019d3d  sub     rsp, 30h
0x180019d41  mov     r15d, r8d
0x180019d44  lea     r12, aGetstreamnumbe; "GetStreamNumberFromDataChunkID"
0x180019d4b  mov     r13, rcx
0x180019d4e  lea     r14, aConvertasciihe; "ConvertASCIIHexDigitToNumber"
0x180019d55  xor     ebp, ebp
0x180019d57  lea     rdi, qword_1801B97E0
0x180019d5e  cmp     r15d, [r13+8]
0x180019d62  jnb     loc_18001A020
0x180019d68  mov     rsi, [r13+0]
0x180019d6c  mov     eax, r15d
0x180019d6f  add     rax, rax
0x180019d72  test    byte ptr [rsi+rax*8+4], 1
0x180019d77  jnz     loc_18001A039
0x180019d7d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d84  mov     esi, [rsi+rax*8]
0x180019d87  jz      loc_18001A050
0x180019d8d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d94  cmp     [rbx+8], bpl
0x180019d98  jz      short loc_180019E04
0x180019d9a  lea     rdi, [rbx+0D0h]
0x180019da1  call    cs:__imp_GetLastError
0x180019da8  nop     dword ptr [rax+rax+00h]
0x180019dad  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180019db0  mov     ebp, eax
0x180019db2  call    cs:__imp_TlsGetValue
0x180019db9  nop     dword ptr [rax+rax+00h]
0x180019dbe  test    rax, rax
0x180019dc1  jz      loc_18001A06E
0x180019dc7  mov     rdi, rax
0x180019dca  mov     ecx, ebp; dwErrCode
0x180019dcc  call    cs:__imp_SetLastError
0x180019dd3  nop     dword ptr [rax+rax+00h]
0x180019dd8  mov     eax, [rdi+7C4h]
0x180019dde  xor     ebp, ebp
0x180019de0  cmp     eax, [rdi+7C8h]
0x180019de6  jnb     short loc_180019DF7
0x180019de8  add     rax, rax
0x180019deb  mov     [rdi+rax*8], r12
0x180019def  mov     dword ptr [rdi+rax*8+8], 2Bh ; '+'
0x180019df7  inc     dword ptr [rdi+7C4h]
0x180019dfd  lea     rdi, qword_1801B97E0
0x180019e04  or      r12d, 0FFFFFFFFh
0x180019e08  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e0f  jz      loc_18001A05A
0x180019e15  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e1c  cmp     [rbx+8], bpl
0x180019e20  jz      short loc_180019E50
0x180019e22  mov     rcx, rbx; this
0x180019e25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019e2a  mov     rcx, rax
0x180019e2d  mov     eax, [rax+7C4h]
0x180019e33  cmp     eax, [rcx+7C8h]
0x180019e39  jnb     short loc_180019E4A
0x180019e3b  add     rax, rax
0x180019e3e  mov     [rcx+rax*8], r14
0x180019e42  mov     dword ptr [rcx+rax*8+8], 0E3h
0x180019e4a  inc     dword ptr [rcx+7C4h]
0x180019e50  lea     eax, [rsi-30h]
0x180019e53  mov     r14d, ebp
0x180019e56  cmp     al, 9
0x180019e58  ja      loc_18001A2C2
0x180019e5e  movzx   ebp, sil
0x180019e62  sub     ebp, 30h ; '0'
0x180019e65  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019e6c  cmp     byte ptr [rbx+8], 0
0x180019e70  jz      short loc_180019E97
0x180019e72  mov     rcx, rbx; this
0x180019e75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019e7a  mov     rcx, rax; this
0x180019e7d  mov     eax, [rax+7C4h]
0x180019e83  test    eax, eax
0x180019e85  jz      short loc_180019E97
0x180019e87  sub     eax, 1
0x180019e8a  mov     [rcx+7C4h], eax
0x180019e90  jnz     short loc_180019E97
0x180019e92  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180019e97  test    r14d, r14d
0x180019e9a  js      loc_18001A137
0x180019ea0  shr     esi, 8
0x180019ea3  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180019eab  jz      loc_18001A064
0x180019eb1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019eb8  cmp     byte ptr [rbx+8], 0
0x180019ebc  jz      short loc_180019EF3
0x180019ebe  mov     rcx, rbx; this
0x180019ec1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019ec6  mov     rcx, rax
0x180019ec9  mov     eax, [rax+7C4h]
0x180019ecf  cmp     eax, [rcx+7C8h]
0x180019ed5  jnb     short loc_180019EED
0x180019ed7  add     rax, rax
0x180019eda  lea     rdx, aConvertasciihe; "ConvertASCIIHexDigitToNumber"
0x180019ee1  mov     [rcx+rax*8], rdx
0x180019ee5  mov     dword ptr [rcx+rax*8+8], 0E3h
0x180019eed  inc     dword ptr [rcx+7C4h]
0x180019ef3  xor     r14d, r14d
0x180019ef6  lea     eax, [rsi-30h]
0x180019ef9  cmp     al, 9
0x180019efb  ja      loc_18001A3B3
0x180019f01  movzx   edi, sil
0x180019f05  sub     edi, 30h ; '0'
0x180019f08  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019f0f  cmp     byte ptr [rbx+8], 0
0x180019f13  jz      short loc_180019F3A
0x180019f15  mov     rcx, rbx; this
0x180019f18  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019f1d  mov     rcx, rax; this
0x180019f20  mov     eax, [rax+7C4h]
0x180019f26  test    eax, eax
0x180019f28  jz      short loc_180019F3A
0x180019f2a  sub     eax, 1
0x180019f2d  mov     [rcx+7C4h], eax
0x180019f33  jnz     short loc_180019F3A
0x180019f35  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180019f3a  test    r14d, r14d
0x180019f3d  js      loc_18001A1BA
0x180019f43  imul    r12d, ebp, 0Fh
0x180019f47  add     r12d, edi
0x180019f4a  xor     ebp, ebp
0x180019f4c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019f53  cmp     [rbx+8], bpl
0x180019f57  jz      loc_180019FEE
0x180019f5d  lea     rdi, [rbx+0D0h]
0x180019f64  call    cs:__imp_GetLastError
0x180019f6b  nop     dword ptr [rax+rax+00h]
0x180019f70  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180019f73  mov     esi, eax
0x180019f75  call    cs:__imp_TlsGetValue
0x180019f7c  nop     dword ptr [rax+rax+00h]
0x180019f81  test    rax, rax
0x180019f84  jz      loc_18001A0A5
0x180019f8a  mov     rdi, rax
0x180019f8d  mov     ecx, esi; dwErrCode
0x180019f8f  call    cs:__imp_SetLastError
0x180019f96  nop     dword ptr [rax+rax+00h]
0x180019f9b  mov     eax, [rdi+7C4h]
0x180019fa1  test    eax, eax
0x180019fa3  jz      short loc_180019FEE
0x180019fa5  sub     eax, 1
0x180019fa8  mov     [rdi+7C4h], eax
0x180019fae  jnz     short loc_180019FEE
0x180019fb0  mov     [rdi+7C4h], ebp
0x180019fb6  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180019fbd  mov     qword ptr [rdi+7E0h], 0
0x180019fc8  mov     [rdi+7CCh], ebp
0x180019fce  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180019fd6  mov     [rdi+7E8h], ebp
0x180019fdc  call    cs:__imp_GetCurrentThreadId
0x180019fe3  nop     dword ptr [rax+rax+00h]
0x180019fe8  mov     [rdi+7C0h], eax
0x180019fee  test    r14d, r14d
0x180019ff1  js      short loc_18001A024
0x180019ff3  cmp     [rsp+68h+arg_8], r12d
0x180019ff8  jnz     short loc_18001A024
0x180019ffa  mov     rcx, [rsp+68h+arg_18]
0x18001a002  mov     eax, 1
0x18001a007  mov     [rcx], r15d
0x18001a00a  mov     rbx, [rsp+68h+arg_0]
0x18001a00f  add     rsp, 30h
0x18001a013  pop     r15
0x18001a015  pop     r14
0x18001a017  pop     r13
0x18001a019  pop     r12
0x18001a01b  pop     rdi
0x18001a01c  pop     rsi
0x18001a01d  pop     rbp
0x18001a01e  retn
0x18001a020  xor     eax, eax
0x18001a022  jmp     short loc_18001A00A
0x18001a024  lea     r12, aGetstreamnumbe; "GetStreamNumberFromDataChunkID"
0x18001a02b  lea     r14, aConvertasciihe; "ConvertASCIIHexDigitToNumber"
0x18001a032  lea     rdi, qword_1801B97E0
0x18001a039  lea     eax, [r15-1]
0x18001a03d  inc     r15d
0x18001a040  cmp     [rsp+68h+arg_20], ebp
0x18001a047  cmovz   r15d, eax
0x18001a04b  jmp     loc_180019D5E
0x18001a050  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a055  jmp     loc_180019D8D
0x18001a05a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a05f  jmp     loc_180019E15
0x18001a064  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a069  jmp     loc_180019EB1
0x18001a06e  call    cs:__imp_GetLastError
0x18001a075  nop     dword ptr [rax+rax+00h]
0x18001a07a  test    eax, eax
0x18001a07c  jnz     loc_180019DCA
0x18001a082  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a089  test    rcx, rcx
0x18001a08c  jz      short loc_18001A0DC
0x18001a08e  mov     rax, [rcx]
0x18001a091  mov     rax, [rax]
0x18001a094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a099  test    rax, rax
0x18001a09c  cmovnz  rdi, rax
0x18001a0a0  jmp     loc_180019DCA
0x18001a0a5  call    cs:__imp_GetLastError
0x18001a0ac  nop     dword ptr [rax+rax+00h]
0x18001a0b1  test    eax, eax
0x18001a0b3  jnz     loc_180019F8D
0x18001a0b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a0c0  test    rcx, rcx
0x18001a0c3  jz      short loc_18001A0EA
0x18001a0c5  mov     rax, [rcx]
0x18001a0c8  mov     rax, [rax]
0x18001a0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d0  test    rax, rax
0x18001a0d3  cmovnz  rdi, rax
0x18001a0d7  jmp     loc_180019F8D
0x18001a0dc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a0e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a0e8  jmp     short loc_18001A08E
0x18001a0ea  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001a0ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a0f6  jmp     short loc_18001A0C5
0x18001a0f8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a100  mov     r14d, 80070057h
0x18001a106  jnz     loc_18001A305
0x18001a10c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a113  nop     dword ptr [rax+rax+00h]
0x18001a118  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a11f  mov     rcx, rax
0x18001a122  test    rax, rax
0x18001a125  jnz     loc_18001A2EC
0x18001a12b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a132  jmp     loc_18001A305
0x18001a137  xor     ebp, ebp
0x18001a139  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a140  jnz     loc_18001A365
0x18001a146  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a14d  nop     dword ptr [rax+rax+00h]
0x18001a152  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a159  mov     rcx, rax
0x18001a15c  test    rax, rax
0x18001a15f  jnz     loc_18001A34C
0x18001a165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a16c  jmp     loc_18001A365
0x18001a171  xor     edi, edi
0x18001a173  mov     esi, 80070057h
0x18001a178  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a17f  mov     r14d, esi
0x18001a182  jnz     loc_18001A3F6
0x18001a188  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a18f  nop     dword ptr [rax+rax+00h]
0x18001a194  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a19b  mov     rcx, rax
0x18001a19e  test    rax, rax
0x18001a1a1  jnz     loc_18001A3DD
0x18001a1a7  lea     rax, qword_1801B97E0
0x18001a1ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a1b5  jmp     loc_18001A3F6
0x18001a1ba  xor     ebp, ebp
0x18001a1bc  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a1c3  jnz     loc_18001A455
0x18001a1c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a1d0  nop     dword ptr [rax+rax+00h]
0x18001a1d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a1dc  mov     rcx, rax
0x18001a1df  test    rax, rax
0x18001a1e2  jnz     loc_18001A43C
0x18001a1e8  lea     rax, qword_1801B97E0
0x18001a1ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a1f6  jmp     loc_18001A455
0x18001a1fb  mov     rcx, rbx; this
0x18001a1fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a203  cmp     [rax+7CCh], r14d
0x18001a20a  jz      loc_18001A316
0x18001a210  mov     r9d, r14d; int
0x18001a213  lea     rdx, aConvertasciihe; "ConvertASCIIHexDigitToNumber"
0x18001a21a  mov     r8d, 0F3h; int
0x18001a220  mov     rcx, rax; this
0x18001a223  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a228  jmp     loc_18001A316
0x18001a22d  mov     rcx, rbx; this
0x18001a230  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a235  cmp     [rax+7CCh], r14d
0x18001a23c  jz      loc_18001A376
0x18001a242  mov     r9d, r14d; int
0x18001a245  lea     rdx, aGetstreamnumbe; "GetStreamNumberFromDataChunkID"
0x18001a24c  mov     r8d, 3Dh ; '='; int
0x18001a252  mov     rcx, rax; this
0x18001a255  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a25a  jmp     loc_18001A376
0x18001a25f  mov     rcx, rbx; this
0x18001a262  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a267  cmp     [rax+7CCh], esi
0x18001a26d  jz      loc_18001A407
0x18001a273  mov     r9d, esi; int
0x18001a276  lea     rdx, aConvertasciihe; "ConvertASCIIHexDigitToNumber"
  ... truncated ...
```
