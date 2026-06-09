# CFileDialog::GetPathName(void)

- ea: `0x1802163c0`
- end: `0x1802167d6`
- name: `?GetPathName@CFileDialog@@QEBA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@XZ`
- size: `1046`
- prototype: `ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *__fastcall(CFileDialog *this, ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *result)`
- caller_count: `8`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180061b80`
- `0x1800c8e60`
- `0x180187e40`
- `0x180214720`
- `0x180216290`
- `0x180216a30`
- `0x180217590`
- `0x18028e0d0`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000df50`
- `0x18000dfe0`
- `0x1802163c0`
- `0x180296d00`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18021652d`
- `VCRUNTIME140!memmove` at `0x18021652d`
- `VCRUNTIME140!memset` at `0x18021655c`
- `VCRUNTIME140!memset` at `0x18021655c`
- `VCRUNTIME140!memcpy` at `0x180216552`
- `VCRUNTIME140!memcpy` at `0x180216552`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18021656e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18021656e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18021650d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180216562`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18021650d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180216562`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802164b0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802164b0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18021659b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802166a0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180216773`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18021659b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802166a0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180216773`
- `USER32!SendMessageW` at `0x18021667f`
- `USER32!SendMessageW` at `0x180216708`
- `USER32!SendMessageW` at `0x18021667f`
- `USER32!SendMessageW` at `0x180216708`
- `USER32!GetParent` at `0x18021663a`
- `USER32!GetParent` at `0x1802166cb`
- `USER32!GetParent` at `0x18021663a`
- `USER32!GetParent` at `0x1802166cb`
- `ole32!CoTaskMemFree` at `0x1802165c0`
- `ole32!CoTaskMemFree` at `0x1802165c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *__fastcall CFileDialog::GetPathName(
        CFileDialog *this,
        ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *result)
{
  wchar_t *m_pszData; // rbx
  wchar_t *v5; // r12
  int v6; // eax
  int v7; // edi
  unsigned __int64 v8; // r13
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rsi
  wchar_t *v11; // rdx
  size_t v12; // r8
  int v13; // eax
  tagOFNW *m_pOFN; // rdx
  HWND Parent; // rax
  CWnd *v16; // r15
  int v17; // eax
  HWND v18; // rax
  CWnd *v19; // r15
  int v21; // eax
  wchar_t *wcPathName; // [rsp+28h] [rbp-8h] BYREF
  ATL::CSimpleStringT<wchar_t,1> sfgaoAttribs; // [rsp+70h] [rbp+40h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strResult; // [rsp+80h] [rbp+50h] BYREF
  IShellItem *psiResult; // [rsp+88h] [rbp+58h] BYREF

  if ( this->m_bVistaStyle == 1 )
  {
    if ( this->m_hWnd )
    {
      m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
      strResult.m_pszData = m_pszData;
      if ( (*(int (__fastcall **)(void *, IShellItem **))(*(_QWORD *)this->m_pIFileDialog + 112LL))(
             this->m_pIFileDialog,
             &psiResult) < 0 )
      {
LABEL_31:
        result->m_pszData = (wchar_t *)&ATL::CSimpleStringT<wchar_t,1>::CloneData((ATL::CStringData *)m_pszData - 1)[1];
        goto LABEL_55;
      }
      if ( psiResult->GetAttributes(psiResult, 0x400000u, (unsigned int *)&sfgaoAttribs) == 1
        && !psiResult->GetAttributes(psiResult, 0x20000000u, (unsigned int *)&sfgaoAttribs)
        || (wcPathName = 0, psiResult->GetDisplayName(psiResult, SIGDN_FILESYSPATH, &wcPathName) < 0) )
      {
LABEL_30:
        psiResult->Release(psiResult);
        goto LABEL_31;
      }
      v5 = wcPathName;
      if ( !wcPathName || (v6 = wcslen(wcPathName), (v7 = v6) == 0) )
      {
        ATL::CSimpleStringT<wchar_t,1>::Empty(&strResult);
        m_pszData = strResult.m_pszData;
        goto LABEL_27;
      }
      v8 = *((unsigned int *)m_pszData - 4);
      v9 = v5 - m_pszData;
      if ( v6 < 0 )
        goto LABEL_57;
      if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - v6)) < 0 )
      {
        ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&strResult, v6);
        m_pszData = strResult.m_pszData;
      }
      v10 = 2LL * v7;
      if ( v9 > v8 )
      {
        v12 = 2LL * *((int *)m_pszData - 3);
        if ( !v10 )
          goto LABEL_24;
        if ( v12 >= v10 )
        {
          memcpy(m_pszData, v5, 2LL * v7);
          goto LABEL_24;
        }
        memset(m_pszData, 0, v12);
      }
      else
      {
        v11 = &m_pszData[v9];
        if ( !v10 )
        {
LABEL_24:
          if ( v7 > *((_DWORD *)m_pszData - 3) )
            goto LABEL_57;
          *((_DWORD *)m_pszData - 4) = v7;
          m_pszData[v10 / 2] = 0;
LABEL_27:
          v13 = wcsnlen(m_pszData, *((int *)m_pszData - 3));
          if ( v13 >= 0 && v13 <= *((_DWORD *)m_pszData - 3) )
          {
            *((_DWORD *)m_pszData - 4) = v13;
            m_pszData[v13] = 0;
            CoTaskMemFree(wcPathName);
            goto LABEL_30;
          }
LABEL_57:
          ATL::AtlThrowImpl(-2147024809);
        }
        if ( !v11 )
        {
          *_errno() = 22;
LABEL_23:
          _invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( 2LL * *((int *)m_pszData - 3) >= v10 )
        {
          memmove(m_pszData, v11, 2LL * v7);
          goto LABEL_24;
        }
      }
      *_errno() = 34;
      goto LABEL_23;
    }
    m_pOFN = this->m_pOFN;
