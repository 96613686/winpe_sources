# CPropertyStoreOverFolderFinal::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180033ac0`
- end: `0x180033e3a`
- name: `?GetValue@CPropertyStoreOverFolderFinal@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(CPropertyStoreOverFolderFinal *__hidden this, const struct _tagpropertykey *, PROPVARIANT *pPropVar)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800328b0`
- `0x180033ac0`
- `0x180033e40`
- `0x1800343b0`
- `0x18004e020`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d09`
- `OLEAUT32!__imp_VariantClear` at `0x180033ccd`
- `OLEAUT32!__imp_VariantClear` at `0x180033ccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyStoreOverFolderFinal::GetValue(
        const struct _ITEMID_CHILD **this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *pPropVar)
{
  __int64 i; // rcx
  __int64 v7; // rdx
  DWORD pid; // eax
  __int64 v10; // rax
  const struct _ITEMID_CHILD *v11; // r15
  wchar_t *v12; // rbx
  wchar_t *v13; // r11
  int v14; // ebp
  __int64 v15; // rcx
  const wchar_t *v16; // rdx
  __int64 v17; // r8
  wchar_t *v18; // r9
  __int64 v19; // r10
  wchar_t v20; // ax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  __int64 v23; // r14
  __int64 v24; // rax
  VARIANT pVar; // [rsp+60h] [rbp-58h] BYREF

  *(_OWORD *)pPropVar = 0;
  pPropVar[2] = 0;
  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    v7 = *((_QWORD *)&CPropertyStoreOverFolderFinal::c_rgGetValueHelpers + 2 * (unsigned int)i);
    if ( *(_DWORD *)(v7 + 16) == a2->pid )
    {
      v10 = *(_QWORD *)v7 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)v7 == *(_QWORD *)&a2->fmtid.Data1 )
        v10 = *(_QWORD *)(v7 + 8) - *(_QWORD *)a2->fmtid.Data4;
      if ( !v10 )
      {
        (*(&funcs_180033797 + 2 * (unsigned int)i))(
          (struct CPropertyStoreOverFolderFinal *)this,
          this[7],
          a2,
          (struct tagPROPVARIANT *)pPropVar,
          0,
          0);
        return 0;
      }
    }
  }
  if ( *((_DWORD *)this + 17) )
    return 0;
  if ( ((_BYTE)this[8] & 8) == 0 )
    goto LABEL_20;
  pid = a2->pid;
  if ( PKEY_FileName.pid == pid )
  {
    i = *(_QWORD *)&PKEY_FileName.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_FileName.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      i = *(_QWORD *)PKEY_FileName.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( !i )
      goto LABEL_20;
  }
  i = *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
  if ( *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
    i = *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
  if ( i )
  {
    if ( PKEY_PropList_NonPersonal.pid != pid )
      goto LABEL_12;
    i = *(_QWORD *)&PKEY_PropList_NonPersonal.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_PropList_NonPersonal.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      i = *(_QWORD *)PKEY_PropList_NonPersonal.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( i )
    {
LABEL_12:
      if ( PKEY_PropList_XPDetailsPanel.pid != pid )
        goto LABEL_67;
      i = *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        i = *(_QWORD *)PKEY_PropList_XPDetailsPanel.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( i )
      {
LABEL_67:
        if ( PKEY_ItemNameDisplayWithoutExtension.pid != pid )
          goto LABEL_68;
        v24 = *(_QWORD *)&PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)&PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
          v24 = *(_QWORD *)PKEY_ItemNameDisplayWithoutExtension.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
        if ( v24 )
        {
LABEL_68:
          if ( !(unsigned int)CPropertyStoreOverFolderFinal::_IsFastProperty(
                                (CPropertyStoreOverFolderFinal *)this,
                                this[7],
                                a2) )
            return 0;
        }
      }
    }
  }
