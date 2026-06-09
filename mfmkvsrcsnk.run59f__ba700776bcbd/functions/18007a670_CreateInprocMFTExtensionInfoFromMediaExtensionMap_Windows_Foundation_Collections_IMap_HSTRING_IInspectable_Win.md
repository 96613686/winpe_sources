# CreateInprocMFTExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocMFTExtensionInfo &)

- ea: `0x18007a670`
- end: `0x18007a78b`
- name: `?CreateInprocMFTExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocMFTExtensionInfo@@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800789cc`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18007a0e4`
- `0x18007a670`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a6c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a6c3`

## string_xrefs

- `0x18007a688`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`
- `0x18007a720`: `CreateInprocMFTExtensionInfoFromMediaExtensionMap`

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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        InprocExtensionInfoFromMediaExtensionMap);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)InprocExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x18007a670  mov     [rsp+arg_0], rbx
0x18007a675  mov     [rsp+arg_8], rsi
0x18007a67a  push    rdi
0x18007a67b  sub     rsp, 30h
0x18007a67f  mov     rsi, r8
0x18007a682  mov     rbx, rdx
0x18007a685  mov     rdi, rcx
0x18007a688  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x18007a68f  mov     r8d, 43Fh; int
0x18007a695  lea     rcx, [rsp+38h+arg_18]; this
0x18007a69a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a69f  mov     r8, rsi
0x18007a6a2  mov     rdx, rbx
0x18007a6a5  mov     rcx, rdi
0x18007a6a8  call    ?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z; CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)
0x18007a6ad  mov     ebx, eax
0x18007a6af  test    eax, eax
0x18007a6b1  jns     loc_18007A763
0x18007a6b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6be  test    rcx, rcx
0x18007a6c1  jnz     short loc_18007A70A
0x18007a6c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a6ca  nop     dword ptr [rax+rax+00h]
0x18007a6cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6d6  mov     rcx, rax
0x18007a6d9  test    rax, rax
0x18007a6dc  jz      short loc_18007A6FC
0x18007a6de  mov     rax, [rax]
0x18007a6e1  mov     edx, 7F0h
0x18007a6e6  mov     rax, [rax+8]
0x18007a6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6ef  test    eax, eax
0x18007a6f1  jz      short loc_18007A6FC
0x18007a6f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6fa  jmp     short loc_18007A70A
0x18007a6fc  lea     rcx, qword_1800DBF70; this
0x18007a703  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a70a  cmp     byte ptr [rcx+8], 0
0x18007a70e  jz      short loc_18007A735
0x18007a710  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a715  cmp     [rax+7CCh], ebx
0x18007a71b  jz      short loc_18007A735
0x18007a71d  mov     r9d, ebx; int
0x18007a720  lea     rdx, aCreateinprocmf; "CreateInprocMFTExtensionInfoFromMediaEx"...
0x18007a727  mov     r8d, 43Fh; int
0x18007a72d  mov     rcx, rax; this
0x18007a730  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a735  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a73c  jb      short loc_18007A76E
0x18007a73e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a745  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007a74c  mov     edx, 8Eh
0x18007a751  mov     [rsp+38h+var_18], ebx
0x18007a755  xor     r9d, r9d
0x18007a758  mov     rcx, [rcx+10h]
0x18007a75c  call    WPP_SF_qD
0x18007a761  jmp     short loc_18007A76E
0x18007a763  cmp     byte ptr [rsi+21h], 0
0x18007a767  jnz     short loc_18007A76E
0x18007a769  bts     dword ptr [rsi+40h], 0Ah
0x18007a76e  lea     rcx, [rsp+38h+arg_18]; this
0x18007a773  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007a778  mov     rsi, [rsp+38h+arg_8]
0x18007a77d  mov     eax, ebx
0x18007a77f  mov     rbx, [rsp+38h+arg_0]
0x18007a784  add     rsp, 30h
0x18007a788  pop     rdi
0x18007a789  retn
```
