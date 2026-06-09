# CbsGetSsBinaryPathByShim

- ea: `0x1400251e4`
- end: `0x140025369`
- name: `CbsGetSsBinaryPathByShim`
- size: `389`
- prototype: `__int64 __fastcall(wchar_t *, Windows::AutoSsShim *this, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400253b0`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400074c0`
- `0x1400251e4`
- `0x1400258f0`
- `0x140025cb4`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400252a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400252a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400252b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400252b2`

## string_xrefs

- `0x140025256`: `Windows::AutoSsShim::GetFilePathLength`
- `0x140025264`: `m_pfnSssGetServicingStackFilePathLength(0, m_Cookie, BinaryName, CharLengthWithNull)`

## pseudocode

```c
__int64 __fastcall CbsGetSsBinaryPathByShim(wchar_t *a1, Windows::AutoSsShim *this, _QWORD *a3)
{
  __int64 v4; // rdx
  signed int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  SIZE_T v12; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v14; // rbx
  int FilePath; // eax
  unsigned int v16; // edi
  _WORD *v18; // [rsp+30h] [rbp-40h] BYREF
  const char *v19; // [rsp+38h] [rbp-38h] BYREF
  const char *v20; // [rsp+40h] [rbp-30h]
  __int64 v21; // [rsp+48h] [rbp-28h]
  const char *v22; // [rsp+50h] [rbp-20h]
  __int64 v23; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int64 v24; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v18 = 0;
  v4 = *((_QWORD *)this + 1);
  v24 = 0;
  LODWORD(v23) = 0;
  v7 = (*((__int64 (__fastcall **)(_QWORD, __int64, wchar_t *, unsigned __int64 *))this + 5))(0, v4, a1, &v24);
  if ( v7 < 0 )
  {
    v21 = 268;
    v19 = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v20 = "Windows::AutoSsShim::GetFilePathLength";
    v22 = "m_pfnSssGetServicingStackFilePathLength(0, m_Cookie, BinaryName, CharLengthWithNull)";
    v8 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           (unsigned int *)&v23,
           (__int64)&v19,
           v7);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = (unsigned int)v8;
      v11 = 130;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
        (const char *)v10);
      goto LABEL_13;
    }
  }
  v23 = 0;
  v12 = 2 * v24;
  if ( !is_mul_ok(v24, 2u) )
  {
    v9 = -2147024362;
    v11 = 133;
    goto LABEL_11;
  }
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 0, v12);
  v14 = v18;
  if ( !v18 )
  {
    v9 = -2147024882;
    v11 = 136;
LABEL_11:
    v10 = v9;
    goto LABEL_12;
  }
  v20 = (const char *)v12;
  *v18 = 0;
  v19 = 0;
  v21 = (__int64)v14;
  FilePath = Windows::AutoSsShim::GetFilePath(this, a1, (struct _LUNICODE_STRING *)&v19);
  v16 = FilePath;
  if ( FilePath >= 0 )
  {
    *a3 = v14;
    v9 = 0;
    v18 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)FilePath);
    v9 = v16;
  }
LABEL_13:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((PVOID *)&v18);
  return v9;
}

```

## disassembly

