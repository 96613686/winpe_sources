# CFontCollectionBuilder::_GetFamilyStatus(ulong *)

- ea: `0x18000e704`
- end: `0x18000e917`
- name: `?_GetFamilyStatus@CFontCollectionBuilder@@AEAAXPEAK@Z`
- size: `531`
- prototype: `void __fastcall(CFontCollectionBuilder *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000fc40`

## callees

- `0x180008aec`
- `0x180008eac`
- `0x18000a794`
- `0x18000ae20`
- `0x18000e704`
- `0x18000f518`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e88e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e88e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e880`
- `fms!FmsGetFilteredFontList` at `0x18000e799`
- `fms!FmsGetFilteredFontList` at `0x18000e7fc`
- `fms!FmsGetFilteredFontList` at `0x18000e799`
- `fms!FmsGetFilteredFontList` at `0x18000e7fc`
- `fms!FmsGetFontProperty` at `0x18000e83d`
- `fms!FmsGetFontProperty` at `0x18000e83d`

## string_xrefs

- `0x18000e76d`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e7ac`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e84e`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e8a6`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
void __fastcall CFontCollectionBuilder::_GetFamilyStatus(CFontCollectionBuilder *this, unsigned int *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  int v6; // r15d
  int FilteredFontList; // eax
  signed int v8; // ebx
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v11; // rax
  unsigned int *v12; // r12
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rcx
  int FontProperty; // eax
  HANDLE v18; // rax
  int *v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  int v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    "_GetFamilyStatus");
  v23[0] = &FontFldrTraceLoggingTelemetry::_GetFamilyStatus::`vftable';
  FontFldrTraceLoggingTelemetry::_GetFamilyStatus::StartActivity((FontFldrTraceLoggingTelemetry::_GetFamilyStatus *)v23);
  if ( !a2 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80070057LL,
      (int)v19);
  v4 = *(_QWORD *)this;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  FilteredFontList = FmsGetFilteredFontList(v4, &v20, 0);
  v8 = FilteredFontList;
  if ( FilteredFontList < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x477,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)FilteredFontList,
      (int)v19);
    goto LABEL_18;
  }
  v9 = 4LL * v20;
  ProcessHeap = GetProcessHeap();
  v11 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v9);
  v12 = v11;
  if ( !v11 )
  {
    v8 = -2147024882;
    goto LABEL_18;
  }
  v13 = FmsGetFilteredFontList(*(_QWORD *)this, &v20, v11);
  v8 = v13;
  if ( v20 && v13 >= 0 )
  {
    v14 = 0;
    do
    {
      v15 = v12[v14];
      v16 = *(_QWORD *)this;
      v19 = &v21;
      v21 = 0;
      v22 = 4;
      FontProperty = FmsGetFontProperty(v16, v15, 26, &v22);
      if ( FontProperty >= 0 )
      {
        if ( v21 )
          v5 = 1;
        else
          v6 = 1;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x482,
          (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
          (const char *)(unsigned int)FontProperty,
          (int)&v21);
      }
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < v20 );
  }
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v12);
  if ( v8 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)v8,
      (int)v19);
    if ( v8 < 0 )
      goto LABEL_22;
  }
  if ( v6 )
    *a2 = (v5 != 0) + 1;
  else
    *a2 = 0;
LABEL_22:
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v23, v8);
  FontFldrTraceLoggingTelemetry::_GetFamilyStatus::~_GetFamilyStatus((FontFldrTraceLoggingTelemetry::_GetFamilyStatus *)v23);
}

```

## disassembly

