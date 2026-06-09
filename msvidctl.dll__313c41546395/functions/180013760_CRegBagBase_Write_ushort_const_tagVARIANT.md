# CRegBagBase::Write(ushort const *,tagVARIANT *)

- ea: `0x180013760`
- end: `0x180013b00`
- name: `?Write@CRegBagBase@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(CRegBagBase *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18001143c`
- `0x18001155c`
- `0x1800130c4`
- `0x180013760`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800138a7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800138a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800138e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800138e1`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800137b2`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001385c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180013968`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001398b`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800137b2`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001385c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180013968`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001398b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180013a1f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180013a1f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013a89`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013a89`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013874`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013aa4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013874`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180013aa4`
- `ADVAPI32!RegSetValueExW` at `0x1800138d6`
- `ADVAPI32!RegSetValueExW` at `0x180013909`
- `ADVAPI32!RegSetValueExW` at `0x1800139cf`
- `ADVAPI32!RegSetValueExW` at `0x180013a6d`
- `ADVAPI32!RegSetValueExW` at `0x180013ac3`
- `ADVAPI32!RegSetValueExW` at `0x1800138d6`
- `ADVAPI32!RegSetValueExW` at `0x180013909`
- `ADVAPI32!RegSetValueExW` at `0x1800139cf`
- `ADVAPI32!RegSetValueExW` at `0x180013a6d`
- `ADVAPI32!RegSetValueExW` at `0x180013ac3`

## pseudocode

```c
HRESULT __fastcall CRegBagBase::Write(CRegBagBase *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  unsigned __int64 vt; // rcx
  LSTATUS v7; // edi
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  CRegBagBase *v12; // rcx
  HRESULT result; // eax
  UINT v14; // eax
  UINT v15; // edi
  DWORD v16; // esi
  HKEY *v17; // r15
  BYTE *lpData; // rbx
  CRegBagBase *v19; // rcx
  struct ATL::CRegKey *v20; // rdx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  SAFEARRAY *parray; // rcx
  BSTR bstrVal; // r9
  int v30; // r8d
  int i; // edx
  CRegBagBase *v32; // rcx
  const BYTE *pbVal; // rbx
  UINT cbData; // [rsp+28h] [rbp-30h]
  void *ppvData; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return -2147467261;
  if ( (a3->vt & 0x4000) != 0 && VariantChangeType(a3, a3, 0, a3->vt & 0xBFFF) < 0 )
    return -2147024809;
  vt = a3->vt;
  v7 = 0;
  if ( (unsigned int)vt <= 0xFFF )
  {
    if ( (_DWORD)vt != 4095 )
    {
      if ( (unsigned int)vt <= 0x10 )
      {
        if ( (_DWORD)vt != 16 )
        {
          if ( !a3->vt || (vt = (unsigned int)(vt - 1), !(_DWORD)vt) )
          {
            CRegBagBase::DeleteValue((CRegBagBase *)vt, (CRegBagBase *)((char *)this + 88), a2);
LABEL_56:
            v20 = (CRegBagBase *)((char *)this + 88);
LABEL_57:
            CRegBagBase::DeleteSubKey(v19, v20, a2);
            return v7;
          }
          v8 = vt - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 5;
              if ( !v10 )
              {
                v14 = SysStringByteLen(a3->bstrVal);
                if ( v14 >= 2 && ((v14 & 1) != 0 || *(_WORD *)(a3->llVal + 2 * ((unsigned __int64)v14 >> 1) - 2)) )
                {
                  v15 = v14 + 1;
                  v16 = ((v14 + 1) & 0xFFFFFFFE) + 2;
                  v17 = (HKEY *)((char *)this + 88);
                  lpData = (BYTE *)SysAllocStringLen(a3->bstrVal, v16 >> 1);
                  *(_WORD *)&lpData[2 * ((unsigned __int64)v15 >> 1)] = 0;
                  v7 = RegSetValueExW(*v17, a2, 0, 1u, lpData, v16);
                  SysFreeString((BSTR)lpData);
                }
                else
                {
                  v17 = (HKEY *)((char *)this + 88);
                  v7 = RegSetValueExW(*v17, a2, 0, 1u, a3->pbVal, v14);
                }
                if ( v7 )
                  return v7;
                v20 = (struct ATL::CRegKey *)v17;
                goto LABEL_57;
              }
              v11 = v10 - 1;
              if ( !v11 )
              {
                if ( VariantChangeType(a3, a3, 0, 0xDu) < 0 )
                  return -2147418113;
                goto LABEL_17;
              }
              v12 = (CRegBagBase *)(unsigned int)(v11 - 2);
              if ( (_DWORD)v12 )
              {
                if ( (_DWORD)v12 == 2 )
                {
LABEL_17:
                  CRegBagBase::DeleteValue(v12, (CRegBagBase *)((char *)this + 88), a2);
                  return CRegBagBase::SaveObject(this, (CRegBagBase *)((char *)this + 88), a2, a3);
                }
                return -2147024809;
              }
            }
          }
        }
        goto LABEL_34;
      }
      v21 = vt - 17;
      if ( !v21 || (v22 = v21 - 1) == 0 )
      {
LABEL_34:
        if ( VariantChangeType(a3, a3, 0, 0x13u) < 0 )
          return -2147024809;
        goto LABEL_38;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
LABEL_38:
        v27 = RegSetValueExW(*((HKEY *)this + 11), a2, 0, 4u, &a3->bVal, 4u);
        v7 = v27;
        if ( v27 )
        {
          if ( v27 > 0 )
            return (unsigned __int16)v27 | 0x80070000;
          return v7;
        }
        goto LABEL_56;
      }
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          if ( (unsigned int)(v25 - 1) > 1 )
            return -2147024809;
          goto LABEL_34;
        }
      }
      else if ( VariantChangeType(a3, a3, 0, 0x15u) < 0 )
      {
        return -2147024809;
      }
      v26 = RegSetValueExW(*((HKEY *)this + 11), a2, 0, 0xBu, &a3->bVal, 8u);
