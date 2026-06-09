# TextFrameToWMValueEx(uchar const *,ulong,WMT_ATTR_DATATYPE *,uchar *,ulong *)

- ea: `0x1800271a0`
- end: `0x180027a05`
- name: `?TextFrameToWMValueEx@@YAJPEBEKPEAW4WMT_ATTR_DATATYPE@@PEAEPEAK@Z`
- size: `2149`
- prototype: `__int64 __fastcall(CallStackTracing *, __int64, enum WMT_ATTR_DATATYPE *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180027d10`
- `0x180029610`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x1800271a0`
- `0x180077708`
- `0x180079680`
- `0x180111960`
- `0x18016a1c4`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027224`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027401`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027224`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180027346`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002761a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180027346`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002761a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027459`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002720a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800273e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002720a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800273e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002770f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027787`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002770f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027787`

## pseudocode

```c
__int64 __fastcall TextFrameToWMValueEx(
        CallStackTracing *a1,
        __int64 a2,
        enum WMT_ATTR_DATATYPE *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  int v5; // r14d
  const unsigned __int8 *v6; // rsi
  CallStackTracing *v9; // rbx
  char *v10; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int8 v15; // bl
  const CHAR *v16; // rbp
  int v17; // edi
  unsigned __int64 v18; // rdx
  int v19; // r8d
  __int64 v20; // rcx
  _WORD *v21; // rax
  unsigned int v22; // esi
  unsigned int v23; // r14d
  CallStackTracing *v24; // rbx
  GUID *v25; // rdi
  DWORD v26; // esi
  GUID *v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v31; // rdx
  CallStackTracing *v32; // rax
  signed int v33; // r12d
  unsigned __int64 v34; // rdi
  signed int v35; // edx
  int v36; // ebx
  int v37; // eax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rax
  CallStackTracing *v42; // rax
  CallStackTracing *v43; // rax
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v5 = a2;
  v6 = (const unsigned __int8 *)a1;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
    CallStackTracing::s_wpInstance = v32;
    a1 = v32;
    if ( !v32 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
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
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v10 = (char *)v39;
    }
    SetLastError(LastError);
    v13 = *((unsigned int *)v10 + 497);
    if ( (unsigned int)v13 < *((_DWORD *)v10 + 498) )
    {
      v14 = 2 * v13;
      *(_QWORD *)&v10[8 * v14] = "TextFrameToWMValueEx";
      *(_DWORD *)&v10[8 * v14 + 8] = 1305;
    }
    ++*((_DWORD *)v10 + 497);
  }
  if ( !v6 || !a3 || !a5 )
  {
    v23 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "TextFrameToWMValueEx", 1324, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_34;
    v31 = 30;
LABEL_46:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, WPP_9186553898a13577d84523ff6f078a03_Traceguids, 0, v23);
    goto LABEL_34;
  }
  if ( !v5 )
  {
    v23 = -1072873844;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
      CallStackTracing::s_wpInstance = v42;
      if ( !v42 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v45 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v45, "TextFrameToWMValueEx", 1332, -1072873844);
    }
    if ( !g_wppLevels )
      goto LABEL_34;
    v31 = 31;
    goto LABEL_46;
  }
  v15 = *v6;
  if ( *v6 >= 4u )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
      CallStackTracing::s_wpInstance = v43;
      if ( !v43 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v46 + 499) != -1072873844 )
        CallStackContext::TraceFailure(v46, "TextFrameToWMValueEx", 1339, -1072873844);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_9186553898a13577d84523ff6f078a03_Traceguids,
        0,
        -1072873844);
    v23 = -1072873844;
    goto LABEL_34;
  }
  v16 = (const CHAR *)(v6 + 1);
  v17 = v5 - 1;
  if ( !v15 || v15 == 3 )
  {
    v18 = (unsigned int)MultiByteToWideChar(v15 != 0 ? 0xFDE9 : 0, 0, (LPCCH)v6 + 1, v17, 0, 0);
    if ( v5 == 1 || v17 > 0 && (v20 = v17, v6[v17]) )
      v18 = (unsigned int)(v18 + 1);
  }
  else
  {
    v18 = (unsigned __int64)v17 >> 1;
    v19 = v18;
    if ( !(_DWORD)v18 || (int)v18 > 0 && *(_WORD *)&v16[2 * (int)v18 - 2] )
      v18 = (unsigned int)(v18 + 1);
    v20 = 65534;
    if ( v15 == 1 && v19 )
    {
      v21 = v6 + 1;
      if ( *(_WORD *)v16 == 0xFEFF )
      {
        v18 = (unsigned int)(v18 - 1);
        if ( v19 == 1 )
          goto LABEL_28;
        v21 = v6 + 3;
      }
      if ( *v21 == 0xFFFE )
        v18 = (unsigned int)(v18 - 1);
    }
  }