```asm
0x18000e704  mov     [rsp-8+arg_10], rbx
0x18000e709  push    rbp
0x18000e70a  push    rsi
0x18000e70b  push    rdi
0x18000e70c  push    r12
0x18000e70e  push    r13
0x18000e710  push    r14
0x18000e712  push    r15
0x18000e714  lea     rbp, [rsp-0A0h]
0x18000e71c  sub     rsp, 1A0h
0x18000e723  mov     rax, cs:__security_cookie
0x18000e72a  xor     rax, rsp
0x18000e72d  mov     [rbp+0D0h+var_40], rax
0x18000e734  mov     r14, rdx
0x18000e737  mov     r13, rcx
0x18000e73a  lea     rdx, aGetfamilystatu; "_GetFamilyStatus"
0x18000e741  lea     rcx, [rsp+1D0h+var_190]
0x18000e746  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e74b  lea     rax, ??_7_GetFamilyStatus@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_GetFamilyStatus::`vftable'
0x18000e752  lea     rcx, [rsp+1D0h+var_190]; this
0x18000e757  mov     [rsp+1D0h+var_190], rax
0x18000e75c  call    ?StartActivity@_GetFamilyStatus@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_GetFamilyStatus::StartActivity(void)
0x18000e761  test    r14, r14
0x18000e764  jnz     short loc_18000E784
0x18000e766  mov     rcx, [rbp+0D8h]; this
0x18000e76d  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e774  mov     r9d, 80070057h; char *
0x18000e77a  mov     edx, 46Fh; void *
0x18000e77f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e784  mov     rcx, [r13+0]
0x18000e788  lea     rdx, [rsp+1D0h+var_1A0]
0x18000e78d  xor     edi, edi
0x18000e78f  xor     r8d, r8d
0x18000e792  mov     [rsp+1D0h+var_1A0], edi
0x18000e796  xor     r15d, r15d
0x18000e799  call    cs:__imp_FmsGetFilteredFontList
0x18000e79f  mov     ebx, eax
0x18000e7a1  test    eax, eax
0x18000e7a3  jns     short loc_18000E7C5
0x18000e7a5  mov     rcx, [rbp+0D8h]; this
0x18000e7ac  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e7b3  mov     r9d, eax; char *
0x18000e7b6  mov     edx, 477h; void *
0x18000e7bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e7c0  jmp     loc_18000E89F
0x18000e7c5  mov     ebx, [rsp+1D0h+var_1A0]
0x18000e7c9  shl     rbx, 2
0x18000e7cd  call    cs:__imp_GetProcessHeap
0x18000e7d3  mov     r8, rbx; dwBytes
0x18000e7d6  mov     edx, 8; dwFlags
0x18000e7db  mov     rcx, rax; hHeap
0x18000e7de  call    cs:__imp_HeapAlloc
0x18000e7e4  mov     r12, rax
0x18000e7e7  test    rax, rax
0x18000e7ea  jz      loc_18000E89A
0x18000e7f0  mov     rcx, [r13+0]
0x18000e7f4  lea     rdx, [rsp+1D0h+var_1A0]
0x18000e7f9  mov     r8, rax
0x18000e7fc  call    cs:__imp_FmsGetFilteredFontList
0x18000e802  mov     ebx, eax
0x18000e804  cmp     [rsp+1D0h+var_1A0], edi
0x18000e808  jbe     short loc_18000E880
0x18000e80a  test    eax, eax
0x18000e80c  js      short loc_18000E880
0x18000e80e  xor     esi, esi
0x18000e810  mov     edx, [r12+rsi*4]
0x18000e814  lea     rax, [rsp+1D0h+var_19C]
0x18000e819  mov     rcx, [r13+0]
0x18000e81d  lea     r9, [rsp+1D0h+var_198]
0x18000e822  mov     r8d, 1Ah
0x18000e828  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18000e82d  mov     [rsp+1D0h+var_19C], 0
0x18000e835  mov     [rsp+1D0h+var_198], 4
0x18000e83d  call    cs:__imp_FmsGetFontProperty
0x18000e843  test    eax, eax
0x18000e845  jns     short loc_18000E864
0x18000e847  mov     rcx, [rbp+0D8h]; this
0x18000e84e  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e855  mov     r9d, eax; char *
0x18000e858  mov     edx, 482h; void *
0x18000e85d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e862  jmp     short loc_18000E878
0x18000e864  cmp     [rsp+1D0h+var_19C], 0
0x18000e869  jz      short loc_18000E872
0x18000e86b  mov     edi, 1
0x18000e870  jmp     short loc_18000E878
0x18000e872  mov     r15d, 1
0x18000e878  inc     esi
0x18000e87a  cmp     esi, [rsp+1D0h+var_1A0]
0x18000e87e  jb      short loc_18000E810
0x18000e880  call    cs:__imp_GetProcessHeap
0x18000e886  mov     r8, r12; lpMem
0x18000e889  xor     edx, edx; dwFlags
0x18000e88b  mov     rcx, rax; hHeap
0x18000e88e  call    cs:__imp_HeapFree
0x18000e894  test    ebx, ebx
0x18000e896  jns     short loc_18000E8BE
0x18000e898  jmp     short loc_18000E89F
0x18000e89a  mov     ebx, 8007000Eh
0x18000e89f  mov     rcx, [rbp+0D8h]; this
0x18000e8a6  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e8ad  mov     r9d, ebx; char *
0x18000e8b0  mov     edx, 493h; void *
0x18000e8b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e8ba  test    ebx, ebx
0x18000e8bc  js      short loc_18000E8D7
0x18000e8be  test    r15d, r15d
0x18000e8c1  jz      short loc_18000E8D0
0x18000e8c3  neg     edi
0x18000e8c5  sbb     eax, eax
0x18000e8c7  neg     eax
0x18000e8c9  inc     eax
0x18000e8cb  mov     [r14], eax
0x18000e8ce  jmp     short loc_18000E8D7
0x18000e8d0  mov     dword ptr [r14], 0
0x18000e8d7  mov     edx, ebx
0x18000e8d9  lea     rcx, [rsp+1D0h+var_190]
0x18000e8de  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e8e3  lea     rcx, [rsp+1D0h+var_190]; this
0x18000e8e8  call    ??1_GetFamilyStatus@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_GetFamilyStatus::~_GetFamilyStatus(void)
0x18000e8ed  mov     rcx, [rbp+0D0h+var_40]
0x18000e8f4  xor     rcx, rsp; StackCookie
0x18000e8f7  call    __security_check_cookie
0x18000e8fc  mov     rbx, [rsp+1D0h+arg_10]
0x18000e904  add     rsp, 1A0h
0x18000e90b  pop     r15
0x18000e90d  pop     r14
0x18000e90f  pop     r13
0x18000e911  pop     r12
0x18000e913  pop     rdi
0x18000e914  pop     rsi
0x18000e915  pop     rbp
0x18000e916  retn
```