LABEL_50:
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      result,
      m_pOFN->lpstrFile);
    return result;
  }
  if ( (this->m_pOFN->Flags & 0x80000) == 0 || !this->m_hWnd )
  {
LABEL_49:
    m_pOFN = this->m_pOFN;
    goto LABEL_50;
  }
  m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  sfgaoAttribs.m_pszData = m_pszData;
  Parent = GetParent(this->m_hWnd);
  v16 = CWnd::FromHandle(Parent);
  if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - 260)) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&sfgaoAttribs, 260);
    m_pszData = sfgaoAttribs.m_pszData;
  }
  if ( SendMessageW(v16->m_hWnd, 0x464u, 0x104u, (LPARAM)m_pszData) >= 0 )
  {
    v17 = wcsnlen(m_pszData, *((int *)m_pszData - 3));
    if ( v17 < 0 || v17 > *((_DWORD *)m_pszData - 3) )
      goto LABEL_58;
    *((_DWORD *)m_pszData - 4) = v17;
    m_pszData[v17] = 0;
  }
  else
  {
    ATL::CSimpleStringT<wchar_t,1>::Empty(&sfgaoAttribs);
    m_pszData = sfgaoAttribs.m_pszData;
  }
  if ( !*((_DWORD *)m_pszData - 4) )
    goto LABEL_47;
  v18 = GetParent(this->m_hWnd);
  v19 = CWnd::FromHandle(v18);
  if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - 260)) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&sfgaoAttribs, 260);
    m_pszData = sfgaoAttribs.m_pszData;
  }
  if ( SendMessageW(v19->m_hWnd, 0x465u, 0x104u, (LPARAM)m_pszData) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,1>::Empty(&sfgaoAttribs);
    m_pszData = sfgaoAttribs.m_pszData;
LABEL_47:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
    goto LABEL_49;
  }
  v21 = wcsnlen(m_pszData, *((int *)m_pszData - 3));
  if ( v21 < 0 || v21 > *((_DWORD *)m_pszData - 3) )
LABEL_58:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)m_pszData - 4) = v21;
  m_pszData[v21] = 0;
  result->m_pszData = (wchar_t *)&ATL::CSimpleStringT<wchar_t,1>::CloneData((ATL::CStringData *)m_pszData - 1)[1];
LABEL_55:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, wchar_t *))(**((_QWORD **)m_pszData - 3) + 8LL))(
      *((_QWORD *)m_pszData - 3),
      m_pszData - 12);
  return result;
}

