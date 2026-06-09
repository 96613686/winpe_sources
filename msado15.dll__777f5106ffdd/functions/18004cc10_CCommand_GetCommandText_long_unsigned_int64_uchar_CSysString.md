# CCommand::GetCommandText(long,unsigned __int64,uchar,CSysString &)

- ea: `0x18004cc10`
- end: `0x18004cfd9`
- name: `?GetCommandText@CCommand@@QEAAJJ_KEAEAVCSysString@@@Z`
- size: `969`
- prototype: `__int64 __usercall@<rax>(CCommand *__hidden this@<rcx>, int@<edx>, unsigned __int64@<r8>, unsigned __int8@<r9b>, struct CSysString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004ca30`

## callees

- `0x1800265d0`
- `0x180045580`
- `0x18004cc10`
- `0x18004f140`
- `0x180059d44`
- `0x18006a22c`
- `0x180084608`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004cec4`
- `OLEAUT32!__imp_SysAllocString` at `0x18004cec4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004ce4f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004cf3f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004ce4f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004cf3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cc77`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ceb1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cfa1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cc77`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ceb1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cfa1`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cca6`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cf0e`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cf25`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cca6`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cf0e`
- `OLEAUT32!__imp_SysStringLen` at `0x18004cf25`

## string_xrefs

