# _CatDBAddNewRowToHashCatNameTable(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,_CRYPTOAPI_BLOB *,ushort const *)

- ea: `0x18000392c`
- end: `0x180003b71`
- name: `?_CatDBAddNewRowToHashCatNameTable@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEAU_CRYPTOAPI_BLOB@@PEBG@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, struct _CRYPTOAPI_BLOB *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003b80`

## callees

- `0x1800038f0`
- `0x18000392c`
- `0x180003de4`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b50`
- `ESENT!JetUpdate` at `0x180003a76`
- `ESENT!JetUpdate` at `0x180003a76`
- `ESENT!JetSetColumn` at `0x1800039a1`
- `ESENT!JetSetColumn` at `0x1800039a1`
- `ESENT!JetPrepareUpdate` at `0x180003967`
- `ESENT!JetPrepareUpdate` at `0x180003967`

## pseudocode

```c
__int64 __fastcall _CatDBAddNewRowToHashCatNameTable(
        struct _JET_DB_STRUCT *a1,
        struct JET_DB_HASH_TABLE_IDS *a2,
        struct _CRYPTOAPI_BLOB *a3,
        WCHAR *a4)
{
  JET_ERR v8; // ebx
  JET_ERR v9; // ebx
  __int64 v10; // r10
  WCHAR *v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // r8
  bool v15; // zf
  WCHAR *v16; // rcx
  __int64 v17; // r8
  WCHAR *v18; // rax
  __int64 v19; // r9
  int v20; // edi
  JET_ERR v21; // edi
  WCHAR *v23; // rax
  const WCHAR *v24; // rcx
  __int64 v25; // rdx
  WCHAR *v26; // rcx
  DWORD v27; // eax
  unsigned int v28; // edx
  unsigned __int16 *v29; // rcx
  unsigned int v30; // r8d
  DWORD v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  JET_GRBIT grbit; // [rsp+28h] [rbp-260h]
  WCHAR WideCharStr[264]; // [rsp+40h] [rbp-248h] BYREF

  v8 = JetPrepareUpdate(*((_QWORD *)a1 + 1), *(_QWORD *)a2, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v8) )
  {
    v27 = _CatDBMapJetError(v8);
    SetLastError(v27);
    v30 = 4850;
LABEL_27:
    ErrLog_LogError(v29, v28, v30, 0, 0, grbit);
    return 0;
  }
  v9 = JetSetColumn(*((_QWORD *)a1 + 1), *(_QWORD *)a2, *((_DWORD *)a2 + 2), a3->pbData, a3->cbData, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v9) )
  {
    v31 = _CatDBMapJetError(v9);
    SetLastError(v31);
    v30 = 4864;
    goto LABEL_27;
  }
  v10 = 2147483646;
  v11 = WideCharStr;
  v12 = 1;
  v13 = 2147483646;
  v14 = 257;
  do
  {
    if ( !v13 )
      break;
    if ( !*a4 )
      break;
    *v11++ = *a4++;
    --v13;
    --v14;
  }
  while ( v14 );
  v15 = v14 == 0;
  v16 = v11 - 1;
  v17 = 257;
  if ( !v15 )
    v16 = v11;
  v18 = WideCharStr;
  *v16 = 0;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = (257 - v17) & -(__int64)(v17 != 0);
  if ( v17 )
  {
    v23 = &WideCharStr[v19];
    v24 = L"|";
    v25 = 257 - v19;
    if ( 257 != v19 )
    {
      do
      {
        if ( !v10 )
          break;
        if ( !*v24 )
          break;
        *v23++ = *v24++;
        --v10;
        --v25;
      }
      while ( v25 );
    }
    v26 = v23 - 1;
    if ( v25 )
      v26 = v23;
    *v26 = 0;
  }
  v20 = CatHelperSetCatalogListColumn(*((_QWORD *)a1 + 1), *(_QWORD *)a2, *((_DWORD *)a2 + 3), 0, WideCharStr);
  if ( (unsigned int)_CatDBJET_errFailure(v20) )
  {
    v32 = _CatDBMapJetError(v20);
    SetLastError(v32);
    v30 = 4879;
    goto LABEL_27;
  }
  v21 = JetUpdate(*((_QWORD *)a1 + 1), *(_QWORD *)a2, 0, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v21) )
  {
    v33 = _CatDBMapJetError(v21);
    SetLastError(v33);
    v30 = 4890;
    goto LABEL_27;
  }
  return v12;
}

