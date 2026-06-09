# CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)

- ea: `0x18003e770`
- end: `0x18003e92d`
- name: `?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003ba10`
- `0x18003e940`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003e770`
- `0x18003ea70`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e87c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e87c`

## string_xrefs

- `0x18003e783`: `CMFPropHandlerBase::RemoveKey`
- `0x18003e8d3`: `CMFPropHandlerBase::RemoveKey`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::RemoveKey(CMFPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  unsigned int v4; // r11d
  unsigned int v5; // esi
  unsigned int i; // ebx
  char *v7; // rdx
  char *v8; // r8
  int v9; // r10d
  unsigned int v10; // ecx
  __int64 v11; // rax
  int v12; // edi
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v17; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v17, "CMFPropHandlerBase::RemoveKey", 578);
  v4 = *((_DWORD *)this + 218);
  v5 = 0;
  for ( i = 0; i < v4; ++i )
  {
    v7 = 0;
    v8 = (char *)this + 424;
    v9 = -2147467259;
    while ( v8 )
    {
      v10 = *((_DWORD *)v8 + 2);
      if ( i >= v10 && i < v10 + 20 )
      {
        if ( ((unsigned __int8)v8[((unsigned __int64)(i - v10) >> 3) + 36]
            & CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks[((_BYTE)i - (_BYTE)v10) & 7]) != 0 )
        {
          v9 = 0;
          v7 = &v8[20 * (i - v10) + 40];
        }
        break;
      }
      v8 = (char *)*((_QWORD *)v8 + 55);
    }
    if ( v9 < 0 )
      v7 = 0;
    if ( v7 && a2->pid == *((_DWORD *)v7 + 4) )
    {
      v11 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v7;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v7 )
        v11 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)v7 + 1);
      if ( !v11 )
      {
        if ( i + 1 <= v4 )
        {
          v12 = 0;
          while ( (int)CTSparseBlock<unsigned long,_tagpropertykey,20,0>::RemoveValue((char *)this + 424, i) >= 0 )
          {
            --*((_DWORD *)this + 218);
            if ( ++v12 )
              goto LABEL_33;
          }
        }
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        v5 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::RemoveKey", 593, -2147418113);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
            this,
            -2147418113);
        break;
      }
    }
  }
LABEL_33:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return v5;
}