- `0x18004cd59`: `<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n`
- `0x18004cd81`: `<CCommand::GetCommandText|ADO|ERR>  line %d\n`
- `0x18004ce0d`: `<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CCommand::GetCommandText(CCommand *this, int a2, unsigned __int64 a3, unsigned __int8 a4, BSTR *a5)
{
  unsigned int v5; // ebx
  int v6; // edi
  int v9; // edx
  int v10; // edx
  int v11; // edx
  BSTR *v12; // rbx
  BSTR *v13; // rdi
  UINT v14; // eax
  const OLECHAR *v15; // rcx
  struct _ADOConnection *Connection; // rax
  int v17; // eax
  unsigned int BidObjectID; // eax
  BSTR *v19; // rdi
  BSTR v20; // rax
  char v21; // cl
  bool v22; // zf
  unsigned int v23; // ebx
  BSTR *v25; // rdi
  BSTR v26; // rax
  char v27; // cl
  char v28; // cl
  OLECHAR *v29; // rcx
  __int64 v30; // r15
  signed int v31; // r12d
  BSTR v32; // rbp
  const void *v33; // rdx
  __int64 v34; // [rsp+20h] [rbp-48h]
  int v35[4]; // [rsp+30h] [rbp-38h] BYREF
  int v36; // [rsp+78h] [rbp+10h] BYREF

  v5 = 0;
  v6 = a4;
  if ( a2 == 2 )
  {
    v25 = a5;
    if ( ((_BYTE)a5[1] & 2) != 0 )
      SysFreeString(*a5);
    v26 = SysAllocString(L"select * from ");
    v27 = *((_BYTE *)v25 + 8);
    *v25 = v26;
    if ( v26 )
      v28 = v27 | 4;
    else
      v28 = v27 & 0xFB;
    *((_BYTE *)v25 + 8) = v28;
    if ( (*((_BYTE *)this + 184) & 4) != 0 )
    {
      v29 = (OLECHAR *)*((_QWORD *)this + 22);
      if ( v29 )
      {
        v30 = (int)SysStringLen(v29);
        if ( *v25 )
          v31 = SysStringLen(*v25);
        else
          v31 = 0;
        v32 = SysAllocStringLen(0, (int)v30 + v31);
        if ( v32 )
        {
          if ( v31 > 0 )
            memcpy_0(v32, *v25, 2LL * v31);
          if ( (*((_BYTE *)this + 184) & 4) != 0 )
            v33 = (const void *)*((_QWORD *)this + 22);
          else
            v33 = 0;
          memcpy_0(&v32[v31], v33, 2 * v30);
          SysFreeString(*v25);
          *v25 = v32;
        }
        else
        {
          *((_BYTE *)v25 + 8) &= ~4u;
        }
      }
    }
    if ( ((_BYTE)v25[1] & 4) == 0 )
      return (unsigned int)-2147024882;
    return v5;
  }
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 3;
    if ( v10 )
    {
      v11 = v10 - 4;
      if ( !v11 || v11 == 504 )
        goto LABEL_6;
    }
    else
    {
      v35[0] = 256;
      v36 = 0;
      Connection = CCommand::GetConnection(this);
      if ( Connection
        && (v17 = (*(__int64 (__fastcall **)(struct _ADOConnection *, const GUID *, __int64, int *, int *))(*(_QWORD *)Connection + 384LL))(
                    Connection,
                    &DBPROPSET_DATASOURCEINFO,
                    109,
                    &v36,
                    v35),
            v5 = v17,
            v17 < 0) )
      {
        if ( v17 != -2147217887 || v36 != 1 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
            {
              bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR>  line %d\n", 1220);
            }
            else
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
              LODWORD(v34) = 1220;
              bidTraceW(
                off_18012A1E0[0],
                1249289,
                L"<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n",
                BidObjectID,
                v34);
            }
          }
          return v5;
        }
      }
      else if ( v36 != 1 && (v35[0] & 0x100) == 0 )
      {
        v19 = a5;
        if ( v35[0] )
        {
          CSysString::operator=(a5, L"exec ");
          CSysString::operator+=(v19, (char *)this + 176);
        }
        else
        {
          CSysString::operator=(a5, (char *)this + 176);
        }
        if ( ((_BYTE)v19[1] & 4) == 0 )
        {
          v5 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            LODWORD(v34) = 1238;
            bidTraceW(
              off_18012A1E0[0],
              1267721,
              L"<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              2147942414LL,
              v34);
          }
        }
        return v5;
      }
      return (unsigned int)CCommand::GetStoredProc(this, a3, v6, (struct CSysString *)a5);
    }
    return v5;
  }
LABEL_6:
  v12 = a5;
  v13 = (BSTR *)((char *)this + 176);
  if ( (BSTR *)((char *)this + 176) != a5 && *v13 != *a5 )
  {
    if ( ((_BYTE)a5[1] & 2) != 0 )
      SysFreeString(*a5);
    if ( ((_BYTE)v13[1] & 4) != 0 && *v13 )
    {
      if ( ((_BYTE)v12[1] & 1) != 0 )
      {
        v14 = SysStringLen(*v13);
        if ( ((_BYTE)v13[1] & 4) != 0 )
          v15 = *v13;
        else
          v15 = 0;
        v20 = SysAllocStringLen(v15, v14);
        v21 = *((_BYTE *)v12 + 8);
        *v12 = v20;
        if ( v20 )
          *((_BYTE *)v12 + 8) = v21 | 4;
        else
          *((_BYTE *)v12 + 8) = v21 & 0xFB;
      }
      else
      {
        *v12 = *v13;
      }
    }
    else
    {
      *v12 = 0;
    }
  }
  v22 = ((_BYTE)v12[1] & 4) == 0;
  v23 = -2147024882;
  if ( !v22 )
    return 0;
  return v23;
}

```

## disassembly