```

## disassembly

```asm
0x18000392c  mov     [rsp+arg_18], rbx
0x180003931  push    rbp
0x180003932  push    rsi
0x180003933  push    rdi
0x180003934  push    r14
0x180003936  push    r15
0x180003938  sub     rsp, 260h
0x18000393f  mov     rax, cs:__security_cookie
0x180003946  xor     rax, rsp
0x180003949  mov     [rsp+288h+var_38], rax
0x180003951  mov     r14, r8
0x180003954  mov     rsi, rdx
0x180003957  mov     rdx, [rdx]; tableid
0x18000395a  mov     rbp, rcx
0x18000395d  mov     rcx, [rcx+8]; sesid
0x180003961  xor     r8d, r8d; prep
0x180003964  mov     rdi, r9
0x180003967  call    cs:__imp_JetPrepareUpdate
0x18000396d  mov     ecx, eax; int
0x18000396f  mov     ebx, eax
0x180003971  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003976  xor     r15d, r15d
0x180003979  test    eax, eax
0x18000397b  jnz     loc_180003B02
0x180003981  mov     eax, [r14]
0x180003984  mov     r9, [r14+8]; pvData
0x180003988  mov     r8d, [rsi+8]; columnid
0x18000398c  mov     rdx, [rsi]; tableid
0x18000398f  mov     rcx, [rbp+8]; sesid
0x180003993  mov     [rsp+288h+psetinfo], r15; psetinfo
0x180003998  mov     [rsp+288h+grbit], r15d; int
0x18000399d  mov     [rsp+288h+cbData], eax; cbData
0x1800039a1  call    cs:__imp_JetSetColumn
0x1800039a7  mov     ecx, eax; int
0x1800039a9  mov     ebx, eax
0x1800039ab  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800039b0  test    eax, eax
0x1800039b2  jnz     loc_180003B19
0x1800039b8  mov     r10d, 7FFFFFFEh
0x1800039be  lea     rax, [rsp+288h+WideCharStr]
0x1800039c3  mov     edx, 101h
0x1800039c8  lea     ebx, [r15+1]
0x1800039cc  mov     ecx, r10d
0x1800039cf  mov     r8d, edx
0x1800039d2  test    rcx, rcx
0x1800039d5  jz      short loc_1800039F5
0x1800039d7  movzx   r9d, word ptr [rdi]
0x1800039db  test    r9w, r9w
0x1800039df  jz      short loc_1800039F5
0x1800039e1  mov     [rax], r9w
0x1800039e5  add     rdi, 2
0x1800039e9  add     rax, 2
0x1800039ed  sub     rcx, rbx
0x1800039f0  sub     r8, rbx
0x1800039f3  jnz     short loc_1800039D2
0x1800039f5  test    r8, r8
0x1800039f8  lea     rcx, [rax-2]
0x1800039fc  mov     r8, rdx
0x1800039ff  cmovnz  rcx, rax
0x180003a03  lea     rax, [rsp+288h+WideCharStr]
0x180003a08  mov     [rcx], r15w
0x180003a0c  cmp     [rax], r15w
0x180003a10  jz      short loc_180003A1B
0x180003a12  add     rax, 2
0x180003a16  sub     r8, rbx
0x180003a19  jnz     short loc_180003A0C
0x180003a1b  mov     rcx, rdx
0x180003a1e  mov     rax, r8
0x180003a21  sub     rcx, r8
0x180003a24  neg     rax
0x180003a27  sbb     r9, r9
0x180003a2a  and     r9, rcx
0x180003a2d  test    r8, r8
0x180003a30  jnz     loc_180003AB6
0x180003a36  mov     r8d, [rsi+0Ch]; columnid
0x180003a3a  lea     rax, [rsp+288h+WideCharStr]
0x180003a3f  mov     rdx, [rsi]; tableid
0x180003a42  xor     r9d, r9d; grbit
0x180003a45  mov     rcx, [rbp+8]; sesid
0x180003a49  mov     qword ptr [rsp+288h+cbData], rax; lpWideCharStr
0x180003a4e  call    ?CatHelperSetCatalogListColumn@@YAJ_K0KKPEBG@Z; CatHelperSetCatalogListColumn(unsigned __int64,unsigned __int64,ulong,ulong,ushort const *)
0x180003a53  mov     ecx, eax; int
0x180003a55  mov     edi, eax
0x180003a57  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003a5c  test    eax, eax
0x180003a5e  jnz     loc_180003B30
0x180003a64  mov     rdx, [rsi]; tableid
0x180003a67  xor     r9d, r9d; cbBookmark
0x180003a6a  mov     rcx, [rbp+8]; sesid
0x180003a6e  xor     r8d, r8d; pvBookmark
0x180003a71  mov     qword ptr [rsp+288h+cbData], r15; pcbActual
0x180003a76  call    cs:__imp_JetUpdate
0x180003a7c  mov     ecx, eax; int
0x180003a7e  mov     edi, eax
0x180003a80  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003a85  test    eax, eax
0x180003a87  jnz     loc_180003B47
0x180003a8d  mov     eax, ebx
0x180003a8f  mov     rcx, [rsp+288h+var_38]
0x180003a97  xor     rcx, rsp; StackCookie
0x180003a9a  call    __security_check_cookie
0x180003a9f  mov     rbx, [rsp+288h+arg_18]
0x180003aa7  add     rsp, 260h
0x180003aae  pop     r15
0x180003ab0  pop     r14
0x180003ab2  pop     rdi
0x180003ab3  pop     rsi
0x180003ab4  pop     rbp
0x180003ab5  retn
0x180003ab6  lea     rax, [rsp+288h+WideCharStr]
0x180003abb  lea     rax, [rax+r9*2]
0x180003abf  lea     rcx, WideCharStr; "|"
0x180003ac6  sub     rdx, r9
0x180003ac9  jz      short loc_180003AEE
0x180003acb  test    r10, r10
0x180003ace  jz      short loc_180003AEE
0x180003ad0  movzx   r8d, word ptr [rcx]
0x180003ad4  test    r8w, r8w
0x180003ad8  jz      short loc_180003AEE
0x180003ada  mov     [rax], r8w
0x180003ade  add     rcx, 2
0x180003ae2  add     rax, 2
0x180003ae6  sub     r10, rbx
0x180003ae9  sub     rdx, rbx
0x180003aec  jnz     short loc_180003ACB
0x180003aee  test    rdx, rdx
0x180003af1  lea     rcx, [rax-2]
0x180003af5  cmovnz  rcx, rax
0x180003af9  mov     [rcx], r15w
0x180003afd  jmp     loc_180003A36
0x180003b02  mov     ecx, ebx; int
0x180003b04  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003b09  mov     ecx, eax; dwErrCode
0x180003b0b  call    cs:__imp_SetLastError
0x180003b11  mov     r8d, 12F2h
0x180003b17  jmp     short loc_180003B5C
0x180003b19  mov     ecx, ebx; int
0x180003b1b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003b20  mov     ecx, eax; dwErrCode
0x180003b22  call    cs:__imp_SetLastError
0x180003b28  mov     r8d, 1300h
0x180003b2e  jmp     short loc_180003B5C
0x180003b30  mov     ecx, edi; int
0x180003b32  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003b37  mov     ecx, eax; dwErrCode
0x180003b39  call    cs:__imp_SetLastError
0x180003b3f  mov     r8d, 130Fh
0x180003b45  jmp     short loc_180003B5C
0x180003b47  mov     ecx, edi; int
0x180003b49  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003b4e  mov     ecx, eax; dwErrCode
0x180003b50  call    cs:__imp_SetLastError
0x180003b56  mov     r8d, 131Ah; unsigned int
0x180003b5c  xor     r9d, r9d; unsigned int
0x180003b5f  mov     [rsp+288h+cbData], r15d; int
0x180003b64  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180003b69  mov     ebx, r15d
0x180003b6c  jmp     loc_180003A8D
```
