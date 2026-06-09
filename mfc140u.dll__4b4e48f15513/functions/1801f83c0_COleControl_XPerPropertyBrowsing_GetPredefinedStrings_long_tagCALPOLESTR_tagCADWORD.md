# COleControl::XPerPropertyBrowsing::GetPredefinedStrings(long,tagCALPOLESTR *,tagCADWORD *)

- ea: `0x1801f83c0`
- end: `0x1801f8653`
- name: `?GetPredefinedStrings@XPerPropertyBrowsing@COleControl@@UEAAJJPEAUtagCALPOLESTR@@PEAUtagCADWORD@@@Z`
- size: `659`
- prototype: `HRESULT __fastcall(COleControl::XPerPropertyBrowsing *this, int dispid, tagCALPOLESTR *lpcaStringsOut, tagCADWORD *lpcaCookiesOut)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180139050`
- `0x1801dd990`
- `0x1801f83c0`
- `0x180231d10`
- `0x180231d70`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801f85bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801f85bf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801f84f1`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801f84f1`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801f853e`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1801f853e`
- `ole32!CoTaskMemAlloc` at `0x1801f8482`
- `ole32!CoTaskMemAlloc` at `0x1801f8494`
- `ole32!CoTaskMemAlloc` at `0x1801f8526`
- `ole32!CoTaskMemAlloc` at `0x1801f8482`
- `ole32!CoTaskMemAlloc` at `0x1801f8494`
- `ole32!CoTaskMemAlloc` at `0x1801f8526`
- `ole32!CoTaskMemFree` at `0x1801f84a7`
- `ole32!CoTaskMemFree` at `0x1801f85e8`
- `ole32!CoTaskMemFree` at `0x1801f85f8`
- `ole32!CoTaskMemFree` at `0x1801f8602`
- `ole32!CoTaskMemFree` at `0x1801f84a7`
- `ole32!CoTaskMemFree` at `0x1801f85e8`
- `ole32!CoTaskMemFree` at `0x1801f85f8`
- `ole32!CoTaskMemFree` at `0x1801f8602`

## pseudocode

