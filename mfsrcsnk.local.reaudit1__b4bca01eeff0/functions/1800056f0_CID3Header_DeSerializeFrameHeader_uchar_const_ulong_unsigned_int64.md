# CID3Header::DeSerializeFrameHeader(uchar const *,ulong,unsigned __int64 *)

- ea: `0x1800056f0`
- end: `0x180005cee`
- name: `?DeSerializeFrameHeader@CID3Header@@UEAAJPEBEKPEA_K@Z`
- size: `1534`
- prototype: `__int64 __fastcall(CID3Header *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800056f0`
- `0x180005cf4`
- `0x18001c6c0`
- `0x180077708`
- `0x180079680`
- `0x1800796d4`
- `0x180079e7c`
- `0x18011cbac`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000576b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005857`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000576b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005857`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000591e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000591e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005751`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000583d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800058b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005751`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000583d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800058b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000594b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800059de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000594b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800059de`

## string_xrefs

- `0x18000572c`: `CID3Header::DeSerializeFrameHeader`
- `0x18000577d`: `CID3Header::DeSerializeFrameHeader`
- `0x18000586e`: `CID3Header::DeSerializeFrameHeader`

## pseudocode

```c
__int64 __fastcall CID3Header::DeSerializeFrameHeader(
        CID3Header *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
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

  v7 = this;
  if ( !CallStackTracing::s_wpInstance )
  {
    v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v29;
    this = v29;
    if ( !v29 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( a3 < 0xA )
  {
    v31 = CallStackTracing::s_wpInstance == 0;
    v17 = -1072875855;
    *a4 = 10;
    if ( v31 )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
      CallStackTracing::s_wpInstance = v33;
      if ( !v33 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, a2);
        CallStackTracing::s_wpInstance = v30;
        if ( !v30 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800056f0  mov     [rsp+arg_8], rbx
0x1800056f5  push    rbp
0x1800056f6  push    rsi
0x1800056f7  push    rdi
0x1800056f8  push    r12
0x1800056fa  push    r13
0x1800056fc  push    r14
0x1800056fe  push    r15
0x180005700  sub     rsp, 40h
0x180005704  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18000570c  lea     rdi, qword_1801B97E0
0x180005713  mov     r15, r9
0x180005716  mov     ebp, r8d
0x180005719  mov     r14, rdx
0x18000571c  mov     r13, rcx
0x18000571f  jz      loc_18000594B
0x180005725  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000572c  lea     rsi, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180005733  cmp     byte ptr [rbx+8], 0
0x180005737  jz      short loc_1800057A8
0x180005739  lea     rdi, [rbx+0D0h]
0x180005740  call    cs:__imp_GetLastError
0x180005747  nop     dword ptr [rax+rax+00h]
0x18000574c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000574f  mov     esi, eax
0x180005751  call    cs:__imp_TlsGetValue
0x180005758  nop     dword ptr [rax+rax+00h]
0x18000575d  test    rax, rax
0x180005760  jz      loc_180005A06
0x180005766  mov     rdi, rax
0x180005769  mov     ecx, esi; dwErrCode
0x18000576b  call    cs:__imp_SetLastError
0x180005772  nop     dword ptr [rax+rax+00h]
0x180005777  mov     eax, [rdi+7C4h]
0x18000577d  lea     rsi, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180005784  cmp     eax, [rdi+7C8h]
0x18000578a  jnb     short loc_18000579B
0x18000578c  add     rax, rax
0x18000578f  mov     [rdi+rax*8], rsi
0x180005793  mov     dword ptr [rdi+rax*8+8], 236h
0x18000579b  inc     dword ptr [rdi+7C4h]
0x1800057a1  lea     rdi, qword_1801B97E0
0x1800057a8  xor     r12d, r12d
0x1800057ab  mov     [r15], r12
0x1800057ae  cmp     ebp, 0Ah
0x1800057b1  jb      loc_1800059A1
0x1800057b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800057be  jnb     loc_180005C42
0x1800057c4  movzx   eax, word ptr [r14]
0x1800057c8  cmp     al, cs:?s_szID3v2HeaderTag@@3QBDB; char const near * const s_szID3v2HeaderTag
0x1800057ce  movzx   ecx, byte ptr [r14+2]
0x1800057d3  mov     [rsp+78h+var_48], ax
0x1800057d8  jnz     loc_180005BCF
0x1800057de  movzx   eax, byte ptr [rsp+78h+var_48+1]
0x1800057e3  cmp     al, cs:byte_18018CB1D
0x1800057e9  jnz     loc_180005BCF
0x1800057ef  cmp     cl, cs:byte_18018CB1E
0x1800057f5  jnz     loc_180005BCF
0x1800057fb  mov     eax, r12d
0x1800057fe  test    eax, eax
0x180005800  jz      loc_180005ADC
0x180005806  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18000580d  mov     ebp, 0C00D3E86h
0x180005812  jz      loc_180005976
0x180005818  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000581f  cmp     [rbx+8], r12b
0x180005823  jz      short loc_180005883
0x180005825  lea     rdi, [rbx+0D0h]
0x18000582c  call    cs:__imp_GetLastError
0x180005833  nop     dword ptr [rax+rax+00h]
0x180005838  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000583b  mov     esi, eax
0x18000583d  call    cs:__imp_TlsGetValue
0x180005844  nop     dword ptr [rax+rax+00h]
0x180005849  test    rax, rax
0x18000584c  jz      loc_180005A78
0x180005852  mov     rdi, rax
0x180005855  mov     ecx, esi; dwErrCode
0x180005857  call    cs:__imp_SetLastError
0x18000585e  nop     dword ptr [rax+rax+00h]
0x180005863  cmp     [rdi+7CCh], ebp
0x180005869  jz      short loc_180005883
0x18000586b  mov     r9d, ebp; int
0x18000586e  lea     rdx, aCid3headerDese; "CID3Header::DeSerializeFrameHeader"
0x180005875  mov     r8d, 24Ah; int
0x18000587b  mov     rcx, rdi; this
0x18000587e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005883  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000588a  jnb     loc_180005C81
0x180005890  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005897  cmp     [rbx+8], r12b
0x18000589b  jz      loc_180005930
0x1800058a1  lea     rdi, [rbx+0D0h]
0x1800058a8  call    cs:__imp_GetLastError
0x1800058af  nop     dword ptr [rax+rax+00h]
0x1800058b4  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800058b7  mov     esi, eax
0x1800058b9  call    cs:__imp_TlsGetValue
0x1800058c0  nop     dword ptr [rax+rax+00h]
0x1800058c5  test    rax, rax
0x1800058c8  jz      loc_180005A41
0x1800058ce  mov     rdi, rax
0x1800058d1  mov     ecx, esi; dwErrCode
0x1800058d3  call    cs:__imp_SetLastError
0x1800058da  nop     dword ptr [rax+rax+00h]
0x1800058df  mov     eax, [rdi+7C4h]
0x1800058e5  test    eax, eax
0x1800058e7  jz      short loc_180005930
0x1800058e9  sub     eax, 1
0x1800058ec  mov     [rdi+7C4h], eax
0x1800058f2  jnz     short loc_180005930
0x1800058f4  mov     [rdi+7C4h], r12d
0x1800058fb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180005902  mov     [rdi+7E0h], r12
0x180005909  mov     [rdi+7CCh], r12d
0x180005910  movups  xmmword ptr [rdi+7D0h], xmm0
0x180005917  mov     [rdi+7E8h], r12d
0x18000591e  call    cs:__imp_GetCurrentThreadId
0x180005925  nop     dword ptr [rax+rax+00h]
0x18000592a  mov     [rdi+7C0h], eax
0x180005930  mov     rbx, [rsp+78h+arg_8]
0x180005938  mov     eax, ebp
0x18000593a  add     rsp, 40h
0x18000593e  pop     r15
0x180005940  pop     r14
0x180005942  pop     r13
0x180005944  pop     r12
0x180005946  pop     rdi
0x180005947  pop     rsi
0x180005948  pop     rbp
0x180005949  retn
0x18000594b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180005952  nop     dword ptr [rax+rax+00h]
0x180005957  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000595e  mov     rcx, rax
0x180005961  test    rax, rax
0x180005964  jnz     loc_180005C06
0x18000596a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180005971  jmp     loc_180005725
0x180005976  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000597d  nop     dword ptr [rax+rax+00h]
0x180005982  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005989  mov     rcx, rax
0x18000598c  test    rax, rax
0x18000598f  jnz     loc_180005C63
0x180005995  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18000599c  jmp     loc_180005818
0x1800059a1  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x1800059a8  mov     ebp, 0C00D36B1h
0x1800059ad  mov     qword ptr [r15], 0Ah
0x1800059b4  jz      short loc_1800059DE
0x1800059b6  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800059bd  cmp     [rbx+8], r12b
0x1800059c1  jnz     loc_180005BD9
0x1800059c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800059ce  jb      loc_180005890
0x1800059d4  mov     edx, 2Bh ; '+'
0x1800059d9  jmp     loc_180005BA5
0x1800059de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800059e5  nop     dword ptr [rax+rax+00h]
0x1800059ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800059f1  mov     rcx, rax
0x1800059f4  test    rax, rax
0x1800059f7  jnz     loc_180005C24
0x1800059fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a04  jmp     short loc_1800059B6
0x180005a06  call    cs:__imp_GetLastError
0x180005a0d  nop     dword ptr [rax+rax+00h]
0x180005a12  test    eax, eax
0x180005a14  jnz     loc_180005769
0x180005a1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a21  test    rcx, rcx
0x180005a24  jz      loc_180005AAF
0x180005a2a  mov     rax, [rcx]
0x180005a2d  mov     rax, [rax]
0x180005a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a35  test    rax, rax
0x180005a38  cmovnz  rdi, rax
0x180005a3c  jmp     loc_180005769
0x180005a41  call    cs:__imp_GetLastError
0x180005a48  nop     dword ptr [rax+rax+00h]
0x180005a4d  test    eax, eax
0x180005a4f  jnz     loc_1800058D1
0x180005a55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a5c  test    rcx, rcx
0x180005a5f  jz      short loc_180005AC0
0x180005a61  mov     rax, [rcx]
0x180005a64  mov     rax, [rax]
0x180005a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a6c  test    rax, rax
0x180005a6f  cmovnz  rdi, rax
0x180005a73  jmp     loc_1800058D1
0x180005a78  call    cs:__imp_GetLastError
0x180005a7f  nop     dword ptr [rax+rax+00h]
0x180005a84  test    eax, eax
0x180005a86  jnz     loc_180005855
0x180005a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a93  test    rcx, rcx
0x180005a96  jz      short loc_180005ACE
0x180005a98  mov     rax, [rcx]
0x180005a9b  mov     rax, [rax]
0x180005a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa3  test    rax, rax
0x180005aa6  cmovnz  rdi, rax
0x180005aaa  jmp     loc_180005855
0x180005aaf  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005ab4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005abb  jmp     loc_180005A2A
0x180005ac0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005ac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005acc  jmp     short loc_180005A61
0x180005ace  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005ad3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005ada  jmp     short loc_180005A98
0x180005adc  movzx   ebx, byte ptr [r14+3]
0x180005ae1  mov     rcx, r13; this
0x180005ae4  movzx   r8d, byte ptr [r14+5]; unsigned __int8
0x180005ae9  movzx   edx, bl; unsigned __int8
0x180005aec  movzx   edi, byte ptr [r14+4]
0x180005af1  call    ?DecodeFlags@CID3Header@@IEAAJEE@Z; CID3Header::DecodeFlags(uchar,uchar)
0x180005af6  mov     edx, [r14+6]
0x180005afa  mov     r8d, edx
0x180005afd  shr     r8d, 10h
0x180005b01  movzx   ecx, dx
0x180005b04  and     ecx, 0FFFFFF00h
0x180005b0a  movzx   eax, dl
0x180005b0d  shl     eax, 10h
0x180005b10  or      ecx, eax
0x180005b12  mov     [r13+214h], edx
0x180005b19  movzx   eax, r8b
0x180005b1d  or      ecx, eax
0x180005b1f  shr     r8d, 8
0x180005b23  shl     ecx, 8
0x180005b26  or      ecx, r8d
0x180005b29  call    ??$SyncSafeBufToNumber@K@CId3SyncSafe@@CAKK@Z; CId3SyncSafe::SyncSafeBufToNumber<ulong>(ulong)
0x180005b2e  lea     ecx, [rbx-2]
0x180005b31  mov     [r13+214h], eax
0x180005b38  cmp     cl, 2
0x180005b3b  jbe     loc_180005CAC
0x180005b41  lea     ecx, [rax-1]
0x180005b44  mov     [r15], rcx
0x180005b47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180005b4e  jnb     loc_180005C8B
0x180005b54  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180005b5b  mov     ebp, 0C00D3E86h
0x180005b60  jz      short loc_180005BC8
0x180005b62  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005b69  cmp     [rbx+8], r12b
0x180005b6d  jz      short loc_180005B93
0x180005b6f  mov     rcx, rbx; this
0x180005b72  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005b77  cmp     [rax+7CCh], ebp
0x180005b7d  jz      short loc_180005B93
0x180005b7f  mov     r9d, ebp; int
0x180005b82  mov     r8d, 266h; int
0x180005b88  mov     rdx, rsi; char *
0x180005b8b  mov     rcx, rax; this
0x180005b8e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005b93  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180005b9a  jb      loc_180005890
0x180005ba0  mov     edx, 2Fh ; '/'
0x180005ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bac  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180005bb3  mov     r9, r13
0x180005bb6  mov     [rsp+78h+var_58], ebp
0x180005bba  mov     rcx, [rcx+10h]
0x180005bbe  call    WPP_SF_qD
0x180005bc3  jmp     loc_180005890
0x180005bc8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005bcd  jmp     short loc_180005B62
0x180005bcf  sbb     eax, eax
0x180005bd1  or      eax, 1
0x180005bd4  jmp     loc_1800057FE
0x180005bd9  mov     rcx, rbx; this
0x180005bdc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005be1  cmp     [rax+7CCh], ebp
0x180005be7  jz      loc_1800059C7
0x180005bed  mov     r9d, ebp; int
0x180005bf0  mov     r8d, 23Dh; int
0x180005bf6  mov     rdx, rsi; char *
0x180005bf9  mov     rcx, rax; this
0x180005bfc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005c01  jmp     loc_1800059C7
0x180005c06  mov     rax, [rax]
0x180005c09  mov     edx, 7F0h
0x180005c0e  mov     rax, [rax+8]
0x180005c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c17  test    eax, eax
0x180005c19  jnz     loc_180005725
0x180005c1f  jmp     loc_18000596A
0x180005c24  mov     rax, [rax]
0x180005c27  mov     edx, 7F0h
0x180005c2c  mov     rax, [rax+8]
0x180005c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c35  test    eax, eax
0x180005c37  jnz     loc_1800059B6
0x180005c3d  jmp     loc_1800059FD
0x180005c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c49  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180005c50  mov     edx, 2Ch ; ','
  ... truncated ...
```
