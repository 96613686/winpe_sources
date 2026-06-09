# CPropertyStoreOverFolderFinal::_GetValue(_tagpropertykey const &,tagPROPVARIANT *,int,ushort * *)

- ea: `0x180033634`
- end: `0x180033a19`
- name: `?_GetValue@CPropertyStoreOverFolderFinal@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `997`
- prototype: `__int64 __usercall@<rax>(CPropertyStoreOverFolderFinal *__hidden this@<rcx>, const struct _tagpropertykey *@<rdx>, PROPVARIANT *pPropVar@<r8>, int@<r9d>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007f3b0`

## callees

- `0x1800328b0`
- `0x180033634`
- `0x180033e40`
- `0x1800343b0`
- `0x18004e020`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800338f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800338cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800338cf`
- `OLEAUT32!__imp_VariantClear` at `0x18003380b`
- `OLEAUT32!__imp_VariantClear` at `0x18003380b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyStoreOverFolderFinal::_GetValue(
        CPropertyStoreOverFolderFinal *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *pPropVar,
        int a4,
        unsigned __int16 **a5)
{
  const struct _ITEMID_CHILD *v8; // r11
  __int64 i; // rcx
  __int64 v10; // rdx
  signed int v11; // ebp
  __int64 v12; // r12
  unsigned __int16 *v13; // rsi
  unsigned __int16 *v14; // rdx
  __int64 v15; // rcx
  const wchar_t *v16; // r9
  __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // r10
  wchar_t v20; // r11
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned __int16 *v23; // rcx
  HRESULT v24; // ebx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int16 *v32; // rax
  VARIANT pVar; // [rsp+68h] [rbp-70h] BYREF

  *(_OWORD *)pPropVar = 0;
  pPropVar[2] = 0;
  v8 = (const struct _ITEMID_CHILD *)*((_QWORD *)this + 7);
  if ( a5 )
    *a5 = 0;
  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    v10 = *((_QWORD *)&CPropertyStoreOverFolderFinal::c_rgGetValueHelpers + 2 * (unsigned int)i);
    if ( *(_DWORD *)(v10 + 16) == a2->pid )
    {
      v21 = *(_QWORD *)v10 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)v10 == *(_QWORD *)&a2->fmtid.Data1 )
        v21 = *(_QWORD *)(v10 + 8) - *(_QWORD *)a2->fmtid.Data4;
      if ( !v21 )
      {
        (*(&funcs_180033797 + 2 * (unsigned int)i))(this, v8, a2, (struct tagPROPVARIANT *)pPropVar, a4, a5);
        return 0;
      }
    }
  }
  v11 = 0;
  if ( !*((_DWORD *)this + 17) )
  {
    if ( (*((_BYTE *)this + 64) & 8) == 0 )
      goto LABEL_9;
    i = a2->pid;
    if ( PKEY_FileName.pid == (_DWORD)i )
    {
      v28 = *(_QWORD *)&PKEY_FileName.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_FileName.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v28 = *(_QWORD *)PKEY_FileName.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( !v28 )
        goto LABEL_9;
    }
    v26 = *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      v26 = *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( !v26 )
      goto LABEL_9;
    if ( PKEY_PropList_NonPersonal.pid == (_DWORD)i )
    {
      v29 = *(_QWORD *)&PKEY_PropList_NonPersonal.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_PropList_NonPersonal.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v29 = *(_QWORD *)PKEY_PropList_NonPersonal.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( !v29 )
        goto LABEL_9;
    }
    if ( PKEY_PropList_XPDetailsPanel.pid == (_DWORD)i )
    {
      v30 = *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v30 = *(_QWORD *)PKEY_PropList_XPDetailsPanel.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( !v30 )
        goto LABEL_9;
    }
    if ( PKEY_ItemNameDisplayWithoutExtension.pid == (_DWORD)i )
    {
      v31 = *(_QWORD *)&PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v31 = *(_QWORD *)PKEY_ItemNameDisplayWithoutExtension.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( !v31 )
        goto LABEL_9;
    }
    if ( (unsigned int)CPropertyStoreOverFolderFinal::_IsFastProperty(
                         this,
                         *((const struct _ITEMID_CHILD **)this + 7),
                         a2) )
    {
LABEL_9:
      v12 = *((_QWORD *)this + 7);
      if ( (byte_1800F1382 & 0x10) != 0 )
        McTemplateU0jq_EtwEventWriteTransfer(
          i,
          ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Start,
          a2,
          a2->pid);
      v13 = 0;
      if ( is_mul_ok(0x19u, 2u) )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(0x32u);
        v11 = v13 == 0 ? 0x8007000E : 0;
        v14 = v13;
      }
      else
      {
        v14 = 0;
        v11 = -2147024362;
      }
      if ( v11 >= 0 )
      {
        if ( v14 )
        {
          v15 = 24;
          v16 = L"PropStoreOverFolderFinal";
          v17 = 25;
          v18 = v14;
          v19 = 0;
          do
          {
            if ( !v15 )
              break;
            v20 = *v16;
            if ( !*v16 )
              break;
            ++v16;
            *v18++ = v20;
            --v15;
            ++v19;
            --v17;
          }
          while ( v17 );
          v22 = v19 - 1;
          if ( v17 )
            v22 = v19;
          v23 = v18 - 1;
          if ( v17 )
            v23 = v18;
          *v23 = 0;
          if ( v17 )
          {
            v27 = 25 - v22;
            if ( v22 != 25 && v22 != 24 && (unsigned __int64)(2 * v27) > 2 )
              memset_0(&v14[v22 + 1], 0, 2 * v27 - 2);
          }
        }
        else
        {
          MEMORY[0] = 0;
        }
        memset(&pVar, 0, sizeof(pVar));
        if ( (*(int (__fastcall **)(_QWORD, __int64, const struct _tagpropertykey *, VARIANT *))(**((_QWORD **)this + 6)
                                                                                               + 136LL))(
               *((_QWORD *)this + 6),
               v12,
               a2,
               &pVar) < 0
          || (v24 = VariantToPropVariant(&pVar, pPropVar), VariantClear(&pVar), v24 >= 0) )
        {
          if ( a5 )
          {
            v32 = v13;
            v13 = 0;
            *a5 = v32;
          }
        }
      }
      if ( (byte_1800F1382 & 0x10) != 0 )
        McTemplateU0jq_EtwEventWriteTransfer(
          i,
          ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Stop,
          a2,
          a2->pid);
      if ( v13 )
        CoTaskMemFree(v13);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180033634  push    rbx
0x180033636  push    rbp
0x180033637  push    rsi
0x180033638  push    rdi
0x180033639  push    r12
0x18003363b  push    r13
0x18003363d  push    r14
0x18003363f  push    r15
0x180033641  sub     rsp, 98h
0x180033648  mov     rax, cs:__security_cookie
0x18003364f  xor     rax, rsp
0x180033652  mov     [rsp+0D8h+var_58], rax
0x18003365a  mov     r13, r8
0x18003365d  mov     rdi, rdx
0x180033660  mov     r14, rcx
0x180033663  mov     r15, [rsp+0D8h+arg_20]
0x18003366b  xorps   xmm0, xmm0
0x18003366e  xor     eax, eax
0x180033670  movups  xmmword ptr [r8], xmm0
0x180033674  mov     [r8+10h], rax
0x180033678  mov     r11, [rcx+38h]
0x18003367c  xor     ebx, ebx
0x18003367e  mov     [rsp+0D8h+var_98], rbx
0x180033683  test    r15, r15
0x180033686  jnz     loc_1800339E1
0x18003368c  mov     ecx, ebx
0x18003368e  lea     rsi, ?c_rgGetValueHelpers@CPropertyStoreOverFolderFinal@@0QBUPKEYTOGETVALUEHELPER@1@B; CPropertyStoreOverFolderFinal::PKEYTOGETVALUEHELPER const near * const CPropertyStoreOverFolderFinal::c_rgGetValueHelpers
0x180033695  cmp     ecx, 4
0x180033698  jnb     short loc_1800336B4
0x18003369a  mov     r10d, ecx
0x18003369d  add     r10, r10
0x1800336a0  mov     rdx, [rsi+r10*8]
0x1800336a4  mov     eax, [rdi+10h]
0x1800336a7  cmp     [rdx+10h], eax
0x1800336aa  jz      loc_180033763
0x1800336b0  inc     ecx
0x1800336b2  jmp     short loc_180033695
0x1800336b4  mov     ebp, ebx
0x1800336b6  cmp     [r14+44h], ebx
0x1800336ba  jnz     loc_180033837
0x1800336c0  test    byte ptr [r14+40h], 8
0x1800336c5  jnz     loc_18003385D
0x1800336cb  mov     r12, [r14+38h]
0x1800336cf  test    cs:byte_1800F1382, 10h
0x1800336d6  jnz     loc_1800339C9
0x1800336dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800336e0  mov     [rsp+0D8h+var_88], rax
0x1800336e5  mov     [rsp+0D8h+var_80], rax
0x1800336ea  mov     rsi, rbx
0x1800336ed  mov     [rsp+0D8h+var_90], rbx
0x1800336f2  lea     ebx, [rax+1Ah]
0x1800336f5  lea     eax, [rbx-17h]
0x1800336f8  mul     rbx
0x1800336fb  xor     r11d, r11d
0x1800336fe  test    rdx, rdx
0x180033701  jz      loc_1800338CC
0x180033707  mov     edx, r11d
0x18003370a  mov     ebp, 80070216h
0x18003370f  test    ebp, ebp
0x180033711  js      loc_180033821
0x180033717  test    rdx, rdx
0x18003371a  jz      loc_1800339E9
0x180033720  mov     ecx, 18h
0x180033725  lea     r9, aPropstoreoverf; "PropStoreOverFolderFinal"
0x18003372c  mov     r8, rbx
0x18003372f  mov     rax, rdx
0x180033732  mov     r10, r11
0x180033735  test    rcx, rcx
0x180033738  jz      short loc_1800337A6
0x18003373a  movzx   r11d, word ptr [r9]
0x18003373e  cmp     r11w, word ptr [rsp+0D8h+var_98]
0x180033744  jz      short loc_1800337A3
0x180033746  add     r9, 2
0x18003374a  mov     [rax], r11w
0x18003374e  add     rax, 2
0x180033752  dec     rcx
0x180033755  inc     r10
0x180033758  xor     r11d, r11d
0x18003375b  sub     r8, 1
0x18003375f  jnz     short loc_180033735
0x180033761  jmp     short loc_1800337A6
0x180033763  mov     rax, [rdx]
0x180033766  sub     rax, [rdi]
0x180033769  jnz     short loc_180033773
0x18003376b  mov     rax, [rdx+8]
0x18003376f  sub     rax, [rdi+8]
0x180033773  test    rax, rax
0x180033776  jnz     loc_1800336B0
0x18003377c  mov     [rsp+0D8h+var_B0], r15; unsigned __int16 **
0x180033781  mov     [rsp+0D8h+var_B8], r9d; int
0x180033786  mov     r9, r13; struct tagPROPVARIANT *
0x180033789  mov     r8, rdi; struct _tagpropertykey *
0x18003378c  mov     rdx, r11; struct _ITEMID_CHILD *
0x18003378f  mov     rcx, r14; struct CPropertyStoreOverFolderFinal *
0x180033792  mov     rax, ds:(funcs_180033797 - 1800AD8D0h)[rsi+r10*8]
0x180033797  call    _guard_dispatch_icall$thunk$10345483385596137414; CPropertyStoreOverFolderFinal::_GetDisplayNameOf(CPropertyStoreOverFolderFinal *,_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *,int,ushort * *) ...
0x18003379c  mov     ebp, ebx
0x18003379e  jmp     loc_180033837
0x1800337a3  xor     r11d, r11d
0x1800337a6  lea     r9, [r10-1]
0x1800337aa  test    r8, r8
0x1800337ad  cmovnz  r9, r10
0x1800337b1  lea     rcx, [rax-2]
0x1800337b5  cmovnz  rcx, rax
0x1800337b9  mov     [rcx], r11w
0x1800337bd  jnz     loc_180033903
0x1800337c3  xorps   xmm0, xmm0
0x1800337c6  xor     eax, eax
0x1800337c8  movups  xmmword ptr [rsp+0D8h+pVar], xmm0
0x1800337cd  mov     qword ptr [rsp+0D8h+pVar+10h], rax
0x1800337d2  mov     rcx, [r14+30h]
0x1800337d6  mov     rax, [rcx]
0x1800337d9  lea     r9, [rsp+0D8h+pVar]
0x1800337de  mov     r8, rdi
0x1800337e1  mov     rdx, r12
0x1800337e4  mov     rax, [rax+88h]
0x1800337eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337f0  xor     r11d, r11d
0x1800337f3  test    eax, eax
0x1800337f5  js      short loc_180033818
0x1800337f7  mov     rdx, r13; pPropVar
0x1800337fa  lea     rcx, [rsp+0D8h+pVar]; pVar
0x1800337ff  call    VariantToPropVariant
0x180033804  mov     ebx, eax
0x180033806  lea     rcx, [rsp+0D8h+pVar]; pvarg
0x18003380b  call    cs:__imp_VariantClear
0x180033811  xor     r11d, r11d
0x180033814  test    ebx, ebx
0x180033816  js      short loc_180033821
0x180033818  test    r15, r15
0x18003381b  jnz     loc_1800339F2
0x180033821  test    cs:byte_1800F1382, 10h
0x180033828  jnz     loc_180033A00
0x18003382e  test    rsi, rsi
0x180033831  jnz     loc_1800338F5
0x180033837  mov     eax, ebp
0x180033839  mov     rcx, [rsp+0D8h+var_58]
0x180033841  xor     rcx, rsp; StackCookie
0x180033844  call    __security_check_cookie
0x180033849  add     rsp, 98h
0x180033850  pop     r15
0x180033852  pop     r14
0x180033854  pop     r13
0x180033856  pop     r12
0x180033858  pop     rdi
0x180033859  pop     rsi
0x18003385a  pop     rbp
0x18003385b  pop     rbx
0x18003385c  retn
0x18003385d  mov     ecx, [rdi+10h]
0x180033860  cmp     cs:PKEY_FileName.pid, ecx
0x180033866  jz      loc_180033935
0x18003386c  mov     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x180033873  sub     rax, [rdi]
0x180033876  jnz     short loc_180033883
0x180033878  mov     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x18003387f  sub     rax, [rdi+8]
0x180033883  test    rax, rax
0x180033886  jz      loc_1800336CB
0x18003388c  cmp     cs:PKEY_PropList_NonPersonal.pid, ecx
0x180033892  jz      loc_18003395A
0x180033898  cmp     cs:PKEY_PropList_XPDetailsPanel.pid, ecx
0x18003389e  jz      loc_18003397F
0x1800338a4  cmp     cs:PKEY_ItemNameDisplayWithoutExtension.pid, ecx
0x1800338aa  jz      loc_1800339A4
0x1800338b0  mov     r8, rdi; struct _tagpropertykey *
0x1800338b3  mov     rdx, [r14+38h]; struct _ITEMID_CHILD *
0x1800338b7  mov     rcx, r14; this
0x1800338ba  call    ?_IsFastProperty@CPropertyStoreOverFolderFinal@@AEAAHPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@@Z; CPropertyStoreOverFolderFinal::_IsFastProperty(_ITEMID_CHILD const *,_tagpropertykey const &)
0x1800338bf  test    eax, eax
0x1800338c1  jz      loc_180033837
0x1800338c7  jmp     loc_1800336CB
0x1800338cc  mov     rcx, rax; cb
0x1800338cf  call    cs:__imp_CoTaskMemAlloc
0x1800338d5  mov     rsi, rax
0x1800338d8  mov     [rsp+0D8h+var_90], rax
0x1800338dd  neg     rax
0x1800338e0  sbb     ebp, ebp
0x1800338e2  not     ebp
0x1800338e4  and     ebp, 8007000Eh
0x1800338ea  mov     rdx, rsi
0x1800338ed  xor     r11d, r11d
0x1800338f0  jmp     loc_18003370F
0x1800338f5  mov     rcx, rsi; pv
0x1800338f8  call    cs:__imp_CoTaskMemFree
0x1800338fe  jmp     loc_180033837
0x180033903  sub     rbx, r9
0x180033906  cmp     rbx, 1
0x18003390a  jbe     loc_1800337C3
0x180033910  lea     r8, [rbx+rbx]
0x180033914  cmp     r8, 2
0x180033918  jbe     loc_1800337C3
0x18003391e  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180033922  inc     r9
0x180033925  lea     rcx, [rdx+r9*2]; void *
0x180033929  xor     edx, edx; Val
0x18003392b  call    memset_0
0x180033930  jmp     loc_1800337C3
0x180033935  mov     rax, qword ptr cs:PKEY_FileName.fmtid.Data1
0x18003393c  sub     rax, [rdi]
0x18003393f  jnz     short loc_18003394C
0x180033941  mov     rax, qword ptr cs:PKEY_FileName.fmtid.Data4
0x180033948  sub     rax, [rdi+8]
0x18003394c  test    rax, rax
0x18003394f  jnz     loc_18003386C
0x180033955  jmp     loc_1800336CB
0x18003395a  mov     rax, qword ptr cs:PKEY_PropList_NonPersonal.fmtid.Data1
0x180033961  sub     rax, [rdi]
0x180033964  jnz     short loc_180033971
0x180033966  mov     rax, qword ptr cs:PKEY_PropList_NonPersonal.fmtid.Data4
0x18003396d  sub     rax, [rdi+8]
0x180033971  test    rax, rax
0x180033974  jnz     loc_180033898
0x18003397a  jmp     loc_1800336CB
0x18003397f  mov     rax, qword ptr cs:PKEY_PropList_XPDetailsPanel.fmtid.Data1
0x180033986  sub     rax, [rdi]
0x180033989  jnz     short loc_180033996
0x18003398b  mov     rax, qword ptr cs:PKEY_PropList_XPDetailsPanel.fmtid.Data4
0x180033992  sub     rax, [rdi+8]
0x180033996  test    rax, rax
0x180033999  jnz     loc_1800338A4
0x18003399f  jmp     loc_1800336CB
0x1800339a4  mov     rax, qword ptr cs:PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1
0x1800339ab  sub     rax, [rdi]
0x1800339ae  jnz     short loc_1800339BB
0x1800339b0  mov     rax, qword ptr cs:PKEY_ItemNameDisplayWithoutExtension.fmtid.Data4
0x1800339b7  sub     rax, [rdi+8]
0x1800339bb  test    rax, rax
0x1800339be  jnz     loc_1800338B0
0x1800339c4  jmp     loc_1800336CB
0x1800339c9  mov     r9d, [rdi+10h]
0x1800339cd  mov     r8, rdi
0x1800339d0  lea     rdx, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Start
0x1800339d7  call    McTemplateU0jq_EtwEventWriteTransfer
0x1800339dc  jmp     loc_1800336DC
0x1800339e1  mov     [r15], rbx
0x1800339e4  jmp     loc_18003368C
0x1800339e9  mov     [rdx], r11w
0x1800339ed  jmp     loc_1800337C3
0x1800339f2  mov     rax, rsi
0x1800339f5  mov     rsi, r11
0x1800339f8  mov     [r15], rax
0x1800339fb  jmp     loc_180033821
0x180033a00  mov     r9d, [rdi+10h]
0x180033a04  mov     r8, rdi
0x180033a07  lea     rdx, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Stop
0x180033a0e  call    McTemplateU0jq_EtwEventWriteTransfer
0x180033a13  jmp     loc_18003382E
```