```

## disassembly

```asm
0x1802163c0  mov     [rsp-38h+arg_8], rbx
0x1802163c5  push    rbp
0x1802163c6  push    rsi
0x1802163c7  push    rdi
0x1802163c8  push    r12
0x1802163ca  push    r13
0x1802163cc  push    r14
0x1802163ce  push    r15
0x1802163d0  mov     rbp, rsp
0x1802163d3  sub     rsp, 30h
0x1802163d7  mov     r14, rdx
0x1802163da  mov     rdi, this
0x1802163dd  xor     r13d, r13d
0x1802163e0  lea     esi, [r13+1]
0x1802163e4  cmp     [this+138h], esi
0x1802163ea  jnz     loc_1802165F8
0x1802163f0  cmp     [this+40h], r13
0x1802163f4  jz      loc_1802165EC
0x1802163fa  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x180216401  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180216408  mov     rax, [rax+18h]
0x18021640c  call    cs:__guard_dispatch_icall_fptr
0x180216412  lea     rbx, [rax+18h]
0x180216416  mov     [rbp+strResult.m_pszData], rbx
0x18021641a  mov     this, [rdi+148h]
0x180216421  mov     rax, [this]
0x180216424  lea     rdx, [rbp+psiResult]
0x180216428  mov     rax, [rax+70h]
0x18021642c  call    cs:__guard_dispatch_icall_fptr
0x180216432  test    eax, eax
0x180216434  js      loc_1802165D7
0x18021643a  mov     this, [rbp+psiResult]
0x18021643e  mov     rax, [this]
0x180216441  lea     r8, [rbp+sfgaoAttribs]
0x180216445  mov     edx, 400000h
0x18021644a  mov     rax, [rax+30h]
0x18021644e  call    cs:__guard_dispatch_icall_fptr
0x180216454  cmp     eax, esi
0x180216456  jnz     short loc_18021647A
0x180216458  mov     this, [rbp+psiResult]
0x18021645c  mov     rax, [this]
0x18021645f  lea     r8, [rbp+sfgaoAttribs]
0x180216463  mov     edx, 20000000h
0x180216468  mov     rax, [rax+30h]
0x18021646c  call    cs:__guard_dispatch_icall_fptr
0x180216472  test    eax, eax
0x180216474  jz      loc_1802165C6
0x18021647a  mov     [rbp+wcPathName], r13
0x18021647e  mov     this, [rbp+psiResult]
0x180216482  mov     rax, [this]
0x180216485  lea     r8, [rbp+wcPathName]
0x180216489  mov     edx, 80058000h
0x18021648e  mov     rax, [rax+28h]
0x180216492  call    cs:__guard_dispatch_icall_fptr
0x180216498  test    eax, eax
0x18021649a  js      loc_1802165C6
0x1802164a0  mov     r12, [rbp+wcPathName]
0x1802164a4  test    r12, r12
0x1802164a7  jz      loc_180216587
0x1802164ad  mov     this, r12; String
0x1802164b0  call    cs:__imp_wcslen
0x1802164b6  mov     rdi, rax
0x1802164b9  test    eax, eax
0x1802164bb  jz      loc_180216587
0x1802164c1  mov     r13d, [rbx-10h]
0x1802164c5  mov     r15, r12
0x1802164c8  sub     r15, rbx
0x1802164cb  sar     r15, 1
0x1802164ce  test    edi, edi
0x1802164d0  js      loc_1802167C0
0x1802164d6  sub     esi, [rbx-8]
0x1802164d9  mov     eax, [rbx-0Ch]
0x1802164dc  sub     eax, edi
0x1802164de  or      eax, esi
0x1802164e0  jge     short loc_1802164F1
0x1802164e2  mov     edx, edi; nLength
0x1802164e4  lea     this, [rbp+strResult]; this
0x1802164e8  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802164ed  mov     rbx, [rbp+strResult.m_pszData]
0x1802164f1  movsxd  rsi, edi
0x1802164f4  add     rsi, rsi
0x1802164f7  cmp     r15, r13
0x1802164fa  ja      short loc_180216535
0x1802164fc  lea     rdx, [rbx+r15*2]; Src
0x180216500  xor     r13d, r13d
0x180216503  test    rsi, rsi
0x180216506  jz      short loc_180216574
0x180216508  test    rdx, rdx
0x18021650b  jnz     short loc_18021651B
0x18021650d  call    cs:__imp__errno
0x180216513  mov     dword ptr [rax], 16h
0x180216519  jmp     short loc_18021656E
0x18021651b  movsxd  rax, dword ptr [rbx-0Ch]
0x18021651f  add     rax, rax
0x180216522  cmp     rax, rsi
0x180216525  jb      short loc_180216562
0x180216527  mov     r8, rsi; Size
0x18021652a  mov     this, rbx; void *
0x18021652d  call    cs:__imp_memmove
0x180216533  jmp     short loc_180216574
0x180216535  movsxd  r8, dword ptr [rbx-0Ch]
0x180216539  add     r8, r8; Size
0x18021653c  xor     r13d, r13d
0x18021653f  test    rsi, rsi
0x180216542  jz      short loc_180216574
0x180216544  mov     this, rbx; void *
0x180216547  cmp     r8, rsi
0x18021654a  jb      short loc_18021655A
0x18021654c  mov     r8, rsi; Size
0x18021654f  mov     rdx, r12; Src
0x180216552  call    cs:__imp_memcpy
0x180216558  jmp     short loc_180216574
0x18021655a  xor     edx, edx; Val
0x18021655c  call    cs:__imp_memset
0x180216562  call    cs:__imp__errno
0x180216568  mov     dword ptr [rax], 22h ; '"'
0x18021656e  call    cs:__imp__invalid_parameter_noinfo
0x180216574  cmp     edi, [rbx-0Ch]
0x180216577  jg      loc_1802167C0
0x18021657d  mov     [rbx-10h], edi
0x180216580  mov     [rsi+rbx], r13w
0x180216585  jmp     short loc_180216594
0x180216587  lea     this, [rbp+strResult]; this
0x18021658b  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180216590  mov     rbx, [rbp+strResult.m_pszData]
0x180216594  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x180216598  mov     this, rbx; Source
0x18021659b  call    cs:__imp_wcsnlen
0x1802165a1  test    eax, eax
0x1802165a3  js      loc_1802167C0
0x1802165a9  cmp     eax, [rbx-0Ch]
0x1802165ac  jg      loc_1802167C0
0x1802165b2  mov     [rbx-10h], eax
0x1802165b5  cdqe
0x1802165b7  mov     [rbx+rax*2], r13w
0x1802165bc  mov     this, [rbp+wcPathName]; pv
0x1802165c0  call    cs:__imp_CoTaskMemFree
0x1802165c6  mov     this, [rbp+psiResult]
0x1802165ca  mov     rax, [this]
0x1802165cd  mov     rax, [rax+10h]
0x1802165d1  call    cs:__guard_dispatch_icall_fptr
0x1802165d7  lea     this, [rbx-18h]; pData
0x1802165db  call    ?CloneData@?$CSimpleStringT@_W$00@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,1>::CloneData(ATL::CStringData *)
0x1802165e0  add     rax, 18h
0x1802165e4  mov     [r14], rax
0x1802165e7  jmp     loc_18021679C
0x1802165ec  mov     rdx, [this+130h]
0x1802165f3  jmp     loc_180216748
0x1802165f8  mov     rax, [this+130h]
0x1802165ff  test    dword ptr [rax+60h], 80000h
0x180216606  jz      loc_180216741
0x18021660c  cmp     [this+40h], r13
0x180216610  jz      loc_180216741
0x180216616  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18021661d  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180216624  mov     rax, [rax+18h]
0x180216628  call    cs:__guard_dispatch_icall_fptr
0x18021662e  lea     rbx, [rax+18h]
0x180216632  mov     [rbp+sfgaoAttribs], rbx
0x180216636  mov     this, [rdi+40h]; hWnd
0x18021663a  call    cs:__imp_GetParent
0x180216640  mov     this, rax; hWnd
0x180216643  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180216648  mov     r15, rax
0x18021664b  mov     edx, esi
0x18021664d  sub     edx, [rbx-8]
0x180216650  mov     ecx, [rbx-0Ch]
0x180216653  mov     r12d, 104h
0x180216659  sub     ecx, r12d
0x18021665c  or      ecx, edx
0x18021665e  jge     short loc_180216670
0x180216660  mov     edx, r12d; nLength
0x180216663  lea     this, [rbp+sfgaoAttribs]; this
0x180216667  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x18021666c  mov     rbx, [rbp+sfgaoAttribs]
0x180216670  mov     r9, rbx; lParam
0x180216673  mov     r8, r12; wParam
0x180216676  mov     edx, 464h; Msg
0x18021667b  mov     this, [r15+40h]; hWnd
0x18021667f  call    cs:__imp_SendMessageW
0x180216685  test    rax, rax
0x180216688  jns     short loc_180216699
0x18021668a  lea     this, [rbp+sfgaoAttribs]; this
0x18021668e  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180216693  mov     rbx, [rbp+sfgaoAttribs]
0x180216697  jmp     short loc_1802166C1
0x180216699  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x18021669d  mov     this, rbx; Source
0x1802166a0  call    cs:__imp_wcsnlen
0x1802166a6  test    eax, eax
0x1802166a8  js      loc_1802167CB
0x1802166ae  cmp     eax, [rbx-0Ch]
0x1802166b1  jg      loc_1802167CB
0x1802166b7  mov     [rbx-10h], eax
0x1802166ba  cdqe
0x1802166bc  mov     [rbx+rax*2], r13w
0x1802166c1  cmp     [rbx-10h], r13d
0x1802166c5  jz      short loc_180216720
0x1802166c7  mov     this, [rdi+40h]; hWnd
0x1802166cb  call    cs:__imp_GetParent
0x1802166d1  mov     this, rax; hWnd
0x1802166d4  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1802166d9  mov     r15, rax
0x1802166dc  sub     esi, [rbx-8]
0x1802166df  mov     ecx, [rbx-0Ch]
0x1802166e2  sub     ecx, r12d
0x1802166e5  or      ecx, esi
0x1802166e7  jge     short loc_1802166F9
0x1802166e9  mov     edx, r12d; nLength
0x1802166ec  lea     this, [rbp+sfgaoAttribs]; this
0x1802166f0  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802166f5  mov     rbx, [rbp+sfgaoAttribs]
0x1802166f9  mov     r9, rbx; lParam
0x1802166fc  mov     r8, r12; wParam
0x1802166ff  mov     edx, 465h; Msg
0x180216704  mov     this, [r15+40h]; hWnd
0x180216708  call    cs:__imp_SendMessageW
0x18021670e  test    rax, rax
0x180216711  jns     short loc_18021676C
0x180216713  lea     this, [rbp+sfgaoAttribs]; this
0x180216717  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x18021671c  mov     rbx, [rbp+sfgaoAttribs]
0x180216720  lea     rdx, [rbx-18h]
0x180216724  or      eax, 0FFFFFFFFh
0x180216727  lock xadd [rdx+10h], eax
0x18021672c  sub     eax, 1
0x18021672f  jg      short loc_180216741
0x180216731  mov     this, [rdx]
0x180216734  mov     rax, [this]
0x180216737  mov     rax, [rax+8]
0x18021673b  call    cs:__guard_dispatch_icall_fptr
0x180216741  mov     rdx, [rdi+130h]
0x180216748  mov     rdx, [rdx+30h]; pszSrc
0x18021674c  mov     this, r14; this
0x18021674f  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180216754  mov     rax, r14
0x180216757  mov     rbx, [rsp+30h+arg_8]
0x18021675c  add     rsp, 30h
0x180216760  pop     r15
0x180216762  pop     r14
0x180216764  pop     r13
0x180216766  pop     r12
0x180216768  pop     rdi
0x180216769  pop     rsi
0x18021676a  pop     rbp
0x18021676b  retn
0x18021676c  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x180216770  mov     this, rbx; Source
0x180216773  call    cs:__imp_wcsnlen
0x180216779  test    eax, eax
0x18021677b  js      short loc_1802167CB
0x18021677d  cmp     eax, [rbx-0Ch]
0x180216780  jg      short loc_1802167CB
0x180216782  mov     [rbx-10h], eax
0x180216785  cdqe
0x180216787  mov     [rbx+rax*2], r13w
0x18021678c  lea     this, [rbx-18h]; pData
0x180216790  call    ?CloneData@?$CSimpleStringT@_W$00@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,1>::CloneData(ATL::CStringData *)
0x180216795  add     rax, 18h
0x180216799  mov     [r14], rax
0x18021679c  or      eax, 0FFFFFFFFh
0x18021679f  lock xadd [rbx-8], eax
0x1802167a4  sub     eax, 1
0x1802167a7  jg      short loc_180216754
0x1802167a9  mov     this, [rbx-18h]
0x1802167ad  mov     rax, [this]
0x1802167b0  lea     rdx, [rbx-18h]
0x1802167b4  mov     rax, [rax+8]
0x1802167b8  call    cs:__guard_dispatch_icall_fptr
0x1802167be  jmp     short loc_180216754
0x1802167c0  mov     ecx, 80070057h; hr
0x1802167c5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1802167cb  mov     ecx, 80070057h; hr
0x1802167d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