LABEL_28:
  v22 = 2 * v18;
  if ( 2 * (_DWORD)v18 )
  {
    v23 = 0;
    if ( v22 > *a5 )
    {
      if ( a4 )
        v23 = -1072875855;
      goto LABEL_32;
    }
    if ( !a4 )
      goto LABEL_32;
    memset_0(a4, 0, *a5);
    v33 = v22 >> 1;
    if ( !v15 || v15 == 3 )
    {
      v37 = MultiByteToWideChar(v15 != 0 ? 0xFDE9 : 0, 0, v16, v17, (LPWSTR)a4, v22 >> 1);
      if ( !v17 || v17 > 0 && v16[v17 - 1] )
      {
        v23 = 0;
        if ( v37 < v33 )
        {
          *(_WORD *)&a4[2 * v37] = 0;
          *a5 = v22;
          goto LABEL_33;
        }
      }
LABEL_32:
      *a5 = v22;
      if ( (int)(v23 + 0x80000000) >= 0 && v23 != -1072875855 )
        goto LABEL_34;
LABEL_33:
      *a3 = WMT_TYPE_STRING;
      goto LABEL_34;
    }
    if ( (unsigned __int8)(v15 - 1) > 1u )
    {
      *(_WORD *)a4 = 0;
      *a5 = v22;
      goto LABEL_33;
    }
    if ( v17 == -1 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *(_WORD *)&v16[2 * v34] );
      LODWORD(v34) = v34 + 1;
      v35 = v34;
    }
    else
    {
      v34 = (unsigned __int64)v17 >> 1;
      if ( !(_DWORD)v34 || (v35 = v34, (int)v34 > 0) && *(_WORD *)&v16[2 * (int)v34 - 2] )
        v35 = v34 + 1;
    }
    if ( v15 == 1 )
    {
      v36 = 0;
      if ( !(_DWORD)v34 )
        goto LABEL_64;
      if ( *(_WORD *)v16 == 0xFEFF )
      {
        v16 += 2;
        --v35;
        LODWORD(v34) = v34 - 1;
        if ( !(_DWORD)v34 )
          goto LABEL_64;
      }
      if ( *(_WORD *)v16 != 0xFFFE )
        goto LABEL_64;
      v16 += 2;
      LODWORD(v34) = v34 - 1;
      --v35;
    }
    v36 = 1;
LABEL_64:
    if ( v33 )
    {
      if ( v35 <= v33 )
      {
        memset_0(a4, 0, 2LL * v35);
        memcpy_0(a4, v16, 2LL * (int)v34);
        if ( v36 )
          ConvertWideCharByteOrder((unsigned __int16 *)a4, v34);
      }
    }
    *a5 = v22;
    v23 = 0;
    goto LABEL_33;
  }
  v23 = -1072873844;
  if ( !CallStackTracing::s_wpInstance )
  {
    v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v18);
    CallStackTracing::s_wpInstance = v44;
    if ( !v44 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v47 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v47 + 499) != -1072873844 )
      CallStackContext::TraceFailure(v47, "TextFrameToWMValueEx", 1354, -1072873844);
  }
  if ( g_wppLevels )
  {
    v31 = 33;
    goto LABEL_46;
  }
