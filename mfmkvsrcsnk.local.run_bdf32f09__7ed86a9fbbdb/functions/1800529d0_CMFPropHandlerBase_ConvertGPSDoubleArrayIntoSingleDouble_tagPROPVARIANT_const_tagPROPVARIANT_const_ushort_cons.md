# CMFPropHandlerBase::ConvertGPSDoubleArrayIntoSingleDouble(tagPROPVARIANT const &,tagPROPVARIANT const &,ushort const *,tagPROPVARIANT *)

- ea: `0x1800529d0`
- end: `0x180052b3f`
- name: `?ConvertGPSDoubleArrayIntoSingleDouble@CMFPropHandlerBase@@CAJAEBUtagPROPVARIANT@@0PEBGPEAU2@@Z`
- size: `367`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800535e0`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800529d0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180052a13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180052a13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052a88`

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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
        0,
        -1072875819);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  }
  return v6;
}

```

## disassembly

```asm
0x1800529d0  mov     [rsp+arg_8], rbx
0x1800529d5  mov     [rsp+arg_10], rbp
0x1800529da  push    rsi
0x1800529db  push    rdi
0x1800529dc  push    r14
0x1800529de  sub     rsp, 30h
0x1800529e2  cmp     word ptr [rcx], 1Fh
0x1800529e6  mov     r14, r9
0x1800529e9  mov     rdi, rdx
0x1800529ec  jnz     short loc_180052A5E
0x1800529ee  mov     eax, 1005h
0x1800529f3  cmp     [rdx], ax
0x1800529f6  jnz     short loc_180052A5E
0x1800529f8  cmp     dword ptr [rdx+8], 3
0x1800529fc  jnz     short loc_180052A5E
0x1800529fe  mov     rcx, [rcx+8]; lpString1
0x180052a02  or      ebp, 0FFFFFFFFh
0x180052a05  xor     ebx, ebx
0x180052a07  mov     r9d, ebp; cchCount2
0x180052a0a  mov     edx, ebp; cchCount1
0x180052a0c  lea     esi, [rbx+1]
0x180052a0f  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x180052a13  call    cs:__imp_CompareStringOrdinal
0x180052a19  cmp     eax, 2
0x180052a1c  mov     rax, [rdi+10h]
0x180052a20  cmovnz  esi, ebp
0x180052a23  movsd   xmm1, qword ptr [rax+10h]
0x180052a28  divsd   xmm1, cs:__real@404e000000000000
0x180052a30  movd    xmm0, esi
0x180052a34  addsd   xmm1, qword ptr [rax+8]
0x180052a39  cvtdq2pd xmm0, xmm0
0x180052a3d  divsd   xmm1, cs:__real@404e000000000000
0x180052a45  addsd   xmm1, qword ptr [rax]
0x180052a49  mov     word ptr [r14], 5
0x180052a4f  mulsd   xmm1, xmm0
0x180052a53  movsd   qword ptr [r14+8], xmm1
0x180052a59  jmp     loc_180052B2A
0x180052a5e  mov     edi, 3A8h
0x180052a63  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x180052a6a  mov     r8d, edi; int
0x180052a6d  lea     rcx, [rsp+48h+arg_0]; this
0x180052a72  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052a77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a7e  mov     ebx, 0C00D36D5h
0x180052a83  test    rcx, rcx
0x180052a86  jnz     short loc_180052AC9
0x180052a88  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052a8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052a95  mov     rcx, rax
0x180052a98  test    rax, rax
0x180052a9b  jz      short loc_180052ABB
0x180052a9d  mov     rax, [rax]
0x180052aa0  mov     edx, 7F0h
0x180052aa5  mov     rax, [rax+8]
0x180052aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052aae  test    eax, eax
0x180052ab0  jz      short loc_180052ABB
0x180052ab2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ab9  jmp     short loc_180052AC9
0x180052abb  lea     rcx, qword_1800D6F70; this
0x180052ac2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ac9  cmp     byte ptr [rcx+8], 0
0x180052acd  jz      short loc_180052AF1
0x180052acf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052ad4  cmp     [rax+7CCh], ebx
0x180052ada  jz      short loc_180052AF1
0x180052adc  mov     r9d, ebx; int
0x180052adf  lea     rdx, aCmfprophandler_2; "CMFPropHandlerBase::ConvertGPSDoubleArr"...
0x180052ae6  mov     r8d, edi; int
0x180052ae9  mov     rcx, rax; this
0x180052aec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052af1  mov     esi, 1
0x180052af6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180052afd  jb      short loc_180052B20
0x180052aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b06  lea     edx, [rsi+46h]
0x180052b09  xor     r9d, r9d
0x180052b0c  mov     [rsp+48h+bIgnoreCase], ebx
0x180052b10  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180052b17  mov     rcx, [rcx+10h]
0x180052b1b  call    WPP_SF_qD
0x180052b20  lea     rcx, [rsp+48h+arg_0]; this
0x180052b25  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180052b2a  mov     rbp, [rsp+48h+arg_10]
0x180052b2f  mov     eax, ebx
0x180052b31  mov     rbx, [rsp+48h+arg_8]
0x180052b36  add     rsp, 30h
0x180052b3a  pop     r14
0x180052b3c  pop     rdi
0x180052b3d  pop     rsi
0x180052b3e  retn
```
