# CKsProxy::CheckMediaType(IUnknown *,ulong,CMediaType const *)

- ea: `0x180020f2c`
- end: `0x1800211d3`
- name: `?CheckMediaType@CKsProxy@@QEAAJPEAUIUnknown@@KPEBVCMediaType@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(CKsProxy *this, LPUNKNOWN pUnkOuter, int, const _AMMediaType *rclsid)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026d10`
- `0x180029960`
- `0x18002da70`

## callees

- `0x180006850`
- `0x18001b190`
- `0x180020f2c`
- `0x180025890`
- `0x18003b130`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800211a6`
- `ole32!CoTaskMemFree` at `0x1800211a6`

## pseudocode

```c
__int64 __fastcall CKsProxy::CheckMediaType(CKsProxy *this, LPUNKNOWN pUnkOuter, int a3, const _AMMediaType *rclsid)
{
  int PinFactoryDataRanges; // edi
  _DWORD *v9; // rsi
  IUnknown *pUnk; // rcx
  char *i; // rbx
  int v12; // eax
  int v13; // r15d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v21; // [rsp+20h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-18h] BYREF
  __int64 v23; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v24; // [rsp+38h] [rbp-8h] BYREF
  struct IKsDataTypeHandler *v25; // [rsp+88h] [rbp+48h] BYREF

  v25 = 0;
  v24 = 0;
  pv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, this->m_pName);
  if ( !rclsid || !pUnkOuter )
    return 2147500035LL;
  OpenDataHandler(rclsid, pUnkOuter, &v25, (LPVOID *)&v24);
  if ( v25 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, this->m_pName);
  PinFactoryDataRanges = CKsProxy::GetPinFactoryDataRanges(this, a3, &pv);
  if ( PinFactoryDataRanges >= 0 )
  {
    v21 = 0;
    if ( v25 )
    {
      v9 = pv;
      PinFactoryDataRanges = v25->KsIsMediaTypeInRanges(v25, pv);
      if ( PinFactoryDataRanges == 1 )
        PinFactoryDataRanges = -2147467259;
      if ( v24 )
        ((void (*)(void))v24->Release)();
    }
    else
    {
      pUnk = rclsid->pUnk;
      v23 = 0;
      if ( pUnk && pUnk->QueryInterface(pUnk, &GUID_d559999a_a4c3_11d2_876a_00a0c9223196, (void **)&v21) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL))(v21, &v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      else
      {
        v23 = 0;
      }
      v9 = pv;
      PinFactoryDataRanges = -2147467259;
      for ( i = (char *)pv + 8; ; i += (*(_DWORD *)i + 7) & 0xFFFFFFF8 )
      {
        v12 = v9[1];
        v13 = v12 - 1;
        v9[1] = v12 - 1;
        if ( !v12 )
          break;
        v14 = *((_QWORD *)i + 2) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
        if ( !v14 )
          v14 = *((_QWORD *)i + 3) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
        if ( !v14 )
          goto LABEL_40;
        v15 = *(_QWORD *)&rclsid->majortype.Data1 - *((_QWORD *)i + 2);
        if ( *(_QWORD *)&rclsid->majortype.Data1 == *((_QWORD *)i + 2) )
          v15 = *(_QWORD *)rclsid->majortype.Data4 - *((_QWORD *)i + 3);
        if ( !v15 )
        {
          v16 = *((_QWORD *)i + 4) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
          if ( !v16 )
            v16 = *((_QWORD *)i + 5) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
          if ( !v16 )
            goto LABEL_40;
          v17 = *(_QWORD *)&rclsid->subtype.Data1 - *((_QWORD *)i + 4);
          if ( !v17 )
            v17 = *(_QWORD *)rclsid->subtype.Data4 - *((_QWORD *)i + 5);
          if ( !v17 )
          {
            v18 = *((_QWORD *)i + 6) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
            if ( !v18 )
              v18 = *((_QWORD *)i + 7) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
            if ( !v18 )
              goto LABEL_40;
            v19 = *(_QWORD *)&rclsid->formattype.Data1 - *((_QWORD *)i + 6);
            if ( !v19 )
              v19 = *(_QWORD *)rclsid->formattype.Data4 - *((_QWORD *)i + 7);
            if ( !v19 )
            {
LABEL_40:
              if ( (int)KsResolveRequiredAttributes(i, v23) >= 0 )
              {
                PinFactoryDataRanges = 0;
                break;
              }
            }
          }
        }
        if ( (i[4] & 2) != 0 )
        {
          i += (*(_DWORD *)i + 7) & 0xFFFFFFF8;
          v9[1] = v13 - 1;
        }
      }
    }
    CoTaskMemFree(v9);
  }
  return (unsigned int)PinFactoryDataRanges;
}