LABEL_20:
  v11 = this[7];
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(i, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Start, a2, a2->pid);
  v12 = 0;
  if ( is_mul_ok(0x19u, 2u) )
  {
    v12 = (wchar_t *)CoTaskMemAlloc(0x32u);
    v14 = 0;
    if ( !v12 )
      v14 = -2147024882;
    v13 = v12;
  }
  else
  {
    v13 = 0;
    v14 = -2147024362;
  }
  if ( v14 >= 0 )
  {
    if ( v13 )
    {
      v15 = 24;
      v16 = L"PropStoreOverFolderFinal";
      v17 = 25;
      v18 = v13;
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
      v21 = v19 - 1;
      if ( v17 )
        v21 = v19;
      v22 = v18 - 1;
      if ( v17 )
        v22 = v18;
      *v22 = 0;
      if ( v17 )
      {
        v23 = 25 - v21;
        if ( v21 != 25 && v21 != 24 && (unsigned __int64)(2 * v23) > 2 )
          memset_0(&v13[v21 + 1], 0, 2 * v23 - 2);
      }
    }
    else
    {
      MEMORY[0] = 0;
    }
    memset(&pVar, 0, sizeof(pVar));
    if ( (*(int (__fastcall **)(const struct _ITEMID_CHILD *, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, VARIANT *))(*(_QWORD *)this[6] + 136LL))(
           this[6],
           v11,
           a2,
           &pVar) >= 0 )
    {
      VariantToPropVariant(&pVar, pPropVar);
      VariantClear(&pVar);
    }
  }
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(i, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Stop, a2, a2->pid);
  if ( v12 )
    CoTaskMemFree(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180033ac0  push    rbx
0x180033ac2  push    rbp
0x180033ac3  push    rsi
0x180033ac4  push    rdi
0x180033ac5  push    r13
0x180033ac7  push    r14
0x180033ac9  push    r15
0x180033acb  sub     rsp, 80h
0x180033ad2  mov     rax, cs:__security_cookie
0x180033ad9  xor     rax, rsp
0x180033adc  mov     [rsp+0B8h+var_40], rax
0x180033ae1  mov     r13, r8
0x180033ae4  mov     rdi, rdx
0x180033ae7  mov     rsi, rcx
0x180033aea  xorps   xmm0, xmm0
0x180033aed  xor     eax, eax
0x180033aef  movups  xmmword ptr [r8], xmm0
0x180033af3  mov     [r8+10h], rax
0x180033af7  xor     ecx, ecx
0x180033af9  lea     r11, ?c_rgGetValueHelpers@CPropertyStoreOverFolderFinal@@0QBUPKEYTOGETVALUEHELPER@1@B; CPropertyStoreOverFolderFinal::PKEYTOGETVALUEHELPER const near * const CPropertyStoreOverFolderFinal::c_rgGetValueHelpers
0x180033b00  cmp     ecx, 4
0x180033b03  jnb     short loc_180033B1B
0x180033b05  mov     r10d, ecx
0x180033b08  add     r10, r10
0x180033b0b  mov     rdx, [r11+r10*8]
0x180033b0f  mov     eax, [rdi+10h]
0x180033b12  cmp     [rdx+10h], eax
0x180033b15  jz      short loc_180033B95
0x180033b17  inc     ecx
0x180033b19  jmp     short loc_180033B00
0x180033b1b  xor     ebx, ebx
0x180033b1d  cmp     [rsi+44h], ebx
0x180033b20  jnz     short loc_180033B8E
0x180033b22  test    byte ptr [rsi+40h], 8
0x180033b26  jz      loc_180033BD5
0x180033b2c  mov     eax, [rdi+10h]
0x180033b2f  cmp     cs:PKEY_FileName.pid, eax
0x180033b35  jz      loc_180033D6A
0x180033b3b  mov     rcx, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x180033b42  sub     rcx, [rdi]
0x180033b45  jnz     short loc_180033B52
0x180033b47  mov     rcx, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x180033b4e  sub     rcx, [rdi+8]
0x180033b52  test    rcx, rcx
0x180033b55  jz      short loc_180033BD5
0x180033b57  cmp     cs:PKEY_PropList_NonPersonal.pid, eax
0x180033b5d  jz      loc_180033D8F
0x180033b63  cmp     cs:PKEY_PropList_XPDetailsPanel.pid, eax
0x180033b69  jz      loc_180033DB4
0x180033b6f  cmp     cs:PKEY_ItemNameDisplayWithoutExtension.pid, eax
0x180033b75  jz      loc_180033DD9
0x180033b7b  mov     r8, rdi; struct _tagpropertykey *
0x180033b7e  mov     rdx, [rsi+38h]; struct _ITEMID_CHILD *
0x180033b82  mov     rcx, rsi; this
0x180033b85  call    ?_IsFastProperty@CPropertyStoreOverFolderFinal@@AEAAHPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@@Z; CPropertyStoreOverFolderFinal::_IsFastProperty(_ITEMID_CHILD const *,_tagpropertykey const &)
0x180033b8a  test    eax, eax
0x180033b8c  jnz     short loc_180033BD5
0x180033b8e  mov     eax, ebx
0x180033b90  jmp     loc_180033CE7
0x180033b95  mov     rax, [rdx]
0x180033b98  sub     rax, [rdi]
0x180033b9b  jnz     short loc_180033BA5
0x180033b9d  mov     rax, [rdx+8]
0x180033ba1  sub     rax, [rdi+8]
0x180033ba5  test    rax, rax
0x180033ba8  jnz     loc_180033B17
0x180033bae  mov     [rsp+0B8h+var_90], rax; unsigned __int16 **
0x180033bb3  mov     [rsp+0B8h+var_98], eax; int
0x180033bb7  mov     r9, r13; struct tagPROPVARIANT *
0x180033bba  mov     r8, rdi; struct _tagpropertykey *
0x180033bbd  mov     rdx, [rsi+38h]; struct _ITEMID_CHILD *
0x180033bc1  mov     rcx, rsi; struct CPropertyStoreOverFolderFinal *
0x180033bc4  mov     rax, ds:(funcs_180033797 - 1800AD8D0h)[r11+r10*8]
0x180033bc9  call    _guard_dispatch_icall$thunk$10345483385596137414; CPropertyStoreOverFolderFinal::_GetDisplayNameOf(CPropertyStoreOverFolderFinal *,_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *,int,ushort * *) ...
0x180033bce  xor     eax, eax
0x180033bd0  jmp     loc_180033CE7
0x180033bd5  mov     r15, [rsi+38h]
0x180033bd9  test    cs:byte_1800F1382, 10h
0x180033be0  jnz     loc_180033DFE
0x180033be6  mov     [rsp+0B8h+var_70], 0FFFFFFFFFFFFFFFFh
0x180033bef  mov     [rsp+0B8h+var_68], 0FFFFFFFFFFFFFFFFh
0x180033bf8  xor     ebx, ebx
0x180033bfa  mov     [rsp+0B8h+var_78], rbx
0x180033bff  mov     eax, 2
0x180033c04  mov     r14d, 19h
0x180033c0a  mul     r14
0x180033c0d  test    rdx, rdx
0x180033c10  jz      loc_180033D06
0x180033c16  xor     r11d, r11d
0x180033c19  mov     ebp, 80070216h
0x180033c1e  test    ebp, ebp
0x180033c20  js      loc_180033CD3
0x180033c26  test    r11, r11
0x180033c29  jz      loc_180033E16
0x180033c2f  mov     ecx, 18h
0x180033c34  lea     rdx, aPropstoreoverf; "PropStoreOverFolderFinal"
0x180033c3b  mov     r8, r14
0x180033c3e  mov     r9, r11
0x180033c41  xor     r10d, r10d
0x180033c44  test    rcx, rcx
0x180033c47  jz      short loc_180033C69
0x180033c49  movzx   eax, word ptr [rdx]
0x180033c4c  test    ax, ax
0x180033c4f  jz      short loc_180033C69
0x180033c51  add     rdx, 2
0x180033c55  mov     [r9], ax
0x180033c59  add     r9, 2
0x180033c5d  dec     rcx
0x180033c60  inc     r10
0x180033c63  sub     r8, 1
0x180033c67  jnz     short loc_180033C44
0x180033c69  lea     rdx, [r10-1]
0x180033c6d  test    r8, r8
0x180033c70  cmovnz  rdx, r10
0x180033c74  lea     rcx, [r9-2]
0x180033c78  cmovnz  rcx, r9
0x180033c7c  xor     eax, eax
0x180033c7e  mov     [rcx], ax
0x180033c81  test    r8, r8
0x180033c84  jnz     loc_180033D37
0x180033c8a  xorps   xmm0, xmm0
0x180033c8d  xor     eax, eax
0x180033c8f  movups  xmmword ptr [rsp+0B8h+pVar], xmm0
0x180033c94  mov     qword ptr [rsp+0B8h+pVar+10h], rax
0x180033c99  mov     rcx, [rsi+30h]
0x180033c9d  mov     rax, [rcx]
0x180033ca0  lea     r9, [rsp+0B8h+pVar]
0x180033ca5  mov     r8, rdi
0x180033ca8  mov     rdx, r15
0x180033cab  mov     rax, [rax+88h]
0x180033cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cb7  test    eax, eax
0x180033cb9  js      short loc_180033CD3
0x180033cbb  mov     rdx, r13; pPropVar
0x180033cbe  lea     rcx, [rsp+0B8h+pVar]; pVar
0x180033cc3  call    VariantToPropVariant
0x180033cc8  lea     rcx, [rsp+0B8h+pVar]; pvarg
0x180033ccd  call    cs:__imp_VariantClear
0x180033cd3  test    cs:byte_1800F1382, 10h
0x180033cda  jnz     loc_180033E21
0x180033ce0  test    rbx, rbx
0x180033ce3  jnz     short loc_180033D2C
0x180033ce5  mov     eax, ebp
0x180033ce7  mov     rcx, [rsp+0B8h+var_40]
0x180033cec  xor     rcx, rsp; StackCookie
0x180033cef  call    __security_check_cookie
0x180033cf4  add     rsp, 80h
0x180033cfb  pop     r15
0x180033cfd  pop     r14
0x180033cff  pop     r13
0x180033d01  pop     rdi
0x180033d02  pop     rsi
0x180033d03  pop     rbp
0x180033d04  pop     rbx
0x180033d05  retn
0x180033d06  mov     rcx, rax; cb
0x180033d09  call    cs:__imp_CoTaskMemAlloc
0x180033d0f  mov     rbx, rax
0x180033d12  mov     [rsp+0B8h+var_78], rax
0x180033d17  xor     ebp, ebp
0x180033d19  mov     eax, 8007000Eh
0x180033d1e  test    rbx, rbx
0x180033d21  cmovz   ebp, eax
0x180033d24  mov     r11, rbx
0x180033d27  jmp     loc_180033C1E
0x180033d2c  mov     rcx, rbx; pv
0x180033d2f  call    cs:__imp_CoTaskMemFree
0x180033d35  jmp     short loc_180033CE5
0x180033d37  sub     r14, rdx
0x180033d3a  cmp     r14, 1
0x180033d3e  jbe     loc_180033C8A
0x180033d44  lea     r8, [r14+r14]
0x180033d48  cmp     r8, 2
0x180033d4c  jbe     loc_180033C8A
0x180033d52  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180033d56  lea     rcx, [r11+2]
0x180033d5a  lea     rcx, [rcx+rdx*2]; void *
0x180033d5e  xor     edx, edx; Val
0x180033d60  call    memset_0
0x180033d65  jmp     loc_180033C8A
0x180033d6a  mov     rcx, qword ptr cs:PKEY_FileName.fmtid.Data1
0x180033d71  sub     rcx, [rdi]
0x180033d74  jnz     short loc_180033D81
0x180033d76  mov     rcx, qword ptr cs:PKEY_FileName.fmtid.Data4
0x180033d7d  sub     rcx, [rdi+8]
0x180033d81  test    rcx, rcx
0x180033d84  jnz     loc_180033B3B
0x180033d8a  jmp     loc_180033BD5
0x180033d8f  mov     rcx, qword ptr cs:PKEY_PropList_NonPersonal.fmtid.Data1
0x180033d96  sub     rcx, [rdi]
0x180033d99  jnz     short loc_180033DA6
0x180033d9b  mov     rcx, qword ptr cs:PKEY_PropList_NonPersonal.fmtid.Data4
0x180033da2  sub     rcx, [rdi+8]
0x180033da6  test    rcx, rcx
0x180033da9  jnz     loc_180033B63
0x180033daf  jmp     loc_180033BD5
0x180033db4  mov     rcx, qword ptr cs:PKEY_PropList_XPDetailsPanel.fmtid.Data1
0x180033dbb  sub     rcx, [rdi]
0x180033dbe  jnz     short loc_180033DCB
0x180033dc0  mov     rcx, qword ptr cs:PKEY_PropList_XPDetailsPanel.fmtid.Data4
0x180033dc7  sub     rcx, [rdi+8]
0x180033dcb  test    rcx, rcx
0x180033dce  jnz     loc_180033B6F
0x180033dd4  jmp     loc_180033BD5
0x180033dd9  mov     rax, qword ptr cs:PKEY_ItemNameDisplayWithoutExtension.fmtid.Data1
0x180033de0  sub     rax, [rdi]
0x180033de3  jnz     short loc_180033DF0
0x180033de5  mov     rax, qword ptr cs:PKEY_ItemNameDisplayWithoutExtension.fmtid.Data4
0x180033dec  sub     rax, [rdi+8]
0x180033df0  test    rax, rax
0x180033df3  jnz     loc_180033B7B
0x180033df9  jmp     loc_180033BD5
0x180033dfe  mov     r9d, [rdi+10h]
0x180033e02  mov     r8, rdi
0x180033e05  lea     rdx, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Start
0x180033e0c  call    McTemplateU0jq_EtwEventWriteTransfer
0x180033e11  jmp     loc_180033BE6
0x180033e16  xor     eax, eax
0x180033e18  mov     [r11], ax
0x180033e1c  jmp     loc_180033C8A
0x180033e21  mov     r9d, [rdi+10h]
0x180033e25  mov     r8, rdi
0x180033e28  lea     rdx, ShellTraceId_ItemStoreOverFolder_GetValueFromDetailsEx_Stop
0x180033e2f  call    McTemplateU0jq_EtwEventWriteTransfer
0x180033e34  jmp     loc_180033CE0
```
