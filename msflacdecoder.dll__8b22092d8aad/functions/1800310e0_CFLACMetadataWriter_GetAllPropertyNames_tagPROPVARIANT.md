# CFLACMetadataWriter::GetAllPropertyNames(tagPROPVARIANT *)

- ea: `0x1800310e0`
- end: `0x1800313ce`
- name: `?GetAllPropertyNames@CFLACMetadataWriter@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(CFLACMetadataWriter *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x1800310e0`
- `0x180031bdc`
- `0x1800344c0`
- `0x180034a04`
- `0x180037a1c`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031149`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003124d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800312dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031149`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003124d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800312dc`

## string_xrefs

- `0x18003111e`: `CFLACMetadataWriter::GetAllPropertyNames`
- `0x1800311a3`: `CFLACMetadataWriter::GetAllPropertyNames`
- `0x1800312aa`: `CFLACMetadataWriter::GetAllPropertyNames`
- `0x180031339`: `CFLACMetadataWriter::GetAllPropertyNames`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFLACMetadataWriter::GetAllPropertyNames(CFLACMetadataWriter *this, struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  int String; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 i; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT v22; // [rsp+50h] [rbp-20h] BYREF

  memset(&v22, 0, sizeof(v22));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CFLACMetadataWriter::GetAllPropertyNames", 187);
  if ( a2 )
  {
    String = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
    {
      memset(&pvar, 0, sizeof(pvar));
      String = CMFPropVariant::CreateString(
                 (CMFPropVariant *)&pvar,
                 31,
                 *(const CHAR **)(*((_QWORD *)this + 2) + 8 * i));
      if ( String < 0 )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != String )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CFLACMetadataWriter::GetAllPropertyNames",
              193,
              String);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v15 = 19;
LABEL_37:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
            (char *)this - 8,
            String);
        }
LABEL_38:
        CMFPropVariant::Clear(&pvar);
        goto LABEL_40;
      }
      String = CMFPropVariant::AppendUniqueElement((CMFPropVariant *)&v22, &pvar);
      if ( String < 0 )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v14 + 499) != String )
            CallStackContext::TraceFailure(v14, "CFLACMetadataWriter::GetAllPropertyNames", 194, String);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v15 = 20;
          goto LABEL_37;
        }
        goto LABEL_38;
      }
      CMFPropVariant::Clear(&pvar);
    }
    *a2 = v22;
    v22.vt = 0;
  }
  else
  {
    String = -2147467261;
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CFLACMetadataWriter::GetAllPropertyNames", 187, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        -2147467261);
  }
LABEL_40:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  CMFPropVariant::Clear(&v22);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800310e0  mov     [rsp-18h+arg_10], rbx
0x1800310e5  mov     [rsp-18h+arg_18], rsi
0x1800310ea  push    rbp
0x1800310eb  push    rdi
0x1800310ec  push    r14
0x1800310ee  mov     rbp, rsp
0x1800310f1  sub     rsp, 70h
0x1800310f5  mov     rax, cs:__security_cookie
0x1800310fc  xor     rax, rsp
0x1800310ff  mov     [rbp+var_8], rax
0x180031103  mov     rsi, rdx
0x180031106  mov     r14, rcx
0x180031109  xorps   xmm0, xmm0
0x18003110c  xor     eax, eax
0x18003110e  movups  xmmword ptr [rbp+var_20], xmm0
0x180031112  mov     qword ptr [rbp+var_20+10h], rax
0x180031116  mov     edi, 0BBh
0x18003111b  mov     r8d, edi; int
0x18003111e  lea     rdx, aCflacmetadataw_4; "CFLACMetadataWriter::GetAllPropertyName"...
0x180031125  lea     rcx, [rbp+var_40]; this
0x180031129  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003112e  nop
0x18003112f  test    rsi, rsi
0x180031132  jnz     loc_1800311E8
0x180031138  mov     ebx, 80004003h
0x18003113d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031144  test    rcx, rcx
0x180031147  jnz     short loc_18003118A
0x180031149  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003114f  mov     rcx, rax
0x180031152  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031159  test    rax, rax
0x18003115c  jz      short loc_18003117C
0x18003115e  mov     rax, [rax]
0x180031161  mov     edx, 7F0h
0x180031166  mov     rax, [rax+8]
0x18003116a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003116f  test    eax, eax
0x180031171  jz      short loc_18003117C
0x180031173  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003117a  jmp     short loc_18003118A
0x18003117c  lea     rcx, qword_18006EB20; this
0x180031183  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003118a  cmp     byte ptr [rcx+8], 0
0x18003118e  jz      short loc_1800311B2
0x180031190  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031195  cmp     [rax+7CCh], ebx
0x18003119b  jz      short loc_1800311B2
0x18003119d  mov     r9d, ebx; int
0x1800311a0  mov     r8d, edi; int
0x1800311a3  lea     rdx, aCflacmetadataw_4; "CFLACMetadataWriter::GetAllPropertyName"...
0x1800311aa  mov     rcx, rax; this
0x1800311ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800311b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800311b7  cmp     al, 1
0x1800311b9  jb      loc_180031398
0x1800311bf  lea     r9, [r14-8]
0x1800311c3  mov     edx, 12h
0x1800311c8  mov     [rsp+70h+var_50], ebx
0x1800311cc  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x1800311d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311da  mov     rcx, [rcx+10h]
0x1800311de  call    WPP_SF_qd
0x1800311e3  jmp     loc_180031398
0x1800311e8  xor     ebx, ebx
0x1800311ea  xor     edi, edi
0x1800311ec  cmp     edi, [r14+18h]
0x1800311f0  jnb     loc_180031381
0x1800311f6  xorps   xmm0, xmm0
0x1800311f9  xor     eax, eax
0x1800311fb  movups  xmmword ptr [rbp+pvar], xmm0
0x1800311ff  mov     qword ptr [rbp+pvar+10h], rax
0x180031203  mov     r8, [r14+10h]
0x180031207  lea     edx, [rax+1Fh]; unsigned __int16
0x18003120a  mov     r8, [r8+rdi*8]; void *
0x18003120e  lea     rcx, [rbp+pvar]; this
0x180031212  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180031217  mov     ebx, eax
0x180031219  test    eax, eax
0x18003121b  js      loc_1800312D0
0x180031221  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180031225  lea     rcx, [rbp+var_20]; this
0x180031229  call    ?AppendUniqueElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendUniqueElement(tagPROPVARIANT const *)
0x18003122e  mov     ebx, eax
0x180031230  test    eax, eax
0x180031232  js      short loc_180031241
0x180031234  lea     rcx, [rbp+pvar]; pvar
0x180031238  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18003123d  inc     edi
0x18003123f  jmp     short loc_1800311EC
0x180031241  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031248  test    rcx, rcx
0x18003124b  jnz     short loc_18003128E
0x18003124d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031253  mov     rcx, rax
0x180031256  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003125d  test    rax, rax
0x180031260  jz      short loc_180031280
0x180031262  mov     rax, [rax]
0x180031265  mov     edx, 7F0h
0x18003126a  mov     rax, [rax+8]
0x18003126e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031273  test    eax, eax
0x180031275  jz      short loc_180031280
0x180031277  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003127e  jmp     short loc_18003128E
0x180031280  lea     rcx, qword_18006EB20; this
0x180031287  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003128e  cmp     byte ptr [rcx+8], 0
0x180031292  jz      short loc_1800312B9
0x180031294  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031299  cmp     [rax+7CCh], ebx
0x18003129f  jz      short loc_1800312B9
0x1800312a1  mov     r9d, ebx; int
0x1800312a4  mov     r8d, 0C2h; int
0x1800312aa  lea     rdx, aCflacmetadataw_4; "CFLACMetadataWriter::GetAllPropertyName"...
0x1800312b1  mov     rcx, rax; this
0x1800312b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800312b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800312be  cmp     al, 1
0x1800312c0  jb      loc_180031376
0x1800312c6  mov     edx, 14h
0x1800312cb  jmp     loc_180031356
0x1800312d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800312d7  test    rcx, rcx
0x1800312da  jnz     short loc_18003131D
0x1800312dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800312e2  mov     rcx, rax
0x1800312e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800312ec  test    rax, rax
0x1800312ef  jz      short loc_18003130F
0x1800312f1  mov     rax, [rax]
0x1800312f4  mov     edx, 7F0h
0x1800312f9  mov     rax, [rax+8]
0x1800312fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031302  test    eax, eax
0x180031304  jz      short loc_18003130F
0x180031306  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003130d  jmp     short loc_18003131D
0x18003130f  lea     rcx, qword_18006EB20; this
0x180031316  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003131d  cmp     byte ptr [rcx+8], 0
0x180031321  jz      short loc_180031348
0x180031323  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031328  cmp     [rax+7CCh], ebx
0x18003132e  jz      short loc_180031348
0x180031330  mov     r9d, ebx; int
0x180031333  mov     r8d, 0C1h; int
0x180031339  lea     rdx, aCflacmetadataw_4; "CFLACMetadataWriter::GetAllPropertyName"...
0x180031340  mov     rcx, rax; this
0x180031343  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031348  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003134d  cmp     al, 1
0x18003134f  jb      short loc_180031376
0x180031351  mov     edx, 13h
0x180031356  lea     r9, [r14-8]
0x18003135a  mov     [rsp+70h+var_50], ebx
0x18003135e  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180031365  mov     rcx, cs:WPP_GLOBAL_Control
0x18003136c  mov     rcx, [rcx+10h]
0x180031370  call    WPP_SF_qd
0x180031375  nop
0x180031376  lea     rcx, [rbp+pvar]; pvar
0x18003137a  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18003137f  jmp     short loc_180031398
0x180031381  movups  xmm0, xmmword ptr [rbp+var_20]
0x180031385  movups  xmmword ptr [rsi], xmm0
0x180031388  movsd   xmm1, qword ptr [rbp+var_20+10h]
0x18003138d  movsd   qword ptr [rsi+10h], xmm1
0x180031392  xor     eax, eax
0x180031394  mov     word ptr [rbp+var_20], ax
0x180031398  lea     rcx, [rbp+var_40]; this
0x18003139c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800313a1  nop
0x1800313a2  lea     rcx, [rbp+var_20]; pvar
0x1800313a6  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800313ab  mov     eax, ebx
0x1800313ad  mov     rcx, [rbp+var_8]
0x1800313b1  xor     rcx, rsp; StackCookie
0x1800313b4  call    __security_check_cookie
0x1800313b9  lea     r11, [rsp+70h+var_s0]
0x1800313be  mov     rbx, [r11+30h]
0x1800313c2  mov     rsi, [r11+38h]
0x1800313c6  mov     rsp, r11
0x1800313c9  pop     r14
0x1800313cb  pop     rdi
0x1800313cc  pop     rbp
0x1800313cd  retn
```
