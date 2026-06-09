# CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(tagPROPVARIANT const &,tagPROPVARIANT const &,ushort const *,tagPROPVARIANT *)

- ea: `0x180054d2c`
- end: `0x180054ea8`
- name: `?ConvertGPSDoubleArrayIntoSingleDouble@CMFPropHandlerBase@@CAJAEBUtagPROPVARIANT@@0PEBGPEAU2@@Z`
- size: `380`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055990`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180054d2c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054d6f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054d6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054dea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054dea`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(
        const struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        const unsigned __int16 *a3,
        struct tagPROPVARIANT *a4)
{
  unsigned int v6; // ebx
  int v7; // esi
  double v8; // xmm1_8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v16; // [rsp+50h] [rbp+8h] BYREF

  if ( a1->vt == 31 && a2->vt == 4101 && a2->lVal == 3 )
  {
    v6 = 0;
    v7 = 1;
    if ( CompareStringOrdinal(a1->bstrVal, -1, a3, -1, 1) != 2 )
      v7 = -1;
    v8 = (*((double *)a2->bstrblobVal.pData + 2) / 60.0 + *((double *)a2->bstrblobVal.pData + 1)) / 60.0
       + *a2->cadbl.pElems;
    a4->vt = 5;
    a4->dblVal = v8 * (double)v7;
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v16,
      "CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble",
      936);
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875819 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble",
          936,
          -1072875819);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
        0,
        -1072875819);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  }
  return v6;
}

```

## disassembly

```asm
0x180054d2c  mov     [rsp+arg_8], rbx
0x180054d31  mov     [rsp+arg_10], rbp
0x180054d36  push    rsi
0x180054d37  push    rdi
0x180054d38  push    r14
0x180054d3a  sub     rsp, 30h
0x180054d3e  cmp     word ptr [rcx], 1Fh
0x180054d42  mov     r14, r9
0x180054d45  mov     rdi, rdx
0x180054d48  jnz     short loc_180054DC0
0x180054d4a  mov     eax, 1005h
0x180054d4f  cmp     [rdx], ax
0x180054d52  jnz     short loc_180054DC0
0x180054d54  cmp     dword ptr [rdx+8], 3
0x180054d58  jnz     short loc_180054DC0
0x180054d5a  mov     rcx, [rcx+8]; lpString1
0x180054d5e  or      ebp, 0FFFFFFFFh
0x180054d61  xor     ebx, ebx
0x180054d63  mov     r9d, ebp; cchCount2
0x180054d66  mov     edx, ebp; cchCount1
0x180054d68  lea     esi, [rbx+1]
0x180054d6b  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x180054d6f  call    cs:__imp_CompareStringOrdinal
0x180054d76  nop     dword ptr [rax+rax+00h]
0x180054d7b  cmp     eax, 2
0x180054d7e  mov     rax, [rdi+10h]
0x180054d82  cmovnz  esi, ebp
0x180054d85  movsd   xmm1, qword ptr [rax+10h]
0x180054d8a  divsd   xmm1, cs:__real@404e000000000000
0x180054d92  movd    xmm0, esi
0x180054d96  addsd   xmm1, qword ptr [rax+8]
0x180054d9b  cvtdq2pd xmm0, xmm0
0x180054d9f  divsd   xmm1, cs:__real@404e000000000000
0x180054da7  addsd   xmm1, qword ptr [rax]
0x180054dab  mov     word ptr [r14], 5
0x180054db1  mulsd   xmm1, xmm0
0x180054db5  movsd   qword ptr [r14+8], xmm1
0x180054dbb  jmp     loc_180054E92
0x180054dc0  mov     edi, 3A8h
0x180054dc5  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x180054dcc  mov     r8d, edi; int
0x180054dcf  lea     rcx, [rsp+48h+arg_0]; this
0x180054dd4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054dd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054de0  mov     ebx, 0C00D36D5h
0x180054de5  test    rcx, rcx
0x180054de8  jnz     short loc_180054E31
0x180054dea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054df1  nop     dword ptr [rax+rax+00h]
0x180054df6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054dfd  mov     rcx, rax
0x180054e00  test    rax, rax
0x180054e03  jz      short loc_180054E23
0x180054e05  mov     rax, [rax]
0x180054e08  mov     edx, 7F0h
0x180054e0d  mov     rax, [rax+8]
0x180054e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e16  test    eax, eax
0x180054e18  jz      short loc_180054E23
0x180054e1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e21  jmp     short loc_180054E31
0x180054e23  lea     rcx, qword_1800DBF70; this
0x180054e2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e31  cmp     byte ptr [rcx+8], 0
0x180054e35  jz      short loc_180054E59
0x180054e37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054e3c  cmp     [rax+7CCh], ebx
0x180054e42  jz      short loc_180054E59
0x180054e44  mov     r9d, ebx; int
0x180054e47  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x180054e4e  mov     r8d, edi; int
0x180054e51  mov     rcx, rax; this
0x180054e54  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054e59  mov     esi, 1
0x180054e5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180054e65  jb      short loc_180054E88
0x180054e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e6e  lea     edx, [rsi+46h]
0x180054e71  xor     r9d, r9d
0x180054e74  mov     [rsp+48h+bIgnoreCase], ebx
0x180054e78  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180054e7f  mov     rcx, [rcx+10h]
0x180054e83  call    WPP_SF_qD
0x180054e88  lea     rcx, [rsp+48h+arg_0]; this
0x180054e8d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054e92  mov     rbp, [rsp+48h+arg_10]
0x180054e97  mov     eax, ebx
0x180054e99  mov     rbx, [rsp+48h+arg_8]
0x180054e9e  add     rsp, 30h
0x180054ea2  pop     r14
0x180054ea4  pop     rdi
0x180054ea5  pop     rsi
0x180054ea6  retn
```