```asm
0x1400251e4  mov     [rsp-28h+arg_18], rbx
0x1400251e9  push    rbp
0x1400251ea  push    rsi
0x1400251eb  push    rdi
0x1400251ec  push    r14
0x1400251ee  push    r15
0x1400251f0  mov     rbp, rsp
0x1400251f3  sub     rsp, 70h
0x1400251f7  mov     rax, cs:__security_cookie
0x1400251fe  xor     rax, rsp
0x140025201  mov     [rbp+var_8], rax
0x140025205  mov     rsi, rdx
0x140025208  mov     [rbp+var_40], 0
0x140025210  mov     rdx, [rdx+8]
0x140025214  lea     r9, [rbp+var_10]
0x140025218  mov     r14, r8
0x14002521b  mov     [rbp+var_10], 0
0x140025223  mov     r15, rcx
0x140025226  mov     dword ptr [rbp+var_18], 0
0x14002522d  mov     rax, [rsi+28h]
0x140025231  mov     r8, rcx
0x140025234  xor     ecx, ecx
0x140025236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002523b  test    eax, eax
0x14002523d  jns     short loc_14002528B
0x14002523f  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x140025246  mov     [rbp+var_28], 10Ch
0x14002524e  mov     [rbp+var_38], rcx
0x140025252  lea     rdx, [rbp+var_38]
0x140025256  lea     rcx, aWindowsAutosss_3; "Windows::AutoSsShim::GetFilePathLength"
0x14002525d  mov     r8d, eax
0x140025260  mov     [rbp+var_30], rcx
0x140025264  lea     rcx, aMPfnsssgetserv_3; "m_pfnSssGetServicingStackFilePathLength"...
0x14002526b  mov     [rbp+var_20], rcx
0x14002526f  lea     rcx, [rbp+var_18]
0x140025273  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140025278  mov     ebx, eax
0x14002527a  test    eax, eax
0x14002527c  jns     short loc_14002528B
0x14002527e  mov     r9d, eax
0x140025281  mov     edx, 82h
0x140025286  jmp     loc_14002532E
0x14002528b  mov     eax, 2
0x140025290  mov     [rbp+var_18], 0
0x140025298  mul     [rbp+var_10]
0x14002529c  mov     rdi, rax
0x14002529f  test    rdx, rdx
0x1400252a2  jnz     short loc_140025321
0x1400252a4  call    cs:__imp_GetProcessHeap
0x1400252aa  mov     r8, rdi; dwBytes
0x1400252ad  xor     edx, edx; dwFlags
0x1400252af  mov     rcx, rax; hHeap
0x1400252b2  call    cs:__imp_HeapAlloc
0x1400252b8  mov     [rbp+var_40], rax
0x1400252bc  mov     rbx, rax
0x1400252bf  test    rax, rax
0x1400252c2  jnz     short loc_1400252D0
0x1400252c4  mov     ebx, 8007000Eh
0x1400252c9  mov     edx, 88h
0x1400252ce  jmp     short loc_14002532B
0x1400252d0  xor     eax, eax
0x1400252d2  mov     [rbp+var_30], rdi
0x1400252d6  lea     r8, [rbp+var_38]; struct _LUNICODE_STRING *
0x1400252da  mov     [rbx], ax
0x1400252dd  mov     rdx, r15; wchar_t *
0x1400252e0  mov     [rbp+var_38], rax
0x1400252e4  mov     rcx, rsi; this
0x1400252e7  mov     [rbp+var_28], rbx
0x1400252eb  call    ?GetFilePath@AutoSsShim@Windows@@QEAAJQEB_WAEAU_LUNICODE_STRING@@@Z; Windows::AutoSsShim::GetFilePath(wchar_t const * const,_LUNICODE_STRING &)
0x1400252f0  mov     edi, eax
0x1400252f2  test    eax, eax
0x1400252f4  jns     short loc_140025312
0x1400252f6  mov     rcx, [rbp+28h]; this
0x1400252fa  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025301  mov     r9d, eax; char *
0x140025304  mov     edx, 8Eh; void *
0x140025309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002530e  mov     ebx, edi
0x140025310  jmp     short loc_14002533E
0x140025312  mov     [r14], rbx
0x140025315  xor     ebx, ebx
0x140025317  mov     [rbp+var_40], 0
0x14002531f  jmp     short loc_14002533E
0x140025321  mov     ebx, 80070216h
0x140025326  mov     edx, 85h; void *
0x14002532b  mov     r9d, ebx; char *
0x14002532e  mov     rcx, [rbp+28h]; this
0x140025332  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002533e  lea     rcx, [rbp+var_40]
0x140025342  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025347  mov     eax, ebx
0x140025349  mov     rcx, [rbp+var_8]
0x14002534d  xor     rcx, rsp; StackCookie
0x140025350  call    __security_check_cookie
0x140025355  mov     rbx, [rsp+70h+arg_18]
0x14002535d  add     rsp, 70h
0x140025361  pop     r15
0x140025363  pop     r14
0x140025365  pop     rdi
0x140025366  pop     rsi
0x140025367  pop     rbp
0x140025368  retn
```
