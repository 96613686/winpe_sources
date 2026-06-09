# NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)

- ea: `0x180004b00`
- end: `0x180004eb0`
- name: `?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z`
- size: `944`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, unsigned __int16 **, unsigned __int16 **, int)`
- caller_count: `30`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180001310`
- `0x1800014e0`
- `0x180001668`
- `0x180001810`
- `0x180002734`
- `0x1800029d0`
- `0x180003380`
- `0x1800034a4`
- `0x180003c20`
- `0x180003ee0`
- `0x180005b10`
- `0x180009860`
- `0x18000e460`
- `0x18001b7b0`
- `0x18001cbc4`
- `0x18001ccc8`
- `0x18001ced0`
- `0x18001d30c`
- `0x18001d878`
- `0x18001ddc4`
- `0x18001ee20`
- `0x18001f120`
- `0x18001f7c0`
- `0x18001f850`
- `0x18001fb60`
- `0x1800200fc`
- `0x180020324`
- `0x180021070`
- `0x180021484`
- `0x180021a90`

## callees

- `0x180004b00`
- `0x1800057f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004de6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004de6`
- `OLEAUT32!__imp_SysAllocString` at `0x180004cf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180004e01`
- `OLEAUT32!__imp_SysAllocString` at `0x180004cf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180004e01`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004d44`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004e3f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004d44`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004e3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180004b77`
- `OLEAUT32!__imp_SysFreeString` at `0x180004b83`
- `OLEAUT32!__imp_SysFreeString` at `0x180004c14`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180004dbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180004b77`
- `OLEAUT32!__imp_SysFreeString` at `0x180004b83`
- `OLEAUT32!__imp_SysFreeString` at `0x180004c14`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180004dbd`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        int a5)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v10; // edi
  unsigned __int16 *v11; // rdx
  OLECHAR *v12; // rbx
  UINT v14; // edx
  __int64 v15; // rax
  OLECHAR *v16; // rsi
  _QWORD *v17; // r12
  int v18; // ebx
  __int64 v19; // rcx
  bool v20; // sf
  wchar_t *v21; // rax
  const OLECHAR *v22; // rax
  unsigned __int16 *v23; // rax
  int v24; // eax
  unsigned __int16 *v25; // rax
  int v26; // [rsp+30h] [rbp-30h]
  BSTR bstrString; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+48h] [rbp-18h] BYREF
  __int64 v30; // [rsp+50h] [rbp-10h] BYREF
  UINT v31; // [rsp+A8h] [rbp+48h] BYREF

  if ( !a4 || !a3 || !a2 )
    return 2147942487LL;
  *a4 = 0;
  *a3 = 0;
  lpVtbl = a2->lpVtbl;
  v30 = 0;
  v28 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))lpVtbl->get_attributes)(a2, &v30);
  if ( v10 < 0
    || v30
    && (v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v30 + 56LL))(
                v30,
                L"name",
                &v28),
        v10 < 0) )
  {
LABEL_5:
    SysFreeString(*a3);
    *a3 = 0;
    SysFreeString(*a4);
    *a4 = 0;
LABEL_16:
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    goto LABEL_18;
  }
  if ( v28 )
  {
    v29 = 0;
    bstrString = 0;
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v28)(v28, &IID_IXMLDOMAttribute, &v29);
    if ( v10 < 0 )
      goto LABEL_10;
    v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 208LL))(v29, &bstrString);
    if ( v10 < 0 )
      goto LABEL_10;
    v12 = bstrString;
    if ( a5 && (!bstrString || !(unsigned int)NPrintTicketUtil::IsValidQName((NPrintTicketUtil *)bstrString, v11)) )
    {
      v10 = -2147221501;
      goto LABEL_11;
    }
    if ( !v12 )
      goto LABEL_13;
    v26 = 0;
    v14 = 0;
    *a3 = 0;
    v15 = -1;
    v31 = 0;
    do
      ++v15;
    while ( v12[v15] );
    v10 = -2147024882;
    if ( (int)v15 > 0 )
    {
      while ( v12[v14] != 58 )
      {
        if ( (int)++v14 >= (int)v15 )
          goto LABEL_30;
      }
      v16 = SysAllocStringLen(v12, v14);
      if ( !v16 )
        goto LABEL_31;
    }
    else
    {
LABEL_30:
      v16 = SysAllocString(&psz);
      if ( !v16 )
      {
LABEL_31:
        v17 = (_QWORD *)((char *)this + 16);
LABEL_32:
        v18 = -2147024882;
        goto LABEL_33;
      }
    }
    v19 = *((_QWORD *)this + 2);
    v17 = (_QWORD *)((char *)this + 16);
    v18 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMElement *, __int64))(*(_QWORD *)v19 + 56LL))(v19, a2, 1);
    if ( v18 >= 0 )
    {
      v26 = 1;
      v18 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, UINT *))(*(_QWORD *)*v17 + 96LL))(
              *v17,
              v16,
              0,
              0,
              &v31);
    }
    v20 = v18 < 0;
    if ( !v18 )
    {
      v25 = SysAllocStringLen(0, ++v31);
      *a3 = v25;
      if ( !v25 )
        goto LABEL_32;
      v18 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, unsigned __int16 *, UINT *))(*(_QWORD *)*v17 + 96LL))(
              *v17,
              v16,
              0,
              v25,
              &v31);
      v20 = v18 < 0;
    }
    if ( !v20 )
    {
LABEL_43:
      if ( v26 )
      {
        v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 64LL))(*v17);
        if ( v24 < 0 )
          v18 = v24;
      }
      if ( v16 )
        SysFreeString(v16);
      if ( v18 < 0 )
      {
        v10 = v18;
LABEL_10:
        v12 = bstrString;
        goto LABEL_11;
      }
      v12 = bstrString;
      if ( *a3 )
      {
        if ( bstrString )
        {
          v21 = wcschr(bstrString, 0x3Au);
          *a4 = 0;
          if ( v21 )
            v22 = v21 + 1;
          else
            v22 = v12;
          v23 = SysAllocString(v22);
          *a4 = v23;
          if ( v23 )
            v10 = 0;
          goto LABEL_10;
        }
        v10 = -2147024809;
      }
      else
      {
        v10 = -2147221501;
      }
LABEL_11:
      if ( v12 )
      {
        SysFreeString(v12);
        bstrString = 0;
      }
LABEL_13:
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v10 >= 0 )
        goto LABEL_16;
      goto LABEL_5;
    }
LABEL_33:
    if ( *a3 )
    {
      SysFreeString(*a3);
      *a3 = 0;
    }
    goto LABEL_43;
  }
LABEL_18:
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180004b00  mov     [rsp-28h+arg_10], rdi
0x180004b05  push    rbp
0x180004b06  push    r12
0x180004b08  push    r13
0x180004b0a  push    r14
0x180004b0c  push    r15
0x180004b0e  mov     rbp, rsp
0x180004b11  sub     rsp, 60h
0x180004b15  mov     r15, r9
0x180004b18  mov     r14, r8
0x180004b1b  mov     r13, rdx
0x180004b1e  mov     r12, rcx
0x180004b21  test    r9, r9
0x180004b24  jz      loc_180004E9A
0x180004b2a  test    r8, r8
0x180004b2d  jz      loc_180004E9A
0x180004b33  test    rdx, rdx
0x180004b36  jz      loc_180004E9A
0x180004b3c  mov     [rsp+60h+arg_8], rsi
0x180004b44  mov     rcx, r13
0x180004b47  xor     esi, esi
0x180004b49  mov     [r9], rsi
0x180004b4c  mov     [r8], rsi
0x180004b4f  mov     rax, [rdx]
0x180004b52  lea     rdx, [rbp+var_10]
0x180004b56  mov     [rbp+var_10], rsi
0x180004b5a  mov     [rbp+var_20], rsi
0x180004b5e  mov     rax, [rax+88h]
0x180004b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6a  mov     edi, eax
0x180004b6c  test    eax, eax
0x180004b6e  jns     loc_180004C91
0x180004b74  mov     rcx, [r14]; bstrString
0x180004b77  call    cs:__imp_SysFreeString
0x180004b7d  mov     [r14], rsi
0x180004b80  mov     rcx, [r15]; bstrString
0x180004b83  call    cs:__imp_SysFreeString
0x180004b89  mov     [r15], rsi
0x180004b8c  jmp     loc_180004C43
0x180004b91  mov     rax, [rcx]
0x180004b94  lea     r8, [rbp+var_20]
0x180004b98  lea     rdx, aName; "name"
0x180004b9f  mov     rax, [rax+38h]
0x180004ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba8  mov     edi, eax
0x180004baa  test    eax, eax
0x180004bac  js      short loc_180004B74
0x180004bae  mov     rcx, [rbp+var_20]
0x180004bb2  test    rcx, rcx
0x180004bb5  jz      loc_180004C5C
0x180004bbb  mov     [rbp+var_18], rsi
0x180004bbf  lea     r8, [rbp+var_18]
0x180004bc3  mov     [rbp+bstrString], rsi
0x180004bc7  lea     rdx, IID_IXMLDOMAttribute
0x180004bce  mov     rax, [rcx]
0x180004bd1  mov     [rsp+60h+arg_0], rbx
0x180004bd9  mov     rax, [rax]
0x180004bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be1  mov     edi, eax
0x180004be3  test    eax, eax
0x180004be5  js      short loc_180004C08
0x180004be7  mov     rcx, [rbp+var_18]
0x180004beb  lea     rdx, [rbp+bstrString]
0x180004bef  mov     rax, [rcx]
0x180004bf2  mov     rax, [rax+0D0h]
0x180004bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bfe  mov     edi, eax
0x180004c00  test    eax, eax
0x180004c02  jns     loc_180004CA3
0x180004c08  mov     rbx, [rbp+bstrString]
0x180004c0c  test    rbx, rbx
0x180004c0f  jz      short loc_180004C1E
0x180004c11  mov     rcx, rbx; bstrString
0x180004c14  call    cs:__imp_SysFreeString
0x180004c1a  mov     [rbp+bstrString], rsi
0x180004c1e  mov     rcx, [rbp+var_18]
0x180004c22  mov     rbx, [rsp+60h+arg_0]
0x180004c2a  test    rcx, rcx
0x180004c2d  jz      short loc_180004C3B
0x180004c2f  mov     rax, [rcx]
0x180004c32  mov     rax, [rax+10h]
0x180004c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3b  test    edi, edi
0x180004c3d  js      loc_180004B74
0x180004c43  mov     rcx, [rbp+var_20]
0x180004c47  test    rcx, rcx
0x180004c4a  jz      short loc_180004C5C
0x180004c4c  mov     rax, [rcx]
0x180004c4f  mov     rax, [rax+10h]
0x180004c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c58  mov     [rbp+var_20], rsi
0x180004c5c  mov     rcx, [rbp+var_10]
0x180004c60  mov     rsi, [rsp+60h+arg_8]
0x180004c68  test    rcx, rcx
0x180004c6b  jz      short loc_180004C79
0x180004c6d  mov     rax, [rcx]
0x180004c70  mov     rax, [rax+10h]
0x180004c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c79  mov     eax, edi
0x180004c7b  mov     rdi, [rsp+60h+arg_10]
0x180004c83  add     rsp, 60h
0x180004c87  pop     r15
0x180004c89  pop     r14
0x180004c8b  pop     r13
0x180004c8d  pop     r12
0x180004c8f  pop     rbp
0x180004c90  retn
0x180004c91  mov     rcx, [rbp+var_10]
0x180004c95  test    rcx, rcx
0x180004c98  jnz     loc_180004B91
0x180004c9e  jmp     loc_180004BAE
0x180004ca3  mov     rbx, [rbp+bstrString]
0x180004ca7  cmp     [rbp+arg_20], esi
0x180004caa  jz      short loc_180004CC5
0x180004cac  test    rbx, rbx
0x180004caf  jz      loc_180004E7C
0x180004cb5  mov     rcx, rbx; this
0x180004cb8  call    ?IsValidQName@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidQName(ushort *)
0x180004cbd  test    eax, eax
0x180004cbf  jz      loc_180004E7C
0x180004cc5  test    rbx, rbx
0x180004cc8  jz      loc_180004C1E
0x180004cce  mov     [rbp+var_30], esi
0x180004cd1  mov     edx, esi; ui
0x180004cd3  mov     [r14], rsi
0x180004cd6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004cdd  mov     [rbp+arg_18], esi
0x180004ce0  inc     rax
0x180004ce3  cmp     [rbx+rax*2], dx
0x180004ce7  jnz     short loc_180004CE0
0x180004ce9  mov     edi, 8007000Eh
0x180004cee  test    eax, eax
0x180004cf0  jg      short loc_180004D30
0x180004cf2  lea     rcx, psz; psz
0x180004cf9  call    cs:__imp_SysAllocString
0x180004cff  mov     rsi, rax
0x180004d02  test    rax, rax
0x180004d05  jnz     short loc_180004D52
0x180004d07  add     r12, 10h
0x180004d0b  mov     ebx, edi
0x180004d0d  mov     rcx, [r14]; bstrString
0x180004d10  test    rcx, rcx
0x180004d13  jz      loc_180004DAF
0x180004d19  call    cs:__imp_SysFreeString
0x180004d1f  mov     qword ptr [r14], 0
0x180004d26  jmp     loc_180004DAF
0x180004d30  mov     ecx, edx
0x180004d32  cmp     word ptr [rbx+rcx*2], 3Ah ; ':'
0x180004d37  jz      short loc_180004D41
0x180004d39  inc     edx
0x180004d3b  cmp     edx, eax
0x180004d3d  jl      short loc_180004D30
0x180004d3f  jmp     short loc_180004CF2
0x180004d41  mov     rcx, rbx; strIn
0x180004d44  call    cs:__imp_SysAllocStringLen
0x180004d4a  mov     rsi, rax
0x180004d4d  test    rax, rax
0x180004d50  jz      short loc_180004D07
0x180004d52  mov     rcx, [r12+10h]
0x180004d57  add     r12, 10h
0x180004d5b  mov     r8d, 1
0x180004d61  mov     rdx, r13
0x180004d64  mov     rax, [rcx]
0x180004d67  mov     rax, [rax+38h]
0x180004d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d70  mov     ebx, eax
0x180004d72  test    eax, eax
0x180004d74  js      short loc_180004DA1
0x180004d76  mov     rcx, [r12]
0x180004d7a  lea     rdx, [rbp+arg_18]
0x180004d7e  mov     [rsp+60h+var_40], rdx
0x180004d83  xor     r9d, r9d
0x180004d86  xor     r8d, r8d
0x180004d89  mov     [rbp+var_30], 1
0x180004d90  mov     rdx, rsi
0x180004d93  mov     rax, [rcx]
0x180004d96  mov     rax, [rax+60h]
0x180004d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9f  mov     ebx, eax
0x180004da1  test    ebx, ebx
0x180004da3  jz      loc_180004E35
0x180004da9  js      loc_180004D0D
0x180004daf  cmp     [rbp+var_30], 0
0x180004db3  jnz     short loc_180004E1E
0x180004db5  test    rsi, rsi
0x180004db8  jz      short loc_180004DC3
0x180004dba  mov     rcx, rsi; bstrString
0x180004dbd  call    cs:__imp_SysFreeString
0x180004dc3  test    ebx, ebx
0x180004dc5  js      short loc_180004E15
0x180004dc7  cmp     qword ptr [r14], 0
0x180004dcb  mov     rbx, [rbp+bstrString]
0x180004dcf  jz      loc_180004EA4
0x180004dd5  test    rbx, rbx
0x180004dd8  jz      loc_180004E86
0x180004dde  mov     edx, 3Ah ; ':'; Ch
0x180004de3  mov     rcx, rbx; Str
0x180004de6  call    cs:__imp_wcschr
0x180004dec  xor     esi, esi
0x180004dee  mov     [r15], rsi
0x180004df1  test    rax, rax
0x180004df4  jz      loc_180004E92
0x180004dfa  add     rax, 2
0x180004dfe  mov     rcx, rax; psz
0x180004e01  call    cs:__imp_SysAllocString
0x180004e07  test    rax, rax
0x180004e0a  mov     [r15], rax
0x180004e0d  cmovnz  edi, esi
0x180004e10  jmp     loc_180004C08
0x180004e15  mov     edi, ebx
0x180004e17  xor     esi, esi
0x180004e19  jmp     loc_180004C08
0x180004e1e  mov     rcx, [r12]
0x180004e22  mov     rax, [rcx]
0x180004e25  mov     rax, [rax+40h]
0x180004e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2e  test    eax, eax
0x180004e30  cmovs   ebx, eax
0x180004e33  jmp     short loc_180004DB5
0x180004e35  mov     edx, [rbp+arg_18]
0x180004e38  xor     ecx, ecx; strIn
0x180004e3a  inc     edx; ui
0x180004e3c  mov     [rbp+arg_18], edx
0x180004e3f  call    cs:__imp_SysAllocStringLen
0x180004e45  mov     [r14], rax
0x180004e48  mov     r9, rax
0x180004e4b  test    rax, rax
0x180004e4e  jz      loc_180004D0B
0x180004e54  mov     rcx, [r12]
0x180004e58  lea     rdx, [rbp+arg_18]
0x180004e5c  mov     [rsp+60h+var_40], rdx
0x180004e61  xor     r8d, r8d
0x180004e64  mov     rdx, rsi
0x180004e67  mov     rax, [rcx]
0x180004e6a  mov     rax, [rax+60h]
0x180004e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e73  mov     ebx, eax
0x180004e75  test    eax, eax
0x180004e77  jmp     loc_180004DA9
0x180004e7c  mov     edi, 80040003h
0x180004e81  jmp     loc_180004C0C
0x180004e86  mov     edi, 80070057h
0x180004e8b  xor     esi, esi
0x180004e8d  jmp     loc_180004C0C
0x180004e92  mov     rax, rbx
0x180004e95  jmp     loc_180004DFE
0x180004e9a  mov     eax, 80070057h
0x180004e9f  jmp     loc_180004C7B
0x180004ea4  mov     edi, 80040003h
0x180004ea9  xor     esi, esi
0x180004eab  jmp     loc_180004C0C
```
