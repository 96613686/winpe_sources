# CreateInprocMFTExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocMFTExtensionInfo &)

- ea: `0x1800770c8`
- end: `0x1800771dc`
- name: `?CreateInprocMFTExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocMFTExtensionInfo@@@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18007559c`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180076bb0`
- `0x1800770c8`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007711b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007711b`

## string_xrefs

- `0x1800770e0`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`
- `0x180077172`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`

## pseudocode

```c
__int64 __fastcall CreateInprocMFTExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  int InprocExtensionInfoFromMediaExtensionMap; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+58h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v14,
    "CreateInprocMFTExtensionInfoFromMediaExtensionMap",
    1087);
  InprocExtensionInfoFromMediaExtensionMap = CreateInprocExtensionInfoFromMediaExtensionMap(a1, a2, a3);
  if ( InprocExtensionInfoFromMediaExtensionMap >= 0 )
  {
    if ( !*(_BYTE *)(a3 + 33) )
      *(_DWORD *)(a3 + 64) |= 0x400u;
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != InprocExtensionInfoFromMediaExtensionMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateInprocMFTExtensionInfoFromMediaExtensionMap",
          1087,
          InprocExtensionInfoFromMediaExtensionMap);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        InprocExtensionInfoFromMediaExtensionMap);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)InprocExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x1800770c8  mov     [rsp+arg_0], rbx
0x1800770cd  mov     [rsp+arg_8], rsi
0x1800770d2  push    rdi
0x1800770d3  sub     rsp, 30h
0x1800770d7  mov     rsi, r8
0x1800770da  mov     rbx, rdx
0x1800770dd  mov     rdi, rcx
0x1800770e0  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x1800770e7  mov     r8d, 43Fh; int
0x1800770ed  lea     rcx, [rsp+38h+arg_18]; this
0x1800770f2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800770f7  mov     r8, rsi
0x1800770fa  mov     rdx, rbx
0x1800770fd  mov     rcx, rdi
0x180077100  call    ?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z; CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)
0x180077105  mov     ebx, eax
0x180077107  test    eax, eax
0x180077109  jns     loc_1800771B5
0x18007710f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077116  test    rcx, rcx
0x180077119  jnz     short loc_18007715C
0x18007711b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077121  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077128  mov     rcx, rax
0x18007712b  test    rax, rax
0x18007712e  jz      short loc_18007714E
0x180077130  mov     rax, [rax]
0x180077133  mov     edx, 7F0h
0x180077138  mov     rax, [rax+8]
0x18007713c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077141  test    eax, eax
0x180077143  jz      short loc_18007714E
0x180077145  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007714c  jmp     short loc_18007715C
0x18007714e  lea     rcx, qword_1800D6F70; this
0x180077155  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007715c  cmp     byte ptr [rcx+8], 0
0x180077160  jz      short loc_180077187
0x180077162  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077167  cmp     [rax+7CCh], ebx
0x18007716d  jz      short loc_180077187
0x18007716f  mov     r9d, ebx; int
0x180077172  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x180077179  mov     r8d, 43Fh; int
0x18007717f  mov     rcx, rax; this
0x180077182  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077187  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007718e  jb      short loc_1800771C0
0x180077190  mov     rcx, cs:WPP_GLOBAL_Control
0x180077197  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007719e  mov     edx, 8Eh
0x1800771a3  mov     [rsp+38h+var_18], ebx
0x1800771a7  xor     r9d, r9d
0x1800771aa  mov     rcx, [rcx+10h]
0x1800771ae  call    WPP_SF_qD
0x1800771b3  jmp     short loc_1800771C0
0x1800771b5  cmp     byte ptr [rsi+21h], 0
0x1800771b9  jnz     short loc_1800771C0
0x1800771bb  bts     dword ptr [rsi+40h], 0Ah
0x1800771c0  lea     rcx, [rsp+38h+arg_18]; this
0x1800771c5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800771ca  mov     rsi, [rsp+38h+arg_8]
0x1800771cf  mov     eax, ebx
0x1800771d1  mov     rbx, [rsp+38h+arg_0]
0x1800771d6  add     rsp, 30h
0x1800771da  pop     rdi
0x1800771db  retn
```
