# CRdlsDBWID::RemoveRdlsDatabase(void)

- ea: `0x180088850`
- end: `0x180088a29`
- name: `?RemoveRdlsDatabase@CRdlsDBWID@@UEAAKXZ`
- size: `473`
- prototype: `unsigned int __fastcall(CRdlsDBWID *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180077e9c`
- `0x180078be4`
- `0x180086484`
- `0x180086754`
- `0x180086778`
- `0x180088850`
- `0x180088e68`
- `0x180096e04`
- `0x1800a5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180088875`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180088875`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889f3`

## string_xrefs

- `0x180088976`: `CreateOdbcExecutionContext, RemoveRdlsDatabase`
- `0x1800888dd`: `] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; DROP DATABASE[`
- `0x1800889c1`: `pOdbcExecContext->ExecuteSql, RemoveRdlsDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsDBWID::RemoveRdlsDatabase(CRdlsDBWID *this)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  OLECHAR *v6; // rdi
  int v7; // r9d
  int v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // r8
  int v13; // [rsp+28h] [rbp-8h]
  BSTR bstrString; // [rsp+50h] [rbp+20h] BYREF
  struct IOdbcExecutionContext *v15; // [rsp+58h] [rbp+28h] BYREF

  v15 = 0;
  bstrString = 0;
  SysFreeString(0);
  bstrString = 0;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( aIfExistsSelect[v3] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"IF EXISTS(SELECT name FROM sys.databases WHERE name = '", v3);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, *((const unsigned __int16 **)this + 2));
  v4 = -1;
  do
    ++v4;
  while ( aBeginAlterData[v4] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"') BEGIN ALTER DATABASE[", v4);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, *((const unsigned __int16 **)this + 2));
  v5 = -1;
  do
    ++v5;
  while ( aSetSingleUserW[v5] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; DROP DATABASE[", v5);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, *((const unsigned __int16 **)this + 2));
  do
    ++v2;
  while ( aEnd[v2] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"] END", v2);
  v6 = bstrString;
  bstrString = 0;
  v8 = CreateOdbcExecutionContext(*((unsigned __int16 **)this + 4), &v15, 32, v7);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, OLECHAR *))(*(_QWORD *)v15 + 112LL))(v15, v6);
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 11;
      v11 = "pOdbcExecContext->ExecuteSql, RemoveRdlsDatabase";
      goto LABEL_19;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 10;
    v11 = "CreateOdbcExecutionContext, RemoveRdlsDatabase";
LABEL_19:
    v13 = v8;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_c9aedbd3feee3e98c50752067cbb8264_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v11,
      v13);
  }
  if ( v6 )
    SysFreeString(v6);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&bstrString);
  ComPlainSmartPtr<IOdbcExecutionContext>::~ComPlainSmartPtr<IOdbcExecutionContext>(&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180088850  mov     [rsp-18h+arg_10], rbx
0x180088855  mov     [rsp-18h+arg_18], rsi
0x18008885a  push    rbp
0x18008885b  push    rdi
0x18008885c  push    r14
0x18008885e  mov     rbp, rsp
0x180088861  sub     rsp, 30h
0x180088865  mov     rsi, rcx
0x180088868  xor     r14d, r14d
0x18008886b  mov     [rbp+arg_8], r14
0x18008886f  mov     [rbp+bstrString], r14
0x180088873  xor     ecx, ecx; bstrString
0x180088875  call    cs:__imp_SysFreeString
0x18008887c  nop     dword ptr [rax+rax+00h]
0x180088881  mov     [rbp+bstrString], r14
0x180088885  lea     rdx, aIfExistsSelect; "IF EXISTS(SELECT name FROM sys.database"...
0x18008888c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180088890  mov     r8, rbx
0x180088893  inc     r8; int
0x180088896  cmp     [rdx+r8*2], r14w
0x18008889b  jnz     short loc_180088893
0x18008889d  lea     rcx, [rbp+bstrString]; this
0x1800888a1  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800888a6  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800888aa  lea     rcx, [rbp+bstrString]; this
0x1800888ae  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800888b3  lea     rdx, aBeginAlterData; "') BEGIN ALTER DATABASE["
0x1800888ba  mov     r8, rbx
0x1800888bd  inc     r8; int
0x1800888c0  cmp     [rdx+r8*2], r14w
0x1800888c5  jnz     short loc_1800888BD
0x1800888c7  lea     rcx, [rbp+bstrString]; this
0x1800888cb  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800888d0  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800888d4  lea     rcx, [rbp+bstrString]; this
0x1800888d8  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800888dd  lea     rdx, aSetSingleUserW; "] SET SINGLE_USER WITH ROLLBACK IMMEDIA"...
0x1800888e4  mov     r8, rbx
0x1800888e7  inc     r8; int
0x1800888ea  cmp     [rdx+r8*2], r14w
0x1800888ef  jnz     short loc_1800888E7
0x1800888f1  lea     rcx, [rbp+bstrString]; this
0x1800888f5  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800888fa  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800888fe  lea     rcx, [rbp+bstrString]; this
0x180088902  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180088907  lea     rdx, aEnd; "] END"
0x18008890e  inc     rbx
0x180088911  cmp     [rdx+rbx*2], r14w
0x180088916  jnz     short loc_18008890E
0x180088918  mov     r8d, ebx; int
0x18008891b  lea     rcx, [rbp+bstrString]; this
0x18008891f  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180088924  mov     rdi, [rbp+bstrString]
0x180088928  mov     [rbp+bstrString], r14
0x18008892c  mov     r8d, 20h ; ' '; int
0x180088932  lea     rdx, [rbp+arg_8]; struct IOdbcExecutionContext **
0x180088936  mov     rcx, [rsi+20h]; unsigned __int16 *
0x18008893a  call    ?CreateOdbcExecutionContext@@YAJPEAGPEAPEAVIOdbcExecutionContext@@JJ@Z; CreateOdbcExecutionContext(ushort *,IOdbcExecutionContext * *,long,long)
0x18008893f  mov     ebx, eax
0x180088941  test    eax, eax
0x180088943  jns     short loc_18008897F
0x180088945  lea     rcx, WPP_GLOBAL_Control
0x18008894c  mov     rax, cs:WPP_GLOBAL_Control
0x180088953  cmp     rax, rcx
0x180088956  jz      loc_1800889EB
0x18008895c  test    byte ptr [rax+1Ch], 8
0x180088960  jz      loc_1800889EB
0x180088966  cmp     byte ptr [rax+19h], 2
0x18008896a  jb      short loc_1800889EB
0x18008896c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180088971  mov     edx, 0Ah
0x180088976  lea     r8, aCreateodbcexec; "CreateOdbcExecutionContext, RemoveRdlsD"...
0x18008897d  jmp     short loc_1800889C8
0x18008897f  mov     rcx, [rbp+arg_8]
0x180088983  mov     rax, [rcx]
0x180088986  mov     rdx, rdi
0x180088989  mov     rax, [rax+70h]
0x18008898d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088992  mov     ebx, eax
0x180088994  test    eax, eax
0x180088996  jns     short loc_1800889EB
0x180088998  lea     rcx, WPP_GLOBAL_Control
0x18008899f  mov     rax, cs:WPP_GLOBAL_Control
0x1800889a6  cmp     rax, rcx
0x1800889a9  jz      short loc_1800889EB
0x1800889ab  test    byte ptr [rax+1Ch], 8
0x1800889af  jz      short loc_1800889EB
0x1800889b1  cmp     byte ptr [rax+19h], 2
0x1800889b5  jb      short loc_1800889EB
0x1800889b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800889bc  mov     edx, 0Bh
0x1800889c1  lea     r8, aPodbcexecconte_10; "pOdbcExecContext->ExecuteSql, RemoveRdl"...
0x1800889c8  mov     [rsp+30h+var_8], ebx
0x1800889cc  mov     [rsp+30h+var_10], r8
0x1800889d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800889d8  mov     r9d, eax
0x1800889db  lea     r8, WPP_c9aedbd3feee3e98c50752067cbb8264_Traceguids
0x1800889e2  mov     rcx, [rcx+10h]
0x1800889e6  call    WPP_SF_DsD
0x1800889eb  test    rdi, rdi
0x1800889ee  jz      short loc_180088A00
0x1800889f0  mov     rcx, rdi; bstrString
0x1800889f3  call    cs:__imp_SysFreeString
0x1800889fa  nop     dword ptr [rax+rax+00h]
0x1800889ff  nop
0x180088a00  lea     rcx, [rbp+bstrString]; this
0x180088a04  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180088a09  nop
0x180088a0a  lea     rcx, [rbp+arg_8]
0x180088a0e  call    ??1?$ComPlainSmartPtr@VIOdbcExecutionContext@@@@QEAA@XZ; ComPlainSmartPtr<IOdbcExecutionContext>::~ComPlainSmartPtr<IOdbcExecutionContext>(void)
0x180088a13  mov     eax, ebx
0x180088a15  mov     rbx, [rsp+30h+arg_10]
0x180088a1a  mov     rsi, [rsp+30h+arg_18]
0x180088a1f  add     rsp, 30h
0x180088a23  pop     r14
0x180088a25  pop     rdi
0x180088a26  pop     rbp
0x180088a27  retn
```
