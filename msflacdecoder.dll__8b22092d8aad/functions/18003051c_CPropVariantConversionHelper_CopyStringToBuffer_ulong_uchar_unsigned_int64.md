# CPropVariantConversionHelper::CopyStringToBuffer(ulong,uchar *,unsigned __int64)

- ea: `0x18003051c`
- end: `0x1800309c9`
- name: `?CopyStringToBuffer@CPropVariantConversionHelper@@QEAAJKPEAE_K@Z`
- size: `1197`
- prototype: `__int64 __fastcall(CPropVariantConversionHelper *__hidden this, unsigned int, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180031ca4`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x1800300e0`
- `0x18003051c`
- `0x180031bdc`
- `0x180033570`
- `0x180034058`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003056e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030619`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800306d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003078c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003091b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003056e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030619`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800306d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003078c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003091b`

## string_xrefs

- `0x18003053b`: `CPropVariantConversionHelper::CopyStringToBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropVariantConversionHelper::CopyStringToBuffer(
        CPropVariantConversionHelper *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned __int64 a4)
{
  __int64 v6; // r14
  __int64 v8; // rdx
  int v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  CPropVariantConversionHelper *v14; // rcx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  _BYTE v36[72]; // [rsp+30h] [rbp-48h] BYREF

  v6 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v36,
    "CPropVariantConversionHelper::CopyStringToBuffer",
    1206);
  v9 = CPropVariantConversionHelper::CalcStringSizes(this);
  if ( v9 < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CPropVariantConversionHelper::CopyStringToBuffer",
          1206,
          v9);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 82;
LABEL_74:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids, this, v9);
      goto LABEL_75;
    }
    goto LABEL_75;
  }
  if ( (unsigned int)v6 >= *((_DWORD *)this + 2) )
  {
LABEL_62:
    v9 = -2147024809;
    goto LABEL_75;
  }
  v14 = *(CPropVariantConversionHelper **)(*((_QWORD *)this + 2) + 8 * v6);
  if ( a4 >= (unsigned __int64)v14 )
  {
    v18 = *(_QWORD *)this;
    if ( **(_WORD **)this == 31 )
    {
      v9 = CPropVariantConversionHelper::WriteUTF8String(
             v14,
             a3,
             a4,
             *(const unsigned __int16 **)(v18 + 8),
             (unsigned __int64)v14);
      if ( v9 < 0 )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v9 )
            CallStackContext::TraceFailure(v22, "CPropVariantConversionHelper::CopyStringToBuffer", 1220, v9);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v13 = 84;
          goto LABEL_74;
        }
      }
      goto LABEL_75;
    }
    switch ( *(_WORD *)v18 )
    {
      case 8:
        v9 = CPropVariantConversionHelper::WriteUTF8String(
               v14,
               a3,
               a4,
               *(const unsigned __int16 **)(v18 + 8),
               (unsigned __int64)v14);
        if ( v9 < 0 )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != v9 )
              CallStackContext::TraceFailure(v26, "CPropVariantConversionHelper::CopyStringToBuffer", 1224, v9);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 85;
            goto LABEL_74;
          }
        }
        goto LABEL_75;
      case 0x101F:
      case 0x1008:
        v9 = CPropVariantConversionHelper::WriteUTF8String(
               v14,
               a3,
               a4,
               *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 8 * v6),
               (unsigned __int64)v14);
        if ( v9 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v9 )
              CallStackContext::TraceFailure(v34, "CPropVariantConversionHelper::CopyStringToBuffer", 1228, v9);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 86;
            goto LABEL_74;
          }
        }
        goto LABEL_75;
      case 0x13:
        v9 = StringCchPrintfA((char *)a3, a4, "%u", *(_DWORD *)(v18 + 8));
        if ( v9 < 0 )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != v9 )
              CallStackContext::TraceFailure(v30, "CPropVariantConversionHelper::CopyStringToBuffer", 1232, v9);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 87;
            goto LABEL_74;
          }
        }
        goto LABEL_75;
    }
    goto LABEL_62;
  }
  v9 = -2147024774;
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != -2147024774 )
      CallStackContext::TraceFailure(v17, "CPropVariantConversionHelper::CopyStringToBuffer", 1215, -2147024774);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v13 = 83;
    goto LABEL_74;
  }
LABEL_75:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003051c  push    rbx
0x18003051e  push    rbp
0x18003051f  push    rsi
0x180030520  push    rdi
0x180030521  push    r12
0x180030523  push    r14
0x180030525  sub     rsp, 48h
0x180030529  mov     rsi, r9
0x18003052c  mov     rbp, r8
0x18003052f  mov     r14d, edx
0x180030532  mov     rdi, rcx
0x180030535  mov     r8d, 4B6h; int
0x18003053b  lea     r12, aCpropvariantco_0; "CPropVariantConversionHelper::CopyStrin"...
0x180030542  mov     rdx, r12; char *
0x180030545  lea     rcx, [rsp+78h+var_48]; this
0x18003054a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003054f  nop
0x180030550  mov     rcx, rdi; this
0x180030553  call    ?CalcStringSizes@CPropVariantConversionHelper@@IEAAJXZ; CPropVariantConversionHelper::CalcStringSizes(void)
0x180030558  mov     ebx, eax
0x18003055a  test    eax, eax
0x18003055c  jns     loc_1800305ED
0x180030562  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030569  test    rcx, rcx
0x18003056c  jnz     short loc_1800305AF
0x18003056e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030574  mov     rcx, rax
0x180030577  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003057e  test    rax, rax
0x180030581  jz      short loc_1800305A1
0x180030583  mov     rax, [rax]
0x180030586  mov     edx, 7F0h
0x18003058b  mov     rax, [rax+8]
0x18003058f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030594  test    eax, eax
0x180030596  jz      short loc_1800305A1
0x180030598  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003059f  jmp     short loc_1800305AF
0x1800305a1  lea     rcx, qword_18006EB20; this
0x1800305a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800305af  cmp     byte ptr [rcx+8], 0
0x1800305b3  jz      short loc_1800305D6
0x1800305b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800305ba  cmp     [rax+7CCh], ebx
0x1800305c0  jz      short loc_1800305D6
0x1800305c2  mov     r9d, ebx; int
0x1800305c5  mov     r8d, 4B6h; int
0x1800305cb  mov     rdx, r12; char *
0x1800305ce  mov     rcx, rax; this
0x1800305d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800305d6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800305db  cmp     al, 1
0x1800305dd  jb      loc_1800309B0
0x1800305e3  mov     edx, 52h ; 'R'
0x1800305e8  jmp     loc_180030991
0x1800305ed  cmp     r14d, [rdi+8]
0x1800305f1  jnb     loc_1800308E3
0x1800305f7  mov     rax, [rdi+10h]
0x1800305fb  mov     rcx, [rax+r14*8]; this
0x1800305ff  cmp     rsi, rcx
0x180030602  jnb     loc_180030698
0x180030608  mov     ebx, 8007007Ah
0x18003060d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030614  test    rcx, rcx
0x180030617  jnz     short loc_18003065A
0x180030619  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003061f  mov     rcx, rax
0x180030622  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030629  test    rax, rax
0x18003062c  jz      short loc_18003064C
0x18003062e  mov     rax, [rax]
0x180030631  mov     edx, 7F0h
0x180030636  mov     rax, [rax+8]
0x18003063a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003063f  test    eax, eax
0x180030641  jz      short loc_18003064C
0x180030643  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003064a  jmp     short loc_18003065A
0x18003064c  lea     rcx, qword_18006EB20; this
0x180030653  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003065a  cmp     byte ptr [rcx+8], 0
0x18003065e  jz      short loc_180030681
0x180030660  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030665  cmp     [rax+7CCh], ebx
0x18003066b  jz      short loc_180030681
0x18003066d  mov     r9d, ebx; int
0x180030670  mov     r8d, 4BFh; int
0x180030676  mov     rdx, r12; char *
0x180030679  mov     rcx, rax; this
0x18003067c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030681  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030686  cmp     al, 1
0x180030688  jb      loc_1800309B0
0x18003068e  mov     edx, 53h ; 'S'
0x180030693  jmp     loc_180030991
0x180030698  mov     r9, [rdi]
0x18003069b  mov     eax, 1Fh
0x1800306a0  cmp     ax, [r9]
0x1800306a4  jnz     loc_180030753
0x1800306aa  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800306af  mov     r9, [r9+8]; unsigned __int16 *
0x1800306b3  mov     r8, rsi; unsigned __int64
0x1800306b6  mov     rdx, rbp; unsigned __int8 *
0x1800306b9  call    ?WriteUTF8String@CPropVariantConversionHelper@@IEAAJPEAE_KPEBG1@Z; CPropVariantConversionHelper::WriteUTF8String(uchar *,unsigned __int64,ushort const *,unsigned __int64)
0x1800306be  mov     ebx, eax
0x1800306c0  test    eax, eax
0x1800306c2  jns     loc_1800309B0
0x1800306c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800306cf  test    rcx, rcx
0x1800306d2  jnz     short loc_180030715
0x1800306d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800306da  mov     rcx, rax
0x1800306dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800306e4  test    rax, rax
0x1800306e7  jz      short loc_180030707
0x1800306e9  mov     rax, [rax]
0x1800306ec  mov     edx, 7F0h
0x1800306f1  mov     rax, [rax+8]
0x1800306f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306fa  test    eax, eax
0x1800306fc  jz      short loc_180030707
0x1800306fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030705  jmp     short loc_180030715
0x180030707  lea     rcx, qword_18006EB20; this
0x18003070e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030715  cmp     byte ptr [rcx+8], 0
0x180030719  jz      short loc_18003073C
0x18003071b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030720  cmp     [rax+7CCh], ebx
0x180030726  jz      short loc_18003073C
0x180030728  mov     r9d, ebx; int
0x18003072b  mov     r8d, 4C4h; int
0x180030731  mov     rdx, r12; char *
0x180030734  mov     rcx, rax; this
0x180030737  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003073c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030741  cmp     al, 1
0x180030743  jb      loc_1800309B0
0x180030749  mov     edx, 54h ; 'T'
0x18003074e  jmp     loc_180030991
0x180030753  mov     eax, 8
0x180030758  cmp     ax, [r9]
0x18003075c  jnz     loc_18003080B
0x180030762  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180030767  mov     r9, [r9+8]; unsigned __int16 *
0x18003076b  mov     r8, rsi; unsigned __int64
0x18003076e  mov     rdx, rbp; unsigned __int8 *
0x180030771  call    ?WriteUTF8String@CPropVariantConversionHelper@@IEAAJPEAE_KPEBG1@Z; CPropVariantConversionHelper::WriteUTF8String(uchar *,unsigned __int64,ushort const *,unsigned __int64)
0x180030776  mov     ebx, eax
0x180030778  test    eax, eax
0x18003077a  jns     loc_1800309B0
0x180030780  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030787  test    rcx, rcx
0x18003078a  jnz     short loc_1800307CD
0x18003078c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030792  mov     rcx, rax
0x180030795  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003079c  test    rax, rax
0x18003079f  jz      short loc_1800307BF
0x1800307a1  mov     rax, [rax]
0x1800307a4  mov     edx, 7F0h
0x1800307a9  mov     rax, [rax+8]
0x1800307ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b2  test    eax, eax
0x1800307b4  jz      short loc_1800307BF
0x1800307b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307bd  jmp     short loc_1800307CD
0x1800307bf  lea     rcx, qword_18006EB20; this
0x1800307c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307cd  cmp     byte ptr [rcx+8], 0
0x1800307d1  jz      short loc_1800307F4
0x1800307d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800307d8  cmp     [rax+7CCh], ebx
0x1800307de  jz      short loc_1800307F4
0x1800307e0  mov     r9d, ebx; int
0x1800307e3  mov     r8d, 4C8h; int
0x1800307e9  mov     rdx, r12; char *
0x1800307ec  mov     rcx, rax; this
0x1800307ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800307f4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800307f9  cmp     al, 1
0x1800307fb  jb      loc_1800309B0
0x180030801  mov     edx, 55h ; 'U'
0x180030806  jmp     loc_180030991
0x18003080b  mov     eax, 101Fh
0x180030810  cmp     ax, [r9]
0x180030814  jz      loc_1800308ED
0x18003081a  mov     eax, 1008h
0x18003081f  cmp     ax, [r9]
0x180030823  jz      loc_1800308ED
0x180030829  mov     eax, 13h
0x18003082e  cmp     ax, [r9]
0x180030832  jnz     loc_1800308E3
0x180030838  mov     r9d, [r9+8]
0x18003083c  lea     r8, aU_0; "%u"
0x180030843  mov     rdx, rsi; unsigned __int64
0x180030846  mov     rcx, rbp; char *
0x180030849  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18003084e  mov     ebx, eax
0x180030850  test    eax, eax
0x180030852  jns     loc_1800309B0
0x180030858  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003085f  test    rcx, rcx
0x180030862  jnz     short loc_1800308A5
0x180030864  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003086a  mov     rcx, rax
0x18003086d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030874  test    rax, rax
0x180030877  jz      short loc_180030897
0x180030879  mov     rax, [rax]
0x18003087c  mov     edx, 7F0h
0x180030881  mov     rax, [rax+8]
0x180030885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003088a  test    eax, eax
0x18003088c  jz      short loc_180030897
0x18003088e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030895  jmp     short loc_1800308A5
0x180030897  lea     rcx, qword_18006EB20; this
0x18003089e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800308a5  cmp     byte ptr [rcx+8], 0
0x1800308a9  jz      short loc_1800308CC
0x1800308ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800308b0  cmp     [rax+7CCh], ebx
0x1800308b6  jz      short loc_1800308CC
0x1800308b8  mov     r9d, ebx; int
0x1800308bb  mov     r8d, 4D0h; int
0x1800308c1  mov     rdx, r12; char *
0x1800308c4  mov     rcx, rax; this
0x1800308c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800308cc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800308d1  cmp     al, 1
0x1800308d3  jb      loc_1800309B0
0x1800308d9  mov     edx, 57h ; 'W'
0x1800308de  jmp     loc_180030991
0x1800308e3  mov     ebx, 80070057h
0x1800308e8  jmp     loc_1800309B0
0x1800308ed  mov     r9, [rdi+18h]
0x1800308f1  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800308f6  mov     r9, [r9+r14*8]; unsigned __int16 *
0x1800308fa  mov     r8, rsi; unsigned __int64
0x1800308fd  mov     rdx, rbp; unsigned __int8 *
0x180030900  call    ?WriteUTF8String@CPropVariantConversionHelper@@IEAAJPEAE_KPEBG1@Z; CPropVariantConversionHelper::WriteUTF8String(uchar *,unsigned __int64,ushort const *,unsigned __int64)
0x180030905  mov     ebx, eax
0x180030907  test    eax, eax
0x180030909  jns     loc_1800309B0
0x18003090f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030916  test    rcx, rcx
0x180030919  jnz     short loc_18003095C
0x18003091b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030921  mov     rcx, rax
0x180030924  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003092b  test    rax, rax
0x18003092e  jz      short loc_18003094E
0x180030930  mov     rax, [rax]
0x180030933  mov     edx, 7F0h
0x180030938  mov     rax, [rax+8]
0x18003093c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030941  test    eax, eax
0x180030943  jz      short loc_18003094E
0x180030945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003094c  jmp     short loc_18003095C
0x18003094e  lea     rcx, qword_18006EB20; this
0x180030955  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003095c  cmp     byte ptr [rcx+8], 0
0x180030960  jz      short loc_180030983
0x180030962  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030967  cmp     [rax+7CCh], ebx
0x18003096d  jz      short loc_180030983
0x18003096f  mov     r9d, ebx; int
0x180030972  mov     r8d, 4CCh; int
0x180030978  mov     rdx, r12; char *
0x18003097b  mov     rcx, rax; this
0x18003097e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030983  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030988  cmp     al, 1
0x18003098a  jb      short loc_1800309B0
0x18003098c  mov     edx, 56h ; 'V'
0x180030991  mov     rcx, cs:WPP_GLOBAL_Control
0x180030998  mov     dword ptr [rsp+78h+var_58], ebx
0x18003099c  mov     r9, rdi
0x18003099f  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x1800309a6  mov     rcx, [rcx+10h]
0x1800309aa  call    WPP_SF_qd
0x1800309af  nop
0x1800309b0  lea     rcx, [rsp+78h+var_48]; this
0x1800309b5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800309ba  mov     eax, ebx
0x1800309bc  add     rsp, 48h
0x1800309c0  pop     r14
0x1800309c2  pop     r12
0x1800309c4  pop     rdi
0x1800309c5  pop     rsi
0x1800309c6  pop     rbp
0x1800309c7  pop     rbx
0x1800309c8  retn
```
