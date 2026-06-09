# CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)

- ea: `0x180058270`
- end: `0x180058434`
- name: `?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180055328`
- `0x180058440`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180058270`
- `0x180058574`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005837c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005837c`

## string_xrefs

- `0x180058283`: `CMFPropHandlerBase::RemoveKey`
- `0x1800583d9`: `CMFPropHandlerBase::RemoveKey`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::RemoveKey(CMFPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  unsigned __int64 v4; // r9
  unsigned int v5; // r11d
  unsigned int v6; // esi
  unsigned int i; // ebx
  char *v8; // rdx
  char *v9; // r8
  int v10; // r10d
  unsigned int v11; // ecx
  __int64 v12; // rax
  int v13; // edi
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v18; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v18, "CMFPropHandlerBase::RemoveKey", 578);
  v5 = *((_DWORD *)this + 218);
  v6 = 0;
  for ( i = 0; i < v5; ++i )
  {
    v8 = 0;
    v9 = (char *)this + 424;
    v10 = -2147467259;
    while ( v9 )
    {
      v11 = *((_DWORD *)v9 + 2);
      if ( i >= v11 && i < v11 + 20 )
      {
        v4 = i - v11;
        if ( ((unsigned __int8)v9[(v4 >> 3) + 36]
            & *((_BYTE *)&CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks
              + (((_BYTE)i - (_BYTE)v11) & 7))) != 0 )
        {
          v10 = 0;
          v8 = &v9[20 * v4 + 40];
        }
        break;
      }
      v9 = (char *)*((_QWORD *)v9 + 55);
    }
    if ( v10 < 0 )
      v8 = 0;
    if ( v8 && a2->pid == *((_DWORD *)v8 + 4) )
    {
      v12 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v8;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v8 )
        v12 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)v8 + 1);
      if ( !v12 )
      {
        if ( i + 1 <= v5 )
        {
          v13 = 0;
          while ( (int)CTSparseBlock<unsigned long,_tagpropertykey,20,0>::RemoveValue((char *)this + 424, i) >= 0 )
          {
            --*((_DWORD *)this + 218);
            if ( ++v13 )
              goto LABEL_33;
          }
        }
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        v6 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v4);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::RemoveKey", 593, -2147418113);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
            this,
            -2147418113);
        break;
      }
    }
  }
LABEL_33:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return v6;
}

