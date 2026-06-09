# CID3Header::DeSerializeFrameHeader(uchar const *,ulong,unsigned __int64 *)

- ea: `0x180012aa0`
- end: `0x180013035`
- name: `?DeSerializeFrameHeader@CID3Header@@UEAAJPEBEKPEA_K@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CID3Header *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180010190`
- `0x180012aa0`
- `0x18001303c`
- `0x180071a44`
- `0x180073b14`
- `0x180073b64`
- `0x180074428`
- `0x180115a1c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012be9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012be9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012afb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c3b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012afb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012bd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012d41`

## string_xrefs

- `0x180012adc`: `CID3Header::DeSerializeFrameHeader`
- `0x180012b1b`: `CID3Header::DeSerializeFrameHeader`
- `0x180012bfa`: `CID3Header::DeSerializeFrameHeader`

## pseudocode

```c
__int64 __fastcall CID3Header::DeSerializeFrameHeader(
        CID3Header *this,
        const unsigned __int8 *a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  unsigned int v5; // ebp
  CID3Header *v7; // r13
  CallStackTracing *v8; // rbx
  char *v9; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  bool v14; // cf
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebp
  CallStackTracing *v18; // rbx
  CallStackContext *v19; // rdi
  DWORD v20; // esi
  CallStackContext *v21; // rax
  CallStackTracing *v22; // rbx
  GUID *v23; // rdi
  DWORD v24; // esi
  GUID *v25; // rax
  int v26; // eax
  int v27; // eax
  CallStackTracing *v29; // rax
  CallStackTracing *v30; // rax
  bool v31; // zf
  __int64 v32; // rdx
  CallStackTracing *v33; // rax
  CallStackTracing *v34; // rcx
  __int64 v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  unsigned __int8 v40; // bl
  unsigned __int8 v41; // di
  unsigned int v42; // edx
  int v43; // eax
  struct CallStackContext *v44; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int16 v46; // [rsp+30h] [rbp-48h]

  v5 = a3;
  v7 = this;
  if ( !CallStackTracing::s_wpInstance )
  {
    v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2, a3, a4);
    CallStackTracing::s_wpInstance = v29;
    this = v29;
    if ( !v29 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v9 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v8 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v34 = CallStackTracing::s_wpInstance;
      }
      v35 = (**(__int64 (__fastcall ***)(CallStackTracing *))v34)(v34);
      if ( v35 )
        v9 = (char *)v35;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CID3Header::DeSerializeFrameHeader";
      *(_DWORD *)&v9[8 * v13 + 8] = 566;
    }
    ++*((_DWORD *)v9 + 497);
  }
  *a4 = 0;
  if ( v5 < 0xA )
  {
    v31 = CallStackTracing::s_wpInstance == 0;
    v17 = -1072875855;
    *a4 = 10;
    if ( v31 )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2, a3, a4);
      CallStackTracing::s_wpInstance = v33;
      if ( !v33 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875855 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::DeSerializeFrameHeader", 573, -1072875855);
    }
    if ( g_wppLevels )
    {
      v32 = 43;
      goto LABEL_68;
    }
  }
  else
  {
    if ( g_wppLevels >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
    v14 = (unsigned __int8)*(_WORD *)a2 < (unsigned __int8)s_szID3v2HeaderTag;
    v15 = a2[2];
    v46 = *(_WORD *)a2;
    if ( (unsigned __int8)*(_WORD *)a2 == (_BYTE)s_szID3v2HeaderTag
      && (v14 = HIBYTE(v46) < 0x44u, HIBYTE(v46) == 68)
      && (v14 = (unsigned __int8)v15 < 0x33u, (_BYTE)v15 == 51) )
    {
      v16 = 0;
    }
    else
    {
      v16 = v14 ? -1 : 1;
    }
    if ( v16 )
    {
      v17 = -1072873850;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, a2, a3, a4);
        CallStackTracing::s_wpInstance = v30;
        if ( !v30 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      v18 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v19 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
        v20 = GetLastError();
        v21 = (CallStackContext *)TlsGetValue(*((_DWORD *)v18 + 3));
        if ( v21 )
        {
          v19 = v21;
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
            v19 = (CallStackContext *)v39;
        }
        SetLastError(v20);
        if ( *((_DWORD *)v19 + 499) != -1072873850 )
          CallStackContext::TraceFailure(v19, "CID3Header::DeSerializeFrameHeader", 586, -1072873850);
      }
      if ( !g_wppLevels )
        goto LABEL_23;
      v32 = 45;
LABEL_68:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, &WPP_37a327c391a7379b3721a372142db134_Traceguids, v7, v17);
      goto LABEL_23;
    }
    v40 = a2[3];
    v41 = a2[4];
    CID3Header::DecodeFlags(v7, v40, a2[5]);
    v42 = *(_DWORD *)(a2 + 6);
    *((_DWORD *)v7 + 133) = v42;
    v43 = CId3SyncSafe::SyncSafeBufToNumber<unsigned long>(HIBYTE(v42) | ((BYTE2(v42)
                                                                         | ((unsigned __int8)v42 << 16)
                                                                         | v42 & 0xFF00) << 8));
    *((_DWORD *)v7 + 133) = v43;
    if ( (unsigned __int8)(v40 - 2) <= 2u )
    {
      v17 = 0;
      *((_BYTE *)v7 + 520) = v40;
      *((_BYTE *)v7 + 521) = v41;
      if ( g_wppLevels >= 0x10u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
      *a4 = 10;
    }
    else
    {
      *a4 = (unsigned int)(v43 - 1);
      if ( g_wppLevels >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
      v17 = -1072873850;
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v44 + 499) != -1072873850 )
          CallStackContext::TraceFailure(v44, "CID3Header::DeSerializeFrameHeader", 614, -1072873850);
      }
      if ( g_wppLevels )
      {
        v32 = 47;
        goto LABEL_68;
      }
    }
  }
LABEL_23:
  v22 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v23 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v24 = GetLastError();
    v25 = (GUID *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v25 )
    {
      v23 = v25;
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
        v23 = (GUID *)v37;
    }
    SetLastError(v24);
    v26 = *(_DWORD *)&v23[124].Data2;
    if ( v26 )
    {
      v27 = v26 - 1;
      *(_DWORD *)&v23[124].Data2 = v27;
      if ( !v27 )
      {
        *(_DWORD *)&v23[124].Data2 = 0;
        *(_QWORD *)&v23[126].Data1 = 0;
        *(_DWORD *)&v23[124].Data4[4] = 0;
        v23[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v23[126].Data4 = 0;
        v23[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x180012aa0  mov     [rsp+arg_8], rbx
0x180012aa5  push    rbp
0x180012aa6  push    rsi
0x180012aa7  push    rdi
0x180012aa8  push    r12
0x180012aaa  push    r13
0x180012aac  push    r14
0x180012aae  push    r15
0x180012ab0  sub     rsp, 40h
0x180012ab4  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180012abc  lea     rdi, qword_1801B07E0
0x180012ac3  mov     r15, r9
0x180012ac6  mov     ebp, r8d
0x180012ac9  mov     r14, rdx
0x180012acc  mov     r13, rcx
0x180012acf  jz      loc_180012CBA
0x180012ad5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012adc  lea     rsi, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180012ae3  cmp     byte ptr [rbx+8], 0
0x180012ae7  jz      short loc_180012B46
0x180012ae9  lea     rdi, [rbx+0D0h]
0x180012af0  call    cs:__imp_GetLastError
0x180012af6  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180012af9  mov     esi, eax
0x180012afb  call    cs:__imp_TlsGetValue
0x180012b01  test    rax, rax
0x180012b04  jz      loc_180012D63
0x180012b0a  mov     rdi, rax
0x180012b0d  mov     ecx, esi; dwErrCode
0x180012b0f  call    cs:__imp_SetLastError
0x180012b15  mov     eax, [rdi+7C4h]
0x180012b1b  lea     rsi, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180012b22  cmp     eax, [rdi+7C8h]
0x180012b28  jnb     short loc_180012B39
0x180012b2a  add     rax, rax
0x180012b2d  mov     [rdi+rax*8], rsi
0x180012b31  mov     dword ptr [rdi+rax*8+8], 236h
0x180012b39  inc     dword ptr [rdi+7C4h]
0x180012b3f  lea     rdi, qword_1801B07E0
0x180012b46  xor     r12d, r12d
0x180012b49  mov     [r15], r12
0x180012b4c  cmp     ebp, 0Ah
0x180012b4f  jb      loc_180012D04
0x180012b55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180012b5c  jnb     loc_180012F89
0x180012b62  movzx   eax, word ptr [r14]
0x180012b66  cmp     al, cs:?s_szID3v2HeaderTag@@3QBDB; char const near * const s_szID3v2HeaderTag
0x180012b6c  movzx   ecx, byte ptr [r14+2]
0x180012b71  mov     [rsp+78h+var_48], ax
0x180012b76  jnz     loc_180012F16
0x180012b7c  movzx   eax, byte ptr [rsp+78h+var_48+1]
0x180012b81  cmp     al, cs:byte_180183FFD
0x180012b87  jnz     loc_180012F16
0x180012b8d  cmp     cl, cs:byte_180183FFE
0x180012b93  jnz     loc_180012F16
0x180012b99  mov     eax, r12d
0x180012b9c  test    eax, eax
0x180012b9e  jz      loc_180012E23
0x180012ba4  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bab  mov     ebp, 0C00D3E86h
0x180012bb0  jz      loc_180012CDF
0x180012bb6  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bbd  cmp     [rbx+8], r12b
0x180012bc1  jz      short loc_180012C0F
0x180012bc3  lea     rdi, [rbx+0D0h]
0x180012bca  call    cs:__imp_GetLastError
0x180012bd0  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180012bd3  mov     esi, eax
0x180012bd5  call    cs:__imp_TlsGetValue
0x180012bdb  test    rax, rax
0x180012bde  jz      loc_180012DC5
0x180012be4  mov     rdi, rax
0x180012be7  mov     ecx, esi; dwErrCode
0x180012be9  call    cs:__imp_SetLastError
0x180012bef  cmp     [rdi+7CCh], ebp
0x180012bf5  jz      short loc_180012C0F
0x180012bf7  mov     r9d, ebp; int
0x180012bfa  lea     rdx, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180012c01  mov     r8d, 24Ah; int
0x180012c07  mov     rcx, rdi; this
0x180012c0a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012c0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012c16  jnb     loc_180012FC8
0x180012c1c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c23  cmp     [rbx+8], r12b
0x180012c27  jz      short loc_180012CA0
0x180012c29  lea     rdi, [rbx+0D0h]
0x180012c30  call    cs:__imp_GetLastError
0x180012c36  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180012c39  mov     esi, eax
0x180012c3b  call    cs:__imp_TlsGetValue
0x180012c41  test    rax, rax
0x180012c44  jz      loc_180012D94
0x180012c4a  mov     rdi, rax
0x180012c4d  mov     ecx, esi; dwErrCode
0x180012c4f  call    cs:__imp_SetLastError
0x180012c55  mov     eax, [rdi+7C4h]
0x180012c5b  test    eax, eax
0x180012c5d  jz      short loc_180012CA0
0x180012c5f  sub     eax, 1
0x180012c62  mov     [rdi+7C4h], eax
0x180012c68  jnz     short loc_180012CA0
0x180012c6a  mov     [rdi+7C4h], r12d
0x180012c71  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180012c78  mov     [rdi+7E0h], r12
0x180012c7f  mov     [rdi+7CCh], r12d
0x180012c86  movups  xmmword ptr [rdi+7D0h], xmm0
0x180012c8d  mov     [rdi+7E8h], r12d
0x180012c94  call    cs:__imp_GetCurrentThreadId
0x180012c9a  mov     [rdi+7C0h], eax
0x180012ca0  mov     rbx, [rsp+78h+arg_8]
0x180012ca8  mov     eax, ebp
0x180012caa  add     rsp, 40h
0x180012cae  pop     r15
0x180012cb0  pop     r14
0x180012cb2  pop     r13
0x180012cb4  pop     r12
0x180012cb6  pop     rdi
0x180012cb7  pop     rsi
0x180012cb8  pop     rbp
0x180012cb9  retn
0x180012cba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012cc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cc7  mov     rcx, rax
0x180012cca  test    rax, rax
0x180012ccd  jnz     loc_180012F4D
0x180012cd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cda  jmp     loc_180012AD5
0x180012cdf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012ce5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cec  mov     rcx, rax
0x180012cef  test    rax, rax
0x180012cf2  jnz     loc_180012FAA
0x180012cf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cff  jmp     loc_180012BB6
0x180012d04  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d0b  mov     ebp, 0C00D36B1h
0x180012d10  mov     qword ptr [r15], 0Ah
0x180012d17  jz      short loc_180012D41
0x180012d19  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d20  cmp     [rbx+8], r12b
0x180012d24  jnz     loc_180012F20
0x180012d2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012d31  jb      loc_180012C1C
0x180012d37  mov     edx, 2Bh ; '+'
0x180012d3c  jmp     loc_180012EEC
0x180012d41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012d47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d4e  mov     rcx, rax
0x180012d51  test    rax, rax
0x180012d54  jnz     loc_180012F6B
0x180012d5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d61  jmp     short loc_180012D19
0x180012d63  call    cs:__imp_GetLastError
0x180012d69  test    eax, eax
0x180012d6b  jnz     loc_180012B0D
0x180012d71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d78  test    rcx, rcx
0x180012d7b  jz      short loc_180012DF6
0x180012d7d  mov     rax, [rcx]
0x180012d80  mov     rax, [rax]
0x180012d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d88  test    rax, rax
0x180012d8b  cmovnz  rdi, rax
0x180012d8f  jmp     loc_180012B0D
0x180012d94  call    cs:__imp_GetLastError
0x180012d9a  test    eax, eax
0x180012d9c  jnz     loc_180012C4D
0x180012da2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012da9  test    rcx, rcx
0x180012dac  jz      short loc_180012E07
0x180012dae  mov     rax, [rcx]
0x180012db1  mov     rax, [rax]
0x180012db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db9  test    rax, rax
0x180012dbc  cmovnz  rdi, rax
0x180012dc0  jmp     loc_180012C4D
0x180012dc5  call    cs:__imp_GetLastError
0x180012dcb  test    eax, eax
0x180012dcd  jnz     loc_180012BE7
0x180012dd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012dda  test    rcx, rcx
0x180012ddd  jz      short loc_180012E15
0x180012ddf  mov     rax, [rcx]
0x180012de2  mov     rax, [rax]
0x180012de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dea  test    rax, rax
0x180012ded  cmovnz  rdi, rax
0x180012df1  jmp     loc_180012BE7
0x180012df6  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012dfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e02  jmp     loc_180012D7D
0x180012e07  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012e0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e13  jmp     short loc_180012DAE
0x180012e15  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012e1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e21  jmp     short loc_180012DDF
0x180012e23  movzx   ebx, byte ptr [r14+3]
0x180012e28  mov     rcx, r13; this
0x180012e2b  movzx   r8d, byte ptr [r14+5]; unsigned __int8
0x180012e30  movzx   edx, bl; unsigned __int8
0x180012e33  movzx   edi, byte ptr [r14+4]
0x180012e38  call    ?DecodeFlags@CID3Header@@IEAAJEE@Z; CID3Header::DecodeFlags(uchar,uchar)
0x180012e3d  mov     edx, [r14+6]
0x180012e41  mov     r8d, edx
0x180012e44  shr     r8d, 10h
0x180012e48  movzx   ecx, dx
0x180012e4b  and     ecx, 0FFFFFF00h
0x180012e51  movzx   eax, dl
0x180012e54  shl     eax, 10h
0x180012e57  or      ecx, eax
0x180012e59  mov     [r13+214h], edx
0x180012e60  movzx   eax, r8b
0x180012e64  or      ecx, eax
0x180012e66  shr     r8d, 8
0x180012e6a  shl     ecx, 8
0x180012e6d  or      ecx, r8d
0x180012e70  call    ??$SyncSafeBufToNumber@K@CId3SyncSafe@@CAKK@Z; CId3SyncSafe::SyncSafeBufToNumber<ulong>(ulong)
0x180012e75  lea     ecx, [rbx-2]
0x180012e78  mov     [r13+214h], eax
0x180012e7f  cmp     cl, 2
0x180012e82  jbe     loc_180012FF3
0x180012e88  lea     ecx, [rax-1]
0x180012e8b  mov     [r15], rcx
0x180012e8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180012e95  jnb     loc_180012FD2
0x180012e9b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180012ea2  mov     ebp, 0C00D3E86h
0x180012ea7  jz      short loc_180012F0F
0x180012ea9  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012eb0  cmp     [rbx+8], r12b
0x180012eb4  jz      short loc_180012EDA
0x180012eb6  mov     rcx, rbx; this
0x180012eb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012ebe  cmp     [rax+7CCh], ebp
0x180012ec4  jz      short loc_180012EDA
0x180012ec6  mov     r9d, ebp; int
0x180012ec9  mov     r8d, 266h; int
0x180012ecf  mov     rdx, rsi; char *
0x180012ed2  mov     rcx, rax; this
0x180012ed5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012eda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012ee1  jb      loc_180012C1C
0x180012ee7  mov     edx, 2Fh ; '/'
0x180012eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ef3  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180012efa  mov     r9, r13
0x180012efd  mov     [rsp+78h+var_58], ebp
0x180012f01  mov     rcx, [rcx+10h]
0x180012f05  call    WPP_SF_qD
0x180012f0a  jmp     loc_180012C1C
0x180012f0f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012f14  jmp     short loc_180012EA9
0x180012f16  sbb     eax, eax
0x180012f18  or      eax, 1
0x180012f1b  jmp     loc_180012B9C
0x180012f20  mov     rcx, rbx; this
0x180012f23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012f28  cmp     [rax+7CCh], ebp
0x180012f2e  jz      loc_180012D2A
0x180012f34  mov     r9d, ebp; int
0x180012f37  mov     r8d, 23Dh; int
0x180012f3d  mov     rdx, rsi; char *
0x180012f40  mov     rcx, rax; this
0x180012f43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012f48  jmp     loc_180012D2A
0x180012f4d  mov     rax, [rax]
0x180012f50  mov     edx, 7F0h
0x180012f55  mov     rax, [rax+8]
0x180012f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f5e  test    eax, eax
0x180012f60  jnz     loc_180012AD5
0x180012f66  jmp     loc_180012CD3
0x180012f6b  mov     rax, [rax]
0x180012f6e  mov     edx, 7F0h
0x180012f73  mov     rax, [rax+8]
0x180012f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7c  test    eax, eax
0x180012f7e  jnz     loc_180012D19
0x180012f84  jmp     loc_180012D5A
0x180012f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f90  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180012f97  mov     edx, 2Ch ; ','
0x180012f9c  mov     rcx, [rcx+10h]
0x180012fa0  call    WPP_SF_
0x180012fa5  jmp     loc_180012B62
0x180012faa  mov     rax, [rax]
0x180012fad  mov     edx, 7F0h
0x180012fb2  mov     rax, [rax+8]
0x180012fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fbb  test    eax, eax
0x180012fbd  jnz     loc_180012BB6
0x180012fc3  jmp     loc_180012CF8
0x180012fc8  mov     edx, 2Dh ; '-'
0x180012fcd  jmp     loc_180012EEC
0x180012fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fd9  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180012fe0  mov     edx, 2Eh ; '.'
0x180012fe5  mov     rcx, [rcx+10h]
  ... truncated ...
```