LABEL_55:
      v7 = v26;
      if ( v26 )
        return v7;
      goto LABEL_56;
    }
LABEL_53:
    pbVal = a3->pbVal;
    if ( !pbVal )
      return v7;
    cbData = SysStringByteLen(a3->bstrVal);
    v26 = RegSetValueExW(*((HKEY *)this + 11), a2, 0, 3u, pbVal, cbData);
    goto LABEL_55;
  }
  if ( (_DWORD)vt == 4104 )
    goto LABEL_53;
  if ( (_DWORD)vt != 8209 )
    return -2147024809;
  parray = a3->parray;
  ppvData = 0;
  if ( !parray )
    return v7;
  result = SafeArrayAccessData(parray, &ppvData);
  if ( result >= 0 )
  {
    bstrVal = a3->bstrVal;
    v30 = 0;
    for ( i = *bstrVal; i; v30 += *(_DWORD *)&bstrVal[4 * i + 12] )
      --i;
    v7 = RegSetValueExW(*((HKEY *)this + 11), a2, 0, 3u, (const BYTE *)ppvData, *((_DWORD *)bstrVal + 1) * v30);
    if ( !v7 )
      CRegBagBase::DeleteSubKey(v32, (CRegBagBase *)((char *)this + 88), a2);
    SafeArrayUnaccessData(a3->parray);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180013760  mov     [rsp+arg_0], rbx
0x180013765  mov     [rsp+arg_10], rbp
0x18001376a  push    rsi
0x18001376b  push    rdi
0x18001376c  push    r12
0x18001376e  push    r14
0x180013770  push    r15
0x180013772  sub     rsp, 30h
0x180013776  xor     r12d, r12d
0x180013779  mov     r14, r8
0x18001377c  mov     rbp, rdx
0x18001377f  mov     r15, rcx
0x180013782  test    rdx, rdx
0x180013785  jz      loc_180013AE4
0x18001378b  test    r8, r8
0x18001378e  jz      loc_180013AE4
0x180013794  movzx   r9d, word ptr [r8]
0x180013798  bt      r9w, 0Eh
0x18001379e  jnb     short loc_1800137C0
0x1800137a0  mov     eax, 0BFFFh
0x1800137a5  xor     r8d, r8d; wFlags
0x1800137a8  and     r9w, ax; vt
0x1800137ac  mov     rdx, r14; pvarSrc
0x1800137af  mov     rcx, r14; pvargDest
0x1800137b2  call    cs:__imp_VariantChangeType
0x1800137b8  test    eax, eax
0x1800137ba  js      loc_180013972
0x1800137c0  movzx   ecx, word ptr [r14]; this
0x1800137c4  mov     eax, 0FFFh
0x1800137c9  mov     edi, r12d
0x1800137cc  cmp     ecx, eax
0x1800137ce  ja      loc_1800139F1
0x1800137d4  jz      loc_180013A94
0x1800137da  cmp     ecx, 10h
0x1800137dd  ja      loc_180013932
0x1800137e3  jz      loc_180013959
0x1800137e9  test    ecx, ecx
0x1800137eb  jz      loc_180013921
0x1800137f1  sub     ecx, 1
0x1800137f4  jz      loc_180013921
0x1800137fa  sub     ecx, 1
0x1800137fd  jz      loc_180013959
0x180013803  sub     ecx, 1
0x180013806  jz      loc_180013959
0x18001380c  sub     ecx, 5
0x18001380f  jz      short loc_180013870
0x180013811  sub     ecx, 1
0x180013814  jz      short loc_18001384D
0x180013816  sub     ecx, 2; this
0x180013819  jz      loc_180013959
0x18001381f  cmp     ecx, 2
0x180013822  jnz     loc_180013A05
0x180013828  mov     r8, rbp; unsigned __int16 *
0x18001382b  lea     rdx, [r15+58h]; struct ATL::CRegKey *
0x18001382f  call    ?DeleteValue@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBG@Z; CRegBagBase::DeleteValue(ATL::CRegKey &,ushort const *)
0x180013834  mov     r9, r14; struct tagVARIANT *
0x180013837  lea     rdx, [r15+58h]; struct ATL::CRegKey *
0x18001383b  mov     r8, rbp; unsigned __int16 *
0x18001383e  mov     rcx, r15; this
0x180013841  call    ?SaveObject@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBGPEAUtagVARIANT@@@Z; CRegBagBase::SaveObject(ATL::CRegKey &,ushort const *,tagVARIANT *)
0x180013846  mov     edi, eax
0x180013848  jmp     loc_1800139EA
0x18001384d  mov     r9d, 0Dh; vt
0x180013853  xor     r8d, r8d; wFlags
0x180013856  mov     rdx, r14; pvarSrc
0x180013859  mov     rcx, r14; pvargDest
0x18001385c  call    cs:__imp_VariantChangeType
0x180013862  test    eax, eax
0x180013864  jns     short loc_180013828
0x180013866  mov     eax, 8000FFFFh
0x18001386b  jmp     loc_180013AE9
0x180013870  mov     rcx, [r14+8]; bstr
0x180013874  call    cs:__imp_SysStringByteLen
0x18001387a  cmp     eax, 2
0x18001387d  jb      short loc_1800138E9
0x18001387f  test    al, 1
0x180013881  jnz     short loc_180013894
0x180013883  mov     rcx, [r14+8]
0x180013887  mov     edx, eax
0x180013889  shr     rdx, 1
0x18001388c  cmp     [rcx+rdx*2-2], r12w
0x180013892  jz      short loc_1800138E9
0x180013894  mov     rcx, [r14+8]; strIn
0x180013898  lea     edi, [rax+1]
0x18001389b  mov     esi, edi
0x18001389d  and     esi, 0FFFFFFFEh
0x1800138a0  add     esi, 2
0x1800138a3  mov     edx, esi
0x1800138a5  shr     edx, 1; ui
0x1800138a7  call    cs:__imp_SysAllocStringLen
0x1800138ad  mov     ecx, edi
0x1800138af  add     r15, 58h ; 'X'
0x1800138b3  shr     rcx, 1
0x1800138b6  mov     r9d, 1; dwType
0x1800138bc  mov     [rsp+58h+cbData], esi; cbData
0x1800138c0  xor     r8d, r8d; Reserved
0x1800138c3  mov     rdx, rbp; lpValueName
0x1800138c6  mov     [rsp+58h+lpData], rax; lpData
0x1800138cb  mov     rbx, rax
0x1800138ce  mov     [rax+rcx*2], r12w
0x1800138d3  mov     rcx, [r15]; hKey
0x1800138d6  call    cs:__imp_RegSetValueExW
0x1800138dc  mov     rcx, rbx; bstrString
0x1800138df  mov     edi, eax
0x1800138e1  call    cs:__imp_SysFreeString
0x1800138e7  jmp     short loc_180013911
0x1800138e9  mov     [rsp+58h+cbData], eax; cbData
0x1800138ed  add     r15, 58h ; 'X'
0x1800138f1  mov     rax, [r14+8]
0x1800138f5  mov     r9d, 1; dwType
0x1800138fb  xor     r8d, r8d; Reserved
0x1800138fe  mov     [rsp+58h+lpData], rax; lpData
0x180013903  mov     rdx, rbp; lpValueName
0x180013906  mov     rcx, [r15]; hKey
0x180013909  call    cs:__imp_RegSetValueExW
0x18001390f  mov     edi, eax
0x180013911  test    edi, edi
0x180013913  jnz     loc_1800139EA
0x180013919  mov     rdx, r15
0x18001391c  jmp     loc_180013AD7
0x180013921  mov     r8, rbp; unsigned __int16 *
0x180013924  lea     rdx, [r15+58h]; struct ATL::CRegKey *
0x180013928  call    ?DeleteValue@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBG@Z; CRegBagBase::DeleteValue(ATL::CRegKey &,ushort const *)
0x18001392d  jmp     loc_180013AD3
0x180013932  sub     ecx, 11h
0x180013935  jz      short loc_180013959
0x180013937  sub     ecx, 1
0x18001393a  jz      short loc_180013959
0x18001393c  sub     ecx, 1
0x18001393f  jz      short loc_1800139B1
0x180013941  sub     ecx, 1
0x180013944  jz      short loc_18001397C
0x180013946  sub     ecx, 1
0x180013949  jz      short loc_180013995
0x18001394b  sub     ecx, 1
0x18001394e  jz      short loc_180013959
0x180013950  cmp     ecx, 1
0x180013953  jnz     loc_180013A05
0x180013959  mov     r9d, 13h; vt
0x18001395f  xor     r8d, r8d; wFlags
0x180013962  mov     rdx, r14; pvarSrc
0x180013965  mov     rcx, r14; pvargDest
0x180013968  call    cs:__imp_VariantChangeType
0x18001396e  test    eax, eax
0x180013970  jns     short loc_1800139B1
0x180013972  mov     eax, 80070057h
0x180013977  jmp     loc_180013AE9
0x18001397c  mov     r9d, 15h; vt
0x180013982  xor     r8d, r8d; wFlags
0x180013985  mov     rdx, r14; pvarSrc
0x180013988  mov     rcx, r14; pvargDest
0x18001398b  call    cs:__imp_VariantChangeType
0x180013991  test    eax, eax
0x180013993  js      short loc_180013972
0x180013995  lea     rax, [r14+8]
0x180013999  mov     [rsp+58h+cbData], 8
0x1800139a1  mov     [rsp+58h+lpData], rax
0x1800139a6  mov     r9d, 0Bh
0x1800139ac  jmp     loc_180013AB9
0x1800139b1  mov     rcx, [r15+58h]; hKey
0x1800139b5  lea     rax, [r14+8]
0x1800139b9  mov     r9d, 4; dwType
0x1800139bf  xor     r8d, r8d; Reserved
0x1800139c2  mov     [rsp+58h+cbData], r9d; cbData
0x1800139c7  mov     rdx, rbp; lpValueName
0x1800139ca  mov     [rsp+58h+lpData], rax; lpData
0x1800139cf  call    cs:__imp_RegSetValueExW
0x1800139d5  mov     edi, eax
0x1800139d7  test    eax, eax
0x1800139d9  jz      loc_180013AD3
0x1800139df  jle     short loc_1800139EA
0x1800139e1  movzx   edi, ax
0x1800139e4  or      edi, 80070000h
0x1800139ea  mov     eax, edi
0x1800139ec  jmp     loc_180013AE9
0x1800139f1  cmp     ecx, 1008h
0x1800139f7  jz      loc_180013A94
0x1800139fd  cmp     ecx, 2011h
0x180013a03  jz      short loc_180013A0C
0x180013a05  mov     edi, 80070057h
0x180013a0a  jmp     short loc_1800139EA
0x180013a0c  mov     rcx, [r14+8]; psa
0x180013a10  mov     [rsp+58h+ppvData], r12
0x180013a15  test    rcx, rcx
0x180013a18  jz      short loc_1800139EA
0x180013a1a  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180013a1f  call    cs:__imp_SafeArrayAccessData
0x180013a25  test    eax, eax
0x180013a27  js      loc_180013AE9
0x180013a2d  mov     r9, [r14+8]
0x180013a31  mov     r8, r12
0x180013a34  movzx   edx, word ptr [r9]
0x180013a38  jmp     short loc_180013A47
0x180013a3a  dec     edx
0x180013a3c  movsxd  rax, edx
0x180013a3f  mov     ecx, [r9+rax*8+18h]
0x180013a44  add     r8, rcx
0x180013a47  test    edx, edx
0x180013a49  jnz     short loc_180013A3A
0x180013a4b  imul    r8d, [r9+4]
0x180013a50  lea     r9d, [rdx+3]; dwType
0x180013a54  mov     rax, [rsp+58h+ppvData]
0x180013a59  mov     rdx, rbp; lpValueName
0x180013a5c  mov     rcx, [r15+58h]; hKey
0x180013a60  mov     [rsp+58h+cbData], r8d; cbData
0x180013a65  xor     r8d, r8d; Reserved
0x180013a68  mov     [rsp+58h+lpData], rax; lpData
0x180013a6d  call    cs:__imp_RegSetValueExW
0x180013a73  mov     edi, eax
0x180013a75  test    eax, eax
0x180013a77  jnz     short loc_180013A85
0x180013a79  mov     r8, rbp; unsigned __int16 *
0x180013a7c  lea     rdx, [r15+58h]; struct ATL::CRegKey *
0x180013a80  call    ?DeleteSubKey@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBG@Z; CRegBagBase::DeleteSubKey(ATL::CRegKey &,ushort const *)
0x180013a85  mov     rcx, [r14+8]; psa
0x180013a89  call    cs:__imp_SafeArrayUnaccessData
0x180013a8f  jmp     loc_1800139EA
0x180013a94  mov     rbx, [r14+8]
0x180013a98  test    rbx, rbx
0x180013a9b  jz      loc_1800139EA
0x180013aa1  mov     rcx, rbx; bstr
0x180013aa4  call    cs:__imp_SysStringByteLen
0x180013aaa  mov     [rsp+58h+cbData], eax; cbData
0x180013aae  mov     r9d, 3; dwType
0x180013ab4  mov     [rsp+58h+lpData], rbx; lpData
0x180013ab9  mov     rcx, [r15+58h]; hKey
0x180013abd  xor     r8d, r8d; Reserved
0x180013ac0  mov     rdx, rbp; lpValueName
0x180013ac3  call    cs:__imp_RegSetValueExW
0x180013ac9  mov     edi, eax
0x180013acb  test    eax, eax
0x180013acd  jnz     loc_1800139EA
0x180013ad3  lea     rdx, [r15+58h]; struct ATL::CRegKey *
0x180013ad7  mov     r8, rbp; unsigned __int16 *
0x180013ada  call    ?DeleteSubKey@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBG@Z; CRegBagBase::DeleteSubKey(ATL::CRegKey &,ushort const *)
0x180013adf  jmp     loc_1800139EA
0x180013ae4  mov     eax, 80004003h
0x180013ae9  mov     rbx, [rsp+58h+arg_0]
0x180013aee  mov     rbp, [rsp+58h+arg_10]
0x180013af3  add     rsp, 30h
0x180013af7  pop     r15
0x180013af9  pop     r14
0x180013afb  pop     r12
0x180013afd  pop     rdi
0x180013afe  pop     rsi
0x180013aff  retn
```
