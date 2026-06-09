# CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(tagPROPVARIANT const &,tagPROPVARIANT const &,ushort const *,tagPROPVARIANT *)

- ea: `0x18003b440`
- end: `0x18003b5b0`
- name: `?ConvertGPSDoubleArrayIntoSingleDouble@CMFPropHandlerBase@@CAJAEBUtagPROPVARIANT@@0PEBGPEAU2@@Z`
- size: `368`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003b440`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003b483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003b483`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b4f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b4f8`

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
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+50h] [rbp+8h] BYREF

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
      (CallStackScopeTrace *)&v14,
      "CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble",
      936);
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875819 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble",
          936,
          -1072875819);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
        0,
        -1072875819);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  }
  return v6;
}

```

## disassembly

```asm
0x18003b440  mov     [rsp+arg_8], rbx
0x18003b445  mov     [rsp+arg_10], rbp
0x18003b44a  push    rsi
0x18003b44b  push    rdi
0x18003b44c  push    r14
0x18003b44e  sub     rsp, 30h
0x18003b452  cmp     word ptr [rcx], 1Fh
0x18003b456  mov     r14, r9
0x18003b459  mov     rdi, rdx
0x18003b45c  jnz     short loc_18003B4CE
0x18003b45e  mov     eax, 1005h
0x18003b463  cmp     [rdx], ax
0x18003b466  jnz     short loc_18003B4CE
0x18003b468  cmp     dword ptr [rdx+8], 3
0x18003b46c  jnz     short loc_18003B4CE
0x18003b46e  mov     rcx, [rcx+8]; lpString1
0x18003b472  or      ebp, 0FFFFFFFFh
0x18003b475  xor     ebx, ebx
0x18003b477  mov     r9d, ebp; cchCount2
0x18003b47a  mov     edx, ebp; cchCount1
0x18003b47c  lea     esi, [rbx+1]
0x18003b47f  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x18003b483  call    cs:__imp_CompareStringOrdinal
0x18003b489  cmp     eax, 2
0x18003b48c  mov     rax, [rdi+10h]
0x18003b490  cmovnz  esi, ebp
0x18003b493  movsd   xmm1, qword ptr [rax+10h]
0x18003b498  divsd   xmm1, cs:__real@404e000000000000
0x18003b4a0  movd    xmm0, esi
0x18003b4a4  addsd   xmm1, qword ptr [rax+8]
0x18003b4a9  cvtdq2pd xmm0, xmm0
0x18003b4ad  divsd   xmm1, cs:__real@404e000000000000
0x18003b4b5  addsd   xmm1, qword ptr [rax]
0x18003b4b9  mov     word ptr [r14], 5
0x18003b4bf  mulsd   xmm1, xmm0
0x18003b4c3  movsd   qword ptr [r14+8], xmm1
0x18003b4c9  jmp     loc_18003B59B
0x18003b4ce  mov     edi, 3A8h
0x18003b4d3  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x18003b4da  mov     r8d, edi; int
0x18003b4dd  lea     rcx, [rsp+48h+arg_0]; this
0x18003b4e2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b4e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b4ee  mov     ebx, 0C00D36D5h
0x18003b4f3  test    rcx, rcx
0x18003b4f6  jnz     short loc_18003B539
0x18003b4f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b4fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b505  mov     rcx, rax
0x18003b508  test    rax, rax
0x18003b50b  jz      short loc_18003B52B
0x18003b50d  mov     rax, [rax]
0x18003b510  mov     edx, 7F0h
0x18003b515  mov     rax, [rax+8]
0x18003b519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b51e  test    eax, eax
0x18003b520  jz      short loc_18003B52B
0x18003b522  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b529  jmp     short loc_18003B539
0x18003b52b  lea     rcx, qword_18006EB20; this
0x18003b532  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b539  cmp     byte ptr [rcx+8], 0
0x18003b53d  jz      short loc_18003B561
0x18003b53f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b544  cmp     [rax+7CCh], ebx
0x18003b54a  jz      short loc_18003B561
0x18003b54c  mov     r9d, ebx; int
0x18003b54f  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x18003b556  mov     r8d, edi; int
0x18003b559  mov     rcx, rax; this
0x18003b55c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b561  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b566  mov     esi, 1
0x18003b56b  cmp     al, sil
0x18003b56e  jb      short loc_18003B591
0x18003b570  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b577  lea     edx, [rsi+46h]
0x18003b57a  xor     r9d, r9d
0x18003b57d  mov     [rsp+48h+bIgnoreCase], ebx
0x18003b581  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003b588  mov     rcx, [rcx+10h]
0x18003b58c  call    WPP_SF_qd
0x18003b591  lea     rcx, [rsp+48h+arg_0]; this
0x18003b596  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b59b  mov     rbp, [rsp+48h+arg_10]
0x18003b5a0  mov     eax, ebx
0x18003b5a2  mov     rbx, [rsp+48h+arg_8]
0x18003b5a7  add     rsp, 30h
0x18003b5ab  pop     r14
0x18003b5ad  pop     rdi
0x18003b5ae  pop     rsi
0x18003b5af  retn
```