```

## disassembly

```asm
0x18003e770  push    rbx
0x18003e772  push    rbp
0x18003e773  push    rsi
0x18003e774  push    rdi
0x18003e775  push    r14
0x18003e777  push    r15
0x18003e779  sub     rsp, 38h
0x18003e77d  mov     rdi, rdx
0x18003e780  mov     r14, rcx
0x18003e783  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x18003e78a  mov     r8d, 242h; int
0x18003e790  lea     rcx, [rsp+68h+arg_0]; this
0x18003e795  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003e79a  mov     r11d, [r14+368h]
0x18003e7a1  xor     esi, esi
0x18003e7a3  xor     ebx, ebx
0x18003e7a5  cmp     ebx, r11d
0x18003e7a8  jnb     loc_18003E914
0x18003e7ae  lea     rbp, [r14+1A8h]
0x18003e7b5  xor     edx, edx
0x18003e7b7  mov     r8, rbp
0x18003e7ba  mov     r10d, 80004005h
0x18003e7c0  test    r8, r8
0x18003e7c3  jz      short loc_18003E80F
0x18003e7c5  mov     ecx, [r8+8]
0x18003e7c9  cmp     ebx, ecx
0x18003e7cb  jb      short loc_18003E7D4
0x18003e7cd  lea     eax, [rcx+14h]
0x18003e7d0  cmp     ebx, eax
0x18003e7d2  jb      short loc_18003E7DD
0x18003e7d4  mov     r8, [r8+1B8h]
0x18003e7db  jmp     short loc_18003E7C0
0x18003e7dd  mov     eax, ebx
0x18003e7df  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_tagpropertykey,20,0>::s_bSingleBitMasks
0x18003e7e6  sub     eax, ecx
0x18003e7e8  mov     r9d, eax
0x18003e7eb  mov     ecx, r9d
0x18003e7ee  shr     rax, 3
0x18003e7f2  and     ecx, 7
0x18003e7f5  mov     al, [rax+r8+24h]
0x18003e7fa  test    [rcx+r15], al
0x18003e7fe  jz      short loc_18003E80F
0x18003e800  lea     rax, [r9+2]
0x18003e804  xor     r10d, r10d
0x18003e807  lea     rax, [rax+rax*4]
0x18003e80b  lea     rdx, [r8+rax*4]
0x18003e80f  xor     eax, eax
0x18003e811  test    r10d, r10d
0x18003e814  cmovs   rdx, rax
0x18003e818  test    rdx, rdx
0x18003e81b  jz      short loc_18003E83A
0x18003e81d  mov     eax, [rdx+10h]
0x18003e820  cmp     [rdi+10h], eax
0x18003e823  jnz     short loc_18003E83A
0x18003e825  mov     rax, [rdi]
0x18003e828  sub     rax, [rdx]
0x18003e82b  jnz     short loc_18003E835
0x18003e82d  mov     rax, [rdi+8]
0x18003e831  sub     rax, [rdx+8]
0x18003e835  test    rax, rax
0x18003e838  jz      short loc_18003E841
0x18003e83a  inc     ebx
0x18003e83c  jmp     loc_18003E7A5
0x18003e841  lea     eax, [rbx+1]
0x18003e844  cmp     eax, r11d
0x18003e847  ja      short loc_18003E86B
0x18003e849  xor     edi, edi
0x18003e84b  mov     edx, ebx
0x18003e84d  mov     rcx, rbp
0x18003e850  call    ?RemoveValue@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,_tagpropertykey,20,0>::RemoveValue(ulong)
0x18003e855  test    eax, eax
0x18003e857  js      short loc_18003E86B
0x18003e859  dec     dword ptr [rbp+1C0h]
0x18003e85f  inc     edi
0x18003e861  cmp     edi, 1
0x18003e864  jb      short loc_18003E84B
0x18003e866  jmp     loc_18003E914
0x18003e86b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e872  mov     esi, 8000FFFFh
0x18003e877  test    rcx, rcx
0x18003e87a  jnz     short loc_18003E8BD
0x18003e87c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e882  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e889  mov     rcx, rax
0x18003e88c  test    rax, rax
0x18003e88f  jz      short loc_18003E8AF
0x18003e891  mov     rax, [rax]
0x18003e894  mov     edx, 7F0h
0x18003e899  mov     rax, [rax+8]
0x18003e89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8a2  test    eax, eax
0x18003e8a4  jz      short loc_18003E8AF
0x18003e8a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8ad  jmp     short loc_18003E8BD
0x18003e8af  lea     rcx, qword_18006EB20; this
0x18003e8b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8bd  cmp     byte ptr [rcx+8], 0
0x18003e8c1  jz      short loc_18003E8E8
0x18003e8c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e8c8  cmp     [rax+7CCh], esi
0x18003e8ce  jz      short loc_18003E8E8
0x18003e8d0  mov     r9d, esi; int
0x18003e8d3  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x18003e8da  mov     r8d, 251h; int
0x18003e8e0  mov     rcx, rax; this
0x18003e8e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e8e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003e8ed  cmp     al, 1
0x18003e8ef  jb      short loc_18003E914
0x18003e8f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8f8  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003e8ff  mov     edx, 32h ; '2'
0x18003e904  mov     [rsp+68h+var_48], esi
0x18003e908  mov     r9, r14
0x18003e90b  mov     rcx, [rcx+10h]
0x18003e90f  call    WPP_SF_qd
0x18003e914  lea     rcx, [rsp+68h+arg_0]; this
0x18003e919  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003e91e  mov     eax, esi
0x18003e920  add     rsp, 38h
0x18003e924  pop     r15
0x18003e926  pop     r14
0x18003e928  pop     rdi
0x18003e929  pop     rsi
0x18003e92a  pop     rbp
0x18003e92b  pop     rbx
0x18003e92c  retn
```
