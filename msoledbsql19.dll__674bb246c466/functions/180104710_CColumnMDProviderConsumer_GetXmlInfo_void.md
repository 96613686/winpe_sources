# CColumnMDProviderConsumer::GetXmlInfo(void)

- ea: `0x180104710`
- end: `0x180104a5e`
- name: `?GetXmlInfo@CColumnMDProviderConsumer@@EEAAJXZ`
- size: `846`
- prototype: `__int64 __fastcall(CColumnMDProviderConsumer *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003030`
- `0x180008fb0`
- `0x1800e2250`
- `0x1801017e0`
- `0x180104710`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180104774`
- `OLEAUT32!__imp_SysStringLen` at `0x180104806`
- `OLEAUT32!__imp_SysStringLen` at `0x180104901`
- `OLEAUT32!__imp_SysStringLen` at `0x180104774`
- `OLEAUT32!__imp_SysStringLen` at `0x180104806`
- `OLEAUT32!__imp_SysStringLen` at `0x180104901`

## string_xrefs

- `0x1801048ad`: `SSPROP_COL_XML_SCHEMACOLLECTIONNAME`
- `0x1801049a8`: `SSPROP_COL_XML_SCHEMACOLLECTION_CATALOGNAME`
- `0x180104a45`: `SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMANAME`

## pseudocode

```c
__int64 __fastcall CColumnMDProviderConsumer::GetXmlInfo(CColumnMDProviderConsumer *this)
{
  __int64 v1; // r8
  unsigned int v3; // ebx
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v6; // rcx
  const wchar_t *v7; // rbx
  UINT v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  const wchar_t *v11; // rbx
  UINT v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  const wchar_t *v16; // rbx
  UINT v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v22; // eax

  v1 = *((_QWORD *)this + 6);
  v3 = 0;
  v4 = *(_QWORD *)(*((_QWORD *)this + 21) + 8 * v1 - 8);
  v5 = *((_QWORD *)this + 20) + 88 * v1;
  v6 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 40LL);
  if ( *(_WORD *)(v6 + 368) )
  {
    v7 = *(const wchar_t **)(v6 + 376);
    if ( v7 )
    {
      v8 = SysStringLen(*(BSTR *)(v6 + 376));
      v9 = CBaseColumnMDProvider::AddToNamePool(
             this,
             v7,
             v8,
             (unsigned __int64 *)(*((_QWORD *)this + 8) + 264LL),
             (unsigned __int16 *)(*((_QWORD *)this + 8) + 256LL));
      v3 = v9;
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B0, 3987465, (unsigned int)v9);
        }
        return v3;
      }
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)this + 8) + 256LL) -= 2;
    }
    else
    {
      v14 = ChangePropStatus(
              0x24u,
              *(_DWORD *)(v5 - 56),
              *(const struct tagDBPROPSET *const *)(v5 - 72),
              *((const struct _GUID **)this + 5));
      v3 = v14;
      if ( v14 < 0 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          v14 = bidTraceHR(off_1802605B0, 4002825, (unsigned int)v14);
        CErrorData::PostFormattedError(
          (CColumnMDProviderConsumer *)((char *)this + 88),
          v14,
          0xA0A1u,
          L"SSPROP_COL_XML_SCHEMACOLLECTIONNAME",
          *((_QWORD *)this + 6));
        return v3;
      }
    }
  }
  v10 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 40LL);
  if ( *(_WORD *)(v10 + 256) )
  {
    v11 = *(const wchar_t **)(v10 + 264);
    if ( v11 )
    {
      v12 = SysStringLen(*(BSTR *)(v10 + 264));
      v13 = CBaseColumnMDProvider::AddToNamePool(
              this,
              v11,
              v12,
              (unsigned __int64 *)(*((_QWORD *)this + 8) + 232LL),
              (unsigned __int16 *)(*((_QWORD *)this + 8) + 224LL));
      v3 = v13;
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B0, 4033545, (unsigned int)v13);
        }
        return v3;
      }
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)this + 8) + 224LL) -= 2;
    }
    else
    {
      v19 = ChangePropStatus(
              0x22u,
              *(_DWORD *)(v5 - 56),
              *(const struct tagDBPROPSET *const *)(v5 - 72),
              *((const struct _GUID **)this + 5));
      v3 = v19;
      if ( v19 < 0 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          v19 = bidTraceHR(off_1802605B0, 4048905, (unsigned int)v19);
        CErrorData::PostFormattedError(
          (CColumnMDProviderConsumer *)((char *)this + 88),
          v19,
          0xA0A1u,
          L"SSPROP_COL_XML_SCHEMACOLLECTION_CATALOGNAME",
          *((_QWORD *)this + 6));
        return v3;
      }
    }
  }
  v15 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 40LL);
  if ( !*(_WORD *)(v15 + 312) )
    goto LABEL_27;
  v16 = *(const wchar_t **)(v15 + 320);
  if ( v16 )
  {
    v17 = SysStringLen(*(BSTR *)(v15 + 320));
    v18 = CBaseColumnMDProvider::AddToNamePool(
            this,
            v16,
            v17,
            (unsigned __int64 *)(*((_QWORD *)this + 8) + 248LL),
            (unsigned __int16 *)(*((_QWORD *)this + 8) + 240LL));
    v3 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_1802605B0, 4080649, (unsigned int)v18);
      }
      return v3;
    }
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)this + 8) + 240LL) -= 2;
    goto LABEL_27;
  }
  v22 = ChangePropStatus(
          0x23u,
          *(_DWORD *)(v5 - 56),
          *(const struct tagDBPROPSET *const *)(v5 - 72),
          *((const struct _GUID **)this + 5));
  v3 = v22;
  if ( v22 >= 0 )
  {
LABEL_27:
    v20 = *((_QWORD *)this + 8);
    if ( *(_WORD *)(v20 + 256) )
      *(_WORD *)(v20 + 60) |= 4u;
    return v3;
  }
  _mm_lfence();
  if ( (bidGblFlags & 2) != 0 )
    v22 = bidTraceHR(off_1802605B0, 4096009, (unsigned int)v22);
  CErrorData::PostFormattedError(
    (CColumnMDProviderConsumer *)((char *)this + 88),
    v22,
    0xA0A1u,
    L"SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMANAME",
    *((_QWORD *)this + 6));
  return v3;
}

