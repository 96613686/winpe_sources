# CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)

- ea: `0x180055dcc`
- end: `0x180055f89`
- name: `?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180052fa0`
- `0x180055f90`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180055dcc`
- `0x1800560c0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055ed8`

## string_xrefs

- `0x180055ddf`: `CMFPropHandlerBase::RemoveKey`
- `0x180055f2f`: `CMFPropHandlerBase::RemoveKey`

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
            v14 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180055dcc  push    rbx
0x180055dce  push    rbp
0x180055dcf  push    rsi
0x180055dd0  push    rdi
0x180055dd1  push    r14
0x180055dd3  push    r15
0x180055dd5  sub     rsp, 38h
0x180055dd9  mov     rdi, rdx
0x180055ddc  mov     r14, rcx
0x180055ddf  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x180055de6  mov     r8d, 242h; int
0x180055dec  lea     rcx, [rsp+68h+arg_0]; this
0x180055df1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055df6  mov     r11d, [r14+368h]
0x180055dfd  xor     esi, esi
0x180055dff  xor     ebx, ebx
0x180055e01  cmp     ebx, r11d
0x180055e04  jnb     loc_180055F70
0x180055e0a  lea     rbp, [r14+1A8h]
0x180055e11  xor     edx, edx
0x180055e13  mov     r8, rbp
0x180055e16  mov     r10d, 80004005h
0x180055e1c  test    r8, r8
0x180055e1f  jz      short loc_180055E6B
0x180055e21  mov     ecx, [r8+8]
0x180055e25  cmp     ebx, ecx
0x180055e27  jb      short loc_180055E30
0x180055e29  lea     eax, [rcx+14h]
0x180055e2c  cmp     ebx, eax
0x180055e2e  jb      short loc_180055E39
0x180055e30  mov     r8, [r8+1B8h]
0x180055e37  jmp     short loc_180055E1C
0x180055e39  mov     eax, ebx
0x180055e3b  lea     r15, ?s_bSingleBitMasks@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_tagpropertykey,20,0>::s_bSingleBitMasks
0x180055e42  sub     eax, ecx
0x180055e44  mov     r9d, eax
0x180055e47  mov     ecx, r9d
0x180055e4a  shr     rax, 3
0x180055e4e  and     ecx, 7
0x180055e51  mov     al, [rax+r8+24h]
0x180055e56  test    [rcx+r15], al
0x180055e5a  jz      short loc_180055E6B
0x180055e5c  lea     rax, [r9+2]
0x180055e60  xor     r10d, r10d
0x180055e63  lea     rax, [rax+rax*4]
0x180055e67  lea     rdx, [r8+rax*4]
0x180055e6b  xor     eax, eax
0x180055e6d  test    r10d, r10d
0x180055e70  cmovs   rdx, rax
0x180055e74  test    rdx, rdx
0x180055e77  jz      short loc_180055E96
0x180055e79  mov     eax, [rdx+10h]
0x180055e7c  cmp     [rdi+10h], eax
0x180055e7f  jnz     short loc_180055E96
0x180055e81  mov     rax, [rdi]
0x180055e84  sub     rax, [rdx]
0x180055e87  jnz     short loc_180055E91
0x180055e89  mov     rax, [rdi+8]
0x180055e8d  sub     rax, [rdx+8]
0x180055e91  test    rax, rax
0x180055e94  jz      short loc_180055E9D
0x180055e96  inc     ebx
0x180055e98  jmp     loc_180055E01
0x180055e9d  lea     eax, [rbx+1]
0x180055ea0  cmp     eax, r11d
0x180055ea3  ja      short loc_180055EC7
0x180055ea5  xor     edi, edi
0x180055ea7  mov     edx, ebx
0x180055ea9  mov     rcx, rbp
0x180055eac  call    ?RemoveValue@?$CTSparseBlock@KU_tagpropertykey@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,_tagpropertykey,20,0>::RemoveValue(ulong)
0x180055eb1  test    eax, eax
0x180055eb3  js      short loc_180055EC7
0x180055eb5  dec     dword ptr [rbp+1C0h]
0x180055ebb  inc     edi
0x180055ebd  cmp     edi, 1
0x180055ec0  jb      short loc_180055EA7
0x180055ec2  jmp     loc_180055F70
0x180055ec7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055ece  mov     esi, 8000FFFFh
0x180055ed3  test    rcx, rcx
0x180055ed6  jnz     short loc_180055F19
0x180055ed8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180055ede  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055ee5  mov     rcx, rax
0x180055ee8  test    rax, rax
0x180055eeb  jz      short loc_180055F0B
0x180055eed  mov     rax, [rax]
0x180055ef0  mov     edx, 7F0h
0x180055ef5  mov     rax, [rax+8]
0x180055ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055efe  test    eax, eax
0x180055f00  jz      short loc_180055F0B
0x180055f02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055f09  jmp     short loc_180055F19
0x180055f0b  lea     rcx, qword_1800D6F70; this
0x180055f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055f19  cmp     byte ptr [rcx+8], 0
0x180055f1d  jz      short loc_180055F44
0x180055f1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180055f24  cmp     [rax+7CCh], esi
0x180055f2a  jz      short loc_180055F44
0x180055f2c  mov     r9d, esi; int
0x180055f2f  lea     rdx, aCmfprophandler_16; "CMFPropHandlerBase::RemoveKey"
0x180055f36  mov     r8d, 251h; int
0x180055f3c  mov     rcx, rax; this
0x180055f3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180055f44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055f4b  jb      short loc_180055F70
0x180055f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f54  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180055f5b  mov     edx, 32h ; '2'
0x180055f60  mov     [rsp+68h+var_48], esi
0x180055f64  mov     r9, r14
0x180055f67  mov     rcx, [rcx+10h]
0x180055f6b  call    WPP_SF_qD
0x180055f70  lea     rcx, [rsp+68h+arg_0]; this
0x180055f75  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180055f7a  mov     eax, esi
0x180055f7c  add     rsp, 38h
0x180055f80  pop     r15
0x180055f82  pop     r14
0x180055f84  pop     rdi
0x180055f85  pop     rsi
0x180055f86  pop     rbp
0x180055f87  pop     rbx
0x180055f88  retn
```
