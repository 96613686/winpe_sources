# CWebBrowser::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180030280`
- end: `0x180030435`
- name: `?Invoke@CWebBrowser@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `437`
- prototype: `__int64 __fastcall(CWebBrowser *__hidden this, int, const struct _GUID *, unsigned int, char, struct tagDISPPARAMS *, VARIANTARG *pvarg, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001284`
- `0x1800046c8`
- `0x180030280`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003030f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800303aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003030f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800303aa`
- `OLEAUT32!__imp_VariantInit` at `0x1800303e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800303e8`
- `USER32!PostMessageW` at `0x18003034b`
- `USER32!PostMessageW` at `0x18003034b`

## string_xrefs

- `0x1800302f5`: `[msdrm]:+Navigation2Complete: Finished Navigating to URL=%S\n`
- `0x180030351`: `[msdrm]:-Navigation2Complete: hr=0x%x\n`

## pseudocode

```c
__int64 __fastcall CWebBrowser::Invoke(
        CWebBrowser *this,
        int a2,
        const struct _GUID *a3,
        __int64 a4,
        char a5,
        struct tagDISPPARAMS *a6,
        VARIANTARG *pvarg)
{
  int v7; // edi
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  LONGLONG llVal; // rcx
  const WCHAR *v15; // rbp
  unsigned int v16; // ebx
  const WCHAR *v17; // rdx
  HWND v18; // rcx
  LONGLONG v19; // rcx
  const WCHAR *v20; // rbp
  unsigned int v21; // ebx
  const WCHAR *v22; // rdx

  v7 = 0;
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 103;
    if ( v10 )
    {
      v11 = v10 - 2;
      if ( v11 )
      {
        v12 = v11 - 144;
        if ( v12 )
        {
          v13 = v12 - 2;
          if ( v13 )
          {
            if ( v13 != 7 )
              v7 = -2147352573;
          }
          else if ( a6->cArgs )
          {
            llVal = a6->rgvarg->llVal;
            v15 = *(const WCHAR **)(llVal + 8);
            if ( v15 )
            {
              v16 = 0;
              _RTLTRACE("[msdrm]:+Navigation2Complete: Finished Navigating to URL=%S\n", *(const wchar_t **)(llVal + 8));
              v17 = (const WCHAR *)*((_QWORD *)this + 10);
              if ( v17 && !lstrcmpiW(v15, v17) )
                *((_DWORD *)this + 22) = 1;
              if ( *((_DWORD *)this + 22) )
              {
                _RTLTRACE("[msdrm]: Killing the browser");
                v18 = (HWND)*((_QWORD *)this + 3);
                if ( v18 )
                  PostMessageW(v18, 0x10u, 0, 0);
                else
                  v16 = -2147418113;
              }
            }
            else
            {
              v16 = -2147024809;
            }
            _RTLTRACE("[msdrm]:-Navigation2Complete: hr=0x%x\n", v16, a3);
          }
        }
        else if ( a6->cArgs > 5 )
        {
          v19 = a6->rgvarg[5].llVal;
          v20 = *(const WCHAR **)(v19 + 8);
          if ( v20 )
          {
            v21 = 0;
            _RTLTRACE("[msdrm]:+BeforeNavigation2: URL=%S\n", *(const wchar_t **)(v19 + 8));
            v22 = (const WCHAR *)*((_QWORD *)this + 10);
            if ( v22 && !lstrcmpiW(v20, v22) )
              *((_DWORD *)this + 22) = 1;
          }
          else
          {
            v21 = -2147024809;
          }
          _RTLTRACE("[msdrm]:-BeforeNavigation2: hr=0x%x\n", v21, a3);
        }
      }
    }
  }
  else if ( (a5 & 2) != 0 )
  {
    if ( pvarg )
    {
      if ( !*((_QWORD *)this + 8)
        || (VariantInit(pvarg),
            pvarg->vt = 9,
            pvarg->llVal = 0,
            v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, ULONG *))this + 8))(
                   *((_QWORD *)this + 8),
                   &IID_IDispatch,
                   (ULONG *)&pvarg->cyVal),
            v7 < 0)
        || !pvarg->llVal )
      {
        v7 = -2147467259;
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  operator delete(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180030280  push    rbx
0x180030282  push    rbp
0x180030283  push    rsi
0x180030284  push    rdi
0x180030285  sub     rsp, 28h
0x180030289  xor     edi, edi
0x18003028b  mov     rsi, rcx
0x18003028e  sub     edx, 1
0x180030291  jz      loc_1800303C4
0x180030297  sub     edx, 67h ; 'g'
0x18003029a  jz      loc_180030423
0x1800302a0  sub     edx, 2
0x1800302a3  jz      loc_180030423
0x1800302a9  sub     edx, 90h
0x1800302af  jz      loc_180030364
0x1800302b5  sub     edx, 2
0x1800302b8  jz      short loc_1800302CD
0x1800302ba  cmp     edx, 7
0x1800302bd  jz      loc_180030423
0x1800302c3  mov     edi, 80020003h
0x1800302c8  jmp     loc_180030423
0x1800302cd  mov     rax, [rsp+48h+arg_28]
0x1800302d2  cmp     [rax+10h], edi
0x1800302d5  jbe     loc_180030423
0x1800302db  mov     rax, [rax]
0x1800302de  mov     rcx, [rax+8]
0x1800302e2  mov     rbp, [rcx+8]
0x1800302e6  test    rbp, rbp
0x1800302e9  jnz     short loc_1800302F2
0x1800302eb  mov     ebx, 80070057h
0x1800302f0  jmp     short loc_180030351
0x1800302f2  mov     rdx, rbp
0x1800302f5  lea     rcx, aMsdrmNavigatio; "[msdrm]:+Navigation2Complete: Finished "...
0x1800302fc  xor     ebx, ebx
0x1800302fe  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180030303  mov     rdx, [rsi+50h]; lpString2
0x180030307  test    rdx, rdx
0x18003030a  jz      short loc_180030320
0x18003030c  mov     rcx, rbp; lpString1
0x18003030f  call    cs:__imp_lstrcmpiW
0x180030315  test    eax, eax
0x180030317  jnz     short loc_180030320
0x180030319  mov     dword ptr [rsi+58h], 1
0x180030320  cmp     [rsi+58h], ebx
0x180030323  jz      short loc_180030351
0x180030325  lea     rcx, aMsdrmKillingTh; "[msdrm]: Killing the browser"
0x18003032c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180030331  mov     rcx, [rsi+18h]; hWnd
0x180030335  test    rcx, rcx
0x180030338  jnz     short loc_180030341
0x18003033a  mov     ebx, 8000FFFFh
0x18003033f  jmp     short loc_180030351
0x180030341  xor     r9d, r9d; lParam
0x180030344  xor     r8d, r8d; wParam
0x180030347  lea     edx, [r9+10h]; Msg
0x18003034b  call    cs:__imp_PostMessageW
0x180030351  lea     rcx, aMsdrmNavigatio_0; "[msdrm]:-Navigation2Complete: hr=0x%x\n"
0x180030358  mov     edx, ebx
0x18003035a  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003035f  jmp     loc_180030423
0x180030364  mov     rax, [rsp+48h+arg_28]
0x180030369  cmp     dword ptr [rax+10h], 5
0x18003036d  jbe     loc_180030423
0x180030373  mov     rax, [rax]
0x180030376  mov     rcx, [rax+80h]
0x18003037d  mov     rbp, [rcx+8]
0x180030381  test    rbp, rbp
0x180030384  jnz     short loc_18003038D
0x180030386  mov     ebx, 80070057h
0x18003038b  jmp     short loc_1800303BB
0x18003038d  mov     rdx, rbp
0x180030390  lea     rcx, aMsdrmBeforenav; "[msdrm]:+BeforeNavigation2: URL=%S\n"
0x180030397  xor     ebx, ebx
0x180030399  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003039e  mov     rdx, [rsi+50h]; lpString2
0x1800303a2  test    rdx, rdx
0x1800303a5  jz      short loc_1800303BB
0x1800303a7  mov     rcx, rbp; lpString1
0x1800303aa  call    cs:__imp_lstrcmpiW
0x1800303b0  test    eax, eax
0x1800303b2  jnz     short loc_1800303BB
0x1800303b4  mov     dword ptr [rsi+58h], 1
0x1800303bb  lea     rcx, aMsdrmBeforenav_0; "[msdrm]:-BeforeNavigation2: hr=0x%x\n"
0x1800303c2  jmp     short loc_180030358
0x1800303c4  test    [rsp+48h+arg_20], 2
0x1800303c9  jz      short loc_180030423
0x1800303cb  mov     rbx, [rsp+48h+pvarg]
0x1800303d3  test    rbx, rbx
0x1800303d6  jnz     short loc_1800303DF
0x1800303d8  mov     edi, 80070057h
0x1800303dd  jmp     short loc_180030423
0x1800303df  cmp     [rcx+40h], rdi
0x1800303e3  jz      short loc_18003041E
0x1800303e5  mov     rcx, rbx; pvarg
0x1800303e8  call    cs:__imp_VariantInit
0x1800303ee  mov     word ptr [rbx], 9
0x1800303f3  lea     r8, [rbx+8]
0x1800303f7  mov     [rbx+8], rdi
0x1800303fb  lea     rdx, IID_IDispatch
0x180030402  mov     rcx, [rsi+40h]
0x180030406  mov     rax, [rcx]
0x180030409  mov     rax, [rax]
0x18003040c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030411  mov     edi, eax
0x180030413  test    eax, eax
0x180030415  js      short loc_18003041E
0x180030417  cmp     qword ptr [rbx+8], 0
0x18003041c  jnz     short loc_180030423
0x18003041e  mov     edi, 80004005h
0x180030423  xor     ecx, ecx; Block
0x180030425  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003042a  mov     eax, edi
0x18003042c  add     rsp, 28h
0x180030430  pop     rdi
0x180030431  pop     rsi
0x180030432  pop     rbp
0x180030433  pop     rbx
0x180030434  retn
```