```asm
0x18004cc10  push    rbx
0x18004cc12  push    rbp
0x18004cc13  push    rsi
0x18004cc14  push    rdi
0x18004cc15  sub     rsp, 48h
0x18004cc19  xor     ebx, ebx
0x18004cc1b  movzx   edi, r9b
0x18004cc1f  mov     rbp, r8
0x18004cc22  mov     rsi, rcx
0x18004cc25  cmp     edx, 2
0x18004cc28  jz      loc_18004CEA0
0x18004cc2e  sub     edx, 1
0x18004cc31  jz      short loc_18004CC4D
0x18004cc33  sub     edx, 3
0x18004cc36  jz      loc_18004CCC4
0x18004cc3c  sub     edx, 4
0x18004cc3f  jz      short loc_18004CC4D
0x18004cc41  cmp     edx, 1F8h
0x18004cc47  jnz     loc_18004CFCD
0x18004cc4d  mov     rbx, [rsp+68h+arg_20]
0x18004cc55  lea     rdi, [rcx+0B0h]
0x18004cc5c  cmp     rdi, rbx
0x18004cc5f  jz      loc_18004CE83
0x18004cc65  mov     rcx, [rbx]; bstrString
0x18004cc68  cmp     [rdi], rcx
0x18004cc6b  jz      loc_18004CE83
0x18004cc71  test    byte ptr [rbx+8], 2
0x18004cc75  jz      short loc_18004CC83
0x18004cc77  call    cs:__imp_SysFreeString
0x18004cc7e  nop     dword ptr [rax+rax+00h]
0x18004cc83  test    byte ptr [rdi+8], 4
0x18004cc87  jz      loc_18004CE7C
0x18004cc8d  mov     rax, [rdi]
0x18004cc90  test    rax, rax
0x18004cc93  jz      loc_18004CE7C
0x18004cc99  test    byte ptr [rbx+8], 1
0x18004cc9d  jz      loc_18004CE77
0x18004cca3  mov     rcx, rax; pbstr
0x18004cca6  call    cs:__imp_SysStringLen
0x18004ccad  nop     dword ptr [rax+rax+00h]
0x18004ccb2  test    byte ptr [rdi+8], 4
0x18004ccb6  jz      loc_18004CE4B
0x18004ccbc  mov     rcx, [rdi]; this
0x18004ccbf  jmp     loc_18004CE4D
0x18004ccc4  mov     [rsp+68h+var_38], 100h
0x18004cccc  mov     [rsp+68h+arg_8], ebx
0x18004ccd0  call    ?GetConnection@CCommand@@QEAAPEAU_ADOConnection@@XZ; CCommand::GetConnection(void)
0x18004ccd5  mov     rcx, rax
0x18004ccd8  test    rax, rax
0x18004ccdb  jz      loc_18004CD9D
0x18004cce1  mov     rax, [rax]
0x18004cce4  lea     rdx, [rsp+68h+var_38]
0x18004cce9  mov     [rsp+68h+var_48], rdx
0x18004ccee  lea     r9, [rsp+68h+arg_8]
0x18004ccf3  mov     r8d, 6Dh ; 'm'
0x18004ccf9  lea     rdx, DBPROPSET_DATASOURCEINFO
0x18004cd00  mov     rax, [rax+180h]
0x18004cd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd0c  mov     ebx, eax
0x18004cd0e  test    eax, eax
0x18004cd10  jns     loc_18004CD9D
0x18004cd16  cmp     eax, 80040E21h
0x18004cd1b  jnz     short loc_18004CD28
0x18004cd1d  cmp     [rsp+68h+arg_8], 1
0x18004cd22  jz      loc_18004CE2E
0x18004cd28  test    byte ptr cs:_bidGblFlags, 2
0x18004cd2f  jz      loc_18004CFCD
0x18004cd35  lea     rcx, [rsi+90h]; this
0x18004cd3c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004cd41  cmp     eax, 0FFFFFFFFh
0x18004cd44  jz      short loc_18004CD7A
0x18004cd46  lea     rcx, [rsi+90h]; this
0x18004cd4d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18004cd52  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004cd59  lea     r8, aCcommandGetcom_1; "<CCommand::GetCommandText|ADO|ERR> %u#,"...
0x18004cd60  mov     r9d, eax
0x18004cd63  mov     dword ptr [rsp+68h+var_48], 4C4h
0x18004cd6b  mov     edx, 131009h
0x18004cd70  call    _bidTraceW
0x18004cd75  jmp     loc_18004CFCD
0x18004cd7a  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004cd81  lea     r8, aCcommandGetcom_0; "<CCommand::GetCommandText|ADO|ERR>  lin"...
0x18004cd88  mov     r9d, 4C4h
0x18004cd8e  mov     edx, 131009h
0x18004cd93  call    _bidTraceW
0x18004cd98  jmp     loc_18004CFCD
0x18004cd9d  cmp     [rsp+68h+arg_8], 1
0x18004cda2  jz      loc_18004CE2E
0x18004cda8  mov     eax, [rsp+68h+var_38]
0x18004cdac  bt      eax, 8
0x18004cdb0  jb      short loc_18004CE2E
0x18004cdb2  mov     rdi, [rsp+68h+arg_20]
0x18004cdba  mov     rcx, rdi
0x18004cdbd  test    eax, eax
0x18004cdbf  jnz     short loc_18004CDCF
0x18004cdc1  lea     rdx, [rsi+0B0h]
0x18004cdc8  call    ??4CSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator=(CSysString const &)
0x18004cdcd  jmp     short loc_18004CDEA
0x18004cdcf  lea     rdx, aExec; "exec "
0x18004cdd6  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x18004cddb  lea     rdx, [rsi+0B0h]
0x18004cde2  mov     rcx, rdi
0x18004cde5  call    ??YCSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator+=(CSysString const &)
0x18004cdea  test    byte ptr [rdi+8], 4
0x18004cdee  jnz     loc_18004CFCD
0x18004cdf4  test    byte ptr cs:_bidGblFlags, 2
0x18004cdfb  mov     ebx, 8007000Eh
0x18004ce00  jz      loc_18004CFCD
0x18004ce06  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18004ce0d  lea     r8, aCcommandGetcom; "<CCommand::GetCommandText|ADO|ERR> 0x%0"...
0x18004ce14  mov     r9d, ebx
0x18004ce17  mov     dword ptr [rsp+68h+var_48], 4D6h
0x18004ce1f  mov     edx, 135809h
0x18004ce24  call    _bidTraceW
0x18004ce29  jmp     loc_18004CFCD
0x18004ce2e  mov     r9, [rsp+68h+arg_20]; struct CSysString *
0x18004ce36  mov     r8d, edi; int
0x18004ce39  mov     rdx, rbp; unsigned __int64
0x18004ce3c  mov     rcx, rsi; this
0x18004ce3f  call    ?GetStoredProc@CCommand@@QEAAJ_KHAEAVCSysString@@@Z; CCommand::GetStoredProc(unsigned __int64,int,CSysString &)
0x18004ce44  mov     ebx, eax
0x18004ce46  jmp     loc_18004CFCD
0x18004ce4b  xor     ecx, ecx; strIn
0x18004ce4d  mov     edx, eax; ui
0x18004ce4f  call    cs:__imp_SysAllocStringLen
0x18004ce56  nop     dword ptr [rax+rax+00h]
0x18004ce5b  movzx   ecx, byte ptr [rbx+8]
0x18004ce5f  mov     [rbx], rax
0x18004ce62  test    rax, rax
0x18004ce65  jnz     short loc_18004CE6F
0x18004ce67  and     cl, 0FBh
0x18004ce6a  mov     [rbx+8], cl
0x18004ce6d  jmp     short loc_18004CE83
0x18004ce6f  or      cl, 4
0x18004ce72  mov     [rbx+8], cl
0x18004ce75  jmp     short loc_18004CE83
0x18004ce77  mov     [rbx], rax
0x18004ce7a  jmp     short loc_18004CE83
0x18004ce7c  mov     qword ptr [rbx], 0
0x18004ce83  test    byte ptr [rbx+8], 4
0x18004ce87  mov     eax, 0
0x18004ce8c  mov     ebx, 8007000Eh
0x18004ce91  cmovnz  ebx, eax
0x18004ce94  mov     eax, ebx
0x18004ce96  add     rsp, 48h
0x18004ce9a  pop     rdi
0x18004ce9b  pop     rsi
0x18004ce9c  pop     rbp
0x18004ce9d  pop     rbx
0x18004ce9e  retn
0x18004cea0  mov     rdi, [rsp+68h+arg_20]
0x18004cea8  test    byte ptr [rdi+8], 2
0x18004ceac  jz      short loc_18004CEBD
0x18004ceae  mov     rcx, [rdi]; bstrString
0x18004ceb1  call    cs:__imp_SysFreeString
0x18004ceb8  nop     dword ptr [rax+rax+00h]
0x18004cebd  lea     rcx, ?szSelectPrefix@@3QBGB; "select * from "
0x18004cec4  call    cs:__imp_SysAllocString
0x18004cecb  nop     dword ptr [rax+rax+00h]
0x18004ced0  movzx   ecx, byte ptr [rdi+8]
0x18004ced4  mov     [rdi], rax
0x18004ced7  test    rax, rax
0x18004ceda  jnz     short loc_18004CEE1
0x18004cedc  and     cl, 0FBh
0x18004cedf  jmp     short loc_18004CEE4
0x18004cee1  or      cl, 4
0x18004cee4  mov     [rdi+8], cl
0x18004cee7  test    byte ptr [rsi+0B8h], 4
0x18004ceee  jz      loc_18004CFC2
0x18004cef4  mov     rcx, [rsi+0B0h]; pbstr
0x18004cefb  test    rcx, rcx
0x18004cefe  jz      loc_18004CFC2
0x18004cf04  mov     [rsp+68h+arg_0], r12
0x18004cf09  mov     [rsp+68h+var_28], r15
0x18004cf0e  call    cs:__imp_SysStringLen
0x18004cf15  nop     dword ptr [rax+rax+00h]
0x18004cf1a  mov     rcx, [rdi]; pbstr
0x18004cf1d  movsxd  r15, eax
0x18004cf20  test    rcx, rcx
0x18004cf23  jz      short loc_18004CF36
0x18004cf25  call    cs:__imp_SysStringLen
0x18004cf2c  nop     dword ptr [rax+rax+00h]
0x18004cf31  mov     r12d, eax
0x18004cf34  jmp     short loc_18004CF39
0x18004cf36  xor     r12d, r12d
0x18004cf39  lea     edx, [r15+r12]; ui
0x18004cf3d  xor     ecx, ecx; strIn
0x18004cf3f  call    cs:__imp_SysAllocStringLen
0x18004cf46  nop     dword ptr [rax+rax+00h]
0x18004cf4b  mov     rbp, rax
0x18004cf4e  test    rax, rax
0x18004cf51  jnz     short loc_18004CF59
0x18004cf53  and     byte ptr [rdi+8], 0FBh
0x18004cf57  jmp     short loc_18004CFB8
0x18004cf59  movsxd  rax, r12d
0x18004cf5c  mov     [rsp+68h+arg_10], r14
0x18004cf64  lea     r14, [rax+rax]
0x18004cf68  test    r12d, r12d
0x18004cf6b  jle     short loc_18004CF7B
0x18004cf6d  mov     rdx, [rdi]; Src
0x18004cf70  mov     r8, r14; Size
0x18004cf73  mov     rcx, rbp; void *
0x18004cf76  call    memcpy_0
0x18004cf7b  test    byte ptr [rsi+0B8h], 4
0x18004cf82  jz      short loc_18004CF8D
0x18004cf84  mov     rdx, [rsi+0B0h]
0x18004cf8b  jmp     short loc_18004CF8F
0x18004cf8d  xor     edx, edx; Src
0x18004cf8f  mov     r8, r15
0x18004cf92  lea     rcx, [r14+rbp]; void *
0x18004cf96  add     r8, r8; Size
0x18004cf99  call    memcpy_0
0x18004cf9e  mov     rcx, [rdi]; bstrString
0x18004cfa1  call    cs:__imp_SysFreeString
0x18004cfa8  nop     dword ptr [rax+rax+00h]
0x18004cfad  mov     r14, [rsp+68h+arg_10]
0x18004cfb5  mov     [rdi], rbp
0x18004cfb8  mov     r12, [rsp+68h+arg_0]
0x18004cfbd  mov     r15, [rsp+68h+var_28]
0x18004cfc2  test    byte ptr [rdi+8], 4
0x18004cfc6  jnz     short loc_18004CFCD
0x18004cfc8  mov     ebx, 8007000Eh
0x18004cfcd  mov     eax, ebx
0x18004cfcf  add     rsp, 48h
0x18004cfd3  pop     rdi
0x18004cfd4  pop     rsi
0x18004cfd5  pop     rbp
0x18004cfd6  pop     rbx
0x18004cfd7  retn
```