```

## disassembly

```asm
0x180058270  push    rbx
0x180058272  push    rbp
0x180058273  push    rsi
0x180058274  push    rdi
0x180058275  push    r14
0x180058277  push    r15
0x180058279  sub     rsp, 38h
0x18005827d  mov     rdi, rdx
0x180058280  mov     r14, rcx
0x180058283  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x18005828a  mov     r8d, 242h; int
0x180058290  lea     rcx, [rsp+68h+arg_0]; this
0x180058295  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005829a  mov     r11d, [r14+368h]
0x1800582a1  xor     esi, esi
0x1800582a3  xor     ebx, ebx
0x1800582a5  cmp     ebx, r11d
0x1800582a8  jnb     loc_18005841A
0x1800582ae  lea     rbp, [r14+1A8h]
0x1800582b5  xor     edx, edx
0x1800582b7  mov     r8, rbp
0x1800582ba  mov     r10d, 80004005h
0x1800582c0  test    r8, r8
0x1800582c3  jz      short loc_18005830F
0x1800582c5  mov     ecx, [r8+8]
0x1800582c9  cmp     ebx, ecx
0x1800582cb  jb      short loc_1800582D4
0x1800582cd  lea     eax, [rcx+14h]
0x1800582d0  cmp     ebx, eax
0x1800582d2  jb      short loc_1800582DD
0x1800582d4  mov     r8, [r8+1B8h]
0x1800582db  jmp     short loc_1800582C0
0x1800582dd  mov     eax, ebx
0x1800582df  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_tagpropertykey,20,0>::s_bSingleBitMasks
0x1800582e6  sub     eax, ecx
0x1800582e8  mov     r9d, eax
0x1800582eb  mov     ecx, r9d
0x1800582ee  shr     rax, 3
0x1800582f2  and     ecx, 7
0x1800582f5  mov     al, [rax+r8+24h]
0x1800582fa  test    [rcx+r15], al
0x1800582fe  jz      short loc_18005830F
0x180058300  lea     rax, [r9+2]
0x180058304  xor     r10d, r10d
0x180058307  lea     rax, [rax+rax*4]
0x18005830b  lea     rdx, [r8+rax*4]
0x18005830f  xor     eax, eax
0x180058311  test    r10d, r10d
0x180058314  cmovs   rdx, rax
0x180058318  test    rdx, rdx
0x18005831b  jz      short loc_18005833A
0x18005831d  mov     eax, [rdx+10h]
0x180058320  cmp     [rdi+10h], eax
0x180058323  jnz     short loc_18005833A
0x180058325  mov     rax, [rdi]
0x180058328  sub     rax, [rdx]
0x18005832b  jnz     short loc_180058335
0x18005832d  mov     rax, [rdi+8]
0x180058331  sub     rax, [rdx+8]
0x180058335  test    rax, rax
0x180058338  jz      short loc_180058341
0x18005833a  inc     ebx
0x18005833c  jmp     loc_1800582A5
0x180058341  lea     eax, [rbx+1]
0x180058344  cmp     eax, r11d
0x180058347  ja      short loc_18005836B
0x180058349  xor     edi, edi
0x18005834b  mov     edx, ebx
0x18005834d  mov     rcx, rbp
0x180058350  call    ?RemoveValue@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,_tagpropertykey,20,0>::RemoveValue(ulong)
0x180058355  test    eax, eax
0x180058357  js      short loc_18005836B
0x180058359  dec     dword ptr [rbp+1C0h]
0x18005835f  inc     edi
0x180058361  cmp     edi, 1
0x180058364  jb      short loc_18005834B
0x180058366  jmp     loc_18005841A
0x18005836b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058372  mov     esi, 8000FFFFh
0x180058377  test    rcx, rcx
0x18005837a  jnz     short loc_1800583C3
0x18005837c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058383  nop     dword ptr [rax+rax+00h]
0x180058388  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005838f  mov     rcx, rax
0x180058392  test    rax, rax
0x180058395  jz      short loc_1800583B5
0x180058397  mov     rax, [rax]
0x18005839a  mov     edx, 7F0h
0x18005839f  mov     rax, [rax+8]
0x1800583a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583a8  test    eax, eax
0x1800583aa  jz      short loc_1800583B5
0x1800583ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800583b3  jmp     short loc_1800583C3
0x1800583b5  lea     rcx, qword_1800DBF70; this
0x1800583bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800583c3  cmp     byte ptr [rcx+8], 0
0x1800583c7  jz      short loc_1800583EE
0x1800583c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800583ce  cmp     [rax+7CCh], esi
0x1800583d4  jz      short loc_1800583EE
0x1800583d6  mov     r9d, esi; int
0x1800583d9  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x1800583e0  mov     r8d, 251h; int
0x1800583e6  mov     rcx, rax; this
0x1800583e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800583ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800583f5  jb      short loc_18005841A
0x1800583f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583fe  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180058405  mov     edx, 32h ; '2'
0x18005840a  mov     [rsp+68h+var_48], esi
0x18005840e  mov     r9, r14
0x180058411  mov     rcx, [rcx+10h]
0x180058415  call    WPP_SF_qD
0x18005841a  lea     rcx, [rsp+68h+arg_0]; this
0x18005841f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180058424  mov     eax, esi
0x180058426  add     rsp, 38h
0x18005842a  pop     r15
0x18005842c  pop     r14
0x18005842e  pop     rdi
0x18005842f  pop     rsi
0x180058430  pop     rbp
0x180058431  pop     rbx
0x180058432  retn
```