```

## disassembly

```asm
0x180104710  mov     [rsp+arg_0], rbx
0x180104715  mov     [rsp+arg_8], rbp
0x18010471a  mov     [rsp+arg_10], rsi
0x18010471f  mov     [rsp+arg_18], rdi
0x180104724  push    r14
0x180104726  sub     rsp, 30h
0x18010472a  mov     r8, [rcx+30h]
0x18010472e  mov     rdi, rcx
0x180104731  mov     rax, [rcx+0A8h]
0x180104738  xor     ebx, ebx
0x18010473a  imul    rsi, r8, 58h ; 'X'
0x18010473e  mov     rbp, [rax+r8*8-8]
0x180104743  mov     r14d, 0FFFEh
0x180104749  add     rsi, [rcx+0A0h]
0x180104750  mov     rax, [rbp+30h]
0x180104754  mov     rcx, [rax+28h]
0x180104758  cmp     [rcx+170h], bx
0x18010475f  jz      short loc_1801047DD
0x180104761  mov     rbx, [rcx+178h]
0x180104768  test    rbx, rbx
0x18010476b  jz      loc_180104864
0x180104771  mov     rcx, rbx; pbstr
0x180104774  call    cs:__imp_SysStringLen
0x18010477a  mov     r9, [rdi+40h]
0x18010477e  mov     rdx, rbx; wchar_t *
0x180104781  mov     r8d, eax; unsigned __int64
0x180104784  mov     rcx, rdi; this
0x180104787  lea     rax, [r9+100h]
0x18010478e  add     r9, 108h; unsigned __int64 *
0x180104795  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18010479a  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEB_W_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(wchar_t const *,unsigned __int64,unsigned __int64 *,ushort *)
0x18010479f  mov     ebx, eax
0x1801047a1  test    eax, eax
0x1801047a3  jns     short loc_1801047CE
0x1801047a5  test    byte ptr cs:_bidGblFlags, 2
0x1801047ac  jz      loc_1801049E3
0x1801047b2  lfence
0x1801047b5  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801047bc  mov     r8d, eax
0x1801047bf  mov     edx, 3CD809h
0x1801047c4  call    _bidTraceHR
0x1801047c9  jmp     loc_1801049E3
0x1801047ce  lfence
0x1801047d1  mov     rax, [rdi+40h]
0x1801047d5  add     [rax+100h], r14w
0x1801047dd  mov     rax, [rbp+30h]
0x1801047e1  mov     rcx, [rax+28h]
0x1801047e5  cmp     word ptr [rcx+100h], 0
0x1801047ed  jz      loc_1801048D8
0x1801047f3  mov     rbx, [rcx+108h]
0x1801047fa  test    rbx, rbx
0x1801047fd  jz      loc_18010495F
0x180104803  mov     rcx, rbx; pbstr
0x180104806  call    cs:__imp_SysStringLen
0x18010480c  mov     r9, [rdi+40h]
0x180104810  mov     rdx, rbx; wchar_t *
0x180104813  mov     r8d, eax; unsigned __int64
0x180104816  mov     rcx, rdi; this
0x180104819  lea     rax, [r9+0E0h]
0x180104820  add     r9, 0E8h; unsigned __int64 *
0x180104827  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18010482c  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEB_W_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(wchar_t const *,unsigned __int64,unsigned __int64 *,ushort *)
0x180104831  mov     ebx, eax
0x180104833  test    eax, eax
0x180104835  jns     loc_1801048C9
0x18010483b  test    byte ptr cs:_bidGblFlags, 2
0x180104842  jz      loc_1801049E3
0x180104848  lfence
0x18010484b  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180104852  mov     r8d, eax
0x180104855  mov     edx, 3D8C09h
0x18010485a  call    _bidTraceHR
0x18010485f  jmp     loc_1801049E3
0x180104864  mov     r9, [rdi+28h]; struct _GUID *
0x180104868  mov     ecx, 24h ; '$'; unsigned int
0x18010486d  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x180104871  mov     edx, [rsi-38h]; unsigned int
0x180104874  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x180104879  mov     ebx, eax
0x18010487b  test    eax, eax
0x18010487d  jns     loc_1801047DD
0x180104883  lfence
0x180104886  test    byte ptr cs:_bidGblFlags, 2
0x18010488d  jz      short loc_1801048A3
0x18010488f  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180104896  mov     r8d, eax
0x180104899  mov     edx, 3D1409h
0x18010489e  call    _bidTraceHR
0x1801048a3  mov     edx, eax; int
0x1801048a5  lea     rcx, [rdi+58h]; this
0x1801048a9  mov     rax, [rdi+30h]
0x1801048ad  lea     r9, aSspropColXmlSc; "SSPROP_COL_XML_SCHEMACOLLECTIONNAME"
0x1801048b4  mov     r8d, 0A0A1h; unsigned int
0x1801048ba  mov     [rsp+38h+var_18], rax
0x1801048bf  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x1801048c4  jmp     loc_1801049E3
0x1801048c9  lfence
0x1801048cc  mov     rax, [rdi+40h]
0x1801048d0  add     [rax+0E0h], r14w
0x1801048d8  mov     rax, [rbp+30h]
0x1801048dc  mov     rcx, [rax+28h]
0x1801048e0  cmp     word ptr [rcx+138h], 0
0x1801048e8  jz      loc_1801049D0
0x1801048ee  mov     rbx, [rcx+140h]
0x1801048f5  test    rbx, rbx
0x1801048f8  jz      loc_180104A00
0x1801048fe  mov     rcx, rbx; pbstr
0x180104901  call    cs:__imp_SysStringLen
0x180104907  mov     r9, [rdi+40h]
0x18010490b  mov     rdx, rbx; wchar_t *
0x18010490e  mov     r8d, eax; unsigned __int64
0x180104911  mov     rcx, rdi; this
0x180104914  lea     rax, [r9+0F0h]
0x18010491b  add     r9, 0F8h; unsigned __int64 *
0x180104922  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180104927  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEB_W_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(wchar_t const *,unsigned __int64,unsigned __int64 *,ushort *)
0x18010492c  mov     ebx, eax
0x18010492e  test    eax, eax
0x180104930  jns     loc_1801049C1
0x180104936  test    byte ptr cs:_bidGblFlags, 2
0x18010493d  jz      loc_1801049E3
0x180104943  lfence
0x180104946  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18010494d  mov     r8d, eax
0x180104950  mov     edx, 3E4409h
0x180104955  call    _bidTraceHR
0x18010495a  jmp     loc_1801049E3
0x18010495f  mov     r9, [rdi+28h]; struct _GUID *
0x180104963  mov     ecx, 22h ; '"'; unsigned int
0x180104968  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x18010496c  mov     edx, [rsi-38h]; unsigned int
0x18010496f  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x180104974  mov     ebx, eax
0x180104976  test    eax, eax
0x180104978  jns     loc_1801048D8
0x18010497e  lfence
0x180104981  test    byte ptr cs:_bidGblFlags, 2
0x180104988  jz      short loc_18010499E
0x18010498a  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180104991  mov     r8d, eax
0x180104994  mov     edx, 3DC809h
0x180104999  call    _bidTraceHR
0x18010499e  mov     edx, eax; int
0x1801049a0  lea     rcx, [rdi+58h]; this
0x1801049a4  mov     rax, [rdi+30h]
0x1801049a8  lea     r9, aSspropColXmlSc_0; "SSPROP_COL_XML_SCHEMACOLLECTION_CATALOG"...
0x1801049af  mov     r8d, 0A0A1h; unsigned int
0x1801049b5  mov     [rsp+38h+var_18], rax
0x1801049ba  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x1801049bf  jmp     short loc_1801049E3
0x1801049c1  lfence
0x1801049c4  mov     rax, [rdi+40h]
0x1801049c8  add     [rax+0F0h], r14w
0x1801049d0  mov     rax, [rdi+40h]
0x1801049d4  cmp     word ptr [rax+100h], 0
0x1801049dc  jz      short loc_1801049E3
0x1801049de  or      word ptr [rax+3Ch], 4
0x1801049e3  mov     rbp, [rsp+38h+arg_8]
0x1801049e8  mov     eax, ebx
0x1801049ea  mov     rbx, [rsp+38h+arg_0]
0x1801049ef  mov     rsi, [rsp+38h+arg_10]
0x1801049f4  mov     rdi, [rsp+38h+arg_18]
0x1801049f9  add     rsp, 30h
0x1801049fd  pop     r14
0x1801049ff  retn
0x180104a00  mov     r9, [rdi+28h]; struct _GUID *
0x180104a04  mov     ecx, 23h ; '#'; unsigned int
0x180104a09  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x180104a0d  mov     edx, [rsi-38h]; unsigned int
0x180104a10  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x180104a15  mov     ebx, eax
0x180104a17  test    eax, eax
0x180104a19  jns     short loc_1801049D0
0x180104a1b  lfence
0x180104a1e  test    byte ptr cs:_bidGblFlags, 2
0x180104a25  jz      short loc_180104A3B
0x180104a27  mov     rcx, cs:off_1802605B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180104a2e  mov     r8d, eax
0x180104a31  mov     edx, 3E8009h
0x180104a36  call    _bidTraceHR
0x180104a3b  mov     edx, eax; int
0x180104a3d  lea     rcx, [rdi+58h]; this
0x180104a41  mov     rax, [rdi+30h]
0x180104a45  lea     r9, aSspropColXmlSc_1; "SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMAN"...
0x180104a4c  mov     r8d, 0A0A1h; unsigned int
0x180104a52  mov     [rsp+38h+var_18], rax
0x180104a57  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x180104a5c  jmp     short loc_1801049E3
```