```c
__int64 __fastcall COleControl::XPerPropertyBrowsing::GetPredefinedStrings(
        COleControl::XPerPropertyBrowsing *this,
        unsigned int dispid,
        tagCALPOLESTR *lpcaStringsOut,
        tagCADWORD *lpcaCookiesOut)
{
  COleControl::XPerPropertyBrowsing *v4; // rbx
  HRESULT (__fastcall *GetPredefinedValue)(IPerPropertyBrowsing *, int, unsigned int, tagVARIANT *); // rax
  signed int m_nSize; // esi
  wchar_t **v10; // rax
  unsigned int *v11; // rax
  unsigned int v12; // ebx
  signed int v13; // r15d
  __int64 v14; // rbx
  wchar_t *m_pszData; // r12
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  wchar_t *v18; // r13
  wchar_t *v19; // rcx
  errno_t v20; // eax
  __int64 i; // rbx
  AFX_MAINTAIN_STATE2 _ctlState; // [rsp+30h] [rbp-39h] BYREF
  CDWordArray cookieArray; // [rsp+40h] [rbp-29h] BYREF
  CStringArray stringArray; // [rsp+68h] [rbp-1h] BYREF
  HRESULT v26; // [rsp+D0h] [rbp+67h]
  rsize_t SizeInWords; // [rsp+E0h] [rbp+77h]

  v4 = this - 86;
  AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(&_ctlState, (AFX_MODULE_STATE *)this[-79].__vftable);
  if ( lpcaStringsOut && lpcaCookiesOut )
  {
    memset(&stringArray.m_pData, 0, 32);
    stringArray.__vftable = (CStringArray_vtbl *)CStringArray::`vftable';
    GetPredefinedValue = v4->__vftable[19].GetPredefinedValue;
    cookieArray.__vftable = (CDWordArray_vtbl *)CDWordArray::`vftable';
    memset(&cookieArray.m_pData, 0, 32);
    v26 = GetPredefinedValue(v4, dispid, (unsigned int)&stringArray, (tagVARIANT *)&cookieArray);
    if ( v26 )
    {
      m_nSize = stringArray.m_nSize;
      if ( (unsigned int)(LODWORD(stringArray.m_nSize) - 1) > 0x1FFFFFFE )
        goto LABEL_8;
      v10 = (wchar_t **)CoTaskMemAlloc(8LL * LODWORD(stringArray.m_nSize));
      lpcaStringsOut->pElems = v10;
      if ( !v10 )
        goto LABEL_8;
      v11 = (unsigned int *)CoTaskMemAlloc(8LL * (unsigned int)m_nSize);
      lpcaCookiesOut->pElems = v11;
      if ( !v11 )
      {
        CoTaskMemFree(lpcaStringsOut->pElems);
LABEL_8:
        v12 = -2147024882;
LABEL_24:
        cookieArray.__vftable = (CDWordArray_vtbl *)CDWordArray::`vftable';
        free(cookieArray.m_pData);
        CStringArray::~CStringArray(&stringArray);
        goto LABEL_30;
      }
      lpcaStringsOut->cElems = m_nSize;
      v13 = 0;
      lpcaCookiesOut->cElems = m_nSize;
      if ( m_nSize > 0 )
      {
        v14 = 0;
        while ( 1 )
        {
          if ( v14 < 0 || v14 >= stringArray.m_nSize )
LABEL_33:
            AfxThrowInvalidArgException();
          m_pszData = stringArray.m_pData[v14].m_pszData;
          if ( !m_pszData )
            break;
          v16 = (unsigned int)wcslen(stringArray.m_pData[v14].m_pszData) + 1;
          SizeInWords = (int)v16;
          if ( (unsigned __int64)(int)v16 > 0x7FFFFFFFFFFFFFFFLL )
            break;
          v17 = 2 * v16;
          if ( v17 > 0xFFFFFFFF )
          {
            v19 = 0;
          }
          else
          {
            v18 = (wchar_t *)CoTaskMemAlloc((unsigned int)v17);
            v19 = v18;
            if ( v18 )
            {
              v20 = wcscpy_s(v18, SizeInWords, m_pszData);
              v19 = v18;
              if ( v20 )
              {
                if ( v20 == 12 )
                  AfxThrowMemoryException();
                if ( v20 != 80 )
                  goto LABEL_33;
              }
            }
          }
          if ( !v19 )
            break;
          lpcaStringsOut->pElems[v14] = v19;
          if ( v14 >= cookieArray.m_nSize )
            goto LABEL_33;
          ++v13;
          lpcaCookiesOut->pElems[v14] = cookieArray.m_pData[v14];
          ++v14;
          if ( v13 >= m_nSize )
            goto LABEL_23;
        }
        for ( i = v13 - 1; i >= 0; CoTaskMemFree(lpcaStringsOut->pElems[i--]) )
          ;
        CoTaskMemFree(lpcaCookiesOut->pElems);
        CoTaskMemFree(lpcaStringsOut->pElems);
        goto LABEL_8;
      }
    }
LABEL_23:
    v12 = v26 == 0;
    goto LABEL_24;
  }
  v12 = -2147467261;
LABEL_30:
  if ( _ctlState.m_pThreadState )
    _ctlState.m_pThreadState->m_pModuleState = _ctlState.m_pPrevModuleState;
  return v12;
}