LABEL_34:
  v24 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v25 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v26 = GetLastError();
    v27 = (GUID *)TlsGetValue(*((_DWORD *)v24 + 3));
    if ( v27 )
    {
      v25 = v27;
    }
    else if ( !GetLastError() )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v40 = CallStackTracing::s_wpInstance;
      }
      v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
      if ( v41 )
        v25 = (GUID *)v41;
    }
    SetLastError(v26);
    v28 = *(_DWORD *)&v25[124].Data2;
    if ( v28 )
    {
      v29 = v28 - 1;
      *(_DWORD *)&v25[124].Data2 = v29;
      if ( !v29 )
      {
        *(_DWORD *)&v25[124].Data2 = 0;
        *(_QWORD *)&v25[126].Data1 = 0;
        *(_DWORD *)&v25[124].Data4[4] = 0;
        v25[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v25[126].Data4 = 0;
        v25[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v23;
}

```

## disassembly

```asm
0x1800271a0  mov     [rsp+arg_18], r9
0x1800271a5  push    rbx
0x1800271a6  push    rsi
0x1800271a7  push    rdi
0x1800271a8  push    r14
0x1800271aa  sub     rsp, 38h
0x1800271ae  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800271b6  lea     rdi, qword_1801B97E0
0x1800271bd  mov     [rsp+58h+arg_0], rbp
0x1800271c2  mov     r14d, edx
0x1800271c5  mov     [rsp+58h+arg_8], r12
0x1800271ca  mov     rsi, rcx
0x1800271cd  mov     [rsp+58h+arg_10], r13
0x1800271d2  mov     r12, r9
0x1800271d5  mov     r13, r8
0x1800271d8  jz      loc_1800274D4
0x1800271de  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800271e5  lea     rbp, aTextframetowmv; "TextFrameToWMValueEx"
0x1800271ec  cmp     byte ptr [rbx+8], 0
0x1800271f0  jz      short loc_180027261
0x1800271f2  lea     rdi, [rbx+0D0h]
0x1800271f9  call    cs:__imp_GetLastError
0x180027200  nop     dword ptr [rax+rax+00h]
0x180027205  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180027208  mov     ebp, eax
0x18002720a  call    cs:__imp_TlsGetValue
0x180027211  nop     dword ptr [rax+rax+00h]
0x180027216  test    rax, rax
0x180027219  jz      loc_180027671
0x18002721f  mov     rdi, rax
0x180027222  mov     ecx, ebp; dwErrCode
0x180027224  call    cs:__imp_SetLastError
0x18002722b  nop     dword ptr [rax+rax+00h]
0x180027230  mov     eax, [rdi+7C4h]
0x180027236  lea     rbp, aTextframetowmv; "TextFrameToWMValueEx"
0x18002723d  cmp     eax, [rdi+7C8h]
0x180027243  jnb     short loc_180027254
0x180027245  add     rax, rax
0x180027248  mov     [rdi+rax*8], rbp
0x18002724c  mov     dword ptr [rdi+rax*8+8], 519h
0x180027254  inc     dword ptr [rdi+7C4h]
0x18002725a  lea     rdi, qword_1801B97E0
0x180027261  mov     [rsp+58h+var_28], r15
0x180027266  test    rsi, rsi
0x180027269  jz      loc_180027479
0x18002726f  test    r13, r13
0x180027272  jz      loc_180027479
0x180027278  mov     r15, [rsp+58h+arg_20]
0x180027280  test    r15, r15
0x180027283  jz      loc_180027479
0x180027289  cmp     r14d, 1
0x18002728d  jb      loc_1800276FB
0x180027293  movzx   ebx, byte ptr [rsi]
0x180027296  cmp     bl, 4
0x180027299  jnb     loc_18002773A
0x18002729f  lea     rbp, [rsi+1]
0x1800272a3  mov     ecx, 0FFFEh
0x1800272a8  lea     edi, [r14-1]
0x1800272ac  mov     r9d, 0FEFFh
0x1800272b2  test    bl, bl
0x1800272b4  jz      short loc_180027320
0x1800272b6  cmp     bl, 1
0x1800272b9  jnz     short loc_180027317
0x1800272bb  cmp     edi, 0FFFFFFFFh
0x1800272be  jz      loc_18002794F
0x1800272c4  movsxd  rdx, edi
0x1800272c7  shr     rdx, 1
0x1800272ca  mov     r8d, edx
0x1800272cd  test    edx, edx
0x1800272cf  jz      loc_180027662
0x1800272d5  jle     short loc_1800272E7
0x1800272d7  movsxd  rcx, edx
0x1800272da  xor     eax, eax
0x1800272dc  cmp     ax, [rbp+rcx*2-2]
0x1800272e1  jnz     loc_180027662
0x1800272e7  mov     ecx, 0FFFEh
0x1800272ec  cmp     bl, 1
0x1800272ef  jnz     short loc_18002736C
0x1800272f1  test    r8d, r8d
0x1800272f4  jz      short loc_18002736C
0x1800272f6  mov     rax, rbp
0x1800272f9  cmp     r9w, [rbp+0]
0x1800272fe  jnz     short loc_18002730E
0x180027300  dec     edx
0x180027302  lea     eax, [r8-1]
0x180027306  test    eax, eax
0x180027308  jz      short loc_18002736C
0x18002730a  lea     rax, [rbp+2]
0x18002730e  cmp     cx, [rax]
0x180027311  jnz     short loc_18002736C
0x180027313  dec     edx
0x180027315  jmp     short loc_18002736C
0x180027317  cmp     bl, 3
0x18002731a  jnz     loc_18002793F
0x180027320  movzx   eax, bl
0x180027323  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x18002732b  neg     al
0x18002732d  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x180027336  mov     r9d, edi; cbMultiByte
0x180027339  mov     r8, rbp; lpMultiByteStr
0x18002733c  sbb     ecx, ecx
0x18002733e  xor     edx, edx; dwFlags
0x180027340  and     ecx, 0FDE9h; CodePage
0x180027346  call    cs:__imp_MultiByteToWideChar
0x18002734d  nop     dword ptr [rax+rax+00h]
0x180027352  mov     edx, eax
0x180027354  test    edi, edi
0x180027356  jz      loc_18002765B
0x18002735c  jle     short loc_18002736C
0x18002735e  movsxd  rcx, edi
0x180027361  cmp     byte ptr [rcx+rbp-1], 0
0x180027366  jnz     loc_18002765B
0x18002736c  lea     esi, [rdx+rdx]
0x18002736f  test    esi, esi
0x180027371  jz      loc_180027773
0x180027377  mov     eax, [r15]
0x18002737a  xor     r14d, r14d
0x18002737d  cmp     esi, eax
0x18002737f  jbe     loc_180027511
0x180027385  test    r12, r12
0x180027388  jnz     loc_1800279AC
0x18002738e  mov     ecx, 80000000h
0x180027393  mov     [r15], esi
0x180027396  lea     eax, [r14+rcx]
0x18002739a  test    ecx, eax
0x18002739c  jz      loc_1800274FF
0x1800273a2  mov     dword ptr [r13+0], 1
0x1800273aa  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800273b1  mov     r15, [rsp+58h+var_28]
0x1800273b6  mov     r13, [rsp+58h+arg_10]
0x1800273bb  mov     r12, [rsp+58h+arg_8]
0x1800273c0  cmp     byte ptr [rbx+8], 0
0x1800273c4  mov     rbp, [rsp+58h+arg_0]
0x1800273c9  jz      loc_18002746B
0x1800273cf  lea     rdi, [rbx+0D0h]
0x1800273d6  call    cs:__imp_GetLastError
0x1800273dd  nop     dword ptr [rax+rax+00h]
0x1800273e2  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800273e5  mov     esi, eax
0x1800273e7  call    cs:__imp_TlsGetValue
0x1800273ee  nop     dword ptr [rax+rax+00h]
0x1800273f3  test    rax, rax
0x1800273f6  jz      loc_1800276A8
0x1800273fc  mov     rdi, rax
0x1800273ff  mov     ecx, esi; dwErrCode
0x180027401  call    cs:__imp_SetLastError
0x180027408  nop     dword ptr [rax+rax+00h]
0x18002740d  mov     eax, [rdi+7C4h]
0x180027413  test    eax, eax
0x180027415  jz      short loc_18002746B
0x180027417  sub     eax, 1
0x18002741a  mov     [rdi+7C4h], eax
0x180027420  jnz     short loc_18002746B
0x180027422  mov     dword ptr [rdi+7C4h], 0
0x18002742c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180027433  mov     qword ptr [rdi+7E0h], 0
0x18002743e  mov     dword ptr [rdi+7CCh], 0
0x180027448  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002744f  mov     dword ptr [rdi+7E8h], 0
0x180027459  call    cs:__imp_GetCurrentThreadId
0x180027460  nop     dword ptr [rax+rax+00h]
0x180027465  mov     [rdi+7C0h], eax
0x18002746b  mov     eax, r14d
0x18002746e  add     rsp, 38h
0x180027472  pop     r14
0x180027474  pop     rdi
0x180027475  pop     rsi
0x180027476  pop     rbx
0x180027477  retn
0x180027479  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180027481  mov     r14d, 80070057h
0x180027487  jz      loc_1800275EF
0x18002748d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027494  cmp     byte ptr [rbx+8], 0
0x180027498  jnz     loc_18002784D
0x18002749e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800274a5  jb      loc_1800273AA
0x1800274ab  mov     edx, 1Eh
0x1800274b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274b7  lea     r8, WPP_9186553898a13577d84523ff6f078a03_Traceguids
0x1800274be  xor     r9d, r9d
0x1800274c1  mov     dword ptr [rsp+58h+lpWideCharStr], r14d
0x1800274c6  mov     rcx, [rcx+10h]
0x1800274ca  call    WPP_SF_qD
0x1800274cf  jmp     loc_1800273AA
0x1800274d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800274db  nop     dword ptr [rax+rax+00h]
0x1800274e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800274e7  mov     rcx, rax
0x1800274ea  test    rax, rax
0x1800274ed  jnz     loc_18002787B
0x1800274f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800274fa  jmp     loc_1800271DE
0x1800274ff  cmp     r14d, 0C00D36B1h
0x180027506  jz      loc_1800273A2
0x18002750c  jmp     loc_1800273AA
0x180027511  test    r12, r12
0x180027514  jz      loc_18002738E
0x18002751a  mov     r8, rax; Size
0x18002751d  xor     edx, edx; Val
0x18002751f  mov     rcx, r12; void *
0x180027522  call    memset_0
0x180027527  mov     r12d, esi
0x18002752a  shr     r12d, 1
0x18002752d  test    bl, bl
0x18002752f  jz      loc_1800275F9
0x180027535  cmp     bl, 3
0x180027538  jz      loc_1800275F9
0x18002753e  lea     eax, [rbx-1]
0x180027541  cmp     al, 1
0x180027543  ja      loc_1800279B7
0x180027549  cmp     edi, 0FFFFFFFFh
0x18002754c  jz      loc_1800279C9
0x180027552  movsxd  rdi, edi
0x180027555  shr     rdi, 1
0x180027558  test    edi, edi
0x18002755a  jz      loc_180027669
0x180027560  mov     edx, edi
0x180027562  jle     short loc_180027574
0x180027564  movsxd  rcx, edi
0x180027567  xor     eax, eax
0x180027569  cmp     ax, [rbp+rcx*2-2]
0x18002756e  jnz     loc_180027669
0x180027574  cmp     bl, 1
0x180027577  jnz     loc_1800279EC
0x18002757d  xor     ebx, ebx
0x18002757f  test    edi, edi
0x180027581  jz      short loc_1800275AC
0x180027583  mov     eax, 0FEFFh
0x180027588  cmp     ax, [rbp+0]
0x18002758c  jnz     short loc_18002759D
0x18002758e  lea     eax, [rdi-1]
0x180027591  add     rbp, 2
0x180027595  dec     edx
0x180027597  mov     edi, eax
0x180027599  test    eax, eax
0x18002759b  jz      short loc_1800275AC
0x18002759d  mov     eax, 0FFFEh
0x1800275a2  cmp     ax, [rbp+0]
0x1800275a6  jz      loc_1800279E4
0x1800275ac  test    r12d, r12d
0x1800275af  jz      short loc_1800275E4
0x1800275b1  cmp     edx, r12d
0x1800275b4  jg      short loc_1800275E4
0x1800275b6  mov     r14, [rsp+58h+arg_18]
0x1800275bb  movsxd  r8, edx
0x1800275be  mov     rcx, r14; void *
0x1800275c1  add     r8, r8; Size
0x1800275c4  xor     edx, edx; Val
0x1800275c6  call    memset_0
0x1800275cb  movsxd  r8, edi
0x1800275ce  mov     rdx, rbp; Src
0x1800275d1  add     r8, r8; Size
0x1800275d4  mov     rcx, r14; void *
0x1800275d7  call    memcpy_0
0x1800275dc  test    ebx, ebx
0x1800275de  jnz     loc_1800279F6
0x1800275e4  mov     [r15], esi
0x1800275e7  xor     r14d, r14d
0x1800275ea  jmp     loc_1800273A2
0x1800275ef  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800275f4  jmp     loc_18002748D
0x1800275f9  neg     bl
0x1800275fb  mov     [rsp+58h+cchWideChar], r12d; cchWideChar
0x180027600  mov     rbx, [rsp+58h+arg_18]
0x180027605  mov     r9d, edi; cbMultiByte
0x180027608  sbb     ecx, ecx
0x18002760a  mov     [rsp+58h+lpWideCharStr], rbx; lpWideCharStr
0x18002760f  and     ecx, 0FDE9h; CodePage
0x180027615  mov     r8, rbp; lpMultiByteStr
0x180027618  xor     edx, edx; dwFlags
0x18002761a  call    cs:__imp_MultiByteToWideChar
0x180027621  nop     dword ptr [rax+rax+00h]
0x180027626  test    edi, edi
0x180027628  jz      short loc_18002763E
0x18002762a  jle     loc_18002738E
0x180027630  movsxd  rcx, edi
0x180027633  cmp     [rcx+rbp-1], r14b
0x180027638  jz      loc_18002738E
0x18002763e  xor     r14d, r14d
0x180027641  cmp     eax, r12d
0x180027644  jge     loc_18002738E
0x18002764a  movsxd  rcx, eax
0x18002764d  xor     eax, eax
0x18002764f  mov     [rbx+rcx*2], ax
0x180027653  mov     [r15], esi
0x180027656  jmp     loc_1800273A2
0x18002765b  inc     edx
0x18002765d  jmp     loc_18002736C
0x180027662  inc     edx
0x180027664  jmp     loc_1800272E7
0x180027669  lea     edx, [rdi+1]
0x18002766c  jmp     loc_180027574
0x180027671  call    cs:__imp_GetLastError
0x180027678  nop     dword ptr [rax+rax+00h]
0x18002767d  test    eax, eax
0x18002767f  jnz     loc_180027222
0x180027685  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002768c  test    rcx, rcx
0x18002768f  jz      short loc_1800276DF
  ... truncated ...
```