```

## disassembly

```asm
0x180020f2c  mov     [rsp-28h+arg_0], rbx
0x180020f31  mov     [rsp-28h+arg_8], rsi
0x180020f36  push    rbp
0x180020f37  push    rdi
0x180020f38  push    r13
0x180020f3a  push    r14
0x180020f3c  push    r15
0x180020f3e  mov     rbp, rsp
0x180020f41  sub     rsp, 40h
0x180020f45  mov     r14, r9
0x180020f48  mov     [rbp+arg_18], 0
0x180020f50  mov     esi, r8d
0x180020f53  mov     [rbp+var_8], 0
0x180020f5b  mov     rdi, rdx
0x180020f5e  mov     [rbp+pv], 0
0x180020f66  mov     rbx, rcx
0x180020f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f70  lea     r15, WPP_GLOBAL_Control
0x180020f77  cmp     rcx, r15
0x180020f7a  jz      short loc_180020F9B
0x180020f7c  cmp     byte ptr [rcx+19h], 2
0x180020f80  jb      short loc_180020F9B
0x180020f82  mov     r9, [rbx+58h]
0x180020f86  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180020f8d  mov     rcx, [rcx+10h]
0x180020f91  mov     edx, 15h
0x180020f96  call    WPP_SF_S
0x180020f9b  test    r14, r14
0x180020f9e  jz      loc_1800211B6
0x180020fa4  test    rdi, rdi
0x180020fa7  jz      loc_1800211B6
0x180020fad  lea     r9, [rbp+var_8]; struct IUnknown **
0x180020fb1  mov     rdx, rdi; pUnkOuter
0x180020fb4  lea     r8, [rbp+arg_18]; struct IKsDataTypeHandler **
0x180020fb8  mov     rcx, r14; rclsid
0x180020fbb  call    ?OpenDataHandler@@YAXPEBVCMediaType@@PEAUIUnknown@@PEAPEAUIKsDataTypeHandler@@PEAPEAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x180020fc0  cmp     [rbp+arg_18], 0
0x180020fc5  jz      short loc_180020FF2
0x180020fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fce  cmp     rcx, r15
0x180020fd1  jz      short loc_180020FF2
0x180020fd3  cmp     byte ptr [rcx+19h], 2
0x180020fd7  jb      short loc_180020FF2
0x180020fd9  mov     r9, [rbx+58h]
0x180020fdd  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180020fe4  mov     rcx, [rcx+10h]
0x180020fe8  mov     edx, 16h
0x180020fed  call    WPP_SF_S
0x180020ff2  lea     r8, [rbp+pv]; void **
0x180020ff6  mov     edx, esi; unsigned int
0x180020ff8  mov     rcx, rbx; this
0x180020ffb  call    ?GetPinFactoryDataRanges@CKsProxy@@QEAAJKPEAPEAX@Z; CKsProxy::GetPinFactoryDataRanges(ulong,void * *)
0x180021000  mov     edi, eax
0x180021002  test    eax, eax
0x180021004  js      loc_1800211B2
0x18002100a  mov     rcx, [rbp+arg_18]
0x18002100e  mov     [rbp+var_20], 0
0x180021016  test    rcx, rcx
0x180021019  jz      short loc_180021059
0x18002101b  mov     rax, [rcx]
0x18002101e  mov     rsi, [rbp+pv]
0x180021022  mov     rdx, rsi
0x180021025  mov     rax, [rax+20h]
0x180021029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002102e  mov     rcx, [rbp+var_8]
0x180021032  mov     edi, eax
0x180021034  cmp     edi, 1
0x180021037  mov     eax, 80004005h
0x18002103c  cmovz   edi, eax
0x18002103f  test    rcx, rcx
0x180021042  jz      loc_1800211A3
0x180021048  mov     rax, [rcx]
0x18002104b  mov     rax, [rax+10h]
0x18002104f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021054  jmp     loc_1800211A3
0x180021059  mov     rcx, [r14+40h]
0x18002105d  mov     [rbp+var_10], 0
0x180021065  test    rcx, rcx
0x180021068  jz      short loc_1800210AA
0x18002106a  mov     rax, [rcx]
0x18002106d  lea     r8, [rbp+var_20]
0x180021071  lea     rdx, _GUID_d559999a_a4c3_11d2_876a_00a0c9223196
0x180021078  mov     rax, [rax]
0x18002107b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021080  test    eax, eax
0x180021082  js      short loc_1800210AA
0x180021084  mov     rcx, [rbp+var_20]
0x180021088  lea     rdx, [rbp+var_10]
0x18002108c  mov     rax, [rcx]
0x18002108f  mov     rax, [rax+18h]
0x180021093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021098  mov     rcx, [rbp+var_20]
0x18002109c  mov     rax, [rcx]
0x18002109f  mov     rax, [rax+10h]
0x1800210a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210a8  jmp     short loc_1800210B2
0x1800210aa  mov     [rbp+var_10], 0
0x1800210b2  mov     rsi, [rbp+pv]
0x1800210b6  mov     edi, 80004005h
0x1800210bb  mov     r13d, 0FFFFFFF8h
0x1800210c1  lea     rbx, [rsi+8]
0x1800210c5  mov     eax, [rsi+4]
0x1800210c8  lea     r15d, [rax-1]
0x1800210cc  mov     [rsi+4], r15d
0x1800210d0  test    eax, eax
0x1800210d2  jz      loc_1800211A3
0x1800210d8  mov     rax, [rbx+10h]
0x1800210dc  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800210e3  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800210ea  sub     rax, rdx
0x1800210ed  jnz     short loc_1800210F6
0x1800210ef  mov     rax, [rbx+18h]
0x1800210f3  sub     rax, rcx
0x1800210f6  test    rax, rax
0x1800210f9  jz      short loc_180021169
0x1800210fb  mov     rax, [r14]
0x1800210fe  sub     rax, [rbx+10h]
0x180021102  jnz     short loc_18002110C
0x180021104  mov     rax, [r14+8]
0x180021108  sub     rax, [rbx+18h]
0x18002110c  test    rax, rax
0x18002110f  jnz     short loc_180021179
0x180021111  mov     rax, [rbx+20h]
0x180021115  sub     rax, rdx
0x180021118  jnz     short loc_180021121
0x18002111a  mov     rax, [rbx+28h]
0x18002111e  sub     rax, rcx
0x180021121  test    rax, rax
0x180021124  jz      short loc_180021169
0x180021126  mov     rax, [r14+10h]
0x18002112a  sub     rax, [rbx+20h]
0x18002112e  jnz     short loc_180021138
0x180021130  mov     rax, [r14+18h]
0x180021134  sub     rax, [rbx+28h]
0x180021138  test    rax, rax
0x18002113b  jnz     short loc_180021179
0x18002113d  mov     rax, [rbx+30h]
0x180021141  sub     rax, rdx
0x180021144  jnz     short loc_18002114D
0x180021146  mov     rax, [rbx+38h]
0x18002114a  sub     rax, rcx
0x18002114d  test    rax, rax
0x180021150  jz      short loc_180021169
0x180021152  mov     rax, [r14+2Ch]
0x180021156  sub     rax, [rbx+30h]
0x18002115a  jnz     short loc_180021164
0x18002115c  mov     rax, [r14+34h]
0x180021160  sub     rax, [rbx+38h]
0x180021164  test    rax, rax
0x180021167  jnz     short loc_180021179
0x180021169  mov     rdx, [rbp+var_10]
0x18002116d  mov     rcx, rbx
0x180021170  call    KsResolveRequiredAttributes
0x180021175  test    eax, eax
0x180021177  jns     short loc_1800211A1
0x180021179  test    byte ptr [rbx+4], 2
0x18002117d  jz      short loc_180021191
0x18002117f  mov     eax, [rbx]
0x180021181  add     eax, 7
0x180021184  and     rax, r13
0x180021187  add     rbx, rax
0x18002118a  lea     eax, [r15-1]
0x18002118e  mov     [rsi+4], eax
0x180021191  mov     eax, [rbx]
0x180021193  add     eax, 7
0x180021196  and     rax, r13
0x180021199  add     rbx, rax
0x18002119c  jmp     loc_1800210C5
0x1800211a1  xor     edi, edi
0x1800211a3  mov     rcx, rsi; pv
0x1800211a6  call    cs:__imp_CoTaskMemFree
0x1800211ad  nop     dword ptr [rax+rax+00h]
0x1800211b2  mov     eax, edi
0x1800211b4  jmp     short loc_1800211BB
0x1800211b6  mov     eax, 80004003h
0x1800211bb  mov     rbx, [rsp+40h+arg_0]
0x1800211c0  mov     rsi, [rsp+40h+arg_8]
0x1800211c5  add     rsp, 40h
0x1800211c9  pop     r15
0x1800211cb  pop     r14
0x1800211cd  pop     r13
0x1800211cf  pop     rdi
0x1800211d0  pop     rbp
0x1800211d1  retn
```