```

## disassembly

```asm
0x1801f83c0  mov     [rsp-8+arg_8], rbx
0x1801f83c5  push    rbp
0x1801f83c6  push    rsi
0x1801f83c7  push    rdi
0x1801f83c8  push    r12
0x1801f83ca  push    r13
0x1801f83cc  push    r14
0x1801f83ce  push    r15
0x1801f83d0  lea     rbp, [rsp-27h]
0x1801f83d5  sub     rsp, 90h
0x1801f83dc  lea     rbx, [this-2B0h]
0x1801f83e3  mov     esi, dispid
0x1801f83e5  mov     rdx, [rbx+38h]; pNewState
0x1801f83e9  lea     this, [rbp+57h+_ctlState]; this
0x1801f83ed  mov     r14, lpcaCookiesOut
0x1801f83f0  mov     rdi, lpcaStringsOut
0x1801f83f3  call    ??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z; AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(AFX_MODULE_STATE *)
0x1801f83f8  xor     r13d, r13d
0x1801f83fb  test    rdi, rdi
0x1801f83fe  jz      loc_1801F8614
0x1801f8404  test    r14, r14
0x1801f8407  jz      loc_1801F8614
0x1801f840d  lea     rax, ??_7CStringArray@@6B@; const CStringArray::`vftable'
0x1801f8414  mov     [rbp+57h+stringArray.m_pData], r13
0x1801f8418  mov     [rbp+57h+stringArray.__vftable], rax
0x1801f841c  lea     r15, ??_7CDWordArray@@6B@; const CDWordArray::`vftable'
0x1801f8423  mov     rax, [rbx]
0x1801f8426  lea     lpcaCookiesOut, [rbp+57h+cookieArray]
0x1801f842a  lea     lpcaStringsOut, [rbp+57h+stringArray]
0x1801f842e  mov     [rbp+57h+stringArray.m_nGrowBy], r13
0x1801f8432  mov     dispid, esi
0x1801f8434  mov     [rbp+57h+stringArray.m_nMaxSize], r13
0x1801f8438  mov     this, rbx
0x1801f843b  mov     [rbp+57h+stringArray.m_nSize], r13
0x1801f843f  mov     rax, [rax+458h]
0x1801f8446  mov     [rbp+57h+cookieArray.__vftable], r15
0x1801f844a  mov     [rbp+57h+cookieArray.m_pData], r13
0x1801f844e  mov     [rbp+57h+cookieArray.m_nGrowBy], r13
0x1801f8452  mov     [rbp+57h+cookieArray.m_nMaxSize], r13
0x1801f8456  mov     [rbp+57h+cookieArray.m_nSize], r13
0x1801f845a  call    cs:__guard_dispatch_icall_fptr
0x1801f8460  mov     [rbp+57h+arg_0], eax
0x1801f8463  test    eax, eax
0x1801f8465  jz      loc_1801F85AD
0x1801f846b  mov     esi, dword ptr [rbp+57h+stringArray.m_nSize]
0x1801f846e  lea     ecx, [rsi-1]
0x1801f8471  cmp     ecx, 1FFFFFFEh
0x1801f8477  ja      short loc_1801F84AD
0x1801f8479  mov     ebx, esi
0x1801f847b  shl     rbx, 3
0x1801f847f  mov     this, rbx; cb
0x1801f8482  call    cs:__imp_CoTaskMemAlloc
0x1801f8488  mov     [rdi+8], rax
0x1801f848c  test    rax, rax
0x1801f848f  jz      short loc_1801F84AD
0x1801f8491  mov     this, rbx; cb
0x1801f8494  call    cs:__imp_CoTaskMemAlloc
0x1801f849a  mov     [r14+8], rax
0x1801f849e  test    rax, rax
0x1801f84a1  jnz     short loc_1801F84B7
0x1801f84a3  mov     this, [rdi+8]; pv
0x1801f84a7  call    cs:__imp_CoTaskMemFree
0x1801f84ad  mov     ebx, 8007000Eh
0x1801f84b2  jmp     loc_1801F85B7
0x1801f84b7  mov     [rdi], esi
0x1801f84b9  mov     r15d, r13d
0x1801f84bc  mov     [r14], esi
0x1801f84bf  test    esi, esi
0x1801f84c1  jle     loc_1801F85A6
0x1801f84c7  mov     rbx, r13
0x1801f84ca  test    rbx, rbx
0x1801f84cd  js      loc_1801F8647
0x1801f84d3  cmp     rbx, [rbp+57h+stringArray.m_nSize]
0x1801f84d7  jge     loc_1801F8647
0x1801f84dd  mov     rax, [rbp+57h+stringArray.m_pData]
0x1801f84e1  mov     r12, [rax+rbx*8]
0x1801f84e5  test    r12, r12
0x1801f84e8  jz      loc_1801F85D5
0x1801f84ee  mov     this, r12; String
0x1801f84f1  call    cs:__imp_wcslen
0x1801f84f7  inc     eax
0x1801f84f9  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1801f8503  movsxd  this, eax
0x1801f8506  mov     [rbp+57h+SizeInWords], this
0x1801f850a  cmp     this, rdx
0x1801f850d  ja      loc_1801F85D5
0x1801f8513  add     rax, rax
0x1801f8516  mov     ecx, 0FFFFFFFFh
0x1801f851b  cmp     rax, this
0x1801f851e  ja      loc_1801F85D0
0x1801f8524  mov     ecx, eax; cb
0x1801f8526  call    cs:__imp_CoTaskMemAlloc
0x1801f852c  mov     r13, rax
0x1801f852f  mov     this, rax; Destination
0x1801f8532  test    rax, rax
0x1801f8535  jz      short loc_1801F856F
0x1801f8537  mov     rdx, [rbp+57h+SizeInWords]; SizeInWords
0x1801f853b  mov     lpcaStringsOut, r12; Source
0x1801f853e  call    cs:__imp_wcscpy_s
0x1801f8544  mov     this, r13
0x1801f8547  test    eax, eax
0x1801f8549  jz      short loc_1801F856F
0x1801f854b  cmp     eax, 0Ch
0x1801f854e  jz      loc_1801F864D
0x1801f8554  cmp     eax, 16h
0x1801f8557  jz      loc_1801F8647
0x1801f855d  cmp     eax, 22h ; '"'
0x1801f8560  jz      loc_1801F8647
0x1801f8566  cmp     eax, 50h ; 'P'
0x1801f8569  jnz     loc_1801F8647
0x1801f856f  xor     r13d, r13d
0x1801f8572  test    this, this
0x1801f8575  jz      short loc_1801F85D5
0x1801f8577  mov     rax, [rdi+8]
0x1801f857b  mov     [rax+rbx*8], this
0x1801f857f  cmp     rbx, [rbp+57h+cookieArray.m_nSize]
0x1801f8583  jge     loc_1801F8647
0x1801f8589  mov     rax, [rbp+57h+cookieArray.m_pData]
0x1801f858d  inc     r15d
0x1801f8590  mov     rdx, [r14+8]
0x1801f8594  mov     ecx, [rax+rbx*4]
0x1801f8597  mov     [rdx+rbx*4], ecx
0x1801f859a  inc     rbx
0x1801f859d  cmp     r15d, esi
0x1801f85a0  jl      loc_1801F84CA
0x1801f85a6  lea     r15, ??_7CDWordArray@@6B@; const CDWordArray::`vftable'
0x1801f85ad  cmp     [rbp+57h+arg_0], r13d
0x1801f85b1  mov     ebx, r13d
0x1801f85b4  setz    bl
0x1801f85b7  mov     this, [rbp+57h+cookieArray.m_pData]; Block
0x1801f85bb  mov     [rbp+57h+cookieArray.__vftable], r15
0x1801f85bf  call    cs:__imp_free
0x1801f85c5  lea     this, [rbp+57h+stringArray]; this
0x1801f85c9  call    ??1CStringArray@@UEAA@XZ; CStringArray::~CStringArray(void)
0x1801f85ce  jmp     short loc_1801F8619
0x1801f85d0  mov     this, r13
0x1801f85d3  jmp     short loc_1801F8572
0x1801f85d5  lea     eax, [r15-1]
0x1801f85d9  movsxd  rbx, eax
0x1801f85dc  test    eax, eax
0x1801f85de  js      short loc_1801F85F4
0x1801f85e0  mov     this, [rdi+8]
0x1801f85e4  mov     this, [this+rbx*8]; pv
0x1801f85e8  call    cs:__imp_CoTaskMemFree
0x1801f85ee  sub     rbx, 1
0x1801f85f2  jns     short loc_1801F85E0
0x1801f85f4  mov     this, [r14+8]; pv
0x1801f85f8  call    cs:__imp_CoTaskMemFree
0x1801f85fe  mov     this, [rdi+8]; pv
0x1801f8602  call    cs:__imp_CoTaskMemFree
0x1801f8608  lea     r15, ??_7CDWordArray@@6B@; const CDWordArray::`vftable'
0x1801f860f  jmp     loc_1801F84AD
0x1801f8614  mov     ebx, 80004003h
0x1801f8619  mov     rax, [rbp+57h+_ctlState.m_pThreadState]
0x1801f861d  test    rax, rax
0x1801f8620  jz      short loc_1801F862A
0x1801f8622  mov     this, [rbp+57h+_ctlState.m_pPrevModuleState]
0x1801f8626  mov     [rax+8], this
0x1801f862a  mov     eax, ebx
0x1801f862c  mov     rbx, [rsp+0C0h+arg_8]
0x1801f8634  add     rsp, 90h
0x1801f863b  pop     r15
0x1801f863d  pop     r14
0x1801f863f  pop     r13
0x1801f8641  pop     r12
0x1801f8643  pop     rdi
0x1801f8644  pop     rsi
0x1801f8645  pop     rbp
0x1801f8646  retn
0x1801f8647  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x1801f864d  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
```
