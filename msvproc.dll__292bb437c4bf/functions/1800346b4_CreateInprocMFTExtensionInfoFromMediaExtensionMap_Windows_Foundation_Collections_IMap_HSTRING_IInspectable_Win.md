# CreateInprocMFTExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocMFTExtensionInfo &)

- ea: `0x1800346b4`
- end: `0x1800347c8`
- name: `?CreateInprocMFTExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocMFTExtensionInfo@@@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180018708`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800346b4`
- `0x1800347d0`
- `0x18003639c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034707`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034707`

## string_xrefs

- `0x1800346cc`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`
- `0x18003475e`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`

## pseudocode

```c
__int64 __fastcall CreateInprocMFTExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  int InprocExtensionInfoFromMediaExtensionMap; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+58h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
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
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return (unsigned int)InprocExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x1800346b4  mov     [rsp+arg_0], rbx
0x1800346b9  mov     [rsp+arg_8], rsi
0x1800346be  push    rdi
0x1800346bf  sub     rsp, 30h
0x1800346c3  mov     rsi, r8
0x1800346c6  mov     rbx, rdx
0x1800346c9  mov     rdi, rcx
0x1800346cc  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x1800346d3  mov     r8d, 43Fh; int
0x1800346d9  lea     rcx, [rsp+38h+arg_18]; this
0x1800346de  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800346e3  mov     r8, rsi
0x1800346e6  mov     rdx, rbx
0x1800346e9  mov     rcx, rdi
0x1800346ec  call    ?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z; CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)
0x1800346f1  mov     ebx, eax
0x1800346f3  test    eax, eax
0x1800346f5  jns     loc_1800347A1
0x1800346fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034702  test    rcx, rcx
0x180034705  jnz     short loc_180034748
0x180034707  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003470d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034714  mov     rcx, rax
0x180034717  test    rax, rax
0x18003471a  jz      short loc_18003473A
0x18003471c  mov     rax, [rax]
0x18003471f  mov     edx, 7F0h
0x180034724  mov     rax, [rax+8]
0x180034728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003472d  test    eax, eax
0x18003472f  jz      short loc_18003473A
0x180034731  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034738  jmp     short loc_180034748
0x18003473a  lea     rcx, qword_180153440; this
0x180034741  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034748  cmp     byte ptr [rcx+8], 0
0x18003474c  jz      short loc_180034773
0x18003474e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034753  cmp     [rax+7CCh], ebx
0x180034759  jz      short loc_180034773
0x18003475b  mov     r9d, ebx; int
0x18003475e  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x180034765  mov     r8d, 43Fh; int
0x18003476b  mov     rcx, rax; this
0x18003476e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034773  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003477a  jb      short loc_1800347AC
0x18003477c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034783  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18003478a  mov     edx, 8Eh
0x18003478f  mov     [rsp+38h+var_18], ebx
0x180034793  xor     r9d, r9d
0x180034796  mov     rcx, [rcx+10h]
0x18003479a  call    WPP_SF_qD
0x18003479f  jmp     short loc_1800347AC
0x1800347a1  cmp     byte ptr [rsi+21h], 0
0x1800347a5  jnz     short loc_1800347AC
0x1800347a7  bts     dword ptr [rsi+40h], 0Ah
0x1800347ac  lea     rcx, [rsp+38h+arg_18]; this
0x1800347b1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800347b6  mov     rsi, [rsp+38h+arg_8]
0x1800347bb  mov     eax, ebx
0x1800347bd  mov     rbx, [rsp+38h+arg_0]
0x1800347c2  add     rsp, 30h
0x1800347c6  pop     rdi
0x1800347c7  retn
```
